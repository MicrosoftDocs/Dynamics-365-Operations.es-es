---
title: Estándares compatibles para la facturación electrónica en Europa
description: Este tema explica el nivel de cobertura que existe en la facturación electrónica para Europa.
author: mrolecki
manager: AnnBe
ms.date: 09/03/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: 10274
ms.search.region: Austria, Denmark, Italy, Norway, Spain, France, Belgium, Netherlands
ms.search.industry: ''
ms.author: mrolecki
ms.search.validFrom: 2016-05-31
ms.dyn365.ops.version: AX 7.0.1
ms.openlocfilehash: c86cc90e5f441641bc14d20898e65325d7c7d716
ms.sourcegitcommit: 1ca48d95fbff2555307cc1e5e5e23feea79a8bc1
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/03/2020
ms.locfileid: "3763686"
---
# <a name="supported-standards-for-electronic-invoicing-in-europe"></a><span data-ttu-id="7337d-103">Estándares compatibles para la facturación electrónica en Europa</span><span class="sxs-lookup"><span data-stu-id="7337d-103">Supported standards for electronic invoicing in Europe</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="7337d-104">Este tema explica el nivel de cobertura que existe en la facturación electrónica para Europa.</span><span class="sxs-lookup"><span data-stu-id="7337d-104">This topic explains the level of coverage that exists for electronic invoicing for Europe.</span></span> 

<span data-ttu-id="7337d-105">La implementación y la adopción de la facturación electrónica a escala de la Unión Europea está regulada por la [Directiva del Consejo 2010/45/EU](https://eur-lex.europa.eu/LexUriServ/LexUriServ.do?uri=OJ:L:2010:189:0001:0008:EN:PDF), que afecta a todos los estados miembros de la UE.</span><span class="sxs-lookup"><span data-stu-id="7337d-105">Implementation and adoption of European Union-wide electronic invoicing is regulated [Council Directive 2010/45/EU](https://eur-lex.europa.eu/LexUriServ/LexUriServ.do?uri=OJ:L:2010:189:0001:0008:EN:PDF), which affects all EU member states.</span></span> <span data-ttu-id="7337d-106">Las empresas que desean beneficiarse de la facturación electrónica deben enviar las facturas de pedido de ventas, facturas de servicios, facturas de proyecto, notas de abono de pedidos de ventas, y notas de crédito de la factura de proyecto como archivos .xml al gobierno u otras partes comerciales que ordenen el uso de la facturación electrónica.</span><span class="sxs-lookup"><span data-stu-id="7337d-106">Companies that want to benefit from electronic invoicing must submit sales order invoices, free text invoices, project invoices, sales order credit notes, and project invoice credit notes as .xml files to the government or other trading parties that mandate use of electronic invoicing.</span></span> <span data-ttu-id="7337d-107">Estos archivos .xml deben cumplir determinados estándares.</span><span class="sxs-lookup"><span data-stu-id="7337d-107">These .xml files must comply with certain standards.</span></span> <span data-ttu-id="7337d-108">Los requisitos específicos de país y la implementación pueden ser diferentes en los estados miembros de la UE, pero suelen usar Universal Business Language ([UBL](https://www.oasis-open.org/committees/tc_home.php?wg_abbrev=ubl)) en diferentes versiones con personalizaciones junto con [PEPPOL](https://www.peppol.eu) especificaciones y puntos de acceso para la validación y el transporte.</span><span class="sxs-lookup"><span data-stu-id="7337d-108">The country-specific requirements and their implementation may differ across EU member states but commonly they are using Universal Business Language ([UBL](https://www.oasis-open.org/committees/tc_home.php?wg_abbrev=ubl)) in different versions with customizations as well as [PEPPOL](https://www.peppol.eu) specifications and access points for validation and transportation.</span></span> <span data-ttu-id="7337d-109">La ventaja principal del UBL es que los documentos empresariales se pueden estandarizar para distintos fines.</span><span class="sxs-lookup"><span data-stu-id="7337d-109">The primary advantage of UBL is that business documents can be standardized for different purposes.</span></span> <span data-ttu-id="7337d-110">Dado que el UBL es una norma flexible e internacional que admite muchos requisitos empresariales, estos documentos empresariales se pueden intercambiar a través de las fronteras nacionales.</span><span class="sxs-lookup"><span data-stu-id="7337d-110">Because UBL is a flexible, international standard that supports many business requirements, these business documents can be exchanged across national borders.</span></span>

## <a name="electronic-invoice-formats-currently-available-in-dynamics-365-finance"></a><span data-ttu-id="7337d-111">Formatos de factura electrónica actualmente disponibles en Dynamics 365 Finance</span><span class="sxs-lookup"><span data-stu-id="7337d-111">Electronic invoice formats currently available in Dynamics 365 Finance</span></span>

<span data-ttu-id="7337d-112">Los formatos específicos de país siguientes de facturas electrónicas están disponibles:</span><span class="sxs-lookup"><span data-stu-id="7337d-112">The following country-specific formats of electronic invoices are available:</span></span>

-   <span data-ttu-id="7337d-113">OIOUBL v.2.02 para Dinamarca</span><span class="sxs-lookup"><span data-stu-id="7337d-113">OIOUBL v.2.02 for Denmark</span></span>
-   <span data-ttu-id="7337d-114">EHF v.3.0 para Noruega</span><span class="sxs-lookup"><span data-stu-id="7337d-114">EHF v.3.0 for Norway</span></span>
-   <span data-ttu-id="7337d-115">PEPPOL BIS v. 2 para Austria, Francia, y Bélgica</span><span class="sxs-lookup"><span data-stu-id="7337d-115">PEPPOL BIS v.2 for Austria, France, and Belgium</span></span>
-   <span data-ttu-id="7337d-116">UBL-OHNL 1.9 para los Países Bajos</span><span class="sxs-lookup"><span data-stu-id="7337d-116">UBL-OHNL 1.9 for the Netherlands</span></span>
-   <span data-ttu-id="7337d-117">FacturaE v.3.2.1 para España</span><span class="sxs-lookup"><span data-stu-id="7337d-117">FacturaE v.3.2.1 for Spain</span></span>
-   <span data-ttu-id="7337d-118">FatturaPA v.1.2 para Italia</span><span class="sxs-lookup"><span data-stu-id="7337d-118">FatturaPA v.1.2 for Italy</span></span>
-   <span data-ttu-id="7337d-119">xRechnung v.1.2 para Alemania</span><span class="sxs-lookup"><span data-stu-id="7337d-119">xRechnung v.1.2 for Germany</span></span>
-   <span data-ttu-id="7337d-120">Abrir PEPPOL BIS Billing v.3.0 para la Unión Europea</span><span class="sxs-lookup"><span data-stu-id="7337d-120">Open PEPPOL BIS Billing v.3.0 for European Union</span></span>
-   <span data-ttu-id="7337d-121">Formato específico estonio versión 1.2</span><span class="sxs-lookup"><span data-stu-id="7337d-121">Estonian specific format version 1.2</span></span>
-   <span data-ttu-id="7337d-122">Finvoice 3.0 para Finlandia</span><span class="sxs-lookup"><span data-stu-id="7337d-122">Finvoice 3.0 for Finland</span></span>

<span data-ttu-id="7337d-123">La facturación electrónica se basa en [Informes electrónicos (ER)](../../dev-itpro/analytics/general-electronic-reporting.md).</span><span class="sxs-lookup"><span data-stu-id="7337d-123">Electronic invoicing is based on [Electronic reporting (ER)](../../dev-itpro/analytics/general-electronic-reporting.md).</span></span> <span data-ttu-id="7337d-124">Un modelo de datos **Modelo de factura**, asignación de modelo de facturas y varias configuraciones de formato específicos de país/región se han creado para Austria (AT), Dinamarca (DK), Italia (IT), Noruega (NO), España (ES), Francia (FR), Bélgica (BE), Países Bajos (NL), Alemania (DE), Estonia (EE), Finlandia (FI) y la Unión Europa (EU).</span><span class="sxs-lookup"><span data-stu-id="7337d-124">An **Invoice model** data model, invoice model mapping, and several country/region-specific ER format configurations have been created for Austria (AT), Denmark (DK), Italy (IT), Norway (NO), Spain (ES), France (FR), Belgium (BE), the Netherlands (NL), Germany (DE), Estonia (EE), Finland (FI), and the European Union (EU).</span></span>

-   <span data-ttu-id="7337d-125">Factura de ventas de OIOUBL - para AT, DK, y NO</span><span class="sxs-lookup"><span data-stu-id="7337d-125">OIOUBL Sales invoice - for AT, DK, and NO</span></span>
-   <span data-ttu-id="7337d-126">Nota de abono de OIOUBL - para AT, DK, y NO</span><span class="sxs-lookup"><span data-stu-id="7337d-126">OIOUBL Sales credit note - for AT, DK, and NO</span></span>
-   <span data-ttu-id="7337d-127">Factura de proyecto de OIOUBL - para AT, DK, y NO</span><span class="sxs-lookup"><span data-stu-id="7337d-127">OIOUBL Project invoice - for AT, DK, and NO</span></span>
-   <span data-ttu-id="7337d-128">Nota de abono de proyecto OIOUBL - para AT, DK, y NO</span><span class="sxs-lookup"><span data-stu-id="7337d-128">OIOUBL Project credit note - for AT, DK, and NO</span></span>
-   <span data-ttu-id="7337d-129">Factura de ventas de UBL para FR</span><span class="sxs-lookup"><span data-stu-id="7337d-129">UBL Sales Invoice FR</span></span>
-   <span data-ttu-id="7337d-130">Nota de abono de ventas de UBL para FR</span><span class="sxs-lookup"><span data-stu-id="7337d-130">UBL Sales Credit Note FR</span></span>
-   <span data-ttu-id="7337d-131">Factura del proyecto de UBL para FR</span><span class="sxs-lookup"><span data-stu-id="7337d-131">UBL Project Invoice FR</span></span>
-   <span data-ttu-id="7337d-132">Nota de abono de proyecto de UBL para FR</span><span class="sxs-lookup"><span data-stu-id="7337d-132">UBL Project Credit Note FR</span></span>
-   <span data-ttu-id="7337d-133">Factura de ventas de UBL para BE</span><span class="sxs-lookup"><span data-stu-id="7337d-133">UBL Sales Invoice BE</span></span>
-   <span data-ttu-id="7337d-134">Nota de abono de ventas de UBL para BE</span><span class="sxs-lookup"><span data-stu-id="7337d-134">UBL Sales Credit Note BE</span></span>
-   <span data-ttu-id="7337d-135">Factura de proyecto de UBL para BE</span><span class="sxs-lookup"><span data-stu-id="7337d-135">UBL Project Invoice BE</span></span>
-   <span data-ttu-id="7337d-136">Nota de abono de proyecto de UBL para BE</span><span class="sxs-lookup"><span data-stu-id="7337d-136">UBL Project Credit Note BE</span></span>
-   <span data-ttu-id="7337d-137">Factura de ventas de UBL para NL</span><span class="sxs-lookup"><span data-stu-id="7337d-137">UBL Sales Invoice NL</span></span>
-   <span data-ttu-id="7337d-138">Nota de abono de ventas de UBL para NL</span><span class="sxs-lookup"><span data-stu-id="7337d-138">UBL Sales Credit Note NL</span></span>
-   <span data-ttu-id="7337d-139">Factura de proyecto de UBL para NL</span><span class="sxs-lookup"><span data-stu-id="7337d-139">UBL Project Invoice NL</span></span>
-   <span data-ttu-id="7337d-140">Nota de abono de proyecto de UBL para NL</span><span class="sxs-lookup"><span data-stu-id="7337d-140">UBL Project Credit Note NL</span></span> 
-   <span data-ttu-id="7337d-141">Factura de ventas (ES)</span><span class="sxs-lookup"><span data-stu-id="7337d-141">Sales invoice (ES)</span></span>
-   <span data-ttu-id="7337d-142">Factura de ventas (IT)</span><span class="sxs-lookup"><span data-stu-id="7337d-142">Sales invoice (IT)</span></span>
-   <span data-ttu-id="7337d-143">Factura de proyecto (ES)</span><span class="sxs-lookup"><span data-stu-id="7337d-143">Project invoice (ES)</span></span>
-   <span data-ttu-id="7337d-144">Factura de proyecto (IT)</span><span class="sxs-lookup"><span data-stu-id="7337d-144">Project invoice (IT)</span></span>
-   <span data-ttu-id="7337d-145">Factura de ventas DE</span><span class="sxs-lookup"><span data-stu-id="7337d-145">Sales Invoice DE</span></span>
-   <span data-ttu-id="7337d-146">Factura de proyecto DE</span><span class="sxs-lookup"><span data-stu-id="7337d-146">Project Invoice DE</span></span>
-   <span data-ttu-id="7337d-147">Factura de ventas de Peppol - para la UE</span><span class="sxs-lookup"><span data-stu-id="7337d-147">Peppol Sales Invoice - for EU</span></span>
-   <span data-ttu-id="7337d-148">Nota de crédito de ventas de Peppol - para la UE</span><span class="sxs-lookup"><span data-stu-id="7337d-148">Peppol Sales Credit Note - for EU</span></span>
-   <span data-ttu-id="7337d-149">Factura de proyecto de Peppol - para la UE</span><span class="sxs-lookup"><span data-stu-id="7337d-149">Peppol Project Invoice - for EU</span></span>
-   <span data-ttu-id="7337d-150">Nota de crédito de proyecto de Peppol - para la UE</span><span class="sxs-lookup"><span data-stu-id="7337d-150">Peppol Project Credit Note - for EU</span></span>
-   <span data-ttu-id="7337d-151">Factura de ventas (EE)</span><span class="sxs-lookup"><span data-stu-id="7337d-151">Sales invoice (EE)</span></span>
-   <span data-ttu-id="7337d-152">Factura de proyecto (EE)</span><span class="sxs-lookup"><span data-stu-id="7337d-152">Project invoice (EE)</span></span>
-   <span data-ttu-id="7337d-153">Factura de ventas (FI)</span><span class="sxs-lookup"><span data-stu-id="7337d-153">Sales invoice (FI)</span></span>
-   <span data-ttu-id="7337d-154">Factura del proyecto (FI)</span><span class="sxs-lookup"><span data-stu-id="7337d-154">Project invoice (FI)</span></span>

<span data-ttu-id="7337d-155">Las facturas electrónicas y las notas de abono que genera incluyen la información requerida, como el número EAN (número europeo de artículo), la persona de contacto, el número de la cuenta de dimensión y la información de la dirección del cliente.</span><span class="sxs-lookup"><span data-stu-id="7337d-155">The electronic invoices and credit notes that you generate include required information, such as a European Article Numbering (EAN) number, contact person, dimension account number, and address information for the customer.</span></span> <span data-ttu-id="7337d-156">Se aplican reglas de validación cuando se generan facturas, de modo que puede verificar que se haya especificado la información correcta.</span><span class="sxs-lookup"><span data-stu-id="7337d-156">Validation rules are applied when invoices are generated so you can verify that the correct information has been entered.</span></span> <span data-ttu-id="7337d-157">El conjunto de información necesaria puede ser diferente de un país a otro.</span><span class="sxs-lookup"><span data-stu-id="7337d-157">The set of required information may differ from country to country.</span></span> <span data-ttu-id="7337d-158">Como los requisitos, al igual que los formatos y los países admitidos, están sujetos a cambios, debe ir siempre a la biblioteca de activos compartidos de Microsoft Dynamics Lifecycle Services (LCS) y ver la lista más actualizada de archivos disponibles que tienen un tipo de activo de **configuración de GER**.</span><span class="sxs-lookup"><span data-stu-id="7337d-158">Because the requirements, as well as supported countries and formats, is subject to change, you should always go to the Shared asset library on Microsoft Dynamics Lifecycle services (LCS) and view the most up-to-date list of available files that have an asset type of **GER configuration**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="7337d-159">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="7337d-159">Additional resources</span></span>
<span data-ttu-id="7337d-160">Para obtener más información acerca de cómo configurar facturas electrónicas, puede reproducir las siguientes [Guías de la tarea](../../fin-and-ops/get-started/help-overview.md#task-guides) en el panel de la Ayuda:</span><span class="sxs-lookup"><span data-stu-id="7337d-160">For more details about how to set up electronic invoices, you can play the following [Task guides](../../fin-and-ops/get-started/help-overview.md#task-guides) in the Help pane:</span></span>

 - <span data-ttu-id="7337d-161">Configurar la facturación electrónica OIOUBL</span><span class="sxs-lookup"><span data-stu-id="7337d-161">Set up OIOUBL electronic invoicing</span></span>
 - <span data-ttu-id="7337d-162">Importar configuraciones de facturación electrónica OIOUBL</span><span class="sxs-lookup"><span data-stu-id="7337d-162">Import OIOUBL electronic invoicing configurations</span></span>
 - <span data-ttu-id="7337d-163">Configurar cuentas de cliente para la facturación electrónica OIOUBL</span><span class="sxs-lookup"><span data-stu-id="7337d-163">Set up customer accounts for OIOUBL electronic invoicing</span></span>

> [!NOTE] 
> <span data-ttu-id="7337d-164">Aunque estas guías de la tarea fueron creadas para el formato de factura *OIOUBL* específicamente danés, son aplicables en otros países compatibles con desviaciones de menor importancia.</span><span class="sxs-lookup"><span data-stu-id="7337d-164">Although these Task guides were created for Danish-specific e-invoice format *OIOUBL*, they are applicable for other supported countries with minor deviations.</span></span>
