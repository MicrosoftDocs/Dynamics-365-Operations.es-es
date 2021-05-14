---
title: Códigos de clasificación nacional de transporte de mercancías por motor (NMFC)
description: Este tema describe cómo trabajar con códigos de clasificación nacional de transporte de mercancías (NMFC) en Microsoft Dynamics 365 Supply Chain Management
author: Henrikan
ms.date: 04/22/2021
ms.topic: article
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: henrikan
ms.search.validFrom: 2021-04-22
ms.dyn365.ops.version: 10.0.8
ms.openlocfilehash: 0307437d3868f7ac34fa16a0913907a046ac14d4
ms.sourcegitcommit: 636c1bf096a8666a551b67e898da1f48feb9a187
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/26/2021
ms.locfileid: "5941891"
---
# <a name="national-motor-freight-classification-nmfc-codes"></a><span data-ttu-id="71d92-103">Códigos de clasificación nacional de transporte de mercancías por motor (NMFC)</span><span class="sxs-lookup"><span data-stu-id="71d92-103">National Motor Freight Classification (NMFC) codes</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="71d92-104">Los códigos de Clasificación Nacional de Carga Motorizada (NMFC) le ayudan a clasificar los artículos que pueden enviarse.</span><span class="sxs-lookup"><span data-stu-id="71d92-104">National Motor Freight Classification (NMFC) codes help you classify items that can be shipped.</span></span> <span data-ttu-id="71d92-105">El código NMFC es una designación que se utiliza para agrupar productos.</span><span class="sxs-lookup"><span data-stu-id="71d92-105">The NMFC code is a designation that is used to group commodities.</span></span> <span data-ttu-id="71d92-106">Permite a las empresas de transporte evaluar los productos para su envío clasificando los artículos en función de consideraciones como lo adecuado del camión, los problemas de carga, los problemas de manipulación y la perecibilidad.</span><span class="sxs-lookup"><span data-stu-id="71d92-106">It enables transport companies to evaluate goods for shipment by classifying items based on considerations such as truck fit, loading issues, handling issues, and perishability.</span></span> <span data-ttu-id="71d92-107">Los productos se agrupan en una de las 18 clases de transporte mediante un rango de números del 50 al 500.</span><span class="sxs-lookup"><span data-stu-id="71d92-107">Commodities are grouped into one of 18 freight classes by using a range of numbers from 50 to 500.</span></span> <span data-ttu-id="71d92-108">La clase en la que se agrupa una mercancía se basa en una evaluación de cuatro características de transporte: densidad, capacidad de almacenamiento, manipulación y responsabilidad.</span><span class="sxs-lookup"><span data-stu-id="71d92-108">The class that a commodity is grouped into is based on an evaluation of four transportation characteristics: density, stowability, handling, and liability.</span></span> <span data-ttu-id="71d92-109">Juntas, estas características establecen la transportabilidad de la mercancía.</span><span class="sxs-lookup"><span data-stu-id="71d92-109">Together, these characteristics establish the commodity's transportability.</span></span>

<span data-ttu-id="71d92-110">Un código NMFC está asociado con cada artículo de envío de carga inferior a un camión (LTL).</span><span class="sxs-lookup"><span data-stu-id="71d92-110">An NMFC code is associated with every less than truckload (LTL) shipping item.</span></span> <span data-ttu-id="71d92-111">Por ejemplo, a un portátil se le puede asignar un NMFC que se clasifica en 2.5, mientras que a los cables eléctricos se le puede asignar un NMFC que se clasifica en 65.</span><span class="sxs-lookup"><span data-stu-id="71d92-111">For example, a laptop might be assigned an NMFC that is classed at 2.5, whereas electrical cords might be assigned an NMFC that is classed at 65.</span></span>

<span data-ttu-id="71d92-112">Esta función puede ayudar a los trabajadores a utilizar los códigos NMFC para clasificar los artículos de envío LTL.</span><span class="sxs-lookup"><span data-stu-id="71d92-112">This feature can help workers use NMFC codes to classify LTL shipping items.</span></span> <span data-ttu-id="71d92-113">A continuación, encontrará algunos ejemplos:</span><span class="sxs-lookup"><span data-stu-id="71d92-113">Here are some examples:</span></span>

- <span data-ttu-id="71d92-114">Si su empresa incluye una descripción de la carga en el conocimiento de embarque (BOL), el transportista tendrá una idea de cuál es la carga.</span><span class="sxs-lookup"><span data-stu-id="71d92-114">If your company includes a freight description on the bill of lading (BOL), the carrier will have some idea what the freight is.</span></span> <span data-ttu-id="71d92-115">El flete es una clasificación importante porque muchas empresas de transporte basan todo su modelo de negocio en los tipos de flete que envían.</span><span class="sxs-lookup"><span data-stu-id="71d92-115">Freight is an important classification because many transportation companies base their whole business model on the types of freight that they ship.</span></span>
- <span data-ttu-id="71d92-116">Esta clasificación puede ser esencial para su empresa porque se utiliza para determinar el coste de una carga determinada.</span><span class="sxs-lookup"><span data-stu-id="71d92-116">This classification might be essential to your company because it's used to determine the cost of a given load.</span></span>
- <span data-ttu-id="71d92-117">Su empresa puede identificar la rentabilidad de una empresa de logística y transporte LTL.</span><span class="sxs-lookup"><span data-stu-id="71d92-117">Your company can identify the profitability of an LTL logistics and transportation company.</span></span>

<span data-ttu-id="71d92-118">En este tema se describe cómo trabajar con códigos NMFC en Microsoft Dynamics 365 Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="71d92-118">This topic describes how to work with NMFC codes in Microsoft Dynamics 365 Supply Chain Management.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="71d92-119">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="71d92-119">Prerequisites</span></span>

<span data-ttu-id="71d92-120">Antes de poder crear códigos NMFC, debe configurar todas las clases de carga LTL que deben asignarse a ellos.</span><span class="sxs-lookup"><span data-stu-id="71d92-120">Before you can create NMFC codes, you must set up all the LTL freight classes that must be mapped to them.</span></span> <span data-ttu-id="71d92-121">Las clases de carga LTL representan categorías de artículos, mientras que los códigos NMFC están relacionados con productos específicos en cada una de las 18 clases de carga.</span><span class="sxs-lookup"><span data-stu-id="71d92-121">LTL freight classes represent categories of items, whereas NMFC codes are related to specific commodities in each of the 18 freight classes.</span></span> <span data-ttu-id="71d92-122">Para obtener más información sobre cómo trabajar con clases LTL, consulte [Clases de carga inferior al camión (LTL)](ltl-class.md).</span><span class="sxs-lookup"><span data-stu-id="71d92-122">For more information about how to work with LTL classes, see [Less than truckload (LTL) classes](ltl-class.md).</span></span>

## <a name="create-an-nmfc-code"></a><span data-ttu-id="71d92-123">Crear un código NMFC</span><span class="sxs-lookup"><span data-stu-id="71d92-123">Create an NMFC code</span></span>

<span data-ttu-id="71d92-124">Para crear un código NMFC, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="71d92-124">To create an NMFC code, follow these steps.</span></span>

1. <span data-ttu-id="71d92-125">Siga uno de estos pasos:</span><span class="sxs-lookup"><span data-stu-id="71d92-125">Follow one of these steps:</span></span>

    - <span data-ttu-id="71d92-126">Vaya a **Gestión de almacenes \> Configurar \> Inventario \> Códigos NMFC**.</span><span class="sxs-lookup"><span data-stu-id="71d92-126">Go to **Warehouse management \> Setup \> Inventory \> NMFC codes**.</span></span>
    - <span data-ttu-id="71d92-127">Vaya a **Administración de transporte \> Configuración \> Estándares de transporte \> Códigos NMFC**.</span><span class="sxs-lookup"><span data-stu-id="71d92-127">Go to **Transportation management \> Setup \> Transportation standards \> NMFC codes**.</span></span>

1. <span data-ttu-id="71d92-128">Seleccione **Nuevo** para crear un código NMFC.</span><span class="sxs-lookup"><span data-stu-id="71d92-128">Select **New** to create an NMFC code.</span></span> <span data-ttu-id="71d92-129">Entonces establezca los campos siguientes:</span><span class="sxs-lookup"><span data-stu-id="71d92-129">Then set the following fields:</span></span>

    - <span data-ttu-id="71d92-130">**Código NMFC**: especifique el código NMFC de tipo de mercancía.</span><span class="sxs-lookup"><span data-stu-id="71d92-130">**NMFC code** – Enter the NMFC code for the commodity type.</span></span>
    - <span data-ttu-id="71d92-131">**Nombre**: escriba un nombre para el código NMFC.</span><span class="sxs-lookup"><span data-stu-id="71d92-131">**Name** – Enter a name for the NMFC code.</span></span>
    - <span data-ttu-id="71d92-132">**Clase LTL**: seleccione la clase LTL que está asociada con el código NMFC.</span><span class="sxs-lookup"><span data-stu-id="71d92-132">**LTL class** – Select the LTL class that is associated with the NMFC code.</span></span>
    - <span data-ttu-id="71d92-133">**Unidad de manipulación BOL**: defina el tipo de manipulación predeterminado para el envío.</span><span class="sxs-lookup"><span data-stu-id="71d92-133">**BOL handling unit** – Define the default handling type for the shipment.</span></span>

## <a name="example-set-up-nmfc-codes"></a><span data-ttu-id="71d92-134">Ejemplo: configurar códigos NMFC</span><span class="sxs-lookup"><span data-stu-id="71d92-134">Example: Set up NMFC codes</span></span>

<span data-ttu-id="71d92-135">El siguiente ejemplo muestra cómo configurar dos códigos NMFC diferentes que puede utilizar con diferentes tipos de productos.</span><span class="sxs-lookup"><span data-stu-id="71d92-135">The following example shows how to set up two different NMFC codes that can be used with different products.</span></span>

1. <span data-ttu-id="71d92-136">Vaya a **Gestión de almacenes \> Configurar \> Inventario \> Códigos NMFC**.</span><span class="sxs-lookup"><span data-stu-id="71d92-136">Go to **Warehouse management \> Setup \> Inventory \> NMFC codes**.</span></span>
1. <span data-ttu-id="71d92-137">En el panel de acciones, haga clic en **Nueva**.</span><span class="sxs-lookup"><span data-stu-id="71d92-137">On the Action Pane, select **New**.</span></span>
1. <span data-ttu-id="71d92-138">En la nueva línea, establezca los siguientes valores:</span><span class="sxs-lookup"><span data-stu-id="71d92-138">On the new line, set the following values:</span></span>

    - <span data-ttu-id="71d92-139">**Código NMFC:** *92.5*</span><span class="sxs-lookup"><span data-stu-id="71d92-139">**NMFC code:** *92.5*</span></span>
    - <span data-ttu-id="71d92-140">**Nombre:** *Ordenadores*</span><span class="sxs-lookup"><span data-stu-id="71d92-140">**Name:** *Computers*</span></span>
    - <span data-ttu-id="71d92-141">**Clase LTL:** *92.5*</span><span class="sxs-lookup"><span data-stu-id="71d92-141">**LTL class:** *92.5*</span></span>
    - <span data-ttu-id="71d92-142">**Unidad de manipulación BOL:** *Unidad*</span><span class="sxs-lookup"><span data-stu-id="71d92-142">**BOL handling unit:** *Unit*</span></span>

1. <span data-ttu-id="71d92-143">En el panel Acciones, seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="71d92-143">On the Action Pane, select **Save**.</span></span>
1. <span data-ttu-id="71d92-144">En el panel de acciones, haga clic en **Nueva**.</span><span class="sxs-lookup"><span data-stu-id="71d92-144">On the Action Pane, select **New**.</span></span>
1. <span data-ttu-id="71d92-145">En la nueva línea, establezca los siguientes valores:</span><span class="sxs-lookup"><span data-stu-id="71d92-145">On the new line, set the following values:</span></span>

    - <span data-ttu-id="71d92-146">**Código NMFC:** *125*</span><span class="sxs-lookup"><span data-stu-id="71d92-146">**NMFC code:** *125*</span></span>
    - <span data-ttu-id="71d92-147">**Nombre:** *Teléfonos*</span><span class="sxs-lookup"><span data-stu-id="71d92-147">**Name:** *Phones*</span></span>
    - <span data-ttu-id="71d92-148">**Clase LTL:** *125*</span><span class="sxs-lookup"><span data-stu-id="71d92-148">**LTL class:** *125*</span></span>
    - <span data-ttu-id="71d92-149">**Unidad de manipulación BOL:** *Unidad*</span><span class="sxs-lookup"><span data-stu-id="71d92-149">**BOL handling unit:** *Unit*</span></span>

1. <span data-ttu-id="71d92-150">En el panel Acciones, seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="71d92-150">On the Action Pane, select **Save**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="71d92-151">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="71d92-151">Additional resources</span></span>

- [<span data-ttu-id="71d92-152">Inferior a clases de camión (LTL)</span><span class="sxs-lookup"><span data-stu-id="71d92-152">Less than truckload (LTL) classes</span></span>](ltl-class.md)
- [<span data-ttu-id="71d92-153">Crear un conocimiento de embarque</span><span class="sxs-lookup"><span data-stu-id="71d92-153">Create a bill of landing</span></span>](create-bill-of-lading.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
