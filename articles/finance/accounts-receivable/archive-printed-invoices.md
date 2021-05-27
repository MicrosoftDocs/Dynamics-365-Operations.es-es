---
title: Archivar facturas de cliente impresas con números hash
description: Este tema explica cómo habilitar el archivo para almacenar facturas de clientes impresas con números de hash.
author: ilyako
ms.date: 03/05/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: 539093
ms.search.region: Global
ms.author: ilyako
ms.search.validFrom: 2021-03-05
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: 841e6059f5b0d70dbd1fe12a1f8910bbb31ddc86
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2021
ms.locfileid: "6018987"
---
# <a name="archive-printed-customer-invoices-with-hash-numbers"></a><span data-ttu-id="18379-103">Archivar facturas de cliente impresas con números hash</span><span class="sxs-lookup"><span data-stu-id="18379-103">Archive printed customer invoices with hash numbers</span></span>

[!include [banner](../includes/banner.md)]

[!include [banner](../includes/preview-banner.md)]

<span data-ttu-id="18379-104">En algunos países, existe un requisito legal para almacenar los números hash calculados en el sistema junto con las impresiones de algunos documentos.</span><span class="sxs-lookup"><span data-stu-id="18379-104">In some countries, there is a legal requirement to store calculated hash numbers in the system together with printouts of some documents.</span></span> <span data-ttu-id="18379-105">Los números hash se pueden utilizar para informar a las autoridades y durante las auditorías.</span><span class="sxs-lookup"><span data-stu-id="18379-105">Hash numbers can be used for reporting to authorities and during audits.</span></span>

<span data-ttu-id="18379-106">Este tema explica cómo configurar el archivo para almacenar facturas de clientes impresas con números de hash.</span><span class="sxs-lookup"><span data-stu-id="18379-106">This topic explains how to configure archiving in order to store printed customer invoices with hash numbers.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="18379-107">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="18379-107">Prerequisites</span></span>

- <span data-ttu-id="18379-108">En el espacio de trabajo **Administración de características**, active la característica **Archivar facturas de clientes impresas con números hash**.</span><span class="sxs-lookup"><span data-stu-id="18379-108">In the **Feature management** workspace, turn on the feature, **Archive printed customer invoices with hash numbers**.</span></span> <span data-ttu-id="18379-109">Para más información, consulte [Resumen de administración de funciones](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md).</span><span class="sxs-lookup"><span data-stu-id="18379-109">For more information, see [Feature management overview](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md).</span></span>
- <span data-ttu-id="18379-110">Configure los formatos imprimibles de los documentos necesarios en **Administración de impresión**.</span><span class="sxs-lookup"><span data-stu-id="18379-110">Configure the printable formats of required documents in **Print management**.</span></span>

<span data-ttu-id="18379-111">Esta funcionalidad es aplicable a los siguientes documentos.</span><span class="sxs-lookup"><span data-stu-id="18379-111">This functionality is applicable to the following documents.</span></span>

<span data-ttu-id="18379-112">**Clientes**</span><span class="sxs-lookup"><span data-stu-id="18379-112">**Accounts receivable**</span></span>
- <span data-ttu-id="18379-113">Factura de cliente</span><span class="sxs-lookup"><span data-stu-id="18379-113">Customer invoice</span></span>
- <span data-ttu-id="18379-114">Nota de abono de cliente</span><span class="sxs-lookup"><span data-stu-id="18379-114">Customer credit note</span></span>
- <span data-ttu-id="18379-115">Factura de servicios</span><span class="sxs-lookup"><span data-stu-id="18379-115">Free text invoice</span></span>
- <span data-ttu-id="18379-116">Nota de abono de texto sin formato</span><span class="sxs-lookup"><span data-stu-id="18379-116">Free text credit note</span></span>

<span data-ttu-id="18379-117">**Gestión y contabilidad de proyectos**</span><span class="sxs-lookup"><span data-stu-id="18379-117">**Project management and accounting**</span></span>
- <span data-ttu-id="18379-118">Factura de proyecto</span><span class="sxs-lookup"><span data-stu-id="18379-118">Project invoice</span></span>
- <span data-ttu-id="18379-119">Nota de abono de proyecto</span><span class="sxs-lookup"><span data-stu-id="18379-119">Project credit note</span></span>

## <a name="configure-customer-master-data"></a><span data-ttu-id="18379-120">Configurar datos maestros de clientes</span><span class="sxs-lookup"><span data-stu-id="18379-120">Configure customer master data</span></span>
<span data-ttu-id="18379-121">Complete los siguientes pasos para configurar los datos de clientes y activar la capacidad de guardar automáticamente facturas impresas como archivos adjuntos.</span><span class="sxs-lookup"><span data-stu-id="18379-121">Complete the following steps to configure customer data and turn on the ability to automatically save printed invoices as attachments.</span></span>

1. <span data-ttu-id="18379-122">Vaya a **Clientes** > **Todos los clientes**.</span><span class="sxs-lookup"><span data-stu-id="18379-122">Go to **Accounts receivable** > **All customers**.</span></span> 
2. <span data-ttu-id="18379-123">Seleccione un cliente y, en la ficha desplegable **Factura y entrega**, en la sección **FACTURA ELECTRÓNICA**, en el campo **Adjunto de factura electrónica**, seleccione **Sí**.</span><span class="sxs-lookup"><span data-stu-id="18379-123">Select a customer, and on the **Invoice and delivery** FastTab, in the **E-INVOCE** section, in the **eInvoice attachment** field, select **Yes**.</span></span>

## <a name="print-invoices"></a><span data-ttu-id="18379-124">Imprimir facturas</span><span class="sxs-lookup"><span data-stu-id="18379-124">Print invoices</span></span>
<span data-ttu-id="18379-125">Puede publicar e imprimir cualquier texto libre, factura de cliente y proyecto o nota de crédito para el cliente configurado en el procedimiento anterior.</span><span class="sxs-lookup"><span data-stu-id="18379-125">You can post and print any free text, customer, and project invoice or credit note for the customer configured in the previous procedure.</span></span>

<span data-ttu-id="18379-126">Abra la página **Archivos adjuntos** de la factura impresa.</span><span class="sxs-lookup"><span data-stu-id="18379-126">Open the **Attachments** page for the printed invoice.</span></span> <span data-ttu-id="18379-127">En la ficha desplegable **Archivo adjunto**, en el grupo de campo **Detalles adicionales**, en el campo **Número de hash del documento**, busque el número hash almacenado calculado para la factura impresa.</span><span class="sxs-lookup"><span data-stu-id="18379-127">On the **Attachment** FastTab, in the **Additional details** field group, in **Document hash number** field, find the stored hash number calculated for the printed invoice.</span></span>

![Número de hash de adjunto](media/attach-hash-num.jpg)

