---
title: Libros derivados
description: Este artículo proporciona información general de la función del libro derivado.
author: ShylaThompson
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: AssetBookTable
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.custom: 3401
ms.assetid: 862d6450-187b-497f-9822-cce45f2c65a9
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 5c31116ba234bd1fce445ac382fe8f8aea263a66
ms.sourcegitcommit: fbc106af09bdadb860677f590464fb93223cbf65
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/06/2019
ms.locfileid: "2769486"
---
# <a name="derived-books"></a><span data-ttu-id="a56d7-103">Libros derivados</span><span class="sxs-lookup"><span data-stu-id="a56d7-103">Derived books</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="a56d7-104">Este artículo proporciona información general de la función del libro derivado.</span><span class="sxs-lookup"><span data-stu-id="a56d7-104">This article provides an overview of derived book functionality.</span></span>

<span data-ttu-id="a56d7-105">El propósito de los libros derivados es simplificar el registro de transacciones de libro de activos fijos que se planifican para intervalos regulares.</span><span class="sxs-lookup"><span data-stu-id="a56d7-105">The purpose of derived books is to simplify the posting of fixed asset book transactions that are planned for regular intervals.</span></span>  <span data-ttu-id="a56d7-106">Debe elegir un libro como libro principal.</span><span class="sxs-lookup"><span data-stu-id="a56d7-106">You choose one book as the primary book.</span></span> <span data-ttu-id="a56d7-107">Este libro es el que se usa normalmente para la depreciación contable.</span><span class="sxs-lookup"><span data-stu-id="a56d7-107">This usually is the book that is used for accounting depreciation.</span></span> <span data-ttu-id="a56d7-108">A continuación, vincúlelo a otros libros que se configuran para registrar transacciones en los mismos intervalos que el libro principal.</span><span class="sxs-lookup"><span data-stu-id="a56d7-108">You then attach to it other books that are set up to post transactions in the same intervals as the primary book.</span></span> <span data-ttu-id="a56d7-109">Los libros de depreciación fiscal se suelen configurar como libros derivados.</span><span class="sxs-lookup"><span data-stu-id="a56d7-109">Tax depreciation books are often set up as derived books.</span></span> 

<span data-ttu-id="a56d7-110">Las transacciones que se configuran habitualmente para registrar los libros derivados son las adquisiciones, los ajustes de adquisición y las cancelaciones.</span><span class="sxs-lookup"><span data-stu-id="a56d7-110">The most common transactions to set up to post to derived books are acquisitions, acquisition adjustments, and disposals.</span></span> 

## <a name="example"></a><span data-ttu-id="a56d7-111">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="a56d7-111">Example</span></span>

<span data-ttu-id="a56d7-112">El libro B y el C se configuran como libros derivados para el libro A para el tipo de transacción de adquisición.</span><span class="sxs-lookup"><span data-stu-id="a56d7-112">Book B and book C are set up as derived books for book A for the Acquisition transaction type.</span></span> <span data-ttu-id="a56d7-113">En el libro A, introduzca una transacción de adquisición de 1.500,00 para el activo 123.</span><span class="sxs-lookup"><span data-stu-id="a56d7-113">In book A, you enter an acquisition transaction for asset 123 for 1,500.00.</span></span> 

<span data-ttu-id="a56d7-114">Una vez registrada la transacción, se genera una transacción de adquisición y se registra en el activo 123 para el libro B y en el activo 123 para el libro C de 1.500,00.</span><span class="sxs-lookup"><span data-stu-id="a56d7-114">When the transaction is posted, an acquisition transaction is generated and posted in asset 123 for book B and in asset 123 for book C for 1,500.00.</span></span> <span data-ttu-id="a56d7-115">Cuando se preparan las transacciones del libro principal para registrarlas en el diario de activos fijos, también puede ver y modificar las transacciones de libros derivados.</span><span class="sxs-lookup"><span data-stu-id="a56d7-115">When you prepare the transactions of the primary book for posting in the fixed asset journal, you can also view and modify the transactions of the derived books.</span></span> <span data-ttu-id="a56d7-116">Si prepara las transacciones del libro principal en otro diario, no se mostrarán las transacciones del valor derivado.</span><span class="sxs-lookup"><span data-stu-id="a56d7-116">If you prepare the primary book transactions in another journal, the transactions of the derived value are not displayed.</span></span> <span data-ttu-id="a56d7-117">Sin embargo, se registrarán en las cuentas y capas de registro adecuadas cuando registre las transacciones del libro principal.</span><span class="sxs-lookup"><span data-stu-id="a56d7-117">However, they are posted to the appropriate accounts and posting layers when you post the primary book transactions.</span></span>

> [!NOTE]                                                                                                                               
> <span data-ttu-id="a56d7-118">Los libros que se configuran para registrar transacciones en intervalos distintos a los intervalos del libro principal, se deben vincular al activo fijo como libros independientes y no como libros derivados.</span><span class="sxs-lookup"><span data-stu-id="a56d7-118">Books that are set up to post transactions at intervals other than the primary book intervals must be attached to the fixed asset as separate books and not as derived books.</span></span>  

<span data-ttu-id="a56d7-119">Para obtener más información, consulte [Registrar con libros derivados](post-derived-value-models.md).</span><span class="sxs-lookup"><span data-stu-id="a56d7-119">For more information, see [Post with derived books](post-derived-value-models.md).</span></span>



