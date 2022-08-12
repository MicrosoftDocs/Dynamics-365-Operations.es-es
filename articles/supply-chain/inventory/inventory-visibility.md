---
title: Información general sobre el complemento de visibilidad de inventario
description: Este artículo explica qué es la visibilidad de inventario y describe sus características.
author: yufeihuang
ms.date: 03/18/2022
ms.topic: overview
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: yufeihuang
ms.search.validFrom: 2020-10-26
ms.dyn365.ops.version: 10.0.15
ms.openlocfilehash: 274f9b368a6074725d1938de5f2172d2810a5985
ms.sourcegitcommit: 28a726b3b0726ecac7620b5736f5457bc75a5f84
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/29/2022
ms.locfileid: "9066652"
---
# <a name="inventory-visibility-add-in-overview"></a>Información general sobre el complemento de visibilidad de inventario

[!include [banner](../includes/banner.md)]

El complemento de visibilidad de inventario (también conocido como *Servicio de Visibilidad de inventario*) ofrece un microservicio independiente y altamente escalable que permite el seguimiento de los cambios de inventario disponible en tiempo real y el seguimiento de la visibilidad en tiempo real en todos sus orígenes de datos y canales. Proporciona una plataforma que le permite administrar su inventario global mediante el uso de una funcionalidad que incluye (pero no se limita a) la siguiente lista:

- Realice un seguimiento centralizado del estado del inventario más reciente (como disponible, pedido, comprado, en tránsito, devuelto y en cuarentena) en todos sus orígenes de datos, almacenes y ubicaciones conectando su Supply Chain Management u orígenes de datos de logística de terceros (tales como sistemas de gestión de pedidos, sistemas de planificación de recursos empresariales de terceros \[ ERP\], punto de venta\[ PDV\] y sistemas de gestión de almacenes) al servicio de visibilidad de inventario.
- Consulte la disponibilidad de stock y la escasez de existencias disponibles y obtenga respuestas inmediatas llamando directamente al servicio de Visibilidad de inventario.
- Evite la sobreventa, especialmente cuando su demanda proviene de diferentes canales, haciendo reservas flexibles en tiempo real en el servicio de Visibilidad de inventario.
- Administre mejor los pedidos comprometidos y las expectativas de los clientes al proporcionar fechas precisas actuales o próximas disponibles, de modo que la función omnicanal neto no comprometido (NNC) pueda calcular las fechas esperadas de cumplimiento de pedidos.

## <a name="extensibility"></a>Extensibilidad

El servicio de visibilidad de inventario es altamente extensible porque la entrada y salida de datos no están restringidas a las aplicaciones de Microsoft. Los sistemas externos pueden acceder al servicio a través de interfaces de programación de aplicaciones (API) RESTful. Además de usar las asignaciones listas para usar que se proporcionan para el origen de datos y las dimensiones de Supply Chain Management, puede integrar la visibilidad de inventario con múltiples sistemas de terceros configurando orígenes de datos adicionales, medidas de estado de inventario (denominadas *medidas físicas* en el servicio de visibilidad de inventario) y las dimensiones del inventario a través de la aplicación de configuración. De esta forma, puede consultar y cambiar de manera flexible sus múltiples orígenes de datos y dimensiones de inventario predefinidas.

Además, dado que la visibilidad del inventario se basa en Microsoft Dataverse, sus datos se pueden usar para compilar e integrarse con Power Apps. También puede aplicar Power BI para crear paneles de información personalizados que cumplan con los requisitos de su negocio.

## <a name="scalability"></a>Escalabilidad

El servicio de visibilidad de inventario se puede escalar hacia arriba o hacia abajo, según el volumen de datos. La experiencia de escalabilidad es normalmente fluida y la lleva a cabo el equipo de la plataforma de Microsoft, en función de la detección y evaluación automáticas del volumen de datos de transacciones.

## <a name="feature-highlights"></a>Características destacadas

### <a name="get-a-global-view-of-real-time-inventory"></a>Obtener una vista global del inventario en tiempo real

Visibilidad de inventario garantiza que tenga acceso a las cantidades de inventario más actualizadas en todo momento, en todos sus canales, ubicaciones y almacenes. Se beneficiará más de usarlo para respaldar su negocio operativo diario siempre que deba obtener registros de inventario. El inventario físico disponible, las cantidades vendidas y las cantidades compradas están disponibles de inmediato. También puede configurar otras medidas de inventario físico (como datos devueltos, en cuarentena y publicados) según lo requiera, a fin de obtener esos detalles en tiempo real. Visibilidad de inventario puede procesar eficientemente millones de publicaciones de cambio de inventario. Estos datos se pueden agregar y reflejar en las últimas cantidades de inventario en el servicio de inmediato, por segundo o por minuto, según el intervalo en el que se publiquen los datos. Para obtener más información, consulte [API públicas de Visibilidad de inventario](inventory-visibility-api.md).

### <a name="soft-reservation-to-avoid-overselling-across-all-order-channels"></a>Reserva flexible para evitar la sobreventa en todos los canales de pedidos

Una *reserva flexible* le permite asignar o marcar cantidades específicas para cumplir con un pedido o demanda. Una reserva flexible no afecta el inventario físico, pero sí resta de la cantidad de inventario *Disponible para reserva* y proporciona una cantidad actualizada para el cumplimiento de pedidos en el futuro. Esta función será útil si las solicitudes de ventas o los pedidos ingresan a su negocio desde uno o más canales u orígenes de datos que están fuera de su sistema de planificación de recursos empresariales (ERP) del sistema de registro.

Si no utiliza reservas flexibles en el servicio de visibilidad de inventario, debe esperar hasta que el sistema ERP sincronice y procese el pedido para obtener una actualización de la cantidad de inventario físico. Este proceso suele tener una latencia enorme. Sin embargo, las reservas flexibles tienen efecto inmediato cada vez que se genera una solicitud de venta o un pedido en sus canales de venta. Por lo tanto, ayudan a prevenir situaciones de sobreventa al garantizar que sus pedidos omnicanal no interfieran entre sí cuando finalmente lleguen al sistema ERP. Las reservas flexibles también garantizan que pueda cumplir con todos los pedidos comprometidos. Por lo tanto, lo ayudan a cumplir con las expectativas del cliente y mantener la lealtad del cliente. Para obtener más información, consulte [Reservas de Visibilidad de inventario](inventory-visibility-reservations.md).

### <a name="immediate-response-of-atp-dates-confirmation"></a>Respuesta inmediata de confirmación de fechas de NNC

La visibilidad de su inventario proyectado a corto plazo (incluidos el suministro, la demanda y los detalles disponibles proyectados) es importante porque ayuda a su empresa a lograr los siguientes objetivos:

- Minimizar los niveles de inventario para reducir los costes de administración de inventario.
- Facilitar el procesamiento de pedidos internos, para que los vendedores puedan calcular las fechas de envío y entrega en función de la disponibilidad de los productos que se solicitan.
- Proporcionar transparencia sobre cuándo los clientes pueden esperar que un artículo agotado esté disponible, proporcionando para ello la próxima fecha disponible.

La función NNC es fácil de adoptar en su proceso diario de entrega de pedidos. Lo que es más importante, al igual que otras ofertas de visibilidad de inventario, la función NNC es *global y en tiempo real*. Por lo tanto, puede configurar varias fórmulas de cálculo de NNC para tener consultas de disponibilidad de inventario completas que cubran todos sus canales comerciales y fuentes de datos. Para obtener más información, consulte [Planes de cambio de visibilidad de inventario disponible y neto no comprometido](inventory-visibility-available-to-promise.md).

### <a name="compatibility-with-warehouse-management-processes-wms-items"></a>Compatibilidad con elementos de procesos de gestión de almacenes (WMS)

Microsoft tiene como objetivo proporcionar una integración lista para usar con procesos de gestión de almacenes (WMS), para que los clientes de WMS también puedan disfrutar de los beneficios del servicio de visibilidad de inventario. Según el primer lanzamiento de versiones de 2022 (versión preliminar pública en marzo), el servicio de inventario admite consultas de artículos disponibles WHS y NNC. La función de reserva flexible y asignación será compatible con los clientes de WMS en el próximo lanzamiento. Para obtener más información, consulte [Compatibilidad de visibilidad de inventario para artículos WMS](inventory-visibility-whs-support.md).

## <a name="licensing"></a>Licencias

El servicio de visibilidad de inventario está disponible en las siguientes versiones:

- **Complemento de visibilidad de inventario para Microsoft Dynamics 365 Supply Chain Management** – Para las empresas que tienen una licencia válida de Supply Chain Management, visibilidad de inventario está disponible sin coste de licencia adicional. Puede empezar a probarlo hoy. Para obtener más detalles de instalación, consulte [Instalar y configurar la visibilidad del inventario ](inventory-visibility-setup.md).
- **Servicio de visibilidad de inventario como componente de IOM** – Esta versión es para clientes de Intelligent Order Management (IOM) o empresas que no utilizan Supply Chain Management como su sistema ERP. La licencia está incluida en el conjunto IOM. Para más información, vea [Resumen de Intelligent Order Management](/dynamics365/intelligent-order-management/overview).

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
