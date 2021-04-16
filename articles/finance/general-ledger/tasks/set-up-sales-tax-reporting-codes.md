---
title: Configurar códigos de notificación de impuestos
description: Los códigos de notificación de impuestos hacen referencia a un número de campo enumerado en un informe de impuestos.
author: twheeloc
ms.date: 08/08/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: TaxReportCollection
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: roschlom
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 1e040bac6ef9e950e8d7f97e3c136636acf1fe43
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/01/2021
ms.locfileid: "5813540"
---
# <a name="set-up-sales-tax-reporting-codes"></a><span data-ttu-id="f3685-103">Configurar códigos de notificación de impuestos</span><span class="sxs-lookup"><span data-stu-id="f3685-103">Set up sales tax reporting codes</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="f3685-104">Los códigos de notificación de impuestos hacen referencia a un número de campo enumerado en un informe de impuestos.</span><span class="sxs-lookup"><span data-stu-id="f3685-104">The Sales tax reporting codes refer to a field number that's listed on a sales tax report.</span></span> <span data-ttu-id="f3685-105">Se utilizan en diseños de informes específicos de cada país.</span><span class="sxs-lookup"><span data-stu-id="f3685-105">They are used on country-specific report layouts.</span></span> <span data-ttu-id="f3685-106">También se utilizan en el informe Pago de impuestos por código.</span><span class="sxs-lookup"><span data-stu-id="f3685-106">They're also used on the Sales tax payment by code report.</span></span> <span data-ttu-id="f3685-107">Ese informe muestra los importes de los impuestos para un período de liquidación, resumido para cada código de informe.</span><span class="sxs-lookup"><span data-stu-id="f3685-107">That report shows sales tax amounts for a settlement period summarized for each reporting code.</span></span> <span data-ttu-id="f3685-108">Una vez creados los códigos de notificación de impuestos, puede hacer referencia a ellos en las fichas desplegables de configuración de informes, a las que puede acceder desde la página **Código de impuestos**.</span><span class="sxs-lookup"><span data-stu-id="f3685-108">After you create Sales tax reporting codes, you can refer to those codes on the Report setup FastTabs, which you can access from the **Sales tax code** page.</span></span> 

<span data-ttu-id="f3685-109">Esta grabación usa la empresa de demostración DEMF.</span><span class="sxs-lookup"><span data-stu-id="f3685-109">This recording uses the DEMF demo company.</span></span>

1. <span data-ttu-id="f3685-110">En el **Panel de navegación**, vaya a **Impuestos > Configuración > Impuestos > Códigos de notificación de impuestos**.</span><span class="sxs-lookup"><span data-stu-id="f3685-110">In the **Navigation pane**, go to **Tax > Setup > Sales tax > Sales tax reporting codes**.</span></span>
2. <span data-ttu-id="f3685-111">Haga clic en **Nuevo**.</span><span class="sxs-lookup"><span data-stu-id="f3685-111">Click **New**.</span></span>
3. <span data-ttu-id="f3685-112">Seleccione el diseño del informe al que pertenece el código de notificación.</span><span class="sxs-lookup"><span data-stu-id="f3685-112">Select the report layout that the reporting code belongs to.</span></span> <span data-ttu-id="f3685-113">Este diseño se usa para filtrar los códigos de notificación disponibles para un código de impuestos.</span><span class="sxs-lookup"><span data-stu-id="f3685-113">This layout is used to filter the available reporting codes for a sales tax code.</span></span> <span data-ttu-id="f3685-114">Cada código de impuestos corresponde a un período de liquidación que pertenece a una autoridad fiscal, que utiliza un diseño de informe.</span><span class="sxs-lookup"><span data-stu-id="f3685-114">Each sales tax code belongs to a settlement period, which belongs to a Sales tax authority, which uses a report layout.</span></span>  
4. <span data-ttu-id="f3685-115">En el campo **Código de notificación**, introduzca un número.</span><span class="sxs-lookup"><span data-stu-id="f3685-115">In the **Reporting code** field, enter a number.</span></span>
5. <span data-ttu-id="f3685-116">En el campo de **Texto del informe**, escriba una descripción para mostrar en los informes.</span><span class="sxs-lookup"><span data-stu-id="f3685-116">In the **Report text** field, enter a description to display on reports.</span></span>
6. <span data-ttu-id="f3685-117">En el campo **Descripción breve**, escriba una descripción para fines internos.</span><span class="sxs-lookup"><span data-stu-id="f3685-117">In the **Brief description** field, enter a description for internal purposes.</span></span>
7. <span data-ttu-id="f3685-118">Haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="f3685-118">Click **Save**.</span></span>



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]