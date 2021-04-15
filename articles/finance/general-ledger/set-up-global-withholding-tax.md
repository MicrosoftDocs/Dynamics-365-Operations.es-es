---
title: Configurar una retención de impuestos global
description: Este tema muestra los pasos para configurar una retención de impuestos global para ventas y compras.
author: roschlom
ms.date: 01/12/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.custom: 15721
ms.assetid: b4b406fa-b772-44ec-8dd8-8eb818a921ef
ms.search.region: Global
ms.author: kailiang
ms.search.validFrom: 2020-01-12
ms.dyn365.ops.version: AX 10.0.17
ms.openlocfilehash: 3270b3f75d719fef9a7eb991c49e9d6585cd44d8
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/01/2021
ms.locfileid: "5815317"
---
# <a name="set-up-global-withholding-tax"></a><span data-ttu-id="4e0fd-103">Configurar una retención de impuestos global</span><span class="sxs-lookup"><span data-stu-id="4e0fd-103">Set up global withholding tax</span></span>

<span data-ttu-id="4e0fd-104">Este tema muestra los pasos para configurar una retención de impuestos global para ventas y compras.</span><span class="sxs-lookup"><span data-stu-id="4e0fd-104">This topic lists the steps for setting up global withholding tax for sales and purchases.</span></span> 

1. <span data-ttu-id="4e0fd-105">Configure las autoridades de retención de impuestos en la página **Autoridades de retención de impuestos**.</span><span class="sxs-lookup"><span data-stu-id="4e0fd-105">Set up withholding tax authorities on the **Withholding tax authorities** page.</span></span>

2. <span data-ttu-id="4e0fd-106">Configure los períodos de liquidación de retenciones en la página **Períodos de liquidación de retención de impuestos**.</span><span class="sxs-lookup"><span data-stu-id="4e0fd-106">Set up withholding settlement periods on the **Withholding tax settlement periods** page.</span></span>

3. <span data-ttu-id="4e0fd-107">Configure el grupo de registro de retenciones en la página **Retención de impuestos > grupo de registro**.</span><span class="sxs-lookup"><span data-stu-id="4e0fd-107">Set up withholding ledger posting group on the **Withholding tax > ledger posting group** page.</span></span>

   > [!Note] 
   >
   > <span data-ttu-id="4e0fd-108">La cuenta **Retención de impuestos** se asignará con una cuenta principal con un **Tipo de registro** de Retención de impuestos.</span><span class="sxs-lookup"><span data-stu-id="4e0fd-108">**Withholding tax** account will be assigned with a main account with **Posting type** of Withholding tax.</span></span> <span data-ttu-id="4e0fd-109">La cuenta **Compensación de retención de impuestos** también se asignará con una cuenta principal con un **Tipo de registro** de "Compensación de retención de impuestos".</span><span class="sxs-lookup"><span data-stu-id="4e0fd-109">**Withholding tax offset** account will also be assigned with a main account with **Posting type** "Withholding tax offset".</span></span> <span data-ttu-id="4e0fd-110">Vaya a **Contabilidad general > Plan de cuentas > Cuentas> Cuentas principales**, configure el **Tipo de registro** en el subformulario **Validación del registro** para las cuentas principales.</span><span class="sxs-lookup"><span data-stu-id="4e0fd-110">Go to **General ledger > Chart of accounts > Accounts > Main accounts**, set up the **Posting type** in the **Posting validation** sub-form for the main accounts.</span></span>

4. <span data-ttu-id="4e0fd-111">Configure los códigos de retención de impuestos en la página **Códigos de retención de impuestos**.</span><span class="sxs-lookup"><span data-stu-id="4e0fd-111">Set up withholding tax codes on the **Withholding tax codes** page.</span></span>

5. <span data-ttu-id="4e0fd-112">Configure los grupos de retención de impuestos en la página **Grupos de retención de impuestos**.</span><span class="sxs-lookup"><span data-stu-id="4e0fd-112">Set up withholding tax groups on the **Withholding tax groups** page.</span></span>

6. <span data-ttu-id="4e0fd-113">Configure los tipos de ingresos para retención de impuestos en la página **Tipos de ingresos para retención** **de impuestos**.</span><span class="sxs-lookup"><span data-stu-id="4e0fd-113">Set up withholding tax revenue types on the **Withholding tax revenue** **types** page.</span></span>

7. <span data-ttu-id="4e0fd-114">Configure los grupos de retención de impuestos en la página **Grupos de retención de impuestos** para un elemento o servicio.</span><span class="sxs-lookup"><span data-stu-id="4e0fd-114">Set up withholding tax groups on the **Item withholding tax groups** page for an item or service.</span></span>

8. <span data-ttu-id="4e0fd-115">Configure **Importe mínimo de la factura** en la página **Parámetros de contabilidad general > Retención de impuestos**.</span><span class="sxs-lookup"><span data-stu-id="4e0fd-115">Set up **Minimum invoice amount** on the **General ledger parameters > Withholding tax** page.</span></span>


[!INCLUDE[footer-include](../../includes/footer-banner.md)]