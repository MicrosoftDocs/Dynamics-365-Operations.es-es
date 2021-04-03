---
title: Estándares compatibles para la facturación electrónica en Europa
description: Este tema explica el nivel de cobertura que existe en la facturación electrónica para Europa.
author: mrolecki
manager: AnnBe
ms.date: 11/19/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.custom: 10274
ms.search.region: Austria, Denmark, Italy, Norway, Spain, France, Belgium, Netherlands
ms.search.industry: ''
ms.author: mrolecki
ms.search.validFrom: 2016-05-31
ms.dyn365.ops.version: AX 7.0.1
ms.openlocfilehash: b25dedca6d8d6726be60d1943ade0865eaf6b0ec
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2021
ms.locfileid: "5262818"
---
# <a name="supported-standards-for-electronic-invoicing-in-europe"></a><span data-ttu-id="15709-103">Estándares compatibles para la facturación electrónica en Europa</span><span class="sxs-lookup"><span data-stu-id="15709-103">Supported standards for electronic invoicing in Europe</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="15709-104">Este tema explica el nivel de cobertura que existe en la facturación electrónica para Europa.</span><span class="sxs-lookup"><span data-stu-id="15709-104">This topic explains the level of coverage that exists for electronic invoicing for Europe.</span></span> 

<span data-ttu-id="15709-105">La implementación y la adopción de la facturación electrónica a escala de la Unión Europea está regulada por la [Directiva del Consejo 2010/45/EU](https://eur-lex.europa.eu/LexUriServ/LexUriServ.do?uri=OJ:L:2010:189:0001:0008:EN:PDF), que afecta a todos los estados miembros de la UE.</span><span class="sxs-lookup"><span data-stu-id="15709-105">Implementation and adoption of European Union-wide electronic invoicing is regulated [Council Directive 2010/45/EU](https://eur-lex.europa.eu/LexUriServ/LexUriServ.do?uri=OJ:L:2010:189:0001:0008:EN:PDF), which affects all EU member states.</span></span> <span data-ttu-id="15709-106">Las empresas que desean beneficiarse de la facturación electrónica deben enviar las facturas de pedido de ventas, facturas de servicios, facturas de proyecto, notas de abono de pedidos de ventas, y notas de crédito de la factura de proyecto como archivos .xml al gobierno u otras partes comerciales que ordenen el uso de la facturación electrónica.</span><span class="sxs-lookup"><span data-stu-id="15709-106">Companies that want to benefit from electronic invoicing must submit sales order invoices, free text invoices, project invoices, sales order credit notes, and project invoice credit notes as .xml files to the government or other trading parties that mandate use of electronic invoicing.</span></span> <span data-ttu-id="15709-107">Estos archivos .xml deben cumplir determinados estándares.</span><span class="sxs-lookup"><span data-stu-id="15709-107">These .xml files must comply with certain standards.</span></span> <span data-ttu-id="15709-108">Los requisitos específicos de país y la implementación pueden ser diferentes en los estados miembros de la UE, pero suelen usar Universal Business Language ([UBL](https://www.oasis-open.org/committees/tc_home.php?wg_abbrev=ubl)) en diferentes versiones con personalizaciones junto con [PEPPOL](https://www.peppol.eu) especificaciones y puntos de acceso para la validación y el transporte.</span><span class="sxs-lookup"><span data-stu-id="15709-108">The country-specific requirements and their implementation may differ across EU member states but commonly they are using Universal Business Language ([UBL](https://www.oasis-open.org/committees/tc_home.php?wg_abbrev=ubl)) in different versions with customizations as well as [PEPPOL](https://www.peppol.eu) specifications and access points for validation and transportation.</span></span> <span data-ttu-id="15709-109">La ventaja principal del UBL es que los documentos empresariales se pueden estandarizar para distintos fines.</span><span class="sxs-lookup"><span data-stu-id="15709-109">The primary advantage of UBL is that business documents can be standardized for different purposes.</span></span> <span data-ttu-id="15709-110">Dado que el UBL es una norma flexible e internacional que admite muchos requisitos empresariales, estos documentos empresariales se pueden intercambiar a través de las fronteras nacionales.</span><span class="sxs-lookup"><span data-stu-id="15709-110">Because UBL is a flexible, international standard that supports many business requirements, these business documents can be exchanged across national borders.</span></span>

## <a name="electronic-invoice-formats-currently-available-in-dynamics-365-finance"></a><span data-ttu-id="15709-111">Formatos de factura electrónica actualmente disponibles en Dynamics 365 Finance</span><span class="sxs-lookup"><span data-stu-id="15709-111">Electronic invoice formats currently available in Dynamics 365 Finance</span></span>

<span data-ttu-id="15709-112">Los formatos específicos de país siguientes de facturas electrónicas están disponibles:</span><span class="sxs-lookup"><span data-stu-id="15709-112">The following country-specific formats of electronic invoices are available:</span></span>

-   <span data-ttu-id="15709-113">OIOUBL v.2.02 para Dinamarca</span><span class="sxs-lookup"><span data-stu-id="15709-113">OIOUBL v.2.02 for Denmark</span></span>
-   <span data-ttu-id="15709-114">EHF v.3.0 para Noruega</span><span class="sxs-lookup"><span data-stu-id="15709-114">EHF v.3.0 for Norway</span></span>
-   <span data-ttu-id="15709-115">PEPPOL BIS v. 2 para Austria, Francia, y Bélgica</span><span class="sxs-lookup"><span data-stu-id="15709-115">PEPPOL BIS v.2 for Austria, France, and Belgium</span></span>
-   <span data-ttu-id="15709-116">UBL-OHNL 1.9 para los Países Bajos</span><span class="sxs-lookup"><span data-stu-id="15709-116">UBL-OHNL 1.9 for the Netherlands</span></span>
-   <span data-ttu-id="15709-117">FacturaE v.3.2.1 para España</span><span class="sxs-lookup"><span data-stu-id="15709-117">FacturaE v.3.2.1 for Spain</span></span>
-   <span data-ttu-id="15709-118">FatturaPA v.1.2 para Italia</span><span class="sxs-lookup"><span data-stu-id="15709-118">FatturaPA v.1.2 for Italy</span></span>
-   <span data-ttu-id="15709-119">xRechnung v.1.2 para Alemania</span><span class="sxs-lookup"><span data-stu-id="15709-119">xRechnung v.1.2 for Germany</span></span>
-   <span data-ttu-id="15709-120">Abrir PEPPOL BIS Billing v.3.0 para la Unión Europea</span><span class="sxs-lookup"><span data-stu-id="15709-120">Open PEPPOL BIS Billing v.3.0 for European Union</span></span>
-   <span data-ttu-id="15709-121">Formato específico estonio versión 1.2</span><span class="sxs-lookup"><span data-stu-id="15709-121">Estonian specific format version 1.2</span></span>
-   <span data-ttu-id="15709-122">Finvoice 3.0 para Finlandia</span><span class="sxs-lookup"><span data-stu-id="15709-122">Finvoice 3.0 for Finland</span></span>

<span data-ttu-id="15709-123">La facturación electrónica se basa en [Informes electrónicos (ER)](../../dev-itpro/analytics/general-electronic-reporting.md).</span><span class="sxs-lookup"><span data-stu-id="15709-123">Electronic invoicing is based on [Electronic reporting (ER)](../../dev-itpro/analytics/general-electronic-reporting.md).</span></span> <span data-ttu-id="15709-124">SE han creado configuraciones de modelos de datos para un **Modelo de factura**, asignaciones de modelos de facturas y de formatos de informes electrónicos específicos para países o regiones para los siguientes países o regiones:</span><span class="sxs-lookup"><span data-stu-id="15709-124">An **Invoice model** data model, invoice model mapping, and several country/region-specific ER format configurations have been created for the following countries/regions:</span></span> 

- <span data-ttu-id="15709-125">Austria (AT)</span><span class="sxs-lookup"><span data-stu-id="15709-125">Austria (AT)</span></span>
- <span data-ttu-id="15709-126">Dinamarca (DK)</span><span class="sxs-lookup"><span data-stu-id="15709-126">Denmark (DK)</span></span>
- <span data-ttu-id="15709-127">Italia (IT)</span><span class="sxs-lookup"><span data-stu-id="15709-127">Italy (IT)</span></span>
- <span data-ttu-id="15709-128">Noruega (NO)</span><span class="sxs-lookup"><span data-stu-id="15709-128">Norway (NO)</span></span>
- <span data-ttu-id="15709-129">España (ES)</span><span class="sxs-lookup"><span data-stu-id="15709-129">Spain (ES)</span></span>
- <span data-ttu-id="15709-130">Francia (FR)</span><span class="sxs-lookup"><span data-stu-id="15709-130">France (FR)</span></span>
- <span data-ttu-id="15709-131">Bélgica (BE)</span><span class="sxs-lookup"><span data-stu-id="15709-131">Belgium (BE)</span></span>
- <span data-ttu-id="15709-132">Países Bajos (NL)</span><span class="sxs-lookup"><span data-stu-id="15709-132">The Netherlands (NL)</span></span>
- <span data-ttu-id="15709-133">Alemania (DE)</span><span class="sxs-lookup"><span data-stu-id="15709-133">Germany (DE)</span></span>
- <span data-ttu-id="15709-134">Estonia (EE)</span><span class="sxs-lookup"><span data-stu-id="15709-134">Estonia (EE)</span></span>
- <span data-ttu-id="15709-135">Finlandia (FI)</span><span class="sxs-lookup"><span data-stu-id="15709-135">Finland (FI)</span></span>
- <span data-ttu-id="15709-136">Unión Europea (UE)</span><span class="sxs-lookup"><span data-stu-id="15709-136">The European Union (EU)</span></span>

<span data-ttu-id="15709-137">Las configuraciones de modelos de datos para **Modelo de factura**, asignación de modelos de facturas y de formatos de informes electrónicos específicos para un país o región incluyen:</span><span class="sxs-lookup"><span data-stu-id="15709-137">The **Invoice model** data model, invoice model mapping, and country/region-specific ER format configurations include:</span></span>

-   <span data-ttu-id="15709-138">Factura de ventas de OIOUBL - para AT, DK, y NO</span><span class="sxs-lookup"><span data-stu-id="15709-138">OIOUBL Sales invoice - for AT, DK, and NO</span></span>
-   <span data-ttu-id="15709-139">Nota de abono de OIOUBL - para AT, DK, y NO</span><span class="sxs-lookup"><span data-stu-id="15709-139">OIOUBL Sales credit note - for AT, DK, and NO</span></span>
-   <span data-ttu-id="15709-140">Factura de proyecto de OIOUBL - para AT, DK, y NO</span><span class="sxs-lookup"><span data-stu-id="15709-140">OIOUBL Project invoice - for AT, DK, and NO</span></span>
-   <span data-ttu-id="15709-141">Nota de abono de proyecto OIOUBL - para AT, DK, y NO</span><span class="sxs-lookup"><span data-stu-id="15709-141">OIOUBL Project credit note - for AT, DK, and NO</span></span>
-   <span data-ttu-id="15709-142">Factura de ventas de UBL para FR</span><span class="sxs-lookup"><span data-stu-id="15709-142">UBL Sales Invoice FR</span></span>
-   <span data-ttu-id="15709-143">Nota de abono de ventas de UBL para FR</span><span class="sxs-lookup"><span data-stu-id="15709-143">UBL Sales Credit Note FR</span></span>
-   <span data-ttu-id="15709-144">Factura del proyecto de UBL para FR</span><span class="sxs-lookup"><span data-stu-id="15709-144">UBL Project Invoice FR</span></span>
-   <span data-ttu-id="15709-145">Nota de abono de proyecto de UBL para FR</span><span class="sxs-lookup"><span data-stu-id="15709-145">UBL Project Credit Note FR</span></span>
-   <span data-ttu-id="15709-146">Factura de ventas de UBL para BE</span><span class="sxs-lookup"><span data-stu-id="15709-146">UBL Sales Invoice BE</span></span>
-   <span data-ttu-id="15709-147">Nota de abono de ventas de UBL para BE</span><span class="sxs-lookup"><span data-stu-id="15709-147">UBL Sales Credit Note BE</span></span>
-   <span data-ttu-id="15709-148">Factura de proyecto de UBL para BE</span><span class="sxs-lookup"><span data-stu-id="15709-148">UBL Project Invoice BE</span></span>
-   <span data-ttu-id="15709-149">Nota de abono de proyecto de UBL para BE</span><span class="sxs-lookup"><span data-stu-id="15709-149">UBL Project Credit Note BE</span></span>
-   <span data-ttu-id="15709-150">Factura de ventas de UBL para NL</span><span class="sxs-lookup"><span data-stu-id="15709-150">UBL Sales Invoice NL</span></span>
-   <span data-ttu-id="15709-151">Nota de abono de ventas de UBL para NL</span><span class="sxs-lookup"><span data-stu-id="15709-151">UBL Sales Credit Note NL</span></span>
-   <span data-ttu-id="15709-152">Factura de proyecto de UBL para NL</span><span class="sxs-lookup"><span data-stu-id="15709-152">UBL Project Invoice NL</span></span>
-   <span data-ttu-id="15709-153">Nota de abono de proyecto de UBL para NL</span><span class="sxs-lookup"><span data-stu-id="15709-153">UBL Project Credit Note NL</span></span> 
-   <span data-ttu-id="15709-154">Factura de ventas (ES)</span><span class="sxs-lookup"><span data-stu-id="15709-154">Sales invoice (ES)</span></span>
-   <span data-ttu-id="15709-155">Factura de ventas (IT)</span><span class="sxs-lookup"><span data-stu-id="15709-155">Sales invoice (IT)</span></span>
-   <span data-ttu-id="15709-156">Factura de proyecto (ES)</span><span class="sxs-lookup"><span data-stu-id="15709-156">Project invoice (ES)</span></span>
-   <span data-ttu-id="15709-157">Factura de proyecto (IT)</span><span class="sxs-lookup"><span data-stu-id="15709-157">Project invoice (IT)</span></span>
-   <span data-ttu-id="15709-158">Factura de ventas DE</span><span class="sxs-lookup"><span data-stu-id="15709-158">Sales Invoice DE</span></span>
-   <span data-ttu-id="15709-159">Factura de proyecto DE</span><span class="sxs-lookup"><span data-stu-id="15709-159">Project Invoice DE</span></span>
-   <span data-ttu-id="15709-160">Factura de ventas de Peppol - para la UE</span><span class="sxs-lookup"><span data-stu-id="15709-160">Peppol Sales Invoice - for EU</span></span>
-   <span data-ttu-id="15709-161">Nota de crédito de ventas de Peppol - para la UE</span><span class="sxs-lookup"><span data-stu-id="15709-161">Peppol Sales Credit Note - for EU</span></span>
-   <span data-ttu-id="15709-162">Factura de proyecto de Peppol - para la UE</span><span class="sxs-lookup"><span data-stu-id="15709-162">Peppol Project Invoice - for EU</span></span>
-   <span data-ttu-id="15709-163">Nota de crédito de proyecto de Peppol - para la UE</span><span class="sxs-lookup"><span data-stu-id="15709-163">Peppol Project Credit Note - for EU</span></span>
-   <span data-ttu-id="15709-164">Factura de ventas (EE)</span><span class="sxs-lookup"><span data-stu-id="15709-164">Sales invoice (EE)</span></span>
-   <span data-ttu-id="15709-165">Factura de proyecto (EE)</span><span class="sxs-lookup"><span data-stu-id="15709-165">Project invoice (EE)</span></span>
-   <span data-ttu-id="15709-166">Factura de ventas (FI)</span><span class="sxs-lookup"><span data-stu-id="15709-166">Sales invoice (FI)</span></span>
-   <span data-ttu-id="15709-167">Factura del proyecto (FI)</span><span class="sxs-lookup"><span data-stu-id="15709-167">Project invoice (FI)</span></span>

<span data-ttu-id="15709-168">Las facturas electrónicas y las notas de abono que genera incluyen la información requerida, como el número EAN (número europeo de artículo), la persona de contacto, el número de la cuenta de dimensión y la información de la dirección del cliente.</span><span class="sxs-lookup"><span data-stu-id="15709-168">The electronic invoices and credit notes that you generate include required information, such as a European Article Numbering (EAN) number, contact person, dimension account number, and address information for the customer.</span></span> <span data-ttu-id="15709-169">Se aplican reglas de validación cuando se generan facturas, de modo que puede verificar que se haya especificado la información correcta.</span><span class="sxs-lookup"><span data-stu-id="15709-169">Validation rules are applied when invoices are generated so you can verify that the correct information has been entered.</span></span> <span data-ttu-id="15709-170">El conjunto de información necesaria puede ser diferente de un país a otro.</span><span class="sxs-lookup"><span data-stu-id="15709-170">The set of required information may differ from country to country.</span></span> <span data-ttu-id="15709-171">Como los requisitos, al igual que los formatos y los países admitidos, están sujetos a cambios, debe ir siempre a la biblioteca de activos compartidos de Microsoft Dynamics Lifecycle Services (LCS) y ver la lista más actualizada de archivos disponibles que tienen un tipo de activo de **configuración de GER**.</span><span class="sxs-lookup"><span data-stu-id="15709-171">Because the requirements, as well as supported countries and formats, is subject to change, you should always go to the Shared asset library on Microsoft Dynamics Lifecycle Services (LCS) and view the most up-to-date list of available files that have an asset type of **GER configuration**.</span></span>

## <a name="electronic-invoice-configuration"></a><span data-ttu-id="15709-172">Configuración de facturas electrónicas</span><span class="sxs-lookup"><span data-stu-id="15709-172">Electronic invoice configuration</span></span>
<span data-ttu-id="15709-173">La configuración y los detalles de las facturas electrónicas dependen del país o región para el que se implementan.</span><span class="sxs-lookup"><span data-stu-id="15709-173">The setup and specifics of electronic invoices depend on the country/region that it's implemented for.</span></span> <span data-ttu-id="15709-174">Para obtener más información sobre cómo configurar y utilizar las facturas electrónicas de los clientes, consulte los temas relacionados específicos de cada país:</span><span class="sxs-lookup"><span data-stu-id="15709-174">For more information about how to set up and use customer electronic invoices, see the related country-specific topics:</span></span>

- [<span data-ttu-id="15709-175">Italia</span><span class="sxs-lookup"><span data-stu-id="15709-175">Italy</span></span>](emea-ita-e-invoices.md)
- [<span data-ttu-id="15709-176">Noruega</span><span class="sxs-lookup"><span data-stu-id="15709-176">Norway</span></span>](emea-nor-e-invoices.md)
- [<span data-ttu-id="15709-177">Alemania</span><span class="sxs-lookup"><span data-stu-id="15709-177">Germany</span></span>](emea-deu-e-invoices.md)
- [<span data-ttu-id="15709-178">Finlandia</span><span class="sxs-lookup"><span data-stu-id="15709-178">Finland</span></span>](https://support.microsoft.com/help/4559937)
- [<span data-ttu-id="15709-179">Estonia</span><span class="sxs-lookup"><span data-stu-id="15709-179">Estonia</span></span>](https://support.microsoft.com/help/4552679)
- [<span data-ttu-id="15709-180">PEPPOL</span><span class="sxs-lookup"><span data-stu-id="15709-180">PEPPOL</span></span>](https://support.microsoft.com/help/4490320)

## <a name="additional-resources"></a><span data-ttu-id="15709-181">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="15709-181">Additional resources</span></span>
<span data-ttu-id="15709-182">Para obtener más información acerca de cómo configurar facturas electrónicas, puede reproducir las siguientes [Guías de la tarea](../../fin-and-ops/get-started/help-overview.md#task-guides) en el panel de la Ayuda:</span><span class="sxs-lookup"><span data-stu-id="15709-182">For more details about how to set up electronic invoices, you can play the following [Task guides](../../fin-and-ops/get-started/help-overview.md#task-guides) in the Help pane:</span></span>

 - <span data-ttu-id="15709-183">Configurar la facturación electrónica OIOUBL</span><span class="sxs-lookup"><span data-stu-id="15709-183">Set up OIOUBL electronic invoicing</span></span>
 - <span data-ttu-id="15709-184">Importar configuraciones de facturación electrónica OIOUBL</span><span class="sxs-lookup"><span data-stu-id="15709-184">Import OIOUBL electronic invoicing configurations</span></span>
 - <span data-ttu-id="15709-185">Configurar cuentas de cliente para la facturación electrónica OIOUBL</span><span class="sxs-lookup"><span data-stu-id="15709-185">Set up customer accounts for OIOUBL electronic invoicing</span></span>

> [!NOTE] 
> <span data-ttu-id="15709-186">Aunque estas guías de la tarea fueron creadas para el formato de factura *OIOUBL* específicamente danés, son aplicables en otros países o regiones compatibles con desviaciones de menor importancia.</span><span class="sxs-lookup"><span data-stu-id="15709-186">Although these Task guides were created for Danish-specific e-invoice format *OIOUBL*, they are applicable for other supported countries/regions with minor deviations.</span></span>


[!INCLUDE[footer-include](../../includes/footer-banner.md)]