---
title: Dimensiones financieras y registro
description: Cuando planifique y configure su plan contable, debe ver cómo funcionarán conjuntamente los distintos componentes cuando se registre un documento o un diario. Estos componentes incluyen las estructuras contables, reglas avanzadas, y saldo y las dimensiones fijas. Este tema explica cuál es cada componente y cómo los componentes funcionan juntos.
author: aprilolson
manager: AnnBe
ms.date: 08/04/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: LedgerChartofAccounts,DimensionDetails
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.custom: 14091
ms.assetid: c64eed1d-df17-448e-8bb6-d94d63b14607
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: July 2017 update
ms.openlocfilehash: 76fd305ce0f0f073648339d1de969981693f1da5
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/27/2019
ms.locfileid: "2186817"
---
# <a name="financial-dimensions-and-posting"></a>Dimensiones financieras y registro 

[!include [banner](../includes/banner.md)]

Cuando planifique y configure su plan contable, debe ver cómo funcionarán conjuntamente los distintos componentes cuando se registre un documento o un diario. Estos componentes incluyen las estructuras contables, reglas avanzadas, y saldo y las dimensiones fijas. Este tema explica cuál es cada componente y cómo los componentes funcionan juntos.

## <a name="chart-of-accounts-and-financial-dimension-components"></a>Componentes de plan contable y dimensiones financieras

Un sistema rico basado en reglas se usa para definir combinaciones válidas de cuentas principales y valores de la dimensión financiera. Esta sección ofrece una visión general breve de la funcionalidad de cada componente y explica dónde se puede encontrar el componente.

### <a name="account-structures"></a>Estructuras contables

Se requiere una estructura contable cuando configura el libro mayor. Debe definir y activar al menos una estructura contable y, debe asignarla al libro mayor. La estructura contable debe contener la cuenta principal. Puede definir el orden de los segmentos que mejor funcione para el negocio. Después de que se defina la cuenta principal, el sistema puede determinar la estructura contable que se usa. Al configurar la cuenta principal primero o cerca del frente de una estructura, puede ayudar a restringir los valores y también ayudar al sistema a aplicar el último valor conocido como valor predeterminado. Puede tener hasta 10 dimensiones financieras adicionales en la estructura contable. La estructura contable define qué valores de dimensión son válidos en combinación con otros valores. también define si los valores de dimensión se deben introducir.

### <a name="advanced-rules"></a>Reglas avanzadas

Reglas avanzadas son un componente opcional al configurar el plan contable. Puede agregar tantas reglas avanzadas como desee a una estructura contable. Reglas avanzadas se suelen usar para gestionar los escenarios donde las dimensiones financieras adicionales deben ser seguidas cuando se cumplen los criterios específicos. Por ejemplo, si usa una cuenta de gastos de viajes, puede que desee realizar un seguimiento de la información adicional, como el evento para el que el empleado viaja. Si hay varias reglas avanzadas, se aplican en orden alfabético, en función de los nombres de las reglas. Los segmentos que agrega una regla se pueden aplicar sólo después de los segmentos de la estructura contable.

### <a name="balancing-dimension"></a>Dimensión del saldo

Puede definir una dimensión financiera del saldo. En la página **libro mayor** , puede definir la dimensión financiera que debe ser saldada. A continuación, siempre que las transacciones se registran en dicha dimensión financiera, el sistema crea automáticamente y registra entradas para crear la dimensión financiera saldada.

### <a name="defaultfixed-financial-dimensions-on-the-main-account"></a>Las dimensiones financieras predeterminada/fijas en la cuenta principal.

Las dimensiones predeterminadas proceden de distintas ubicaciones, como grabaciones master (por ejemplo, cliente o los registros de proveedor), encabezados del documento, y la cuenta principal. Este tema se centra en las dimensiones predeterminadas en la cuenta principal de la entidad jurídica. Puede definir si una cuenta principal tiene un valor **No fijo** o **Fijo** para cada dimensión financiera que se utilice en todas las estructuras contables para el libro mayor. Si una dimensión financiera es **No fijo**, usa un valor predeterminado, pero este valor se puede sobrescribir. Este comportamiento se aplica a todos los valores predeterminados en el sistema, incluso los valores predeterminados que proceden de registros maestros. Si una dimensión financiera se establece en un valor **Fijo**, el valor se aplica siempre, independientemente de si vino de alguna parte como valor predeterminado o si el usuario lo ha especificado.

## <a name="order-in-which-default-dimensions-are-applied-during-posting"></a>Orden en que las dimensiones predeterminadas se aplican durante el registro

Las entidades tienen a menudo preguntas sobre el orden en que varios componentes se ejecutan. Es muy importante que entienda el orden en que se aplican las dimensiones predeterminadas, pues este comportamiento afecta al método que siga para configurar.

> [!NOTE]
> Esta información solo afecta a la aplicación de dimensiones predeterminadas en la aplicación. Si importa datos mediante Microsoft Excel o el marco de gestión de datos, el comportamiento se diferencia.

### <a name="example-1"></a>Ejemplo 1

**Estructura contable**

| Cuenta principal            | Unidad de negocio           | Departamento              | Centro de coste             |
|-------------------------|-------------------------|-------------------------|-------------------------|
| Se permiten todos los valores. | Se permiten todos los valores. | Se permiten todos los valores. | Se permiten todos los valores. |

**Cuenta principal**

| Cuenta principal | Nombre          | Entidad jurídica | Departamento                                 |
|--------------|---------------|--------------|--------------------------------------------|
| 401100       | Ventas de producto | USMF         | Fijo - 022 departamento de Ventas y Marketing |

La ilustración siguiente muestra la dimensión fija predeterminada que está configurada en la cuenta principal 401100.

[![Dimensiones financieras predeterminadas](./media/default-dimensions.png)](./media/default-dimensions.png)

Para este ejemplo muy básico, entraremos en un diario general donde la dimensión de departamento se establece para usar el valor predeterminado **023** (operaciones). Incorporaremos y enviaremos una cuenta contable. La ilustración siguiente muestra la dimensión financiera predeterminada en el encabezado de la contabilidad general.

[![Diarios generales](./media/general-journal.png)](./media/general-journal.png)

La dimensión predeterminada en la cabecera de diario hará que el departamento 023 se aplique de forma predeterminada en la línea de la cuenta de ventas. La ilustración siguiente muestra la línea de diario general, donde se aplica el valor **023** de dimensión predeterminada de cabecera.

[![Asiento del diario](./media/journal-voucher.png)](./media/journal-voucher.png)

Sin embargo, cuando se registra la línea, se aplica la dimensión fija, y la línea se envía al departamento 022. La ilustración siguiente muestra el asiento enviado, donde la dimensión fija se aplica para la cuenta de ventas.

[![Transacciones de asiento](./media/voucher-transactions.png)](./media/voucher-transactions.png)

### <a name="example-2"></a>Ejemplo 2

Este ejemplo usa la misma configuración que el primer ejemplo. Sin embargo, agregaremos a un segundo componente y utilizaremos la dimensión de departamento como dimensión del saldo. En la siguiente ilustración, **Departamento** se establece como la dimensión financiera del saldo para el libro mayor de USMF.

[![Contabilidad](./media/ledger.png)](./media/ledger.png)

Cuando se usa la misma configuración de la cabecera de diario, y se registra la misma transacción, la dimensión fija se aplica primero. A continuación la lógica de saldo se aplica para ayudar a garantizar que cada departamento tiene una entrada saldada. La ilustración siguiente muestra las transacciones de asiento que incluyen la entrada de saldo después de que se aplique la dimensión fija.

[![Transacciones de asiento](./media/voucher-transactions2.png)](./media/voucher-transactions2.png)

### <a name="example-3"></a>Ejemplo 3

En este ejemplo, agregaremos una regla avanzada. La regla avanzada especifica que si usa la cuenta de ventas 401100 y departamento 022 (Ventas y marketing), el sistema debe seguir un segmento adicional que se denomina Cliente.

Este ejemplo es importante debido al orden. Se determina la estructura contable tras especificar la cuenta principal. Si se hace referencia a la configuración de la estructura contable, el sistema puede determinar que la cuenta principal, departamento de unidad de negocio, y el centro de coste son relevantes. En este punto, la regla avanzada no se ha activado, ya que no se aplican las dimensiones fijas hasta que las dimensiones predeterminadas se hayan aplicado para el asiento del diario durante el registro. En la siguiente ilustración, el segmento de cliente no está presente, ya que los criterios para la regla avanzada no se han cumplido.

[![Cuenta contable](./media/drop-down.png)](./media/drop-down.png)

El registro no se realiza correctamente, porque la dimensión fija se aplicó al final del proceso. La validación de dimensiones determina que el segmento del cliente se requiere si la cuenta principal es 401100 y el departamento es 022. El registro no se puede producir debido al error de validación. La ilustración siguiente muestra el mensaje que aparece a la validación de la dimensión que determina que el cliente es un segmento requerido.

[![Detalles de mensaje](./media/message.png)](./media/message.png)

En este ejemplo, debe sobrescribir el valor predeterminado para activar la regla avanzada y puede insertar el segmento del cliente. Sin embargo, esta solución no siempre es posible, y algunos usuarios ni siquiera son conscientes de las reglas de registro. Por lo tanto, es importante que se entienda el orden en que las dimensiones predeterminadas se aplican al configurar el plan contable.

Para lograr lo que desea en este ejemplo, puede cambiar la configuración de varias formas. Por ejemplo, puede crear una nueva estructura contable para las cuentas de ventas e incluir el segmento de cliente en la estructura. También puede agregar más filas en una estructura contable existente, y especificar la cuenta principal y valores validos de departamento. A continuación, en la estructura adicional del cliente, es posible que encuentre útil el tener una estructura de cuenta de ventas independiente en la que esté presente el segmento del cliente.

## <a name="additional-resources"></a>Recursos adicionales 

Algunos de los siguientes recursos se refieren a una versión anterior de nuestro software. Sin embargo, buena parte de la información sobre la aplicación de dimensiones predeterminadas y muchos de los conceptos son iguales en la versión anterior, y las referencias todavía son válidas.

[Diarios equilibrados para la contabilidad interunidad](example-balanced-journals-interunit-accounting.md)

[Planificar su plan de cuentas](plan-chart-of-accounts.md) 

[Planee su plan te cuentas en el blog de AX 2012](https://blogs.msdn.microsoft.com/axsa/2014/06/12/planning-your-chart-of-accounts-in-ax-2012-part-1-of-7/) – Este vínculo va a la Parte 1 de una serie de siete partes.

[Dimensión que establece como valor predeterminado en distribuciones contables](https://blogs.msdn.microsoft.com/ax_gfm_framework_team_blog/2013/12/16/dimension-defaulting-in-accounting-distributions-part-1-introduction/)

[Dimensión que establece como valor predeterminado en marco de las dimensiones](https://blogs.msdn.microsoft.com/ax_gfm_framework_team_blog/2014/09/)
