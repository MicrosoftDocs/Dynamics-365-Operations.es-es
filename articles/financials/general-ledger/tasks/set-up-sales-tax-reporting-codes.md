---
title: Configurar códigos de notificación de impuestos
description: Los códigos de notificación de impuestos hacen referencia a un número de campo en un informe de impuestos.
author: twheeloc
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: TaxReportCollection
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: vstehman
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 4543cf7eaa0b1ef8e32d3fdafa2c354cd3739256
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/29/2019
ms.locfileid: "335678"
---
# <a name="set-up-sales-tax-reporting-codes"></a><span data-ttu-id="fe69a-103">Configurar códigos de notificación de impuestos</span><span class="sxs-lookup"><span data-stu-id="fe69a-103">Set up sales tax reporting codes</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="fe69a-104">Los códigos de notificación de impuestos hacen referencia a un número de campo en un informe de impuestos.</span><span class="sxs-lookup"><span data-stu-id="fe69a-104">The Sales tax reporting codes refer to a field number on a sales tax report.</span></span> <span data-ttu-id="fe69a-105">Se usan en diseños de informe específicos de país y en el pago de impuestos por informe de código para imprimir los importes de impuestos para un período de liquidación resumido por código de notificación.</span><span class="sxs-lookup"><span data-stu-id="fe69a-105">They are used on country specific report layouts and the Sales tax payment by code report to print sales tax amounts for a settlement period summarized per reporting code.</span></span> <span data-ttu-id="fe69a-106">Una vez creados los códigos de notificación de impuestos, puede hacer referencia a ellos en las fichas desplegables- Configuración del informe de la página Código de impuestos.</span><span class="sxs-lookup"><span data-stu-id="fe69a-106">After you create Sales tax reporting codes, you can refer to them on the Report setup FastTabs in the Sales tax code page.</span></span> 

<span data-ttu-id="fe69a-107">Esta grabación usa la empresa de demostración DEMF.</span><span class="sxs-lookup"><span data-stu-id="fe69a-107">This recording uses the DEMF demo company.</span></span>



1. <span data-ttu-id="fe69a-108">Vaya a Impuestos > Configuración > Impuestos > Códigos de notificación de impuestos.</span><span class="sxs-lookup"><span data-stu-id="fe69a-108">Go to Tax > Setup > Sales tax > Sales tax reporting codes.</span></span>
2. <span data-ttu-id="fe69a-109">Haga clic en Nuevo.</span><span class="sxs-lookup"><span data-stu-id="fe69a-109">Click New.</span></span>
3. <span data-ttu-id="fe69a-110">Seleccione el diseño del informe al que pertenece el código de notificación.</span><span class="sxs-lookup"><span data-stu-id="fe69a-110">Select the report layout that the reporting code belongs to.</span></span>
    * <span data-ttu-id="fe69a-111">Este diseño se usa para filtrar los códigos de notificación disponibles para un código de impuestos.</span><span class="sxs-lookup"><span data-stu-id="fe69a-111">This layout is used to filter the available reporting codes for a Sales tax code.</span></span> <span data-ttu-id="fe69a-112">Cada código de impuestos corresponde a un período de liquidación que pertenece a una autoridad fiscal que usa un diseño de informe.</span><span class="sxs-lookup"><span data-stu-id="fe69a-112">Each Sales tax code belongs to a settlement period which belongs to a Sales tax authority which uses a Report layout.</span></span>  
4. <span data-ttu-id="fe69a-113">Especifique un número que haga referencia a un campo del informe de impuestos.</span><span class="sxs-lookup"><span data-stu-id="fe69a-113">Enter a number that refers to a field on a sales tax report.</span></span>
5. <span data-ttu-id="fe69a-114">En el campo de texto del informe, escriba una descripción para mostrar en los informes.</span><span class="sxs-lookup"><span data-stu-id="fe69a-114">In the Report text field, enter a description to display on reports.</span></span>
6. <span data-ttu-id="fe69a-115">En el campo Descripción breve, escriba una descripción para fines internos.</span><span class="sxs-lookup"><span data-stu-id="fe69a-115">In the Brief description field, enter a description for internal purposes.</span></span>
7. <span data-ttu-id="fe69a-116">Haga clic en Guardar.</span><span class="sxs-lookup"><span data-stu-id="fe69a-116">Click Save.</span></span>

