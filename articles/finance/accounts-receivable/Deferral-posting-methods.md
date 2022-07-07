---
title: Métodos de registro de aplazamiento
description: Este artículo describe las diferencias entre los métodos de registro de aplazamiento para los aplazamientos de ingresos y gastos en la facturación de suscripción.
author: JodiChristiansen
ms.date: 6/10/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.custom: 539093
ms.search.region: Global
ms.author: jchrist
ms.search.validFrom: 2021-11-05
ms.dyn365.ops.version: 10.0.24
ms.openlocfilehash: c66ed1c38251140dd798c39797873ceb5f7121a4
ms.sourcegitcommit: cfe8fbc202c3eb05d894076fdf99e46704f17365
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/15/2022
ms.locfileid: "9019104"
---
# <a name="deferral-posting-methods"></a>Métodos de registro de aplazamiento

Este artículo describe las diferencias entre los métodos de registro de aplazamiento para los aplazamientos de ingresos y gastos en la facturación de suscripción.

En la página **Parámetros de aplazamiento de ingresos y gastos**, las opciones para los métodos de registro de aplazamiento son **Balance de situación** y **Pérdidas y ganancias**. El ejemplo de este artículo ayudará a explicar las diferencias entre los dos métodos y las razones por las que podría usar un método u otro.

El método **Balance de situación** emplea solo dos cuentas. Por lo tanto, se requiere menos configuración. El método **Pérdidas y ganancias** tiene dos cuentas adicionales (**Reconocimiento inicial** y **Contrapartida de reconocimiento**) para ingresos, descuentos y costes, según el tipo de transacción. Estas cuentas se configuran en la página **Valores predeterminados de aplazamiento** (**Facturación de suscripción \> Aplazamientos de ingresos y gastos \> Configuración**). Aunque el ejemplo se centra en los ingresos aplazados, el mismo concepto se puede aplicar a los descuentos y costes aplazados.

## <a name="example"></a>Ejemplo

La factura de venta 1 tiene un total de 3000 $ y tiene ingresos aplazados. Las siguientes tablas muestran las distribuciones cuando se contabiliza esta factura de venta.

**Método de balance de situación**

| Tipo | Cuenta | Débito | Crédito|
|---|---|---|---|
| Débito | Clientes | 3,000.00 | |
| Crédito | Ingresos diferidos | | 3,000.00 |

**Método de pérdidas y ganancias**

| Tipo | Cuenta | Débito | Crédito |
|---|---|---|---|
| Débito | Clientes | 3,000.00 | |
| Débito | Contrapartida de reconocimiento de ingresos | 3,000.00 | |
| Crédito | Ingresos diferidos | | 3,000.00 |
| Crédito | Reconocimiento inicial de ingresos | | 3,000.00 |

La factura de venta 2 tiene un total de 2000 $ y no tiene ingresos aplazados.

| Tipo | Cuenta | Importe |
|---|---|---|
| Débito | Clientes | 3,000.00 |
| Crédito | Ingresos | 3,000.00 |

**Cifras totales del método Balance de situación para las facturas de venta 1 y 2 combinadas**

| Cuenta | Débito | Crédito |
|---|---|---|
| Clientes | 5,000.00 | |
| Ingresos | | 2,000.00 |
| Ingresos diferidos | | 3,000.00 |

Cuando se usa el método **Balance de situación**, no es tan fácil ver los ingresos brutos de un periodo. Algunos de los ingresos se registran en la cuenta **Ingresos aplazados**. Tenga en cuenta que, dado que los ingresos se reconocen en cada periodo, existen múltiples débitos y créditos en la cuenta **Ingresos aplazados**. Los ingresos brutos para un período determinado se mezclarán con las entradas y salidas del reconocimiento de ingresos.

**Cifras totales del método Pérdidas y ganancia para las facturas de venta 1 y 2 combinadas**

| Cuenta | Débito | Crédito |
|---|---|---|
| Clientes | 5,000.00 | |
| Ingresos | | 5,000.00 |
| Contrapartida de ingresos | 3,000.00 | |
| Ingresos diferidos | | 3,000.00 |

Todos los ingresos van a la cuenta **Ingresos** de pérdidas y ganancias. Luego, los ingresos aplazados se trasladan del extracto de pérdidas y ganancias hacia el balance de situación. Puede ver fácilmente los ingresos brutos porque todo se contabiliza en la cuenta **Ingresos**. Sin embargo, parte de ese ingreso bruto es diferido. Por lo tanto, se traslada a la cuenta **Ingresos aplazados** y se reconoce posteriormente.

En el método **Pérdidas y ganancias**, puede consultar la cuenta **Ingresos** y **Contrapartida de ingresos** para ver los ingresos brutos de 5000 $ y los ingresos netos (netos de aplazados) de 2000 $. Aunque el método **Pérdidas y ganancias** puede facilitar la presentación de informes, hay más cuentas para configurar.
