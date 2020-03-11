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
ms.openlocfilehash: 98c08ae2ab4c7cceadb6caaf98fa431e56be4b97
ms.sourcegitcommit: 3c1eb3d89c6ab9bd70b806ca42ef9df74cf850bc
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/12/2020
ms.locfileid: "3042743"
---
# <a name="specify-a-custom-storage-location-for-generated-documents"></a><span data-ttu-id="47ba0-103">Especifique una ubicación de almacenamiento personalizada para los documentos generados</span><span class="sxs-lookup"><span data-stu-id="47ba0-103">Specify a custom storage location for generated documents</span></span>

[!include[banner](../includes/banner.md)]

<span data-ttu-id="47ba0-104">La interfaz de programación de aplicaciones (API) del marco de informes electrónicos (ER) permite ampliar la lista de ubicaciones de almacenamiento para los documentos que los formatos de ER generan.</span><span class="sxs-lookup"><span data-stu-id="47ba0-104">The application programming interface (API) of the Electronic reporting (ER) framework lets you extend the list of storage locations for documents that ER formats generate.</span></span> <span data-ttu-id="47ba0-105">Este tema proporciona una visión general de las principales tareas que debe completar para agregar una ubicación de almacenamiento personalizada.</span><span class="sxs-lookup"><span data-stu-id="47ba0-105">This topic includes an overview of the main tasks that you must complete to add a custom storage location.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="47ba0-106">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="47ba0-106">Prerequisites</span></span>

<span data-ttu-id="47ba0-107">Debe implementar una topología que admita una compilación continua.</span><span class="sxs-lookup"><span data-stu-id="47ba0-107">You must deploy a topology that supports continuous build.</span></span> <span data-ttu-id="47ba0-108">(Para obtener más información, consulte [Implementar topologías que admiten la automatización continua de la compilación y la prueba](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/perf-test/continuous-build-test-automation)). Debe tener acceso a esta topología para uno de los roles siguientes:</span><span class="sxs-lookup"><span data-stu-id="47ba0-108">(For more information, see [Deploy topologies that support continuous build and test automation](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/perf-test/continuous-build-test-automation).) You must have access to this topology for one of the following roles:</span></span>

- <span data-ttu-id="47ba0-109">Desarrollador de informes electrónicos</span><span class="sxs-lookup"><span data-stu-id="47ba0-109">Electronic reporting developer</span></span>
- <span data-ttu-id="47ba0-110">Consultor funcional de informes electrónicos</span><span class="sxs-lookup"><span data-stu-id="47ba0-110">Electronic reporting functional consultant</span></span>
- <span data-ttu-id="47ba0-111">Administrador del sistema</span><span class="sxs-lookup"><span data-stu-id="47ba0-111">System administrator</span></span>

<span data-ttu-id="47ba0-112">También debe tener acceso al entorno de desarrollo para esta topología.</span><span class="sxs-lookup"><span data-stu-id="47ba0-112">You must also have access to the development environment for this topology.</span></span>

## <a name="create-or-import-an-er-format-configuration"></a><span data-ttu-id="47ba0-113">Creación o importación de una configuración del formato de ER</span><span class="sxs-lookup"><span data-stu-id="47ba0-113">Create or import an ER format configuration</span></span>

<span data-ttu-id="47ba0-114">En la topología actual, [cree un nuevo formato de ER](tasks/er-format-configuration-2016-11.md) para generar documentos para los que pretende agregar una ubicación de almacenamiento personalizada.</span><span class="sxs-lookup"><span data-stu-id="47ba0-114">In the current topology, [create a new ER format](tasks/er-format-configuration-2016-11.md) to generate documents that you plan to add a custom storage location for.</span></span> <span data-ttu-id="47ba0-115">O bien, [importe un formato de ER existente en esta topología](general-electronic-reporting-manage-configuration-lifecycle.md).</span><span class="sxs-lookup"><span data-stu-id="47ba0-115">Alternatively, [import an existing ER format into this topology](general-electronic-reporting-manage-configuration-lifecycle.md).</span></span>

![Página de diseñador de formato](media/er-extend-file-storages-format.png)

> [!IMPORTANT]
> <span data-ttu-id="47ba0-117">El formato del ER que cree o importe debe contener al menos uno de los siguientes elementos de formato:</span><span class="sxs-lookup"><span data-stu-id="47ba0-117">The ER format that you create or import must contain at least one of the following format elements:</span></span>
>
> - <span data-ttu-id="47ba0-118">Archivo</span><span class="sxs-lookup"><span data-stu-id="47ba0-118">File</span></span>
> - <span data-ttu-id="47ba0-119">Carpeta</span><span class="sxs-lookup"><span data-stu-id="47ba0-119">Folder</span></span>
> - <span data-ttu-id="47ba0-120">Combinación</span><span class="sxs-lookup"><span data-stu-id="47ba0-120">Merger</span></span>
> - <span data-ttu-id="47ba0-121">Archivo adjunto</span><span class="sxs-lookup"><span data-stu-id="47ba0-121">Attachment</span></span>

## <a name="create-a-new-document-type"></a><span data-ttu-id="47ba0-122">Crear un tipo de documento nuevo</span><span class="sxs-lookup"><span data-stu-id="47ba0-122">Create a new document type</span></span>

<span data-ttu-id="47ba0-123">Para especificar cómo se distribuyen los documentos que un formato de ER genera, debe configurar [Informes electrónicos (ER)](electronic-reporting-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="47ba0-123">To specify how documents that an ER format generates are routed, you must configure [Electronic reporting (ER) destinations](electronic-reporting-destinations.md).</span></span> <span data-ttu-id="47ba0-124">En cada destino de ER que se configure para almacenar documentos generados como archivos, debe especificar un tipo de documento del marco de la gestión de documentos.</span><span class="sxs-lookup"><span data-stu-id="47ba0-124">In each ER destination that is configured to store generated documents as files, you must specify a document type of the Document management framework.</span></span> <span data-ttu-id="47ba0-125">Los distintos tipos de documentos se pueden usar para distribuir los documentos que distintos formatos de ER generan.</span><span class="sxs-lookup"><span data-stu-id="47ba0-125">Different document types can be used to route documents that different ER formats generate.</span></span>

1. <span data-ttu-id="47ba0-126">Agregue un nuevo [tipo de documento](https://docs.microsoft.com/dynamics365/fin-ops-core/fin-ops/organization-administration/configure-document-management) para el formato de ER que ha creado o importado anteriormente.</span><span class="sxs-lookup"><span data-stu-id="47ba0-126">Add a new [document type](https://docs.microsoft.com/dynamics365/fin-ops-core/fin-ops/organization-administration/configure-document-management) for the ER format that you created or imported earlier.</span></span> <span data-ttu-id="47ba0-127">En la ilustración siguiente, el tipo de documento es **FileX**.</span><span class="sxs-lookup"><span data-stu-id="47ba0-127">In the illustration that follows, the document type is **FileX**.</span></span>
2. <span data-ttu-id="47ba0-128">Para distinguir este tipo de documento de otros tipos de documentos, incluya una palabra clave específica en su nombre.</span><span class="sxs-lookup"><span data-stu-id="47ba0-128">To differentiate this document type from other document types, include a specific keyword in its name.</span></span> <span data-ttu-id="47ba0-129">Por ejemplo, en la ilustración siguiente, el nombre es **Carpeta (LOCAL)**.</span><span class="sxs-lookup"><span data-stu-id="47ba0-129">For example, in the illustration that follows, the name is **(LOCAL) folder**.</span></span>
3. <span data-ttu-id="47ba0-130">En el campo **Clase**, especifique **Asociar archivo**.</span><span class="sxs-lookup"><span data-stu-id="47ba0-130">In the **Class** field, specify **Attach file**.</span></span>
4. <span data-ttu-id="47ba0-131">En el campo **Grupo**, especifique **archivo**.</span><span class="sxs-lookup"><span data-stu-id="47ba0-131">In the **Group** field, specify **File**.</span></span>

![Página de tipos de documento](media/er-extend-file-storages-document-type.png)

> [!NOTE]
> <span data-ttu-id="47ba0-133">Los tipos de documento son específicos de la empresa.</span><span class="sxs-lookup"><span data-stu-id="47ba0-133">Document types are company-specific.</span></span> <span data-ttu-id="47ba0-134">Para usar un formato de ER con un destino configurado en varias empresas, debe configurar un tipo de documento independiente en cada empresa.</span><span class="sxs-lookup"><span data-stu-id="47ba0-134">To use an ER format with a configured destination in multiple companies, you must configure a separate document type in each company.</span></span>

## <a name="review-source-code"></a><span data-ttu-id="47ba0-135">Revisar código fuente</span><span class="sxs-lookup"><span data-stu-id="47ba0-135">Review source code</span></span>

<span data-ttu-id="47ba0-136">Revise el código del método **insertFile()** de la clase **ERDocuManagement**.</span><span class="sxs-lookup"><span data-stu-id="47ba0-136">Review the code of the **insertFile()** method of the **ERDocuManagement** class.</span></span> <span data-ttu-id="47ba0-137">Observe que el evento **AttachingFile()** está activado mientras que el archivo generado está vinculado a un registro.</span><span class="sxs-lookup"><span data-stu-id="47ba0-137">Notice that the **AttachingFile()** event is raised while the generated file is attached to a record.</span></span>


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

<span data-ttu-id="47ba0-138">Se activa el evento **AttachingFile()** cuando se procesan los destinos de ER siguientes:</span><span class="sxs-lookup"><span data-stu-id="47ba0-138">The **AttachingFile()** event is raised when the following ER destinations are processed:</span></span>

- <span data-ttu-id="47ba0-139">**Archivo** Cuando se usa este destino, un registro nuevo para el formato de ER que se ejecuta se crea en la tabla de ERFormatMappingRunJobTable.</span><span class="sxs-lookup"><span data-stu-id="47ba0-139">**Archive** – When this destination is used, a new record for the ER format that is run is created in the ERFormatMappingRunJobTable table.</span></span> <span data-ttu-id="47ba0-140">El campo **Archivado** de este registro se establece en **Falso**.</span><span class="sxs-lookup"><span data-stu-id="47ba0-140">The **Archived** field in this record is set to **False**.</span></span> <span data-ttu-id="47ba0-141">Si el formato de ER se ejecuta correctamente, el documento generado se vincula a este registro, y se activa el evento **AttachingFile()**.</span><span class="sxs-lookup"><span data-stu-id="47ba0-141">If the ER format is successfully run, the generated document is attached to this record, and the **AttachingFile()** event is raised.</span></span> <span data-ttu-id="47ba0-142">El tipo de documento seleccionado en este destino de ER determina la ubicación de almacenamiento del archivo adjunto (almacenamiento de Microsoft Azure o una carpeta de Microsoft SharePoint).</span><span class="sxs-lookup"><span data-stu-id="47ba0-142">The document type that is selected in this ER destination determines the storage location for the attached file (Microsoft Azure Storage or a Microsoft SharePoint folder).</span></span>
- <span data-ttu-id="47ba0-143">**Archivo de trabajo** Cuando se usa este destino, un registro nuevo para el formato de ER que se ejecuta se crea en la tabla de ERFormatMappingRunJobTable.</span><span class="sxs-lookup"><span data-stu-id="47ba0-143">**Job archive** – When this destination is used, a new record for the ER form that is run is created in the ERFormatMappingRunJobTable table.</span></span> <span data-ttu-id="47ba0-144">El campo **Archivado** de este registro se establece en **True**.</span><span class="sxs-lookup"><span data-stu-id="47ba0-144">The **Archived** field in this record is set to **True**.</span></span> <span data-ttu-id="47ba0-145">Si el formato de ER se ejecuta correctamente, el documento generado se vincula a este registro, y se activa el evento **AttachingFile()**.</span><span class="sxs-lookup"><span data-stu-id="47ba0-145">If the ER format is successfully run, the generated document is attached to this record, and the **AttachingFile()** event is raised.</span></span> <span data-ttu-id="47ba0-146">El tipo de documento que se configura en los parámetros de ER determina la ubicación de almacenamiento del archivo adjunto (Azure Storage o una carpeta de SharePoint).</span><span class="sxs-lookup"><span data-stu-id="47ba0-146">The document type that is configured in the ER parameters determines the storage location for the attached file (Azure Storage or a SharePoint folder).</span></span>

![Página de parámetros de informes electrónicos](media/er-extend-file-storages-parameters.png)

## <a name="configure-an-er-destination"></a><span data-ttu-id="47ba0-148">Configurar un destino de ER</span><span class="sxs-lookup"><span data-stu-id="47ba0-148">Configure an ER destination</span></span>

1. <span data-ttu-id="47ba0-149">Configure el destino archivado de uno de los elementos anteriormente mencionados (archivo, carpeta, combinación o datos adjuntos) del formato de ER que ha creado o importado.</span><span class="sxs-lookup"><span data-stu-id="47ba0-149">Configure the archived destination for one of the previously mentioned elements (file, folder, merger, or attachment) of the ER format that you created or imported.</span></span> <span data-ttu-id="47ba0-150">Para obtener instrucciones, consulte [Destinación de configuración de ER](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/analytics/tasks/er-destinations-2016-11).</span><span class="sxs-lookup"><span data-stu-id="47ba0-150">For guidance, see [ER Configure destinations](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/analytics/tasks/er-destinations-2016-11).</span></span>
2. <span data-ttu-id="47ba0-151">Utilice el tipo de documento que ha agregado anteriormente para el destino configurado.</span><span class="sxs-lookup"><span data-stu-id="47ba0-151">Use the document type that you added earlier for the configured destination.</span></span> <span data-ttu-id="47ba0-152">(Para el ejemplo en este tema, el tipo de documento es **FileX**.)</span><span class="sxs-lookup"><span data-stu-id="47ba0-152">(For the example in this topic, the document type is **FileX**.)</span></span>

![Cuadro de diálogo Configuración de destino](media/er-extend-file-storages-destination.png)

## <a name="modify-source-code"></a><span data-ttu-id="47ba0-154">Modificación de código de origen</span><span class="sxs-lookup"><span data-stu-id="47ba0-154">Modify source code</span></span>

1. <span data-ttu-id="47ba0-155">Agregue una nueva clase al proyecto de Microsoft Visual Studio , y escriba el código para suscribirse al evento **AttachingFile()** que se menciona anteriormente.</span><span class="sxs-lookup"><span data-stu-id="47ba0-155">Add a new class to your Microsoft Visual Studio project, and write code to subscribe to the **AttachingFile()** event that was mentioned earlier.</span></span> <span data-ttu-id="47ba0-156">(Para obtener más información sobre el patrón de extensibilidad usado, consulte [Responder mediante EventHandlerResult](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/extensibility/respond-event-handler-result).) Por ejemplo, en la nueva clase, escriba código que realice las acciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="47ba0-156">(For more information about the extensibility pattern that is used, see [Respond by using EventHandlerResult](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/extensibility/respond-event-handler-result).) For example, in the new class, write code that performs the following actions:</span></span>

    1. <span data-ttu-id="47ba0-157">Almacenar los archivos generados en una carpeta del sistema de archivos local del servidor que ejecuta el servicio Application Object Server (AOS).</span><span class="sxs-lookup"><span data-stu-id="47ba0-157">Store generated files in a folder of the local file system of the server that runs the Application Object Server (AOS) service.</span></span>
    2. <span data-ttu-id="47ba0-158">Almacenar estos archivos generados solo si se utiliza el nuevo tipo de documento (por ejemplo, el tipo **FileX** que tiene la palabra clave “(LOCAL)” en su nombre) mientras se asocia un archivo al registro en el registro de trabajo de la ejecución de ER.</span><span class="sxs-lookup"><span data-stu-id="47ba0-158">Store these generated files only when the new document type (for example, the **FileX** type that has the "(LOCAL)" keyword in its name) is used while a file is attached to the record in the ER execution job log.</span></span>

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

2. <span data-ttu-id="47ba0-159">Reconstruir su proyecto.</span><span class="sxs-lookup"><span data-stu-id="47ba0-159">Rebuild your project.</span></span>

## <a name="run-the-er-format-that-you-created-or-imported"></a><span data-ttu-id="47ba0-160">Ejecutar el formato de ER que ha creado o importado.</span><span class="sxs-lookup"><span data-stu-id="47ba0-160">Run the ER format that you created or imported</span></span>

1. <span data-ttu-id="47ba0-161">Ejecutar el formato de ER que ha creado o importado.</span><span class="sxs-lookup"><span data-stu-id="47ba0-161">Execute the ER format that you created or imported.</span></span>
2. <span data-ttu-id="47ba0-162">Vaya a **Administración de la organización \> Informes electrónicos \> Trabajos de informes electrónicos**.</span><span class="sxs-lookup"><span data-stu-id="47ba0-162">Go to **Organization administration \> Electronic reporting \> Electronic reporting jobs**.</span></span> <span data-ttu-id="47ba0-163">Encuentre el registro creado para este trabajo de ejecución, y que contenga el archivo generado vinculado a él.</span><span class="sxs-lookup"><span data-stu-id="47ba0-163">Find the record that was created for this execution job, and that has the generated file attached to it.</span></span>
3. <span data-ttu-id="47ba0-164">Explore la carpeta **C:\\0** local para encontrar el mismo archivo generado.</span><span class="sxs-lookup"><span data-stu-id="47ba0-164">Explore the local **C:\\0** folder to find same generated file.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="47ba0-165">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="47ba0-165">Additional resources</span></span>

- [<span data-ttu-id="47ba0-166">Destinos de informes electrónicos (ER)</span><span class="sxs-lookup"><span data-stu-id="47ba0-166">Electronic reporting (ER) destinations</span></span>](electronic-reporting-destinations.md)
- [<span data-ttu-id="47ba0-167">Página de inicio de extensibilidad</span><span class="sxs-lookup"><span data-stu-id="47ba0-167">Extensibility home page</span></span>](../extensibility/extensibility-home-page.md)
