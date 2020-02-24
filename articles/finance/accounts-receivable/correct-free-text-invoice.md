---
title: Corrección de una factura de servicios
description: Este artículo explica cómo corregir una factura de servicios que se ha registrado y cómo reenviarla como factura corregida.
author: ShivamPandey-msft
manager: AnnBe
ms.date: 08/22/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CustFreeInvoice
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.custom: 13991
ms.assetid: 2a0a4789-8619-4974-bef9-0923cc848420
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 0bf6e7a070d7c151c6ff5d868f4f916359b82683
ms.sourcegitcommit: 4e62c22b53693c201baa646a8f047edb5a0a2747
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/07/2020
ms.locfileid: "3031001"
---
# <a name="correct-a-free-text-invoice"></a><span data-ttu-id="5adec-103">Corrección de una factura de servicios</span><span class="sxs-lookup"><span data-stu-id="5adec-103">Correct a free text invoice</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="5adec-104">Este artículo explica cómo corregir una factura de servicios que se ha registrado y cómo reenviarla como factura corregida.</span><span class="sxs-lookup"><span data-stu-id="5adec-104">This article explains how to correct a free text invoice that has been posted and reissue it as a corrected invoice.</span></span>

<span data-ttu-id="5adec-105">Para corregir una factura de servicios que ya se ha registrado, ábrala.</span><span class="sxs-lookup"><span data-stu-id="5adec-105">To correct a free text invoice that has already been posted, open the posted free text invoice.</span></span> <span data-ttu-id="5adec-106">En la página **Factura**, seleccione **Cancelar** y, a continuación seleccione **Corregir factura**.</span><span class="sxs-lookup"><span data-stu-id="5adec-106">On the **Invoice** page, select **Cancel**, and then select **Correct invoice**.</span></span> <span data-ttu-id="5adec-107">Seleccione un código de razón, agregue comentarios y seleccione la fecha para la nueva factura corregida.</span><span class="sxs-lookup"><span data-stu-id="5adec-107">Select a reason code, add comments, and select the date for new corrected invoice.</span></span> <span data-ttu-id="5adec-108">Puede modificar la factura corregida y registrarla.</span><span class="sxs-lookup"><span data-stu-id="5adec-108">You can modify the corrected invoice, and post it.</span></span> 

<span data-ttu-id="5adec-109">Al registrar la factura corregida, se crea una factura de cancelación por un importe de crédito que sea igual al importe de la factura original.</span><span class="sxs-lookup"><span data-stu-id="5adec-109">When you post the corrected invoice, a canceling invoice is created for a credit amount that equals the original invoice amount.</span></span> <span data-ttu-id="5adec-110">Por lo tanto, el saldo combinado de las facturas original y de cancelación es igual a 0 (cero).</span><span class="sxs-lookup"><span data-stu-id="5adec-110">Therefore, the combined balance of the original invoice and the canceling invoice is 0 (zero).</span></span> <span data-ttu-id="5adec-111">La factura de cancelación se liquida con la factura original.</span><span class="sxs-lookup"><span data-stu-id="5adec-111">The canceling invoice is settled against the original invoice.</span></span> 

<span data-ttu-id="5adec-112">Después de registrar la factura corregida, tendrá tres facturas:</span><span class="sxs-lookup"><span data-stu-id="5adec-112">After you post the corrected invoice, you will have three invoices:</span></span>

-   <span data-ttu-id="5adec-113">**Factura original**: factura que contiene la información que está corrigiendo.</span><span class="sxs-lookup"><span data-stu-id="5adec-113">**Original invoice** – The invoice that includes the information that you're correcting.</span></span>
-   <span data-ttu-id="5adec-114">**Factura de cancelación**: factura de crédito que genera el sistema para cancelar la factura corregida más recientemente.</span><span class="sxs-lookup"><span data-stu-id="5adec-114">**Canceling invoice** – The system-generated credit invoice that was created to cancel the invoice that was most recently corrected.</span></span>
-   <span data-ttu-id="5adec-115">**Factura corregida**: factura que contiene la información de factura corregida.</span><span class="sxs-lookup"><span data-stu-id="5adec-115">**Corrected invoice** – The invoice that contains the corrected invoice information.</span></span>

<span data-ttu-id="5adec-116">Puede identificar la cancelación y la corrección de facturas de dos maneras:</span><span class="sxs-lookup"><span data-stu-id="5adec-116">You can identify canceling and correcting invoices in two ways:</span></span>

-   <span data-ttu-id="5adec-117">La página **Todas las facturas de servicios** incluye una columna **Corrección** donde puede ver qué facturas se han cancelado y qué facturas se han corregido.</span><span class="sxs-lookup"><span data-stu-id="5adec-117">The **All free text invoices** page includes a **Correction** column, where you can see which invoices are canceling invoices and corrected invoices.</span></span>
-   <span data-ttu-id="5adec-118">El encabezado de la factura de servicios muestra un estado de **Factura de cancelación '\[número de factura\]'** o **Factura corregida '\[número de factura\]'**.</span><span class="sxs-lookup"><span data-stu-id="5adec-118">The header of the free text invoice shows a status of **Cancelling invoice '\[invoice number\]'** or **Corrected invoice '\[invoice number\]'**.</span></span>

> [!NOTE]
> <span data-ttu-id="5adec-119">Esta característica solo está disponible si se selecciona la clave de configuración **Corrección de factura de servicios**.</span><span class="sxs-lookup"><span data-stu-id="5adec-119">This feature is available only if the **Free text invoice correction** configuration key is selected.</span></span> <span data-ttu-id="5adec-120">Para obtener más información sobre cómo habilitar las claves de Configuración, consulte la sección Habilitar (o deshabilitar) las claves de configuración del tema [Modo de mantenimiento](../../fin-ops-core/dev-itpro/sysadmin/maintenance-mode.md).</span><span class="sxs-lookup"><span data-stu-id="5adec-120">For more information on how to enable Configuration keys refer to the Enable (or disable) configuration keys section in the [Maintenance mode](../../fin-ops-core/dev-itpro/sysadmin/maintenance-mode.md) topic.</span></span> 



