---
title: Flujos de trabajo de acuerdos de gestión de devoluciones
description: Este tema explica cómo configurar un flujo de trabajo de gestión de devoluciones para aprobar y activar acuerdos.
author: sherry-zheng
ms.date: 02/19/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: WorkflowTableListPageRnr
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: chuzheng
ms.search.validFrom: 2021-02-19
ms.dyn365.ops.version: Release 10.0.18
ms.openlocfilehash: ee342de6d069131e230120c5d65aef58da8e632a
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2021
ms.locfileid: "6020396"
---
# <a name="rebate-management-deal-workflows"></a><span data-ttu-id="29d4f-103">Flujos de trabajo de acuerdos de gestión de devoluciones</span><span class="sxs-lookup"><span data-stu-id="29d4f-103">Rebate management deal workflows</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="29d4f-104">Para aprobar acuerdos de devoluciones, la gestión de devoluciones utiliza la misma plataforma de flujo de trabajo que otras aplicaciones de Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="29d4f-104">To approve rebate deals, Rebate management uses the same workflow platform as other Finance and Operations apps.</span></span> <span data-ttu-id="29d4f-105">Hay dos procesos de trabajo asociados con cada flujo de trabajo:</span><span class="sxs-lookup"><span data-stu-id="29d4f-105">Two job processes are associated with every workflow:</span></span>

- <span data-ttu-id="29d4f-106">Un elemento del flujo de trabajo activa el trato para que el usuario o el proceso del flujo de trabajo puedan aprobar las transacciones.</span><span class="sxs-lookup"><span data-stu-id="29d4f-106">One element of the workflow activates the deal so that the user or workflow process can approve the transactions.</span></span>
- <span data-ttu-id="29d4f-107">Un elemento del flujo de trabajo aprueba el acuerdo.</span><span class="sxs-lookup"><span data-stu-id="29d4f-107">One element of the workflow approves the deal.</span></span>

<span data-ttu-id="29d4f-108">Antes de poder utilizar una oferta de devolución, debe estar activa en el módulo **Gestión de devoluciones**.</span><span class="sxs-lookup"><span data-stu-id="29d4f-108">Before you can use a rebate deal, it must be active in the **Rebate management** module.</span></span> <span data-ttu-id="29d4f-109">Para activar una oferta, primero debe crear y configurar un *Flujo de trabajo de la operación de gestión de devoluciones*.</span><span class="sxs-lookup"><span data-stu-id="29d4f-109">To activate a deal, you must first create and configure a *Rebate management deal workflow*.</span></span>

<span data-ttu-id="29d4f-110">Una vez que se activa un flujo de trabajo para la gestión de devoluciones, los usuarios no pueden aprobar acuerdos manualmente.</span><span class="sxs-lookup"><span data-stu-id="29d4f-110">After a workflow is activated for Rebate management, users can't manually approve deals.</span></span> <span data-ttu-id="29d4f-111">El flujo de trabajo debe usarse siempre.</span><span class="sxs-lookup"><span data-stu-id="29d4f-111">The workflow must be always used.</span></span>

## <a name="create-and-manage-rebate-management-deal-workflows"></a><span data-ttu-id="29d4f-112">Crear y administrar flujos de trabajo de acuerdos de gestión de devoluciones</span><span class="sxs-lookup"><span data-stu-id="29d4f-112">Create and manage Rebate management deal workflows</span></span>

<span data-ttu-id="29d4f-113">Para trabajar con sus flujos de trabajo de gestión de devoluciones de acuerdos, vaya a **Gestión de devoluciones \> Configuración \> Flujos de trabajo de gestión de devoluciones**.</span><span class="sxs-lookup"><span data-stu-id="29d4f-113">To work with your Rebate management deal workflows, go to **Rebate management \> Setup \> Rebate management workflows**.</span></span> <span data-ttu-id="29d4f-114">Allí, puede ver, crear y actualizar flujos de trabajo según sea necesario.</span><span class="sxs-lookup"><span data-stu-id="29d4f-114">There, you can view, create, and update workflows as required.</span></span> <span data-ttu-id="29d4f-115">Solo un flujo de trabajo de este tipo puede estar activa a la vez.</span><span class="sxs-lookup"><span data-stu-id="29d4f-115">Only one workflow of this type can be active at a time.</span></span> <span data-ttu-id="29d4f-116">Para obtener más información sobre los flujos de trabajo, cómo trabajar con la página **Flujos de trabajo de gestión de devoluciones** y cómo crear flujos de trabajo, consulte [Descripción general del sistema de flujo de trabajo](../../fin-ops-core/fin-ops/organization-administration/overview-workflow-system.md) y sus temas relacionados.</span><span class="sxs-lookup"><span data-stu-id="29d4f-116">For more information about workflows, how to work with the **Rebate management workflows** page, and how to create workflows, see [Workflow system overview](../../fin-ops-core/fin-ops/organization-administration/overview-workflow-system.md) and its related topics.</span></span>

## <a name="use-a-workflow-to-activate-a-deal"></a><span data-ttu-id="29d4f-117">Utilice un flujo de trabajo para activar un acuerdo</span><span class="sxs-lookup"><span data-stu-id="29d4f-117">Use a workflow to activate a deal</span></span>

<span data-ttu-id="29d4f-118">Para activar un acuerdo a través de un flujo de trabajo, ábralo (por ejemplo, en la página **Todas las ofertas de gestión de devoluciones**).</span><span class="sxs-lookup"><span data-stu-id="29d4f-118">To activate a deal through a workflow, open the deal (for example, on the **All rebate management deals** page).</span></span> <span data-ttu-id="29d4f-119">Luego, en el panel de acciones, seleccione **Flujo de trabajo \> Enviar**.</span><span class="sxs-lookup"><span data-stu-id="29d4f-119">Then, on the Action Pane, select **Workflow \> Submit**.</span></span> <span data-ttu-id="29d4f-120">Una vez que el nuevo acuerdo se haya procesado y aprobado a través del flujo de trabajo, estará activo y listo para usar.</span><span class="sxs-lookup"><span data-stu-id="29d4f-120">After the new deal has been processed and approved through the workflow, it will be active and ready to use.</span></span>

<span data-ttu-id="29d4f-121">Una vez que se ha activado un acuerdo, no puede cambiar su configuración.</span><span class="sxs-lookup"><span data-stu-id="29d4f-121">After a deal has been activated, you can't change its setup.</span></span> <span data-ttu-id="29d4f-122">Si debe cambiar una oferta activa, desactívela y luego cree una nueva oferta.</span><span class="sxs-lookup"><span data-stu-id="29d4f-122">If you must change an active deal, inactivate it, and then create a new deal.</span></span> <span data-ttu-id="29d4f-123">Si el nuevo acuerdo se parece al anterior, puede crearlo copiando el anterior.</span><span class="sxs-lookup"><span data-stu-id="29d4f-123">If the new deal will resemble the old deal, you can create it by copying the old deal.</span></span>
