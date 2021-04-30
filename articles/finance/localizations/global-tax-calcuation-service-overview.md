---
title: Cálculo de impuestos (versión preliminar)
description: Este tema explica el alcance general y las características de la funcionalidad de cálculo de impuestos.
author: wangchen
ms.date: 04/12/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application user
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: ''
ms.search.region: Global
ms.author: wangchen
ms.search.validFrom: 2021-04-01
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: 3df952e0632807e55f176e63dc2047be5e622ec2
ms.sourcegitcommit: 951393b05bf409333cb3c7ad977bcaa804aa801b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/13/2021
ms.locfileid: "5892358"
---
# <a name="tax-calculation-preview"></a>Cálculo de impuestos (versión preliminar)

[!include [banner](../includes/banner.md)]

[!include [banner](../includes/preview-banner.md)]

El cálculo de impuestos es un servicio multiinquilino hiperescalable que permite que Global Tax Engine automatice y simplifique el proceso de determinación y cálculo de impuestos. El motor de impuestos es completamente configurable. Los elementos que se pueden configurar incluyen, entre otros, el modelo de datos imponibles, el código impositivo, la matriz de aplicabilidad impositiva y la fórmula de cálculo de impuestos. El motor de impuestos se ejecuta en la plataforma de servicios centrales de Microsoft Azure y ofrece tecnología moderna y escalabilidad exponencial.

El cálculo de impuestos se integra con Dynamics 365 Finance y Dynamics 365 Supply Chain Management. Posteriormente, también se integrará con Dynamics 365 Project Operations, Dynamics 365 Commerce y otras aplicaciones propias y de terceros.

El cálculo de impuestos es un motor de impuestos basado en microservicio que ofrece una escalabilidad exponencial. Puede ayudarle a llevar a cabo las siguientes tareas:

- Configure el cálculo de impuestos a través del Regulatory Configuration Service (RCS). RCS es una versión mejorada del diseñador de informes electrónicos (ER) y está disponible como un servicio independiente.
- Configure la matriz de impuestos para determinar automáticamente los códigos y los tipos impositivos.
- Configure la matriz de impuestos para determinar automáticamente el número de registro de impuestos.
- Configure el diseñador de cálculo de impuestos para definir fórmulas y condiciones.
- Comparta la solución de determinación y cálculo de impuestos entre entidades legales.

Para utilizar el servicio de cálculo de impuestos, instale el complemento del servicio de cálculo de impuestos de su proyecto en Microsoft Dynamics Lifecycle Services (LCS). Luego, complete la configuración en RCS y habilite el servicio de cálculo de impuestos en Finance y Supply Chain Management. Para obtener más información, vea [Introducción al servicio de impuestos](./global-get-started-with-tax-calculation-service.md).

## <a name="availability"></a>Disponibilidad

El cálculo de impuestos está disponible solo en entornos de espacio aislado y para clientes seleccionados, a través de un programa en versión preliminar pública. Con el tiempo, estará disponible de manera general para todos los clientes y en entornos de producción.

Se seguirán entregando nuevas características, por lo que asegúrese de consultar la documentación más actualizada con frecuencia, para conocer la cobertura y el alcance de las características compatibles.

El cálculo de impuestos está implementado en las siguientes geografías de Azure. También se implementará en más geografías de Azure, según las necesidades del cliente:

- Estados Unidos
- Europa

> [!NOTE]
> El cálculo de impuestos no admite implementaciones locales de Dynamics 365. Tampoco es compatible con versiones anteriores, como Dynamics AX 2012.

## <a name="feature-highlights"></a>Características destacadas

- Una matriz de impuestos configurable para determinar automáticamente y calcular los impuestos
- Compatibilidad con múltiples números de registro del impuesto
- Compatibilidad de órdenes de transferencia para la determinación y cálculo de impuestos
- Compatibilidad de órdenes de transferencia para la determinación de múltiples números de registro de impuestos

## <a name="supported-transactions"></a>Transacciones admitidas

El cálculo de impuestos puede habilitarse por entidad legal y transacción. Se admiten las siguientes transacciones:

- Proceso de ventas

    - Presupuesto de ventas
    - Pedido de ventas
    - Confirmación
    - Lista de selección
    - Traslado
    - Factura de ventas
    - Factura rectificativa
    - Pedido de devolución
    - Cargo misceláneo de encabezado
    - Cargo misceláneo de línea

- Proceso de compra

    - Pedido de compra
    - Confirmación
    - Lista de recepciones
    - Recepción de producto
    - Factura de compra
    - Cargo misceláneo de encabezado
    - Cargo misceláneo de línea
    - Factura rectificativa
    - Pedido de devolución
    - Solicitud de compra
    - Cargo misceláneo de línea de solicitud de compra
    - Solicitud de presupuesto
    - Cargo misceláneo de encabezado de solicitud de presupuesto
    - Cargo misceláneo de línea de solicitud de presupuesto

- Proceso de inventario

    - Pedido de transferencia: envío
    - Pedido de transferencia: recepción

## <a name="related-resources"></a>Recursos relacionados

[Introducción al servicio de impuestos](./global-get-started-with-tax-calculation-service.md)

[Número de registro de IVA múltiple](./emea-multiple-vat-registration-numbers.md)

[Compatibilidad de la característica de impuestos para pedidos de transferencia](./tasks/tax-feature-support-for-transfer-order.md)

[Cómo crear una extensión en el servicio de impuestos](./tax-service-add-data-fields-tax-integration-by-extension.md)