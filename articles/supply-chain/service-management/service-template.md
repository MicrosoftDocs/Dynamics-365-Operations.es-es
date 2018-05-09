---
title: Plantillas de servicio
description: "Puede definir un acuerdo de servicio como plantilla y, a continuación, copiar las líneas de la plantilla en otro acuerdo o pedido de servicio."
author: YuyuScheller
manager: AnnBe
ms.date: 02/19/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: SMAAgreementTable
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Core, Operations
ms.custom: 
ms.assetid: 
ms.search.region: Global
ms.author: YuyuScheller
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: efcb77ff883b29a4bbaba27551e02311742afbbd
ms.openlocfilehash: 3a64df055ffc7aa08c5983209987256455626f50
ms.contentlocale: es-es
ms.lasthandoff: 05/08/2018

---

# <a name="service-templates"></a><span data-ttu-id="f387d-103">Plantillas de servicio</span><span class="sxs-lookup"><span data-stu-id="f387d-103">Service templates</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="f387d-104">Puede definir un acuerdo de servicio como plantilla y, a continuación, copiar las líneas de la plantilla en otro acuerdo o pedido de servicio.</span><span class="sxs-lookup"><span data-stu-id="f387d-104">You can define a service agreement as a template and copy the lines of the template later into another service agreement or into a service order.</span></span>

## <a name="example"></a><span data-ttu-id="f387d-105">ejemplo</span><span class="sxs-lookup"><span data-stu-id="f387d-105">Example</span></span>

<span data-ttu-id="f387d-106">Un cliente al que presta servicio tiene ascensores de servicio idénticos en cinco ubicaciones distintas.</span><span class="sxs-lookup"><span data-stu-id="f387d-106">A customer for whom you provide service has identical service elevators at five different locations.</span></span>

<span data-ttu-id="f387d-107">Desea establecer cinco acuerdos de servicio para el cliente, uno para cada sitio.</span><span class="sxs-lookup"><span data-stu-id="f387d-107">You want to set up five service agreements for the customer, one for each site.</span></span>
<span data-ttu-id="f387d-108">Para limitar el trabajo repetitivo de configuración y asegurarse de que la información de configuración de los acuerdos de servicio sea idéntica, crea un acuerdo de servicio y lo especifica como plantilla para el trabajo de servicio de los ascensores.</span><span class="sxs-lookup"><span data-stu-id="f387d-108">To limit repetitive setup work, and to make sure that the setup information in the service agreements is identical, you create a service agreement and specify it as a template for the service work on the elevators.</span></span>

<span data-ttu-id="f387d-109">A continuación, podrá copiar las líneas de la plantilla en los cinco acuerdos de servicio, de modo que cada uno de ellos se rellene con las líneas de la plantilla.</span><span class="sxs-lookup"><span data-stu-id="f387d-109">You can now copy the template lines into the five new service agreements, so that each service agreement is populated with the lines from the template.</span></span>

## <a name="create-a-template"></a><span data-ttu-id="f387d-110">Crear una plantilla</span><span class="sxs-lookup"><span data-stu-id="f387d-110">Create a template</span></span>

<span data-ttu-id="f387d-111">Al crear una plantilla de servicio, crea un acuerdo de servicio y las líneas que éste requiere, y vincula el acuerdo de servicio a un grupo de plantillas de servicio.</span><span class="sxs-lookup"><span data-stu-id="f387d-111">When you create a service template, you create a service agreement, create the required lines on it, and attach the service agreement to a service-template group.</span></span>

> [!NOTE]
> <span data-ttu-id="f387d-112">Un acuerdo de servicio sólo se puede definir como plantilla si no tiene vinculado ningún pedido de servicio.</span><span class="sxs-lookup"><span data-stu-id="f387d-112">A service agreement can be defined as a template only if it has no service orders attached to it.</span></span> <span data-ttu-id="f387d-113">Asimismo, no se pueden generar pedidos de servicio a partir de un acuerdo de servicio definido como plantilla.</span><span class="sxs-lookup"><span data-stu-id="f387d-113">Also, no service orders can be generated from a service agreement that is defined as a template.</span></span>

## <a name="copy-template-lines"></a><span data-ttu-id="f387d-114">Copiar líneas de plantilla</span><span class="sxs-lookup"><span data-stu-id="f387d-114">Copy template lines</span></span>

<span data-ttu-id="f387d-115">Es posible copiar las líneas de plantilla desde una plantilla de servicio a otro acuerdo de servicio o a un pedido de servicio.</span><span class="sxs-lookup"><span data-stu-id="f387d-115">You can copy template lines from a service template into another service agreement or into a service order.</span></span>

<span data-ttu-id="f387d-116">Al copiar líneas de plantilla a los pedidos o acuerdos de servicio, los grupos de plantilla se muestran en una vista de árbol con cada grupo expandido.</span><span class="sxs-lookup"><span data-stu-id="f387d-116">When you copy template lines into your service orders or service agreements, your template groups are displayed in a tree view in which each group can be expanded.</span></span> <span data-ttu-id="f387d-117">Esta visualización permite ver todas las plantillas y las líneas correspondientes.</span><span class="sxs-lookup"><span data-stu-id="f387d-117">This display lets you view each template and template line.</span></span>

<span data-ttu-id="f387d-118">Es más fácil determinar las líneas de plantilla de servicio que desea copiar si agrupa las plantillas en nombres que reflejen su uso.</span><span class="sxs-lookup"><span data-stu-id="f387d-118">It is easier to determine the service-template lines that you want to copy if you have grouped the templates under names that reflect the use of the templates.</span></span>

## <a name="related-topics"></a><span data-ttu-id="f387d-119">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="f387d-119">Related topics</span></span>

[<span data-ttu-id="f387d-120">Copiar líneas de plantilla de servicio</span><span class="sxs-lookup"><span data-stu-id="f387d-120">Copy service templates lines</span></span>](copy-service-template-lines.md)

