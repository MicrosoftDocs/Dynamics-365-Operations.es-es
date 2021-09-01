---
title: Solucionar problemas de operaciones de inventario
description: Este tema describe cómo solucionar problemas que pueden surgir al trabajar con operaciones de inventario.
author: sherry-zheng
ms.date: 12/03/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: chuzheng
ms.search.validFrom: 2020-12-03
ms.dyn365.ops.version: Release 10.0.16
ms.openlocfilehash: 1198bc12830afa2ae2c5eb8e77413a9d8ef70c625823f676ab1965ff250c2443
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2021
ms.locfileid: "6730402"
---
# <a name="troubleshoot-inventory-operations"></a>Solucionar problemas de operaciones de inventario

[!include [banner](../includes/banner.md)]

Este tema describe cómo solucionar problemas que pueden surgir al trabajar con operaciones de inventario.

## <a name="i-cant-find-the-workflow-drop-down-dialog-box-for-inventory-journals"></a>No encuentro el cuadro de diálogo desplegable "Flujo de trabajo" para los diarios de inventario.

### <a name="issue-description"></a>Descripción del problema

No encuentra el cuadro de diálogo desplegable **Flujo de trabajo** en la página del diario, o las operaciones de flujo de trabajo relacionadas no están disponibles.

Este problema puede producirse por tres motivos, como se describe en las siguientes subsecciones.

### <a name="issue-resolution-1"></a>Solución del problema 1

Si el problema se aplica a todos los usuarios, es posible que se deba a que el flujo de trabajo de aprobación no se ha asignado al nombre del diario. Para arreglar el problema, siga estos pasos.

1. Vaya a **Gestión del inventario &gt; Configurar &gt; Nombres de diarios &gt; Inventario**.
1. En el panel de lista, seleccione un nombre de diario para abrir su configuración.
1. En la ficha desplegable **General**, establezca la opción **Flujo de trabajo de aprobación** en *Sí*. Seleccione **Sí** si se le solicita que confirme el cambio.
1. En el campo **Flujo de trabajo**, seleccione el flujo de trabajo que desee usar para el nombre de diario seleccionado.

### <a name="issue-resolution-2"></a>Solución del problema 2

Si su flujo de trabajo utiliza código personalizado, pueden surgir problemas después de actualizar el sistema. Por ejemplo, en el flujo de trabajo del diario, el botón **Enviar** puede aparecer atenuado, por lo que no puede seleccionarlo para aprobar un envío.

Si el botón **Enviar** está atenuado, es posible que su flujo de trabajo se haya personalizado, lo que significa que el método del flujo de trabajo, `canSubmitToWorkflow()` en `FormDataUtil`, se ha extendido. Para solucionar este problema, cambie la forma en que amplía el método del `canSubmitToWorkflow()` para usar la estructura en el siguiente ejemplo.

```xpp
[ExtensionOf(formStr(InventJournalMovement))]
public final class InventJournalMovement_extension
{
    public boolean canSubmitToWorkflow()
    {
        boolean ret = YourLogicOfCanSubmitToWorkflow();

        return ret;
    }
}
```

### <a name="issue-resolution-3"></a>Solución del problema 3

Si el problema solo se aplica a algunos usuarios específicos, es posible que esos usuarios no tengan los privilegios de seguridad necesarios para ejecutar operaciones de flujo de trabajo en diarios de inventario. Compruebe que cada usuario afectado tenga el privilegio de seguridad *Mantener el flujo de trabajo del diario de inventario*. De forma predeterminada, este privilegio se asigna a un deber que tiene el mismo nombre, y ese deber se aplica a los roles *Trabajador de almacén* y *Responsable de almacén*.

## <a name="my-inventory-journal-remains-in-system-locked-status-and-the-workflow-batch-job-doesnt-work"></a>Mi diario de inventario permanece en el estado bloqueado por el sistema y el trabajo por lotes del flujo de trabajo no funciona.

### <a name="issue-description"></a>Descripción del problema

Uno de sus diarios de inventario está bloqueado por alguna operación y no se libera. Por ejemplo, si se produce un error desconocido durante la publicación (que es una operación de bloqueo del sistema), el diario puede permanecer en estado de bloqueado por el sistema. En este caso, el controlador de elementos de trabajo de flujo de trabajo generará un error mientras bloquea la validación.

### <a name="issue-resolution"></a>Solución del problema

Inicie sesión en la instancia de SQL Server para Supply Chain Management y compruebe si **InventJournalTable.SystemBlocked** se establece en *1*. Si es así, asegúrese de que el diario no esté en estado bloqueado y luego restablezca **InventJournalTable.SystemBlocked** en *0*.

## <a name="my-inventory-journal-workflow-is-never-completed-and-the-journal-cant-be-edited-or-posted"></a>El flujo de trabajo de mi diario de inventario nunca se completa y el diario no se puede editar ni publicar.

### <a name="issue-description"></a>Descripción del problema

Después de enviar un flujo de trabajo de aprobación de diario, el procesamiento del flujo de trabajo deja de responder y no puede editar ni procesar sus diarios.

### <a name="issue-resolution"></a>Solución del problema

Hay varias razones por las que es posible que no se complete el procesamiento del flujo de trabajo. Compruebe los siguientes problemas:

- Vaya a **Gestión de inventarios &gt; Configuración &gt; Flujos de trabajo de gestión de inventario**, y revise la configuración del flujo de trabajo afectado. Para obtener más información, consulte [Flujos de trabajo de aprobación de diario de inventario](inventory-journal-workflow.md).
- Es posible que el flujo de trabajo encuentre una excepción o un error. Revise el historial de elementos de trabajo del flujo de trabajo afectado para ver si incluye un error de aplicación que finaliza el flujo de trabajo.
- El diario de inventario se puede actualizar o editar solo si está aprobado. Si la recuperación está activa, puede intentar recuperar el diario. La ejecución del trabajo por lotes del flujo de trabajo puede suspenderse por varios motivos. Algunas de estas razones pueden deberse al problema del marco del flujo de trabajo.

## <a name="inventory-journal-workflow-conditions-apply-only-at-the-journal-level-not-at-the-line-level"></a>Las condiciones del flujo de trabajo del diario de inventario solo se aplican a nivel de diario, no a nivel de línea

### <a name="issue-description"></a>Descripción del problema

Puede experimentar este problema si, por ejemplo, intenta configurar una condición de flujo de trabajo de diario de inventario en el importe del coste. Configura la condición para que el paso 1 se ejecute únicamente cuando el importe del coste sea menor que 100. A continuación, configura otra condición para que el paso 2 se ejecute únicamente cuando el importe del coste sea mayor o igual que 100. Luego, cuando se ejecuta el flujo de trabajo, el historial de flujo de trabajo muestra solo una línea y la primera condición siempre se evalúa como *verdadero*, independientemente del valor que se envíe.

### <a name="issue-workaround"></a>Solución del problema

En la versión actual, las condiciones del flujo de trabajo de inventario solo se aplican a nivel de diario, no a nivel de línea. Este comportamiento se debe al diseño. Le recomendamos que establezca sus criterios de condiciones solo en los atributos de nivel de diario.

## <a name="the-filter-pane-on-the-on-hand-list-page-doesnt-filter-results-as-i-expect"></a>El panel de filtro de la página Lista disponible no filtra los resultados como esperaba.

### <a name="issue-description"></a>Descripción del problema

Los filtros del panel de filtro de la página **Lista disponible** no filtra los resultados como se espera.

### <a name="issue-resolution"></a>Solución del problema

Este comportamiento se debe al diseño.

La página  **Lista disponible** se obtiene de una tabla detallada de inventario disponible que incluye todas las dimensiones disponibles. Sin embargo, la lista en esta página es un resumen. Por lo tanto, podría combinar filas de la tabla de origen agregando valores de acuerdo con las dimensiones que se muestran.

Los filtros que se configuran en el panel de filtro se aplican a la tabla de origen, no a la lista agregada. Este comportamiento a veces puede conllevar resultados inesperados, como se muestra en [estos ejemplos](inventory-on-hand-list.md#examples).

Sin embargo, los  [filtros que se proporcionan en la cuadrícula](inventory-on-hand-list.md#grid-filters) *sí* se aplican a la lista agregada. Estos filtros incluyen tanto el filtro rápido en la parte superior de la cuadrícula como el filtro para cada encabezado de columna.

## <a name="the-unit-and-unit-quantity-arent-working-correctly-in-the-inventory-journal"></a>La unidad y la cantidad de unidades no funcionan correctamente en el diario de inventario.

### <a name="issue-description"></a>Descripción del problema

Puede encontrar uno o ambos de los siguientes problemas cuando trabaja con unidades y cantidades en un diario de inventario:

- No ve unidades o cantidades de unidades en el diario de inventario mientras se configura una unidad de conversión para el producto liberado y no puede cambiar la unidad en el diario de inventario.
- Ve los campos **Cantidad** y **Unidad** en el diario de inventario, pero no ve el campo **Cantidad de unidades**. Si cambia la unidad, introduce una cantidad y registra el diario, el diario sigue mostrando la unidad de medida original para esa cantidad.

### <a name="issue-resolution"></a>Solución del problema

Para arreglar este problema, siga estos pasos.

1. En el espacio de trabajo **Administración de características**, asegúrese de que la característica *Uso de unidad de medida y cantidad de unidad en diarios de inventario* está activada. Esta característica agrega los campos **Unidad** y **Cantidad de unidades** al diario.
1. Una vez activada la característica, use los campos **Cantidad**, **Cantidad de unidades** y **Unidad** de la siguiente manera:

    - **Cantidad**: especifique la cantidad utilizando la unidad predeterminada que se define para el producto liberado. Sin embargo, la unidad predeterminada en sí no se muestra aquí. Si se configura una conversión entre la unidad predeterminada y la unidad seleccionada en el campo **Unidad**, el campo **Cantidad** se actualiza automáticamente, según las selecciones de los campos **Cantidad de unidades** y **Unidad**.
    - **Cantidad de unidades**: especifique la cantidad empleando la unidad de medida seleccionada en el campo **Unidad**.
    - **Unidad**: seleccione la unidad para aplicar al valor en el campo **Cantidad de unidades**.

## <a name="i-receive-the-following-error-message-maximum-number-of-decimals-for-the-stock-keeping-unit-is-0"></a>Recibo el siguiente mensaje de error: "El número máximo de decimales para la referencia de almacén es 0".

### <a name="issue-description"></a>Descripción del problema

Al registrar una transacción de inventario o una reserva de inventario, recibe el siguiente mensaje de error: "El número máximo de decimales para la referencia de almacén es 0".

Este problema se produce cuando la cantidad de la transacción de inventario se especifica como un valor decimal que está por debajo del nivel de precisión que admite el campo. Por ejemplo, se ha especificado una cantidad de *0,5* para una transacción de inventario, pero solo se admiten cantidades de enteros. Por lo tanto, el valor debe ser *1* en lugar de *0,5*.

### <a name="issue-resolution"></a>Solución del problema

1. Ejecute el siguiente script en su instancia de SQL Server para redondear cantidades en las transacciones de inventario. Este script corregirá valores en la tabla **inventTrans**.

    ```sql
    update it set it.QTY = round(it.qty, decimalPrecisionValue) from inventtrans it where it.DATAAREAID='XXXX' and it.PARTITION=XXXXXX and it.qty <> round(it.qty, decimalPrecisionValue) and exists (select 'x' from INVENTTABLEMODULE a, unitofmeasure b where  a.unitid =b.SYMBOL and a.partition=it.partition and a.PARTITION=b.PARTITION and  MODULETYPE =0 and  b.DECIMALPRECISION=decimalPrecisionValue and a.DATAAREAID='XXXX' and a.ITEMID =it.ITEMID and it.DATAAREAID=a.DATAAREAID)
    ```

1. Ejecute una comprobación de coherencia disponible donde la opción **arreglar error** está activada. Esta comprobación corregirá valores en la tabla **inventSum**.

> [!IMPORTANT]
> Recomendamos encarecidamente que edite cuidadosamente el script según sea necesario para su entorno, lo pruebe en un entorno de prueba y luego compruebe los datos resultantes antes de ejecutar el script en un entorno de producción.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]