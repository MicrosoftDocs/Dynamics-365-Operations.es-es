---
title: Supervisar las ventas y el rendimiento de margen
description: Puede supervisar ventas y rendimiento de margen en tiempo real con Microsoft Dynamics 365 for Retail.
author: ashishmsft
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
ms.search.form: RetailSales
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: 85123
ms.assetid: ddd15820-c3e6-4607-819e-8cef744ce9c9
ms.search.region: global
ms.search.industry: Retail
ms.author: asharchw
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.openlocfilehash: e2b3591f6403542c79457d12ae850ad40d9253a1
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/29/2019
ms.locfileid: "357275"
---
# <a name="monitor-sales-and-margin-performance"></a><span data-ttu-id="f0dce-103">Supervisar las ventas y el rendimiento de margen</span><span class="sxs-lookup"><span data-stu-id="f0dce-103">Monitor sales and margin performance</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="f0dce-104">Puede supervisar ventas y rendimiento de margen en tiempo real con Microsoft Dynamics 365 for Retail.</span><span class="sxs-lookup"><span data-stu-id="f0dce-104">You can monitor sales and margin performance in real time using Microsoft Dynamics 365 for Retail.</span></span>

<span data-ttu-id="f0dce-105">Como parte de Dynamics 365 for Retail, los usuarios pueden supervisar las ventas y el rendimiento de margen en tiempo real en diferentes niveles de la jerarquía organizativa para las siguientes dimensiones:</span><span class="sxs-lookup"><span data-stu-id="f0dce-105">As part of Dynamics 365 for Retail, users can monitor sales and margin performance in real time across different levels of the organization hierarchy for the following dimensions:</span></span>

- <span data-ttu-id="f0dce-106">Productos</span><span class="sxs-lookup"><span data-stu-id="f0dce-106">Products</span></span>
- <span data-ttu-id="f0dce-107">Categorías</span><span class="sxs-lookup"><span data-stu-id="f0dce-107">Categories</span></span>
- <span data-ttu-id="f0dce-108">Descuentos</span><span class="sxs-lookup"><span data-stu-id="f0dce-108">Discounts</span></span>
- <span data-ttu-id="f0dce-109">Años como período de tiempo</span><span class="sxs-lookup"><span data-stu-id="f0dce-109">Years as time period</span></span>
- <span data-ttu-id="f0dce-110">Registros o terminales</span><span class="sxs-lookup"><span data-stu-id="f0dce-110">Registers/terminals</span></span>
- <span data-ttu-id="f0dce-111">Personal o empleados</span><span class="sxs-lookup"><span data-stu-id="f0dce-111">Staff/employees</span></span>
- <span data-ttu-id="f0dce-112">Clientes</span><span class="sxs-lookup"><span data-stu-id="f0dce-112">Customers</span></span>
- <span data-ttu-id="f0dce-113">Unidades operativas</span><span class="sxs-lookup"><span data-stu-id="f0dce-113">Operating units</span></span>

<span data-ttu-id="f0dce-114">Además, dos informes únicos que se aprovechan de la estructuración de cuadrícula jerárquica permiten a los usuarios supervisar las ventas y el rendimiento de margen explorando en profundidad desde el nodo de la categoría superior hasta los nodos de hoja individuales de la jerarquía de categoría de productos de venta minorista predeterminada.</span><span class="sxs-lookup"><span data-stu-id="f0dce-114">Additionally, two unique reports that take advantage of hierarchical grid structuring let users monitor sales and margin performance by drilling down from the top category node to individual leaf nodes of the category in the default retail product category hierarchy.</span></span> <span data-ttu-id="f0dce-115">Los usuarios también pueden explorar en profundidad la unidad operativa superior hasta un canal individual de la jerarquía organizativa que se define como la jerarquía organizativa predeterminada para fines de la jerarquía de informes de venta minorista.</span><span class="sxs-lookup"><span data-stu-id="f0dce-115">Users can also drill-down from the top operating unit to an individual channel in the organization hierarchy that is defined as the default organization hierarchy for retail reporting hierarchy purposes.</span></span> <span data-ttu-id="f0dce-116">Puede abrir los informes desde cualquiera de las ubicaciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="f0dce-116">You can open the reports from any of the following locations:</span></span>

- <span data-ttu-id="f0dce-117">Espacio de trabajo **Gestión de tienda de venta minorista** &gt; **Retail** &gt; **Canales** &gt; **Gestión de tienda de venta minorista** &gt; **Informes**</span><span class="sxs-lookup"><span data-stu-id="f0dce-117">**Retail store management** workspace &gt; **Retail** &gt; **Channels** &gt; **Retail store management** &gt; **Reports**</span></span>
- <span data-ttu-id="f0dce-118">Espacio de trabajo **Gestión de producto y categoría** &gt; **Retail** &gt; **Producto y categorías** &gt; **Gestión de tienda de venta** &gt; **Informes**</span><span class="sxs-lookup"><span data-stu-id="f0dce-118">**Category and product management** workspace &gt; **Retail** &gt; **Product and categories** &gt; **Retail store management** &gt; **Reports**</span></span>
- <span data-ttu-id="f0dce-119">Espacio de trabajo **Administración de precios y descuentos** &gt; **Retail** &gt; **Precios y descuentos** &gt; **Gestión de tienda de venta minorista** &gt; **Informes**</span><span class="sxs-lookup"><span data-stu-id="f0dce-119">**Pricing and discount management** workspace &gt; **Retail** &gt; **Pricing and discounts** &gt; **Retail store management** &gt; **Reports**</span></span>
- <span data-ttu-id="f0dce-120">Sección **Consultas e informes** &gt; **Retail** &gt; **Consultas e informes** &gt; **Informes de ventas**</span><span class="sxs-lookup"><span data-stu-id="f0dce-120">**Inquiries and reports** section &gt; **Retail** &gt; **Inquiries and reports** &gt; **Sales reports**</span></span>
