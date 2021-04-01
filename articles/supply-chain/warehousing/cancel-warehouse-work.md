---
title: Cancelar trabajo de almacén para control de excepciones
description: En este tema se describe la funcionalidad Cancelar trabajo que permite a los supervisores de almacén gestionar el trabajo bloqueado.
author: omulvad
manager: tfehr
ms.date: 10/15/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSTroubIeshootingSeIfService, WHSTroubleshootingSelfService
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2019-10-1
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 21cfa03ed52ffce32267ec0497ae3443937c1018
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2021
ms.locfileid: "5233112"
---
# <a name="cancel-warehouse-work-for-exception-handling"></a><span data-ttu-id="680f1-103">Cancelar trabajo de almacén para control de excepciones</span><span class="sxs-lookup"><span data-stu-id="680f1-103">Cancel warehouse work for exception handling</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="680f1-104">La funcionalidad Cancelar trabajo en Microsoft Dynamics 365 Supply Chain Management permite al usuario administrador cancelar un determinado trabajo de almacén que está actualmente en curso, pero que está bloqueado por el sistema o no se puede completar debido a circunstancias excepcionales.</span><span class="sxs-lookup"><span data-stu-id="680f1-104">The Cancel work functionality in Microsoft Dynamics 365 Supply Chain Management lets the admin user cancel specific warehouse work that is currently in progress, but that is blocked by the system or can't be completed because of exceptional circumstances.</span></span> <span data-ttu-id="680f1-105">Esta funcionalidad es una alternativa segura y atractiva a las secuencias de comandos correctivos de SQL que corrigen datos incoherentes.</span><span class="sxs-lookup"><span data-stu-id="680f1-105">This functionality is an attractive and secure alternative to SQL corrective scripts that fix inconsistent data.</span></span> <span data-ttu-id="680f1-106">Sin embargo, mientras que estas secuencias de comandos se suelen solicitar a los profesionales de TI, los usuarios de la empresa que tengan derechos de administrador pueden usar la funcionalidad Cancelar trabajo.</span><span class="sxs-lookup"><span data-stu-id="680f1-106">However, whereas these scripts are typically requested from IT professionals, the Cancel work functionality can be used by users in the company who have admin rights.</span></span>

<span data-ttu-id="680f1-107">Puede acceder a la funcionalidad Cancelar trabajo en **Gestión de almacenes** \> **Tareas periódicas** \> **Limpiar \> Cancelar trabajo**.</span><span class="sxs-lookup"><span data-stu-id="680f1-107">You can access the Cancel work functionality at **Warehouse management** \> **Periodic tasks** \> **Clean up \> Cancel work**.</span></span> <span data-ttu-id="680f1-108">En el cuadro de diálogo **Cancelar trabajo**, especifique el id. de trabajo del trabajo que desee cancelar y, a continuación, seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="680f1-108">In the **Cancel work** dialog box, specify the work ID of the work to cancel, and then select **OK**.</span></span>

## <a name="warehouse-work-that-can-be-canceled"></a><span data-ttu-id="680f1-109">Trabajo de almacén que se puede cancelar</span><span class="sxs-lookup"><span data-stu-id="680f1-109">Warehouse work that can be canceled</span></span>

<span data-ttu-id="680f1-110">Durante las operaciones de picking de almacén, un trabajador puede encontrarse situaciones en las que ha registrado cantidades como seleccionadas desde una ubicación de almacenamiento a su ubicación de usuario, pero que no puede registrar la operación de colocación.</span><span class="sxs-lookup"><span data-stu-id="680f1-110">During warehouse picking operations, a worker might encounter situations where they have registered quantities as picked from a storage location to their user location, but then they can't register the put operation.</span></span> <span data-ttu-id="680f1-111">Los datos incoherentes del almacén suelen ser, pero no siempre, el motivo por el que se bloquea el trabajo.</span><span class="sxs-lookup"><span data-stu-id="680f1-111">Inconsistent warehouse data is often, but not always, the reason why work is blocked.</span></span>

<span data-ttu-id="680f1-112">A diferencia de la funcionalidad habitual de Cancelar a la que se puede acceder mediante el botón **Cancelar** en el encabezado de trabajo, la funcionalidad Cancelar trabajo no requiere que la última línea de trabajo completada sea una línea de trabajo del tipo **colocación**.</span><span class="sxs-lookup"><span data-stu-id="680f1-112">Unlike the regular Cancel functionality that can be accessed by using the **Cancel** button on the work header, the Cancel work functionality doesn't require that the last completed work line be a work line of the **put** type.</span></span> <span data-ttu-id="680f1-113">Es decir, para la funcionalidad Cancelar trabajo, la lógica de cancelación se puede ejecutar incluso si la cantidad de artículos en una línea del trabajo está en una ubicación de usuario.</span><span class="sxs-lookup"><span data-stu-id="680f1-113">In other words, for the Cancel work functionality, cancellation logic can be run even if the item quantity on a work line is in a user location.</span></span>

> [!NOTE]
> <span data-ttu-id="680f1-114">Para el trabajo que se debe cancelar por razones operativas, los usuarios de almacén deben seguir usando la funcionalidad Cancelar en la página de trabajo.</span><span class="sxs-lookup"><span data-stu-id="680f1-114">For work that must be canceled for operational reasons, warehouse users must continue to use the regular Cancel functionality on the work page.</span></span>

<span data-ttu-id="680f1-115">Solo se puede cancelar el trabajo del tipo **Ventas**, **Emisión de transferencia**, **Picking de materia prima** o **Reabastecimiento** mediante la funcionalidad Cancelar trabajo.</span><span class="sxs-lookup"><span data-stu-id="680f1-115">Only work of the **Sales**, **Transfer issue**, **Raw material picking**, or **Replenishment** type can be canceled by using the Cancel work functionality.</span></span> <span data-ttu-id="680f1-116">La lógica de cancelación no se ejecutará para un trabajo de picking de materia prima ni para un trabajo que se puede cancelar mediante la funcionalidad habitual Cancelar (consulte la nota anterior).</span><span class="sxs-lookup"><span data-stu-id="680f1-116">Cancellation logic won't be run for frozen raw material picking work or work that can be canceled by using the regular Cancel functionality (see the preceding note).</span></span>

<span data-ttu-id="680f1-117">Para desbloquear el trabajo, el sistema cancela cualquier línea de trabajo restante y corrige los datos de almacén que se asocian al id. de trabajo que especificó el usuario.</span><span class="sxs-lookup"><span data-stu-id="680f1-117">To unblock the work, the system cancels any remaining work lines and fixes the warehouse data that is associated with the work ID that the user specified.</span></span> <span data-ttu-id="680f1-118">A continuación, se puede reanudar cualquier operación habitual de manipulación en el almacén que implique la cantidad de artículos afectada.</span><span class="sxs-lookup"><span data-stu-id="680f1-118">Any regular warehouse-handling operations that involve the affected item quantity can then resume.</span></span>

<span data-ttu-id="680f1-119">Para poner el artículo afectado en una ubicación concreta después de que se cancele el trabajo, el usuario debe usar una operación de movimiento de inventario o de ajuste de cantidad en un dispositivo móvil.</span><span class="sxs-lookup"><span data-stu-id="680f1-119">To put the affected item in a specific location after the work is canceled, the user must use an inventory movement or quantity adjustment operation on a mobile device.</span></span>


[!INCLUDE[footer-include](../../includes/footer-banner.md)]