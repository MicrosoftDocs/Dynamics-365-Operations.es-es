---
title: Ajustar arrendamientos
description: El tema explica cómo ajustar un arrendamiento. Es posible que se requiera un ajuste si se modifican los términos del arrendamiento, se prorroga el arrendamiento o cambian otras circunstancias.
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
ms.openlocfilehash: 9d1c6e20e72fb2816c32e71e8921a94724ae5656
ms.sourcegitcommit: aeee39c01d3f93a6dfcf2013965fa975a740596a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/28/2020
ms.locfileid: "4447817"
---
# <a name="adjust-leases"></a>Ajustar arrendamientos

[!include [banner](../includes/banner.md)]

El tema explica cómo ajustar un arrendamiento. Es posible que se requiera un ajuste si se modifican los términos del arrendamiento, se prorroga el arrendamiento o cambian otras circunstancias. El arrendamiento de activos cumple con la orientación que proporcionan el Tema 842 de la Codificación de Normas de Contabilidad (ASC 842) y la Norma Internacional de Información Financiera 16 (NIIF 16) sobre las modificaciones del arrendamiento. ASC 842-20-15-1 define una modificación de arrendamiento como cualquier cambio en los términos y condiciones de un contrato que provoque un cambio en el ámbito o la consideración de un arrendamiento. El párrafo 39 de la IFRS 16 establece que un arrendatario debe volver a evaluar el pasivo por arrendamiento de manera que refleje los cambios en los pagos por arrendamiento.

Para las organizaciones que se adhieren a ASC 842 o IFRS 16, un arrendamiento se vuelve a medir para reflejar un cambio en el valor presente de los pagos mínimos futuros del arrendamiento (PVFMLP). Si el PVFMLP aumenta, el movimiento de diario que se crea será un débito al activo por derecho de uso (ROU) y un crédito al pasivo por arrendamiento por la diferencia entre el nuevo PVFMLP y el PVFMLP anterior. Si el PVFMLP disminuye, el movimiento del diario será un débito al pasivo por arrendamiento y un crédito al activo por derecho de uso por la diferencia.

Si el ajuste reduce el activo por derecho de uso más allá de 0 (cero), el resto se acreditará a la ganancia en la cuenta de registro de modificación de arrendamiento que se especifica en la página **Cuentas de movimientos de arrendamiento**. El sistema contabiliza estas transacciones y otros asientos de ajuste, como cambios de clasificación, costos directos iniciales, incentivos de arrendamiento, pagos anticipados y costes de desmantelamiento que surgen de las modificaciones del arrendamiento.

Para obtener orientación específica sobre las transacciones de ajuste de arrendamiento, le recomendamos que consulte IFRS 16 y ASC 842.

Para ajustar un arrendamiento, siga estos pasos. Los datos modificados actualizarán las programaciones de arrendamiento después de que se ejecute el proceso Crear programación.

1. Vaya a **Arrendamiento de activos \> Arrendamientos \> Resumen de arrendamiento**.
2. En la página **Resumen de arrendamiento**, seleccione el arrendamiento a ajustar y luego seleccione **Ajustar arrendamiento**.
3. En la página **Ajustar arrendamiento**, introduzca la nueva información para el arrendamiento ajustado.

    Note que la página **Ajustar arrendamiento** se parece a la página **Agregar arrendamiento**. Además, igual que la fecha de inicio que especifica cuando agrega un contrato de arrendamiento determina cuándo comienza el nuevo contrato de arrendamiento, el campo **Fecha de modificación** de la página **Ajustar arrendamiento** determina cuándo comienza el arrendamiento modificado. Esta fecha no puede ser posterior a la fecha de inicio en las líneas de programación de pagos.

    > [!NOTE]
    > Los campos **Consideraciones de ROU** se aplican al ajuste del arrendamiento. Si no hay costes directos iniciales, incentivos de arrendamiento, pagos anticipados o costos de desmantelamiento asociados con el arrendamiento modificado, debe dejar estos campos en blanco. Los importes originales no se aplicarán al contrato de arrendamiento actualizado. Cualquier costo adicional en el que se incurra cuando se modifica el arrendamiento debe introducirse en la página **Ajustar arrendamiento**.
    > 
    > Por ejemplo, un arrendador ofrece un incentivo 1000 $ por aceptar una extensión de arrendamiento. En este caso, cuando ajusta el arrendamiento para tener en cuenta la extensión, introduzca **1000** en el campo **Incentivos de arrendamiento**. Si no hay incentivos asociados con el ajuste de arrendamiento, debe borrar cualquier valor que se haya introducido previamente en este campo. La misma lógica se aplica a otras consideraciones de ROU.

    Las líneas de la programación de pagos del arrendamiento ajustado deben crearse de forma prospectiva. Las líneas de programación de pagos que se crean de forma prospectiva no pueden comenzar antes de que entren en vigor las modificaciones del arrendamiento.

    Los siguientes pasos son casi idénticos a los pasos para reconocer inicialmente un arrendamiento.

4. Seleccione **Crear programaciones** para generar la programación de pagos ajustada. Recibe un mensaje que indica que se ha creado la programación de pagos para el arrendamiento.

    > [!IMPORTANT]
    > Antes de seleccionar **Crear programaciones**, asegúrese de que la fecha de modificación y las líneas de programación de pagos sean precisas. También, asegúrese de que todos los costos directos iniciales, incentivos de arrendamiento, pagos anticipados o costos de desmantelamiento correspondan solo a los costes que surgen del ajuste.

5. Para ver la programación de pagos recién creado, seleccione **Libros** y abra la página **Programación de pagos**.
6. En la página **Programación de pagos**, puede editar los importes de pago ajustados antes de confirmar la programación de pagos. Para confirmar la programación, seleccione **Confirmar programación**.

    Cuando se confirma la programación de pagos, se crean los nuevas programaciones de depreciación de activos y pasivos por arrendamiento.

7. Para ver el nuevo programa de amortización del pasivo por arrendamiento que se genera a partir de las nuevas entradas, cierre la página **Programación de pago** y abra la página **Programación de amortización de pasivos**.
8. Para ver la programación de depreciación de activos recién generada, abra la página **Programación de depreciación de activos** en la página **Detalles del libro**.
9. Para generar el movimiento del diario de ajuste, seleccione **Función \> Ajuste de arrendamiento**. Recibe un mensaje que indica que se ha creado el movimiento de diario de ajuste. 
10. Para ver el movimiento del diario, seleccione **Diarios \> Diario de arrendamiento de activos**.
11. Para publicar el movimiento del diario, seleccione la línea y luego seleccione **Registrar**.

## <a name="view-lease-versions"></a>Ver versiones de arrendamiento

Si se ha modificado un arrendamiento, puede ver las diferentes versiones de este. También puede ver las programaciones históricas y los detalles de los arrendamientos anteriores.

1. En la página **Resumen de arrendamiento**, seleccione el arrendamiento a copiar y, a continuación, en el Panel de acciones, seleccione **Historial de versiones del arrendamiento**.

    Si el arrendamiento seleccionado se ha ajustado, la página **Historial de versiones de arrendamiento** muestra las diferentes versiones del mismo. El contrato de arrendamiento original se etiqueta como **1** y las versiones posteriores tienen un orden numérico ascendente.

    Para una versión de arrendamiento seleccionada, puede ver las dimensiones financieras, los detalles del contrato, la ubicación y las líneas de programación de pagos.

2. Para ver programaciones históricas, abra el arrendamiento modificado desde la página **Resumen de arrendamiento**, seleccione el libro deseado y, a continuación, en el Panel de acciones, seleccione **Historial de versiones del libro**.
3. En la página **Versión del libro**, seleccione la versión deseada y la programación deseada a ver.
