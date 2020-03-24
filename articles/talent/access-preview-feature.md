---
title: Administrar características
description: Este tema describe cómo un administrador puede habilitar las características de vista previa en Microsoft Dynamics 365 Talent, y enumera las características que se habilitan actualmente para la vista previa.
author: andreabichsel
manager: AnnBe
ms.date: 02/03/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-human-resources
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Talent, Core
ms.custom: 7521
ms.assetid: 3b953d5f-6325-4c9e-8b9b-6ab0458a73f8
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: AX 7.1.0, Talent
ms.openlocfilehash: d818e9e04ce88e5ab285ef8176334809447fb477
ms.sourcegitcommit: 1d5a4f70a931e78b06811add97c1962e8d93689b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/13/2020
ms.locfileid: "3124805"
---
# <a name="manage-features"></a><span data-ttu-id="ab511-103">Administrar características</span><span class="sxs-lookup"><span data-stu-id="ab511-103">Manage features</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="ab511-104">Como parte de nuestro desarrollo continuo de las capacidades de administración del capital humano (HCM) para Microsoft Dynamics 365 Human Resources, deseamos que los clientes experimenten las nuevas características lo más rápidamente posible.</span><span class="sxs-lookup"><span data-stu-id="ab511-104">As part of our continuous rollout of human capital management (HCM) capabilities for Microsoft Dynamics 365 Human Resources, we want to let customers experience new features as soon as possible.</span></span> <span data-ttu-id="ab511-105">Los administradores pueden ver y utilizar características de vista previa en los entornos.</span><span class="sxs-lookup"><span data-stu-id="ab511-105">Administrators can see and use preview features in their environments.</span></span> <span data-ttu-id="ab511-106">Estas características casi están preparadas para la disponibilidad general y han pasado por un amplio proceso de pruebas.</span><span class="sxs-lookup"><span data-stu-id="ab511-106">These features are almost ready for general availability and have gone through extensive testing.</span></span> <span data-ttu-id="ab511-107">Simplemente estamos buscando una ronda final de comentarios de clientes y de validación antes de estén disponibles de forma general.</span><span class="sxs-lookup"><span data-stu-id="ab511-107">We're just looking for a final round of customer feedback and validation before we release them for general availability.</span></span>

<span data-ttu-id="ab511-108">Este tema describe cómo puede habilitar las características de vista previa, y enumera las características que están habilitadas actualmente para la vista previa.</span><span class="sxs-lookup"><span data-stu-id="ab511-108">This topic describes how you can enable preview features, and it lists the features that are currently available for preview.</span></span> <span data-ttu-id="ab511-109">Esta lista se actualizará a medida que se pongan nuevas características a disposición de todos y a medida que se lancen nuevas características para probarlas previamente.</span><span class="sxs-lookup"><span data-stu-id="ab511-109">This list will be updated as features are released to general availability and as new features are released to preview.</span></span> <span data-ttu-id="ab511-110">No se da ninguna notificación cuando las nuevas características se lanzan para obtener una vista previa.</span><span class="sxs-lookup"><span data-stu-id="ab511-110">No notification is given when new features are released to preview.</span></span> <span data-ttu-id="ab511-111">Los usuarios solo comenzarán a ver las características.</span><span class="sxs-lookup"><span data-stu-id="ab511-111">Users will just start to see the features.</span></span> <span data-ttu-id="ab511-112">Para obtener más información sobre características nuevas en Talent, consulte [Novedades o cambios en Dynamics 365 Talent](./whats-new.md) y [Notas de la versión de Dynamics 365 y Power Platform](https://docs.microsoft.com/business-applications-release-notes).</span><span class="sxs-lookup"><span data-stu-id="ab511-112">For more information about new features in Talent, see [What's new or changed in Dynamics 365 Talent](./whats-new.md) and [Dynamics 365 and Power Platform Release Notes](https://docs.microsoft.com/business-applications-release-notes).</span></span>

## <a name="enable-or-disable-preview-features"></a><span data-ttu-id="ab511-113">Habilitar o deshabilitar las funciones de vista previa</span><span class="sxs-lookup"><span data-stu-id="ab511-113">Enable or disable preview features</span></span>

<span data-ttu-id="ab511-114">Para obtener acceso a características de vista previa, primero debe permitirlas en el entorno.</span><span class="sxs-lookup"><span data-stu-id="ab511-114">To access preview features, you must first enable them in your environment.</span></span> <span data-ttu-id="ab511-115">Habilitar o deshabilitar las características de vista previa es específica del entorno.</span><span class="sxs-lookup"><span data-stu-id="ab511-115">Enabling or disabling preview features is environment-specific.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="ab511-116">Cuando activa la configuración **Funciones de vista previa**, habilita las características de vista preliminar para todos los usuarios de la organización que se encuentran en dicho entorno.</span><span class="sxs-lookup"><span data-stu-id="ab511-116">When you turn on the **Preview Features** setting, you enable preview features for all users in your organization who are in that environment.</span></span> <span data-ttu-id="ab511-117">Cuando desactiva la configuración, deshabilita las características de vista previa y hace que no sean accesibles a los usuarios.</span><span class="sxs-lookup"><span data-stu-id="ab511-117">When you turn off the setting, you disable preview features and make them inaccessible to your users.</span></span> <span data-ttu-id="ab511-118">Las funciones de vista previa tienen compatibilidad limitada en Talent.</span><span class="sxs-lookup"><span data-stu-id="ab511-118">Preview features have limited support in Talent.</span></span> <span data-ttu-id="ab511-119">Es posible que apliquen menos medidas de privacidad y de seguridad, y no se incluyen en el contrato de nivel de servicio (SLA) de Talent.</span><span class="sxs-lookup"><span data-stu-id="ab511-119">They might use fewer privacy and security measures, and they aren't included in the Talent service level agreement (SLA).</span></span> <span data-ttu-id="ab511-120">No debe utilizar características de vista preliminar para procesar datos personales (es decir, toda información que pueda identificarle), o para procesar otros datos sujetos a requisitos de conformidad legales o administrativos.</span><span class="sxs-lookup"><span data-stu-id="ab511-120">You should not use preview features to process personal data (that is, any information that could identify you), or to process other data that is subject to legal or regulatory compliance requirements.</span></span>

### <a name="attract"></a><span data-ttu-id="ab511-121">Atraer</span><span class="sxs-lookup"><span data-stu-id="ab511-121">Attract</span></span>

1. <span data-ttu-id="ab511-122">Inicie sesión en Microsoft Dynamics 365 Talent: Attract.</span><span class="sxs-lookup"><span data-stu-id="ab511-122">Sign in to Microsoft Dynamics 365 Talent: Attract.</span></span>
2. <span data-ttu-id="ab511-123">En el menú **Configuración** (el símbolo de engranaje) en la esquina superior derecha, seleccione **Centro de administración**.</span><span class="sxs-lookup"><span data-stu-id="ab511-123">On the **Setup** menu (the gear symbol) in the upper-right corner, select **Admin center**.</span></span>
3. <span data-ttu-id="ab511-124">En la pestaña **Administración de características**, seleccione la opción que está al lado de **Vista previa de características** para que se vuelva azul y pase a **Activada**.</span><span class="sxs-lookup"><span data-stu-id="ab511-124">On the **Feature management** tab, select the option next to **Preview features** so that it turns blue and says **On**.</span></span>

    ![Habilitar vista previa de características en Attract](./media/attract-enable-preview-features.png)

4. <span data-ttu-id="ab511-126">Seleccione o cancele la selección de características individuales de la vista previa.</span><span class="sxs-lookup"><span data-stu-id="ab511-126">Select or cancel the selection of individual preview features.</span></span> <span data-ttu-id="ab511-127">Si no hace nada, se activan todas las funciones disponibles de la vista previa.</span><span class="sxs-lookup"><span data-stu-id="ab511-127">If you do nothing, all available preview features are enabled.</span></span>
5. <span data-ttu-id="ab511-128">Actualice al explorador para empezar a ver las nuevas características.</span><span class="sxs-lookup"><span data-stu-id="ab511-128">Refresh your browser to start to see the new features.</span></span> <span data-ttu-id="ab511-129">Cualquier usuario que ya haya iniciado sesión verá las características la siguiente vez que inicie sesión, o puede actualizar al explorador para ver las características inmediatamente.</span><span class="sxs-lookup"><span data-stu-id="ab511-129">Any users who are already signed in will see the features the next time they sign in, or they can refresh their browser to see the features immediately.</span></span>

> [!NOTE]
> <span data-ttu-id="ab511-130">Algunas funciones de vista previa puede requerir configuración adicional.</span><span class="sxs-lookup"><span data-stu-id="ab511-130">Some preview features might require additional configuration.</span></span> <span data-ttu-id="ab511-131">Siga los vínculos que se encuentran junto a la característica de vista preliminar para completar la configuración.</span><span class="sxs-lookup"><span data-stu-id="ab511-131">Follow the links next to the preview feature to complete the setup for it.</span></span>

## <a name="feedback"></a><span data-ttu-id="ab511-132">Realimentación</span><span class="sxs-lookup"><span data-stu-id="ab511-132">Feedback</span></span>

<span data-ttu-id="ab511-133">Queremos conocer su experiencia con cualquiera de estas características de la vista previa.</span><span class="sxs-lookup"><span data-stu-id="ab511-133">We want to hear from you about your experience with any of these preview features.</span></span> <span data-ttu-id="ab511-134">Recomendamos que publique con regularidad sus comentarios en los sitios siguientes cuando use estas características u otras:</span><span class="sxs-lookup"><span data-stu-id="ab511-134">We encourage you to regularly post your feedback on the following sites as you use these or any other features:</span></span>

- <span data-ttu-id="ab511-135">[Comunidad](https://community.dynamics.com/enterprise/f/759?pi53869=0&category=Talent) – Este sitio es un gran recurso en el que los usuarios pueden discutir los casos de uso, hacer preguntas, y obtener ayuda de la comunidad.</span><span class="sxs-lookup"><span data-stu-id="ab511-135">[Community](https://community.dynamics.com/enterprise/f/759?pi53869=0&category=Talent) – This site is a great resource where users can discuss use cases, ask questions, and get community help.</span></span>
- <span data-ttu-id="ab511-136">Infórmenos sobre las características que desea ver en el producto, así como los cambios que crea que deberíamos realizar en las características existentes.</span><span class="sxs-lookup"><span data-stu-id="ab511-136">Let us know about features that you want to see in the product, or let us know about any changes you think we should make to existing features.</span></span> <span data-ttu-id="ab511-137">Sugiera ideas para productos en los siguientes sitios:</span><span class="sxs-lookup"><span data-stu-id="ab511-137">Suggest product ideas on the following sites:</span></span>

    - [<span data-ttu-id="ab511-138">Ideas para Attract</span><span class="sxs-lookup"><span data-stu-id="ab511-138">Attract ideas</span></span>](https://powerusers.microsoft.com/t5/Ideas-for-Attract/idb-p/Attract)
    - [<span data-ttu-id="ab511-139">Ideas para Onboard</span><span class="sxs-lookup"><span data-stu-id="ab511-139">Onboard ideas</span></span>](https://powerusers.microsoft.com/t5/Ideas-for-Onboard/idb-p/Onboard)

<span data-ttu-id="ab511-140">Asegúrese de no incluir datos personales (información que podría identificarlo) en los envíos de comentarios o de revisión del producto.</span><span class="sxs-lookup"><span data-stu-id="ab511-140">Make sure that you don't include personal data (any information that could identify you) in your feedback or product review submissions.</span></span> <span data-ttu-id="ab511-141">La información que se obtiene se puede analizar más, pero no se usará para responder a solicitudes, de acuerdo con las leyes aplicables de privacidad.</span><span class="sxs-lookup"><span data-stu-id="ab511-141">Collected information might be analyzed further and isn't used to answer requests under applicable privacy laws.</span></span> <span data-ttu-id="ab511-142">La información personal obtenida por separado en estos programas está sujeta a la [Declaración de privacidad de Microsoft](https://privacy.microsoft.com/privacystatement).</span><span class="sxs-lookup"><span data-stu-id="ab511-142">Personal data that is collected separately under these programs is subject to the [Microsoft Privacy Statement](https://privacy.microsoft.com/privacystatement).</span></span>

> [!TIP]
> <span data-ttu-id="ab511-143">Marque este tema, y consúltelo a menudo para mantenerse actualizado sobre características nuevas de vista previa a medida que las lanzamos al mercado.</span><span class="sxs-lookup"><span data-stu-id="ab511-143">Bookmark this topic, and check back often to stay up to date about new preview features as we release them.</span></span>

## <a name="see-also"></a><span data-ttu-id="ab511-144">Consulte también</span><span class="sxs-lookup"><span data-stu-id="ab511-144">See also</span></span>

- [<span data-ttu-id="ab511-145">Pruebe o compre las aplicaciones Talent</span><span class="sxs-lookup"><span data-stu-id="ab511-145">Try or buy Talent apps</span></span>](https://dynamics.microsoft.com/talent/overview/)
- [<span data-ttu-id="ab511-146">Novedades y cambios en Dynamics 365 Talent</span><span class="sxs-lookup"><span data-stu-id="ab511-146">What's new or changed in Dynamics 365 Talent</span></span>](./whats-new.md)
- [<span data-ttu-id="ab511-147">Planes de lanzamiento</span><span class="sxs-lookup"><span data-stu-id="ab511-147">Release plans</span></span>](https://docs.microsoft.com/business-applications-release-notes/index)
- [<span data-ttu-id="ab511-148">Obtener soporte para Microsoft Dynamics 365 Talent</span><span class="sxs-lookup"><span data-stu-id="ab511-148">Get support for Microsoft Dynamics 365 Talent</span></span>](./talent-support.md)
