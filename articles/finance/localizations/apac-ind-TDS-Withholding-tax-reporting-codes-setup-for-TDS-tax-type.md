---
title: Configurar códigos de notificación de retención de impuestos para tipos de impuestos de TDS
description: Los códigos de notificación de retención de impuestos se utilizan para generar declaraciones del formulario 26Q y del formulario 27Q para impuestos deducidos en el origen (TDS). Este tema explica cómo configurar los pasos de los códigos de notificación de retención de impuestos para que pueda configurar los códigos de notificación de TDS.
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
ms.openlocfilehash: 1f9325d182f89b98e8b943ae047c55e7e1aeb02f
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2021
ms.locfileid: "6023578"
---
# <a name="set-up-withholding-tax-reporting-codes-for-the-tds-tax-type"></a><span data-ttu-id="1a6bb-104">Configurar códigos de notificación de retención de impuestos para tipos de impuestos de TDS</span><span class="sxs-lookup"><span data-stu-id="1a6bb-104">Set up withholding tax reporting codes for the TDS tax type</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="1a6bb-105">Los códigos de notificación de retención de impuestos se utilizan para generar declaraciones del formulario 26Q y del formulario 27Q para impuestos deducidos en el origen (TDS).</span><span class="sxs-lookup"><span data-stu-id="1a6bb-105">Withholding tax reporting codes are used to generate Form 26Q and Form 27Q statements for Tax Deducted at Source (TDS).</span></span> <span data-ttu-id="1a6bb-106">Este tema explica cómo configurar los pasos de los códigos de notificación de retención de impuestos para que pueda configurar los códigos de notificación de TDS.</span><span class="sxs-lookup"><span data-stu-id="1a6bb-106">This topic explains how to set up withholding tax reporting codes steps so that you can set up TDS reporting codes.</span></span>

1. <span data-ttu-id="1a6bb-107">Vaya a **Impuesto \> Configuración \> Retención de impuestos \> Códigos de notificación de retención de impuestos**.</span><span class="sxs-lookup"><span data-stu-id="1a6bb-107">Go to **Tax \> Setup \> Withholding tax \> Withholding tax reporting codes**.</span></span>

    <span data-ttu-id="1a6bb-108">[![Página Códigos de notificación de retenciones de impuestos](./media/apac-ind-TDS-16.png)](./media/apac-ind-TDS-16.png)</span><span class="sxs-lookup"><span data-stu-id="1a6bb-108">[![Withholding tax reporting codes page](./media/apac-ind-TDS-16.png)](./media/apac-ind-TDS-16.png)</span></span>

2. <span data-ttu-id="1a6bb-109">En el campo **Tipo de impuesto**, seleccione **TDS** para definir los códigos de notificación de retención de impuestos para el tipo de impuesto TDS.</span><span class="sxs-lookup"><span data-stu-id="1a6bb-109">In the **Tax type** field, select **TDS** to define withholding tax reporting codes for the TDS tax type.</span></span>
3. <span data-ttu-id="1a6bb-110">En el campo **Componente de retención de impuestos**, seleccione el componente de TDS para el que está definiendo el código de notificación de retención de impuestos.</span><span class="sxs-lookup"><span data-stu-id="1a6bb-110">In the **Withholding tax component** field, select the TDS component to that you're defining the withholding tax reporting code for.</span></span> <span data-ttu-id="1a6bb-111">El campo **Grupo de componentes de retención de impuestos** muestra el grupo de componentes de TDS que se definió para el componente de TDS que está definiendo.</span><span class="sxs-lookup"><span data-stu-id="1a6bb-111">The **Withholding tax component group** field shows the TDS component group that was defined for the TDS component that you're defining.</span></span>

    <span data-ttu-id="1a6bb-112">El campo **Código de sección** en la ficha desplegable **General** muestra el código de sección que se adjunta al grupo de componentes de TDS.</span><span class="sxs-lookup"><span data-stu-id="1a6bb-112">The **Section code** field on the **General** FastTab shows the section code that is attached to the TDS component group.</span></span>

4. <span data-ttu-id="1a6bb-113">En la ficha desplegable **General**, en el campo **Código de notificación**, seleccione el código de notificación de TDS:</span><span class="sxs-lookup"><span data-stu-id="1a6bb-113">On the **General** FastTab, in the **Reporting code** field, select the TDS reporting code:</span></span>

    - <span data-ttu-id="1a6bb-114">TDS</span><span class="sxs-lookup"><span data-stu-id="1a6bb-114">TDS</span></span>
    - <span data-ttu-id="1a6bb-115">TCS</span><span class="sxs-lookup"><span data-stu-id="1a6bb-115">TCS</span></span>
    - <span data-ttu-id="1a6bb-116">Suplemento</span><span class="sxs-lookup"><span data-stu-id="1a6bb-116">Surcharge</span></span>
    - <span data-ttu-id="1a6bb-117">PE\_Cess</span><span class="sxs-lookup"><span data-stu-id="1a6bb-117">PE\_Cess</span></span>
    - <span data-ttu-id="1a6bb-118">SHE\_Cess</span><span class="sxs-lookup"><span data-stu-id="1a6bb-118">SHE\_Cess</span></span>

5. <span data-ttu-id="1a6bb-119">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="1a6bb-119">Close the page.</span></span>
