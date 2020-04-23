---
title: Recepción de matrículas de entidad de almacén a través de Warehouse Mobile App
description: Este tema explica cómo configurar Warehouse Mobile App para admitir el uso de un proceso de recepción de matrículas para recibir inventario físico.
author: perlynne
manager: tfehr
ms.date: 03/31/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2020-03-31
ms.dyn365.ops.version: Release 10.0.11
ms.openlocfilehash: 98cd608edea1d5365d0d3532244f1fcdb6293d3c
ms.sourcegitcommit: 3a823444005d316bd95fc663e2dbc8252ac7d93a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/14/2020
ms.locfileid: "3261374"
---
# <a name="license-plate-receiving-via-the-warehousing-mobile-app"></a><span data-ttu-id="0c054-103">Recepción de matrículas de entidad de almacén a través de Warehouse Mobile App</span><span class="sxs-lookup"><span data-stu-id="0c054-103">License plate receiving via the Warehousing mobile app</span></span>

<span data-ttu-id="0c054-104">Este tema explica cómo configurar Warehouse Mobile App para admitir el uso de un proceso de recepción de matrículas para recibir inventario físico.</span><span class="sxs-lookup"><span data-stu-id="0c054-104">This topic explains how to set up the Warehousing mobile app so that it supports using a license plate receiving process to receive physical inventory.</span></span>

<span data-ttu-id="0c054-105">Puede usar esta funcionalidad para registrar rápidamente la recepción del inventario entrante relacionado con un aviso de envío por adelantado (ASN).</span><span class="sxs-lookup"><span data-stu-id="0c054-105">You can use this functionality to quickly record the receipt of inbound inventory that is related to an advance ship notice (ASN).</span></span> <span data-ttu-id="0c054-106">El sistema crea automáticamente un aviso de envío por adelantado cuando los procesos de gestión de almacén se utilizan para enviar un pedido de transferencia.</span><span class="sxs-lookup"><span data-stu-id="0c054-106">The system automatically creates an ASN when warehouse management processes are used to ship a transfer order.</span></span> <span data-ttu-id="0c054-107">Para el proceso de pedido de compra, un aviso de envío por adelantado puede registrarse manualmente o puede importarse automáticamente mediante el uso de un proceso de entidad de datos de aviso de envío por adelantado entrante.</span><span class="sxs-lookup"><span data-stu-id="0c054-107">For the purchase order process, an ASN can be manually recorded, or it can be automatically imported by using an inbound ASN data entity process.</span></span>

<span data-ttu-id="0c054-108">Los datos de aviso de envío por adelantado están vinculados a cargas y envíos a través de *estructuras de embalaje*, donde los pallets (matrículas principales) pueden contener cajas (matrículas anidadas).</span><span class="sxs-lookup"><span data-stu-id="0c054-108">The ASN data is linked to loads and shipments via the *packing structures*, where pallets (parent license plates) can contain cases (nested license plates).</span></span>

> [!NOTE]
> <span data-ttu-id="0c054-109">Para reducir el número de transacciones de inventario cuando se utilizan estructuras de embalaje que tienen matrículas anidadas, el sistema registra el inventario físico disponible en la placa principal.</span><span class="sxs-lookup"><span data-stu-id="0c054-109">To reduce the number of inventory transactions when packing structures that have nested license plates are used, the system records the physical on-hand inventory on the parent license plate.</span></span> <span data-ttu-id="0c054-110">Para activar el movimiento del inventario físico disponible de la matrícula principal a las matrículas anidadas, en función de los datos de la estructura de embalaje, el dispositivo móvil debe proporcionar un elemento de menú que se base en el proceso de creación de trabajo *Paquete de matrículas anidadas*.</span><span class="sxs-lookup"><span data-stu-id="0c054-110">To trigger the movement of the physical on-hand inventory from the parent license plate to the nested license plates, based on the packing structure data, the mobile device must provide a menu item that is based on the *Pack to nested license plates* work creation process.</span></span>

<!-- To be used later (will require further editing):
## Warehousing mobile device app processing

When a worker scans an incoming license plate ID, the system initializes a license plate receiving process. Based on this information, the content of the license plate (data coming from the ASN) gets physically registered at the inbound dock location. The flows that follow will depend your business process needs.

## Work policies

As with (for example) the *Report as finished* mobile device menu item process, the license plate receiving process supports several workflows based on the defined setup.

### Work policies with work creation

Registration of physical on-hand where either the same warehouse worker immediately process a put-away work process following the inbound receiving (License plate receiving and put away) or where the registration and put away process gets handled as two different warehouse operations (License plate receiving) following the processing of the put-away work by using the existing work process via another mobile device menu item.

## Work policies without work creation

You can use the license plate receiving process without creating work by using the *License plate receiving without creating work* feature.

By defining **Work policies** with a **Work order type** of *Transfer receipt* and/or *Purchase orders*, and using the **Process** for **License plate receiving (and put away)**, the two Warehousing app process:

- License plate receiving
- License plate receiving and put away

will not create work, but only register the inbound physical inventory on the license plate at the inbound receiving dock.

For more information about the *Report as finished* production scenario, see the [Warehouse work policies overview](warehouse-work-policies.md).

-->

## <a name="show-or-skip-the-receiving-summary-page"></a><span data-ttu-id="0c054-111">Mostrar u omitir la página de resumen de recepción</span><span class="sxs-lookup"><span data-stu-id="0c054-111">Show or skip the receiving summary page</span></span>

<span data-ttu-id="0c054-112">Puedes usar la característica *Controle si desea mostrar una página de resumen de recepción en dispositivos móviles* para aprovechar un flujo adicional detallado de la aplicación Warehouse como parte del proceso de recepción de matrículas.</span><span class="sxs-lookup"><span data-stu-id="0c054-112">You can use the *Control whether to display a receiving summary page on mobile devices* feature to take advantage of an additional detailed Warehouse app flow as part of the license plate receiving process.</span></span>

<span data-ttu-id="0c054-113">Antes de poder usar esta función debe estar activada en su sistema.</span><span class="sxs-lookup"><span data-stu-id="0c054-113">Before you can use this feature, it must be turned on in your system.</span></span> <span data-ttu-id="0c054-114">Los administradores pueden usar la configuración de [gestión de funciones](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) para verificar el estado de la función y activarla.</span><span class="sxs-lookup"><span data-stu-id="0c054-114">Admins can use the [feature management](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) settings to check the status of the feature and turn it on.</span></span> <span data-ttu-id="0c054-115">En el espacio de trabajo **Administración de características**, esta característica aparece de la siguiente forma:</span><span class="sxs-lookup"><span data-stu-id="0c054-115">In the **Feature management** workspace, this feature is listed in the following way:</span></span>

- <span data-ttu-id="0c054-116">**Módulo:** *Gestión de almacén*</span><span class="sxs-lookup"><span data-stu-id="0c054-116">**Module:** *Warehouse management*</span></span>
- <span data-ttu-id="0c054-117">**Nombre de la característica:** *Controle si desea mostrar una página de resumen de recepción en dispositivos móviles*</span><span class="sxs-lookup"><span data-stu-id="0c054-117">**Feature name:** *Control whether to display a receiving summary page on mobile devices*</span></span>

<span data-ttu-id="0c054-118">Cuando esta función está activada, los elementos del menú del dispositivo móvil para la recepción de matrículas o la recepción y almacenamiento de matrículas proporcionarán un ajuste **Mostrar la página de resumen de recepción**.</span><span class="sxs-lookup"><span data-stu-id="0c054-118">When this feature is turned on, mobile device menu items for license plate receiving or license plate receiving and put-away will provide a **Display receiving summary page** setting.</span></span> <span data-ttu-id="0c054-119">Esta configuración tiene las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="0c054-119">This setting has the following options:</span></span>

- <span data-ttu-id="0c054-120">**Mostrar un resumen detallado** - Durante la recepción de la placa, los trabajadores verán una página adicional que muestra la información de aviso de envío por adelantado completa.</span><span class="sxs-lookup"><span data-stu-id="0c054-120">**Display a detailed summary** – During license plate receiving, workers will see an extra page that shows the full ASN information.</span></span>
- <span data-ttu-id="0c054-121">**Saltar el resumen** - Los trabajadores no verán la información completa de aviso del envío por adelantado.</span><span class="sxs-lookup"><span data-stu-id="0c054-121">**Skip the summary** – Workers won't see the full ASN information.</span></span> <span data-ttu-id="0c054-122">Los trabajadores del almacén tampoco podrán establecer un código de disposición ni agregar excepciones durante el proceso de recepción.</span><span class="sxs-lookup"><span data-stu-id="0c054-122">Warehouse workers also won't be able to set a disposition code or add exceptions during the receiving process.</span></span>

## <a name="prevent-transfer-ordershipped-license-plates-from-being-used-at-warehouses-other-than-the-destination-warehouse"></a><span data-ttu-id="0c054-123">Evite que las matrículas del pedido de transferencia enviadas se utilicen en almacenes que no sean el almacén de destino</span><span class="sxs-lookup"><span data-stu-id="0c054-123">Prevent transfer order–shipped license plates from being used at warehouses other than the destination warehouse</span></span>

<span data-ttu-id="0c054-124">No se puede utilizar un proceso de recepción de matrículas si un aviso de envío por adelantado contiene una Id. de matrícula que ya existe y tiene datos físicos disponibles en una ubicación de almacén distinta de la ubicación del almacén donde se está registrando la matrícula de entidad.</span><span class="sxs-lookup"><span data-stu-id="0c054-124">A license plate receiving process can't be used if an ASN contains a license plate ID that already exists and has physical on-hand data at a warehouse location other than the warehouse location where the license plate registration is occurring.</span></span>

<span data-ttu-id="0c054-125">Para escenarios de órdenes de transferencia donde el almacén de tránsito no rastrea las matrículas de entidad (y, por lo tanto, tampoco rastrea el inventario físico disponible por matrícula), puede usar la característica *Evite que las matrículas de la orden de transferencia enviadas se utilicen en otros almacenes distintos del almacén de destino* para evitar actualizaciones físicas disponibles de las matrículas de entidad que están en tránsito.</span><span class="sxs-lookup"><span data-stu-id="0c054-125">For transfer order scenarios where the transit warehouse doesn't track license plates (and therefore also doesn't track physical on-hand inventory per license plate), you can use the *Prevent transfer order shipped license plates from being used on other warehouses than the destination warehouse* feature to prevent physical on-hand updates of license plates that are in transit.</span></span>

<span data-ttu-id="0c054-126">Antes de poder usar esta función debe estar activada en su sistema.</span><span class="sxs-lookup"><span data-stu-id="0c054-126">Before you can use this feature, it must be turned on in your system.</span></span> <span data-ttu-id="0c054-127">Los administradores pueden usar la configuración de [gestión de funciones](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) para verificar el estado de la función y activarla.</span><span class="sxs-lookup"><span data-stu-id="0c054-127">Admins can use the [feature management](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) settings to check the status of the feature and turn it on.</span></span> <span data-ttu-id="0c054-128">En el espacio de trabajo **Administración de características**, esta característica aparece de la siguiente forma:</span><span class="sxs-lookup"><span data-stu-id="0c054-128">In the **Feature management** workspace, this feature is listed in the following way:</span></span>

- <span data-ttu-id="0c054-129">**Módulo:** *Gestión de almacén*</span><span class="sxs-lookup"><span data-stu-id="0c054-129">**Module:** *Warehouse management*</span></span>
- <span data-ttu-id="0c054-130">**Nombre de la característica:** *Evite que las matrículas del pedido de transferencia enviadas se utilicen en otros almacenes que no sean el almacén de destino*</span><span class="sxs-lookup"><span data-stu-id="0c054-130">**Feature name:** *Prevent transfer order shipped license plates from being used on other warehouses than the destination warehouse*</span></span>

<span data-ttu-id="0c054-131">Para administrar la funcionalidad cuando esta función está disponible, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="0c054-131">To manage the functionality when this feature is available, follow these steps.</span></span>

1. <span data-ttu-id="0c054-132">Vaya a **Gestión de almacenes \> Configuración \> Parámetros de gestión de almacenes**.</span><span class="sxs-lookup"><span data-stu-id="0c054-132">Go to **Warehouse management \> Setup \> Warehouse management parameters**.</span></span>
1. <span data-ttu-id="0c054-133">En la pestaña **General**, en la ficha desplegable **Matrículas de entidad**, configure el campo **Política de matrícula de almacén de tránsito** a uno de los siguientes valores:</span><span class="sxs-lookup"><span data-stu-id="0c054-133">On the **General** tab, on the **License plates** FastTab, set the **Transit warehouse license plate policy** field to one of the following values:</span></span>

    - <span data-ttu-id="0c054-134">**Permitir la reutilización de matrículas no rastreadas** - El sistema funciona de la misma manera que funciona cuando la características *Evite que las matrículas de entidad de la orden de transferencia enviadas se utilicen en otros almacenes que no sean el almacén de destino* no está disponible.</span><span class="sxs-lookup"><span data-stu-id="0c054-134">**Allow reuse of non-tracked license plate** – The system works the same way that it works when the *Prevent transfer order shipped license plates from being used on other warehouses than the destination warehouse* feature isn't available.</span></span> <span data-ttu-id="0c054-135">Este valor es la configuración predeterminada cuando activa la función por primera vez.</span><span class="sxs-lookup"><span data-stu-id="0c054-135">This value is the default setting when you first activate the feature.</span></span>
    - <span data-ttu-id="0c054-136">**Evitar la reutilización de matrículas no rastreadas** - Solo las actualizaciones disponibles que estén relacionadas con una matrícula enviada se permitirán en el almacén de destino hasta que se haya recibido la orden de transferencia.</span><span class="sxs-lookup"><span data-stu-id="0c054-136">**Prevent reuse of non-tracked license plate** – Only on-hand updates that are related to a shipped license plate will be allowed at the destination warehouse until the transfer order has been received.</span></span>

## <a name="more-information"></a><span data-ttu-id="0c054-137">Más información</span><span class="sxs-lookup"><span data-stu-id="0c054-137">More information</span></span>

<!-- To read more about inbound loads, see [Link for Inbound load (Olga's doc.)] -->

<span data-ttu-id="0c054-138">Para obtener más información sobre los elementos del menú del dispositivo móvil, vea [Configurar dispositivos móviles para trabajos de almacén](configure-mobile-devices-warehouse.md).</span><span class="sxs-lookup"><span data-stu-id="0c054-138">For more information about mobile device menu items, see [Set up mobile devices for warehouse work](configure-mobile-devices-warehouse.md).</span></span>
