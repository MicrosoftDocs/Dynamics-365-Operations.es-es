---
title: Códigos de paso de oleada
description: Este tema proporciona una visión general de los códigos de paso de la oleada y cómo se usan.
author: josaw1
manager: AnnBe
ms.date: 09/06/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2019-09-30
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 0f89c6098db9e2e3a9aa4ee3666e4b9ae608f054
ms.sourcegitcommit: d8f1135cdbc2deca70bc4b2805a0519253c9a31f
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/06/2019
ms.locfileid: "1992366"
---
# <a name="wave-step-codes"></a><span data-ttu-id="7d3ec-103">Códigos de paso de oleada</span><span class="sxs-lookup"><span data-stu-id="7d3ec-103">Wave step codes</span></span>

[!include [banner](../includes/preview-banner.md)]
[!include [banner](../includes/banner.md)]

## <a name="about-wave-step-codes"></a><span data-ttu-id="7d3ec-104">Acerca de los códigos del paso de oleada</span><span class="sxs-lookup"><span data-stu-id="7d3ec-104">About wave step codes</span></span>

<span data-ttu-id="7d3ec-105">Los códigos del paso de oleada son códigos que los usuarios pueden configurar y usar para vincular instancias específicas de los métodos de la oleada a una plantilla correspondiente.</span><span class="sxs-lookup"><span data-stu-id="7d3ec-105">Wave step codes are codes that users can set up and use to link specific instances of wave methods to a corresponding template.</span></span> <span data-ttu-id="7d3ec-106">Las plantillas incluyen las plantillas para reabastecimiento, la puesta en contenedores, la impresión de etiquetas, el edificio de carga y la ordenación.</span><span class="sxs-lookup"><span data-stu-id="7d3ec-106">The templates include templates for replenishment, containerization, label printing, load building, and sorting.</span></span>

<span data-ttu-id="7d3ec-107">Cuando los códigos del paso de oleada no se usan, los usuarios deben introducir texto para referenciar una plantilla específica del método de la instancia de oleada.</span><span class="sxs-lookup"><span data-stu-id="7d3ec-107">When wave step codes aren't used, users must enter free text to reference a specific template from the wave method instance.</span></span> <span data-ttu-id="7d3ec-108">El texto libre suele tener errores, por lo que los usuarios deben asegurarse de que el texto de paso de oleada que añaden para un método específico de paso de oleada en una plantilla de oleada coincide exactamente con el texto de paso de oleada en la plantilla objetivo.</span><span class="sxs-lookup"><span data-stu-id="7d3ec-108">Free text is prone to error, because users must make sure that the wave step text that they add for a specific wave step method in a wave template exactly matches the wave step text in the target template.</span></span>

<span data-ttu-id="7d3ec-109">Los códigos del paso de oleada para un tipo de etapa específico de la oleada se configuran en una página independiente.</span><span class="sxs-lookup"><span data-stu-id="7d3ec-109">Wave step codes for a specific wave step type are set up on a separate page.</span></span> <span data-ttu-id="7d3ec-110">Para cada instancia del método del paso de oleada en una plantilla de oleada que precisa un código del paso de oleada, el código del paso de oleada se debe seleccionar en una lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="7d3ec-110">For every wave step method instance in a wave template that requires a wave step code, the wave step code must be selected in a drop-down list.</span></span> <span data-ttu-id="7d3ec-111">La selección de una lista desplegable reemplaza la entrada de texto en la factura de servicios y ayuda a reducir el riesgo y el impacto de los errores humanos.</span><span class="sxs-lookup"><span data-stu-id="7d3ec-111">Selection in a drop-down list replaces free text entry and helps reduce the risk and impact of human error.</span></span> <span data-ttu-id="7d3ec-112">Los códigos de configuración se usan para vincular un método de paso de oleada en una plantilla de oleada a una plantilla objetivo para el método.</span><span class="sxs-lookup"><span data-stu-id="7d3ec-112">Setup codes are used to link a wave step method in a wave template to a target template for the method.</span></span>

> [!NOTE]
> <span data-ttu-id="7d3ec-113">El uso de la función de los códigos de paso de la oleada es opcional, y gestionada por entidad jurídica.</span><span class="sxs-lookup"><span data-stu-id="7d3ec-113">Use of the wave step codes feature is optional, and uptake is per legal entity.</span></span> <span data-ttu-id="7d3ec-114">Por lo tanto, si una entidad jurídica específica el uso de la característica, todos los códigos existentes del paso de oleada en esa entidad jurídica se actualizan a la nueva estructura.</span><span class="sxs-lookup"><span data-stu-id="7d3ec-114">Therefore, if a specific legal entity uses the feature, all existing wave step codes in that legal entity are upgraded to the new structure.</span></span>

## <a name="setup-demo"></a><span data-ttu-id="7d3ec-115">Demostración de instalación</span><span class="sxs-lookup"><span data-stu-id="7d3ec-115">Setup demo</span></span> 

<span data-ttu-id="7d3ec-116">Para esta demostración, los datos de prueba deben estar instalados y debe usar los datos de la compañía de prueba **USMF**.</span><span class="sxs-lookup"><span data-stu-id="7d3ec-116">For this demo, demo data must be installed, and you must use the **USMF** demo data company.</span></span>

### <a name="enable-wave-step-codes"></a><span data-ttu-id="7d3ec-117">Habilitar códigos de paso de oleada</span><span class="sxs-lookup"><span data-stu-id="7d3ec-117">Enable wave step codes</span></span>

<span data-ttu-id="7d3ec-118">Siga estos pasos para activar la característica de los códigos del paso de oleada.</span><span class="sxs-lookup"><span data-stu-id="7d3ec-118">Follow these steps to turn on the wave step codes feature.</span></span>

1. <span data-ttu-id="7d3ec-119">Vaya a **Gestión de almacenes \> Configuración \> Parámetros de gestión de almacenes**.</span><span class="sxs-lookup"><span data-stu-id="7d3ec-119">Go to **Warehouse management \> Setup \> Warehouse management parameters**.</span></span>
2. <span data-ttu-id="7d3ec-120">En la pestaña **General**, en la ficha desplegable **Procesado de oleadas**, establezca la opción **Habilitar códigos de paso de oleada** en **Sí**.</span><span class="sxs-lookup"><span data-stu-id="7d3ec-120">On the **General** tab, on the **Wave processing** FastTab, set the **Enable wave step codes** option to **Yes**.</span></span>

<span data-ttu-id="7d3ec-121">Todos los textos libres de paso de oleada se actualizarán a la nueva estructura.</span><span class="sxs-lookup"><span data-stu-id="7d3ec-121">All existing wave step free texts are upgraded to the new structure.</span></span> <span data-ttu-id="7d3ec-122">Una vez que la actualización se complete para una entidad jurídica, la opción **Habilitar códigos de paso de oleada** dejará de estar disponible en la página **Parámetros de la gestión de almacenes** .</span><span class="sxs-lookup"><span data-stu-id="7d3ec-122">After this upgrade is completed for a legal entity, the **Enable wave step codes** option is no longer available on the **Warehouse management parameters** page.</span></span>

<span data-ttu-id="7d3ec-123">Las validaciones se realizan durante la actualización y si falla la actualización, recibirá un mensaje de error.</span><span class="sxs-lookup"><span data-stu-id="7d3ec-123">Validations are done during the upgrade, and if the upgrade fails, you receive an error message.</span></span> <span data-ttu-id="7d3ec-124">Una actualización puede fallar debido a los conflictos siguientes:</span><span class="sxs-lookup"><span data-stu-id="7d3ec-124">An upgrade might fail because of the following conflicts:</span></span>

- <span data-ttu-id="7d3ec-125">Existen textos libres duplicados de paso de oleada.</span><span class="sxs-lookup"><span data-stu-id="7d3ec-125">Duplicate wave step free texts exist.</span></span>
- <span data-ttu-id="7d3ec-126">Existen personalizaciones.</span><span class="sxs-lookup"><span data-stu-id="7d3ec-126">Customizations exist.</span></span>
- <span data-ttu-id="7d3ec-127">Un texto libre de paso de oleada está asociado con una instancia de método de paso de oleada que no coincide con el tipo de plantilla esperado.</span><span class="sxs-lookup"><span data-stu-id="7d3ec-127">A wave step free text that is associated with a wave step method instance doesn't match the expected template type.</span></span>

<span data-ttu-id="7d3ec-128">Una vez haya resuelto los conflictos que ha identificado durante las validaciones, puede volver a ejecutar el proceso de actualización.</span><span class="sxs-lookup"><span data-stu-id="7d3ec-128">After you've resolved any conflicts that are identified during the validations, you can rerun the upgrade process.</span></span>

<span data-ttu-id="7d3ec-129">Cuando la actualización tiene éxito, la página **Códigos de paso de oleada** (**Administración de almacenes \> Configuración \> Oleadas  \> Códigos de paso de oleada**) pasa a estar disponible.</span><span class="sxs-lookup"><span data-stu-id="7d3ec-129">When the upgrade succeeds, the **Wave step codes** page (**Warehouse management \> Setup \> Waves \> Wave step codes**) becomes available.</span></span> <span data-ttu-id="7d3ec-130">Esta página muestra los códigos de paso de oleada actualizados cuando la función de los códigos de paso de oleada se ha activado.</span><span class="sxs-lookup"><span data-stu-id="7d3ec-130">This page lists the wave step codes that were upgraded when the wave step codes feature was turned on.</span></span>

### <a name="create-new-wave-step-codes"></a><span data-ttu-id="7d3ec-131">Crear códigos de paso de oleada nuevos</span><span class="sxs-lookup"><span data-stu-id="7d3ec-131">Create new wave step codes</span></span>

<span data-ttu-id="7d3ec-132">Puede usar la página **Códigos de paso de oleada** para crear y eliminar códigos de paso de oleada.</span><span class="sxs-lookup"><span data-stu-id="7d3ec-132">You can use the **Wave step codes** page to create and delete wave step codes.</span></span>

<span data-ttu-id="7d3ec-133">Cada nuevo código de paso de oleada y su ID asociada deben ser únicos en todos los tipos de paso de oleada y deben definirse para un tipo de paso de oleada específico.</span><span class="sxs-lookup"><span data-stu-id="7d3ec-133">Every new wave step code and its associated ID must be unique across all wave step types, and they must be defined for a specific wave step type.</span></span>

### <a name="apply-wave-step-codes"></a><span data-ttu-id="7d3ec-134">Aplicar códigos del paso de oleada</span><span class="sxs-lookup"><span data-stu-id="7d3ec-134">Apply wave step codes</span></span>

<span data-ttu-id="7d3ec-135">Después de definir los códigos adecuados de paso de oleada, se pueden aplicar a los métodos de proceso de oleada.</span><span class="sxs-lookup"><span data-stu-id="7d3ec-135">After you've defined the appropriate wave step codes, they can be applied to the wave process methods.</span></span>

<span data-ttu-id="7d3ec-136">Para aplicar los códigos de paso de oleada, vaya a la plantilla adecuada de destino.</span><span class="sxs-lookup"><span data-stu-id="7d3ec-136">To apply wave step codes, go to the appropriate target template.</span></span> <span data-ttu-id="7d3ec-137">Aquí están las plantillas de destino a los que están diseñados para apuntar los códigos de paso de oleada:</span><span class="sxs-lookup"><span data-stu-id="7d3ec-137">Here are the target templates that the wave step codes are designated to point to:</span></span>

- <span data-ttu-id="7d3ec-138">**Plantillas de reabastecimiento:** Gestión de almacén \> Configuración \> Reabastecimiento \> Plantillas de reabastecimiento</span><span class="sxs-lookup"><span data-stu-id="7d3ec-138">**Replenishment templates:** Warehouse management \> Setup \> Replenishment \> Replenishment templates</span></span>
- <span data-ttu-id="7d3ec-139">**Plantillas de planificación de carga:** Gestión de almacén \> Configuración \> Carga \> Plantillas de planificación de carga</span><span class="sxs-lookup"><span data-stu-id="7d3ec-139">**Load build templates:** Warehouse management \> Setup \> Load \> Load build templates</span></span>
- <span data-ttu-id="7d3ec-140">**Plantillas de ordenación:** Gestión de almacén \> Configuración \> Embalado \> Plantillas de ordenación salientes</span><span class="sxs-lookup"><span data-stu-id="7d3ec-140">**Sort templates:** Warehouse management \> Setup \> Packing \> Outbound sorting templates</span></span>
- <span data-ttu-id="7d3ec-141">**Plantillas de contenedores:** Gestión de almacén \> Configurar \> Contenedores \> Plantillas de planificación de contenedor</span><span class="sxs-lookup"><span data-stu-id="7d3ec-141">**Containerization templates:** Warehouse management \> Setup \> Containers \> Container build templates</span></span>
- <span data-ttu-id="7d3ec-142">**Plantillas de impresión de etiqueta:** Gestión de almacén \> Configuración \> Ruta de documento \> Plantillas de etiqueta de oleada</span><span class="sxs-lookup"><span data-stu-id="7d3ec-142">**Label printing templates:** Warehouse management \> Setup \> Document routing \> Wave label templates</span></span>

<span data-ttu-id="7d3ec-143">Las plantillas en esta lista se aplican cuando se hacen referencia de un método de proceso de oleada seleccionado en una plantilla de oleada.</span><span class="sxs-lookup"><span data-stu-id="7d3ec-143">The templates in this list are applied when they are referenced from a wave process method that is selected in a wave template.</span></span> <span data-ttu-id="7d3ec-144">Cuando el código del paso de oleada en un método de proceso de oleada en una plantilla de oleada coincide con el código de paso de oleada en uno de los tipos de plantilla, la plantilla se aplica.</span><span class="sxs-lookup"><span data-stu-id="7d3ec-144">When the wave step code on a wave process method in a wave template matches the wave step code in one of the templates types, the template is applied.</span></span>

### <a name="sample-scenario"></a><span data-ttu-id="7d3ec-145">Escenario de ejemplo</span><span class="sxs-lookup"><span data-stu-id="7d3ec-145">Sample scenario</span></span>

<span data-ttu-id="7d3ec-146">El siguiente procedimiento ayuda a garantizar que la plantilla de reabastecimiento que ha creado se use para la plantilla de oleada.</span><span class="sxs-lookup"><span data-stu-id="7d3ec-146">The following procedure helps guarantee that the replenishment template that you created will be applied for the wave template.</span></span>

1. <span data-ttu-id="7d3ec-147">Vaya a **Gestión de almacén \> Configuración \> Oleadas \> Códigos de paso de oleada** y cree un código de paso de oleada para el tipo **Reabastecimiento**.</span><span class="sxs-lookup"><span data-stu-id="7d3ec-147">Go to **Warehouse management \> Setup \> Waves \> Wave step codes**, and create a wave step code for the **Replenishment** type.</span></span>
2. <span data-ttu-id="7d3ec-148">Vaya a **Gestión de almacén \> Configuración \> Reabastecimiento \> Plantillas de reabastecimiento** y cree una plantilla de reabastecimiento.</span><span class="sxs-lookup"><span data-stu-id="7d3ec-148">Go to **Warehouse management \> Setup \> Replenishment \> Replenishment templates**, and create a replenishment template.</span></span>
3. <span data-ttu-id="7d3ec-149">En la plantilla de reabastecimiento, seleccione el código de paso de oleada que ha creado para el tipo **Reabastecimiento**.</span><span class="sxs-lookup"><span data-stu-id="7d3ec-149">In the replenishment template, select the wave step code that you created for the **Replenishment** type.</span></span>
4. <span data-ttu-id="7d3ec-150">Vaya a **Gestión de almacén \> Configuración \> Oleadas \> Plantillas de oleada** y seleccione la plantilla de oleada que quiere usar.</span><span class="sxs-lookup"><span data-stu-id="7d3ec-150">Go to **Warehouse management \> Setup \> Waves \> Wave templates**, and select the wave template that you intend to use.</span></span>
5. <span data-ttu-id="7d3ec-151">En la plantilla, en la ficha desplegable **Métodos** seleccione el método **Reabastecimiento**.</span><span class="sxs-lookup"><span data-stu-id="7d3ec-151">In the template, on the **Methods** FastTab, select the **Replenishment** method.</span></span>
6. <span data-ttu-id="7d3ec-152">En el campo **Código de paso de oleada**, selección el código de paso de oleada que seleccionó en la plantilla reabastecimiento.</span><span class="sxs-lookup"><span data-stu-id="7d3ec-152">In the **Wave step code** field, select the wave step code that you selected in the replenishment template.</span></span>
