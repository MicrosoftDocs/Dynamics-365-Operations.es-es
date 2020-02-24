---
title: Tipo de destino de ER de archivo
description: Este tema proporciona información sobre cómo configurar un destino de archivo para cada componente FOLDER o FILE de un formato de informe electrónico (ER) que está configurado para generar documentos salientes.
author: NickSelin
manager: AnnBe
ms.date: 01/27/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
ms.search.form: DocuType, ERSolutionTable, ERFormatDestinationTable
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: 97423
ms.assetid: ''
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-05-31
ms.dyn365.ops.version: AX 7.0.1
ms.openlocfilehash: 15611a4f0000ca5ccb0ac3f4012251d5bf5689ec
ms.sourcegitcommit: 54baab2a04e5c534fc2d1fd67b67e23a152d4e57
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "3019988"
---
# <span data-ttu-id="468c7-103"><a name="ArchiveDestinationType">Destino de archivo</a></span><span class="sxs-lookup"><span data-stu-id="468c7-103"><a name="ArchiveDestinationType">Archive destination</a></span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="468c7-104">Puede configurar un destino de archivo para cada componente FOLDER o FILE de un formato de informe electrónico (ER) que está configurado para generar documentos salientes.</span><span class="sxs-lookup"><span data-stu-id="468c7-104">You can configure an archive destination for each FOLDER or FILE component of an Electronic reporting (ER) format that is configured to generate outbound documents.</span></span> <span data-ttu-id="468c7-105">Según la configuración de destino, un documento generado se almacena como archivo adjunto de un registro de la lista de trabajos de ER.</span><span class="sxs-lookup"><span data-stu-id="468c7-105">Based on the destination setting, a generated document is stored as an attachment of a record of the ER jobs list.</span></span>

<span data-ttu-id="468c7-106">Puede utilizar esta opción para enviar el documento generado a una carpeta de Microsoft SharePoint o Microsoft Azure Storage.</span><span class="sxs-lookup"><span data-stu-id="468c7-106">You can use this option to send the generated document to a Microsoft SharePoint folder or Microsoft Azure Storage.</span></span> <span data-ttu-id="468c7-107">Establezca **Habilitada** en **Sí** para enviar la salida a un destino que se define por el tipo de documento seleccionado.</span><span class="sxs-lookup"><span data-stu-id="468c7-107">Set **Enabled** to **Yes** to send output to a destination that is defined by the selected document type.</span></span> <span data-ttu-id="468c7-108">Solo los tipos de documento donde el grupo se establece en **Archivo** están disponibles para su selección.</span><span class="sxs-lookup"><span data-stu-id="468c7-108">Only document types where the group is set to **File** are available for selection.</span></span> <span data-ttu-id="468c7-109">Defina los [tipos](https://docs.microsoft.com/dynamics365/fin-ops-core/fin-ops/organization-administration/configure-document-management#configure-document-types) de documento en **Administración de la organización** \> **Administración de documentos** \> **Tipos de documento**.</span><span class="sxs-lookup"><span data-stu-id="468c7-109">You define document [types](https://docs.microsoft.com/dynamics365/fin-ops-core/fin-ops/organization-administration/configure-document-management#configure-document-types) at **Organization administration** \> **Document management** \> **Document types**.</span></span> <span data-ttu-id="468c7-110">La configuración de destinos de ER es la misma que la configuración para el sistema de administración de documentos.</span><span class="sxs-lookup"><span data-stu-id="468c7-110">The configuration for ER destinations is the same as the configuration for the document management system.</span></span>

<span data-ttu-id="468c7-111">[![Página de tipos de documento](./media/ER_Destinations-SharePointDocuType.png)](./media/ER_Destinations-SharePointDocuType.png)</span><span class="sxs-lookup"><span data-stu-id="468c7-111">[![Document types page](./media/ER_Destinations-SharePointDocuType.png)](./media/ER_Destinations-SharePointDocuType.png)</span></span>

<span data-ttu-id="468c7-112">La ubicación determina dónde se guarda el archivo.</span><span class="sxs-lookup"><span data-stu-id="468c7-112">The location determines where the file is saved.</span></span> <span data-ttu-id="468c7-113">Una vez que se habilite el destino de **Archivado**, los resultados se pueden guardar en el archivo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="468c7-113">After the **Archive** destination is enabled, the results can be saved in the Job archive.</span></span> <span data-ttu-id="468c7-114">Puede ver los resultados en **Administración de organización** \> **Informes electrónicos** \> **Trabajos archivados de informes electrónicos**.</span><span class="sxs-lookup"><span data-stu-id="468c7-114">You can view the results at **Organization administration** \> **Electronic reporting** \> **Electronic reporting archived jobs**.</span></span>

> [!NOTE]
> <span data-ttu-id="468c7-115">Seleccione un tipo de documento para el archivo de trabajo en **Administración de organización** \> **Áreas de trabajo** \> **Informes electrónicos** \> **Parámetros de informes electrónicos**.</span><span class="sxs-lookup"><span data-stu-id="468c7-115">Select a document type for the Job archive by navigating to **Organization administration** \> **Workspaces** \> **Electronic reporting** \> **Electronic reporting parameters**.</span></span> <span data-ttu-id="468c7-116">Para obtener más información, consulte [Configurar el marco de informes electrónicos (ER)](electronic-reporting-er-configure-parameters.md#prerequisites-for-er-setup).</span><span class="sxs-lookup"><span data-stu-id="468c7-116">For more information, [Configure the Electronic reporting (ER) framework](electronic-reporting-er-configure-parameters.md#prerequisites-for-er-setup).</span></span>

## <a name="sharepoint"></a><span data-ttu-id="468c7-117">SharePoint</span><span class="sxs-lookup"><span data-stu-id="468c7-117">SharePoint</span></span>

<span data-ttu-id="468c7-118">Puede guardar un archivo en una carpeta de SharePoint designada.</span><span class="sxs-lookup"><span data-stu-id="468c7-118">You can save a file in a designated SharePoint folder.</span></span> <span data-ttu-id="468c7-119">Para definir el servidor de SharePoint predeterminado, vaya a **Administración de la organización** \> **Administración de documentos** \> **Parámetros de la administración de documentos**.</span><span class="sxs-lookup"><span data-stu-id="468c7-119">To define the default SharePoint server, go to **Organization administration** \> **Document management** \> **Document management parameters**.</span></span> <span data-ttu-id="468c7-120">En la pestaña **SharePoint**, configure la carpeta SharePoint.</span><span class="sxs-lookup"><span data-stu-id="468c7-120">On the **SharePoint** tab, configure the SharePoint folder.</span></span> <span data-ttu-id="468c7-121">Luego, puede seleccionarla como carpeta donde se guardará la salida ER.</span><span class="sxs-lookup"><span data-stu-id="468c7-121">Then, you can select it as the folder where the ER output will be saved.</span></span> <span data-ttu-id="468c7-122">La ubicación de **SharePoint** debe seleccionarse en este tipo de documento.</span><span class="sxs-lookup"><span data-stu-id="468c7-122">The **SharePoint** location must be selected in this document type.</span></span>

<span data-ttu-id="468c7-123">[![Selección de una carpeta de SharePoint](./media/ER_Destinations-SharePointDocuTypeLocation.png)](./media/ER_Destinations-SharePointDocuTypeLocation.png)</span><span class="sxs-lookup"><span data-stu-id="468c7-123">[![Selecting a SharePoint folder](./media/ER_Destinations-SharePointDocuTypeLocation.png)](./media/ER_Destinations-SharePointDocuTypeLocation.png)</span></span>

## <a name="azure-storage"></a><span data-ttu-id="468c7-124">Almacenamiento de Azure</span><span class="sxs-lookup"><span data-stu-id="468c7-124">Azure Storage</span></span>

<span data-ttu-id="468c7-125">Cuando se establece la ubicación del tipo de documento en **Almacenamiento de Azure**, puede guardar un archivo en el Almacenamiento de Azure.</span><span class="sxs-lookup"><span data-stu-id="468c7-125">When the document type location is set to **Azure storage**, you can save a file to Azure Storage.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="468c7-126">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="468c7-126">Additional resources</span></span>

- [<span data-ttu-id="468c7-127">Visión general de los informes electrónicos (ER)</span><span class="sxs-lookup"><span data-stu-id="468c7-127">Electronic reporting (ER) overview</span></span>](general-electronic-reporting.md)
- [<span data-ttu-id="468c7-128">Destinos de informes electrónicos (ER)</span><span class="sxs-lookup"><span data-stu-id="468c7-128">Electronic reporting (ER) destinations</span></span>](electronic-reporting-destinations.md)
- [<span data-ttu-id="468c7-129">Configurar la gestión de documentos</span><span class="sxs-lookup"><span data-stu-id="468c7-129">Configure document management</span></span>](../../fin-ops/organization-administration/configure-document-management.md)
