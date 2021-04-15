---
title: Evaluar rentabilidad de clientes y productos
description: Este artículo explica cómo puede usar los análisis en memoria y en tiempo real para tener acceso, explorar y obtener información acerca de los clientes y de la rentabilidad de productos desde sus datos de Dynamics 365 Commerce.
author: ashishmsft
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: SysOperationsTemplateForm, RetailStoreManagementWorkspace
audience: Application User
ms.reviewer: josaw
ms.custom: 52902
ms.assetid: 1a77d04b-2985-4bee-9138-c216fe0483de
ms.search.region: global
ms.search.industry: Retail
ms.author: asharchw
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.openlocfilehash: 80a2f38f2b3f039b17556116d6aea738faa1db50
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/31/2021
ms.locfileid: "5797338"
---
# <a name="assess-customer-and-product-profitability"></a><span data-ttu-id="702e1-103">Evaluar rentabilidad de clientes y productos</span><span class="sxs-lookup"><span data-stu-id="702e1-103">Assess customer and product profitability</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="702e1-104">Este artículo explica cómo puede usar los análisis en memoria y en tiempo real para tener acceso, explorar y obtener información acerca de los clientes y de la rentabilidad de productos desde sus datos de Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="702e1-104">This article explains how you can use the in-memory and real-time analytics to access, explore, and gain insight about customers and product profitability from your Dynamics 365 Commerce data.</span></span>

<span data-ttu-id="702e1-105">Como parte de Commerce, los usuarios pueden estudiar la rentabilidad de los clientes principales (10 a 100) en distintos niveles de la jerarquía organizativa, en función de uno de los criterios siguientes:</span><span class="sxs-lookup"><span data-stu-id="702e1-105">As part of Commerce, users can study profitability for the top customers (10 to 100) across different levels of the organization hierarchy, based on one of the following criteria:</span></span>

- <span data-ttu-id="702e1-106">Importe de venta</span><span class="sxs-lookup"><span data-stu-id="702e1-106">Sales amount</span></span>
- <span data-ttu-id="702e1-107">Cantidad</span><span class="sxs-lookup"><span data-stu-id="702e1-107">Quantity</span></span>
- <span data-ttu-id="702e1-108">Margen de beneficio bruto</span><span class="sxs-lookup"><span data-stu-id="702e1-108">Gross profit margin</span></span>
- <span data-ttu-id="702e1-109">Porcentaje de margen</span><span class="sxs-lookup"><span data-stu-id="702e1-109">Margin percentage</span></span>

<span data-ttu-id="702e1-110">Para esta evaluación, puede usar el informe listo para usar **Clientes principales**, que puede abrir desde cualquiera de las siguientes ubicaciones:</span><span class="sxs-lookup"><span data-stu-id="702e1-110">For this assessment, you can use the out-of-box **Top customers** report, which you can open from any of the following locations:</span></span>

- <span data-ttu-id="702e1-111">Espacio de trabajo **Administración de tiendas** &gt; **Retail y Commerce** &gt; **Canales** &gt; **Administración de tiendas** &gt; **Informes** &gt; **Informe de mejores clientes**</span><span class="sxs-lookup"><span data-stu-id="702e1-111">**Store management** workspace &gt; **Retail and Commerce** &gt; **Channels** &gt; **Store management** &gt; **Reports** &gt; **Top customers report**</span></span>
- <span data-ttu-id="702e1-112">Sección **Consultas e informes** &gt; **Retail y Commerce** &gt; **Consultas e informes** &gt; **Informes de ventas** &gt; **Informe de clientes principales**</span><span class="sxs-lookup"><span data-stu-id="702e1-112">**Inquiries and reports** section &gt; **Retail and Commerce** &gt; **Inquiries and reports** &gt; **Sales reports** &gt; **Top customers report**</span></span>

<span data-ttu-id="702e1-113">Igualmente, los usuarios pueden estudiar la rentabilidad de los peroductos (10 a 100) en distintos niveles de la jerarquía organizativa, en función de uno de los criterios siguientes:</span><span class="sxs-lookup"><span data-stu-id="702e1-113">Likewise, users can study profitability for the top products (10 to 100) across different levels of the organization hierarchy, based on one of the following criteria:</span></span>

- <span data-ttu-id="702e1-114">Importe de venta</span><span class="sxs-lookup"><span data-stu-id="702e1-114">Sales amount</span></span>
- <span data-ttu-id="702e1-115">Cantidad</span><span class="sxs-lookup"><span data-stu-id="702e1-115">Quantity</span></span>
- <span data-ttu-id="702e1-116">Margen de beneficio bruto</span><span class="sxs-lookup"><span data-stu-id="702e1-116">Gross profit margin</span></span>
- <span data-ttu-id="702e1-117">Porcentaje de margen</span><span class="sxs-lookup"><span data-stu-id="702e1-117">Margin percentage</span></span>

<span data-ttu-id="702e1-118">Para esta evaluación, puede usar el informe listo para usar **Productos principales** report, which you can open from any of the following locations:</span><span class="sxs-lookup"><span data-stu-id="702e1-118">For this assessment, you can use the out-of-box **Top products** report, which you can open from any of the following locations:</span></span>

- <span data-ttu-id="702e1-119">Espacio de trabajo **Administración de tiendas** &gt; **Retail y Commerce** &gt; **Canales** &gt; **Administración de tiendas** &gt; **Informes** &gt; **Informe de productos principales**</span><span class="sxs-lookup"><span data-stu-id="702e1-119">**Store management** workspace &gt; **Retail and Commerce** &gt; **Channels** &gt; **Store management** &gt; **Reports** &gt; **Top products report**</span></span>
- <span data-ttu-id="702e1-120">Espacio de trabajo **Administración de categorías y productos** &gt; **Retail y Commerce** &gt; **Productos y categorías** &gt; **Administración de tiendas** &gt; **Informes** &gt; **Informe de productos principales**</span><span class="sxs-lookup"><span data-stu-id="702e1-120">**Category and product management** workspace &gt; **Retail and Commerce** &gt; **Products and categories** &gt; **Store management** &gt; **Reports** &gt; **Top products report**</span></span>
- <span data-ttu-id="702e1-121">Sección **Consultas e informes** &gt; **Retail y Commerce** &gt; **Consultas e informes** &gt; **Informes de ventas** &gt; **Informe de productos principales**</span><span class="sxs-lookup"><span data-stu-id="702e1-121">**Inquiries and reports** section &gt; **Retail and Commerce** &gt; **Inquiries and reports** &gt; **Sales reports** &gt; **Top products report**</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]