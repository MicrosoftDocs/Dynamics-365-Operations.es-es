---
title: Dar de baja los programas de facturación
description: Este tema explica cómo dar de baja los programas de facturación y sus líneas en la facturación de suscripción.
author: JodiChristiansen
ms.date: 11/04/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: twheeloc
ms.custom: 539093
ms.search.region: Global
ms.author: jchrist
ms.search.validFrom: 2021-11-05
ms.dyn365.ops.version: 10.0.24
ms.openlocfilehash: e823ce950d6a4687dc7cda14e06bffdbb4f37f7e
ms.sourcegitcommit: a58dfb892e43921157014f0784bd411f5c40e454
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2022
ms.locfileid: "8690987"
---
# <a name="terminate-billing-schedules"></a>Dar de baja los programas de facturación

[!include [banner](../includes/banner.md)]

Este tema explica cómo dar de baja los programas de facturación y sus líneas en la facturación de suscripción. Al dar de baja un programa de facturación, debe tener el estado **Activo**. No puede tener un estado de **En espera**. Del mismo modo, al dar de baja una línea de programa de facturación, debe tener el estado **Activo**. La sección de encabezado del programa de facturación no se ve afectada cuando da de baja una línea del programa de facturación.

Para dar de baja un programa de facturación o una línea de programa de facturación, vaya a uno de los siguientes lugares:

- La página de listas **Programas de facturación (todas/activas)**
- Un programa de facturación específico en la página **Todos los programas de facturación**
- Una línea de programa de facturación específica en la página **Todos los programas de facturación**

> [!NOTE]
> Si desea dar de baja varios programas de facturación al mismo tiempo, utilice la página **Procesamiento de baja masiva**.

## <a name="terminate-a-billing-schedule-or-line"></a>Dar de baja un programa de facturación o una línea

Para dar de baja un programa de facturación o una línea de programa de facturación, siga estos pasos.

1. Seleccione un programa de facturación o una línea de programa de facturación y, a continuación, seleccione **Dar de baja**. 
2. Selecciona la **Fecha de baja**, el **Tipo de baja** y el **Código de motivo**.
3. Seleccione el campo **Opción de crédito** a **Emitir crédito**.
4. Seleccione **Dar de baja**.

El estado del programa de facturación cambia según el tipo de baja que haya seleccionado. Si ha seleccionado **Factura restante** como tipo de baja, el estado de todas las líneas en el programa de facturación es **Última facturación**. El estado del programa de facturación permanece **Activo** hasta que se procese la última factura. Una vez procesada la última factura, el estado se actualiza a **Dado de baja**. Si ha seleccionado **Ajustar programa** como tipo de baja, el estado del programa de facturación se actualizará inmediatamente a **Dado de baja**.

## <a name="terminate-a-billing-schedule-or-line-and-apply-a-refund"></a>Dar de baja un programa de facturación o línea y aplicar una devolución

Para dar de baja un programa de facturación o una línea de programa de facturación y aplicar una devolución, siga estos pasos.

1. Seleccione un programa de facturación o una línea de programa de facturación y, a continuación, seleccione **Dar de baja**.
2. Selecciona la **Fecha de baja**, el **Tipo de baja**, el **Código de motivo** y la **Opción de crédito**.
3. Seleccione **Dar de baja con devolución**. Aparecerá la página **Procesamiento de baja masiva** y se filtrará para que muestre el programa de facturación.
4. Seleccione **Ver versión preliminar** para ver las líneas de programa de facturación y, a continuación, seleccione **Procesar**.

Después de procesar el crédito, abra la página **Ver detalle de facturación** para revisar el crédito que se aplicó al programa de facturación. Si el importe del crédito es mayor que 0 (cero), todas las líneas futuras no facturadas se eliminan y se reemplazan con líneas de detalles de facturación que muestran los importes negativos del crédito que se aplicó al programa de facturación.

### <a name="view-example"></a>Ver ejemplo

Un programa de facturación tiene la siguiente información:

- La fecha de inicio es el 1 de enero de 2020.
- La fecha de finalización es el 31 de diciembre de 2020.
- El importe del período de facturación es de 100,00 por mes.
- Se han creado facturas para períodos de facturación de enero a julio.
- La fecha de baja del contrato es el 15 de junio de 2020.

Cuando se procesa el ajuste de crédito, todos los períodos de facturación futuros (de agosto a diciembre) se eliminan de la página **Ver detalle de facturación**. Se agrega una línea de ajuste de crédito después del período de facturación de julio:

- Del 16 de junio al 31 de julio, con un importe de crédito de 150,00

Si se utiliza la función de ingresos no facturados, la página **Auditoría de movimientos del diario de ingresos sin facturar** se actualiza con la entrada de la baja.

## <a name="terminate-a-billing-schedule-or-line-without-applying-a-credit"></a>Dar de baja un programa de facturación o línea sin aplicar un crédito.

Para dar de baja un programa de facturación o una línea de programa de facturación sin aplicar un crédito, siga estos pasos.

1. Seleccione un programa de facturación o una línea de programa de facturación y, a continuación, seleccione **Dar de baja**.
2. Selecciona el campo **Fecha de baja**.
3. Ponga el campo **Tipo de baja** en **Sin ajuste**. El campo **Opción de crédito** se pone automáticamente en **Sin crédito**.
3. Establezca el campo **Código de motivo**.
4. En el campo **Notas sobre la baja**, especifique las notas adicionales necesarias.
5. Seleccione **Dar de baja**. 

Cuando se procesa la baja, se eliminan todas las líneas de detalles de facturación posteriores a la fecha de rescisión. (Estas líneas incluyen la línea que contiene la fecha de baja). No se pueden crear facturas para las líneas terminadas. Si se elimina la baja, todas las líneas que se hayan dado de baja se vuelven a agregar a la página **Ver detalles de facturación** y están de nuevo disponible para la facturación.

## <a name="fields"></a>Campos

La página **Ver detalles de facturación** contiene los siguientes campos.

| Campo | Description |
|-------|-------------| 
| Fecha de finalización | Seleccione la fecha en la que quiere dar de baja un programa de facturación o una línea de programa de facturación. |
| Tipo de finalización | <p>Seleccione el tipo de baja:</p><ul><li>**Ajustar programa** – Cortar los periodos de facturación por la línea en la fecha de baja y cambiar el estado de la línea a **Última facturación**. Si existe un programa de aplazamiento para el artículo de línea, se ajusta revirtiendo la cantidad que ya no debe reconocerse. Si la fecha de inicio de facturación es posterior a la fecha de baja, se eliminan los períodos de facturación restantes.</li><li>**Factura restante** – Agregue cualquier importe restante para el período de facturación al período de baja y cambie el estado de la línea a **Última facturación**. Si existe una programación de aplazamiento para el elemento de línea, se actualiza la fecha de finalización del aplazamiento. Si la fecha de inicio de facturación es posterior a la fecha de baja, el monto total de todos los períodos de facturación restantes se agrega al período de facturación y los períodos de facturación restantes se eliminan.</li><li>**Sin ajuste** – Dar de baja los periodos de facturación de la línea en la fecha de baja especificada. No se realizan ajustes. Cuando se selecciona este tipo de baja, el campo **Opción de crédito** se establece en **Sin crédito**, y el campo **Prorrateo diario** se establece en **No**. Ambos campos se vuelven de solo lectura y no se pueden cambiar.</li></ul> |
| Opción de crédito | <p>Seleccione cómo se aplica el crédito cuando da de baja una línea de programa de facturación:</p><ul><li>**Ajuste de crédito** – Cree un ajuste de crédito para un programa de facturación al dar de baja una línea. El ajuste de crédito aparece en un período de facturación futuro para el programa de facturación. El ajuste también ajusta automáticamente el monto de la factura para el próximo período de facturación hasta que el crédito haya terminado de aplicarse al programa de facturación.</li><li>**Emitir crédito** – Cree una nota de crédito al dar de baja un programa de facturación o una línea de programa de facturación.</li><li>**Sin crédito** – No cree un ajuste de crédito o una nota de crédito al dar de baja un programa de facturación o una línea de programa de facturación. Esta opción está disponible solo cuando utiliza una baja del tipo **Sin ajuste** para dar de baja un programa de facturación.</li></ul><p>La opción predeterminada está en la página **Parámetros de facturación de contratos recurrentes**.</p> |
| Código de motivo | Seleccione el código de motivo para la baja. |
| Descripción del motivo | La descripción del código de motivo. |
| Notas de finalización | Escriba notas acerca de la baja. |

<!--## Additional information-->
