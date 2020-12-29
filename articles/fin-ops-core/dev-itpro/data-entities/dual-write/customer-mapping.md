---
title: Maestro de clientes integrado
description: En este tema se describe la integración de datos de cliente entre Finance and Operations y Dataverse.
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
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: ramasri
ms.dyn365.ops.version: ''
ms.search.validFrom: 2019-07-15
ms.openlocfilehash: 801538e320ca78b0cc55bb4e4b8a80d38b9b48d6
ms.sourcegitcommit: 659375c4cc7f5524cbf91cf6160f6a410960ac16
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/05/2020
ms.locfileid: "4685648"
---
# <a name="integrated-customer-master"></a><span data-ttu-id="3519d-103">Maestro de clientes integrado</span><span class="sxs-lookup"><span data-stu-id="3519d-103">Integrated customer master</span></span>

[!include [banner](../../includes/banner.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]


<span data-ttu-id="3519d-104">Los datos del cliente se pueden dominar en más de una aplicación de Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="3519d-104">Customer data can be mastered in more than one Dynamics 365 application.</span></span> <span data-ttu-id="3519d-105">Por ejemplo, una fila de cliente puede originarse a través de la actividad de ventas en Dynamics 365 Sales (una aplicación basada en modelos en Dynamics 365), o una fila puede originarse a través de la actividad minorista en Dynamics 365 Commerce (una aplicación de Finance and Operations).</span><span class="sxs-lookup"><span data-stu-id="3519d-105">For example, a customer row can originate though sales activity in Dynamics 365 Sales (a model-driven app in Dynamics 365), or a row can originate through retail activity in Dynamics 365 Commerce (a Finance and Operations app).</span></span> <span data-ttu-id="3519d-106">No importa dónde se originan los datos del cliente, se integran detrás de escena.</span><span class="sxs-lookup"><span data-stu-id="3519d-106">No matter where where the customer data originates, it is integrated behind the scenes.</span></span> <span data-ttu-id="3519d-107">El maestro de clientes integrado le brinda la flexibilidad de dominar los datos del cliente en cualquier aplicación de Dynamics 365 y brinda una visión integral del cliente a través del conjunto de aplicaciones de Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="3519d-107">Integrated customer master gives you the flexibility to master customer data in any Dynamics 365 application and provides a comprehensive view of the customer across the Dynamics 365 application suite.</span></span>

## <a name="customer-data-flow"></a><span data-ttu-id="3519d-108">Flujo de datos del cliente</span><span class="sxs-lookup"><span data-stu-id="3519d-108">Customer data flow</span></span>

<span data-ttu-id="3519d-109">*Cliente* es un concepto bien definido en aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="3519d-109">*Customer* is a well-defined concept in applications.</span></span> <span data-ttu-id="3519d-110">Por lo tanto, la integración de los datos del cliente solo implica la armonización del concepto de cliente entre las dos aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="3519d-110">Therefore, the integration of customer data just involves harmonizing the customer concept between the two applications.</span></span> <span data-ttu-id="3519d-111">La ilustración siguiente muestra el flujo de datos del cliente.</span><span class="sxs-lookup"><span data-stu-id="3519d-111">The following illustration shows the customer data flow.</span></span>

![Flujo de datos del cliente](media/dual-write-customer-data-flow.png)

<span data-ttu-id="3519d-113">En general, los clientes pueden clasificarse en dos tipos: clientes comerciales/organizativos y consumidores/usuarios finales.</span><span class="sxs-lookup"><span data-stu-id="3519d-113">Customers can be broadly classified into two types: commercial/organizational customers and consumers/end users.</span></span> <span data-ttu-id="3519d-114">Estos dos tipos de clientes se almacenan y controlan de forma diferente en Finance and Operations y en Dataverse.</span><span class="sxs-lookup"><span data-stu-id="3519d-114">These two types of customers are stored and handled differently in Finance and Operations and Dataverse.</span></span>

<span data-ttu-id="3519d-115">En Finance and Operations, tanto los clientes comerciales/organizativos como los consumidores/usuarios finales se controlan en una sola tabla que se llama **CustTable** (CustCustomerV3Entity) y se clasifican según el atributo **Type**.</span><span class="sxs-lookup"><span data-stu-id="3519d-115">In Finance and Operations, both commercial/organizational customers and consumers/end users are mastered in a single table that is named **CustTable** (CustCustomerV3Entity), and they are classified based on the **Type** attribute.</span></span> <span data-ttu-id="3519d-116">(Si **Type** se establece en **Organization**, el cliente es un cliente comercial/organizativo y si **Type** se establece en **Person**, el cliente es consumidor/usuario final). La información de la persona de contacto principal se gestiona a través de la entidad SMMContactPersonEntity.</span><span class="sxs-lookup"><span data-stu-id="3519d-116">(If **Type** is set to **Organization**, the customer is a commercial/organizational customer, and if **Type** is set to **Person**, the customer is a consumer/end user.) The primary contact person information is handled through the SMMContactPersonEntity entity.</span></span>

<span data-ttu-id="3519d-117">En Dataverse, los clientes comerciales/organizativos se controlan en la entidad de cuenta y se identifican como clientes cuando el atributo **RelationshipType** se establece en **Customer**.</span><span class="sxs-lookup"><span data-stu-id="3519d-117">In Dataverse, commercial/organizational customers are mastered in the Account entity and are identified as customers when the **RelationshipType** attribute is set to **Customer**.</span></span> <span data-ttu-id="3519d-118">La entidad Contact representa tanto a consumidores/usuarios finales como la persona de contacto.</span><span class="sxs-lookup"><span data-stu-id="3519d-118">Both consumers/end users and the contact person are represented by the Contact entity.</span></span> <span data-ttu-id="3519d-119">Para proporcionar una clara separación entre un cliente/usuario final y una persona de contacto, la entidad **Contact** tiene un indicador booleano llamado **Sellable**.</span><span class="sxs-lookup"><span data-stu-id="3519d-119">To provide a clear separation between a consumer/end user and a contact person, the **Contact** entity has a Boolean flag that is named **Sellable**.</span></span> <span data-ttu-id="3519d-120">Si **Sellable** es **True**, el contacto es un consumidor/usuario final y se pueden crear citas y pedidos para dicho contacto.</span><span class="sxs-lookup"><span data-stu-id="3519d-120">When **Sellable** is **True**, the contact is a consumer/end user, and quotations and orders can be created for that contact.</span></span> <span data-ttu-id="3519d-121">Si **Sellable** es **False**, el contacto es solo una persona de contacto principal de un cliente.</span><span class="sxs-lookup"><span data-stu-id="3519d-121">When **Sellable** is **False**, the contact is just a primary contact person of a customer.</span></span>

<span data-ttu-id="3519d-122">Cuando un contacto no sellable participa en un presupuesto o un proceso de pedido, **Sellable** se establece en **True** para marcar el contacto como sellable.</span><span class="sxs-lookup"><span data-stu-id="3519d-122">When a non-sellable contact participates in a quotation or order process, **Sellable** is set to **True** to flag the contact as a sellable contact.</span></span> <span data-ttu-id="3519d-123">Un contacto que se ha convertido en un contacto sellable permanece como contacto sellable.</span><span class="sxs-lookup"><span data-stu-id="3519d-123">A contact that has become a sellable contact remains a sellable contact.</span></span>

## <a name="templates"></a><span data-ttu-id="3519d-124">Plantillas</span><span class="sxs-lookup"><span data-stu-id="3519d-124">Templates</span></span>

<span data-ttu-id="3519d-125">Los datos del cliente incluyen toda la información sobre el cliente, como el grupo de clientes, las direcciones, la información de contacto, el perfil de pago, el perfil de factura y el estado de fidelidad.</span><span class="sxs-lookup"><span data-stu-id="3519d-125">Customer data includes all information about the customer, such as the customer group, addresses, contact information, payment profile, invoice profile, and loyalty status.</span></span> <span data-ttu-id="3519d-126">Una colección de asignaciones de tabla funciona conjuntamente durante la interacción de los datos del cliente, como se muestra en la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="3519d-126">A collection of table maps works together during customer data interaction, as shown in the following table.</span></span>

<span data-ttu-id="3519d-127">Aplicaciones de Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="3519d-127">Finance and Operations apps</span></span> | <span data-ttu-id="3519d-128">Otras aplicaciones de Dynamics 365</span><span class="sxs-lookup"><span data-stu-id="3519d-128">Other Dynamics 365 apps</span></span>         | <span data-ttu-id="3519d-129">Descripción</span><span class="sxs-lookup"><span data-stu-id="3519d-129">Description</span></span>
----------------------------|---------------------------------|------------
<span data-ttu-id="3519d-130">Contactos V2 de CDS</span><span class="sxs-lookup"><span data-stu-id="3519d-130">CDS Contacts V2</span></span>             | <span data-ttu-id="3519d-131">contactos</span><span class="sxs-lookup"><span data-stu-id="3519d-131">contacts</span></span>                        | <span data-ttu-id="3519d-132">Esta plantilla sincroniza toda la información de contacto principal, secundaria, y terciaria, para clientes y proveedores.</span><span class="sxs-lookup"><span data-stu-id="3519d-132">This template synchronizes all primary, secondary, and tertiary contact information, for both customers and vendors.</span></span>
<span data-ttu-id="3519d-133">Grupos de clientes</span><span class="sxs-lookup"><span data-stu-id="3519d-133">Customer groups</span></span>             | <span data-ttu-id="3519d-134">msdyn_customergroups</span><span class="sxs-lookup"><span data-stu-id="3519d-134">msdyn_customergroups</span></span>            | <span data-ttu-id="3519d-135">Esta plantilla sincroniza la información del grupo de clientes.</span><span class="sxs-lookup"><span data-stu-id="3519d-135">This template synchronizes customer group information.</span></span>
<span data-ttu-id="3519d-136">Método de pago de cliente</span><span class="sxs-lookup"><span data-stu-id="3519d-136">Customer payment method</span></span>     | <span data-ttu-id="3519d-137">msdyn_customerpaymentmethods</span><span class="sxs-lookup"><span data-stu-id="3519d-137">msdyn_customerpaymentmethods</span></span>    | <span data-ttu-id="3519d-138">Esta plantilla sincroniza la información del método de pago del cliente.</span><span class="sxs-lookup"><span data-stu-id="3519d-138">This template synchronizes customer payment method information.</span></span>
<span data-ttu-id="3519d-139">Clientes V3</span><span class="sxs-lookup"><span data-stu-id="3519d-139">Customers V3</span></span>                | <span data-ttu-id="3519d-140">cuentas</span><span class="sxs-lookup"><span data-stu-id="3519d-140">accounts</span></span>                        | <span data-ttu-id="3519d-141">Esta plantilla sincroniza la información de maestro de cliente para los clientes comerciales y organizativos.</span><span class="sxs-lookup"><span data-stu-id="3519d-141">This template synchronizes customer master information for commercial and organizational customers.</span></span>
<span data-ttu-id="3519d-142">Clientes V3</span><span class="sxs-lookup"><span data-stu-id="3519d-142">Customers V3</span></span>                | <span data-ttu-id="3519d-143">contactos</span><span class="sxs-lookup"><span data-stu-id="3519d-143">contacts</span></span>                        | <span data-ttu-id="3519d-144">Esta plantilla sincroniza los datos maestros de cliente para los consumidores y los usuarios finales.</span><span class="sxs-lookup"><span data-stu-id="3519d-144">This template synchronizes customer master data for consumers and end users.</span></span>
<span data-ttu-id="3519d-145">Afijos de nombre</span><span class="sxs-lookup"><span data-stu-id="3519d-145">Name affixes</span></span>                | <span data-ttu-id="3519d-146">msdyn_nameaffixes</span><span class="sxs-lookup"><span data-stu-id="3519d-146">msdyn_nameaffixes</span></span>               | <span data-ttu-id="3519d-147">Esta plantilla sincroniza los datos de referencia de los afijos de nombre, para clientes y proveedores.</span><span class="sxs-lookup"><span data-stu-id="3519d-147">This template synchronizes name affixes reference data, for both customers and vendors.</span></span>
<span data-ttu-id="3519d-148">Líneas de días de pago de CDS V2</span><span class="sxs-lookup"><span data-stu-id="3519d-148">Payment day lines CDS V2</span></span>    | <span data-ttu-id="3519d-149">msdyn_paymentdaylines</span><span class="sxs-lookup"><span data-stu-id="3519d-149">msdyn_paymentdaylines</span></span>           | <span data-ttu-id="3519d-150">Esta plantilla sincroniza los datos de referencia de las líneas de días de pago, para clientes y proveedores.</span><span class="sxs-lookup"><span data-stu-id="3519d-150">This template synchronizes payment day lines reference data, for both customers and vendors.</span></span>
<span data-ttu-id="3519d-151">Días de pago de CDS</span><span class="sxs-lookup"><span data-stu-id="3519d-151">Payment days CDS</span></span>            | <span data-ttu-id="3519d-152">msdyn_paymentdays</span><span class="sxs-lookup"><span data-stu-id="3519d-152">msdyn_paymentdays</span></span>               | <span data-ttu-id="3519d-153">Esta plantilla sincroniza los datos de referencia de los días de pago, para clientes y proveedores.</span><span class="sxs-lookup"><span data-stu-id="3519d-153">This template synchronizes payment days reference data, for both customers and vendors.</span></span>
<span data-ttu-id="3519d-154">Líneas de multivencimientos</span><span class="sxs-lookup"><span data-stu-id="3519d-154">Payment schedule lines</span></span>      | <span data-ttu-id="3519d-155">msdyn_paymentschedulelines</span><span class="sxs-lookup"><span data-stu-id="3519d-155">msdyn_paymentschedulelines</span></span>      | <span data-ttu-id="3519d-156">Sincroniza los datos de referencia de las líneas de programación de pago, para clientes y proveedores.</span><span class="sxs-lookup"><span data-stu-id="3519d-156">Syncs payment schedule lines reference data, for both customers and vendors.</span></span>
<span data-ttu-id="3519d-157">Multivencimientos</span><span class="sxs-lookup"><span data-stu-id="3519d-157">Payment schedule</span></span>            | <span data-ttu-id="3519d-158">msdyn_paymentschedules</span><span class="sxs-lookup"><span data-stu-id="3519d-158">msdyn_paymentschedules</span></span>          | <span data-ttu-id="3519d-159">Esta plantilla sincroniza los datos de referencia de la programación de pago, para clientes y proveedores.</span><span class="sxs-lookup"><span data-stu-id="3519d-159">This template synchronizes payment schedule reference data, for both customers and vendors.</span></span>
<span data-ttu-id="3519d-160">Condiciones de pago</span><span class="sxs-lookup"><span data-stu-id="3519d-160">Terms of payment</span></span>            | <span data-ttu-id="3519d-161">msdyn_paymentterms</span><span class="sxs-lookup"><span data-stu-id="3519d-161">msdyn_paymentterms</span></span>              | <span data-ttu-id="3519d-162">Esta plantilla sincroniza los datos de referencia de las los términos de pago (términos de pago), para clientes y proveedores.</span><span class="sxs-lookup"><span data-stu-id="3519d-162">This template synchronizes payment terms (terms of payment) reference data, for both customers and vendors.</span></span>

[!include [banner](../../includes/dual-write-symbols.md)]

[!include [mapping contacts contacts](includes/CDSContactsV2-contacts.md)]

[!include [mapping customer group](includes/CustCustomerGroup-msdyn-customergroups.md)]

[!include [mapping customer payment method](includes/CustomerPaymentMethod-msdyn-customerpaymentmethods.md)]

[!include [mapping customer accounts](includes/CustomersV3-accounts.md)]

[!include [mapping customer contacts](includes/CustomersV3-contacts.md)]

[!include [mapping name affixes](includes/NameAffixes-msdyn-nameaffixes.md)]

[!include [mapping payment day lines](includes/PaymentDayLinesCdsV2-msdyn-paymentdaylines.md)]

[!include [mapping payment days](includes/PaymentDaysCds-msdyn-paymentdays.md)]

[!include [mapping payment schedule lines](includes/PaymentScheduleLines-msdyn-paymentschedulelines.md)]

[!include [mapping payment schedules](includes/PaymentSchedules-msdyn-paymentschedules.md)]

[!include [mapping terms of payment](includes/TermsofPayment-msdyn-paymentterms.md)]
