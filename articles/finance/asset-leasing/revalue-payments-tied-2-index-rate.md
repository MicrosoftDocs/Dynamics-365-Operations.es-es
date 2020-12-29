---
title: Revalorizar los pagos por arrendamiento vinculados a un tipo indexado
description: Este tema describe el ajuste que se realiza para arrendar el pasivo para un activo por derecho de uso (ROU) cuando los pagos de arrendamiento variables cambian debido a un cambio en el tipo indexado.
author: moaamer
manager: Ann Beebe
ms.date: 10/28/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations, Retail
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2020-10-28
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: 83684afbd5e11b890a59bc1469ddefffd1777c4e
ms.sourcegitcommit: aeee39c01d3f93a6dfcf2013965fa975a740596a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/28/2020
ms.locfileid: "4447796"
---
# <a name="revalue-lease-payments-that-are-linked-to-an-index-rate"></a>Revalorizar los pagos por arrendamiento vinculados a un tipo indexado

[!include [banner](../includes/banner.md)]

Este tema describe el ajuste que se realiza para el pasivo por arrendamiento para un activo por derecho de uso (ROU) cuando los pagos de arrendamiento variables cambian debido a un cambio en el tipo indexado. El pasivo por arrendamiento y los activos por derecho de uso se ajustarán para los nuevos importes de pago. Según el Tema 842 de Codificación de Normas de Contabilidad (ASC 842), que es el estándar en los Principios de Contabilidad Generalmente Aceptados en los EE. UU. (US GAAP), solo los pagos variables cambian cuando los pagos aumentan o disminuyen debido a un cambio en el tipo indexado, a menos que existan cambios adicionales en los flujos de efectivo. Estos cambios adicionales pueden incluir un cambio en los términos del arrendamiento relacionados con las tasas de interés. Para obtener más información, consulte la ASC 842-10-55-225 y el párrafo 42 (b) de la Norma Internacional de Información Financiera 16 (IFRS 16).

## <a name="adjust-lease-payments"></a>Ajustar los pagos de arrendamientos

Siga estos pasos para revalorizar los pagos por arrendamiento vinculados a un tipo indexado.

1. Para ejecutar el proceso de revalorización del índice de arrendamiento, vaya a **Arrendamiento de activos \> Periódico \> Revalorización de la tasa de índice**.

    La página **Revalorización de la tasa de índice** aparece y muestra todos los procesos anteriores de revalorización del índice de arrendamiento que se han ejecutado. La información de esta página incluye el id. de proceso que se generó a partir de la configuración de la secuencia numérica, la entidad jurídica el número de libros de arrendamiento que se ajustaron, el ajuste de pasivo total para los arrendamientos IFRS 16 y los pagos variables totales que se ajustaron para arrendamientos ASC 842.

2. Para ejecutar la revalorización, en el panel de acciones, seleccione **Revalorización del índice de arrendamiento**.

    Aparece el cuadro de diálogo **Parámetros de revalorización del índice**. Aquí, puede filtrar y seleccionar qué arrendamientos, grupos de arrendamientos u otros criterios deben usarse cuando seleccione los arrendamientos a revalorizar. Además, en la pestaña **Ejecutar en segundo plano**, puede configurar el proceso de revalorización del índice para que se ejecute en un lote.

4. Seleccione los filtros para seleccionar los arrendamientos que deben incluirse en el procesamiento en segundo plano y luego seleccione **Aceptar**.

    Aparece el cuadro de diálogo **Vista previa de la revalorización del tipo indexado**, que muestra los arrendamientos que se revalorizarán. También muestra los ajustes de activos y pasivos o los ajustes de pagos variables.
    
5. Para evitar que los arrendamientos se revaloricen, seleccione los arrendamientos que **deberían** revalorizarse. Si no selecciona ningún arrendamiento, todos los arrendamientos se revalorizarán. Cuando haya terminado, seleccione **Aceptar** para revalorizar los pagos por arrendamiento.
6. Para ver las transacciones que se crearon para un proceso de revalorización de índice específico, seleccione el id. de proceso y luego seleccione **Transacciones**.

    Aparece un cuadro de diálogo que muestra los detalles de las transacciones que se crearon durante el procesamiento.

> [!NOTE]
> Solo se pueden revalorizar los arrendamientos que tienen una fecha de revalorización anterior o igual a la fecha del sistema. El sistema ignora automáticamente todos los arrendamientos que tienen una fecha de revalorización posterior a la fecha del sistema.

## <a name="asc-842-leases--index-revaluation"></a>Arrendamientos ASC 842: revalorización del índice

Para ver los efectos del proceso de revalorización del arrendamiento en los arrendamientos ASC 842, abra la programación de pagos de un arrendamiento. La página muestra solo los pagos variables que se han realizado en o después de que se modificó la fecha de revalorización debido a la revalorización del índice. Las programaciones de amortización y depreciación permanecen sin cambios. Cuando crea una factura que tiene un pago variable, el pago variable se carga en la cuenta contable de pago variable. Además, el importe del pago variable se agrega a la entrada de crédito que se registra directamente en el proveedor o se registra en la cuenta de pagarés, según la configuración del libro de arrendamiento.

Las líneas de programación de pagos de la página de detalles del arrendamiento se actualizan automáticamente con una nueva línea que indica el nuevo tipo indexado. Además, una columna muestra si la línea se creó manualmente o mediante el proceso de revalorización del índice.

## <a name="ifrs-16-leases--index-revaluation"></a>Arrendamientos IFRS 16: revalorización del índice

Para ver los efectos del proceso de revalorización del arrendamiento en los arrendamientos IFRS 16, abra los detalles del arrendamiento de un arrendamiento ajustado. Los campos **Plazo del arrendamiento** y **Vida útil del activo** se han actualizado para reflejar el paso del tiempo desde la fecha de inicio o la fecha de modificación hasta la fecha de revalorización. Además, las líneas de la programación de pagos se han actualizado para reflejar los nuevos pagos del arrendamiento, el nuevo tipo indexado y cómo se creó la línea.

Puede ver el programa de pago recién generado que comienza en la fecha de revalorización y mostrar el importe total de pago actualizado. También se han creado una nueva programación de amortización del pasivo por arrendamiento y una programación de depreciación de activos para reflejar la programación de pagos ajustada.

El movimiento de diario ha registrado automáticamente el movimiento de diario de ajuste en la cuenta para el cambio en los pagos por arrendamiento relacionados con la revalorización del índice.
