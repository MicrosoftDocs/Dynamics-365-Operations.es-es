---
title: Ejecución programada
description: En este tema se explica la ejecución programada en Administración de activos.
author: josaw1
manager: tfehr
ms.date: 08/13/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: riluan
ms.search.validFrom: 2019-08-30
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 0ed61411920edebb1ab9b87856a5418fa43bc2f4
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2021
ms.locfileid: "5264931"
---
# <a name="scheduled-execution"></a><span data-ttu-id="f2807-103">Ejecución programada</span><span class="sxs-lookup"><span data-stu-id="f2807-103">Scheduled execution</span></span>

[!include [banner](../../includes/banner.md)]

 

<span data-ttu-id="f2807-104">Puede utilizar niveles de servicio de la orden de trabajo para configurar la ejecución programada.</span><span class="sxs-lookup"><span data-stu-id="f2807-104">You can use work order service levels to set up scheduled execution.</span></span> <span data-ttu-id="f2807-105">(Para obtener más información sobre los niveles de servicio de la orden de trabajo, consulte [Nivel de servicio y descripción](service-level-and-description.md).) La ejecución programada brinda flexibilidad en la planificación de trabajo para los trabajadores de mantenimiento, ya que puede configurar requisitos más o menos detallados para el intervalo durante la que se debe completar una orden de trabajo.</span><span class="sxs-lookup"><span data-stu-id="f2807-105">(For more information about work order service levels, see [Service level and description](service-level-and-description.md).) Scheduled execution provides flexibility in work planning for maintenance workers, because you can set up more detailed or less detailed requirements for the interval that a work order should be completed during.</span></span> <span data-ttu-id="f2807-106">Por ejemplo, un trabajador de mantenimiento que completa un trabajo más rápido de lo esperado en una instalación de producción podría pasar a otro trabajo cercano que se planificó para la semana actual pero no necesariamente para el día actual.</span><span class="sxs-lookup"><span data-stu-id="f2807-106">For example, a maintenance worker who completes a job faster than expected in a production facility might be able to move on to another nearby job that was planned for the current week but not necessarily for the current day.</span></span> <span data-ttu-id="f2807-107">Este enfoque permite la optimización de la planificación del trabajador y la finalización del trabajo.</span><span class="sxs-lookup"><span data-stu-id="f2807-107">This approach allows for optimization of worker planning and job completion.</span></span>

<span data-ttu-id="f2807-108">La configuración de ejecución programada, que está relacionada con las órdenes de trabajo, puede ser genérica o específica.</span><span class="sxs-lookup"><span data-stu-id="f2807-108">Scheduled execution setup, which is related to work orders, can be generic or specific.</span></span> <span data-ttu-id="f2807-109">Puede configurar líneas genéricas que no se limitan a tipos de órdenes de trabajo específicas, tipos de activos, etc.</span><span class="sxs-lookup"><span data-stu-id="f2807-109">You can set up generic lines that aren't limited to specific work order types, asset types, and so on.</span></span> <span data-ttu-id="f2807-110">Como alternativa, puede crear líneas de ejecución programadas que se aplican a un tipo de orden de trabajo específica, tipo de activo, tipo de trabajo de mantenimiento, etc.</span><span class="sxs-lookup"><span data-stu-id="f2807-110">Alternatively, you can create scheduled execution lines that apply to a specific work order type, asset type, maintenance job type, and so on.</span></span>

1. <span data-ttu-id="f2807-111">Seleccione **Administración de activos** \> **Configuración** \> **Órdenes de trabajo** \> **Ejecución programada**.</span><span class="sxs-lookup"><span data-stu-id="f2807-111">Select **Asset management** \> **Setup** \> **Work orders** \> **Scheduled execution**.</span></span>
2. <span data-ttu-id="f2807-112">Seleccione **Nueva** para crear una línea de ejecución programada.</span><span class="sxs-lookup"><span data-stu-id="f2807-112">Select **New** to create a scheduled execution line.</span></span>
3. <span data-ttu-id="f2807-113">En los campos **Ubicación técnica**, **Tipo de orden de trabajo**, **Tipo de activo**, **Fabricante**, **Modelo**, **Categoría de tipo de trabajo de mantenimiento**, **Tipo de trabajo de mantenimiento**, **Variante de tipo de trabajo de mantenimiento** y **Comercio**, seleccionar valores como sea necesario.</span><span class="sxs-lookup"><span data-stu-id="f2807-113">In the **Functional location**, **Work order type**, **Asset type**, **Manufacturer**, **Model**, **Maintenance job type category**, **Maintenance job type**, **Maintenance job type variant**, and **Trade** fields, select values as you require.</span></span>
4. <span data-ttu-id="f2807-114">En el campo **Nivel de servicio**, seleccione un nivel de servicio de la orden de trabajo.</span><span class="sxs-lookup"><span data-stu-id="f2807-114">In the **Service level** field, select a work order service level.</span></span> <span data-ttu-id="f2807-115">Si deja este campo en blanco, haga el tipo más genérico de línea de ejecución programada.</span><span class="sxs-lookup"><span data-stu-id="f2807-115">If you leave this field blank, you make the most generic type of scheduled execution line.</span></span> <span data-ttu-id="f2807-116">Para obtener un ejemplo de una línea genérica, vea el primer registro en la ilustración que se indica a continuación.</span><span class="sxs-lookup"><span data-stu-id="f2807-116">For an example of a generic line, see the first record in the illustration that follows.</span></span> <span data-ttu-id="f2807-117">Esa línea habilita todas las órdenes de trabajo que no tienen ningún nivel de servicio de la orden de trabajo que se programe para una fecha y hora específica.</span><span class="sxs-lookup"><span data-stu-id="f2807-117">That line enables all work orders that have no work order service level to be scheduled for a specific date and time.</span></span>
5. <span data-ttu-id="f2807-118">En el campo **Ejecución programada**, seleccione el intervalo de tiempo.</span><span class="sxs-lookup"><span data-stu-id="f2807-118">In the **Scheduled execution** field, select the time interval.</span></span>
6. <span data-ttu-id="f2807-119">Seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="f2807-119">Select **Save**.</span></span>

![Ejecución programada](media/20-setup-for-work-orders.png)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]