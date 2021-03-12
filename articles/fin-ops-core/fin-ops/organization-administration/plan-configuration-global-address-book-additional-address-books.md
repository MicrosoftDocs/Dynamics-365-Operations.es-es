---
title: Plan para la libreta de direcciones global y otras libretas de direcciones
description: Este tema describe las consideraciones y las decisiones que debe realizar durante el proceso de planificación, antes de configurar y configurar la libreta de direcciones global y todas las libretas de direcciones adicionales.
author: msftbrking
manager: AnnBe
ms.date: 01/13/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: DirAddressBook, DirAddressBookTeam, DirParameters, DirPartyTable
audience: Application User
ms.reviewer: sericks
ms.custom: 23341
ms.assetid: a41cd8de-9ee0-4275-aea5-131db5326e5b
ms.search.region: Global
ms.author: brking
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 8f0a53e1f9b378759e0c5adbe0612a5fa8cddc82
ms.sourcegitcommit: b112925c389a460a98c3401cc2c67df7091b066f
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/19/2020
ms.locfileid: "4796955"
---
# <a name="plan-for-the-global-address-book-and-other-address-books"></a><span data-ttu-id="33e1e-103">Plan para la libreta de direcciones global y otras libretas de direcciones</span><span class="sxs-lookup"><span data-stu-id="33e1e-103">Plan for the global address book and other address books</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="33e1e-104">Este tema describe las consideraciones y las decisiones que debe realizar durante el proceso de planificación, antes de configurar y configurar la libreta de direcciones global y todas las libretas de direcciones adicionales.</span><span class="sxs-lookup"><span data-stu-id="33e1e-104">This topic describes the considerations and decisions that you must make during the planning process, before you set up and configure the global address book and any additional address books.</span></span> <span data-ttu-id="33e1e-105">Algunas de las decisiones requerirán que confirme las decisiones que se han realizado para otras áreas de producto, como la jerarquía organizativa.</span><span class="sxs-lookup"><span data-stu-id="33e1e-105">Some of the decisions will require that you confirm the decisions that have been made for other areas of the product, such as the organization hierarchy.</span></span>

## <a name="global-address-book"></a><span data-ttu-id="33e1e-106">Libreta de direcciones global</span><span class="sxs-lookup"><span data-stu-id="33e1e-106">Global address book</span></span>

<span data-ttu-id="33e1e-107">Antes de comenzar a trabajar con la libreta de direcciones global, debe determinar los valores predeterminados para ella.</span><span class="sxs-lookup"><span data-stu-id="33e1e-107">Before you begin to work with the global address book, you must determine the default values for it.</span></span> <span data-ttu-id="33e1e-108">Estos valores predeterminados se usan para todas las libretas de direcciones adicionales que cree.</span><span class="sxs-lookup"><span data-stu-id="33e1e-108">These default values are then used for any additional address books that you create.</span></span>

<span data-ttu-id="33e1e-109">**Decisiones**</span><span class="sxs-lookup"><span data-stu-id="33e1e-109">**Decisions**</span></span>

- <span data-ttu-id="33e1e-110">¿En qué secuencia se deben mostrar los nombres para los registros de parte del tipo **Persona**?</span><span class="sxs-lookup"><span data-stu-id="33e1e-110">What sequence should names be displayed in for party records of the **Person** type?</span></span> <span data-ttu-id="33e1e-111">Por ejemplo, una secuencia es apellido, segundo nombre, nombre.</span><span class="sxs-lookup"><span data-stu-id="33e1e-111">For example, one sequence is last name, middle name, first name.</span></span>
- <span data-ttu-id="33e1e-112">¿Se deben eliminar los registros de parte de la libreta de direcciones cuando se elimina el rol de registro?</span><span class="sxs-lookup"><span data-stu-id="33e1e-112">Should party records be deleted from the address book when the role record is deleted?</span></span> <span data-ttu-id="33e1e-113">Por ejemplo, si se elimina un registro de cliente, ¿se debe eliminar también el registro de parte?</span><span class="sxs-lookup"><span data-stu-id="33e1e-113">For example, if a customer record is deleted, should the party record also be deleted?</span></span>
- <span data-ttu-id="33e1e-114">Cuándo se crea un registro nuevo, ¿se deben notificar los usuarios se si encuentra un registro duplicado en la libreta de direcciones global?</span><span class="sxs-lookup"><span data-stu-id="33e1e-114">When a new record is created, should users be notified if a duplicate record is found in the global address book?</span></span>
- <span data-ttu-id="33e1e-115">¿Debe incluirse el número del Sistema de numeración universal de datos (DUNS) en la información del registro de parte?</span><span class="sxs-lookup"><span data-stu-id="33e1e-115">Should the Data Universal Numbering System (DUNS) number be included in a party record's information?</span></span>
- <span data-ttu-id="33e1e-116">Si el número DUNS se incluye en un registro de parte, ¿debe comprobarse la unicidad del número?</span><span class="sxs-lookup"><span data-stu-id="33e1e-116">If the DUNS number is included in a party record, should the uniqueness of the number be checked?</span></span>
- <span data-ttu-id="33e1e-117">Cuándo se crea un registro de parte en la libreta de direcciones global, ¿desea un tipo de parte, una persona o una organización predeterminados?</span><span class="sxs-lookup"><span data-stu-id="33e1e-117">When a party record is created in the global address book, do you want a default party type, person, or organization?</span></span>
- <span data-ttu-id="33e1e-118">¿Qué roles de usuario deben tener acceso a las direcciones privadas y a la información de los registros de partes?</span><span class="sxs-lookup"><span data-stu-id="33e1e-118">Which user roles should have access to the private addresses and contact information of party records?</span></span>

## <a name="additional-address-books"></a><span data-ttu-id="33e1e-119">Libretas de direcciones adicionales</span><span class="sxs-lookup"><span data-stu-id="33e1e-119">Additional address books</span></span>

<span data-ttu-id="33e1e-120">Después de crear la libreta de direcciones global, puede crear libretas de direcciones adicionales como sea necesario, como una libreta de direcciones independiente para cada empresa de su organización o para cada línea de negocio.</span><span class="sxs-lookup"><span data-stu-id="33e1e-120">After you create the global address book, you can create additional address books as you require, such as a separate address book for each company in your organization or for each line of business.</span></span> <span data-ttu-id="33e1e-121">Por ejemplo, Fabrikam es una organización internacional con varias empresas y líneas de negocios.</span><span class="sxs-lookup"><span data-stu-id="33e1e-121">For example, Fabrikam is an international organization that has multiple companies and multiple lines of business.</span></span> <span data-ttu-id="33e1e-122">Fabrikam planea crear una libreta de direcciones para cada línea de negocios.</span><span class="sxs-lookup"><span data-stu-id="33e1e-122">Fabrikam plans to create an address book for each line of business.</span></span> <span data-ttu-id="33e1e-123">En el caso de las líneas de negocios que están presentes en más de una ubicación —por ejemplo, la empresa de herramientas neumáticas—, Fabrikam planea crear una libreta de direcciones para cada ubicación.</span><span class="sxs-lookup"><span data-stu-id="33e1e-123">For lines of business that occur in more than one location, such as the pneumatic tools business, Fabrikam plans to create an address book for each location.</span></span> <span data-ttu-id="33e1e-124">Chris, el encargado de TI en Fabrikam, ha creado la lista siguiente de las libretas de direcciones que se requieren.</span><span class="sxs-lookup"><span data-stu-id="33e1e-124">Chris, the IT manager at Fabrikam, has created the following list of address books that are required.</span></span> <span data-ttu-id="33e1e-125">Esta lista también describe los registros de parte que cada libreta de direcciones debe incluir.</span><span class="sxs-lookup"><span data-stu-id="33e1e-125">This list also describes the party records that each address book must include.</span></span>

- <span data-ttu-id="33e1e-126">**Contratos del sector público (PubSC)**: registros de parte de todas las partes involucradas en los contratos del sector público que Fabrikam mantiene.</span><span class="sxs-lookup"><span data-stu-id="33e1e-126">**Public Sector Contracts (PubSC)** – Party records for all parties that are involved in the public sector contracts that Fabrikam holds.</span></span>
- <span data-ttu-id="33e1e-127">**Contratos del sector privado (PriSC)**: registros de parte de todas las partes involucradas en los contratos del sector privado que Fabrikam mantiene.</span><span class="sxs-lookup"><span data-stu-id="33e1e-127">**Private Sector Contracts (PriSC)** – Party records for all parties that are involved in the private sector contracts that Fabrikam holds.</span></span>
- <span data-ttu-id="33e1e-128">**Herramientas electrónicas (ET)**: registros de parte de todas las partes que están involucradas en la compra o venta de herramientas electrónicas o que, de lo contrario, tienen relación con las herramientas electrónicas que proporciona o adquiere Fabrikam en la empresa Fabrikam-Japón.</span><span class="sxs-lookup"><span data-stu-id="33e1e-128">**Electronic Tools (ET)** – Party records for all parties that are involved in the purchase or sale of electronic tools, or that otherwise interact with the electronic tools that are provided by or purchased for Fabrikam in the Fabrikam-Japan company.</span></span>
- <span data-ttu-id="33e1e-129">**Herramientas neumáticas (PTJPN)**: registros de parte de todas las partes que están involucradas en la compra o venta de herramientas neumáticas o que, de lo contrario, tienen relación con las herramientas neumáticas que proporciona o adquiere Fabrikam en la empresa Fabrikam-Japón.</span><span class="sxs-lookup"><span data-stu-id="33e1e-129">**Pneumatic Tools (PTJPN)** – Party records for all parties that are involved in the purchase or sale of pneumatic tools, or that otherwise interact with the pneumatic tools that are provided by or purchased for Fabrikam in the Fabrikam-Japan company.</span></span>
- <span data-ttu-id="33e1e-130">**Herramientas neumáticas (PTUSA)**: registros de parte de todas las partes que están involucradas en la compra o venta de herramientas neumáticas o que, de lo contrario, tienen relación con las herramientas neumáticas que proporciona o adquiere Fabrikam en la empresa Fabrikam-US.</span><span class="sxs-lookup"><span data-stu-id="33e1e-130">**Pneumatic Tools (PTUSA)** – Party records for all parties that are involved in the purchase or sale of pneumatic tools, or that otherwise interact with the pneumatic tools that are provided by or purchased for Fabrikam in the Fabrikam-US company.</span></span>

<span data-ttu-id="33e1e-131">**Decisión:**</span><span class="sxs-lookup"><span data-stu-id="33e1e-131">**Decision:**</span></span>

- <span data-ttu-id="33e1e-132">¿Cuántas libretas de direcciones adicionales creará?</span><span class="sxs-lookup"><span data-stu-id="33e1e-132">How many additional address books will you create?</span></span>
