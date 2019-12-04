---
title: Novedades o cambios en la aplicación Dynamics AX versión 7.0.1 (mayo de 2016)
description: Este artículo describe las características que son nuevas o que han cambiado en la aplicación Microsoft Dynamics AX versión 7.0.1. Esta versión se publicó en mayo de 2016 y tiene un número de compilación de 7.0.1265.23014.
author: sericks007
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
ROBOTS: NOINDEX, NOFOLLOW
audience: Application User, Developer, IT Pro
ms.reviewer: josaw
ms.search.scope: Operations
ms.custom: 91213
ms.assetid: f0bbc78f-87fc-40e9-b46a-6655893f69be
ms.search.region: Global
ms.author: sericks
ms.search.validFrom: 2016-05-31
ms.dyn365.ops.version: AX 7.0.1
ms.openlocfilehash: 715e0f8d08c6abbde35eb917cddc4ecf4b7b67ed
ms.sourcegitcommit: 57bc7e17682e2edb5e1766496b7a22f4621819dd
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/18/2019
ms.locfileid: "2811465"
---
# <a name="whats-new-or-changed-in-dynamics-ax-application-version-701-may-2016"></a><span data-ttu-id="6dd22-104">Novedades o cambios en la aplicación Dynamics AX versión 7.0.1 (mayo de 2016)</span><span class="sxs-lookup"><span data-stu-id="6dd22-104">What's new or changed in Dynamics AX application version 7.0.1 (May 2016)</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="6dd22-105">Este artículo describe las características que son nuevas o que han cambiado en la aplicación Microsoft Dynamics AX versión 7.0.1.</span><span class="sxs-lookup"><span data-stu-id="6dd22-105">This article describes features that are either new or changed in Microsoft Dynamics AX application version 7.0.1.</span></span> <span data-ttu-id="6dd22-106">Esta versión se publicó en mayo de 2016 y tiene un número de compilación de 7.0.1265.23014.</span><span class="sxs-lookup"><span data-stu-id="6dd22-106">This version was released in May 2016 and has a build number of 7.0.1265.23014.</span></span>

## <a name="electronic-reporting-er"></a><span data-ttu-id="6dd22-107">Informes electrónicos (ER)</span><span class="sxs-lookup"><span data-stu-id="6dd22-107">Electronic reporting (ER)</span></span>

| <span data-ttu-id="6dd22-108">¿Qué se puede hacer?</span><span class="sxs-lookup"><span data-stu-id="6dd22-108">What can you do?</span></span> | <span data-ttu-id="6dd22-109">¿Por qué esto es importante?</span><span class="sxs-lookup"><span data-stu-id="6dd22-109">Why is this important?</span></span> |
|------------------|------------------------|
| <span data-ttu-id="6dd22-110">Configure un cuadro de diálogo en tiempo de ejecución para diseñar informes de informes electrónicos (ER), de manera que los usuarios puedan seleccionar las dimensiones financieras que desean.</span><span class="sxs-lookup"><span data-stu-id="6dd22-110">Configure a run-time dialog box for designing Electronic reporting (ER) reports, so that users can select the financial dimensions that they want.</span></span> | <span data-ttu-id="6dd22-111">En tiempo de ejecución, en el cuadro de diálogo para ejecutar un informe de ER, los usuarios pueden seleccionar varias dimensiones financieras.</span><span class="sxs-lookup"><span data-stu-id="6dd22-111">At run time, in the dialog box for running an ER report, users can select multiple financial dimensions.</span></span> <span data-ttu-id="6dd22-112">Los detalles de las dimensiones financieras seleccionadas se mostrarán en el documento electrónico que se genera.</span><span class="sxs-lookup"><span data-stu-id="6dd22-112">The details of the selected financial dimensions will be displayed in the electronic document that is generated.</span></span> |
| <span data-ttu-id="6dd22-113">Configure el acceso a varias dimensiones financieras durante el diseño de un informe de ER, mediante una asignación única al origen de datos deseado.</span><span class="sxs-lookup"><span data-stu-id="6dd22-113">Configure access to multiple financial dimensions during the design of an ER report, via a single mapping to the desired data source.</span></span> | <span data-ttu-id="6dd22-114">La misma configuración de informes de ER se puede utilizar para generar documentos electrónicos que presentan datos transaccionales junto con detalles de las dimensiones financieras, independientemente del número de dimensiones financieras seleccionadas por el usuario o configuradas por la instancia o entidad jurídica actual.</span><span class="sxs-lookup"><span data-stu-id="6dd22-114">The same ER report configuration can be used to generate electronic documents that present transactional data together with details of financial dimensions, regardless of the number of financial dimensions that are either selected by the user or configured for the current legal entity or instance.</span></span> |
| <span data-ttu-id="6dd22-115">Configure un informe de ER para introducir datos en las columnas generadas dinámicamente de un documento electrónico que se crea en el formato de hoja de cálculo OPENXML.</span><span class="sxs-lookup"><span data-stu-id="6dd22-115">Configure an ER report to enter data in dynamically generated columns of an electronic document that is created in OPENXML worksheet format.</span></span> | <span data-ttu-id="6dd22-116">Un informe de ER puede introducir datos en una hoja de cálculo OPENXML que se genera a través de columnas de replicación horizontal.</span><span class="sxs-lookup"><span data-stu-id="6dd22-116">An ER report can enter data in an OPENXML worksheet that is generated, via horizontally replicating columns.</span></span> <span data-ttu-id="6dd22-117">Por lo tanto, se puede reutilizar la misma configuración de informes de ER para generar documentos electrónicos que tienen un número diferente de columnas generadas dinámicamente.</span><span class="sxs-lookup"><span data-stu-id="6dd22-117">Therefore, the same ER report configuration can be reused to generate electronic documents that have a different number of dynamically generated columns.</span></span> |
| <span data-ttu-id="6dd22-118">Configure los destinos de ER para que el resultado de salida de un formato se dirija a un destino específico: archivo o correo electrónico (carpeta de Microsoft SharePoint o Almacenamiento de Microsoft Azure).</span><span class="sxs-lookup"><span data-stu-id="6dd22-118">Configure ER destinations so that the output result of a format is directed to specific destination: file, email, or archive (Microsoft SharePoint folder or Microsoft Azure Storage).</span></span> | <span data-ttu-id="6dd22-119">Anteriormente, cuando ejecutaba una configuración de ER, aparecería un cuadro de mensaje que requería la acción de usuario para guardar o abrir un archivo.</span><span class="sxs-lookup"><span data-stu-id="6dd22-119">Previously, when you ran an ER configuration, a message box appeared that required user action to save or open a file.</span></span> <span data-ttu-id="6dd22-120">Ahora puede preconfigurar un destino para cada configuración de formato y para cada componente de salida (una carpeta o un archivo) por separado.</span><span class="sxs-lookup"><span data-stu-id="6dd22-120">You can now pre-configure a destination for each format configuration and for each output component (a folder or a file) separately.</span></span> <span data-ttu-id="6dd22-121">Los usuarios que tienen derechos de acceso adecuados también pueden modificar la configuración de destino en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="6dd22-121">Users who have appropriate access rights can also modify destination settings at run time.</span></span> |

## <a name="pos--microsoft-dynamics-ax-retail"></a><span data-ttu-id="6dd22-122">PDV - Microsoft Dynamics AX Retail</span><span class="sxs-lookup"><span data-stu-id="6dd22-122">POS – Microsoft Dynamics AX Retail</span></span>

| <span data-ttu-id="6dd22-123">¿Qué se puede hacer?</span><span class="sxs-lookup"><span data-stu-id="6dd22-123">What can you do?</span></span> | <span data-ttu-id="6dd22-124">¿Por qué esto es importante?</span><span class="sxs-lookup"><span data-stu-id="6dd22-124">Why is this important?</span></span> |
|------------------|------------------------|
| <span data-ttu-id="6dd22-125">Utilice el explorador de Google Chrome.</span><span class="sxs-lookup"><span data-stu-id="6dd22-125">Use the Google Chrome browser.</span></span> | <span data-ttu-id="6dd22-126">Los minoristas pueden iniciar ahora Cloud POS desde el explorador de Chrome y pueden probar toda la funcionalidad que está disponible en la versión de Microsoft Edge e Internet Explorer de Cloud POS.</span><span class="sxs-lookup"><span data-stu-id="6dd22-126">Retailers can now start Cloud POS from the Chrome browser, and can experience all the functionality that is available in the Microsoft Edge and Internet Explorer version of Cloud POS.</span></span> |

## <a name="financial-reporting"></a><span data-ttu-id="6dd22-127">Informes financieros</span><span class="sxs-lookup"><span data-stu-id="6dd22-127">Financial reporting</span></span>

| <span data-ttu-id="6dd22-128">¿Qué se puede hacer?</span><span class="sxs-lookup"><span data-stu-id="6dd22-128">What can you do?</span></span> | <span data-ttu-id="6dd22-129">¿Por qué esto es importante?</span><span class="sxs-lookup"><span data-stu-id="6dd22-129">Why is this important?</span></span> |
|------------------|------------------------|
| <span data-ttu-id="6dd22-130">Vuelva a generar el data mart de informes financieros.</span><span class="sxs-lookup"><span data-stu-id="6dd22-130">Rebuild the Financial reporting data mart.</span></span> | <span data-ttu-id="6dd22-131">Al mover las bases de datos de Dynamics AX entre entornos o realizar otros cambios invasivos en el entorno, es posible que se tenga que volver a generar la base de datos de informes financieros.</span><span class="sxs-lookup"><span data-stu-id="6dd22-131">When you move Dynamics AX databases between environments or make other invasive changes to the environment, the Financial reporting database might have to be rebuilt.</span></span> <span data-ttu-id="6dd22-132">Ahora se proporciona un script de Windows PowerShell para volver a generar la base de datos.</span><span class="sxs-lookup"><span data-stu-id="6dd22-132">A Windows PowerShell script is now provided to rebuild the database for you.</span></span> |
| <span data-ttu-id="6dd22-133">Ya no se pueden seleccionar opciones del diseñador de informes que no son válidas.</span><span class="sxs-lookup"><span data-stu-id="6dd22-133">You can no longer select report designer options that aren't valid.</span></span> | <span data-ttu-id="6dd22-134">Varias opciones del diseñador de informes que se utilizaban en las versiones del mercado de Management Reporter no se aplican a esta versión de Dynamics AX.</span><span class="sxs-lookup"><span data-stu-id="6dd22-134">Several report designer options that were used in the in-market versions of Management reporter don't apply to this version of Dynamics AX.</span></span> <span data-ttu-id="6dd22-135">Estas opciones estaban relacionados con el diseño de informes financieros, salida y vinculación.</span><span class="sxs-lookup"><span data-stu-id="6dd22-135">These options were related to financial report design, output, and linking.</span></span> <span data-ttu-id="6dd22-136">Estas opciones se han quitado del diseñador de informes financieros para evitar errores de usuario.</span><span class="sxs-lookup"><span data-stu-id="6dd22-136">These options have been removed from the financial report designer to prevent user errors.</span></span> |

## <a name="financial-management"></a><span data-ttu-id="6dd22-137">Administración financiera</span><span class="sxs-lookup"><span data-stu-id="6dd22-137">Financial management</span></span>

| <span data-ttu-id="6dd22-138">¿Qué se puede hacer?</span><span class="sxs-lookup"><span data-stu-id="6dd22-138">What can you do?</span></span> | <span data-ttu-id="6dd22-139">¿Por qué esto es importante?</span><span class="sxs-lookup"><span data-stu-id="6dd22-139">Why is this important?</span></span> |
|------------------|------------------------|
| <span data-ttu-id="6dd22-140">Generar archivos de pago positivos para los pagos de proveedores.</span><span class="sxs-lookup"><span data-stu-id="6dd22-140">Generate positive pay files for accounts payable payments.</span></span> | <span data-ttu-id="6dd22-141">Los archivos positivos de pago se pueden generar para ayudar a evitar fraude de cheques.</span><span class="sxs-lookup"><span data-stu-id="6dd22-141">Positive pay files can be generated to help prevent check fraud.</span></span> |

## <a name="warehouse-and-production"></a><span data-ttu-id="6dd22-142">Almacén y producción</span><span class="sxs-lookup"><span data-stu-id="6dd22-142">Warehouse and production</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="6dd22-143">¿Qué se puede hacer?</span><span class="sxs-lookup"><span data-stu-id="6dd22-143">What can you do?</span></span></th>
<th><span data-ttu-id="6dd22-144">¿Por qué esto es importante?</span><span class="sxs-lookup"><span data-stu-id="6dd22-144">Why is this important?</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="6dd22-145">Definir una directiva de trabajo de almacén que controle la creación de trabajo para un conjunto de productos en almacenes específicos.</span><span class="sxs-lookup"><span data-stu-id="6dd22-145">Define a warehouse work policy that controls the creation of work for a set of products at specific locations.</span></span></td>
<td><span data-ttu-id="6dd22-146">Los procesos de almacén no siempre incluyen trabajo.</span><span class="sxs-lookup"><span data-stu-id="6dd22-146">Warehouse processes don't always include work.</span></span> <span data-ttu-id="6dd22-147">Mediante la nueva directiva de trabajo de almacén, puede evitar la creación de trabajo para picking de materia prima y ubicación de bienes terminados para un conjunto de productos en ubicaciones específicas.</span><span class="sxs-lookup"><span data-stu-id="6dd22-147">By using the new warehouse work policy, you can prevent work from being created for raw material picking and put-away of finished goods for a set of products at specific locations.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="6dd22-148">Especificar que una ubicación de salida de producción no está controlada por matrículas de entidad de almacén.</span><span class="sxs-lookup"><span data-stu-id="6dd22-148">Specify that a production output location isn't license plate–controlled.</span></span></td>
<td><span data-ttu-id="6dd22-149">Ahora puede especificar que una ubicación de salida de producción no está controlada por matrículas de entidad de almacén.</span><span class="sxs-lookup"><span data-stu-id="6dd22-149">You can now specify that a product output location isn't license plate–controlled.</span></span> <span data-ttu-id="6dd22-150">Por ejemplo, esta característica es útil cuando un pedido de producción ascendente notifica artículos como terminados directamente a una ubicación que actúa como la ubicación de entrada de producción para un pedido de producción descendente.</span><span class="sxs-lookup"><span data-stu-id="6dd22-150">For example, this feature is useful when an upstream production order reports items as finished directly to a location that acts as production input location for a downstream production order.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="6dd22-151">Admitir listas de materiales que incluyan artículos con diferentes dimensiones de producto del mismo artículo.</span><span class="sxs-lookup"><span data-stu-id="6dd22-151">Support BOMs that include items with different product dimensions of the same item.</span></span></td>
<td><span data-ttu-id="6dd22-152">Cuando se utiliza una o varias de las dimensiones del producto en producción, tendrá situaciones en las que desee producir un artículo, en función de una variante diferente del mismo artículo.</span><span class="sxs-lookup"><span data-stu-id="6dd22-152">When using one or multiple of the product dimensions in production, you can have situations where you would like to produce an item, based on a different variant of the same item.</span></span> <span data-ttu-id="6dd22-153">Para obtener más información, consulte <a href="https://blogs.msdn.microsoft.com/axmfg/2015/12/22/support-for-boms-that-includes-items-with-different-product-dimensions-of-the-same-item/">este blog</a>.</span><span class="sxs-lookup"><span data-stu-id="6dd22-153">For more information, see <a href="https://blogs.msdn.microsoft.com/axmfg/2015/12/22/support-for-boms-that-includes-items-with-different-product-dimensions-of-the-same-item/">this blog</a>.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="6dd22-154">Los pedidos de producción con estructuras circulares en el primer nivel de sus listas de materiales se excluyen del cálculo del nivel de L. MAT para la planificación de recursos materiales.</span><span class="sxs-lookup"><span data-stu-id="6dd22-154">Production orders with circular structures at the first level of their BOMs are excluded from BOM level calculation for material resource planning.</span></span></td>
<td><span data-ttu-id="6dd22-155">No es posible asignar niveles de L. MAT correctos a las variantes de producto para los pedidos de producción que causan circularidad en la jerarquía de L. MAT.</span><span class="sxs-lookup"><span data-stu-id="6dd22-155">It is not possible to assign correct BOM levels to product variants for production orders that cause circularity in the BOM hierarchy.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="6dd22-156">Calcule niveles de L. MAT independientes para la planificación de recursos materiales y el cálculo de costes:</span><span class="sxs-lookup"><span data-stu-id="6dd22-156">Calculate separate BOM levels for material resource planning and cost calculation:</span></span>
<ul>
<li><span data-ttu-id="6dd22-157">Para la planificación de recursos materiales, los niveles de L. MAT se calculan en la nueva tabla <strong>ReqItemLevel</strong>.</span><span class="sxs-lookup"><span data-stu-id="6dd22-157">For material resource planning, BOM levels are calculated in the new <strong>ReqItemLevel</strong> table.</span></span> <span data-ttu-id="6dd22-158">Los pedidos de producción finalizados se omiten en el cálculo.</span><span class="sxs-lookup"><span data-stu-id="6dd22-158">Ended production orders are ignored in the calculation.</span></span></li>
<li><span data-ttu-id="6dd22-159">Para el cálculo de costes de producción, los niveles de L. MAT se calculan en la <strong>InventTable</strong>.</span><span class="sxs-lookup"><span data-stu-id="6dd22-159">For production cost calculation, BOM levels are calculated in the <strong>InventTable</strong>.</span></span> <span data-ttu-id="6dd22-160">Los pedidos de producción finalizados se incluyen en el cálculo.</span><span class="sxs-lookup"><span data-stu-id="6dd22-160">Ended production orders are included in the calculation.</span></span></li>
</ul>
</td>
<td>
<ul>
<li><span data-ttu-id="6dd22-161">Cuando se ejecuta la planificación de recursos materiales, por ejemplo, la expansión y la programación de la planificación maestra, solo se tienen que volver a calcular los niveles de la lista de materiales utilizados para la planificación de recursos de materiales.</span><span class="sxs-lookup"><span data-stu-id="6dd22-161">When running material resource planning, for example, master planning plan scheduling and explosion, only BOM levels used for material resource planning need to be recalculated.</span></span> <span data-ttu-id="6dd22-162">En otras palabras, no hay ninguna necesidad de calcular niveles de lista de materiales utilizados para el cálculo de gestión de costes de producción.</span><span class="sxs-lookup"><span data-stu-id="6dd22-162">In other words, there is no need to calculate BOM levels used for production costing calculation.</span></span></li>
<li><span data-ttu-id="6dd22-163">Al ejecutar operaciones de gestión de costes, por ejemplo, el cierre de inventario, solo se tienen que volver a calcular los niveles de lista de materiales para el cálculo de gestión de costes de producción.</span><span class="sxs-lookup"><span data-stu-id="6dd22-163">When running costing operations, for example, inventory closing, only BOM levels used for production costing calculation need to be recalculated.</span></span></li>
</ul>
</td>
</tr>
</tbody>
</table>

## <a name="additional-resources"></a><span data-ttu-id="6dd22-164">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="6dd22-164">Additional resources</span></span>

[<span data-ttu-id="6dd22-165">Página principal de Novedades y cambios en Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="6dd22-165">What's new or changed in Finance and Operations home page</span></span>](whats-new-changed.md)

[<span data-ttu-id="6dd22-166">Guías de tareas nuevas o actualizadas (mayo de 2016)</span><span class="sxs-lookup"><span data-stu-id="6dd22-166">New or updated task guides (May 2016)</span></span>](new-updated-task-guides-available-may-2016.md)