---
title: Configurar las denominaciones de efectivo para el punto de venta (POS)
description: Cobre denominaciones en las notas y las divisas se pueden definir en back office que se usará en los cajeros, socios de ventas, y los administradores en el almacén dentro de Retail POS.
author: jblucher
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
ms.search.form: RetailStoreTable, RetailStoreCashDeclarationTable
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: 16231
ms.assetid: f28a827c-3a50-4d5e-83eb-e5a768db70a1
ms.search.region: global
ms.search.industry: Retail
ms.author: jeffbl
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.openlocfilehash: a34ae8084c0ad55221f4ab93eb8c6481fa8c4771
ms.sourcegitcommit: 81a647904dd305c4be2e4b683689f128548a872d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/01/2020
ms.locfileid: "3023903"
---
# <a name="configure-cash-denominations-for-the-point-of-sale-pos"></a><span data-ttu-id="6c666-103">Configurar las denominaciones de efectivo para el punto de venta (POS)</span><span class="sxs-lookup"><span data-stu-id="6c666-103">Configure cash denominations for the point of sale (POS)</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="6c666-104">Cobre denominaciones en las notas y las divisas se pueden definir en back office que se usará en los cajeros, socios de ventas, y los administradores en el almacén dentro de Retail POS.</span><span class="sxs-lookup"><span data-stu-id="6c666-104">Cash denominations for notes and coins can be defined in the back office to be used by cashiers, sales associates, and managers at the store from within the POS.</span></span> <span data-ttu-id="6c666-105">Estas denominaciones se pueden usar para ayudar a contar el efectivo al final del día o para rápidamente obtener una venta.</span><span class="sxs-lookup"><span data-stu-id="6c666-105">These denominations can be used to aid in counting cash for end of day tender declarations or for quickly tendering a sale.</span></span>

## <a name="define-denominations"></a><span data-ttu-id="6c666-106">Especificar  denominaciones</span><span class="sxs-lookup"><span data-stu-id="6c666-106">Define denominations</span></span>

<span data-ttu-id="6c666-107">Las denominaciones se configuran por almacén en la opción **Configurar** \> **Declaración de efectivo** de la propiedad de la tienda.</span><span class="sxs-lookup"><span data-stu-id="6c666-107">The denominations are set up per store on the **Set up** \> **Cash declaration** option from the store property page.</span></span>

![Opción de declaración de efectivo](./media/image1-denomination.png)

<span data-ttu-id="6c666-109">Definir denominaciones</span><span class="sxs-lookup"><span data-stu-id="6c666-109">To define a denomination:</span></span>

1. <span data-ttu-id="6c666-110">Haga clic en **Nuevo**.</span><span class="sxs-lookup"><span data-stu-id="6c666-110">Click **New**.</span></span>
1. <span data-ttu-id="6c666-111">Especifique el tipo (moneda o billete).</span><span class="sxs-lookup"><span data-stu-id="6c666-111">Specify the type (coin or note).</span></span>
1. <span data-ttu-id="6c666-112">Especifique el importe (valor).</span><span class="sxs-lookup"><span data-stu-id="6c666-112">Specify the amount (value).</span></span>

![Página de denominaciones de declaración de efectivo](./media/image2-denomination.png)

## <a name="configure-the-functionality-profile"></a><span data-ttu-id="6c666-114">Configure el perfil de funcionalidad.</span><span class="sxs-lookup"><span data-stu-id="6c666-114">Configure the functionality profile</span></span>

<span data-ttu-id="6c666-115">Al pagar en efectivo mediante PDV, el usuario puede usar las denominaciones de la nota para especificar rápidamente el importe pagado el cliente.</span><span class="sxs-lookup"><span data-stu-id="6c666-115">When paying by cash in POS, the user can use the note denominations to quickly enter the amount paid by the customer.</span></span> <span data-ttu-id="6c666-116">En el perfil de funcionalidad, puede configurar las dos opciones para mostrar la denominación en el sistema PDV.</span><span class="sxs-lookup"><span data-stu-id="6c666-116">In the functionality profile, you can configure the two options for showing the denomination in POS.</span></span>

- <span data-ttu-id="6c666-117">**Mayor o igual al importe debido**: De forma predeterminada, el sistema PDV solo mostrará las denominaciones de la nota que sean mayores que el importe debido, lo que permite la venta a un toque.</span><span class="sxs-lookup"><span data-stu-id="6c666-117">**Greater or equal to amount due** – By default, POS will only show the note denominations that are greater than the amount due, which allows for one-touch tendering.</span></span> <span data-ttu-id="6c666-118">Por ejemplo, si el importe debido es 7,50$, el sistema PDV mostraría las siguientes denominaciones: 10$, 20$ y 100$.</span><span class="sxs-lookup"><span data-stu-id="6c666-118">For example, if the amount due is $7.50, POS would show the following denominations: $10, $20, $50, and $100.</span></span> <span data-ttu-id="6c666-119">Al tocar en cualquiera de estos importes automáticamente ofrecerá la venta por dicho importe.</span><span class="sxs-lookup"><span data-stu-id="6c666-119">Touching any of these amounts will automatically tender the sale for that amount.</span></span> <span data-ttu-id="6c666-120">Los billetes de 1$ y 5$ no se muestran ya que estos importes son inferiores al importe debido.</span><span class="sxs-lookup"><span data-stu-id="6c666-120">The $1 and $5 notes are not shown since these amounts are less than the amount due.</span></span>
- <span data-ttu-id="6c666-121">**Todas las denominaciones**: Seleccione esta opción para mostrar siempre todas las denominaciones de nota en el PDV, independientemente del importe debido.</span><span class="sxs-lookup"><span data-stu-id="6c666-121">**All denominations** – Select this option to always show all note denominations in POS, regardless of the amount due.</span></span> <span data-ttu-id="6c666-122">Esto significa que el usuario puede usar una combinación de notas para lograr el importe debido.</span><span class="sxs-lookup"><span data-stu-id="6c666-122">This means that the user can use a combination of notes to reach the amount due.</span></span> <span data-ttu-id="6c666-123">Por ejemplo, si el importe debido es 25,00$, el usuario puede elegir 20$ y 5$ para completar la venta.</span><span class="sxs-lookup"><span data-stu-id="6c666-123">For example, if the amount due is $25.00, the user can choose $20 and $5 to complete the sale.</span></span>
