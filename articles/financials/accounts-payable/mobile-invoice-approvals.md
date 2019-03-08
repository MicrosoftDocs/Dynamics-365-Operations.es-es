---
title: Aprobaciones de factura móvil
description: Este tema está pensando para proporcionar un método práctico de diseñar escenarios móviles en Dynamics 365 for Finance and Operations con las aprobaciones de facturas de proveedores para aplicaciones móviles como un caso de uso.
author: ShivamPandey-msft
manager: AnnBe
ms.date: 08/22/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User, IT Pro
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.custom: 262034
ms.assetid: 9db38b3f-26b3-436e-8449-7ff243568a18
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: e39d81b0d600012f936865b53f8556eb3ef0a3d9
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/29/2019
ms.locfileid: "314403"
---
# <a name="mobile-invoice-approvals"></a><span data-ttu-id="5ac3b-103">Aprobaciones de factura móvil</span><span class="sxs-lookup"><span data-stu-id="5ac3b-103">Mobile invoice approvals</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="5ac3b-104">Las capacidades móviles en Microsoft Dynamics 365 for Finance and Operations permiten a un usuario empresarial diseñar experiencias móviles.</span><span class="sxs-lookup"><span data-stu-id="5ac3b-104">Mobile capabilities in Microsoft Dynamics 365 for Finance and Operations let a business user design mobile experiences.</span></span> <span data-ttu-id="5ac3b-105">Para situaciones avanzadas, la plataforma también permite a los desarrolladores ampliar las capacidades como desean.</span><span class="sxs-lookup"><span data-stu-id="5ac3b-105">For advanced scenarios, the platform also lets developers extend the capabilities as they desire.</span></span> <span data-ttu-id="5ac3b-106">La forma más eficaz de aprender algunos de los conceptos nuevos sobre capacidades móviles es pasar por el proceso de diseño de algunos escenarios.</span><span class="sxs-lookup"><span data-stu-id="5ac3b-106">The most effective way to learn some of the new concepts on mobile is to go through the process of designing a few scenarios.</span></span> <span data-ttu-id="5ac3b-107">Este tema está pensando para proporcionar un método práctico de diseñar escenarios móviles con las aprobaciones de facturas de proveedores para aplicaciones móviles como un caso de uso.</span><span class="sxs-lookup"><span data-stu-id="5ac3b-107">This topic is intended to provide a practical approach to designing mobile scenarios by taking vendor invoice approvals for mobile as a use case.</span></span> <span data-ttu-id="5ac3b-108">Este tema le ayudará a diseñar otras variaciones de los escenarios y se puede aplicar a otros escenarios que no están relacionados con las facturas de proveedores.</span><span class="sxs-lookup"><span data-stu-id="5ac3b-108">This topic should help you design other variations of the scenarios and can also be applied to other scenarios that aren’t related to vendor invoices.</span></span>

<a name="prerequisites"></a><span data-ttu-id="5ac3b-109">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="5ac3b-109">Prerequisites</span></span>
-------------

| <span data-ttu-id="5ac3b-110">Requisito previo</span><span class="sxs-lookup"><span data-stu-id="5ac3b-110">Prerequisite</span></span>                                                                                            | <span data-ttu-id="5ac3b-111">Descripción</span><span class="sxs-lookup"><span data-stu-id="5ac3b-111">Description</span></span>                                                                                                                                                          |
|---------------------------------------------------------------------------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| <span data-ttu-id="5ac3b-112">Manual sobre capacidades móviles de lectura previa</span><span class="sxs-lookup"><span data-stu-id="5ac3b-112">Mobile handbook pre-read</span></span>                                                                                |[<span data-ttu-id="5ac3b-113">Plataforma móvil</span><span class="sxs-lookup"><span data-stu-id="5ac3b-113">Mobile platform</span></span>](../../dev-itpro/mobile-apps/platform/mobile-platform-home-page.md)                                                                                                  |
| <span data-ttu-id="5ac3b-114">Dynamics 365 for Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="5ac3b-114">Dynamics 365 for Finance and Operations</span></span>                                                                             | <span data-ttu-id="5ac3b-115">Un entorno que tiene la versión 1611 de Microsoft Dynamics 365 for Operations y Microsoft Dynamics for Operations con la actualización de plataforma 3 (noviembre de 2016)</span><span class="sxs-lookup"><span data-stu-id="5ac3b-115">An environment that has Microsoft Dynamics 365 for Operations version 1611 and Microsoft Dynamics for Operations platform update 3 (November 2016)</span></span>                   |
| <span data-ttu-id="5ac3b-116">Instalar revisión KB 3204341.</span><span class="sxs-lookup"><span data-stu-id="5ac3b-116">Install hotfix KB 3204341.</span></span>                                                                              | <span data-ttu-id="5ac3b-117">El grabador de tareas puede registrar de forma errónea dos comandos Close para diálogos desplegables incluidos en la actualización 3 de Dynamics 365 for Operations (noviembre de 2016)</span><span class="sxs-lookup"><span data-stu-id="5ac3b-117">Task recorder can erroneously record two Close commands for dropdown dialogs this is included in Dynamics 365 for Operation platform update 3 (November 2016 update)</span></span> |
| <span data-ttu-id="5ac3b-118">Instalar revisión KB 3207800.</span><span class="sxs-lookup"><span data-stu-id="5ac3b-118">Install hotfix KB 3207800.</span></span>                                                                              | <span data-ttu-id="5ac3b-119">Esta revisión habilita los datos adjuntos que se verán en el cliente móvil, lo cual se incluye en la actualización 3 de Dynamics 365 for Operation (noviembre de 2016).</span><span class="sxs-lookup"><span data-stu-id="5ac3b-119">This hotfix enables attachments to be viewed on the mobile client this is included in Dynamics 365 for Operation platform update 3 (November 2016 update).</span></span>           |
| <span data-ttu-id="5ac3b-120">Instalar revisión KB 3208224.</span><span class="sxs-lookup"><span data-stu-id="5ac3b-120">Install hotfix KB 3208224.</span></span>                                                                              | <span data-ttu-id="5ac3b-121">El código de la aplicación para la aplicación de aprobación de facturas de proveedores móviles se incluye en la aplicación 7.0.1 de Microsoft Dynamics AX (mayo de 2016).</span><span class="sxs-lookup"><span data-stu-id="5ac3b-121">Application code for the mobile vendor invoice approval application this is included in Microsoft Dynamics AX application 7.0.1 (May 2016).</span></span>                          |
| <span data-ttu-id="5ac3b-122">Un dispositivo Android, iOS o Windows que tengan la aplicación móvil instalada para Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="5ac3b-122">An Android or iOS or a Windows device that has the mobile app installed for Finance and Operations</span></span> | <span data-ttu-id="5ac3b-123">Busque la aplicación en la tienda de aplicaciones apropiada.</span><span class="sxs-lookup"><span data-stu-id="5ac3b-123">Search for the app in the appropriate app store.</span></span>                                                                                                                     |

## <a name="introduction"></a><span data-ttu-id="5ac3b-124">Introducción</span><span class="sxs-lookup"><span data-stu-id="5ac3b-124">Introduction</span></span>
<span data-ttu-id="5ac3b-125">Las aprobaciones móviles para las facturas de proveedor requieren la tres revisiones mencionadas en la sección de los requisititos previos.</span><span class="sxs-lookup"><span data-stu-id="5ac3b-125">Mobile approvals for vendor invoices require the three hotfixes that are mentioned in the “Prerequisites” section.</span></span> <span data-ttu-id="5ac3b-126">Estas revisiones no proporcionan un espacio de trabajo para las aprobaciones de facturas.</span><span class="sxs-lookup"><span data-stu-id="5ac3b-126">These hotfixes don’t provide a workspace for the invoice approvals.</span></span> <span data-ttu-id="5ac3b-127">Para saber qué es un espacio de trabajo en el contexto de las aplicaciones móviles, lea el manual referido en la sección de los requisitos previos.</span><span class="sxs-lookup"><span data-stu-id="5ac3b-127">To learn what a workspace is in the context of mobile, read the mobile handbook that is mentioned in the “Prerequisites” section.</span></span> <span data-ttu-id="5ac3b-128">Se debe diseñar un espacio de trabajo para aprobaciones de facturas.</span><span class="sxs-lookup"><span data-stu-id="5ac3b-128">The invoice approvals workspace must be designed.</span></span> 

<span data-ttu-id="5ac3b-129">Cada organización articula y define su proceso empresarial para las facturas de proveedores de forma diferente.</span><span class="sxs-lookup"><span data-stu-id="5ac3b-129">Every organization orchestrates and defines its business process for vendor invoices differently.</span></span> <span data-ttu-id="5ac3b-130">Antes de diseñar una experiencia móvil para las aprobaciones de la facturas de proveedores, debe tener en cuenta los siguientes aspectos del proceso empresarial.</span><span class="sxs-lookup"><span data-stu-id="5ac3b-130">Before you design a mobile experience for vendor invoice approvals, you should consider the following aspects of the business process.</span></span> <span data-ttu-id="5ac3b-131">La idea es usar estos puntos de datos tanto como sea posible para optimizar la experiencia del usuario en el dispositivo.</span><span class="sxs-lookup"><span data-stu-id="5ac3b-131">The idea is to use these data points as much as possible to optimize the user experience on the device.</span></span>

-   <span data-ttu-id="5ac3b-132">¿Qué campos del encabezado de la factura el usuario deseará ver en la experiencia móvil, y en qué pedidos?</span><span class="sxs-lookup"><span data-stu-id="5ac3b-132">What fields from the invoice header will the user want to see in the mobile experience, and in what order?</span></span>
-   <span data-ttu-id="5ac3b-133">¿Qué líneas del encabezado de la factura el usuario deseará ver en la experiencia móvil, y en qué pedidos?</span><span class="sxs-lookup"><span data-stu-id="5ac3b-133">What fields from the invoice lines will the user want to see in the mobile experience, and in what order?</span></span>
-   <span data-ttu-id="5ac3b-134">¿Cuántas líneas de factura hay en una factura?</span><span class="sxs-lookup"><span data-stu-id="5ac3b-134">How many invoice lines are there in an invoice?</span></span> <span data-ttu-id="5ac3b-135">Aplique la regla 80-20 aquí, y optimice para llegar al 80 por ciento.</span><span class="sxs-lookup"><span data-stu-id="5ac3b-135">Apply the 80-20 rule here, and optimize for the 80 percent.</span></span>
-   <span data-ttu-id="5ac3b-136">¿Los usuarios desearán ver las distribuciones contables (codificación de la factura) en el dispositivo móvil durante las revisiones?</span><span class="sxs-lookup"><span data-stu-id="5ac3b-136">Will users want to see accounting distributions (invoice coding) on the mobile device during reviews?</span></span> <span data-ttu-id="5ac3b-137">Si la respuesta a esta pregunta es afirmativa, tenga en cuenta las preguntas siguientes:</span><span class="sxs-lookup"><span data-stu-id="5ac3b-137">If the answer to this question is yes, consider the following questions:</span></span>
    -   <span data-ttu-id="5ac3b-138">¿Cuántas distribuciones contables (precio total, impuestos, cargos, divisiones, etc.) hay para una línea de factura?</span><span class="sxs-lookup"><span data-stu-id="5ac3b-138">How many accounting distributions (extended price, sales tax, charges, splits, and so on) are there for an invoice line?</span></span> <span data-ttu-id="5ac3b-139">Una vez más, aplique la regla 80-20.</span><span class="sxs-lookup"><span data-stu-id="5ac3b-139">Again, apply the 80-20 rule.</span></span>
    -   <span data-ttu-id="5ac3b-140">¿Las facturas también tienen distribuciones contables en el encabezado de factura?</span><span class="sxs-lookup"><span data-stu-id="5ac3b-140">Do the invoices also have accounting distributions on the invoice header?</span></span> <span data-ttu-id="5ac3b-141">En dicho caso, ¿estas distribuciones contables deben estar disponible en el dispositivo?</span><span class="sxs-lookup"><span data-stu-id="5ac3b-141">If so, should these accounting distributions be available on the device?</span></span>

> [!NOTE]
> <span data-ttu-id="5ac3b-142">Este tema no explica cómo editar distribuciones contables, porque esta funcionalidad no se admite actualmente para los escenarios móviles.</span><span class="sxs-lookup"><span data-stu-id="5ac3b-142">This topic doesn’t explain how to edit accounting distributions, because this functionality isn’t currently supported for mobile scenarios.</span></span>

-   <span data-ttu-id="5ac3b-143">¿Los usuarios desearán ver los datos adjuntos de la factura en el dispositivo?</span><span class="sxs-lookup"><span data-stu-id="5ac3b-143">Will users want to see attachments for the invoice on the device?</span></span>

<span data-ttu-id="5ac3b-144">El diseño de la experiencia móvil de las aprobaciones de facturas variará, en función de las respuestas a estas preguntas.</span><span class="sxs-lookup"><span data-stu-id="5ac3b-144">The design of the mobile experience for invoice approvals will differ, depending on the answers to these questions.</span></span> <span data-ttu-id="5ac3b-145">El objetivo es optimizar la experiencia del usuario para el proceso empresarial en las plataformas móviles de una organización.</span><span class="sxs-lookup"><span data-stu-id="5ac3b-145">The objective is to optimize the user experience for the business process on mobile in an organization.</span></span> <span data-ttu-id="5ac3b-146">En el resto de este tema, revisaremos dos variaciones del escenario que se basan en diferentes respuestas a las preguntas anteriores.</span><span class="sxs-lookup"><span data-stu-id="5ac3b-146">In the rest of this topic, we will look at two scenario variations that are based on different answers to the preceding questions.</span></span> 

<span data-ttu-id="5ac3b-147">Como orientación general, al trabajar con el diseñador para aplicaciones móviles, asegúrese de “publicar” los cambios para evitar perder las actualizaciones.</span><span class="sxs-lookup"><span data-stu-id="5ac3b-147">As a general guidance, when working with the mobile designer, make sure to 'publish' the changes to prevent losing the updates.</span></span>

## <a name="designing-a-simple-invoice-approval-scenario-for-contoso"></a><span data-ttu-id="5ac3b-148">Diseñar una situación de ejemplo sencillo de aprobación de facturas para Contoso</span><span class="sxs-lookup"><span data-stu-id="5ac3b-148">Designing a simple invoice approval scenario for Contoso</span></span>
<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="5ac3b-149">Atributo de escenario</span><span class="sxs-lookup"><span data-stu-id="5ac3b-149">Scenario attribute</span></span></th>
<th><span data-ttu-id="5ac3b-150">Respuesta</span><span class="sxs-lookup"><span data-stu-id="5ac3b-150">Answer</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="5ac3b-151">¿Qué campos del encabezado de la factura el usuario deseará ver en la experiencia móvil, y en qué pedidos?</span><span class="sxs-lookup"><span data-stu-id="5ac3b-151">What fields from the invoice header will the user want to see in the mobile experience, and in what order?</span></span></td>
<td><ol>
<li><span data-ttu-id="5ac3b-152">Nombre del proveedor</span><span class="sxs-lookup"><span data-stu-id="5ac3b-152">Vendor name</span></span></li>
<li><span data-ttu-id="5ac3b-153">Total de la factura</span><span class="sxs-lookup"><span data-stu-id="5ac3b-153">Invoice total</span></span></li>
<li><span data-ttu-id="5ac3b-154">Cuenta de facturación</span><span class="sxs-lookup"><span data-stu-id="5ac3b-154">Invoice account</span></span></li>
<li><span data-ttu-id="5ac3b-155">Número de factura</span><span class="sxs-lookup"><span data-stu-id="5ac3b-155">Invoice number</span></span></li>
<li><span data-ttu-id="5ac3b-156">Fecha de la factura</span><span class="sxs-lookup"><span data-stu-id="5ac3b-156">Invoice date</span></span></li>
<li><span data-ttu-id="5ac3b-157">Descripción de factura</span><span class="sxs-lookup"><span data-stu-id="5ac3b-157">Invoice description</span></span></li>
<li><span data-ttu-id="5ac3b-158">Fecha de vencimiento</span><span class="sxs-lookup"><span data-stu-id="5ac3b-158">Due date</span></span></li>
<li><span data-ttu-id="5ac3b-159">Divisa de la factura</span><span class="sxs-lookup"><span data-stu-id="5ac3b-159">Invoice currency</span></span></li>
</ol></td>
</tr>
<tr class="even">
<td><span data-ttu-id="5ac3b-160">¿Qué líneas del encabezado de la factura el usuario deseará ver en la experiencia móvil, y en qué pedidos?</span><span class="sxs-lookup"><span data-stu-id="5ac3b-160">What fields from the invoice lines will the user want to see in the mobile experience, and in what order?</span></span></td>
<td><ol>
<li><span data-ttu-id="5ac3b-161">Categoría de compras</span><span class="sxs-lookup"><span data-stu-id="5ac3b-161">Procurement category</span></span></li>
<li><span data-ttu-id="5ac3b-162">Cantidad</span><span class="sxs-lookup"><span data-stu-id="5ac3b-162">Quantity</span></span></li>
<li><span data-ttu-id="5ac3b-163">Precio unitario</span><span class="sxs-lookup"><span data-stu-id="5ac3b-163">Unit price</span></span></li>
<li><span data-ttu-id="5ac3b-164">Importe neto de línea</span><span class="sxs-lookup"><span data-stu-id="5ac3b-164">Line net amount</span></span></li>
<li><span data-ttu-id="5ac3b-165">Importe de la declaración de IRPF</span><span class="sxs-lookup"><span data-stu-id="5ac3b-165">1099 amount</span></span></li>
</ol></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="5ac3b-166">¿Cuántas líneas de factura hay en una factura?</span><span class="sxs-lookup"><span data-stu-id="5ac3b-166">How many invoice lines are there in an invoice?</span></span> <span data-ttu-id="5ac3b-167">Aplique la regla 80-20 aquí, y optimice para llegar al 80 por ciento.</span><span class="sxs-lookup"><span data-stu-id="5ac3b-167">Apply the 80-20 rule here, and optimize for the 80 percent.</span></span></td>
<td><span data-ttu-id="5ac3b-168">1</span><span class="sxs-lookup"><span data-stu-id="5ac3b-168">1</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="5ac3b-169">¿Los usuarios desearán ver las distribuciones contables (codificación de la factura) en el dispositivo móvil durante las revisiones?</span><span class="sxs-lookup"><span data-stu-id="5ac3b-169">Will users want to see accounting distributions (invoice coding) on the mobile device during reviews?</span></span></td>
<td><span data-ttu-id="5ac3b-170">Sí</span><span class="sxs-lookup"><span data-stu-id="5ac3b-170">Yes</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="5ac3b-171">¿Cuántas distribuciones contables (precio total, impuestos, cargos, etc.) hay para una línea de factura?</span><span class="sxs-lookup"><span data-stu-id="5ac3b-171">How many accounting distributions (extended price, sales tax, charges, and so on) are there for an invoice line?</span></span> <span data-ttu-id="5ac3b-172">Una vez más, aplique la regla 80-20.</span><span class="sxs-lookup"><span data-stu-id="5ac3b-172">Again, apply the 80-20 rule.</span></span></td>
<td><span data-ttu-id="5ac3b-173">Precio total: 2 Impuestos: 0 Cargos: 0</span><span class="sxs-lookup"><span data-stu-id="5ac3b-173">Extended price: 2 Sales tax: 0 Charges: 0</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="5ac3b-174">¿Las facturas también tienen distribuciones contables en el encabezado de factura?</span><span class="sxs-lookup"><span data-stu-id="5ac3b-174">Do the invoices also have accounting distributions on the invoice header?</span></span> <span data-ttu-id="5ac3b-175">En dicho caso, ¿estas distribuciones contables deben estar disponible en el dispositivo?</span><span class="sxs-lookup"><span data-stu-id="5ac3b-175">If so, should these accounting distributions be available on the device?</span></span></td>
<td><span data-ttu-id="5ac3b-176">No utilizado</span><span class="sxs-lookup"><span data-stu-id="5ac3b-176">Not used</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="5ac3b-177">¿Los usuarios desearán ver los datos adjuntos de la factura en el dispositivo?</span><span class="sxs-lookup"><span data-stu-id="5ac3b-177">Will users want to see attachments for the invoice on the device?</span></span></td>
<td><span data-ttu-id="5ac3b-178">Sí</span><span class="sxs-lookup"><span data-stu-id="5ac3b-178">Yes</span></span></td>
</tr>
</tbody>
</table>

### <a name="create-the-workspace"></a><span data-ttu-id="5ac3b-179">Crear el espacio de trabajo</span><span class="sxs-lookup"><span data-stu-id="5ac3b-179">Create the workspace</span></span>

1.  <span data-ttu-id="5ac3b-180">En un explorador, abra Finance and Operations e inicie sesión.</span><span class="sxs-lookup"><span data-stu-id="5ac3b-180">In a browser, open Finance and Operations, and sign in.</span></span>
2.  <span data-ttu-id="5ac3b-181">Una vez que haya iniciado sesión, agregue **&mode=mobile** a la dirección URL como se muestra en el siguiente ejemplo, y actualice la página: https://&lt;yoururl&gt;/?cmp=usmf&mi=DefaultDashboard **&mode=mobile**</span><span class="sxs-lookup"><span data-stu-id="5ac3b-181">After you’ve signed in, append **&mode=mobile** to the URL as shown in the following example, and refresh the page: https://&lt;yoururl&gt;/?cmp=usmf&mi=DefaultDashboard **&mode=mobile**</span></span>
3.  <span data-ttu-id="5ac3b-182">Haga clic en el botón **Configuración** (engranaje) en la parte superior derecha de la página y, a continuación, haga clic en **Aplicación móvil**.</span><span class="sxs-lookup"><span data-stu-id="5ac3b-182">Click the **Settings** (gear) button in the upper right of the page, and then click **Mobile app**.</span></span> <span data-ttu-id="5ac3b-183">El diseñador para aplicaciones móviles de la aplicación debe aparecer igual que lo hace el Grabador de tareas.</span><span class="sxs-lookup"><span data-stu-id="5ac3b-183">The mobile app designer must show up just as Task recorder shows up.</span></span>
4.  <span data-ttu-id="5ac3b-184">Haga clic en **Agregar** para crear un nuevo espacio de trabajo.</span><span class="sxs-lookup"><span data-stu-id="5ac3b-184">Click **Add** to create a new workspace.</span></span> <span data-ttu-id="5ac3b-185">Para este ejemplo, asigne un nombre al espacio de trabajo **Mis aprobaciones**.</span><span class="sxs-lookup"><span data-stu-id="5ac3b-185">For this example, name the workspace **My approvals**.</span></span>
5.  <span data-ttu-id="5ac3b-186">Escribir una descripción.</span><span class="sxs-lookup"><span data-stu-id="5ac3b-186">Enter a description.</span></span>
6.  <span data-ttu-id="5ac3b-187">Seleccione un color para el espacio de trabajo.</span><span class="sxs-lookup"><span data-stu-id="5ac3b-187">Select a workspace color.</span></span> <span data-ttu-id="5ac3b-188">El color del espacio de trabajo se usará para el estilo global de la experiencia móvil de este espacio de trabajo.</span><span class="sxs-lookup"><span data-stu-id="5ac3b-188">The workspace color will be used for the overall style of the mobile experience for this workspace.</span></span>
7.  <span data-ttu-id="5ac3b-189">Seleccione un icono para el espacio de trabajo.</span><span class="sxs-lookup"><span data-stu-id="5ac3b-189">Select an icon for the workspace.</span></span>
8.  <span data-ttu-id="5ac3b-190">Haga clic en **Listo**</span><span class="sxs-lookup"><span data-stu-id="5ac3b-190">Click **Done**</span></span>
9.  <span data-ttu-id="5ac3b-191">Haga clic en **Publicar espacio de trabajo** para guardar los cambios</span><span class="sxs-lookup"><span data-stu-id="5ac3b-191">Click **Publish workspace** to save the changes</span></span>

### <a name="vendor-invoices-assigned-to-me"></a><span data-ttu-id="5ac3b-192">Facturas de proveedor asignadas al usuario</span><span class="sxs-lookup"><span data-stu-id="5ac3b-192">Vendor invoices assigned to me</span></span>

<span data-ttu-id="5ac3b-193">La primera página para aplicaciones móviles que debe diseñar es la lista de facturas que se asignan al usuario para revisión.</span><span class="sxs-lookup"><span data-stu-id="5ac3b-193">The first mobile page that you should design is the list of invoices that are assigned to the user for review.</span></span> <span data-ttu-id="5ac3b-194">Para diseñar esta página para aplicaciones móviles, use la página **VendMobileInvoiceAssignedToMeListPage** en Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="5ac3b-194">To design this mobile page, use the **VendMobileInvoiceAssignedToMeListPage** page in Finance and Operations.</span></span> <span data-ttu-id="5ac3b-195">Para completar este procedimiento, asegúrese de que al menos se le asigna una factura de proveedores para revisión, y que la línea de factura tiene dos distribuciones.</span><span class="sxs-lookup"><span data-stu-id="5ac3b-195">Before you complete this procedure, make sure that at least one vendor invoice is assigned to you for review, and that the invoice line has two distributions.</span></span> <span data-ttu-id="5ac3b-196">Esta configuración cumple los requisitos para este supuesto.</span><span class="sxs-lookup"><span data-stu-id="5ac3b-196">This setup meets the requirements for this scenario.</span></span>

1.  <span data-ttu-id="5ac3b-197">En la dirección URL de Finance and Operations, reemplace el nombre del elemento de menú con **VendMobileInvoiceAssignedToMeListPage** para abrir la versión móvil de la página con la lista **Facturas de proveedor pendientes asignadas a mí** en el módulo **Proveedores**.</span><span class="sxs-lookup"><span data-stu-id="5ac3b-197">In the Finance and Operations URL, replace the name of the menu item with **VendMobileInvoiceAssignedToMeListPage** to open the mobile version of the **Pending vendor invoices assigned to me** list page in the **Accounts payable** module.</span></span> <span data-ttu-id="5ac3b-198">En función del número de facturas que tiene en el sistema asignadas a usted, esta página mostrará dichas facturas.</span><span class="sxs-lookup"><span data-stu-id="5ac3b-198">Depending on the number of invoices that you have in your system assigned to you, this page will show those invoices.</span></span> <span data-ttu-id="5ac3b-199">Para buscar una factura específica, utilice el filtro a la izquierda.</span><span class="sxs-lookup"><span data-stu-id="5ac3b-199">To find a specific invoice, you can use the filter on the left.</span></span> <span data-ttu-id="5ac3b-200">Sin embargo, no se requiere una factura concreta para este ejemplo.</span><span class="sxs-lookup"><span data-stu-id="5ac3b-200">However, we don’t require a specific invoice for this example.</span></span> <span data-ttu-id="5ac3b-201">Simplemente se requiere que tenga asignada alguna factura, lo que le permitirá diseñar la página para aplicaciones móviles.</span><span class="sxs-lookup"><span data-stu-id="5ac3b-201">We just require some invoice assigned to you which is going to allow you to design the mobile page.</span></span> <span data-ttu-id="5ac3b-202">Las nuevas páginas disponibles se diseñaron específicamente para desarrollar los escenarios móviles para la factura de proveedor.</span><span class="sxs-lookup"><span data-stu-id="5ac3b-202">The new pages that are available have been designed specifically for developing mobile scenarios for vendor invoice.</span></span> <span data-ttu-id="5ac3b-203">Por lo tanto, debe usar estas páginas.</span><span class="sxs-lookup"><span data-stu-id="5ac3b-203">Therefore, you must use these pages.</span></span> <span data-ttu-id="5ac3b-204">La dirección debe URL ser similar a la URL siguiente y, después de especificarla, la página que se muestra en la ilustración debe aparecer: https://&lt;yourURL&gt;/?cmp=usmf&mi=**VendMobileInvoiceAssignedToMeListPage**&mode=mobile [![Página de Facturas de proveedor pendientes asignadas a mí](./media/mobile-invoice-approvals01-1024x281.png)](./media/mobile-invoice-approvals01.png)</span><span class="sxs-lookup"><span data-stu-id="5ac3b-204">The URL should resemble the following URL, and after you enter it, the page that is shown in the illustration must appear: https://&lt;yourURL&gt;/?cmp=usmf&mi=**VendMobileInvoiceAssignedToMeListPage**&mode=mobile [![Pending vendor invoices assigned to me page](./media/mobile-invoice-approvals01-1024x281.png)](./media/mobile-invoice-approvals01.png)</span></span>
2.  <span data-ttu-id="5ac3b-205">Haga clic en el botón **Configuración** (engranaje) en la parte superior derecha de la página y, a continuación, haga clic en **Aplicación móvil**</span><span class="sxs-lookup"><span data-stu-id="5ac3b-205">Click the **Settings** (gear) button in the upper right of the page, and then click **Mobile app**</span></span>
3.  <span data-ttu-id="5ac3b-206">Seleccione su espacio de trabajo y haga clic en **Editar**</span><span class="sxs-lookup"><span data-stu-id="5ac3b-206">Select your workspace and click **Edit**</span></span>
4.  <span data-ttu-id="5ac3b-207">Haga clic en **Agregar página** para crear la primera página para aplicaciones móviles.</span><span class="sxs-lookup"><span data-stu-id="5ac3b-207">Click **Add page** to create the first mobile page.</span></span>
5.  <span data-ttu-id="5ac3b-208">Escriba un nombre, por ejemplo **Mis facturas de proveedor** y una descripción, por ejemplo **Facturas de proveedor que se me asignaron para revisión**.</span><span class="sxs-lookup"><span data-stu-id="5ac3b-208">Enter a name, such as **My vendor invoices**, and a description, such as **Vendor invoices assigned to me for review**.</span></span>
6.  <span data-ttu-id="5ac3b-209">Haga clic en **Listo**.</span><span class="sxs-lookup"><span data-stu-id="5ac3b-209">Click **Done**.</span></span>
7.  <span data-ttu-id="5ac3b-210">En el diseñador para aplicaciones móviles, en la ficha **Campos**, haga clic en **Seleccionar campos**.</span><span class="sxs-lookup"><span data-stu-id="5ac3b-210">In the mobile designer, on the **Fields** tab, click **Select fields**.</span></span> <span data-ttu-id="5ac3b-211">Las columnas de la página de lista deben ser semejantes a la siguiente ilustración.</span><span class="sxs-lookup"><span data-stu-id="5ac3b-211">The columns on the list page must resemble the following illustration.</span></span> <span data-ttu-id="5ac3b-212">[![Columnas en la página Facturas de proveedor pendientes asignadas a mí](./media/mobile-invoice-approvals02-1024x117.png)](./media/mobile-invoice-approvals02.png)</span><span class="sxs-lookup"><span data-stu-id="5ac3b-212">[![Columns on the Pending vendor invoices assigned to me page](./media/mobile-invoice-approvals02-1024x117.png)](./media/mobile-invoice-approvals02.png)</span></span>
8.  <span data-ttu-id="5ac3b-213">Agregue las columnas necesarias de la página con la lista que se deben mostrar a los usuarios en la página para aplicaciones móviles.</span><span class="sxs-lookup"><span data-stu-id="5ac3b-213">Add the required columns from the list page that must be shown to the users in the mobile page.</span></span> <span data-ttu-id="5ac3b-214">El orden en que se agrega es el orden en que los campos se mostrarán al usuario final.</span><span class="sxs-lookup"><span data-stu-id="5ac3b-214">The order in which you add is the order in which the fields will be displayed to the end user.</span></span> <span data-ttu-id="5ac3b-215">La única forma de cambiar orden de los campos es volviendo a seleccionar todos los campos.</span><span class="sxs-lookup"><span data-stu-id="5ac3b-215">The only way to change the ordering of the fields will be by re-selecting all the fields.</span></span> <span data-ttu-id="5ac3b-216">Según los requisitos para esta situación, son necesarias los ocho campos siguientes.</span><span class="sxs-lookup"><span data-stu-id="5ac3b-216">Based on the requirements for this scenario, the following eight fields are required.</span></span> <span data-ttu-id="5ac3b-217">Sin embargo, algunos usuarios pueden considerar que ocho campos son demasiada información para tener en un dispositivo móvil.</span><span class="sxs-lookup"><span data-stu-id="5ac3b-217">However, some users might consider eight fields too much information to have on a mobile device.</span></span> <span data-ttu-id="5ac3b-218">Por lo tanto, mostraremos solamente los campos más importantes en la vista de lista del móvil.</span><span class="sxs-lookup"><span data-stu-id="5ac3b-218">Therefore, we will show only the most important fields in the mobile list view.</span></span> <span data-ttu-id="5ac3b-219">Los campos restantes aparecerán en la vista de detalles que diseñaremos posteriormente.</span><span class="sxs-lookup"><span data-stu-id="5ac3b-219">The remaining fields will appear in the details view that we will design later.</span></span> <span data-ttu-id="5ac3b-220">Por ahora, agregaremos los campos siguientes.</span><span class="sxs-lookup"><span data-stu-id="5ac3b-220">For now, we will add the following fields.</span></span> <span data-ttu-id="5ac3b-221">Haga clic en el signo más (**+**) en estas columnas para agregar a la página para aplicaciones móviles.</span><span class="sxs-lookup"><span data-stu-id="5ac3b-221">Click the plus sign (**+**) in these columns to add to the mobile page.</span></span>
    - <span data-ttu-id="5ac3b-222">Nombre del proveedor</span><span class="sxs-lookup"><span data-stu-id="5ac3b-222">Vendor name</span></span>
    - <span data-ttu-id="5ac3b-223">Total de la factura</span><span class="sxs-lookup"><span data-stu-id="5ac3b-223">Invoice total</span></span>
    - <span data-ttu-id="5ac3b-224">Cuenta de facturación</span><span class="sxs-lookup"><span data-stu-id="5ac3b-224">Invoice account</span></span>
    - <span data-ttu-id="5ac3b-225">Número de factura</span><span class="sxs-lookup"><span data-stu-id="5ac3b-225">Invoice number</span></span>
    - <span data-ttu-id="5ac3b-226">Fecha de la factura</span><span class="sxs-lookup"><span data-stu-id="5ac3b-226">Invoice date</span></span>

    <span data-ttu-id="5ac3b-227">Después de que se agreguen los campos, la página para aplicaciones móviles debe asemejarse a la siguiente ilustración.</span><span class="sxs-lookup"><span data-stu-id="5ac3b-227">After the fields are added, the mobile page must resemble the following illustration.</span></span> 
    <span data-ttu-id="5ac3b-228">[![Página después de haber agregado campos](./media/mobile-invoice-approvals03.png)](./media/mobile-invoice-approvals03.png)</span><span class="sxs-lookup"><span data-stu-id="5ac3b-228">[![Page after fields are added](./media/mobile-invoice-approvals03.png)](./media/mobile-invoice-approvals03.png)</span></span>
9.  <span data-ttu-id="5ac3b-229">También debe agregar las siguientes columnas ahora, de modo que podamos habilitar acciones de flujo de trabajo posteriormente.</span><span class="sxs-lookup"><span data-stu-id="5ac3b-229">You must also add the following columns now, so that we can enable workflow actions later.</span></span>
    - <span data-ttu-id="5ac3b-230">Mostrar tarea completa</span><span class="sxs-lookup"><span data-stu-id="5ac3b-230">Show complete task</span></span>
    - <span data-ttu-id="5ac3b-231">Muestra tarea de delegado</span><span class="sxs-lookup"><span data-stu-id="5ac3b-231">Show delegate task</span></span>
    - <span data-ttu-id="5ac3b-232">Mostar la tarea de recuperación</span><span class="sxs-lookup"><span data-stu-id="5ac3b-232">Show recall task</span></span>
    - <span data-ttu-id="5ac3b-233">Mostrar tarea de rechazo</span><span class="sxs-lookup"><span data-stu-id="5ac3b-233">Show reject task</span></span>
    - <span data-ttu-id="5ac3b-234">Mostrar tarea de finalización de solicitud</span><span class="sxs-lookup"><span data-stu-id="5ac3b-234">Show request completion task</span></span>
    - <span data-ttu-id="5ac3b-235">Mostrar tarea de reenvío</span><span class="sxs-lookup"><span data-stu-id="5ac3b-235">Show resubmit task</span></span>

10. <span data-ttu-id="5ac3b-236">Haga clic en **Listo** para salir del modo de edición.</span><span class="sxs-lookup"><span data-stu-id="5ac3b-236">Click **Done** to exit edit mode.</span></span>
11. <span data-ttu-id="5ac3b-237">Haga clic en **Atrás** y, a continuación, **Listo** para salir del espacio de trabajo</span><span class="sxs-lookup"><span data-stu-id="5ac3b-237">Click **Back** and then **Done** to exit the workspace</span></span>
12. <span data-ttu-id="5ac3b-238">Haga clic en **Publicar espacio de trabajo** para guardar el trabajo.</span><span class="sxs-lookup"><span data-stu-id="5ac3b-238">Click **Publish workspace** to save your work.</span></span>
13. <span data-ttu-id="5ac3b-239">Habilite **Mostrar total factura en lista de facturas de proveedor pendiente** en los parámetros de proveedores desde **Factura**.</span><span class="sxs-lookup"><span data-stu-id="5ac3b-239">Enable **Display invoice total on pending vendor invoices list** in accounts payable parameters form under **Invoice**.</span></span> <span data-ttu-id="5ac3b-240">Tenga en cuenta que, al habilitar este parámetro, los totales de las facturas se calcularán para mostrarse en la página de la lista de facturas de proveedor pendientes.</span><span class="sxs-lookup"><span data-stu-id="5ac3b-240">Note that, only by enabling this parameter, invoice totals will be calculated to be displayed on the pending vendor invoices list page.</span></span> <span data-ttu-id="5ac3b-241">Esta es una nueva capacidad que forma parte de la revisión 3208224 del requisito previo.</span><span class="sxs-lookup"><span data-stu-id="5ac3b-241">This is a new capability as part of the pre-requisite hot fix 3208224.</span></span>

### <a name="vendor-invoice-details"></a><span data-ttu-id="5ac3b-242">Detalles de la factura de proveedor</span><span class="sxs-lookup"><span data-stu-id="5ac3b-242">Vendor invoice details</span></span>

<span data-ttu-id="5ac3b-243">Para diseñar la página de detalles de la factura para móvil, use la página **VendMobileInvoiceHeaderDetails** en Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="5ac3b-243">To design the invoice details page for mobile, use the **VendMobileInvoiceHeaderDetails** page in Finance and Operations.</span></span> <span data-ttu-id="5ac3b-244">Tenga en cuenta que, en función del número de facturas que tiene en el sistema, esta página muestra la factura más antigua (la factura que se creó primero).</span><span class="sxs-lookup"><span data-stu-id="5ac3b-244">Note that, depending on the number of invoices that you have in your system, this page shows the oldest invoice (the invoice that was created first).</span></span> <span data-ttu-id="5ac3b-245">Para buscar una factura específica, utilice el filtro a la izquierda.</span><span class="sxs-lookup"><span data-stu-id="5ac3b-245">To find a specific invoice, you can use the filter on the left.</span></span> <span data-ttu-id="5ac3b-246">Sin embargo, no se requiere una factura concreta para este ejemplo.</span><span class="sxs-lookup"><span data-stu-id="5ac3b-246">However, we don’t require a specific invoice for this example.</span></span> <span data-ttu-id="5ac3b-247">Simplemente requerimos algunos datos de la factura para que podamos diseñar la página para dispositivos móviles.</span><span class="sxs-lookup"><span data-stu-id="5ac3b-247">We just require some invoice data so that we can design the mobile page.</span></span> <span data-ttu-id="5ac3b-248">[![Página del flujo de trabajo](./media/mobile-invoice-approvals04-1024x425.png)](./media/mobile-invoice-approvals04.png)</span><span class="sxs-lookup"><span data-stu-id="5ac3b-248">[![Workflow page](./media/mobile-invoice-approvals04-1024x425.png)](./media/mobile-invoice-approvals04.png)</span></span>

1. <span data-ttu-id="5ac3b-249">En la dirección URL de Finance and Operations, sustituya el nombre del elemento de menú con **VendMobileInvoiceHeaderDetails** para abrir el formulario</span><span class="sxs-lookup"><span data-stu-id="5ac3b-249">In the Finance and Operations URL, replace the name of the menu item with **VendMobileInvoiceHeaderDetails** to open the form</span></span>
2. <span data-ttu-id="5ac3b-250">Abra el diseñador para aplicaciones móviles desde el botón **Configuración** (engranaje).</span><span class="sxs-lookup"><span data-stu-id="5ac3b-250">Open the mobile designer from the **Settings** (gear) button.</span></span>
3. <span data-ttu-id="5ac3b-251">Haga clic en el botón **Editar** para iniciar el modo de edición en el espacio de trabajo.</span><span class="sxs-lookup"><span data-stu-id="5ac3b-251">Click the **Edit** button to start edit mode in the workspace.</span></span>
4. <span data-ttu-id="5ac3b-252">Seleccione la página **Mis facturas de proveedor** que ha creado antes y haga clic en **Editar**.</span><span class="sxs-lookup"><span data-stu-id="5ac3b-252">Select the **My vendor invoices** page that you created earlier, and then click **Edit**.</span></span>
5. <span data-ttu-id="5ac3b-253">En los la ficha **Campos**, haga clic en el encabezado de columna **Cuadrícula**.</span><span class="sxs-lookup"><span data-stu-id="5ac3b-253">On the **Fields** tab, click the **Grid** column heading.</span></span>
6. <span data-ttu-id="5ac3b-254">Haga clic en **Propiedades &gt; Agregar página**.</span><span class="sxs-lookup"><span data-stu-id="5ac3b-254">Click **Properties &gt; Add page**.</span></span> <span data-ttu-id="5ac3b-255">**Nota:** Al hacer clic en el encabezado de **Cuadrícula** y agregar una página, la relación con la página de detalles se establece automáticamente.</span><span class="sxs-lookup"><span data-stu-id="5ac3b-255">**Note:** When you click the **Grid** heading and add a page, the relationship with the details page is established automatically.</span></span>
7. <span data-ttu-id="5ac3b-256">Especifique un título de la página, por ejemplo **Detalles de la factura** y una descripción como **Ver detalles de línea y encabezado de la factura**.</span><span class="sxs-lookup"><span data-stu-id="5ac3b-256">Enter a page title, such as **Invoice details**, and a description, such as **View invoice header and line details**.</span></span>
8. <span data-ttu-id="5ac3b-257">Haga clic en **Seleccionar campos**.</span><span class="sxs-lookup"><span data-stu-id="5ac3b-257">Click **Select fields**.</span></span> <span data-ttu-id="5ac3b-258">Tenga en cuenta que el orden en que se agrega es el orden en que los campos se mostrarán al usuario final.</span><span class="sxs-lookup"><span data-stu-id="5ac3b-258">Note that, the order in which you add is the order in which the fields will be displayed to the end user.</span></span> <span data-ttu-id="5ac3b-259">La única forma de cambiar orden de los campos es volviendo a seleccionar todos los campos.</span><span class="sxs-lookup"><span data-stu-id="5ac3b-259">The only way to change the ordering of the fields will be by re-selecting all the fields.</span></span> 
9. <span data-ttu-id="5ac3b-260">Agregue los siguientes campos desde el encabezado, según los requisitos para esta situación:</span><span class="sxs-lookup"><span data-stu-id="5ac3b-260">Add the following fields from the header, based on the requirements for this scenario:</span></span>
   - <span data-ttu-id="5ac3b-261">Nombre del proveedor</span><span class="sxs-lookup"><span data-stu-id="5ac3b-261">Vendor name</span></span>
   - <span data-ttu-id="5ac3b-262">Total de la factura</span><span class="sxs-lookup"><span data-stu-id="5ac3b-262">Invoice total</span></span>
   - <span data-ttu-id="5ac3b-263">Cuenta de facturación</span><span class="sxs-lookup"><span data-stu-id="5ac3b-263">Invoice account</span></span>
   - <span data-ttu-id="5ac3b-264">Número de factura</span><span class="sxs-lookup"><span data-stu-id="5ac3b-264">Invoice number</span></span>
   - <span data-ttu-id="5ac3b-265">Fecha de la factura</span><span class="sxs-lookup"><span data-stu-id="5ac3b-265">Invoice date</span></span>
   - <span data-ttu-id="5ac3b-266">Descripción de factura</span><span class="sxs-lookup"><span data-stu-id="5ac3b-266">Invoice description</span></span>
   - <span data-ttu-id="5ac3b-267">Fecha de vencimiento</span><span class="sxs-lookup"><span data-stu-id="5ac3b-267">Due date</span></span>
   - <span data-ttu-id="5ac3b-268">Divisa de la factura</span><span class="sxs-lookup"><span data-stu-id="5ac3b-268">Invoice currency</span></span>

10. <span data-ttu-id="5ac3b-269">Agregue los siguientes campos en la cuadrícula de las líneas en la página:</span><span class="sxs-lookup"><span data-stu-id="5ac3b-269">Add the following fields from the lines grid on the page:</span></span>
    - <span data-ttu-id="5ac3b-270">Categoría de compras</span><span class="sxs-lookup"><span data-stu-id="5ac3b-270">Procurement category</span></span>
    - <span data-ttu-id="5ac3b-271">Cantidad</span><span class="sxs-lookup"><span data-stu-id="5ac3b-271">Quantity</span></span>
    - <span data-ttu-id="5ac3b-272">Precio unitario</span><span class="sxs-lookup"><span data-stu-id="5ac3b-272">Unit price</span></span>
    - <span data-ttu-id="5ac3b-273">Importe neto de línea</span><span class="sxs-lookup"><span data-stu-id="5ac3b-273">Line net amount</span></span>
    - <span data-ttu-id="5ac3b-274">Importe de la declaración de IRPF</span><span class="sxs-lookup"><span data-stu-id="5ac3b-274">1099 amount</span></span>

11. <span data-ttu-id="5ac3b-275">Después de agregar todos los campos de los dos pasos anteriores, haga clic en **Listo**.</span><span class="sxs-lookup"><span data-stu-id="5ac3b-275">After all the fields from the previous two steps have been added, click **Done**.</span></span> <span data-ttu-id="5ac3b-276">La página deben asemejarse a la siguiente ilustración.</span><span class="sxs-lookup"><span data-stu-id="5ac3b-276">The page must resemble the following illustration.</span></span>
    <span data-ttu-id="5ac3b-277">[![Página después de haber agregado campos](./media/mobile-invoice-approvals05.png)](./media/mobile-invoice-approvals05.png)</span><span class="sxs-lookup"><span data-stu-id="5ac3b-277">[![Page after fields are added](./media/mobile-invoice-approvals05.png)](./media/mobile-invoice-approvals05.png)</span></span>
12. <span data-ttu-id="5ac3b-278">Haga clic en **Listo** para salir del modo de edición.</span><span class="sxs-lookup"><span data-stu-id="5ac3b-278">Click **Done** to exit edit mode.</span></span>
13. <span data-ttu-id="5ac3b-279">Haga clic en **Atrás** y, a continuación, **Listo** para salir del espacio de trabajo</span><span class="sxs-lookup"><span data-stu-id="5ac3b-279">Click **Back** and then **Done** to exit the workspace</span></span>
14. <span data-ttu-id="5ac3b-280">Haga clic en **Publicar espacio de trabajo** para guardar el trabajo</span><span class="sxs-lookup"><span data-stu-id="5ac3b-280">Click **Publish workspace** to save your work</span></span>

### <a name="workflow-actions"></a><span data-ttu-id="5ac3b-281">Acciones de flujo de trabajo</span><span class="sxs-lookup"><span data-stu-id="5ac3b-281">Workflow actions</span></span>

<span data-ttu-id="5ac3b-282">Para agregar acciones de flujo, use la página **VendMobileInvoiceHeaderDetails** en Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="5ac3b-282">To add workflow actions, use the **VendMobileInvoiceHeaderDetails** page in Finance and Operations.</span></span> <span data-ttu-id="5ac3b-283">Para abrir esta página, reemplace el nombre del elemento de menú de la dirección URL, como lo hizo anteriormente.</span><span class="sxs-lookup"><span data-stu-id="5ac3b-283">To open this page, replace the name of the menu item in the URL, as you did earlier.</span></span> <span data-ttu-id="5ac3b-284">Después, abra el diseñador para aplicaciones móviles desde el botón **Configuración** (engranaje).</span><span class="sxs-lookup"><span data-stu-id="5ac3b-284">Then open the mobile designer from the **Settings** (gear) button.</span></span> <span data-ttu-id="5ac3b-285">Siga estos pasos para agregar acciones de flujo de trabajo en la página de detalles.</span><span class="sxs-lookup"><span data-stu-id="5ac3b-285">Follow these steps to add workflow actions on the details page.</span></span> <span data-ttu-id="5ac3b-286">Debe tener facturas asignadas y que tengan un estado apropiado para que las acciones del flujo de trabajo para las que va a realizar el diseño estén disponibles.</span><span class="sxs-lookup"><span data-stu-id="5ac3b-286">You must have invoices assigned to you that are in the appropriate state to make the workflow actions available to you that you are going to design for.</span></span>

#### <a name="record-workflow-actions"></a><span data-ttu-id="5ac3b-287">Registrar acciones de flujo de trabajo</span><span class="sxs-lookup"><span data-stu-id="5ac3b-287">Record workflow actions</span></span>
1.  <span data-ttu-id="5ac3b-288">Haga clic en el botón **Editar** para iniciar el modo de edición en el espacio de trabajo.</span><span class="sxs-lookup"><span data-stu-id="5ac3b-288">Click the **Edit** button to start edit mode in the workspace.</span></span>
2.  <span data-ttu-id="5ac3b-289">Seleccione la página **Mis facturas de proveedor** que ha creado antes y haga clic en **Editar**.</span><span class="sxs-lookup"><span data-stu-id="5ac3b-289">Select the **Invoice details** page that you created earlier, and then click **Edit**.</span></span>
3.  <span data-ttu-id="5ac3b-290">En la ficha **Acciones**, haga clic en **Agregar acción**.</span><span class="sxs-lookup"><span data-stu-id="5ac3b-290">On the **Actions** tab, click **Add action**.</span></span>
4.  <span data-ttu-id="5ac3b-291">Especifique un título de acción, como **Aprobar** y una descripción como **Aprobar factura**.</span><span class="sxs-lookup"><span data-stu-id="5ac3b-291">Enter an action title, such as **Approve**, and a description, such as **Approve invoice**.</span></span> <span data-ttu-id="5ac3b-292">Tenga en cuenta que el título de la acción que escriba aquí se convierte en el nombre de la acción que se muestra al usuario en la aplicación móvil.</span><span class="sxs-lookup"><span data-stu-id="5ac3b-292">Note that the action title that you enter here becomes the name of the action that is shown to the user in the mobile app.</span></span>
5.  <span data-ttu-id="5ac3b-293">Haga clic en **Listo**.</span><span class="sxs-lookup"><span data-stu-id="5ac3b-293">Click **Done**.</span></span>
6.  <span data-ttu-id="5ac3b-294">Haga clic en **Seleccionar campos**.</span><span class="sxs-lookup"><span data-stu-id="5ac3b-294">Click **Select fields**.</span></span>
7.  <span data-ttu-id="5ac3b-295">Realice el proceso del flujo de trabajo en la página **VendMobileInvoiceHeaderDetails** y complete la acción que se quería registrar.</span><span class="sxs-lookup"><span data-stu-id="5ac3b-295">Go through the workflow process on the **VendMobileInvoiceHeaderDetails** page, and complete the action that you wanted to record.</span></span> <span data-ttu-id="5ac3b-296">Asegúrese de especificar los comentarios del flujo de trabajo durante este proceso, de forma que se incluya un campo de comentarios en la experiencia móvil.</span><span class="sxs-lookup"><span data-stu-id="5ac3b-296">Make sure that you enter workflow comments during this process, so that a comments field is also included in the mobile experience.</span></span>
8.  <span data-ttu-id="5ac3b-297">Una vez que se ejecute la acción del flujo de trabajo, haga clic en **Listo** para completar la tarea Seleccionar campos.</span><span class="sxs-lookup"><span data-stu-id="5ac3b-297">After the workflow action is run, click **Done** to complete the Select fields task.</span></span>
9.  <span data-ttu-id="5ac3b-298">Haga clic en **Listo** para salir del modo de edición.</span><span class="sxs-lookup"><span data-stu-id="5ac3b-298">Click **Done** to exit edit mode.</span></span>
10. <span data-ttu-id="5ac3b-299">Haga clic en **Atrás** y, a continuación, **Listo** para salir del espacio de trabajo</span><span class="sxs-lookup"><span data-stu-id="5ac3b-299">Click **Back** and then **Done** to exit the workspace</span></span>
11. <span data-ttu-id="5ac3b-300">Haga clic en **Publicar espacio de trabajo** para guardar el trabajo</span><span class="sxs-lookup"><span data-stu-id="5ac3b-300">Click **Publish workspace** to save your work</span></span>
12. <span data-ttu-id="5ac3b-301">Repita los pasos anteriores para registrar todas las acciones del flujo de trabajo necesarias.</span><span class="sxs-lookup"><span data-stu-id="5ac3b-301">Repeat the previous steps to record all the required workflow actions.</span></span> 

#### <a name="create-a-js-file"></a><span data-ttu-id="5ac3b-302">Crear un archivo .js</span><span class="sxs-lookup"><span data-stu-id="5ac3b-302">Create a .js file</span></span>
1. <span data-ttu-id="5ac3b-303">Abra el Bloc de notas o Microsoft Visual Studio, y pegue el código siguiente.</span><span class="sxs-lookup"><span data-stu-id="5ac3b-303">Open Notepad or Microsoft Visual Studio, and paste the following code.</span></span> <span data-ttu-id="5ac3b-304">Guarde el archivo como archivo .js.</span><span class="sxs-lookup"><span data-stu-id="5ac3b-304">Save the file as a .js file.</span></span> <span data-ttu-id="5ac3b-305">Este código hace lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="5ac3b-305">This code does the following:</span></span>
    - <span data-ttu-id="5ac3b-306">Oculta las columnas adicionales relacionadas con el flujo de trabajo adicionales que agregamos anteriormente en la página de la lista para dispositivos móviles.</span><span class="sxs-lookup"><span data-stu-id="5ac3b-306">It hides the extra workflow-related columns that we added earlier on the mobile list page.</span></span> <span data-ttu-id="5ac3b-307">Agregamos estas columnas de modo que la aplicación tenga información en contexto y se pueda ir al paso siguiente.</span><span class="sxs-lookup"><span data-stu-id="5ac3b-307">We added these columns so that the app has that information in context and can do the next step.</span></span>
    - <span data-ttu-id="5ac3b-308">Según el paso del flujo de trabajo que está activo, aplica la lógica para mostrar solo esas acciones.</span><span class="sxs-lookup"><span data-stu-id="5ac3b-308">Based on the workflow step that is active, it applies logic to show only those actions.</span></span>

> [!NOTE]
> <span data-ttu-id="5ac3b-309">El nombre de las páginas y otros controles del código de JS deberían ser los mismos que los nombres en el espacio de trabajo.</span><span class="sxs-lookup"><span data-stu-id="5ac3b-309">The name of the pages and other controls in the code must be the same as the names in the workspace.</span></span>

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

2.  <span data-ttu-id="5ac3b-310">Cargar el archivo del código en el espacio de trabajo seleccionando la ficha **Lógica**</span><span class="sxs-lookup"><span data-stu-id="5ac3b-310">Upload the code file to the workspace by selecting the **Logic** tab</span></span>
3.  <span data-ttu-id="5ac3b-311">Haga clic en **Listo** para salir del modo de edición.</span><span class="sxs-lookup"><span data-stu-id="5ac3b-311">Click **Done** to exit edit mode.</span></span>
4.  <span data-ttu-id="5ac3b-312">Haga clic en **Atrás** y, a continuación, **Listo** para salir del espacio de trabajo</span><span class="sxs-lookup"><span data-stu-id="5ac3b-312">Click **Back** and then **Done** to exit the workspace</span></span>
5.  <span data-ttu-id="5ac3b-313">Haga clic en **Publicar espacio de trabajo** para guardar el trabajo</span><span class="sxs-lookup"><span data-stu-id="5ac3b-313">Click **Publish workspace** to save your work</span></span>

### <a name="vendor-invoice-attachments"></a><span data-ttu-id="5ac3b-314">Datos adjuntos de la factura de proveedor</span><span class="sxs-lookup"><span data-stu-id="5ac3b-314">Vendor invoice attachments</span></span>

1. <span data-ttu-id="5ac3b-315">Haga clic en el botón **Configuración** (engranaje) en la parte superior derecha de la página y, a continuación, haga clic en **Aplicación móvil**</span><span class="sxs-lookup"><span data-stu-id="5ac3b-315">Click the **Settings** (gear) button in the upper right of the page, and then click **Mobile app**</span></span>
2. <span data-ttu-id="5ac3b-316">Haga clic en el botón **Editar** para iniciar el modo de edición en el espacio de trabajo.</span><span class="sxs-lookup"><span data-stu-id="5ac3b-316">Click the **Edit** button to start edit mode in the workspace.</span></span>
3. <span data-ttu-id="5ac3b-317">Seleccione la página <strong>Detalles de la factura \*\*que ha creado antes y haga clic en \*\*Editar</strong>.</span><span class="sxs-lookup"><span data-stu-id="5ac3b-317">Select the <strong>Invoice details \*\*page that you created earlier, and then click \*\*Edit</strong>.</span></span>
4. <span data-ttu-id="5ac3b-318">Establezca la opción **Administración de documentos** en **Sí** como se indica a continuación.</span><span class="sxs-lookup"><span data-stu-id="5ac3b-318">Set the **Document management** option to **Yes** as shown below.</span></span> <span data-ttu-id="5ac3b-319">**Nota:** Si no hay requisitos para mostrar los datos adjuntos en el dispositivo móvil, puede dejar esta opción establecida en **No**, que es la configuración predeterminada.</span><span class="sxs-lookup"><span data-stu-id="5ac3b-319">**Note:** If there are no requirements to show attachments on the mobile device, you can leave this option set to **No**, which is the default setting.</span></span>
   <span data-ttu-id="5ac3b-320">![Administración de documentos](./media/docmanagement-216x300.png)</span><span class="sxs-lookup"><span data-stu-id="5ac3b-320">![Document management](./media/docmanagement-216x300.png)</span></span>
5. <span data-ttu-id="5ac3b-321">Haga clic en **Listo** para salir del modo de edición.</span><span class="sxs-lookup"><span data-stu-id="5ac3b-321">Click **Done** to exit edit mode.</span></span>
6. <span data-ttu-id="5ac3b-322">Haga clic en **Atrás** y, a continuación, **Listo** para salir del espacio de trabajo</span><span class="sxs-lookup"><span data-stu-id="5ac3b-322">Click **Back** and then **Done** to exit the workspace</span></span>
7. <span data-ttu-id="5ac3b-323">Haga clic en **Publicar espacio de trabajo** para guardar el trabajo</span><span class="sxs-lookup"><span data-stu-id="5ac3b-323">Click **Publish workspace** to save your work</span></span>

### <a name="vendor-invoice-line-distributions"></a><span data-ttu-id="5ac3b-324">Distribuciones de línea de la factura de proveedor</span><span class="sxs-lookup"><span data-stu-id="5ac3b-324">Vendor invoice line distributions</span></span>

<span data-ttu-id="5ac3b-325">Los requisitos para este escenario confirman que solo habrá distribuciones a nivel de línea y que las facturas serán siempre de una línea.</span><span class="sxs-lookup"><span data-stu-id="5ac3b-325">The requirements for this scenario confirm that there will be only line-level distributions, and that an invoice will always have only one line.</span></span> <span data-ttu-id="5ac3b-326">Puesto que este escenario es sencillo, la experiencia del usuario en el dispositivo móvil también debe ser lo suficientemente sencilla para que el usuario no tenga que buscar en profundidad para ver las distribuciones.</span><span class="sxs-lookup"><span data-stu-id="5ac3b-326">Because this scenario is simple, the user experience on the mobile device must also be simple enough that the user doesn’t have to drill down several levels to view the distributions.</span></span> <span data-ttu-id="5ac3b-327">Las facturas de proveedor de Finance and Operations incluyen la opción para mostrar todas las distribuciones del encabezado de la factura.</span><span class="sxs-lookup"><span data-stu-id="5ac3b-327">Vendor invoices in Finance and Operations include the option of showing all distributions from the invoice header.</span></span> <span data-ttu-id="5ac3b-328">Esta experiencia es lo que necesitamos para el escenario de dispositivos móviles.</span><span class="sxs-lookup"><span data-stu-id="5ac3b-328">This experience is what we need for the mobile scenario.</span></span> <span data-ttu-id="5ac3b-329">Por lo tanto, utilizaremos la página **VendMobileInvoiceAllDistributionTree** para diseñar esta parte del escenario móvil.</span><span class="sxs-lookup"><span data-stu-id="5ac3b-329">Therefore, we will use the **VendMobileInvoiceAllDistributionTree** page to design this part of the mobile scenario.</span></span> 

> [!NOTE] 
> <span data-ttu-id="5ac3b-330">Conocer los requisitos nos ayuda a decidir qué página determinada se va utilizar y exactamente cómo optimizar la experiencia móvil del usuario cuando diseñamos el escenario.</span><span class="sxs-lookup"><span data-stu-id="5ac3b-330">Knowing the requirements helps us decide which specific page to use and how exactly to optimize the mobile experience for the user when we design the scenario.</span></span> <span data-ttu-id="5ac3b-331">En el segundo escenario, utilizaremos una página diferente para mostrar las distribuciones, ya los requisitos para esa situación son diferentes.</span><span class="sxs-lookup"><span data-stu-id="5ac3b-331">In the second scenario, we will use a different page to show the distributions, because the requirements for that scenario differ.</span></span>

1.  <span data-ttu-id="5ac3b-332">En la dirección URL, reemplace el nombre del elemento de menú tal como hizo antes.</span><span class="sxs-lookup"><span data-stu-id="5ac3b-332">In the URL, replace the name of the menu item, as you did before.</span></span> <span data-ttu-id="5ac3b-333">La página que aparece debe asemejarse a la siguiente ilustración.</span><span class="sxs-lookup"><span data-stu-id="5ac3b-333">The page that appears should resemble the following illustration.</span></span>
<span data-ttu-id="5ac3b-334">[![Página de todas las distribuciones](./media/mobile-invoice-approvals06.png)](./media/mobile-invoice-approvals06.png)</span><span class="sxs-lookup"><span data-stu-id="5ac3b-334">[![All distributions page](./media/mobile-invoice-approvals06.png)](./media/mobile-invoice-approvals06.png)</span></span>
2.  <span data-ttu-id="5ac3b-335">Abra el diseñador para aplicaciones móviles desde el botón **Configuración** (engranaje).</span><span class="sxs-lookup"><span data-stu-id="5ac3b-335">Open the mobile designer from the **Settings** (gear) button.</span></span>
3.  <span data-ttu-id="5ac3b-336">Haga clic en el botón **Editar** para iniciar el modo de edición en el espacio de trabajo.</span><span class="sxs-lookup"><span data-stu-id="5ac3b-336">Click the **Edit** button to start edit mode in the workspace.</span></span> <span data-ttu-id="5ac3b-337">**Nota:** Verá dos nuevas páginas que se han creado automáticamente.</span><span class="sxs-lookup"><span data-stu-id="5ac3b-337">**Note:** You will see that two new pages were created automatically.</span></span> <span data-ttu-id="5ac3b-338">El sistema crea estas páginas porque ha activado la gestión de documentos en la sección anterior.</span><span class="sxs-lookup"><span data-stu-id="5ac3b-338">The system creates these pages, because you turned on document management in the previous section.</span></span> <span data-ttu-id="5ac3b-339">Puede omitir estas páginas nuevas.</span><span class="sxs-lookup"><span data-stu-id="5ac3b-339">You can ignore these new pages.</span></span>
4.  <span data-ttu-id="5ac3b-340">Haga clic en **Agregar página**.</span><span class="sxs-lookup"><span data-stu-id="5ac3b-340">Click **Add page**.</span></span>
5.  <span data-ttu-id="5ac3b-341">Especifique un título para la página como **Ver contabilidad** y una descripción como **Ver contabilidad para la factura**.</span><span class="sxs-lookup"><span data-stu-id="5ac3b-341">Enter a page title, such as **View accounting**, and a description, such as **View accounting for the invoice**.</span></span>
6.  <span data-ttu-id="5ac3b-342">Haga clic en **Listo**.</span><span class="sxs-lookup"><span data-stu-id="5ac3b-342">Click **Done**.</span></span>
7.  <span data-ttu-id="5ac3b-343">En la ficha **Campos**, haga clic en **Seleccionar campos**, seleccione los siguientes campos de la página de las distribuciones, y haga clic en **Listo**:</span><span class="sxs-lookup"><span data-stu-id="5ac3b-343">On the **Fields** tab, click **Select fields**, select the following fields from the distributions page, and then click **Done**:</span></span>
    1.  <span data-ttu-id="5ac3b-344">Importe</span><span class="sxs-lookup"><span data-stu-id="5ac3b-344">Amount</span></span>
    2.  <span data-ttu-id="5ac3b-345">Divisa</span><span class="sxs-lookup"><span data-stu-id="5ac3b-345">Currency</span></span>
    3.  <span data-ttu-id="5ac3b-346">Cuenta contable</span><span class="sxs-lookup"><span data-stu-id="5ac3b-346">Ledger account</span></span>

    > [!NOTE] 
    > <span data-ttu-id="5ac3b-347">No seleccionamos la columna **Descripción** en la cuadrícula de las distribuciones debido a que los requisitos para este escenario confirmaron que el precio total es el único importe para el que habrá distribuciones.</span><span class="sxs-lookup"><span data-stu-id="5ac3b-347">We didn’t select the **Description** column from the distributions grid, because the requirements for this scenario confirmed that the extended price is the only amount that there will be distributions for.</span></span> <span data-ttu-id="5ac3b-348">Por tanto, el usuario no necesitará otro campo para determinar el tipo de importe para el que es la distribución.</span><span class="sxs-lookup"><span data-stu-id="5ac3b-348">Therefore, the user won’t require another field to determine the amount type that the distribution is for.</span></span> <span data-ttu-id="5ac3b-349">Sin embargo, en el escenario siguiente, **utilizaremos** esta información porque los requisitos para esa situación especifican que otros tipos de importe tienen distribuciones (por ejemplo, impuestos).</span><span class="sxs-lookup"><span data-stu-id="5ac3b-349">However, in the next scenario, we **will** use this information, because the requirements for that scenario specify that other amount types have distributions (for example, sales tax).</span></span>
8.  <span data-ttu-id="5ac3b-350">Haga clic en **Listo** para salir del modo de edición.</span><span class="sxs-lookup"><span data-stu-id="5ac3b-350">Click **Done** to exit edit mode.</span></span>
9.  <span data-ttu-id="5ac3b-351">Haga clic en **Atrás** y, a continuación, **Listo** para salir del espacio de trabajo</span><span class="sxs-lookup"><span data-stu-id="5ac3b-351">Click **Back** and then **Done** to exit the workspace</span></span>
10. <span data-ttu-id="5ac3b-352">Haga clic en **Publicar espacio de trabajo** para guardar el trabajo</span><span class="sxs-lookup"><span data-stu-id="5ac3b-352">Click **Publish workspace** to save your work</span></span>

> [!NOTE] 
> <span data-ttu-id="5ac3b-353">Nota: La página para dispositivos móviles **Ver contabilidad** no está vinculada actualmente a ninguna página para dispositivos móviles que hemos diseñado hasta el momento.</span><span class="sxs-lookup"><span data-stu-id="5ac3b-353">The **View accounting** mobile page isn’t currently linked to any of the mobile pages that we have designed so far.</span></span> <span data-ttu-id="5ac3b-354">Dado que el usuario debe poder navegar a la página **Ver contabilidad** desde la página **Detalles de la factura** en el dispositivo móvil, debemos proporcionar navegación desde la página **Detalles de la factura** hasta la página **Ver contabilidad**.</span><span class="sxs-lookup"><span data-stu-id="5ac3b-354">Because the user should be able to navigate to the **View accounting** page from the **Invoice details** page on the mobile device, we must provide navigation from the **Invoice details** page to the **View accounting** page.</span></span> <span data-ttu-id="5ac3b-355">Establecemos esta navegación mediante el uso de lógica JavaScript adicional.</span><span class="sxs-lookup"><span data-stu-id="5ac3b-355">We establish this navigation by using additional logic via JavaScript.</span></span>

1.  <span data-ttu-id="5ac3b-356">Abre el archivo .js que ha creado anteriormente y agregue las líneas que se resaltan en el código siguiente.</span><span class="sxs-lookup"><span data-stu-id="5ac3b-356">Open the .js file that you created earlier, and add the lines that are highlighted in the following code.</span></span> <span data-ttu-id="5ac3b-357">Este código hace dos cosas:</span><span class="sxs-lookup"><span data-stu-id="5ac3b-357">This code does two things:</span></span>
    1.  <span data-ttu-id="5ac3b-358">Ayuda a garantizar que los usuarios no pueden navegar directamente desde el espacio de trabajo a la página **Ver contabilidad**.</span><span class="sxs-lookup"><span data-stu-id="5ac3b-358">It helps guarantee that users can’t navigate directly from the workspace to the **View accounting** page.</span></span>
    2.  <span data-ttu-id="5ac3b-359">Establece un control de navegación desde la página **Detalles de la factura** hasta la página **Ver contabilidad**.</span><span class="sxs-lookup"><span data-stu-id="5ac3b-359">It establishes a navigation control from the **Invoice details** page to the **View accounting** page.</span></span>

> [!NOTE] 
> <span data-ttu-id="5ac3b-360">El nombre de las páginas y otros controles del código de JS deberían ser los mismos que los nombres en el espacio de trabajo.</span><span class="sxs-lookup"><span data-stu-id="5ac3b-360">The name of the pages and other controls in the code must be the same as the names in the workspace.</span></span>

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

2.  <span data-ttu-id="5ac3b-361">Cargar el archivo del código en el espacio de trabajo seleccionando la ficha **Lógica** para sobrescribir el código anterior</span><span class="sxs-lookup"><span data-stu-id="5ac3b-361">Upload the code file to the workspace by selecting the **Logic** tab to overwrite the previous code</span></span>
3.  <span data-ttu-id="5ac3b-362">Haga clic en **Listo** para salir del modo de edición.</span><span class="sxs-lookup"><span data-stu-id="5ac3b-362">Click **Done** to exit edit mode.</span></span>
4.  <span data-ttu-id="5ac3b-363">Haga clic en **Atrás** y, a continuación, **Listo** para salir del espacio de trabajo</span><span class="sxs-lookup"><span data-stu-id="5ac3b-363">Click **Back** and then **Done** to exit the workspace</span></span>
5.  <span data-ttu-id="5ac3b-364">Haga clic en **Publicar espacio de trabajo** para guardar el trabajo</span><span class="sxs-lookup"><span data-stu-id="5ac3b-364">Click **Publish workspace** to save your work</span></span>

### <a name="validation"></a><span data-ttu-id="5ac3b-365">Validación</span><span class="sxs-lookup"><span data-stu-id="5ac3b-365">Validation</span></span>

<span data-ttu-id="5ac3b-366">Desde el dispositivo móvil, abra la aplicación y conéctese a la instancia de su instancia de Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="5ac3b-366">From your mobile device, open the app, and connect to your Finance and Operations instance.</span></span> <span data-ttu-id="5ac3b-367">Asegúrese de tener haber iniciado sesión en la empresa donde tenga asignadas las facturas de proveedores para revisión.</span><span class="sxs-lookup"><span data-stu-id="5ac3b-367">Make sure that you sign in to the company where vendor invoices are assigned to you for review.</span></span> <span data-ttu-id="5ac3b-368">Debería poder realizar las acciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="5ac3b-368">You should be able to perform the following actions:</span></span>

-   <span data-ttu-id="5ac3b-369">Ver el espacio de trabajo **Mis aprobaciones**.</span><span class="sxs-lookup"><span data-stu-id="5ac3b-369">See the **My approvals** workspace.</span></span>
-   <span data-ttu-id="5ac3b-370">Explorar en profundidad el espacio de trabajo **Mis aprobaciones** y ver la página **Mis facturas de proveedor**.</span><span class="sxs-lookup"><span data-stu-id="5ac3b-370">Drill into the **My approvals** workspace and see the **My vendor invoices** page.</span></span>
-   <span data-ttu-id="5ac3b-371">Explorar en profundidad la página **Mis facturas de proveedores** y ver la lista de facturas que se le han asignado.</span><span class="sxs-lookup"><span data-stu-id="5ac3b-371">Drill into the **My vendor invoices** page and see the list of invoices that are assigned to you.</span></span>
-   <span data-ttu-id="5ac3b-372">Explorar en profundidad una de las facturas y ver los detalles del encabezado y la línea de la factura.</span><span class="sxs-lookup"><span data-stu-id="5ac3b-372">Drill into one of the invoices, and see the invoice header details and line details.</span></span>
-   <span data-ttu-id="5ac3b-373">En la página de detalles, ver un vínculo a los datos adjuntos y utilizarlo para navegar a la lista de datos adjuntos y verlos.</span><span class="sxs-lookup"><span data-stu-id="5ac3b-373">On the details page, see a link to attachments, and use this link to navigate to the attachments list and view the attachments.</span></span>
-   <span data-ttu-id="5ac3b-374">En la página de detalles, ver un vínculo a la página **Ver contabilidad** y utilizarlo para navegar a la página de distribuciones y ver las distribuciones.</span><span class="sxs-lookup"><span data-stu-id="5ac3b-374">On the details page, see a link to the **View accounting** page, and use this link to navigate to the distributions page and view the distributions.</span></span>
-   <span data-ttu-id="5ac3b-375">En la página de detalles, haga clic en el menú **Acciones** de la parte inferior y realice las acciones del flujo de trabajo aplicables al paso del flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="5ac3b-375">On the details page, click the **Actions** menu at the bottom, and perform workflow actions that are applicable to the workflow step.</span></span>

## <a name="designing-a-complex-invoice-approval-scenario-for-fabrikam"></a><span data-ttu-id="5ac3b-376">Diseñar un escenario de aprobación de factoras complejo para Fabrikam</span><span class="sxs-lookup"><span data-stu-id="5ac3b-376">Designing a complex invoice approval scenario for Fabrikam</span></span>
<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="5ac3b-377">Atributo de escenario</span><span class="sxs-lookup"><span data-stu-id="5ac3b-377">Scenario attribute</span></span></th>
<th><span data-ttu-id="5ac3b-378">Respuesta</span><span class="sxs-lookup"><span data-stu-id="5ac3b-378">Answer</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="5ac3b-379">¿Qué campos del encabezado de la factura el usuario deseará ver en la experiencia móvil, y en qué pedidos?</span><span class="sxs-lookup"><span data-stu-id="5ac3b-379">What fields from the invoice header will the user want to see in the mobile experience, and in what order?</span></span></td>
<td><ol>
<li><span data-ttu-id="5ac3b-380">Nombre del proveedor</span><span class="sxs-lookup"><span data-stu-id="5ac3b-380">Vendor name</span></span></li>
<li><span data-ttu-id="5ac3b-381">Importe de la factura</span><span class="sxs-lookup"><span data-stu-id="5ac3b-381">Invoice amount</span></span></li>
<li><span data-ttu-id="5ac3b-382">Cuenta de facturación</span><span class="sxs-lookup"><span data-stu-id="5ac3b-382">Invoice account</span></span></li>
<li><span data-ttu-id="5ac3b-383">Número de factura</span><span class="sxs-lookup"><span data-stu-id="5ac3b-383">Invoice number</span></span></li>
<li><span data-ttu-id="5ac3b-384">Fecha de la factura</span><span class="sxs-lookup"><span data-stu-id="5ac3b-384">Invoice date</span></span></li>
<li><span data-ttu-id="5ac3b-385">Descripción de factura</span><span class="sxs-lookup"><span data-stu-id="5ac3b-385">Invoice description</span></span></li>
<li><span data-ttu-id="5ac3b-386">Fecha de vencimiento</span><span class="sxs-lookup"><span data-stu-id="5ac3b-386">Due date</span></span></li>
<li><span data-ttu-id="5ac3b-387">Divisa de la factura</span><span class="sxs-lookup"><span data-stu-id="5ac3b-387">Invoice currency</span></span></li>
</ol></td>
</tr>
<tr class="even">
<td><span data-ttu-id="5ac3b-388">¿Qué líneas del encabezado de la factura el usuario deseará ver en la experiencia móvil, y en qué pedidos?</span><span class="sxs-lookup"><span data-stu-id="5ac3b-388">What fields from the invoice lines will the user want to see in the mobile experience, and in what order?</span></span></td>
<td><ol>
<li><span data-ttu-id="5ac3b-389">Categoría de compras</span><span class="sxs-lookup"><span data-stu-id="5ac3b-389">Procurement category</span></span></li>
<li><span data-ttu-id="5ac3b-390">Cantidad</span><span class="sxs-lookup"><span data-stu-id="5ac3b-390">Quantity</span></span></li>
<li><span data-ttu-id="5ac3b-391">Precio unitario</span><span class="sxs-lookup"><span data-stu-id="5ac3b-391">Unit price</span></span></li>
<li><span data-ttu-id="5ac3b-392">Importe neto de línea</span><span class="sxs-lookup"><span data-stu-id="5ac3b-392">Line net amount</span></span></li>
<li><span data-ttu-id="5ac3b-393">Importe de la declaración de IRPF</span><span class="sxs-lookup"><span data-stu-id="5ac3b-393">1099 amount</span></span></li>
</ol></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="5ac3b-394">¿Cuántas líneas de factura hay en una factura?</span><span class="sxs-lookup"><span data-stu-id="5ac3b-394">How many invoice lines are there in an invoice?</span></span> <span data-ttu-id="5ac3b-395">Aplique la regla 80-20 aquí, y optimice para llegar al 80 por ciento.</span><span class="sxs-lookup"><span data-stu-id="5ac3b-395">Apply the 80-20 rule here, and optimize for the 80 percent.</span></span></td>
<td><span data-ttu-id="5ac3b-396">5</span><span class="sxs-lookup"><span data-stu-id="5ac3b-396">5</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="5ac3b-397">¿Los usuarios desearán ver las distribuciones contables (codificación de la factura) en el dispositivo móvil durante las revisiones?</span><span class="sxs-lookup"><span data-stu-id="5ac3b-397">Will users want to see accounting distributions (invoice coding) on the mobile device during reviews?</span></span></td>
<td><span data-ttu-id="5ac3b-398">Sí</span><span class="sxs-lookup"><span data-stu-id="5ac3b-398">Yes</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="5ac3b-399">¿Cuántas distribuciones contables (precio total, impuestos, cargos, etc.) hay para una línea de factura?</span><span class="sxs-lookup"><span data-stu-id="5ac3b-399">How many accounting distributions (extended price, sales tax, charges, and so on) are there for an invoice line?</span></span> <span data-ttu-id="5ac3b-400">Una vez más, aplique la regla 80-20.</span><span class="sxs-lookup"><span data-stu-id="5ac3b-400">Again, apply the 80-20 rule.</span></span></td>
<td><span data-ttu-id="5ac3b-401">Precio total: 2 Impuestos: 2 Cargos: 2</span><span class="sxs-lookup"><span data-stu-id="5ac3b-401">Extended price: 2 Sales tax: 2 Charges: 2</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="5ac3b-402">¿Las facturas también tienen distribuciones contables en el encabezado de factura?</span><span class="sxs-lookup"><span data-stu-id="5ac3b-402">Do the invoices also have accounting distributions on the invoice header?</span></span> <span data-ttu-id="5ac3b-403">En dicho caso, ¿estas distribuciones contables deben estar disponible en el dispositivo?</span><span class="sxs-lookup"><span data-stu-id="5ac3b-403">If so, should these accounting distributions be available on the device?</span></span></td>
<td><span data-ttu-id="5ac3b-404">No utilizado</span><span class="sxs-lookup"><span data-stu-id="5ac3b-404">Not used</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="5ac3b-405">¿Los usuarios desearán ver los datos adjuntos de la factura en el dispositivo?</span><span class="sxs-lookup"><span data-stu-id="5ac3b-405">Will users want to see attachments for the invoice on the device?</span></span></td>
<td><span data-ttu-id="5ac3b-406">Sí</span><span class="sxs-lookup"><span data-stu-id="5ac3b-406">Yes</span></span></td>
</tr>
</tbody>
</table>

### <a name="next-steps"></a><span data-ttu-id="5ac3b-407">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="5ac3b-407">Next steps</span></span>

<span data-ttu-id="5ac3b-408">Las variaciones siguientes se pueden realizar para el escenario 1, en función de los requisitos para el escenario 2.</span><span class="sxs-lookup"><span data-stu-id="5ac3b-408">The following variations can be done for scenario 1, based on the requirements for scenario 2.</span></span> <span data-ttu-id="5ac3b-409">Puede usar esta sección para mejorar la experiencia móvil de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="5ac3b-409">You can use this section to improve your mobile app experience.</span></span>

1.  <span data-ttu-id="5ac3b-410">Dado que habrá más líneas de factura en el escenario 2, los cambios siguientes en el diseño ayudarán a optimizar la experiencia del usuario en el dispositivo móvil:</span><span class="sxs-lookup"><span data-stu-id="5ac3b-410">Because more invoice lines are expected in scenario 2, the following changes to the design will help optimize the user experience on the mobile device:</span></span>
    1.  <span data-ttu-id="5ac3b-411">En lugar de ver las líneas de la factura en la página de detalles (como en el escenario 1), los usuarios pueden elegir ver las líneas en una página independiente para dispositivos móviles.</span><span class="sxs-lookup"><span data-stu-id="5ac3b-411">Instead of viewing invoice lines on the details page (as in scenario 1), users can choose to view lines on a separate mobile page.</span></span>
    2.  <span data-ttu-id="5ac3b-412">Dado que habrá más de una línea de factura este escenario, si la página **VendMobileInvoiceAllDistributionTree** se utiliza para diseñar la página de distribuciones para dispositivos móviles (como en el escenario 1), puede que resulte confuso para que el usuario correlacionar líneas con distribuciones.</span><span class="sxs-lookup"><span data-stu-id="5ac3b-412">Because more than one invoice line is expected in this scenario, if the **VendMobileInvoiceAllDistributionTree** page is used to design the distributions page for mobile (as in scenario 1), it might be confusing for the user to correlate lines to distributions.</span></span> <span data-ttu-id="5ac3b-413">Por lo tanto, use la página **VendMobileInvoiceLineDistributionTree** para diseñar la página de distribuciones.</span><span class="sxs-lookup"><span data-stu-id="5ac3b-413">Therefore, use the **VendMobileInvoiceLineDistributionTree** page to design the distributions page.</span></span>
    3.  <span data-ttu-id="5ac3b-414">Por ello, las distribuciones se deben mostrar en el contexto de una línea de factura en este escenario.</span><span class="sxs-lookup"><span data-stu-id="5ac3b-414">Ideally, the distributions should be shown in the context of an invoice line in this scenario.</span></span> <span data-ttu-id="5ac3b-415">Por lo tanto, asegúrese de que el usuario puede explorar en una línea para ver la página de las distribuciones.</span><span class="sxs-lookup"><span data-stu-id="5ac3b-415">Therefore, make sure that the user can drill into a line to see the distributions page.</span></span> <span data-ttu-id="5ac3b-416">Use la capacidad del vínculo de la página para establecer una búsqueda detallada, tal como hizo para el encabezado y las páginas de detalles en el escenario 1.</span><span class="sxs-lookup"><span data-stu-id="5ac3b-416">Use the page link capability to establish the drill-through, just as you did for the header and details pages in scenario 1.</span></span>

2.  <span data-ttu-id="5ac3b-417">Dado que habrá más de un tipo de importe en las distribuciones en el escenario 2 (los impuestos, los gastos, etc.), será útil mostrar la descripción del tipo de importe.</span><span class="sxs-lookup"><span data-stu-id="5ac3b-417">Because more than one amount type is expected on the distributions in scenario 2 (sales tax, charges, and so on), it will be useful to show the description of the amount type.</span></span> <span data-ttu-id="5ac3b-418">(Omitimos esta información en el escenario 1).</span><span class="sxs-lookup"><span data-stu-id="5ac3b-418">(We omitted this information in scenario 1.)</span></span>




