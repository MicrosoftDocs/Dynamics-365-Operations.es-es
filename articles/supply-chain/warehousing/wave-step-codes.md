---
title: Códigos de paso de oleada
description: Este tema proporciona una visión general de los códigos de paso de la oleada y cómo se usan.
author: josaw1
ms.date: 09/06/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: WHSWaveTableListPage, WHSWaveStepCode, WHSReplenishmentTemplates, WHSWaveTemplateTable
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2019-09-30
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: f44d500d58dffb37b27d230b0633336eb87996a6
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/01/2021
ms.locfileid: "5838067"
---
# <a name="wave-step-codes"></a><span data-ttu-id="c5635-103">Códigos de paso de oleada</span><span class="sxs-lookup"><span data-stu-id="c5635-103">Wave step codes</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="c5635-104">Los códigos del paso de oleada son códigos que los usuarios pueden configurar y usar para vincular instancias específicas de los métodos de la oleada a una plantilla correspondiente.</span><span class="sxs-lookup"><span data-stu-id="c5635-104">Wave step codes are codes that users can set up and use to link specific instances of wave methods to a corresponding template.</span></span> <span data-ttu-id="c5635-105">Las plantillas incluyen las plantillas para reabastecimiento, la puesta en contenedores, la impresión de etiquetas, el edificio de carga y la ordenación.</span><span class="sxs-lookup"><span data-stu-id="c5635-105">The templates include templates for replenishment, containerization, label printing, load building, and sorting.</span></span>

<span data-ttu-id="c5635-106">Cuando los códigos del paso de oleada no se usan, los usuarios deben introducir texto para referenciar una plantilla específica del método de la instancia de oleada.</span><span class="sxs-lookup"><span data-stu-id="c5635-106">When wave step codes aren't used, users must enter free text to reference a specific template from the wave method instance.</span></span> <span data-ttu-id="c5635-107">El uso de texto libre es propenso a generar errores, ya que los usuarios deben asegurarse de que el texto de paso de oleada que agreguen para un método específico de paso de oleada en una plantilla de oleada coincida exactamente con el texto de paso de oleada de la plantilla objetivo.</span><span class="sxs-lookup"><span data-stu-id="c5635-107">Free text is prone to errors because users must make sure that the wave step text that they add for a specific wave step method in a wave template exactly matches the wave step text in the target template.</span></span>

<span data-ttu-id="c5635-108">Los códigos del paso de oleada para un tipo de etapa específico de la oleada se configuran en una página independiente.</span><span class="sxs-lookup"><span data-stu-id="c5635-108">Wave step codes for a specific wave step type are set up on a separate page.</span></span> <span data-ttu-id="c5635-109">Para cada instancia del método del paso de oleada en una plantilla de oleada que precisa un código del paso de oleada, el código del paso de oleada se debe seleccionar en una lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="c5635-109">For every wave step method instance in a wave template that requires a wave step code, the wave step code must be selected in a drop-down list.</span></span> <span data-ttu-id="c5635-110">La selección de una lista desplegable reemplaza la entrada de texto en la factura de servicios y ayuda a reducir el riesgo y el impacto de los errores humanos.</span><span class="sxs-lookup"><span data-stu-id="c5635-110">Selection in a drop-down list replaces free text entry and helps reduce the risk and impact of human error.</span></span> <span data-ttu-id="c5635-111">Los códigos de configuración se usan para vincular un método de paso de oleada en una plantilla de oleada a una plantilla objetivo para el método.</span><span class="sxs-lookup"><span data-stu-id="c5635-111">Setup codes are used to link a wave step method in a wave template to a target template for the method.</span></span>

> [!NOTE]
> <span data-ttu-id="c5635-112">El uso de los códigos de paso de oleada es opcional.</span><span class="sxs-lookup"><span data-stu-id="c5635-112">Use of the wave step codes feature is optional.</span></span> <span data-ttu-id="c5635-113">Está habilitado en toda la organización para todas las entidades jurídicas.</span><span class="sxs-lookup"><span data-stu-id="c5635-113">It is enabled organization-wide for all legal entities.</span></span>

## <a name="setup-demo"></a><span data-ttu-id="c5635-114">Demostración de instalación</span><span class="sxs-lookup"><span data-stu-id="c5635-114">Setup demo</span></span> 

<span data-ttu-id="c5635-115">Para esta demostración, los datos de prueba deben estar instalados y debe usar los datos de la compañía de prueba **USMF**.</span><span class="sxs-lookup"><span data-stu-id="c5635-115">For this demo, demo data must be installed, and you must use the **USMF** demo data company.</span></span>

### <a name="enable-wave-step-codes"></a><span data-ttu-id="c5635-116">Habilitar códigos de paso de oleada</span><span class="sxs-lookup"><span data-stu-id="c5635-116">Enable wave step codes</span></span>

<span data-ttu-id="c5635-117">Siga estos pasos para activar la característica de los códigos del paso de oleada.</span><span class="sxs-lookup"><span data-stu-id="c5635-117">Follow these steps to turn on the wave step codes feature.</span></span>

1. <span data-ttu-id="c5635-118">Vaya a **Administración de características**.</span><span class="sxs-lookup"><span data-stu-id="c5635-118">Go to **Feature Management**.</span></span>
2. <span data-ttu-id="c5635-119">Seleccione habilitar la función llamada **Código de paso de oleada de toda la organización**.</span><span class="sxs-lookup"><span data-stu-id="c5635-119">Select to enable the feature called **Organization-wide Wave Step Code**.</span></span>

<span data-ttu-id="c5635-120">Todos los textos libres de paso de oleada de todas las entidades jurídicas se actualizarán a la nueva estructura.</span><span class="sxs-lookup"><span data-stu-id="c5635-120">All existing wave step free texts in all legal entities are upgraded to the new structure.</span></span> <span data-ttu-id="c5635-121">Una vez completada esta actualización para todas las entidades jurídicas, se habilita la función.</span><span class="sxs-lookup"><span data-stu-id="c5635-121">After this upgrade is completed for all legal entities, then the feature is enabled.</span></span> <span data-ttu-id="c5635-122">Si la característica no se puede habilitar para una o más entidades jurídicas, no se habilita para ninguna entidad jurídica.</span><span class="sxs-lookup"><span data-stu-id="c5635-122">If the feature cannot be enabled for one or more legal entities, then the feature is not enabled for any legal entities.</span></span>

<span data-ttu-id="c5635-123">Durante la habilitación, las validaciones se realizan al actualizar datos.</span><span class="sxs-lookup"><span data-stu-id="c5635-123">During the enablement, validations are done during the data upgrade.</span></span> <span data-ttu-id="c5635-124">Si se produce un error de actualización aparecerá un mensaje de error.</span><span class="sxs-lookup"><span data-stu-id="c5635-124">If the upgrade fails, you receive an error message.</span></span> <span data-ttu-id="c5635-125">Una actualización puede fallar debido a los conflictos siguientes:</span><span class="sxs-lookup"><span data-stu-id="c5635-125">An upgrade might fail because of the following conflicts:</span></span>

- <span data-ttu-id="c5635-126">Existen textos libres duplicados de paso de oleada.</span><span class="sxs-lookup"><span data-stu-id="c5635-126">Duplicate wave step free texts exist.</span></span>
- <span data-ttu-id="c5635-127">Existen personalizaciones.</span><span class="sxs-lookup"><span data-stu-id="c5635-127">Customizations exist.</span></span>
- <span data-ttu-id="c5635-128">Un texto libre de paso de oleada está asociado con una instancia de método de paso de oleada que no coincide con el tipo de plantilla esperado.</span><span class="sxs-lookup"><span data-stu-id="c5635-128">A wave step free text that is associated with a wave step method instance doesn't match the expected template type.</span></span>

<span data-ttu-id="c5635-129">Una vez haya resuelto los conflictos que ha identificado durante las validaciones, puede volver a habilitar la características.</span><span class="sxs-lookup"><span data-stu-id="c5635-129">After you've resolved any conflicts that are identified during the validations, you can retry to enable the feature.</span></span>

<span data-ttu-id="c5635-130">Una vez habilitada la característica, la página **Códigos de paso de oleada** (**Administración de almacenes \> Configuración \> Oleadas \> Códigos de paso de oleada**) pasa a estar disponible.</span><span class="sxs-lookup"><span data-stu-id="c5635-130">When the feature has been enabled, the **Wave step codes** page (**Warehouse management \> Setup \> Waves \> Wave step codes**) becomes available.</span></span> <span data-ttu-id="c5635-131">Esta página muestra los códigos de paso de oleada que se actualizaron al habilitar la característica Código de paso de oleada de toda la organización.</span><span class="sxs-lookup"><span data-stu-id="c5635-131">This page lists the wave step codes that were upgraded when the Organization-wide Wave Step Code feature was enabled.</span></span>

### <a name="create-new-wave-step-codes"></a><span data-ttu-id="c5635-132">Crear códigos de paso de oleada nuevos</span><span class="sxs-lookup"><span data-stu-id="c5635-132">Create new wave step codes</span></span>

<span data-ttu-id="c5635-133">Puede usar la página **Códigos de paso de oleada** para crear y eliminar códigos de paso de oleada.</span><span class="sxs-lookup"><span data-stu-id="c5635-133">You can use the **Wave step codes** page to create and delete wave step codes.</span></span>

<span data-ttu-id="c5635-134">Cada nuevo código de paso de oleada y su ID asociada deben ser únicos en todos los tipos de paso de oleada y deben definirse para un tipo de paso de oleada específico.</span><span class="sxs-lookup"><span data-stu-id="c5635-134">Every new wave step code and its associated ID must be unique across all wave step types, and they must be defined for a specific wave step type.</span></span>

### <a name="apply-wave-step-codes"></a><span data-ttu-id="c5635-135">Aplicar códigos del paso de oleada</span><span class="sxs-lookup"><span data-stu-id="c5635-135">Apply wave step codes</span></span>

<span data-ttu-id="c5635-136">Después de definir los códigos adecuados de paso de oleada, se pueden aplicar a los métodos de proceso de oleada.</span><span class="sxs-lookup"><span data-stu-id="c5635-136">After you've defined the appropriate wave step codes, they can be applied to the wave process methods.</span></span>

<span data-ttu-id="c5635-137">Para aplicar los códigos de paso de oleada, vaya a la plantilla adecuada de destino.</span><span class="sxs-lookup"><span data-stu-id="c5635-137">To apply wave step codes, go to the appropriate target template.</span></span> <span data-ttu-id="c5635-138">Aquí están las plantillas de destino a los que están diseñados para apuntar los códigos de paso de oleada:</span><span class="sxs-lookup"><span data-stu-id="c5635-138">Here are the target templates that the wave step codes are designated to point to:</span></span>

- <span data-ttu-id="c5635-139">**Plantillas de reabastecimiento:** Gestión de almacén \> Configuración \> Reabastecimiento \> Plantillas de reabastecimiento</span><span class="sxs-lookup"><span data-stu-id="c5635-139">**Replenishment templates:** Warehouse management \> Setup \> Replenishment \> Replenishment templates</span></span>
- <span data-ttu-id="c5635-140">**Plantillas de planificación de carga:** Gestión de almacén \> Configuración \> Carga \> Plantillas de planificación de carga</span><span class="sxs-lookup"><span data-stu-id="c5635-140">**Load build templates:** Warehouse management \> Setup \> Load \> Load build templates</span></span>
- <span data-ttu-id="c5635-141">**Plantillas de ordenación:** Gestión de almacén \> Configuración \> Embalado \> Plantillas de ordenación salientes</span><span class="sxs-lookup"><span data-stu-id="c5635-141">**Sort templates:** Warehouse management \> Setup \> Packing \> Outbound sorting templates</span></span>
- <span data-ttu-id="c5635-142">**Plantillas de contenedores:** Gestión de almacén \> Configurar \> Contenedores \> Plantillas de planificación de contenedor</span><span class="sxs-lookup"><span data-stu-id="c5635-142">**Containerization templates:** Warehouse management \> Setup \> Containers \> Container build templates</span></span>
- <span data-ttu-id="c5635-143">**Plantillas de impresión de etiqueta:** Gestión de almacén \> Configuración \> Ruta de documento \> Plantillas de etiqueta de oleada</span><span class="sxs-lookup"><span data-stu-id="c5635-143">**Label printing templates:** Warehouse management \> Setup \> Document routing \> Wave label templates</span></span>

<span data-ttu-id="c5635-144">Las plantillas en esta lista se aplican cuando se hacen referencia de un método de proceso de oleada seleccionado en una plantilla de oleada.</span><span class="sxs-lookup"><span data-stu-id="c5635-144">The templates in this list are applied when they are referenced from a wave process method that is selected in a wave template.</span></span> <span data-ttu-id="c5635-145">Cuando el código del paso de oleada en un método de proceso de oleada en una plantilla de oleada coincide con el código de paso de oleada en uno de los tipos de plantilla, la plantilla se aplica.</span><span class="sxs-lookup"><span data-stu-id="c5635-145">When the wave step code on a wave process method in a wave template matches the wave step code in one of the templates types, the template is applied.</span></span>

### <a name="sample-scenario"></a><span data-ttu-id="c5635-146">Escenario de ejemplo</span><span class="sxs-lookup"><span data-stu-id="c5635-146">Sample scenario</span></span>

<span data-ttu-id="c5635-147">El siguiente procedimiento ayuda a garantizar que la plantilla de reabastecimiento que ha creado se use para la plantilla de oleada.</span><span class="sxs-lookup"><span data-stu-id="c5635-147">The following procedure helps guarantee that the replenishment template that you created will be applied for the wave template.</span></span>

1. <span data-ttu-id="c5635-148">Vaya a **Gestión de almacén \> Configuración \> Oleadas \> Códigos de paso de oleada** y cree un código de paso de oleada para el tipo **Reabastecimiento**.</span><span class="sxs-lookup"><span data-stu-id="c5635-148">Go to **Warehouse management \> Setup \> Waves \> Wave step codes**, and create a wave step code for the **Replenishment** type.</span></span>
2. <span data-ttu-id="c5635-149">Vaya a **Gestión de almacén \> Configuración \> Reabastecimiento \> Plantillas de reabastecimiento** y cree una plantilla de reabastecimiento.</span><span class="sxs-lookup"><span data-stu-id="c5635-149">Go to **Warehouse management \> Setup \> Replenishment \> Replenishment templates**, and create a replenishment template.</span></span>
3. <span data-ttu-id="c5635-150">En la plantilla de reabastecimiento, seleccione el código de paso de oleada que ha creado para el tipo **Reabastecimiento**.</span><span class="sxs-lookup"><span data-stu-id="c5635-150">In the replenishment template, select the wave step code that you created for the **Replenishment** type.</span></span>
4. <span data-ttu-id="c5635-151">Vaya a **Gestión de almacén \> Configuración \> Oleadas \> Plantillas de oleada** y seleccione la plantilla de oleada que quiere usar.</span><span class="sxs-lookup"><span data-stu-id="c5635-151">Go to **Warehouse management \> Setup \> Waves \> Wave templates**, and select the wave template that you intend to use.</span></span>
5. <span data-ttu-id="c5635-152">En la plantilla, en la ficha desplegable **Métodos** seleccione el método **Reabastecimiento**.</span><span class="sxs-lookup"><span data-stu-id="c5635-152">In the template, on the **Methods** FastTab, select the **Replenishment** method.</span></span>
6. <span data-ttu-id="c5635-153">En el campo **Código de paso de oleada**, selección el código de paso de oleada que seleccionó en la plantilla reabastecimiento.</span><span class="sxs-lookup"><span data-stu-id="c5635-153">In the **Wave step code** field, select the wave step code that you selected in the replenishment template.</span></span>

<span data-ttu-id="c5635-154">Debe realizar estos pasos para cada entidad jurídica.</span><span class="sxs-lookup"><span data-stu-id="c5635-154">You perform these steps for each legal entity.</span></span>


[!INCLUDE[footer-include](../../includes/footer-banner.md)]