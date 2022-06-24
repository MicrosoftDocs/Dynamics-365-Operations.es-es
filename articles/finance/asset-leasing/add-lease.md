---
title: Agregar o copiar arrendamientos (Vista previa)
description: Este artículo describe cómo crear un nuevo arrendamiento introduciendo información para él en Arrendamiento de activos o copiando información de un arrendamiento existente.
author: moaamer
ms.date: 01/11/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: twheeloc
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2020-10-28
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: 798ab3ece45ee6f21694a364cfb7a4ff14a9c8aa
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/03/2022
ms.locfileid: "8880943"
---
# <a name="add-or-copy-leases-preview"></a>Agregar o copiar arrendamientos (Vista previa)

[!include [banner](../includes/banner.md)]

Este artículo explica cómo crear un arrendamiento desde cero en Arrendamiento de activos y también cómo crear un arrendamiento copiando un arrendamiento existente. El proceso para crear un arrendamiento desde cero implica introducir información para el nuevo arrendamiento y luego crear una programación de arrendamiento. Después de configurar al menos un arrendamiento, es posible que le resulte más fácil copiar la información de un arrendamiento existente y luego editar esa información según sea necesario para crear un nuevo contrato de arrendamiento.

## <a name="create-a-lease"></a>Crear un arrendamiento

Siga estos pasos para crear un arrendamiento en Arrendamiento de activos.

1. En la página **Resumen de arrendamientos**, en el panel Acciones, seleccione **Nuevo**.
2. Introduzca la información del arrendameinto. Los campos obligatorios tienen los bordes rojos.

La fecha de inicio del pago por arrendamiento no puede ser anterior a la fecha de inicio del arrendamiento. Si introduce una fecha de inicio para el pago por arrendamiento que sea anterior a la fecha de inicio del arrendamiento, recibirá un mensaje de error.

Por defecto, la opción **Desglose del importe del pago** en el ficha desplegable **General** de la página **Detalles del arrendamiento** está configurada para **No** si la opción **Permitir desglose de pagos** en la página **Parámetros de arrendamiento de activos** está configurada en **Sí**. 

Si la opción **Desglose del importe del pago** está configurada en **Sí**, el campo **Importe del pago** en la ficha desplegable **Líneas de multivencimientos** está bloqueado. Se fijará en el total de los importes de pago que se introduzcan posteriormente en el catálogo **Desglose del importe del pago**.

Seleccione **Desglose del importe del pago** para abrir una página donde puede agregar los tipos de pago detallados. El botón **Agregar totales al importe del pago** moverá los totales al campo **Importe del pago**.

> [!NOTE]
> Si agrega un importe de pago detallado y luego selecciona la tecla **Esc**, los importes introducidos no se añadirán al campo **Importe del pago** en la ficha desplegable **Líneas de multivencimientos**. En su lugar, se almacenarán en el cuadro de diálogo **Desglose del importe del pago**. Si desea que el cuadro de diálogo muestre el importe total, seleccione la columna **Importe**, seleccione y mantenga presionado (o haga clic con el botón derecho) y luego seleccione **Totalizar esta columnatotal**. 

El botón **Copiar línea** copiará el desglose de pago detallado.

## <a name="create-a-lease-schedule"></a>Crear una programación de arrendamiento

Una vez que haya terminado de introducir la información para el arrendamiento, siga estos pasos para crear una programación de arrendamiento.

> [!NOTE]
> Las dimensiones financieras pueden cambiar en función de las dimensiones financieras personalizadas.

1. Seleccione **Crear programaciones** para generar los libros de arrendamiento. Los libros de arrendamiento incluyen los programas de pago, amortización, depreciación y gastos.
2. Para acceder a los libros de arrendamiento y ver las programaciones recién creadas, seleccione la pestaña **Libros**.

    La página **Detalles del libro** muestra cómo se contabiliza el arrendamiento mediante los libros que le han sido asignados. Desde aquí, puede ver las programaciones de arrendamiento.

    La programación de pagos contiene las entradas de la pestaña **Líneas de programación de pagos** en la página **Agregar arrendamiento**. Sigue pudiendo cambiar cada importe del pago y el pago variable. El pasivo por arrendamiento se calcula en base a la programación de pagos modificada.

    > [!NOTE]
    > La fecha de inicio del pago del arrendamiento debe ser la misma o una fecha posterior a la fecha de inicio del arrendamiento. Recibirá un mensaje de error si la fecha de inicio para el pago es anterior a la fecha de inicio del arrendamiento. 

4. Una vez que haya terminado de revisar la programación de pagos, seleccione **Confirmar programación**. Una vez confirmada la programación, el arrendamiento ya no está disponible para su edición.

    > [!NOTE]
    > El sistema calcula automáticamente el plazo del arrendamiento a partir de las líneas de programación de pagos en la página **Agregar arrendamiento**.
    >
    > Para calcular el plazo del arrendamiento en meses, el sistema encuentra la diferencia entre la fecha de inicio y la fecha de finalización para una línea de programación de pagos específica. Luego pasa a la siguiente línea de programación de pagos y vuelve a encontrar la diferencia. Finalmente, el sistema suma todos los importes para determinar el plazo del arrendamiento en meses.

5. Para ver los gastos por intereses del período calculados, abra la página **Programación de amortización de pasivos**. Para ver la depreciación lineal calculada, abra la página **Programa de depreciación de activos**.
6. Una vez que haya terminado de revisar la cantidad calculada, puede crear el movimiento de diario de reconocimiento inicial en la página **Reconocimiento inicial**. Recibe un mensaje que indica que se ha creado el diario.

    > [!NOTE]
    > El movimiento de diario no se registra en el Libro mayor hasta que lo registre manualmente.

7. Para revisar la entrada de reconocimiento inicial propuesta antes de publicarla, seleccione **Diario de arrendamiento de activos**.

    > [!NOTE]
    > El diario de arrendamiento de activos no se puede crear manualmente. Se crea automáticamente cuando se crean las programaciones de arrendamiento.

8. Cuando haya terminado de revisar la entrada del diario de reconocimiento inicial y esté listo para publicarlo, seleccione **Publicar** para reconocer el activo por derecho de uso (ROU) y el pasivo por arrendamiento en el libro mayor.

## <a name="copy-a-lease"></a>Copiar arrendamiento

El arrendamiento de activos le permite copiar los detalles de un arrendamiento para crear un nuevo arrendamiento que tenga la misma información. A continuación, puede cambiar los campos de arrendamiento antes de crear las programaciones para el arrendamiento copiado.

1. En la página **Resumen de arrendamiento**, seleccione el arrendamiento a copiar y, a continuación, en el Panel de acciones, seleccione **Copiar arrendamiento**.

    > [!NOTE]
    > Si el parámetro **Manual** está desactivado para la secuencia numérica de los id. de arrendamiento, el siguiente número de la secuencia se genera automáticamente como id. de arrendamiento del arrendamiento copiado. Si el parámetro **Manual** está activado, recibe un mensaje que le solicita introducir el id. de arrendamiento antes de proceder a copiar el arrendamiento.

2. Seleccione **Copiar**. Los detalles del arrendamiento del arrendamiento seleccionado se copian a un nuevo arrendamiento. Luego, puede editar los detalles del nuevo contrato de arrendamiento antes de guardarlo y crear las programaciones de arrendamiento.

## <a name="asset-leasing-journal"></a>Diario de arrendamientos de activos

Todos los movimientos de diario que se crean en Arrendamiento de activos se incluyen en el diario de Arrendamiento de activos. En la página **Diario de arrendamiento de activos** (**Arrendamiento de activos \> Entradas de diario \> Diario de arrendamiento de activos**), puede filtrar por estado de publicación, ver entradas de diario específicas y los comprobantes, y registrar entradas de diario no publicadas.

> [!NOTE]
> El diario de arrendamiento de activos no se puede crear manualmente. Se crea automáticamente cuando se crean las programaciones de arrendamiento.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
