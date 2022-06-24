---
title: Entornos de servicio
description: Este artículo brinda información acerca de los entornos de servicio para Facturación electrónica y explica cómo configurarlos.
author: dkalyuzh
ms.date: 02/28/2022
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
ms.openlocfilehash: 8c743c5b2fbc7dcc3ae04fa4d7ca0e65de6c2507
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/03/2022
ms.locfileid: "8901258"
---
# <a name="service-environments"></a>Entornos de servicio

[!include [banner](../includes/banner.md)]

Los entornos de servicio son particiones lógicas que se crean para respaldar las características de globalización y los documentos correspondientes que se procesan en el servicio de Facturación electrónica. Los secretos de seguridad y los certificados digitales, así como los permisos de acceso (gobernanza), deben configurarse en el nivel del entorno de servicio.

Puede crear tantos entornos de servicio como necesite. Todos los entornos de servicio que crea son independientes entre sí. Como procedimiento recomendado, le recomendamos que cree al menos dos entornos de servicio:

- Un entorno para los propósitos principales de desarrollo y validación. Este entorno suele ser un entorno de pruebas de aceptación de usuario (UAT).
- Un entorno para fines de producción. Este entorno suele ser un entorno de producción.

Este tipo de partición ayuda a garantizar que los procesos de facturación electrónica se validen y personalicen en el espacio aislado antes de pasar a producción.

Los entornos de servicio deben crearse y mantenerse en Regulatory Configuration Service (RCS). A continuación, cuando estén listos, deben publicarse en el servicio de Facturación electrónica. El proceso de publicación envía los parámetros del entorno de servicio desde la instancia de RCS al servicio de Facturación Electrónica.

Si no completa el proceso de publicación después de crear un nuevo entorno de servicio o ajustar un entorno de servicio existente (por ejemplo, agregando o eliminando usuarios o secretos de Key Vault de Microsoft Azure), los cambios no serán efectivos. A los entornos publicados solo se puede obtener acceso mediante Dynamics 365 Finance o Dynamics 365 Supply Chain Management.

## <a name="service-environment-statuses"></a>Estados de entornos de servicio

Los entornos de servicio se pueden gestionar a través de su estado. Puede ver el estado de un entorno en la página **Entornos de servicio**. Están disponibles los siguientes estados:

- **No publicado**: se ha creado el entorno, pero aún no se ha publicado.
- **Publicado**: se ha publicado el entorno en el servicio de Facturación electrónica.
- **Cambiado**: se han cambiado los atributos de un entorno publicado, pero los cambios aún no se han publicado.

## <a name="users"></a>Usuarios

Cada entorno de servicio debe enumerar los usuarios que pueden conectarse a Facturación electrónica desde Finance o Supply Chain Management.

## <a name="applications"></a>Aplicaciones

En algunos escenarios, es posible que las aplicaciones que no sean Finance o Supply Chain Management deban conectarse al servicio de Facturación electrónica para enviar documentos electrónicos para su posterior procesamiento o para recuperar información como el estado del envío de un documento. En estos escenarios, la aplicación debe estar definida en la lista de aplicaciones. De esta forma, tendrá acceso al servicio de Facturación Electrónica. La aplicación también debe estar registrada como aplicación en Azure Active Directory (Azure AD) y se debe utilizar el id. de objeto para identificarlo. 

Debido a que Microsoft requiere un alto nivel de control de seguridad sobre las aplicaciones que pueden conectarse al servicio de Facturación electrónica, debe ponerse en contacto con Microsoft en <DGXRegulatoryservicesengineering@service.microsoft.com> y proporcionar los siguientes detalles de su aplicación:

- Id. de suscriptor de Azure AD
- Id. de entorno de Lifecycle Services (LCS) de Microsoft Dynamics
- Id. de aplicación (id. cliente)
- Id. de objeto
- Justificación y descripción de alto nivel de la solicitud

Microsoft evaluará la solicitud e inscribirá la aplicación en el registro de seguridad para garantizar que pueda operar con Facturación Electrónica.

## <a name="number-sequences"></a>Secuencias numéricas

Si sus escenarios requieren secuencias numéricas (por ejemplo, en los nombres de archivos), puede usar secuencias numéricas definidas para un entorno específico, pero se pueden usar en características de globalización o para una característica de globalización específica. Después de definir una secuencia numérica, puede usarla en variables y canalizaciones de procesamiento. Para realizar un seguimiento de su uso, en la página **Secuencias numéricas**, busque un valor de **Actual** para el parámetro **En uso**.

### <a name="working-with-number-sequences"></a>Trabajar con secuencias numéricas
En la página **Secuencias numéricas**: 

- Seleccione **Nuevo** para crear una secuencia numérica. Especifique un nombre y una descripción. 
- Seleccione **Eliminar** para eliminar una secuencia numérica si ya no se usa.
- No tiene que seleccionar **Publicar** en el Panel de acciones para publicar los cambios en una secuencia numérica. La actualización se realiza automáticamente.

## <a name="create-a-key-vault-reference"></a>Crear una referencia de Key Vault

1. Inicie sesión en su cuenta de RCS.
2. En el espacio de trabajo **Características de globalización**, en la sección **Ambiente**, seleccione el mosaico **Facturación electrónica**.
3. En la página **Configuración de entornos**, en el Panel de acciones, seleccione **Entornos de servicio**.
4. En la página **Entornos de servicio**, en el Panel de acciones, seleccione **Parámetros de Key Vault**.
5. En la página **Parámetros de Key Vault** seleccione **Nuevo** para crear una referencia de Key Vault.
6. En el campo **Nombre**, especifique el nombre de la referencia de Key Vault.
7. En el campo **Descripción**, escriba una descripción.
8. En el campo **URI de Key Vault**, pegue el URI de Key Vault desde el almacén de claves (`https://<your key vault>.vault.azure.net/`). Para más información, consulte [Crear un Azure Key Vault en Azure Portal](e-invoicing-create-azure-key-vault-azure-portal.md).
9. Seleccione **Guardar**.
    
## <a name="create-a-secret-for-the-storage-account-secret-token"></a>Crear un secreto para el token de secreto de la cuenta de almacenamiento

1. En la página **Parámetros de Key Vault**, seleccione la referencia de Key Vault que ha creado en el procedimiento anterior y, a continuación, en la sección **Certificados**, seleccione **Agregar**.
2. En el campo **Nombre**, introduzca el nombre del secreto de la cuenta de almacenamiento. Este nombre debe coincidir con el nombre del secreto de Key Vault que contiene el token de firma de acceso compartido (SAS) de almacenamiento. Para obtener más información, consulte [Crear una cuenta de Azure Storage en Azure Portal](e-invoicing-create-azure-storage-account-azure-portal.md). 
3. En el campo **Descripción**, escriba una descripción.
4. En el campo **Tipo**, seleccione **Secreto**.
5. Seleccione **Guardar**.
    
## <a name="create-a-service-environment"></a>Crear un entorno de servicio

1. En la página **Entornos de servicio**, seleccione **Nuevo** para crear un entorno de servicio.
2. En el campo **Nombre**, especifique el nombre del entorno de Facturación electrónica.
3. En el campo **Descripción**, escriba una descripción.
4. En el campo **Secreto de token SAS de almacenamiento**, seleccione el nombre del secreto de cuenta de almacenamiento que se debe utilizar para autenticar el acceso a la cuenta de almacenamiento.
5. En la sección **Usuarios**, seleccione **Agregar** para agregar un usuario que puede enviar facturas electrónicas a través del entorno y conectarse a la cuenta de almacenamiento.
6. En el campo **Id. de usuario**, introduzca el alias del usuario. 
7. En el campo **Correo electrónico**, escriba la dirección de correo electrónico del usuario.
8. Seleccione **Guardar**.
9. En el panel de acciones, seleccione **Publicar** para publicar el entorno en el servicio de Facturación electrónica. Compruebe que el valor del campo **Estado** se cambia a **Publicado**.
