---
title: Configurar códigos de notificación de impuestos
description: Los códigos de notificación de impuestos hacen referencia a un número de campo en un informe de impuestos.
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
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: vstehman
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 460e41d69a78cda664e0d3af828fdc482169ac52
ms.sourcegitcommit: 57e1dafa186fec77ddd8ba9425d238e36e0f0998
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/18/2020
ms.locfileid: "3145084"
---
# <a name="set-up-sales-tax-reporting-codes"></a><span data-ttu-id="3f8a9-103">Configurar códigos de notificación de impuestos</span><span class="sxs-lookup"><span data-stu-id="3f8a9-103">Set up sales tax reporting codes</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="3f8a9-104">Los códigos de notificación de impuestos hacen referencia a un número de campo en un informe de impuestos.</span><span class="sxs-lookup"><span data-stu-id="3f8a9-104">The Sales tax reporting codes refer to a field number on a sales tax report.</span></span> <span data-ttu-id="3f8a9-105">Se usan en diseños de informe específicos de país y en el pago de impuestos por informe de código para imprimir los importes de impuestos para un período de liquidación resumido por código de notificación.</span><span class="sxs-lookup"><span data-stu-id="3f8a9-105">They are used on country specific report layouts and the Sales tax payment by code report to print sales tax amounts for a settlement period summarized per reporting code.</span></span> <span data-ttu-id="3f8a9-106">Una vez creados los códigos de notificación de impuestos, puede hacer referencia a ellos en las fichas desplegables- Configuración del informe de la página Código de impuestos.</span><span class="sxs-lookup"><span data-stu-id="3f8a9-106">After you create Sales tax reporting codes, you can refer to them on the Report setup FastTabs in the Sales tax code page.</span></span> 

<span data-ttu-id="3f8a9-107">Esta grabación usa la empresa de demostración DEMF.</span><span class="sxs-lookup"><span data-stu-id="3f8a9-107">This recording uses the DEMF demo company.</span></span>

1. <span data-ttu-id="3f8a9-108">En el **Panel de navegación**, vaya a **Impuestos > Configuración > Impuestos > Códigos de notificación de impuestos**.</span><span class="sxs-lookup"><span data-stu-id="3f8a9-108">In the **Navigation pane**, go to **Tax > Setup > Sales tax > Sales tax reporting codes**.</span></span>
2. <span data-ttu-id="3f8a9-109">Haga clic en **Nuevo**.</span><span class="sxs-lookup"><span data-stu-id="3f8a9-109">Click **New**.</span></span>
3. <span data-ttu-id="3f8a9-110">Seleccione el diseño del informe al que pertenece el código de notificación.</span><span class="sxs-lookup"><span data-stu-id="3f8a9-110">Select the report layout that the reporting code belongs to.</span></span> <span data-ttu-id="3f8a9-111">Este diseño se usa para filtrar los códigos de notificación disponibles para un código de impuestos.</span><span class="sxs-lookup"><span data-stu-id="3f8a9-111">This layout is used to filter the available reporting codes for a Sales tax code.</span></span> <span data-ttu-id="3f8a9-112">Cada código de impuestos corresponde a un período de liquidación que pertenece a una autoridad fiscal que usa un diseño de informe.</span><span class="sxs-lookup"><span data-stu-id="3f8a9-112">Each Sales tax code belongs to a settlement period which belongs to a Sales tax authority which uses a Report layout.</span></span>  
4. <span data-ttu-id="3f8a9-113">En el campo **Código de notificación**, introduzca un número.</span><span class="sxs-lookup"><span data-stu-id="3f8a9-113">In the **Reporting code** field, enter a number.</span></span>
5. <span data-ttu-id="3f8a9-114">En el campo de **Texto del informe**, escriba una descripción para mostrar en los informes.</span><span class="sxs-lookup"><span data-stu-id="3f8a9-114">In the **Report text** field, enter a description to display on reports.</span></span>
6. <span data-ttu-id="3f8a9-115">En el campo **Descripción breve**, escriba una descripción para fines internos.</span><span class="sxs-lookup"><span data-stu-id="3f8a9-115">In the **Brief description** field, enter a description for internal purposes.</span></span>
7. <span data-ttu-id="3f8a9-116">Haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="3f8a9-116">Click **Save**.</span></span>

