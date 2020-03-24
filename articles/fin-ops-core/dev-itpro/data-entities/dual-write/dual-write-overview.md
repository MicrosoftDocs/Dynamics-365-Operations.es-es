---
title: Descripción general de doble escritura
description: Este tema proporciona una visión general de doble escritura. La doble escritura es una infraestructura que proporciona interacción casi en tiempo real entre aplicaciones basadas en modelos de Microsoft Dynamics 365 y aplicaciones de Finance and Operations.
author: RamaKrishnamoorthy
manager: AnnBe
ms.date: 02/06/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User, IT Pro
ms.reviewer: rhaertle
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: ramasri
ms.dyn365.ops.version: ''
ms.search.validFrom: 2020-01-06
ms.openlocfilehash: c4a643d4981364cea5b549118c201ac8a9798e02
ms.sourcegitcommit: 141e0239b6310ab4a6a775bc0997120c31634f79
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/10/2020
ms.locfileid: "3113883"
---
# <a name="dual-write-overview"></a>Descripción general de doble escritura

[!include [banner](../../includes/banner.md)]

[!include [banner](../../includes/preview-banner.md)]

## <a name="what-is-dual-write"></a>¿Qué es la doble escritura?

La doble escritura es una infraestructura lista para usar que proporciona interacción casi en tiempo real entre aplicaciones basadas en modelos de Microsoft Dynamics 365 y aplicaciones de Finance and Operations. Cuando los datos sobre clientes, productos, personas y operaciones fluyen más allá de los límites de la aplicación, todos los departamentos de una organización tienen poder.

La doble escritura proporciona una integración bidireccional estrechamente acoplada entre aplicaciones Finance and Operations y Common Data Service. Cualquier cambio de datos en aplicaciones Finance and Operations hace que se escriba en Common Data Service y cualquier cambio de datos en Common Data Service hace que se escriba en las aplicaciones Finance and Operations. Este flujo de datos automatizado proporciona una experiencia de usuario integrada en todas las aplicaciones.

![Relación de datos entre aplicaciones](media/dual-write-overview.jpg)

La doble escritura tiene dos aspectos: un aspecto *infraestructura* y un aspecto *solicitud*.

### <a name="infrastructure"></a>Infraestructura

La infraestructura de doble escritura es extensible y fiable, e incluye las siguientes características clave:

+ Flujo de datos síncrono y bidireccional entre aplicaciones
+ Sincronización, junto con modos de reproducción, pausa y recuperación para admitir el sistema durante los modos en línea y fuera de línea / asíncrono.
+ Capacidad para sincronizar datos iniciales entre las aplicaciones
+ Vista consolidada de actividad y registros de errores para administradores de datos
+ Posibilidad de configurar alertas y umbrales personalizados y suscribirse a notificaciones
+ Interfaz de usuario intuitiva (UI) para filtrado y transformaciones
+ Capacidad para establecer y ver las dependencias y relaciones de la entidad
+ Extensibilidad para entidades y mapas estándar y personalizados
+ Administración fiable del ciclo de vida de la aplicación
+ Experiencia de configuración lista para usar para nuevos clientes

### <a name="application"></a>Solicitud

La doble escritura crea una asignación entre conceptos en aplicaciones de Finance and Operations aplicaciones y conceptos en aplicaciones basadas en modelos en Dynamics 365. Esta integración admite los siguientes escenarios:

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
+ Gestión de fuente única para usuarios
+ Canales integrados para venta minorista y comercialización
+ Visibilidad de promociones y descuentos
+ Funciones de solicitud de servicio
+ Operaciones de servicio optimizadas

## <a name="top-reasons-to-use-dual-write"></a>Principales razones para usar doble escritura

La doble escritura proporciona integración de datos en las aplicaciones Microsoft Dynamics 365. Este marco robusto vincula entornos y permite que diferentes aplicaciones empresariales trabajen juntas. Estas son las principales razones por las que debería usar la doble escritura:

+ La doble escritura proporciona una integración estrechamente acoplada, casi en tiempo real y bidireccional entre aplicaciones Finance and Operations y aplicaciones basadas en modelos en Dynamics 365. Esta integración hace de Microsoft Dynamics 365 la ventanilla única para todas sus soluciones empresariales. Los clientes que usan Dynamics 365 Finance y Dynamics 365 Supply Chain Management, pero que usan soluciones que no son de Microsoft para la gestión de relaciones con los clientes (CRM), se están pasando a Dynamics 365 por su soporte de doble escritura.
+ Los datos de clientes, productos, operaciones, proyectos e Internet de las cosas (IoT) fluyen automáticamente a Common Data Service a través de doble escritura. Esta conexión es muy útil para las empresas que están interesadas en expansiones de Microsoft Power Platform.
+ La infraestructura de doble escritura sigue el principio sin código / código bajo. Se requiere un mínimo esfuerzo de ingeniería para ampliar los mapas estándar de tabla a tabla e incluir mapas personalizados.
+ La doble escritura admite tanto el modo en línea como el modo fuera de línea. Microsoft es la única compañía que ofrece soporte para modos en línea y fuera de línea.

## <a name="what-does-dual-write-mean-for-users-and-architects-of-crm-products"></a>¿Qué significa la doble escritura para los usuarios y arquitectos de productos CRM?

La doble escritura automatiza el flujo de datos entre aplicaciones Finance and Operations y Common Data Service. En futuras versiones, los conceptos de las aplicaciones basadas en modelos en Dynamics 365 (por ejemplo, cliente, contacto, presupuesto y pedido) se ampliarán a clientes de mercado medio y mercado medio alto.

En la primera versión, la mayor parte de la automatización se maneja con soluciones de doble escritura. En futuras versiones, esas soluciones se convertirán en parte de Common Data Service. Al comprender los próximos cambios a Common Data Service, puede ahorrar esfuerzos a largo plazo. Estos son algunos de los cambios cruciales:

+ Common Data Service tendrá nuevos conceptos, como empresa y parte. Estos conceptos afectarán a todas las aplicaciones basadas en Common Data Service, como Dynamics 365 Sales, Dynamics 365 Marketing, Dynamics 365 Customer Service y Dynamics 365 Field Service.
+ Las actividades y notas se unifican y amplían para admitir tanto C1 (usuarios del sistema) como C2 (clientes del sistema).
+ Estos son algunos de los próximos cambios en Common Data Service:

    - El tipo de datos decimal reemplazará el tipo de datos de dinero.
    - La efectividad de la fecha admitirá datos pasados, presentes y futuros en el mismo lugar.
    - Habrá más soporte para la divisa y los tipos de cambio, y la interfaz de la aplicación de programación **Tipo de cambio** (API) se revisará.
    - Se admitirán conversiones de unidades.

Para obtener más información sobre los próximos cambios, vea [Datos en Common Data Service - fases 1 y 2](https://docs.microsoft.com/dynamics365-release-plan/2019wave2/finance-operations-crossapp-capabilities/data-common-data-service-phase-1).
