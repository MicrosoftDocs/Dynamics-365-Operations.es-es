---
title: Extractos electrónicos de cuenta contable
description: Este artículo explica cómo configurar y generar los archivos XML de contabilidad general que todas las empresas de México debe presentar a las autoridades fiscales mexicanas (SAT) de manera mensual.
author: sndray
manager: AnnBe
ms.date: 12/07/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ERSolutionTable, LedgerConsolidateAccountGroup, LedgerJournalTable, LedgerJournalTransVendInvoice, LedgerParameters, MainAccount, MainAccountConsolidateAccount, VendEditInvoice, VendPaymMode, VendTransInvoicePool
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: 265314
ms.assetid: b4a95c26-a49d-4a1d-bf70-90f457df2ddf
ms.search.region: Mexico
ms.author: sndray
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: fabd00786bb7644f1691212e42917defd6c6443b
ms.sourcegitcommit: 2460d0da812c45fce67a061386db52e0ae46b0f3
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/30/2019
ms.locfileid: "2250341"
---
# <a name="electronic-ledger-accounting-statements"></a><span data-ttu-id="52f4b-103">Extractos electrónicos de cuenta contable</span><span class="sxs-lookup"><span data-stu-id="52f4b-103">Electronic ledger accounting statements</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="52f4b-104">Este artículo explica cómo configurar y generar los archivos XML de contabilidad general que todas las empresas de México debe presentar a las autoridades fiscales mexicanas (SAT) de manera mensual.</span><span class="sxs-lookup"><span data-stu-id="52f4b-104">This article explains how to set up and generate the general ledger XML files that all companies in Mexico are required to report to the Mexican tax authorities (SAT) on a monthly basis.</span></span>

<span data-ttu-id="52f4b-105">Todas las empresas de México deben informar de los extractos de cuenta contable a las autoridades fiscales mexicanas (Servicio de Administración Tributaria \[SAT\]) todos los meses.</span><span class="sxs-lookup"><span data-stu-id="52f4b-105">All companies in Mexico are required to report ledger accounting statements to the Mexican tax authorities (Servicio de Administración Tributaria \[SAT\]) every month.</span></span> <span data-ttu-id="52f4b-106">El anexo 24 de la Resolución de Diversos Impuestos requiere que envíe los archivos XML de contabilidad general.</span><span class="sxs-lookup"><span data-stu-id="52f4b-106">Annex 24 of Miscellaneous Tax Resolution requires that you submit general ledger XML files.</span></span> <span data-ttu-id="52f4b-107">Puede generar los siguientes archivos XML por empresa:</span><span class="sxs-lookup"><span data-stu-id="52f4b-107">You can generate the following XML files per company:</span></span>

-   <span data-ttu-id="52f4b-108">Plan contable</span><span class="sxs-lookup"><span data-stu-id="52f4b-108">Chart of account</span></span>
-   <span data-ttu-id="52f4b-109">Saldo de comprobación mensual</span><span class="sxs-lookup"><span data-stu-id="52f4b-109">Monthly Trial Balance</span></span>
-   <span data-ttu-id="52f4b-110">Transacciones de diario, junto con las transacciones de subcontabilidad relacionadas (Comprobante Fiscal Digital a través de Internet \[CFDI\], Comprobante Fiscal Digital \[CFD\] y otras operaciones)</span><span class="sxs-lookup"><span data-stu-id="52f4b-110">Journal transactions, together with the related subledger transactions (Comprobante Fiscal Digital a través de Internet \[CFDI\], Comprobante Fiscal Digital \[CFD\], and other operations)</span></span>
-   <span data-ttu-id="52f4b-111">Cuenta contable auxiliar</span><span class="sxs-lookup"><span data-stu-id="52f4b-111">Auxiliary ledger account</span></span>

<span data-ttu-id="52f4b-112">Esta función solo está disponible cuando el país o la región de la empresa se define como MEX.</span><span class="sxs-lookup"><span data-stu-id="52f4b-112">This functionality is available only when the country/region of the company is defined as MEX.</span></span> 

## <a name="prerequisites"></a><span data-ttu-id="52f4b-113">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="52f4b-113">Prerequisites</span></span>
<span data-ttu-id="52f4b-114">El siguiente proceso muestra los requisitos previos que se deben implementar antes de comenzar a generar los archivos XML que el SAT requiere.</span><span class="sxs-lookup"><span data-stu-id="52f4b-114">The following process lists the prerequisites that must be in place before you start to generate the XML files that SAT requires.</span></span> <span data-ttu-id="52f4b-115">Los parámetros determinan la manera en que se exponen los datos en los archivos XML y se requieren todos ellos.</span><span class="sxs-lookup"><span data-stu-id="52f4b-115">Parameters determine how the data will be exposed in the XML files, and all of them are required.</span></span> <span data-ttu-id="52f4b-116">Los parámetros que faltan pueden provocar incoherencias o validaciones incorrectas en la herramienta de validación del gobierno.</span><span class="sxs-lookup"><span data-stu-id="52f4b-116">Missing parameters can cause inconsistencies or incorrect validations in the government validation tool.</span></span>

1.  <span data-ttu-id="52f4b-117">Configurar parámetros de cuenta principal.</span><span class="sxs-lookup"><span data-stu-id="52f4b-117">Set up main account parameters.</span></span>
2.  <span data-ttu-id="52f4b-118">Configurar una cuenta\_principal para identificar el nivel de cuenta.</span><span class="sxs-lookup"><span data-stu-id="52f4b-118">Set up a Parent\_Account to identify the level of account.</span></span>
3.  <span data-ttu-id="52f4b-119">Configurar cuentas totales en todos los niveles.</span><span class="sxs-lookup"><span data-stu-id="52f4b-119">Set up total accounts in all levels.</span></span>
4.  <span data-ttu-id="52f4b-120">Configuración de un grupo de cuentas SAT.</span><span class="sxs-lookup"><span data-stu-id="52f4b-120">Set up SAT account group.</span></span>
5.  <span data-ttu-id="52f4b-121">Crear un grupo de cuentas de consolidación para SAT.</span><span class="sxs-lookup"><span data-stu-id="52f4b-121">Create consolidation account group for SAT.</span></span>
6.  <span data-ttu-id="52f4b-122">Asignar cuenta principal a cuentas de nivel y de grupo SAT.</span><span class="sxs-lookup"><span data-stu-id="52f4b-122">Assign main account to SAT group and level accounts.</span></span>
7.  <span data-ttu-id="52f4b-123">Configuración de métodos de pago y cuentas bancarias.</span><span class="sxs-lookup"><span data-stu-id="52f4b-123">Set up Method of payments and Bank accounts.</span></span>
8.  <span data-ttu-id="52f4b-124">Asignación de método de pago SAT.</span><span class="sxs-lookup"><span data-stu-id="52f4b-124">Assign SAT method of payments.</span></span>
9.  <span data-ttu-id="52f4b-125">Asigne código de banco SAT en el campo número de ruta.</span><span class="sxs-lookup"><span data-stu-id="52f4b-125">Assign SAT bank code in routing number field.</span></span>



### <a name="chart-of-accounts"></a><span data-ttu-id="52f4b-126">Plan contable</span><span class="sxs-lookup"><span data-stu-id="52f4b-126">Chart of accounts</span></span>

<span data-ttu-id="52f4b-127">Por requisitos del gobierno, el archivo XML Plan contable debe incluir información específica que debe configurar por adelantado para evitar incoherencias cuando se genera y se valida el archivo XML.</span><span class="sxs-lookup"><span data-stu-id="52f4b-127">Per government requirements, the Chart of account XML file must include specific information that you must configure in advance to prevent inconsistencies when the XML file is generated and validated.</span></span> <span data-ttu-id="52f4b-128">Establezca los siguientes parámetros para configurar esta información:</span><span class="sxs-lookup"><span data-stu-id="52f4b-128">Set the following parameters to configure this information:</span></span>

- <span data-ttu-id="52f4b-129">**Cuenta principal primaria:** la etiqueta **&lt;SubCtaDe&gt;** del archivo XML se usa para especificar la cuenta del nivel anterior.</span><span class="sxs-lookup"><span data-stu-id="52f4b-129">**Parent main account:** The **&lt;SubCtaDe&gt;** tag in the XML file is used to specify the account of the previous level.</span></span> <span data-ttu-id="52f4b-130">En este caso, usamos un campo de país o región de **Cuenta principal** en la configuración del plan de cuentas.</span><span class="sxs-lookup"><span data-stu-id="52f4b-130">In this case, we use a **Parent account** country/region field in the configuration of the chart of accounts.</span></span>
- <span data-ttu-id="52f4b-131">**Nivel de cuenta:** la etiqueta **&lt;Nivel&gt;** del archivo XML se usa para especificar el nivel del grupo de cuentas del gobierno.</span><span class="sxs-lookup"><span data-stu-id="52f4b-131">**Account level:** The **&lt;Nivel&gt;** tag in the XML file is used to specify the level of the government account group.</span></span> <span data-ttu-id="52f4b-132">Localizamos la funcionalidad del campo **Grupo de cuentas de consolidación** en **Cuentas de consolidación adicionales** para especificar el nivel del grupo de cuentas del gobierno.</span><span class="sxs-lookup"><span data-stu-id="52f4b-132">We localized the functionality of the **Consolidation account group** field under **Additional consolidation accounts** to specify the level of the government account group.</span></span>
- <span data-ttu-id="52f4b-133">**Indicador de débito o crédito:** la etiqueta **&lt;Natur&gt;** del archivo XML se usa para especificar el indicador de débito y crédito de la cuenta principal.</span><span class="sxs-lookup"><span data-stu-id="52f4b-133">**Debit and Credit indicator:** The **&lt;Natur&gt;** tag in the XML file is used to specify the debit and credit indicator of the main account.</span></span> <span data-ttu-id="52f4b-134">Se han definido las siguientes reglas:</span><span class="sxs-lookup"><span data-stu-id="52f4b-134">The following rules have been defined:</span></span>
  - <span data-ttu-id="52f4b-135">**Débito D**</span><span class="sxs-lookup"><span data-stu-id="52f4b-135">**D-Debit**</span></span>
    -   <span data-ttu-id="52f4b-136">Tipo de cuenta principal = Coste, Activo</span><span class="sxs-lookup"><span data-stu-id="52f4b-136">Main Account type = Cost, Asset</span></span>
    -   <span data-ttu-id="52f4b-137">Tipo de cuenta principal: Si Pérdidas/ganancias y Propuesta Debe/Haber = Débito</span><span class="sxs-lookup"><span data-stu-id="52f4b-137">Main Account type:  If Profit & Loss and DB/CR proposal = Debit</span></span>
    -   <span data-ttu-id="52f4b-138">Tipo de cuenta principal: Si Saldo y Propuesta Debe/Haber = Débito</span><span class="sxs-lookup"><span data-stu-id="52f4b-138">Main Account type: If Balance and DB/CR proposal = Debit</span></span>
    -   <span data-ttu-id="52f4b-139">Tipo de cuenta principal: Si Pérdidas/ganancias y Propuesta Debe/Haber = En blanco</span><span class="sxs-lookup"><span data-stu-id="52f4b-139">Main Account type: If Profit & Loss and DB/CR proposal = Blank</span></span>
    -   <span data-ttu-id="52f4b-140">Tipo de cuenta principal: Si Saldo y Propuesta Debe/Haber = En blanco</span><span class="sxs-lookup"><span data-stu-id="52f4b-140">Main Account type: If Balance and DB/CR proposal = Blank</span></span>
  - <span data-ttu-id="52f4b-141">**Crédito A**</span><span class="sxs-lookup"><span data-stu-id="52f4b-141">**A-Credit**</span></span>
    -   <span data-ttu-id="52f4b-142">Tipo de cuenta: Ingresos, Pasivo</span><span class="sxs-lookup"><span data-stu-id="52f4b-142">Account type : Revenue, Liability</span></span>
    -   <span data-ttu-id="52f4b-143">Tipo de cuenta AX: Si Pérdidas/ganancias y Propuesta Debe/Haber = Crédito</span><span class="sxs-lookup"><span data-stu-id="52f4b-143">Account type AX: If Profit & Loss and DB/CR proposal = Credit</span></span>
    -   <span data-ttu-id="52f4b-144">Tipo de cuenta AX: Si Saldo y Propuesta Debe/Haber = Crédito</span><span class="sxs-lookup"><span data-stu-id="52f4b-144">Account type AX: If Balance and DB/CR proposal = Credit</span></span>
- <span data-ttu-id="52f4b-145">**Importe de totales en todos los niveles:** Configure el valor de **Totales** en el plan de cuentas para habilitar la generación de un archivo XML Saldo de comprobación mensual que incluye los importes de los totales relacionados en todos los niveles de la jerarquía.</span><span class="sxs-lookup"><span data-stu-id="52f4b-145">**Totals amount in all levels:** Configure the **Totals** value in the chart of accounts to enable generation of a Monthly Trial Balance XML file that includes the related totals amounts in all levels of the hierarchy.</span></span>

### <a name="sat-account-group"></a><span data-ttu-id="52f4b-146">Grupo de cuentas SAT</span><span class="sxs-lookup"><span data-stu-id="52f4b-146">SAT account group</span></span>

<span data-ttu-id="52f4b-147">El archivo XML Gráfico del plan contable incluye una etiqueta **&lt;CodAgrup&gt;** que se usa para especificar el grupo de cuentas del gobierno relacionado para la cuenta notificada.</span><span class="sxs-lookup"><span data-stu-id="52f4b-147">The Chart of account XML file includes a **&lt;CodAgrup&gt;** tag that is used to specify the related government account group for the reported account.</span></span> <span data-ttu-id="52f4b-148">El gobierno ha publicado una tabla en el portal gubernamental.</span><span class="sxs-lookup"><span data-stu-id="52f4b-148">The government has published a table on the government portal.</span></span> <span data-ttu-id="52f4b-149">Para cumplir este requisito, debe usar la funcionalidad de Grupos de cuentas de consolidación, que le permite configurar la asignación entre el plan de cuentas de la empresa y el grupo de la cuenta del gobierno.</span><span class="sxs-lookup"><span data-stu-id="52f4b-149">To meet this requirement, you must use the Consolidation account groups functionality, which lets you configure the mapping between your company chart of account and the government account group.</span></span> <span data-ttu-id="52f4b-150">A continuación, cuando genere el informe, se le solicitará que indique qué grupo de cuentas consolidadas se usa para especificar la agrupación del gobierno.</span><span class="sxs-lookup"><span data-stu-id="52f4b-150">Then, when you generate the report, you will be asked to indicate which consolidated account group is used to specify the government grouping.</span></span>

### <a name="payment-methods"></a><span data-ttu-id="52f4b-151">Métodos de pago</span><span class="sxs-lookup"><span data-stu-id="52f4b-151">Payment methods</span></span>

<span data-ttu-id="52f4b-152">En situaciones específicas, el gobierno puede solicitar que entregue un archivo XML Transacciones de diario que detalle todas las transacciones de contabilidad y el documento que las originó.</span><span class="sxs-lookup"><span data-stu-id="52f4b-152">In specific situations, the government might request that you deliver a Journal transaction XML file that details all accounting transactions and the document that originated them.</span></span> <span data-ttu-id="52f4b-153">Cuando estas transacciones estén relacionadas con pagos de proveedores, debe especificar el tipo de pago en el nodo **&lt;OtrMetododePago&gt;** y el atributo **&lt;MetPagPol&gt;** mediante una tabla específica que se publica por el gobierno.</span><span class="sxs-lookup"><span data-stu-id="52f4b-153">When these transactions are related to vendors payments, you must specify the type of payment in the **&lt;OtrMetododePago&gt;** node and the **&lt;MetPagPol&gt;** attribute by using a specific table that is published by the government.</span></span> <span data-ttu-id="52f4b-154">Haga clic en **Proveedores** &gt; **Configuración de pagos** &gt; **Formas de pago** y asigne el método de pago SAT al método de pago de la empresa.</span><span class="sxs-lookup"><span data-stu-id="52f4b-154">Click **Accounts payable** &gt; **Payment setup** &gt; **Methods of payment**, and assign the SAT payment method to the company's method of payment.</span></span>

### <a name="bank-transactions"></a><span data-ttu-id="52f4b-155">Transacciones bancarias</span><span class="sxs-lookup"><span data-stu-id="52f4b-155">Bank transactions</span></span>

<span data-ttu-id="52f4b-156">El archivo XML Transacciones de diario debe incluir todas las transacciones de transferencias bancarias que se registran en la contabilidad general donde se requiere alguna información adicional en un nodo específico **&lt;Transferencias&gt;** y se requieren sus atributos **&lt;BancoOriNal&gt;** y **&lt;BancoDestNal&gt;** para informar del código de banco gubernamental.</span><span class="sxs-lookup"><span data-stu-id="52f4b-156">The Journal transaction XML file must include all bank transfer transactions that are posted to the general ledger where some additional information is required in a specific node **&lt;Transferencias&gt;** and their attributes **&lt;BancoOriNal&gt;** and **&lt;BancoDestNal&gt;** is required to inform the government bank code.</span></span> <span data-ttu-id="52f4b-157">Haga clic en **Gestión de efectivo y bancos** &gt; **Cuentas bancarias** y use el campo **Número de ruta** para configurar esta información.</span><span class="sxs-lookup"><span data-stu-id="52f4b-157">Click **Cash and bank management** &gt; **Bank accounts**, and use the **Routing number** field to set up this information.</span></span>

### <a name="invoice-identification"></a><span data-ttu-id="52f4b-158">Identificación de factura</span><span class="sxs-lookup"><span data-stu-id="52f4b-158">Invoice identification</span></span>

<span data-ttu-id="52f4b-159">El archivo XML Transacciones de diario también requiere que identifique el número de factura cuando se emita y se reciba una factura.</span><span class="sxs-lookup"><span data-stu-id="52f4b-159">The Journal transaction XML file also requires that you identify the invoice number when an invoice is issued and received.</span></span> <span data-ttu-id="52f4b-160">Según la legislación mexicana, este número de factura se puede representar de distintas maneras, en función de cómo se haya entregado la factura:</span><span class="sxs-lookup"><span data-stu-id="52f4b-160">Per Mexican legislation, this invoice number can be represented in various ways, depending on how the invoice was delivered:</span></span>

-   <span data-ttu-id="52f4b-161">Factura normal (no electrónica).</span><span class="sxs-lookup"><span data-stu-id="52f4b-161">Regular invoice (non-electronic).</span></span> <span data-ttu-id="52f4b-162">Debe incluir la **Serie** y el **Número de factura**.</span><span class="sxs-lookup"><span data-stu-id="52f4b-162">You must include the **Series** and **Invoice number**.</span></span>
-   <span data-ttu-id="52f4b-163">CFD: Debe incluir el **UUID** de un CFD de factura electrónica.</span><span class="sxs-lookup"><span data-stu-id="52f4b-163">CFD: You must include the **UUID** of an electronic invoice CFD.</span></span>
-   <span data-ttu-id="52f4b-164">CFDI: Debe incluir el **UUID** de un CFD de factura electrónica.</span><span class="sxs-lookup"><span data-stu-id="52f4b-164">CFDI:  You must include the **UUID** of an electronic invoice CFD.</span></span>

<span data-ttu-id="52f4b-165">Los usuarios pueden incluir ahora esta información en las transacciones que se generan de las siguientes áreas:</span><span class="sxs-lookup"><span data-stu-id="52f4b-165">Users can now include this information in transactions that are generated from the following areas:</span></span>

-   <span data-ttu-id="52f4b-166">Factura de compra</span><span class="sxs-lookup"><span data-stu-id="52f4b-166">Purchase invoice</span></span>
-   <span data-ttu-id="52f4b-167">Factura de proveedor (pedido que no es de compra)</span><span class="sxs-lookup"><span data-stu-id="52f4b-167">Vendor invoice (non–purchase order)</span></span>
-   <span data-ttu-id="52f4b-168">Registro de facturas</span><span class="sxs-lookup"><span data-stu-id="52f4b-168">Invoice register</span></span>
-   <span data-ttu-id="52f4b-169">Diario de facturas</span><span class="sxs-lookup"><span data-stu-id="52f4b-169">Invoice journal</span></span>
-   <span data-ttu-id="52f4b-170">Aprobación de factura</span><span class="sxs-lookup"><span data-stu-id="52f4b-170">Invoice approval</span></span>
-   <span data-ttu-id="52f4b-171">Grupo de facturas</span><span class="sxs-lookup"><span data-stu-id="52f4b-171">Invoice pool</span></span>

### <a name="electronic-reporting"></a><span data-ttu-id="52f4b-172">Informes electrónicos</span><span class="sxs-lookup"><span data-stu-id="52f4b-172">Electronic reporting</span></span>

<span data-ttu-id="52f4b-173">Esta característica se basa en la configuración de informes electrónicos (ER), donde cada formato de archivo XML se define con el diseñador de modelos y formatos para informes electrónicos.</span><span class="sxs-lookup"><span data-stu-id="52f4b-173">This feature is based on Electronic reporting configuration (ER), where each XML file format is defined by using the model and format designer for electronic reporting.</span></span> 

<span data-ttu-id="52f4b-174">Necesita descargar las últimas versiones siguientes de los modelos y formatos de configuraciones de ER de la **biblioteca de activos compartidos de LCS**</span><span class="sxs-lookup"><span data-stu-id="52f4b-174">You need to download the following latest versions of the ER configurations models and formats from **LCS shared asset library**</span></span>
1.  <span data-ttu-id="52f4b-175">Modelo electrónico de cuenta contable MX</span><span class="sxs-lookup"><span data-stu-id="52f4b-175">Electronic ledger accounting model MX</span></span>
2.  <span data-ttu-id="52f4b-176">Libro mayor auxiliar XML MX (formato)</span><span class="sxs-lookup"><span data-stu-id="52f4b-176">Auxiliary Ledger XML MX (format)</span></span>
3.  <span data-ttu-id="52f4b-177">Plan de cuentas XML MX (formato)</span><span class="sxs-lookup"><span data-stu-id="52f4b-177">Chart of Account XML MX (format)</span></span>
4.  <span data-ttu-id="52f4b-178">Diario XML MX (formato)</span><span class="sxs-lookup"><span data-stu-id="52f4b-178">Journal XML MX (format)</span></span>
5.  <span data-ttu-id="52f4b-179">Saldo de comprobación XML MX (formato)</span><span class="sxs-lookup"><span data-stu-id="52f4b-179">Trial Balance XML MX (format)</span></span>

<span data-ttu-id="52f4b-180">A continuación, deberá importar los archivos anteriores a Dynamics 365 Finance.</span><span class="sxs-lookup"><span data-stu-id="52f4b-180">Next, you need to import the above files in Dynamics 365 Finance.</span></span> 

1. <span data-ttu-id="52f4b-181">**Administración de la organización > Informes electrónicos > Configuraciones**</span><span class="sxs-lookup"><span data-stu-id="52f4b-181">**Organization administration > Electronic Reporting > Configurations**</span></span>
2. <span data-ttu-id="52f4b-182">**Exchange > Carga desde archivo XML** y **Aceptar** para confirmar.</span><span class="sxs-lookup"><span data-stu-id="52f4b-182">**Exchange > Load from XML file** and **OK** to confirm.</span></span> <span data-ttu-id="52f4b-183">Necesita repetir esta acción para cada archivo XML.</span><span class="sxs-lookup"><span data-stu-id="52f4b-183">You need to repeat this action for each XML file.</span></span>


<span data-ttu-id="52f4b-184">Después de que el depósito se actualice en el entorno con los archivos que acaba de cargar, debe identificar estos formatos en los parámetros de contabilidad general.</span><span class="sxs-lookup"><span data-stu-id="52f4b-184">After the repository is updated in your environment with the recently files loaded, you must identify these formats in the general ledger parameters.</span></span> <span data-ttu-id="52f4b-185">Haga clic en los parámetros **Contabilidad general** &gt; **Configuración de contabilidad** &gt; **Contabilidad general** y, a continuación, en el grupo de campos **Asignación de informes electrónicos**, seleccione el formato que desea utilizar para generar los archivos XML.</span><span class="sxs-lookup"><span data-stu-id="52f4b-185">Click **General ledger** &gt; **Ledger setup** &gt; **General ledger parameters**, and then, in the **Electronic reporting mapping** field group, select the format to use to generate the XML files.</span></span>

## <a name="generate-electronic-ledger-accounting-files"></a><span data-ttu-id="52f4b-186">Generar archivos electrónicos de cuenta contable</span><span class="sxs-lookup"><span data-stu-id="52f4b-186">Generate electronic ledger accounting files</span></span>
<span data-ttu-id="52f4b-187">Haga clic en **Contabilidad general** &gt; **Consulta e informes** &gt; **Informes de contabilidad** &gt; **Extracto electrónico de cuenta contable** para generar los archivos XML necesarios y descargarlos en el entorno.</span><span class="sxs-lookup"><span data-stu-id="52f4b-187">Click **General ledger** &gt; **Inquire and reports** &gt; **Ledger reports** &gt; **Electronic ledger accounting statement** to generate the required XML files and download them to your environment.</span></span> <span data-ttu-id="52f4b-188">La tabla siguiente describe los parámetros que debe establecer.</span><span class="sxs-lookup"><span data-stu-id="52f4b-188">The following table describes the parameters that you must set.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><span data-ttu-id="52f4b-189"><strong>Grupo de cuentas de consolidación de SAT</strong></span><span class="sxs-lookup"><span data-stu-id="52f4b-189"><strong>SAT consolidation account group</strong></span></span></td>
<td><span data-ttu-id="52f4b-190">Seleccione el grupo de cuentas de consolidación que haya configurado anteriormente para identificar el grupo de cuentas SAT.</span><span class="sxs-lookup"><span data-stu-id="52f4b-190">Select the consolidation account group that you previously configured to identify the SAT account group.</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="52f4b-191"><strong>Período</strong></span><span class="sxs-lookup"><span data-stu-id="52f4b-191"><strong>Period</strong></span></span></td>
<td><span data-ttu-id="52f4b-192">Seleccione el período del informe.</span><span class="sxs-lookup"><span data-stu-id="52f4b-192">Select the period for the report.</span></span> <span data-ttu-id="52f4b-193">La fecha seleccionada incluirá todas las transacciones de contabilidad general para el mes seleccionado.</span><span class="sxs-lookup"><span data-stu-id="52f4b-193">The selected date will include all general ledger transactions for the selected month.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="52f4b-194"><strong>Transacciones de cierre</strong></span><span class="sxs-lookup"><span data-stu-id="52f4b-194"><strong>Closing transactions</strong></span></span></td>
<td><span data-ttu-id="52f4b-195">Este control deslizante indica si las transacciones de cierre se deben incluir como transacciones en el archivo XML Saldo de comprobación mensual.</span><span class="sxs-lookup"><span data-stu-id="52f4b-195">This slider indicates if the closing transactions should be included as transactions in the Monthly Trial Balance XML file.</span></span> <span data-ttu-id="52f4b-196">Cambie este control deslizante a <strong>No</strong> para excluir las transacciones de cierre del archivo XML Saldo de comprobación mensual.</span><span class="sxs-lookup"><span data-stu-id="52f4b-196">Switch this slider to <strong>No</strong> to exclude closing transactions from the Monthly Trial balance XML file.</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="52f4b-197"><strong>Saldo de comprobación</strong></span><span class="sxs-lookup"><span data-stu-id="52f4b-197"><strong>Trial Balance</strong></span></span></td>
<td><span data-ttu-id="52f4b-198">Active esta casilla para generar los archivos XML Plan de cuentas y Saldo de comprobación mensual para el período especificado.</span><span class="sxs-lookup"><span data-stu-id="52f4b-198">Select this check box to generate the Chart of account and Monthly Trial Balance XML files for the specified period.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="52f4b-199"><strong>Tipo de entrega</strong></span><span class="sxs-lookup"><span data-stu-id="52f4b-199"><strong>Delivery type</strong></span></span></td>
<td><span data-ttu-id="52f4b-200">Especifique el tipo de entrega:</span><span class="sxs-lookup"><span data-stu-id="52f4b-200">Specify the type of delivery:</span></span>
<ul>
<li><span data-ttu-id="52f4b-201">Normal</span><span class="sxs-lookup"><span data-stu-id="52f4b-201">Normal</span></span></li>
<li><span data-ttu-id="52f4b-202">Complementario</span><span class="sxs-lookup"><span data-stu-id="52f4b-202">Complementary</span></span></li>
</ul></td>
</tr>
<tr class="even">
<td><span data-ttu-id="52f4b-203"><strong>Fecha de actualización</strong></span><span class="sxs-lookup"><span data-stu-id="52f4b-203"><strong>Update date</strong></span></span></td>
<td><span data-ttu-id="52f4b-204">Especifique la fecha actualizada de una entrega complementaria.</span><span class="sxs-lookup"><span data-stu-id="52f4b-204">Specify the updated date of a complementary delivery.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="52f4b-205"><strong>Movimientos contables</strong></span><span class="sxs-lookup"><span data-stu-id="52f4b-205"><strong>Ledger entries</strong></span></span></td>
<td><span data-ttu-id="52f4b-206">Este control deslizante indica si el archivo XML Transacciones de diario se genera para el período especificado.</span><span class="sxs-lookup"><span data-stu-id="52f4b-206">This slider indicates if the Journal transaction XML file is generated for the specified period.</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="52f4b-207"><strong>Libro mayor auxiliar</strong></span><span class="sxs-lookup"><span data-stu-id="52f4b-207"><strong>Auxiliary ledger</strong></span></span></td>
<td><span data-ttu-id="52f4b-208">Este control deslizante indica si el archivo XML Libro mayor auxiliar se genera para el período especificado.</span><span class="sxs-lookup"><span data-stu-id="52f4b-208">This slider indicates if the Auxiliary ledger XML file is generated for the specified period.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="52f4b-209"><strong>Tipo de solicitud</strong></span><span class="sxs-lookup"><span data-stu-id="52f4b-209"><strong>Request type</strong></span></span></td>
<td><span data-ttu-id="52f4b-210">Seleccione esta opción para identificar el tipo de solicitud cuando el control deslizante <strong>Asientos contables</strong> o <strong>Libro mayor auxiliar</strong> está establecido en <strong>Sí</strong>.</span><span class="sxs-lookup"><span data-stu-id="52f4b-210">Select this option to identify the type of request when the <strong>Ledger entries</strong> or <strong>Auxiliary ledger</strong> slider is set to <strong>Yes</strong>.</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="52f4b-211"><strong>Número de pedido</strong></span><span class="sxs-lookup"><span data-stu-id="52f4b-211"><strong>Order number</strong></span></span></td>
<td><span data-ttu-id="52f4b-212">Especifique el número de pedido que se ha asignado por la autoridad fiscal del gobierno, si el tipo de solicitud es <strong>Control</strong> o <strong>Control obligatorio</strong>.</span><span class="sxs-lookup"><span data-stu-id="52f4b-212">Enter the order number that was assigned by the government tax authority, if the request type is <strong>Control</strong> or <strong>Compulsive control</strong>.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="52f4b-213"><strong>Número de proceso</strong></span><span class="sxs-lookup"><span data-stu-id="52f4b-213"><strong>Process Number</strong></span></span></td>
<td><span data-ttu-id="52f4b-214">Especifique el número de proceso que se ha asignado por la autoridad fiscal del gobierno, si el tipo de solicitud es <strong>Devolución</strong> o <strong>Compensación</strong>.</span><span class="sxs-lookup"><span data-stu-id="52f4b-214">Enter the process number that was assigned by the government tax authority, if the request type is <strong>Return</strong> or <strong>Compensation</strong>.</span></span></td>
</tr>
</tbody>
</table>


## <a name="produce-mexican-electronic-ledger-accounting-report-mx-00020"></a><span data-ttu-id="52f4b-215">Producir el informe electrónico de contabilidad de libro mayor del producto mexicano (MX-00020)</span><span class="sxs-lookup"><span data-stu-id="52f4b-215">Produce Mexican electronic ledger accounting report (MX-00020)</span></span>

<span data-ttu-id="52f4b-216">Esta tarea le muestra todos los pasos necesarios para configurar la generación de archivos XML electrónicos de cuenta contable mediante la herramienta de informes electrónicos.</span><span class="sxs-lookup"><span data-stu-id="52f4b-216">This task walks through all necessary steps to configure the generation of electronic ledger accounting XML files by using the Electronic Reporting tool.</span></span> <span data-ttu-id="52f4b-217">Necesita descargar la versión más alta del modelo y las configuraciones de ER de las configuraciones de biblioteca- GER compartidas de LCS.</span><span class="sxs-lookup"><span data-stu-id="52f4b-217">You need to download the higher version of ER model and configurations from LCS shared library-GER configurations.</span></span>

-   <span data-ttu-id="52f4b-218">Modelo: Modelo de cuenta contable electrónica (MX)</span><span class="sxs-lookup"><span data-stu-id="52f4b-218">Model: Electromic ledger accounting model MX</span></span> 
-   <span data-ttu-id="52f4b-219">Archivo de formato: Plan de cuentas XML (MX)</span><span class="sxs-lookup"><span data-stu-id="52f4b-219">Format file: Chart of account XML(MX)</span></span>
-   <span data-ttu-id="52f4b-220">Archivo de formato: Saldo de comprobación XML (MX)</span><span class="sxs-lookup"><span data-stu-id="52f4b-220">Format file: Trial Balance XML (MX).</span></span> <span data-ttu-id="52f4b-221">Saldo de comprobación mensual</span><span class="sxs-lookup"><span data-stu-id="52f4b-221">Monthly Trial Balance</span></span>
-   <span data-ttu-id="52f4b-222">Archivo de formato: Diarios XML (MX).</span><span class="sxs-lookup"><span data-stu-id="52f4b-222">Format file : Journals XML (MX).</span></span> <span data-ttu-id="52f4b-223">Transacciones de diario, junto con las transacciones de subcontabilidad relacionadas (Comprobante Fiscal Digital a través de Internet \[CFDI\], Comprobante Fiscal Digital \[CFD\] y otras operaciones)</span><span class="sxs-lookup"><span data-stu-id="52f4b-223">Journal transactions, together with the related subledger transactions (Comprobante Fiscal Digital a través de Internet \[CFDI\], Comprobante Fiscal Digital \[CFD\], and other operations)</span></span>
-   <span data-ttu-id="52f4b-224">Archivo de formato: Libro mayor auxiliar XML (MX)</span><span class="sxs-lookup"><span data-stu-id="52f4b-224">Format file: Auxiliary ledger XML (MX)</span></span> 


### <a name="import-a-configuration-including-xml-formats"></a><span data-ttu-id="52f4b-225">Importación de una configuración con formatos XML</span><span class="sxs-lookup"><span data-stu-id="52f4b-225">Import a configuration including XML formats</span></span>
1. <span data-ttu-id="52f4b-226">Vaya a Administración de la organización > Espacios de trabajo > Informes electrónicos.</span><span class="sxs-lookup"><span data-stu-id="52f4b-226">Go to Organization administration > Workspaces > Electronic reporting.</span></span>
2. <span data-ttu-id="52f4b-227">En la lista Proveedores de configuración, haga clic en Definir como activo en el cuadro de proveedor de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="52f4b-227">In the Configuration providers list, click Set active on the Microsoft provider box.</span></span>
    * <span data-ttu-id="52f4b-228">Si el proveedor de Microsoft ya es el proveedor activo, puede omitir este paso.</span><span class="sxs-lookup"><span data-stu-id="52f4b-228">If the Microsoft provider is already the active provider, you can skip this step.</span></span>  
3. <span data-ttu-id="52f4b-229">Haga clic en Configuraciones de informes.</span><span class="sxs-lookup"><span data-stu-id="52f4b-229">Click Reporting configurations</span></span>
4. <span data-ttu-id="52f4b-230">Haga clic en Exchange y seleccione la opción Cargar desde un archivo XML</span><span class="sxs-lookup"><span data-stu-id="52f4b-230">Click Exchange and select the option Load from XML file</span></span>
5. <span data-ttu-id="52f4b-231">Seleccione y examine el archivo del modelo de XML descargado previamente desde LCS y haga clic en Aceptar para confirmar</span><span class="sxs-lookup"><span data-stu-id="52f4b-231">Select and browse the XML model file previously downloaded from LCS and then click OK to confirm</span></span>
6. <span data-ttu-id="52f4b-232">Repita los pasos 4 y 5 para importar el resto de formatos de archivo XML</span><span class="sxs-lookup"><span data-stu-id="52f4b-232">Repeat the steps 4 and 5 to import the rest of XML file formats</span></span>
    * <span data-ttu-id="52f4b-233">Podrá ver un (1) modelo y los cuatro (4) formatos XML que importó anteriormente.</span><span class="sxs-lookup"><span data-stu-id="52f4b-233">You will be able to see one (1) model and the four (4) XML formats that you previously imported.</span></span>  

### <a name="configure-general-ledger-parameters-for-electronic-reporting-mapping"></a><span data-ttu-id="52f4b-234">Configuración de parámetros de contabilidad general para asignar informes electrónicos</span><span class="sxs-lookup"><span data-stu-id="52f4b-234">Configure general ledger parameters for electronic reporting mapping</span></span>
1. <span data-ttu-id="52f4b-235">Vaya a Contabilidad general > Configuración de contabilidad > Parámetros de Contabilidad general.</span><span class="sxs-lookup"><span data-stu-id="52f4b-235">Go to General ledger > Ledger setup > General ledger parameters.</span></span>
2. <span data-ttu-id="52f4b-236">En el campo Saldo de comprobación, haga clic en el botón desplegable para abrir la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="52f4b-236">In the Trial balance field, click the drop-down button to open the lookup.</span></span>
3. <span data-ttu-id="52f4b-237">En la lista, seleccione el formato XML de saldo de comprobación.</span><span class="sxs-lookup"><span data-stu-id="52f4b-237">In the list, select the Trial Balance XML format</span></span>
4. <span data-ttu-id="52f4b-238">En la lista, haga clic en el vínculo de la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="52f4b-238">In the list, click the link in the selected row.</span></span>
5. <span data-ttu-id="52f4b-239">En el campo Libro mayor auxiliar, haga clic en el botón desplegable para abrir la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="52f4b-239">In the Auxiliary ledger field, click the drop-down button to open the lookup.</span></span>
6. <span data-ttu-id="52f4b-240">En la lista, seleccione el formato XML de libro mayor auxiliar.</span><span class="sxs-lookup"><span data-stu-id="52f4b-240">In the list, selecy the Auxiliary ledger XML format</span></span>
7. <span data-ttu-id="52f4b-241">En el campo Movimientos contables, haga clic en el botón desplegable para abrir la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="52f4b-241">In the Ledger entries field, click the drop-down button to open the lookup.</span></span>
8. <span data-ttu-id="52f4b-242">En la lista, seleccione el formato XML para diarios.</span><span class="sxs-lookup"><span data-stu-id="52f4b-242">In the list, select the Journal XML format</span></span>
9. <span data-ttu-id="52f4b-243">En la lista, haga clic en el vínculo de la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="52f4b-243">In the list, click the link in the selected row.</span></span>
10. <span data-ttu-id="52f4b-244">En el campo Plan contable, haga clic en el botón desplegable para abrir la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="52f4b-244">In the Chart of accounts field, click the drop-down button to open the lookup.</span></span>
11. <span data-ttu-id="52f4b-245">En la lista, seleccione el formato XML para plan de cuentas.</span><span class="sxs-lookup"><span data-stu-id="52f4b-245">In the list, select the Chart of Account XML format.</span></span>
12. <span data-ttu-id="52f4b-246">Haga clic en Guardar.</span><span class="sxs-lookup"><span data-stu-id="52f4b-246">Click Save.</span></span>

### <a name="generate-xml-files"></a><span data-ttu-id="52f4b-247">Generación de archivos XML</span><span class="sxs-lookup"><span data-stu-id="52f4b-247">Generate XML files</span></span>
1. <span data-ttu-id="52f4b-248">Vaya Contabilidad general > Consultas e informes > Informes de contabilidad > Extracto electrónico de cuenta contable.</span><span class="sxs-lookup"><span data-stu-id="52f4b-248">Go to General ledger > Inquiries and reports > Ledger reports > Electronic ledger accounting statement.</span></span>
2. <span data-ttu-id="52f4b-249">En el campo Grupo de cuentas de consolidación de SAT, haga clic en el botón desplegable para abrir la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="52f4b-249">In the SAT consolidation account group field, click the drop-down button to open the lookup.</span></span>
3. <span data-ttu-id="52f4b-250">En la lista, busque y seleccione el registro deseado.</span><span class="sxs-lookup"><span data-stu-id="52f4b-250">In the list, find and select the desired record.</span></span>
4. <span data-ttu-id="52f4b-251">En la lista, haga clic en el vínculo de la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="52f4b-251">In the list, click the link in the selected row.</span></span>
5. <span data-ttu-id="52f4b-252">En el campo Período, especifique una fecha.</span><span class="sxs-lookup"><span data-stu-id="52f4b-252">In the Period field, enter a date.</span></span>
6. <span data-ttu-id="52f4b-253">Active o desactive la opción Saldo de comprobación.</span><span class="sxs-lookup"><span data-stu-id="52f4b-253">Check or uncheck the Trial Balance opcion</span></span>
    * <span data-ttu-id="52f4b-254">Esta opción genera los archivos XML del plan contable y el saldo de comprobación.</span><span class="sxs-lookup"><span data-stu-id="52f4b-254">This option generates the Chart of Account and Trial Balance XML files.</span></span>  
7. <span data-ttu-id="52f4b-255">Active o desactive la casilla Movimientos contables.</span><span class="sxs-lookup"><span data-stu-id="52f4b-255">Select or clear the Ledger entries check box.</span></span>
8. <span data-ttu-id="52f4b-256">Active o desactive la casilla Libro mayor auxiliar.</span><span class="sxs-lookup"><span data-stu-id="52f4b-256">Select or clear the Auxiliary ledger check box.</span></span>
9. <span data-ttu-id="52f4b-257">En el campo Tipo de solicitud, seleccione una opción.</span><span class="sxs-lookup"><span data-stu-id="52f4b-257">In the Request type field, select an option.</span></span>
10. <span data-ttu-id="52f4b-258">En el campo Número de pedido, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="52f4b-258">In the Order number field, type a value.</span></span>
11. <span data-ttu-id="52f4b-259">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="52f4b-259">Click OK.</span></span>


## <a name="additional-resources"></a><span data-ttu-id="52f4b-260">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="52f4b-260">Additional resources</span></span>

- [<span data-ttu-id="52f4b-261">CFDI versión 3.3</span><span class="sxs-lookup"><span data-stu-id="52f4b-261">CFDI Version 3.3</span></span>](latam-mex-cfdi-3-3.md)


