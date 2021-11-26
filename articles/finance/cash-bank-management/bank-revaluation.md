---
title: Revalorización bancaria de divisa extranjera
description: Este tema proporciona una visión general del proceso de revalorización de divisa extranjera del banco. Incluye información sobre la configuración, la ejecución del proceso, el cálculo para el proceso, y la inversión de transacciones de revalorización.
author: roschlom
ms.date: 05/16/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: BankCurrencyRevalHistory
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: roschlom
ms.search.validFrom: 2019-03-08
ms.dyn365.ops.version: 10
ms.openlocfilehash: 3df6a22e06abbfa75a12ffddac242dd34f5beba5
ms.sourcegitcommit: 408786b164b44bee4e16ae7c3d956034d54c3f80
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/05/2021
ms.locfileid: "7754129"
---
# <a name="bank-foreign-currency-revaluation"></a>Revalorización bancaria de divisa extranjera

[!include [banner](../includes/banner.md)]


Este tema proporciona una visión general del proceso de revalorización de divisa extranjera del banco. Explica cómo configurar y ejecutar el proceso, y proporciona información acerca del cálculo para el proceso. También se explica cómo invertir las transacciones de revalorización, si se necesita la inversión.

Como parte de una período final, las prácticas contables requieren que los saldos de la cuenta de ese banco en divisas extranjeras se revaloricen mediante distintos tipos de cambio (circulante, histórico, medio, etc.). La característica de revalorización de divisa extranjera del banco se puede usar para revalorizar una o más cuentas bancarias. La función también es una función global. Por lo tanto, desde una sola página, puede revalorizar los bancos en todas las entidades jurídicas a las que tiene acceso.

> [!NOTE]
> Si ejecuta el proceso de revalorización, el saldo en cada cuenta bancaria que se haya registrado en una divisa extranjera se revalorizará. Las transacciones de pérdidas o ganancias no realizadas que se crean durante el proceso de revalorización son generadas por el sistema. Se pueden crear dos transacciones, una para la divisa de contabilidad y una para la divisa de notificación, si una divisa de notificación es procedente. Cada entrada contable se publicará para el beneficio o pérdida no realizada y la cuenta principal que se revalorizará.

## <a name="prepare-to-run-foreign-currency-revaluation"></a>Preparación para ejecutar una revalorización de divisa extranjera

Para poder ejecutar el proceso de revalorización, se requiere la siguiente configuración.

- En la página **Libro mayor**, especifique el tipo de cambio. Si no se define un tipo de cambio en la cuenta principal, se va a utilizar este tipo de cambio durante la revalorización de divisa extranjera.
- En la página **Libro mayor**, especifique las cuentas de beneficio realizado, pérdida realizada, beneficio no realizado y pérdida no realizada para la revalorización de divisa. Se utilizan las cuentas de beneficio realizado y de pérdida realizada cuando se liquiden las transacciones de los clientes y los proveedores. Las cuentas de beneficio no realizado y pérdidas no realizadas se usan para revalorizar transacciones abiertas y cuentas principales de contabilidad general.
- En la página **Cuentas de revalorización de divisa**, seleccione cuentas de revalorización de divisa diferentes para cada divisa y empresa. Si no se define ninguna cuenta, se usan las cuentas de la página **Libro mayor**.

## <a name="enable-foreign-currency-revaluation"></a>Active revalorización de divisa extranjera

Debe activar la característica de la revalorización de divisa extranjera del banco antes de poder procesar revalorizaciones de divisa extranjera.

1. Vaya a **Gestión de efectivo y bancos \> Configurar \> Parámetros de gestión de efectivo y bancos**.
2. En la pestaña **General** , bajo **Revalorización de divisa extranjera**, establezca la opción **Activar revalorización bancaria** en **Sí** para activar la función para la entidad jurídica actual. 
3. En la pestaña **Secuencias numéricas** , agregue una secuencia numérica para la revalorización de divisa extranjera.
4. Actualice el explorador para ver **Revalorización de divisa extranjera** en la sección **Tareas periódicas** de la página de área.

Debe activar la función para cada entidad jurídica que utiliza la revalorización de divisa extranjera. Si tiene asignado el rol de administrador del sistema o el rol de administrador de características, puede eliminar este paso habilitando la característica denominada **Habilitar la revalorización del banco sin un parámetro** en el área de trabajo **Administración de características**.

> [!NOTE]
> Si su entidad jurídica usa un ruso, un polaco, o un país/húngaro un código de región, puede hacer ya la revalorización de divisa extranjera del banco. No podrá utilizar la revalorización de divisa extranjera usada por otros países o regiones.

## <a name="process-foreign-currency-revaluation"></a>Procesamiento de la revalorización de divisa extranjera

Después de que la configuración se complete, use la página **Revalorización de divisa extranjera** en gestión de efectivo y bancos para revalorizar los saldos de una o más cuentas bancarias en todas las entidades jurídicas. Puede ejecutar el proceso en tiempo real o puede programarlo para ejecutarlo mediante un lote.

La página **Revalorización de divisa extranjera** muestra el historial de cada proceso de revalorización. Muestra si el proceso se ejecutó y qué criterios se definieron y ofrece un vínculo al asiento que se creó para la revalorización. También muestra si una revalorización anterior se ha invertido. Para ejecutar el proceso de revalorización, seleccione **Revalorización de divisa extranjera** en el panel de acciones para abrir el cuadro **Banco - revalorización de divisa extranjera**.

El campo **Fecha de revalorización** define la fecha límite para calcular el saldo de la divisa extranjera que se va a revalorizar. La suma de todas las transacciones bancarias que tuvieron lugar hasta esta fecha se revaloriza.

El campo **Fecha del tipo de cambio** define la fecha del tipo de cambio que se usará para revalorizar los saldos de la divisa. Por ejemplo, puede revalorizar los saldos el 31 de enero pero usar el tipo de cambio definido para el 1 de febrero.

El proceso de revalorización se puede ejecutar para una o más entidades jurídicas. La búsqueda mostrará solo las entidades jurídicas a las que tiene acceso. Seleccione las entidades jurídicas para las que desee seleccionar las cuentas bancarias que son aptas para la revalorización de divisa extranjera. En la cuadrícula se mostrarán todas las cuentas bancarias para esas entidades legales.

Establezca la opción **Vista previa antes del registro** en **Sí** si desea revisar los resultados de la revalorización antes de registrarla. La revalorización de divisa extranjera tiene una vista previa que se pueda registrar. No es necesario ejecutar el proceso de revalorización de nuevo. Puede exportar los resultados de la vista previa a Microsoft Excel para conservar un historial de cómo se calcularon los importes. No puede usar el procesamiento por lotes si desea obtener una vista previa de los resultados de la revalorización.

Seleccione **Aceptar** para procesar la revalorización de divisa extranjera. Se crea un registro para realizar un seguimiento del historial de cada vez. Se creará un registro individual para cada entidad jurídica y capa de registro.

## <a name="calculate-unrealized-gainloss"></a>Calcule las pérdidas/ganancias no realizadas

En gestión de efectivo y bancos, la divisa del banco se considerará como la divisa base y no se revaloriza. El saldo de la cuenta bancaria en la divisa de contabilidad se revaloriza mediante los tipos de cambio entre la divisa del banco y la divisa de contabilidad en **Fecha del tipo de cambio**. El saldo de la cuenta bancaria en la divisa de notificación también se revaloriza mediante los tipos de cambio entre la divisa del banco y la divisa de notificación en **Fecha del tipo de cambio**.

Se crea una transacción para la diferencia entre el saldo de la cuenta bancaria y el nuevo saldo que se calcula para la divisa de contabilidad. Se crea otra transacción para la diferencia entre el saldo de la cuenta bancaria y el nuevo saldo que se calcula para la divisa de notificación. Las entradas para estas transacciones se marcan como conciliadas. 

No se crea ninguna entrada para la divisa de contabilidad si la divisa del banco coincide con la divisa de contabilidad. De forma similar, no se crea ninguna entrada para la divisa de notificación si la divisa del banco coincide con la divisa de notificación.

La transacción de revalorización de divisa extranjera también se divide en las distintas dimensiones que se encuentran en las transacciones bancarias. La división se basa en el saldo de cada dimensión. Por ejemplo, el saldo bancario totales son de 10 000, pero el saldo para la unidad de negocio 001 es 4000, mientras que el saldo de la unidad de negocio 002 es 6000. En este caso, el 40 por ciento del importe de la revalorización se registra en la cuenta de revalorización que tiene la unidad de negocio 001 y el 60 por ciento se registra en la cuenta de revalorización que tiene la unidad de negocio 002. Si la estructura contable no incluye una unidad de negocio, el importe completo se registra en la cuenta de revalorización.

## <a name="reverse-foreign-currency-revaluation"></a>Invertir revalorización de divisa extranjera

Si debe invertir la transacción de revalorización, seleccione el botón **Invertir transacción** en el panel de acción de la página **Revalorización de divisa extranjera**. Un nuevo registro histórico de la revalorización de divisa extranjera se creará para mantener la traza de auditoría histórica de cuándo se produjo o se ha invertido la revalorización.

Para invertir varias revalorizaciones, debe invertir la revalorización más actual primero. Después continúe invirtiendo las revalorizaciones más antiguas por fecha más antigua. A continuación puede procesar las nuevas revalorizaciones para los períodos que se invirtió.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
