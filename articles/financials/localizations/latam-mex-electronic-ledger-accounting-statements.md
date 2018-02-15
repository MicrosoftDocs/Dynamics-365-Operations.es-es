---
title: "Extractos electrónicos de cuenta contable"
description: "Este artículo explica cómo configurar y generar la versión 1.1 de los archivos XML de contabilidad general que todas las empresas de México debe presentar a las autoridades fiscales mexicanas (SAT) de manera mensual."
author: sndray
manager: AnnBe
ms.date: 12/06/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: ERSolutionTable, LedgerConsolidateAccountGroup, LedgerJournalTable, LedgerJournalTransVendInvoice, LedgerParameters, MainAccount, MainAccountConsolidateAccount, VendEditInvoice, VendPaymMode, VendTransInvoicePool
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.custom: 265314
ms.assetid: b4a95c26-a49d-4a1d-bf70-90f457df2ddf
ms.search.region: Mexico
ms.author: sndray
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 46e2f11e13bce74f36363c60d749196cbf2ee6b5
ms.openlocfilehash: 67d300bf9dcf08864b652e0e92d45b0c0dcc0ca6
ms.contentlocale: es-es
ms.lasthandoff: 01/03/2018

---

# <a name="electronic-ledger-accounting-statements"></a><span data-ttu-id="4dfc1-103">Extractos electrónicos de cuenta contable</span><span class="sxs-lookup"><span data-stu-id="4dfc1-103">Electronic ledger accounting statements</span></span>

[!include[banner](../includes/banner.md)]


<span data-ttu-id="4dfc1-104">Este artículo explica cómo configurar y generar la versión 1.1 de los archivos XML de contabilidad general que todas las empresas de México debe presentar a las autoridades fiscales mexicanas (SAT) de manera mensual.</span><span class="sxs-lookup"><span data-stu-id="4dfc1-104">This article explains how to set up and generate the general ledger XML files version 1.1 that all companies in Mexico are required to report to the Mexican tax authorities (SAT) on a monthly basis.</span></span>

<span data-ttu-id="4dfc1-105">Todas las empresas de México deben informar de los extractos de cuenta contable a las autoridades fiscales mexicanas (Servicio de Administración Tributaria \[SAT\]) todos los meses.</span><span class="sxs-lookup"><span data-stu-id="4dfc1-105">All companies in Mexico are required to report ledger accounting statements to the Mexican tax authorities (Servicio de Administración Tributaria \[SAT\]) every month.</span></span> <span data-ttu-id="4dfc1-106">El anexo 24 de la Resolución de Diversos Impuestos para 2015 requiere que envíe la versión 1.1 de los archivos XML de contabilidad general.</span><span class="sxs-lookup"><span data-stu-id="4dfc1-106">Annex 24 of Miscellaneous Tax Resolution for 2015 requires that you submit general ledger XML files version 1.1.</span></span> <span data-ttu-id="4dfc1-107">Puede generar los siguientes archivos XML por empresa:</span><span class="sxs-lookup"><span data-stu-id="4dfc1-107">You can generate the following XML files per company:</span></span>

-   <span data-ttu-id="4dfc1-108">Plan contable</span><span class="sxs-lookup"><span data-stu-id="4dfc1-108">Chart of account</span></span>
-   <span data-ttu-id="4dfc1-109">Saldo de comprobación mensual</span><span class="sxs-lookup"><span data-stu-id="4dfc1-109">Monthly Trial Balance</span></span>
-   <span data-ttu-id="4dfc1-110">Transacciones de diario, junto con las transacciones de subcontabilidad relacionadas (Comprobante Fiscal Digital a través de Internet \[CFDI\], Comprobante Fiscal Digital \[CFD\] y otras operaciones)</span><span class="sxs-lookup"><span data-stu-id="4dfc1-110">Journal transactions, together with the related subledger transactions (Comprobante Fiscal Digital a través de Internet \[CFDI\], Comprobante Fiscal Digital \[CFD\], and other operations)</span></span>
-   <span data-ttu-id="4dfc1-111">Cuenta contable auxiliar</span><span class="sxs-lookup"><span data-stu-id="4dfc1-111">Auxiliary ledger account</span></span>

<span data-ttu-id="4dfc1-112">Esta función solo está disponible cuando el país o la región de la empresa se define como MEX.</span><span class="sxs-lookup"><span data-stu-id="4dfc1-112">This functionality is available only when the country/region of the company is defined as MEX.</span></span> 
> [!NOTE]
>  <span data-ttu-id="4dfc1-113">El gobierno también requiere un archivo XML auxiliar adicional (folios) que detalla todos los documentos fiscales (CFDI, CFD y otros).</span><span class="sxs-lookup"><span data-stu-id="4dfc1-113">The government also requires an additional auxiliary XML file (folios) that details all fiscal documents (CFDI, CFD, and others).</span></span> <span data-ttu-id="4dfc1-114">Este archivo no se incluye en la característica actual, puesto que esta información se incluye en el archivo XML Transacciones de diario, como se especifica en el Capítulo 2.8, sección 2.8.1.3 de la Resolución de Diversos Impuestos para 2015 (segunda sección) del 30 de diciembre de 2014.</span><span class="sxs-lookup"><span data-stu-id="4dfc1-114">This file isn't included in the current feature, because this information is included in the Journal transactions XML file, as specified in Chapter 2.8, section 2.8.1.3 of the Miscellaneous Tax Resolution for 2015 (Second section) of December 30, 2014.</span></span> <span data-ttu-id="4dfc1-115">Para obtener más información, consulte <http://www.sat.gob.mx/fichas_tematicas/buzon_tributario/Documents/extracto_reglas.pdf>.</span><span class="sxs-lookup"><span data-stu-id="4dfc1-115">For more information, see <http://www.sat.gob.mx/fichas_tematicas/buzon_tributario/Documents/extracto_reglas.pdf>.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="4dfc1-116">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="4dfc1-116">Prerequisites</span></span>
<span data-ttu-id="4dfc1-117">El siguiente proceso muestra los requisitos previos que se deben implementar antes de comenzar a generar los archivos XML que el SAT requiere.</span><span class="sxs-lookup"><span data-stu-id="4dfc1-117">The following process lists the prerequisites that must be in place before you start to generate the XML files that SAT requires.</span></span> <span data-ttu-id="4dfc1-118">Los parámetros determinan la manera en que se exponen los datos en los archivos XML y se requieren todos ellos.</span><span class="sxs-lookup"><span data-stu-id="4dfc1-118">Parameters determine how the data will be exposed in the XML files, and all of them are required.</span></span> <span data-ttu-id="4dfc1-119">Los parámetros que faltan pueden provocar incoherencias o validaciones incorrectas en la herramienta de validación del gobierno.</span><span class="sxs-lookup"><span data-stu-id="4dfc1-119">Missing parameters can cause inconsistencies or incorrect validations in the government validation tool.</span></span>

1.  <span data-ttu-id="4dfc1-120">Configurar parámetros de cuenta principal.</span><span class="sxs-lookup"><span data-stu-id="4dfc1-120">Set up main account parameters.</span></span>
2.  <span data-ttu-id="4dfc1-121">Configurar una cuenta\_principal para identificar el nivel de cuenta.</span><span class="sxs-lookup"><span data-stu-id="4dfc1-121">Set up a Parent\_Account to identify the level of account.</span></span>
3.  <span data-ttu-id="4dfc1-122">Configurar cuentas totales en todos los niveles.</span><span class="sxs-lookup"><span data-stu-id="4dfc1-122">Set up total accounts in all levels.</span></span>
4.  <span data-ttu-id="4dfc1-123">Configuración de un grupo de cuentas SAT.</span><span class="sxs-lookup"><span data-stu-id="4dfc1-123">Set up SAT account group.</span></span>
5.  <span data-ttu-id="4dfc1-124">Crear un grupo de cuentas de consolidación para SAT.</span><span class="sxs-lookup"><span data-stu-id="4dfc1-124">Create consolidation account group for SAT.</span></span>
6.  <span data-ttu-id="4dfc1-125">Asignar cuenta principal a cuentas de nivel y de grupo SAT.</span><span class="sxs-lookup"><span data-stu-id="4dfc1-125">Assign main account to SAT group and level accounts.</span></span>
7.  <span data-ttu-id="4dfc1-126">Configuración de métodos de pago y cuentas bancarias.</span><span class="sxs-lookup"><span data-stu-id="4dfc1-126">Set up Method of payments and Bank accounts.</span></span>
8.  <span data-ttu-id="4dfc1-127">Asignación de método de pago SAT.</span><span class="sxs-lookup"><span data-stu-id="4dfc1-127">Assign SAT method of payments.</span></span>
9.  <span data-ttu-id="4dfc1-128">Asigne código de banco SAT en el campo número de ruta.</span><span class="sxs-lookup"><span data-stu-id="4dfc1-128">Assign SAT bank code in routing number field.</span></span>

 

### <a name="chart-of-accounts"></a><span data-ttu-id="4dfc1-129">Plan contable</span><span class="sxs-lookup"><span data-stu-id="4dfc1-129">Chart of accounts</span></span>

<span data-ttu-id="4dfc1-130">Por requisitos del gobierno, el archivo XML Plan contable debe incluir información específica que debe configurar por adelantado para evitar incoherencias cuando se genera y se valida el archivo XML.</span><span class="sxs-lookup"><span data-stu-id="4dfc1-130">Per government requirements, the Chart of account XML file must include specific information that you must configure in advance to prevent inconsistencies when the XML file is generated and validated.</span></span> <span data-ttu-id="4dfc1-131">Establezca los siguientes parámetros para configurar esta información:</span><span class="sxs-lookup"><span data-stu-id="4dfc1-131">Set the following parameters to configure this information:</span></span>

-   <span data-ttu-id="4dfc1-132">**Cuenta principal primaria:** la etiqueta **&lt;SubCtaDe&gt;** del archivo XML se usa para especificar la cuenta del nivel anterior.</span><span class="sxs-lookup"><span data-stu-id="4dfc1-132">**Parent main account:** The **&lt;SubCtaDe&gt;** tag in the XML file is used to specify the account of the previous level.</span></span> <span data-ttu-id="4dfc1-133">En este caso, usamos un campo de país o región de **Cuenta principal** en la configuración del plan de cuentas.</span><span class="sxs-lookup"><span data-stu-id="4dfc1-133">In this case, we use a **Parent account** country/region field in the configuration of the chart of accounts.</span></span>
-   <span data-ttu-id="4dfc1-134">**Nivel de cuenta:** la etiqueta **&lt;Nivel&gt;** del archivo XML se usa para especificar el nivel del grupo de cuentas del gobierno.</span><span class="sxs-lookup"><span data-stu-id="4dfc1-134">**Account level:** The **&lt;Nivel&gt;** tag in the XML file is used to specify the level of the government account group.</span></span> <span data-ttu-id="4dfc1-135">Localizamos la funcionalidad del campo **Grupo de cuentas de consolidación** en **Cuentas de consolidación adicionales** para especificar el nivel del grupo de cuentas del gobierno.</span><span class="sxs-lookup"><span data-stu-id="4dfc1-135">We localized the functionality of the **Consolidation account group** field under **Additional consolidation accounts** to specify the level of the government account group.</span></span>
-   <span data-ttu-id="4dfc1-136">**Indicador de débito o crédito:** la etiqueta **&lt;Natur&gt;** del archivo XML se usa para especificar el indicador de débito y crédito de la cuenta principal.</span><span class="sxs-lookup"><span data-stu-id="4dfc1-136">**Debit and Credit indicator:** The **&lt;Natur&gt;** tag in the XML file is used to specify the debit and credit indicator of the main account.</span></span> <span data-ttu-id="4dfc1-137">Se han definido las siguientes reglas:</span><span class="sxs-lookup"><span data-stu-id="4dfc1-137">The following rules have been defined:</span></span>
    -   <span data-ttu-id="4dfc1-138">**Débito D**</span><span class="sxs-lookup"><span data-stu-id="4dfc1-138">**D-Debit**</span></span>
        -   <span data-ttu-id="4dfc1-139">Tipo de cuenta principal = Coste, Activo</span><span class="sxs-lookup"><span data-stu-id="4dfc1-139">Main Account type = Cost, Asset</span></span>
        -   <span data-ttu-id="4dfc1-140">Tipo de cuenta principal: Si Pérdidas/ganancias y Propuesta Debe/Haber = Débito</span><span class="sxs-lookup"><span data-stu-id="4dfc1-140">Main Account type:  If Profit & Loss and DB/CR proposal = Debit</span></span>
        -   <span data-ttu-id="4dfc1-141">Tipo de cuenta principal: Si Saldo y Propuesta Debe/Haber = Débito</span><span class="sxs-lookup"><span data-stu-id="4dfc1-141">Main Account type: If Balance and DB/CR proposal = Debit</span></span>
        -   <span data-ttu-id="4dfc1-142">Tipo de cuenta principal: Si Pérdidas/ganancias y Propuesta Debe/Haber = En blanco</span><span class="sxs-lookup"><span data-stu-id="4dfc1-142">Main Account type: If Profit & Loss and DB/CR proposal = Blank</span></span>
        -   <span data-ttu-id="4dfc1-143">Tipo de cuenta principal: Si Saldo y Propuesta Debe/Haber = En blanco</span><span class="sxs-lookup"><span data-stu-id="4dfc1-143">Main Account type: If Balance and DB/CR proposal = Blank</span></span>
    -    <span data-ttu-id="4dfc1-144">**Crédito A**</span><span class="sxs-lookup"><span data-stu-id="4dfc1-144">**A-Credit**</span></span>
        -   <span data-ttu-id="4dfc1-145">Tipo de cuenta: Ingresos, Pasivo</span><span class="sxs-lookup"><span data-stu-id="4dfc1-145">Account type : Revenue, Liability</span></span>
        -   <span data-ttu-id="4dfc1-146">Tipo de cuenta AX: Si Pérdidas/ganancias y Propuesta Debe/Haber = Crédito</span><span class="sxs-lookup"><span data-stu-id="4dfc1-146">Account type AX: If Profit & Loss and DB/CR proposal = Credit</span></span>
        -   <span data-ttu-id="4dfc1-147">Tipo de cuenta AX: Si Saldo y Propuesta Debe/Haber = Crédito</span><span class="sxs-lookup"><span data-stu-id="4dfc1-147">Account type AX: If Balance and DB/CR proposal = Credit</span></span>
-   <span data-ttu-id="4dfc1-148">**Importe de totales en todos los niveles:** Configure el valor de **Totales** en el plan de cuentas para habilitar la generación de un archivo XML Saldo de comprobación mensual que incluye los importes de los totales relacionados en todos los niveles de la jerarquía.</span><span class="sxs-lookup"><span data-stu-id="4dfc1-148">**Totals amount in all levels:** Configure the **Totals** value in the chart of accounts to enable generation of a Monthly Trial Balance XML file that includes the related totals amounts in all levels of the hierarchy.</span></span>

### <a name="sat-account-group"></a><span data-ttu-id="4dfc1-149">Grupo de cuentas SAT</span><span class="sxs-lookup"><span data-stu-id="4dfc1-149">SAT account group</span></span>

<span data-ttu-id="4dfc1-150">El archivo XML Gráfico del plan contable incluye una etiqueta **&lt;CodAgrup&gt;** que se usa para especificar el grupo de cuentas del gobierno relacionado para la cuenta notificada.</span><span class="sxs-lookup"><span data-stu-id="4dfc1-150">The Chart of account XML file includes a **&lt;CodAgrup&gt;** tag that is used to specify the related government account group for the reported account.</span></span> <span data-ttu-id="4dfc1-151">El gobierno ha publicado una tabla en el portal gubernamental.</span><span class="sxs-lookup"><span data-stu-id="4dfc1-151">The government has published a table on the government portal.</span></span> <span data-ttu-id="4dfc1-152">Para cumplir este requisito, debe usar la funcionalidad de Grupos de cuentas de consolidación, que le permite configurar la asignación entre el plan de cuentas de la empresa y el grupo de la cuenta del gobierno.</span><span class="sxs-lookup"><span data-stu-id="4dfc1-152">To meet this requirement, you must use the Consolidation account groups functionality, which lets you configure the mapping between your company chart of account and the government account group.</span></span> <span data-ttu-id="4dfc1-153">A continuación, cuando genere el informe, se le solicitará que indique qué grupo de cuentas consolidadas se usa para especificar la agrupación del gobierno.</span><span class="sxs-lookup"><span data-stu-id="4dfc1-153">Then, when you generate the report, you will be asked to indicate which consolidated account group is used to specify the government grouping.</span></span>

### <a name="payment-methods"></a><span data-ttu-id="4dfc1-154">Métodos de pago</span><span class="sxs-lookup"><span data-stu-id="4dfc1-154">Payment methods</span></span>

<span data-ttu-id="4dfc1-155">En situaciones específicas, el gobierno puede solicitar que entregue un archivo XML Transacciones de diario que detalle todas las transacciones de contabilidad y el documento que las originó.</span><span class="sxs-lookup"><span data-stu-id="4dfc1-155">In specific situations, the government might request that you deliver a Journal transaction XML file that details all accounting transactions and the document that originated them.</span></span> <span data-ttu-id="4dfc1-156">Cuando estas transacciones estén relacionadas con pagos de proveedores, debe especificar el tipo de pago en el nodo **&lt;OtrMetododePago&gt;** y el atributo **&lt;MetPagPol&gt;** mediante una tabla específica que se publica por el gobierno.</span><span class="sxs-lookup"><span data-stu-id="4dfc1-156">When these transactions are related to vendors payments, you must specify the type of payment in the **&lt;OtrMetododePago&gt;** node and the **&lt;MetPagPol&gt;** attribute by using a specific table that is published by the government.</span></span> <span data-ttu-id="4dfc1-157">Haga clic en **Proveedores** &gt; **Configuración de pagos** &gt; **Formas de pago** y asigne el método de pago SAT al método de pago de la empresa.</span><span class="sxs-lookup"><span data-stu-id="4dfc1-157">Click **Accounts payable** &gt; **Payment setup** &gt; **Methods of payment**, and assign the SAT payment method to the company's method of payment.</span></span>

### <a name="bank-transactions"></a><span data-ttu-id="4dfc1-158">Transacciones bancarias</span><span class="sxs-lookup"><span data-stu-id="4dfc1-158">Bank transactions</span></span>

<span data-ttu-id="4dfc1-159">El archivo XML Transacciones de diario debe incluir todas las transacciones de transferencias bancarias que se registran en la contabilidad general donde se requiere alguna información adicional en un nodo específico **&lt;Transferencias&gt;** y se requieren sus atributos **&lt;BancoOriNal&gt;** y **&lt;BancoDestNal&gt;** para informar del código de banco gubernamental.</span><span class="sxs-lookup"><span data-stu-id="4dfc1-159">The Journal transaction XML file must include all bank transfer transactions that are posted to the general ledger where some additional information is required in a specific node **&lt;Transferencias&gt;** and their attributes **&lt;BancoOriNal&gt;** and **&lt;BancoDestNal&gt;** is required to inform the government bank code.</span></span> <span data-ttu-id="4dfc1-160">Haga clic en **Gestión de efectivo y bancos** &gt; **Cuentas bancarias** y use el campo **Número de ruta** para configurar esta información.</span><span class="sxs-lookup"><span data-stu-id="4dfc1-160">Click **Cash and bank management** &gt; **Bank accounts**, and use the **Routing number** field to set up this information.</span></span>

### <a name="invoice-identification"></a><span data-ttu-id="4dfc1-161">Identificación de factura</span><span class="sxs-lookup"><span data-stu-id="4dfc1-161">Invoice identification</span></span>

<span data-ttu-id="4dfc1-162">El archivo XML Transacciones de diario también requiere que identifique el número de factura cuando se emita y se reciba una factura.</span><span class="sxs-lookup"><span data-stu-id="4dfc1-162">The Journal transaction XML file also requires that you identify the invoice number when an invoice is issued and received.</span></span> <span data-ttu-id="4dfc1-163">Según la legislación mexicana, este número de factura se puede representar de distintas maneras, en función de cómo se haya entregado la factura:</span><span class="sxs-lookup"><span data-stu-id="4dfc1-163">Per Mexican legislation, this invoice number can be represented in various ways, depending on how the invoice was delivered:</span></span>

-   <span data-ttu-id="4dfc1-164">Factura normal (no electrónica).</span><span class="sxs-lookup"><span data-stu-id="4dfc1-164">Regular invoice (non-electronic).</span></span> <span data-ttu-id="4dfc1-165">Debe incluir la **Serie** y el **Número de factura**.</span><span class="sxs-lookup"><span data-stu-id="4dfc1-165">You must include the **Series** and **Invoice number**.</span></span>
-   <span data-ttu-id="4dfc1-166">CFD: Debe incluir el **UUID** de un CFD de factura electrónica.</span><span class="sxs-lookup"><span data-stu-id="4dfc1-166">CFD: You must include the **UUID** of an electronic invoice CFD.</span></span>
-   <span data-ttu-id="4dfc1-167">CFDI: Debe incluir el **UUID** de un CFD de factura electrónica.</span><span class="sxs-lookup"><span data-stu-id="4dfc1-167">CFDI:  You must include the **UUID** of an electronic invoice CFD.</span></span>

<span data-ttu-id="4dfc1-168">Los usuarios pueden incluir ahora esta información en las transacciones que se generan de las siguientes áreas:</span><span class="sxs-lookup"><span data-stu-id="4dfc1-168">Users can now include this information in transactions that are generated from the following areas:</span></span>

-   <span data-ttu-id="4dfc1-169">Factura de compra</span><span class="sxs-lookup"><span data-stu-id="4dfc1-169">Purchase invoice</span></span>
-   <span data-ttu-id="4dfc1-170">Factura de proveedor (pedido que no es de compra)</span><span class="sxs-lookup"><span data-stu-id="4dfc1-170">Vendor invoice (non–purchase order)</span></span>
-   <span data-ttu-id="4dfc1-171">Registro de facturas</span><span class="sxs-lookup"><span data-stu-id="4dfc1-171">Invoice register</span></span>
-   <span data-ttu-id="4dfc1-172">Diario de facturas</span><span class="sxs-lookup"><span data-stu-id="4dfc1-172">Invoice journal</span></span>
-   <span data-ttu-id="4dfc1-173">Aprobación de factura</span><span class="sxs-lookup"><span data-stu-id="4dfc1-173">Invoice approval</span></span>
-   <span data-ttu-id="4dfc1-174">Grupo de facturas</span><span class="sxs-lookup"><span data-stu-id="4dfc1-174">Invoice pool</span></span>

### <a name="electronic-reporting"></a><span data-ttu-id="4dfc1-175">Informes electrónicos</span><span class="sxs-lookup"><span data-stu-id="4dfc1-175">Electronic reporting</span></span>

<span data-ttu-id="4dfc1-176">Esta característica se basa en la configuración de informes electrónicos (ER), donde cada formato de archivo XML se define con el diseñador de modelos y formatos para informes electrónicos.</span><span class="sxs-lookup"><span data-stu-id="4dfc1-176">This feature is based on Electronic reporting configuration (ER), where each XML file format is defined by using the model and format designer for electronic reporting.</span></span> <span data-ttu-id="4dfc1-177">Use el tipo de configuración de repositorio **Recursos de AX** para importar estas configuraciones en la empresa actual y habilitar la generación de archivos XML.</span><span class="sxs-lookup"><span data-stu-id="4dfc1-177">Use the **AX resources** repository configuration type to import these configurations into the current company and enable the generation of XML files.</span></span> <span data-ttu-id="4dfc1-178">Haga clic en **Administración de la organización** &gt; **Espacios de trabajo** &gt; **Informes electrónicos** &gt; **Repositorios**.</span><span class="sxs-lookup"><span data-stu-id="4dfc1-178">Click **Organization administration** &gt; **Workspaces** &gt; **Electronic reporting** &gt; **Repositories**.</span></span>

<span data-ttu-id="4dfc1-179">Debe cargar los siguientes modelos y formatos de repositorio:</span><span class="sxs-lookup"><span data-stu-id="4dfc1-179">You must upload the following repository models and formats:</span></span>

1.  <span data-ttu-id="4dfc1-180">Modelo electrónico de cuenta contable MX</span><span class="sxs-lookup"><span data-stu-id="4dfc1-180">Electronic ledger accounting model MX</span></span>
2.  <span data-ttu-id="4dfc1-181">Libro mayor auxiliar XML MX (formato)</span><span class="sxs-lookup"><span data-stu-id="4dfc1-181">Auxiliary Ledger XML MX (format)</span></span>
3.  <span data-ttu-id="4dfc1-182">Plan de cuentas XML MX (formato)</span><span class="sxs-lookup"><span data-stu-id="4dfc1-182">Chart of Account XML MX (format)</span></span>
4.  <span data-ttu-id="4dfc1-183">Diario XML MX (formato)</span><span class="sxs-lookup"><span data-stu-id="4dfc1-183">Journal XML MX (format)</span></span>
5.  <span data-ttu-id="4dfc1-184">Saldo de comprobación XML MX (formato)</span><span class="sxs-lookup"><span data-stu-id="4dfc1-184">Trial Balance XML MX (format)</span></span>

<span data-ttu-id="4dfc1-185">Después de que el depósito esté disponible en el entorno, debe identificar estos formatos en los parámetros de contabilidad general.</span><span class="sxs-lookup"><span data-stu-id="4dfc1-185">After the repository is available in your environment, you must identify these formats in the general ledger parameters.</span></span> <span data-ttu-id="4dfc1-186">Haga clic en los parámetros **Contabilidad general** &gt; **Configuración de contabilidad** &gt; **Contabilidad general** y, a continuación, en el grupo de campos **Asignación de informes electrónicos**, seleccione el formato que desea utilizar para generar los archivos XML.</span><span class="sxs-lookup"><span data-stu-id="4dfc1-186">Click **General ledger** &gt; **Ledger setup** &gt; **General ledger parameters**, and then, in the **Electronic reporting mapping** field group, select the format to use to generate the XML files.</span></span>

## <a name="generate-electronic-ledger-accounting-files"></a><span data-ttu-id="4dfc1-187">Generar archivos electrónicos de cuenta contable</span><span class="sxs-lookup"><span data-stu-id="4dfc1-187">Generate electronic ledger accounting files</span></span>
<span data-ttu-id="4dfc1-188">Haga clic en **Contabilidad general** &gt; **Consulta e informes** &gt; **Informes de contabilidad** &gt; **Extracto electrónico de cuenta contable** para generar los archivos XML necesarios y descargarlos en el entorno.</span><span class="sxs-lookup"><span data-stu-id="4dfc1-188">Click **General ledger** &gt; **Inquire and reports** &gt; **Ledger reports** &gt; **Electronic ledger accounting statement** to generate the required XML files and download them to your environment.</span></span> <span data-ttu-id="4dfc1-189">La tabla siguiente describe los parámetros que debe establecer.</span><span class="sxs-lookup"><span data-stu-id="4dfc1-189">The following table describes the parameters that you must set.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><span data-ttu-id="4dfc1-190"><strong>Grupo de cuentas de consolidación de SAT</strong></span><span class="sxs-lookup"><span data-stu-id="4dfc1-190"><strong>SAT consolidation account group</strong></span></span></td>
<td><span data-ttu-id="4dfc1-191">Seleccione el grupo de cuentas de consolidación que haya configurado anteriormente para identificar el grupo de cuentas SAT.</span><span class="sxs-lookup"><span data-stu-id="4dfc1-191">Select the consolidation account group that you previously configured to identify the SAT account group.</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="4dfc1-192"><strong>Período</strong></span><span class="sxs-lookup"><span data-stu-id="4dfc1-192"><strong>Period</strong></span></span></td>
<td><span data-ttu-id="4dfc1-193">Seleccione el período del informe.</span><span class="sxs-lookup"><span data-stu-id="4dfc1-193">Select the period for the report.</span></span> <span data-ttu-id="4dfc1-194">La fecha seleccionada incluirá todas las transacciones de contabilidad general para el mes seleccionado.</span><span class="sxs-lookup"><span data-stu-id="4dfc1-194">The selected date will include all general ledger transactions for the selected month.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="4dfc1-195"><strong>Transacciones de cierre</strong></span><span class="sxs-lookup"><span data-stu-id="4dfc1-195"><strong>Closing transactions</strong></span></span></td>
<td><span data-ttu-id="4dfc1-196">Este control deslizante indica si las transacciones de cierre se deben incluir como transacciones en el archivo XML Saldo de comprobación mensual.</span><span class="sxs-lookup"><span data-stu-id="4dfc1-196">This slider indicates if the closing transactions should be included as transactions in the Monthly Trial Balance XML file.</span></span> <span data-ttu-id="4dfc1-197">Cambie este control deslizante a <strong>No</strong> para excluir las transacciones de cierre del archivo XML Saldo de comprobación mensual.</span><span class="sxs-lookup"><span data-stu-id="4dfc1-197">Switch this slider to <strong>No</strong> to exclude closing transactions from the Monthly Trial balance XML file.</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="4dfc1-198"><strong>Saldo de comprobación</strong></span><span class="sxs-lookup"><span data-stu-id="4dfc1-198"><strong>Trial Balance</strong></span></span></td>
<td><span data-ttu-id="4dfc1-199">Active esta casilla para generar los archivos XML Plan de cuentas y Saldo de comprobación mensual para el período especificado.</span><span class="sxs-lookup"><span data-stu-id="4dfc1-199">Select this check box to generate the Chart of account and Monthly Trial Balance XML files for the specified period.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="4dfc1-200"><strong>Tipo de entrega</strong></span><span class="sxs-lookup"><span data-stu-id="4dfc1-200"><strong>Delivery type</strong></span></span></td>
<td><span data-ttu-id="4dfc1-201">Especifique el tipo de entrega:</span><span class="sxs-lookup"><span data-stu-id="4dfc1-201">Specify the type of delivery:</span></span>
<ul>
<li><span data-ttu-id="4dfc1-202">Normal</span><span class="sxs-lookup"><span data-stu-id="4dfc1-202">Normal</span></span></li>
<li><span data-ttu-id="4dfc1-203">Complementario</span><span class="sxs-lookup"><span data-stu-id="4dfc1-203">Complementary</span></span></li>
</ul></td>
</tr>
<tr class="even">
<td><span data-ttu-id="4dfc1-204"><strong>Fecha de actualización</strong></span><span class="sxs-lookup"><span data-stu-id="4dfc1-204"><strong>Update date</strong></span></span></td>
<td><span data-ttu-id="4dfc1-205">Especifique la fecha actualizada de una entrega complementaria.</span><span class="sxs-lookup"><span data-stu-id="4dfc1-205">Specify the updated date of a complementary delivery.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="4dfc1-206"><strong>Movimientos contables</strong></span><span class="sxs-lookup"><span data-stu-id="4dfc1-206"><strong>Ledger entries</strong></span></span></td>
<td><span data-ttu-id="4dfc1-207">Este control deslizante indica si el archivo XML Transacciones de diario se genera para el período especificado.</span><span class="sxs-lookup"><span data-stu-id="4dfc1-207">This slider indicates if the Journal transaction XML file is generated for the specified period.</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="4dfc1-208"><strong>Libro mayor auxiliar</strong></span><span class="sxs-lookup"><span data-stu-id="4dfc1-208"><strong>Auxiliary ledger</strong></span></span></td>
<td><span data-ttu-id="4dfc1-209">Este control deslizante indica si el archivo XML Libro mayor auxiliar se genera para el período especificado.</span><span class="sxs-lookup"><span data-stu-id="4dfc1-209">This slider indicates if the Auxiliary ledger XML file is generated for the specified period.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="4dfc1-210"><strong>Tipo de solicitud</strong></span><span class="sxs-lookup"><span data-stu-id="4dfc1-210"><strong>Request type</strong></span></span></td>
<td><span data-ttu-id="4dfc1-211">Seleccione esta opción para identificar el tipo de solicitud cuando el control deslizante <strong>Asientos contables</strong> o <strong>Libro mayor auxiliar</strong> está establecido en <strong>Sí</strong>.</span><span class="sxs-lookup"><span data-stu-id="4dfc1-211">Select this option to identify the type of request when the <strong>Ledger entries</strong> or <strong>Auxiliary ledger</strong> slider is set to <strong>Yes</strong>.</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="4dfc1-212"><strong>Número de pedido</strong></span><span class="sxs-lookup"><span data-stu-id="4dfc1-212"><strong>Order number</strong></span></span></td>
<td><span data-ttu-id="4dfc1-213">Especifique el número de pedido que se ha asignado por la autoridad fiscal del gobierno, si el tipo de solicitud es <strong>Control</strong> o <strong>Control obligatorio</strong>.</span><span class="sxs-lookup"><span data-stu-id="4dfc1-213">Enter the order number that was assigned by the government tax authority, if the request type is <strong>Control</strong> or <strong>Compulsive control</strong>.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="4dfc1-214"><strong>Número de proceso</strong></span><span class="sxs-lookup"><span data-stu-id="4dfc1-214"><strong>Process Number</strong></span></span></td>
<td><span data-ttu-id="4dfc1-215">Especifique el número de proceso que se ha asignado por la autoridad fiscal del gobierno, si el tipo de solicitud es <strong>Devolución</strong> o <strong>Compensación</strong>.</span><span class="sxs-lookup"><span data-stu-id="4dfc1-215">Enter the process number that was assigned by the government tax authority, if the request type is <strong>Return</strong> or <strong>Compensation</strong>.</span></span></td>
</tr>
</tbody>
</table>


## <a name="additional-resources"></a><span data-ttu-id="4dfc1-216">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="4dfc1-216">Additional resources</span></span>

- [<span data-ttu-id="4dfc1-217">Versión CFDI 3.3</span><span class="sxs-lookup"><span data-stu-id="4dfc1-217">CFDI Version 3.3</span></span>](latam-mex-cfdi-3-3.md)



