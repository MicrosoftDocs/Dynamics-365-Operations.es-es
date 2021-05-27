---
title: Configurar números de registro de TDS para entidades jurídicas
description: Este tema explica cómo configurar números de registro para entidades jurídicas de impuestos deducidos en el origen (TDS).
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
ms.openlocfilehash: 3550b2b7b305702ffc337ba0a9bb79f60a9de120
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2021
ms.locfileid: "6023565"
---
# <a name="set-up-tds-registration-numbers-for-legal-entities"></a><span data-ttu-id="a1ba3-103">Configurar números de registro de TDS para entidades jurídicas</span><span class="sxs-lookup"><span data-stu-id="a1ba3-103">Set up TDS registration numbers for legal entities</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="a1ba3-104">Este tema explica cómo configurar números de registro para entidades jurídicas de impuestos deducidos en el origen (TDS).</span><span class="sxs-lookup"><span data-stu-id="a1ba3-104">This topic explains how to set up Tax Deducted at Source (TDS) registration numbers for legal entities.</span></span>

1. <span data-ttu-id="a1ba3-105">Vaya a **Administración de la organización \> Organizaciones \> Entidades jurídicas**.</span><span class="sxs-lookup"><span data-stu-id="a1ba3-105">Go to **Organization administration \> Organizations \> Legal entities**.</span></span>

    <span data-ttu-id="a1ba3-106">[![Página Entidades jurídicas](./media/apac-ind-TDS-4.png)](./media/apac-ind-TDS-4.png)</span><span class="sxs-lookup"><span data-stu-id="a1ba3-106">[![Legal entities page](./media/apac-ind-TDS-4.png)](./media/apac-ind-TDS-4.png)</span></span>

2. <span data-ttu-id="a1ba3-107">En la ficha desplegable **Información de impuestos**, en el campo **Número de cuenta permanente**, introduzca el número de cuenta permanente (PAN) de la entidad jurídica.</span><span class="sxs-lookup"><span data-stu-id="a1ba3-107">On the **Tax information** FastTab, in the **Permanent account number** field, enter the permanent account number (PAN) of the legal entity.</span></span>
3. <span data-ttu-id="a1ba3-108">En el campo **Número de círculo**, introduzca el número de círculo de la autoridad de TDS.</span><span class="sxs-lookup"><span data-stu-id="a1ba3-108">In the **Circle number** field, enter the circle number of the TDS authority.</span></span>
4. <span data-ttu-id="a1ba3-109">En el campo **Número de distrito**, introduzca el número de distrito de la autoridad de TDS.</span><span class="sxs-lookup"><span data-stu-id="a1ba3-109">In the **Ward number** field, enter the ward number of the TDS authority.</span></span>
5. <span data-ttu-id="a1ba3-110">En el campo **Oficial evaluador**, introduzca los detalles del oficial evaluador para la autoridad TDS.</span><span class="sxs-lookup"><span data-stu-id="a1ba3-110">In the **Assessing officer** field, enter the details of the assessing officer for the TDS authority.</span></span>
6. <span data-ttu-id="a1ba3-111">En el campo **Tipo de deductor**, seleccione la categoría de tipo de deductor para la entidad jurídica.</span><span class="sxs-lookup"><span data-stu-id="a1ba3-111">In the **Type of deductor** field, select the deductor type category for the legal entity.</span></span>
7. <span data-ttu-id="a1ba3-112">En el panel de acciones, seleccione **Id. de registro** para abrir la página **Administrar direcciones**.</span><span class="sxs-lookup"><span data-stu-id="a1ba3-112">On the Action Pane, select **Registration IDs** to open the **Manage addresses** page.</span></span>
8. <span data-ttu-id="a1ba3-113">En la ficha desplegable **Información de impuestos**, seleccione **Agregar** o **Editar** para abrir la página **Administrar información de impuestos**, donde puede mantener la entrada de registro de impuestos.</span><span class="sxs-lookup"><span data-stu-id="a1ba3-113">On the **Tax information** FastTab, select **Add** or **Edit** to open the **Manage tax information** page, where you can maintain the tax registration entry.</span></span>

    <span data-ttu-id="a1ba3-114">[![Página Administrar direcciones](./media/apac-ind-TDS-5.png)](./media/apac-ind-TDS-5.png)</span><span class="sxs-lookup"><span data-stu-id="a1ba3-114">[![Manage addresses page](./media/apac-ind-TDS-5.png)](./media/apac-ind-TDS-5.png)</span></span>

9. <span data-ttu-id="a1ba3-115">En la ficha desplegable **Retención de impuestos**, en el campo **Número de cuenta de impuestos (TAN)**, introduzca el número de registro.</span><span class="sxs-lookup"><span data-stu-id="a1ba3-115">On the **Withholding tax** FastTab, in the **Tax Account Number (TAN)** field, enter the registration number.</span></span> <span data-ttu-id="a1ba3-116">Este número debe constar de cuatro caracteres alfabéticos, luego cinco caracteres numéricos y luego un carácter alfabético.</span><span class="sxs-lookup"><span data-stu-id="a1ba3-116">This number must consist of four alphabetic characters, then five numeric characters, and then one alphabetic character.</span></span> <span data-ttu-id="a1ba3-117">Este es un ejemplo: **AXDF87645F**.</span><span class="sxs-lookup"><span data-stu-id="a1ba3-117">Here is an example: **AXDF87645F**.</span></span>
10. <span data-ttu-id="a1ba3-118">En el campo **Nombre o descripción**, escriba una descripción del número de registro de la retención de impuestos.</span><span class="sxs-lookup"><span data-stu-id="a1ba3-118">In the **Name or description** field, enter a description of the withholding tax registration number.</span></span>

    <span data-ttu-id="a1ba3-119">[![Página Administrar información de impuestos](./media/apac-ind-TDS-5-1.png)](./media/apac-ind-TDS-5-1.png)</span><span class="sxs-lookup"><span data-stu-id="a1ba3-119">[![Manage tax information page](./media/apac-ind-TDS-5-1.png)](./media/apac-ind-TDS-5-1.png)</span></span>

11. <span data-ttu-id="a1ba3-120">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="a1ba3-120">Close the page.</span></span>
