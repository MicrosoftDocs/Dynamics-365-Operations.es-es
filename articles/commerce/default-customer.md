---
title: Crear un cliente predeterminado
description: Este tema describe cómo crear un cliente predeterminado para usar al crear un canal en Microsoft Dynamics 365 Commerce.
author: samjarawan
manager: annbe
ms.date: 01/27/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: samjar
ms.search.validFrom: 2020-01-20
ms.dyn365.ops.version: Release 10.0.8
ms.openlocfilehash: 1dd4dfc5b8ca7af66941d081b4c20be0f5d6001d
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/15/2021
ms.locfileid: "4993409"
---
# <a name="create-a-default-customer"></a><span data-ttu-id="ada78-103">Crear un cliente predeterminado</span><span class="sxs-lookup"><span data-stu-id="ada78-103">Create a default customer</span></span>


[!include [banner](includes/banner.md)]

<span data-ttu-id="ada78-104">Este tema describe cómo crear un cliente predeterminado para usar al crear un canal en Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="ada78-104">This topic describes how to create a default customer to use when creating a channel in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="ada78-105">Visión general</span><span class="sxs-lookup"><span data-stu-id="ada78-105">Overview</span></span>

<span data-ttu-id="ada78-106">Al crear un canal, deberá proporcionar un cliente predeterminado.</span><span class="sxs-lookup"><span data-stu-id="ada78-106">When creating a channel, you will need to provide a default customer.</span></span> <span data-ttu-id="ada78-107">Se puede crear fácilmente un cliente predeterminado después de crear primero el grupo de clientes y la libreta de direcciones de clientes.</span><span class="sxs-lookup"><span data-stu-id="ada78-107">A default customer can easily be created after first creating the customer group and customer address book.</span></span>

## <a name="create-a-customer-group"></a><span data-ttu-id="ada78-108">Creación de un grupo de clientes</span><span class="sxs-lookup"><span data-stu-id="ada78-108">Create a customer group</span></span>

<span data-ttu-id="ada78-109">Si todavía no existen grupos de clientes, puede crear uno.</span><span class="sxs-lookup"><span data-stu-id="ada78-109">If no customer groups exist yet, you can create one.</span></span> <span data-ttu-id="ada78-110">Ejemplos pueden ser grupos para representar diferentes grupos de clientes, como mayoristas, minoristas, Internet, empleados, etc.</span><span class="sxs-lookup"><span data-stu-id="ada78-110">Examples may be groups to represent different customer groups, such as wholesale, retail, Internet, Employees, etc.</span></span>

<span data-ttu-id="ada78-111">Para crear un grupo de clientes, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="ada78-111">To create a customer group, follow these steps.</span></span>

1. <span data-ttu-id="ada78-112">En el panel de navegación, vaya a **Módulos \> Comercio minorista y comercio \> Clientes \> Grupos de clientes**.</span><span class="sxs-lookup"><span data-stu-id="ada78-112">In the navigation pane, go to **Modules \> Retail and commerce \> Customers \> Customer groups**.</span></span>
1. <span data-ttu-id="ada78-113">En el panel de acciones, seleccione **Nueva**.</span><span class="sxs-lookup"><span data-stu-id="ada78-113">On the action pane, select **New**.</span></span>
1. <span data-ttu-id="ada78-114">En el cuadro **Grupo de clientes**, especifique un id. de grupo de clientes.</span><span class="sxs-lookup"><span data-stu-id="ada78-114">In the **Customer group** box, enter a customer group ID.</span></span>
1. <span data-ttu-id="ada78-115">Especifique una descripción adecuada en el cuadro **Descripción**.</span><span class="sxs-lookup"><span data-stu-id="ada78-115">In the **Description** box, enter an appropriate description.</span></span>
1. <span data-ttu-id="ada78-116">Especifique un valor adecuado en el cuadro **Condiciones de pago**.</span><span class="sxs-lookup"><span data-stu-id="ada78-116">In the **Terms of payment** box, enter an appropriate value.</span></span>
1. <span data-ttu-id="ada78-117">En el cuadro **Tiempo entre la fecha de vencimiento de la factura y la fecha de pago**, ingrese un valor apropiado.</span><span class="sxs-lookup"><span data-stu-id="ada78-117">In the **Time between invoice due date and payment date** box, enter an appropriate value.</span></span>
1. <span data-ttu-id="ada78-118">En el cuadro **Grupo de impuestos predeterminado**, ingrese un grupo de impuestos si corresponde.</span><span class="sxs-lookup"><span data-stu-id="ada78-118">In the **Default tax group** box, enter a tax group if applicable.</span></span>
1. <span data-ttu-id="ada78-119">Seleccione la casilla **Los precios incluyen impuestos** si es aplicable.</span><span class="sxs-lookup"><span data-stu-id="ada78-119">Select the **Prices include sales tax** check box if applicable.</span></span>
1. <span data-ttu-id="ada78-120">En el cuadro **Motivo de cancelación predeterminado**, especifique un valor apropiado, según corresponda.</span><span class="sxs-lookup"><span data-stu-id="ada78-120">In the **Default write-off reason** box, enter an appropriate value, if applicable.</span></span>

<span data-ttu-id="ada78-121">La siguiente imagen muestra varios grupos de clientes configurados.</span><span class="sxs-lookup"><span data-stu-id="ada78-121">The following image shows several configured customer groups.</span></span>

![Grupos de clientes](media/customer-groups.png)

## <a name="create-a-customer-address-book"></a><span data-ttu-id="ada78-123">Crear una nueva libreta de direcciones de clientes.</span><span class="sxs-lookup"><span data-stu-id="ada78-123">Create a customer address book</span></span>

<span data-ttu-id="ada78-124">Un cliente debe estar asociado con una libreta de direcciones.</span><span class="sxs-lookup"><span data-stu-id="ada78-124">A customer needs to be associated with an address book.</span></span> <span data-ttu-id="ada78-125">Si aún no ha creado una, deberá hacerlo.</span><span class="sxs-lookup"><span data-stu-id="ada78-125">If one has not yet been created, then you will need to create one.</span></span>

<span data-ttu-id="ada78-126">Para crear una libreta de direcciones de clientes, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="ada78-126">To create a customer address book, follow these steps.</span></span>

1. <span data-ttu-id="ada78-127">En el panel de navegación, vaya a **Módulos \> Retail y Commerce \> Configuración de canales \> Libretas de direcciones**.</span><span class="sxs-lookup"><span data-stu-id="ada78-127">In the navigation pane, go to **Modules \> Retail and commerce \> Channel setup \> Address Books**.</span></span>
1. <span data-ttu-id="ada78-128">En el panel de acciones, seleccione **Nueva**.</span><span class="sxs-lookup"><span data-stu-id="ada78-128">On the action pane, select **New**.</span></span>
1. <span data-ttu-id="ada78-129">Escriba un nombre en el cuadro **Nombre**.</span><span class="sxs-lookup"><span data-stu-id="ada78-129">In the **Name** box, enter a name.</span></span>
1. <span data-ttu-id="ada78-130">En el cuadro **Descripción**, escriba una descripción.</span><span class="sxs-lookup"><span data-stu-id="ada78-130">In the **Description** box, enter a description.</span></span>
1. <span data-ttu-id="ada78-131">En el panel de acciones, seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="ada78-131">On the action pane, select **Save**.</span></span>

<span data-ttu-id="ada78-132">En la imagen siguiente se muestra un ejemplo de libreta de direcciones.</span><span class="sxs-lookup"><span data-stu-id="ada78-132">The following image shows an example address book.</span></span>

![Libreta de direcciones](media/address-book.png)

## <a name="create-a-default-customer"></a><span data-ttu-id="ada78-134">Crear un cliente predeterminado</span><span class="sxs-lookup"><span data-stu-id="ada78-134">Create a default customer</span></span>

<span data-ttu-id="ada78-135">Para crear un cliente predeterminado, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="ada78-135">To create a default customer, follow these steps.</span></span>

1. <span data-ttu-id="ada78-136">En el panel de navegación, vaya a **Módulos \> Venta minorista y comercio \> Clientes \> Todos los clientes**.</span><span class="sxs-lookup"><span data-stu-id="ada78-136">In the navigation pane, go to **Modules \> Retail and commerce \> Customers \> All customers**.</span></span>
1. <span data-ttu-id="ada78-137">En el panel de acciones, seleccione **Nueva**.</span><span class="sxs-lookup"><span data-stu-id="ada78-137">On the action pane, select **New**.</span></span>
1. <span data-ttu-id="ada78-138">En la lista desplegable **Tipo**, seleccione "Persona".</span><span class="sxs-lookup"><span data-stu-id="ada78-138">In the **Type** drop-down list, select "Person".</span></span>
1. <span data-ttu-id="ada78-139">En la lista desplegable **Cuenta de cliente**, seleccione o ingrese un número de cuenta (por ejemplo, "100001").</span><span class="sxs-lookup"><span data-stu-id="ada78-139">In the **Customer account** drop-down list, select or enter an account number (for example, "100001").</span></span>
1. <span data-ttu-id="ada78-140">En la lista desplegable **Nombre de pila**, seleccione o escriba un nombre (por ejemplo, "Predeterminado").</span><span class="sxs-lookup"><span data-stu-id="ada78-140">In the **First name** drop-down list, select or enter a name (for example, "Default").</span></span>
1. <span data-ttu-id="ada78-141">En la lista desplegable **Segundo nombre**, seleccione o escriba un nombre (por ejemplo, "Venta minorista").</span><span class="sxs-lookup"><span data-stu-id="ada78-141">In the **Middle name** drop-down list, select or enter a name (for example, "Retail").</span></span>
1. <span data-ttu-id="ada78-142">En la lista desplegable **Apellido**, seleccione o escriba un nombre (por ejemplo, "Cliente").</span><span class="sxs-lookup"><span data-stu-id="ada78-142">In the **Last name** drop-down list, select or enter a name (for example, "Customer").</span></span>
1. <span data-ttu-id="ada78-143">En la lista desplegable **Divisa**, seleccione o escriba una divisa (por ejemplo, "USD").</span><span class="sxs-lookup"><span data-stu-id="ada78-143">In the **Currency** drop-down list, select or enter a currency (for example, "USD").</span></span>
1. <span data-ttu-id="ada78-144">En la lista desplegable **Divisa**, seleccione el grupo de clientes creado anteriormente.</span><span class="sxs-lookup"><span data-stu-id="ada78-144">In the **Currency** drop-down list, select the customer group created previously.</span></span>
1. <span data-ttu-id="ada78-145">En la lista desplegable **Libretas de direcciones**, seleccione una libreta de direcciones de clientes existente.</span><span class="sxs-lookup"><span data-stu-id="ada78-145">In the **Address books**  drop-down list, select an existing customer address book.</span></span>
1. <span data-ttu-id="ada78-146">Seleccione **Guardar** para guardar y volver a la pantalla de detalles del cliente para el nuevo cliente.</span><span class="sxs-lookup"><span data-stu-id="ada78-146">Select **Save** to save and return to customer details screen for the new customer.</span></span>

> [!NOTE]
> <span data-ttu-id="ada78-147">No es necesario agregar una dirección para un cliente predeterminado.</span><span class="sxs-lookup"><span data-stu-id="ada78-147">It is not necessary to add an address for a default customer.</span></span>

<span data-ttu-id="ada78-148">En la imagen siguiente se muestra un ejemplo de creación de cliente.</span><span class="sxs-lookup"><span data-stu-id="ada78-148">The following image shows an example of customer creation.</span></span>

![Creación de un cliente predeterminado](media/default-customer-creation.png)

<span data-ttu-id="ada78-150">La siguiente imagen muestra una configuración predeterminada del cliente.</span><span class="sxs-lookup"><span data-stu-id="ada78-150">The following image shows a default customer configuration.</span></span>

![Ejemplo de configuración de cliente](media/default-customer-configuration1.png)

<span data-ttu-id="ada78-152">La mayoría de los valores predeterminados en la pantalla de desviaciones del cliente pueden permanecer, pero se deben cambiar dos valores.</span><span class="sxs-lookup"><span data-stu-id="ada78-152">Most of the default values on the customer detials screen can remain, but two values should be changed.</span></span>

1. <span data-ttu-id="ada78-153">En la pantalla de detalles del cliente, expanda **Valores predeterminados de pedido de ventas**.</span><span class="sxs-lookup"><span data-stu-id="ada78-153">On the customer details screen, expand **Sales order defaults**.</span></span>
1. <span data-ttu-id="ada78-154">En la lista desplegable **Sitio**, seleccione o ingrese un sitio preconfigurado.</span><span class="sxs-lookup"><span data-stu-id="ada78-154">In the **Site** drop-down list, select or enter a pre-configured site.</span></span>
1. <span data-ttu-id="ada78-155">En la lista desplegable **Almacén**, seleccione o ingrese un almacén preconfigurado.</span><span class="sxs-lookup"><span data-stu-id="ada78-155">In the **Warehouse** drop-down list, and select or enter a pre-configured warehouse.</span></span>

<span data-ttu-id="ada78-156">En la imagen siguiente se muestra un ejemplo de configuración de cliente.</span><span class="sxs-lookup"><span data-stu-id="ada78-156">The following image shows an example customer configuration.</span></span>

![Ejemplo de configuración de cliente](media/default-customer-configuration2.png)

## <a name="additional-resources"></a><span data-ttu-id="ada78-158">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="ada78-158">Additional resources</span></span>

[<span data-ttu-id="ada78-159">Resumen de canales</span><span class="sxs-lookup"><span data-stu-id="ada78-159">Channels overview</span></span>](channels-overview.md)

[<span data-ttu-id="ada78-160">Requisitos previos de configuración de canales</span><span class="sxs-lookup"><span data-stu-id="ada78-160">Channel setup prerequisites</span></span>](channels-prerequisites.md)
