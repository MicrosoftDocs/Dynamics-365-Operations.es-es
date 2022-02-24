---
title: Agregar o copiar arrendamientos (Vista previa)
description: Este tema describe cómo crear un nuevo arrendamiento introduciendo información para él en Arrendamiento de activos o copiando información de un arrendamiento existente.
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
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2020-10-28
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: abbf04d009a4b347792cd8b317e334da2a4cbbee
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/15/2021
ms.locfileid: "4969612"
---
# <a name="add-or-copy-leases-preview"></a>Agregar o copiar arrendamientos (Vista previa)

[!include [banner](../includes/banner.md)]

Este tema explica cómo crear un arrendamiento desde cero en Arrendamiento de activos y también cómo crear un arrendamiento copiando un arrendamiento existente. El proceso para crear un arrendamiento desde cero implica introducir información para el nuevo arrendamiento y luego crear una programación de arrendamiento. Después de configurar al menos un arrendamiento, es posible que le resulte más fácil copiar la información de un arrendamiento existente y luego editar esa información según sea necesario para crear un nuevo contrato de arrendamiento.

## <a name="create-a-lease"></a>Crear un arrendamiento

Siga estos pasos para crear un arrendamiento en Arrendamiento de activos.

1. En la página **Resumen de arrendamientos**, en el panel Acciones, seleccione **Nuevo**.
2. Introduzca la información del arrendameinto. Los campos obligatorios tienen los bordes rojos.

## <a name="create-a-lease-schedule"></a>Crear una programación de arrendamiento

Una vez que haya terminado de introducir la información para el arrendamiento, siga estos pasos para crear una programación de arrendamiento.

> [!NOTE]
> Las dimensiones financieras pueden cambiar en función de las dimensiones financieras personalizadas.

1. Seleccione **Crear programaciones** para generar los libros de arrendamiento. Los libros de arrendamiento incluyen los programas de pago, amortización, depreciación y gastos.
2. Para acceder a los libros de arrendamiento y ver las programaciones recién creadas, seleccione la pestaña **Libros**.

    La página **Detalles del libro** muestra cómo se contabiliza el arrendamiento mediante los libros que le han sido asignados. Desde aquí, puede ver las programaciones de arrendamiento.

    La programación de pagos contiene las entradas de la pestaña **Líneas de programación de pagos** en la página **Agregar arrendamiento**. Sigue pudiendo cambiar cada importe del pago y el pago variable. El pasivo por arrendamiento se calcula en base a la programación de pagos modificada.

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
