---
title: Conjuntos de dimensiones financieras
description: Este tema describe los conjuntos de dimensiones financieras y proporciona algunos consejos para optimizar su uso.
author: yukonpeegs
ms.date: 03/23/2021
ms.topic: article
ems.prod: ''
ms.technology: ''
ms.search.form: DimensionFocus, LedgerTrialBalanceListPage
audience: Application User
ms.reviewer: roschlom
ms.custom: 25871
ms.search.region: Global
ms.author: epegors
ms.search.validFrom: 2021-03-23
ms.dyn365.ops.version: 10.0.16
ms.openlocfilehash: ba11be028ebeea140df93e2a07dbb463402e3ef0
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2021
ms.locfileid: "6021837"
---
# <a name="financial-dimension-sets"></a><span data-ttu-id="31203-103">Conjuntos de dimensiones financieras</span><span class="sxs-lookup"><span data-stu-id="31203-103">Financial dimension sets</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="31203-104">Este tema describe los conjuntos de dimensiones financieras y proporciona algunos consejos para optimizar su uso.</span><span class="sxs-lookup"><span data-stu-id="31203-104">This topic describes financial dimension sets and provides some tips for optimizing their use.</span></span>

<span data-ttu-id="31203-105">Un conjunto de dimensiones es una lista ordenada de dimensiones financieras que se puede utilizar para resumir los datos del libro mayor de una manera definida por el usuario.</span><span class="sxs-lookup"><span data-stu-id="31203-105">A dimension set is an ordered list of financial dimensions that can be used to summarize General ledger data in a user-defined way.</span></span> <span data-ttu-id="31203-106">Un uso principal de los conjuntos de dimensiones es definir un balance de prueba.</span><span class="sxs-lookup"><span data-stu-id="31203-106">A primary use of dimension sets is to define a trial balance.</span></span>

<span data-ttu-id="31203-107">El único conjunto de dimensiones estándar es el conjunto de dimensiones que contiene solo la cuenta principal.</span><span class="sxs-lookup"><span data-stu-id="31203-107">The only standard dimension set is the dimension set that contains only the main account.</span></span>

<span data-ttu-id="31203-108">Usa la página **Conjuntos de dimensiones financieras** para crear y gestionar conjuntos de dimensiones financieras.</span><span class="sxs-lookup"><span data-stu-id="31203-108">You use the **Financial dimension sets** page to create and manage financial dimension sets.</span></span>

## <a name="dimension-set-balances"></a><span data-ttu-id="31203-109">Saldos de conjuntos de dimensiones</span><span class="sxs-lookup"><span data-stu-id="31203-109">Dimension set balances</span></span>

<span data-ttu-id="31203-110">Un conjunto de dimensiones puede tener saldos basados en sus dimensiones financieras.</span><span class="sxs-lookup"><span data-stu-id="31203-110">A dimension set can have balances that are based on its financial dimensions.</span></span> <span data-ttu-id="31203-111">Los saldos existen en el Libro mayor y se basan en la definición del conjunto de dimensiones.</span><span class="sxs-lookup"><span data-stu-id="31203-111">The balances exist in General ledger and are based on the dimension set definition.</span></span> <span data-ttu-id="31203-112">Los saldos se resumen a partir de los datos del libro mayor para ayudar a mejorar el rendimiento cuando se recuperan (por ejemplo, cuando se genera un saldo de prueba).</span><span class="sxs-lookup"><span data-stu-id="31203-112">The balances are summarized from the General ledger data to help improve performance when they are retrieved (for example, when a trial balance is generated).</span></span>

## <a name="create-balances"></a><span data-ttu-id="31203-113">Crear saldos</span><span class="sxs-lookup"><span data-stu-id="31203-113">Create balances</span></span>

<span data-ttu-id="31203-114">Utilice el botón **Crear saldos** para inicializar los saldos de un conjunto de dimensiones que actualmente no tiene saldos.</span><span class="sxs-lookup"><span data-stu-id="31203-114">Use the **Create balances** button to initialize the balances for a dimension set that doesn't currently have balances.</span></span>

> [!NOTE]
> <span data-ttu-id="31203-115">Le recomendamos que limite el número de conjuntos de dimensiones que tienen saldos, porque las actualizaciones de saldos afectan a todas las actividades de contabilización del Libro mayor.</span><span class="sxs-lookup"><span data-stu-id="31203-115">We recommend that you limit the number of dimension sets that have balances, because balance updates affect all General ledger posting activities.</span></span>

## <a name="update-balances"></a><span data-ttu-id="31203-116">Actualizar saldos</span><span class="sxs-lookup"><span data-stu-id="31203-116">Update balances</span></span>

<span data-ttu-id="31203-117">Utilice **Actualizar saldos** para incluir la última actividad de contabilización del Libro mayor en los saldos.</span><span class="sxs-lookup"><span data-stu-id="31203-117">Use the **Update balances** button to include the latest General ledger posting activity in the balances.</span></span> <span data-ttu-id="31203-118">Las actualizaciones de equilibrio son operaciones ligeras.</span><span class="sxs-lookup"><span data-stu-id="31203-118">Balance updates are light operations.</span></span> <span data-ttu-id="31203-119">Deben procesar solo la actividad de contabilización del Libro mayor que se ha producido desde la última actualización.</span><span class="sxs-lookup"><span data-stu-id="31203-119">They must process only the General ledger posting activity that has occurred since the last update.</span></span>

> [!NOTE]
> <span data-ttu-id="31203-120">La visualización del balance de prueba fuerza una actualización, para garantizar que los saldos que se muestran sean actuales.</span><span class="sxs-lookup"><span data-stu-id="31203-120">Display of the trial balance forces an update, to ensure that the balances that are shown are current.</span></span> <span data-ttu-id="31203-121">Considere la posibilidad de utilizar un trabajo por lotes recurrente para que las actualizaciones de los conjuntos de dimensiones que utiliza con más frecuencia sean rápidas.</span><span class="sxs-lookup"><span data-stu-id="31203-121">Consider using a recurring batch job so that updates to your most frequently used dimension sets are quick.</span></span> <span data-ttu-id="31203-122">De esta forma, ayuda a minimizar el tiempo que deben esperar los usuarios del balance de prueba.</span><span class="sxs-lookup"><span data-stu-id="31203-122">In this way, you help minimize the time that trial balance users must wait.</span></span>

## <a name="rebuild-balances"></a><span data-ttu-id="31203-123">Volver a elaborar saldos</span><span class="sxs-lookup"><span data-stu-id="31203-123">Rebuild balances</span></span>

<span data-ttu-id="31203-124">Utilice el botón **Reconstruir saldos** para recrear los saldos desde cero.</span><span class="sxs-lookup"><span data-stu-id="31203-124">Use the **Rebuild balances** button to re-create the balances from scratch.</span></span> <span data-ttu-id="31203-125">De esta manera, ayuda a garantizar que coincidan con los datos del Libro mayor.</span><span class="sxs-lookup"><span data-stu-id="31203-125">In this way, you help ensure that they match the data in General ledger.</span></span> <span data-ttu-id="31203-126">La reconstrucción de los saldos requiere mucho procesamiento y, por lo general, no debería ser necesaria.</span><span class="sxs-lookup"><span data-stu-id="31203-126">A rebuild of balances requires lots of processing and should not usually be required.</span></span>

> [!NOTE]
> <span data-ttu-id="31203-127">Si tiene un escenario que regularmente requiere una reconstrucción de saldos, le recomendamos que se comunique con el servicio de atención al cliente.</span><span class="sxs-lookup"><span data-stu-id="31203-127">If you have a scenario that regularly requires a rebuild of balances, we recommend that you contact customer support.</span></span> <span data-ttu-id="31203-128">El servicio de atención al cliente puede ayudarlo a determinar por qué los saldos no coinciden con los datos del Libro mayor.</span><span class="sxs-lookup"><span data-stu-id="31203-128">Customer support can help you determine why balances don't match the data in General ledger.</span></span>

## <a name="clear-balances"></a><span data-ttu-id="31203-129">Borrar saldos</span><span class="sxs-lookup"><span data-stu-id="31203-129">Clear balances</span></span>

<span data-ttu-id="31203-130">Utilice **Saldos claros** para eliminar los saldos y detener cualquier actualización adicional.</span><span class="sxs-lookup"><span data-stu-id="31203-130">Use the **Clear balances** button to remove the balances and stop any further updates.</span></span> <span data-ttu-id="31203-131">El conjunto de dimensiones ya no tendrá un impacto en las actividades de contabilización del libro mayor.</span><span class="sxs-lookup"><span data-stu-id="31203-131">The dimension set will no longer have an impact on General ledger posting activities.</span></span>

<span data-ttu-id="31203-132">Para obtener más información, consulte [Dimensiones financieras](financial-dimensions.md).</span><span class="sxs-lookup"><span data-stu-id="31203-132">For more information, see [Financial dimensions](financial-dimensions.md).</span></span>

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
