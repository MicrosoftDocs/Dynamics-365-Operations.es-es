---
title: El cliente se desconecta
description: Este artículo explica qué hacer si el cliente está desconectado del entorno y no sabe por qué.
author: andreabichsel
ms.date: 02/03/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: db0e8efec1a5a6f01c9b7c4d9334a959fc42886b
ms.sourcegitcommit: cabd991fda2bfcabb55db84c225b24a7bb061631
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/12/2021
ms.locfileid: "6027996"
---
# <a name="client-disconnects"></a><span data-ttu-id="35776-103">El cliente se desconecta</span><span class="sxs-lookup"><span data-stu-id="35776-103">Client disconnects</span></span>

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

<span data-ttu-id="35776-104">**Detalles del entorno**</span><span class="sxs-lookup"><span data-stu-id="35776-104">**Environment details**</span></span> 

<span data-ttu-id="35776-105">Este problema puede aparecer en todos los entornos.</span><span class="sxs-lookup"><span data-stu-id="35776-105">This issue can occur in all environments.</span></span>
 
<span data-ttu-id="35776-106">**Síntoma**</span><span class="sxs-lookup"><span data-stu-id="35776-106">**Symptom**</span></span> 

<span data-ttu-id="35776-107">El cliente está desconectado del entorno y no sabe por qué.</span><span class="sxs-lookup"><span data-stu-id="35776-107">The customer is disconnected from the environment and doesn't know why.</span></span> <span data-ttu-id="35776-108">El cliente recibe uno de los mensajes de error siguientes:</span><span class="sxs-lookup"><span data-stu-id="35776-108">The customer receives one of the following error messages:</span></span>

- <span data-ttu-id="35776-109">Hemos perdido la conexión.</span><span class="sxs-lookup"><span data-stu-id="35776-109">We've lost your connection.</span></span> <span data-ttu-id="35776-110">Haga clic en Cerrar para continuar trabajando.</span><span class="sxs-lookup"><span data-stu-id="35776-110">Click Close to continue working.</span></span>
- <span data-ttu-id="35776-111">Parece que perdió la conectividad de red. Haga clic en Reintentar para intentarlo de nuevo.</span><span class="sxs-lookup"><span data-stu-id="35776-111">It appears you lost network connectivity, click Retry to try again.</span></span>

<span data-ttu-id="35776-112">**Indicador rojo**</span><span class="sxs-lookup"><span data-stu-id="35776-112">**Red flag**</span></span>

<span data-ttu-id="35776-113">Este problema se produce a menudo cuando los usuarios se encuentran en la etapa de implementación, comparan información a través de entornos de la producción y entornos de pruebas, y se olvidan de que se mueven entre las sesiones.</span><span class="sxs-lookup"><span data-stu-id="35776-113">This issue often occurs when users are in the implementation stage, are comparing information across production and test environments, and forget that they are moving between sessions.</span></span> <span data-ttu-id="35776-114">Si los usuarios se encuentran en esta etapa, experimentarán probablemente este error.</span><span class="sxs-lookup"><span data-stu-id="35776-114">If users are at this stage, they will most likely experience this issue.</span></span>

<span data-ttu-id="35776-115">**Emisión**</span><span class="sxs-lookup"><span data-stu-id="35776-115">**Issue**</span></span> 

<span data-ttu-id="35776-116">**Tipos de explorador:** Google Chrome, Internet Explorer y Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="35776-116">**Browser types:** Google Chrome, Internet Explorer, and Microsoft Edge</span></span>

<span data-ttu-id="35776-117">Microsoft Dynamics 365 Human Resources desconecta a usuarios cuando dos sesiones están abiertas a la vez para el mismo usuario y el mismo tipo de explorador.</span><span class="sxs-lookup"><span data-stu-id="35776-117">Microsoft Dynamics 365 Human Resources disconnects users when two different sessions are open at the same time for the same user and the same browser type.</span></span> <span data-ttu-id="35776-118">(Por ejemplo, el usuario A está viendo el entorno 1 y el entorno 2 en Chrome.) No importa si los usuarios abren las distintas ventanas del explorador o diferentes fichas.</span><span class="sxs-lookup"><span data-stu-id="35776-118">(For example, user A is viewing both environment 1 and environment 2 in Chrome.) It doesn't matter whether the users open different browser windows or different tabs.</span></span> <span data-ttu-id="35776-119">Si las mismas credenciales del usuario se utilizan para iniciar sesión en el entorno 1 y el entorno 2 al mismo tiempo y en el mismo tipo de explorador, Human Resources desconectará una de las sesiones.</span><span class="sxs-lookup"><span data-stu-id="35776-119">If the same user credentials are used to sign in to both environment 1 and environment 2 at the same time and in the same browser type, Human Resources disconnects one of the sessions.</span></span>

<span data-ttu-id="35776-120">**Solución**</span><span class="sxs-lookup"><span data-stu-id="35776-120">**Solution**</span></span>

<span data-ttu-id="35776-121">Asegúrese de que sólo un entorno esté abierto al mismo tiempo para un tipo de explorador dado.</span><span class="sxs-lookup"><span data-stu-id="35776-121">Make sure that only one environment is open at a time for a given browser type.</span></span> <span data-ttu-id="35776-122">Los usuarios pueden abrir variras sesiones en el mismo entorno (es decir, varias fichas en el mismo explorador).</span><span class="sxs-lookup"><span data-stu-id="35776-122">Users can open multiple sessions to the same environment (that is, multiple tabs in the same browser).</span></span>

<span data-ttu-id="35776-123">Los usuarios que desean desplazarse entre dos entornos al mismo tiempo deben abrir cada entorno en un tipo de explorador diferente.</span><span class="sxs-lookup"><span data-stu-id="35776-123">Users who want to jump between two environments at the same time should open each environment in a different browser type.</span></span> <span data-ttu-id="35776-124">(Por ejemplo, el usuario A puede ver el entorno 1 en Chrome y el entorno 2 en Microsoft Edge.)</span><span class="sxs-lookup"><span data-stu-id="35776-124">(For example, user A can view environment 1 in Chrome and environment 2 in Microsoft Edge.)</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]