---
title: Configurar un canal de SharePoint
description: Este artículo explica cómo configurar el canal de Microsoft SharePoint para procesar las facturas electrónicas entrantes.
author: dkalyuzh
ms.date: 02/09/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.custom:
- "97423"
- intro-internal
ms.assetid: ''
ms.search.region: Global
ms.author: janeaug
ms.search.validFrom: 2020-07-08
ms.dyn365.ops.version: AX 10.0.12
ms.openlocfilehash: 89538adde4d14212fb0deccad05f828d146f16db
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/03/2022
ms.locfileid: "8910052"
---
# <a name="configure-a-sharepoint-channel"></a>Configurar un canal de SharePoint

[!include [banner](../includes/banner.md)]

Como requisito previo para configurar un canal de Microsoft SharePoint para procesar documentos entrantes, complete los pasos descritos en [ Configurar una conexión de SharePoint](e-invoicing-create-sharepoint-connection.md).

A continuación, puede utilizar el canal de SharePoint para importar facturas electrónicas de archivos que están almacenados en sus carpetas de SharePoint.

1. En su sitio de SharePoint, cree las siguientes carpetas:

    - **Carpeta principal**: la carpeta desde la que el servicio procesará los archivos.
    - **Carpeta de archivo**: la carpeta donde se almacenarán los archivos procesados.
    - **Carpeta de errores**: la carpeta a la que el sistema moverá los archivos si falla el procesamiento.

2. En Regulatory Configuration Service (RCS), seleccione la característica de Facturación electrónico que ha creado. Asegúrese de seleccionar la versión con un estado de **Borrador**.
3. En la pestaña **Configuraciones**, seleccione **Agregar**.
4. En el cuadro de diálogo **Crear configuración de características**, en el grupo del campo **Nuevo**, seleccione la opción **Configuración personalizada**.
5. En el grupo del campo **Tipo de configuración**, seleccione la opción **Canal de datos**.
6. En el campo **Seleccionar canal de datos**, seleccione **Carpeta de SharePoint**.
7. Seleccione **Crear**.
8. Seleccione la línea que ha creado y, a continuación, seleccione **Editar**.
9. En la pestaña **Canal de datos**, en la sección **Parámetros**, establezca los siguientes campos obligatorios.

    | Campo                 | Description |
    |-----------------------|-------------|
    | Canal de datos          | Introduzca un nombre único para identificar el canal de datos. El nombre puede tener un máximo de 10 caracteres. Se hará referencia a él en las reglas de aplicabilidad y en las aplicaciones conectadas durante el proceso de comunicación. |
    | Dirección de SharePoint    | Escriba la dirección URL de SharePoint. Por ejemplo, escriba `<domain>.sharepoint.com`. |
    | Id. de aplicación        | Escriba el nombre del secreto de Azure Key Vault que contiene el id. de la cuenta de usuario de SharePoint. Este secreto debe crearse en Key Vault y configurarse en su entorno de servicio. El valor es el valor **Id. de la aplicación (cliente)** de [Configurar conexión de SharePoint](e-invoicing-create-sharepoint-connection.md). |
    | Secreto de la aplicación    | Escriba el nombre del secreto de Key Vault que contiene la contraseña de la cuenta de usuario de SharePoint. El valor es el valor **Secreto de registro de aplicación** de [Configurar conexión de SharePoint](e-invoicing-create-sharepoint-connection.md). |
    | Nombre del sitio             | Permite escribir el nombre del sitio de SharePoint. |
    | Nombre de la biblioteca de documentos | Introduzca el nombre de la biblioteca de documentos de SharePoint. |
    | Tiempo de espera               | Escriba el tiempo máximo, en milisegundos (ms), durante el cual el sistema debe esperar una respuesta. El valor predeterminado es 10 000 ms (10 segundos). |
    | Carpeta principal           | Especifique el origen de la importación de archivos desde el que el servicio debe procesar los archivos. |
    | Carpeta de almacenamiento        | Especifique la carpeta donde se deben almacenar los archivos procesados. |
    | Carpeta de errores          | Especifique la carpeta a la que el sistema moverá los archivos si falla el procesamiento. |
    | Tamaño máximo de archivo         | Introduzca el tamaño máximo, en bytes, de un solo archivo que se procesa. El valor predeterminado es 20 000 000 bytes. |
    | Número máximo de archivos      | Introduzca el número máximo de archivos que se pueden procesar para una única acción. Si no desea limitar el número de archivos, establezca el valor en **0** (cero). |
    | Filtro de archivos           | Introduzca una cadena para filtrar por nombre de archivo. Este campo es opcional. Se admite una máscara simple como **\*smth\* .ext**, donde cada asterisco (\*) representa cero o más ocurrencias de cualquier carácter. Por ejemplo, introduzca **\*.pdf** para configurar el canal para leer archivos PDF. |
    | Nombre de archivo personalizado      | Introduzca el nombre de archivo personalizado del cliente. |

10. En la pestaña **Reglas de aplicabilidad**, revise y actualice los criterios según sea necesario. El valor del campo **Canal** debe ser igual al valor que introdujo en el campo **Canal de datos** en el paso anterior.
11. Seleccione **Guardar** y cierre la página.
