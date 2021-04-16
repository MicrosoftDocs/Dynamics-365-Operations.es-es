---
title: Ver resultados de automatización de facturas de proveedores (versión preliminar)
description: Este tema explica cómo ver el estado de las facturas de proveedores que se encuentran en el proceso automatizado de envío al flujo de trabajo.
author: abruer
ms.date: 10/16/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.assetid: ''
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2020-09-08
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: 872ec404da0cce41c4ea0f882a3fa8af56316ce3
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/01/2021
ms.locfileid: "5837234"
---
# <a name="view-vendor-invoice-automation-results"></a><span data-ttu-id="9029a-103">Ver resultados de automatización de facturas de proveedores</span><span class="sxs-lookup"><span data-stu-id="9029a-103">View vendor invoice automation results</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="9029a-104">Este tema explica cómo ver el estado de las facturas de proveedores que se encuentran en el proceso automatizado de envío al flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="9029a-104">This topic explains how to view the status of vendor invoices that are in the automated submit-to-workflow process.</span></span> <span data-ttu-id="9029a-105">Los detalles del historial de automatización se mantienen para cada factura de proveedor importada.</span><span class="sxs-lookup"><span data-stu-id="9029a-105">Details of the automation history are maintained for each imported vendor invoice.</span></span> <span data-ttu-id="9029a-106">Dependiendo de los procesos comerciales que haya automatizado, la página **Facturas de proveedores pendientes** muestra los valores **Estado de conciliación del recibo automatizado** y **Envío automatizado al estado del flujo de trabajo**.</span><span class="sxs-lookup"><span data-stu-id="9029a-106">Depending on the business processes that you've automated, the **Pending vendor invoices** page shows **Automated receipt match status** and **Automated submit to workflow status** values.</span></span> <span data-ttu-id="9029a-107">Puede ver los detalles y hacer un plan para enfocarse en las facturas que fallaron en un paso automático.</span><span class="sxs-lookup"><span data-stu-id="9029a-107">You can view the details and make a plan to focus on the invoices that failed an automated step.</span></span> <span data-ttu-id="9029a-108">Luego, después de corregir el problema, puede reanudar el proceso automatizado para la factura importada.</span><span class="sxs-lookup"><span data-stu-id="9029a-108">Then, after you correct the issue, you can resume the automated process for the imported invoice.</span></span>

<span data-ttu-id="9029a-109">Antes de poder editar una factura que se ha enviado, debe pausar el procesamiento automatizado.</span><span class="sxs-lookup"><span data-stu-id="9029a-109">Before you can edit an invoice that has been submitted, you must pause the automated processing.</span></span> <span data-ttu-id="9029a-110">Si una factura en el proceso automatizado de envío a flujo de trabajo debe estar en pausa, configure el campo **Incluir en procesamiento automatizado** como **No** en la página **Facturas de proveedores**.</span><span class="sxs-lookup"><span data-stu-id="9029a-110">If an invoice in the automated submit-to-workflow process must be paused, set the **Include in Automated processing** field to **No** on the **Vendor invoices** page.</span></span> <span data-ttu-id="9029a-111">La automatización no se ejecutará hasta que **Incluir en procesamiento automatizado** se establezca en **Sí**.</span><span class="sxs-lookup"><span data-stu-id="9029a-111">Automation then won't run until **Include in Automated processing** is set to **Yes**.</span></span> <span data-ttu-id="9029a-112">Una factura se puede pausar para una mayor automatización si aún no está en el sistema de flujo de trabajo y el proceso automatizado no la utiliza.</span><span class="sxs-lookup"><span data-stu-id="9029a-112">An invoice can be paused from further automation if it isn't yet in the workflow system and isn't used by the automated process.</span></span>

<span data-ttu-id="9029a-113">Si una factura importada está sujeta al proceso de envío al flujo de trabajo, puede ver su valor **Estado de la automatización** en la página **Facturas de proveedores**.</span><span class="sxs-lookup"><span data-stu-id="9029a-113">If an imported invoice is subject to the submit-to-workflow process, you can view its **Automation status** value on the **Vendor invoices** page.</span></span> <span data-ttu-id="9029a-114">Se siguen los siguientes estados:</span><span class="sxs-lookup"><span data-stu-id="9029a-114">The following statuses are tracked:</span></span>

- <span data-ttu-id="9029a-115">**Incluido** - Los procesos automatizados que se definen en la página **Parámetros de cuentas por pagar** se ejecutan correctamente pero aún no se han completado.</span><span class="sxs-lookup"><span data-stu-id="9029a-115">**Included** – The automated processes that are defined on the **Accounts payable parameters** page are running correctly but haven't yet been completed.</span></span>
- <span data-ttu-id="9029a-116">**Pausado** - Los procesos automatizados que se definen en la página **Parámetros de cuentas por pagar** se han ejecutado, pero al menos un paso del proceso falló.</span><span class="sxs-lookup"><span data-stu-id="9029a-116">**Paused** – The automated processes that are defined on the **Accounts payable parameters** page have run, but at least one step in the process failed.</span></span> <span data-ttu-id="9029a-117">El estado **Pausado** también se aplica si el campo **Incluir en procesamiento automatizado** está configurado como **No**.</span><span class="sxs-lookup"><span data-stu-id="9029a-117">The **Paused** status is also applied if the **Include in automated processing** field is set to **No**.</span></span> <span data-ttu-id="9029a-118">Puede ver los errores seleccionando **Ver resultados más recientes**.</span><span class="sxs-lookup"><span data-stu-id="9029a-118">You can view the failures by selecting **View most recent results**.</span></span>
- <span data-ttu-id="9029a-119">**En flujo de trabajo** - La factura importada se ha enviado al sistema de flujo de trabajo, ya sea mediante el proceso automatizado de envío al flujo de trabajo o manualmente.</span><span class="sxs-lookup"><span data-stu-id="9029a-119">**In workflow** – The imported invoice has been submitted to the workflow system, either by the automated submit-to-workflow process or manually.</span></span>
- <span data-ttu-id="9029a-120">**Flujo de trabajo completo** - Se ha completado el proceso de flujo de trabajo para la factura importada.</span><span class="sxs-lookup"><span data-stu-id="9029a-120">**Workflow complete** – The workflow process has been completed for the imported invoice.</span></span>


[!INCLUDE[footer-include](../../includes/footer-banner.md)]