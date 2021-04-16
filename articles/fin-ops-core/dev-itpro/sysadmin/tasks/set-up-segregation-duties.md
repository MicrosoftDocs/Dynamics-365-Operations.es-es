---
title: Configuración de segregación de controles
description: Puede configurar reglas para tareas diferentes que deban llevar a cabo diferentes usuarios.
author: peakerbl
ms.date: 01/04/2021
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: SysSecSegregationOfDutiesRule
audience: Application User
ms.reviewer: sericks
ms.search.region: Global
ms.author: peakerbl
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: e25fee324ce95cd04b86ee0e4e6a56cfacb61a53
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/31/2021
ms.locfileid: "5745750"
---
# <a name="set-up-segregation-of-duties"></a><span data-ttu-id="cc5ea-103">Configuración de segregación de controles</span><span class="sxs-lookup"><span data-stu-id="cc5ea-103">Set up segregation of duties</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="cc5ea-104">Puede configurar reglas para tareas diferentes que deban llevar a cabo diferentes usuarios.</span><span class="sxs-lookup"><span data-stu-id="cc5ea-104">You can set up rules to separate tasks that must be performed by different users.</span></span> <span data-ttu-id="cc5ea-105">Este concepto se denomina "segregación de controles".</span><span class="sxs-lookup"><span data-stu-id="cc5ea-105">This concept is named segregation of duties.</span></span> <span data-ttu-id="cc5ea-106">Por ejemplo, puede que no desee que sea la misma persona la que confirme la recepción de mercancías y la que procese el pago al proveedor.</span><span class="sxs-lookup"><span data-stu-id="cc5ea-106">For example, you might not want the same person to acknowledge the receipt of goods and to process payment to the vendor.</span></span> <span data-ttu-id="cc5ea-107">La segregación de controles ayuda a reducir el riesgo de fraude, y también ayuda a detectar errores o irregularidades.</span><span class="sxs-lookup"><span data-stu-id="cc5ea-107">Segregation of duties helps you reduce the risk of fraud, and it also helps you detect errors or irregularities.</span></span> <span data-ttu-id="cc5ea-108">También puede usar la segregación de controles para aplicar directivas de control internas.</span><span class="sxs-lookup"><span data-stu-id="cc5ea-108">You can also use segregation of duties to enforce internal control policies.</span></span> <span data-ttu-id="cc5ea-109">Complete el siguiente procedimiento para crear una regla.</span><span class="sxs-lookup"><span data-stu-id="cc5ea-109">Complete the following procedure to create a rule.</span></span> <span data-ttu-id="cc5ea-110">Es necesario ser administrador del sistema para completar el procedimiento.</span><span class="sxs-lookup"><span data-stu-id="cc5ea-110">You must be a system administrator to complete the procedure.</span></span>

1. <span data-ttu-id="cc5ea-111">Vaya a **Administración del sistema** > **Seguridad** > **Segregación de controles** > **Reglas de segregación de controles**.</span><span class="sxs-lookup"><span data-stu-id="cc5ea-111">Go to **System administration** > **Security** > **Segregation of duties** > **Segregation of duties rules**.</span></span>
2. <span data-ttu-id="cc5ea-112">Haga clic en **Nuevo**.</span><span class="sxs-lookup"><span data-stu-id="cc5ea-112">Click **New**.</span></span>
3. <span data-ttu-id="cc5ea-113">En el campo **Nombre** escriba un valor para la regla.</span><span class="sxs-lookup"><span data-stu-id="cc5ea-113">In the **Name** field, type a value for the rule.</span></span>
4. <span data-ttu-id="cc5ea-114">En el campo **Primer deber**, haga clic en el botón desplegable para abrir la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="cc5ea-114">In the **First duty** field, click the drop-down button to open the lookup.</span></span>
5. <span data-ttu-id="cc5ea-115">En la lista, busque y seleccione el registro deseado.</span><span class="sxs-lookup"><span data-stu-id="cc5ea-115">In the list, find and select the desired record.</span></span> <span data-ttu-id="cc5ea-116">Seleccione el primer deber controlado por la regla.</span><span class="sxs-lookup"><span data-stu-id="cc5ea-116">Select the first duty that is controlled by the rule.</span></span>
6. <span data-ttu-id="cc5ea-117">En el campo **Segundo deber**, haga clic en el botón desplegable para abrir la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="cc5ea-117">In the **Second duty** field, click the drop-down button to open the lookup.</span></span> 
7. <span data-ttu-id="cc5ea-118">En la lista, busque y seleccione el registro deseado.</span><span class="sxs-lookup"><span data-stu-id="cc5ea-118">In the list, find and select the desired record.</span></span> <span data-ttu-id="cc5ea-119">Seleccione el segundo deber controlado por la regla.</span><span class="sxs-lookup"><span data-stu-id="cc5ea-119">Select the second duty that is controlled by the rule.</span></span>
10. <span data-ttu-id="cc5ea-120">En el campo **Gravedad**, seleccione una opción.</span><span class="sxs-lookup"><span data-stu-id="cc5ea-120">In the **Severity** field, select an option.</span></span> <span data-ttu-id="cc5ea-121">Seleccione la gravedad del riesgo que se genera cuando el mismo usuario o rol realiza ambos deberes.</span><span class="sxs-lookup"><span data-stu-id="cc5ea-121">Select the severity of the risk that occurs when the same user or role performs both duties.</span></span>  
11. <span data-ttu-id="cc5ea-122">En el campo **Riesgo de seguridad**, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="cc5ea-122">In the **Security risk** field, type a value.</span></span> <span data-ttu-id="cc5ea-123">Escriba una descripción del riesgo para la seguridad.</span><span class="sxs-lookup"><span data-stu-id="cc5ea-123">Enter a description of the security risk.</span></span>  
12. <span data-ttu-id="cc5ea-124">En el campo **Mitigación de seguridad**, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="cc5ea-124">In the **Security mitigation** field, type a value.</span></span> <span data-ttu-id="cc5ea-125">Escriba una descripción de las acciones para mitigar el riesgo de seguridad.</span><span class="sxs-lookup"><span data-stu-id="cc5ea-125">Enter a description of the actions that you take to mitigate the security risk.</span></span> <span data-ttu-id="cc5ea-126">Por ejemplo, puede mitigar el riesgo realizando revisiones más detalladas del proceso, realizando una revisión administrativa mensual o compartiendo recursos con otros departamentos.</span><span class="sxs-lookup"><span data-stu-id="cc5ea-126">For example, you can mitigate the risk by conducting more detailed reviews of the process, by conducting a monthly managerial review, or by sharing resources with other departments.</span></span>     
13. <span data-ttu-id="cc5ea-127">Haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="cc5ea-127">Click **Save**.</span></span>

> [!IMPORTANT] 
> <span data-ttu-id="cc5ea-128">El cumplimiento de las reglas para la segregación de controles no se verifica cuando crea una regla.</span><span class="sxs-lookup"><span data-stu-id="cc5ea-128">Compliance with the rules for segregation of duties is not verified when you create a rule.</span></span> <span data-ttu-id="cc5ea-129">Puede crear una regla que cree un conflicto para los roles existentes.</span><span class="sxs-lookup"><span data-stu-id="cc5ea-129">You can create a rule that creates a conflict for existing roles.</span></span> <span data-ttu-id="cc5ea-130">Las asignaciones de roles de usuario existentes también pueden estar en conflicto con la nueva regla.</span><span class="sxs-lookup"><span data-stu-id="cc5ea-130">Existing user role assignments can also be in conflict with the new rule.</span></span> <span data-ttu-id="cc5ea-131">Debe validar el cumplimiento después de crear o modificar una regla.</span><span class="sxs-lookup"><span data-stu-id="cc5ea-131">You must validate compliance after you create or modify a rule.</span></span> <span data-ttu-id="cc5ea-132">Para más información, consulte [Identificar y resolver conflictos de segregación de controles](identify-resolve-conflicts-segregation-duties.md)</span><span class="sxs-lookup"><span data-stu-id="cc5ea-132">For more information, see [Identify and resolve conflicts in segregation of duties](identify-resolve-conflicts-segregation-duties.md)</span></span>


[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]