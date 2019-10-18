---
title: Grupos de cuentas de consolidación y cuentas de consolidación adicionales
description: Este tema proporciona información sobre grupos de cuentas de consolidación y cuentas de consolidación adicionales y explica cómo se utilizan en Microsoft Dynamics 365 Finance.
author: aprilolson
manager: AnnBe
ms.date: 01/11/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: LedgerConsolidateAccountGroup
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.custom: 265544
ms.assetid: 71c31df7-b655-46a8-8844-4f92a8bd71b0
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: 8db7a60656434aafd8114b08c2c0e9493140f27b
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/27/2019
ms.locfileid: "2179813"
---
# <a name="consolidation-account-groups-and-additional-consolidation-accounts"></a><span data-ttu-id="f8d3c-103">Grupos de cuentas de consolidación y cuentas de consolidación adicionales</span><span class="sxs-lookup"><span data-stu-id="f8d3c-103">Consolidation account groups and additional consolidation accounts</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="f8d3c-104">Este tema proporciona información sobre grupos de cuentas de consolidación y cuentas de consolidación adicionales y explica cómo se utilizan en Microsoft Dynamics 365 Finance.</span><span class="sxs-lookup"><span data-stu-id="f8d3c-104">This topic provides information about consolidation account groups and additional consolidation accounts, and explains how they are used in Microsoft Dynamics 365 Finance.</span></span>

<a name="consolidation-account-groups"></a><span data-ttu-id="f8d3c-105">Grupos de cuentas de consolidación</span><span class="sxs-lookup"><span data-stu-id="f8d3c-105">Consolidation account groups</span></span>
----------------------------

<span data-ttu-id="f8d3c-106">Los grupos de cuentas de consolidación permiten crear grupos de las cuentas que desee usar para consolidar los datos.</span><span class="sxs-lookup"><span data-stu-id="f8d3c-106">Consolidation account groups let you create groups of the accounts that you want to use to consolidate data.</span></span> <span data-ttu-id="f8d3c-107">Normalmente, un grupo de cuentas de consolidación representa un plan contable impuesto por el gobierno o asigna cuentas a un grupo definido por la sede central de la empresa.</span><span class="sxs-lookup"><span data-stu-id="f8d3c-107">Most often, a consolidation account group represents a government-mandated chart of accounts or maps accounts to a group that is defined by the company's headquarters.</span></span> <span data-ttu-id="f8d3c-108">Los grupos de cuentas de consolidación están en la zona **Configuración** del módulo **Consolidaciones**.</span><span class="sxs-lookup"><span data-stu-id="f8d3c-108">You can find consolidation account groups in the **Setup** area of the **Consolidations** module.</span></span> <span data-ttu-id="f8d3c-109">Al agregar un nuevo grupo, especifique un identificador único para el grupo de cuentas y un nombre.</span><span class="sxs-lookup"><span data-stu-id="f8d3c-109">When you add a new group, you enter a unique identifier for the account group and a name.</span></span>

## <a name="additional-consolidation-accounts"></a><span data-ttu-id="f8d3c-110">Cuentas de consolidación adicionales</span><span class="sxs-lookup"><span data-stu-id="f8d3c-110">Additional consolidation accounts</span></span>
<span data-ttu-id="f8d3c-111">Las cuentas de consolidación adicionales permiten asignar una cuenta de un plan contable existente a un grupo de cuentas de consolidación.</span><span class="sxs-lookup"><span data-stu-id="f8d3c-111">Additional consolidation accounts let you assign an account from an existing chart of accounts to a consolidation account group.</span></span> <span data-ttu-id="f8d3c-112">Después, puede especificar un valor y un nombre de la cuenta de consolidación.</span><span class="sxs-lookup"><span data-stu-id="f8d3c-112">You can then specify a consolidation account value and name.</span></span> 

<span data-ttu-id="f8d3c-113">Los grupos de cuentas de consolidación adicionales están en la zona **Configuración** del módulo **Consolidaciones**.</span><span class="sxs-lookup"><span data-stu-id="f8d3c-113">You can find additional consolidation accounts in the **Setup** area of the **Consolidations** module.</span></span> <span data-ttu-id="f8d3c-114">Al crear una nueva cuenta de consolidación, debe especificar la siguiente información:</span><span class="sxs-lookup"><span data-stu-id="f8d3c-114">When you create a new consolidation account, you must specify the following information:</span></span>

-   <span data-ttu-id="f8d3c-115">**Cuenta principal**: este campo es una búsqueda que muestra todas las cuentas principales que se basan en el plan contable que seleccionó en la página.</span><span class="sxs-lookup"><span data-stu-id="f8d3c-115">**Main account** – This field is a lookup that shows all the main accounts that are based on the chart of accounts that you selected on the page.</span></span> <span data-ttu-id="f8d3c-116">Al seleccionar una cuenta, el nombre se especifica en el campo **Nombre de la cuenta principal**.</span><span class="sxs-lookup"><span data-stu-id="f8d3c-116">When you select an account, the name is automatically entered in the **Main account name** field.</span></span>
-   <span data-ttu-id="f8d3c-117">**Grupo de cuentas de consolidación**: utilice este campo para especificar un grupo al que asignar la cuenta.</span><span class="sxs-lookup"><span data-stu-id="f8d3c-117">**Consolidation account group** – Use this field to specify the group to assign the account to.</span></span> <span data-ttu-id="f8d3c-118">Si consolida de dos formas diferentes, debe agregar la misma cuenta a los cuatro grupos de cuentas de consolidación.</span><span class="sxs-lookup"><span data-stu-id="f8d3c-118">If you consolidate in two different ways, you must add the same account to all four consolidation account groups.</span></span>
-   <span data-ttu-id="f8d3c-119">**Cuenta de consolidación**: especifique el valor de la cuenta de consolidación.</span><span class="sxs-lookup"><span data-stu-id="f8d3c-119">**Consolidation account** – Enter the value of the consolidation account.</span></span> <span data-ttu-id="f8d3c-120">Este valor no tiene que ser una cuenta de un plan contable.</span><span class="sxs-lookup"><span data-stu-id="f8d3c-120">This value doesn't have to be an account from a chart of accounts.</span></span> <span data-ttu-id="f8d3c-121">Puede ser cualquier valor que necesite.</span><span class="sxs-lookup"><span data-stu-id="f8d3c-121">It can be any value that you require.</span></span>
-   <span data-ttu-id="f8d3c-122">**Nombre de cuenta de consolidación**: permite especificar el nombre de la cuenta que desea que aparezca en consultas e informes.</span><span class="sxs-lookup"><span data-stu-id="f8d3c-122">**Consolidation account name** – Enter the name of account as you want it to appear on inquiries and reports.</span></span>
-   <span data-ttu-id="f8d3c-123">**Nivel del SAT**: este campo se usa para informar sobre extractos de cuenta a las autoridades fiscales mexicanas.</span><span class="sxs-lookup"><span data-stu-id="f8d3c-123">**SAT level** – This field is used to report account statements to the Mexican tax authorities.</span></span> 

<span data-ttu-id="f8d3c-124">Cuando haya terminado de crear los grupos de cuentas de la consolidación y las cuentas de consolidación adicionales, puede seleccionar el grupo en el proceso en línea de consolidación.</span><span class="sxs-lookup"><span data-stu-id="f8d3c-124">When you've finished creating your consolidation account groups and additional consolidation accounts, you can select the group in the Consolidate online process.</span></span>


<span data-ttu-id="f8d3c-125">Para obtener más información, consulte [Crear grupos de consolidación y cuentas de consolidación adicionales](../general-ledger/tasks/create-consolidation-groups.md)</span><span class="sxs-lookup"><span data-stu-id="f8d3c-125">For more information, see [Create consolidation groups and additional consolidation accounts](../general-ledger/tasks/create-consolidation-groups.md).</span></span> 



