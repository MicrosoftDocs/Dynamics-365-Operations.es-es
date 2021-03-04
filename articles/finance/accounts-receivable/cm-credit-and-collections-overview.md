---
title: Visión general de crédito y cobros
description: Este tema proporciona una introducción a la funcionalidad de crédito y cobros.
author: mikefalkner
manager: AnnBe
ms.date: 09/04/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: roschloma
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: roschlom
ms.search.validFrom: ''
ms.dyn365.ops.version: ''
ms.openlocfilehash: 67e0b3d1058e5fc085f51577ccf0b79e51546de0
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/13/2020
ms.locfileid: "4447573"
---
# <a name="credit-and-collections-overview"></a>Visión general de crédito y cobros

[!include [banner](../includes/banner.md)]

Puede administrar los límites de crédito para sus clientes y realizar actividades de cobro cuando sea necesario.

## <a name="credit-management"></a>Gestión de créditos

La administración de crédito de cliente le permite administrar los límites de crédito y controlar el flujo de pedidos de ventas mediante el proceso de registro, según las reglas de crédito que cree.

El proceso de administración de crédito puede incluir algunos de los pasos siguientes:

- Actualizar los atributos de crédito para clientes, a fin de proporcionar información adicional sobre su solvencia.
- Crear límites de crédito para clientes que utilizan ajustes de límite de crédito.
- Crear límites de crédito temporales para clientes que utilizan ajustes de límite de crédito. De esta manera, puede aumentar o disminuir temporalmente los límites de crédito del cliente, según los requisitos comerciales.
- Agregar información que pueda afectar al límite de crédito, como información seguros y garantías.
- Crear grupos de crédito de clientes que vinculen a los clientes para que puedan compartir un solo límite de crédito.
- Asignar puntuaciones de riesgo a los clientes y luego usar esas puntuaciones para generar automáticamente límites de crédito para esos clientes mediante ajustes de límite de crédito.
- Crear reglas de bloqueo que pondrán un pedido en espera durante uno o más procesos de registro en función de factores como el riesgo, las condiciones de pago, los límites de crédito, los importes vencidos y el porcentaje del límite de crédito utilizado.
- Administrar una lista de pedidos de ventas que están en espera, revisar los motivos de la retención y mitigar los problemas.
- Liberar pedidos de ventas para que continúen a través del proceso de registro.
- Configurar el flujo de trabajo para administrar la aprobación de los cambios de límite de crédito y las liberaciones de pedidos de ventas.

## <a name="collections-management"></a>Gestión de cobros

La página **Cobros** proporciona una vista centralizada en la que se administra información de cobros de clientes. Los administradores de cobros pueden usar esta vista centralizada para gestionar los cobros. Los agentes de cobros pueden comenzar el proceso de cobro por las listas de clientes que se generan mediante criterios de cobro predefinidos o por la página **Clientes**.

Antes de comenzar a configurar cobros o a trabajar con ellos, debe comprender los siguientes conceptos:

- Las instantáneas de vencimiento de los clientes contienen información sobre saldos vencidos en un momento determinado.
- Las secciones de clientes de cobros le ayudan a organizar su trabajo.
- Los agentes de cobros tienen sus propias secciones de clientes.
- En las páginas de lista se organizan los clientes, las actividades y los casos de cobros.
- Toda la información de cobros de un cliente se encuentra en una página, desde donde puede responder.
- El interés y las cuotas se pueden condonar, restablecer o invertir en un solo paso.
- Se pueden crear transacciones de cancelación en un solo paso.
- Se pueden procesar pagos de fondos insuficientes (NSF) en un solo paso.

Para ver descripciones de estos conceptos, consulte [Conceptos clave de la administración de cobros](./cm-collections-concepts.md).

## <a name="additional-resources"></a>Recursos adicionales

[Configuración de parámetros de la administración de crédito de cliente](./cm-credit-mgmt-setup.md)

[Información de configuración de la administración de crédito de cliente](./cm-setup-information.md)

[Agregar información de administración de crédito para un cliente](./cm-add-credit-mgmt-information-customer.md)

[Grupos de crédito del cliente](./cm-customer-credit-groups.md)

[Ajustes de límite de crédito de cliente](./cm-credit-limit-adjustments.md)

[Retenciones de crédito para pedidos de ventas](./cm-sales-order-credit-holds.md)

[Tareas periódicas de administración de crédito de cliente](./cm-periodic-tasks.md)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]