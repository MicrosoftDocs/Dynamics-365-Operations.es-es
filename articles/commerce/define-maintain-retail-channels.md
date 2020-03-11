---
title: Definir y mantener canales comerciales
description: Este tema proporciona una visión general del proceso para configurar tiendas físicas, que se conocen como tiendas en Dynamics 365 Commerce. Incluye información acerca de las tareas que debe completar tanto antes como después de configurar una tienda.
author: mugunthanm
manager: AnnBe
ms.date: 01/06/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
ms.search.form: RetailStoreTable, RetailStoreTableListPagePreviewPane
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: 16481
ms.assetid: 14496d96-1c72-43ce-a2e7-8467bab4ae46
ms.search.region: Global
ms.search.industry: Retail
ms.author: mumani
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.openlocfilehash: 0fbca2c9178cd372653287afdf72deaf75442604
ms.sourcegitcommit: 12b9d6f2dd24e52e46487748c848864909af6967
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2020
ms.locfileid: "3057923"
---
# <a name="define-and-maintain-retail-channels"></a><span data-ttu-id="1784d-104">Definir y mantener canales comerciales</span><span class="sxs-lookup"><span data-stu-id="1784d-104">Define and maintain retail channels</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="1784d-105">Este tema proporciona una visión general del proceso para configurar tiendas físicas, que se conocen como tiendas en Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="1784d-105">This topic provides an overview of the process for setting up brick-and-mortar stores, which are referred to as stores in Dynamics 365 Commerce.</span></span> <span data-ttu-id="1784d-106">Incluye información acerca de las tareas que debe completar tanto antes como después de configurar una tienda.</span><span class="sxs-lookup"><span data-stu-id="1784d-106">It includes information about the tasks that you must complete both before and after you set up a store.</span></span>

<span data-ttu-id="1784d-107">Commerce admite varios canales, como tiendas en línea, almacenes físicos y centros de llamadas.</span><span class="sxs-lookup"><span data-stu-id="1784d-107">Commerce supports multiple channels, such as online stores, call centers, and brick-and-mortar stores.</span></span> <span data-ttu-id="1784d-108">Las tiendas físicas también se denominan tiendas.</span><span class="sxs-lookup"><span data-stu-id="1784d-108">A brick-and-mortar store is called a store.</span></span> <span data-ttu-id="1784d-109">Cada tienda puede tener sus propios métodos de pago, grupos de precios, puntos de venta (PDV), cuentas de ingresos y gastos o personal.</span><span class="sxs-lookup"><span data-stu-id="1784d-109">Each store can have its own payment methods, price groups, point of sale (POS) registers, income accounts and expense accounts, and staff.</span></span> <span data-ttu-id="1784d-110">Debe configurar todos estos elementos para una tienda antes de crearla.</span><span class="sxs-lookup"><span data-stu-id="1784d-110">You must set up all these elements for a store before you create it.</span></span> <span data-ttu-id="1784d-111">Después de crear la tienda, se asignan los productos que desea que tenga.</span><span class="sxs-lookup"><span data-stu-id="1784d-111">After you create the store, you assign the products that you want it to carry.</span></span> <span data-ttu-id="1784d-112">También asigna empleados, cajas registradoras y clientes a la tienda.</span><span class="sxs-lookup"><span data-stu-id="1784d-112">You also assign employees, registers, and customers to the store.</span></span> <span data-ttu-id="1784d-113">Por último, la nueva tienda se agrega a una jerarquía organizativa.</span><span class="sxs-lookup"><span data-stu-id="1784d-113">Finally, you add the new store to an organization hierarchy.</span></span>

## <a name="setting-up-stores"></a><span data-ttu-id="1784d-114">Configurar tiendas</span><span class="sxs-lookup"><span data-stu-id="1784d-114">Setting up stores</span></span>

<span data-ttu-id="1784d-115">Antes de poder configurar una tienda en Commerce, debe completar algunas de las tareas de requisitos previos.</span><span class="sxs-lookup"><span data-stu-id="1784d-115">Before you can set up a store in Commerce, you must complete some prerequisite tasks.</span></span> <span data-ttu-id="1784d-116">A continuación, puede crear la tienda y agregar detalles.</span><span class="sxs-lookup"><span data-stu-id="1784d-116">You can then create the store and add details.</span></span>

### <a name="prerequisites"></a><span data-ttu-id="1784d-117">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="1784d-117">Prerequisites</span></span>

<span data-ttu-id="1784d-118">Para poder configurar una tienda, debe completar las siguientes tareas:</span><span class="sxs-lookup"><span data-stu-id="1784d-118">You must complete the following tasks before you can set up a store:</span></span>

1. <span data-ttu-id="1784d-119">Configure la estructura de la organización y las jerarquías organizativas para las selecciones comerciales, el reabastecimiento y los informes.</span><span class="sxs-lookup"><span data-stu-id="1784d-119">Configure your organization structure, and set up organization hierarchies for retail assortments, replenishment, and reporting.</span></span>
2. <span data-ttu-id="1784d-120">Configure un almacén que represente la tienda.</span><span class="sxs-lookup"><span data-stu-id="1784d-120">Set up a warehouse that represents the store.</span></span>
3. <span data-ttu-id="1784d-121">Configure las secuencias numéricas para las tiendas, los extractos de tienda y los comprobantes del extracto.</span><span class="sxs-lookup"><span data-stu-id="1784d-121">Set up number sequences for stores, store statements, and statement vouchers.</span></span>
4. <span data-ttu-id="1784d-122">Configurar parámetros para Commerce.</span><span class="sxs-lookup"><span data-stu-id="1784d-122">Configure parameters for Commerce.</span></span>
5. <span data-ttu-id="1784d-123">Configure los métodos de pago que acepta la tienda.</span><span class="sxs-lookup"><span data-stu-id="1784d-123">Set up the methods of payment that the store accepts.</span></span>
6. <span data-ttu-id="1784d-124">Para procesar transacciones de tarjeta de crédito en los registros de PDV, también puede configurar servicios de pago.</span><span class="sxs-lookup"><span data-stu-id="1784d-124">To process credit card transactions at POS registers, you can also set up payment services.</span></span>
7. <span data-ttu-id="1784d-125">Configure los grupos de impuestos.</span><span class="sxs-lookup"><span data-stu-id="1784d-125">Set up sales tax groups.</span></span>
8. <span data-ttu-id="1784d-126">Configurar productos.</span><span class="sxs-lookup"><span data-stu-id="1784d-126">Set up products.</span></span> <span data-ttu-id="1784d-127">Como parte de esta tarea, también configura jerarquías de productos, variantes del producto y surtidos de producto.</span><span class="sxs-lookup"><span data-stu-id="1784d-127">As part of this task, you also set up product hierarchies, product variants, and product assortments.</span></span>
9. <span data-ttu-id="1784d-128">Configure los grupos de precios de producto.</span><span class="sxs-lookup"><span data-stu-id="1784d-128">Set up product price groups.</span></span>
10. <span data-ttu-id="1784d-129">Configure el precio del producto.</span><span class="sxs-lookup"><span data-stu-id="1784d-129">Set up product pricing.</span></span> <span data-ttu-id="1784d-130">Como parte de esta tarea, también configura ajustes de precios, descuentos y períodos de descuento.</span><span class="sxs-lookup"><span data-stu-id="1784d-130">As part of this task, you also set up price adjustments, discounts, and discount periods.</span></span>
11. <span data-ttu-id="1784d-131">Configure los empleados.</span><span class="sxs-lookup"><span data-stu-id="1784d-131">Set up staff members.</span></span>

    > [!NOTE]
    > <span data-ttu-id="1784d-132">También debe asignar los permisos adecuados a los trabajadores, de modo que puedan iniciar sesión y realizar tareas con el sistema PDV.</span><span class="sxs-lookup"><span data-stu-id="1784d-132">You must also assign appropriate permissions to the workers, so that they can sign in and perform tasks by using the POS system.</span></span>

12. <span data-ttu-id="1784d-133">Configure los perfiles de PDV que se deben asignar a la tienda.</span><span class="sxs-lookup"><span data-stu-id="1784d-133">Configure the POS profiles to assign to the store.</span></span> <span data-ttu-id="1784d-134">Esta tarea incluye muchas otras tareas, por ejemplo, la configuración de los registros, los perfiles sin conexión y los formatos y perfiles de recepción.</span><span class="sxs-lookup"><span data-stu-id="1784d-134">This task includes many other tasks, such as setting up registers, setting up offline profiles, and setting up receipt formats and profiles.</span></span>

<span data-ttu-id="1784d-135">Revise todas las tareas que se incluyen en los requisitos previos y complete solo las tareas que se aplican a su caso.</span><span class="sxs-lookup"><span data-stu-id="1784d-135">Review all the tasks that are included in the prerequisites, and complete only the tasks that apply to you.</span></span>

### <a name="set-up-a-store"></a><span data-ttu-id="1784d-136">Configurar una tienda</span><span class="sxs-lookup"><span data-stu-id="1784d-136">Set up a store</span></span>

<span data-ttu-id="1784d-137">Tras completar las tareas de requisito previo, complete estas tareas para configurar los detalles de la tienda:</span><span class="sxs-lookup"><span data-stu-id="1784d-137">After you complete the prerequisite tasks, complete these tasks to set up the details for the store:</span></span>

1. <span data-ttu-id="1784d-138">Cree una tienda.</span><span class="sxs-lookup"><span data-stu-id="1784d-138">Create a store.</span></span>
2. <span data-ttu-id="1784d-139">Asigne un grupo de impuestos a la tienda.</span><span class="sxs-lookup"><span data-stu-id="1784d-139">Assign a sales tax group to the store.</span></span>
3. <span data-ttu-id="1784d-140">Asigne los métodos de pago aceptados a la tienda.</span><span class="sxs-lookup"><span data-stu-id="1784d-140">Assign the accepted payment methods to the store.</span></span>
4. <span data-ttu-id="1784d-141">Agregue detalles a las descripciones de producto para los productos que ofrece en las tiendas.</span><span class="sxs-lookup"><span data-stu-id="1784d-141">Add details to the product descriptions for products that you offer in your stores.</span></span> <span data-ttu-id="1784d-142">Por ejemplo, puede agregar texto enriquecido e imágenes.</span><span class="sxs-lookup"><span data-stu-id="1784d-142">For example, you can add rich text and images.</span></span> <span data-ttu-id="1784d-143">Estos detalles de producto aparecen en distintos contextos, por ejemplo, en el registro de PDV o en etiquetas impresas.</span><span class="sxs-lookup"><span data-stu-id="1784d-143">These product details appear in various contexts, such as on the POS register or on printed labels.</span></span>
5. <span data-ttu-id="1784d-144">Agregue la tienda a la jerarquía organizativa predeterminada que está asignada a una finalidad de **Selección comercial**, **Reabastecimiento comercial** o **Informes comerciales**.</span><span class="sxs-lookup"><span data-stu-id="1784d-144">Add the store to the default organization hierarchy that is assigned to a purpose of **Retail assortment**, **Retail replenishment**, or **Retail reporting**.</span></span>

### <a name="after-you-set-up-a-store"></a><span data-ttu-id="1784d-145">Después de configurar una tienda</span><span class="sxs-lookup"><span data-stu-id="1784d-145">After you set up a store</span></span>

<span data-ttu-id="1784d-146">Tras especificar los detalles de la tienda, complete estas tareas para enviar los datos de la nueva tienda minorista a PDV.</span><span class="sxs-lookup"><span data-stu-id="1784d-146">After you enter the details for the store, complete these tasks to send the new store data to POS:</span></span>

1. <span data-ttu-id="1784d-147">Configure los registros de PDV para la tienda.</span><span class="sxs-lookup"><span data-stu-id="1784d-147">Configure the POS registers for the store.</span></span>
2. <span data-ttu-id="1784d-148">Asigne los surtidos del producto a la tienda.</span><span class="sxs-lookup"><span data-stu-id="1784d-148">Assign product assortments to the store.</span></span>
3. <span data-ttu-id="1784d-149">Procese los surtidos para generar la lista de productos incluidos en el surtido y para hacer que los productos estén disponibles en la tienda.</span><span class="sxs-lookup"><span data-stu-id="1784d-149">Process assortments to generate the list of products that are included in the assortment and to make the products available in the store.</span></span>
4. <span data-ttu-id="1784d-150">Envíe datos como, por ejemplo, secuencias numéricas, perfiles de hardware y diseños de pantalla de PDV a los registros de PDV.</span><span class="sxs-lookup"><span data-stu-id="1784d-150">Send data such as number sequences, hardware profiles, and POS screen layouts to the POS registers.</span></span>
5. <span data-ttu-id="1784d-151">Publique la tienda para enviar datos de tienda a PDV.</span><span class="sxs-lookup"><span data-stu-id="1784d-151">Publish the store to send store data to POS.</span></span>
6. <span data-ttu-id="1784d-152">Ejecute los trabajos para enviar los datos de tienda a PDV.</span><span class="sxs-lookup"><span data-stu-id="1784d-152">Run the jobs to send the store data to POS.</span></span>

## <a name="organization-hierarchies"></a><span data-ttu-id="1784d-153">Jerarquías organizativas</span><span class="sxs-lookup"><span data-stu-id="1784d-153">Organization hierarchies</span></span>

<span data-ttu-id="1784d-154">Commerce usa jerarquías organizativas para estructurar los canales.</span><span class="sxs-lookup"><span data-stu-id="1784d-154">Commerce uses organization hierarchies to structure channels.</span></span> <span data-ttu-id="1784d-155">Las jerarquías organizativas representan las relaciones que hay entre las organizaciones que forman el negocio.</span><span class="sxs-lookup"><span data-stu-id="1784d-155">Organization hierarchies represent the relationships between the organizations that make up your business.</span></span> <span data-ttu-id="1784d-156">Al configurar tiendas, puede agregarlas a una jerarquía organizativa.</span><span class="sxs-lookup"><span data-stu-id="1784d-156">When you set up stores, you can add them to an organization hierarchy.</span></span> <span data-ttu-id="1784d-157">A continuación, los almacenes comparten los datos que se usan para las selecciones, el reaprovisionamiento y los informes.</span><span class="sxs-lookup"><span data-stu-id="1784d-157">The stores then share data that is used for assortments, replenishment, and reporting.</span></span>

> [!NOTE]
> <span data-ttu-id="1784d-158">Para usar la funcionalidad de ventas de Commerce, la clave de configuración **Envíos múltiples** debe estar habilitada.</span><span class="sxs-lookup"><span data-stu-id="1784d-158">To use Commerce sales functionality, the configuration key for **Multiple ship-to** must be enabled.</span></span> <span data-ttu-id="1784d-159">Esta clave de configuración se puede encontrar en las claves **Configuración de comercio** en **Administración del sistema**\> **Configuración** \> **Configuración de licencia**.</span><span class="sxs-lookup"><span data-stu-id="1784d-159">This configuration key can be found in the **Trade configuration** keys under **System Administration**\> **Setup** \> **License Configuration**.</span></span> <span data-ttu-id="1784d-160">Esto es necesario debido a que realiza diversas validaciones en función de la dirección de entrega configurada en el nivel de línea del pedido de ventas.</span><span class="sxs-lookup"><span data-stu-id="1784d-160">This is required due to various validations based on the delivery address configured at the sales order line level.</span></span>

