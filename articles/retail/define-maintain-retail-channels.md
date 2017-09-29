---
title: Definir y mantener canales comerciales
description: "Este artículo proporciona una visión general del proceso para configurar tiendas físicas, que se conocen como tiendas minoristas en Microsoft Dynamics 365 for Retail. Incluye información acerca de las tareas que debe completar tanto antes como después de configurar una tienda minorista."
author: mugunthanm
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-365-retail
ms.technology: 
ms.search.form: RetailStoreTable, RetailStoreTableListPagePreviewPane
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations, Retail
ms.custom: 16481
ms.assetid: 14496d96-1c72-43ce-a2e7-8467bab4ae46
ms.search.region: Global
ms.search.industry: Retail
ms.author: mumani
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.translationtype: Human Translation
ms.sourcegitcommit: 97d374230cc6e833b9f585de000e1252f2a78b9d
ms.openlocfilehash: 700b8868a68be7f0172202d737b4f1ae9813ecf3
ms.contentlocale: es-es
ms.lasthandoff: 08/30/2017

---

# <a name="define-and-maintain-retail-channels"></a><span data-ttu-id="5677b-104">Definir y mantener canales comerciales</span><span class="sxs-lookup"><span data-stu-id="5677b-104">Define and maintain retail channels</span></span>

[!include[banner](includes/banner.md)]


<span data-ttu-id="5677b-105">Este artículo proporciona una visión general del proceso para configurar tiendas físicas, que se conocen como tiendas minoristas en Microsoft Dynamics 365 for Retail.</span><span class="sxs-lookup"><span data-stu-id="5677b-105">This article provides an overview of the process for setting up brick-and-mortar stores, which are referred to as retail stores in Microsoft Dynamics 365 for Retail.</span></span> <span data-ttu-id="5677b-106">Incluye información acerca de las tareas que debe completar tanto antes como después de configurar una tienda minorista.</span><span class="sxs-lookup"><span data-stu-id="5677b-106">It includes information about the tasks that you must complete both before and after you set up a retail store.</span></span>

<span data-ttu-id="5677b-107">Dynamics 365 for Retail admite varios canales de venta, como tiendas en línea, centros de llamadas y almacenes físicos.</span><span class="sxs-lookup"><span data-stu-id="5677b-107">Dynamics 365 for Retail supports multiple retail channels, such as online stores, call centers, and brick-and-mortar stores.</span></span> <span data-ttu-id="5677b-108">Las tiendas físicas también se denominan tiendas minoristas.</span><span class="sxs-lookup"><span data-stu-id="5677b-108">A brick-and-mortar store is called a retail store.</span></span> <span data-ttu-id="5677b-109">Cada tienda minorista puede tener sus propios métodos de pago, grupos de precios, puntos de venta (PDV), cuentas de ingresos y gastos o personal.</span><span class="sxs-lookup"><span data-stu-id="5677b-109">Each retail store can have its own payment methods, price groups, point of sale (POS) registers, income accounts and expense accounts, and staff.</span></span> <span data-ttu-id="5677b-110">Debe configurar todos estos elementos para una tienda antes de crearla.</span><span class="sxs-lookup"><span data-stu-id="5677b-110">You must set up all these elements for a retail store before you create it.</span></span> <span data-ttu-id="5677b-111">Después de crear la tienda, se asignan los productos que desea que tenga.</span><span class="sxs-lookup"><span data-stu-id="5677b-111">After you create the retail store, you assign the products that you want it to carry.</span></span> <span data-ttu-id="5677b-112">También asigna empleados, cajas registradoras y clientes a la tienda.</span><span class="sxs-lookup"><span data-stu-id="5677b-112">You also assign employees, registers, and customers to the store.</span></span> <span data-ttu-id="5677b-113">Por último, la nueva tienda se agrega a una jerarquía organizativa.</span><span class="sxs-lookup"><span data-stu-id="5677b-113">Finally, you add the new store to an organization hierarchy.</span></span>

## <a name="setting-up-retail-stores"></a><span data-ttu-id="5677b-114">Configurar tiendas</span><span class="sxs-lookup"><span data-stu-id="5677b-114">Setting up retail stores</span></span>
<span data-ttu-id="5677b-115">Antes de poder configurar una tienda minorista en Dynamics 365 for Retail, debe completar algunas de las tareas de requisitos previos.</span><span class="sxs-lookup"><span data-stu-id="5677b-115">Before you can set up a retail store in Dynamics 365 for Retail, you must complete some prerequisite tasks.</span></span> <span data-ttu-id="5677b-116">A continuación, puede crear la tienda y agregar detalles.</span><span class="sxs-lookup"><span data-stu-id="5677b-116">You can then create the retail store and add details.</span></span>

### <a name="prerequisites"></a><span data-ttu-id="5677b-117">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="5677b-117">Prerequisites</span></span>

<span data-ttu-id="5677b-118">Para poder configurar una tienda, debe completar las siguientes tareas:</span><span class="sxs-lookup"><span data-stu-id="5677b-118">You must complete the following tasks before you can set up a retail store:</span></span>

1.  <span data-ttu-id="5677b-119">Configure la estructura de la organización y las jerarquías organizativas para las selecciones comerciales, el reabastecimiento y los informes.</span><span class="sxs-lookup"><span data-stu-id="5677b-119">Configure your organization structure, and set up organization hierarchies for retail assortments, replenishment, and reporting.</span></span>
2.  <span data-ttu-id="5677b-120">Configure un almacén que represente la tienda.</span><span class="sxs-lookup"><span data-stu-id="5677b-120">Set up a warehouse that represents the retail store.</span></span>
3.  <span data-ttu-id="5677b-121">Configure las secuencias numéricas para las tiendas minoristas, los extractos de tienda y los comprobantes del extracto.</span><span class="sxs-lookup"><span data-stu-id="5677b-121">Set up number sequences for retail stores, store statements, and statement vouchers.</span></span>
4.  <span data-ttu-id="5677b-122">Configure parámetros para Venta minorista.</span><span class="sxs-lookup"><span data-stu-id="5677b-122">Configure parameters for Retail.</span></span>
5.  <span data-ttu-id="5677b-123">Configure los métodos de pago que acepta la tienda.</span><span class="sxs-lookup"><span data-stu-id="5677b-123">Set up the methods of payment that the store accepts.</span></span>
6.  <span data-ttu-id="5677b-124">Para procesar transacciones de tarjeta de crédito en los registros de PDV, también puede configurar servicios de pago.</span><span class="sxs-lookup"><span data-stu-id="5677b-124">To process credit card transactions at retail POS registers, you can also set up payment services.</span></span>
7.  <span data-ttu-id="5677b-125">Configure los grupos de impuestos.</span><span class="sxs-lookup"><span data-stu-id="5677b-125">Set up sales tax groups.</span></span>
8.  <span data-ttu-id="5677b-126">Configure los productos comerciales.</span><span class="sxs-lookup"><span data-stu-id="5677b-126">Set up retail products.</span></span> <span data-ttu-id="5677b-127">Como parte de esta tarea, también configura jerarquías de productos comerciales, variantes del producto y surtidos de producto.</span><span class="sxs-lookup"><span data-stu-id="5677b-127">As part of this task, you also set up retail product hierarchies, product variants, and product assortments.</span></span>
9.  <span data-ttu-id="5677b-128">Configure los grupos de precios de producto.</span><span class="sxs-lookup"><span data-stu-id="5677b-128">Set up product price groups.</span></span>
10. <span data-ttu-id="5677b-129">Configure los precios de producto comercial.</span><span class="sxs-lookup"><span data-stu-id="5677b-129">Set up retail product pricing.</span></span> <span data-ttu-id="5677b-130">Como parte de esta tarea, también configura ajustes de precios, descuentos y períodos de descuento.</span><span class="sxs-lookup"><span data-stu-id="5677b-130">As part of this task, you also set up price adjustments, discounts, and discount periods.</span></span>
11. <span data-ttu-id="5677b-131">Configure los empleados.</span><span class="sxs-lookup"><span data-stu-id="5677b-131">Set up staff members.</span></span> <span data-ttu-id="5677b-132">**Nota:** También debe asignar los permisos adecuados a los trabajadores, de modo que puedan iniciar sesión y realizar tareas con el sistema de Dynamics 365 for Retail POS.</span><span class="sxs-lookup"><span data-stu-id="5677b-132">**Note:** You must also assign appropriate permissions to the workers, so that they can sign in and perform tasks by using the Dynamics 365 for Retail for Retail POS system.</span></span>
12. <span data-ttu-id="5677b-133">Configure los perfiles de Retail POS que se deben asignar a la tienda.</span><span class="sxs-lookup"><span data-stu-id="5677b-133">Configure the Retail POS profiles to assign to the store.</span></span> <span data-ttu-id="5677b-134">Esta tarea incluye muchas otras tareas, por ejemplo, la configuración de los registros, los perfiles sin conexión y los formatos y perfiles de recepción.</span><span class="sxs-lookup"><span data-stu-id="5677b-134">This task includes many other tasks, such as setting up registers, setting up offline profiles, and setting up receipt formats and profiles.</span></span>

<span data-ttu-id="5677b-135">Revise todas las tareas que se incluyen en el requisito previo y complete solo las tareas que se aplican a su caso.</span><span class="sxs-lookup"><span data-stu-id="5677b-135">Review all the tasks that are included in the prerequisite, and complete only the tasks that apply to you.</span></span>

### <a name="set-up-a-retail-store"></a><span data-ttu-id="5677b-136">Configurar una tienda comercial</span><span class="sxs-lookup"><span data-stu-id="5677b-136">Set up a retail store</span></span>

<span data-ttu-id="5677b-137">Tras completar las tareas de requisito previo, complete estas tareas para configurar los detalles de la tienda minorista:</span><span class="sxs-lookup"><span data-stu-id="5677b-137">After you complete the prerequisite tasks, complete these tasks to set up the details for the retail store:</span></span>

1.  <span data-ttu-id="5677b-138">Cree una nueva tienda.</span><span class="sxs-lookup"><span data-stu-id="5677b-138">Create a retail store.</span></span>
2.  <span data-ttu-id="5677b-139">Asigne un grupo de impuestos a la tienda.</span><span class="sxs-lookup"><span data-stu-id="5677b-139">Assign a sales tax group to the store.</span></span>
3.  <span data-ttu-id="5677b-140">Asigne los métodos de pago aceptados a la tienda.</span><span class="sxs-lookup"><span data-stu-id="5677b-140">Assign the accepted payment methods to the store.</span></span>
4.  <span data-ttu-id="5677b-141">Agregue detalles a las descripciones de producto para los productos que ofrece en las tiendas comerciales.</span><span class="sxs-lookup"><span data-stu-id="5677b-141">Add details to the product descriptions for products that you offer in your retail stores.</span></span> <span data-ttu-id="5677b-142">Por ejemplo, puede agregar texto enriquecido e imágenes.</span><span class="sxs-lookup"><span data-stu-id="5677b-142">For example, you can add rich text and images.</span></span> <span data-ttu-id="5677b-143">Estos detalles de producto aparecen en distintos contextos, por ejemplo, en el registro de PDV o en etiquetas impresas.</span><span class="sxs-lookup"><span data-stu-id="5677b-143">These product details appear in various contexts, such as on the POS register or on printed labels.</span></span>
5.  <span data-ttu-id="5677b-144">Agregue la tienda a una jerarquía organizativa predeterminada que está asignada a una finalidad de **Selección comercial**, **Reabastecimiento comercial** o **Informes comerciales**.</span><span class="sxs-lookup"><span data-stu-id="5677b-144">Add the store to an the default organization hierarchy that is assigned to a purpose of **Retail assortment**, **Retail replenishment**, or **Retail reporting**.</span></span>

### <a name="after-you-set-up-a-retail-store"></a><span data-ttu-id="5677b-145">Después de configurar una tienda minorista</span><span class="sxs-lookup"><span data-stu-id="5677b-145">After you set up a retail store</span></span>

<span data-ttu-id="5677b-146">Tras especificar los detalles de la tienda minorista, complete estas tareas para enviar los datos de la nueva tienda minorista a Retail POS:</span><span class="sxs-lookup"><span data-stu-id="5677b-146">After you enter the details for the retail store, complete these tasks to send the new retail store data to Retail POS:</span></span>

1.  <span data-ttu-id="5677b-147">Configure los registros de PDV para la tienda.</span><span class="sxs-lookup"><span data-stu-id="5677b-147">Configure the POS registers for the store.</span></span>
2.  <span data-ttu-id="5677b-148">Asigne los surtidos del producto a la tienda.</span><span class="sxs-lookup"><span data-stu-id="5677b-148">Assign product assortments to the store.</span></span>
3.  <span data-ttu-id="5677b-149">Procese los surtidos para generar la lista de productos incluidos en el surtido y para hacer que los productos estén disponibles en la tienda minorista.</span><span class="sxs-lookup"><span data-stu-id="5677b-149">Process assortments to generate the list of products that are included in the assortment and to make the products available in the retail store.</span></span>
4.  <span data-ttu-id="5677b-150">Envíe datos como, por ejemplo, secuencias numéricas, perfiles de hardware y diseños de pantalla de PDV a los registros de Retail POS.</span><span class="sxs-lookup"><span data-stu-id="5677b-150">Send data such as number sequences, hardware profiles, and POS screen layouts to the Retail POS registers.</span></span>
5.  <span data-ttu-id="5677b-151">Publique la tienda comercial para enviar datos de tienda a Retail POS.</span><span class="sxs-lookup"><span data-stu-id="5677b-151">Publish the retail store to send store data to Retail POS.</span></span>
6.  <span data-ttu-id="5677b-152">Ejecute los trabajos para enviar los datos de tienda a Retail POS.</span><span class="sxs-lookup"><span data-stu-id="5677b-152">Run the jobs to send the store data to Retail POS.</span></span>

## <a name="organization-hierarchies"></a><span data-ttu-id="5677b-153">Jerarquías organizativas</span><span class="sxs-lookup"><span data-stu-id="5677b-153">Organization hierarchies</span></span>
<span data-ttu-id="5677b-154">Retail usa jerarquías organizativas para estructurar los canales comerciales.</span><span class="sxs-lookup"><span data-stu-id="5677b-154">Retail uses organization hierarchies to structure retail channels.</span></span> <span data-ttu-id="5677b-155">Las jerarquías organizativas representan las relaciones que hay entre las organizaciones que forman el negocio.</span><span class="sxs-lookup"><span data-stu-id="5677b-155">Organization hierarchies represent the relationships between the organizations that make up your business.</span></span> <span data-ttu-id="5677b-156">Al configurar tiendas, puede agregarlas a una jerarquía organizativa.</span><span class="sxs-lookup"><span data-stu-id="5677b-156">When you set up stores, you can add them to an organization hierarchy.</span></span> <span data-ttu-id="5677b-157">A continuación, los almacenes comparten los datos que se usan para las selecciones, el reaprovisionamiento y los informes.</span><span class="sxs-lookup"><span data-stu-id="5677b-157">The stores then share data that is used for assortments, replenishment, and reporting.</span></span>




