---
title: Crear y aplicar términos de retención de pago a proveedores
description: Este tema proporciona información acerca de la configuración y el mantenimiento de los términos de retención de pagos a proveedores.
author: kfend
manager: AnnBe
ms.date: 05/26/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Service industries
ms.author: v-radsh
ms.dyn365.ops.version: 7
ms.search.validFrom: 2019-01-15
ms.openlocfilehash: 0e14050a79220b5d02763a025040edb934489d00
ms.sourcegitcommit: cecd97fd74ff7b31f1a677e8fdf3e233aa28ef5a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/28/2020
ms.locfileid: "3410265"
---
# <a name="create-and-apply-vendor-payment-retention-terms"></a><span data-ttu-id="8278b-103">Crear y aplicar términos de retención de pago a proveedores</span><span class="sxs-lookup"><span data-stu-id="8278b-103">Create and apply vendor payment retention terms</span></span>

[!include [banner](../includes/banner.md)] 

<span data-ttu-id="8278b-104">Configurar los términos de retención de pagos del proveedor para un proyecto es útil cuando su organización desea retener parte de los pagos realizados a un proveedor.</span><span class="sxs-lookup"><span data-stu-id="8278b-104">Setting up vendor payment retention terms for a project is useful when your organization wants to retain part of the payments made to a vendor.</span></span> <span data-ttu-id="8278b-105">Por ejemplo, cuando desea retener el pago a un proveedor hasta que los productos entregados cumplan con sus expectativas.</span><span class="sxs-lookup"><span data-stu-id="8278b-105">For example, when you want to hold payment to a vendor until the products delivered meet your expectations.</span></span> <span data-ttu-id="8278b-106">Cuando negocie un contrato de proveedor, puede especificar las condiciones de retención de pagos de proveedor.</span><span class="sxs-lookup"><span data-stu-id="8278b-106">Vendor payment retention terms can be specified when you negotiate a vendor contract.</span></span>

## <a name="create-vendor-payment-retention-terms"></a><span data-ttu-id="8278b-107">Condiciones de retención de pagos a proveedor</span><span class="sxs-lookup"><span data-stu-id="8278b-107">Create vendor payment retention terms</span></span>

<span data-ttu-id="8278b-108">Puede especificar el porcentaje de un pago de proveedor a retener y el porcentaje de los importes retenidos anteriormente a liberar.</span><span class="sxs-lookup"><span data-stu-id="8278b-108">You can enter the percentage of vendor payment for retention and the percentage of the previously retained amounts to be released.</span></span> <span data-ttu-id="8278b-109">Los importes se retienen automáticamente en las facturas de proveedor hasta que el contrato alcance el estado especificado de finalización.</span><span class="sxs-lookup"><span data-stu-id="8278b-109">Amounts are automatically retained on vendor invoices until the contract reaches the specified state of completion.</span></span> <span data-ttu-id="8278b-110">Una vez que haya configurado las condiciones de retención para un proveedor, puede aplicarlas a cualquier proyecto de ese proveedor.</span><span class="sxs-lookup"><span data-stu-id="8278b-110">After you set up the retention terms, you can apply them to any project for that vendor.</span></span>

<span data-ttu-id="8278b-111">Use los pasos siguientes para configurar y mantener las condiciones de retención de pagos a proveedor.</span><span class="sxs-lookup"><span data-stu-id="8278b-111">Use the following steps to set up and maintain retention terms for vendor payments.</span></span> 

1. <span data-ttu-id="8278b-112">Vaya a **Gestión de proyectos y contabilidad** > **Retencion** > **Términos de retención de pago a proveedor**.</span><span class="sxs-lookup"><span data-stu-id="8278b-112">Go to **Project management and accounting** > **Retention** > **Vendor payment retention terms**.</span></span>
2. <span data-ttu-id="8278b-113">Seleccione **Nuevo** para agregar una nueva condición de retención de proveedor.</span><span class="sxs-lookup"><span data-stu-id="8278b-113">Select **New** to add a new vendor retention term.</span></span> <span data-ttu-id="8278b-114">El valor de **Id. de regla** de la nueva condición se especifica automáticamente.</span><span class="sxs-lookup"><span data-stu-id="8278b-114">The **Rule ID** value for the new term is automatically entered.</span></span> 
3. <span data-ttu-id="8278b-115">Introduzca una breve descripción en el campo **Descripción** y, en la ficha desplegable **Condiciones**, seleccione **Añadir línea** para introducir valores de término para lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="8278b-115">Enter a brief description in the **Description** field, and on the **Terms** FastTab, select **Add line** to enter term values for the following:</span></span>

   - <span data-ttu-id="8278b-116">**Porcentaje de unidades entregado**: introduzca un porcentaje de completado del término.</span><span class="sxs-lookup"><span data-stu-id="8278b-116">**Percentage of units delivered**: Enter a percentage of completion for the term.</span></span> <span data-ttu-id="8278b-117">Los importes se retienen automáticamente en las facturas al proveedor hasta que la etapa de proyecto de finalización sea igual al porcentaje especificado.</span><span class="sxs-lookup"><span data-stu-id="8278b-117">Amounts are automatically retained on vendor invoices until the project stage of completion is equal to the specified percentage.</span></span> <span data-ttu-id="8278b-118">Por ejemplo, si especifica 50,00, los importes se retienen hasta que el proyecto se haya completado en un 50 por ciento.</span><span class="sxs-lookup"><span data-stu-id="8278b-118">For example, if you enter 50.00, amounts are retained until the project is 50 percent completed.</span></span>
   - <span data-ttu-id="8278b-119">**Porcentaje a retener**: introduzca un porcentaje del importe de una factura de proveedor a retener.</span><span class="sxs-lookup"><span data-stu-id="8278b-119">**Percentage to retain**: Enter a percentage of the vendor invoice amount to be retained.</span></span> <span data-ttu-id="8278b-120">Por ejemplo, si especifica 10,00, el 10 por ciento del importe de una facturas a proveedor se retiene hasta que el proyecto alcance el porcentaje de finalización seleccionado en el campo **Porcentaje de unidades entregado**.</span><span class="sxs-lookup"><span data-stu-id="8278b-120">For example, if you enter 10.00, then 10 percent of the amount on a vendor invoice is retained until the project reaches the percentage of completion as set in the **Percentage of units delivered field**.</span></span>
   - <span data-ttu-id="8278b-121">**Porcentaje a liberar**: seleccione **Agregar línea** para introducir un porcentaje de los importes retenidos anteriormente que se liberarán en el nivel seleccionado de finalización del proyecto.</span><span class="sxs-lookup"><span data-stu-id="8278b-121">**Percentage to release**: Select **Add line** to enter a percentage of any previously retained amounts to be released for the selected level of project completion.</span></span>

> [!NOTE]
> <span data-ttu-id="8278b-122">Si tiene más de un hito para distintos niveles de finalización del proyecto, especifique una línea de termino de retención independiente al proveedor para cada regla de retención.</span><span class="sxs-lookup"><span data-stu-id="8278b-122">If you have more than one milestone for different levels of project completion, enter a separate vendor retention term line for each retention rule.</span></span> <span data-ttu-id="8278b-123">Cada línea puede especificar otro porcentaje de retención y otro porcentaje de liberación para cada nivel designado de finalización del proyecto.</span><span class="sxs-lookup"><span data-stu-id="8278b-123">Each line can specify a different retention percentage and a different release percentage for each designated level of project completion.</span></span>

<span data-ttu-id="8278b-124">Una vez que haya creado las condiciones de retención para un proveedor, puede aplicarlos a un proyecto.</span><span class="sxs-lookup"><span data-stu-id="8278b-124">After you create vendor retention terms for a vendor, you can apply the terms to a project.</span></span>

## <a name="apply-vendor-retention-terms-to-a-project"></a><span data-ttu-id="8278b-125">Aplicar términos de retención a proveedor a un proyecto</span><span class="sxs-lookup"><span data-stu-id="8278b-125">Apply vendor retention terms to a project</span></span>

1. <span data-ttu-id="8278b-126">Vaya a **Gestión de proyectos y contabilidad** > **Proyectos** > **Todos los proyectos** y abra un proyecto desde la página de lista de proyectos.</span><span class="sxs-lookup"><span data-stu-id="8278b-126">Go to **Project management and accounting** > **Projects** > **All projects** and open a project from the project list page.</span></span>
2. <span data-ttu-id="8278b-127">En la ficha desplegable **Contratos de proveedor**, seleccione **Agregar línea**.</span><span class="sxs-lookup"><span data-stu-id="8278b-127">On the **Vendor agreements** FastTab, select **Add line**.</span></span>
3. <span data-ttu-id="8278b-128">En el campo **Código de cuenta**, seleccione una de las opciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="8278b-128">In the **Account code field**, select one of the following options:</span></span> 

   - <span data-ttu-id="8278b-129">**Tabla**: las condiciones de retención al proveedor se aplican a un único proveedor.</span><span class="sxs-lookup"><span data-stu-id="8278b-129">**Table**: The vendor retention terms apply to a single vendor.</span></span>
   - <span data-ttu-id="8278b-130">**Grupo**: las condiciones de retención al proveedor se aplican a todos los proveedores de un grupo de proveedores.</span><span class="sxs-lookup"><span data-stu-id="8278b-130">**Group**: The vendor retention terms apply to all vendors in a vendor group.</span></span>
   - <span data-ttu-id="8278b-131">**Todos**: las condiciones de retención al proveedor se aplican a todos los proveedores.</span><span class="sxs-lookup"><span data-stu-id="8278b-131">**All**: The vendor retention terms apply to all vendors.</span></span>

4. <span data-ttu-id="8278b-132">En el campo **Proveedor/Grupo de proveedores**, seleccione el proveedor o el grupo de proveedores a los que las condiciones de retención de proveedor se aplican.</span><span class="sxs-lookup"><span data-stu-id="8278b-132">In the **Vendor/Vendor group field**, select the vendor or vendor group to which the vendor retention terms apply.</span></span> <span data-ttu-id="8278b-133">Este campo no está disponible si ha seleccionado **Todos** en el paso anterior.</span><span class="sxs-lookup"><span data-stu-id="8278b-133">If you selected **All** in the previous step, this field is unavailable.</span></span>
5. <span data-ttu-id="8278b-134">En el campo **Términos de retención a proveedor**, seleccione uno de los términos de retención que creó en el procedimiento anterior.</span><span class="sxs-lookup"><span data-stu-id="8278b-134">In the **Vendor retention terms** field, select the retention terms that you created in the previous procedure.</span></span>
6. <span data-ttu-id="8278b-135">Si el proyecto también tiene condiciones de pago al cobro (AaC) configuradas para el proveedor, especifique el porcentaje de umbral para el proyecto en el campo **Porcentaje del umbral AaC**.</span><span class="sxs-lookup"><span data-stu-id="8278b-135">If the project also has pay-when-paid (PWP) terms set up for the vendor, enter the threshold percentage for the project in the **PWP threshold percentage** field.</span></span>

<span data-ttu-id="8278b-136">Las condiciones de retención de proveedor también se muestran en los pedidos de compra que se crean para el proveedor.</span><span class="sxs-lookup"><span data-stu-id="8278b-136">The vendor retention terms are also displayed on purchase orders that you create for the vendor.</span></span>
