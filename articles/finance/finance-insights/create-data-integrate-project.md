---
title: Crear un proyecto integrador de datos (versión preliminar)
description: Este tema explica cómo crear un proyecto integrador de datos.
author: ShivamPandey-msft
ms.date: 07/24/2020
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
ms.search.validFrom: 2020-07-24
ms.dyn365.ops.version: AX 10.0.13
ms.openlocfilehash: 9ecf6ef7b7f052ebbb1201dcd04a7431f5b72ce5
ms.sourcegitcommit: b64c52d85aa6f110f3b1959a5521637dd8631b5b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/07/2021
ms.locfileid: "5867456"
---
# <a name="create-a-data-integrator-project-preview"></a><span data-ttu-id="bfb51-103">Crear un proyecto integrador de datos (versión preliminar)</span><span class="sxs-lookup"><span data-stu-id="bfb51-103">Create a data integrator project (preview)</span></span>

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

<span data-ttu-id="bfb51-104">Este tema explica cómo crear un proyecto integrador de datos.</span><span class="sxs-lookup"><span data-stu-id="bfb51-104">This topic explains how to create a data integrator project.</span></span>

1. <span data-ttu-id="bfb51-105">Inicie sesión en Microsoft Dynamics 365 Finance.</span><span class="sxs-lookup"><span data-stu-id="bfb51-105">Sign in to Microsoft Dynamics 365 Finance.</span></span>
2. <span data-ttu-id="bfb51-106">Vaya a **Espacios de trabajo \> Administración de datos** y seleccione **Entidades de datos**.</span><span class="sxs-lookup"><span data-stu-id="bfb51-106">Go to **Workspaces \> Data management**, and select **Data entities**.</span></span> <span data-ttu-id="bfb51-107">Espere hasta que se hayan actualizado todas las entidades de datos antes de continuar con el siguiente paso.</span><span class="sxs-lookup"><span data-stu-id="bfb51-107">Wait until all the data entities have been refreshed before you move on to the next step.</span></span>
3. <span data-ttu-id="bfb51-108">Abra el [Portal de Power Apps](https://make.powerapps.com/) y siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="bfb51-108">Open the [Power Apps portal](https://make.powerapps.com/), and follow these steps:</span></span>

    1. <span data-ttu-id="bfb51-109">Seleccione el entorno adecuado.</span><span class="sxs-lookup"><span data-stu-id="bfb51-109">Select the appropriate environment.</span></span>
    2. <span data-ttu-id="bfb51-110">En el panel de navegación izquierdo, seleccione **Datos \> Conexiones**.</span><span class="sxs-lookup"><span data-stu-id="bfb51-110">In the left navigation pane, select **Data \> Connections**.</span></span>
    3. <span data-ttu-id="bfb51-111">Conéctese a las instancias adecuadas de los siguientes elementos:</span><span class="sxs-lookup"><span data-stu-id="bfb51-111">Connect to appropriate instances of the following items:</span></span>

        - <span data-ttu-id="bfb51-112">Dynamics 365</span><span class="sxs-lookup"><span data-stu-id="bfb51-112">Dynamics 365</span></span>
        - <span data-ttu-id="bfb51-113">Dynamics 365 para Fin & Ops</span><span class="sxs-lookup"><span data-stu-id="bfb51-113">Dynamics 365 for Fin & Ops</span></span>

4. <span data-ttu-id="bfb51-114">Abra los [entornos de Power Apps](https://admin.powerapps.com/environments) y siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="bfb51-114">Open the [Power Apps environments](https://admin.powerapps.com/environments), and follow these steps:</span></span>

    1. <span data-ttu-id="bfb51-115">Seleccione **Integrador de datos**.</span><span class="sxs-lookup"><span data-stu-id="bfb51-115">Select **Data Integrator**.</span></span>
    2. <span data-ttu-id="bfb51-116">Seleccione **Conjuntos de conexión**.</span><span class="sxs-lookup"><span data-stu-id="bfb51-116">Select **Connection sets**.</span></span>
    3. <span data-ttu-id="bfb51-117">Seleccione **Nuevo conjunto de conexión**.</span><span class="sxs-lookup"><span data-stu-id="bfb51-117">Select **New connection set**.</span></span>
    4. <span data-ttu-id="bfb51-118">Escriba un nombre para la conexión.</span><span class="sxs-lookup"><span data-stu-id="bfb51-118">Enter a name for the connection.</span></span>
    5. <span data-ttu-id="bfb51-119">Seleccione las conexiones adecuadas para los siguientes elementos:</span><span class="sxs-lookup"><span data-stu-id="bfb51-119">Select the appropriate connections for the following items:</span></span>

        - <span data-ttu-id="bfb51-120">Dynamics 365</span><span class="sxs-lookup"><span data-stu-id="bfb51-120">Dynamics 365</span></span>
        - <span data-ttu-id="bfb51-121">Dynamics 365 para Fin & Ops</span><span class="sxs-lookup"><span data-stu-id="bfb51-121">Dynamics 365 for Fin & Ops</span></span>

    6. <span data-ttu-id="bfb51-122">Seleccione el mapeo de la organización apropiado.</span><span class="sxs-lookup"><span data-stu-id="bfb51-122">Select the appropriate organization mapping.</span></span>
    7. <span data-ttu-id="bfb51-123">Seleccione **Crear**.</span><span class="sxs-lookup"><span data-stu-id="bfb51-123">Select **Create**.</span></span>

5. <span data-ttu-id="bfb51-124">Abra los [entornos de Power Apps](https://admin.powerapps.com/environments) y siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="bfb51-124">Open the [Power Apps environments](https://admin.powerapps.com/environments), and follow these steps:</span></span>  

    1. <span data-ttu-id="bfb51-125">Cree proyectos de integración de datos para las siguientes plantillas utilizando el conjunto de conexiones que acaba de crear:</span><span class="sxs-lookup"><span data-stu-id="bfb51-125">Create data integration projects for the following templates by using the connection set that you just created:</span></span>

        - <span data-ttu-id="bfb51-126">Resultados de información sobre pagos del cliente (CDS a Fin and Ops)</span><span class="sxs-lookup"><span data-stu-id="bfb51-126">Customer payment insights results (CDS to Fin and Ops)</span></span>
            - <span data-ttu-id="bfb51-127">Si está utilizando la versión 10.0.17 o posterior, debe utilizar la plantilla denominada Resultado de información de pago del cliente (CDS a Fin and Ops 10.0.17 +).</span><span class="sxs-lookup"><span data-stu-id="bfb51-127">If you are using version 10.0.17 or later, you need to use the template named, Customer payment insights result (CDS to Fin and Ops 10.0.17+).</span></span>
        - <span data-ttu-id="bfb51-128">Resultados de series de tiempo de flujo de efectivo (CDS a Fin and Ops)</span><span class="sxs-lookup"><span data-stu-id="bfb51-128">Cash flow time series results (CDS to Fin and Ops)</span></span>
        - <span data-ttu-id="bfb51-129">Resultados de series de tiempo de presupuestos (CDS a Fin and Ops)</span><span class="sxs-lookup"><span data-stu-id="bfb51-129">Budget time series results (CDS to Fin and Ops)</span></span>

    2. <span data-ttu-id="bfb51-130">Establezca la programación adecuada para cada proyecto.</span><span class="sxs-lookup"><span data-stu-id="bfb51-130">Set the appropriate scheduling for each project.</span></span>

> [!NOTE]
> <span data-ttu-id="bfb51-131">Si no ve las entidades requeridas en CDS, vaya a **Crédito y cobros > Configuración > Información financiera> Finance Insights > Parámetros de Finance Insights**, habilite la función de predicciones de pago del cliente y haga clic en el botón **Crear modelo de predicción**.</span><span class="sxs-lookup"><span data-stu-id="bfb51-131">If you do not see the required entities in CDS, please go to **Credit and collections > Setup > Finance Insights > Finance insights parameters**, enable Customer payment predictions feature and click on **Create prediction model** button.</span></span> <span data-ttu-id="bfb51-132">Cuando se complete la implementación del modelo de IA (correcta o con errores), las entidades CDS necesarias para crear la integración se implementarán en CDS.</span><span class="sxs-lookup"><span data-stu-id="bfb51-132">When the deployment of AI model is completed (successful or failed), the CDS entities needed to create integration will be deployed in CDS.</span></span>

## <a name="privacy-notice"></a><span data-ttu-id="bfb51-133">Aviso de privacidad</span><span class="sxs-lookup"><span data-stu-id="bfb51-133">Privacy notice</span></span>

<span data-ttu-id="bfb51-134">Las versiones preliminares (1) pueden utilizar menos privacidad y menos medidas de seguridad que el servicio Dynamics 365 Finance and Operations, (2) no están incluidas en el acuerdo de nivel de servicio para este servicio, (3) no deben utilizarse para procesar datos personales u otros datos que estén sujetos a requisitos de cumplimiento legal o reglamentario, y (4) disponen de soporte limitado.</span><span class="sxs-lookup"><span data-stu-id="bfb51-134">Previews (1) might use less privacy and fewer security measures than the Dynamics 365 Finance and Operations service, (2) aren't included in the service level agreement (SLA) for this service, (3) should not be used to process personal data or other data that is subject to legal or regulatory compliance requirements, and (4) have limited support.</span></span>


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
