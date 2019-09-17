---
title: Habilitar la integración de Broadbean en Microsoft Dynamics 365 for Talent - Attract
description: Este tema explica cómo configurar Microsoft Dynamics 365 for Talent - Attract para registrar trabajos en plataformas externas de trabajo como Broadbean.
author: andreabichsel
manager: AnnBe
ms.date: 07/08/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Talent, Core
ms.custom: 7521
ms.assetid: 3b953d5f-6325-4c9e-8b9b-6ab0458a73f8
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2019-07-08
ms.dyn365.ops.version: Talent October 2018 update
ms.openlocfilehash: 2334c2bd0edccf3000f8d91651afafd4619ad0b8
ms.sourcegitcommit: 7c49475402632069685df714546770d30804af7f
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/11/2019
ms.locfileid: "1739688"
---
# <a name="enable-broadbean-integration"></a><span data-ttu-id="d3c6d-103">Habilitar la integración de Broadbean</span><span class="sxs-lookup"><span data-stu-id="d3c6d-103">Enable Broadbean integration</span></span>

[!include[banner](../includes/banner.md)]

<span data-ttu-id="d3c6d-104">Usted quiere presentar sus vacantes a tantos candidatos cualificados como sea posible.</span><span class="sxs-lookup"><span data-stu-id="d3c6d-104">You want to get your open positions in front of as many qualified candidates as possible.</span></span> <span data-ttu-id="d3c6d-105">Los sitios de contratación como Broadbean se lleva a cabo este objetivo.</span><span class="sxs-lookup"><span data-stu-id="d3c6d-105">Recruiting sites such as Broadbean help you accomplish this goal.</span></span> <span data-ttu-id="d3c6d-106">Microsoft Dynamics 365 for Talent: Attract ahora le permite registrar trabajos en Broadbean y Microsoft proporciona constantemente nuevas ofertas en esta área.</span><span class="sxs-lookup"><span data-stu-id="d3c6d-106">Microsoft Dynamics 365 for Talent: Attract now lets you post jobs to Broadbean, and Microsoft is constantly providing new offerings in this area.</span></span>

> [!NOTE]
> - <span data-ttu-id="d3c6d-107">Para registrar trabajos en los sitios externos, debe tener el [Complemento de contratación completo](https://docs.microsoft.com/dynamics365/unified-operations/talent/attract-comprehensive-hiring).</span><span class="sxs-lookup"><span data-stu-id="d3c6d-107">To post jobs to external sites, you must have the [Comprehensive hiring add-on](https://docs.microsoft.com/dynamics365/unified-operations/talent/attract-comprehensive-hiring).</span></span>
> - <span data-ttu-id="d3c6d-108">Para registrar trabajos a en Broadbean a través de Attract, debe tener una suscripción de Broadbean.</span><span class="sxs-lookup"><span data-stu-id="d3c6d-108">To post jobs to Broadbean through Attract, you must have a Broadbean subscription.</span></span>
> - <span data-ttu-id="d3c6d-109">Esta característica está actualmente en vista previa.</span><span class="sxs-lookup"><span data-stu-id="d3c6d-109">This feature is currently in preview.</span></span> <span data-ttu-id="d3c6d-110">Si desea probarlo, debe [activarlo en la configuración de administrador de Attract](https://docs.microsoft.com/dynamics365/unified-operations/talent/access-preview-feature).</span><span class="sxs-lookup"><span data-stu-id="d3c6d-110">If you want to try it, you must [turn it on in the Attract admin settings](https://docs.microsoft.com/dynamics365/unified-operations/talent/access-preview-feature).</span></span>

## <a name="configure-broadbean-integration"></a><span data-ttu-id="d3c6d-111">Configurar integración de Broadbean</span><span class="sxs-lookup"><span data-stu-id="d3c6d-111">Configure Broadbean integration</span></span>

1. <span data-ttu-id="d3c6d-112">Iniciar sesión en Attract como administrador.</span><span class="sxs-lookup"><span data-stu-id="d3c6d-112">Sign in to Attract as an admin.</span></span>

2. <span data-ttu-id="d3c6d-113">Seleccione el botón **Configuración** (el símbolo de engranaje) en la esquina superior derecha de la página y a continuación seleccione **Centro de administración**.</span><span class="sxs-lookup"><span data-stu-id="d3c6d-113">Select the **Settings** button (the gear symbol) in the upper-right corner of the page, and then select **Admin center**.</span></span>

3. <span data-ttu-id="d3c6d-114">Póngase en contacto con Broadbean y introduzca su información en **Nombre de usuario**, **identificador de cliente**, y **token de cifrado**.</span><span class="sxs-lookup"><span data-stu-id="d3c6d-114">Contact Broadbean, and enter your information in the **Username**, **Client ID**, and **Encryption Token** fields.</span></span>

4. <span data-ttu-id="d3c6d-115">Seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="d3c6d-115">Select **Save**.</span></span>

> [!WARNING]
> <span data-ttu-id="d3c6d-116">Sus credenciales de Broadbean son importantes y confidenciales.</span><span class="sxs-lookup"><span data-stu-id="d3c6d-116">Your Broadbean credentials are sensitive and confidential.</span></span> <span data-ttu-id="d3c6d-117">Por lo tanto, almacénelas y compártalas de forma responsable.</span><span class="sxs-lookup"><span data-stu-id="d3c6d-117">Therefore, store and share them responsibly.</span></span> <span data-ttu-id="d3c6d-118">Cualquiera que tenga un rol de administrador en Attract puede ver estas credenciales.</span><span class="sxs-lookup"><span data-stu-id="d3c6d-118">Anyone who has an Administrator role in Attract can view these credentials.</span></span>

> [!NOTE]
> <span data-ttu-id="d3c6d-119">Microsoft y Attract no están involucradas en crear y mantener estos valores.</span><span class="sxs-lookup"><span data-stu-id="d3c6d-119">Microsoft and Attract aren't involved in creating and maintaining these values.</span></span> <span data-ttu-id="d3c6d-120">Es su responsabilidad mantenerlas actualizadas en Attract y trabajar con Broadbean para resolver los problemas relacionados con sus credenciales.</span><span class="sxs-lookup"><span data-stu-id="d3c6d-120">It's your responsibility to keep them up to date in Attract and to work with Broadbean to resolve any issues that involve your credentials.</span></span>
