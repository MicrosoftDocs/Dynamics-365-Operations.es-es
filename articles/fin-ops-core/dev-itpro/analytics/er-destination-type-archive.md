---
title: Tipo de destino de ER de archivo
description: Este tema proporciona información sobre cómo configurar un destino de archivo para cada componente FOLDER o FILE de un formato de informe electrónico (ER) que está configurado para generar documentos salientes.
author: NickSelin
manager: AnnBe
ms.date: 11/30/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
ms.search.form: DocuType, ERSolutionTable, ERFormatDestinationTable
audience: Application User
ms.reviewer: kfend
ms.custom: 97423
ms.assetid: ''
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-05-31
ms.dyn365.ops.version: AX 7.0.1
ms.openlocfilehash: 3dee7ec614ec1372feaa1150f5e4ebb14c32f60e
ms.sourcegitcommit: 659375c4cc7f5524cbf91cf6160f6a410960ac16
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/05/2020
ms.locfileid: "4679687"
---
# <a name="archive-er-destination-type"></a><span data-ttu-id="8f7cd-103">Tipo de destino de ER de archivo</span><span class="sxs-lookup"><span data-stu-id="8f7cd-103">Archive ER destination type</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="8f7cd-104">Puede configurar un destino de archivo para cada componente **Carpeta** o **Archivo** de un formato de informe electrónico (ER) que está configurado para generar documentos salientes.</span><span class="sxs-lookup"><span data-stu-id="8f7cd-104">You can configure an archive destination for each **Folder** or **File** component of an Electronic reporting (ER) format that is configured to generate outbound documents.</span></span> <span data-ttu-id="8f7cd-105">Según la configuración de destino, un documento generado se almacena como archivo adjunto de un registro de la lista de trabajos de ER.</span><span class="sxs-lookup"><span data-stu-id="8f7cd-105">Based on the destination setting, a generated document is stored as an attachment of a record of the ER jobs list.</span></span> <span data-ttu-id="8f7cd-106">Para ver los resultados vaya a **Administración de organización** \> **Informes electrónicos** \> **Trabajos de informes electrónicos**.</span><span class="sxs-lookup"><span data-stu-id="8f7cd-106">To view the results, go to **Organization administration** \> **Electronic reporting** \> **Electronic reporting jobs**.</span></span>

<span data-ttu-id="8f7cd-107">Puede utilizar esta opción para enviar el documento generado a una carpeta de Microsoft SharePoint o Microsoft Azure Storage.</span><span class="sxs-lookup"><span data-stu-id="8f7cd-107">You can use this option to send the generated document to a Microsoft SharePoint folder or Microsoft Azure Storage.</span></span> <span data-ttu-id="8f7cd-108">Establezca **Habilitada** en **Sí** para enviar la salida a un destino que se define por el tipo de documento seleccionado.</span><span class="sxs-lookup"><span data-stu-id="8f7cd-108">Set **Enabled** to **Yes** to send output to a destination that is defined by the selected document type.</span></span> <span data-ttu-id="8f7cd-109">Solo los tipos de documento donde el grupo se establece en **Archivo** están disponibles para su selección.</span><span class="sxs-lookup"><span data-stu-id="8f7cd-109">Only document types where the group is set to **File** are available for selection.</span></span> <span data-ttu-id="8f7cd-110">Defina los [tipos](https://docs.microsoft.com/dynamics365/fin-ops-core/fin-ops/organization-administration/configure-document-management#configure-document-types) de documento en **Administración de la organización** \> **Administración de documentos** \> **Tipos de documento**.</span><span class="sxs-lookup"><span data-stu-id="8f7cd-110">You define document [types](https://docs.microsoft.com/dynamics365/fin-ops-core/fin-ops/organization-administration/configure-document-management#configure-document-types) at **Organization administration** \> **Document management** \> **Document types**.</span></span> <span data-ttu-id="8f7cd-111">La configuración de destinos de ER es la misma que la configuración para el sistema de administración de documentos.</span><span class="sxs-lookup"><span data-stu-id="8f7cd-111">The configuration for ER destinations is the same as the configuration for the document management system.</span></span>

<span data-ttu-id="8f7cd-112">[![Página de tipos de documento](./media/ER_Destinations-SharePointDocuType.png)](./media/ER_Destinations-SharePointDocuType.png)</span><span class="sxs-lookup"><span data-stu-id="8f7cd-112">[![Document types page](./media/ER_Destinations-SharePointDocuType.png)](./media/ER_Destinations-SharePointDocuType.png)</span></span>

<span data-ttu-id="8f7cd-113">La ubicación determina dónde se guarda el archivo.</span><span class="sxs-lookup"><span data-stu-id="8f7cd-113">The location determines where the file is saved.</span></span> <span data-ttu-id="8f7cd-114">Una vez que se habilite el destino de **Archivado**, los resultados se pueden guardar en el archivo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="8f7cd-114">After the **Archive** destination is enabled, the results can be saved in the Job archive.</span></span> <span data-ttu-id="8f7cd-115">Puede ver los resultados en **Administración de organización** \> **Informes electrónicos** \> **Trabajos archivados de informes electrónicos**.</span><span class="sxs-lookup"><span data-stu-id="8f7cd-115">You can view the results at **Organization administration** \> **Electronic reporting** \> **Electronic reporting archived jobs**.</span></span>

> [!NOTE]
> <span data-ttu-id="8f7cd-116">Seleccione un tipo de documento para el archivo de trabajo en **Administración de organización** \> **Áreas de trabajo** \> **Informes electrónicos** \> **Parámetros de informes electrónicos**.</span><span class="sxs-lookup"><span data-stu-id="8f7cd-116">Select a document type for the Job archive by navigating to **Organization administration** \> **Workspaces** \> **Electronic reporting** \> **Electronic reporting parameters**.</span></span> <span data-ttu-id="8f7cd-117">Para obtener más información, consulte [Configurar el marco de informes electrónicos (ER)](electronic-reporting-er-configure-parameters.md#prerequisites-for-er-setup).</span><span class="sxs-lookup"><span data-stu-id="8f7cd-117">For more information, see [Configure the Electronic reporting (ER) framework](electronic-reporting-er-configure-parameters.md#prerequisites-for-er-setup).</span></span>

## <a name="sharepoint"></a><span data-ttu-id="8f7cd-118">SharePoint</span><span class="sxs-lookup"><span data-stu-id="8f7cd-118">SharePoint</span></span>

<span data-ttu-id="8f7cd-119">Puede guardar un archivo en una carpeta de SharePoint designada.</span><span class="sxs-lookup"><span data-stu-id="8f7cd-119">You can save a file in a designated SharePoint folder.</span></span> <span data-ttu-id="8f7cd-120">Para definir el servidor de SharePoint predeterminado, vaya a **Administración de la organización** \> **Administración de documentos** \> **Parámetros de la administración de documentos**.</span><span class="sxs-lookup"><span data-stu-id="8f7cd-120">To define the default SharePoint server, go to **Organization administration** \> **Document management** \> **Document management parameters**.</span></span> <span data-ttu-id="8f7cd-121">En la pestaña **SharePoint**, configure la carpeta SharePoint.</span><span class="sxs-lookup"><span data-stu-id="8f7cd-121">On the **SharePoint** tab, configure the SharePoint folder.</span></span> <span data-ttu-id="8f7cd-122">Luego, puede seleccionarla como carpeta donde se guardará la salida ER.</span><span class="sxs-lookup"><span data-stu-id="8f7cd-122">Then, you can select it as the folder where the ER output will be saved.</span></span> <span data-ttu-id="8f7cd-123">La ubicación de **SharePoint** debe seleccionarse en este tipo de documento.</span><span class="sxs-lookup"><span data-stu-id="8f7cd-123">The **SharePoint** location must be selected in this document type.</span></span>

<span data-ttu-id="8f7cd-124">[![Selección de una carpeta de SharePoint](./media/ER_Destinations-SharePointDocuTypeLocation.png)](./media/ER_Destinations-SharePointDocuTypeLocation.png)</span><span class="sxs-lookup"><span data-stu-id="8f7cd-124">[![Selecting a SharePoint folder](./media/ER_Destinations-SharePointDocuTypeLocation.png)](./media/ER_Destinations-SharePointDocuTypeLocation.png)</span></span>

## <a name="azure-storage"></a><span data-ttu-id="8f7cd-125">Almacenamiento de Azure</span><span class="sxs-lookup"><span data-stu-id="8f7cd-125">Azure Storage</span></span>

<span data-ttu-id="8f7cd-126">Cuando se establece la ubicación del tipo de documento en **Almacenamiento de Azure**, puede guardar un archivo en el Almacenamiento de Azure.</span><span class="sxs-lookup"><span data-stu-id="8f7cd-126">When the document type location is set to **Azure storage**, you can save a file to Azure Storage.</span></span>

> [!NOTE] 
> <span data-ttu-id="8f7cd-127">El marco de ER almacena permanentemente archivos en Azure Blob Storage, a diferencia del marco de administración de datos que aplica la política de retención de siete días para los documentos que deben procesarse.</span><span class="sxs-lookup"><span data-stu-id="8f7cd-127">The ER framework permanently stores files in Azure Blob storage unlike the Data management framework that applies the seven-day retention policy for documents that must be processed.</span></span> <span data-ttu-id="8f7cd-128">Para más información, consulte [API para obtener el estado del mensaje](../data-entities/recurring-integrations.md#api-for-getting-message-status) y [API de verificación de estado](../data-entities/data-management-api.md#status-check-api).</span><span class="sxs-lookup"><span data-stu-id="8f7cd-128">For more information, see [API for getting message status](../data-entities/recurring-integrations.md#api-for-getting-message-status) and [Status check API](../data-entities/data-management-api.md#status-check-api).</span></span> <span data-ttu-id="8f7cd-129">Los archivos relacionados con ER se almacenarán en Azure Blob Storage como archivos adjuntos de los registros de la tabla de la aplicación durante el tiempo que sea necesario.</span><span class="sxs-lookup"><span data-stu-id="8f7cd-129">The ER-related files will be stored in Azure Blob storage as attachments of application table records as long as necessary.</span></span> <span data-ttu-id="8f7cd-130">Se eliminará un solo archivo de Azure Blob Storage junto con el registro de la tabla de aplicación al que se adjuntó este archivo.</span><span class="sxs-lookup"><span data-stu-id="8f7cd-130">A single file will be deleted from Azure Blob storage along with the application table record that this file was attached to.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="8f7cd-131">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="8f7cd-131">Additional resources</span></span>

- [<span data-ttu-id="8f7cd-132">Visión general de los informes electrónicos (ER)</span><span class="sxs-lookup"><span data-stu-id="8f7cd-132">Electronic reporting (ER) overview</span></span>](general-electronic-reporting.md)
- [<span data-ttu-id="8f7cd-133">Destinos de informes electrónicos (ER)</span><span class="sxs-lookup"><span data-stu-id="8f7cd-133">Electronic reporting (ER) destinations</span></span>](electronic-reporting-destinations.md)
- [<span data-ttu-id="8f7cd-134">Configurar la gestión de documentos</span><span class="sxs-lookup"><span data-stu-id="8f7cd-134">Configure document management</span></span>](../../fin-ops/organization-administration/configure-document-management.md)
