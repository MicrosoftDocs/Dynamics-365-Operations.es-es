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
ms.openlocfilehash: 8797a68507a5116c6adbf1f2d805838fa507958c
ms.sourcegitcommit: 445f6d8d0df9f2cbac97e85e3ec3ed8b7d18d3a2
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/01/2020
ms.locfileid: "3745594"
---
# <a name="archive-destination"></a><span data-ttu-id="ffe74-103">Destino de archivo</span><span class="sxs-lookup"><span data-stu-id="ffe74-103">Archive destination</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="ffe74-104">Puede configurar un destino de archivo para cada componente FOLDER o FILE de un formato de informe electrónico (ER) que está configurado para generar documentos salientes.</span><span class="sxs-lookup"><span data-stu-id="ffe74-104">You can configure an archive destination for each FOLDER or FILE component of an Electronic reporting (ER) format that is configured to generate outbound documents.</span></span> <span data-ttu-id="ffe74-105">Según la configuración de destino, un documento generado se almacena como archivo adjunto de un registro de la lista de trabajos de ER.</span><span class="sxs-lookup"><span data-stu-id="ffe74-105">Based on the destination setting, a generated document is stored as an attachment of a record of the ER jobs list.</span></span>

<span data-ttu-id="ffe74-106">Puede utilizar esta opción para enviar el documento generado a una carpeta de Microsoft SharePoint o Microsoft Azure Storage.</span><span class="sxs-lookup"><span data-stu-id="ffe74-106">You can use this option to send the generated document to a Microsoft SharePoint folder or Microsoft Azure Storage.</span></span> <span data-ttu-id="ffe74-107">Establezca **Habilitada** en **Sí** para enviar la salida a un destino que se define por el tipo de documento seleccionado.</span><span class="sxs-lookup"><span data-stu-id="ffe74-107">Set **Enabled** to **Yes** to send output to a destination that is defined by the selected document type.</span></span> <span data-ttu-id="ffe74-108">Solo los tipos de documento donde el grupo se establece en **Archivo** están disponibles para su selección.</span><span class="sxs-lookup"><span data-stu-id="ffe74-108">Only document types where the group is set to **File** are available for selection.</span></span> <span data-ttu-id="ffe74-109">Defina los [tipos](https://docs.microsoft.com/dynamics365/fin-ops-core/fin-ops/organization-administration/configure-document-management#configure-document-types) de documento en **Administración de la organización** \> **Administración de documentos** \> **Tipos de documento**.</span><span class="sxs-lookup"><span data-stu-id="ffe74-109">You define document [types](https://docs.microsoft.com/dynamics365/fin-ops-core/fin-ops/organization-administration/configure-document-management#configure-document-types) at **Organization administration** \> **Document management** \> **Document types**.</span></span> <span data-ttu-id="ffe74-110">La configuración de destinos de ER es la misma que la configuración para el sistema de administración de documentos.</span><span class="sxs-lookup"><span data-stu-id="ffe74-110">The configuration for ER destinations is the same as the configuration for the document management system.</span></span>

<span data-ttu-id="ffe74-111">[![Página de tipos de documento](./media/ER_Destinations-SharePointDocuType.png)](./media/ER_Destinations-SharePointDocuType.png)</span><span class="sxs-lookup"><span data-stu-id="ffe74-111">[![Document types page](./media/ER_Destinations-SharePointDocuType.png)](./media/ER_Destinations-SharePointDocuType.png)</span></span>

<span data-ttu-id="ffe74-112">La ubicación determina dónde se guarda el archivo.</span><span class="sxs-lookup"><span data-stu-id="ffe74-112">The location determines where the file is saved.</span></span> <span data-ttu-id="ffe74-113">Una vez que se habilite el destino de **Archivado**, los resultados se pueden guardar en el archivo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="ffe74-113">After the **Archive** destination is enabled, the results can be saved in the Job archive.</span></span> <span data-ttu-id="ffe74-114">Puede ver los resultados en **Administración de organización** \> **Informes electrónicos** \> **Trabajos archivados de informes electrónicos**.</span><span class="sxs-lookup"><span data-stu-id="ffe74-114">You can view the results at **Organization administration** \> **Electronic reporting** \> **Electronic reporting archived jobs**.</span></span>

> [!NOTE]
> <span data-ttu-id="ffe74-115">Seleccione un tipo de documento para el archivo de trabajo en **Administración de organización** \> **Áreas de trabajo** \> **Informes electrónicos** \> **Parámetros de informes electrónicos**.</span><span class="sxs-lookup"><span data-stu-id="ffe74-115">Select a document type for the Job archive by navigating to **Organization administration** \> **Workspaces** \> **Electronic reporting** \> **Electronic reporting parameters**.</span></span> <span data-ttu-id="ffe74-116">Para obtener más información, consulte [Configurar el marco de informes electrónicos (ER)](electronic-reporting-er-configure-parameters.md#prerequisites-for-er-setup).</span><span class="sxs-lookup"><span data-stu-id="ffe74-116">For more information, [Configure the Electronic reporting (ER) framework](electronic-reporting-er-configure-parameters.md#prerequisites-for-er-setup).</span></span>

## <a name="sharepoint"></a><span data-ttu-id="ffe74-117">SharePoint</span><span class="sxs-lookup"><span data-stu-id="ffe74-117">SharePoint</span></span>

<span data-ttu-id="ffe74-118">Puede guardar un archivo en una carpeta de SharePoint designada.</span><span class="sxs-lookup"><span data-stu-id="ffe74-118">You can save a file in a designated SharePoint folder.</span></span> <span data-ttu-id="ffe74-119">Para definir el servidor de SharePoint predeterminado, vaya a **Administración de la organización** \> **Administración de documentos** \> **Parámetros de la administración de documentos**.</span><span class="sxs-lookup"><span data-stu-id="ffe74-119">To define the default SharePoint server, go to **Organization administration** \> **Document management** \> **Document management parameters**.</span></span> <span data-ttu-id="ffe74-120">En la pestaña **SharePoint**, configure la carpeta SharePoint.</span><span class="sxs-lookup"><span data-stu-id="ffe74-120">On the **SharePoint** tab, configure the SharePoint folder.</span></span> <span data-ttu-id="ffe74-121">Luego, puede seleccionarla como carpeta donde se guardará la salida ER.</span><span class="sxs-lookup"><span data-stu-id="ffe74-121">Then, you can select it as the folder where the ER output will be saved.</span></span> <span data-ttu-id="ffe74-122">La ubicación de **SharePoint** debe seleccionarse en este tipo de documento.</span><span class="sxs-lookup"><span data-stu-id="ffe74-122">The **SharePoint** location must be selected in this document type.</span></span>

<span data-ttu-id="ffe74-123">[![Selección de una carpeta de SharePoint](./media/ER_Destinations-SharePointDocuTypeLocation.png)](./media/ER_Destinations-SharePointDocuTypeLocation.png)</span><span class="sxs-lookup"><span data-stu-id="ffe74-123">[![Selecting a SharePoint folder](./media/ER_Destinations-SharePointDocuTypeLocation.png)](./media/ER_Destinations-SharePointDocuTypeLocation.png)</span></span>

## <a name="azure-storage"></a><span data-ttu-id="ffe74-124">Almacenamiento de Azure</span><span class="sxs-lookup"><span data-stu-id="ffe74-124">Azure Storage</span></span>

<span data-ttu-id="ffe74-125">Cuando se establece la ubicación del tipo de documento en **Almacenamiento de Azure**, puede guardar un archivo en el Almacenamiento de Azure.</span><span class="sxs-lookup"><span data-stu-id="ffe74-125">When the document type location is set to **Azure storage**, you can save a file to Azure Storage.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="ffe74-126">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="ffe74-126">Additional resources</span></span>

- [<span data-ttu-id="ffe74-127">Visión general de los informes electrónicos (ER)</span><span class="sxs-lookup"><span data-stu-id="ffe74-127">Electronic reporting (ER) overview</span></span>](general-electronic-reporting.md)
- [<span data-ttu-id="ffe74-128">Destinos de informes electrónicos (ER)</span><span class="sxs-lookup"><span data-stu-id="ffe74-128">Electronic reporting (ER) destinations</span></span>](electronic-reporting-destinations.md)
- [<span data-ttu-id="ffe74-129">Configurar la gestión de documentos</span><span class="sxs-lookup"><span data-stu-id="ffe74-129">Configure document management</span></span>](../../fin-ops/organization-administration/configure-document-management.md)
