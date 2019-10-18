---
title: Configuración de segregación de controles
description: Puede configurar reglas para tareas diferentes que deban llevar a cabo diferentes usuarios.
author: maertenm
manager: AnnBe
ms.date: 06/25/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SysSecSegregationOfDutiesRule
audience: Application User
ms.reviewer: sericks
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: maertenm
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 40b40b77877680e28671b7a15ea8c8b58ce94417
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/27/2019
ms.locfileid: "2180884"
---
# <a name="set-up-segregation-of-duties"></a><span data-ttu-id="058ad-103">Configuración de segregación de controles</span><span class="sxs-lookup"><span data-stu-id="058ad-103">Set up segregation of duties</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="058ad-104">Puede configurar reglas para tareas diferentes que deban llevar a cabo diferentes usuarios.</span><span class="sxs-lookup"><span data-stu-id="058ad-104">You can set up rules to separate tasks that must be performed by different users.</span></span> <span data-ttu-id="058ad-105">Este concepto se denomina "segregación de controles".</span><span class="sxs-lookup"><span data-stu-id="058ad-105">This concept is named segregation of duties.</span></span> <span data-ttu-id="058ad-106">Por ejemplo, puede que no desee que sea la misma persona la que confirme la recepción de mercancías y procese el pago al proveedor.</span><span class="sxs-lookup"><span data-stu-id="058ad-106">For example, you might not want the same person both to acknowledge the receipt of goods and to process payment to the vendor.</span></span> <span data-ttu-id="058ad-107">La segregación de controles ayuda a reducir el riesgo de fraude, y también ayuda a detectar errores o irregularidades.</span><span class="sxs-lookup"><span data-stu-id="058ad-107">Segregation of duties helps you reduce the risk of fraud, and it also helps you detect errors or irregularities.</span></span> <span data-ttu-id="058ad-108">También puede usar la segregación de controles para aplicar directivas de control internas.</span><span class="sxs-lookup"><span data-stu-id="058ad-108">You can also use segregation of duties to enforce internal control policies.</span></span> <span data-ttu-id="058ad-109">Complete el siguiente procedimiento para crear una regla.</span><span class="sxs-lookup"><span data-stu-id="058ad-109">Complete the following procedure to create a rule.</span></span> <span data-ttu-id="058ad-110">Es necesario ser administrador del sistema para completar el procedimiento.</span><span class="sxs-lookup"><span data-stu-id="058ad-110">You must be a system administrator to complete the procedure.</span></span> <span data-ttu-id="058ad-111">La empresa de datos de demostración utilizada para crear este procedimiento es DAT.</span><span class="sxs-lookup"><span data-stu-id="058ad-111">The demo data company used to create this procedure is DAT.</span></span> 

1. <span data-ttu-id="058ad-112">Vaya a **Panel de navegación > Módulos > Administración del sistema > Seguridad > Segregación de controles > Reglas de segregación de controles**.</span><span class="sxs-lookup"><span data-stu-id="058ad-112">Go to **Navigation pane > Modules > System administration > Security > Segregation of duties > Segregation of duties rules**.</span></span>
2. <span data-ttu-id="058ad-113">Haga clic en **Nuevo**.</span><span class="sxs-lookup"><span data-stu-id="058ad-113">Click **New**.</span></span>
3. <span data-ttu-id="058ad-114">En el campo **Nombre** escriba un valor para la regla.</span><span class="sxs-lookup"><span data-stu-id="058ad-114">In the **Name** field, type a value for the rule.</span></span>
4. <span data-ttu-id="058ad-115">En el campo **Primer deber**, haga clic en el botón desplegable para abrir la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="058ad-115">In the **First duty** field, click the drop-down button to open the lookup.</span></span>
5. <span data-ttu-id="058ad-116">En la lista, busque y seleccione el registro deseado.</span><span class="sxs-lookup"><span data-stu-id="058ad-116">In the list, find and select the desired record.</span></span> <span data-ttu-id="058ad-117">Seleccione el primer deber controlado por la regla.</span><span class="sxs-lookup"><span data-stu-id="058ad-117">Select the first duty that is controlled by the rule.</span></span>
6. <span data-ttu-id="058ad-118">En el campo **Segundo deber**, haga clic en el botón desplegable para abrir la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="058ad-118">In the **Second duty** field, click the drop-down button to open the lookup.</span></span> 
7. <span data-ttu-id="058ad-119">En la lista, busque y seleccione el registro deseado.</span><span class="sxs-lookup"><span data-stu-id="058ad-119">In the list, find and select the desired record.</span></span> <span data-ttu-id="058ad-120">Seleccione el segundo deber controlado por la regla.</span><span class="sxs-lookup"><span data-stu-id="058ad-120">Select the second duty that is controlled by the rule.</span></span>
10. <span data-ttu-id="058ad-121">En el campo **Gravedad**, seleccione una opción.</span><span class="sxs-lookup"><span data-stu-id="058ad-121">In the **Severity** field, select an option.</span></span> <span data-ttu-id="058ad-122">Seleccione la gravedad del riesgo que se genera cuando el mismo usuario o rol realiza ambos deberes.</span><span class="sxs-lookup"><span data-stu-id="058ad-122">Select the severity of the risk that occurs when the same user or role performs both duties.</span></span>  
11. <span data-ttu-id="058ad-123">En el campo **Riesgo de seguridad**, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="058ad-123">In the **Security risk** field, type a value.</span></span> <span data-ttu-id="058ad-124">Escriba una descripción del riesgo para la seguridad.</span><span class="sxs-lookup"><span data-stu-id="058ad-124">Enter a description of the security risk.</span></span>  
12. <span data-ttu-id="058ad-125">En el campo **Mitigación de seguridad**, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="058ad-125">In the **Security mitigation** field, type a value.</span></span> <span data-ttu-id="058ad-126">Escriba una descripción de las acciones para mitigar el riesgo de seguridad.</span><span class="sxs-lookup"><span data-stu-id="058ad-126">Enter a description of the actions that you take to mitigate the security risk.</span></span> <span data-ttu-id="058ad-127">Por ejemplo, puede mitigar el riesgo realizando revisiones más detalladas del proceso, realizando una revisión administrativa mensual o compartiendo recursos con otros departamentos.</span><span class="sxs-lookup"><span data-stu-id="058ad-127">For example, you can mitigate the risk by conducting more detailed reviews of the process, by conducting a monthly managerial review, or by sharing resources with other departments.</span></span>     
13. <span data-ttu-id="058ad-128">Haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="058ad-128">Click **Save**.</span></span>

