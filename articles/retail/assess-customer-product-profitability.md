---
title: Evaluar rentabilidad de clientes y productos
description: "Este artículo explica cómo puede usar los análisis en memoria y en tiempo real para tener acceso, explorar y obtener información acerca de los clientes y de la rentabilidad de productos desde sus datos de Microsoft Dynamics 365 for Retail."
author: ashishmsft
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-365-retail
ms.technology: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: 52902
ms.assetid: 1a77d04b-2985-4bee-9138-c216fe0483de
ms.search.region: global
ms.search.industry: Retail
ms.author: asharchw
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: 04ebc624212e6909eda7589b71cd84a22010e721
ms.contentlocale: es-es
ms.lasthandoff: 11/03/2017

---

# <a name="assess-customer-and-product-profitability"></a><span data-ttu-id="ad6b5-103">Evaluar rentabilidad de clientes y productos</span><span class="sxs-lookup"><span data-stu-id="ad6b5-103">Assess customer and product profitability</span></span>

[!include[banner](includes/banner.md)]


<span data-ttu-id="ad6b5-104">Este artículo explica cómo puede usar los análisis en memoria y en tiempo real para tener acceso, explorar y obtener información acerca de los clientes y de la rentabilidad de productos desde sus datos de Microsoft Dynamics 365 for Retail.</span><span class="sxs-lookup"><span data-stu-id="ad6b5-104">This article explains how you can use the in-memory and real-time analytics to access, explore, and gain insight about customers and product profitability from your Microsoft Dynamics 365 for Retail data.</span></span> 

<span data-ttu-id="ad6b5-105">Como parte de Dynamics 365 for Retail, los usuarios pueden estudiar la rentabilidad de los clientes principales (10 a 100) en distintos niveles de la jerarquía organizativa, en función de uno de los criterios siguientes:</span><span class="sxs-lookup"><span data-stu-id="ad6b5-105">As part of Dynamics 365 for Retail, users can study profitability for the top customers (10 to 100) across different levels of the organization hierarchy, based on one of the following criteria:</span></span>

-   <span data-ttu-id="ad6b5-106">Importe de venta</span><span class="sxs-lookup"><span data-stu-id="ad6b5-106">Sales amount</span></span>
-   <span data-ttu-id="ad6b5-107">Cantidad</span><span class="sxs-lookup"><span data-stu-id="ad6b5-107">Quantity</span></span>
-   <span data-ttu-id="ad6b5-108">Margen de beneficio bruto</span><span class="sxs-lookup"><span data-stu-id="ad6b5-108">Gross profit margin</span></span>
-   <span data-ttu-id="ad6b5-109">Porcentaje de margen</span><span class="sxs-lookup"><span data-stu-id="ad6b5-109">Margin percentage</span></span>

<span data-ttu-id="ad6b5-110">Para esta evaluación, puede usar el informe listo para usar **Clientes principales**, que puede abrir desde cualquiera de las siguientes ubicaciones:</span><span class="sxs-lookup"><span data-stu-id="ad6b5-110">For this assessment, you can use the out-of-box **Top customers** report, which you can open from any of the following locations:</span></span>

-   <span data-ttu-id="ad6b5-111">Espacio de trabajo **Gestión de tienda de venta minorista** &gt; **Retail** &gt; **Canales** &gt; **Gestión de tienda de venta minorista** &gt; **Informes** &gt; **Informe de mejores clientes**</span><span class="sxs-lookup"><span data-stu-id="ad6b5-111">**Retail store management** workspace &gt; **Retail** &gt; **Channels** &gt; **Retail store management** &gt; **Reports** &gt; **Top customers report**</span></span>
-   <span data-ttu-id="ad6b5-112">Sección **Consultas e informes** &gt; **Retail** &gt; **Consultas e informes** &gt; **Informes de ventas** &gt; **Informe de mejores clientes**</span><span class="sxs-lookup"><span data-stu-id="ad6b5-112">**Inquiries and reports** section &gt; **Retail** &gt; **Inquiries and reports** &gt; **Sales reports** &gt; **Top customers report**</span></span>

<span data-ttu-id="ad6b5-113">Igualmente, los usuarios pueden estudiar la rentabilidad de los peroductos (10 a 100) en distintos niveles de la jerarquía organizativa, en función de uno de los criterios siguientes:</span><span class="sxs-lookup"><span data-stu-id="ad6b5-113">Likewise, users can study profitability for the top products (10 to 100) across different levels of the organization hierarchy, based on one of the following criteria:</span></span>

-   <span data-ttu-id="ad6b5-114">Importe de venta</span><span class="sxs-lookup"><span data-stu-id="ad6b5-114">Sales amount</span></span>
-   <span data-ttu-id="ad6b5-115">Cantidad</span><span class="sxs-lookup"><span data-stu-id="ad6b5-115">Quantity</span></span>
-   <span data-ttu-id="ad6b5-116">Margen de beneficio bruto</span><span class="sxs-lookup"><span data-stu-id="ad6b5-116">Gross profit margin</span></span>
-   <span data-ttu-id="ad6b5-117">Porcentaje de margen</span><span class="sxs-lookup"><span data-stu-id="ad6b5-117">Margin percentage</span></span>

<span data-ttu-id="ad6b5-118">Para esta evaluación, puede usar el informe listo para usar **Productos principales** report, which you can open from any of the following locations:</span><span class="sxs-lookup"><span data-stu-id="ad6b5-118">For this assessment, you can use the out-of-box **Top products** report, which you can open from any of the following locations:</span></span>

-   <span data-ttu-id="ad6b5-119">Espacio de trabajo **Gestión de tienda de venta minorista** &gt; **Retail** &gt; **Canales** &gt; **Gestión de tienda de venta minorista** &gt; **Informes** &gt; **Informe de productos principales**</span><span class="sxs-lookup"><span data-stu-id="ad6b5-119">**Retail store management** workspace &gt; **Retail** &gt; **Channels** &gt; **Retail store management** &gt; **Reports** &gt; **Top products report**</span></span>
-   <span data-ttu-id="ad6b5-120">Espacio de trabajo **Gestión de producto y categoría** &gt; **Retail** &gt; **Productos y categorías** &gt; **Gestión de tienda de venta** &gt; **Informes** &gt; **Informe de productos principales**</span><span class="sxs-lookup"><span data-stu-id="ad6b5-120">**Category and product management** workspace &gt; **Retail** &gt; **Products and categories** &gt; **Retail store management** &gt; **Reports** &gt; **Top products report**</span></span>
-   <span data-ttu-id="ad6b5-121">Sección **Consultas e informes** &gt; **Retail** &gt; **Consultas e informes** &gt; **Informes de ventas** &gt; **Informe de productos principales**</span><span class="sxs-lookup"><span data-stu-id="ad6b5-121">**Inquiries and reports** section &gt; **Retail** &gt; **Inquiries and reports** &gt; **Sales reports** &gt; **Top products report**</span></span>




