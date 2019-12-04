---
title: Registrar las transacciones de activos fijos para registrar capas
description: Este artículo ofrece una visión general de la funcionalidad de la capa de registro para las transacciones de activos fijos.
author: ShylaThompson
manager: AnnBe
ms.date: 04/25/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: AssetBookTable, LedgerJournalTransAsset
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.custom: 3001
ms.assetid: 7dabde57-0843-47c3-85ef-f36b6f472e30
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: bc8c4f4f41ed39447ae441dd8e01cfcf80c939b5
ms.sourcegitcommit: fbc106af09bdadb860677f590464fb93223cbf65
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/06/2019
ms.locfileid: "2770721"
---
# <a name="post-fixed-asset-transactions-to-posting-layers"></a><span data-ttu-id="08d4d-103">Registrar las transacciones de activos fijos para registrar capas</span><span class="sxs-lookup"><span data-stu-id="08d4d-103">Post fixed asset transactions to posting layers</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="08d4d-104">Este artículo ofrece una visión general de la funcionalidad de la capa de registro para las transacciones de activos fijos.</span><span class="sxs-lookup"><span data-stu-id="08d4d-104">This article gives an overview of posting layer functionality for fixed asset transactions.</span></span>

<span data-ttu-id="08d4d-105">Un activo fijo se deprecia de distintas formas y para distintos fines.</span><span class="sxs-lookup"><span data-stu-id="08d4d-105">A fixed asset is often depreciated in different ways for different purposes.</span></span> <span data-ttu-id="08d4d-106">La depreciación relacionada con los impuestos se calcula usando las reglas actuales de impuestos para lograr la depreciación más alta posible antes de los impuestos, pero la depreciación a efectos de notificación se calcula de acuerdo con los estándares y leyes contables.</span><span class="sxs-lookup"><span data-stu-id="08d4d-106">Depreciation for tax purposes is calculated by using current tax rules to achieve the highest possible depreciation before taxes, but depreciation for reporting purposes is calculated according to accounting laws and standards.</span></span> <span data-ttu-id="08d4d-107">Los distintos tipos de depreciación se calculan y registran independientemente en las capas de registro.</span><span class="sxs-lookup"><span data-stu-id="08d4d-107">The various kinds of depreciation are calculated and recorded separately in the posting layers.</span></span>

<span data-ttu-id="08d4d-108">Cada libro vinculado a un activo fijo se configura para una capa de registro concreta que tiene un objetivo de depreciación general.</span><span class="sxs-lookup"><span data-stu-id="08d4d-108">Each book that is attached to a fixed asset is set up for a particular posting layer that has an overall depreciation objective.</span></span> <span data-ttu-id="08d4d-109">Existen diez capas de registro: Actual, operaciones, Impuesto y siete niveles personalizados.</span><span class="sxs-lookup"><span data-stu-id="08d4d-109">There are ten posting layers: Current, Operations, Tax, and seven Custom layers.</span></span> <span data-ttu-id="08d4d-110">También puede deshabilitar el registro del libro en la contabilidad general configurando el campo Registrar en el libro mayora No.</span><span class="sxs-lookup"><span data-stu-id="08d4d-110">You can also disable posting to the general ledger for the book by setting the Post to general ledger field to No.</span></span> <span data-ttu-id="08d4d-111">El campo de Capa de registro se establece automáticamente como Ninguno.</span><span class="sxs-lookup"><span data-stu-id="08d4d-111">The Posting layer field is then automatically set to None.</span></span> <span data-ttu-id="08d4d-112">Normalmente, los libros que no se registran en la contabilidad general se usan para fines de informes tributarios.</span><span class="sxs-lookup"><span data-stu-id="08d4d-112">Typically, books that don’t post to the general ledger are used for tax reporting purposes.</span></span> <span data-ttu-id="08d4d-113">Este método proporciona flexibilidad adicional para eliminar las transacciones históricas para el libro de activos, ya que no se han asignado a la contabilidad general.</span><span class="sxs-lookup"><span data-stu-id="08d4d-113">This approach gives you the additional flexibility to delete historical transactions for the asset book, because they haven’t been committed to the general ledger.</span></span>

<span data-ttu-id="08d4d-114">Los diarios de activos se definen mediante la página de Nombres de diario en Contabilidad general > Configuración del diario > Nombres de diario.</span><span class="sxs-lookup"><span data-stu-id="08d4d-114">Fixed asset journals are defined by using the Journal names page at General ledger > Journal setup > Journal names.</span></span> <span data-ttu-id="08d4d-115">Cada diario en el que puede registrar las depreciaciones se define por su nombre de diario para una capa de registro únicamente.</span><span class="sxs-lookup"><span data-stu-id="08d4d-115">Each journal that you can post depreciations in is defined by its journal name for only one posting layer.</span></span> <span data-ttu-id="08d4d-116">La capa de registro del diario no se puede cambiar.</span><span class="sxs-lookup"><span data-stu-id="08d4d-116">The posting layer in the journal can’t be changed.</span></span> <span data-ttu-id="08d4d-117">Esta restricción permite garantizar que las transacciones de cada capa de registro se mantengan aparte.</span><span class="sxs-lookup"><span data-stu-id="08d4d-117">This restriction helps guarantee that transactions for each posting layer are kept separate.</span></span> <span data-ttu-id="08d4d-118">Se debe crear un nombre de diario como mínimo para cada capa de registro.</span><span class="sxs-lookup"><span data-stu-id="08d4d-118">At least one journal name must be created for each posting layer.</span></span> <span data-ttu-id="08d4d-119">Si utiliza libros que no se registran en la contabilidad general, también deberá crear un diario en el que la capa de registro se establezca en Ninguno.</span><span class="sxs-lookup"><span data-stu-id="08d4d-119">If you’re using books that don’t post to the general ledger, you must also create a journal where the posting layer is set to None.</span></span>

<span data-ttu-id="08d4d-120">Puede especificar las cuentas contables para las transacciones de activos fijos en la página de Perfiles de contabilización de activos fijos.</span><span class="sxs-lookup"><span data-stu-id="08d4d-120">You can designate ledger accounts for fixed asset transactions on the Fixed asset posting profiles page.</span></span> <span data-ttu-id="08d4d-121">Para cada perfil de registro, debe seleccionar el tipo de transacción y el libro correspondiente, y después designar las cuentas contables.</span><span class="sxs-lookup"><span data-stu-id="08d4d-121">For each posting profile, you must select the relevant transaction type and book, and then designate the ledger accounts.</span></span> <span data-ttu-id="08d4d-122">Configurar un registro del perfil de contabilización para cada libro que se envía a la contabilidad general.</span><span class="sxs-lookup"><span data-stu-id="08d4d-122">Set up a posting profile record for each book that will post to the general ledger.</span></span>

> [!NOTE] 
> <span data-ttu-id="08d4d-123">El uso de libros derivados le permite registrar transacciones para distintas capas de registro simultáneamente.</span><span class="sxs-lookup"><span data-stu-id="08d4d-123">By using derived books, you can post transactions to different posting layers at the same time.</span></span> <span data-ttu-id="08d4d-124">Puede crear transacciones del libro principal en un diario con la capa de registro correspondiente a la capa de registro del libro.</span><span class="sxs-lookup"><span data-stu-id="08d4d-124">You create the transactions of the primary book in a journal where the posting layer corresponds to the book posting layer.</span></span> <span data-ttu-id="08d4d-125">Durante el registro, las transacciones derivadas del libro se registran en sus capas de registro adecuadas.</span><span class="sxs-lookup"><span data-stu-id="08d4d-125">During posting, the derived book transactions are posted to the appropriate posting layers.</span></span>

<span data-ttu-id="08d4d-126">Para obtener más información, consulte [Libros derivados](derived-books.md) y [Registrar con los libros derivados](post-derived-value-models.md).</span><span class="sxs-lookup"><span data-stu-id="08d4d-126">For more information see, [Derived books](derived-books.md) and [Post with derived books](post-derived-value-models.md).</span></span>



