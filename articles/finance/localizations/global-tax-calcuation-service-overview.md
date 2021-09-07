---
title: Información general del cálculo de impuestos
description: Este tema explica el alcance general y las características de la funcionalidad de cálculo de impuestos.
author: wangchen
ms.date: 08/17/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: TaxIntegrationTaxServiceParameters
audience: Application user
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: intro-internal
ms.search.region: Global
ms.author: wangchen
ms.search.validFrom: 2021-04-01
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: 72895cc18368ebf38818f30510cec999391c7910
ms.sourcegitcommit: 03f53980a4bc67b73ac2be76a3b3e7331d0db705
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/18/2021
ms.locfileid: "7394595"
---
# <a name="tax-calculation-overview"></a>Información general del cálculo de impuestos

[!include [banner](../includes/banner.md)]

[!include [banner](../includes/preview-banner.md)]

El cálculo de impuestos es un servicio multiinquilino hiperescalable que permite que Global Tax Engine automatice y simplifique el proceso de determinación y cálculo de impuestos. El motor de impuestos es completamente configurable. Los elementos que se pueden configurar incluyen, entre otros, el modelo de datos imponibles, el código impositivo, la matriz de aplicabilidad impositiva y la fórmula de cálculo de impuestos. El motor de impuestos se ejecuta en la plataforma de servicios centrales de Microsoft Azure y ofrece tecnología moderna y escalabilidad exponencial.

El cálculo de impuestos se integra con Dynamics 365 Finance y Dynamics 365 Supply Chain Management. Posteriormente, también se integrará con Dynamics 365 Project Operations, Dynamics 365 Commerce y otras aplicaciones propias y de terceros.

> [!IMPORTANT]
> Cuando habilita Cálculo de impuestos, es posible que algunas operaciones con datos relacionados se realicen en un centro de datos que no sea el centro de datos que mantiene los datos del servicio. Revise los [Términos y condiciones](../../fin-ops-core/fin-ops/get-started/public-preview-terms.md) antes de habilitar Cálculo de impuestos. Su privacidad es importante para nosotros. Para obtener más información, lea nuestra [Declaración de privacidad](https://go.microsoft.com/fwlink/?LinkId=521839).

Cálculo de impuestos es un motor de impuestos basado en microservicios que ofrece escalabilidad exponencial y puede ayudarle a realizar las siguientes tareas:

- Determinar automáticamente el grupo de impuestos, el grupo de impuestos de artículos y los códigos de impuestos correctos mediante un mecanismo de determinación mejorado.
- Admitir varios números de registro de impuestos en una entidad jurídica y determinar automáticamente el número de registro de impuestos correcto en las transacciones gravables.
- Apoyar la determinación, el cálculo, la contabilización y la liquidación de impuestos para los pedidos de transferencia.
- Definir fórmulas y condiciones de cálculo de impuestos configurables para sus requisitos empresariales específicos.
- Compartir la solución de determinación y cálculo de impuestos entre entidades jurídicas para ahorrar esfuerzos de mantenimiento y evitar errores.
- Apoyar la determinación del número de registro de impuestos de clientes y proveedores.
- Ayudar a determinar el código de lista.
- Admitir parámetros de cálculo de impuestos en el nivel de jurisdicción impositiva.

Para utilizar Cálculo de impuestos, instale el complemento Cálculo de impuestos desde su proyecto en Microsoft Dynamics Lifecycle Services. Después, complete la configuración en [Regulatory Configuration Service](https://marketing.configure.global.dynamics.com/) y habilite Cálculo de impuestos en Finance y Supply Chain Management. Para obtener más información, vea [Introducción al servicio de impuestos](global-get-started-with-tax-calculation-service.md).

## <a name="availability"></a>Disponibilidad

Cálculo de impuestos generalmente está disponible en entornos de producción para todos los clientes a partir de la versión 10.0.21.

Se seguirán ofreciendo nuevas funcionalidades. Consulte con frecuencia el plan de lanzamiento más actualizado para conocer la cobertura y el ámbito de las funciones compatibles.

El cálculo de impuestos está implementado en las siguientes geografías de Azure. Se agregarán más áreas geográficas de Azure según las necesidades de los clientes.

- Asia Pacífico
- Australia
- Canadá
- Europa
- Japón
- Reino Unido
- Estados Unidos

> [!NOTE]
> Cálculo de impuestos no admite la versión anterior de Dynamics 365, como Dynamics AX 2012, o implementaciones locales de Dynamics 365.

## <a name="data-flow"></a>Flujo de datos

A continuación se muestra un resumen del proceso de flujo de datos para Cálculo de impuestos. 

1. En RCS, vea e importe configuraciones de modelos de documentos gravables y configuraciones de asignación de modelos. Si debe ampliar las configuraciones para un escenario avanzado, consulte [Agregar campos de datos en configuraciones de impuestos](tax-service-add-data-fields-tax-configurations.md).
2. En RCS, cree o mantenga funciones de impuestos. Puede utilizar las funciones de impuestos para mantener los tipos impositivos y las reglas de aplicabilidad de impuestos.
3. Una vez completada la configuración de la función de impuestos, publique las configuraciones de impuestos y las funciones de impuestos de RCS en el repositorio global.
4. En Finance, seleccione la versión de configuración de la función fiscal que se utilizará para una entidad jurídica específica.
5. En Finance y Supply Chain Management, utilice las transacciones de la forma habitual. Cuando sea necesario usar Cálculo de impuestos, el cliente recopilará información de la transacción, como el pedido de ventas o el pedido de compra, y empaquetará la información como una carga útil. A continuación, se enviará una solicitud para calcular el impuesto.
6. Se recibe del cliente la solicitud de cálculo de impuestos y se completa el cálculo. A continuación, el resultado de impuestos se devuelve al cliente.
7. El cliente de Dynamics 365 recibe el resultado de impuestos y presenta el resultado del cálculo de impuestos en una página de impuestos.

## <a name="supported-transactions"></a>Transacciones admitidas

Las transacciones pueden habilitar Cálculo de impuestos. 

En la versión 10.0.21 se admiten las siguientes transacciones: 

- Sales

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

- Compra

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

- Inventario

    - Pedido de transferencia: envío
    - Pedido de transferencia: recepción

## <a name="supported-countriesregions"></a>Países o regiones admitidos

Cálculo de impuestos se puede habilitar por entidad jurídica. 

En la versión 10.0.21 se admiten los siguientes países o regiones para la dirección principal de una entidad jurídica:

- Austria
- Bélgica
- Dinamarca
- Estonia
- Finlandia
- Francia
- Alemania
- Hungría
- Islandia
- Italia
- Letonia
- Lituania
- Países Bajos
- Noruega
- Polonia
- Suecia
- Suiza
- Reino Unido
- Estados Unidos

## <a name="related-resources"></a>Recursos relacionados

[Introducción al servicio de impuestos](./global-get-started-with-tax-calculation-service.md)

[Número de registro de IVA múltiple](./emea-multiple-vat-registration-numbers.md)

[Compatibilidad de la característica de impuestos para pedidos de transferencia](./tasks/tax-feature-support-for-transfer-order.md)

[Cómo crear una extensión en el servicio de impuestos](./tax-service-add-data-fields-tax-integration-by-extension.md)
