---
title: Almacenamiento de informe de vencimiento de inventario
description: Este tema describe la funcionalidad que permite ejecutar un informe de antigüedad de inventario y generar resultados como formulario y gráfico.
author: AndersGirke
ms.date: 11/11/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: InventAgingStorage, InventAgingStorageChart, InventAgingStorageDetails
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: aevengir
ms.search.validFrom: 2019-01-10
ms.dyn365.ops.version: ''
ms.openlocfilehash: 17ca0a105521f3216dfefcc170d60c1eb7137bf6
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/01/2021
ms.locfileid: "5809767"
---
# <a name="inventory-aging-report-storage"></a><span data-ttu-id="ba508-103">Almacenamiento de informe de vencimiento de inventario</span><span class="sxs-lookup"><span data-stu-id="ba508-103">Inventory aging report storage</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="ba508-104">En Microsoft Dynamics 365 Supply Chain Management, puede ejecutar un informe de **Almacenamiento de informe de vencimiento de inventario** y generar resultados como un formulario y gráfico.</span><span class="sxs-lookup"><span data-stu-id="ba508-104">In Microsoft Dynamics 365 Supply Chain Management, you can run an **Inventory aging report storage** report and make the output available as a form and a chart.</span></span> <span data-ttu-id="ba508-105">En el formulario, las columnas y saldos agregados se ajustan dinámicamente, en función del diseño que se configura.</span><span class="sxs-lookup"><span data-stu-id="ba508-105">In the form, columns and aggregate balances are dynamically adjusted, depending on the layout that is configured.</span></span> <span data-ttu-id="ba508-106">El gráfico proporciona una visión general visual que admite el filtrado y permite explorar en profundidad los detalles.</span><span class="sxs-lookup"><span data-stu-id="ba508-106">The chart provides a visual overview that supports filtering and lets you drill down into details.</span></span> <span data-ttu-id="ba508-107">Además, una entidad de datos que se denomina **Informe de vencimiento de inventario** permite exportar los resultados de una ejecución de informe de **Almacenamiento de informe de vencimiento de inventario** en un formato como un archivo Microsoft Excel o PDF.</span><span class="sxs-lookup"><span data-stu-id="ba508-107">Additionally, a data entity that is named **Inventory aging report** lets you export the results of an **Inventory aging report storage** report run to a format such as a Microsoft Excel file or a PDF file.</span></span>

<span data-ttu-id="ba508-108">Este método de ejecutar un informe de **Almacenamiento de informe de vencimiento de inventario** resulta útil cuando los resultados contienen muchas líneas.</span><span class="sxs-lookup"><span data-stu-id="ba508-108">This method of running an **Inventory aging report storage** report is helpful in cases where the output contains many lines.</span></span> <span data-ttu-id="ba508-109">Por ejemplo, el resultado contendrá muchas líneas si tiene 50 000 artículos y 300 tiendas que se crean como almacenes, y solicita vencimientos de inventario por elemento, sitio y almacén.</span><span class="sxs-lookup"><span data-stu-id="ba508-109">For example, the output will contain many lines if you have 50,000 items and 300 stores that are created as warehouses, and you request inventory aging by item, site, and warehouse.</span></span>

## <a name="enable-the-inventory-value-storage-report-feature"></a><span data-ttu-id="ba508-110">Habilitar la función de informe de almacenamiento de valor de inventario</span><span class="sxs-lookup"><span data-stu-id="ba508-110">Enable the Inventory value storage report feature</span></span>

<span data-ttu-id="ba508-111">Antes de poder usar esta función debe habilitarla en su sistema.</span><span class="sxs-lookup"><span data-stu-id="ba508-111">Before you can use this feature, you must enable it on your system.</span></span> <span data-ttu-id="ba508-112">Los administradores pueden usar la configuración de [gestión de funciones](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) para verificar el estado de la función y habilitarla si es necesario.</span><span class="sxs-lookup"><span data-stu-id="ba508-112">Administrators can use the [feature management](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) settings to check the feature status and enable it if needed.</span></span> <span data-ttu-id="ba508-113">Aquí, la función aparece como:</span><span class="sxs-lookup"><span data-stu-id="ba508-113">Here, the feature is listed as:</span></span>

- <span data-ttu-id="ba508-114">**Módulo** - Gestión de costes</span><span class="sxs-lookup"><span data-stu-id="ba508-114">**Module** - Cost management</span></span>
- <span data-ttu-id="ba508-115">**Nombre de la característica**: Almacenamiento de informe de vencimiento de inventario</span><span class="sxs-lookup"><span data-stu-id="ba508-115">**Feature name** - Inventory aging report storage</span></span>

## <a name="run-an-inventory-aging-report-storage"></a><span data-ttu-id="ba508-116">Ejecutar un almacenamiento de informe de vencimiento de inventario</span><span class="sxs-lookup"><span data-stu-id="ba508-116">Run an Inventory aging report storage</span></span>

1. <span data-ttu-id="ba508-117">Vaya a **Gestión de costes \> Consultas e informes \> Almacenamiento del informe de vencimiento de inventario**.</span><span class="sxs-lookup"><span data-stu-id="ba508-117">Go to **Cost management \> Inquiries and reports \> Inventory aging report storage**.</span></span>
1. <span data-ttu-id="ba508-118">Seleccione **Nuevo**.</span><span class="sxs-lookup"><span data-stu-id="ba508-118">Select **New**.</span></span>
1. <span data-ttu-id="ba508-119">En el campo **Identificador de procesos: nombre**, especifique un nombre único para informe.</span><span class="sxs-lookup"><span data-stu-id="ba508-119">In the **Process Identifier – Name** field, enter a unique name for the report.</span></span>
1. <span data-ttu-id="ba508-120">Seleccione el informe **Identificación: Id.** y fíltrelo como sea necesario.</span><span class="sxs-lookup"><span data-stu-id="ba508-120">Select the **Identification – ID** report, and filter it as you require.</span></span>

    <span data-ttu-id="ba508-121">La ejecución de informes se realiza siempre en un trabajo por lotes.</span><span class="sxs-lookup"><span data-stu-id="ba508-121">Report execution is always done in a batch job.</span></span>

1. <span data-ttu-id="ba508-122">Después de que el trabajo por lotes se complete, se mostrará el resultado en la página **Almacenamiento del informe de vencimiento de inventario**.</span><span class="sxs-lookup"><span data-stu-id="ba508-122">After the batch job is completed, the output is shown on the **Inventory aging report storage** page.</span></span>
1. <span data-ttu-id="ba508-123">Para ver el resultado como un formulario con un diseño tradicional de la cuadrículas, seleccione **Ver detalles**.</span><span class="sxs-lookup"><span data-stu-id="ba508-123">To view the output as a form that has a traditional grid layout, select **View details**.</span></span> <span data-ttu-id="ba508-124">Para ver el resultado como un gráfico agregado, seleccione **Ver gráfico**.</span><span class="sxs-lookup"><span data-stu-id="ba508-124">To view the output as an aggregated chart, select **View chart**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="ba508-125">El formulario no incluirá los subtotales definidos en el diseño del informe.</span><span class="sxs-lookup"><span data-stu-id="ba508-125">The form won't include subtotals that are defined in the report layout.</span></span>

<span data-ttu-id="ba508-126">La entidad de los datos **Informe de vencimiento de inventario** le permite exportar el resultado de un informe de **Almacenamiento de informe de vencimiento de inventario** aplicando un filtro para el campo **Identificador de procesos: nombre** a cualquier formato que admita la administración de datos.</span><span class="sxs-lookup"><span data-stu-id="ba508-126">The **Inventory aging report** data entity lets you export the output of an **Inventory aging report storage** report by applying a filter for the **Process Identifier – Name** field to any format that Data management supports.</span></span>


[!INCLUDE[footer-include](../../includes/footer-banner.md)]