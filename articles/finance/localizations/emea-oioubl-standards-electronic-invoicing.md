---
title: Estándares compatibles para la facturación electrónica en Europa
description: Este tema explica el nivel de cobertura que existe en la facturación electrónica para Europa.
author: mrolecki
manager: AnnBe
ms.date: 07/11/2017
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
ms.openlocfilehash: c1d1ec695626404389dec2b07dd6e34358cd2d5a
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/27/2019
ms.locfileid: "2175724"
---
# <a name="supported-standards-for-electronic-invoicing-in-europe"></a><span data-ttu-id="07bcf-103">Estándares compatibles para la facturación electrónica en Europa</span><span class="sxs-lookup"><span data-stu-id="07bcf-103">Supported standards for electronic invoicing in Europe</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="07bcf-104">Este tema explica el nivel de cobertura que existe en la facturación electrónica para Europa.</span><span class="sxs-lookup"><span data-stu-id="07bcf-104">This topic explains the level of coverage that exists for electronic invoicing for Europe.</span></span> 

<span data-ttu-id="07bcf-105">La implementación y la adopción de la facturación electrónica a escala de la Unión Europea está regulada por la [Directiva del Consejo 2010/45/EU](https://eur-lex.europa.eu/LexUriServ/LexUriServ.do?uri=OJ:L:2010:189:0001:0008:EN:PDF), que afecta a todos los estados miembros de la UE.</span><span class="sxs-lookup"><span data-stu-id="07bcf-105">Implementation and adoption of European Union-wide electronic invoicing is regulated [Council Directive 2010/45/EU](https://eur-lex.europa.eu/LexUriServ/LexUriServ.do?uri=OJ:L:2010:189:0001:0008:EN:PDF), which affects all EU member states.</span></span> <span data-ttu-id="07bcf-106">Las empresas que desean beneficiarse de la facturación electrónica deben enviar las facturas de pedido de ventas, facturas de servicios, facturas de proyecto, notas de abono de pedidos de ventas, y notas de crédito de la factura de proyecto como archivos .xml al gobierno u otras partes comerciales que ordenen el uso de la facturación electrónica.</span><span class="sxs-lookup"><span data-stu-id="07bcf-106">Companies that want to benefit from electronic invoicing must submit sales order invoices, free text invoices, project invoices, sales order credit notes, and project invoice credit notes as .xml files to the government or other trading parties that mandate use of electronic invoicing.</span></span> <span data-ttu-id="07bcf-107">Estos archivos .xml deben cumplir determinados estándares.</span><span class="sxs-lookup"><span data-stu-id="07bcf-107">These .xml files must comply with certain standards.</span></span> <span data-ttu-id="07bcf-108">Los requisitos específicos de país y la implementación pueden ser diferentes en los estados miembros de la UE, pero suelen usar Universal Business Language ([UBL](https://www.oasis-open.org/committees/tc_home.php?wg_abbrev=ubl)) en diferentes versiones con personalizaciones junto con [PEPPOL](https://www.peppol.eu) especificaciones y puntos de acceso para la validación y el transporte.</span><span class="sxs-lookup"><span data-stu-id="07bcf-108">The country-specific requirements and their implementation may differ across EU member states but commonly they are using Universal Business Language ([UBL](https://www.oasis-open.org/committees/tc_home.php?wg_abbrev=ubl)) in different versions with customizations as well as [PEPPOL](https://www.peppol.eu) specifications and access points for validation and transportation.</span></span> <span data-ttu-id="07bcf-109">La ventaja principal del UBL es que los documentos empresariales se pueden estandarizar para distintos fines.</span><span class="sxs-lookup"><span data-stu-id="07bcf-109">The primary advantage of UBL is that business documents can be standardized for different purposes.</span></span> <span data-ttu-id="07bcf-110">Dado que el UBL es una norma flexible e internacional que admite muchos requisitos empresariales, estos documentos empresariales se pueden intercambiar a través de las fronteras nacionales.</span><span class="sxs-lookup"><span data-stu-id="07bcf-110">Because UBL is a flexible, international standard that supports many business requirements, these business documents can be exchanged across national borders.</span></span>

## <a name="what-electronic-invoice-formats-are-currently-available-in-dynamics-365-finance"></a><span data-ttu-id="07bcf-111">¿Qué formatos de factura electrónica se encuentran disponibles en Dynamics 365 Finance?</span><span class="sxs-lookup"><span data-stu-id="07bcf-111">What electronic invoice formats are currently available in Dynamics 365 Finance?</span></span>

<span data-ttu-id="07bcf-112">Los formatos específicos de país siguientes de facturas electrónicas están disponibles:</span><span class="sxs-lookup"><span data-stu-id="07bcf-112">The following country-specific formats of electronic invoices are available:</span></span>

-   <span data-ttu-id="07bcf-113">OIOUBL v.2.02 para Dinamarca</span><span class="sxs-lookup"><span data-stu-id="07bcf-113">OIOUBL v.2.02 for Denmark</span></span>
-   <span data-ttu-id="07bcf-114">EHF v.2.0.8 para Noruega</span><span class="sxs-lookup"><span data-stu-id="07bcf-114">EHF v.2.0.8 for Norway</span></span>
-   <span data-ttu-id="07bcf-115">PEPPOL BIS v. 2 para Austria, Francia, y Bélgica</span><span class="sxs-lookup"><span data-stu-id="07bcf-115">PEPPOL BIS v.2 for Austria, France, and Belgium</span></span>
-   <span data-ttu-id="07bcf-116">UBL-OHNL 1.9 para los Países Bajos</span><span class="sxs-lookup"><span data-stu-id="07bcf-116">UBL-OHNL 1.9 for the Netherlands</span></span>
-   <span data-ttu-id="07bcf-117">FacturaE v.3.2.1 para España</span><span class="sxs-lookup"><span data-stu-id="07bcf-117">FacturaE v.3.2.1 for Spain</span></span>
-   <span data-ttu-id="07bcf-118">FatturaPA v.1.2 para Italia</span><span class="sxs-lookup"><span data-stu-id="07bcf-118">FatturaPA v.1.2 for Italy</span></span>

<span data-ttu-id="07bcf-119">La facturación electrónica se basa en [informes electrónicos](../../dev-itpro/analytics/general-electronic-reporting.md).</span><span class="sxs-lookup"><span data-stu-id="07bcf-119">Electronic invoicing is based on [electronic reporting](../../dev-itpro/analytics/general-electronic-reporting.md).</span></span> <span data-ttu-id="07bcf-120">Existe un modelo de datos **Modelo de factura de cliente** y varias configuraciones de formato de informes electrónicos específicas para países creadas para Austria (AT), Dinamarca (DK), Italia (IT), Noruega (NO), España (ES), Francia (FR), Bélgica (BE) y Países Bajos (NL).</span><span class="sxs-lookup"><span data-stu-id="07bcf-120">There is a **Customer invoice model** data model and a number of country-specific electronic reporting format configurations created for Austria (AT), Denmark (DK), Italy (IT), Norway (NO), Spain (ES), France (FR), Belgium (BE), and the Netherlands (NL).</span></span>

-   <span data-ttu-id="07bcf-121">Factura de ventas de OIOUBL - para AT, DK, y NO</span><span class="sxs-lookup"><span data-stu-id="07bcf-121">OIOUBL Sales invoice - for AT, DK, and NO</span></span>
-   <span data-ttu-id="07bcf-122">Nota de abono de OIOUBL - para AT, DK, y NO</span><span class="sxs-lookup"><span data-stu-id="07bcf-122">OIOUBL Sales credit note - for AT, DK, and NO</span></span>
-   <span data-ttu-id="07bcf-123">Factura de proyecto de OIOUBL - para AT, DK, y NO</span><span class="sxs-lookup"><span data-stu-id="07bcf-123">OIOUBL Project invoice - for AT, DK, and NO</span></span>
-   <span data-ttu-id="07bcf-124">Nota de abono de proyecto OIOUBL - para AT, DK, y NO</span><span class="sxs-lookup"><span data-stu-id="07bcf-124">OIOUBL Project credit note - for AT, DK, and NO</span></span>
-   <span data-ttu-id="07bcf-125">Factura de ventas de UBL para FR</span><span class="sxs-lookup"><span data-stu-id="07bcf-125">UBL Sales Invoice FR</span></span>
-   <span data-ttu-id="07bcf-126">Nota de abono de ventas de UBL para FR</span><span class="sxs-lookup"><span data-stu-id="07bcf-126">UBL Sales Credit Note FR</span></span>
-   <span data-ttu-id="07bcf-127">Factura del proyecto de UBL para FR</span><span class="sxs-lookup"><span data-stu-id="07bcf-127">UBL Project Invoice FR</span></span>
-   <span data-ttu-id="07bcf-128">Nota de abono de proyecto de UBL para FR</span><span class="sxs-lookup"><span data-stu-id="07bcf-128">UBL Project Credit Note FR</span></span>
-   <span data-ttu-id="07bcf-129">Factura de ventas de UBL para BE</span><span class="sxs-lookup"><span data-stu-id="07bcf-129">UBL Sales Invoice BE</span></span>
-   <span data-ttu-id="07bcf-130">Nota de abono de ventas de UBL para BE</span><span class="sxs-lookup"><span data-stu-id="07bcf-130">UBL Sales Credit Note BE</span></span>
-   <span data-ttu-id="07bcf-131">Factura de proyecto de UBL para BE</span><span class="sxs-lookup"><span data-stu-id="07bcf-131">UBL Project Invoice BE</span></span>
-   <span data-ttu-id="07bcf-132">Nota de abono de proyecto de UBL para BE</span><span class="sxs-lookup"><span data-stu-id="07bcf-132">UBL Project Credit Note BE</span></span>
-   <span data-ttu-id="07bcf-133">Factura de ventas de UBL para NL</span><span class="sxs-lookup"><span data-stu-id="07bcf-133">UBL Sales Invoice NL</span></span>
-   <span data-ttu-id="07bcf-134">Nota de abono de ventas de UBL para NL</span><span class="sxs-lookup"><span data-stu-id="07bcf-134">UBL Sales Credit Note NL</span></span>
-   <span data-ttu-id="07bcf-135">Factura de proyecto de UBL para NL</span><span class="sxs-lookup"><span data-stu-id="07bcf-135">UBL Project Invoice NL</span></span>
-   <span data-ttu-id="07bcf-136">Nota de abono de proyecto de UBL para NL</span><span class="sxs-lookup"><span data-stu-id="07bcf-136">UBL Project Credit Note NL</span></span> 
-   <span data-ttu-id="07bcf-137">Factura de ventas (ES)</span><span class="sxs-lookup"><span data-stu-id="07bcf-137">Sales invoice (ES)</span></span>
-   <span data-ttu-id="07bcf-138">Factura de ventas (IT)</span><span class="sxs-lookup"><span data-stu-id="07bcf-138">Sales invoice (IT)</span></span>
-   <span data-ttu-id="07bcf-139">Factura de proyecto (ES)</span><span class="sxs-lookup"><span data-stu-id="07bcf-139">Project invoice (ES)</span></span>
-   <span data-ttu-id="07bcf-140">Factura de proyecto (IT)</span><span class="sxs-lookup"><span data-stu-id="07bcf-140">Project invoice (IT)</span></span>

<span data-ttu-id="07bcf-141">Las facturas electrónicas y las notas de abono que genera incluyen la información requerida, como el número EAN (número europeo de artículo), la persona de contacto, el número de la cuenta de dimensión y la información de la dirección del cliente.</span><span class="sxs-lookup"><span data-stu-id="07bcf-141">The electronic invoices and credit notes that you generate include required information, such as a European Article Numbering (EAN) number, contact person, dimension account number, and address information for the customer.</span></span> <span data-ttu-id="07bcf-142">Se aplican reglas de validación cuando se generan facturas, de modo que puede verificar que se haya especificado la información correcta.</span><span class="sxs-lookup"><span data-stu-id="07bcf-142">Validation rules are applied when invoices are generated so you can verify that the correct information has been entered.</span></span> <span data-ttu-id="07bcf-143">El conjunto de información necesaria puede ser diferente de un país a otro.</span><span class="sxs-lookup"><span data-stu-id="07bcf-143">The set of required information may differ from country to country.</span></span> <span data-ttu-id="07bcf-144">Como los requisitos, al igual que los formatos y los países admitidos, están sujetos a cambios, debe ir siempre a la biblioteca de activos compartidos de Microsoft Dynamics Lifecycle Services (LCS) y ver la lista más actualizada de archivos disponibles que tienen un tipo de activo de **configuración de GER**.</span><span class="sxs-lookup"><span data-stu-id="07bcf-144">Because the requirements, as well as supported countries and formats, is subject to change, you should always go to the Shared asset library on Microsoft Dynamics Lifecycle services (LCS) and view the most up-to-date list of available files that have an asset type of **GER configuration**.</span></span>

## <a name="additional-information"></a><span data-ttu-id="07bcf-145">Información adicional</span><span class="sxs-lookup"><span data-stu-id="07bcf-145">Additional information</span></span>
<span data-ttu-id="07bcf-146">Para obtener más información acerca de cómo configurar facturas electrónicas, puede reproducir las siguientes [Guías de la tarea](../../fin-and-ops/get-started/help-overview.md#task-guides) en el panel de la Ayuda:</span><span class="sxs-lookup"><span data-stu-id="07bcf-146">For more details about how to set up electronic invoices, you can play the following [Task guides](../../fin-and-ops/get-started/help-overview.md#task-guides) in the Help pane:</span></span>

 - <span data-ttu-id="07bcf-147">Configurar la facturación electrónica OIOUBL</span><span class="sxs-lookup"><span data-stu-id="07bcf-147">Set up OIOUBL electronic invoicing</span></span>
 - <span data-ttu-id="07bcf-148">Importar configuraciones de facturación electrónica OIOUBL</span><span class="sxs-lookup"><span data-stu-id="07bcf-148">Import OIOUBL electronic invoicing configurations</span></span>
 - <span data-ttu-id="07bcf-149">Configurar cuentas de cliente para la facturación electrónica OIOUBL</span><span class="sxs-lookup"><span data-stu-id="07bcf-149">Set up customer accounts for OIOUBL electronic invoicing</span></span>

> [!NOTE] 
> <span data-ttu-id="07bcf-150">Aunque estas guías de la tarea fueron creadas para el formato de factura *OIOUBL* específicamente danés, son aplicables en otros países compatibles con desviaciones de menor importancia.</span><span class="sxs-lookup"><span data-stu-id="07bcf-150">Although these Task guides were created for Danish-specific e-invoice format *OIOUBL*, they are applicable for other supported countries with minor deviations.</span></span>
