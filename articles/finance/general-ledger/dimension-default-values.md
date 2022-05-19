---
title: Dimensiones financieras predeterminadas en diarios financieros
description: Este tema se describen las reglas que definen cómo se establecen los valores de la dimensión financiera en las transacciones que se introducen a través de diarios financieros. También incluye detalles para escenarios donde se usan dimensiones fijas.
author: kweekley
ms.date: 09/04/2021
ms.topic: index-page
ms.prod: ''
ms.technology: ''
ms.search.form: LedgerJournalTransDaily, LedgerJournalTransVendInvoice, LedgerJournalTransVendPaym, LedgerJournalTransCustPaym
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2020-12-14
ms.dyn365.ops.version: 10.0.17
ms.openlocfilehash: 51235b8a5dac50aad5031456760c970e50506d66
ms.sourcegitcommit: d1683d033fc74adbc4465dd26f7b0055e7639753
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/05/2022
ms.locfileid: "8713117"
---
# <a name="default-financial-dimensions-on-financial-journals"></a>Dimensiones financieras predeterminadas en diarios financieros

[!include [banner](../includes/banner.md)]

Este tema se describen las reglas que definen cómo se establecen los valores de la dimensión financiera en las transacciones que se introducen a través de diarios financieros (pero no a través de diarios de inventario o diarios de proyecto). También incluye detalles para escenarios donde se usan dimensiones fijas.

## <a name="symptom"></a>Síntoma

Los valores de la dimensión financiera no se establecen de la manera prevista en la Cuenta o la Cuenta de contrapartida dentro de un diario financiero. Los siguientes escenarios son dos ejemplos:

Se introduce un asiento en un diario general. La Cuenta es una cuenta de proveedor y la Cuenta de contrapartida es una cuenta bancaria. Las dimensiones financieras del proveedor se introducen de forma predeterminada en la Cuenta, pero las dimensiones financieras del banco no se introducen de manera predeterminada en la Cuenta de contrapartida. En su lugar, los valores de dimensión de la Cuenta se introducen de forma predeterminada en la Cuenta de contrapartida.

Un cliente tiene asignados valores de dimensión financiera predeterminados y una cuenta principal de ingresos tiene un valor de dimensión fija asignado para la dimensión financiera Departamento. Se introduce un asiento en un diario general.  La Cuenta es el cliente y la Cuenta de contrapartida es una cuenta contable, específicamente la cuenta de ingresos con el valor de dimensión fija. La dimensión fija no está configurada en la Cuenta de contrapartida para la cuenta principal de ingresos. En su lugar, se establece en el valor de dimensión Departamento de la Cuenta, que proviene del cliente.  Después de registrar el asiento, el valor de dimensión fija se utiliza en el asiento contable registrado, pero el asiento aún muestra el valor del departamento del cliente en la cuenta de ingresos. 

¿Qué reglas se siguen para los valores de la dimensión financiera establecidos en los asientos dentro de un diario?

## <a name="resolution"></a>Resolución

Se siguen las siguientes reglas para introducir valores de dimensión financiera de forma predeterminada en las líneas de un asiento en los diarios financieros, como el diario general o el diario de facturas de proveedor. 

1. **Cabecera de diario**

   - Las dimensiones del encabezado del diario se introducen de forma predeterminada a partir de las dimensiones de nombre de diario.

2. **Cuenta de línea de diario**

   - Las dimensiones de la cuenta de línea de diario se introducen de forma predeterminada a partir de las dimensiones de encabezado de diario.
   - Si alguna dimensión financiera está en blanco, sus valores se introducen de forma predeterminada desde las dimensiones de cliente, proveedor, banco, activo fijo, proyecto o libro mayor.

     - Si el tipo de cuenta es **Libro mayor**, una dimensión fija en una cuenta contable se trata como una dimensión predeterminada durante la entrada de transacción.
     - Si el tipo de cuenta es **Cliente**, **Proveedor**, **Banco**, **Activos fijos** o **Proyecto**, la cuenta principal aún no se puede determinar. Por lo tanto, nunca se introducirá una dimensión fija de forma predeterminada para la cuenta.

3. **Cuenta de contrapartida de línea de diario**

 - En primer lugar, las dimensiones de la cuenta de contrapartida de la línea de diario se toman de forma predeterminada a partir de las dimensiones de la cuenta de línea de diario.

 - Si alguna dimensión financiera está en blanco, la siguiente entrada predeterminada procederá de las dimensiones predeterminadas del Cliente, Proveedor, Banco, Activos fijos, Proyecto o Libro mayor.
   1. Si el tipo de Cuenta de contrapartida es **Libro mayor**, una dimensión fija en una Cuenta contable se trata como una dimensión predeterminada durante la entrada de transacción. Si ya se introdujo un valor de dimensión de forma predeterminada desde la Cuenta, el valor de la dimensión fija o predeterminada de la cuenta principal no reemplazará el valor existente.
   2. Si el tipo de Cuenta de contrapartida es **Cliente**, **Proveedor**, **Banco**, **Activos fijos** o **Proyecto**, la cuenta principal aún no se conoce, por lo que una dimensión fija nunca será predeterminada para la Cuenta de contrapartida.

4. **Registro**

    1. Durante el registro, se evalúa la cuenta principal de cada línea del asiento contable (tanto para la Cuenta como para la Cuenta de contrapartida) para determinar si hay un valor de dimensión fijo. Si se define una dimensión fija, cualquier valor existente o en blanco se reemplaza por ese valor de dimensión fija.

        El valor de dimensión fija **no** se muestra en las líneas del diario después del registro. En su lugar, se muestra en el asiento contable cuando ve el asiento después de registrarse.

    2. No se introduce ningún otro valor de dimensión de forma predeterminada durante el registro, incluidas las cuentas contables adicionales que se pueden agregar durante el registro, como las cuentas de redondeo de decimales y cuentas de destinatario de pago y remitente de pago de empresas vinculadas. Las entradas de dimensión predeterminadas para cuentas contables adicionales se toman de la cuenta o cuentas de contrapartida.

Con el fin de introducir valores de dimensión de forma predeterminada, el proceso predeterminado del diario no puede determinar si un valor de dimensión en blanco se dejó en blanco intencionalmente o si no se realizó la entrada predeterminada. Si un valor de dimensión se deja en blanco de manera intencionada, es posible que se siga introduciendo un valor de forma predeterminada utilizando el orden predeterminado que se ha descrito anteriormente. Si necesita que una dimensión tenga un valor en blanco, es posible que deba crear una dimensión que tenga un valor de **0** (cero) o **En blanco**, de modo que pueda usarse en lugar de una dimensión en blanco.

Revise los siguientes escenarios para ver ejemplos del orden predeterminado de la dimensión financiera.

### <a name="scenario-1"></a>Escenario 1

Vaya a **Contabilidad general \> Configuración del diario \> Nombres de diarios** y seleccione el nombre de diario **GenJrn**. A continuación, en la ficha desplegable **Dimensiones financieras**, defina los siguientes valores para las dimensiones financieras predeterminadas:

- **BUSINESSUNIT**: 001
- **DEPARTMENT**: 024

[![Página Nombres de diarios](./media/financial-dimension-defaulting-jrnl-names-01.png)](./media/financial-dimension-defaulting-jrnl-names-01.png)

Vaya a **Contabilidad general \> Entradas del diario \> Diario general** y cree un nuevo diario general que use el nombre de diario **GenJrn**. Las dimensiones se introducen de forma predeterminada desde el nombre del diario (tabla LedgerJournalName) hasta el encabezado del diario (tabla LedgerJournalTable), como se muestra en la pestaña **Dimensiones financieras**.

[![Pestaña Dimensiones financieras en la página Diarios generales](./media/financial-dimension-defaulting-genrl-jrnl-02.png)](./media/financial-dimension-defaulting-genrl-jrnl-02.png)

Vaya a las **Líneas**. En el campo **Tipo de cuenta**, seleccione **Libro mayor** y, a continuación, en el campo **Cuenta**, introduzca **170150**. A continuación, seleccione la tecla **Tabulador** para salir del campo. Las dimensiones se introducen de forma predeterminada a partir del encabezado de diario. Por lo tanto, el valor de **Cuenta** se muestra como **170150-001-024**.

[![Líneas de diario para un diario general en la página Asiento del diario](./media/financial-dimension-defaulting-jrnl-vchr-03.png)](./media/financial-dimension-defaulting-jrnl-vchr-03.png)

Cambie el valor de la **Cuenta** a **170150-001-023**. Escriba un importe de débito o un importe de crédito. En el campo **Tipo de cuenta de contrapartida**, seleccione **Libro mayor** y, a continuación, en el campo **Cuenta de contrapartida**, introduzca **600150**. Los valores de dimensión se introducen de manera predeterminada desde la cuenta. Por lo tanto, el valor de **Cuenta de contrapartida** se muestra como **600150-001-023**.

### <a name="scenario-2"></a>Escenario 2

Utilice las mismas dimensiones financieras que definió para el nombre del diario en el escenario 1. A continuación, vaya a **Clientes \> Clientes\> Todos los clientes** y defina los valores de dimensión financiera predeterminados para el cliente US-001. Seleccione el cliente para abrir los detalles del cliente. En la pestaña **Dimensiones financieras**, mantenga el valor predeterminado para la dimensión **BUSINESSUNIT** (**001**). Agregue la dimensión **COSTCENTER** y escriba **007** como el valor.

Cree un nuevo diario general que utilice el nombre de diario **GenJrn**. En la pestaña **Dimensiones financieras**, cambie el valor de **BUSINESSUNIT** predeterminado de **001** a **002**.

Vaya a las **Líneas**. En el campo **Tipo de cuenta**, seleccione **Cliente** y, a continuación, en el campo **Cuenta**, introduzca **US-001**. Para ver las dimensiones financieras de los tipos de cuentas no contables, seleccione **Dimensiones financieras \> Cuenta**. Se introducen las siguientes entradas predeterminadas para los valores de dimensión financiera:

- **BUSINESSUNIT**: 002: la entrada predeterminada se toma del encabezado del diario. El valor **001** no se introduce de forma predeterminada desde el cliente US-001, porque ya se introdujo un valor predeterminado.
- **COSTCENTER**: 007: la entrada predeterminada se toma de la configuración del cliente US-001.
- **DEPARTMENT**: 024: la entrada predeterminada se toma del encabezado del diario.

De nuevo en la línea, en el campo **Tipo de cuenta de contrapartida**, seleccione **Libro mayor** y, a continuación, en el campo **Cuenta de contrapartida**, introduzca **600150**. Se introducen los siguientes valores predeterminados de dimensión financiera en la línea:

- **BUSINESSUNIT**: 002: la entrada predeterminada se toma de las dimensiones financieras de la cuenta. (Se introdujo originalmente de forma predeterminada a partir del encabezado de diario.)
- **DEPARTMENT**: 024: la entrada predeterminada se toma de las dimensiones financieras de la cuenta. (Se introdujo originalmente de forma predeterminada a partir del encabezado de diario.)
- **COSTCENTER**: 007: la entrada predeterminada se toma de las dimensiones financieras de la cuenta. (Se introdujo originalmente de forma predeterminada a partir del cliente.)

### <a name="scenario-3"></a>Escenario 3

En el mismo diario que usó para el escenario 2, agregue una nueva línea. En el campo **Tipo de cuenta**, seleccione **Libro mayor** y, a continuación, en el campo **Cuenta**, introduzca **170150**. Borre los valores de dimensión predeterminados para que solo quede la cuenta principal 170150. En el campo **Tipo de cuenta de contrapartida**, seleccione **Cliente** y, a continuación, en el campo **Cuenta de contrapartida**, introduzca **US-001**. Se introducen las siguientes entradas predeterminadas para los valores de dimensión financiera:

- **BUSINESSUNIT**: 002: la entrada predeterminada se toma del encabezado del diario, porque el valor de dimensión de la Cuenta está en blanco. El valor **001** no se introduce de forma predeterminada desde el cliente US-001, porque ya se tomó un valor predeterminado del encabezado de diario. Si el valor de **BUSINESSUNIT** se dejó en blanco intencionalmente, también debe eliminar la dimensión financiera en la Cuenta de compensación.
- **COSTCENTER**: 007: la entrada predeterminada se toma del cliente US-001, porque el valor de la dimensión de la Cuenta y el valor de la dimensión del encabezado de diario están en blanco. Si el valor de **COSTCENTER** se dejó en blanco intencionalmente, también debe eliminar la dimensión financiera en la Cuenta de compensación.
- **DEPARTMENT**: 024: la entrada predeterminada se toma del encabezado de diario, porque el valor de dimensión de la Cuenta está en blanco. Si el valor de **DEPARTMENT** se dejó en blanco intencionalmente, también debe eliminar la dimensión financiera en la Cuenta de compensación.

### <a name="scenario-4"></a>Escenario 4

Utilice los mismos valores de dimensión financiera predeterminados que definió para el nombre del diario y el cliente en los escenarios 1 y 2. A continuación, defina un valor de dimensión fijo para la dimensión **BUSINESSUNIT** de la cuenta principal 170150. Vaya a **Contabilidad general \> Plan de cuentas \> Cuentas \> Cuentas principales**. En el campo **Cuenta principal**, seleccione **170150**, y a continuación, en la pestaña **Anulaciones de entidad jurídica**, seleccione **Agregar**. Seleccione **USMF** como entidad jurídica y, a continuación, seleccione **Agregar**. Seleccione ese registro y luego seleccione **Dimensiones predeterminadas**. Cambie la dimensión **BUSINESSUNIT** a **Valor fijo** y especifique **003** como el valor.

Cree un nuevo diario general que utilice el nombre de diario **GenJrn**. En la pestaña **Dimensiones financieras**, elimine todos los valores de dimensión predeterminados.

Vaya a las **Líneas**. En el campo **Tipo de cuenta**, seleccione **Libro mayor** y, a continuación, en el campo **Cuenta**, introduzca **170150**. A continuación, seleccione la tecla **Tabulador** para salir del campo. Los valores de dimensión se introducen de forma predeterminada a partir de la configuración de cuenta principal para la cuenta 170150. Por lo tanto, el valor de **Cuenta** se muestra como **170150-003-**.

Cambie el valor de la **Cuenta** a **170150-004-**. **La funcionalidad del diario no evita que se cambie un valor de dimensión fija.** Escriba un importe de débito o un importe de crédito. En el campo **Tipo de cuenta de contrapartida**, seleccione **Libro mayor** y, a continuación, en el campo **Cuenta de contrapartida**, introduzca **170250**. El valor de dimensión financiera 004 se introduce de manera predeterminada desde la Cuenta. A continuación, registre el documento. En la revista, seleccione **Asiento**. Observe que el valor de **BUSINESSUNIT** se revertió al valor de dimensión fija, **003**, durante el registro.

Cuando regrese al asiento del diario, la dimensión **BUSINESSUNIT** **no** refleja el valor de dimensión fija. Siempre tiene el valor que se mostró en la pantalla antes del registro. El proceso de registro no cambia nada de lo que se introduce en el asiento. Solo se cambia el asiento contable durante el registro.

## <a name="developer-notes"></a>Notas del desarrollador

Si es un desarrollador y desea ver el código del proceso predeterminado, revise los siguientes métodos:

- **LedgerJournalEngine.accountModified()**: este método es el punto de entrada principal para el proceso predeterminado de la dimensión de la cuenta principal que es estándar para todos los diarios (y se reemplaza por algunos tipos de diario).
- **LedgerJournalEngine.offsetAccountModified()**: este método es el principal punto de entrada para el proceso predeterminado de dimensión de la cuenta de contrapartida.
