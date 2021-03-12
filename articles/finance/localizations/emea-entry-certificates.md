---
title: Certificados de entrada de la UE
description: Este artículo proporciona información acerca de los certificados de entrada en la Unión Europea (UE).
author: ShylaThompson
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CustEntryCertificateJour_W, CustParameters, CustTable, SalesTable
audience: Application User
ms.reviewer: kfend
ms.custom: 11464
ms.search.region: Austria, Belgium, Czech Republic, Denmark, Estonia, Finland, France, Germany, Hungary, Ireland, Italy, Latvia, Lithuania, Netherlands, Poland, Spain, Sweden, United Kingdom
ms.author: mrolecki
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: f91317f327852bc44a8c88887c18b69f6ec020e8
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/15/2021
ms.locfileid: "4962782"
---
# <a name="eu-entry-certificates"></a><span data-ttu-id="ec649-103">Certificado de entrada de la UE</span><span class="sxs-lookup"><span data-stu-id="ec649-103">EU entry certificates</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="ec649-104">Este artículo proporciona información acerca de los certificados de entrada en la Unión Europea (UE).</span><span class="sxs-lookup"><span data-stu-id="ec649-104">This article provides information about European Union (EU) entry certificates.</span></span>

<span data-ttu-id="ec649-105">Puede realizar las tareas siguientes para un certificado de entrada de la Unión Europea (UE):</span><span class="sxs-lookup"><span data-stu-id="ec649-105">You can complete the following tasks for a European Union (EU) entry certificate:</span></span>

-   <span data-ttu-id="ec649-106">Crear y emitir un certificado de entrada de la UE junto con un albarán o una factura de cliente para la entrega de artículos o servicios en los países o regiones de la UE.</span><span class="sxs-lookup"><span data-stu-id="ec649-106">Create and issue an EU entry certificate together with a packing slip or customer invoice for the delivery of items or services to EU countries/regions.</span></span>
-   <span data-ttu-id="ec649-107">Recibir el certificado de entrada de la UE firmado por un cliente de la UE.</span><span class="sxs-lookup"><span data-stu-id="ec649-107">Receive the EU entry certificate that is signed by an EU customer.</span></span>
-   <span data-ttu-id="ec649-108">Cargar el certificado de entrada de la UE firmado que se recibe del cliente o de un tercero que es responsable de entregar los artículos al cliente.</span><span class="sxs-lookup"><span data-stu-id="ec649-108">Upload the signed EU entry certificate that is received either from the customer or from a third party who is responsible for delivering items to the customer.</span></span>
-   <span data-ttu-id="ec649-109">Asociar el certificado de entrada de la UE cargado con una factura de cliente.</span><span class="sxs-lookup"><span data-stu-id="ec649-109">Associate the uploaded EU entry certificate with a customer invoice.</span></span>
-   <span data-ttu-id="ec649-110">Actualizar el estado del certificado de entrada de la UE cargado.</span><span class="sxs-lookup"><span data-stu-id="ec649-110">Update the status of the uploaded EU entry certificate.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="ec649-111">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="ec649-111">Prerequisites</span></span>
<span data-ttu-id="ec649-112">La tabla siguiente muestra los requisitos previos que deben cumplirse antes de comenzar.</span><span class="sxs-lookup"><span data-stu-id="ec649-112">The following table shows the prerequisites that must be in place before you start.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="ec649-113">Categoría</span><span class="sxs-lookup"><span data-stu-id="ec649-113">Category</span></span></th>
<th><span data-ttu-id="ec649-114">Requisito previo</span><span class="sxs-lookup"><span data-stu-id="ec649-114">Prerequisite</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="ec649-115">País o región</span><span class="sxs-lookup"><span data-stu-id="ec649-115">Country/region</span></span></td>
<td><span data-ttu-id="ec649-116">La dirección principal de la entidad jurídica debe estar en un estado miembro de la Unión Europea.</span><span class="sxs-lookup"><span data-stu-id="ec649-116">The primary address of the legal entity must be in a EU member state.</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="ec649-117">Tareas de configuración relacionadas</span><span class="sxs-lookup"><span data-stu-id="ec649-117">Related set up tasks</span></span></td>
<td><ul>
<li><span data-ttu-id="ec649-118">En la página <strong>Parámetros de clientes</strong>, seleccione las opciones <strong>Habilitar administración de certificados de entrada</strong> y <strong>Habilitar emisión de certificados de entrada</strong>.</span><span class="sxs-lookup"><span data-stu-id="ec649-118">On the <strong>Accounts receivable parameters</strong> page, select the <strong>Enable entry certificate management</strong> and <strong>Enable entry certificate issuing</strong> options.</span></span></li>
<li><span data-ttu-id="ec649-119">En la página <strong>Clientes</strong>, en la ficha desplegable <strong>Factura y entrega</strong>, seleccione <strong>Se necesita certificado de entrada</strong> para indicar que un certificado de entrada de la UE es obligatorio para el cliente.</span><span class="sxs-lookup"><span data-stu-id="ec649-119">On the <strong>Customers</strong> page, on the <strong>Invoice and delivery</strong> FastTab, select the <strong>Entry certificate required</strong> option to indicate that an EU entry certificate is mandatory for the customer.</span></span> <span data-ttu-id="ec649-120">Seleccione la opción <strong>Emitir certificado de entrada</strong> para emitir un certificado de entrada de la UE para la entidad jurídica del cliente.</span><span class="sxs-lookup"><span data-stu-id="ec649-120">Select the <strong>Issue entry certificate</strong> option to issue an EU entry certificate of the legal entity to the customer.</span></span></li>
<li><span data-ttu-id="ec649-121">En la página <strong>Parámetros de clientes</strong>, seleccione un código de secuencia numérica para la referencia <strong>Certificado de entrada</strong>.</span><span class="sxs-lookup"><span data-stu-id="ec649-121">On the <strong>Accounts receivable parameters</strong> page, select a number sequence code for the <strong>Entry certificate</strong> reference.</span></span></li>
</ul></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="ec649-122">Transacciones relacionadas</span><span class="sxs-lookup"><span data-stu-id="ec649-122">Related transactions</span></span></td>
<td><ul>
<li><span data-ttu-id="ec649-123">Cree una cuenta de cliente.</span><span class="sxs-lookup"><span data-stu-id="ec649-123">Create a customer account.</span></span></li>
<li><span data-ttu-id="ec649-124">Cree un pedido de ventas.</span><span class="sxs-lookup"><span data-stu-id="ec649-124">Create a sales order.</span></span></li>
</ul></td>
</tr>
</tbody>
</table>

## <a name="creating-registering-and-uploading-an-eu-entry-certificate"></a><span data-ttu-id="ec649-125">Creación, registro y carga de un certificado de entrada de la UE</span><span class="sxs-lookup"><span data-stu-id="ec649-125">Creating, registering, and uploading an EU entry certificate</span></span>
<span data-ttu-id="ec649-126">Puede crear un certificado de entrada de la UE de forma automática o manual.</span><span class="sxs-lookup"><span data-stu-id="ec649-126">You can create an EU entry certificate automatically or manually.</span></span> <span data-ttu-id="ec649-127">Un certificado de entrada de la UE se crea y se imprime automáticamente al registrar un albarán o una factura para un cliente mediante a través de la página **Registro del albarán** o la página **Registro de factura**.</span><span class="sxs-lookup"><span data-stu-id="ec649-127">An EU entry certificate is created and printed automatically when you post a packing slip or invoice for a customer by using the **Packing slip posting** page or the **Posting invoice** page.</span></span> <span data-ttu-id="ec649-128">Para crear manualmente o reimprimir un certificado de entrada de la UE para una factura de cliente, use la página **Diario de facturas**.</span><span class="sxs-lookup"><span data-stu-id="ec649-128">To manually create or reprint an EU entry certificate for a customer invoice, use the **Invoice journal** page.</span></span> <span data-ttu-id="ec649-129">También, puede usar la página **Diario de certificado de entrada** para especificar detalles acerca de un certificado de entrada de la UE emitido por un tercero.</span><span class="sxs-lookup"><span data-stu-id="ec649-129">Additionally, you can use the **Entry certificate journal** page to enter details about an EU entry certificate that is issued by a third party.</span></span>

### <a name="creating-an-eu-entry-certificate-automatically-or-manually"></a><span data-ttu-id="ec649-130">Creación de un certificado de entrada de la UE de forma automática o manual</span><span class="sxs-lookup"><span data-stu-id="ec649-130">Creating an EU entry certificate automatically or manually</span></span>

<span data-ttu-id="ec649-131">Puede crear un certificado de entrada de la UE automáticamente usando un albarán en la página **Todos los pedidos de ventas** o mediante una factura en la página **Pedido de venta**.</span><span class="sxs-lookup"><span data-stu-id="ec649-131">You can create an EU entry certificate automatically by using a packing slip on the **All sales orders** page or by using an invoice on the **Sales order** page.</span></span> <span data-ttu-id="ec649-132">Para crear manualmente un certificado de entrada de la UE, puede usar una factura en la página **Diario de facturas**.</span><span class="sxs-lookup"><span data-stu-id="ec649-132">To manually create an EU entry certificate, you can use an invoice on the **Invoice journal** page.</span></span> <span data-ttu-id="ec649-133">Sin embargo, debe cambiar el estado de certificado de la factura antes de crear manualmente un certificado de entrada de la UE.</span><span class="sxs-lookup"><span data-stu-id="ec649-133">However, you must change the certification status of the invoice before you manually create an EU entry certificate.</span></span>

### <a name="registering-an-eu-entry-certificate"></a><span data-ttu-id="ec649-134">Registro de un certificado de entrada de la UE</span><span class="sxs-lookup"><span data-stu-id="ec649-134">Registering an EU entry certificate</span></span>

<span data-ttu-id="ec649-135">Si se requiere un registro, puede usar la página **Diario de certificado de entrada** para registrar una entrada de la UE emitido por un tercero.</span><span class="sxs-lookup"><span data-stu-id="ec649-135">If registration is required, you can use the **Entry certificate journal** page to register an EU entry certificate that is issued by a third party.</span></span>

### <a name="uploading-a-received-eu-entry-certificate"></a><span data-ttu-id="ec649-136">Carga de un certificado de entrada de la UE recibido</span><span class="sxs-lookup"><span data-stu-id="ec649-136">Uploading a received EU entry certificate</span></span>

<span data-ttu-id="ec649-137">Utilice la página **Archivos adjuntos** para cargar un certificado de entrada de la UE firmado por un cliente de la UE.</span><span class="sxs-lookup"><span data-stu-id="ec649-137">Use the **Attachments** page to upload a received EU entry certificate that is signed by an EU customer.</span></span> <span data-ttu-id="ec649-138">Después de que se carga el certificado, puede asociarlo con una factura como prueba de la entrega de los artículos.</span><span class="sxs-lookup"><span data-stu-id="ec649-138">After the certificate is uploaded, you can associate it with an invoice as proof that the items were delivered.</span></span> <span data-ttu-id="ec649-139">Se requiere esta prueba si debe emitir una factura que no incluya el Impuesto sobre el valor añadido (IVA) y también se usa durante la auditoría.</span><span class="sxs-lookup"><span data-stu-id="ec649-139">This proof is required if you must issue an invoice that doesn't include value-added tax (VAT), and it's also used during auditing.</span></span>

### <a name="optional-updating-the-certification-status-and-printing-status-of-an-invoice"></a><span data-ttu-id="ec649-140">Opcional: Actualización del estado de impresión y certificación de una factura</span><span class="sxs-lookup"><span data-stu-id="ec649-140">Optional: Updating the certification status and printing status of an invoice</span></span>

<span data-ttu-id="ec649-141">Puede actualizar el estado de certificación de entrada y el estado de impresión de una factura de cliente mediante la página **Diario de facturas**.</span><span class="sxs-lookup"><span data-stu-id="ec649-141">You can update the entry certification status and printing status of a customer invoice by using the **Invoice journal** page.</span></span>

## <a name="technical-information-for-system-administrators"></a><span data-ttu-id="ec649-142">Información técnica para administradores del sistema</span><span class="sxs-lookup"><span data-stu-id="ec649-142">Technical information for system administrators</span></span>
<span data-ttu-id="ec649-143">Si no tiene acceso a las páginas que se usan para completar esta tarea, póngase en contacto con el administrador del sistema y proporcione la información que se indica en la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="ec649-143">If you don't have access to the pages that are used to complete this task, contact your system administrator, and provide the information that is shown in the following table.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="ec649-144">Categoría</span><span class="sxs-lookup"><span data-stu-id="ec649-144">Category</span></span></th>
<th><span data-ttu-id="ec649-145">Requisito previo</span><span class="sxs-lookup"><span data-stu-id="ec649-145">Prerequisite</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="ec649-146">Roles y responsabilidades de seguridad</span><span class="sxs-lookup"><span data-stu-id="ec649-146">Security roles and duties</span></span></td>
<td><span data-ttu-id="ec649-147">Para configurar y crear certificados de entrada de la UE para artículos o servicios, debe ser miembro de un rol de seguridad que incluya las siguientes responsabilidades:</span><span class="sxs-lookup"><span data-stu-id="ec649-147">To set up and create EU entry certificates for items or services, you must be a member of a security role that includes the following duties:</span></span>
<ul>
<li><span data-ttu-id="ec649-148"><strong>Funcionario de clientes</strong> (CustInvoiceAccountsReceivableClerk)</span><span class="sxs-lookup"><span data-stu-id="ec649-148"><strong>Accounts receivable clerk</strong> (CustInvoiceAccountsReceivableClerk)</span></span></li>
<li><span data-ttu-id="ec649-149"><strong>Representante de servicio al cliente</strong> (TradeCustomerServiceRepresentative)</span><span class="sxs-lookup"><span data-stu-id="ec649-149"><strong>Customer service representative</strong> (TradeCustomerServiceRepresentative)</span></span></li>
<li><span data-ttu-id="ec649-150"><strong>Funcionario de ventas</strong> (TradeSalesClerk)</span><span class="sxs-lookup"><span data-stu-id="ec649-150"><strong>Sales clerk</strong> (TradeSalesClerk)</span></span></li>
<li><span data-ttu-id="ec649-151"><strong>Funcionario de envío</strong> (InventShippingClerk)</span><span class="sxs-lookup"><span data-stu-id="ec649-151"><strong>Shipping clerk</strong> (InventShippingClerk)</span></span></li>
</ul></td>
</tr>
</tbody>
</table>





