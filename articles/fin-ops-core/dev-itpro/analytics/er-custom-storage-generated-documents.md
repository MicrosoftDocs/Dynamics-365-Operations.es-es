---
title: Especifique una ubicación de almacenamiento personalizada para los documentos generados
description: Este tema explica cómo ampliar la lista de ubicaciones de almacenamiento para los documentos que los formatos de informes electrónicos (ER) generan.
author: NickSelin
manager: AnnBe
ms.date: 02/22/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2019-3-31
ms.dyn365.ops.version: 10
ms.openlocfilehash: 45a2335d7a661ddc1d8907c56ae8193387f44e26
ms.sourcegitcommit: 4e62c22b53693c201baa646a8f047edb5a0a2747
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/07/2020
ms.locfileid: "3030875"
---
# <a name="specify-a-custom-storage-location-for-generated-documents"></a>Especifique una ubicación de almacenamiento personalizada para los documentos generados

[!include[banner](../includes/banner.md)]

La interfaz de programación de aplicaciones (API) del marco de informes electrónicos (ER) permite ampliar la lista de ubicaciones de almacenamiento para los documentos que los formatos de ER generan. Este tema proporciona una visión general de las principales tareas que debe completar para agregar una ubicación de almacenamiento personalizada.

## <a name="prerequisites"></a>Requisitos previos

Debe implementar una topología que admita una compilación continua. (Para obtener más información, consulte [Implementar topologías que admiten la automatización continua de la compilación y la prueba](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/perf-test/continuous-build-test-automation)). Debe tener acceso a esta topología para uno de los roles siguientes:

- Desarrollador de informes electrónicos
- Consultor funcional de informes electrónicos
- Administrador del sistema

También debe tener acceso al entorno de desarrollo para esta topología.

## <a name="create-or-import-an-er-format-configuration"></a>Creación o importación de una configuración del formato de ER

En la topología actual, [cree un nuevo formato de ER](tasks/er-format-configuration-2016-11.md) para generar documentos para los que pretende agregar una ubicación de almacenamiento personalizada. O bien, [importe un formato de ER existente en esta topología](general-electronic-reporting-manage-configuration-lifecycle.md).

![Página de diseñador de formato](media/er-extend-file-storages-format.png)

> [!IMPORTANT]
> El formato del ER que cree o importe debe contener al menos uno de los siguientes elementos de formato:
>
> - Archivo
> - Carpeta
> - Combinación
> - Archivo adjunto

## <a name="create-a-new-document-type"></a>Crear un tipo de documento nuevo

Para especificar cómo se distribuyen los documentos que un formato de ER genera, debe configurar [Informes electrónicos (ER)](electronic-reporting-destinations.md). En cada destino de ER que se configure para almacenar documentos generados como archivos, debe especificar un tipo de documento del marco de la gestión de documentos. Los distintos tipos de documentos se pueden usar para distribuir los documentos que distintos formatos de ER generan.

1. Agregue un nuevo [tipo de documento](https://docs.microsoft.com/dynamics365/fin-ops-core/fin-ops/organization-administration/configure-document-management) para el formato de ER que ha creado o importado anteriormente. En la ilustración siguiente, el tipo de documento es **FileX**.
2. Para distinguir este tipo de documento de otros tipos de documentos, incluya una palabra clave específica en su nombre. Por ejemplo, en la ilustración siguiente, el nombre es **Carpeta (LOCAL)**.
3. En el campo **Clase**, especifique **Asociar archivo**.
4. En el campo **Grupo**, especifique **archivo**.

![Página de tipos de documento](media/er-extend-file-storages-document-type.png)

> [!NOTE]
> Los tipos de documento son específicos de la empresa. Para usar un formato de ER con un destino configurado en varias empresas, debe configurar un tipo de documento independiente en cada empresa.

## <a name="review-source-code"></a>Revisar código fuente

Revise el código del método **insertFile()** de la clase **ERDocuManagement**. Observe que el evento **AttachingFile()** está activado mientras que el archivo generado está vinculado a un registro.

```xpp
/// <summary>
/// Inserts file as attachment in Document Management.
/// </summary>
/// <param name = "_owner">A record as the attachment owner.</param>
/// <param name = "_stream">The file stream.</param>
/// <param name = "_filePath">The file path with name.</param>
/// <param name = "_attachmentName">The name of file attachment.</param>
/// <returns>The reference to inserted file.</returns>
[Hookable(false)]
public DocuRef insertFile(
    Common _owner, 
    System.IO.Stream _stream, 
    str _filePath, 
    str _attachmentName, 
    DocuTypeId _docuTypeId)
{
    DocuRef docuRef;
    if (_stream)
    {
        DocuType::createDefaults();
        if (!this.isDocuTypeValid(_docuTypeId))
        {
            throw error(strFmt("@ElectronicReporting:DocuTypeIsNotValid", _docuTypeId));
        }
        var args = ERDocuManagementAttachingFileEventArgs::construct(_owner, _stream, _filePath, _attachmentName, _docuTypeId);
        ERDocuManagementEvents::onAttachingFile(args);
        if (args.isHandled())
        {
            docuRef = args.getDocuRef();
        }
        else
        {
            docuRef = this.attachFile(_owner, _stream, _filePath, _attachmentName, _docuTypeId);
        }
    }
    return docuRef;
}
```

Se activa el evento **AttachingFile()** cuando se procesan los destinos de ER siguientes:

- **Archivo** Cuando se usa este destino, un registro nuevo para el formato de ER que se ejecuta se crea en la tabla de ERFormatMappingRunJobTable. El campo **Archivado** de este registro se establece en **Falso**. Si el formato de ER se ejecuta correctamente, el documento generado se vincula a este registro, y se activa el evento **AttachingFile()**. El tipo de documento seleccionado en este destino de ER determina la ubicación de almacenamiento del archivo adjunto (almacenamiento de Microsoft Azure o una carpeta de Microsoft SharePoint).
- **Archivo de trabajo** Cuando se usa este destino, un registro nuevo para el formato de ER que se ejecuta se crea en la tabla de ERFormatMappingRunJobTable. El campo **Archivado** de este registro se establece en **True**. Si el formato de ER se ejecuta correctamente, el documento generado se vincula a este registro, y se activa el evento **AttachingFile()**. El tipo de documento que se configura en los parámetros de ER determina la ubicación de almacenamiento del archivo adjunto (Azure Storage o una carpeta de SharePoint).

![Página de parámetros de informes electrónicos](media/er-extend-file-storages-parameters.png)

## <a name="configure-an-er-destination"></a>Configurar un destino de ER

1. Configure el destino archivado de uno de los elementos anteriormente mencionados (archivo, carpeta, combinación o datos adjuntos) del formato de ER que ha creado o importado. Para obtener instrucciones, consulte [Destinación de configuración de ER](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/analytics/tasks/er-destinations-2016-11).
2. Utilice el tipo de documento que ha agregado anteriormente para el destino configurado. (Para el ejemplo en este tema, el tipo de documento es **FileX**.)

![Cuadro de diálogo Configuración de destino](media/er-extend-file-storages-destination.png)

## <a name="modify-source-code"></a>Modificación de código de origen

1. Agregue una nueva clase al proyecto de Microsoft Visual Studio , y escriba el código para suscribirse al evento **AttachingFile()** que se menciona anteriormente. (Para obtener más información sobre el patrón de extensibilidad usado, consulte [Responder mediante EventHandlerResult](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/extensibility/respond-event-handler-result).) Por ejemplo, en la nueva clase, escriba código que realice las acciones siguientes:

    1. Almacenar los archivos generados en una carpeta del sistema de archivos local del servidor que ejecuta el servicio Application Object Server (AOS).
    2. Almacenar estos archivos generados solo si se utiliza el nuevo tipo de documento (por ejemplo, el tipo **FileX** que tiene la palabra clave “(LOCAL)” en su nombre) mientras se asocia un archivo al registro en el registro de trabajo de la ejecución de ER.

    ```xpp
    class ERDocuSubscriptionSample
    {
        void new()
        {
        }
        [SubscribesTo(classStr(ERDocuManagementEvents), 
        staticDelegateStr(ERDocuManagementEvents, 
        attachingFile))]
        public static void ERDocuManagementEvents_attachingFile(ERDocuManagementAttachingFileEventArgs _args)
        {
            if (!_args.isHandled())
            {
                DocuType docuType = DocuType::find(_args.getDocuTypeId());
                if (strContains(docuType.Name, '(LOCAL)'))
                {
                    _args.markAsHandled();
                    var stream = _args.getStream();
                    if (stream.CanSeek)
                    {
                        stream.Seek(0, System.IO.SeekOrigin::Begin);
                    }
                    using (var localStream = System.IO.File::OpenWrite(@'c:\0\' + _args.getAttachmentName()))
                    {
                        stream.CopyTo(localStream);
                    }
                }
            }
        }
    }
    ```

2. Reconstruir su proyecto.

## <a name="run-the-er-format-that-you-created-or-imported"></a>Ejecutar el formato de ER que ha creado o importado.

1. Ejecutar el formato de ER que ha creado o importado.
2. Vaya a **Administración de la organización \> Informes electrónicos \> Trabajos de informes electrónicos**. Encuentre el registro creado para este trabajo de ejecución, y que contenga el archivo generado vinculado a él.
3. Explore la carpeta **C:\\0** local para encontrar el mismo archivo generado.

## <a name="additional-resources"></a>Recursos adicionales

- [Destinos de informes electrónicos (ER)](electronic-reporting-destinations.md)
- [Página de inicio de extensibilidad](../extensibility/extensibility-home-page.md)
