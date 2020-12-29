---
title: Configurar nombres de diarios de arrendamiento
description: Este tema explica cómo definir nombres de diarios de arrendamiento. Los nombres de los diarios de arrendamiento especifican los diarios en los que se contabilizan las entradas que se originan en Arrendamiento de activos.
author: moaamer
manager: Ann Beebe
ms.date: 10/28/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations, Retail
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2020-10-28
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: e8b1b908dfd6d1d6072b6efa83f13ae5784c85c1
ms.sourcegitcommit: aeee39c01d3f93a6dfcf2013965fa975a740596a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/28/2020
ms.locfileid: "4447795"
---
# <a name="set-up-lease-journal-names"></a><span data-ttu-id="9eb36-104">Configurar nombres de diarios de arrendamiento</span><span class="sxs-lookup"><span data-stu-id="9eb36-104">Set up lease journal names</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="9eb36-105">Los nombres de los diarios de arrendamiento especifican los diarios en los que se contabilizan las transacciones que se originan en Arrendamiento de activos.</span><span class="sxs-lookup"><span data-stu-id="9eb36-105">Lease journal names specify the journals that Asset leasing transactions are posted to.</span></span> <span data-ttu-id="9eb36-106">Solo los nombres de diarios asignados al tipo de diario **Arrendamiento de activos** aparecen en los campos **Reconocimiento inicial** y **Nombre del diario mensual** de la página **Parámetros de arrendamiento de activos**.</span><span class="sxs-lookup"><span data-stu-id="9eb36-106">Only journal names that are assigned to the **Asset leasing** journal type appear in the **Initial Recognition** and **Monthly Journal Name** fields on the **Asset leasing parameters** page.</span></span> <span data-ttu-id="9eb36-107">Solamente el tipo de diario **Registro de facturas de proveedores** se puede asignar al campo **Nombre del diario de facturas**.</span><span class="sxs-lookup"><span data-stu-id="9eb36-107">Only **vendor invoice recording** journal type can be assigned to the **Invoice journal name** field.</span></span>

<span data-ttu-id="9eb36-108">Para configurar los nombres de los diarios de arrendamiento, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="9eb36-108">To configure lease journal names, follow these steps.</span></span>

1. <span data-ttu-id="9eb36-109">Vaya a **Arrendamiento de activos \> Configuración \> Parámetros de arrendamiento de activos**.</span><span class="sxs-lookup"><span data-stu-id="9eb36-109">Go to **Asset leasing \> Setup \> Asset leasing parameters**.</span></span>
2. <span data-ttu-id="9eb36-110">En la pestaña **General**, en el campo **Nombre del diario de reconocimiento inicial**, seleccione un diario.</span><span class="sxs-lookup"><span data-stu-id="9eb36-110">On the **General** tab, in the **Initial recognition journal name** field, and select a journal.</span></span> <span data-ttu-id="9eb36-111">Todas las entradas del diario de reconocimiento inicial se registrarán en este nombre de diario.</span><span class="sxs-lookup"><span data-stu-id="9eb36-111">All initial recognition journal entries will be posted to this journal name.</span></span>
3. <span data-ttu-id="9eb36-112">En el campo **Nombre de diario de facturas**, seleccione un diario.</span><span class="sxs-lookup"><span data-stu-id="9eb36-112">In the **Invoice journal name** field, select a journal.</span></span> <span data-ttu-id="9eb36-113">Si la opción **Pagar al proveedor** está configurada en **Sí** para el libro de arrendamiento, las facturas de pago de arrendamiento y gastos se publicarán en este nombre de diario.</span><span class="sxs-lookup"><span data-stu-id="9eb36-113">If the **Pay to vendor** option is set to **Yes** for the lease book, lease and expense payment invoices will be posted to this journal name.</span></span>
4. <span data-ttu-id="9eb36-114">En el campo **Nombre de diario de arrendamiento**, seleccione un diario.</span><span class="sxs-lookup"><span data-stu-id="9eb36-114">In the **Lease journal name** field, select a journal.</span></span> <span data-ttu-id="9eb36-115">Todos los movimientos de depreciación, intereses y reclasificación a corto plazo se registrarán en este nombre de diario.</span><span class="sxs-lookup"><span data-stu-id="9eb36-115">All depreciation, interest, and short-term reclassification entries will be posted to this journal name.</span></span> <span data-ttu-id="9eb36-116">Si la opción **Pagar al proveedor** está configurada en **No** para el libro de arrendamiento, las movimientos de pagos de arrendamientos y de pagos de gastos se publicarán en este nombre de diario.</span><span class="sxs-lookup"><span data-stu-id="9eb36-116">If the **Pay to vendor** option is set to **No** for the lease book, lease payments and expense payment entries will also be posted to this journal name.</span></span>
