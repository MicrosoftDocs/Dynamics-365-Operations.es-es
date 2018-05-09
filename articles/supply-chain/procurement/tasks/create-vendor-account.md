--- 
title: Crear una cuenta de proveedor
description: "Este procedimiento muestra cómo crear una cuenta de proveedor y agregar una dirección e información de contacto."
author: mkirknel
manager: AnnBe
ms.date: 06/06/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: bis
ms.search.scope: Operations
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: efcb77ff883b29a4bbaba27551e02311742afbbd
ms.openlocfilehash: aaa5b503af95883c2c7fdfb2ad7f3e3062d28961
ms.contentlocale: es-es
ms.lasthandoff: 05/08/2018

---
# <a name="create-a-vendor-account"></a><span data-ttu-id="580a8-103">Crear una cuenta de proveedor</span><span class="sxs-lookup"><span data-stu-id="580a8-103">Create a vendor account</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="580a8-104">Este procedimiento muestra cómo crear una cuenta de proveedor y agregar una dirección e información de contacto.</span><span class="sxs-lookup"><span data-stu-id="580a8-104">This procedure shows how to create a vendor account, and add an address and contact information.</span></span> <span data-ttu-id="580a8-105">El procedimiento no muestra cómo rellenar todos los campos para realizar compras o de uso financiero.</span><span class="sxs-lookup"><span data-stu-id="580a8-105">The procedure does not show how to populate all fields for purchasing and financial purposes.</span></span> <span data-ttu-id="580a8-106">Para obtener más información acerca de estos campos, lea las descripciones de los campos.</span><span class="sxs-lookup"><span data-stu-id="580a8-106">To learn more about those fields, please read the field descriptions.</span></span> <span data-ttu-id="580a8-107">Puede utilizar este procedimiento con los datos de la empresa de demostración USMF o utilizar sus propios datos.</span><span class="sxs-lookup"><span data-stu-id="580a8-107">You can use this procedure in demo data company USMF or on your own data.</span></span> <span data-ttu-id="580a8-108">Las cuentas de proveedor las crean normalmente los profesionales de compras o el personal de cuentas de cliente.</span><span class="sxs-lookup"><span data-stu-id="580a8-108">Vendor accounts are typically created by a procurement professional or accounts receivable personnel.</span></span>


## <a name="create-a-vendor-account"></a><span data-ttu-id="580a8-109">Crear una cuenta de proveedor</span><span class="sxs-lookup"><span data-stu-id="580a8-109">Create a vendor account</span></span>
1. <span data-ttu-id="580a8-110">Vaya a Adquisición y abastecimiento > Proveedores > Todos los proveedores.</span><span class="sxs-lookup"><span data-stu-id="580a8-110">Go to Procurement and sourcing > Vendors > All vendors.</span></span>
2. <span data-ttu-id="580a8-111">Haga clic en Nuevo.</span><span class="sxs-lookup"><span data-stu-id="580a8-111">Click New.</span></span>
3. <span data-ttu-id="580a8-112">En el campo Cuenta de proveedor, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="580a8-112">In the Vendor account field, type a value.</span></span>
    * <span data-ttu-id="580a8-113">El valor se puede completar automáticamente.</span><span class="sxs-lookup"><span data-stu-id="580a8-113">The value may be populated automatically.</span></span> <span data-ttu-id="580a8-114">Si así es, puede omitir este paso.</span><span class="sxs-lookup"><span data-stu-id="580a8-114">If so, you can skip this step.</span></span>  
    * <span data-ttu-id="580a8-115">Puede crear cuentas de proveedor para una persona o una organización.</span><span class="sxs-lookup"><span data-stu-id="580a8-115">You can create vendor accounts for a person or organization.</span></span> <span data-ttu-id="580a8-116">Esto afectará a qué campos quedan disponibles.</span><span class="sxs-lookup"><span data-stu-id="580a8-116">This will affect which fields are available.</span></span> <span data-ttu-id="580a8-117">En este ejemplo, crearemos una cuenta de proveedor para una organización.</span><span class="sxs-lookup"><span data-stu-id="580a8-117">In this example, we’ll create a vendor account for an organization.</span></span>   
4. <span data-ttu-id="580a8-118">En el campo Nombre, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="580a8-118">In the Name field, enter or select a value.</span></span>
    * <span data-ttu-id="580a8-119">Si el proveedor está ya registrado en el sistema, podrá usar la lista desplegable y seleccionarlo en este campo; la nueva cuenta de proveedor heredará la dirección y la información de contacto ya registrada.</span><span class="sxs-lookup"><span data-stu-id="580a8-119">If your vendor is an already a registered party in your system you can use drop down and select them in this field and the new vendor account will inherit the address and contact information that’s already registered.</span></span>  
5. <span data-ttu-id="580a8-120">En el campo Grupo, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="580a8-120">In the Group field, enter or select a value.</span></span>
    * <span data-ttu-id="580a8-121">El grupo de proveedores se utiliza para agrupar proveedores con alguno de los siguientes parámetros en común: condiciones de pago, período de liquidación, cuentas contables de registro de inventarios, incluido el grupo de impuestos, cuentas contables predeterminadas, códigos de filtro de producto o configuración de previsión de suministro.</span><span class="sxs-lookup"><span data-stu-id="580a8-121">The vendor group is used to group vendors that have any of the following parameters in common: Terms of payment , settle period,  inventory posting ledger accounts – including the sales tax group, default ledger accounts, product filter codes, or supply forecast configuration.</span></span>  
6. <span data-ttu-id="580a8-122">En el campo Número de empleados, especifique un número.</span><span class="sxs-lookup"><span data-stu-id="580a8-122">In the Number of employees field, enter a number.</span></span>
7. <span data-ttu-id="580a8-123">En el campo Número de organización, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="580a8-123">In the Organization number field, type a value.</span></span>

## <a name="add-an-address"></a><span data-ttu-id="580a8-124">Adición de una dirección</span><span class="sxs-lookup"><span data-stu-id="580a8-124">Add an address</span></span>
1. <span data-ttu-id="580a8-125">Expanda la sección Direcciones.</span><span class="sxs-lookup"><span data-stu-id="580a8-125">Expand the Addresses section.</span></span>
2. <span data-ttu-id="580a8-126">Haga clic en Agregar.</span><span class="sxs-lookup"><span data-stu-id="580a8-126">Click Add.</span></span>
3. <span data-ttu-id="580a8-127">En el campo Propósito, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="580a8-127">In the Purpose field, enter or select a value.</span></span>
    * <span data-ttu-id="580a8-128">Puede seleccionar uno o más propósitos.</span><span class="sxs-lookup"><span data-stu-id="580a8-128">You can select one or more purposes.</span></span> <span data-ttu-id="580a8-129">Estos se usan para seleccionar la dirección correcta para un propósito dado.</span><span class="sxs-lookup"><span data-stu-id="580a8-129">These are used to select the correct address for a given purpose.</span></span> <span data-ttu-id="580a8-130">Por ejemplo, si el propósito es “Factura”, dicha dirección se usará al enviar facturas.</span><span class="sxs-lookup"><span data-stu-id="580a8-130">For example, if the purpose is “Invoice” that address will be used when you send invoices.</span></span>  
4. <span data-ttu-id="580a8-131">En el campo Nombre o descripción, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="580a8-131">In the Name or description field, type a value.</span></span>
5. <span data-ttu-id="580a8-132">En el campo País o región, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="580a8-132">In the Country/region field, enter or select a value.</span></span>
    * <span data-ttu-id="580a8-133">Especifique los detalles de la dirección.</span><span class="sxs-lookup"><span data-stu-id="580a8-133">Enter the address details.</span></span> <span data-ttu-id="580a8-134">El país o región que haya seleccionado determinará los campos visibles, según el formato de dirección del país o la región.</span><span class="sxs-lookup"><span data-stu-id="580a8-134">The country/region that you selected will determine the fields you are presented with, corresponding to the address format for the country/region.</span></span>   
6. <span data-ttu-id="580a8-135">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="580a8-135">Click OK.</span></span>

## <a name="add-contact-information"></a><span data-ttu-id="580a8-136">Adición de información de contacto</span><span class="sxs-lookup"><span data-stu-id="580a8-136">Add contact information</span></span>
1. <span data-ttu-id="580a8-137">Haga clic en Agregar.</span><span class="sxs-lookup"><span data-stu-id="580a8-137">Click Add.</span></span>
2. <span data-ttu-id="580a8-138">En el campo Descripción, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="580a8-138">In the Description field, type a value.</span></span>
3. <span data-ttu-id="580a8-139">En el campo Tipo, seleccione una opción.</span><span class="sxs-lookup"><span data-stu-id="580a8-139">In the Type field, select an option.</span></span>
4. <span data-ttu-id="580a8-140">En el campo Dirección y número de contacto, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="580a8-140">In the Contact number/address field, type a value.</span></span>
    * <span data-ttu-id="580a8-141">Puede activar la casilla Principal si se trata del contacto principal.</span><span class="sxs-lookup"><span data-stu-id="580a8-141">You can select the Primary check box if this is the primary contact.</span></span>  
5. <span data-ttu-id="580a8-142">Haga clic en Guardar.</span><span class="sxs-lookup"><span data-stu-id="580a8-142">Click Save.</span></span>
6. <span data-ttu-id="580a8-143">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="580a8-143">Close the page.</span></span>
7. <span data-ttu-id="580a8-144">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="580a8-144">Close the page.</span></span>


