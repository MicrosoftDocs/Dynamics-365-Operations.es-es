---
title: Ajustar arrendamientos
description: El tema explica cómo ajustar un arrendamiento. Es posible que se requiera un ajuste si se modifican los términos del arrendamiento, se prorroga el arrendamiento o cambian otras circunstancias.
author: moaamer
ms.date: 10/28/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2020-10-28
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: 1016b69fd59bbe90924996f5c931cb5d0f779253de66f5f3821a8c3001d3313b
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2021
ms.locfileid: "6729663"
---
# <a name="adjust-leases"></a>Ajustar arrendamientos

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

El tema explica cómo ajustar un arrendamiento. Es posible que se requiera un ajuste si se modifican los términos del arrendamiento, se prorroga el arrendamiento o cambian otras circunstancias. El arrendamiento de activos cumple con la orientación que proporcionan el Tema 842 de la Codificación de Normas de Contabilidad (ASC 842) y la Norma Internacional de Información Financiera 16 (NIIF 16) sobre las modificaciones del arrendamiento. ASC 842-20-15-1 define una modificación de arrendamiento como cualquier cambio en los términos y condiciones de un contrato que provoque un cambio en el ámbito o la consideración de un arrendamiento. El párrafo 39 de la IFRS 16 establece que un arrendatario debe volver a evaluar el pasivo por arrendamiento de manera que refleje los cambios en los pagos por arrendamiento.

Para las organizaciones que se adhieren a ASC 842 o IFRS 16, un arrendamiento se vuelve a medir para reflejar un cambio en el valor presente de los pagos mínimos futuros del arrendamiento (PVFMLP). Si el PVFMLP aumenta, el movimiento de diario que se crea será un débito en la cuenta del activo por derecho de uso (ROU) y un crédito en la cuenta de pasivo por arrendamiento por la diferencia entre el nuevo PVFMLP y el PVFMLP anterior. Si el PVFMLP disminuye, el movimiento del diario será un débito en la cuenta del pasivo por arrendamiento y un crédito en la cuenta del activo por derecho de uso por la diferencia.

Si el ajuste reduce el activo por derecho de uso más allá de 0 (cero), el resto se acreditará a la ganancia en la cuenta de registro de modificación de arrendamiento que se especifica en la página **Cuentas de movimientos de arrendamiento**. El sistema contabiliza estas transacciones y otros asientos de ajuste, como cambios de clasificación, costos directos iniciales, incentivos de arrendamiento, pagos anticipados y costes de desmantelamiento que surgen de las modificaciones del arrendamiento.

Para obtener orientación específica sobre las transacciones de ajuste de arrendamiento, le recomendamos que consulte IFRS 16 y ASC 842.

## <a name="lease-adjustment-wizard"></a>Asistente para ajustes de arrendamientos

Para ajustar un arrendamiento, complete los siguientes pasos. Los datos modificados actualizarán las programaciones de arrendamiento después de registrar desde el asistente **Ajuste de arrendamiento**. Puede guardar su trabajo y cerrar el asistente en cualquier momento, y luego volver más tarde para reanudar su trabajo.

Para abrir el asistente **Ajuste de arrendamiento** desde el resumen de arrendamiento, siga estos pasos.

1. Vaya a **Arrendamiento de activos \> Arrendamientos \> Resumen de arrendamiento**. 
2. Seleccione el arrendamiento a ajustar y luego seleccione **Asistente de ajuste**.
3. Siga las indicaciones del asistente para introducir los cambios requeridos.

Para abrir el asistente **Ajuste de arrendamiento** desde la página **Ajustes de arrendamiento**, para un ajuste que ya está en progreso, siga estos pasos.

1.  Vaya a **Alquiler \> Arrendamientos \> Ajustes de arrendamientos**.
2.  Seleccione un arrendamiento que tenga un estado de ajuste **En progreso** y luego seleccione **Asistente de ajuste**.
3.  En los campos **Fecha de inicio de la modificación** y **Fecha contable**, introduzca las fechas apropiadas.
4.  Seleccione **Siguiente**.

    El arrendamiento ahora se agrega a la página **Ajustes de arrendamientos**, donde puede introducir la nueva información al respecto.

    Una vez que se ha ajustado el arrendamiento, se le aplican los campos de consideraciones de derecho de uso. Si no hay costes directos iniciales, incentivos de arrendamiento, pagos anticipados ni costes de desmantelamiento asociados con el arrendamiento modificado, deje en blanco los campos correspondientes. Los importes originales no se aplicarán al contrato de arrendamiento actualizado. 

    Por ejemplo, un arrendador ofrece un incentivo 1000 $ por aceptar una extensión de arrendamiento. En este caso, cuando ajusta el arrendamiento para tener en cuenta la extensión, introduzca **1.000** en el campo **Incentivos de arrendamiento provenientes de ajustes**.

    Las líneas de programación de pagos ahora muestran todos los pagos del mes y los meses posteriores, en el campo **Fecha de inicio de la modificación**. Debido a que las modificaciones son prospectivas, las líneas de programación de pagos no pueden comenzar antes de que comience la modificación. Para ver las líneas de la programación de pagos anteriores a la fecha de inicio de la modificación, vaya a la página **Historial de versiones de arrendamiento**.

8.  Seleccione **Siguiente**.

    La siguiente página muestra detalles clave sobre el ajuste de arrendamiento esperado, como los valores en libros del pasivo por arrendamiento antes de la modificación y el nuevo pasivo por arrendamiento esperado después de la modificación. La página también muestra una vista previa del movimiento de diario para el ajuste de arrendamiento esperado.

9.  Seleccione **Enviar al flujo de trabajo** para enviar el ajuste de arrendamiento al sistema de flujo de trabajo si el flujo de trabajo de ajuste de arrendamiento está activo y el ajuste aún no se ha aprobado. Para más información sobre cómo utilizar el flujo de trabajo de ajuste de arrendamiento, consulte [Utilizar flujos de trabajo de ajuste](use-create-lease-wrkflw.md).

    > [!NOTE]
    > En este punto, el sistema vuelve a calcular las variables de ajuste para verificar que no se hayan contabilizado transacciones contra el arrendamiento desde que se calcularon por primera vez el resumen de ajustes y el movimiento de diario de ajustes. Si algún valor cambia, la cuadrícula de resumen de ajustes se actualiza y puede revisar la información antes de volver a enviar los ajustes de arrendamiento al sistema de flujo de trabajo.

10. Si un flujo de trabajo no está activo o si se ha aprobado el ajuste de arrendamiento, seleccione **Terminar** para procesar los cambios y contabilizar el movimiento de diario de ajuste.

    > [!NOTE] 
    > En este punto, el sistema vuelve a calcular las variables de ajuste para verificar que no se hayan contabilizado transacciones contra el arrendamiento desde que se calcularon por primera vez el resumen de ajustes y el movimiento de diario de ajustes. Si algún valor cambia, se actualiza la cuadrícula de descripción general del ajuste y puede revisar los cambios antes de seleccionar **Terminar**. Si el flujo de trabajo está activo y el ajuste de arrendamiento se ha aprobado, cualquier cambio en la descripción general del ajuste hará que el estado de aprobación vuelva a ser **No presentado**. En este caso, debe volver a enviar el ajuste de arrendamiento al sistema de flujo de trabajo.

    En la página **Ajustes de arrendamiento**, el estado de ajuste ahora está establecido en **Terminado**.

    En la página **Ajustes de arrendamiento**, seguirá pudiendo ver las fichas desplegables **Resumen de ajustes** y **Vista previa de entrada de ajuste**. Los detalles del arrendamiento y la información de fecha se muestran en el historial de versiones de ese arrendamiento.

    Ahora se crea una nueva versión de arrendamiento y un nuevo conjunto de programaciones utilizando la información modificada. 

13. Para ver los nuevos horarios, vaya al contrato de arrendamiento y luego seleccione **Libros**.
14. Para ver el calendario de pagos recién generado, seleccione **Calendario de pagos**.
15. Para ver el nuevo programa de amortización del pasivo por arrendamiento que se genera a partir de la nueva información, cierre la página **Programación de pago** y abra la página **Programación de amortización de pasivos**.
16. Para ver la programación de depreciación de activos recién generada, abra la página **Programación de depreciación de activos** en la página **Detalles del libro**.
17. Para ver el movimiento del diario de ajuste, seleccione **Diarios \> Diario de arrendamiento de activos**.

## <a name="cancel-a-lease-adjustment"></a>Cancelar un ajuste de arrendamiento

Para eliminar un ajuste de arrendamiento que está en curso, siga estos pasos.

1.  Vaya a **Alquiler \> Arrendamientos \> Ajustes de arrendamientos**.
2.  Seleccione ese ajuste de arrendamiento en curso para cancelar.
3.  Seleccione **Cancelar ajuste**. 
4.  Seleccione **Aceptar**.

    > [!NOTE] 
    > Si selecciona **Cancelar** en el asistente **Ajuste de arrendamiento**, se revierte el cambio más reciente que se completó en el asistente, pero no se elimina un ajuste que está en curso.

## <a name="use-the-lease-adjustment-workflow"></a>Utilizar el flujo de trabajo de ajuste de arrendamiento

Esta sección explica cómo utilizar el flujo de trabajo de ajuste de arrendamiento. El flujo de trabajo de ajuste de arrendamiento le ayuda a administrar los ajustes de arrendamiento de manera coherente, al proporcionar un conjunto de pasos de aprobación y asignarlos a usuarios específicos que aprueban un ajuste de arrendamiento antes de que sea definitivo. Una vez aprobado el ajuste de arrendamiento en el flujo de trabajo, puede utilizar el asistente **Ajuste de arrendamiento** para completar el ajuste del arrendamiento.

1.  Para enviar un ajuste de arrendamiento para su aprobación, vaya a **Alquiler \> Arrendamientos \> Ajustes de arrendamiento**.
2.  Seleccione el id. del ajuste de arrendamiento y luego seleccione **Asistente de ajuste**.
3.  En la última página del asistente, seleccione **Enviar para aprobación**.
4.  Introduzca un comentario sobre el ajuste y luego seleccione **Aceptar**.

    El estado del flujo de trabajo cambia a **Aprobación pendiente** y todos los campos del asistente están bloqueados para su edición.

5.  Para aprobar un ajuste de arrendamiento, vaya a **Alquiler \> Arrendamientos \> Ajustes de arrendamientos**.
6.  Seleccione el id. de arrendamiento del ajuste de arrendamiento y revise las fichas desplegables **Resumen de ajustes** y **Vista previa de entrada de ajuste**.
7.  Seleccione **Flujo de trabajo \> Aprobado**.

    En la página **Ajustes de arrendamiento**, el estado del flujo de trabajo ahora está establecido en **Aprobado**. En este punto, el ajuste de arrendamiento está listo para contabilizarse a través del movimiento de diario de ajuste.

8.  Para continuar procesando el ajuste de arrendamiento y contabilizar la entrada de ajuste, vaya a **Arrendamiento \> Arrendamientos \> Ajustes de arrendamiento**.
9.  Seleccione el id. del ajuste de arrendamiento y luego seleccione **Asistente de ajuste**.
10. Seleccione **Siguiente** hasta llegar a la última página del asistente y luego seleccione **Terminar**.

El sistema vuelve a calcular los valores contables del arrendamiento para garantizar que las variables de ajuste que se aprobaron estén vigentes. Si hay algún cambio, el estado de aprobación se vuelve a establecer en **Borrador** y deberá volver a enviar el ajuste de arrendamiento al sistema de flujo de trabajo.

## <a name="view-lease-versions"></a>Ver versiones de arrendamiento

Si se ha ajustado un arrendamiento, puede ver las diferentes versiones de este. También puede ver las programaciones históricas y los detalles de los arrendamientos anteriores.

1. En la página **Resumen de arrendamiento**, seleccione el arrendamiento a copiar y, a continuación, en el Panel de acciones, seleccione **Historial de versiones del arrendamiento**.

    Si el arrendamiento seleccionado se ha ajustado, la página **Historial de versiones de arrendamiento** muestra las diferentes versiones del mismo. El contrato de arrendamiento original se etiqueta como **1** y las versiones posteriores tienen un orden numérico ascendente.

    Para una versión de arrendamiento seleccionada, puede ver las dimensiones financieras, los detalles del contrato, la ubicación y las líneas de programación de pagos.

2. Para ver programaciones históricas, abra el arrendamiento modificado desde la página **Resumen de arrendamiento**, seleccione el libro deseado y, a continuación, en el Panel de acciones, seleccione **Historial de versiones del libro**.
3. En la página **Versión del libro**, seleccione una versión y una programación a ver.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]