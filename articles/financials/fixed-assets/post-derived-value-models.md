---
title: Registro con los libros derivados
description: "Este artículo describe cómo usar los libros derivados."
author: ShylaThompson
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: AssetBookTable, LedgerJournalTransAsset
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.custom: 3421
ms.assetid: f5187c21-eec5-4148-b178-b8a5feff7f23
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 1d98cbff30620256c9d13e7b4a90314db150e33e
ms.openlocfilehash: ff1dbf67a53a5639e448da707898b55cd00cba94
ms.contentlocale: es-es
ms.lasthandoff: 08/07/2018

---

# <a name="post-with-derived-books"></a><span data-ttu-id="2a60e-103">Registro con los libros derivados</span><span class="sxs-lookup"><span data-stu-id="2a60e-103">Post with derived books</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="2a60e-104">Este artículo describe cómo usar los libros derivados.</span><span class="sxs-lookup"><span data-stu-id="2a60e-104">This article describes how to use derived books.</span></span>

<span data-ttu-id="2a60e-105">Al registrar transacciones para un libro que contiene libros derivados, las transacciones del libro derivado se registran de forma automática en los diarios, pedidos de compra o facturas de servicios.</span><span class="sxs-lookup"><span data-stu-id="2a60e-105">When you post transactions for a book that contains derived books, the derived book transactions are posted automatically in journals, purchase orders, or free text invoices.</span></span> <span data-ttu-id="2a60e-106">No obstante, si prepara las transacciones del libro principal en el libro de activos fijos, podrá ver y modificar los importes de las transacciones derivadas antes de registrarlos.</span><span class="sxs-lookup"><span data-stu-id="2a60e-106">However, if you prepare the primary book transactions in the Fixed assets journal, you can view and modify the amounts of the derived transactions before you post them.</span></span>
-   <span data-ttu-id="2a60e-107">Algunas cuentas, como las cuentas de proveedor y cliente e impuestos, se actualizan únicamente mediante los registros del libro principal.</span><span class="sxs-lookup"><span data-stu-id="2a60e-107">Certain accounts, such as sales tax and customer or vendor accounts, are updated only once by postings of the primary book.</span></span> <span data-ttu-id="2a60e-108">Las transacciones del libro derivado se contabilizan en las cuentas que se han definido para el libro derivado en la página de Perfiles de contabilización de activos fijos.</span><span class="sxs-lookup"><span data-stu-id="2a60e-108">The derived book transactions are posted to the accounts that have been defined for the derived book in the Fixed asset posting profiles page.</span></span>
-   <span data-ttu-id="2a60e-109">La adquisición se usa a menudo como el tipo de transacción del libro derivado.</span><span class="sxs-lookup"><span data-stu-id="2a60e-109">Acquisition is often used as the transaction type for the derived books.</span></span> <span data-ttu-id="2a60e-110">Esto se usa cuando el libro y el libro derivado se deben aplicar al activo fijo desde el momento de adquisición del activo fijo.</span><span class="sxs-lookup"><span data-stu-id="2a60e-110">You use this when the book and the derived book should be applied to the fixed asset from the time of the acquisition of the fixed asset.</span></span>
-   <span data-ttu-id="2a60e-111">También se pueden aplicar otros valores para el tipo de transacción.</span><span class="sxs-lookup"><span data-stu-id="2a60e-111">Other values for the transaction type can also apply.</span></span> <span data-ttu-id="2a60e-112">Por ejemplo, si el libro principal de los libros derivados tiene los mismos intervalos en relación con la venta o cancelación, todos los tipos de transacción de activos fijos están disponibles para la configuración de un libro derivado.</span><span class="sxs-lookup"><span data-stu-id="2a60e-112">For example, if the primary book and the derived books have the same intervals regarding sale or disposal, all fixed asset transaction types are available for the setup of a derived book.</span></span>

> [!WARNING]
> <span data-ttu-id="2a60e-113">La depreciación registrada en el libro derivado será del mismo importe que se registró para el libro principal.</span><span class="sxs-lookup"><span data-stu-id="2a60e-113">Depreciation posted in the derived book will be the same amount as was posted for the primary book.</span></span> <span data-ttu-id="2a60e-114">Si los métodos de depreciación son distintos entre los libros, no debe generar transacciones de depreciación mediante el proceso derivado.</span><span class="sxs-lookup"><span data-stu-id="2a60e-114">If the depreciation methods are different between the books, you should not generate depreciation transactions using the derived process.</span></span> |

## <a name="example"></a><span data-ttu-id="2a60e-115">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="2a60e-115">Example</span></span> 
<span data-ttu-id="2a60e-116">La siguiente información describe cómo configurar las transacciones de adquisición con la función del libro derivado.</span><span class="sxs-lookup"><span data-stu-id="2a60e-116">The following information describes how to set up acquisition transactions with the derived book functionality.</span></span>

1.  <span data-ttu-id="2a60e-117">Crear libros en la página de Libros.</span><span class="sxs-lookup"><span data-stu-id="2a60e-117">Create the books on the Books page.</span></span>
    -   <span data-ttu-id="2a60e-118">El libro de contabilidad: MV 1, capa de registro actual</span><span class="sxs-lookup"><span data-stu-id="2a60e-118">The book for accounting: VM 1, Current posting layer</span></span>
    -   <span data-ttu-id="2a60e-119">El libro con fines tributarios: MV 2, capa de registro de impuestos</span><span class="sxs-lookup"><span data-stu-id="2a60e-119">The book for tax purposes: VM 2, Tax posting layer</span></span>

2.  <span data-ttu-id="2a60e-120">En el MV 1, haga clic en la ficha de libros derivados y seleccione MV 2 en el campo Libro y Adquisición en el campo Tipo de transacción.</span><span class="sxs-lookup"><span data-stu-id="2a60e-120">On VM 1, click the Derived books tab. Select VM 2 in the Book field, and Acquisition in the Transaction type field.</span></span>

<span data-ttu-id="2a60e-121">A continuación, los libros se podrán vincular a activos fijos concretos.</span><span class="sxs-lookup"><span data-stu-id="2a60e-121">The books then can be attached to specific fixed assets.</span></span> 

<span data-ttu-id="2a60e-122">Cuando una adquisición se registra para un activo fijo con libro MV 1, la adquisición se registra no sólo con el MV 1, sino también con el libro derivado MV 2.</span><span class="sxs-lookup"><span data-stu-id="2a60e-122">When an acquisition is posted for a fixed asset with book VM 1, the acquisition is posted not only on VM 1, but also on the derived book VM 2.</span></span> <span data-ttu-id="2a60e-123">El estado de ambos libros de activo fijo se actualizará a Abierto.</span><span class="sxs-lookup"><span data-stu-id="2a60e-123">The status of both fixed asset books is updated to Open.</span></span>

> [!NOTE]                                                                                                         
> <span data-ttu-id="2a60e-124">Si no utiliza los libros derivados, debe registrar la adquisición del activo fijo para el libro MV 1 y el libro VM 2.</span><span class="sxs-lookup"><span data-stu-id="2a60e-124">If you do not use derived books, you must post the acquisition of the fixed asset both for book VM 1 and book VM 2.</span></span>

<span data-ttu-id="2a60e-125">Para obtener más información, consulte [Libros derivados](derived-books.md).</span><span class="sxs-lookup"><span data-stu-id="2a60e-125">For more information, see [Derived books](derived-books.md)</span></span>




