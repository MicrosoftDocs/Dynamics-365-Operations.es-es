---
title: Divisa dual
description: Este tema proporciona información sobre la divisa dual, donde la divisa de notificación se usa como segunda divisa de contabilidad para Microsoft Dynamics 365 for Finance and Operations.
author: kweekley
manager: AnnBe
ms.date: 10/10/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: LedgerJournalTable, Ledger, AssetTransReportingCurrencyAmountsWizard,BankAccountTransReportingCurrencyAmountsWizard, LedgerTrialBalanceListPage
audience: Application User
ms.reviewer: shylaw
ms.search.scope: ''
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2018-10
ms.dyn365.ops.version: 8.0999999999999996
ms.openlocfilehash: 8de178ec80f7408d657e746b633703f386c8e02d
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/29/2019
ms.locfileid: "330319"
---
# <a name="dual-currency"></a>Divisa dual

[!include [banner](../includes/banner.md)]

La funcionalidad que se introdujo en Microsoft Dynamics 365 for Finance and Operations versión 8.1 (octubre de 2018) habilita el cambio de propósito de la divisa de notificación y su uso como segunda divisa de contabilidad. Esta función se denomina *divisa dual*. Los cambios de la divisa dual no se pueden desactivar con una clave de configuración o un parámetro. Dado que la divisa de notificación se usa como segunda divisa de contabilidad, la manera en que la divisa de notificación se calcula en la lógica del registro ha cambiado.

Además, diferentes módulos se han mejorado para seguir, informar y usar la divisa de notificación en varios procesos. Los módulos afectados son **Contabilidad general**, **Informes financieros**, **Proveedores**, **Clientes**, **Gestión de efectivo y bancos** y **Activos fijos**. Tras realizar una actualización, debe completar pasos específicos para Gestión de efectivo y bancos, y Activos fijos. Por lo tanto, asegúrese de leer las secciones relevantes de este tema con cuidado.

## <a name="posting-process"></a>Proceso de registro

La lógica del registro se ha cambiado para todas las transacciones que generan una entrada contable en la contabilidad general. Aquí indicamos cómo se calculaba anteriormente la divisa de notificación:

Importe en divisa de transacción \> Importe en divisa de contabilidad \> Importe de la divisa de notificación

Por ejemplo, se especifica una transacción en la divisa del dólar canadiense (CAD). El importe en CAD se convierte a la divisa de contabilidad, que es el dólar estadounidense (USD). El importe en USD se convierte a la divisa de notificación, que es el euro (EUR). Por lo tanto, los tipos de cambio tienen que existir entre CAD y USD, y entre USD y euros.

Este es el cálculo nuevo:

Importe en divisa de transacción \> Importe en divisa de contabilidad

Importe en divisa de transacción \> Importe en divisa de notificación

Debido a este cambio, los tipos de cambio tienen que existir ahora entre CAD y USD, y entre CAD y euros.

## <a name="reports-and-inquiries"></a>Informes y consultas

Ahora en diversos informes y consultas se muestran importes en divisa de notificación e importes en divisa de contabilidad. No todos los informes y consultas se han actualizado. Por ejemplo, los informes que muestran importes solo en la divisa de transacción no han cambiado.

Los cambios siguen dos patrones:

- Si el informe o la consulta tenía suficiente espacio para mostrar importes en la divisa de contabilidad y la divisa de notificación, los importes de la divisa de notificación se agregaban.
- Si el informe o la consulta no tenía suficiente espacio para mostrar importes en ambas divisas, una opción se agregaba de manera que los usuarios pudieran seleccionar qué divisa se muestra.

Para varios informes y consultas, también se añadió lógica para suprimir los importes de divisa de notificación si la divisa de notificación es la misma que la divisa de contabilidad, o si la divisa de notificación no se definió en el libro mayor de la entidad jurídica.

## <a name="financial-journals"></a>Diarios financieros

Los diarios financieros, como el diario y el diario de facturas de proveedor, se han actualizado para que incluyan información adicional sobre la divisa de notificación. Ahora los totales para el asiento y el diario se muestran en la divisa de notificación. Además, la información acerca del tipo de cambio de la divisa de notificación aparece ahora en la pestaña **General** de líneas de diario. Por lo tanto, puede anular el tipo de cambio de la divisa de notificación al entrar transacciones.

## <a name="module-changes"></a>Cambios en módulos

Los módulos siguientes utilizan la divisa de notificación como segunda divisa de contabilidad:

- [Contabilidad general](#general-ledger)
- [Informes financieros](#financial-reporting)
- [Proveedores](#accounts-payable-and-accounts-receivable)
- [Clientes](#accounts-payable-and-accounts-receivable)
- [Gestión de efectivo y bancos](#cash-and-bank-management)
- [Activos fijos](#fixed-assets)

### <a name="general-ledger"></a>Contabilidad general

Si una divisa de notificación estaba definida en el libro mayor, la contabilidad general ya realiza el seguimiento de los importes de divisa de notificación en todos los asientos contables. Sin embargo, estos importes ahora se convierten a partir de los importes de divisa de la transacción.

Los siguientes cambios adicionales se realizaron en el módulo **Contabilidad general**:

- Un tipo de cambio independiente de la divisa de notificación se puede definir en la contabilidad. Si una organización no desea usar un tipo de cambio distinto, puede dejar el campo para el tipo de cambio de la divisa de notificación en blanco. De manera alternativa, puede seleccionar el mismo tipo de cambio que se usa para la divisa de contabilidad. Si deja el campo en blanco, el sistema utiliza el tipo de cambio de la divisa de contabilidad.
- Un diario nuevo, el diario de ajuste de divisa de notificación, permite registrar los ajustes en cuentas contables solo en la divisa de notificación. Este diario habilita el registro únicamente en las cuentas contables. No admite empresas vinculadas, y la divisa debe ser la divisa de notificación de la entidad jurídica en la que se registra el diario. Cuando se registra el diario, los importes de divisa de transacción y la divisa de contabilidad son 0 (cero), y el importe de la divisa de notificación se registra con el importe especificado en la transacción. Dado que ha cambiado la forma en que se usa la divisa de notificación en los módulos **proveedores**, **clientes**, y **Activos fijos**, este diario se puede usar para los ajustes después de la actualización. Para ver ejemplos de cómo este diario se puede usar, consulte las secciones de estos módulos.
- El proceso para la asignación de período se ha actualizado para que asigne importes en las divisas de transacción, contabilidad e informe. Anteriormente, los importes se asignaban en las divisas de transacción y contabilidad y, a continuación, el importe de la divisa de contabilidad se convertía a la divisa de notificación. Dicho comportamiento podía hacer que un saldo permaneciera en la cuenta contable en la divisa de notificación. Ahora, cuando los importes se calculan y se usan en la entrada contable, no se hace ninguna conversión.
- El proceso para la revalorización de divisa extranjera ya revalorizó importes en la divisa de notificación. Sin embargo, el importe de la divisa de notificación ahora se calcula con el importe de la divisa de la transacción, como se describe en la sección [Proceso de registro](#posting-process) anterior en este tema.
- Muchos informes y consultas de contabilidad general tenían ya la divisa de notificación, pero algunos no la tenían. Un ejemplo es la página de lista **Saldo de comprobación**. Esta página de lista ahora incluye columnas para la divisa de contabilidad y la divisa de notificación. Tenga en cuenta que las columnas para la divisa de notificación están ocultas si la divisa de contabilidad y la divisa de notificación son iguales, o si no se definió ninguna divisa de notificación en el libro mayor.

### <a name="financial-reporting"></a>Informes financieros

Una mejora en el módulo **Informe financiero** permite incluir importes de divisa de notificación en un informe financiero de dos maneras. En la definición de columna, puede notificar directamente en los importes de divisa de notificación que se registran en la contabilidad (nueva funcionalidad). Como alternativa, puede continuar convirtiendo importes de la divisa de contabilidad a la divisa de notificación (funcionalidad existente).

Este cambio está disponible a través de la configuración **Visualización de divisas** en la definición de columna. Si se selecciona **Divisa de informe del libro mayor**, los importes de la columna no se convierten. En su lugar, se notifican directamente desde la contabilidad general. Si desea que la columna muestre importes convertidos, seleccione la opción **Convertir a XXXX**, donde *XXXX* es la divisa de notificación que la columna debe mostrar. En este caso, los importes de la divisa de contabilidad se convertirán a la divisa seleccionada usando la funcionalidad de conversión ya existente.

### <a name="accounts-payable-and-accounts-receivable"></a>Proveedores y Clientes

Los módulos **proveedores** y **clientes** ya hacían el seguimiento de los importes en divisa de notificación. Sin embargo, los importes no se mostraban ni se utilizaban para varios procesos. Se realizaron los siguientes cambios:

- Ahora los importes de divisa de notificación se muestran en las transacciones de clientes y proveedores. Los importes de divisa de notificación también se muestran para el saldo de apertura de cada transacción.
- Se ha actualizado el proceso de vencimiento de modo que una organización puede ver los depósitos de antigüedad en la divisa de contabilidad o la divisa de notificación.
- Diferentes consultas e informes se actualizaron de modo que muestren importes de divisa de notificación. Los ejemplos incluyen los informes **Conciliación Libro mayor-Cliente** y **Conciliación de proveedor a libro mayor**.
- El proceso para la revalorización de divisa extranjera ya revalorizó importes en la divisa de notificación. Sin embargo, el importe de la divisa de notificación ahora se calcula con el importe de la divisa de la transacción, como se describe en la sección [Proceso de registro](#posting-process).
- **Consideración de la actualización:** Antes de una actualización, los importes en divisa de notificación para los documentos (facturas, pagos, etc.) se calculan mediante la divisa de contabilidad. Por ejemplo, se registra una factura antes de que una organización se actualice, y la factura no se paga. Durante la actualización, la entrada contable de la factura no se cambia. Sin embargo, una vez realizada la actualización, los cambios para la divisa dual están en vigor. Por lo tanto, cuando se realiza un pago para la factura, el importe de la divisa de notificación del pago ahora se calcula a través del importe de la divisa de la transacción. Cuando se liquidan el pago y la factura, se puede calcular una ligera diferencia en el beneficio realizado/importe perdido, ya que los importes de la divisa de notificación ahora se calculan de manera diferente. Si se considera que la diferencia que se calcula es significativa, el nuevo diario de ajuste de divisa de notificación se puede utilizar para ajustar el saldo del beneficio realizado/pérdida y las cuentas contables de los proveedores/clientes solo en la divisa de notificación.

### <a name="cash-and-bank-management"></a>Gestión de efectivo y bancos

Anteriormente, el módulo **Gestión de efectivo y bancos** no realizaba el seguimiento de ningún importe de la divisa de notificación para las transacciones que se registraban con cada cuenta bancaria. Tras realizar una actualización, se realiza automáticamente el seguimiento de los importes de divisa de notificación para cualquier nueva transacción que se registre. Sin embargo, los importes de la divisa de notificación se deben agregar a las transacciones registradas anteriormente en el subdiario contable.

- **Consideración de la actualización:** como las transacciones de cuentas bancarias no realizaban anteriormente el seguimiento de los importes de divisa de notificación en el sublibro de contabilidad, se ha agregado un asistente para que pueda agregar importes de divisa de notificación a las transacciones de la cuenta bancaria. Este asistente **no** vuelve a registrar la contabilidad general. En su lugar, obtiene los importes de divisa de notificación de la contabilidad general y los actualiza en las tablas del subdiario contable.

    - Para iniciar el asistente, seleccione **Gestión de efectivo y bancos** \> **Configuración** \> **Añadir importes en divisa de notificación a las transacciones de cuenta bancaria**.
    - El asistente muestra las transacciones de todas las cuentas bancarias de la empresa actual que tienen un importe en la divisa de notificación de 0 (cero). Solo se incluyen las transacciones que se registraron antes de la actualización.
    - Para cada transacción de cuenta bancaria, el asistente encuentra las entradas contables correspondientes en la contabilidad general y escribe un importe predeterminado de la divisa de notificación. Aunque los importes puedan editarse, se recomienda **no** hacerlo. De lo contrario, es posible que no pueda conciliar los saldos de cuenta del banco en la contabilidad general. La única vez en que se debe editar un importe es si el importe de la divisa de notificación no se puede encontrar en la contabilidad general. En ese caso, el asistente mostrará un importe de 0 (cero) para la divisa de notificación.
    - Si selecciona **Cancelar** en el asistente, las transacciones de cuentas bancarias y cualquier modificación en los importes de divisa de notificación se guardará hasta la siguiente vez que ejecute el asistente. Sin embargo, los importes en divisa de notificación no se actualizan en las transacciones de cuenta bancaria. Esa actualización solo se produce cuando se selecciona **Fin** en el asistente. Puede ejecutar el asistente varias veces. Por lo tanto, puede corregir cualquier importe incorrecto de la divisa de notificación si se equivoca.

- No se cambió ningún proceso de gestión de efectivos y banco, pero varios informes y consultas se actualizaron de modo que muestren importes de divisa de notificación. Los informes de previsiones de flujo de efectivo son una excepción. No se actualizaron para incluir los importes de la divisa de notificación.

### <a name="fixed-assets"></a>Activos fijos

Anteriormente, el módulo **Activos fijos** no realizaba el seguimiento de ningún importe de la divisa de notificación para las transacciones que se registraban con cada libro de activos fijos. Tras realizar una actualización, se realiza automáticamente el seguimiento de los importes de divisa de notificación para cualquier nueva transacción que se registre. Sin embargo, los importes de la divisa de notificación se deben agregar a las transacciones registradas anteriormente en el subdiario contable.

Además, cambios importantes se han realizado en el proceso de depreciación. Estos cambios requieren la acción del usuario después de una actualización. Es importante que lea y comprenda los siguientes cambios, aunque no esté aún usando activos fijos.

- La forma en que el proceso de depreciación determina el importe de la divisa de notificación ha cambiado. El escenario siguiente compara cómo la depreciación determinaba anteriormente el importe de la divisa de notificación y cómo ahora determina el importe de la divisa de notificación.

    **Supuesto de depreciación**

    Un activo se adquiere y se registra con los importes siguientes. Tenga en cuenta que el importe de la divisa de notificación se registra en la contabilidad general, pero no se almacena en las tablas del subdiario contable del activo fijo.

    | Tipo de transacción | Importe de transacción | Tipo de cambio | Importe en divisa de contabilidad | Tipo de cambio | Importe en divisa de notificación |
    |------------------|--------------------|---------------|----------------------------|---------------|---------------------------|
    | Adquisición      | 1.000.000 coronas danesas      | 2.0           | 500.000 USD                | 2,5           | 200.000 EUR               |

    **Depreciación anterior de la divisa de notificación**

    Al final del año, la propuesta de depreciación se ejecuta y se calculan los importes siguientes.

    | Tipo de transacción | Importe de transacción | Tipo de cambio | Importe en divisa de contabilidad | Tipo de cambio | Importe en divisa de notificación |
    |------------------|--------------------|---------------|----------------------------|---------------|---------------------------|
    | Depreciación     | 50.000 USD         | 1.0           | 50.000 USD                 | 2.6           | 19.230,77 EUR             |

    Cuando se ejecuta la propuesta de depreciación, calcula el importe de la divisa de contabilidad usando el método de depreciación. A continuación convierte dicho importe a la divisa de notificación usando el tipo de cambio actual entre USD y euros. Esta conversión produce problemas, porque el activo no se puede depreciar completamente en la divisa de notificación cuando se utiliza la tasa de zona.

    **Nueva depreciación de la divisa de notificación**

    Se ha cambiado el proceso de depreciación para que el importe de la divisa de notificación se calcule también mediante el método de depreciación. Aquí se muestran los resultados de cuando la depreciación se ejecuta en el activo.

    | Tipo de transacción | Importe de transacción | Tipo de cambio | Importe en divisa de contabilidad | Tipo de cambio                                                       | Importe en divisa de notificación |
    |------------------|--------------------|---------------|----------------------------|---------------------------------------------------------------------|---------------------------|
    | Depreciación     | 50.000 USD         | 1.0           | 50.000 USD                 | 2,5<blockquote>[!NOTE] Aunque se visualiza este tipo de cambio, no se usa para convertir a la divisa de notificación.</blockquote> | 20.000 EUR                |

    Cuando se ejecuta la propuesta de depreciación, calcula el importe de la divisa de contabilidad y el importe de la divisa de notificación mediante el método de depreciación. A continuación se utilizan los importes de la entrada contable en la contabilidad general. No se realiza ninguna conversión para determinar el importe de la divisa de notificación.

- **Consideración de la actualización:** como las transacciones de libro de activos fijos no realizaban anteriormente el seguimiento de la divisa de notificación, se ha agregado un asistente para que pueda agregar importes de divisa de notificación a las transacciones de la cuenta bancaria. Este asistente **no** vuelve a registrar la contabilidad general. Dado que la forma en que la propuesta de depreciación calcula los importes de divisa de notificación ha cambiado, el asistente **tiene que** ejecutarse y completarse para cada empresa antes de que una organización pueda especificar cualquier transacción de depreciación.

    - Para iniciar el asistente, seleccione **Activos fijos** \> **Configuración** \> **Añadir importes en divisa de notificación a libros de activos fijos**.
    - El asistente muestra las transacciones de todos los libros de activos fijos de la empresa actual que tienen un importe en la divisa de notificación de 0 (cero). Solo se incluyen las transacciones que se registraron antes de la actualización.
    - El asistente **no** extrae los importes de la divisa de notificación de la contabilidad general. Como se describe en la situación de ejemplo anterior, los importes de la divisa de notificación que se registraban originalmente en la contabilidad general usaban incorrectamente la tasa de zona. Estos importes no deben aparecer en el subdiario de activo fijo, ya que el cálculo de depreciación siguiente utilizará importes incorrectos. En su lugar, el asistente encuentra el tipo de cambio en la fecha de la primera adquisición. A continuación usa dicho tipo de cambio para recomendar el importe de divisa de notificación que se debe registrar en el subdiario contable. Por ejemplo, aquí se muestra qué puede mostrar el asistente para la situación de ejemplo anterior.

        | Activo fijo | Reserva      | Tipo de transacción | Fecha de la transacción | Divisa | Importe en divisa de la transacción | Importe  | Tasa de cambio | Importe en divisa de notificación |
        |-------------|-----------|------------------|------------------|----------|--------------------------------|---------|-----------|---------------------------|
        | BUIL-00001  | 200\_SLLT | Adquisición      | 6/3/2016         | Coronas danesas      | 1.000.000                      | 500,000 | 2,5       | 250,000                   |
        | BUIL-00001  | 200\_SLLT | Depreciación     | 6/3/2016         | Coronas danesas      | 50.000                         | 50.000  | 2,5       | 250,000                   |
        | BUIL-00001  | 200\_SLLT | Depreciación     | 6/3/2016         | Coronas danesas      | 50.000                         | 50.000  | 2,5       | 250,000                   |
        | BUIL-00001  | 200\_SLLT | Depreciación     | 6/3/2016         | Coronas danesas      | 50.000                         | 50.000  | 2,5       | 250,000                   |

    - Muchos clientes realizaban el seguimiento de los detalles de transacción de activos en libros. Estos detalles incluyen los tipos de cambio e importes. Si tiene estos datos en un libro, puede crear un tipo de cambio personalizado y actualizarlo con los tipos de cambio del libro. A continuación este tipo de cambio se va a utilizar para especificar un tipo de cambio predeterminado en la fecha de adquisición y para calcular el importe de la divisa de notificación. Si no se selecciona ningún tipo de cambio, el asistente usa el tipo de cambio definido en el libro mayor.
    - Los importes del tipo de cambio y la divisa de notificación se pueden cambiar. Si se cambia el tipo de cambio, el importe de la divisa de notificación se vuelve a calcular usando el nuevo tipo.
    - Si selecciona **Cancelar** en el asistente, las transacciones del libro de activos fijos y cualquier modificación en los importes de tipo d ecambio o de divisa de notificación se guardará hasta la siguiente vez que ejecute el asistente. Sin embargo, los importes en divisa de notificación no se actualizan en las transacciones del libro de activos fijos. Esa actualización solo se produce cuando se selecciona **Fin** en el asistente. Puede ejecutar el asistente varias veces. Por lo tanto, puede corregir cualquier importe incorrecto de la divisa de notificación si se equivoca.
    - Cuando los importes de la divisa de notificación estén completamente actualizados en el sublibro de contabilidad, **tiene** que establecer la opción **¿Se han actualizado todos los importes de divisa de notificación en las transacciones del libro de activos fijos?** en **Sí** y después seleccionar **Fin**. Los cálculos de depreciación no se pueden completar hasta que no haya establecido la opción **¿Se han actualizado todos los importes de divisa de notificación en las transacciones del libro de activos fijos?** en **Sí**. Después que la opción esté establecida en **Sí**, el asistente dejará de estar disponible.
    - Una vez que las transacciones de activos fijos en el sublibro de contabilidad se actualicen con importes de divisa de notificación, dichos importes no coincidirán con los importes que se han registrado originalmente en la contabilidad general. Sin embargo, el diario de ajuste de divisa de notificación se puede usar para actualizar los saldos de las cuentas contables de depreciación en la contabilidad general, de modo que coincidan con los importes que se registraron originalmente.
    - Una nueva entidad **Importes en divisa de notificación para transacción de activos** que se ha agregado en el espacio de trabajo **Gestión de datos** le permite exportar los datos desde el asistente. Entonces puede utilizar los datos para determinar el saldo en el subdiario de activo fijo para las transacciones de depreciación. Dicho saldo se puede utilizar para determinar el importe del ajuste de divisa de notificación en la contabilidad general.

- **Consideración de actualización:** se han agregado nuevos campos de configuración a los activos fijos y se usan en el cálculo de depreciación. Es posible que tenga que actualizar estos campos antes del cálculo de la depreciación siguiente.

    - En el libro de activos fijos (**Activos fijos** \> **Libros**), la ficha desplegable **General** tiene un nuevo campo **Precio de adquisición en divisa de notificación**.
    - En el libro de activos fijos (**Activos fijos** \> **Libros**), la ficha desplegable **Depreciación** tiene un nuevo campo **Valor residual previsto en la divisa de notificación**.
    - En los parámetros de activo fijo (**Activos fijos** \> **Configuración** \> **Parámetros de activos fijos**), la ficha desplegable **General** tiene un nuevo campo **Importe mínimo de depreciación en la divisa de notificación**.
    - En los libros (**Activos fijos** \> **Configuración** \> **Libros**), la ficha desplegable **General** tiene dos nuevos campos: **Redondear depreciación en la divisa de notificación** y **Dejar valor neto en los libros en la divisa de notificación**.

- Dado que la propuesta de depreciación calcula ahora importes en la divisa de contabilidad y la divisa de notificación, se ha actualizado el diario de activos fijos de modo que muestre los importes de depreciación en la divisa de notificación. Para las transacciones de depreciación, la divisa de la transacción es siempre la divisa de contabilidad. Por lo tanto, dichos importes seguirán apareciendo en las columnas **Debe** y **Crédito**. Dos nuevas columnas, **Debe en divisa de notificación** y **Crédito en divisa de notificación**, se han agregado a la cuadrícula.

    - Los nuevos campos solo están disponibles cuando el tipo de transacción sea uno de los cuatro tipos de depreciación: **Deprecación**, **Ajuste de depreciación**, **Depreciación extraordinaria**, o **Índice de depreciación especial**.
    - Si se especifica un tipo de transacción de la deprecación en el diario de activos fijos, los importes de la divisa de notificación aparecerán en las nuevas columnas. Estos importes se pueden modificar.
    - Si la divisa de contabilidad y las divisas de notificación en el libro mayor son las mismas, los importes se mantendrán sincronizados. Si cambia el importe de **Crédito**, el importe de **Crédito en divisa de notificación** será automáticamente cambiado de modo que coincida con él.
    - Si especifica cualquier otro tipo de transacción en el diario de activos fijos, los importes **Débito en divisa de notificación** y **Crédito en divisa de notificación** nunca se muestran, ya sea antes o después del registro. Los importes de la divisa de contabilidad y la divisa de notificación siguen estando disponibles en el asiento que registra en la contabilidad general.
