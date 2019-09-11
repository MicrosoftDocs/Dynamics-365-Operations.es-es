---
title: Visión general de la configuración de proveedores
description: Este artículo describe las páginas que usa para configurar la funcionalidad básica y opcional para Proveedores en Microsoft Dynamics 365 for Finance and Operations. También describen los pasos de configuración que debe completar antes de comenzar a configurar Proveedores.
author: abruer
manager: AnnBe
ms.date: 07/25/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: BankAccountTable, DeliveryMode, PaymTerm, VendGroup, VendParameters, VendPaymMode, VendTable
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.custom: 24671
ms.assetid: 82561fe7-b2d6-464c-9347-79d0ce0f9743
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: ce2caf8df871ee8f577b3a1af9d71244a1dc4694
ms.sourcegitcommit: e286572ce94a9442a5b3076c3ff5b429be0ed512
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/06/2019
ms.locfileid: "1864999"
---
# <a name="configure-accounts-payable-overview"></a><span data-ttu-id="80e12-104">Visión general de la configuración de proveedores</span><span class="sxs-lookup"><span data-stu-id="80e12-104">Configure Accounts payable overview</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="80e12-105">Este artículo describe las páginas que usa para configurar la funcionalidad básica y opcional para Proveedores en Microsoft Dynamics 365 for Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="80e12-105">This article describes the pages that you use to set up basic and optional functionality for Accounts payable in Microsoft Dynamics 365 for Finance and Operations.</span></span> <span data-ttu-id="80e12-106">También describen los pasos de configuración que debe completar antes de comenzar a configurar Proveedores.</span><span class="sxs-lookup"><span data-stu-id="80e12-106">It also describes setup steps that you must complete before you start to set up Accounts payable.</span></span>

<a name="prerequisites-for-accounts-payable-setup"></a><span data-ttu-id="80e12-107">Requisitos previos para la configuración de proveedores</span><span class="sxs-lookup"><span data-stu-id="80e12-107">Prerequisites for Accounts payable setup</span></span>
----------------------------------------

<span data-ttu-id="80e12-108">Para poder configurar los proveedores, debe completar la configuración siguiente:</span><span class="sxs-lookup"><span data-stu-id="80e12-108">Before you can set up Accounts payable, you must complete the following setup:</span></span>

-   <span data-ttu-id="80e12-109">En contabilidad general:</span><span class="sxs-lookup"><span data-stu-id="80e12-109">In General ledger:</span></span>
    -   <span data-ttu-id="80e12-110">Si pretende usar diarios de pagos, debe configurarlos.</span><span class="sxs-lookup"><span data-stu-id="80e12-110">If you plan to use payment journals, set up payment journals.</span></span>
    -   <span data-ttu-id="80e12-111">Si pretende ejecutar ajustes del tipo de cambio, configure los códigos de divisa en la página de divisas, los tipos de cambio en la página de tipos de cambio y los tipos de cambio de divisa puesto en la página de tipos de cambio de divisa.</span><span class="sxs-lookup"><span data-stu-id="80e12-111">If you plan to run exchange rate adjustments, set up currency codes on the Currencies page, set up exchange rate types on the Exchange rate types page, and set up currency exchange rates on the Currency exchange rates page.</span></span>
-   <span data-ttu-id="80e12-112">En Gestión de efectivo y bancos, configure cuentas bancarias para usarlas con formas de pago.</span><span class="sxs-lookup"><span data-stu-id="80e12-112">In Cash and bank management, set up bank accounts to use with methods of payment.</span></span>

## <a name="setup-pages-for-accounts-payable"></a><span data-ttu-id="80e12-113">Configurar páginas para proveedores</span><span class="sxs-lookup"><span data-stu-id="80e12-113">Setup pages for Accounts payable</span></span>

<span data-ttu-id="80e12-114">Utilice las páginas siguientes para configurar la funcionalidad básica de Proveedores para cada entidad jurídica.</span><span class="sxs-lookup"><span data-stu-id="80e12-114">Use the following pages to set up the basic functionality of Accounts payable for each legal entity.</span></span> <span data-ttu-id="80e12-115">Las páginas se enumeran en el orden de configuración recomendado.</span><span class="sxs-lookup"><span data-stu-id="80e12-115">The pages are listed in the recommended order of setup.</span></span> <span data-ttu-id="80e12-116">Para simplificar el proceso de configuración, puede crear plantillas a partir de los primeros registros que cree.</span><span class="sxs-lookup"><span data-stu-id="80e12-116">To make the setup process easier, you can create templates from the first records that you create.</span></span> <span data-ttu-id="80e12-117">En una plantilla, normalmente suelen introducirse valores en muchos campos para reflejar las características que la organización desea implantar para un tipo concreto de proveedor.</span><span class="sxs-lookup"><span data-stu-id="80e12-117">In a template, values are typically entered in many fields to reflect the features that the organization wants to implement for a particular type of vendor.</span></span>
1.  <span data-ttu-id="80e12-118">En la página de términos de pago, defina las condiciones de pago que va a asignar a los pedidos de ventas, pedidos de compra, clientes y proveedores, que determinan las fechas de vencimiento de las facturas.</span><span class="sxs-lookup"><span data-stu-id="80e12-118">On the Terms of payment page, define the terms of payment that you assign to sales orders, purchase orders, customers, and vendors, and that determine invoice due dates.</span></span> <span data-ttu-id="80e12-119">Para obtener más información, consulte [Definir tarifas de pago del proveedor](tasks/define-vendor-payment-fees.md).</span><span class="sxs-lookup"><span data-stu-id="80e12-119">For more information, see [Define vendor payment fees](tasks/define-vendor-payment-fees.md).</span></span>
2.  <span data-ttu-id="80e12-120">En la página Métodos de pago - Proveedor, cree y mantenga la información sobre cómo paga la organización a sus proveedores.</span><span class="sxs-lookup"><span data-stu-id="80e12-120">On the Methods of payment - vendors page, create and maintain information about how the organization pays its vendors.</span></span>
3.  <span data-ttu-id="80e12-121">En la página de grupos de proveedores, cree y mantenga grupos de proveedores que comparten los principales parámetros para el registro, liquidación y pago, informes y previsiones.</span><span class="sxs-lookup"><span data-stu-id="80e12-121">On the Vendor groups page, create and maintain groups of vendors that share important parameters for posting, settlement and payment, reporting, and forecasting.</span></span>
4.  <span data-ttu-id="80e12-122">En la página de perfiles de contabilización de proveedores, defina cómo se registran las transacciones del proveedor en la contabilidad general.</span><span class="sxs-lookup"><span data-stu-id="80e12-122">On the Vendor posting profiles page, define how vendor transactions are posted to the general ledger.</span></span>
5.  <span data-ttu-id="80e12-123">En la página de parámetros de proveedores, configure los parámetros predeterminados que se aplican si no se especifica una configuración más concreta, parámetros para varios tipos de funciones y varias secuencias numéricas para proveedores.</span><span class="sxs-lookup"><span data-stu-id="80e12-123">On the Accounts payable parameters page, set up default settings that are applied if a more specific setting isn't specified, parameters for various kinds of functionality, and the various number sequences for Accounts payable.</span></span>
6.  <span data-ttu-id="80e12-124">En la página de configuración de formulario, defina el formato de varios documentos relacionados con proveedores y que la organización usa para realizar un seguimiento de las recepciones de los proveedores y para indicar motivos del flujo de pagos a los proveedores.</span><span class="sxs-lookup"><span data-stu-id="80e12-124">On the Form setup page, define the format of various documents that are related to vendors, and that the organization uses to keep track of receipts from vendors and enter reasons for the flow of payments to vendors.</span></span>
7.  <span data-ttu-id="80e12-125">En la página Proveedores, cree y mantenga las cuentas de proveedor y también las de autoridades fiscales a las que su organización paga impuestos.</span><span class="sxs-lookup"><span data-stu-id="80e12-125">On the Vendors page, create and maintain vendor accounts, and also the tax authorities that your organization reports sales taxes to.</span></span>

## <a name="optional-setup-pages-for-accounts-payable"></a><span data-ttu-id="80e12-126">Páginas de configuración opcionales de proveedores</span><span class="sxs-lookup"><span data-stu-id="80e12-126">Optional setup pages for Accounts payable</span></span>
<span data-ttu-id="80e12-127">Además de la funcionalidad básica, los proveedores tienen otra funcionalidad que puede configurar.</span><span class="sxs-lookup"><span data-stu-id="80e12-127">In addition to the basic functionality, Accounts payable has other functionality that you can set up.</span></span>

<span data-ttu-id="80e12-128">Las páginas de configuración adicionales están organizadas por funciones.</span><span class="sxs-lookup"><span data-stu-id="80e12-128">The additional setup pages are organized by functionality.</span></span>

<span data-ttu-id="80e12-129">**Directivas**</span><span class="sxs-lookup"><span data-stu-id="80e12-129">**Policies**</span></span>
-   <span data-ttu-id="80e12-130">En la página de la directiva de facturas de proveedor, configure las directivas de facturas de proveedor.</span><span class="sxs-lookup"><span data-stu-id="80e12-130">On the Vendor invoice policy page, set up vendor invoice policies.</span></span>

<span data-ttu-id="80e12-131">**Conciliación de facturas**</span><span class="sxs-lookup"><span data-stu-id="80e12-131">**Invoice matching**</span></span>

-   <span data-ttu-id="80e12-132">En la página de tolerancias de totales de facturas, configure las tolerancias para los totales de factura.</span><span class="sxs-lookup"><span data-stu-id="80e12-132">On the Invoice totals tolerances page, set up tolerances for invoice totals.</span></span>
-   <span data-ttu-id="80e12-133">En la página de directiva de conciliación, configure directivas de triple y doble conciliación.</span><span class="sxs-lookup"><span data-stu-id="80e12-133">On the Matching policy page, set up two-way and three-way matching policies.</span></span>
-   <span data-ttu-id="80e12-134">En la página de tolerancias de precios, configure las tolerancias para los precios por unidad.</span><span class="sxs-lookup"><span data-stu-id="80e12-134">On the Price tolerances page, set up tolerances for unit prices.</span></span>
-   <span data-ttu-id="80e12-135">En la página de grupos de tolerancias para los precios de artículos, configure grupos de tolerancia para los precios de artículos.</span><span class="sxs-lookup"><span data-stu-id="80e12-135">On the Item price tolerance groups page, set up tolerance groups for item prices.</span></span>
-   <span data-ttu-id="80e12-136">En la página de grupos de tolerancias para los precios de proveedor, configure grupos de tolerancia para los precios de proveedor.</span><span class="sxs-lookup"><span data-stu-id="80e12-136">On the Vendor price tolerance groups page, set up  tolerance groups for vendor prices.</span></span>
-   <span data-ttu-id="80e12-137">En la página de tolerancias de gastos, configure las tolerancias para gastos.</span><span class="sxs-lookup"><span data-stu-id="80e12-137">On the Charges tolerances page, set up tolerances for charges.</span></span>

<span data-ttu-id="80e12-138">**Flujo de trabajo**</span><span class="sxs-lookup"><span data-stu-id="80e12-138">**Workflow**</span></span>

-   <span data-ttu-id="80e12-139">En la página de flujos de trabajo de proveedores, configure los parámetros de flujos de trabajo para las aprobaciones del diario y las solicitudes de compra.</span><span class="sxs-lookup"><span data-stu-id="80e12-139">On the Accounts payable workflows page, set up workflow configurations for journal approvals and purchase requisitions.</span></span>

<span data-ttu-id="80e12-140">**Motivos**</span><span class="sxs-lookup"><span data-stu-id="80e12-140">**Reasons**</span></span>

-   <span data-ttu-id="80e12-141">En la página de motivos de proveedor, configure los códigos de motivo.</span><span class="sxs-lookup"><span data-stu-id="80e12-141">On the Vendor reasons page, set up reason codes.</span></span>

<span data-ttu-id="80e12-142">**Gastos**</span><span class="sxs-lookup"><span data-stu-id="80e12-142">**Charges**</span></span>

-   <span data-ttu-id="80e12-143">En la página de código de gastos, configure los códigos para los gastos que se usan en los pedidos de compra.</span><span class="sxs-lookup"><span data-stu-id="80e12-143">On the Charges code page, set up codes for the charges that are used in purchase orders.</span></span>
-   <span data-ttu-id="80e12-144">En la página de grupo de gastos del proveedor , cree y mantenga grupos de gastos para los proveedores.</span><span class="sxs-lookup"><span data-stu-id="80e12-144">On the Vendor charges group page, create and maintain charges groups for vendors.</span></span>
-   <span data-ttu-id="80e12-145">En la página de grupos de gastos de artículos, cree y mantenga grupos de gastos para los artículos.</span><span class="sxs-lookup"><span data-stu-id="80e12-145">On the Item charge groups page, create and maintain charges groups for items.</span></span>
-   <span data-ttu-id="80e12-146">En la página de gastos automáticos, defina los gastos que se asignan automáticamente a pedidos.</span><span class="sxs-lookup"><span data-stu-id="80e12-146">On the Auto charges page, define the charges that are automatically assigned to orders.</span></span>

<span data-ttu-id="80e12-147">**Artículos adicionales**</span><span class="sxs-lookup"><span data-stu-id="80e12-147">**Supplementary items**</span></span>

-   <span data-ttu-id="80e12-148">En la página Grupos de artículos adicionales - Proveedor , cree y mantenga grupos de artículos adicionales para proveedores.</span><span class="sxs-lookup"><span data-stu-id="80e12-148">On the Supplementary item groups - Vendor page, create and maintain supplementary item groups for vendors.</span></span>
-   <span data-ttu-id="80e12-149">En la página Grupos de artículos adicionales - Inventario, cree y mantenga grupos de artículos adicionales para artículos.</span><span class="sxs-lookup"><span data-stu-id="80e12-149">On the Supplementary item groups - Inventory page, create and maintain supplementary item groups for items.</span></span>

<span data-ttu-id="80e12-150">**Distribución**</span><span class="sxs-lookup"><span data-stu-id="80e12-150">**Distribution**</span></span>

-   <span data-ttu-id="80e12-151">En la página de condiciones de entrega, cree y mantenga las condiciones de la transferencia de artículos de vendedor a comprador.</span><span class="sxs-lookup"><span data-stu-id="80e12-151">On the Terms of delivery page, create and maintain the conditions for an item's transfer from seller to buyer.</span></span>
-   <span data-ttu-id="80e12-152">En la página de modos de entrega, cree y mantenga los métodos de transporte que se usan cuando un pedido se entrega del vendedor al comprador.</span><span class="sxs-lookup"><span data-stu-id="80e12-152">On the Modes of delivery page, create and maintain the methods of transport that are used when an order is delivered from the seller to the buyer.</span></span>
-   <span data-ttu-id="80e12-153">En la página de códigos de destino, cree y mantenga los identificadores y las descripciones de los destinos de entrega.</span><span class="sxs-lookup"><span data-stu-id="80e12-153">On the Destination codes page, create and maintain identifiers and descriptions for delivery destinations.</span></span>

<span data-ttu-id="80e12-154">**Formularios**</span><span class="sxs-lookup"><span data-stu-id="80e12-154">**Forms**</span></span>

-   <span data-ttu-id="80e12-155">En la página de notas de formulario, cree el texto estándar que aparece en varias páginas.</span><span class="sxs-lookup"><span data-stu-id="80e12-155">On the Form notes page, create the standard text that appears on various pages.</span></span>
-   <span data-ttu-id="80e12-156">En la página de parámetros de ordenación del formulario, configure el orden de clasificación para solicitudes, listas de recepciones, albaranes y facturas.</span><span class="sxs-lookup"><span data-stu-id="80e12-156">On the Form sorting parameters page, set up the sorting order for requisitions, receipt lists, packing slips, and invoices.</span></span>
-   <span data-ttu-id="80e12-157">En función de la configuración de la gestión de impresión página, configure la información de la gestión de impresión para originales y copias de páginas.</span><span class="sxs-lookup"><span data-stu-id="80e12-157">On the Print management setup page, set up print management information for originals and copies of pages.</span></span>

<span data-ttu-id="80e12-158">**Pagos**</span><span class="sxs-lookup"><span data-stu-id="80e12-158">**Payments**</span></span>

-   <span data-ttu-id="80e12-159">En la página, configure y gestione las condiciones para obtener descuentos por pronto pago.</span><span class="sxs-lookup"><span data-stu-id="80e12-159">On the Cash discounts page, set up and manage the terms for obtaining cash discounts.</span></span> <span data-ttu-id="80e12-160">Los códigos de descuento por pronto pago se vinculan a los proveedores y se aplican a los pedidos de compra.</span><span class="sxs-lookup"><span data-stu-id="80e12-160">The cash discount codes are linked to vendors and are applied to purchase orders.</span></span>
-   <span data-ttu-id="80e12-161">En la página de multivencimientos, configure los multivencimientos que se usan para gestionar los pagos de plazo a los proveedores.</span><span class="sxs-lookup"><span data-stu-id="80e12-161">On the Payment schedules page, set up the payment schedules that are used to manage installment payments to vendors.</span></span>
-   <span data-ttu-id="80e12-162">En la página de días de pago, defina los días de pago que se utilizan para calcular las fechas de vencimiento y especificar los días de pago para un día concreto de la semana o del mes.</span><span class="sxs-lookup"><span data-stu-id="80e12-162">On the Payment days page, define the payment days that are used to calculate due dates, and specify payment days for a specific day of the week or month.</span></span>
-   <span data-ttu-id="80e12-163">En la página de cuota de pago, cree y mantenga las cuotas de pago asociadas con los proveedores.</span><span class="sxs-lookup"><span data-stu-id="80e12-163">On the Payment fee page, create and maintain the payment fees that are associated with vendors.</span></span>
-   <span data-ttu-id="80e12-164">En la página de instrucción de pago, cree y mantenga las instrucciones de pago.</span><span class="sxs-lookup"><span data-stu-id="80e12-164">On the Payment instruction page, create and maintain payment instructions.</span></span>

<span data-ttu-id="80e12-165">**Estadísticas**</span><span class="sxs-lookup"><span data-stu-id="80e12-165">**Statistics**</span></span>

-   <span data-ttu-id="80e12-166">En la página de definiciones de período de vencimiento, configure los intervalos definidos por el usuario que se usan para analizar la distribución de vencimiento de las cuentas de proveedor.</span><span class="sxs-lookup"><span data-stu-id="80e12-166">On the Aging period definitions page, set up user-defined intervals that are used to analyze the maturity distribution of vendor accounts.</span></span>
-   <span data-ttu-id="80e12-167">En la página de línea de negocio, cree los códigos de línea de negocio (LOB) que se asignan a los proveedores.</span><span class="sxs-lookup"><span data-stu-id="80e12-167">On the Line of business page, create the line of business (LOB) codes that are assigned to vendors.</span></span>

<span data-ttu-id="80e12-168">**IRPF**</span><span class="sxs-lookup"><span data-stu-id="80e12-168">**Tax 1099**</span></span>

-   <span data-ttu-id="80e12-169">En la página de **campos de IRPF**, compruebe y actualice los importes mínimos que se deben notificar a la agencia tributaria en función de los últimos requisitos fiscales.</span><span class="sxs-lookup"><span data-stu-id="80e12-169">On the **1099 fields** page, verify and update the minimum amounts that must be reported to the Internal Revenue Service (IRS), based on the latest IRS requirements.</span></span>

## <a name="optional-setup-for-other-modules"></a><span data-ttu-id="80e12-170">**Configuración opcional para otros módulos**</span><span class="sxs-lookup"><span data-stu-id="80e12-170">**Optional setup for other modules**</span></span>
<span data-ttu-id="80e12-171">**Administración de la organización**</span><span class="sxs-lookup"><span data-stu-id="80e12-171">**Organization administration**</span></span>

-   <span data-ttu-id="80e12-172">En la página de secuencias numéricas, configure los grupos de secuencias numéricas para los números de factura.</span><span class="sxs-lookup"><span data-stu-id="80e12-172">On the Number sequences page, set up number sequence groups for invoice numbers.</span></span>
-   <span data-ttu-id="80e12-173">En las siguientes páginas, configure la información de dirección:</span><span class="sxs-lookup"><span data-stu-id="80e12-173">On the following pages, set up address information:</span></span>
    -   <span data-ttu-id="80e12-174">Configuración de dirección</span><span class="sxs-lookup"><span data-stu-id="80e12-174">Address setup</span></span>
    -   <span data-ttu-id="80e12-175">Códigos NAF</span><span class="sxs-lookup"><span data-stu-id="80e12-175">NAF codes</span></span>
    -   <span data-ttu-id="80e12-176">Importar códigos postales</span><span class="sxs-lookup"><span data-stu-id="80e12-176">Import ZIP/postal codes</span></span>

<span data-ttu-id="80e12-177">**Contabilidad general**</span><span class="sxs-lookup"><span data-stu-id="80e12-177">**General ledger**</span></span>

-   <span data-ttu-id="80e12-178">En la página, configure las dimensiones financieras.</span><span class="sxs-lookup"><span data-stu-id="80e12-178">On the Financial dimensions page, set up financial dimensions.</span></span>
-   <span data-ttu-id="80e12-179">En las páginas siguientes, configure la información de impuestos:</span><span class="sxs-lookup"><span data-stu-id="80e12-179">On the following pages, set up tax information:</span></span>
    -   <span data-ttu-id="80e12-180">Códigos de impuestos</span><span class="sxs-lookup"><span data-stu-id="80e12-180">Sales tax codes</span></span>
    -   <span data-ttu-id="80e12-181">Grupos de impuestos</span><span class="sxs-lookup"><span data-stu-id="80e12-181">Sales tax groups</span></span>
    -   <span data-ttu-id="80e12-182">Grupos de impuestos de artículos</span><span class="sxs-lookup"><span data-stu-id="80e12-182">Item sales tax groups</span></span>
    -   <span data-ttu-id="80e12-183">Grupo de cuentas</span><span class="sxs-lookup"><span data-stu-id="80e12-183">Account group</span></span>
    -   <span data-ttu-id="80e12-184">Códigos de exención de impuestos</span><span class="sxs-lookup"><span data-stu-id="80e12-184">Sales tax exempt codes</span></span>
    -   <span data-ttu-id="80e12-185">Jurisdicciones de impuestos</span><span class="sxs-lookup"><span data-stu-id="80e12-185">Sales tax jurisdictions</span></span>
    -   <span data-ttu-id="80e12-186">Autoridades fiscales</span><span class="sxs-lookup"><span data-stu-id="80e12-186">Sales tax authorities</span></span>
    -   <span data-ttu-id="80e12-187">Períodos de liquidación de impuestos</span><span class="sxs-lookup"><span data-stu-id="80e12-187">Sales tax settlement periods</span></span>

<span data-ttu-id="80e12-188">**Gestión de efectivo y bancos**</span><span class="sxs-lookup"><span data-stu-id="80e12-188">**Cash and bank management**</span></span>

-   <span data-ttu-id="80e12-189">En la página de códigos de propósito de pago, configure el código de propósito del banco central.</span><span class="sxs-lookup"><span data-stu-id="80e12-189">On the Payment purpose codes page, set up the Central Bank purpose code.</span></span>





