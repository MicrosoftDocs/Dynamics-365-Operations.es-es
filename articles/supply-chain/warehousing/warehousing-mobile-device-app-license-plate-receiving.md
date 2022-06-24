---
title: Recepción de matrículas de entidad de almacén mediante la aplicación móvil Warehouse Management
description: Este artículo explica cómo configurar la aplicación móvil Warehouse Management para admitir el uso de un proceso de recepción de matrículas para recibir inventario físico.
author: perlynne
ms.date: 04/29/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: WHSParameters, WHSRFMenuItem, WHSLicensePlate, WHSPackingStructure
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2020-03-31
ms.dyn365.ops.version: 10.0.11
ms.openlocfilehash: fe083f16bd47b3f7bdfd366ae4b0fe4a02f49185
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/03/2022
ms.locfileid: "8907011"
---
# <a name="license-plate-receiving-via-the-warehouse-management-mobile-app"></a>Recepción de matrículas de entidad de almacén mediante la aplicación móvil Warehouse Management

[!include [banner](../includes/banner.md)]

Este artículo explica cómo configurar la aplicación móvil Warehouse Management para admitir el uso de un proceso de recepción de matrículas para recibir inventario físico.

Puede usar esta funcionalidad para registrar rápidamente la recepción del inventario entrante relacionado con un aviso de envío por adelantado (ASN). El sistema crea automáticamente un aviso de envío por adelantado cuando los procesos de gestión de almacén se utilizan para enviar un pedido de transferencia. Para el proceso de pedido de compra, un aviso de envío por adelantado puede registrarse manualmente o puede importarse automáticamente mediante el uso de un proceso de entidad de datos de aviso de envío por adelantado entrante.

Los datos de aviso de envío por adelantado están vinculados a cargas y envíos a través de *estructuras de embalaje*, donde los pallets (matrículas principales) pueden contener cajas (matrículas anidadas).

> [!NOTE]
> Para reducir el número de transacciones de inventario cuando se utilizan estructuras de embalaje que tienen matrículas anidadas, el sistema registra el inventario físico disponible en la placa principal. Para activar el movimiento del inventario físico disponible de la matrícula principal a las matrículas anidadas, en función de los datos de la estructura de embalaje, el dispositivo móvil debe proporcionar un elemento de menú que se base en el proceso de creación de trabajo *Paquete de matrículas anidadas*.

## <a name="warehousing-mobile-device-app-processing"></a>Almacenamiento de procesamiento de aplicaciones de dispositivos móviles

Cuando un trabajador escanea un id. de matrícula entrante, el sistema inicializa un proceso de recepción de matrícula. En base a esta información, el contenido de la matrícula (datos provenientes de la ASN) se registra físicamente en la ubicación del muelle de entrada. Los flujos que siguen dependerán de las necesidades de su proceso empresarial.

## <a name="work-policies"></a>Directivas de trabajo

Como con (por ejemplo) el proceso del elemento del menú del dispositivo móvil *Informar como terminado*, el proceso de recepción de matrículas admite varios flujos de trabajo basados en la configuración definida.

### <a name="work-policies-with-work-creation"></a>Políticas de trabajo con creación de trabajo

Cuando registra artículos entrantes utilizando una política de trabajo que crea trabajo, el sistema genera y guarda registros de trabajo de almacenamiento para cada registro. Si usas el proceso de trabajo *Matrícula que recibe y guarda*, en ese caso el registro y el almacenamiento se manejan como una sola operación utilizando un único artículo del menú del dispositivo móvil. Si usas el proceso *Recepción de matrícula*, luego los procesos de recepción y almacenamiento se manejan como dos operaciones de almacén diferentes, cada una con su propio elemento de menú del dispositivo móvil.

### <a name="work-policies-without-work-creation"></a>Políticas de trabajo sin creación de trabajo

Puede utilizar el proceso de recepción de matrículas sin crear trabajo. Si define políticas de trabajo que tienen un tipo de orden de trabajo de *Recibo de transferencía* y/o *Ordenes de compra* y usa el proceso para *Recepción de matrícula (y guardado)*, los siguientes dos procesos de aplicaciones móviles de Warehousing no crearán trabajo. En cambio, solo registrarán el inventario físico entrante en la matrícula, en el muelle de recepción entrante.

- *Recepción de matrícula de entidad de almacén*
- *Recepción de matrícula de entidad de almacén y ubicación*

> [!NOTE]
> - Debe definir al menos una ubicación para una política de trabajo en la sección **Ubicaciones de inventario**. No puede especificar la misma ubicación para múltiples políticas de trabajo.
> - La opción **Imprimir etiqueta** para almacenar elementos del menú del dispositivo móvil no imprimirá una etiqueta de licencia sin creación de trabajo.

Para que esta funcionalidad esté disponible en su sistema, debe activar la característica *Mejoras en la recepción de matrículas* en [administración de características](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md).

### <a name="receive-inventory-on-a-location-that-doesnt-track-license-plates"></a>Recibir inventario en una ubicación que no rastree las matrículas

Es posible utilizar una ubicación de almacén asignada a un perfil de ubicación incluso cuando **Utilice el seguimiento de matrículas** no está activado. Por lo tanto, cuando recibe inventario, puede registrar directamente el inventario disponible en una ubicación sin creación de trabajo.

## <a name="add-mobile-device-menu-items-for-each-receiving-location-in-a-warehouse"></a>Agregar elementos de menú del dispositivo móvil para cada ubicación de recepción de un almacén

La característica *Mejoras en la recepción de matrículas* le permite recibir en cualquier ubicación de un almacén agregando artículos de menú que reciben (y guardan) placas de matrícula específicas de la ubicación a la aplicación móvil Warehousing. Anteriormente, el sistema admitía recibir solo en la ubicación predeterminada que se define para cada almacén. Sin embargo, cuando esta característica está activada, los elementos del menú del dispositivo móvil para recepción de matrícula (y guardado) ahora proporcionan la opción **Usar datos predeterminados**, que le permite seleccionar una ubicación "a" personalizada para cada elemento del menú. (Esta opción ya estaba disponible para algunos otros tipos de elementos de menú).

Para que esta funcionalidad esté disponible en su sistema, debe activar la característica *Mejoras en la recepción de matrículas* en [administración de características](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md).

## <a name="show-or-skip-the-receiving-summary-page"></a>Mostrar u omitir la página de resumen de recepción

Puedes usar la característica *Controle si desea mostrar una página de resumen de recepción en dispositivos móviles* para aprovechar un flujo adicional detallado de la aplicación móvil Warehouse Management como parte del proceso de recepción de matrículas.

Cuando esta característica está activada, los elementos del menú del dispositivo móvil para la recepción de matrículas o la recepción y almacenamiento de matrículas proporcionarán un ajuste **Mostrar la página de resumen de recepción**. Esta configuración tiene las siguientes opciones:

- **Mostrar un resumen detallado** - Durante la recepción de la placa, los trabajadores verán una página adicional que muestra la información de aviso de envío por adelantado completa.
- **Saltar el resumen** - Los trabajadores no verán la información completa de aviso del envío por adelantado. Los trabajadores del almacén tampoco podrán establecer un código de disposición ni agregar excepciones durante el proceso de recepción.

Para usar esta funcionalidad, la característica *Controlar si desea mostrar una página de resumen de recepción en dispositivos móviles* debe activarse en su sistema. A partir de la versión 10.0.21 de Supply Chain Management, esta función está activada de forma predeterminada. A partir de la versión 10.0.25 de Supply Chain Management, esta característica es obligatoria y no se puede desactivar. Si está ejecutando una versión anterior a la 10.0.25, los administradores pueden activar o desactivar esta funcionalidad buscando la característica *Controlar si desea mostrar una página de resumen de recepción en dispositivos móviles* en el espacio de trabajo [Administración de características](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md).

## <a name="prevent-transfer-ordershipped-license-plates-from-being-used-at-warehouses-other-than-the-destination-warehouse"></a>Evite que las matrículas del pedido de transferencia enviadas se utilicen en almacenes que no sean el almacén de destino

No se puede utilizar un proceso de recepción de matrículas si un aviso de envío por adelantado contiene una id. de matrícula que ya existe y tiene datos físicos disponibles en una ubicación de almacén distinta de la ubicación de almacén donde se está registrando la matrícula.

Para escenarios de órdenes de transferencia donde el almacén de tránsito no rastrea las matrículas de entidad (y, por lo tanto, tampoco rastrea el inventario físico disponible por matrícula), puede usar la característica *Evite que las matrículas de la orden de transferencia enviadas se utilicen en otros almacenes distintos del almacén de destino* para evitar actualizaciones físicas disponibles de las matrículas de entidad que están en tránsito. Para que esta funcionalidad esté disponible, debe activar la característica *Evitar que la transferencia de matrículas de pedido se usen en otros almacenes que no sean el almacén de destino* en su sistema. A partir de la versión 10.0.25 de Supply Chain Management, esta característica es obligatoria y no se puede desactivar. Si está ejecutando una versión anterior a la 10.0.25, los administradores pueden activar o desactivar esta característica en el espacio de trabajo [Administración de características](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md).

Para administrar la funcionalidad cuando esta característica está disponible, siga estos pasos.

1. Vaya a **Gestión de almacenes \> Configuración \> Parámetros de gestión de almacenes**.
1. En la pestaña **General**, en la ficha desplegable **Matrículas de entidad**, configure el campo **Política de matrícula de almacén de tránsito** a uno de los siguientes valores:

    - **Permitir la reutilización de matrículas no rastreadas** - El sistema funciona de la misma manera que funciona cuando la características *Evite que las matrículas de entidad de la orden de transferencia enviadas se utilicen en otros almacenes que no sean el almacén de destino* no está disponible. Este valor es la configuración predeterminada cuando activa la característica por primera vez.
    - **Evitar la reutilización de matrículas no rastreadas** - Solo las actualizaciones disponibles que estén relacionadas con una matrícula enviada se permitirán en el almacén de destino hasta que se haya recibido la orden de transferencia.

## <a name="more-information"></a>Más información

Para obtener más información sobre los elementos del menú del dispositivo móvil, consulte [Configurar dispositivos móviles para trabajos de almacén](configure-mobile-devices-warehouse.md).

Para más información sobre el escenario de producción *Informar como terminado*, consulte el [Resumen de políticas de trabajo de almacén](warehouse-work-policies.md).

Para más información sobre la gestión de cargas entrantes , consulte [Gestión de almacén de cargas entrantes para pedidos de compra](inbound-load-handling.md).


[!INCLUDE[footer-include](../../includes/footer-banner.md)]