---
title: 'MX-00008: Id. de registro de proveedores'
description: Este procedimiento le muestra cómo crear el proveedor para México de modo que se admita una declaración DIOT y otros informes legales.
author: sndray
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: VendTable
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.search.region: Mexico
ms.author: sndray
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: f59bf334a70de9a455a1e01b0da4aae535c1e6c1
ms.sourcegitcommit: 75db3b75d35d27034f9b56e7119c9d0cb7666830
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/03/2019
ms.locfileid: "2552338"
---
# <a name="mx-00008---vendor-registration-ids"></a><span data-ttu-id="c7ec7-103">MX-00008: Id. de registro de proveedores</span><span class="sxs-lookup"><span data-stu-id="c7ec7-103">MX-00008 - Vendor registration IDs</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="c7ec7-104">Este procedimiento le muestra cómo crear el proveedor para México de modo que se admita una declaración DIOT y otros informes legales.</span><span class="sxs-lookup"><span data-stu-id="c7ec7-104">This procedure walks you through creating the vendor for Mexico to support DIOT declaration and other legal reports.</span></span> <span data-ttu-id="c7ec7-105">Este procedimiento usa los datos de la empresa de demostración MXMF.</span><span class="sxs-lookup"><span data-stu-id="c7ec7-105">This procedure uses the MXMF demo company data.</span></span>

1. <span data-ttu-id="c7ec7-106">Vaya a Proveedores > Proveedores > Todos los proveedores.</span><span class="sxs-lookup"><span data-stu-id="c7ec7-106">Go to Accounts payable > Vendors > All vendors.</span></span>
2. <span data-ttu-id="c7ec7-107">Haga clic en Nuevo.</span><span class="sxs-lookup"><span data-stu-id="c7ec7-107">Click New.</span></span>
3. <span data-ttu-id="c7ec7-108">En el campo Nombre, escriba el nombre del proveedor.</span><span class="sxs-lookup"><span data-stu-id="c7ec7-108">In the Name field, enter the vendor's name.</span></span>
4. <span data-ttu-id="c7ec7-109">En el campo Grupo, seleccione un grupo para el proveedor.</span><span class="sxs-lookup"><span data-stu-id="c7ec7-109">In the Group field, select a group for the vendor.</span></span>
5. <span data-ttu-id="c7ec7-110">Expanda o contraiga la sección Factura y entrega.</span><span class="sxs-lookup"><span data-stu-id="c7ec7-110">Expand or collapse the Invoice and delivery section.</span></span>
6. <span data-ttu-id="c7ec7-111">En el campo Tipo de empresa, seleccione una opción.</span><span class="sxs-lookup"><span data-stu-id="c7ec7-111">In the Company type field, select an option.</span></span>
7. <span data-ttu-id="c7ec7-112">En el campo Número de RFC, escriba el número de RFC de 12 o 13 caracteres del proveedor.</span><span class="sxs-lookup"><span data-stu-id="c7ec7-112">In the RFC number field, enter the 12 or 13-character RFC number of the vendor..</span></span>
    * <span data-ttu-id="c7ec7-113">El número de Registro Federal del Contribuyentes (RFC) es el número de identificación fiscal asignado por las autoridades fiscales a una persona o una corporación.</span><span class="sxs-lookup"><span data-stu-id="c7ec7-113">The Federal Registration for Taxpayers (RFC) number is the tax identification number assigned by tax authorities to a person or corporation.</span></span> <span data-ttu-id="c7ec7-114">Los identificadores de registro de impuestos se validan según el formato especificado por las autoridades fiscales de México.</span><span class="sxs-lookup"><span data-stu-id="c7ec7-114">The tax registration IDs are validated according to the format specified by tax authorities in Mexico.</span></span>  
8. <span data-ttu-id="c7ec7-115">En el campo Número de CURP, escriba el número de CURP de 18 caracteres del proveedor.</span><span class="sxs-lookup"><span data-stu-id="c7ec7-115">In the CURP number field, enter the 18-character CURP number of the vendor..</span></span>
    * <span data-ttu-id="c7ec7-116">Si el tipo de empresa para este proveedor es una persona jurídica, este campo es obligatorio.</span><span class="sxs-lookup"><span data-stu-id="c7ec7-116">If the Company type for this vendor is Legal Person, this field is required.</span></span>  
9. <span data-ttu-id="c7ec7-117">En el campo Inscripción estatal, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="c7ec7-117">In the State inscription field, type a value.</span></span>
10. <span data-ttu-id="c7ec7-118">En el campo Tipo de proveedor, seleccione una opción.</span><span class="sxs-lookup"><span data-stu-id="c7ec7-118">In the Type of vendor field, select an option.</span></span>
11. <span data-ttu-id="c7ec7-119">En el campo Tipo de operación, seleccione una opción.</span><span class="sxs-lookup"><span data-stu-id="c7ec7-119">In the Type of operation field, select an option.</span></span>
    * <span data-ttu-id="c7ec7-120">La opción que seleccione se convierte en la selección predeterminada al crear transacciones de compras del proveedor.</span><span class="sxs-lookup"><span data-stu-id="c7ec7-120">The option that you select becomes the default selection when you create purchase transactions for the vendor.</span></span>  
    * <span data-ttu-id="c7ec7-121">Para los proveedores extranjeros, especifique el id. de registro de impuestos, el código de país o región y la nacionalidad.</span><span class="sxs-lookup"><span data-stu-id="c7ec7-121">For foreign vendors, enter the Tax registration ID, the country/region code, and the nationality.</span></span>  
12. <span data-ttu-id="c7ec7-122">Haga clic en Guardar.</span><span class="sxs-lookup"><span data-stu-id="c7ec7-122">Click Save.</span></span>

