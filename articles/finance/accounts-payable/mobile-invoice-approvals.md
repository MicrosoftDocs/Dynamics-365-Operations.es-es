---
title: Aprobaciones de factura móvil
description: Este tema está pensando para proporcionar un método práctico de diseñar escenarios móviles con las aprobaciones de facturas de proveedores para aplicaciones móviles como un caso de uso.
author: abruer
manager: AnnBe
ms.date: 08/22/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User, IT Pro
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.custom: 262034
ms.assetid: 9db38b3f-26b3-436e-8449-7ff243568a18
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: dd72c8a54498cc6ffae7125c5c2f44bfac5a5995
ms.sourcegitcommit: 574309903f15eeab7911091114885b5c7279d22a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/24/2019
ms.locfileid: "2658653"
---
# <a name="mobile-invoice-approvals"></a><span data-ttu-id="09f90-103">Aprobaciones de factura móvil</span><span class="sxs-lookup"><span data-stu-id="09f90-103">Mobile invoice approvals</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="09f90-104">Las capacidades móviles permiten a un usuario empresarial diseñar experiencias móviles.</span><span class="sxs-lookup"><span data-stu-id="09f90-104">Mobile capabilities let a business user design mobile experiences.</span></span> <span data-ttu-id="09f90-105">Para situaciones avanzadas, la plataforma también permite a los desarrolladores ampliar las capacidades como desean.</span><span class="sxs-lookup"><span data-stu-id="09f90-105">For advanced scenarios, the platform also lets developers extend the capabilities as they desire.</span></span> <span data-ttu-id="09f90-106">La forma más eficaz de aprender algunos de los conceptos nuevos sobre capacidades móviles es pasar por el proceso de diseño de algunos escenarios.</span><span class="sxs-lookup"><span data-stu-id="09f90-106">The most effective way to learn some of the new concepts on mobile is to go through the process of designing a few scenarios.</span></span> <span data-ttu-id="09f90-107">Este tema está pensando para proporcionar un método práctico de diseñar escenarios móviles con las aprobaciones de facturas de proveedores para aplicaciones móviles como un caso de uso.</span><span class="sxs-lookup"><span data-stu-id="09f90-107">This topic is intended to provide a practical approach to designing mobile scenarios by taking vendor invoice approvals for mobile as a use case.</span></span> <span data-ttu-id="09f90-108">Este tema le ayudará a diseñar otras variaciones de los escenarios y se puede aplicar a otros escenarios que no están relacionados con las facturas de proveedores.</span><span class="sxs-lookup"><span data-stu-id="09f90-108">This topic should help you design other variations of the scenarios and can also be applied to other scenarios that aren’t related to vendor invoices.</span></span>

<a name="prerequisites"></a><span data-ttu-id="09f90-109">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="09f90-109">Prerequisites</span></span>
-------------

| <span data-ttu-id="09f90-110">Requisito previo</span><span class="sxs-lookup"><span data-stu-id="09f90-110">Prerequisite</span></span>                                                                                            | <span data-ttu-id="09f90-111">Descripción</span><span class="sxs-lookup"><span data-stu-id="09f90-111">Description</span></span>                                                                                                                                                          |
|---------------------------------------------------------------------------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| <span data-ttu-id="09f90-112">Manual sobre capacidades móviles de lectura previa</span><span class="sxs-lookup"><span data-stu-id="09f90-112">Mobile handbook pre-read</span></span>                                                                                |[<span data-ttu-id="09f90-113">Plataforma móvil</span><span class="sxs-lookup"><span data-stu-id="09f90-113">Mobile platform</span></span>](../../dev-itpro/mobile-apps/platform/mobile-platform-home-page.md)                                                                                                  |
| <span data-ttu-id="09f90-114">Dynamics 365 Finance</span><span class="sxs-lookup"><span data-stu-id="09f90-114">Dynamics 365 Finance</span></span>                                                                              | <span data-ttu-id="09f90-115">Un entorno que tiene la versión 1611 y la actualización de plataforma 3 (noviembre de 2016)</span><span class="sxs-lookup"><span data-stu-id="09f90-115">An environment that has version 1611 and Platform update 3 (November 2016)</span></span>                   |
| <span data-ttu-id="09f90-116">Instalar revisión KB 3204341.</span><span class="sxs-lookup"><span data-stu-id="09f90-116">Install hotfix KB 3204341.</span></span>                                                                              | <span data-ttu-id="09f90-117">El grabador de tareas puede registrar de forma errónea dos comandos Close para diálogos desplegables incluidos la actualización de plataforma 3 (noviembre de 2016).</span><span class="sxs-lookup"><span data-stu-id="09f90-117">Task recorder can erroneously record two Close commands for dropdown dialogs; this is included in Platform update 3 (November 2016 update).</span></span> |
| <span data-ttu-id="09f90-118">Instalar revisión KB 3207800.</span><span class="sxs-lookup"><span data-stu-id="09f90-118">Install hotfix KB 3207800.</span></span>                                                                              | <span data-ttu-id="09f90-119">Esta revisión habilita los datos adjuntos que se verán en el cliente móvil, lo cual se incluye en la actualización de plataforma 3 (noviembre de 2016).</span><span class="sxs-lookup"><span data-stu-id="09f90-119">This hotfix enables attachments to be viewed on the mobile client; this is included in Platform update 3 (November 2016 update).</span></span>           |
| <span data-ttu-id="09f90-120">Instalar revisión KB 3208224.</span><span class="sxs-lookup"><span data-stu-id="09f90-120">Install hotfix KB 3208224.</span></span>                                                                              | <span data-ttu-id="09f90-121">El código de la aplicación para la aplicación de aprobación de facturas de proveedores móviles se incluye en la versión 7.0.1 (mayo de 2016).</span><span class="sxs-lookup"><span data-stu-id="09f90-121">Application code for the mobile vendor invoice approval application; this is included in version 7.0.1 (May 2016).</span></span>                          |
| <span data-ttu-id="09f90-122">Un dispositivo Android, iOS o Windows que tengan la aplicación móvil instalada.</span><span class="sxs-lookup"><span data-stu-id="09f90-122">An Android or iOS or a Windows device that has the mobile app installed.</span></span> | <span data-ttu-id="09f90-123">Busque la aplicación en la tienda de aplicaciones apropiada.</span><span class="sxs-lookup"><span data-stu-id="09f90-123">Search for the app in the appropriate app store.</span></span>                                                                                                                     |

## <a name="introduction"></a><span data-ttu-id="09f90-124">Introducción</span><span class="sxs-lookup"><span data-stu-id="09f90-124">Introduction</span></span>
<span data-ttu-id="09f90-125">Las aprobaciones móviles para las facturas de proveedor requieren la tres revisiones mencionadas en la sección de los requisititos previos.</span><span class="sxs-lookup"><span data-stu-id="09f90-125">Mobile approvals for vendor invoices require the three hotfixes that are mentioned in the “Prerequisites” section.</span></span> <span data-ttu-id="09f90-126">Estas revisiones no proporcionan un espacio de trabajo para las aprobaciones de facturas.</span><span class="sxs-lookup"><span data-stu-id="09f90-126">These hotfixes don’t provide a workspace for the invoice approvals.</span></span> <span data-ttu-id="09f90-127">Para saber qué es un espacio de trabajo en el contexto de las aplicaciones móviles, lea el manual referido en la sección de los requisitos previos.</span><span class="sxs-lookup"><span data-stu-id="09f90-127">To learn what a workspace is in the context of mobile, read the mobile handbook that is mentioned in the “Prerequisites” section.</span></span> <span data-ttu-id="09f90-128">Se debe diseñar un espacio de trabajo para aprobaciones de facturas.</span><span class="sxs-lookup"><span data-stu-id="09f90-128">The invoice approvals workspace must be designed.</span></span> 

<span data-ttu-id="09f90-129">Cada organización articula y define su proceso empresarial para las facturas de proveedores de forma diferente.</span><span class="sxs-lookup"><span data-stu-id="09f90-129">Every organization orchestrates and defines its business process for vendor invoices differently.</span></span> <span data-ttu-id="09f90-130">Antes de diseñar una experiencia móvil para las aprobaciones de la facturas de proveedores, debe tener en cuenta los siguientes aspectos del proceso empresarial.</span><span class="sxs-lookup"><span data-stu-id="09f90-130">Before you design a mobile experience for vendor invoice approvals, you should consider the following aspects of the business process.</span></span> <span data-ttu-id="09f90-131">La idea es usar estos puntos de datos tanto como sea posible para optimizar la experiencia del usuario en el dispositivo.</span><span class="sxs-lookup"><span data-stu-id="09f90-131">The idea is to use these data points as much as possible to optimize the user experience on the device.</span></span>

-   <span data-ttu-id="09f90-132">¿Qué campos del encabezado de la factura el usuario deseará ver en la experiencia móvil, y en qué pedidos?</span><span class="sxs-lookup"><span data-stu-id="09f90-132">What fields from the invoice header will the user want to see in the mobile experience, and in what order?</span></span>
-   <span data-ttu-id="09f90-133">¿Qué líneas del encabezado de la factura el usuario deseará ver en la experiencia móvil, y en qué pedidos?</span><span class="sxs-lookup"><span data-stu-id="09f90-133">What fields from the invoice lines will the user want to see in the mobile experience, and in what order?</span></span>
-   <span data-ttu-id="09f90-134">¿Cuántas líneas de factura hay en una factura?</span><span class="sxs-lookup"><span data-stu-id="09f90-134">How many invoice lines are there in an invoice?</span></span> <span data-ttu-id="09f90-135">Aplique la regla 80-20 aquí, y optimice para llegar al 80 por ciento.</span><span class="sxs-lookup"><span data-stu-id="09f90-135">Apply the 80-20 rule here, and optimize for the 80 percent.</span></span>
-   <span data-ttu-id="09f90-136">¿Los usuarios desearán ver las distribuciones contables (codificación de la factura) en el dispositivo móvil durante las revisiones?</span><span class="sxs-lookup"><span data-stu-id="09f90-136">Will users want to see accounting distributions (invoice coding) on the mobile device during reviews?</span></span> <span data-ttu-id="09f90-137">Si la respuesta a esta pregunta es afirmativa, tenga en cuenta las preguntas siguientes:</span><span class="sxs-lookup"><span data-stu-id="09f90-137">If the answer to this question is yes, consider the following questions:</span></span>
    -   <span data-ttu-id="09f90-138">¿Cuántas distribuciones contables (precio total, impuestos, cargos, divisiones, etc.) hay para una línea de factura?</span><span class="sxs-lookup"><span data-stu-id="09f90-138">How many accounting distributions (extended price, sales tax, charges, splits, and so on) are there for an invoice line?</span></span> <span data-ttu-id="09f90-139">Una vez más, aplique la regla 80-20.</span><span class="sxs-lookup"><span data-stu-id="09f90-139">Again, apply the 80-20 rule.</span></span>
    -   <span data-ttu-id="09f90-140">¿Las facturas también tienen distribuciones contables en el encabezado de factura?</span><span class="sxs-lookup"><span data-stu-id="09f90-140">Do the invoices also have accounting distributions on the invoice header?</span></span> <span data-ttu-id="09f90-141">En dicho caso, ¿estas distribuciones contables deben estar disponible en el dispositivo?</span><span class="sxs-lookup"><span data-stu-id="09f90-141">If so, should these accounting distributions be available on the device?</span></span>

> [!NOTE]
> <span data-ttu-id="09f90-142">Este tema no explica cómo editar distribuciones contables, porque esta funcionalidad no se admite actualmente para los escenarios móviles.</span><span class="sxs-lookup"><span data-stu-id="09f90-142">This topic doesn’t explain how to edit accounting distributions, because this functionality isn’t currently supported for mobile scenarios.</span></span>

-   <span data-ttu-id="09f90-143">¿Los usuarios desearán ver los datos adjuntos de la factura en el dispositivo?</span><span class="sxs-lookup"><span data-stu-id="09f90-143">Will users want to see attachments for the invoice on the device?</span></span>

<span data-ttu-id="09f90-144">El diseño de la experiencia móvil de las aprobaciones de facturas variará, en función de las respuestas a estas preguntas.</span><span class="sxs-lookup"><span data-stu-id="09f90-144">The design of the mobile experience for invoice approvals will differ, depending on the answers to these questions.</span></span> <span data-ttu-id="09f90-145">El objetivo es optimizar la experiencia del usuario para el proceso empresarial en las plataformas móviles de una organización.</span><span class="sxs-lookup"><span data-stu-id="09f90-145">The objective is to optimize the user experience for the business process on mobile in an organization.</span></span> <span data-ttu-id="09f90-146">En el resto de este tema, revisaremos dos variaciones del escenario que se basan en diferentes respuestas a las preguntas anteriores.</span><span class="sxs-lookup"><span data-stu-id="09f90-146">In the rest of this topic, we will look at two scenario variations that are based on different answers to the preceding questions.</span></span> 

<span data-ttu-id="09f90-147">Como orientación general, al trabajar con el diseñador para aplicaciones móviles, asegúrese de “publicar” los cambios para evitar perder las actualizaciones.</span><span class="sxs-lookup"><span data-stu-id="09f90-147">As a general guidance, when working with the mobile designer, make sure to 'publish' the changes to prevent losing the updates.</span></span>

## <a name="designing-a-simple-invoice-approval-scenario-for-contoso"></a><span data-ttu-id="09f90-148">Diseñar una situación de ejemplo sencillo de aprobación de facturas para Contoso</span><span class="sxs-lookup"><span data-stu-id="09f90-148">Designing a simple invoice approval scenario for Contoso</span></span>
<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="09f90-149">Atributo de escenario</span><span class="sxs-lookup"><span data-stu-id="09f90-149">Scenario attribute</span></span></th>
<th><span data-ttu-id="09f90-150">Respuesta</span><span class="sxs-lookup"><span data-stu-id="09f90-150">Answer</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="09f90-151">¿Qué campos del encabezado de la factura el usuario deseará ver en la experiencia móvil, y en qué pedidos?</span><span class="sxs-lookup"><span data-stu-id="09f90-151">What fields from the invoice header will the user want to see in the mobile experience, and in what order?</span></span></td>
<td><ol>
<li><span data-ttu-id="09f90-152">Nombre del proveedor</span><span class="sxs-lookup"><span data-stu-id="09f90-152">Vendor name</span></span></li>
<li><span data-ttu-id="09f90-153">Total de la factura</span><span class="sxs-lookup"><span data-stu-id="09f90-153">Invoice total</span></span></li>
<li><span data-ttu-id="09f90-154">Cuenta de facturación</span><span class="sxs-lookup"><span data-stu-id="09f90-154">Invoice account</span></span></li>
<li><span data-ttu-id="09f90-155">Número de factura</span><span class="sxs-lookup"><span data-stu-id="09f90-155">Invoice number</span></span></li>
<li><span data-ttu-id="09f90-156">Fecha de la factura</span><span class="sxs-lookup"><span data-stu-id="09f90-156">Invoice date</span></span></li>
<li><span data-ttu-id="09f90-157">Descripción de factura</span><span class="sxs-lookup"><span data-stu-id="09f90-157">Invoice description</span></span></li>
<li><span data-ttu-id="09f90-158">Fecha de vencimiento</span><span class="sxs-lookup"><span data-stu-id="09f90-158">Due date</span></span></li>
<li><span data-ttu-id="09f90-159">Divisa de la factura</span><span class="sxs-lookup"><span data-stu-id="09f90-159">Invoice currency</span></span></li>
</ol></td>
</tr>
<tr class="even">
<td><span data-ttu-id="09f90-160">¿Qué líneas del encabezado de la factura el usuario deseará ver en la experiencia móvil, y en qué pedidos?</span><span class="sxs-lookup"><span data-stu-id="09f90-160">What fields from the invoice lines will the user want to see in the mobile experience, and in what order?</span></span></td>
<td><ol>
<li><span data-ttu-id="09f90-161">Categoría de compras</span><span class="sxs-lookup"><span data-stu-id="09f90-161">Procurement category</span></span></li>
<li><span data-ttu-id="09f90-162">Cantidad</span><span class="sxs-lookup"><span data-stu-id="09f90-162">Quantity</span></span></li>
<li><span data-ttu-id="09f90-163">Precio unitario</span><span class="sxs-lookup"><span data-stu-id="09f90-163">Unit price</span></span></li>
<li><span data-ttu-id="09f90-164">Importe neto de línea</span><span class="sxs-lookup"><span data-stu-id="09f90-164">Line net amount</span></span></li>
<li><span data-ttu-id="09f90-165">Importe de la declaración de IRPF</span><span class="sxs-lookup"><span data-stu-id="09f90-165">1099 amount</span></span></li>
</ol></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="09f90-166">¿Cuántas líneas de factura hay en una factura?</span><span class="sxs-lookup"><span data-stu-id="09f90-166">How many invoice lines are there in an invoice?</span></span> <span data-ttu-id="09f90-167">Aplique la regla 80-20 aquí, y optimice para llegar al 80 por ciento.</span><span class="sxs-lookup"><span data-stu-id="09f90-167">Apply the 80-20 rule here, and optimize for the 80 percent.</span></span></td>
<td><span data-ttu-id="09f90-168">1</span><span class="sxs-lookup"><span data-stu-id="09f90-168">1</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="09f90-169">¿Los usuarios desearán ver las distribuciones contables (codificación de la factura) en el dispositivo móvil durante las revisiones?</span><span class="sxs-lookup"><span data-stu-id="09f90-169">Will users want to see accounting distributions (invoice coding) on the mobile device during reviews?</span></span></td>
<td><span data-ttu-id="09f90-170">Sí</span><span class="sxs-lookup"><span data-stu-id="09f90-170">Yes</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="09f90-171">¿Cuántas distribuciones contables (precio total, impuestos, cargos, etc.) hay para una línea de factura?</span><span class="sxs-lookup"><span data-stu-id="09f90-171">How many accounting distributions (extended price, sales tax, charges, and so on) are there for an invoice line?</span></span> <span data-ttu-id="09f90-172">Una vez más, aplique la regla 80-20.</span><span class="sxs-lookup"><span data-stu-id="09f90-172">Again, apply the 80-20 rule.</span></span></td>
<td><span data-ttu-id="09f90-173">Precio total: 2 Impuestos: 0 Cargos: 0</span><span class="sxs-lookup"><span data-stu-id="09f90-173">Extended price: 2 Sales tax: 0 Charges: 0</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="09f90-174">¿Las facturas también tienen distribuciones contables en el encabezado de factura?</span><span class="sxs-lookup"><span data-stu-id="09f90-174">Do the invoices also have accounting distributions on the invoice header?</span></span> <span data-ttu-id="09f90-175">En dicho caso, ¿estas distribuciones contables deben estar disponible en el dispositivo?</span><span class="sxs-lookup"><span data-stu-id="09f90-175">If so, should these accounting distributions be available on the device?</span></span></td>
<td><span data-ttu-id="09f90-176">No utilizado</span><span class="sxs-lookup"><span data-stu-id="09f90-176">Not used</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="09f90-177">¿Los usuarios desearán ver los datos adjuntos de la factura en el dispositivo?</span><span class="sxs-lookup"><span data-stu-id="09f90-177">Will users want to see attachments for the invoice on the device?</span></span></td>
<td><span data-ttu-id="09f90-178">Sí</span><span class="sxs-lookup"><span data-stu-id="09f90-178">Yes</span></span></td>
</tr>
</tbody>
</table>

### <a name="create-the-workspace"></a><span data-ttu-id="09f90-179">Crear el espacio de trabajo</span><span class="sxs-lookup"><span data-stu-id="09f90-179">Create the workspace</span></span>

1.  <span data-ttu-id="09f90-180">En un explorador, inicie sesión en la aplicación.</span><span class="sxs-lookup"><span data-stu-id="09f90-180">In a browser, and sign in to the application.</span></span>
2.  <span data-ttu-id="09f90-181">Una vez que haya iniciado sesión, agregue **&mode=mobile** a la dirección URL como se muestra en el siguiente ejemplo, y actualice la página: https://&lt;yoururl&gt;/?cmp=usmf&mi=DefaultDashboard **&mode=mobile**</span><span class="sxs-lookup"><span data-stu-id="09f90-181">After you’ve signed in, append **&mode=mobile** to the URL as shown in the following example, and refresh the page: https://&lt;yoururl&gt;/?cmp=usmf&mi=DefaultDashboard **&mode=mobile**</span></span>
3.  <span data-ttu-id="09f90-182">Haga clic en el botón **Configuración** (engranaje) en la parte superior derecha de la página y, a continuación, haga clic en **Aplicación móvil**.</span><span class="sxs-lookup"><span data-stu-id="09f90-182">Click the **Settings** (gear) button in the upper right of the page, and then click **Mobile app**.</span></span> <span data-ttu-id="09f90-183">El diseñador para aplicaciones móviles de la aplicación debe aparecer igual que lo hace el Grabador de tareas.</span><span class="sxs-lookup"><span data-stu-id="09f90-183">The mobile app designer must show up just as Task recorder shows up.</span></span>
4.  <span data-ttu-id="09f90-184">Haga clic en **Agregar** para crear un nuevo espacio de trabajo.</span><span class="sxs-lookup"><span data-stu-id="09f90-184">Click **Add** to create a new workspace.</span></span> <span data-ttu-id="09f90-185">Para este ejemplo, asigne un nombre al espacio de trabajo **Mis aprobaciones**.</span><span class="sxs-lookup"><span data-stu-id="09f90-185">For this example, name the workspace **My approvals**.</span></span>
5.  <span data-ttu-id="09f90-186">Escribir una descripción.</span><span class="sxs-lookup"><span data-stu-id="09f90-186">Enter a description.</span></span>
6.  <span data-ttu-id="09f90-187">Seleccione un color para el espacio de trabajo.</span><span class="sxs-lookup"><span data-stu-id="09f90-187">Select a workspace color.</span></span> <span data-ttu-id="09f90-188">El color del espacio de trabajo se usará para el estilo global de la experiencia móvil de este espacio de trabajo.</span><span class="sxs-lookup"><span data-stu-id="09f90-188">The workspace color will be used for the overall style of the mobile experience for this workspace.</span></span>
7.  <span data-ttu-id="09f90-189">Seleccione un icono para el espacio de trabajo.</span><span class="sxs-lookup"><span data-stu-id="09f90-189">Select an icon for the workspace.</span></span>
8.  <span data-ttu-id="09f90-190">Haga clic en **Listo**</span><span class="sxs-lookup"><span data-stu-id="09f90-190">Click **Done**</span></span>
9.  <span data-ttu-id="09f90-191">Haga clic en **Publicar espacio de trabajo** para guardar los cambios</span><span class="sxs-lookup"><span data-stu-id="09f90-191">Click **Publish workspace** to save the changes</span></span>

### <a name="vendor-invoices-assigned-to-me"></a><span data-ttu-id="09f90-192">Facturas de proveedor asignadas al usuario</span><span class="sxs-lookup"><span data-stu-id="09f90-192">Vendor invoices assigned to me</span></span>

<span data-ttu-id="09f90-193">La primera página para aplicaciones móviles que debe diseñar es la lista de facturas que se asignan al usuario para revisión.</span><span class="sxs-lookup"><span data-stu-id="09f90-193">The first mobile page that you should design is the list of invoices that are assigned to the user for review.</span></span> <span data-ttu-id="09f90-194">Para diseñar esta página para aplicaciones móviles, use la página **VendMobileInvoiceAssignedToMeListPage**.</span><span class="sxs-lookup"><span data-stu-id="09f90-194">To design this mobile page, use the **VendMobileInvoiceAssignedToMeListPage** page.</span></span> <span data-ttu-id="09f90-195">Para completar este procedimiento, asegúrese de que al menos se le asigna una factura de proveedores para revisión, y que la línea de factura tiene dos distribuciones.</span><span class="sxs-lookup"><span data-stu-id="09f90-195">Before you complete this procedure, make sure that at least one vendor invoice is assigned to you for review, and that the invoice line has two distributions.</span></span> <span data-ttu-id="09f90-196">Esta configuración cumple los requisitos para este supuesto.</span><span class="sxs-lookup"><span data-stu-id="09f90-196">This setup meets the requirements for this scenario.</span></span>

1.  <span data-ttu-id="09f90-197">En la dirección URL, reemplace el nombre del elemento de menú con **VendMobileInvoiceAssignedToMeListPage** para abrir la versión móvil de la página con la lista **Facturas de proveedor pendientes asignadas a mí** en el módulo **Proveedores**.</span><span class="sxs-lookup"><span data-stu-id="09f90-197">In the URL, replace the name of the menu item with **VendMobileInvoiceAssignedToMeListPage** to open the mobile version of the **Pending vendor invoices assigned to me** list page in the **Accounts payable** module.</span></span> <span data-ttu-id="09f90-198">En función del número de facturas que tiene en el sistema asignadas a usted, esta página mostrará dichas facturas.</span><span class="sxs-lookup"><span data-stu-id="09f90-198">Depending on the number of invoices that you have in your system assigned to you, this page will show those invoices.</span></span> <span data-ttu-id="09f90-199">Para buscar una factura específica, utilice el filtro a la izquierda.</span><span class="sxs-lookup"><span data-stu-id="09f90-199">To find a specific invoice, you can use the filter on the left.</span></span> <span data-ttu-id="09f90-200">Sin embargo, no se requiere una factura concreta para este ejemplo.</span><span class="sxs-lookup"><span data-stu-id="09f90-200">However, we don’t require a specific invoice for this example.</span></span> <span data-ttu-id="09f90-201">Simplemente se requiere que tenga asignada alguna factura, lo que le permitirá diseñar la página para aplicaciones móviles.</span><span class="sxs-lookup"><span data-stu-id="09f90-201">We just require some invoice assigned to you which is going to allow you to design the mobile page.</span></span> <span data-ttu-id="09f90-202">Las nuevas páginas disponibles se diseñaron específicamente para desarrollar los escenarios móviles para la factura de proveedor.</span><span class="sxs-lookup"><span data-stu-id="09f90-202">The new pages that are available have been designed specifically for developing mobile scenarios for vendor invoice.</span></span> <span data-ttu-id="09f90-203">Por lo tanto, debe usar estas páginas.</span><span class="sxs-lookup"><span data-stu-id="09f90-203">Therefore, you must use these pages.</span></span> <span data-ttu-id="09f90-204">La dirección debe URL ser similar a la URL siguiente y, después de especificarla, la página que se muestra en la ilustración debe aparecer: https://&lt;yourURL&gt;/?cmp=usmf&mi=**VendMobileInvoiceAssignedToMeListPage**&mode=mobile</span><span class="sxs-lookup"><span data-stu-id="09f90-204">The URL should resemble the following URL, and after you enter it, the page that is shown in the illustration must appear: https://&lt;yourURL&gt;/?cmp=usmf&mi=**VendMobileInvoiceAssignedToMeListPage**&mode=mobile</span></span> 

    <span data-ttu-id="09f90-205">[![Página Facturas de proveedor pendientes asignadas a mí](./media/mobile-invoice-approvals01-1024x281.png)](./media/mobile-invoice-approvals01.png)</span><span class="sxs-lookup"><span data-stu-id="09f90-205">[![Pending vendor invoices assigned to me page](./media/mobile-invoice-approvals01-1024x281.png)](./media/mobile-invoice-approvals01.png)</span></span>
    
2.  <span data-ttu-id="09f90-206">Haga clic en el botón **Configuración** (engranaje) en la parte superior derecha de la página y, a continuación, haga clic en **Aplicación móvil**</span><span class="sxs-lookup"><span data-stu-id="09f90-206">Click the **Settings** (gear) button in the upper right of the page, and then click **Mobile app**</span></span>
3.  <span data-ttu-id="09f90-207">Seleccione su espacio de trabajo y haga clic en **Editar**</span><span class="sxs-lookup"><span data-stu-id="09f90-207">Select your workspace and click **Edit**</span></span>
4.  <span data-ttu-id="09f90-208">Haga clic en **Agregar página** para crear la primera página para aplicaciones móviles.</span><span class="sxs-lookup"><span data-stu-id="09f90-208">Click **Add page** to create the first mobile page.</span></span>
5.  <span data-ttu-id="09f90-209">Escriba un nombre, por ejemplo **Mis facturas de proveedor** y una descripción, por ejemplo **Facturas de proveedor que se me asignaron para revisión**.</span><span class="sxs-lookup"><span data-stu-id="09f90-209">Enter a name, such as **My vendor invoices**, and a description, such as **Vendor invoices assigned to me for review**.</span></span>
6.  <span data-ttu-id="09f90-210">Haga clic en **Listo**.</span><span class="sxs-lookup"><span data-stu-id="09f90-210">Click **Done**.</span></span>
7.  <span data-ttu-id="09f90-211">En el diseñador para aplicaciones móviles, en la ficha **Campos**, haga clic en **Seleccionar campos**.</span><span class="sxs-lookup"><span data-stu-id="09f90-211">In the mobile designer, on the **Fields** tab, click **Select fields**.</span></span> <span data-ttu-id="09f90-212">Las columnas de la página de lista deben ser semejantes a la siguiente ilustración.</span><span class="sxs-lookup"><span data-stu-id="09f90-212">The columns on the list page must resemble the following illustration.</span></span> 

    <span data-ttu-id="09f90-213">[![Columnas en la página Facturas de proveedor pendientes asignadas a mí](./media/mobile-invoice-approvals02-1024x117.png)](./media/mobile-invoice-approvals02.png)</span><span class="sxs-lookup"><span data-stu-id="09f90-213">[![Columns on the Pending vendor invoices assigned to me page](./media/mobile-invoice-approvals02-1024x117.png)](./media/mobile-invoice-approvals02.png)</span></span>
    
8.  <span data-ttu-id="09f90-214">Agregue las columnas necesarias de la página con la lista que se deben mostrar a los usuarios en la página para aplicaciones móviles.</span><span class="sxs-lookup"><span data-stu-id="09f90-214">Add the required columns from the list page that must be shown to the users in the mobile page.</span></span> <span data-ttu-id="09f90-215">El orden en que se agrega es el orden en que los campos se mostrarán al usuario final.</span><span class="sxs-lookup"><span data-stu-id="09f90-215">The order in which you add is the order in which the fields will be displayed to the end user.</span></span> <span data-ttu-id="09f90-216">La única forma de cambiar orden de los campos es volviendo a seleccionar todos los campos.</span><span class="sxs-lookup"><span data-stu-id="09f90-216">The only way to change the ordering of the fields will be by re-selecting all the fields.</span></span> <span data-ttu-id="09f90-217">Según los requisitos para esta situación, son necesarias los ocho campos siguientes.</span><span class="sxs-lookup"><span data-stu-id="09f90-217">Based on the requirements for this scenario, the following eight fields are required.</span></span> <span data-ttu-id="09f90-218">Sin embargo, algunos usuarios pueden considerar que ocho campos son demasiada información para tener en un dispositivo móvil.</span><span class="sxs-lookup"><span data-stu-id="09f90-218">However, some users might consider eight fields too much information to have on a mobile device.</span></span> <span data-ttu-id="09f90-219">Por lo tanto, mostraremos solamente los campos más importantes en la vista de lista del móvil.</span><span class="sxs-lookup"><span data-stu-id="09f90-219">Therefore, we will show only the most important fields in the mobile list view.</span></span> <span data-ttu-id="09f90-220">Los campos restantes aparecerán en la vista de detalles que diseñaremos posteriormente.</span><span class="sxs-lookup"><span data-stu-id="09f90-220">The remaining fields will appear in the details view that we will design later.</span></span> <span data-ttu-id="09f90-221">Por ahora, agregaremos los campos siguientes.</span><span class="sxs-lookup"><span data-stu-id="09f90-221">For now, we will add the following fields.</span></span> <span data-ttu-id="09f90-222">Haga clic en el signo más (**+**) en estas columnas para agregar a la página para aplicaciones móviles.</span><span class="sxs-lookup"><span data-stu-id="09f90-222">Click the plus sign (**+**) in these columns to add to the mobile page.</span></span>
    - <span data-ttu-id="09f90-223">Nombre del proveedor</span><span class="sxs-lookup"><span data-stu-id="09f90-223">Vendor name</span></span>
    - <span data-ttu-id="09f90-224">Total de la factura</span><span class="sxs-lookup"><span data-stu-id="09f90-224">Invoice total</span></span>
    - <span data-ttu-id="09f90-225">Cuenta de facturación</span><span class="sxs-lookup"><span data-stu-id="09f90-225">Invoice account</span></span>
    - <span data-ttu-id="09f90-226">Número de factura</span><span class="sxs-lookup"><span data-stu-id="09f90-226">Invoice number</span></span>
    - <span data-ttu-id="09f90-227">Fecha de la factura</span><span class="sxs-lookup"><span data-stu-id="09f90-227">Invoice date</span></span>

  <span data-ttu-id="09f90-228">Después de que se agreguen los campos, la página para aplicaciones móviles debe asemejarse a la siguiente ilustración.</span><span class="sxs-lookup"><span data-stu-id="09f90-228">After the fields are added, the mobile page must resemble the following illustration.</span></span> 
    
   <span data-ttu-id="09f90-229">[![Página después de haber agregado campos](./media/mobile-invoice-approvals03.png)](./media/mobile-invoice-approvals03.png)</span><span class="sxs-lookup"><span data-stu-id="09f90-229">[![Page after fields are added](./media/mobile-invoice-approvals03.png)](./media/mobile-invoice-approvals03.png)</span></span>

9.  <span data-ttu-id="09f90-230">También debe agregar las siguientes columnas ahora, de modo que podamos habilitar acciones de flujo de trabajo posteriormente.</span><span class="sxs-lookup"><span data-stu-id="09f90-230">You must also add the following columns now, so that we can enable workflow actions later.</span></span>
    - <span data-ttu-id="09f90-231">Mostrar tarea completa</span><span class="sxs-lookup"><span data-stu-id="09f90-231">Show complete task</span></span>
    - <span data-ttu-id="09f90-232">Muestra tarea de delegado</span><span class="sxs-lookup"><span data-stu-id="09f90-232">Show delegate task</span></span>
    - <span data-ttu-id="09f90-233">Mostar la tarea de recuperación</span><span class="sxs-lookup"><span data-stu-id="09f90-233">Show recall task</span></span>
    - <span data-ttu-id="09f90-234">Mostrar tarea de rechazo</span><span class="sxs-lookup"><span data-stu-id="09f90-234">Show reject task</span></span>
    - <span data-ttu-id="09f90-235">Mostrar tarea de finalización de solicitud</span><span class="sxs-lookup"><span data-stu-id="09f90-235">Show request completion task</span></span>
    - <span data-ttu-id="09f90-236">Mostrar tarea de reenvío</span><span class="sxs-lookup"><span data-stu-id="09f90-236">Show resubmit task</span></span>

10. <span data-ttu-id="09f90-237">Haga clic en **Listo** para salir del modo de edición.</span><span class="sxs-lookup"><span data-stu-id="09f90-237">Click **Done** to exit edit mode.</span></span>
11. <span data-ttu-id="09f90-238">Haga clic en **Atrás** y, a continuación, **Listo** para salir del espacio de trabajo</span><span class="sxs-lookup"><span data-stu-id="09f90-238">Click **Back** and then **Done** to exit the workspace</span></span>
12. <span data-ttu-id="09f90-239">Haga clic en **Publicar espacio de trabajo** para guardar el trabajo.</span><span class="sxs-lookup"><span data-stu-id="09f90-239">Click **Publish workspace** to save your work.</span></span>
13. <span data-ttu-id="09f90-240">Habilite **Mostrar total factura en lista de facturas de proveedor pendiente** en los parámetros de proveedores desde **Factura**.</span><span class="sxs-lookup"><span data-stu-id="09f90-240">Enable **Display invoice total on pending vendor invoices list** in accounts payable parameters form under **Invoice**.</span></span> <span data-ttu-id="09f90-241">Tenga en cuenta que, al habilitar este parámetro, los totales de las facturas se calcularán para mostrarse en la página de la lista de facturas de proveedor pendientes.</span><span class="sxs-lookup"><span data-stu-id="09f90-241">Note that, only by enabling this parameter, invoice totals will be calculated to be displayed on the pending vendor invoices list page.</span></span> <span data-ttu-id="09f90-242">Esta es una nueva capacidad que forma parte de la revisión 3208224 del requisito previo.</span><span class="sxs-lookup"><span data-stu-id="09f90-242">This is a new capability as part of the pre-requisite hot fix 3208224.</span></span>

### <a name="vendor-invoice-details"></a><span data-ttu-id="09f90-243">Detalles de la factura de proveedor</span><span class="sxs-lookup"><span data-stu-id="09f90-243">Vendor invoice details</span></span>

<span data-ttu-id="09f90-244">Para diseñar la página de detalles de la factura para móvil, use la página **VendMobileInvoiceHeaderDetails**.</span><span class="sxs-lookup"><span data-stu-id="09f90-244">To design the invoice details page for mobile, use the **VendMobileInvoiceHeaderDetails** page.</span></span> <span data-ttu-id="09f90-245">Tenga en cuenta que, en función del número de facturas que tiene en el sistema, esta página muestra la factura más antigua (la factura que se creó primero).</span><span class="sxs-lookup"><span data-stu-id="09f90-245">Note that, depending on the number of invoices that you have in your system, this page shows the oldest invoice (the invoice that was created first).</span></span> <span data-ttu-id="09f90-246">Para buscar una factura específica, utilice el filtro a la izquierda.</span><span class="sxs-lookup"><span data-stu-id="09f90-246">To find a specific invoice, you can use the filter on the left.</span></span> <span data-ttu-id="09f90-247">Sin embargo, no se requiere una factura concreta para este ejemplo.</span><span class="sxs-lookup"><span data-stu-id="09f90-247">However, we don’t require a specific invoice for this example.</span></span> <span data-ttu-id="09f90-248">Simplemente requerimos algunos datos de la factura para que podamos diseñar la página para dispositivos móviles.</span><span class="sxs-lookup"><span data-stu-id="09f90-248">We just require some invoice data so that we can design the mobile page.</span></span> 

<span data-ttu-id="09f90-249">[![Página del flujo de trabajo](./media/mobile-invoice-approvals04-1024x425.png)](./media/mobile-invoice-approvals04.png)</span><span class="sxs-lookup"><span data-stu-id="09f90-249">[![Workflow page](./media/mobile-invoice-approvals04-1024x425.png)](./media/mobile-invoice-approvals04.png)</span></span>

1. <span data-ttu-id="09f90-250">En la dirección URL, sustituya el nombre del elemento de menú con **VendMobileInvoiceHeaderDetails** para abrir el formulario</span><span class="sxs-lookup"><span data-stu-id="09f90-250">In the URL, replace the name of the menu item with **VendMobileInvoiceHeaderDetails** to open the form</span></span>

2. <span data-ttu-id="09f90-251">Abra el diseñador para aplicaciones móviles desde el botón **Configuración** (engranaje).</span><span class="sxs-lookup"><span data-stu-id="09f90-251">Open the mobile designer from the **Settings** (gear) button.</span></span>

3. <span data-ttu-id="09f90-252">Haga clic en el botón **Editar** para iniciar el modo de edición en el espacio de trabajo.</span><span class="sxs-lookup"><span data-stu-id="09f90-252">Click the **Edit** button to start edit mode in the workspace.</span></span>

4. <span data-ttu-id="09f90-253">Seleccione la página **Mis facturas de proveedor** que ha creado antes y haga clic en **Editar**.</span><span class="sxs-lookup"><span data-stu-id="09f90-253">Select the **My vendor invoices** page that you created earlier, and then click **Edit**.</span></span>

5. <span data-ttu-id="09f90-254">En los la ficha **Campos**, haga clic en el encabezado de columna **Cuadrícula**.</span><span class="sxs-lookup"><span data-stu-id="09f90-254">On the **Fields** tab, click the **Grid** column heading.</span></span>

6. <span data-ttu-id="09f90-255">Haga clic en **Propiedades &gt; Agregar página**.</span><span class="sxs-lookup"><span data-stu-id="09f90-255">Click **Properties &gt; Add page**.</span></span> <span data-ttu-id="09f90-256">**Nota:** Al hacer clic en el encabezado de **Cuadrícula** y agregar una página, la relación con la página de detalles se establece automáticamente.</span><span class="sxs-lookup"><span data-stu-id="09f90-256">**Note:** When you click the **Grid** heading and add a page, the relationship with the details page is established automatically.</span></span>

7. <span data-ttu-id="09f90-257">Especifique un título de la página, por ejemplo **Detalles de la factura** y una descripción como **Ver detalles de línea y encabezado de la factura**.</span><span class="sxs-lookup"><span data-stu-id="09f90-257">Enter a page title, such as **Invoice details**, and a description, such as **View invoice header and line details**.</span></span>

8. <span data-ttu-id="09f90-258">Haga clic en **Seleccionar campos**.</span><span class="sxs-lookup"><span data-stu-id="09f90-258">Click **Select fields**.</span></span> <span data-ttu-id="09f90-259">Tenga en cuenta que el orden en que se agrega es el orden en que los campos se mostrarán al usuario final.</span><span class="sxs-lookup"><span data-stu-id="09f90-259">Note that, the order in which you add is the order in which the fields will be displayed to the end user.</span></span> <span data-ttu-id="09f90-260">La única forma de cambiar orden de los campos es volviendo a seleccionar todos los campos.</span><span class="sxs-lookup"><span data-stu-id="09f90-260">The only way to change the ordering of the fields will be by re-selecting all the fields.</span></span> 

9. <span data-ttu-id="09f90-261">Agregue los siguientes campos desde el encabezado, según los requisitos para esta situación:</span><span class="sxs-lookup"><span data-stu-id="09f90-261">Add the following fields from the header, based on the requirements for this scenario:</span></span>
   - <span data-ttu-id="09f90-262">Nombre del proveedor</span><span class="sxs-lookup"><span data-stu-id="09f90-262">Vendor name</span></span>
   - <span data-ttu-id="09f90-263">Total de la factura</span><span class="sxs-lookup"><span data-stu-id="09f90-263">Invoice total</span></span>
   - <span data-ttu-id="09f90-264">Cuenta de facturación</span><span class="sxs-lookup"><span data-stu-id="09f90-264">Invoice account</span></span>
   - <span data-ttu-id="09f90-265">Número de factura</span><span class="sxs-lookup"><span data-stu-id="09f90-265">Invoice number</span></span>
   - <span data-ttu-id="09f90-266">Fecha de la factura</span><span class="sxs-lookup"><span data-stu-id="09f90-266">Invoice date</span></span>
   - <span data-ttu-id="09f90-267">Descripción de factura</span><span class="sxs-lookup"><span data-stu-id="09f90-267">Invoice description</span></span>
   - <span data-ttu-id="09f90-268">Fecha de vencimiento</span><span class="sxs-lookup"><span data-stu-id="09f90-268">Due date</span></span>
   - <span data-ttu-id="09f90-269">Divisa de la factura</span><span class="sxs-lookup"><span data-stu-id="09f90-269">Invoice currency</span></span>

10. <span data-ttu-id="09f90-270">Agregue los siguientes campos en la cuadrícula de las líneas en la página:</span><span class="sxs-lookup"><span data-stu-id="09f90-270">Add the following fields from the lines grid on the page:</span></span>
    - <span data-ttu-id="09f90-271">Categoría de compras</span><span class="sxs-lookup"><span data-stu-id="09f90-271">Procurement category</span></span>
    - <span data-ttu-id="09f90-272">Cantidad</span><span class="sxs-lookup"><span data-stu-id="09f90-272">Quantity</span></span>
    - <span data-ttu-id="09f90-273">Precio unitario</span><span class="sxs-lookup"><span data-stu-id="09f90-273">Unit price</span></span>
    - <span data-ttu-id="09f90-274">Importe neto de línea</span><span class="sxs-lookup"><span data-stu-id="09f90-274">Line net amount</span></span>
    - <span data-ttu-id="09f90-275">Importe de la declaración de IRPF</span><span class="sxs-lookup"><span data-stu-id="09f90-275">1099 amount</span></span>

11. <span data-ttu-id="09f90-276">Después de agregar todos los campos de los dos pasos anteriores, haga clic en **Listo**.</span><span class="sxs-lookup"><span data-stu-id="09f90-276">After all the fields from the previous two steps have been added, click **Done**.</span></span> <span data-ttu-id="09f90-277">La página deben asemejarse a la siguiente ilustración.</span><span class="sxs-lookup"><span data-stu-id="09f90-277">The page must resemble the following illustration.</span></span>
    
    <span data-ttu-id="09f90-278">[![Página después de haber agregado campos](./media/mobile-invoice-approvals05.png)](./media/mobile-invoice-approvals05.png)</span><span class="sxs-lookup"><span data-stu-id="09f90-278">[![Page after fields are added](./media/mobile-invoice-approvals05.png)](./media/mobile-invoice-approvals05.png)</span></span>

12. <span data-ttu-id="09f90-279">Haga clic en **Listo** para salir del modo de edición.</span><span class="sxs-lookup"><span data-stu-id="09f90-279">Click **Done** to exit edit mode.</span></span>

13. <span data-ttu-id="09f90-280">Haga clic en **Atrás** y, a continuación, **Listo** para salir del espacio de trabajo</span><span class="sxs-lookup"><span data-stu-id="09f90-280">Click **Back** and then **Done** to exit the workspace</span></span>

14. <span data-ttu-id="09f90-281">Haga clic en **Publicar espacio de trabajo** para guardar el trabajo</span><span class="sxs-lookup"><span data-stu-id="09f90-281">Click **Publish workspace** to save your work</span></span>

### <a name="workflow-actions"></a><span data-ttu-id="09f90-282">Acciones de flujo de trabajo</span><span class="sxs-lookup"><span data-stu-id="09f90-282">Workflow actions</span></span>

<span data-ttu-id="09f90-283">Para agregar acciones de flujo de trabajo, use la página **VendMobileInvoiceHeaderDetails**.</span><span class="sxs-lookup"><span data-stu-id="09f90-283">To add workflow actions, use the **VendMobileInvoiceHeaderDetails** page.</span></span> <span data-ttu-id="09f90-284">Para abrir esta página, reemplace el nombre del elemento de menú de la dirección URL, como lo hizo anteriormente.</span><span class="sxs-lookup"><span data-stu-id="09f90-284">To open this page, replace the name of the menu item in the URL, as you did earlier.</span></span> <span data-ttu-id="09f90-285">Después, abra el diseñador para aplicaciones móviles desde el botón **Configuración** (engranaje).</span><span class="sxs-lookup"><span data-stu-id="09f90-285">Then open the mobile designer from the **Settings** (gear) button.</span></span> <span data-ttu-id="09f90-286">Siga estos pasos para agregar acciones de flujo de trabajo en la página de detalles.</span><span class="sxs-lookup"><span data-stu-id="09f90-286">Follow these steps to add workflow actions on the details page.</span></span> <span data-ttu-id="09f90-287">Debe tener facturas asignadas y que tengan un estado apropiado para que las acciones del flujo de trabajo para las que va a realizar el diseño estén disponibles.</span><span class="sxs-lookup"><span data-stu-id="09f90-287">You must have invoices assigned to you that are in the appropriate state to make the workflow actions available to you that you are going to design for.</span></span>

#### <a name="record-workflow-actions"></a><span data-ttu-id="09f90-288">Registrar acciones de flujo de trabajo</span><span class="sxs-lookup"><span data-stu-id="09f90-288">Record workflow actions</span></span>
1.  <span data-ttu-id="09f90-289">Haga clic en el botón **Editar** para iniciar el modo de edición en el espacio de trabajo.</span><span class="sxs-lookup"><span data-stu-id="09f90-289">Click the **Edit** button to start edit mode in the workspace.</span></span>
2.  <span data-ttu-id="09f90-290">Seleccione la página **Mis facturas de proveedor** que ha creado antes y haga clic en **Editar**.</span><span class="sxs-lookup"><span data-stu-id="09f90-290">Select the **Invoice details** page that you created earlier, and then click **Edit**.</span></span>
3.  <span data-ttu-id="09f90-291">En la ficha **Acciones**, haga clic en **Agregar acción**.</span><span class="sxs-lookup"><span data-stu-id="09f90-291">On the **Actions** tab, click **Add action**.</span></span>
4.  <span data-ttu-id="09f90-292">Especifique un título de acción, como **Aprobar** y una descripción como **Aprobar factura**.</span><span class="sxs-lookup"><span data-stu-id="09f90-292">Enter an action title, such as **Approve**, and a description, such as **Approve invoice**.</span></span> <span data-ttu-id="09f90-293">Tenga en cuenta que el título de la acción que escriba aquí se convierte en el nombre de la acción que se muestra al usuario en la aplicación móvil.</span><span class="sxs-lookup"><span data-stu-id="09f90-293">Note that the action title that you enter here becomes the name of the action that is shown to the user in the mobile app.</span></span>
5.  <span data-ttu-id="09f90-294">Haga clic en **Listo**.</span><span class="sxs-lookup"><span data-stu-id="09f90-294">Click **Done**.</span></span>
6.  <span data-ttu-id="09f90-295">Haga clic en **Seleccionar campos**.</span><span class="sxs-lookup"><span data-stu-id="09f90-295">Click **Select fields**.</span></span>
7.  <span data-ttu-id="09f90-296">Realice el proceso del flujo de trabajo en la página **VendMobileInvoiceHeaderDetails** y complete la acción que se quería registrar.</span><span class="sxs-lookup"><span data-stu-id="09f90-296">Go through the workflow process on the **VendMobileInvoiceHeaderDetails** page, and complete the action that you wanted to record.</span></span> <span data-ttu-id="09f90-297">Asegúrese de especificar los comentarios del flujo de trabajo durante este proceso, de forma que se incluya un campo de comentarios en la experiencia móvil.</span><span class="sxs-lookup"><span data-stu-id="09f90-297">Make sure that you enter workflow comments during this process, so that a comments field is also included in the mobile experience.</span></span>
8.  <span data-ttu-id="09f90-298">Una vez que se ejecute la acción del flujo de trabajo, haga clic en **Listo** para completar la tarea Seleccionar campos.</span><span class="sxs-lookup"><span data-stu-id="09f90-298">After the workflow action is run, click **Done** to complete the Select fields task.</span></span>
9.  <span data-ttu-id="09f90-299">Haga clic en **Listo** para salir del modo de edición.</span><span class="sxs-lookup"><span data-stu-id="09f90-299">Click **Done** to exit edit mode.</span></span>
10. <span data-ttu-id="09f90-300">Haga clic en **Atrás** y, a continuación, **Listo** para salir del espacio de trabajo</span><span class="sxs-lookup"><span data-stu-id="09f90-300">Click **Back** and then **Done** to exit the workspace</span></span>
11. <span data-ttu-id="09f90-301">Haga clic en **Publicar espacio de trabajo** para guardar el trabajo</span><span class="sxs-lookup"><span data-stu-id="09f90-301">Click **Publish workspace** to save your work</span></span>
12. <span data-ttu-id="09f90-302">Repita los pasos anteriores para registrar todas las acciones del flujo de trabajo necesarias.</span><span class="sxs-lookup"><span data-stu-id="09f90-302">Repeat the previous steps to record all the required workflow actions.</span></span> 

#### <a name="create-a-js-file"></a><span data-ttu-id="09f90-303">Crear un archivo .js</span><span class="sxs-lookup"><span data-stu-id="09f90-303">Create a .js file</span></span>
1. <span data-ttu-id="09f90-304">Abra el Bloc de notas o Microsoft Visual Studio, y pegue el código siguiente.</span><span class="sxs-lookup"><span data-stu-id="09f90-304">Open Notepad or Microsoft Visual Studio, and paste the following code.</span></span> <span data-ttu-id="09f90-305">Guarde el archivo como archivo .js.</span><span class="sxs-lookup"><span data-stu-id="09f90-305">Save the file as a .js file.</span></span> <span data-ttu-id="09f90-306">Este código hace lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="09f90-306">This code does the following:</span></span>
    - <span data-ttu-id="09f90-307">Oculta las columnas adicionales relacionadas con el flujo de trabajo adicionales que agregamos anteriormente en la página de la lista para dispositivos móviles.</span><span class="sxs-lookup"><span data-stu-id="09f90-307">It hides the extra workflow-related columns that we added earlier on the mobile list page.</span></span> <span data-ttu-id="09f90-308">Agregamos estas columnas de modo que la aplicación tenga información en contexto y se pueda ir al paso siguiente.</span><span class="sxs-lookup"><span data-stu-id="09f90-308">We added these columns so that the app has that information in context and can do the next step.</span></span>
    - <span data-ttu-id="09f90-309">Según el paso del flujo de trabajo que está activo, aplica la lógica para mostrar solo esas acciones.</span><span class="sxs-lookup"><span data-stu-id="09f90-309">Based on the workflow step that is active, it applies logic to show only those actions.</span></span>

> [!NOTE]
> <span data-ttu-id="09f90-310">El nombre de las páginas y otros controles del código de JS deberían ser los mismos que los nombres en el espacio de trabajo.</span><span class="sxs-lookup"><span data-stu-id="09f90-310">The name of the pages and other controls in the code must be the same as the names in the workspace.</span></span>

    function main(metadataService, dataService, cacheService, $q) {
           return {
               appInit: function (appMetadata) {
                   // Hide controls that need to be present, but not visible
                   metadataService.configureControl('My-vendor-invoices', 'ShowAccept', { hidden: true });
                   metadataService.configureControl('My-vendor-invoices', 'ShowApprove', { hidden: true });
                   metadataService.configureControl('My-vendor-invoices', 'ShowReject', { hidden: true });
                   metadataService.configureControl('My-vendor-invoices', 'ShowDelegate', { hidden: true });
                   metadataService.configureControl('My-vendor-invoices', 'ShowRequestChange', { hidden: true });
                 metadataService.configureControl('My-vendor-invoices', 'ShowRecall', { hidden: true });
                   metadataService.configureControl('My-vendor-invoices', 'ShowComplete', { hidden: true });
               metadataService.configureControl('My-vendor-invoices', 'ShowResubmit', { hidden: true });
               },
               pageInit: function (pageMetadata, params) {
        if (pageMetadata.Name == 'Invoice-details') {
                       // Show/hide workflow actions based on workflow step
                       metadataService.configureAction('Accept', { visible: true });
                       metadataService.configureAction('Approve', { visible: true });
                       metadataService.configureAction('Reject', { visible: true });
                       metadataService.configureAction('Delegate', { visible: true });
                       metadataService.configureAction('Request-change', { visible: true });
                       metadataService.configureAction('Recall', { visible: true });
                       metadataService.configureAction('Complete', { visible: true });
                       metadataService.configureAction('Resubmit', { visible: true });

                       var entityContextParts = params.pageContext.split(':');
                       var data = dataService.getEntityData(entityContextParts[0], entityContextParts[1]);

                       var acceptControl = data.getPropertyValue('VendInvoiceInfoTable/showAccept');
                       var approveControl = data.getPropertyValue('VendInvoiceInfoTable/showApprove');
                       var rejectControl = data.getPropertyValue('VendInvoiceInfoTable/showReject');
                       var delegateControl = data.getPropertyValue('VendInvoiceInfoTable/showDelegate');
                       var requestChangeControl = data.getPropertyValue('VendInvoiceInfoTable/showRequestChange');
                       var recallControl = data.getPropertyValue('VendInvoiceInfoTable/showRecall');
                       var completeControl = data.getPropertyValue('VendInvoiceInfoTable/showComplete');
                       var resubmitControl = data.getPropertyValue('VendInvoiceInfoTable/showResubmit');

                       var showAcceptControl = Boolean(acceptControl == 1);
                       var showApproveControl = Boolean(approveControl == 1);
                       var showRejectControl = Boolean(rejectControl == 1);
                      var showDelegateControl = Boolean(delegateControl == 1);
                       var showRequestChangeControl = Boolean(requestChangeControl == 1);
                       var showRecallControl = Boolean(recallControl == 1);
                       var showCompleteControl = Boolean(completeControl == 1);
                       var showResubmitControl = Boolean(resubmitControl == 1);

                       metadataService.configureAction('Accept', { visible: showAcceptControl });
                       metadataService.configureAction('Approve', { visible: showApproveControl });
                       metadataService.configureAction('Reject', { visible: showRejectControl });
                       metadataService.configureAction('Delegate', { visible: showDelegateControl });
                       metadataService.configureAction('Request-change', { visible: showRequestChangeControl });
                       metadataService.configureAction('Recall', { visible: showRecallControl });
                       metadataService.configureAction('Complete', { visible: showCompleteControl });
                     metadataService.configureAction('Resubmit', { visible: showResubmitControl });
                   }
                 },
           };
        }

2.  <span data-ttu-id="09f90-311">Cargar el archivo del código en el espacio de trabajo seleccionando la ficha **Lógica**</span><span class="sxs-lookup"><span data-stu-id="09f90-311">Upload the code file to the workspace by selecting the **Logic** tab</span></span>
3.  <span data-ttu-id="09f90-312">Haga clic en **Listo** para salir del modo de edición.</span><span class="sxs-lookup"><span data-stu-id="09f90-312">Click **Done** to exit edit mode.</span></span>
4.  <span data-ttu-id="09f90-313">Haga clic en **Atrás** y, a continuación, **Listo** para salir del espacio de trabajo</span><span class="sxs-lookup"><span data-stu-id="09f90-313">Click **Back** and then **Done** to exit the workspace</span></span>
5.  <span data-ttu-id="09f90-314">Haga clic en **Publicar espacio de trabajo** para guardar el trabajo</span><span class="sxs-lookup"><span data-stu-id="09f90-314">Click **Publish workspace** to save your work</span></span>

### <a name="vendor-invoice-attachments"></a><span data-ttu-id="09f90-315">Datos adjuntos de la factura de proveedor</span><span class="sxs-lookup"><span data-stu-id="09f90-315">Vendor invoice attachments</span></span>

1. <span data-ttu-id="09f90-316">Haga clic en el botón **Configuración** (engranaje) en la parte superior derecha de la página y, a continuación, haga clic en **Aplicación móvil**</span><span class="sxs-lookup"><span data-stu-id="09f90-316">Click the **Settings** (gear) button in the upper right of the page, and then click **Mobile app**</span></span>

2. <span data-ttu-id="09f90-317">Haga clic en el botón **Editar** para iniciar el modo de edición en el espacio de trabajo.</span><span class="sxs-lookup"><span data-stu-id="09f90-317">Click the **Edit** button to start edit mode in the workspace.</span></span>

3. <span data-ttu-id="09f90-318">Seleccione la página <strong>Detalles de la factura \*\*que ha creado antes y haga clic en \*\*Editar</strong>.</span><span class="sxs-lookup"><span data-stu-id="09f90-318">Select the <strong>Invoice details \*\*page that you created earlier, and then click \*\*Edit</strong>.</span></span>

4. <span data-ttu-id="09f90-319">Establezca la opción **Administración de documentos** en **Sí** como se indica a continuación.</span><span class="sxs-lookup"><span data-stu-id="09f90-319">Set the **Document management** option to **Yes** as shown below.</span></span> <span data-ttu-id="09f90-320">**Nota:** Si no hay requisitos para mostrar los datos adjuntos en el dispositivo móvil, puede dejar esta opción establecida en **No**, que es la configuración predeterminada.</span><span class="sxs-lookup"><span data-stu-id="09f90-320">**Note:** If there are no requirements to show attachments on the mobile device, you can leave this option set to **No**, which is the default setting.</span></span>
   
   ![Administración de documentos](./media/docmanagement-216x300.png)

5. <span data-ttu-id="09f90-322">Haga clic en **Listo** para salir del modo de edición.</span><span class="sxs-lookup"><span data-stu-id="09f90-322">Click **Done** to exit edit mode.</span></span>

6. <span data-ttu-id="09f90-323">Haga clic en **Atrás** y, a continuación, **Listo** para salir del espacio de trabajo</span><span class="sxs-lookup"><span data-stu-id="09f90-323">Click **Back** and then **Done** to exit the workspace</span></span>

7. <span data-ttu-id="09f90-324">Haga clic en **Publicar espacio de trabajo** para guardar el trabajo</span><span class="sxs-lookup"><span data-stu-id="09f90-324">Click **Publish workspace** to save your work</span></span>

### <a name="vendor-invoice-line-distributions"></a><span data-ttu-id="09f90-325">Distribuciones de línea de la factura de proveedor</span><span class="sxs-lookup"><span data-stu-id="09f90-325">Vendor invoice line distributions</span></span>

<span data-ttu-id="09f90-326">Los requisitos para este escenario confirman que solo habrá distribuciones a nivel de línea y que las facturas serán siempre de una línea.</span><span class="sxs-lookup"><span data-stu-id="09f90-326">The requirements for this scenario confirm that there will be only line-level distributions, and that an invoice will always have only one line.</span></span> <span data-ttu-id="09f90-327">Puesto que este escenario es sencillo, la experiencia del usuario en el dispositivo móvil también debe ser lo suficientemente sencilla para que el usuario no tenga que buscar en profundidad para ver las distribuciones.</span><span class="sxs-lookup"><span data-stu-id="09f90-327">Because this scenario is simple, the user experience on the mobile device must also be simple enough that the user doesn’t have to drill down several levels to view the distributions.</span></span> <span data-ttu-id="09f90-328">Las facturas de proveedor incluyen la opción para mostrar todas las distribuciones del encabezado de la factura.</span><span class="sxs-lookup"><span data-stu-id="09f90-328">Vendor invoices include the option of showing all distributions from the invoice header.</span></span> <span data-ttu-id="09f90-329">Esta experiencia es lo que necesitamos para el escenario de dispositivos móviles.</span><span class="sxs-lookup"><span data-stu-id="09f90-329">This experience is what we need for the mobile scenario.</span></span> <span data-ttu-id="09f90-330">Por lo tanto, utilizaremos la página **VendMobileInvoiceAllDistributionTree** para diseñar esta parte del escenario móvil.</span><span class="sxs-lookup"><span data-stu-id="09f90-330">Therefore, we will use the **VendMobileInvoiceAllDistributionTree** page to design this part of the mobile scenario.</span></span> 

> [!NOTE] 
> <span data-ttu-id="09f90-331">Conocer los requisitos nos ayuda a decidir qué página determinada se va utilizar y exactamente cómo optimizar la experiencia móvil del usuario cuando diseñamos el escenario.</span><span class="sxs-lookup"><span data-stu-id="09f90-331">Knowing the requirements helps us decide which specific page to use and how exactly to optimize the mobile experience for the user when we design the scenario.</span></span> <span data-ttu-id="09f90-332">En el segundo escenario, utilizaremos una página diferente para mostrar las distribuciones, ya los requisitos para esa situación son diferentes.</span><span class="sxs-lookup"><span data-stu-id="09f90-332">In the second scenario, we will use a different page to show the distributions, because the requirements for that scenario differ.</span></span>

1.  <span data-ttu-id="09f90-333">En la dirección URL, reemplace el nombre del elemento de menú tal como hizo antes.</span><span class="sxs-lookup"><span data-stu-id="09f90-333">In the URL, replace the name of the menu item, as you did before.</span></span> <span data-ttu-id="09f90-334">La página que aparece debe asemejarse a la siguiente ilustración.</span><span class="sxs-lookup"><span data-stu-id="09f90-334">The page that appears should resemble the following illustration.</span></span>

<span data-ttu-id="09f90-335">[![Página de todas las distribuciones](./media/mobile-invoice-approvals06.png)](./media/mobile-invoice-approvals06.png)</span><span class="sxs-lookup"><span data-stu-id="09f90-335">[![All distributions page](./media/mobile-invoice-approvals06.png)](./media/mobile-invoice-approvals06.png)</span></span>

2.  <span data-ttu-id="09f90-336">Abra el diseñador para aplicaciones móviles desde el botón **Configuración** (engranaje).</span><span class="sxs-lookup"><span data-stu-id="09f90-336">Open the mobile designer from the **Settings** (gear) button.</span></span>

3.  <span data-ttu-id="09f90-337">Haga clic en el botón **Editar** para iniciar el modo de edición en el espacio de trabajo.</span><span class="sxs-lookup"><span data-stu-id="09f90-337">Click the **Edit** button to start edit mode in the workspace.</span></span> <span data-ttu-id="09f90-338">**Nota:** Verá dos nuevas páginas que se han creado automáticamente.</span><span class="sxs-lookup"><span data-stu-id="09f90-338">**Note:** You will see that two new pages were created automatically.</span></span> <span data-ttu-id="09f90-339">El sistema crea estas páginas porque ha activado la gestión de documentos en la sección anterior.</span><span class="sxs-lookup"><span data-stu-id="09f90-339">The system creates these pages, because you turned on document management in the previous section.</span></span> <span data-ttu-id="09f90-340">Puede omitir estas páginas nuevas.</span><span class="sxs-lookup"><span data-stu-id="09f90-340">You can ignore these new pages.</span></span>

4.  <span data-ttu-id="09f90-341">Haga clic en **Agregar página**.</span><span class="sxs-lookup"><span data-stu-id="09f90-341">Click **Add page**.</span></span>

5.  <span data-ttu-id="09f90-342">Especifique un título para la página como **Ver contabilidad** y una descripción como **Ver contabilidad para la factura**.</span><span class="sxs-lookup"><span data-stu-id="09f90-342">Enter a page title, such as **View accounting**, and a description, such as **View accounting for the invoice**.</span></span>

6.  <span data-ttu-id="09f90-343">Haga clic en **Listo**.</span><span class="sxs-lookup"><span data-stu-id="09f90-343">Click **Done**.</span></span>

7.  <span data-ttu-id="09f90-344">En la ficha **Campos**, haga clic en **Seleccionar campos**, seleccione los siguientes campos de la página de las distribuciones, y haga clic en **Listo**:</span><span class="sxs-lookup"><span data-stu-id="09f90-344">On the **Fields** tab, click **Select fields**, select the following fields from the distributions page, and then click **Done**:</span></span>
    1.  <span data-ttu-id="09f90-345">Importe</span><span class="sxs-lookup"><span data-stu-id="09f90-345">Amount</span></span>
    2.  <span data-ttu-id="09f90-346">Divisa</span><span class="sxs-lookup"><span data-stu-id="09f90-346">Currency</span></span>
    3.  <span data-ttu-id="09f90-347">Cuenta contable</span><span class="sxs-lookup"><span data-stu-id="09f90-347">Ledger account</span></span>

    > [!NOTE] 
    > <span data-ttu-id="09f90-348">No seleccionamos la columna **Descripción** en la cuadrícula de las distribuciones debido a que los requisitos para este escenario confirmaron que el precio total es el único importe para el que habrá distribuciones.</span><span class="sxs-lookup"><span data-stu-id="09f90-348">We didn’t select the **Description** column from the distributions grid, because the requirements for this scenario confirmed that the extended price is the only amount that there will be distributions for.</span></span> <span data-ttu-id="09f90-349">Por tanto, el usuario no necesitará otro campo para determinar el tipo de importe para el que es la distribución.</span><span class="sxs-lookup"><span data-stu-id="09f90-349">Therefore, the user won’t require another field to determine the amount type that the distribution is for.</span></span> <span data-ttu-id="09f90-350">Sin embargo, en el escenario siguiente, **utilizaremos** esta información porque los requisitos para esa situación especifican que otros tipos de importe tienen distribuciones (por ejemplo, impuestos).</span><span class="sxs-lookup"><span data-stu-id="09f90-350">However, in the next scenario, we **will** use this information, because the requirements for that scenario specify that other amount types have distributions (for example, sales tax).</span></span>

8.  <span data-ttu-id="09f90-351">Haga clic en **Listo** para salir del modo de edición.</span><span class="sxs-lookup"><span data-stu-id="09f90-351">Click **Done** to exit edit mode.</span></span>

9.  <span data-ttu-id="09f90-352">Haga clic en **Atrás** y, a continuación, **Listo** para salir del espacio de trabajo</span><span class="sxs-lookup"><span data-stu-id="09f90-352">Click **Back** and then **Done** to exit the workspace</span></span>

10. <span data-ttu-id="09f90-353">Haga clic en **Publicar espacio de trabajo** para guardar el trabajo</span><span class="sxs-lookup"><span data-stu-id="09f90-353">Click **Publish workspace** to save your work</span></span>

> [!NOTE] 
> <span data-ttu-id="09f90-354">Nota: La página para dispositivos móviles **Ver contabilidad** no está vinculada actualmente a ninguna página para dispositivos móviles que hemos diseñado hasta el momento.</span><span class="sxs-lookup"><span data-stu-id="09f90-354">The **View accounting** mobile page isn’t currently linked to any of the mobile pages that we have designed so far.</span></span> <span data-ttu-id="09f90-355">Dado que el usuario debe poder navegar a la página **Ver contabilidad** desde la página **Detalles de la factura** en el dispositivo móvil, debemos proporcionar navegación desde la página **Detalles de la factura** hasta la página **Ver contabilidad**.</span><span class="sxs-lookup"><span data-stu-id="09f90-355">Because the user should be able to navigate to the **View accounting** page from the **Invoice details** page on the mobile device, we must provide navigation from the **Invoice details** page to the **View accounting** page.</span></span> <span data-ttu-id="09f90-356">Establecemos esta navegación mediante el uso de lógica JavaScript adicional.</span><span class="sxs-lookup"><span data-stu-id="09f90-356">We establish this navigation by using additional logic via JavaScript.</span></span>

1.  <span data-ttu-id="09f90-357">Abre el archivo .js que ha creado anteriormente y agregue las líneas que se resaltan en el código siguiente.</span><span class="sxs-lookup"><span data-stu-id="09f90-357">Open the .js file that you created earlier, and add the lines that are highlighted in the following code.</span></span> <span data-ttu-id="09f90-358">Este código hace dos cosas:</span><span class="sxs-lookup"><span data-stu-id="09f90-358">This code does two things:</span></span>
    1.  <span data-ttu-id="09f90-359">Ayuda a garantizar que los usuarios no pueden navegar directamente desde el espacio de trabajo a la página **Ver contabilidad**.</span><span class="sxs-lookup"><span data-stu-id="09f90-359">It helps guarantee that users can’t navigate directly from the workspace to the **View accounting** page.</span></span>
    2.  <span data-ttu-id="09f90-360">Establece un control de navegación desde la página **Detalles de la factura** hasta la página **Ver contabilidad**.</span><span class="sxs-lookup"><span data-stu-id="09f90-360">It establishes a navigation control from the **Invoice details** page to the **View accounting** page.</span></span>

> [!NOTE] 
> <span data-ttu-id="09f90-361">El nombre de las páginas y otros controles del código de JS deberían ser los mismos que los nombres en el espacio de trabajo.</span><span class="sxs-lookup"><span data-stu-id="09f90-361">The name of the pages and other controls in the code must be the same as the names in the workspace.</span></span>

    function main(metadataService, dataService, cacheService, $q) {
           return {
               appInit: function (appMetadata) {
                   // Hide controls that need to be present, but not visible
                   metadataService.configureControl('My-vendor-invoices', 'ShowAccept', { hidden: true });
                   metadataService.configureControl('My-vendor-invoices', 'ShowApprove', { hidden: true });
                   metadataService.configureControl('My-vendor-invoices', 'ShowReject', { hidden: true });
                   metadataService.configureControl('My-vendor-invoices', 'ShowDelegate', { hidden: true });
                   metadataService.configureControl('My-vendor-invoices', 'ShowRequestChange', { hidden: true });
                 metadataService.configureControl('My-vendor-invoices', 'ShowRecall', { hidden: true });
                   metadataService.configureControl('My-vendor-invoices', 'ShowComplete', { hidden: true });
               metadataService.configureControl('My-vendor-invoices', 'ShowResubmit', { hidden: true });
                   // Hide pages not applicable for root navigation
                   metadataService.hideNavigation('View-accounting');
                   //Link to view accounting
                   metadataService.addLink('Invoice-details', 'View-accounting', 'View-accounting-nav-control', 'View accounting', true);
               },
               pageInit: function (pageMetadata, params) {
        if (pageMetadata.Name == 'Invoice-details') {
                       // Show/hide workflow actions based on workflow step
                       metadataService.configureAction('Accept', { visible: true });
                       metadataService.configureAction('Approve', { visible: true });
                       metadataService.configureAction('Reject', { visible: true });
                       metadataService.configureAction('Delegate', { visible: true });
                       metadataService.configureAction('Request-change', { visible: true });
                       metadataService.configureAction('Recall', { visible: true });
                       metadataService.configureAction('Complete', { visible: true });
                       metadataService.configureAction('Resubmit', { visible: true });

                       var entityContextParts = params.pageContext.split(':');
                       var data = dataService.getEntityData(entityContextParts[0], entityContextParts[1]);

                       var acceptControl = data.getPropertyValue('VendInvoiceInfoTable/showAccept');
                       var approveControl = data.getPropertyValue('VendInvoiceInfoTable/showApprove');
                       var rejectControl = data.getPropertyValue('VendInvoiceInfoTable/showReject');
                       var delegateControl = data.getPropertyValue('VendInvoiceInfoTable/showDelegate');
                       var requestChangeControl = data.getPropertyValue('VendInvoiceInfoTable/showRequestChange');
                       var recallControl = data.getPropertyValue('VendInvoiceInfoTable/showRecall');
                       var completeControl = data.getPropertyValue('VendInvoiceInfoTable/showComplete');
                       var resubmitControl = data.getPropertyValue('VendInvoiceInfoTable/showResubmit');

                       var showAcceptControl = Boolean(acceptControl == 1);
                       var showApproveControl = Boolean(approveControl == 1);
                     var showRejectControl = Boolean(rejectControl == 1);
                       var showDelegateControl = Boolean(delegateControl == 1);
                       var showRequestChangeControl = Boolean(requestChangeControl == 1);
                       var showRecallControl = Boolean(recallControl == 1);
                       var showCompleteControl = Boolean(completeControl == 1);
                       var showResubmitControl = Boolean(resubmitControl == 1);

                       metadataService.configureAction('Accept', { visible: showAcceptControl });
                       metadataService.configureAction('Approve', { visible: showApproveControl });
                       metadataService.configureAction('Reject', { visible: showRejectControl });
                       metadataService.configureAction('Delegate', { visible: showDelegateControl });
                       metadataService.configureAction('Request-change', { visible: showRequestChangeControl });
                       metadataService.configureAction('Recall', { visible: showRecallControl });
                       metadataService.configureAction('Complete', { visible: showCompleteControl });
                       metadataService.configureAction('Resubmit', { visible: showResubmitControl });
        }
                 },
           };
        }

2.  <span data-ttu-id="09f90-362">Cargar el archivo del código en el espacio de trabajo seleccionando la ficha **Lógica** para sobrescribir el código anterior</span><span class="sxs-lookup"><span data-stu-id="09f90-362">Upload the code file to the workspace by selecting the **Logic** tab to overwrite the previous code</span></span>
3.  <span data-ttu-id="09f90-363">Haga clic en **Listo** para salir del modo de edición.</span><span class="sxs-lookup"><span data-stu-id="09f90-363">Click **Done** to exit edit mode.</span></span>
4.  <span data-ttu-id="09f90-364">Haga clic en **Atrás** y, a continuación, **Listo** para salir del espacio de trabajo</span><span class="sxs-lookup"><span data-stu-id="09f90-364">Click **Back** and then **Done** to exit the workspace</span></span>
5.  <span data-ttu-id="09f90-365">Haga clic en **Publicar espacio de trabajo** para guardar el trabajo</span><span class="sxs-lookup"><span data-stu-id="09f90-365">Click **Publish workspace** to save your work</span></span>

### <a name="validation"></a><span data-ttu-id="09f90-366">Validación</span><span class="sxs-lookup"><span data-stu-id="09f90-366">Validation</span></span>

<span data-ttu-id="09f90-367">Desde el dispositivo móvil, abra la aplicación y conéctese a la instancia de su instancia.</span><span class="sxs-lookup"><span data-stu-id="09f90-367">From your mobile device, open the app, and connect to your instance.</span></span> <span data-ttu-id="09f90-368">Asegúrese de tener haber iniciado sesión en la empresa donde tenga asignadas las facturas de proveedores para revisión.</span><span class="sxs-lookup"><span data-stu-id="09f90-368">Make sure that you sign in to the company where vendor invoices are assigned to you for review.</span></span> <span data-ttu-id="09f90-369">Debería poder realizar las acciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="09f90-369">You should be able to perform the following actions:</span></span>

-   <span data-ttu-id="09f90-370">Ver el espacio de trabajo **Mis aprobaciones**.</span><span class="sxs-lookup"><span data-stu-id="09f90-370">See the **My approvals** workspace.</span></span>
-   <span data-ttu-id="09f90-371">Explorar en profundidad el espacio de trabajo **Mis aprobaciones** y ver la página **Mis facturas de proveedor**.</span><span class="sxs-lookup"><span data-stu-id="09f90-371">Drill into the **My approvals** workspace and see the **My vendor invoices** page.</span></span>
-   <span data-ttu-id="09f90-372">Explorar en profundidad la página **Mis facturas de proveedores** y ver la lista de facturas que se le han asignado.</span><span class="sxs-lookup"><span data-stu-id="09f90-372">Drill into the **My vendor invoices** page and see the list of invoices that are assigned to you.</span></span>
-   <span data-ttu-id="09f90-373">Explorar en profundidad una de las facturas y ver los detalles del encabezado y la línea de la factura.</span><span class="sxs-lookup"><span data-stu-id="09f90-373">Drill into one of the invoices, and see the invoice header details and line details.</span></span>
-   <span data-ttu-id="09f90-374">En la página de detalles, ver un vínculo a los datos adjuntos y utilizarlo para navegar a la lista de datos adjuntos y verlos.</span><span class="sxs-lookup"><span data-stu-id="09f90-374">On the details page, see a link to attachments, and use this link to navigate to the attachments list and view the attachments.</span></span>
-   <span data-ttu-id="09f90-375">En la página de detalles, ver un vínculo a la página **Ver contabilidad** y utilizarlo para navegar a la página de distribuciones y ver las distribuciones.</span><span class="sxs-lookup"><span data-stu-id="09f90-375">On the details page, see a link to the **View accounting** page, and use this link to navigate to the distributions page and view the distributions.</span></span>
-   <span data-ttu-id="09f90-376">En la página de detalles, haga clic en el menú **Acciones** de la parte inferior y realice las acciones del flujo de trabajo aplicables al paso del flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="09f90-376">On the details page, click the **Actions** menu at the bottom, and perform workflow actions that are applicable to the workflow step.</span></span>

## <a name="designing-a-complex-invoice-approval-scenario-for-fabrikam"></a><span data-ttu-id="09f90-377">Diseñar un escenario de aprobación de factoras complejo para Fabrikam</span><span class="sxs-lookup"><span data-stu-id="09f90-377">Designing a complex invoice approval scenario for Fabrikam</span></span>
<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="09f90-378">Atributo de escenario</span><span class="sxs-lookup"><span data-stu-id="09f90-378">Scenario attribute</span></span></th>
<th><span data-ttu-id="09f90-379">Respuesta</span><span class="sxs-lookup"><span data-stu-id="09f90-379">Answer</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="09f90-380">¿Qué campos del encabezado de la factura el usuario deseará ver en la experiencia móvil, y en qué pedidos?</span><span class="sxs-lookup"><span data-stu-id="09f90-380">What fields from the invoice header will the user want to see in the mobile experience, and in what order?</span></span></td>
<td><ol>
<li><span data-ttu-id="09f90-381">Nombre del proveedor</span><span class="sxs-lookup"><span data-stu-id="09f90-381">Vendor name</span></span></li>
<li><span data-ttu-id="09f90-382">Importe de la factura</span><span class="sxs-lookup"><span data-stu-id="09f90-382">Invoice amount</span></span></li>
<li><span data-ttu-id="09f90-383">Cuenta de facturación</span><span class="sxs-lookup"><span data-stu-id="09f90-383">Invoice account</span></span></li>
<li><span data-ttu-id="09f90-384">Número de factura</span><span class="sxs-lookup"><span data-stu-id="09f90-384">Invoice number</span></span></li>
<li><span data-ttu-id="09f90-385">Fecha de la factura</span><span class="sxs-lookup"><span data-stu-id="09f90-385">Invoice date</span></span></li>
<li><span data-ttu-id="09f90-386">Descripción de factura</span><span class="sxs-lookup"><span data-stu-id="09f90-386">Invoice description</span></span></li>
<li><span data-ttu-id="09f90-387">Fecha de vencimiento</span><span class="sxs-lookup"><span data-stu-id="09f90-387">Due date</span></span></li>
<li><span data-ttu-id="09f90-388">Divisa de la factura</span><span class="sxs-lookup"><span data-stu-id="09f90-388">Invoice currency</span></span></li>
</ol></td>
</tr>
<tr class="even">
<td><span data-ttu-id="09f90-389">¿Qué líneas del encabezado de la factura el usuario deseará ver en la experiencia móvil, y en qué pedidos?</span><span class="sxs-lookup"><span data-stu-id="09f90-389">What fields from the invoice lines will the user want to see in the mobile experience, and in what order?</span></span></td>
<td><ol>
<li><span data-ttu-id="09f90-390">Categoría de compras</span><span class="sxs-lookup"><span data-stu-id="09f90-390">Procurement category</span></span></li>
<li><span data-ttu-id="09f90-391">Cantidad</span><span class="sxs-lookup"><span data-stu-id="09f90-391">Quantity</span></span></li>
<li><span data-ttu-id="09f90-392">Precio unitario</span><span class="sxs-lookup"><span data-stu-id="09f90-392">Unit price</span></span></li>
<li><span data-ttu-id="09f90-393">Importe neto de línea</span><span class="sxs-lookup"><span data-stu-id="09f90-393">Line net amount</span></span></li>
<li><span data-ttu-id="09f90-394">Importe de la declaración de IRPF</span><span class="sxs-lookup"><span data-stu-id="09f90-394">1099 amount</span></span></li>
</ol></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="09f90-395">¿Cuántas líneas de factura hay en una factura?</span><span class="sxs-lookup"><span data-stu-id="09f90-395">How many invoice lines are there in an invoice?</span></span> <span data-ttu-id="09f90-396">Aplique la regla 80-20 aquí, y optimice para llegar al 80 por ciento.</span><span class="sxs-lookup"><span data-stu-id="09f90-396">Apply the 80-20 rule here, and optimize for the 80 percent.</span></span></td>
<td><span data-ttu-id="09f90-397">5</span><span class="sxs-lookup"><span data-stu-id="09f90-397">5</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="09f90-398">¿Los usuarios desearán ver las distribuciones contables (codificación de la factura) en el dispositivo móvil durante las revisiones?</span><span class="sxs-lookup"><span data-stu-id="09f90-398">Will users want to see accounting distributions (invoice coding) on the mobile device during reviews?</span></span></td>
<td><span data-ttu-id="09f90-399">Sí</span><span class="sxs-lookup"><span data-stu-id="09f90-399">Yes</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="09f90-400">¿Cuántas distribuciones contables (precio total, impuestos, cargos, etc.) hay para una línea de factura?</span><span class="sxs-lookup"><span data-stu-id="09f90-400">How many accounting distributions (extended price, sales tax, charges, and so on) are there for an invoice line?</span></span> <span data-ttu-id="09f90-401">Una vez más, aplique la regla 80-20.</span><span class="sxs-lookup"><span data-stu-id="09f90-401">Again, apply the 80-20 rule.</span></span></td>
<td><span data-ttu-id="09f90-402">Precio total: 2 Impuestos: 2 Cargos: 2</span><span class="sxs-lookup"><span data-stu-id="09f90-402">Extended price: 2 Sales tax: 2 Charges: 2</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="09f90-403">¿Las facturas también tienen distribuciones contables en el encabezado de factura?</span><span class="sxs-lookup"><span data-stu-id="09f90-403">Do the invoices also have accounting distributions on the invoice header?</span></span> <span data-ttu-id="09f90-404">En dicho caso, ¿estas distribuciones contables deben estar disponible en el dispositivo?</span><span class="sxs-lookup"><span data-stu-id="09f90-404">If so, should these accounting distributions be available on the device?</span></span></td>
<td><span data-ttu-id="09f90-405">No utilizado</span><span class="sxs-lookup"><span data-stu-id="09f90-405">Not used</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="09f90-406">¿Los usuarios desearán ver los datos adjuntos de la factura en el dispositivo?</span><span class="sxs-lookup"><span data-stu-id="09f90-406">Will users want to see attachments for the invoice on the device?</span></span></td>
<td><span data-ttu-id="09f90-407">Sí</span><span class="sxs-lookup"><span data-stu-id="09f90-407">Yes</span></span></td>
</tr>
</tbody>
</table>

### <a name="next-steps"></a><span data-ttu-id="09f90-408">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="09f90-408">Next steps</span></span>

<span data-ttu-id="09f90-409">Las variaciones siguientes se pueden realizar para el escenario 1, en función de los requisitos para el escenario 2.</span><span class="sxs-lookup"><span data-stu-id="09f90-409">The following variations can be done for scenario 1, based on the requirements for scenario 2.</span></span> <span data-ttu-id="09f90-410">Puede usar esta sección para mejorar la experiencia móvil de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="09f90-410">You can use this section to improve your mobile app experience.</span></span>

1.  <span data-ttu-id="09f90-411">Dado que habrá más líneas de factura en el escenario 2, los cambios siguientes en el diseño ayudarán a optimizar la experiencia del usuario en el dispositivo móvil:</span><span class="sxs-lookup"><span data-stu-id="09f90-411">Because more invoice lines are expected in scenario 2, the following changes to the design will help optimize the user experience on the mobile device:</span></span>
    1.  <span data-ttu-id="09f90-412">En lugar de ver las líneas de la factura en la página de detalles (como en el escenario 1), los usuarios pueden elegir ver las líneas en una página independiente para dispositivos móviles.</span><span class="sxs-lookup"><span data-stu-id="09f90-412">Instead of viewing invoice lines on the details page (as in scenario 1), users can choose to view lines on a separate mobile page.</span></span>
    2.  <span data-ttu-id="09f90-413">Dado que habrá más de una línea de factura este escenario, si la página **VendMobileInvoiceAllDistributionTree** se utiliza para diseñar la página de distribuciones para dispositivos móviles (como en el escenario 1), puede que resulte confuso para que el usuario correlacionar líneas con distribuciones.</span><span class="sxs-lookup"><span data-stu-id="09f90-413">Because more than one invoice line is expected in this scenario, if the **VendMobileInvoiceAllDistributionTree** page is used to design the distributions page for mobile (as in scenario 1), it might be confusing for the user to correlate lines to distributions.</span></span> <span data-ttu-id="09f90-414">Por lo tanto, use la página **VendMobileInvoiceLineDistributionTree** para diseñar la página de distribuciones.</span><span class="sxs-lookup"><span data-stu-id="09f90-414">Therefore, use the **VendMobileInvoiceLineDistributionTree** page to design the distributions page.</span></span>
    3.  <span data-ttu-id="09f90-415">Por ello, las distribuciones se deben mostrar en el contexto de una línea de factura en este escenario.</span><span class="sxs-lookup"><span data-stu-id="09f90-415">Ideally, the distributions should be shown in the context of an invoice line in this scenario.</span></span> <span data-ttu-id="09f90-416">Por lo tanto, asegúrese de que el usuario puede explorar en una línea para ver la página de las distribuciones.</span><span class="sxs-lookup"><span data-stu-id="09f90-416">Therefore, make sure that the user can drill into a line to see the distributions page.</span></span> <span data-ttu-id="09f90-417">Use la capacidad del vínculo de la página para establecer una búsqueda detallada, tal como hizo para el encabezado y las páginas de detalles en el escenario 1.</span><span class="sxs-lookup"><span data-stu-id="09f90-417">Use the page link capability to establish the drill-through, just as you did for the header and details pages in scenario 1.</span></span>

2.  <span data-ttu-id="09f90-418">Dado que habrá más de un tipo de importe en las distribuciones en el escenario 2 (los impuestos, los gastos, etc.), será útil mostrar la descripción del tipo de importe.</span><span class="sxs-lookup"><span data-stu-id="09f90-418">Because more than one amount type is expected on the distributions in scenario 2 (sales tax, charges, and so on), it will be useful to show the description of the amount type.</span></span> <span data-ttu-id="09f90-419">(Omitimos esta información en el escenario 1).</span><span class="sxs-lookup"><span data-stu-id="09f90-419">(We omitted this information in scenario 1.)</span></span>




