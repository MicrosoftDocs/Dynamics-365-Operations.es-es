---
title: Configurar códigos de notificación de impuestos
description: Los códigos de notificación de impuestos hacen referencia a un número de campo enumerado en un informe de impuestos.
author: twheeloc
manager: AnnBe
ms.date: 08/08/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: TaxReportCollection
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: roschlom
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: be24e18da63d1a613c3c6e72f7c767c7af9b6656
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2021
ms.locfileid: "5222152"
---
# <a name="set-up-sales-tax-reporting-codes"></a><span data-ttu-id="af057-103">Configurar códigos de notificación de impuestos</span><span class="sxs-lookup"><span data-stu-id="af057-103">Set up sales tax reporting codes</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="af057-104">Los códigos de notificación de impuestos hacen referencia a un número de campo enumerado en un informe de impuestos.</span><span class="sxs-lookup"><span data-stu-id="af057-104">The Sales tax reporting codes refer to a field number that's listed on a sales tax report.</span></span> <span data-ttu-id="af057-105">Se utilizan en diseños de informes específicos de cada país.</span><span class="sxs-lookup"><span data-stu-id="af057-105">They are used on country-specific report layouts.</span></span> <span data-ttu-id="af057-106">También se utilizan en el informe Pago de impuestos por código.</span><span class="sxs-lookup"><span data-stu-id="af057-106">They're also used on the Sales tax payment by code report.</span></span> <span data-ttu-id="af057-107">Ese informe muestra los importes de los impuestos para un período de liquidación, resumido para cada código de informe.</span><span class="sxs-lookup"><span data-stu-id="af057-107">That report shows sales tax amounts for a settlement period summarized for each reporting code.</span></span> <span data-ttu-id="af057-108">Una vez creados los códigos de notificación de impuestos, puede hacer referencia a ellos en las fichas desplegables de configuración de informes, a las que puede acceder desde la página **Código de impuestos**.</span><span class="sxs-lookup"><span data-stu-id="af057-108">After you create Sales tax reporting codes, you can refer to those codes on the Report setup FastTabs, which you can access from the **Sales tax code** page.</span></span> 

<span data-ttu-id="af057-109">Esta grabación usa la empresa de demostración DEMF.</span><span class="sxs-lookup"><span data-stu-id="af057-109">This recording uses the DEMF demo company.</span></span>

1. <span data-ttu-id="af057-110">En el **Panel de navegación**, vaya a **Impuestos > Configuración > Impuestos > Códigos de notificación de impuestos**.</span><span class="sxs-lookup"><span data-stu-id="af057-110">In the **Navigation pane**, go to **Tax > Setup > Sales tax > Sales tax reporting codes**.</span></span>
2. <span data-ttu-id="af057-111">Haga clic en **Nuevo**.</span><span class="sxs-lookup"><span data-stu-id="af057-111">Click **New**.</span></span>
3. <span data-ttu-id="af057-112">Seleccione el diseño del informe al que pertenece el código de notificación.</span><span class="sxs-lookup"><span data-stu-id="af057-112">Select the report layout that the reporting code belongs to.</span></span> <span data-ttu-id="af057-113">Este diseño se usa para filtrar los códigos de notificación disponibles para un código de impuestos.</span><span class="sxs-lookup"><span data-stu-id="af057-113">This layout is used to filter the available reporting codes for a sales tax code.</span></span> <span data-ttu-id="af057-114">Cada código de impuestos corresponde a un período de liquidación que pertenece a una autoridad fiscal, que utiliza un diseño de informe.</span><span class="sxs-lookup"><span data-stu-id="af057-114">Each sales tax code belongs to a settlement period, which belongs to a Sales tax authority, which uses a report layout.</span></span>  
4. <span data-ttu-id="af057-115">En el campo **Código de notificación**, introduzca un número.</span><span class="sxs-lookup"><span data-stu-id="af057-115">In the **Reporting code** field, enter a number.</span></span>
5. <span data-ttu-id="af057-116">En el campo de **Texto del informe**, escriba una descripción para mostrar en los informes.</span><span class="sxs-lookup"><span data-stu-id="af057-116">In the **Report text** field, enter a description to display on reports.</span></span>
6. <span data-ttu-id="af057-117">En el campo **Descripción breve**, escriba una descripción para fines internos.</span><span class="sxs-lookup"><span data-stu-id="af057-117">In the **Brief description** field, enter a description for internal purposes.</span></span>
7. <span data-ttu-id="af057-118">Haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="af057-118">Click **Save**.</span></span>



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]