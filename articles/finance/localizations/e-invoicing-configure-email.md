---
title: Configurar un canal de correo electrónico
description: Este artículo explica cómo configurar un canal de correo electrónico para recibir facturas electrónicas.
author: dkalyuzh
ms.date: 02/09/2022
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
ms.openlocfilehash: 9227b032ffe896ad6a67962e5047fd797a883ae1
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/03/2022
ms.locfileid: "8902396"
---
# <a name="configure-an-email-channel"></a>Configurar un canal de correo electrónico

[!include [banner](../includes/banner.md)]

Si la característica Facturación electrónica que creó importa facturas electrónicas de proveedores de archivos adjuntos que se reciben por correo electrónico, debe configurar un canal de cuenta de correo electrónico.

1. En Regulatory Configuration Service (RCS), seleccione la característica de Facturación electrónico que ha creado. Asegúrese de seleccionar la versión con un estado de **Borrador**.
2. En la pestaña **Configuraciones**, seleccione **Agregar**.
3. En el cuadro de diálogo **Crear configuración de características**, en el grupo del campo **Nuevo**, seleccione la opción **Configuración personalizada**.
4. En el grupo del campo **Tipo de configuración**, seleccione la opción **Canal de datos**.
5. En el campo **Seleccionar canal de datos**, introduzca **Correo electrónico entrante**.
6. Seleccione **Crear**.
7. Seleccione la línea que ha creado y, a continuación, seleccione **Editar**.
8. En la pestaña **Canal de datos**, en la sección **Parámetros**, establezca los siguientes campos obligatorios.

    | Campo                | Description |
    |----------------------|-------------|
    | Canal de datos         | Introduzca un nombre único para identificar el canal de datos. El nombre puede tener un máximo de 10 caracteres. Se hará referencia a él en las reglas de aplicabilidad y en las aplicaciones conectadas durante el proceso de comunicación. |
    | Dirección del servidor       | Introduzca la dirección del servidor del proveedor de la cuenta de correo electrónico. Por ejemplo, la dirección del servidor para el proveedor `https://outlook.live.com` es imap-mail.outlook.com. |
    | Puerto del servidor          | Introduzca el número del puerto que utiliza el proveedor de la cuenta de correo electrónico. Por ejemplo, el puerto del servidor para `https://outlook.live.com` es 993. |
    | Secreto de nombre de usuario     | Escriba el nombre del secreto de Azure Key Vault de Microsoft Azure que contiene el id. de la cuenta de usuario de correo electrónico. Este secreto debe crearse en Key Vault y configurarse en su entorno de servicio. |
    | Secreto de contraseña de usuario | Escriba el nombre del secreto de Key Vault que contiene la contraseña de la cuenta de usuario de correo electrónico. |
    | Tiempo de espera              | El límite de tiempo máximo, en milisegundos (ms), durante el cual el sistema debe esperar una respuesta. El valor predeterminado es 10 000 ms (10 segundos). |
    | Carpeta principal          | Especifique el origen de la importación de correo electrónico, o la carpeta, desde el que el servicio debe procesar los archivos. |
    | Carpeta de almacenamiento       | Especifique la carpeta donde se deben almacenar los correos electrónicos procesados. Si no especifica esta carpeta, el sistema la creará automáticamente. |
    | Carpeta de errores         | Especifique la carpeta a la que el sistema moverá los correos electrónicos si falla el procesamiento. Si no especifica esta carpeta, el sistema la creará automáticamente. |
    | Tamaño máximo del mensaje     | Introduzca el tamaño máximo, en bytes, de un solo mensaje que se procesa. El valor predeterminado es 20 000 000 bytes. |
    | Número máximo de mensajes   | Introduzca el número máximo de mensajes que se pueden procesar para una única acción. Si no desea limitar el número de mensajes, establezca el valor en **0** (cero). |
    | Filtro De          | Introduzca una cadena para filtrar por dirección de remitente. Solo se procesarán los correos electrónicos en los que la dirección del remitente coincida con el filtro. Este campo es opcional. Para especificar varias direcciones de remitente, utilice puntos y comas (;) como separadores. |
    | Filtro de asunto       | Introduzca una cadena para filtrar por asunto. Solo se procesará el asunto que coincida con el filtro. Este campo es opcional. Se admite una máscara simple como **\*smth\* .ext**, donde cada asterisco (\*) representa cero o más ocurrencias de cualquier carácter. |
    | Filtro de fecha          | Especifique una fecha para definir la antigüedad máxima, en días, de los mensajes que se procesan. Este campo es opcional. El valor predeterminado es de 30 días. |
    | Modo de procesamiento      | <p>Seleccione una de las siguientes opciones para especificar si todos los archivos adjuntos de un correo electrónico se pueden procesar juntos o si cada archivo adjunto se debe procesar por separado:</p><ul><li><b>Por archivo adjunto</b>: se creará un nuevo documento electrónico para cada archivo adjunto en el correo electrónico. Por ejemplo, si un correo electrónico incluye varios archivos que contienen datos de factura electrónica, cada archivo se considerará una nueva factura electrónica en el sistema.</li><li><b>Por correo electrónico</b> : un archivo adjunto se considerará archivo adjunto base y se creará una factura electrónica en el sistema. Otros archivos adjuntos se pueden utilizar como archivos auxiliares.</li></ul> |

9. En la sección **Filtro de archivos adjuntos**, agregue la información de filtrado de archivos. Solo se procesarán los adjuntos que satisfacen el filtro definido. Por ejemplo, **\*.xml** filtrará los archivos adjuntos que tengan la extensión de nombre de archivo .xml. El nombre del archivo adjunto se utiliza en Dynamics 365 Finance o Dynamics 365 Supply Chain Management durante la instalación.

    - Si establece el campo **Modo de procesamiento** en **Por correo electrónico** en el paso anterior, puede agregar varios filtros aquí. El nombre identificará el documento específico.
    - Si establece el **Modo de procesamiento** en **Por archivo adjunto**, solo puede agregar un filtro.

10. En la pestaña **Reglas de aplicabilidad**, revise y actualice los criterios según sea necesario. El valor del campo **Canal** debe ser igual al valor que introdujo en el campo **Canal de datos** en el paso 8.
11. Seleccione **Guardar** y cierre la página.
