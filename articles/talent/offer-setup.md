---
title: Configuración de la gestión de ofertas
description: Este tema describe cómo configurar ofertas en Talent.
author: andreabichsel
manager: AnnBe
ms.date: 02/04/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Core, Talent
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2018-10-18
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 7fa0e5d30c06db16e105631e492af022acfcfd66
ms.sourcegitcommit: 2b890cd7a801055ab0ca24398efc8e4e777d4d8c
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/07/2019
ms.locfileid: "1519017"
---
# <a name="set-up-offer-management"></a><span data-ttu-id="c0ee4-103">Configuración de la gestión de ofertas</span><span class="sxs-lookup"><span data-stu-id="c0ee4-103">Set up offer management</span></span> 

[!include [banner](includes/banner.md)]

<span data-ttu-id="c0ee4-104">Cuando trasladan a un candidato a la etapa de oferta en Dynamics 365 for Talent: Attract, debe asegurarse de que las ofertas se pueden crear rápidamente para el candidato, aprobar según sea necesario, y enviarlas al candidato.</span><span class="sxs-lookup"><span data-stu-id="c0ee4-104">When a candidate is moved to the offer stage in Dynamics 365 for Talent: Attract, you need to ensure that the offers can be quickly created for the candidate, approved as necessary, and sent out to the candidate.</span></span> <span data-ttu-id="c0ee4-105">Puesto que la mayoría de las propuestas son estándar, se pueden crear con plantillas reutilizables.</span><span class="sxs-lookup"><span data-stu-id="c0ee4-105">Because most offers are standard, they can be created from reusable templates.</span></span> <span data-ttu-id="c0ee4-106">En Attract, todas las propuestas se agrupan en un paquete de propuesta, que es una recopilación de uno o más documentos.</span><span class="sxs-lookup"><span data-stu-id="c0ee4-106">In Attract, all offers are rolled into an offer package, which is a collection of one or more offer documents.</span></span> 

<span data-ttu-id="c0ee4-107">Este tema muestra todos los pasos que un administrador de Attract seguiría para configurar diferentes plantillas de paquete de oferta como parte de la capacidad de gestión de la oferta de Attract.</span><span class="sxs-lookup"><span data-stu-id="c0ee4-107">This topic lists all the steps that an Attract administrator would follow to set up different offer package templates as part of the offer management capability in Attract.</span></span> <span data-ttu-id="c0ee4-108">Los usuarios con roles de usuario que no son de administrador no tendrán acceso a estas capacidades.</span><span class="sxs-lookup"><span data-stu-id="c0ee4-108">Users with non-administrator roles will not have access to these capabilities.</span></span>

>[!NOTE]
> <span data-ttu-id="c0ee4-109">Las capacidades de gestión de la propuesta están disponibles como parte del complemento de contratación completa.</span><span class="sxs-lookup"><span data-stu-id="c0ee4-109">Offer management capabilities are available as part of the Comprehensive Hiring Add-On.</span></span>

## <a name="offer-data"></a><span data-ttu-id="c0ee4-110">Datos de oferta</span><span class="sxs-lookup"><span data-stu-id="c0ee4-110">Offer data</span></span> 

<span data-ttu-id="c0ee4-111">Los datos de la propuesta son la unidad más pequeña dentro de la plantilla de paquete de propuesta.</span><span class="sxs-lookup"><span data-stu-id="c0ee4-111">Offer data is the smallest unit inside the offer package template.</span></span> <span data-ttu-id="c0ee4-112">Una oferta típica consta de texto estándar y un conjunto de valores.</span><span class="sxs-lookup"><span data-stu-id="c0ee4-112">A typical offer consists of standard text and a set of values.</span></span> <span data-ttu-id="c0ee4-113">Los conjuntos de valores son los únicos valores que pueden cambiar entre ofertas.</span><span class="sxs-lookup"><span data-stu-id="c0ee4-113">The sets of values are the only pieces that could change between offers.</span></span> <span data-ttu-id="c0ee4-114">Durante la creación de la propuesta, el aspecto más importante en el que se puede concentrar el creador de la propuesta es la lista de marcadores de posición de los datos de la propuesta presentes en una plantilla de paquete de propuesta.</span><span class="sxs-lookup"><span data-stu-id="c0ee4-114">During the offer creation, the most important aspect that the offer creator can focus on is the list of offer data placeholders present in an offer package template.</span></span> <span data-ttu-id="c0ee4-115">Para configurar los datos de la oferta, haga lo siguiente.</span><span class="sxs-lookup"><span data-stu-id="c0ee4-115">To set up offer data, do the following.</span></span>

1.  <span data-ttu-id="c0ee4-116">Vaya a **Administración de ofertas**.</span><span class="sxs-lookup"><span data-stu-id="c0ee4-116">Go to **Offer management**.</span></span>

1.  <span data-ttu-id="c0ee4-117">Expanda la sección **Biblioteca** en el panel de navegación izquierdo y a continuación, vaya a **Datos de oferta**.</span><span class="sxs-lookup"><span data-stu-id="c0ee4-117">Expand the **Library** section in the left navigation pane, then go to **Offer data**.</span></span>

    >[!NOTE]
    > <span data-ttu-id="c0ee4-118">En la página **Datos de oferta** están las secciones **Detalles del candidato** y **Detalles del trabajo**.</span><span class="sxs-lookup"><span data-stu-id="c0ee4-118">On the **Offer data** page are the **Candidate details** and **Job details** sections.</span></span> <span data-ttu-id="c0ee4-119">Attract proporciona inmediatamente unos cuantos marcadores de posición de los datos de la oferta.</span><span class="sxs-lookup"><span data-stu-id="c0ee4-119">Attract provides a few offer data placeholders out-of-the-box.</span></span>
    
    > <span data-ttu-id="c0ee4-120">Existen secciones en la página para organizar los distintos marcadores de posición de los datos de la propuesta en grupos lógicos.</span><span class="sxs-lookup"><span data-stu-id="c0ee4-120">There are sections on the page to organize different offer data placeholders together in logical groups.</span></span> <span data-ttu-id="c0ee4-121">Estas secciones son útiles para el mantenimiento de los datos de la propuesta y el rellenado de datos durante el proceso de creación de la propuesta.</span><span class="sxs-lookup"><span data-stu-id="c0ee4-121">These sections can help with maintenance of offer data and population of data during the offer creation process.</span></span>

1.  <span data-ttu-id="c0ee4-122">Para crear una nueva sección de datos de oferta, haga clic en **Agregar una sección** y escriba un nombre único para la sección.</span><span class="sxs-lookup"><span data-stu-id="c0ee4-122">To create a new offer data section, click **Add a section** and enter a unique name for the section.</span></span>

1.  <span data-ttu-id="c0ee4-123">Para agregar marcadores de posición de los datos de la oferta en una sección, haga clic en **Agregar datos de oferta** y escriba un nombre único para el marcador. de posición.</span><span class="sxs-lookup"><span data-stu-id="c0ee4-123">To add offer data placeholders to any section, click **Add offer data** and enter a unique name for the placeholder.</span></span>

1.  <span data-ttu-id="c0ee4-124">Para editar el nombre de una sección, pase el mouse sobre el nombre de sección y actualice el nombre.</span><span class="sxs-lookup"><span data-stu-id="c0ee4-124">To edit the name of any section, hover over the section name and update the name.</span></span>

1.  <span data-ttu-id="c0ee4-125">Para editar el nombre de cualquier marcador de datos de oferta existente, primero asegúrese de que el marcador ya no forme parte de ninguna plantilla.</span><span class="sxs-lookup"><span data-stu-id="c0ee4-125">To edit the name of any existing offer data placeholder, first make sure that the placeholder is not already part of any template.</span></span> <span data-ttu-id="c0ee4-126">A continuación, pase el mouse por encima del nombre del marcador de posición de datos de la oferta y actualice el nombre según sea necesario.</span><span class="sxs-lookup"><span data-stu-id="c0ee4-126">Then, hover over the name of the offer data placeholder and update the name as needed.</span></span>

1. <span data-ttu-id="c0ee4-127">Para eliminar un marcador de datos de oferta existente, primero asegúrese de que el marcador no forme parte de ninguna otra plantilla.</span><span class="sxs-lookup"><span data-stu-id="c0ee4-127">To delete an existing offer data placeholder, first make sure that the placeholder is not part of any other template.</span></span> <span data-ttu-id="c0ee4-128">A continuación, pase el mouse sobre el marcador y cuando aparezca el icono de papelera, haga clic en él para eliminar el marcador de los datos de la propuesta.</span><span class="sxs-lookup"><span data-stu-id="c0ee4-128">Then, hover over the placeholder and when the trash can icon appears, click the trash can to delete the offer data placeholder.</span></span>
    >[!NOTE]
    > <span data-ttu-id="c0ee4-129">Puede ver de cuántas plantillas forma parte un marcador de datos de oferta consultando el indicador numérico que está junto a cada dato de la propuesta.</span><span class="sxs-lookup"><span data-stu-id="c0ee4-129">You can see how many templates an offer data placeholder is part of by the number indicator next to each offer data.</span></span> 

1. <span data-ttu-id="c0ee4-130">Para eliminar una sección, pase el mouse sobre el nombre.</span><span class="sxs-lookup"><span data-stu-id="c0ee4-130">To delete any section, hover over the name.</span></span> <span data-ttu-id="c0ee4-131">Si no aparece ninguno de los marcadores de datos de la propuesta de la sección en ninguna plantilla, puede hacer clic en el icono de papelera para eliminarlo.</span><span class="sxs-lookup"><span data-stu-id="c0ee4-131">If none of the offer data placeholders inside the section appear in any template, you can click the trash can icon to delete it.</span></span> 
    >[!NOTE]
    > <span data-ttu-id="c0ee4-132">Al eliminar la sección también eliminará todos los marcadores de los datos de la oferta de la sección.</span><span class="sxs-lookup"><span data-stu-id="c0ee4-132">Deleting the section will also delete all the offer data placeholders inside that section.</span></span>

<span data-ttu-id="c0ee4-133">Una vez que se hayan configurado los marcadores de los datos de la propuesta, puede utilizarlos en todas las plantillas de documento.</span><span class="sxs-lookup"><span data-stu-id="c0ee4-133">After the offer data placeholders have been set up, you can use them across any document template.</span></span> <span data-ttu-id="c0ee4-134">Los marcadores de datos de la propuesta no se limitan a una plantilla específica; el mismo conjunto se puede usar en todas las plantillas.</span><span class="sxs-lookup"><span data-stu-id="c0ee4-134">Offer data placeholders are not restricted to a specific template -- the same set can be used across all templates.</span></span>

## <a name="offer-data-rules"></a><span data-ttu-id="c0ee4-135">Reglas de datos de la oferta</span><span class="sxs-lookup"><span data-stu-id="c0ee4-135">Offer data rules</span></span>

<span data-ttu-id="c0ee4-136">La mayoría de las organizaciones tienen reglas para cómo crear ofertas.</span><span class="sxs-lookup"><span data-stu-id="c0ee4-136">Most organization have rules for how offers must be created.</span></span> <span data-ttu-id="c0ee4-137">Por ejemplo, una organización puede requerir que una combinación de propuesta del sueldo anual máximo para una ubicación concreta y el nivel de asignación de la antigüedad tenga que estar dentro de un intervalo determinado, o que solo haya algunos valores específicos posibles para el nivel de oferta de la nueva contratación.</span><span class="sxs-lookup"><span data-stu-id="c0ee4-137">For example, an organization may want to require that the maximum annual salary offer for a specific location and seniority level combination has to be within a certain range, or that there are only a few specific values possible for the offer level for the new hire.</span></span> <span data-ttu-id="c0ee4-138">Attract admite actualmente todas las reglas de datos de este tipo mediante un archivo CSV.</span><span class="sxs-lookup"><span data-stu-id="c0ee4-138">Attract currently supports all such data rules using a CSV file.</span></span>

<span data-ttu-id="c0ee4-139">Para preparar el archivo CSV de las reglas de los datos, haga lo siguiente.</span><span class="sxs-lookup"><span data-stu-id="c0ee4-139">To prepare the data rules CSV file, do the following.</span></span>

1.  <span data-ttu-id="c0ee4-140">Determine el marcador de los datos de la propuesta para el conjunto de reglas.</span><span class="sxs-lookup"><span data-stu-id="c0ee4-140">Determine the offer data placeholder for the rule set.</span></span> <span data-ttu-id="c0ee4-141">Por ejemplo, **Sueldo anual**.</span><span class="sxs-lookup"><span data-stu-id="c0ee4-141">For example, **Annual Salary**.</span></span>

1.  <span data-ttu-id="c0ee4-142">Identifique los valores de los marcadores de datos de la oferta dependientes.</span><span class="sxs-lookup"><span data-stu-id="c0ee4-142">Identify the dependent offer data placeholder values.</span></span> <span data-ttu-id="c0ee4-143">Por ejemplo, **Ubicación de trabajo** y **Nivel**.</span><span class="sxs-lookup"><span data-stu-id="c0ee4-143">For example, **Job Location** and **Level**.</span></span>

1.  <span data-ttu-id="c0ee4-144">Especifique las columnas 1 y 2 como **Ubicación de trabajo** y **Nivel**.</span><span class="sxs-lookup"><span data-stu-id="c0ee4-144">Specify columns 1 and 2 as **Job Location** and **Level**.</span></span>

1.  <span data-ttu-id="c0ee4-145">Para cargar un valor de rango, convierta las columnas 3 y 4 en **Sueldo anual**.</span><span class="sxs-lookup"><span data-stu-id="c0ee4-145">To upload a range value, make columns 3 and 4 **Annual Salary**.</span></span> <span data-ttu-id="c0ee4-146">Para cargar un valor específico en lugar de un intervalo, convierta la columna 3 en **Sueldo anual**.</span><span class="sxs-lookup"><span data-stu-id="c0ee4-146">To upload a specific value instead of a range, only make column 3 **Annual Salary**.</span></span>

1.  <span data-ttu-id="c0ee4-147">Rellene el archivo Microsoft Excel en función de sus roles necesarios.</span><span class="sxs-lookup"><span data-stu-id="c0ee4-147">Populate the Microsoft Excel file based on your required roles.</span></span>

1.  <span data-ttu-id="c0ee4-148">Asegúrese de que cada fila es una combinación única de todos los valores conjuntos.</span><span class="sxs-lookup"><span data-stu-id="c0ee4-148">Ensure that each row is a unique combination of all the values put together.</span></span>

1.  <span data-ttu-id="c0ee4-149">Guardar el archivo en formato CSV.</span><span class="sxs-lookup"><span data-stu-id="c0ee4-149">Save the file as a CSV format.</span></span>

<span data-ttu-id="c0ee4-150">Para cargar el archivo de las reglas de los datos de la oferta haga lo siguiente.</span><span class="sxs-lookup"><span data-stu-id="c0ee4-150">To upload the offer data rules file, do the following.</span></span>

1.  <span data-ttu-id="c0ee4-151">Vaya a **Administración de ofertas**.</span><span class="sxs-lookup"><span data-stu-id="c0ee4-151">Go to **Offer management**.</span></span>

1.  <span data-ttu-id="c0ee4-152">Expanda la sección **Biblioteca** en el panel de navegación izquierdo y a continuación, vaya a **Reglas de datos de oferta**.</span><span class="sxs-lookup"><span data-stu-id="c0ee4-152">Expand the **Library** section in the left navigation panel, then go to **Offer data rules**.</span></span>

1.  <span data-ttu-id="c0ee4-153">Haga clic en **Conjunto de datos nuevo** para mostrar el cuadro de diálogo **Cargar**.</span><span class="sxs-lookup"><span data-stu-id="c0ee4-153">Click **New data set** to display the **Upload** dialog box.</span></span>

1.  <span data-ttu-id="c0ee4-154">Especifique un nombre único para el conjunto de reglas y después cargue el archivo CSV guardado.</span><span class="sxs-lookup"><span data-stu-id="c0ee4-154">Specify a unique name for the rule set and then upload the saved CSV file.</span></span>

1.  <span data-ttu-id="c0ee4-155">Haga clic en **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="c0ee4-155">Click **Add**.</span></span>
    <span data-ttu-id="c0ee4-156">El conjunto de reglas se procesará en segundo plano y cuando finalice se le notificará en la aplicación y por correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="c0ee4-156">The rule set will be processed in the background and you will be notified in-app and via email once it completes.</span></span>

    <span data-ttu-id="c0ee4-157">Se le notificará si hay errores mientras se procesa la carga.</span><span class="sxs-lookup"><span data-stu-id="c0ee4-157">You will be notified if there are errors while processing the upload.</span></span> <span data-ttu-id="c0ee4-158">A continuación puede descargar el registro de errores, corregir el archivo, y cargarlo de nuevo.</span><span class="sxs-lookup"><span data-stu-id="c0ee4-158">You can then download the error log, fix the file, and upload it again.</span></span>

1.  <span data-ttu-id="c0ee4-159">Utilice la opción de botón de las elipsis (**…**) si desea descargar el conjunto de reglas y actualizar el conjunto de valores.</span><span class="sxs-lookup"><span data-stu-id="c0ee4-159">Use the ellipses button (**…**) option if you want to download the rule set and update the set of values.</span></span> <span data-ttu-id="c0ee4-160">Después de actualizar, puede cargar el archivo de nuevo.</span><span class="sxs-lookup"><span data-stu-id="c0ee4-160">After updating, you can upload the file again.</span></span>

1.  <span data-ttu-id="c0ee4-161">Puede eliminar una carga existente del conjunto de reglas si el marcador de posición que se define no se está utilizando en otra plantilla de documento.</span><span class="sxs-lookup"><span data-stu-id="c0ee4-161">You can delete an existing rule set upload if the placeholder being defined is not being used in another document template.</span></span>

>[!NOTE]
> - <span data-ttu-id="c0ee4-162">Cada marcador solo puede tener un conjunto exclusivo de columnas de las que dependa.</span><span class="sxs-lookup"><span data-stu-id="c0ee4-162">Each placeholder can only have one unique set of columns that it is dependent on.</span></span> <span data-ttu-id="c0ee4-163">Por ejemplo, si **Sueldo anual** depende de **Ubicación de trabajo** y **Nivel**, no puede cargar a otro conjunto de reglas en el que **Sueldo anual** dependa de otro conjunto de columnas.</span><span class="sxs-lookup"><span data-stu-id="c0ee4-163">For example, if **Annual Salary** is dependent on **Job Location** and **Level**, you can't upload another rule set where **Annual Salary** is dependent on a different set of columns.</span></span>

> - <span data-ttu-id="c0ee4-164">Puede descargar conjuntos de reglas de los datos de la propuesta de muestra en la pestaña **Ejemplos** en la página **Reglas de datos de la oferta**.</span><span class="sxs-lookup"><span data-stu-id="c0ee4-164">You can download sample offer data rule sets on the **Samples** tab on the **Offer data rules** page.</span></span>

> - <span data-ttu-id="c0ee4-165">Cuando un creador de oferta anula los valores recomendados por las reglas de los datos de la oferta, la propuesta se marca como no estándar y es obligatorio un flujo de trabajo de aprobación de la oferta.</span><span class="sxs-lookup"><span data-stu-id="c0ee4-165">When an offer creator overrides the values that are recommended by the offer data rules, the offer is flagged as non-standard and offer approval workflow will be mandated.</span></span>

## <a name="document-templates"></a><span data-ttu-id="c0ee4-166">Plantillas de documentos</span><span class="sxs-lookup"><span data-stu-id="c0ee4-166">Document templates</span></span>

<span data-ttu-id="c0ee4-167">Una plantilla de documento de oferta puede ayudar a los administradores a crear cartas de propuesta.</span><span class="sxs-lookup"><span data-stu-id="c0ee4-167">An offer document template can help administrators create offer letters.</span></span> <span data-ttu-id="c0ee4-168">La plantilla de documento de oferta es una combinación del texto que formará parte de la oferta así como de los marcadores de datos de la oferta definida.</span><span class="sxs-lookup"><span data-stu-id="c0ee4-168">The offer document template is a combination of the text that will be part of the offer as well as the defined offer data placeholders.</span></span> 

<span data-ttu-id="c0ee4-169">Para crear una plantilla de documento de oferta, haga lo siguiente.</span><span class="sxs-lookup"><span data-stu-id="c0ee4-169">To create an offer document template, do the following.</span></span>

1.  <span data-ttu-id="c0ee4-170">Vaya a **Administración de ofertas**.</span><span class="sxs-lookup"><span data-stu-id="c0ee4-170">Go to **Offer management**.</span></span>

1.  <span data-ttu-id="c0ee4-171">Expanda la sección **Biblioteca** en el panel de navegación izquierdo y a continuación, vaya a **Plantillas**.</span><span class="sxs-lookup"><span data-stu-id="c0ee4-171">Expand the **Library** section in the left navigation pane and go to **Templates**.</span></span>

    <span data-ttu-id="c0ee4-172">La página **Plantillas** mostrará una lista de plantillas de documento que ya se han definido.</span><span class="sxs-lookup"><span data-stu-id="c0ee4-172">The **Templates** page will display a list of document templates that have already been defined.</span></span>

1.  <span data-ttu-id="c0ee4-173">Para crear una plantilla de documento nueva, haga clic en **Nueva plantilla**.</span><span class="sxs-lookup"><span data-stu-id="c0ee4-173">To create a new document template, click **New Template**.</span></span>

1.  <span data-ttu-id="c0ee4-174">Especifique un nombre único para la plantilla y haga clic en **Crear**.</span><span class="sxs-lookup"><span data-stu-id="c0ee4-174">Enter a unique name for the template and click **Create**.</span></span>

1.  <span data-ttu-id="c0ee4-175">Use el editor de texto enriquecido para insertar o editar el contenido del documento de la propuesta.</span><span class="sxs-lookup"><span data-stu-id="c0ee4-175">Use the rich text editor to insert or edit the offer document content.</span></span> <span data-ttu-id="c0ee4-176">Puede insertar tablas, imágenes, e hipervínculos mediante las opciones disponibles en la parte superior del editor de texto.</span><span class="sxs-lookup"><span data-stu-id="c0ee4-176">You can insert tables, images, and hyperlinks using the options available at the top of the text editor.</span></span>

1.  <span data-ttu-id="c0ee4-177">Puede insertar marcadores de posición de datos de la propuesta en el documento de la plantilla de la propuesta:</span><span class="sxs-lookup"><span data-stu-id="c0ee4-177">You can insert offer data placeholders in the offer template document by:</span></span>

    - <span data-ttu-id="c0ee4-178">Arrastrando y soltando desde el panel derecho.</span><span class="sxs-lookup"><span data-stu-id="c0ee4-178">Dragging and dropping from the right pane.</span></span>

    - <span data-ttu-id="c0ee4-179">Poniendo un hashtag en el marcador de los datos de la propuesta directamente en el puesto.</span><span class="sxs-lookup"><span data-stu-id="c0ee4-179">Hashtag the offer data placeholder directly into position.</span></span> <span data-ttu-id="c0ee4-180">Escribiendo **\#** y después empezando a escribir el nombre del marcador de los datos de la propuesta.</span><span class="sxs-lookup"><span data-stu-id="c0ee4-180">Type **\#** and then start typing the name of the offer data placeholder.</span></span> <span data-ttu-id="c0ee4-181">Las opciones aparecerán en la lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="c0ee4-181">Options will appear in the drop-down list.</span></span> <span data-ttu-id="c0ee4-182">Haga clic o pulse en **Entrar** para insertar el marcador de los datos de la propuesta.</span><span class="sxs-lookup"><span data-stu-id="c0ee4-182">Click or press **Enter** to insert the offer data placeholder.</span></span>

    >[!NOTE]
    > - <span data-ttu-id="c0ee4-183">Para asociar un marcador a la plantilla de documento de oferta sin mostrar su valor al candidato, pase el mouse sobre el marcador de los datos de la propuesta y haga clic en el icono **Fijar**.</span><span class="sxs-lookup"><span data-stu-id="c0ee4-183">To associate a placeholder to the offer document template without exposing its value to the candidate, hover over the offer data placeholder and click the **Pin** icon.</span></span> <span data-ttu-id="c0ee4-184">Esto pasará el marcador a la sección **Datos de oferta anclados** de la plantilla de documento de la propuesta.</span><span class="sxs-lookup"><span data-stu-id="c0ee4-184">This will push the placeholder to the **Pinned offer data** section of the offer document template.</span></span> <span data-ttu-id="c0ee4-185">Para desanclar, siga los mismos pasos pero haga clic en **Desanclar** en la lista de marcadores de posición de los datos de la propuesta.</span><span class="sxs-lookup"><span data-stu-id="c0ee4-185">To unpin, follow the same steps but click **Unpin** in the list of offer data placeholders.</span></span>

    > - <span data-ttu-id="c0ee4-186">Para ver la lista de marcadores de posición de datos de la propuesta activos, cambie a la ficha **Activo** en el panel derecho.</span><span class="sxs-lookup"><span data-stu-id="c0ee4-186">To view the list of active offer data placeholders, switch to the **Active** tab in the right pane.</span></span>

    > - <span data-ttu-id="c0ee4-187">Si inserta un marcador de posición controlado por un conjunto de reglas de datos de la oferta, puede ver la dependencia de ese marcador de datos de la oferta en otros valores.</span><span class="sxs-lookup"><span data-stu-id="c0ee4-187">If you insert a placeholder that is driven by an offer data rule set, you can see the dependency of that offer data placeholder on other values.</span></span>

    > - <span data-ttu-id="c0ee4-188">Como alternativa, puede **Importar** el contenido de un archivo .docx en su equipo local y editarlo según sea necesario.</span><span class="sxs-lookup"><span data-stu-id="c0ee4-188">Alternatively, you can **Import** the content from a .docx file on your local machine and edit as required.</span></span> <span data-ttu-id="c0ee4-189">De esta forma, no tiene que escribir todo el contenido en el editor.</span><span class="sxs-lookup"><span data-stu-id="c0ee4-189">That way, you don’t have to type in all the content in the editor.</span></span>

1. <span data-ttu-id="c0ee4-190">Para obtener una vista preliminar del documento de la propuesta, use la opción **Vista previa** de la parte superior de la página.</span><span class="sxs-lookup"><span data-stu-id="c0ee4-190">To preview the offer document, use the **Preview** option at the top of the page.</span></span>

1. <span data-ttu-id="c0ee4-191">Para determinar si un creador de la propuesta puede editar el contenido del documento de la propuesta, use la opción **Gestionar permiso** de la parte superior de la página.</span><span class="sxs-lookup"><span data-stu-id="c0ee4-191">To control whether an offer creator can edit the offer document content, use the **Manage permission** option at the top of the page.</span></span> <span data-ttu-id="c0ee4-192">Si desea que el creador de la oferta solo inserte valores de marcador de posición y no edite el texto, establezca el valor de permiso en **No**.</span><span class="sxs-lookup"><span data-stu-id="c0ee4-192">If you want the offer creator to only insert placeholder values and not edit text, set the permission value to **No**.</span></span>

1. <span data-ttu-id="c0ee4-193">Haga clic en **Guardar** para guardar su progreso.</span><span class="sxs-lookup"><span data-stu-id="c0ee4-193">Click **Save** to save your progress.</span></span> <span data-ttu-id="c0ee4-194">La plantilla se guardará en estado de borrador.</span><span class="sxs-lookup"><span data-stu-id="c0ee4-194">The template will be saved in a draft state.</span></span>

1. <span data-ttu-id="c0ee4-195">Para finalizar y marcar el documento como publicado, haga clic en **Fin**.</span><span class="sxs-lookup"><span data-stu-id="c0ee4-195">To finalize and mark the document as published, click **Finish**.</span></span>

1. <span data-ttu-id="c0ee4-196">Puede ver qué plantillas de documento están activas actualmente, en modo de borrador, y se han almacenado y ya no se usan en la experiencia de destino de la biblioteca de plantillas de documentos.</span><span class="sxs-lookup"><span data-stu-id="c0ee4-196">You can see which document templates are currently active, in draft mode, and have been archived and are no longer in use on the document templates library landing experience.</span></span>

>[!NOTE]
> <span data-ttu-id="c0ee4-197">Puede eliminar cualquier plantilla de documento de oferta que no sea parte de una plantilla de paquete de oferta ya existente.</span><span class="sxs-lookup"><span data-stu-id="c0ee4-197">You can delete any offer document template that is not part of an existing offer package template.</span></span>


## <a name="offer-package-templates"></a><span data-ttu-id="c0ee4-198">Plantillas de paquetes de oferta</span><span class="sxs-lookup"><span data-stu-id="c0ee4-198">Offer package templates</span></span>

<span data-ttu-id="c0ee4-199">Los paquetes de ofertas son artefactos de oferta que se comparten con el candidato y están formados por una combinación de una o varias plantillas de documento de oferta.</span><span class="sxs-lookup"><span data-stu-id="c0ee4-199">Offer packages are the offer artifacts that are shared with the candidate and consist of a combination of one or more offer document templates.</span></span> <span data-ttu-id="c0ee4-200">Para crear un paquete de oferta, haga lo siguiente.</span><span class="sxs-lookup"><span data-stu-id="c0ee4-200">To create an offer package, do the following.</span></span>

1.  <span data-ttu-id="c0ee4-201">Vaya a **Administración de ofertas**.</span><span class="sxs-lookup"><span data-stu-id="c0ee4-201">Go to **Offer management**.</span></span>

1.  <span data-ttu-id="c0ee4-202">Vaya a **Paquetes** en el panel de exploración izquierdo.</span><span class="sxs-lookup"><span data-stu-id="c0ee4-202">Go to **Packages** from the left navigation pane.</span></span>

    <span data-ttu-id="c0ee4-203">Se muestra una lista de plantillas de paquetes activa que están disponibles para las usen los creadores de la propuesta.</span><span class="sxs-lookup"><span data-stu-id="c0ee4-203">A list of active package templates that are available for offer creators to use is displayed.</span></span>

1.  <span data-ttu-id="c0ee4-204">Para crear un nuevo paquete de oferta, haga clic en **Nuevo paquete**.</span><span class="sxs-lookup"><span data-stu-id="c0ee4-204">To create a new offer package, click **New Package**.</span></span>

1.  <span data-ttu-id="c0ee4-205">Especifique un nombre único y haga clic en **Crear**.</span><span class="sxs-lookup"><span data-stu-id="c0ee4-205">Enter a unique name and click **Create**.</span></span>

1.  <span data-ttu-id="c0ee4-206">Haga clic en **Agregar plantilla**.</span><span class="sxs-lookup"><span data-stu-id="c0ee4-206">Click **Add template**.</span></span>

    >[!NOTE]
    > - <span data-ttu-id="c0ee4-207">Puede elegir crear una plantilla nueva o seleccionar una ya existente.</span><span class="sxs-lookup"><span data-stu-id="c0ee4-207">You can choose to create a new template or choose from an existing one.</span></span>

    > - <span data-ttu-id="c0ee4-208">Si elige agregar una plantilla ya existente, tiene que asegurarse de que la plantilla de documento de la oferta se haya guardado, finalizado y marcado como activa.</span><span class="sxs-lookup"><span data-stu-id="c0ee4-208">If you choose to add an existing template, you need to make sure that the   offer document template was saved, finalized, and marked as   active.</span></span>
    
    > - <span data-ttu-id="c0ee4-209">Puede elegir tantas plantillas de documento como desee.</span><span class="sxs-lookup"><span data-stu-id="c0ee4-209">You can choose as many document templates as you want.</span></span> 
    
1.  <span data-ttu-id="c0ee4-210">Haga clic en **Listo** para volver a **Gestión de paquetes**.</span><span class="sxs-lookup"><span data-stu-id="c0ee4-210">Click **Done** to return to **Package management**.</span></span>

    <span data-ttu-id="c0ee4-211">Puede configurar la secuencia de documentos y también marcar si el documento específico de la oferta es necesario durante la creación de la oferta.</span><span class="sxs-lookup"><span data-stu-id="c0ee4-211">You can configure the sequence of the documents and also mark whether the specific offer document is required during offer creation.</span></span> <span data-ttu-id="c0ee4-212">El creador de la oferta tendrá una opción de eliminar documentos marcados como **No requerido**.</span><span class="sxs-lookup"><span data-stu-id="c0ee4-212">The offer creator will have an option to delete the documents marked as **Not required**.</span></span>

1. <span data-ttu-id="c0ee4-213">Para guardar la plantilla del paquete de la oferta de modo que todos los creadores de ofertas puedan usarla, haga clic en **Guardar y publicar**.</span><span class="sxs-lookup"><span data-stu-id="c0ee4-213">To save the offer package template so that it's usable by all offer creators, click **Save and publish**.</span></span>

   <span data-ttu-id="c0ee4-214">Para ver las plantillas de paquete de oferta de borrador, vaya a la pestaña **Borradores**. Si se realiza un cambio en la plantilla de paquete de oferta, tiene que guardarse y volverse a publicar.</span><span class="sxs-lookup"><span data-stu-id="c0ee4-214">To view draft offer package templates, go to the **Drafts** tab. If a change is made to the offer package template, it must be  saved and republished.</span></span>

## <a name="configure-an-offer-process"></a><span data-ttu-id="c0ee4-215">Configurar un proceso de oferta</span><span class="sxs-lookup"><span data-stu-id="c0ee4-215">Configure an offer process</span></span>

<span data-ttu-id="c0ee4-216">Existen varias partes del proceso de creación de la oferta que un administrador de Attract puede configurar.</span><span class="sxs-lookup"><span data-stu-id="c0ee4-216">There are several parts of the offer creation process that can be configured by an Attract administrator.</span></span>

- <span data-ttu-id="c0ee4-217">**Aprobaciones de oferta** - Elija si es necesario aprobar la oferta antes de enviarla al candidato.</span><span class="sxs-lookup"><span data-stu-id="c0ee4-217">**Offer approvals** - Choose whether offer approvals are required before the offer can be sent to the candidate.</span></span> <span data-ttu-id="c0ee4-218">Como administrador, puede decidir también si todas las aprobaciones de oferta se producirrán de manera secuencial o en un flujo de trabajo de aprobación paralelo.</span><span class="sxs-lookup"><span data-stu-id="c0ee4-218">As an administrator, you can also decide whether all offer approvals will happen in a sequential manner or parallel approval workflow.</span></span> <span data-ttu-id="c0ee4-219">También puede ordenar si los aprobadores de la propuesta deben agregar un comentario junto con su aprobación de la propuesta.</span><span class="sxs-lookup"><span data-stu-id="c0ee4-219">You can also mandate whether offer approvers must add a comment along with their offer approval.</span></span> <span data-ttu-id="c0ee4-220">Las aprobaciones de propuesta son obligatorias para todas las ofertas que no son estándar.</span><span class="sxs-lookup"><span data-stu-id="c0ee4-220">Offer approvals are mandatory for all non-standard offers.</span></span>

- <span data-ttu-id="c0ee4-221">**Experiencia de la propuesta del candidato** - Como administrador, tiene la opción de establecer si todas las propuestas tienen una fecha de vencimiento, y si es así cuál tiene que ser el aplazamiento predeterminado para la fecha de vencimiento.</span><span class="sxs-lookup"><span data-stu-id="c0ee4-221">**Candidate’s offer experience** - As administrator, you can choose to set whether all offers have an expiration date, and if so, what the default offset for the expiration date should be.</span></span> <span data-ttu-id="c0ee4-222">También puede configurar si los candidatos pueden rechazar una propuesta.</span><span class="sxs-lookup"><span data-stu-id="c0ee4-222">You can also configure whether candidates can decline an offer.</span></span>

- <span data-ttu-id="c0ee4-223">**Firmas electrónicas** - Como administrador, puede elegir también el método que los candidatos pueden utilizar para firmar propuestas.</span><span class="sxs-lookup"><span data-stu-id="c0ee4-223">**e-Signatures** - As an administrator, you can also choose the method that candidates can use to sign offers.</span></span>
    - <span data-ttu-id="c0ee4-224">Adobe Sign- Todos los paquetes de la propuesta se enviarán y firmarán mediante Adobe Sign.</span><span class="sxs-lookup"><span data-stu-id="c0ee4-224">Adobe Sign - All offer packages will be sent and signed via Adobe Sign.</span></span> <span data-ttu-id="c0ee4-225">Cada creador de ofertas que publica la oferta necesita tener su cuenta de Adobe Sign conectada a Attract.</span><span class="sxs-lookup"><span data-stu-id="c0ee4-225">Each offer creator publishing the offer needs to have their Adobe Sign account connected to Attract.</span></span> <span data-ttu-id="c0ee4-226">Para las licencias de Adobe Sign y una prueba gratis, visite este [vínculo](https://acrobat.adobe.com/us/en/business/integrations/microsoft-dynamics-365-for-talent.html).</span><span class="sxs-lookup"><span data-stu-id="c0ee4-226">For Adobe Sign licenses and a free Trial, please visit this [link](https://acrobat.adobe.com/us/en/business/integrations/microsoft-dynamics-365-for-talent.html).</span></span>

    - <span data-ttu-id="c0ee4-227">DocuSign- Todos los paquetes de la propuesta se enviarán y firmarán mediante DocuSign.</span><span class="sxs-lookup"><span data-stu-id="c0ee4-227">DocuSign - All offer packages will be sent and signed via DocuSign.</span></span> <span data-ttu-id="c0ee4-228">Cada creador de ofertas que publica la oferta necesita tener su cuenta de DocuSign conectada a Attract.</span><span class="sxs-lookup"><span data-stu-id="c0ee4-228">Each offer creator publishing the offer needs to have their DocuSign account connected to Attract.</span></span> 
    
    - <span data-ttu-id="c0ee4-229">ESign - ésta es la opción predeterminada, proporcionada lista para usar, donde el usuario puede firmar una oferta escribiendo su nombre e iniciales.</span><span class="sxs-lookup"><span data-stu-id="c0ee4-229">ESign - This is the default option, provided out of the box, where the user can sign an offer by typing their name and initials.</span></span>


<span data-ttu-id="c0ee4-230">Para obtener más información acerca del proceso de creación de la oferta, consulte [Crear, aprobar y firmar propuestas](./creating-offers.md).</span><span class="sxs-lookup"><span data-stu-id="c0ee4-230">To learn more about the offer creation process, see [Creating, approving, and signing offers](./creating-offers.md).</span></span>
