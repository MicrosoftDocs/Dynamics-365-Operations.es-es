---
title: Cálculo de impuestos en líneas de diario generales
description: Este tema explica cómo se calculan los impuestos para distintos tipos de cuentas (proveedor, cliente, contabilidad, y proyecto) en las líneas del diario general.
author: EricWang
ms.date: 08/14/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: TaxTable
audience: Application User
ms.reviewer: roschlom
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: roschlom
ms.search.validFrom: 2019-08-14
ms.dyn365.ops.version: 10.0.6
ms.openlocfilehash: e4d367fe6cb729c9c5658a9bbbac04e53fdf9644
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/01/2021
ms.locfileid: "5815341"
---
# <a name="sales-tax-calculation-on-general-journal-lines"></a>Cálculo de impuestos en líneas de diario generales
[!include [banner](../includes/banner.md)]

Este tema explica cómo se calculan los impuestos para distintos tipos de cuentas (proveedor, cliente, contabilidad, y proyecto) en las líneas del diario general.

El proceso se puede dividir en tres pasos:

- Determine la dirección de impuestos.

- Determine el importe de impuestos que se guardará una tabla temporal de impuestos.

- Determine el importe de los impuestos y en el asiento.

## <a name="determine-the-sales-tax-direction"></a>Determine la dirección de impuestos

La forma en que determinan la dirección de impuestos depende del tipo de cuenta en el asiento. La dirección de impuestos la determina la combinación del tipo de cuentas y el código de impuestos. Las secciones siguientes listan las posibilidades con más detalle. 

### <a name="account-type-is-project"></a>Tipo de cuenta es Proyecto

Si tiene un asiento línea de diario en el que tipo de cuenta es **Proyecto**, todas las líneas de diario en el asiento aplicarán la misma dirección de impuestos. La siguiente ilustración muestra la regla. Los puntos siguientes muestran direcciones posibles de impuestos para las cuentas del proyecto.

•   Si el código de impuestos es IVA de importación, la dirección de impuestos es IVA de importación.

•   Si el código de impuestos es exención de impuestos, la dirección de impuestos es Compra libre de impuestos.

•   Si el código de impuestos es IVA intracomunitario, la dirección de impuestos es Impuestos repercutidos.

•   Si el código de impuestos es cargo invertido, la dirección de impuestos es Impuestos repercutidos.

De lo contrario, la dirección de impuestos es un impuesto soportados.

El siguiente diagrama muestra gráficamente la regla.

![Posibilidades de la dirección de impuestos de cuentas del proyecto](media/Sales-Tax-Direction-Vendor.jpg)

### <a name="account-type-is-vendor"></a>El tipo de cuenta es proveedor

Si tiene un asiento línea de diario en el que tipo de cuenta es **Proveedor**, todas las líneas de diario en el asiento aplicarán la misma dirección de impuestos. Los puntos siguientes muestran direcciones posibles de impuestos para las cuentas del proveedor. 

•   Si el código de impuestos es IVA de importación, la dirección de impuestos es IVA de importación.

•   Si el código de impuestos es exención de impuestos, la dirección de impuestos es Compra libre de impuestos.

•   Si el código de impuestos es IVA intracomunitario, la dirección de impuestos es Impuestos repercutidos.

•   Si el código de impuestos es cargo invertido, la dirección de impuestos es Impuestos repercutidos.

De lo contrario, la dirección de impuestos es un impuesto soportados.

El siguiente diagrama muestra gráficamente la regla.

![Posibilidades de la dirección de impuestos de cuentas de proveedor](media/Sales-Tax-Direction-Vendor.jpg)

### <a name="account-type-is-customer"></a>El tipo de cuenta es Cliente

Si tiene un asiento línea de diario en el que tipo de cuenta es **Cliente**, todas las líneas de diario en el asiento aplicarán la misma dirección de impuestos. Los puntos siguientes muestran direcciones posibles de impuestos para las cuentas de cliente.

•   Si el código de impuestos es exención de impuestos, la dirección de impuestos es Compra libre de impuestos.

•   Si el código de impuestos es IVA intracomunitario, la dirección de impuestos es Impuestos soportados.

•   Si el código de impuestos es cargo invertido, la dirección de impuestos es Impuestos soportados.

De lo contrario, la dirección de impuestos es un impuesto repercutidos.

El siguiente diagrama muestra gráficamente la regla.

![Posibilidades de la dirección de impuestos de cuentas de cliente](media/Sales-Tax-Direction-Customer.jpg)

### <a name="account-type-is-ledger"></a>El tipo de cuenta es Libro mayor

La ilustración siguiente muestra la regla que se aplica cuando un asiento sólo tiene líneas de diario donde el tipo de cuenta es **Libro mayor**. Los puntos siguientes muestran direcciones posibles de impuestos para las cuentas de libro mayor.

•   Si el código de impuestos es IVA de importación, la dirección de impuestos es IVA de importación.

•   Si el código de impuestos es exención de impuestos, la dirección de impuestos es Compra libre de impuestos.

De lo contrario, si el importe del diario es debe (positivo), la dirección de impuestos es Impuesto soportado; si el importe del diario es de crédito (negativo), la dirección de impuestos Impuesto repercutido.

El siguiente diagrama muestra gráficamente la regla.

![Posibilidades de la dirección de impuestos de cuentas de libro mayor](media/Sales-Tax-Direction-Ledger.jpg)

#### <a name="override-the-sales-tax-direction"></a>Anular la dirección de impuestos

Puede anular la dirección de impuestos cuando el asiento sólo contiene líneas que en la que el tipo de cuenta es **Libro mayor**.

Vaya a **Contabilidad general \> Plan de cuentas \> Cuentas \> Cuentas principales**, y seleccione la ficha desplegable **Anular entidad jurídica**.

## <a name="determine-the-sales-tax-amount"></a>Determine la cantidad de impuestos

Esta sección describe cómo se calcula el signo del importe de impuestos.

![Página de transacciones de impuestos](media/sales-tax-amount-sign.jpg)

En la tabla siguiente se muestra la regla genérica para determinar el signo de los importes de impuestos en la tabla temporal de impuestos.

| Cantidad de línea del diario | Dirección del impuesto  | Signo de importe de impuestos |
|---------------------|----------------------|-----------------------|
| Positivo            | Impuestos soportados | Positivo              |
| Positivo            | Impuestos repercutidos    | Negativo              |
| Negativo            | Impuestos soportados | Negativo              |
| Negativo            | Impuestos repercutidos    | Positivo              |

Hay una regla especial para los asientos con líneas sólo **Proyecto** o **Libro mayor** , cuando se selecciona un grupo de impuestos o grupo de impuestos en la línea **Libro mayor**. Esta regla se controla mediante la función Habilitar cálculo independiente de impuestos para los diarios generales. Cuando se desactiva esta función, el importe de impuestos de los usos en línea **Libro mayor** usan la línea de débito/crédito de la línea **Proyecto**. Cuando se activa esta función, el importe de impuestos en la línea **Libro mayor** usa su propia dirección de crédito/débito. En las siguientes tablas se muestra la regla para cada escenario. 

**Regla cuando se activa la función**

| Línea cantidad del proyecto del diario | Dirección del impuesto  | Signo de importe de impuestos |
|--------------------------------|----------------------|-----------------------|
| Positivo                       | Impuestos soportados | Positivo              |
| Negativo                       | Impuestos soportados | Negativo              |

**Regla cuando se desactiva la función**

| Línea cantidad del libro mayor  | Dirección del impuesto  | Signo de importe de impuestos |
|--------------------------------|----------------------|-----------------------|
| Positivo                       | Impuestos soportados | Positivo              |
| Negativo                       | Impuestos soportados | Negativo              |

## <a name="determine-the-sales-tax-amount-and-account-on-the-voucher"></a>Determine el importe de los impuestos y en el asiento

Al registrar impuestos, la cuenta principal se recupera del perfil del grupo de registro. Cuando los impuestos son soportados, el sistema utiliza la cuenta de impuestos soportados que se especifica en el perfil. Para los impuestos repercutidos, el sistema utiliza la cuenta de impuestos repercutidos que se especifica en el perfil.

La tabla siguiente muestra la regla genérica.

| Dirección del impuesto  | Signo de importe de impuestos | Cuenta de impuestos      | Importe del asiento |
|----------------------|-----------------------|------------------------|-------------------|
| Impuestos soportados | Positivo              | Cuenta Impuestos soportados | Positivo (Débito)  |
| Impuestos soportados | Negativo              | Cuenta Impuestos soportados | Negativo (Crédito)  |
| Impuestos repercutidos    | Positivo              | Cuenta Impuestos repercutidos    | Negativo (Crédito)  |
| Impuestos repercutidos    | Negativo              | Cuenta Impuestos repercutidos    | Positivo (Débito)  |


[!INCLUDE[footer-include](../../includes/footer-banner.md)]