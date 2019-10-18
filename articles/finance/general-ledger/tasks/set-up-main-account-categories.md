---
title: Configurar categorías de cuenta principal
description: En este tema explica cómo configurar categorías de cuenta principal en Dynamics 365 Finance.
author: aprilolson
manager: AnnBe
ms.date: 08/08/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: MainAccountCategory, MainAccountCategoryLink
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 8e2ba1d900f5d87a76fa93bf53f2970320e7d84c
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/27/2019
ms.locfileid: "2186012"
---
# <a name="set-up-main-account-categories"></a><span data-ttu-id="85e11-103">Configurar categorías de cuenta principal</span><span class="sxs-lookup"><span data-stu-id="85e11-103">Set up main account categories</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="85e11-104">En este tema explica cómo configurar categorías de cuenta principal.</span><span class="sxs-lookup"><span data-stu-id="85e11-104">This topic explains how to set up main account categories.</span></span> <span data-ttu-id="85e11-105">Las categorías de cuenta principal se usan para los informes predeterminados en los informes financieros y en Power BI.</span><span class="sxs-lookup"><span data-stu-id="85e11-105">Main account categories are used for the default reports in financial reporting and in Power BI.</span></span> <span data-ttu-id="85e11-106">Las categorías de cuenta principal que se crean de forma predeterminada se pueden cambiar de nombre pero no se pueden eliminar.</span><span class="sxs-lookup"><span data-stu-id="85e11-106">Main account categories that are created by default can be renamed but not deleted.</span></span> <span data-ttu-id="85e11-107">Las categorías de cuentas adicionales se pueden crear y usar para fines de informes y análisis.</span><span class="sxs-lookup"><span data-stu-id="85e11-107">Additional account categories can be created and used for reporting and analysis purposes.</span></span> <span data-ttu-id="85e11-108">En este tema tarea se utiliza la empresa de demostración USMF.</span><span class="sxs-lookup"><span data-stu-id="85e11-108">This topic uses the USMF demo company.</span></span>

## <a name="create-a-main-account-category"></a><span data-ttu-id="85e11-109">Crear una categoría de cuenta principal</span><span class="sxs-lookup"><span data-stu-id="85e11-109">Create a main account category</span></span>
1. <span data-ttu-id="85e11-110">En el panel de navegación, vaya a **Módulos > Contabilidad general > Plan de cuentas > Cuentas > Categorías de cuenta principal**.</span><span class="sxs-lookup"><span data-stu-id="85e11-110">In the navigation pane, go to **Modules > General Ledger > Chart of accounts > Accounts > Main account categories**.</span></span>
2. <span data-ttu-id="85e11-111">Seleccione **Nuevo**.</span><span class="sxs-lookup"><span data-stu-id="85e11-111">Select **New**.</span></span>
3. <span data-ttu-id="85e11-112">En el campo **Categoría de cuenta principal**, especifique un nombre único.</span><span class="sxs-lookup"><span data-stu-id="85e11-112">In the **Main account category** field, enter a unique name.</span></span>
4. <span data-ttu-id="85e11-113">En el **campo Descripción**, especifique una descripción para la categoría de cuenta principal.</span><span class="sxs-lookup"><span data-stu-id="85e11-113">In the **Description field**, enter a description for the main account category.</span></span>
5. <span data-ttu-id="85e11-114">En el campo **Tipo de cuenta principal**, seleccione el tipo de cuenta principal que se vinculará a la categoría.</span><span class="sxs-lookup"><span data-stu-id="85e11-114">In the **Main account type** field, select the main account type that will be linked to the category.</span></span>

## <a name="link-main-accounts-to-account-category"></a><span data-ttu-id="85e11-115">Vincular cuentas principales a categoría de cuenta</span><span class="sxs-lookup"><span data-stu-id="85e11-115">Link main accounts to account category</span></span>
1. <span data-ttu-id="85e11-116">Haga clic en **Vincular cuentas principales**.</span><span class="sxs-lookup"><span data-stu-id="85e11-116">Click **Link main accounts**.</span></span>
2. <span data-ttu-id="85e11-117">En la lista, seleccione las cuentas principales para asignar a la categoría de cuenta principal marcando las casillas de la columna **Vinculada**.</span><span class="sxs-lookup"><span data-stu-id="85e11-117">In the list, select the main accounts to assign to the main account category by checking the boxes in the **Linked** column.</span></span> <span data-ttu-id="85e11-118">La asignación de cuentas principales a una categoría de cuenta principal agregará los saldos de las cuentas cuando se use esa categoría para análisis e informes financieros.</span><span class="sxs-lookup"><span data-stu-id="85e11-118">Assigning main accounts to a main account category will aggregate the balances of the accounts when that category is used for financial reporting and analysis.</span></span>  
3. <span data-ttu-id="85e11-119">Active o desactive la opción **Vinculada** para elegir las cuentas principales.</span><span class="sxs-lookup"><span data-stu-id="85e11-119">Select or clear the **Linked** option to choose the main accounts.</span></span>
4. <span data-ttu-id="85e11-120">Seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="85e11-120">Select **OK**.</span></span>
5. <span data-ttu-id="85e11-121">Seleccione **Sí**.</span><span class="sxs-lookup"><span data-stu-id="85e11-121">Select **Yes**.</span></span>
