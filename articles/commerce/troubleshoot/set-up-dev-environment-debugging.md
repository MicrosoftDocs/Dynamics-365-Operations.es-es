---
title: Configurar un ambiente de desarrollo de comercio electrónico para depurar frente a una máquina virtual de servidor minorista de nivel 1
description: Este tema explica cómo configurar un ambiente de desarrollo de comercio electrónico para depurar frente a una máquina virtual (VM) de servidor minorista de nivel 1.
author: Reza-Assadi
manager: AnnBe
ms.date: 03/11/2021
ms.topic: Troubleshooting
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Retail
ms.author: rassadi
ms.search.validFrom: 2021-01-31
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: 35380a559a4f1b22bdf04ff25cb2bbfc51aff45b
ms.sourcegitcommit: 6c108be3378b365e6ec596a1a8666d59b758db25
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2021
ms.locfileid: "5585510"
---
# <a name="set-up-an-e-commerce-development-environment-to-debug-against-a-tier-1-retail-server-virtual-machine"></a><span data-ttu-id="71e9f-103">Configurar un ambiente de desarrollo de comercio electrónico para depurar frente a una máquina virtual de servidor minorista de nivel 1</span><span class="sxs-lookup"><span data-stu-id="71e9f-103">Set up an e-commerce development environment to debug against a Tier 1 Retail Server virtual machine</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="71e9f-104">Este tema explica cómo configurar un ambiente de desarrollo de comercio electrónico para depurar frente a una máquina virtual (VM) de servidor minorista de nivel 1.</span><span class="sxs-lookup"><span data-stu-id="71e9f-104">This topic explains how to set up an e-commerce development environment to debug against a Tier 1 Retail Server virtual machine (VM).</span></span>

## <a name="description"></a><span data-ttu-id="71e9f-105">Descripción</span><span class="sxs-lookup"><span data-stu-id="71e9f-105">Description</span></span>

<span data-ttu-id="71e9f-106">Los ambientes de nivel 1 de Microsoft Dynamics 365 Commerce se implementan normalmente para el tiempo de ejecución de Commerce (CRT) y el desarrollo de extensión de punto de venta (POS).</span><span class="sxs-lookup"><span data-stu-id="71e9f-106">Microsoft Dynamics 365 Commerce Tier 1 environments are typically deployed for Commerce runtime (CRT) and point of sale (POS) extension development.</span></span> <span data-ttu-id="71e9f-107">Son ambientes independientes.</span><span class="sxs-lookup"><span data-stu-id="71e9f-107">They are standalone environments.</span></span> <span data-ttu-id="71e9f-108">Debido a la naturaleza de software como servicio (SaaS) de la arquitectura, no incluyen componentes de comercio electrónico.</span><span class="sxs-lookup"><span data-stu-id="71e9f-108">Because of the software as a service (SaaS) nature of the architecture, they don't include e-commerce components.</span></span>

<span data-ttu-id="71e9f-109">En algunos escenarios, es posible que desee probar las llamadas a extensiones en un entorno de nivel 1, para poder depurar extensiones de componentes de comercio electrónico.</span><span class="sxs-lookup"><span data-stu-id="71e9f-109">In some scenarios, you might want to test calls to extensions in a Tier 1 environment, so that you can debug extensions from e-commerce components.</span></span> <span data-ttu-id="71e9f-110">Para conocer las instrucciones generales, consulte [Depurar con un entorno de desarrollo de Commerce de nivel 1](../e-commerce-extensibility/debug-tier-1.md).</span><span class="sxs-lookup"><span data-stu-id="71e9f-110">For general instructions, see [Debug against a Tier 1 Commerce development environment](../e-commerce-extensibility/debug-tier-1.md).</span></span>

<span data-ttu-id="71e9f-111">Cuando depura frente en un entorno de nivel 1, debido a que el sitio ahora llama a un Retail Server diferente, las llamadas entre servidores pueden causar varios errores relacionados con la directiva de seguridad del contenido.</span><span class="sxs-lookup"><span data-stu-id="71e9f-111">When you debug against a Tier 1 environment, because the site is now calling a different Retail Server, cross-server calls might cause various errors that are related to the content security policy.</span></span>

<span data-ttu-id="71e9f-112">La siguiente ilustración muestra un ejemplo de error que puede ocurrir cuando se selecciona una variante en la página de detalles de un producto.</span><span class="sxs-lookup"><span data-stu-id="71e9f-112">The following illustration shows an example of an error that might occur when a variant is selected on a product details page.</span></span>

![Error cuando se selecciona una variante en la página de detalles de un producto](media/unhandled-rejection-error.jpg)

<span data-ttu-id="71e9f-114">La siguiente ilustración muestra un ejemplo de un error similar en las herramientas de depuración de un navegador (Herramientas de desarrollo F12).</span><span class="sxs-lookup"><span data-stu-id="71e9f-114">The following illustration shows an example of a similar error in a browser's debugger tools (F12 Developer Tools).</span></span> <span data-ttu-id="71e9f-115">El mensaje de error menciona la violación de la directiva de directiva de seguridad de contenido.</span><span class="sxs-lookup"><span data-stu-id="71e9f-115">The error message mentions violation of the content security policy directive.</span></span>

![Error de las herramientas del depurador](media/debugger-tools-error.JPG)

## <a name="resolution"></a><span data-ttu-id="71e9f-117">Resolución</span><span class="sxs-lookup"><span data-stu-id="71e9f-117">Resolution</span></span>

### <a name="disable-the-content-security-policy-for-the-site-in-commerce-site-builder"></a><span data-ttu-id="71e9f-118">Deshabilite la directiva de seguridad de contenido para el sitio en el creador de sitios de Commerce</span><span class="sxs-lookup"><span data-stu-id="71e9f-118">Disable the content security policy for the site in Commerce site builder</span></span>

1. <span data-ttu-id="71e9f-119">Seleccione el sitio en el que está trabajando.</span><span class="sxs-lookup"><span data-stu-id="71e9f-119">Select the site that you're working on.</span></span>
1. <span data-ttu-id="71e9f-120">Seleccione **Configuración** y después seleccione **Extensiones**.</span><span class="sxs-lookup"><span data-stu-id="71e9f-120">Select **Settings**, and then select **Extensions**.</span></span>
1. <span data-ttu-id="71e9f-121">En la pestaña **Directiva de seguridad de contenido**, seleccione **Deshabilitar la directiva de seguridad de contenido**.</span><span class="sxs-lookup"><span data-stu-id="71e9f-121">On the **Content security policy** tab, select **Disable content security policy**.</span></span>
1. <span data-ttu-id="71e9f-122">Seleccione **Guardar y publicar**.</span><span class="sxs-lookup"><span data-stu-id="71e9f-122">Select **Save and publish**.</span></span>

> [!NOTE]
> <span data-ttu-id="71e9f-123">El inicio de sesión de empresa a consumidor (B2C) no funcionará en un entorno de desarrollo local.</span><span class="sxs-lookup"><span data-stu-id="71e9f-123">Business-to-consumer (B2C) sign-in won't work in a local development environment.</span></span> <span data-ttu-id="71e9f-124">Sin embargo, puede utilizar los pagos de invitados o crear simulaciones de página para simular el inicio de sesión de un usuario, según sea necesario.</span><span class="sxs-lookup"><span data-stu-id="71e9f-124">However, you can use guest checkouts or build page mocks to simulate a user sign-in as required.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="71e9f-125">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="71e9f-125">Additional resources</span></span>

[<span data-ttu-id="71e9f-126">Introducción al desarrollo de extensibilidad en línea de comercio electrónico</span><span class="sxs-lookup"><span data-stu-id="71e9f-126">Get started with e-commerce online extensibility development</span></span>](../e-commerce-extensibility/sdk-getting-started.md)

[<span data-ttu-id="71e9f-127">Administrar la directiva de seguridad de contenido (CSP) en el sitio de comercio electrónico</span><span class="sxs-lookup"><span data-stu-id="71e9f-127">Manage content security policy (CSP) on e-commerce site</span></span>](../manage-csp.md)
