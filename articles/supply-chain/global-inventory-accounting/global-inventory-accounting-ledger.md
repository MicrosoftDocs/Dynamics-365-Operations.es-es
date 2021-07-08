---
title: Libro mayor de contabilidad de inventario global
description: Este tema describe los libros de contabilidad de inventario global, que se definen mediante una combinación de una moneda, un calendario, una convención y una asociación con una entidad jurídica.
author: AndersGirke
ms.date: 06/18/2021
ms.topic: article
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: aevengir
ms.search.validFrom: 2021-06-18
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: ea3434675aa3b7f2304be93ef9b489747994fa9d
ms.sourcegitcommit: eceae470f4ae58000ec33fea34db34b7a7a1af43
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/18/2021
ms.locfileid: "6273220"
---
# <a name="global-inventory-accounting-ledger"></a><span data-ttu-id="0bef6-103">Libro mayor de contabilidad de inventario global</span><span class="sxs-lookup"><span data-stu-id="0bef6-103">Global Inventory Accounting ledger</span></span>

[!include [banner](../includes/banner.md)]
[!INCLUDE [preview-banner](../includes/preview-banner.md)]

<span data-ttu-id="0bef6-104">La contabilidad de inventario global tiene su propio conjunto de libros mayores.</span><span class="sxs-lookup"><span data-stu-id="0bef6-104">Global Inventory Accounting has its own set of ledgers.</span></span> <span data-ttu-id="0bef6-105">Cada vez que se procesa una transacción relacionada con el inventario para una entidad legal relevante, el sistema puede contabilizar esa transacción en cualquier número de libros de contabilidad de inventario global, según sea necesario.</span><span class="sxs-lookup"><span data-stu-id="0bef6-105">Each time an inventory-related transaction is processed for a relevant legal entity, the system can account for that transaction in any number of Global Inventory Accounting ledgers, as required.</span></span>

<span data-ttu-id="0bef6-106">Un libro es un registro de medidas de débito y de crédito.</span><span class="sxs-lookup"><span data-stu-id="0bef6-106">A ledger is a register of debit and credit measures.</span></span> <span data-ttu-id="0bef6-107">Estas medidas se clasifican utilizando elementos de costo y cuentas del libro mayor auxiliar.</span><span class="sxs-lookup"><span data-stu-id="0bef6-107">These measures are classified by using cost elements and subledger accounts.</span></span> <span data-ttu-id="0bef6-108">Un libro de contabilidad de inventario global se define por su combinación de una moneda, un calendario, una convención y una asociación con una entidad jurídica.</span><span class="sxs-lookup"><span data-stu-id="0bef6-108">A Global Inventory Accounting ledger is defined by its combination of a currency, a calendar, a convention, and an association with a legal entity.</span></span>

<span data-ttu-id="0bef6-109">Para configurar sus libros de contabilidad de inventario global, vaya a **Contabilidad global de inventarios \> Configuración \> Libros mayores de contabilidad de inventario global**.</span><span class="sxs-lookup"><span data-stu-id="0bef6-109">To set up your Global Inventory Accounting ledgers, go to **Global inventory accounting \> Setup \> Global inventory accounting ledgers**.</span></span> <span data-ttu-id="0bef6-110">Para cada libro, establezca los siguientes campos:</span><span class="sxs-lookup"><span data-stu-id="0bef6-110">For each ledger, set the following fields:</span></span>

- <span data-ttu-id="0bef6-111">**Nombre**: especifique el nombre del libro.</span><span class="sxs-lookup"><span data-stu-id="0bef6-111">**Name** – Enter the name of the ledger.</span></span>
- <span data-ttu-id="0bef6-112">**Descripción**: escriba una descripción del libro.</span><span class="sxs-lookup"><span data-stu-id="0bef6-112">**Description** – Enter a description of the ledger.</span></span>
- <span data-ttu-id="0bef6-113">**Calendario fiscal** - Especifique el calendario fiscal para el libro mayor.</span><span class="sxs-lookup"><span data-stu-id="0bef6-113">**Fiscal calendar** – Specify the fiscal calendar for the ledger.</span></span>
- <span data-ttu-id="0bef6-114">**Tipo de moneda y tipo de cambio** - Utilice los campos de esta ficha desplegable para seleccionar la moneda de contabilidad que utiliza el libro mayor y el tipo de tipo de cambio.</span><span class="sxs-lookup"><span data-stu-id="0bef6-114">**Currency and exchange rate type** – Use the fields on this FastTab to select the accounting currency that the ledger uses, and the exchange rate type.</span></span> <span data-ttu-id="0bef6-115">La moneda que seleccione puede diferir de la moneda que utiliza la entidad jurídica.</span><span class="sxs-lookup"><span data-stu-id="0bef6-115">The currency that you select can differ from the currency that the legal entity uses.</span></span> <span data-ttu-id="0bef6-116">En la Contabilidad de inventario global, los usuarios pueden definir tantos libros de costes como necesiten.</span><span class="sxs-lookup"><span data-stu-id="0bef6-116">In Global Inventory Accounting, users can define as many costing ledgers as they require.</span></span> <span data-ttu-id="0bef6-117">La contabilidad de inventario global admite la contabilidad de inventario en múltiples monedas y en múltiples valoraciones.</span><span class="sxs-lookup"><span data-stu-id="0bef6-117">Global Inventory Accounting supports inventory accounting in multiple currencies and in multiple valuations.</span></span> <span data-ttu-id="0bef6-118">Establezca los campos siguientes:</span><span class="sxs-lookup"><span data-stu-id="0bef6-118">Set the following fields:</span></span>

    - <span data-ttu-id="0bef6-119">**Divisa** - Seleccione la moneda de cálculo de costes en la que se actualizan los valores relacionados con el inventario.</span><span class="sxs-lookup"><span data-stu-id="0bef6-119">**Currency** – Select the costing currency that inventory-related values are maintained in.</span></span> <span data-ttu-id="0bef6-120">Estos valores incluyen el valor del inventario, el costo de los bienes vendidos, el inventario en tránsito y todo tipo de variaciones.</span><span class="sxs-lookup"><span data-stu-id="0bef6-120">These values include the inventory value, cost of goods sold, inventory in transit, and all kinds of variance.</span></span>
    - <span data-ttu-id="0bef6-121">**Tipo de tipo de cambio** - Seleccione el tipo de cambio que el sistema debe usar para convertir el monto de la transacción en la moneda de la transacción y el costo estándar de los artículos en la moneda de cálculo de costos.</span><span class="sxs-lookup"><span data-stu-id="0bef6-121">**Exchange rate type** – Select the exchange rate that the system should use to convert the transaction amount in the transaction currency and the standard cost of the items into the costing currency.</span></span>

- <span data-ttu-id="0bef6-122">**Nombre de la convención** - Especificar una convención.</span><span class="sxs-lookup"><span data-stu-id="0bef6-122">**Convention name** – Specify a convention.</span></span> <span data-ttu-id="0bef6-123">Una convención es una colección de políticas que establecen cómo se contabilizarán los costos en este libro mayor.</span><span class="sxs-lookup"><span data-stu-id="0bef6-123">A convention is a collection of policies that establish how costs will be accounted in this ledger.</span></span>
- <span data-ttu-id="0bef6-124">**Entidad legal** - El libro mayor contabilizará los documentos que se contabilizan en la entidad jurídica seleccionada.</span><span class="sxs-lookup"><span data-stu-id="0bef6-124">**Legal entity** – The ledger will account the documents that are posted to the selected legal entity.</span></span>
- <span data-ttu-id="0bef6-125">**Cebado** - Seleccione si las transacciones de inventario que se crearon antes de que se creara el libro mayor deben procesarse de acuerdo con la moneda y la convención en el libro mayor.</span><span class="sxs-lookup"><span data-stu-id="0bef6-125">**Priming** – Select whether inventory transactions that were created before the ledger was created should be processed according to the currency and convention in the ledger.</span></span> <span data-ttu-id="0bef6-126">Seleccione uno de los siguientes valores:</span><span class="sxs-lookup"><span data-stu-id="0bef6-126">Select one of the following values:</span></span>

    - <span data-ttu-id="0bef6-127">**Activado** - El libro mayor debe procesar las transacciones que se crearon antes de que se creara el libro mayor.</span><span class="sxs-lookup"><span data-stu-id="0bef6-127">**Activated** – The ledger should process transactions that were created before the ledger was created.</span></span>
    - <span data-ttu-id="0bef6-128">**Desactivado** - El libro mayor debe procesar solo las transacciones que se crearon después de que se creara el libro mayor.</span><span class="sxs-lookup"><span data-stu-id="0bef6-128">**Deactivated** – The ledger should process only transactions that are created after the ledger was created.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="0bef6-129">**No** podrá regresar y configurar este campo después de ingresar nuevos documentos.</span><span class="sxs-lookup"><span data-stu-id="0bef6-129">You will **not** be able to come back and set this field after you enter new documents.</span></span>

- <span data-ttu-id="0bef6-130">**Estado** - El sistema establece automáticamente el estado de los libros de contabilidad recién creados en *Preparar*.</span><span class="sxs-lookup"><span data-stu-id="0bef6-130">**Status** – The system automatically sets the status of newly created ledgers to *Prepare*.</span></span>
