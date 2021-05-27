---
title: Configuración de reversiones en diarios y líneas
description: Este tema trata sobre por qué un asiento de reversión introducido en un diario general podría no incluirse en la transacción registrada.
author: kweekley
ms.date: 04/29/2021
ms.topic: index-page
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2021-5-05
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: 74020f6fc9b0fa8e05a1e2a09fd13dcd60490dc0
ms.sourcegitcommit: 817716c2e96f24af0ef1d7d5323afdeccdc602f3
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/13/2021
ms.locfileid: "6028584"
---
# <a name="reverse-settings-on-journals-and-lines"></a><span data-ttu-id="afbb9-103">Configuración de reversiones en diarios y líneas</span><span class="sxs-lookup"><span data-stu-id="afbb9-103">Reverse settings on journals and lines</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="afbb9-104">Este tema trata sobre por qué un asiento de reversión introducido en un diario general podría no incluirse en la transacción registrada.</span><span class="sxs-lookup"><span data-stu-id="afbb9-104">This topic addresses why a reversing entry that was entered on a general journal might not be included on the posted transaction.</span></span>  

## <a name="symptom"></a><span data-ttu-id="afbb9-105">Síntoma</span><span class="sxs-lookup"><span data-stu-id="afbb9-105">Symptom</span></span>

<span data-ttu-id="afbb9-106">Un diario general incluye una entrada de reversión y una fecha de reversión en el diario.</span><span class="sxs-lookup"><span data-stu-id="afbb9-106">A general journal includes a reversing entry and reversing date on the journal.</span></span> <span data-ttu-id="afbb9-107">Al registrar el diario, ninguno de los asientos se revierte.</span><span class="sxs-lookup"><span data-stu-id="afbb9-107">When you post the journal, none of the vouchers are reversed.</span></span> <span data-ttu-id="afbb9-108">¿Por qué ocurre esto?</span><span class="sxs-lookup"><span data-stu-id="afbb9-108">Why does this happen?</span></span>

## <a name="resolution"></a><span data-ttu-id="afbb9-109">Resolución</span><span class="sxs-lookup"><span data-stu-id="afbb9-109">Resolution</span></span>

<span data-ttu-id="afbb9-110">Cuando se registra el diario, el proceso de reversión solo se fija en la configuración de **Entrada de reversión** y **Fecha de reversión** de la sección **Líneas** del asiento.</span><span class="sxs-lookup"><span data-stu-id="afbb9-110">When the journal is posted, the reversing process looks only at the **Revering entry** and **Reversing date** settings on the **Lines** section of the voucher.</span></span> <span data-ttu-id="afbb9-111">Este enfoque permite que un diario incluya algunos asientos marcados para reversión y otros que no lo están.</span><span class="sxs-lookup"><span data-stu-id="afbb9-111">This approach allows a journal to include some vouchers that are marked for reversing, and others that are not.</span></span>

<span data-ttu-id="afbb9-112">Los valores del diario solo se utilizan como predeterminados al agregar *nuevas* líneas.</span><span class="sxs-lookup"><span data-stu-id="afbb9-112">The values from the journal are only used as defaults when adding *new* lines.</span></span> <span data-ttu-id="afbb9-113">El cambio de los valores del diario no afecta las líneas existentes.</span><span class="sxs-lookup"><span data-stu-id="afbb9-113">Changing the values on the journal doesn’t affect existing lines.</span></span> <span data-ttu-id="afbb9-114">En este ejemplo, las líneas de asientos se introdujeron primero.</span><span class="sxs-lookup"><span data-stu-id="afbb9-114">In this example, the voucher lines were entered first.</span></span> <span data-ttu-id="afbb9-115">Cuando introduzca el detalle de la línea antes de designar el diario como de reversión, la designación como entrada inversa y la fecha no se aplicará a ninguna línea existente.</span><span class="sxs-lookup"><span data-stu-id="afbb9-115">When you enter the line detail before designating the journal as reversing, the designation as a reversing entry and date won't be applied to any existing lines.</span></span>

<span data-ttu-id="afbb9-116">El cambio de la entrada o la fecha de reversión en una línea existente propaga ese cambio a otras líneas del mismo asiento.</span><span class="sxs-lookup"><span data-stu-id="afbb9-116">Changing the reversing entry or reversing date on an existing line propagates that change to other lines in the same voucher.</span></span> <span data-ttu-id="afbb9-117">Para optimizar el rendimiento, la cuadrícula no se actualiza después de propagar cambios a otras líneas.</span><span class="sxs-lookup"><span data-stu-id="afbb9-117">To optimize performance, the grid is not refreshed after propagating changes to other Lines.</span></span> <span data-ttu-id="afbb9-118">Puede mostrar los valores actualizados actualizando la cuadrícula.</span><span class="sxs-lookup"><span data-stu-id="afbb9-118">You can display the updated values by refreshing the grid.</span></span>


