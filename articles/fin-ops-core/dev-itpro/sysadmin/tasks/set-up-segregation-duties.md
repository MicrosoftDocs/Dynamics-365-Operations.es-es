---
title: Configuración de segregación de controles
description: Puede configurar reglas para tareas diferentes que deban llevar a cabo diferentes usuarios.
author: peakerbl
manager: AnnBe
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
ms.openlocfilehash: 1c1521d6bbbe12964fef0942fcc4943f12a4360a
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/09/2021
ms.locfileid: "5562506"
---
# <a name="set-up-segregation-of-duties"></a><span data-ttu-id="7879e-103">Configuración de segregación de controles</span><span class="sxs-lookup"><span data-stu-id="7879e-103">Set up segregation of duties</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="7879e-104">Puede configurar reglas para tareas diferentes que deban llevar a cabo diferentes usuarios.</span><span class="sxs-lookup"><span data-stu-id="7879e-104">You can set up rules to separate tasks that must be performed by different users.</span></span> <span data-ttu-id="7879e-105">Este concepto se denomina "segregación de controles".</span><span class="sxs-lookup"><span data-stu-id="7879e-105">This concept is named segregation of duties.</span></span> <span data-ttu-id="7879e-106">Por ejemplo, puede que no desee que sea la misma persona la que confirme la recepción de mercancías y la que procese el pago al proveedor.</span><span class="sxs-lookup"><span data-stu-id="7879e-106">For example, you might not want the same person to acknowledge the receipt of goods and to process payment to the vendor.</span></span> <span data-ttu-id="7879e-107">La segregación de controles ayuda a reducir el riesgo de fraude, y también ayuda a detectar errores o irregularidades.</span><span class="sxs-lookup"><span data-stu-id="7879e-107">Segregation of duties helps you reduce the risk of fraud, and it also helps you detect errors or irregularities.</span></span> <span data-ttu-id="7879e-108">También puede usar la segregación de controles para aplicar directivas de control internas.</span><span class="sxs-lookup"><span data-stu-id="7879e-108">You can also use segregation of duties to enforce internal control policies.</span></span> <span data-ttu-id="7879e-109">Complete el siguiente procedimiento para crear una regla.</span><span class="sxs-lookup"><span data-stu-id="7879e-109">Complete the following procedure to create a rule.</span></span> <span data-ttu-id="7879e-110">Es necesario ser administrador del sistema para completar el procedimiento.</span><span class="sxs-lookup"><span data-stu-id="7879e-110">You must be a system administrator to complete the procedure.</span></span>

1. <span data-ttu-id="7879e-111">Vaya a **Administración del sistema** > **Seguridad** > **Segregación de controles** > **Reglas de segregación de controles**.</span><span class="sxs-lookup"><span data-stu-id="7879e-111">Go to **System administration** > **Security** > **Segregation of duties** > **Segregation of duties rules**.</span></span>
2. <span data-ttu-id="7879e-112">Haga clic en **Nuevo**.</span><span class="sxs-lookup"><span data-stu-id="7879e-112">Click **New**.</span></span>
3. <span data-ttu-id="7879e-113">En el campo **Nombre** escriba un valor para la regla.</span><span class="sxs-lookup"><span data-stu-id="7879e-113">In the **Name** field, type a value for the rule.</span></span>
4. <span data-ttu-id="7879e-114">En el campo **Primer deber**, haga clic en el botón desplegable para abrir la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="7879e-114">In the **First duty** field, click the drop-down button to open the lookup.</span></span>
5. <span data-ttu-id="7879e-115">En la lista, busque y seleccione el registro deseado.</span><span class="sxs-lookup"><span data-stu-id="7879e-115">In the list, find and select the desired record.</span></span> <span data-ttu-id="7879e-116">Seleccione el primer deber controlado por la regla.</span><span class="sxs-lookup"><span data-stu-id="7879e-116">Select the first duty that is controlled by the rule.</span></span>
6. <span data-ttu-id="7879e-117">En el campo **Segundo deber**, haga clic en el botón desplegable para abrir la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="7879e-117">In the **Second duty** field, click the drop-down button to open the lookup.</span></span> 
7. <span data-ttu-id="7879e-118">En la lista, busque y seleccione el registro deseado.</span><span class="sxs-lookup"><span data-stu-id="7879e-118">In the list, find and select the desired record.</span></span> <span data-ttu-id="7879e-119">Seleccione el segundo deber controlado por la regla.</span><span class="sxs-lookup"><span data-stu-id="7879e-119">Select the second duty that is controlled by the rule.</span></span>
10. <span data-ttu-id="7879e-120">En el campo **Gravedad**, seleccione una opción.</span><span class="sxs-lookup"><span data-stu-id="7879e-120">In the **Severity** field, select an option.</span></span> <span data-ttu-id="7879e-121">Seleccione la gravedad del riesgo que se genera cuando el mismo usuario o rol realiza ambos deberes.</span><span class="sxs-lookup"><span data-stu-id="7879e-121">Select the severity of the risk that occurs when the same user or role performs both duties.</span></span>  
11. <span data-ttu-id="7879e-122">En el campo **Riesgo de seguridad**, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="7879e-122">In the **Security risk** field, type a value.</span></span> <span data-ttu-id="7879e-123">Escriba una descripción del riesgo para la seguridad.</span><span class="sxs-lookup"><span data-stu-id="7879e-123">Enter a description of the security risk.</span></span>  
12. <span data-ttu-id="7879e-124">En el campo **Mitigación de seguridad**, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="7879e-124">In the **Security mitigation** field, type a value.</span></span> <span data-ttu-id="7879e-125">Escriba una descripción de las acciones para mitigar el riesgo de seguridad.</span><span class="sxs-lookup"><span data-stu-id="7879e-125">Enter a description of the actions that you take to mitigate the security risk.</span></span> <span data-ttu-id="7879e-126">Por ejemplo, puede mitigar el riesgo realizando revisiones más detalladas del proceso, realizando una revisión administrativa mensual o compartiendo recursos con otros departamentos.</span><span class="sxs-lookup"><span data-stu-id="7879e-126">For example, you can mitigate the risk by conducting more detailed reviews of the process, by conducting a monthly managerial review, or by sharing resources with other departments.</span></span>     
13. <span data-ttu-id="7879e-127">Haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="7879e-127">Click **Save**.</span></span>

> [!IMPORTANT] 
> <span data-ttu-id="7879e-128">El cumplimiento de las reglas para la segregación de controles no se verifica cuando crea una regla.</span><span class="sxs-lookup"><span data-stu-id="7879e-128">Compliance with the rules for segregation of duties is not verified when you create a rule.</span></span> <span data-ttu-id="7879e-129">Puede crear una regla que cree un conflicto para los roles existentes.</span><span class="sxs-lookup"><span data-stu-id="7879e-129">You can create a rule that creates a conflict for existing roles.</span></span> <span data-ttu-id="7879e-130">Las asignaciones de roles de usuario existentes también pueden estar en conflicto con la nueva regla.</span><span class="sxs-lookup"><span data-stu-id="7879e-130">Existing user role assignments can also be in conflict with the new rule.</span></span> <span data-ttu-id="7879e-131">Debe validar el cumplimiento después de crear o modificar una regla.</span><span class="sxs-lookup"><span data-stu-id="7879e-131">You must validate compliance after you create or modify a rule.</span></span> <span data-ttu-id="7879e-132">Para más información, consulte [Identificar y resolver conflictos de segregación de controles](identify-resolve-conflicts-segregation-duties.md)</span><span class="sxs-lookup"><span data-stu-id="7879e-132">For more information, see [Identify and resolve conflicts in segregation of duties](identify-resolve-conflicts-segregation-duties.md)</span></span>


[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]