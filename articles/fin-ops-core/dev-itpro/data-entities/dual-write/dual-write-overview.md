---
title: Visión general de la doble escritura
description: Este tema describe de forma general la doble escritura, que proporciona interacción casi en tiempo real entre aplicaciones de interacción con los clientes y aplicaciones de Finance and Operations.
author: RamaKrishnamoorthy
ms.date: 02/06/2020
ms.topic: article
audience: Application User, IT Pro
ms.reviewer: tfehr
ms.custom: intro-internal
ms.search.region: global
ms.author: ramasri
ms.search.validFrom: 2020-01-06
ms.openlocfilehash: 131c002000ee6ebed81a23f45ce17b7a7fff0b95
ms.sourcegitcommit: 9f8da0ae3dcf3861e8ece2c2df4f693490563d5e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/16/2021
ms.locfileid: "7817370"
---
# <a name="dual-write-overview"></a>Visión general de la doble escritura

[!include [banner](../../includes/banner.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]



## <a name="what-is-dual-write"></a>¿Qué es la doble escritura?

La doble escritura es una infraestructura lista para usar que proporciona interacción casi en tiempo real entre aplicaciones de interacción con los clientes y aplicaciones de Finance and Operations. Cuando los datos sobre clientes, productos, personas y operaciones fluyen más allá de los límites de la aplicación, todos los departamentos de una organización tienen poder.

La doble escritura proporciona una integración bidireccional estrechamente acoplada entre aplicaciones Finance and Operations y Dataverse. Cualquier cambio de datos en aplicaciones Finance and Operations hace que se escriba en Dataverse y cualquier cambio de datos en Dataverse hace que se escriba en las aplicaciones Finance and Operations. Este flujo de datos automatizado proporciona una experiencia de usuario integrada en todas las aplicaciones.

![Relación de datos entre aplicaciones.](media/dual-write-overview.jpg)

La doble escritura tiene dos aspectos: un aspecto *infraestructura* y un aspecto *solicitud*.

### <a name="infrastructure"></a>Infraestructura

La infraestructura de doble escritura es extensible y fiable, e incluye las siguientes características clave:

+ Flujo de datos síncrono y bidireccional entre aplicaciones
+ Sincronización, junto con modos de reproducción, pausa y recuperación para admitir el sistema durante los modos en línea y fuera de línea / asíncrono.
+ Capacidad para sincronizar datos iniciales entre las aplicaciones
+ Vista combinada de actividad y registros de errores para administradores de datos
+ Posibilidad de configurar alertas y umbrales personalizados y suscribirse a notificaciones
+ Interfaz de usuario intuitiva (UI) para filtrado y transformaciones
+ Capacidad para establecer y ver las dependencias y relaciones de la tabla
+ Extensibilidad para tablas y mapas estándar y personalizados
+ Administración fiable del ciclo de vida de la aplicación
+ Experiencia de configuración lista para usar para nuevos clientes

### <a name="application"></a>Solicitud

La doble escritura crea una asignación entre conceptos en aplicaciones de Finance and Operations aplicaciones y conceptos en aplicaciones de interacción con los clientes. Esta integración admite los siguientes escenarios:

+ Maestro de clientes integrado
+ Acceso a tarjetas de fidelización de clientes y puntos de recompensa
+ Experiencia unificada del producto maestro
+ Reconocimiento de jerarquía organizativa
+ Maestro de proveedores integrado
+ Acceso a datos financieros y de referencia fiscal
+ Experiencia de motor de precio bajo demanda
+ Experiencia integrada de cliente potencial a efectivo
+ Capacidad para servir tanto los activos internos como los activos de los clientes a través de agentes de campo
+ Experiencia integrada de adquisición a pago
+ Actividades integradas y notas para los datos y documentos del cliente
+ Capacidad para buscar disponibilidad de inventario disponible y detalles
+ Experiencia cliente potencial a efectivo
+ Capacidad para manejar múltiples direcciones y roles a través del concepto de parte


## <a name="top-reasons-to-use-dual-write"></a>Principales razones para usar doble escritura

La doble escritura proporciona integración de datos en las aplicaciones Microsoft Dynamics 365. Este marco robusto vincula entornos y permite que diferentes aplicaciones empresariales trabajen juntas. Estas son las principales razones por las que debería usar la doble escritura:

+ La doble escritura proporciona una integración estrechamente acoplada, casi en tiempo real y bidireccional entre aplicaciones Finance and Operations y aplicaciones Customer Engagement. Esta integración hace de Microsoft Dynamics 365 la ventanilla única para todas sus soluciones empresariales. Los clientes que usan Dynamics 365 Finance y Dynamics 365 Supply Chain Management, pero que usan soluciones que no son de Microsoft para la gestión de relaciones con los clientes (CRM), se están pasando a Dynamics 365 por su soporte de doble escritura.
+ Los datos de clientes, productos, operaciones, proyectos e Internet de las cosas (IoT) fluyen automáticamente a Dataverse a través de doble escritura. Esta conexión es útil para las empresas que están interesadas en expansiones de Power Platform.
+ La infraestructura de doble escritura sigue el principio sin código / código bajo. Se requiere un mínimo esfuerzo de ingeniería para ampliar los mapas estándar de tabla a tabla e incluir mapas personalizados.
+ La doble escritura admite tanto el modo en línea como el modo fuera de línea. Microsoft es la única compañía que ofrece soporte para modos en línea y fuera de línea.

## <a name="what-does-dual-write-mean-for-developers-and-architects-of-customer-engagement-apps"></a><a id="developer-architect"></a>¿Qué significa la escritura dual para los desarrolladores y arquitectos de aplicaciones de interacción con los clientes?

La doble escritura automatiza el flujo de datos entre aplicaciones Finance and Operations y aplicaciones de interacción con los clientes. La escritura dual consta de dos soluciones AppSource que están instaladas en Dataverse. Las soluciones amplían el esquema de la tabla, los complementos y los flujos de trabajo en Dataverse para que puedan escalar al tamaño de ERP. Para una implementación exitosa, los desarrolladores y arquitectos de aplicaciones de interacción con los clientes deben comprender estos cambios y colaborar con sus iguales en las aplicaciones de Finance and Operations.

Para crear paridad con las aplicaciones de Finance and Operations, la escritura dual hace algunos cambios cruciales en el esquema de Dataverse. Si comprende el plan, puede evitar algunas modificaciones de diseño y desarrollo en el futuro.

+ Cuando el paquete de AppSource de escritura dual está instalado, Dataverse tendrá nuevos conceptos como empresa y parte. Estos conceptos ayudan a las aplicaciones basadas en Dataverse, incluidos Dynamics 365 Sales, Dynamics 365 Marketing, Dynamics 365 Customer Service y Dynamics 365 Field Service a interactuar sin problemas con las aplicaciones de Finance and Operations.

+ Las actividades y notas se unifican y amplían para admitir tanto C1 (usuarios del sistema) como C2 (clientes del sistema).

+ Para evitar la pérdida de datos durante la transmisión de divisas entre las aplicaciones de Finance and Operations y Dataverse, podrá ampliar el número de posiciones decimales en el tipo de datos de divisa de las aplicaciones de interacción con los clientes. La característica traduce automáticamente las filas existentes al nuevo estado extendido en la capa de metadatos. Durante este proceso, el valor de la moneda se convierte en datos decimales en lugar de datos monetarios, y el valor de la moneda admite 10 lugares decimales. Esta función es opcional y las organizaciones que no necesitan más de 4 lugares decimales de precisión no necesitan participar. Para más información, consulte [Migración de tipo de datos de moneda para escritura dual](currrency-decimal-places.md).

+ La [fecha de vigencia](../../dev-tools/date-effectivity.md) se agregará a Dataverse. Admitirá datos pasados, presentes y futuros en la misma tabla.

+ Las [conversiones de unidades](../../../../supply-chain/pim/tasks/manage-unit-measure.md) de productos son compatibles con productos, presupuestos, pedidos y facturas.

Para obtener más información sobre los próximos cambios, consulte [Novedades o cambios en escritura dual](whats-new-dual-write.md).



[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]
