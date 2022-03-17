---
title: Configurar una conexión de SharePoint
description: En este tema se explica cómo configurar una conexión para que Facturación Electrónica pueda acceder a un sitio de Microsoft SharePoint.
author: dkalyuzh
ms.date: 12/15/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: dkalyuzh
ms.search.validFrom: ''
ms.dyn365.ops.version: ''
ms.openlocfilehash: 6b9fffc1f3525e69792517dd1c6ebdcfbe5a74d2
ms.sourcegitcommit: ffdb6794746ffe5461f9dcf34ed8e64976d22d2d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/02/2022
ms.locfileid: "8371725"
---
# <a name="configure-a-sharepoint-connection"></a>Configurar una conexión de SharePoint

[!include [banner](../includes/banner.md)]

El servicio de Facturación electrónica puede leer archivos de carpetas de Microsoft SharePoint y cargar archivos a SharePoint. Para garantizar que Facturación electrónica pueda obtener acceso a un sitio de SharePoint, debe proporcionar las credenciales del sitio al servicio de Facturación electrónica. Además, para garantizar que las credenciales se almacenan de forma segura, no las proporcione directamente. En su lugar, guárdelas en un almacén de claves de Azure y proporcione un secreto de Azure Key Vault.

## <a name="grant-access-to-a-sharepoint-folder"></a>Conceder acceso a una carpeta de SharePoint

1. Cree un registro de aplicación en el inquilino donde está instalado Regulatory Configuration Service (RCS).

    1. Inicie sesión en el [portal de Azure](https://portal.azure.com/).
    2. Vaya a **Registros de aplicación**.
    3. Seleccione **Nuevo registro**.
    4. Escriba un nombre, como **Aplicación de SharePoint para Facturación electrónica**, y complete el registro.
    5. Seleccione el registro de la nueva aplicación.
    6. En la pestaña **Autenticación**, habilite la opción **Permitir flujos de clientes públicos**.
    4. En la pestaña **Certificados y secretos**, seleccione **Nuevo secreto de cliente** para crear un secreto de cliente.
    5. Copie el valor del secreto que se creó.

    Siga estas directrices.

    - No utilice el mismo registro de aplicación para diferentes servicios.
    - Siga las [recomendaciones de directiva de contraseñas](/microsoft-365/admin/misc/password-policy-recommendations?view=o365-worldwide).
    - Configure la rotación de contraseñas. Durante la rotación, cree un nuevo secreto de cliente para el registro de la aplicación, actualice el almacén de claves y luego elimine el secreto anterior.

2. Guarde los valores de **Secreto de registro de la aplicación** e **Id. de la aplicación (cliente)** como dos nuevos secretos en el almacén de claves en la configuración de su entorno de Facturación electrónica.
3. Agregue los secretos que ha creado en los parámetros de Key Vault en la configuración de su entorno de Facturación electrónica en RCS.
4. En Azure Portal, conceda acceso a SharePoint. Este paso se debe completar por el administrador de inquilinos.

    1. Seleccione el registro de aplicación que ha creado.
    2. En la pestaña **Permisos de API**, seleccione **Agregar un permiso**.
    3. Seleccione **Gráfico de Microsoft (permisos de la aplicación)** \> **Sites.Selected**.
    4. Seleccione **Conceder consentimiento de administrador para \<user&nbsp;name\>**.
    5. Revise el campo **Estado** para asegurarse de que se conceden permisos.

        ![Permisos concedidos en la pestaña de permisos de la API.](media/configured-permissions.jpg)

    6. Abra [Explorador de gráficos - Microsoft Graph](https://developer.microsoft.com/graph/graph-explorer) e inicie sesión.
    7. En el panel izquierdo, en la pestaña **Consultas de ejemplo**, debajo de **Sitios de SharePoint**, seleccione **obtener el sitio de SharePoint basado en la ruta relativa del sitio**.
    8. Rellene los parámetros **\{nombre de host\}** y **\{ruta relativa al servidor\}**. Por ejemplo, complete `<domain>.sharepoint.com` para **\{nombre de host\}** y `sites/<siteName>` para **\{server-relative-path\}**.

        > [!NOTE]
        > Para el sitio web predeterminado, deje el parámetro **\{server-relative-path\}** en blanco.

    9. Seleccione **Ejecutar consulta** y guarde el resultado.
    10. Configure la siguiente consulta.

        `POST https://graph.microsoft.com/v1.0/sites/{site-id}/permissions`

        En esta consulta, **\{site-id\}** es el valor del nodo **id.** de la respuesta de consulta anterior.

        Este es el cuerpo de la solicitud.

        ```json
        {
            "roles": [
                "read",
                "write"
            ],
            "grantedToIdentities": [
                {
                    "application": {
                        "id": "{app-id}",
                        "displayName": "{app-name}"
                    }
                }
            ]
        }
        ```

        En este cuerpo de solicitud, **\{app-id\}** es el valor de **Id. de aplicación (cliente)**, y **\{app-name\}** es el valor del **Nombre de la aplicación**.

        ![Consulta POST.](media/app-id-query.jpg)

    11. En la pestaña **Modificar permisos**, seleccione **Abrir el panel de permisos** y luego seleccione **Sitios** \> **Sites.FullControl.All** \> **Consentimiento**.
    12. Seleccione **Editar consulta**.

El servicio de Facturación electrónica ya tiene acceso a su sitio de SharePoint.
