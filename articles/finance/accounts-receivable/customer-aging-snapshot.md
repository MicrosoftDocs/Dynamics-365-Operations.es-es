---
title: Instantáneas de vencimientos de clientes
description: Este artículo proporciona información sobre las instantáneas de vencimientos de clientes. Una instantánea de vencimientos calcula los saldos para un grupo de clientes en un momento determinado.
author: JodiChristiansen
ms.date: 05/05/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: twheeloc
ms.search.region: Global
ms.author: ilyako
ms.search.validFrom: 2021-05-05
ms.dyn365.ops.version: 10.0.17
ms.openlocfilehash: c1a83f2648b52e436d19a11862e58dc33313f341
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/03/2022
ms.locfileid: "8902584"
---
# <a name="customer-aging-snapshots"></a>Instantáneas de vencimientos de clientes

[!include [banner](../includes/banner.md)]

Este artículo proporciona información sobre las instantáneas de vencimientos de clientes. Una instantánea de vencimientos calcula los saldos para un grupo de clientes en un momento determinado. Puede crear registros de instantánea de vencimientos para todos los clientes o para los clientes de un grupo de clientes.

La información de la instantánea de vencimientos se muestra en la página de lista **Saldos vencidos** y en la página **Cobros**. Debe crear una instantánea de vencimientos antes de poder usar la página de lista **Saldos vencidos**. La página de lista solo muestra clientes para los que se haya creado una instantánea de vencimientos.

El espacio de trabajo **Crédito y cobros de clientes** también muestra el vencimiento del cliente. Para más información, consulte [el contenido de Power BI sobre administración de créditos y cobros](credit-collections-power-bi.md).

> [!NOTE]
> Para ayudar a reducir el tiempo necesario para crear una instantánea de vencimientos, active la característica **Mejora del rendimiento de vencimiento del cliente** en el espacio de trabajo **Administración de características**. Sin embargo, no utilice secciones de clientes cuando esta característica esté activada. Si se selecciona una sección de clientes, la característica no funcionará, pero aún puede crear una instantánea de vencimiento.

Cuando cree una instantánea de vencimiento del cliente, use los siguientes campos para introducir información sobre ella:

- **Definición de período de vencimiento**: seleccione la definición de período de vencimiento para la instantánea de vencimiento. Puede tener una instantánea de vencimiento para cada definición de período de vencimiento. La instantánea de vencimiento y la definición del período de vencimiento deben crearse por separado.
- **Id. de grupo**: este campo es opcional. Puede utilizar un grupo para definir el conjunto de clientes que deben procesarse en la instantánea de vencimiento. Si selecciona una sección de clientes en este campo, se crea una instantánea de vencimientos solo para las cuentas de cliente que forman parte de la sección de clientes. La sección de clientes seleccionada debe ser del tipo **Instantánea de vencimientos**. Si deja este campo en blanco, se crea una instantánea de vencimiento para todas las cuentas de los clientes.

    > [!NOTE]
    > Si la característica **Mejora del rendimiento de vencimiento del cliente** está activada, no seleccione una sección de clientes.

- **Criterios**: la instantánea de vencimiento vencerá según la fecha que seleccione:

    - **Fecha de la transacción**: vence cada transacción en función de su fecha de transacción.
    - **Fecha de vencimiento**: vence cada transacción en función de su fecha de vencimiento.
    - **Fecha de documento**: vence cada transacción en función de la fecha de documento.

- **Vencimiento a partir de**: seleccione la fecha para usarla como el campo **Fecha actual** para la instantánea de vencimiento. Después, los períodos de vencimiento se calculan en función de esta fecha. 

    - **Fecha de hoy**: use la fecha del sistema. Seleccione esta opción si el procesamiento se configura para que se ejecute en un trabajo por lotes periódico. Luego, cada vez que se ejecuta el lote, se usa la fecha del sistema de esa ejecución.
    - **Fecha seleccionada**: use una fecha especificada. Si selecciona esta opción, debe especificar una fecha de vencimiento.

    Por ejemplo, el período de vencimiento actual es de 30 días. Si seleccionas **Fecha de hoy** en este campo, el período de vencimiento actual comienza en la fecha de hoy y luego incluye los 29 días anteriores. Si seleccionas **Fecha seleccionada** e introduce una fecha, el período de vencimiento actual comienza en la fecha especificada y luego incluye los 29 días anteriores.

- **Actualizar estado de cobro**: establezca esta opción en **Sí** para actualizar el estado del cobro de transacciones en la página **Cobros** de **Compromiso de pago** a **Compromiso de pago roto** si la fecha de vencimiento es posterior a la fecha en el campo **Fecha de compromiso de pago**. Establezca esta opción en **No** para dejar el estado del cobro sin cambios en la página **Cobros**.
- **Incluir clientes sin saldo**: establezca esta opción en **Sí** para incluir a todos los clientes, independientemente de su saldo. Si incluye a todos los clientes, le recomendamos que active la característica **Mejora del rendimiento de vencimiento del cliente** y que no utilice secciones de clientes. Establezca esta opción en **No** para incluir solo a los clientes que tienen saldo. Esta configuración ayuda a acelerar el rendimiento, ya que se omiten los clientes que no tienen saldo.
- **Intervalo de empresas**: en la pestaña **Intervalo de empresas**, seleccione las entidades jurídicas (empresas) que incluir en la instantánea de vencimiento. Solo las entidades jurídicas que se configuran para pagos centralizados están disponibles para su selección. Las transacciones de las entidades jurídicas seleccionadas se incluyen en los períodos de vencimiento para los clientes que tienen el mismo Id. de parte en todas esas entidades jurídicas. Los importes de divisa se convierten a la divisa de la entidad jurídica en la que ha iniciado sesión al crear la instantánea de vencimientos.

Le recomendamos que programe este proceso para que se ejecute en un lote.

> [!NOTE]
> Para ayudar a mejorar el rendimiento del lote cuando se crean instantáneas de vencimiento, introduzca un número en el campo **Número máximo de tareas por lotes** en la ficha desplegable **Valores predeterminados de cobros** en la pestaña **Cobros** de la página **Parámetros de clientes**. En el campo **Calcular vencimientos de saldos de clientes**, le recomendamos que comience con el valor predeterminado de **100** y luego ajuste el valor para optimizar el procesamiento para su situación.

