---
title: Maestro de clientes integrado
description: En este tema se describe la integración de datos de cliente entre Finance and Operations y Common Data Service.
author: RamaKrishnamoorthy
manager: AnnBe
ms.date: 07/15/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User, IT Pro
ms.reviewer: rhaertle
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: ramasri
ms.dyn365.ops.version: ''
ms.search.validFrom: 2019-07-15
ms.openlocfilehash: 269346d38eeb3812c352d16f9d50fbcd09307c12
ms.sourcegitcommit: 1d5a4f70a931e78b06811add97c1962e8d93689b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/13/2020
ms.locfileid: "3124598"
---
# <a name="integrated-customer-master"></a><span data-ttu-id="550ae-103">Maestro de clientes integrado</span><span class="sxs-lookup"><span data-stu-id="550ae-103">Integrated customer master</span></span>

[!include [banner](../../includes/banner.md)]

[!include [preview-banner](../../includes/preview-banner.md)]

<span data-ttu-id="550ae-104">Es habitual que los registros de cliente se controlen en más de una aplicación.</span><span class="sxs-lookup"><span data-stu-id="550ae-104">It's typical for customer records to be mastered in more than one application.</span></span> <span data-ttu-id="550ae-105">Por ejemplo, la actividad de ventas puede aportar registros de clientes comerciales a través de una aplicación de Sales y el comercio electrónico o la venta minorista pueden aportar registros de cliente a través de una aplicación de Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="550ae-105">For example, sales activity can bring in commercial customer records through a Sales application, and e-Commerce or retail sales can bring in customer records through a Finance and Operations application.</span></span> <span data-ttu-id="550ae-106">Independientemente del origen del registro de cliente, se encuentra integrado en segundo plano entre aplicaciones e infraestructuras diferentes.</span><span class="sxs-lookup"><span data-stu-id="550ae-106">Regardless of where the customer record originates, it's integrated behind the scenes across application boundaries and infrastructure differences.</span></span> <span data-ttu-id="550ae-107">El control de cliente integrado ayuda a gestionar escenarios de múltiples maestros y proporciona una vista completa del cliente al conjunto de aplicaciones de Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="550ae-107">Integrated customer mastering helps handle multi-mastering scenarios and provides a comprehensive view of the customer to the Dynamics 365 application suite.</span></span>

## <a name="customer-data-flow"></a><span data-ttu-id="550ae-108">Flujo de datos del cliente</span><span class="sxs-lookup"><span data-stu-id="550ae-108">Customer data flow</span></span>

<span data-ttu-id="550ae-109">*Cliente* es un concepto bien definido en aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="550ae-109">*Customer* is a well-defined concept in applications.</span></span> <span data-ttu-id="550ae-110">Por lo tanto, la integración de los datos del cliente solo implica la armonización del concepto de cliente entre las dos aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="550ae-110">Therefore, the integration of customer data just involves harmonizing the customer concept between the two applications.</span></span> <span data-ttu-id="550ae-111">La ilustración siguiente muestra el flujo de datos del cliente.</span><span class="sxs-lookup"><span data-stu-id="550ae-111">The following illustration shows the customer data flow.</span></span>

![Flujo de datos del cliente](media/dual-write-customer-data-flow.png)

<span data-ttu-id="550ae-113">En general, los clientes pueden clasificarse en dos tipos: clientes comerciales/organizativos y consumidores/usuarios finales.</span><span class="sxs-lookup"><span data-stu-id="550ae-113">Customers can be broadly classified into two types: commercial/organizational customers and consumers/end users.</span></span> <span data-ttu-id="550ae-114">Estos dos tipos de clientes se almacenan y controlan de forma diferente en Finance and Operations y en Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="550ae-114">These two types of customers are stored and handled differently in Finance and Operations and Common Data Service.</span></span>

<span data-ttu-id="550ae-115">En Finance and Operations, tanto los clientes comerciales/organizativos como los consumidores/usuarios finales se controlan en una sola tabla que se llama **CustTable** (CustomerCustomerV3Entity) y se clasifican según el atributo **Type**.</span><span class="sxs-lookup"><span data-stu-id="550ae-115">In Finance and Operations, both commercial/organizational customers and consumers/end users are mastered in a single table that is named **CustTable** (CustomerCustomerV3Entity), and they are classified based on the **Type** attribute.</span></span> <span data-ttu-id="550ae-116">(Si **Type** se establece en **Organization**, el cliente es un cliente comercial/organizativo y si **Type** se establece en **Person**, el cliente es consumidor/usuario final). La información de la persona de contacto principal se gestiona a través de la entidad SMMContactPersonEntity.</span><span class="sxs-lookup"><span data-stu-id="550ae-116">(If **Type** is set to **Organization**, the customer is a commercial/organizational customer, and if **Type** is set to **Person**, the customer is a consumer/end user.) The primary contact person information is handled through the SMMContactPersonEntity entity.</span></span>

<span data-ttu-id="550ae-117">En Common Data Service, los clientes comerciales/organizativos se controlan en la entidad de cuenta y se identifican como clientes cuando el atributo **RelationshipType** se establece en **Customer**.</span><span class="sxs-lookup"><span data-stu-id="550ae-117">In Common Data Service, commercial/organizational customers are mastered in the Account entity and are identified as customers when the **RelationshipType** attribute is set to **Customer**.</span></span> <span data-ttu-id="550ae-118">La entidad Contact representa tanto a consumidores/usuarios finales como la persona de contacto.</span><span class="sxs-lookup"><span data-stu-id="550ae-118">Both consumers/end users and the contact person are represented by the Contact entity.</span></span> <span data-ttu-id="550ae-119">Para proporcionar una clara separación entre un cliente/usuario final y una persona de contacto, la entidad **Contact** tiene un indicador booleano llamado **Sellable**.</span><span class="sxs-lookup"><span data-stu-id="550ae-119">To provide a clear separation between a consumer/end user and a contact person, the **Contact** entity has a Boolean flag that is named **Sellable**.</span></span> <span data-ttu-id="550ae-120">Si **Sellable** es **True**, el contacto es un consumidor/usuario final y se pueden crear citas y pedidos para dicho contacto.</span><span class="sxs-lookup"><span data-stu-id="550ae-120">When **Sellable** is **True**, the contact is a consumer/end user, and quotations and orders can be created for that contact.</span></span> <span data-ttu-id="550ae-121">Si **Sellable** es **False**, el contacto es solo una persona de contacto principal de un cliente.</span><span class="sxs-lookup"><span data-stu-id="550ae-121">When **Sellable** is **False**, the contact is just a primary contact person of a customer.</span></span>

<span data-ttu-id="550ae-122">Cuando un contacto no sellable participa en un presupuesto o un proceso de pedido, **Sellable** se establece en **True** para marcar el contacto como sellable.</span><span class="sxs-lookup"><span data-stu-id="550ae-122">When a non-sellable contact participates in a quotation or order process, **Sellable** is set to **True** to flag the contact as a sellable contact.</span></span> <span data-ttu-id="550ae-123">Un contacto que se ha convertido en un contacto sellable permanece como contacto sellable.</span><span class="sxs-lookup"><span data-stu-id="550ae-123">A contact that has become a sellable contact remains a sellable contact.</span></span>

## <a name="templates"></a><span data-ttu-id="550ae-124">Plantillas</span><span class="sxs-lookup"><span data-stu-id="550ae-124">Templates</span></span>

<span data-ttu-id="550ae-125">Los datos del cliente incluyen toda la información sobre el cliente, como el grupo de clientes, las direcciones, la información de contacto, el perfil de pago, el perfil de factura y el estado de fidelidad.</span><span class="sxs-lookup"><span data-stu-id="550ae-125">Customer data includes all information about the customer, such as the customer group, addresses, contact information, payment profile, invoice profile, and loyalty status.</span></span> <span data-ttu-id="550ae-126">Una colección de mapas de entidad funciona conjuntamente durante la interacción de los datos del cliente, como se muestra en la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="550ae-126">A collection of entity maps works together during customer data interaction, as shown in the following table.</span></span>

<span data-ttu-id="550ae-127">Aplicaciones de Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="550ae-127">Finance and Operations apps</span></span> | <span data-ttu-id="550ae-128">Otras aplicaciones de Dynamics 365</span><span class="sxs-lookup"><span data-stu-id="550ae-128">Other Dynamics 365 apps</span></span>         | <span data-ttu-id="550ae-129">Descripción</span><span class="sxs-lookup"><span data-stu-id="550ae-129">Description</span></span>
----------------------------|---------------------------------|------------
<span data-ttu-id="550ae-130">Contactos V2 de CDS</span><span class="sxs-lookup"><span data-stu-id="550ae-130">CDS Contacts V2</span></span>             | <span data-ttu-id="550ae-131">contactos</span><span class="sxs-lookup"><span data-stu-id="550ae-131">contacts</span></span>                        | <span data-ttu-id="550ae-132">Esta plantilla sincroniza toda la información de contacto principal, secundaria, y terciaria, para clientes y proveedores.</span><span class="sxs-lookup"><span data-stu-id="550ae-132">This template synchronizes all primary, secondary, and tertiary contact information, for both customers and vendors.</span></span>
<span data-ttu-id="550ae-133">Grupos de clientes</span><span class="sxs-lookup"><span data-stu-id="550ae-133">Customer groups</span></span>             | <span data-ttu-id="550ae-134">msdyn_customergroups</span><span class="sxs-lookup"><span data-stu-id="550ae-134">msdyn_customergroups</span></span>            | <span data-ttu-id="550ae-135">Esta plantilla sincroniza la información del grupo de clientes.</span><span class="sxs-lookup"><span data-stu-id="550ae-135">This template synchronizes customer group information.</span></span>
<span data-ttu-id="550ae-136">Método de pago de cliente</span><span class="sxs-lookup"><span data-stu-id="550ae-136">Customer payment method</span></span>     | <span data-ttu-id="550ae-137">msdyn_customerpaymentmethods</span><span class="sxs-lookup"><span data-stu-id="550ae-137">msdyn_customerpaymentmethods</span></span>    | <span data-ttu-id="550ae-138">Esta plantilla sincroniza la información del método de pago del cliente.</span><span class="sxs-lookup"><span data-stu-id="550ae-138">This template synchronizes customer payment method information.</span></span>
<span data-ttu-id="550ae-139">Clientes V3</span><span class="sxs-lookup"><span data-stu-id="550ae-139">Customers V3</span></span>                | <span data-ttu-id="550ae-140">cuentas</span><span class="sxs-lookup"><span data-stu-id="550ae-140">accounts</span></span>                        | <span data-ttu-id="550ae-141">Esta plantilla sincroniza la información de maestro de cliente para los clientes comerciales y organizativos.</span><span class="sxs-lookup"><span data-stu-id="550ae-141">This template synchronizes customer master information for commercial and organizational customers.</span></span>
<span data-ttu-id="550ae-142">Clientes V3</span><span class="sxs-lookup"><span data-stu-id="550ae-142">Customers V3</span></span>                | <span data-ttu-id="550ae-143">contactos</span><span class="sxs-lookup"><span data-stu-id="550ae-143">contacts</span></span>                        | <span data-ttu-id="550ae-144">Esta plantilla sincroniza los datos maestros de cliente para los consumidores y los usuarios finales.</span><span class="sxs-lookup"><span data-stu-id="550ae-144">This template synchronizes customer master data for consumers and end users.</span></span>
<span data-ttu-id="550ae-145">Tarjeta de fidelización</span><span class="sxs-lookup"><span data-stu-id="550ae-145">Loyalty card</span></span>                | <span data-ttu-id="550ae-146">msdyn_loyaltycards</span><span class="sxs-lookup"><span data-stu-id="550ae-146">msdyn_loyaltycards</span></span>              | <span data-ttu-id="550ae-147">Esta plantilla sincroniza la información de la tarjeta de fidelización del cliente.</span><span class="sxs-lookup"><span data-stu-id="550ae-147">This template synchronizes customer loyalty card information.</span></span>
<span data-ttu-id="550ae-148">Afijos de nombre</span><span class="sxs-lookup"><span data-stu-id="550ae-148">Name affixes</span></span>                | <span data-ttu-id="550ae-149">msdyn_nameaffixes</span><span class="sxs-lookup"><span data-stu-id="550ae-149">msdyn_nameaffixes</span></span>               | <span data-ttu-id="550ae-150">Esta plantilla sincroniza los datos de referencia de los afijos de nombre, para clientes y proveedores.</span><span class="sxs-lookup"><span data-stu-id="550ae-150">This template synchronizes name affixes reference data, for both customers and vendors.</span></span>
<span data-ttu-id="550ae-151">Líneas de días de pago de CDS V2</span><span class="sxs-lookup"><span data-stu-id="550ae-151">Payment day lines CDS V2</span></span>    | <span data-ttu-id="550ae-152">msdyn_paymentdaylines</span><span class="sxs-lookup"><span data-stu-id="550ae-152">msdyn_paymentdaylines</span></span>           | <span data-ttu-id="550ae-153">Esta plantilla sincroniza los datos de referencia de las líneas de días de pago, para clientes y proveedores.</span><span class="sxs-lookup"><span data-stu-id="550ae-153">This template synchronizes payment day lines reference data, for both customers and vendors.</span></span>
<span data-ttu-id="550ae-154">Días de pago de CDS</span><span class="sxs-lookup"><span data-stu-id="550ae-154">Payment days CDS</span></span>            | <span data-ttu-id="550ae-155">msdyn_paymentdays</span><span class="sxs-lookup"><span data-stu-id="550ae-155">msdyn_paymentdays</span></span>               | <span data-ttu-id="550ae-156">Esta plantilla sincroniza los datos de referencia de los días de pago, para clientes y proveedores.</span><span class="sxs-lookup"><span data-stu-id="550ae-156">This template synchronizes payment days reference data, for both customers and vendors.</span></span>
<span data-ttu-id="550ae-157">Líneas de multivencimientos</span><span class="sxs-lookup"><span data-stu-id="550ae-157">Payment schedule lines</span></span>      | <span data-ttu-id="550ae-158">msdyn_paymentschedulelines</span><span class="sxs-lookup"><span data-stu-id="550ae-158">msdyn_paymentschedulelines</span></span>      | <span data-ttu-id="550ae-159">Sincroniza los datos de referencia de las líneas de programación de pago, para clientes y proveedores.</span><span class="sxs-lookup"><span data-stu-id="550ae-159">Syncs payment schedule lines reference data, for both customers and vendors.</span></span>
<span data-ttu-id="550ae-160">Multivencimientos</span><span class="sxs-lookup"><span data-stu-id="550ae-160">Payment schedule</span></span>            | <span data-ttu-id="550ae-161">msdyn_paymentschedules</span><span class="sxs-lookup"><span data-stu-id="550ae-161">msdyn_paymentschedules</span></span>          | <span data-ttu-id="550ae-162">Esta plantilla sincroniza los datos de referencia de la programación de pago, para clientes y proveedores.</span><span class="sxs-lookup"><span data-stu-id="550ae-162">This template synchronizes payment schedule reference data, for both customers and vendors.</span></span>
<span data-ttu-id="550ae-163">Condiciones de pago</span><span class="sxs-lookup"><span data-stu-id="550ae-163">Terms of payment</span></span>            | <span data-ttu-id="550ae-164">msdyn_paymentterms</span><span class="sxs-lookup"><span data-stu-id="550ae-164">msdyn_paymentterms</span></span>              | <span data-ttu-id="550ae-165">Esta plantilla sincroniza los datos de referencia de las los términos de pago (términos de pago), para clientes y proveedores.</span><span class="sxs-lookup"><span data-stu-id="550ae-165">This template synchronizes payment terms (terms of payment) reference data, for both customers and vendors.</span></span>

[!include [banner](../../includes/dual-write-symbols.md)]

[!include [mapping contacts contacts](includes/CDSContactsV2-contacts.md)]

[!include [mapping customer group](includes/CustCustomerGroup-msdyn-customergroups.md)]

[!include [mapping customer payment method](includes/CustomerPaymentMethod-msdyn-customerpaymentmethods.md)]

[!include [mapping customer accounts](includes/CustomersV3-accounts.md)]

[!include [mapping customer contacts](includes/CustomersV3-contacts.md)]

[!include [mapping loyalty card](includes/LoyaltyCard-msdyn-loyaltycards.md)]

[!include [mapping name affixes](includes/NameAffixes-msdyn-nameaffixes.md)]

[!include [mapping payment day lines](includes/PaymentDayLinesCdsV2-msdyn-paymentdaylines.md)]

[!include [mapping payment days](includes/PaymentDaysCds-msdyn-paymentdays.md)]

[!include [mapping payment schedule lines](includes/PaymentScheduleLines-msdyn-paymentschedulelines.md)]

[!include [mapping payment schedules](includes/PaymentSchedules-msdyn-paymentschedules.md)]

[!include [mapping terms of payment](includes/TermsofPayment-msdyn-paymentterms.md)]
