---
title: Informe de vencimiento de inventario
description: Este tema describe la funcionalidad que permite ejecutar un informe de antigüedad de inventario y generar resultados como formulario y gráfico.
author: AndersGirke
manager: AnnBe
ms.date: 11/11/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CostAdminWorkspace, CostAnalysisWorkspace
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: aevengir
ms.search.validFrom: 2019-01-10
ms.dyn365.ops.version: ''
ms.openlocfilehash: 21411c104c854224ff3689dc8e080b88d9fc7d23
ms.sourcegitcommit: 9267608347c9781fb4ba70f1384ca24da69c716d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/15/2019
ms.locfileid: "2810260"
---
# <a name="inventory-aging-report"></a><span data-ttu-id="e5323-103">Informe de vencimiento de inventario</span><span class="sxs-lookup"><span data-stu-id="e5323-103">Inventory aging report</span></span>


[!include [banner](../includes/banner.md)]
[!include [banner](../includes/preview-banner.md)]

<span data-ttu-id="e5323-104">En Microsoft Dynamics 365 Supply Chain Management, puede ejecutar un informe de **Vencimiento de inventario** generar resultados como un formulario y gráfico.</span><span class="sxs-lookup"><span data-stu-id="e5323-104">In Microsoft Dynamics 365 Supply Chain Management, you can run an **Inventory aging** report and make the output available as a form and a chart.</span></span> <span data-ttu-id="e5323-105">En el formulario, las columnas y saldos agregados se ajustan dinámicamente, en función del diseño que se configura.</span><span class="sxs-lookup"><span data-stu-id="e5323-105">In the form, columns and aggregate balances are dynamically adjusted, depending on the layout that is configured.</span></span> <span data-ttu-id="e5323-106">El gráfico proporciona una visión general visual que admite el filtrado y permite explorar en profundidad los detalles.</span><span class="sxs-lookup"><span data-stu-id="e5323-106">The chart provides a visual overview that supports filtering and lets you drill down into details.</span></span> <span data-ttu-id="e5323-107">Además, una entidad de datos que se denomina **Informe de vencimiento de inventario** permite exportar los resultados de una ejecución de informe de **Vencimiento de inventario** en un formato como un archivo Microsoft Excel o PDF.</span><span class="sxs-lookup"><span data-stu-id="e5323-107">Additionally, a data entity that is named **Inventory aging report** lets you export the results of an **Inventory aging** report run to a format such as a Microsoft Excel file or a PDF file.</span></span>

<span data-ttu-id="e5323-108">Este método de ejecutar un informe de **Vencimiento de inventario** resulta útil cuando los resultados contienen muchas líneas.</span><span class="sxs-lookup"><span data-stu-id="e5323-108">This method of running an **Inventory aging** report is helpful in cases where the output contains many lines.</span></span> <span data-ttu-id="e5323-109">Por ejemplo, el resultado contendrá muchas líneas si tiene 50 000 artículos y 300 tiendas que se crean como almacenes, y solicita vencimientos de inventario por elemento, sitio y almacén.</span><span class="sxs-lookup"><span data-stu-id="e5323-109">For example, the output will contain many lines if you have 50,000 items and 300 stores that are created as warehouses, and you request inventory aging by item, site, and warehouse.</span></span>

## <a name="run-an-inventory-aging-report"></a><span data-ttu-id="e5323-110">Ejecutar un informe de vencimiento de inventario</span><span class="sxs-lookup"><span data-stu-id="e5323-110">Run an Inventory aging report</span></span>

1. <span data-ttu-id="e5323-111">Vaya a **Gestión de costes \> Consultas e informes \> Almacenamiento del informe de vencimiento de inventario**.</span><span class="sxs-lookup"><span data-stu-id="e5323-111">Go to **Cost management \> Inquiries and reports \> Inventory aging report storage**.</span></span>
1. <span data-ttu-id="e5323-112">Seleccione **Nuevo**.</span><span class="sxs-lookup"><span data-stu-id="e5323-112">Select **New**.</span></span>
1. <span data-ttu-id="e5323-113">En el campo **Identificador de procesos: nombre**, especifique un nombre único para informe.</span><span class="sxs-lookup"><span data-stu-id="e5323-113">In the **Process Identifier – Name** field, enter a unique name for the report.</span></span>
1. <span data-ttu-id="e5323-114">Seleccione el informe **Identificación: Id.** y fíltrelo como sea necesario.</span><span class="sxs-lookup"><span data-stu-id="e5323-114">Select the **Identification – ID** report, and filter it as you require.</span></span>

    <span data-ttu-id="e5323-115">La ejecución de informes se realiza siempre en un trabajo por lotes.</span><span class="sxs-lookup"><span data-stu-id="e5323-115">Report execution is always done in a batch job.</span></span>

1. <span data-ttu-id="e5323-116">Después de que el trabajo por lotes se complete, se mostrará el resultado en la página **Almacenamiento del informe de vencimiento de inventario**.</span><span class="sxs-lookup"><span data-stu-id="e5323-116">After the batch job is completed, the output is shown on the **Inventory aging report storage** page.</span></span>
1. <span data-ttu-id="e5323-117">Para ver el resultado como un formulario con un diseño tradicional de la cuadrículas, seleccione **Ver detalles**.</span><span class="sxs-lookup"><span data-stu-id="e5323-117">To view the output as a form that has a traditional grid layout, select **View details**.</span></span> <span data-ttu-id="e5323-118">Para ver el resultado como un gráfico agregado, seleccione **Ver gráfico**.</span><span class="sxs-lookup"><span data-stu-id="e5323-118">To view the output as an aggregated chart, select **View chart**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="e5323-119">El formulario no incluirá los subtotales definidos en el diseño del informe.</span><span class="sxs-lookup"><span data-stu-id="e5323-119">The form won't include subtotals that are defined in the report layout.</span></span>

<span data-ttu-id="e5323-120">La entidad de los datos **Informe de vencimiento de inventario** le permite exportar el resultado de un informe **Vencimiento de inventario** aplicando un filtro para el campo **Identificador de procesos: nombre** a cualquier formato que admita la administración de datos.</span><span class="sxs-lookup"><span data-stu-id="e5323-120">The **Inventory aging report** data entity lets you export the output of an **Inventory aging** report by applying a filter for the **Process Identifier – Name** field to any format that Data management supports.</span></span>
