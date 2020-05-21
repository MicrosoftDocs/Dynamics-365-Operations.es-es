---
title: Matrícula que se recibe a través de la aplicación de almacenamiento
description: Este tema explica cómo configurar la aplicación Warehouse Mobile para admitir el uso de un proceso de recepción de matrículas para recibir inventario físico.
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
ms.openlocfilehash: 7d5ac6598ab80ece0164d7c92f5d84e91d21b385
ms.sourcegitcommit: ffd845d4230646499b6f074cb43e69ab95787671
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/07/2020
ms.locfileid: "3346385"
---
# <a name="license-plate-receiving-via-the-warehousing-app"></a>Matrícula que se recibe a través de la aplicación de almacenamiento

Este tema explica cómo configurar la aplicación de almacenamiento para admitir el uso de un proceso de recepción de matrículas para recibir inventario físico.

Puede usar esta funcionalidad para registrar rápidamente la recepción del inventario entrante relacionado con un aviso de envío por adelantado (ASN). El sistema crea automáticamente un aviso de envío por adelantado cuando los procesos de gestión de almacén se utilizan para enviar un pedido de transferencia. Para el proceso de pedido de compra, un aviso de envío por adelantado puede registrarse manualmente o puede importarse automáticamente mediante el uso de un proceso de entidad de datos de aviso de envío por adelantado entrante.

Los datos de aviso de envío por adelantado están vinculados a cargas y envíos a través de *estructuras de embalaje*, donde los pallets (matrículas principales) pueden contener cajas (matrículas anidadas).

> [!NOTE]
> Para reducir el número de transacciones de inventario cuando se utilizan estructuras de embalaje que tienen matrículas anidadas, el sistema registra el inventario físico disponible en la placa principal. Para activar el movimiento del inventario físico disponible de la matrícula principal a las matrículas anidadas, en función de los datos de la estructura de embalaje, el dispositivo móvil debe proporcionar un elemento de menú que se base en el proceso de creación de trabajo *Paquete de matrículas anidadas*.

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

## <a name="show-or-skip-the-receiving-summary-page"></a>Mostrar u omitir la página de resumen de recepción

Puedes usar la función *Controlar si mostrar una página de resumen de recepción en dispositivos móviles* para aprovechar un flujo adicional detallado de la aplicación de almacenamiento como parte del proceso de recepción de matrículas.

Antes de poder usar esta función debe estar activada en su sistema. Los administradores pueden usar la configuración de [gestión de funciones](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) para verificar el estado de la función y activarla. En el espacio de trabajo **Administración de características**, esta característica aparece de la siguiente forma:

- **Módulo:** *Gestión de almacén*
- **Nombre de la característica:** *Controle si desea mostrar una página de resumen de recepción en dispositivos móviles*

Cuando esta función está activada, los elementos del menú del dispositivo móvil para la recepción de matrículas o la recepción y almacenamiento de matrículas proporcionarán un ajuste **Mostrar la página de resumen de recepción**. Esta configuración tiene las siguientes opciones:

- **Mostrar un resumen detallado** - Durante la recepción de la placa, los trabajadores verán una página adicional que muestra la información de aviso de envío por adelantado completa.
- **Saltar el resumen** - Los trabajadores no verán la información completa de aviso del envío por adelantado. Los trabajadores del almacén tampoco podrán establecer un código de disposición ni agregar excepciones durante el proceso de recepción.

## <a name="prevent-transfer-ordershipped-license-plates-from-being-used-at-warehouses-other-than-the-destination-warehouse"></a>Evite que las matrículas del pedido de transferencia enviadas se utilicen en almacenes que no sean el almacén de destino

No se puede utilizar un proceso de recepción de matrículas si un aviso de envío por adelantado contiene una Id. de matrícula que ya existe y tiene datos físicos disponibles en una ubicación de almacén distinta de la ubicación del almacén donde se está registrando la matrícula de entidad.

Para escenarios de órdenes de transferencia donde el almacén de tránsito no rastrea las matrículas de entidad (y, por lo tanto, tampoco rastrea el inventario físico disponible por matrícula), puede usar la característica *Evite que las matrículas de la orden de transferencia enviadas se utilicen en otros almacenes distintos del almacén de destino* para evitar actualizaciones físicas disponibles de las matrículas de entidad que están en tránsito.

Antes de poder usar esta función debe estar activada en su sistema. Los administradores pueden usar la configuración de [gestión de funciones](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) para verificar el estado de la función y activarla. En el espacio de trabajo **Administración de características**, esta característica aparece de la siguiente forma:

- **Módulo:** *Gestión de almacén*
- **Nombre de la característica:** *Evite que las matrículas del pedido de transferencia enviadas se utilicen en otros almacenes que no sean el almacén de destino*

Para administrar la funcionalidad cuando esta función está disponible, siga estos pasos.

1. Vaya a **Gestión de almacenes \> Configuración \> Parámetros de gestión de almacenes**.
1. En la pestaña **General**, en la ficha desplegable **Matrículas de entidad**, configure el campo **Política de matrícula de almacén de tránsito** a uno de los siguientes valores:

    - **Permitir la reutilización de matrículas no rastreadas** - El sistema funciona de la misma manera que funciona cuando la características *Evite que las matrículas de entidad de la orden de transferencia enviadas se utilicen en otros almacenes que no sean el almacén de destino* no está disponible. Este valor es la configuración predeterminada cuando activa la función por primera vez.
    - **Evitar la reutilización de matrículas no rastreadas** - Solo las actualizaciones disponibles que estén relacionadas con una matrícula enviada se permitirán en el almacén de destino hasta que se haya recibido la orden de transferencia.

## <a name="more-information"></a>Más información

<!-- To read more about inbound loads, see [Link for Inbound load (Olga's doc.)] -->

Para obtener más información sobre los elementos del menú del dispositivo móvil, vea [Configurar dispositivos móviles para trabajos de almacén](configure-mobile-devices-warehouse.md).
