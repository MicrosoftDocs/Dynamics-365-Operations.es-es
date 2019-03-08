---
title: Conversión de consolidaciones financieras y divisa
description: Este tema describe las consolidaciones financieras y la conversión de divisas en contabilidad general.
author: aprilolson
manager: AnnBe
ms.date: 07/09/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2018-5-31
ms.dyn365.ops.version: 8.0.1
ms.openlocfilehash: 8427d53bac3216d362b2bf8983a847f069351b3b
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/29/2019
ms.locfileid: "354009"
---
# <a name="financial-consolidations-and-currency-translation"></a>Conversión de consolidaciones financieras y divisa

[!include [banner](../includes/banner.md)]

Este tema le informa sobre el método que Microsoft Dynamics 365 for Finance and Operations y el informe financiero usan para las consolidaciones. Describe las situaciones que implican informes de varias compañías, agregaciones, eliminaciones e intereses minoritarios. También explica cómo gestionar situaciones especiales, como escenarios donde las entidades jurídicas tienen varios períodos fiscales o varios planes contables.

Este tema se escribió para los usuarios y los consultores funcionales, y supone que los lectores tienen una comprensión general de Finance and Operations y los informes financieros. La configuración básica no se aborda.

> [!NOTE]
> El término *entidad jurídica* se utiliza en Finance and Operations y el término *empresa* se usa en informes financieros. Ambos términos se utilizan en este tema. Sin embargo, a efectos de este tema, sus significados son iguales.

## <a name="audience"></a>Audiencia
Este tema está destinado a los usuarios de las finanzas y contabilidad y los consultores de solicitudes que desean utilizar Finance and Reporting y los informes financieros para la consolidar varias empresas y datos en varias divisas.

## <a name="approach"></a>Enfoque
Finance and Operations usa una entidad jurídica independiente para procesar una consolidación. Habilita las consolidaciones de instancia única pero proporciona una opción para obtener datos de otros orígenes. El proceso de consolidación debe ejecutarse cada vez que los cambios se introducen en las entidades jurídicas de origen.

El informe financiero puede consolidar varias empresas durante la generación de informes. Aunque los datos se almacenen en un data mart, se creen versiones de ellos, y se pueden exportar, cada empresa de origen es la propietaria y el contenedor de los datos. El informe se puede ejecutar en cualquier momento, incluso cada minuto (por ejemplo). Proporciona muchos beneficios adicionales, como la capacidad de explorar en profundidad todas las empresas y dimensiones.

Los usuarios pueden usar Consolida en línea, informes financiero, o una combinación. Su elección depende de las necesidades de su empresa y de las preferencias de los auditores.

## <a name="consolidations"></a>Consolidaciones
El módulo **Consolidaciones** incluye las opciones para consolidar varias entidades jurídicas durante el proceso de consolidación, y para importar o exportar el saldo de una empresa. También puede configurar eliminaciones y registrar diarios de eliminaciones.

## <a name="benefits-of-using-consolidate-online"></a>Beneficios de usar Consolidar en línea
Los clientes que usan el módulo **Consolidaciones** obtendrán diversos beneficios:

- **Profundidad de datos** Puede crear informes consolidados que reúnen los datos reales y de presupuesto tanto a nivel de cuenta como a nivel de dimensión.
- **Consolidaciones dinámicas** Las consolidaciones se pueden procesar varias veces.
- **Capacidades de la auditoría** Las dimensiones y las cuentas se mantienen para el análisis y la auditoría, y los saldos se crean por fecha.
- **Conversión de la divisa** Puede configurar los intervalos y las tasas de la cuenta para convertir la divisa de contabilidad de la empresa de origen a la divisa de contabilidad de la empresa de consolidación.
- **proceso de eliminación en una empresa de eliminación o consolidada** Puede procesar y registrar eliminaciones en único proceso durante la consolidación. Como alternativa, puede ejecutar una oferta por separado.

## <a name="supported-consolidation-scenarios"></a>Situaciones de ejemplo de consolidaciones admitidas
Aquí hay alguna de las situaciones de consolidación que Consolidar en línea admite:

- Consolidaciones de un solo nivel entre entidades jurídicas
- Consolidaciones que suponen eliminaciones
- Interés minoritario (para esta situación, el cálculo manual y la entrada en la empresa deben utilizarse.)
- Numerosos planes contables en entidades jurídicas
- Diferentes calendarios fiscales en numerosas entidades jurídicas
- Consolidaciones que implican varias divisas contables

## <a name="legal-entity-setup"></a>Configuración de entidades legales
Antes de procesar una consolidación, debe configurar la entidad jurídica. Puede ejecutar la consolidación tantas veces como sea necesario, y todos los datos se convertirán desde la divisa de contabilidad de la empresa de origen a la divisa que está definida para la empresa de consolidación. Por lo tanto, para la siguiente estructura organizativa, si debe convertir todas las empresas norteamericanas primero a dólares estadounidenses (USD) y luego a euros (EUR), la divisa de la empresa matriz, debe tener al menos dos empresas de consolidación.

![Estructura organizativa](./media/organizational-structure.png "Estructura organizativa")

En la estructura organizativa anterior, debe tener una entidad jurídica para la consolidación norteamericana, ya que las consolidaciones se consolidan siempre desde la divisa de contabilidad de la empresa de origen hasta la divisa de la empresa de consolidación. En el ejemplo, si todas las empresas están incluidas en una sola consolidación, la filial mexicana se convertirá de Pesos mexicanos (MXN) a euros, y no del MXN a USD y a euros.

Al crear la entidad jurídica, puede especificar si se usa la empresa para el proceso de consolidación y el proceso de eliminación, o sólo uno de estos procesos. En la siguiente ilustración, se usa la empresa para ambos procesos. Tenga en cuenta que no puede registrar los diarios en una empresa de consolidación, pero puede registrarlos en una empresa de eliminación. Por lo tanto, puede que desee tener una empresa de eliminación independiente.

![Entidad jurídica que se usa para la consolidación y la eliminación](./media/sep-elimination-company.png "Entidad jurídica que se usa para la consolidación y la eliminación")

## <a name="main-accounts-and-consolidation-account-groups"></a>Cuentas principales y grupos de cuentas de consolidación
Una decisión que debe tomar es cómo desea consolidar su plan de cuentas. Durante el proceso de consolidación, tiene tres opciones para consolidar cuentas principales.

La primera opción es usar las cuentas principales de las empresas de origen. En este caso, cada cuenta de todas las empresas se consolida. Por ejemplo, si el efectivo es la cuenta 100000 en la empresa USMF y la cuenta 1100 en la empresa DEMF, la empresa de consolidación incluirá ambas cuentas. Cada cuenta tendrá su saldo respectivo.

La segunda opción es especificar una cuenta predeterminada de consolidación en la página **Cuentas principales**. La cuenta a continuación se asignará a la cuenta de consolidación. Esta opción puede ser útil si tiene varios planes contables o debe asignar a un gráfico definido por las sedes.

![Cuenta de consolidación predeterminada especificada en la página de las cuentas principales](./media/main-accounts.png "Cuenta de consolidación predeterminada especificada en la página de las cuentas principales")

La tercera opción es usar grupos de cuentas de consolidación. Puede definir tantos grupos de cuentas de consolidación como sea necesario. A continuación, en la página **Cuentas de consolidación adicional**, sólo se asigna la cuenta principal del plan de cuentas a la cuenta que se requiere para ese grupo.

![Asignación en la página Cuentas de consolidación adicional](./media/additional-consolidation-accounts.png "Asignación en la página Cuentas de consolidación adicional")

## <a name="consolidating-online"></a>Consolidación en línea
Para aprender a especificar detalles de consolidaciones en línea, consulte [Consolidar en línea](./consolidate-online.md).

## <a name="managing-consolidation-transactions"></a>Gestión de transacciones de consolidaciones
Para ver los resultados de la consolidación, tiene varias opciones:

- Generar un informe financiero con la empresa de consolidación.
- Revise la página de la lista **Saldo de comprobación** en la empresa de consolidación.
- En la lista de transacciones de consolidación en la página **Consolidaciones**, vea los saldos que se crean por fecha para cada empresa de origen por cada período.

    ![Transacciones de consolidación en la página Consolidaciones](./media/managing-consolidation-transactions.png "Transacciones de consolidación en la página Consolidaciones")

Para ejecutar la consolidación de nuevo, simplemente puede procesar la consolidación. Como alternativa, puede seleccionar **Eliminar transacciones** en la página **Consolidaciones**.

## <a name="consolidate-with-import"></a>Consolidar con importación
La funcionalidad Consolidar con importación funciona como la funcionalidad Consolidar en línea. Cuando selecciona las entidades jurídicas, se examina el archivo de origen que contiene los datos.

## <a name="export-company-balances"></a>Exportación de saldos de compañía
La funcionalidad Exportación de saldos de compañía funciona también como la funcionalidad Consolidar en línea. Cuando seleccione las entidades jurídicas, establecerá una ruta de archivo para la salida.

## <a name="elimination-rules"></a>Reglas de eliminación
Para eliminar transacciones de empresas vinculadas, puede crear una regla de eliminación. Como alternativa, puede hacer una entrada de eliminación manual en una empresa que esté designada como empresa de eliminación. Si crea una regla de eliminación, tiene dos opciones para el método de eliminación: **Cambio neto** y **Fijo**.

### <a name="set-up-elimination-rules"></a>Configurar reglas de eliminación
Al configurar reglas de eliminación de Finance and Operations, puede crear una dimensión financiera que se use específicamente para la eliminación. La mayoría de los clientes denominan esta dimensión financiera **Socio comercial** o algo similar. Si decide no utilizar una dimensión financiera, asegúrese de tener cuentas principales que solo se usen para transacciones de empresas vinculadas.

Puede encontrar la configuración de eliminaciones en el área de **Configuración** del módulo de **Consolidaciones**. Tras introducir una descripción para la regla, debe seleccionar la empresa en la que registrará el diario de eliminaciones. La empresa que seleccione ha de tener la opción **Usar para el proceso de eliminación financiera** seleccionada en la configuración de la entidad jurídica.

Puede definir la fecha en la que la regla de eliminación se convierte en efectiva y la fecha en la que vence, como sea necesario. Si quiere que la regla de eliminación esté disponible en el proceso de propuesta de eliminación, debe establecer la opción **Activa** en **Sí**. Seleccione un nombre de diario del tipo **Eliminación**.

![Propiedades básicas de una regla de eliminación](./media/ledger-elimination-rule-journal.png "Propiedades básicas de una regla de eliminación")

Una vez que haya definido los fundamentos, seleccione **Líneas** para definir las reglas de procesamiento reales. Hay dos opciones para las eliminaciones, puede eliminar el importe neto de cambio o definir un importe fijo.

Seleccione las cuentas de origen. Puede usar un asterisco (\*) como carácter comodín. Por ejemplo, **1\*** selecciona todas las cuentas que empiezan por **1** como origen de datos para la asignación.

Una vez que haya seleccionado las cuentas de origen, use el campo **Especificación de la cuenta** para especificar la cuenta de la empresas de destino que se utiliza. Seleccione **Origen** si desea usar la misma cuenta principal que está definida en la cuenta de Origen. Si selecciona **Definido por el usuario**, deberá especificar una cuenta de destino.

![Página de la línea de regla de eliminación contable](./media/ledger-elimination-rule-line.png "Página de la línea de regla de eliminación contable")

El campo **Especificación de la dimensión** funciona como el campo **Especificación de la cuenta**. Seleccione **Origen** para utilizar las mismas dimensiones en la empresa de destino y la empresa de origen. Si selecciona **Definido por el usuario**, tiene que especificar las dimensiones de la empresa de destino seleccionando **Dimensiones de destino**. A continuación, seleccione las dimensiones de origen y las dimensiones financieras y los valores que se usan como origen de la eliminación.

### <a name="process-elimination-transactions"></a>Procesar transacciones de eliminación
Hay dos maneras de procesar transacciones de eliminación. La transacción se puede procesar durante el proceso en línea de consolidación, o puede crear un diario de eliminaciones y ejecutar el proceso de propuesta de eliminación. Esta sección se centra en la segunda opción.

En una empresa definida como empresa de eliminación, seleccione **Diario de eliminaciones** en el módulo de **Consolidaciones**. Una vez que haya seleccionado el nombre de diario, seleccione **Líneas**. Para ejecutar la propuesta, seleccione **Propuestas** \> **Propuesta de eliminación**.

Seleccione la empresa que es el origen de los datos consolidados y, a continuación, seleccione la regla del proceso. Escriba las fechas de inicio y fin para definir el intervalo de fechas donde se buscan los importes de eliminación. El campo **Fecha de registro de contabilidad general** especifica la fecha utilizada para registrar el diario en la contabilidad general. Después de seleccionar **Aceptar**, puede revisar los importes y registrar el diario.

> [!NOTE]
> El diario de eliminaciones muestra los importes para valores de la cuenta en la divisa de las transacciones de origen, no en la divisa de contabilidad. Cuando revise los importes en el diario de eliminaciones, es posible que encuentre que este comportamiento confunde.

Para obtener más información y ejemplos, consulte [Reglas de eliminación](./elimination-rules.md).

## <a name="currency-revaluation-in-a-consolidation-company"></a>Revalorización de divisa en una empresa de consolidación
Cuando se consolidan datos desde una divisa de contabilidad a otra, debe seguir ejecutando la revalorización de divisa si hay un cambio en los tipos de cambio, para que los saldos de cuenta se revaloricen correctamente. Al consolidar por primera vez los datos, use la pestaña **Conversión de la divisa** para seleccionar los tipos de cambio iniciales que deben usarse para su conversión durante el proceso de consolidación. Después de que se introduzcan un nuevo tipo de cambio (por ejemplo, el mes próximo), debe revalorizar los saldos de cuenta. Después se actualizarán los beneficios no realizados o las pérdidas, en función de la fecha y los nuevos tipos de cambio.

Para obtener más información sobre la revalorización de divisas en una empresa de consolidación consulte [Revalorización de divisa en una empresa de consolidación](currency-revaluation-consolidation-company.md).

Para obtener más información sobre cómo funciona la revalorización de divisas en el módulo **contabilidad general**, consulte [Revalorización de divisa extranjera para la contabilidad general](./foreign-currency-revaluation-general-ledger.md).

### <a name="additional-information"></a>Información adicional
- Se consolidan todas las capas de registro cuando se procesa la consolidación.
- Los diarios de eliminaciones sólo se pueden registrar en la capa actual.
- Sólo los saldos en funcionamiento se consolidan. Por lo tanto, para ver los saldos de apertura, debe ejecutar igualmente un cierre de fin de año en la empresa de consolidación.
- Puede registrar un diario en una empresa de eliminación, pero no en una empresa de consolidación.

## <a name="benefits-of-using-financial-reporting-for-financial-consolidations-and-currency-translation-or-to-complement-consolidate-online-for-consolidated-reporting"></a>Beneficios de usar el informe financiero para las consolidaciones financieras y la conversión de divisas, o para complementar Consolidar en línea para las notificaciones consolidadas
Los clientes que usan informes financieros para las consolidaciones financieras y la conversión de divisas, o para complementar Consolidar en línea para las notificaciones consolidadas obtienen diversos beneficios:

- **Profundidad de datos** Puede crear informes consolidados que reúnen los datos reales y de presupuesto tanto a nivel de cuenta como a nivel de dimensión. Para Finance and Operations estos datos incluyen datos del control presupuestario y de la planificación de presupuesto.
- **Consolidaciones dinámicas** Las consolidaciones se pueden realizar en cualquier momento y en cualquier nivel de la jerarquía organizativa.
- **Completar capacidades de la auditoría** Todas las dimensiones, las cuentas y los detalles de transacciones se mantienen para el análisis y la auditoría. Además, el informe financiero proporciona una exploración inversa completa a la transacción original en cualquiera de las entidades jurídicas que se consolidan.
- **Conversión agilizada de la divisa** Tras la configuración mínima en Finance and Operations, puede convertir cualquier informe de notificación financiera a cualquier divisa de notificación que se haya configurado. Además, puede configurar un número ilimitado de divisas de notificación.
- **Registrar eliminaciones en el origen** Puede crear e imprimir un informe de eliminación para verificar transacciones de eliminación. Puede registrar cualquier nueva eliminación como transacciones de empresas vinculadas estándar. También puede usar una entidad jurídica de eliminación para cualquier transacción que no desee en las entidades jurídicas.

## <a name="supported-consolidation-scenarios"></a>Situaciones de ejemplo de consolidaciones admitidas
Aquí hay alguna de las situaciones de consolidación que Informes financieros admite:

- Consolidaciones de un solo nivel y varios niveles entre entidades jurídicas
- Consolidaciones que usan estructuras de la organización que se crean a partir de las entidades jurídicas
- Consolidaciones que suponen eliminaciones
- Interés minoritario
- Numerosos planes contables en entidades jurídicas
- Diferentes calendarios fiscales en numerosas entidades jurídicas
- Consolidaciones que implican varias divisas contables
- Consolidaciones de unidad de negocio

## <a name="generating-consolidated-financial-statements"></a>Generar informes financieros consolidados
Para obtener información sobre los escenarios donde puede generar o consolidar informes financieros, consulte [Generar informes financieros consolidados](./generating-consolidated-financial-statements.md).
