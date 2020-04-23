---
title: Plantilla de L. MAT
description: Una plantilla de lista de materiales (L. MAT) le proporciona una lista estandarizada de componentes para objetos de servicio de los que se realiza un mantenimiento periódico.
author: ShylaThompson
manager: tfehr
ms.date: 09/19/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SMATemplateBOMTable
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: ShylaThompson
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 8842a293a50efb24590784cc52ef0254eca10e3a
ms.sourcegitcommit: 4f9912439ff78acf0c754d5bff972c4b85763093
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/02/2020
ms.locfileid: "3206551"
---
# <a name="template-boms"></a><span data-ttu-id="a6724-103">Plantilla de L. MAT</span><span class="sxs-lookup"><span data-stu-id="a6724-103">Template BOMs</span></span>    

[!include [banner](../includes/banner.md)]


<span data-ttu-id="a6724-104">Una plantilla de lista de materiales (L. MAT) le proporciona una lista estandarizada de componentes para objetos de servicio de los que se realiza un mantenimiento periódico.</span><span class="sxs-lookup"><span data-stu-id="a6724-104">A template bill of materials (BOM) provides you with a standardized list of components for service objects that are serviced regularly.</span></span> <span data-ttu-id="a6724-105">Los componentes que aparecen en la plantilla de L. MAT representan los subcomponentes individuales del objeto de servicio.</span><span class="sxs-lookup"><span data-stu-id="a6724-105">The components that are listed in the template BOM represent the individual subcomponents of the service object.</span></span> <span data-ttu-id="a6724-106">Aplicando una L. MAT de plantilla a un objeto de servicio, puede realizar un registro de los subcomponentes que se han sustituido en el objeto de servicio.</span><span class="sxs-lookup"><span data-stu-id="a6724-106">By applying a template BOM to a service object, you can keep a record of the subcomponents that have been replaced on the service object.</span></span>

<span data-ttu-id="a6724-107">Para aplicar una plantilla de L. MAT a un acuerdo de servicio o a un pedido de servicio, debe vincularla a la relación de objetos de servicio.</span><span class="sxs-lookup"><span data-stu-id="a6724-107">To apply a template BOM to a service agreement or a service order, you attach it to a service object relation.</span></span>


> [!NOTE]
> <P><span data-ttu-id="a6724-108">Puede aplicar solo una plantilla de L. MAT con un objeto de servicio.</span><span class="sxs-lookup"><span data-stu-id="a6724-108">You can apply only one template BOM to a service object.</span></span></P>

## <a name="create-a-template-bom"></a><span data-ttu-id="a6724-109">Crear plantilla de L. MAT manual</span><span class="sxs-lookup"><span data-stu-id="a6724-109">Create a template BOM</span></span>

<span data-ttu-id="a6724-110">La siguiente tabla contiene información sobre los distintos métodos que puede usar para crear una plantilla de L. MAT.</span><span class="sxs-lookup"><span data-stu-id="a6724-110">The following table contains information about the various methods that you can use to create a template BOM.</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="a6724-111">Método</span><span class="sxs-lookup"><span data-stu-id="a6724-111">Method</span></span></p></th>
<th><p><span data-ttu-id="a6724-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="a6724-112">Description</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a6724-113">Producción</span><span class="sxs-lookup"><span data-stu-id="a6724-113">Production</span></span></p></td>
<td><p><span data-ttu-id="a6724-114">La L. MAT de plantilla se basa en un pedido de producción.</span><span class="sxs-lookup"><span data-stu-id="a6724-114">The template BOM is based on a production order.</span></span> <span data-ttu-id="a6724-115">Esta opción solo es aplicable si trabaja en un ambiente de producción.</span><span class="sxs-lookup"><span data-stu-id="a6724-115">This option is applicable only if you operate in a production environment.</span></span> <span data-ttu-id="a6724-116">La ventaja es que dispone de un listado actual y detallado de los componentes que componen un artículo.</span><span class="sxs-lookup"><span data-stu-id="a6724-116">The benefit is that you have a current, detailed listing of the components that make up an item.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a6724-117">Artículo BOM</span><span class="sxs-lookup"><span data-stu-id="a6724-117">Item BOM</span></span></p></td>
<td><p><span data-ttu-id="a6724-118">La L. MAT de plantilla se basa en una L. MAT de artículo.</span><span class="sxs-lookup"><span data-stu-id="a6724-118">The template BOM is based on an item BOM.</span></span> <span data-ttu-id="a6724-119">La L. MAT del artículo, a diferencia de la L. MAT de producción, es una lista estática de los componentes que componen un artículo.</span><span class="sxs-lookup"><span data-stu-id="a6724-119">The item BOM, unlike the production BOM, is a static list of the components that make up an item.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a6724-120">Plantilla existente</span><span class="sxs-lookup"><span data-stu-id="a6724-120">Existing template</span></span></p></td>
<td><p><span data-ttu-id="a6724-121">La plantilla se basa en una L. MAT de plantilla existente.</span><span class="sxs-lookup"><span data-stu-id="a6724-121">The template is based on an existing template BOM.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a6724-122">Manual</span><span class="sxs-lookup"><span data-stu-id="a6724-122">Manual</span></span></p></td>
<td><p><span data-ttu-id="a6724-123">Si sabe qué piezas de repuesto son las que se sustituyen habitualmente en un objeto de servicio, podrá crear su L. MAT de plantilla de forma manual.</span><span class="sxs-lookup"><span data-stu-id="a6724-123">If you know what spare parts are typically replaced on a service object, you can create your template BOM manually.</span></span> <span data-ttu-id="a6724-124">Este método ayuda a garantizar que los componentes que se incluyen en la plantilla reflejen los requisitos reales de su área de trabajo.</span><span class="sxs-lookup"><span data-stu-id="a6724-124">This method helps make sure that the components that are included in the template reflect the actual requirements of your workplace.</span></span></p></td>
</tr>
</tbody>
</table>


## <a name="apply-the-template-bom-to-a-service-agreement-or-service-order"></a><span data-ttu-id="a6724-125">Aplicar la L. MAT de plantilla a un acuerdo de servicio o en un pedido de servicio</span><span class="sxs-lookup"><span data-stu-id="a6724-125">Apply the template BOM to a service agreement or service order</span></span>

<span data-ttu-id="a6724-126">Puede aplicar una plantilla de L. MAT a un acuerdo de servicio, a un pedido de servicio, o a ambos.</span><span class="sxs-lookup"><span data-stu-id="a6724-126">You can apply a template BOM to a service agreement, a service order, or both.</span></span> <span data-ttu-id="a6724-127">El primero normalmente abarca una relación de largo plazo con un cliente.</span><span class="sxs-lookup"><span data-stu-id="a6724-127">The service agreement usually covers a long-term relationship with a customer.</span></span> <span data-ttu-id="a6724-128">El historial de sustituciones registradas en la L. MAT de servicio está formado por datos de los que podrá disponer para el acuerdo de servicio.</span><span class="sxs-lookup"><span data-stu-id="a6724-128">The history of replacements that is recorded in the service BOM is useful data to have for the service agreement.</span></span>

<span data-ttu-id="a6724-129">También puede aplicar una L. MAT de plantilla a un pedido de servicio para registrar el historial del servicio que se ha realizado en un objeto de servicio.</span><span class="sxs-lookup"><span data-stu-id="a6724-129">You can also apply a template BOM to a service order to record the history of the service that has been performed on a service object.</span></span>

## <a name="copy-the-history-of-a-service-bom"></a><span data-ttu-id="a6724-130">Copiar el historial de una L. MAT de servicio</span><span class="sxs-lookup"><span data-stu-id="a6724-130">Copy the history of a service BOM</span></span>

<span data-ttu-id="a6724-131">Puede copiar el historial de una línea de L. MAT de servicio de un acuerdo de servicio a otro.</span><span class="sxs-lookup"><span data-stu-id="a6724-131">You can copy the history of a service BOM line from one service agreement to another service agreement.</span></span> <span data-ttu-id="a6724-132">Al copiar el historial de servicio entre los acuerdos de servicio, puede conservar el registro de las sustituciones realizadas a un artículo.</span><span class="sxs-lookup"><span data-stu-id="a6724-132">By copying the service history between service agreements, you can preserve the record of replacements for an item.</span></span>

<span data-ttu-id="a6724-133">**Ejemplo**</span><span class="sxs-lookup"><span data-stu-id="a6724-133">**Example**</span></span>

<span data-ttu-id="a6724-134">Ha configurado un acuerdo de servicio de tres años para el vehículo de un cliente.</span><span class="sxs-lookup"><span data-stu-id="a6724-134">You have set up a three-year service agreement for a customer's car.</span></span> <span data-ttu-id="a6724-135">Durante ese período, el cliente se acostumbrará al buen servicio prestado por la empresa.</span><span class="sxs-lookup"><span data-stu-id="a6724-135">During that period, the customer becomes accustomed to the good service that the company provides.</span></span> <span data-ttu-id="a6724-136">Por lo tanto, cuando expire el contrato, el cliente deseará configurar uno nuevo.</span><span class="sxs-lookup"><span data-stu-id="a6724-136">Therefore, after the agreement expires, the customer wants to set up a new one.</span></span> <span data-ttu-id="a6724-137">Ahora puede negociar un acuerdo más favorable para la empresa.</span><span class="sxs-lookup"><span data-stu-id="a6724-137">You are now able to negotiate a more favorable agreement for the company.</span></span> <span data-ttu-id="a6724-138">Dado que el registro de componentes sustituidos puede resultar de utilidad en el futuro, puede copiar el historial de la L. MAT de servicio en el nuevo acuerdo.</span><span class="sxs-lookup"><span data-stu-id="a6724-138">Because the record of replaced components might be useful in the future, you copy the history of the service BOM to the new agreement.</span></span>

## <a name="modify-the-template-bom"></a><span data-ttu-id="a6724-139">Modificar la plantilla de L. MAT</span><span class="sxs-lookup"><span data-stu-id="a6724-139">Modify the template BOM</span></span>

<span data-ttu-id="a6724-140">Si una plantilla de L. MAT no se ha vinculado a un objeto de servicio, puede modificar o eliminar las líneas.</span><span class="sxs-lookup"><span data-stu-id="a6724-140">If a template BOM has not been attached to a service object, you can modify or delete lines in it.</span></span> <span data-ttu-id="a6724-141">Una vez vinculada la plantilla de L. MAT a un objeto de servicio, puede modificar solo la versión local de la L. MAT.</span><span class="sxs-lookup"><span data-stu-id="a6724-141">After the template BOM is attached to a service object, you can modify only the local version of the BOM.</span></span> <span data-ttu-id="a6724-142">Si desea duplicar la configuración de una versión local de una plantilla de L. MAT, puede crear una nueva plantilla de L. MAT basada en la versión local.</span><span class="sxs-lookup"><span data-stu-id="a6724-142">If you want to duplicate the setup of a local version of a template BOM, you can create a new template BOM based on the local version.</span></span> <span data-ttu-id="a6724-143">Para obtener más información, consulte [Modificar un L. MAT de servicio](modify-service-bom.md).</span><span class="sxs-lookup"><span data-stu-id="a6724-143">For more information, see [Modify a Service BOM](modify-service-bom.md).</span></span>

<span data-ttu-id="a6724-144">Si reemplaza un artículo que esté en la L. MAT, puede registrar la sustitución en la línea de L. MAT en el diseñador de L. MAT.</span><span class="sxs-lookup"><span data-stu-id="a6724-144">If you replace an item in the BOM, you can register the replacement on the BOM line in the BOM designer.</span></span> <span data-ttu-id="a6724-145">Si lo desea, también es posible crear una línea de pedido de servicio para el objeto de sustitución.</span><span class="sxs-lookup"><span data-stu-id="a6724-145">Optionally, you can create a service order line for the replacement object.</span></span> <span data-ttu-id="a6724-146">Si crea una línea de pedido de servicio, puede facturar el artículo de sustitución.</span><span class="sxs-lookup"><span data-stu-id="a6724-146">If you create a service order line, you can invoice the replacement item.</span></span> <span data-ttu-id="a6724-147">Si no crea una línea de pedido de servicio para una sustitución, el registro de sustitución se conserva para realizar un seguimiento del historial del objeto de servicio.</span><span class="sxs-lookup"><span data-stu-id="a6724-147">If you do not create a service order line for a replacement, the replacement registration is kept to track the history of the service object.</span></span>

## <a name="change-how-information-on-the-bom-line-is-displayed"></a><span data-ttu-id="a6724-148">Cambiar el modo en que se muestra la información de la línea de L. MAT</span><span class="sxs-lookup"><span data-stu-id="a6724-148">Change how information on the BOM line is displayed</span></span>

<span data-ttu-id="a6724-149">Puede cambiar el modo que se muestra la información de la línea de L. MAT para todas las listas L. MAT de plantilla y de servicio.</span><span class="sxs-lookup"><span data-stu-id="a6724-149">You can change the way that information on the BOM line is displayed for all template and service BOMs.</span></span> <span data-ttu-id="a6724-150">Los cambios se aplican a todas las plantillas de L. MAT y L. MAT de servicio.</span><span class="sxs-lookup"><span data-stu-id="a6724-150">The changes are applied to all template BOMs and service BOMs.</span></span> <span data-ttu-id="a6724-151">Esto incluye a todas las que estén asociadas a los objetos de servicio.</span><span class="sxs-lookup"><span data-stu-id="a6724-151">This includes those that are attached to service objects.</span></span>

## <a name="set-up-number-sequences-for-template-boms"></a><span data-ttu-id="a6724-152">Configurar secuencias numéricas para la plantillas de L. MAT</span><span class="sxs-lookup"><span data-stu-id="a6724-152">Set up number sequences for template BOMs</span></span>

<span data-ttu-id="a6724-153">Para usar las L. MAT de plantilla, debe configurar dos secuencias numéricas.</span><span class="sxs-lookup"><span data-stu-id="a6724-153">To use template BOMs, you must set up two number sequences.</span></span> <span data-ttu-id="a6724-154">Configure una secuencia numérica para la L. MAT de plantilla y otra para el número de línea del historial de L. MAT.</span><span class="sxs-lookup"><span data-stu-id="a6724-154">Set up one number sequence for the template BOM and one for the BOM history line number.</span></span>


> [!NOTE]
> <P><span data-ttu-id="a6724-155">Las secuencias numéricas se usan para asignar identificadores a los registros que los necesiten.</span><span class="sxs-lookup"><span data-stu-id="a6724-155">Number sequences are used to allocate identifiers to records that require them.</span></span> <span data-ttu-id="a6724-156">Antes de poder asignar una secuencia numérica a una L. MAT de plantilla o a un número de línea del historial de L. MAT, debe configurar los códigos de secuencias numéricas.</span><span class="sxs-lookup"><span data-stu-id="a6724-156">Before you can assign a number sequence to a template BOM or a BOM history line number, you must set up number sequences codes.</span></span></P>


## <a name="set-up-number-sequences"></a><span data-ttu-id="a6724-157">Configurar secuencias numéricas</span><span class="sxs-lookup"><span data-stu-id="a6724-157">Set up number sequences</span></span>

1.  <span data-ttu-id="a6724-158">En la página de lista **Secuencias numéricas**, cree las secuencias numéricas para las plantillas de L. MAT. y el número de línea del historial de L. MAT.</span><span class="sxs-lookup"><span data-stu-id="a6724-158">On the **Number sequences** list page, create number sequences for template BOMs and the BOM history line number.</span></span> 

2.  <span data-ttu-id="a6724-159">Haga clic en **Gestión de servicio** \> **Configuración** \> **Parámetros de la gestión de servicio**.</span><span class="sxs-lookup"><span data-stu-id="a6724-159">Click **Service management** \> **Setup** \> **Service management parameters**.</span></span>

3.  <span data-ttu-id="a6724-160">Haga clic en **Secuencias numéricas** y, a continuación, seleccione un código de secuencia numérica para las referencias de la secuencia numérica que haya creado en el formulario **Secuencias numéricas**.</span><span class="sxs-lookup"><span data-stu-id="a6724-160">Click **Number sequences**, and then select a number sequence code for the number sequence references that you created in the **Number sequences** form.</span></span>

4.  <span data-ttu-id="a6724-161">Cierre el formulario para guardar los cambios.</span><span class="sxs-lookup"><span data-stu-id="a6724-161">Close the form to save your changes.</span></span>


> [!NOTE]
> <P><span data-ttu-id="a6724-162">El número de línea del historial de L. MAT lo usa el sistema para asociar las transacciones del historial de L. MAT a un acuerdo de servicio o a un pedido de servicio.</span><span class="sxs-lookup"><span data-stu-id="a6724-162">The BOM history line number is used by the system to associate the transactions in the BOM history with a service agreement or service order.</span></span> <span data-ttu-id="a6724-163">El número no se muestra en la interfaz de usuario.</span><span class="sxs-lookup"><span data-stu-id="a6724-163">The number is not displayed in the user interface.</span></span></P>



## <a name="see-also"></a><span data-ttu-id="a6724-164">Consulte también</span><span class="sxs-lookup"><span data-stu-id="a6724-164">See also</span></span>

[<span data-ttu-id="a6724-165">Crear plantilla de L. MAT manual</span><span class="sxs-lookup"><span data-stu-id="a6724-165">Create a template BOM</span></span>](create-template-bom.md)

[<span data-ttu-id="a6724-166">Gestionar plantilla de L. MAT en las relaciones de objetos de acuerdos de servicio</span><span class="sxs-lookup"><span data-stu-id="a6724-166">Manage template BOMs on object relations</span></span>](manage-template-boms-on-object-relations.md)

[<span data-ttu-id="a6724-167">Modificar un L. MAT de servicio</span><span class="sxs-lookup"><span data-stu-id="a6724-167">Modify a Service BOM</span></span>](modify-service-bom.md)

 


