---
title: Declaración de retención de impuestos para Egipto
description: Este tema explica cómo configurar y generar las declaraciones de retención de impuestos para Egipto.
author: sndray
ms.date: 03/08/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.search.scope: ''
ms.search.region: Global
ms.author: tfehr
ms.search.validFrom: 2017-06-20
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: e0d13a2de9acaa8b1c896e130b4dabb222e45dcb
ms.sourcegitcommit: d18d9cdb175c9d42eafbed66352c24b2aa94258b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/13/2021
ms.locfileid: "5881431"
---
#  <a name="withholding-tax-declaration-for-egypt-eg-00005"></a><span data-ttu-id="fd9c3-103">Declaración de retención de impuestos para Egipto (EG-00005)</span><span class="sxs-lookup"><span data-stu-id="fd9c3-103">Withholding tax declaration for Egypt (EG-00005)</span></span>

[!include[banner](../includes/banner.md)]

[!include[banner](../includes/preview-banner.md)]

## <a name="overview"></a><span data-ttu-id="fd9c3-104">Información general</span><span class="sxs-lookup"><span data-stu-id="fd9c3-104">Overview</span></span>
<span data-ttu-id="fd9c3-105">Este tema explica cómo configurar y generar la declaración de retención de impuestos y los formularios 41 y 11 de declaración de retención de impuestos para entidades legales en Egipto</span><span class="sxs-lookup"><span data-stu-id="fd9c3-105">This topic explains how to set up and generate the withholding tax declaration and the withholding tax declaration forms 41 and 11 for legal entities in Egypt</span></span> 

<span data-ttu-id="fd9c3-106">Todas las entidades egipcias deben preparar el formulario 41 que resume todos los impuestos que se retienen de los proveedores locales y proveedores de servicios.</span><span class="sxs-lookup"><span data-stu-id="fd9c3-106">All Egyptian entities must prepare the form  41 which summarizes all taxes that are retained from local suppliers and service providers.</span></span> <span data-ttu-id="fd9c3-107">Además del formulario 41, se debe generar el formulario 11 para detallar todos los impuestos retenidos de proveedores extranjeros.</span><span class="sxs-lookup"><span data-stu-id="fd9c3-107">In addition to form 41, form 11 must be generated to detail all of the retained taxed from foreign providers.</span></span> 

<span data-ttu-id="fd9c3-108">El informe **Declaración de retención de impuestos** de Dynamics 365 Finance incluye los siguientes informes:</span><span class="sxs-lookup"><span data-stu-id="fd9c3-108">The **Withholding tax declaration** report in Dynamics 365 Finance includes the following reports:</span></span>

- <span data-ttu-id="fd9c3-109">Número de formulario de declaración.</span><span class="sxs-lookup"><span data-stu-id="fd9c3-109">Declaration form No.</span></span> <span data-ttu-id="fd9c3-110">41</span><span class="sxs-lookup"><span data-stu-id="fd9c3-110">41</span></span>
- <span data-ttu-id="fd9c3-111">Número de formulario de declaración.</span><span class="sxs-lookup"><span data-stu-id="fd9c3-111">Declaration form No.</span></span> <span data-ttu-id="fd9c3-112">11</span><span class="sxs-lookup"><span data-stu-id="fd9c3-112">11</span></span>
    
    
## <a name="prerequisites"></a><span data-ttu-id="fd9c3-113">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="fd9c3-113">Prerequisites</span></span>
<span data-ttu-id="fd9c3-114">La dirección principal de la entidad jurídica debe estar en Egipto.</span><span class="sxs-lookup"><span data-stu-id="fd9c3-114">The primary address of the legal entity must be in Egypt.</span></span>
<span data-ttu-id="fd9c3-115">En el espacio de trabajo **Administración de funciones**, active las siguientes características:</span><span class="sxs-lookup"><span data-stu-id="fd9c3-115">In the **Feature management** workspace, the following feature must be enabled:</span></span>

   - <span data-ttu-id="fd9c3-116">**Retención de impuestos global**</span><span class="sxs-lookup"><span data-stu-id="fd9c3-116">**Global withholding tax**</span></span>

<span data-ttu-id="fd9c3-117">Para obtener más información acerca de cómo habilitar características, consulte [Visión general de la Administración de características.](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md)</span><span class="sxs-lookup"><span data-stu-id="fd9c3-117">For more information about how to enable features, see [Feature management overview.](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md)</span></span>

1. <span data-ttu-id="fd9c3-118">Vaya a **Impuesto** > **Configuración** > **Parámetros** > **Parámetros del libro mayor** y luego, en la pestaña **Retención de impuestos**, establezca **Habilitar la retención de impuestos global** en **Sí**.</span><span class="sxs-lookup"><span data-stu-id="fd9c3-118">Go to **Tax** > **Setup** > **Parameters** > **General ledger parameters**, and on the **Withholding tax** tab, set **Enable global withholding tax** to **Yes**.</span></span>
2. <span data-ttu-id="fd9c3-119">En el espacio de trabajo **Informes electrónicos**, importe los siguientes formatos de informes electrónicos desde el repositorio:</span><span class="sxs-lookup"><span data-stu-id="fd9c3-119">In the **Electronic reporting** workspace, import the following Electronic reporting formats from the repository:</span></span>

    - <span data-ttu-id="fd9c3-120">Excel de declaración de WHT (EG)</span><span class="sxs-lookup"><span data-stu-id="fd9c3-120">WHT Declaration Excel (EG)</span></span>

    > [!NOTE]
    > <span data-ttu-id="fd9c3-121">El formato anterior se basa en el **Modelo de declaración de impuestos** y usa la **Asignación de modelos de declaración de impuestos**.</span><span class="sxs-lookup"><span data-stu-id="fd9c3-121">The format above is based on the **Tax declaration model** and uses the **Tax declaration model mapping**.</span></span> <span data-ttu-id="fd9c3-122">Esta configuración adicional se importa automáticamente.</span><span class="sxs-lookup"><span data-stu-id="fd9c3-122">This additional configuration is automatically imported.</span></span>

<span data-ttu-id="fd9c3-123">Para obtener más información sobre cómo importar configuraciones de informes electrónicos, consulte [Descargar configuraciones de informes electrónicos de Lifecycle Services](../../fin-ops-core/dev-itpro/analytics/download-electronic-reporting-configuration-lcs.md).</span><span class="sxs-lookup"><span data-stu-id="fd9c3-123">For more information about how to import Electronic reporting configurations, see [Download Electronic reporting configurations from Lifecycle Services](../../fin-ops-core/dev-itpro/analytics/download-electronic-reporting-configuration-lcs.md).</span></span>

## <a name="download-electronic-reporting-configurations"></a><span data-ttu-id="fd9c3-124">Descargar configuraciones de informes electrónicos</span><span class="sxs-lookup"><span data-stu-id="fd9c3-124">Download Electronic reporting configurations</span></span>

<span data-ttu-id="fd9c3-125">La implementación de los formularios de declaración WHT para Egipto se basa en configuraciones de informes electrónicos (ER).</span><span class="sxs-lookup"><span data-stu-id="fd9c3-125">The implementation of the WHT declaration forms for Egypt is based on Electronic reporting (ER) configurations.</span></span> <span data-ttu-id="fd9c3-126">Para obtener más información sobre las capacidades y los conceptos de los informes configurables, consulte [Informes electrónicos](../../fin-ops-core/dev-itpro/analytics/general-electronic-reporting.md).</span><span class="sxs-lookup"><span data-stu-id="fd9c3-126">For more information about the capabilities and concepts of configurable reporting, see [Electronic reporting](../../fin-ops-core/dev-itpro/analytics/general-electronic-reporting.md).</span></span>

<span data-ttu-id="fd9c3-127">Para entornos de producción y pruebas de aceptación del usuario (UAT), siga las instrucciones del tema, [Descargar configuraciones de informes electrónicos de Lifecycle Services](../../fin-ops-core/dev-itpro/analytics/download-electronic-reporting-configuration-lcs.md).</span><span class="sxs-lookup"><span data-stu-id="fd9c3-127">For production and user acceptance testing (UAT) environments, follow the instructions in the topic, [Download Electronic reporting configurations from Lifecycle Services](../../fin-ops-core/dev-itpro/analytics/download-electronic-reporting-configuration-lcs.md).</span></span>

<span data-ttu-id="fd9c3-128">Para generar las declaraciones de retención en una entidad jurídica egipcia, debe cargar las siguientes configuraciones:</span><span class="sxs-lookup"><span data-stu-id="fd9c3-128">To generate the Withholding declarations in an Egyptian legal entity, you need to upload the following configurations:</span></span>

- <span data-ttu-id="fd9c3-129">Modelo de declaración de impuestos model.version.82.xml o versión posterior</span><span class="sxs-lookup"><span data-stu-id="fd9c3-129">Tax declaration model.version.82.xml or later version</span></span>
- <span data-ttu-id="fd9c3-130">Modelo de declaración de impuestos mapping.version.82.133.xml o versión posterior</span><span class="sxs-lookup"><span data-stu-id="fd9c3-130">Tax declaration model mapping.version.82.133.xml or a later version</span></span>
- <span data-ttu-id="fd9c3-131">Excel de declaración WHT (EG).version.82.21 o versión posterior</span><span class="sxs-lookup"><span data-stu-id="fd9c3-131">WHT Declaration Excel (EG).version.82.21  or a later version</span></span>

<span data-ttu-id="fd9c3-132">Una vez que haya terminado de descargar las configuraciones de ER desde Lifecycle Services (LCS) o el repositorio global, complete los siguientes pasos.</span><span class="sxs-lookup"><span data-stu-id="fd9c3-132">After you finish downloading the ER configurations from Lifecycle Services (LCS) or the global repository, complete the following steps.</span></span>

1. <span data-ttu-id="fd9c3-133">Vaya al espacio de trabajo **Informes electrónicos** y seleccione el mosaico **Configuraciones de informes** .</span><span class="sxs-lookup"><span data-stu-id="fd9c3-133">Go to the **Electronic reporting** workspace and select the **Reporting configurations** tile.</span></span>
1. <span data-ttu-id="fd9c3-134">En la página **Configuraciones**, en el panel de acciones, seleccione **Exchange > Cargar desde archivo XML**.</span><span class="sxs-lookup"><span data-stu-id="fd9c3-134">On the **Configurations** page, on the Action Pane, select **Exchange > Load from XML file**.</span></span>
1. <span data-ttu-id="fd9c3-135">Cargue todos los archivos en el orden en que aparecen en las viñetas anteriores.</span><span class="sxs-lookup"><span data-stu-id="fd9c3-135">Upload all the files in the order in which they are listed in the previous bullets.</span></span> <span data-ttu-id="fd9c3-136">Una vez cargadas todas las configuraciones, el árbol de configuración debe estar presente en Finance.</span><span class="sxs-lookup"><span data-stu-id="fd9c3-136">After all of the configurations are uploaded, the configuration tree should be present in Finance.</span></span>

## <a name="set-up-application-specific-parameters"></a><span data-ttu-id="fd9c3-137">Configurar parámetros específicos de la aplicación</span><span class="sxs-lookup"><span data-stu-id="fd9c3-137">Set up application-specific parameters</span></span>

<span data-ttu-id="fd9c3-138">La opción de parámetros específicos de la aplicación permite a los usuarios establecer los criterios de cómo se clasificarán y calcularán las transacciones fiscales en cada línea de un informe generado en función de la configuración del **grupo de partidas de retención de impuestos** u otros criterios establecidos en la definición de búsqueda.</span><span class="sxs-lookup"><span data-stu-id="fd9c3-138">The application-specific parameters option lets users establish the criteria of how the tax transactions will be classified and calculated in each line of a generated report depending on the configuration of **withholding tax item group** or other criteria established in the definition of lookup.</span></span>

<span data-ttu-id="fd9c3-139">El formulario de declaración de retenciones 41 incluye una columna específica donde la transacción de retención de impuestos debe clasificarse de acuerdo con la clasificación de la autoridad tributaria denominada **Tipo de código de descuento**.</span><span class="sxs-lookup"><span data-stu-id="fd9c3-139">Withholding declaration form 41 includes a specific column where the withholding tax transaction must be classified in accordance with the tax authority classification named **Discount code type**.</span></span> <span data-ttu-id="fd9c3-140">En lugar de incluir estas nuevas clasificaciones como nuevos datos de entrada cuando se publican las transacciones, las clasificaciones se determinarán en función de las diferentes búsquedas introducidas en **Configuraciones** > **Configurar parámetros específicos de la aplicación** > **Configuración** para cumplir con los requisitos de los informes de retención para Egipto.</span><span class="sxs-lookup"><span data-stu-id="fd9c3-140">Instead of including these new classifications as new entry data when the transactions are posted, the classifications will be determined based on the different lookups introduced in **Configurations** > **Set up application-specific parameters** > **Setup** to meet the requirements of withholding reports for Egypt.</span></span> 

<span data-ttu-id="fd9c3-141">La siguiente configuración se utiliza para clasificar las transacciones en el informe del formulario 41 de declaración de retenciones:</span><span class="sxs-lookup"><span data-stu-id="fd9c3-141">The following configuration is used to classify the transactions in the Withholding declaration form 41 report:</span></span>

- <span data-ttu-id="fd9c3-142">**DiscountTaxTypeLookup** -> Columna n.º 18</span><span class="sxs-lookup"><span data-stu-id="fd9c3-142">**DiscountTaxTypeLookup**-> Column No 18</span></span> 

<span data-ttu-id="fd9c3-143">Complete los siguientes pasos para configurar las diferentes búsquedas utilizadas para generar la declaración WHT y los informes de libros relacionados.</span><span class="sxs-lookup"><span data-stu-id="fd9c3-143">Complete the following steps to set up the different lookups used to generate the WHT declaration and related books reports.</span></span> 

1. <span data-ttu-id="fd9c3-144">En el espacio de trabajo **Informes electrónicos**, seleccione **Configuraciones** > **Configuración** para configurar las reglas para identificar cómo se clasifican las transacciones en el informe de declaración WHT.</span><span class="sxs-lookup"><span data-stu-id="fd9c3-144">In the **Electronic reporting** workspace, select **Configurations** > **Setup** to set up the rules to identify how transactions are classified in the WHT declaration report.</span></span> 
2. <span data-ttu-id="fd9c3-145">Seleccione la versión actual y en la ficha desplegable **Búsquedas**, seleccione el nombre de búsqueda.</span><span class="sxs-lookup"><span data-stu-id="fd9c3-145">Select the current version, and on the **Lookups** FastTab, select the lookup name.</span></span> <span data-ttu-id="fd9c3-146">Por ejemplo, **DiscountTaxTypeLookup**.</span><span class="sxs-lookup"><span data-stu-id="fd9c3-146">For example, **DiscountTaxTypeLookup**.</span></span> <span data-ttu-id="fd9c3-147">Esta búsqueda identifica la lista de tipos de descuento requeridos por la autoridad fiscal.</span><span class="sxs-lookup"><span data-stu-id="fd9c3-147">This lookup identifies the list of discount types required by the tax authority.</span></span>
3. <span data-ttu-id="fd9c3-148">En la ficha desplegable **Condiciones**, seleccione **Agregar** y, en la nueva línea de la columna **Resultado de la búsqueda**, seleccione la línea relacionada que representa la clasificación en la **Columna 18**.</span><span class="sxs-lookup"><span data-stu-id="fd9c3-148">On the **Conditions** FastTab, select **Add** and in the new line in the **Lookup result** column, select the related line that represents the classification in the **Column 18**.</span></span>
4. <span data-ttu-id="fd9c3-149">En la columna **Grupo de elementos de retención de impuestos**, seleccione el código relacionado que se utiliza para identificar la clasificación.</span><span class="sxs-lookup"><span data-stu-id="fd9c3-149">In the **Withholding tax item group** column, select the related code that's used to identify the classification.</span></span> <span data-ttu-id="fd9c3-150">Por ejemplo, **Descuento permitido**.</span><span class="sxs-lookup"><span data-stu-id="fd9c3-150">For example, **Allowed discount**.</span></span>  
5. <span data-ttu-id="fd9c3-151">Repita los pasos 3 y 4 para todas las búsquedas disponibles.</span><span class="sxs-lookup"><span data-stu-id="fd9c3-151">Repeat steps 3 and 4 for all available lookups.</span></span>
6. <span data-ttu-id="fd9c3-152">Seleccione **Agregar** de nuevo para incluir la línea de registro final y, en la columna **Resultado de la búsqueda**, seleccione **No aplicable**.</span><span class="sxs-lookup"><span data-stu-id="fd9c3-152">Select **Add** again to include the final record line, and in the **Lookup result** column, select **Not applicable**.</span></span> 
7. <span data-ttu-id="fd9c3-153">En las columnas restantes, seleccione **No en blanco**.</span><span class="sxs-lookup"><span data-stu-id="fd9c3-153">In the remaining columns, select **Not blank**.</span></span> 

> [!NOTE]

## <a name="set-up-general-ledger-parameters"></a><span data-ttu-id="fd9c3-154">Configurar los parámetros de Contabilidad general</span><span class="sxs-lookup"><span data-stu-id="fd9c3-154">Set up General ledger parameters</span></span>

<span data-ttu-id="fd9c3-155">Para generar los informes del formulario de declaración WHT en Microsoft Excel, defina un formato ER en la página **Parámetros del libro mayor**.</span><span class="sxs-lookup"><span data-stu-id="fd9c3-155">To generate the WHT declaration form reports in Microsoft Excel, define an ER format on the **General ledger parameters** page.</span></span>

1. <span data-ttu-id="fd9c3-156">Vaya a **Impuesto** > **Configuración** > **Parámetros del libro mayor**.</span><span class="sxs-lookup"><span data-stu-id="fd9c3-156">Go to **Tax** > **Setup** > **General ledger parameters**.</span></span>
2. <span data-ttu-id="fd9c3-157">En la pestaña **Retención de impuestos**, en el campo **Asignación de formato de declaración WHT**, seleccione **Excel de declaración WHT (EG)**.</span><span class="sxs-lookup"><span data-stu-id="fd9c3-157">On the **Withholding tax** tab, in the **WHT declaration format mapping** field, select **WHT Declaration Excel (EG)**.</span></span> <span data-ttu-id="fd9c3-158">Si deja el campo en blanco, el informe estándar de impuestos sobre las ventas se generará en formato SSRS.</span><span class="sxs-lookup"><span data-stu-id="fd9c3-158">If you leave the field blank, the standard sales tax report will be generated in SSRS format.</span></span>


![Formulario de declaración](media/egypt-wht-declaration-setup1.png)

## <a name="generate-the-withholding-declaration-forms"></a><span data-ttu-id="fd9c3-160">Generar los formularios de declaración de retención</span><span class="sxs-lookup"><span data-stu-id="fd9c3-160">Generate the Withholding declaration forms</span></span>
<span data-ttu-id="fd9c3-161">El proceso de preparación y envío de un formulario de declaración de retención para un período específico se basa en las transacciones de retención de impuestos contabilizadas durante el trabajo de liquidación y contabilización de pago de impuestos.</span><span class="sxs-lookup"><span data-stu-id="fd9c3-161">The process of preparing and submitting a Withholding declaration form for a specific period is based on the withholding tax transactions posted during the settle and post payment tax job.</span></span> <span data-ttu-id="fd9c3-162">Para obtener más información sobre la retención de impuestos global, consulte [Retención global de impuestos](../general-ledger/global-withholding-tax-overview.md).</span><span class="sxs-lookup"><span data-stu-id="fd9c3-162">For more information about global withholding tax, see [Global withholding tax](../general-ledger/global-withholding-tax-overview.md).</span></span>

<span data-ttu-id="fd9c3-163">Complete los pasos siguientes para generar un informe de declaración de impuestos.</span><span class="sxs-lookup"><span data-stu-id="fd9c3-163">Complete the following steps to generate the tax declaration report.</span></span>

1. <span data-ttu-id="fd9c3-164">Vaya a **Impuesto** > **Declaraciones** > **Retención de impuestos** > \**Pago de retención de impuestos*.</span><span class="sxs-lookup"><span data-stu-id="fd9c3-164">Go to **Tax** > **Declarations** > **Withholding tax** > \**Withholding tax payment*.</span></span>
2. <span data-ttu-id="fd9c3-165">Seleccione el período de liquidación y luego seleccione la fecha de inicio para el informe.</span><span class="sxs-lookup"><span data-stu-id="fd9c3-165">Select the settlement period and then select the from date for the report.</span></span> 
3. <span data-ttu-id="fd9c3-166">Escriba la fecha de la transacción y luego seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="fd9c3-166">Enter the transaction date and then select **OK**.</span></span>
4. <span data-ttu-id="fd9c3-167">En el cuadro de diálogo que se abre, seleccione uno o más de los tipos de formulario **Formulario N.º 41**, **Formulario N.º 11** o **Ninguno**.</span><span class="sxs-lookup"><span data-stu-id="fd9c3-167">In the dialog box that opens, select one or more of the form types \*\*Form No 41 \*\*, **Form No 11**, or **None**.</span></span> <span data-ttu-id="fd9c3-168">Si selecciona **Ninguno**, se genera el informe estándar.</span><span class="sxs-lookup"><span data-stu-id="fd9c3-168">If you select **None**, the standard report is generated.</span></span> 
5. <span data-ttu-id="fd9c3-169">Seleccione el idioma.</span><span class="sxs-lookup"><span data-stu-id="fd9c3-169">Select the language.</span></span> <span data-ttu-id="fd9c3-170">Todos los informes se traducen en **en-us** y **ar-eg**.</span><span class="sxs-lookup"><span data-stu-id="fd9c3-170">All reports are translated in **en-us** and **ar-eg**.</span></span>
6. <span data-ttu-id="fd9c3-171">Introduzca la sucursal y el nombre del banco donde se pagará el impuesto.</span><span class="sxs-lookup"><span data-stu-id="fd9c3-171">Enter the branch and name of the bank where the tax payment will be paid.</span></span>
7. <span data-ttu-id="fd9c3-172">Seleccione el tipo de negocio y luego introduzca los números de cheque y documento.</span><span class="sxs-lookup"><span data-stu-id="fd9c3-172">Select the business type and then enter the check and document numbers.</span></span> 
8. <span data-ttu-id="fd9c3-173">Introduzca el tipo de entidad.</span><span class="sxs-lookup"><span data-stu-id="fd9c3-173">Enter the entity type.</span></span> 
9. <span data-ttu-id="fd9c3-174">Introduzca el nombre de la persona registrada para asignar el formulario y seleccione **Aceptar** para confirmar la generación del informe.</span><span class="sxs-lookup"><span data-stu-id="fd9c3-174">Enter the name of person registered to assign the form and select **OK** to confirm the report generation.</span></span> 

 
[!INCLUDE[footer-include](../../includes/footer-banner.md)]
