---
title: Integración de notas
description: Este tema describe la integración de datos de notas en escritura doble.
author: RamaKrishnamoorthy
ms.date: 02/22/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User, IT Pro
ms.reviewer: rhaertle
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: ramasri
ms.dyn365.ops.version: ''
ms.search.validFrom: 2021-02-22
ms.openlocfilehash: ed068f4264269334babec9acd59d9d58551333b4
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2021
ms.locfileid: "6018395"
---
# <a name="note-integration"></a><span data-ttu-id="b09e0-103">Integración de notas</span><span class="sxs-lookup"><span data-stu-id="b09e0-103">Note integration</span></span>

[!include [banner](../../includes/banner.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

<span data-ttu-id="b09e0-104">Durante los procesos comerciales, los usuarios de Microsoft Dynamics 365 a menudo recopilan información sobre sus clientes.</span><span class="sxs-lookup"><span data-stu-id="b09e0-104">During business processes, Microsoft Dynamics 365 users often gather information about their customers.</span></span> <span data-ttu-id="b09e0-105">Esta información se registra como actividades y notas.</span><span class="sxs-lookup"><span data-stu-id="b09e0-105">This information is recorded as activities and notes.</span></span> <span data-ttu-id="b09e0-106">Este tema describe la integración de datos de notas en escritura doble.</span><span class="sxs-lookup"><span data-stu-id="b09e0-106">This topic describes the integration of note data in dual-write.</span></span>

<span data-ttu-id="b09e0-107">La información del cliente se puede clasificar de las siguientes formas:</span><span class="sxs-lookup"><span data-stu-id="b09e0-107">Customer information can be classified in the following ways:</span></span>

+ <span data-ttu-id="b09e0-108">**Información procesable que un usuario de Dynamics 365 maneja en nombre de un cliente**: por ejemplo, Contoso (un usuario de Dynamics 365) está realizando un espectáculo de juegos.</span><span class="sxs-lookup"><span data-stu-id="b09e0-108">**Actionable information that a Dynamics 365 user handles on behalf of a customer** – For example, Contoso (a Dynamics 365 user) is conducting a game show.</span></span> <span data-ttu-id="b09e0-109">Uno de los clientes de Contoso (un cliente) quiere asistir al espectáculo de juegos.</span><span class="sxs-lookup"><span data-stu-id="b09e0-109">One of Contoso's customers (a customer) wants to attend the game show.</span></span> <span data-ttu-id="b09e0-110">El cliente le pide a un empleado de Contoso que le reserve un espacio en el espectáculo de juegos.</span><span class="sxs-lookup"><span data-stu-id="b09e0-110">The customer asks a Contoso employee to book a slot in the game show for them.</span></span> <span data-ttu-id="b09e0-111">La reserva se produce en el calendario de asistentes a eventos de Contoso.</span><span class="sxs-lookup"><span data-stu-id="b09e0-111">The booking occurs in Contoso's event attendee's calendar.</span></span>
+ <span data-ttu-id="b09e0-112">**Información procesable para un usuario de Dynamics 365**: por ejemplo, un cliente que compra una unidad Surface introduce instrucciones especiales que indican que el dispositivo debe envolverse para regalo antes de la entrega.</span><span class="sxs-lookup"><span data-stu-id="b09e0-112">**Actionable information for a Dynamics 365 user** – For example, a customer who is purchasing a Surface unit enters special instructions that indicate that the device should be gift wrapped before delivery.</span></span> <span data-ttu-id="b09e0-113">Estas instrucciones son información procesable que debe manejar el empleado de Contoso responsable del empaquetado.</span><span class="sxs-lookup"><span data-stu-id="b09e0-113">These instructions are actionable information that should be handled by the Contoso employee who is responsible for packaging.</span></span>
+ <span data-ttu-id="b09e0-114">**Información no procesable**: por ejemplo, un cliente visita la tienda de Contoso y, durante su conversación con un asociado de la tienda, expresa interés en juegos y accesorios para juegos de *Halo*.</span><span class="sxs-lookup"><span data-stu-id="b09e0-114">**Non-actionable information** – For example, a customer visits the Contoso store and, during their conversation with a store associate, expresses interest in *Halo* games and gaming accessories.</span></span> <span data-ttu-id="b09e0-115">El asociado de la tienda toma nota de esta información.</span><span class="sxs-lookup"><span data-stu-id="b09e0-115">The store associate makes a note of this information.</span></span> <span data-ttu-id="b09e0-116">El motor de recomendaciones de productos lo utiliza para hacer recomendaciones al cliente.</span><span class="sxs-lookup"><span data-stu-id="b09e0-116">The product recommendations engine then uses it to make recommendations to the customer.</span></span>

<span data-ttu-id="b09e0-117">En general, la información procesable se captura como *actividades* en las aplicaciones de Finance and Operations y las aplicaciones de participación del cliente.</span><span class="sxs-lookup"><span data-stu-id="b09e0-117">In general, actionable information is captured as *activities* in Finance and Operations apps and customer engagement apps.</span></span> <span data-ttu-id="b09e0-118">La información no procesable se captura como *notas* en las aplicaciones de Finance and Operations y como *anotaciones* en las aplicaciones de participación del cliente.</span><span class="sxs-lookup"><span data-stu-id="b09e0-118">Non-actionable information is captured as *notes* in Finance and Operations apps, and as *annotations* in customer engagement apps.</span></span>

> [!TIP]
> <span data-ttu-id="b09e0-119">Aunque las notas están destinadas para información no procesable, las aplicaciones no le impedirán usarlas para almacenar y manejar información procesable si desea usarlas de esa manera.</span><span class="sxs-lookup"><span data-stu-id="b09e0-119">Although notes are intended for non-actionable information, the apps won't prevent you from using them to store and handle actionable information if you want to use them in that way.</span></span>

<span data-ttu-id="b09e0-120">Microsoft está lanzando actualmente funcionalidad para la integración de notas.</span><span class="sxs-lookup"><span data-stu-id="b09e0-120">Microsoft is currently releasing functionality for note integration.</span></span> <span data-ttu-id="b09e0-121">(La funcionalidad para la integración de actividades se lanzará más adelante). Tenga en cuenta que la integración está disponible para clientes, proveedores, pedidos de venta y pedidos de compra.</span><span class="sxs-lookup"><span data-stu-id="b09e0-121">(Functionality for activity integration will be released later.) Note integration is available for customers, vendors, sales orders, and purchase orders.</span></span>

## <a name="create-a-note-in-a-customer-engagement-app"></a><span data-ttu-id="b09e0-122">Crear una nota en una aplicación de interacción con el cliente</span><span class="sxs-lookup"><span data-stu-id="b09e0-122">Create a note in a customer engagement app</span></span>

<span data-ttu-id="b09e0-123">Para crear una nota en una aplicación de interacción con el cliente y luego sincronizarla con una aplicación de Finance and Operations, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="b09e0-123">To create a note in a customer engagement app and then sync it to a Finance and Operations app, follow these steps.</span></span>

1. <span data-ttu-id="b09e0-124">En la aplicación de interacción con el cliente, abra el registro de la cuenta de un cliente.</span><span class="sxs-lookup"><span data-stu-id="b09e0-124">In the customer engagement app, open the account record for a customer.</span></span>
2. <span data-ttu-id="b09e0-125">En el panel **Escala de tiempo**, seleccione el signo más (**+**) y luego seleccione **Nota** para crear una nota.</span><span class="sxs-lookup"><span data-stu-id="b09e0-125">In the **Timeline** pane, select the plus sign (**+**), and then select **Note** to create a note.</span></span>

    ![Creación de una nota en una aplicación de interacción con el cliente](media/notes-ce-1.png)

3. <span data-ttu-id="b09e0-127">Introduzca un título y una descripción, y luego seleccione **Agregar nota**.</span><span class="sxs-lookup"><span data-stu-id="b09e0-127">Enter a title and description, and then select **Add note**.</span></span>

    ![Introducción de un título y una descripción](media/notes-ce-2.png)

    <span data-ttu-id="b09e0-129">La nueva nota se agrega a la escala de tiempo del cliente.</span><span class="sxs-lookup"><span data-stu-id="b09e0-129">The new note is added to the customer timeline.</span></span>

    ![Nueva nota en la escala de tiempo del cliente](media/notes-ce-3.png)

4. <span data-ttu-id="b09e0-131">Inicie sesión en la aplicación Finance and Operations y abra el mismo registro de cliente.</span><span class="sxs-lookup"><span data-stu-id="b09e0-131">Sign in to the Finance and Operations app, and open the same customer record.</span></span> <span data-ttu-id="b09e0-132">Tenga en cuenta que el botón **Archivos adjuntos** (símbolo de un clip) de la esquina superior derecha indica que el registro tiene un archivo adjunto.</span><span class="sxs-lookup"><span data-stu-id="b09e0-132">Notice that the **Attachments** button (paperclip symbol) in the upper-right corner indicates that the record has an attachment.</span></span>

    ![Notificación sobre un archivo adjunto](media/notes-ce-4.png)

5. <span data-ttu-id="b09e0-134">Seleccione el botón **Archivos adjuntos** para abrir la página **Archivos adjuntos**.</span><span class="sxs-lookup"><span data-stu-id="b09e0-134">Select the **Attachments** button to open the **Attachments** page.</span></span> <span data-ttu-id="b09e0-135">Debería encontrar la nota que creó en la aplicación de interacción con el cliente.</span><span class="sxs-lookup"><span data-stu-id="b09e0-135">You should find the note that you created in the customer engagement app.</span></span>

    ![Nota de la aplicación de interacción con el cliente](media/notes-ce-5.png)

<span data-ttu-id="b09e0-137">Las actualizaciones de la nota se sincronizan entre sí, entre la aplicación Finance and Operations y la aplicación de interacción con el cliente.</span><span class="sxs-lookup"><span data-stu-id="b09e0-137">Any updates to the note are synced back and forth between the Finance and Operations app and the customer engagement app.</span></span>

## <a name="create-a-note-in-a-finance-and-operations-app"></a><span data-ttu-id="b09e0-138">Crear una nota en una aplicación de Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="b09e0-138">Create a note in a Finance and Operations app</span></span>

<span data-ttu-id="b09e0-139">También puede crear una nota en una aplicación de Finance and Operations, y se sincronizará con una aplicación de interacción con el cliente.</span><span class="sxs-lookup"><span data-stu-id="b09e0-139">You can also create a note in a Finance and Operations app, and it will be synced to a customer engagement app.</span></span>

<span data-ttu-id="b09e0-140">Para crear una nota en una aplicación de Finance and Operations y luego sincronizarla con una aplicación de interacción con el cliente, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="b09e0-140">To create a note in a Finance and Operations app and then sync it to a customer engagement app, follow these steps.</span></span>

1. <span data-ttu-id="b09e0-141">En la aplicación Finance and Operations, en la página **Archivos adjuntos**, seleccione **Nueva** \> **Nota**.</span><span class="sxs-lookup"><span data-stu-id="b09e0-141">In the Finance and Operations app, on the **Attachments** page, select **New** \> **Note**.</span></span>

    ![Creación de una nota en la aplicación Finance and Operations](media/notes-fo-1.png)

2. <span data-ttu-id="b09e0-143">Introduzca un título y un breve conjunto de instrucciones, y luego seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="b09e0-143">Enter a title and a brief set of instructions, and then select **Save**.</span></span>

    ![Introducción de un título e instrucciones](media/notes-fo-2.png)

3. <span data-ttu-id="b09e0-145">En la aplicación de interacción con el cliente, actualice el registro.</span><span class="sxs-lookup"><span data-stu-id="b09e0-145">In the customer engagement app, update the record.</span></span> <span data-ttu-id="b09e0-146">Debería encontrar la nueva nota en la escala de tiempo.</span><span class="sxs-lookup"><span data-stu-id="b09e0-146">You should find the new note on the timeline.</span></span>

    ![Nueva nota en la escala de tiempo en la aplicación de interacción con el cliente](media/notes-fo-3.png)

<span data-ttu-id="b09e0-148">Puede clasificar una nota como interna o externa.</span><span class="sxs-lookup"><span data-stu-id="b09e0-148">You can classify a note as either internal or external.</span></span>

- <span data-ttu-id="b09e0-149">En la aplicación Finance and Operations, en la página **Archivos adjuntos**, abra la nota y, a continuación, en el campo **Restricción** campo, seleccione **Interna** o **Externa**.</span><span class="sxs-lookup"><span data-stu-id="b09e0-149">In the Finance and Operations app, on the **Attachments** page, open the note, and then, in the **Restriction** field, select **Internal** or **External**.</span></span>

    ![Campo de restricción](media/notes-fo-4.png)

<span data-ttu-id="b09e0-151">También puede crear una URL.</span><span class="sxs-lookup"><span data-stu-id="b09e0-151">You can also create a URL.</span></span>

1. <span data-ttu-id="b09e0-152">En la aplicación Finance and Operations, en la página **Archivos adjuntos**, seleccione **Nueva** \> **URL**.</span><span class="sxs-lookup"><span data-stu-id="b09e0-152">In the Finance and Operations app, on the **Attachments** page, select **New** \> **URL**.</span></span>
2. <span data-ttu-id="b09e0-153">Escriba un título y la URL.</span><span class="sxs-lookup"><span data-stu-id="b09e0-153">Enter a title and the URL.</span></span>
3. <span data-ttu-id="b09e0-154">En el campo **Restricción**, seleccione **Interna** o **Externa**.</span><span class="sxs-lookup"><span data-stu-id="b09e0-154">In the **Restriction** field, select **Internal** or **External**.</span></span>

    ![Creación de una URL en la aplicación Finance and Operations](media/notes-fo-5.png)

4. <span data-ttu-id="b09e0-156">Seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="b09e0-156">Select **Save**.</span></span>

    <span data-ttu-id="b09e0-157">Debido a que las aplicaciones de participación del cliente no tienen un tipo de URL, la URL se integra con escritura doble en forma de nota.</span><span class="sxs-lookup"><span data-stu-id="b09e0-157">Because customer engagement apps don't have a URL type, the URL is integrated with dual-write as a note.</span></span>

    ![URL que aparece como uan nota en la aplicación de interacción con el cliente](media/notes-ce-6.png)

> [!NOTE]
> <span data-ttu-id="b09e0-159">No se admiten archivos adjuntos.</span><span class="sxs-lookup"><span data-stu-id="b09e0-159">File attachments aren't supported.</span></span>

## <a name="templates"></a><span data-ttu-id="b09e0-160">Plantillas</span><span class="sxs-lookup"><span data-stu-id="b09e0-160">Templates</span></span>

<span data-ttu-id="b09e0-161">La integración de notas incluye una colección de mapas de tabla que funcionan conjuntamente durante la interacción de los datos, como se muestra en la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="b09e0-161">Note integration includes a collection of table maps that work together during data interaction, as shown in the following table.</span></span>

| <span data-ttu-id="b09e0-162">Aplicación de Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="b09e0-162">Finance and Operations app</span></span> | <span data-ttu-id="b09e0-163">Aplicación Customer Engagement</span><span class="sxs-lookup"><span data-stu-id="b09e0-163">Customer engagement app</span></span> | <span data-ttu-id="b09e0-164">Descripción</span><span class="sxs-lookup"><span data-stu-id="b09e0-164">Description</span></span> |
|----------------------------|-------------------------|-------------|
| [<span data-ttu-id="b09e0-165">Archivos adjuntos de clientes</span><span class="sxs-lookup"><span data-stu-id="b09e0-165">Customer Attachments</span></span>](mapping-reference.md#230) | <span data-ttu-id="b09e0-166">Anotaciones</span><span class="sxs-lookup"><span data-stu-id="b09e0-166">Annotations</span></span> | <span data-ttu-id="b09e0-167">Empresas que utilizan texto sin formato y las URL para capturar información específica del cliente (tanto para organizaciones como para personas).</span><span class="sxs-lookup"><span data-stu-id="b09e0-167">Businesses that use plain text and URLs to capture customer-specific information (for both organizations and persons).</span></span> |
| [<span data-ttu-id="b09e0-168">Documentos adjuntos de proveedor</span><span class="sxs-lookup"><span data-stu-id="b09e0-168">Vendor document attachments</span></span>](mapping-reference.md#231) | <span data-ttu-id="b09e0-169">Anotaciones</span><span class="sxs-lookup"><span data-stu-id="b09e0-169">Annotations</span></span> | <span data-ttu-id="b09e0-170">Empresas que utilizan texto sin formato y las URL para capturar información específica del proveedor (tanto para organizaciones como para personas).</span><span class="sxs-lookup"><span data-stu-id="b09e0-170">Businesses that use plain text and URLs to capture vendor-specific information (for both organizations and persons).</span></span> |
| [<span data-ttu-id="b09e0-171">Datos adjuntos de documento de encabezado de pedido de ventas</span><span class="sxs-lookup"><span data-stu-id="b09e0-171">Sales order header document attachments</span></span>](mapping-reference.md#229) | <span data-ttu-id="b09e0-172">Anotaciones</span><span class="sxs-lookup"><span data-stu-id="b09e0-172">Annotations</span></span> | <span data-ttu-id="b09e0-173">Empresas que utilizan texto sin formato y las URL para capturar información específica de pedidos de ventas.</span><span class="sxs-lookup"><span data-stu-id="b09e0-173">Businesses that use plain text and URLs to capture sales order–specific information.</span></span> |
| [<span data-ttu-id="b09e0-174">Datos adjuntos de documento de encabezado de pedido de compra</span><span class="sxs-lookup"><span data-stu-id="b09e0-174">Purchase order header document attachments</span></span>](mapping-reference.md#232) | <span data-ttu-id="b09e0-175">Anotaciones</span><span class="sxs-lookup"><span data-stu-id="b09e0-175">Annotations</span></span> | <span data-ttu-id="b09e0-176">Empresas que utilizan texto sin formato y las URL para capturar información específica de pedidos de compras.</span><span class="sxs-lookup"><span data-stu-id="b09e0-176">Businesses that use plain text and URLs to capture purchase order–specific information.</span></span> |

<span data-ttu-id="b09e0-177">Para más información, consulte [Referencia de asignación de escritura doble](mapping-reference.md).</span><span class="sxs-lookup"><span data-stu-id="b09e0-177">For more information, see [Dual-write mapping reference](mapping-reference.md).</span></span>
