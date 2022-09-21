---
title: Información general del cálculo de impuestos
description: Este artículo explica el alcance general y las características de la funcionalidad de cálculo de impuestos.
author: EricWangChen
ms.date: 09/08/2022
ms.topic: overview
ms.prod: ''
ms.technology: ''
audience: Application user
ms.reviewer: kfend
ms.search.region: Global
ms.author: wangchen
ms.search.validFrom: 2021-04-01
ms.dyn365.ops.version: 10.0.18
ms.search.form: TaxIntegrationTaxServiceParameters
ms.openlocfilehash: a193db82b2b079c1e10fbfb6bfde7aa43b18bc4a
ms.sourcegitcommit: dbb997f252377b8884674edd95e66caf8d817816
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/10/2022
ms.locfileid: "9465176"
---
# <a name="tax-calculation-overview"></a>Información general del cálculo de impuestos

[!include [banner](../includes/banner.md)]

El cálculo de impuestos es un servicio multiinquilino hiperescalable que permite que Global Tax Engine automatice y simplifique el proceso de determinación y cálculo de impuestos. El motor de impuestos es completamente configurable. Los elementos que se pueden configurar incluyen, entre otros, el modelo de datos imponibles, el código impositivo, la matriz de aplicabilidad impositiva y la fórmula de cálculo de impuestos. El motor de impuestos se ejecuta en la plataforma de servicios centrales de Microsoft Azure y ofrece tecnología moderna y escalabilidad exponencial.

El cálculo de impuestos se integra con Dynamics 365 Finance y Dynamics 365 Supply Chain Management. Posteriormente, también se integrará con Dynamics 365 Project Operations, Dynamics 365 Commerce y otras aplicaciones propias y de terceros.

> [!IMPORTANT]
> Cuando habilita Cálculo de impuestos, es posible que algunas operaciones con datos relacionados se realicen en un centro de datos que no sea el centro de datos que mantiene los datos del servicio. Revise los [Términos y condiciones](https://go.microsoft.com/fwlink/?linkid=2156043) antes de habilitar Cálculo de impuestos. Su privacidad es importante para nosotros. Para obtener más información, lea nuestra [Declaración de privacidad](https://go.microsoft.com/fwlink/?LinkId=521839).

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
- Brasil
- Canadá
- Europa
- Francia
- India
- Japón
- Sudáfrica
- Suiza
- Emiratos Árabes Unidos
- Reino Unido
- Estados Unidos

> [!NOTE]
> Cálculo de impuestos no admite la versión anterior de Dynamics 365, como Dynamics AX 2012, o implementaciones locales de Dynamics 365.

## <a name="versions"></a>Versiones
Le recomendamos que importe y configure su configuración de cálculo de impuestos con la versión que coincida con su versión de Finance o Supply Chain Management.

| Versión de Finance o Supply Chain Management | Versión de configuración de impuestos               |
| --------------- | --------------------------------------- |
| 10.0.30         | Configuración de Cálculo de impuestos 40.55.239 |
| 10.0.29         | Configuración de Cálculo de impuestos 40.55.236 |
| 10.0.28         | Configuración de Cálculo de impuestos 40.54.234 |
| 10.0.27         | Configuración de Cálculo de impuestos 40.54.234 |


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

La siguiente tabla enumera las transacciones admitidas en la versión correspondiente.

| Versión | Transacciones |
|---------|--------------|
| 10.0.29 | Diarios periódicos |
| 10.0.28 | Diario de pagos del proveedor<br> Diario de pagos de clientes | 
| 10.0.26 | Diarios generales<br> Diario de facturas del proveedor |
| 10.0.23 | Factura de servicios |
| 10.0.21| Ventas<br><ul><li>Presupuesto de ventas</li><li>Pedido de ventas</li><li>Confirmación</li><li>Lista de selección</li><li>Traslado</li><li>Factura de ventas</li><li>Factura rectificativa</li><li>Pedido de devolución</li><li>Cargo misceláneo de encabezado</li><li>Cargo misceláneo de línea</li></ul>Compra<br><ul><li>Pedido de compra</li><li>Confirmación</li><li>Lista de recepciones</li><li>Recepción de producto</li><li>Factura de compra</li><li>Cargo misceláneo de encabezado</li><li>Cargo misceláneo de línea</li><li>Factura rectificativa</li><li>Pedido de devolución</li><li>Solicitud de compra</li><li>Cargo misceláneo de línea de solicitud de compra</li><li>Solicitud de presupuesto</li><li>Cargo misceláneo de encabezado de solicitud de presupuesto</li><li>Cargo misceláneo de línea de solicitud de presupuesto</li></ul>Inventario<ul><li>Pedido de transferencia: envío</li><li>Pedido de transferencia: recepción</li></ul>|

## <a name="supported-countriesregions"></a>Países o regiones admitidos

El cálculo de impuestos se puede ejecutar con funciones de localización compatibles. La tabla siguiente muestra los países/regiones para la dirección principal de una entidad jurídica.

| Versión | País o región |
|---------|----------------|
| 10.0.26 | - China <br>- República Checa<br>- España |
| 10.0.24 | México |
| 10.0.23 | - Tailandia <br>- Japón <br>- Malasia <br>- Singapur |
| 10.0.22 | - Australia<br>- Baréin <br>- Canadá<br>- Egipto <br>- RAE de Hong Kong <br>- Kuwait <br>- Nueva Zelanda <br>- Omán <br>- Catar <br>- Arabia Saudí <br>- Sudáfrica <br>- Emiratos Árabes Unidos |
| 10.0.21 | - Austria <br>- Bélgica <br>- Dinamarca <br>- Estonia <br>- Finlandia <br>- Francia <br>- Alemania <br>- Hungría <br>- Islandia <br>- Irlanda <br>- Italia <br>- Letonia <br>- Lituania <br>- Países Bajos <br>- Noruega <br>- Polonia <br>- Suecia <br>- Suiza <br>- Reino Unido <br>- Estados Unidos |

Para cualquier país o región no localizados por Microsoft, el cálculo de impuestos también se puede habilitar y ejecutar con otras características globales.

## <a name="related-resources"></a>Recursos relacionados

[Introducción al servicio de impuestos](./global-get-started-with-tax-calculation-service.md)

[Número de registro de IVA múltiple](./emea-multiple-vat-registration-numbers.md)

[Compatibilidad de la característica de impuestos para pedidos de transferencia](./tasks/tax-feature-support-for-transfer-order.md)

[Cómo crear una extensión en el servicio de impuestos](./tax-service-add-data-fields-tax-integration-by-extension.md)
