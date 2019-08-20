---
title: Vista de activos
description: En este tema se describe la vista de activos en Administración de activos.
author: josaw1
manager: AnnBe
ms.date: 06/26/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CatProcureCatalogEdit, CatProcureCatalogListPage
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 2214
ms.assetid: 2f3e0441-414d-402b-b28b-7ab0d650d658
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 63e5ec5b2a47706763df8105932d722986535a9b
ms.sourcegitcommit: 747bcd25ce7c6c20ce9eaa0027e730f74d4fd6aa
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/23/2019
ms.locfileid: "1783571"
---
# <a name="asset-view"></a><span data-ttu-id="04771-103">Vista de activos</span><span class="sxs-lookup"><span data-stu-id="04771-103">Asset view</span></span>

[!include [banner](../../includes/banner.md)]

[!include [banner](../../includes/preview-banner.md)]

<span data-ttu-id="04771-104">En este tema se describe la vista de activos en Administración de activos.</span><span class="sxs-lookup"><span data-stu-id="04771-104">This topic describes the asset view in Asset Management.</span></span> <span data-ttu-id="04771-105">La página **Vista de activo** muestra los activos activos y las ubicaciones funcionales en una vista de árbol.</span><span class="sxs-lookup"><span data-stu-id="04771-105">The **Asset view** page shows active assets and functional locations in a tree view.</span></span> <span data-ttu-id="04771-106">Por lo tanto, puede obtener fácilmente una visión general de las relaciones de los activos con las ubicaciones funcionales.</span><span class="sxs-lookup"><span data-stu-id="04771-106">Therefore, you can easily get an overview of asset relations to functional locations.</span></span> <span data-ttu-id="04771-107">Además, puede ver información detallada sobre ubicaciones funcionales, activos y listas de materiales relacionadas (BOM).</span><span class="sxs-lookup"><span data-stu-id="04771-107">Additionally, you can view detailed information about functional locations, assets, and related bills of materials (BOMs).</span></span> <span data-ttu-id="04771-108">También puede obtener una visión general rápida de las solicitudes de mantenimiento y órdenes de trabajo activas relacionadas con un activo.</span><span class="sxs-lookup"><span data-stu-id="04771-108">You can also get a quick overview of active maintenance requests and work orders that are related to an asset.</span></span>

1. <span data-ttu-id="04771-109">Seleccione **Administración de activos** \> **Común** \> **Activos** \> **Todos los activos**.</span><span class="sxs-lookup"><span data-stu-id="04771-109">Select **Asset management** \> **Common** \> **Assets** \> **Asset view**.</span></span>
2. <span data-ttu-id="04771-110">Para cambiar la vista que se muestra en la página, seleccione un nuevo valor en el campo **Vista** .</span><span class="sxs-lookup"><span data-stu-id="04771-110">To change the view that is shown on the page, select a new value in the **View** field.</span></span>

    > [!NOTE]
    > <span data-ttu-id="04771-111">La vista predeterminada que se mostrará al abrir la página **Vista de activo** depende del valor seleccionado en el campo **Vista** en la pestaña **Activos** de la página **Parámetros de administración de activos** (**Administración de activos** \> **Configuración** \> **Parámetros de administración de activos**).</span><span class="sxs-lookup"><span data-stu-id="04771-111">The default view that is shown when you open the **Asset view** page depends on the value that is selected in the **View** field on the **Assets** tab of the **Asset management parameters** page (**Asset management** \> **Setup** \> **Asset management parameters**).</span></span>

<span data-ttu-id="04771-112">En el lado derecho de la página, las fichas desplegables muestran los detalles de la vista seleccionada.</span><span class="sxs-lookup"><span data-stu-id="04771-112">On the right side of the page, FastTabs shows details of the selected view.</span></span>

<span data-ttu-id="04771-113">La ruta de navegación que aparece sobre la vista de árbol muestra la selección actual en la vista de árbol.</span><span class="sxs-lookup"><span data-stu-id="04771-113">The breadcrumb trail that appears above the tree view shows the current selection in the tree view.</span></span> <span data-ttu-id="04771-114">Esta ruta de navegación utiliza el formato siguiente:</span><span class="sxs-lookup"><span data-stu-id="04771-114">This breadcrumb trail uses the following format:</span></span>

<span data-ttu-id="04771-115">Id. de ubicación funcional / Id. de ubicación funcional (si hay más de una ubicación técnica) \> Id. de activo / Id. de activo (si hay más de un activo) - Número de artículo.</span><span class="sxs-lookup"><span data-stu-id="04771-115">Functional location ID / Functional location ID (if there is more than one functional location) \> Asset ID / Asset ID (if there is more than one asset) - Item number.</span></span>

<span data-ttu-id="04771-116">Si ha seleccionado un activo en la vista de árbol, puede seleccionar **Solicitudes activas** u **Órdenes de trabajo activas** para ver las solicitudes de mantenimiento o las órdenes de trabajo relacionadas con el activo.</span><span class="sxs-lookup"><span data-stu-id="04771-116">If you've selected an asset in the tree view, you can select **Active requests** or **Active work orders** to view the maintenance requests or work orders that are related to the asset.</span></span> <span data-ttu-id="04771-117">También puede seleccionar **Abrir** \> **Ubicación técnica**, **Activo** o **L. MAT de activos** para abrir la vista relacionada.</span><span class="sxs-lookup"><span data-stu-id="04771-117">You can also select **Open** \> **Functional location**, **Asset**, or **Asset BOM** to open the related view.</span></span>

<span data-ttu-id="04771-118">La opción **Ubicaciones funcionales de activo** que puede seleccionar en el campo **Vista** también está disponible en cualquier búsqueda de activos donde pueda seleccionar un activo.</span><span class="sxs-lookup"><span data-stu-id="04771-118">The **Asset functional locations** option that you can select in the **View** field is also available in any asset lookup where you can select an asset.</span></span> <span data-ttu-id="04771-119">La vista de árbol se muestra en una pestaña **Vista de activo**, por ejemplo, donde [crea un activo](../objects/create-an-object.md), crea una solicitud de mantenimiento o bien crea una orden de trabajo.</span><span class="sxs-lookup"><span data-stu-id="04771-119">The tree view is shown on an **Asset view** tab, for example, where you [create an asset](../objects/create-an-object.md), create a maintenance request, or create a work order.</span></span>
