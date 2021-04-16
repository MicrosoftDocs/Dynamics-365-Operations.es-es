---
title: Habilitar las predicciones de pago de los clientes (versión preliminar)
description: Este tema explica cómo activar y configurar la característica de predicciones de pago de clientes en Finance Insights.
author: ShivamPandey-msft
ms.date: 05/27/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.custom: 14151
ms.assetid: 3d43ba40-780c-459a-a66f-9a01d556e674
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2020-05-29
ms.dyn365.ops.version: AX 10.0.12
ms.openlocfilehash: ecc3851cc91c8fe17a7582f2be06e84cf9bc2d83
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/01/2021
ms.locfileid: "5818665"
---
# <a name="enable-customer-payment-predictions-preview"></a><span data-ttu-id="4fb35-103">Habilitar las predicciones de pago de los clientes (versión preliminar)</span><span class="sxs-lookup"><span data-stu-id="4fb35-103">Enable customer payment predictions (preview)</span></span>

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

<span data-ttu-id="4fb35-104">Este tema explica cómo activar y configurar la característica de predicciones de pago de clientes en Finance Insights.</span><span class="sxs-lookup"><span data-stu-id="4fb35-104">This topic explains how to turn on and configure the Customer payment predictions feature in Finance insights.</span></span> <span data-ttu-id="4fb35-105">Active la característica en el espacio de trabajo **Administración de características** e introduzca los ajustes de configuración en la página **Parámetros de información financiera**.</span><span class="sxs-lookup"><span data-stu-id="4fb35-105">You turn on the feature in the **Feature management** workspace and enter configuration settings on the **Financial insights parameters** page.</span></span> <span data-ttu-id="4fb35-106">Este tema también incluye información que puede ayudarle a utilizar la característica de manera eficaz.</span><span class="sxs-lookup"><span data-stu-id="4fb35-106">This topic also includes information that can help you effectively use the feature.</span></span>

> [!NOTE]
> <span data-ttu-id="4fb35-107">Antes de completar los siguientes pasos, asegúrese de completar los pasos de requisitos previos en el tema [Configurar para información financiera](configure-for-fin-insites.md).</span><span class="sxs-lookup"><span data-stu-id="4fb35-107">Before you complete the following steps, be sure to complete the prerequisite steps in the [Configure for Finance insights](configure-for-fin-insites.md) topic.</span></span>

1. <span data-ttu-id="4fb35-108">Utilice la información de la página de entorno en Microsoft Dynamics Lifecycle Services (LCS) para conectarse a la instancia principal de Azure SQL para ese entorno.</span><span class="sxs-lookup"><span data-stu-id="4fb35-108">Use information from the environment page in Microsoft Dynamics Lifecycle Services (LCS) to connect to the primary instance of Azure SQL for that environment.</span></span> <span data-ttu-id="4fb35-109">Ejecute el siguiente comando Transact-SQL (T-SQL) para activar paquetes piloto para el entorno de espacio aislado.</span><span class="sxs-lookup"><span data-stu-id="4fb35-109">Run the following Transact-SQL (T-SQL) command to turn on flights for the sandbox environment.</span></span> <span data-ttu-id="4fb35-110">(Es posible que tenga que activar el acceso para su dirección IP en LCS antes de poder conectarse de forma remota a Application Object Server \[AOS\].)</span><span class="sxs-lookup"><span data-stu-id="4fb35-110">(You might have to turn on access for your IP address in LCS before you can connect remotely to Application Object Server \[AOS\].)</span></span>

    `INSERT INTO SYSFLIGHTING (FLIGHTNAME, ENABLED, PARTITION) VALUES ('PayPredEnableFeature', 1, 5637144576)`

    > [!NOTE]
    > <span data-ttu-id="4fb35-111">Si su implementación de Microsoft Dynamics 365 Finance es una implementación de Service Fabric, puede omitir este paso.</span><span class="sxs-lookup"><span data-stu-id="4fb35-111">If your deployment of Microsoft Dynamics 365 Finance is a Service Fabric deployment, you can skip this step.</span></span> <span data-ttu-id="4fb35-112">El equipo de información financiera ya debería haber activado el paquete piloto por usted.</span><span class="sxs-lookup"><span data-stu-id="4fb35-112">The Finance insights team should already have turned on the flight for you.</span></span> <span data-ttu-id="4fb35-113">Si no ve la característica en el espacio de trabajo **Administración de características**, o si experimenta problemas al intentar activarlas, póngase en contacto con <fiap@microsoft.com>.</span><span class="sxs-lookup"><span data-stu-id="4fb35-113">If you don't see the feature in the **Feature management** workspace, or if experience issues when you try to turn it on, contact <fiap@microsoft.com>.</span></span>

2. <span data-ttu-id="4fb35-114">Active la característica de información de pago del cliente:</span><span class="sxs-lookup"><span data-stu-id="4fb35-114">Turn on the Customer payment insights feature:</span></span>

    1. <span data-ttu-id="4fb35-115">Vaya a **Administración del sistema \> Espacios de trabajo \> Administración de características**.</span><span class="sxs-lookup"><span data-stu-id="4fb35-115">Go to **System administration \> Workspaces \> Feature management**.</span></span>
    2. <span data-ttu-id="4fb35-116">Busque la característica denominada **Información sobre pagos del cliente (versión preliminar)**.</span><span class="sxs-lookup"><span data-stu-id="4fb35-116">Find the feature that is named **Customer payment insights (preview)**.</span></span>
    3. <span data-ttu-id="4fb35-117">Seleccione **Habilitar ahora**.</span><span class="sxs-lookup"><span data-stu-id="4fb35-117">Select **Enable now**.</span></span>

    <span data-ttu-id="4fb35-118">La característica Información de pagos de clientes ya está activada y lista para configurarse.</span><span class="sxs-lookup"><span data-stu-id="4fb35-118">The Customer payment insights feature is now turned on and ready to be configured.</span></span>

3. <span data-ttu-id="4fb35-119">Configure la característica de Información de pagos de clientes:</span><span class="sxs-lookup"><span data-stu-id="4fb35-119">Configure the Customer payment insights feature:</span></span>

    1. <span data-ttu-id="4fb35-120">Vaya a **Crédito y cobros \> Configurar \> Información financiera \> Parámetros de información financiera**.</span><span class="sxs-lookup"><span data-stu-id="4fb35-120">Go to **Credit and collections \> Setup \> Finance insights \> Finance insights parameters**.</span></span>

        <span data-ttu-id="4fb35-121">[![Página de parámetros de información financiera antes de configurar la característica](./media/finance-insights-parameters.png)](./media/finance-insights-parameters.png)</span><span class="sxs-lookup"><span data-stu-id="4fb35-121">[![Financial insights parameters page before the feature is configured](./media/finance-insights-parameters.png)](./media/finance-insights-parameters.png)</span></span>

    2. <span data-ttu-id="4fb35-122">En la página **Parámetros de información financiera**, en la pestaña **Información sobre pagos de clientes**, seleccione el vínculo **Ver los campos de datos usados en el modelo de predicción** para abrir la página **Campos de datos para el modelo de predicción**.</span><span class="sxs-lookup"><span data-stu-id="4fb35-122">On the **Financial insights parameters** page, on the **Customer payment insights** tab, select the **View the data fields used in the prediction model** link to open the **Data fields for prediction model** page.</span></span> <span data-ttu-id="4fb35-123">Allí, puede ver la lista predeterminada de campos que se utilizan para crear el modelo de predicción de inteligencia artificial (IA) para las predicciones de pago de los clientes.</span><span class="sxs-lookup"><span data-stu-id="4fb35-123">There, you can view the default list of fields that are used to create the artificial intelligence (AI) prediction model for customer payment predictions.</span></span>

        <span data-ttu-id="4fb35-124">Para usar la lista predeterminada de campos para crear el modelo de predicción, cierre la página **Campos de datos para el modelo de predicción**, y luego, en la página **Parámetros de información financiera**, configure la opción **Habilitar característica** en **Sí**.</span><span class="sxs-lookup"><span data-stu-id="4fb35-124">To use the default list of fields to create the prediction model, close the **Data fields for prediction model** page, and then, on the **Financial insights parameters** page, set the **Enable feature** option to **Yes**.</span></span>

    3. <span data-ttu-id="4fb35-125">Especifique el período de transacción "muy tarde" para definir qué significa el ámbito de predicción **Muy tarde** para su negocio.</span><span class="sxs-lookup"><span data-stu-id="4fb35-125">Specify the "very late" transaction period to define what the **Very late** prediction bucket means for your business.</span></span>

        <span data-ttu-id="4fb35-126">Para cada factura abierta, el sistema predice la probabilidad de pago en tres ámbitos: **Puntutal**, **Tarde** y **Muy tarde**.</span><span class="sxs-lookup"><span data-stu-id="4fb35-126">For each open invoice, the system predicts the probability of payment in three buckets: **On time**, **Late**, and **Very late**.</span></span>

        - <span data-ttu-id="4fb35-127">**Puntual**: este grupo incluye pagos que se prevé que se pagarán en la fecha de vencimiento de la transacción o antes.</span><span class="sxs-lookup"><span data-stu-id="4fb35-127">**On time** – This bucket includes payments that are predicted to be paid on or before the transaction due date.</span></span>
        - <span data-ttu-id="4fb35-128">**Tarde**: este segmento incluye los pagos que se prevé que se pagarán después de la fecha de vencimiento de la transacción, pero antes del inicio del período de transacción "muy tarde".</span><span class="sxs-lookup"><span data-stu-id="4fb35-128">**Late** – This bucket includes payments that are predicted to be paid after the transaction due date but before the start of the "very late" transaction period.</span></span>
        - <span data-ttu-id="4fb35-129">**Muy tarde**: este segmento incluye los pagos que se prevé que se pagarán después del comienzo del período de transacción "muy tarde".</span><span class="sxs-lookup"><span data-stu-id="4fb35-129">**Very late** – This bucket includes payments that are predicted to be paid after the start of the "very late" transaction period.</span></span>

        > [!NOTE]
        > <span data-ttu-id="4fb35-130">Si cambia el período de transacción "muy tarde" y selecciona **Cambiar el umbral de tarde** después de creado el modelo de predicción de IA para los pagos de los clientes, se elimina el modelo de predicción existente y se crea un nuevo modelo.</span><span class="sxs-lookup"><span data-stu-id="4fb35-130">If you change the "very late" transaction period and select **Change late threshold** after the AI prediction model for customer payments has been created, the existing prediction model is deleted, and a new model is created.</span></span> <span data-ttu-id="4fb35-131">El nuevo modelo de predicción moverá las transacciones al período "muy tarde", según la configuración introducida para definirlo.</span><span class="sxs-lookup"><span data-stu-id="4fb35-131">The new prediction model will move transactions into the "very late" period, based on the settings that were entered to define it.</span></span>

    4. <span data-ttu-id="4fb35-132">Una vez que haya terminado de definir el período de transacción "muy tarde", seleccione **Crear modelo de predicción** para crear el modelo de predicción.</span><span class="sxs-lookup"><span data-stu-id="4fb35-132">After you've finished defining the "very late" transaction period, select **Create prediction model** to create the prediction model.</span></span> <span data-ttu-id="4fb35-133">La sección **Modelo de predicción** de la página **Parámetros de información financiera** muestra el estado del modelo de predicción.</span><span class="sxs-lookup"><span data-stu-id="4fb35-133">The **Prediction model** section on the **Financial insights parameters** page shows the status of the prediction model.</span></span>

        > [!NOTE]
        > <span data-ttu-id="4fb35-134">En cualquier momento, mientras se crea el modelo de predicción, puede seleccionar **Restablecer la creación del modelo** para reiniciar el proceso.</span><span class="sxs-lookup"><span data-stu-id="4fb35-134">At any time while the prediction model is being created, you can select **Reset model creation** to restart the process.</span></span>

    <span data-ttu-id="4fb35-135">La característica ya se ha configurado y está lista para utilizarla.</span><span class="sxs-lookup"><span data-stu-id="4fb35-135">The feature has now been configured and is ready to be used.</span></span>

<span data-ttu-id="4fb35-136">Una vez que la característica se ha activado y configurado, el modelo de predicción se ha creado y está funcionando, la sección **Modelo de predicción** de la página **Parámetros de información financiera** muestra la precisión del modelo, como se muestra en la siguiente ilustración.</span><span class="sxs-lookup"><span data-stu-id="4fb35-136">After the feature has been turned on and configured, and the prediction model has been created and is working, the **Prediction model** section of the **Financial insights parameters** page shows the accuracy of the model, as shown in the following illustration.</span></span>

<span data-ttu-id="4fb35-137">[![Precisión del modelo de predicción en la página de parámetros de información financiera](./media/finance-insights-parameters-accuracy.png)](./media/finance-insights-parameters-accuracy.png)</span><span class="sxs-lookup"><span data-stu-id="4fb35-137">[![Accuracy of the prediction model on the Financial insights parameters page](./media/finance-insights-parameters-accuracy.png)](./media/finance-insights-parameters-accuracy.png)</span></span>

## <a name="release-details"></a><span data-ttu-id="4fb35-138">Detalles de la liberación</span><span class="sxs-lookup"><span data-stu-id="4fb35-138">Release details</span></span>

<span data-ttu-id="4fb35-139">La versión preliminar pública de Finance Insights está disponible para implementaciones de prueba en los Estados Unidos de América, Europa y el Reino Unido.</span><span class="sxs-lookup"><span data-stu-id="4fb35-139">Finance insights public preview is available for trial deployments in the United States of America, Europe, and the United Kingdom.</span></span> <span data-ttu-id="4fb35-140">Microsoft está agregando gradualmente soporte para más regiones.</span><span class="sxs-lookup"><span data-stu-id="4fb35-140">Microsoft is incrementally adding support for more regions.</span></span>

<span data-ttu-id="4fb35-141">Las funciones de versión preliminar pública pueden y deben activarse solo en entornos de espacio aislado de nivel 2.</span><span class="sxs-lookup"><span data-stu-id="4fb35-141">Public preview features can and should be turned on only in Tier-2 sandbox environments.</span></span> <span data-ttu-id="4fb35-142">Los modelos de configuración e IA que se crean en un entorno de espacio aislado no se pueden migrar a un entorno de producción.</span><span class="sxs-lookup"><span data-stu-id="4fb35-142">Setup and AI models that are created in a sandbox environment can't be migrated to a production environment.</span></span> <span data-ttu-id="4fb35-143">Para más información, consulte [Condiciones de uso suplementarias para Vistas previas de Microsoft Dynamics 365](https://docs.microsoft.com/dynamics365/fin-ops-core/fin-ops/get-started/public-preview-terms).</span><span class="sxs-lookup"><span data-stu-id="4fb35-143">For more information, see [Supplemental Terms of Use for Microsoft Dynamics 365 Previews](https://docs.microsoft.com/dynamics365/fin-ops-core/fin-ops/get-started/public-preview-terms).</span></span>

## <a name="privacy-notice"></a><span data-ttu-id="4fb35-144">Aviso de privacidad</span><span class="sxs-lookup"><span data-stu-id="4fb35-144">Privacy notice</span></span>

<span data-ttu-id="4fb35-145">Las versiones preliminares (1) pueden utilizar menos privacidad y menos medidas de seguridad que el servicio Dynamics 365 Finance and Operations, (2) no están incluidas en el acuerdo de nivel de servicio para este servicio, (3) no deben utilizarse para procesar datos personales u otros datos que estén sujetos a requisitos de cumplimiento legal o reglamentario, y (4) disponen de soporte limitado.</span><span class="sxs-lookup"><span data-stu-id="4fb35-145">Previews (1) might use less privacy and fewer security measures than the Dynamics 365 Finance and Operations service, (2) aren't included in the service level agreement (SLA) for this service, (3) should not be used to process personal data or other data that is subject to legal or regulatory compliance requirements, and (4) have limited support.</span></span>


[!INCLUDE[footer-include](../../includes/footer-banner.md)]