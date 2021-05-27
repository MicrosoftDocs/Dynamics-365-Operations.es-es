---
title: Configurar autoridades de retención de impuestos para tipos de impuestos de TDS
description: Este tema explica cómo configurar autoridades de impuestos deducidos en el origen (TDS).
author: kailiang
ms.date: 02/12/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.custom: 15721
ms.assetid: b4b406fa-b772-44ec-8dd8-8eb818a921ef
ms.search.region: Global
ms.author: kailiang
ms.search.validFrom: 2021-02-12
ms.dyn365.ops.version: AX 10.0.17
ms.openlocfilehash: 5375363a9b1383a83e80fc3c4b841780adab4172
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2021
ms.locfileid: "6023560"
---
# <a name="set-up-withholding-tax-authorities-for-the-tds-tax-type"></a><span data-ttu-id="2b3ee-103">Configurar autoridades de retención de impuestos para tipos de impuestos de TDS</span><span class="sxs-lookup"><span data-stu-id="2b3ee-103">Set up withholding tax authorities for the TDS tax type</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="2b3ee-104">Este tema explica cómo configurar autoridades de impuestos deducidos en el origen (TDS).</span><span class="sxs-lookup"><span data-stu-id="2b3ee-104">This topic explains how to set up Tax Deducted at Source (TDS) authorities.</span></span>

1. <span data-ttu-id="2b3ee-105">Vaya a **Impuestos \> Impuestos indirectos \> Autoridades de retención de impuestos**.</span><span class="sxs-lookup"><span data-stu-id="2b3ee-105">Go to **Tax \> Indirect taxes \> Withholding tax authorities**.</span></span>

    <span data-ttu-id="2b3ee-106">[![Página Autoridades de retenciones de impuestos](./media/apac-ind-TDS-12.png)](./media/apac-ind-TDS-12.png)</span><span class="sxs-lookup"><span data-stu-id="2b3ee-106">[![Withholding tax authorities page](./media/apac-ind-TDS-12.png)](./media/apac-ind-TDS-12.png)</span></span>

2. <span data-ttu-id="2b3ee-107">En el campo **Tipo de impuesto**, seleccione **TDS** para configurar autoridades de retención de impuestos para el tipo de impuesto TDS.</span><span class="sxs-lookup"><span data-stu-id="2b3ee-107">In the **Tax type** field, select **TDS** to set up withholding tax authorities for the TDS tax type.</span></span>
3. <span data-ttu-id="2b3ee-108">En el panel de acciones, haga clic en **Nuevo** para crear una línea.</span><span class="sxs-lookup"><span data-stu-id="2b3ee-108">On the Action Pane, select **New** to create a line.</span></span>
4. <span data-ttu-id="2b3ee-109">En el campo **Autoridad de retención de impuestos**, introduzca un nombre para la autoridad de TDS.</span><span class="sxs-lookup"><span data-stu-id="2b3ee-109">In the **Withholding tax authority** field, enter a name for the TDS authority.</span></span>
5. <span data-ttu-id="2b3ee-110">En el campo **Descripción**, escriba una descripción.</span><span class="sxs-lookup"><span data-stu-id="2b3ee-110">In the **Description** field, enter a description.</span></span>
6. <span data-ttu-id="2b3ee-111">En la ficha desplegable **General**, en el campo **Cuenta del proveedor**, seleccione la cuenta del proveedor para la autoridad de TDS.</span><span class="sxs-lookup"><span data-stu-id="2b3ee-111">On the **General** FastTab, in the **Vendor account** field, select the vendor account for the TDS authority.</span></span>

    > [!NOTE]
    > <span data-ttu-id="2b3ee-112">Debe definir el nombre del banco donde se depositarán los fondos adeudados al proveedor de la autoridad de TDS.</span><span class="sxs-lookup"><span data-stu-id="2b3ee-112">You must define the name of the bank where funds that are owed to the TDS authority vendor will be deposited.</span></span> <span data-ttu-id="2b3ee-113">El nombre del banco se define en la página **Cuentas bancarias** (**Proveedores \> Todos los proveedores \> Proveedor \> Configurar \> Cuentas bancarias**).</span><span class="sxs-lookup"><span data-stu-id="2b3ee-113">The bank's name is defined on the **Bank accounts** page (**Accounts payable \> All vendors \> Vendor \> Set up \> Bank accounts**).</span></span>

7. <span data-ttu-id="2b3ee-114">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="2b3ee-114">Close the page.</span></span>
