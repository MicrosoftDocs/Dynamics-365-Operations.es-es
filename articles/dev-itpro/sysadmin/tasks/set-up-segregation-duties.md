--- 
title: "Configuración de segregación de controles"
description: Puede configurar reglas para tareas diferentes que deban llevar a cabo diferentes usuarios.
author: maertenm
manager: AnnBe
ms.date: 11/15/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: sericks
ms.search.scope: Operations
ms.search.region: Global
ms.author: maertenm
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 754f28cd2831d8a9a57c408518d240de460b732b
ms.contentlocale: es-es
ms.lasthandoff: 09/29/2017

---
# <a name="set-up-segregation-of-duties"></a><span data-ttu-id="3193b-103">Configuración de segregación de controles</span><span class="sxs-lookup"><span data-stu-id="3193b-103">Set up segregation of duties</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="3193b-104">Puede configurar reglas para tareas diferentes que deban llevar a cabo diferentes usuarios.</span><span class="sxs-lookup"><span data-stu-id="3193b-104">You can set up rules to separate tasks that must be performed by different users.</span></span> <span data-ttu-id="3193b-105">Este concepto se denomina "segregación de controles".</span><span class="sxs-lookup"><span data-stu-id="3193b-105">This concept is named segregation of duties.</span></span> <span data-ttu-id="3193b-106">Por ejemplo, puede que no desee que sea la misma persona la que confirme la recepción de mercancías y procese el pago al proveedor.</span><span class="sxs-lookup"><span data-stu-id="3193b-106">For example, you might not want the same person both to acknowledge the receipt of goods and to process payment to the vendor.</span></span> <span data-ttu-id="3193b-107">La segregación de controles ayuda a reducir el riesgo de fraude, y también ayuda a detectar errores o irregularidades.</span><span class="sxs-lookup"><span data-stu-id="3193b-107">Segregation of duties helps you reduce the risk of fraud, and it also helps you detect errors or irregularities.</span></span> <span data-ttu-id="3193b-108">También puede usar la segregación de controles para aplicar directivas de control internas.</span><span class="sxs-lookup"><span data-stu-id="3193b-108">You can also use segregation of duties to enforce internal control policies.</span></span> <span data-ttu-id="3193b-109">Complete el siguiente procedimiento para crear una regla.</span><span class="sxs-lookup"><span data-stu-id="3193b-109">Complete the following procedure to create a rule.</span></span> <span data-ttu-id="3193b-110">Es necesario ser administrador del sistema para completar el procedimiento.</span><span class="sxs-lookup"><span data-stu-id="3193b-110">You must be a system administrator to complete the procedure.</span></span> <span data-ttu-id="3193b-111">La empresa de datos de demostración utilizada para crear este procedimiento es DAT.</span><span class="sxs-lookup"><span data-stu-id="3193b-111">The demo data company used to create this procedure is DAT.</span></span> 

1. <span data-ttu-id="3193b-112">Vaya a Administración del sistema > Seguridad > Segregación de controles > Reglas de segregación de controles.</span><span class="sxs-lookup"><span data-stu-id="3193b-112">Go to System administration > Security > Segregation of duties > Segregation of duties rules.</span></span>
2. <span data-ttu-id="3193b-113">Haga clic en Nuevo.</span><span class="sxs-lookup"><span data-stu-id="3193b-113">Click New.</span></span>
3. <span data-ttu-id="3193b-114">En el campo Nombre, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="3193b-114">In the Name field, type a value.</span></span>
    * <span data-ttu-id="3193b-115">Especifique un nombre para la regla.</span><span class="sxs-lookup"><span data-stu-id="3193b-115">Enter a name for the rule.</span></span>  
4. <span data-ttu-id="3193b-116">En el campo Primer deber, haga clic en el botón desplegable para abrir la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="3193b-116">In the First duty field, click the drop-down button to open the lookup.</span></span>
5. <span data-ttu-id="3193b-117">En la lista, busque y seleccione el registro deseado.</span><span class="sxs-lookup"><span data-stu-id="3193b-117">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="3193b-118">Seleccione el primer deber controlado por la regla.</span><span class="sxs-lookup"><span data-stu-id="3193b-118">Select the first duty that is controlled by the rule.</span></span>  
6. <span data-ttu-id="3193b-119">En la lista, haga clic en el vínculo de la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="3193b-119">In the list, click the link in the selected row.</span></span>
7. <span data-ttu-id="3193b-120">En el campo Segundo deber, haga clic en el botón desplegable para abrir la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="3193b-120">In the Second duty field, click the drop-down button to open the lookup.</span></span>
8. <span data-ttu-id="3193b-121">En la lista, busque y seleccione el registro deseado.</span><span class="sxs-lookup"><span data-stu-id="3193b-121">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="3193b-122">Seleccione el segundo deber controlado por la regla.</span><span class="sxs-lookup"><span data-stu-id="3193b-122">Select the second duty that is controlled by the rule.</span></span>  
9. <span data-ttu-id="3193b-123">En la lista, haga clic en el vínculo de la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="3193b-123">In the list, click the link in the selected row.</span></span>
10. <span data-ttu-id="3193b-124">En el campo Gravedad, seleccione una opción.</span><span class="sxs-lookup"><span data-stu-id="3193b-124">In the Severity field, select an option.</span></span>
    * <span data-ttu-id="3193b-125">Seleccione la gravedad del riesgo que se genera cuando el mismo usuario o rol realiza ambos deberes.</span><span class="sxs-lookup"><span data-stu-id="3193b-125">Select the severity of the risk that occurs when the same user or role performs both duties.</span></span>  
11. <span data-ttu-id="3193b-126">En el campo Riesgo de seguridad, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="3193b-126">In the Security risk field, type a value.</span></span>
    * <span data-ttu-id="3193b-127">Escriba una descripción del riesgo para la seguridad.</span><span class="sxs-lookup"><span data-stu-id="3193b-127">Enter a description of the security risk.</span></span>  
12. <span data-ttu-id="3193b-128">En el campo Mitigación de seguridad, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="3193b-128">In the Security mitigation field, type a value.</span></span>
    * <span data-ttu-id="3193b-129">Escriba una descripción de las acciones para mitigar el riesgo de seguridad.</span><span class="sxs-lookup"><span data-stu-id="3193b-129">Enter a description of the actions that you take to mitigate the security risk.</span></span> <span data-ttu-id="3193b-130">Por ejemplo, puede mitigar el riesgo realizando revisiones más detalladas del proceso, realizando una revisión administrativa mensual o compartiendo recursos con otros departamentos.</span><span class="sxs-lookup"><span data-stu-id="3193b-130">For example, you can mitigate the risk by conducting more detailed reviews of the process, by conducting a monthly managerial review, or by sharing resources with other departments.</span></span>  
13. <span data-ttu-id="3193b-131">Haga clic en Guardar.</span><span class="sxs-lookup"><span data-stu-id="3193b-131">Click Save.</span></span>


