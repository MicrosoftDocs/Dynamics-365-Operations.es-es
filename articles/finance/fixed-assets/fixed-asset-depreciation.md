---
title: Depreciación de activo fijo
description: Este tema proporciona información general de la depreciación de los activos fijos.
author: ShylaThompson
ms.date: 10/30/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: AssetBonus, AssetBookTable
audience: Application User
ms.reviewer: roschlom
ms.custom: 3121
ms.assetid: 98ff891f-e0e2-4184-b618-28107a50851f
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 1ec8544b885485781b0b9c0a59ec47f90fdceb6b
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/01/2021
ms.locfileid: "5826891"
---
# <a name="fixed-asset-depreciation"></a><span data-ttu-id="5b8a2-103">Depreciación de activo fijo</span><span class="sxs-lookup"><span data-stu-id="5b8a2-103">Fixed asset depreciation</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="5b8a2-104">Este tema proporciona información general de la depreciación de los activos fijos.</span><span class="sxs-lookup"><span data-stu-id="5b8a2-104">This topic provides an overview of depreciation for fixed assets.</span></span>

<span data-ttu-id="5b8a2-105">La depreciación es una transacción periódica que reduce normalmente el valor del activo fijo en el balance de situación y que se carga como un gasto en la cuenta de pérdidas y ganancias.</span><span class="sxs-lookup"><span data-stu-id="5b8a2-105">Depreciation is a periodic transaction that typically reduces the value of the fixed asset on the balance sheet, and is charged as an expenditure to a profit and loss account.</span></span> <span data-ttu-id="5b8a2-106">Por lo tanto, se usa normalmente una cuenta principal para abonar la depreciación periódica en el balance de situación.</span><span class="sxs-lookup"><span data-stu-id="5b8a2-106">Therefore, a main account is typically used to credit the periodic depreciation on the balance sheet.</span></span> <span data-ttu-id="5b8a2-107">Una cuenta de contrapartida es una cuenta en la parte de pérdidas y ganancias del plan contable.</span><span class="sxs-lookup"><span data-stu-id="5b8a2-107">An offset account is an account in the profit and loss part of the chart of accounts.</span></span>

## <a name="depreciation-adjustment"></a><span data-ttu-id="5b8a2-108">Ajuste de depreciación</span><span class="sxs-lookup"><span data-stu-id="5b8a2-108">Depreciation adjustment</span></span>
<span data-ttu-id="5b8a2-109">Normalmente, solo se registra una corrección en una transacción de depreciación registrada como un ajuste de depreciación.</span><span class="sxs-lookup"><span data-stu-id="5b8a2-109">Usually, only a correction to a posted depreciation transaction is posted as a depreciation adjustment.</span></span> <span data-ttu-id="5b8a2-110">Por lo tanto, la cuenta principal y la cuenta de contrapartida se configuran de la misma forma que las cuentas para depreciación.</span><span class="sxs-lookup"><span data-stu-id="5b8a2-110">Therefore, both the main account and the offset account are set up just like the accounts for depreciation.</span></span> <span data-ttu-id="5b8a2-111">Un ajuste de depreciación puede ser un importe positivo o negativo, pero la función de la cuenta principal (como una cuenta de balance de situación) y la función de la cuenta de contrapartida (por lo general, una cuenta de pérdidas y ganancias) no se modifica.</span><span class="sxs-lookup"><span data-stu-id="5b8a2-111">A depreciation adjustment can be either a positive amount or a negative amount, but the functionality of the main account (as a balance sheet account) and the functionality of the offset account (usually as a profit and loss account) remain the same.</span></span>

## <a name="extraordinary-depreciation"></a><span data-ttu-id="5b8a2-112">Depreciación extraordinaria</span><span class="sxs-lookup"><span data-stu-id="5b8a2-112">Extraordinary depreciation</span></span>
<span data-ttu-id="5b8a2-113">La depreciación extraordinaria funciona como la depreciación básica.</span><span class="sxs-lookup"><span data-stu-id="5b8a2-113">Extraordinary depreciation works like basic depreciation.</span></span> <span data-ttu-id="5b8a2-114">Por lo tanto, se usa una cuenta principal para abonar el importe de depreciación al balance y reducir el valor del activo fijo.</span><span class="sxs-lookup"><span data-stu-id="5b8a2-114">Therefore, a main account is used to credit the depreciation amount to the balance sheet and reduce the value of the fixed asset.</span></span> <span data-ttu-id="5b8a2-115">Una cuenta de contrapartida es una cuenta de pérdidas y ganancias, donde la depreciación calculada para el período fiscal se carga como gasto.</span><span class="sxs-lookup"><span data-stu-id="5b8a2-115">An offset account is a profit and loss account, where the depreciation that is calculated for the fiscal period is charged as an expenditure.</span></span> 

<span data-ttu-id="5b8a2-116">La depreciación extraordinaria funciona independientemente de la depreciación básica.</span><span class="sxs-lookup"><span data-stu-id="5b8a2-116">Extraordinary depreciation works independently of basic depreciation.</span></span> <span data-ttu-id="5b8a2-117">Al tratar la depreciación extraordinaria como un tipo de transacción individual, puede registrar y notificar la depreciación extraordinaria aparte de la depreciación básica.</span><span class="sxs-lookup"><span data-stu-id="5b8a2-117">By having extraordinary depreciation as a separate transaction type, you can post and report the extraordinary depreciation separately from the basic depreciation.</span></span>

## <a name="special-depreciation-allowance"></a><span data-ttu-id="5b8a2-118">Método de amortización por depreciación especial</span><span class="sxs-lookup"><span data-stu-id="5b8a2-118">Special depreciation allowance</span></span>
<span data-ttu-id="5b8a2-119">Puede utilizar las amortizaciones por depreciación especial para disponer de importes de depreciación adicionales durante el primer año en que un activo se pone en servicio y se deprecia.</span><span class="sxs-lookup"><span data-stu-id="5b8a2-119">You can use special depreciation allowances to take extra depreciation amounts during the first year that an asset is put in service and depreciated.</span></span> <span data-ttu-id="5b8a2-120">Los métodos de amortización por depreciación especial se debe realizar antes de cualquier cálculo de depreciación.</span><span class="sxs-lookup"><span data-stu-id="5b8a2-120">Special depreciation allowances must be taken before any other depreciation calculations.</span></span> <span data-ttu-id="5b8a2-121">Dado que los métodos de amortización por depreciación especial a menudo son desconocidos hasta tiempo más tarde en la vida del activo fijo, es mejor usar este tipo de depreciación con un libro que no se registre en la contabilidad general.</span><span class="sxs-lookup"><span data-stu-id="5b8a2-121">Because special depreciation allowances are often unknown until later in the service life of the fixed asset, it's best to use this type of depreciation with a book that doesn't post to the general ledger.</span></span> <span data-ttu-id="5b8a2-122">Puede usar la función periódica de Borrar transacciones no registradas en la contabilidad general para eliminar el historial de transacciones de esos libros.</span><span class="sxs-lookup"><span data-stu-id="5b8a2-122">You can use the Delete transactions not posted to general ledger periodic function to delete the transaction history for these books.</span></span> <span data-ttu-id="5b8a2-123">A continuación puede eliminar el historial de la depreciación del libro de activos fijos, registrar el método de amortización por depreciación especial cuando lo conozca y enviar las transacciones de depreciación restantes del año.</span><span class="sxs-lookup"><span data-stu-id="5b8a2-123">You can then delete the depreciation history for the fixed asset book, post the special depreciation allowance when it's known, and then post the remaining depreciation transactions for the year.</span></span> 

<span data-ttu-id="5b8a2-124">Puede crear un número ilimitado de registros de amortización por depreciación especial.</span><span class="sxs-lookup"><span data-stu-id="5b8a2-124">You can create an unlimited number of special depreciation allowance records.</span></span> <span data-ttu-id="5b8a2-125">Cuando haya asignado dichos registros a un libro del grupo de activos, se aplican al libro de activos.</span><span class="sxs-lookup"><span data-stu-id="5b8a2-125">After you assign those records to an asset group book, they are applied to the asset book.</span></span> 

<span data-ttu-id="5b8a2-126">La amortización por depreciación especial se especifica como porcentaje o como importe fijo.</span><span class="sxs-lookup"><span data-stu-id="5b8a2-126">A special depreciation allowance is entered as either a percentage or a fixed amount.</span></span> <span data-ttu-id="5b8a2-127">Cuando se registran las propuestas de depreciación, las transacciones de depreciación de bonificación se registran en el libro como transacciones independientes de las transacciones de depreciación.</span><span class="sxs-lookup"><span data-stu-id="5b8a2-127">When you post depreciation proposals, special depreciation allowance transactions are posted to the book as transactions that are separate from the depreciation transactions.</span></span>

## <a name="depreciation-calendars"></a><span data-ttu-id="5b8a2-128">Calendarios de depreciación</span><span class="sxs-lookup"><span data-stu-id="5b8a2-128">Depreciation calendars</span></span>
<span data-ttu-id="5b8a2-129">Cada libro tiene un calendario que se utiliza cuando deprecia activos fijos.</span><span class="sxs-lookup"><span data-stu-id="5b8a2-129">Each book has a calendar that is used when you depreciate fixed assets.</span></span> <span data-ttu-id="5b8a2-130">De forma predeterminada, si no indica un calendario en el libro, el libro utiliza el calendario fiscal del libro mayor.</span><span class="sxs-lookup"><span data-stu-id="5b8a2-130">By default, if you don't indicate a calendar on the book, the book uses the ledger fiscal calendar.</span></span> <span data-ttu-id="5b8a2-131">Debe seleccionar un calendario fiscal para un libro cuando el perfil de depreciación asociado al libro utiliza un año de depreciación fiscal.</span><span class="sxs-lookup"><span data-stu-id="5b8a2-131">You must select a fiscal calendar for a book when the depreciation profile that is associated with the book uses a fiscal depreciation year.</span></span> 

<span data-ttu-id="5b8a2-132">Puede crear calendarios compartidos mediante la **página de Calendarios fiscales de** la Contabilidad general.</span><span class="sxs-lookup"><span data-stu-id="5b8a2-132">You can create shared calendars by using the **Fiscal calendars** page in General ledger.</span></span>

<span data-ttu-id="5b8a2-133">Para obtener más información, consulte [Convenciones y métodos de depreciación](depreciation-methods-conventions.md).</span><span class="sxs-lookup"><span data-stu-id="5b8a2-133">For more information, see [Depreciation methods and conventions](depreciation-methods-conventions.md).</span></span>





[!INCLUDE[footer-include](../../includes/footer-banner.md)]