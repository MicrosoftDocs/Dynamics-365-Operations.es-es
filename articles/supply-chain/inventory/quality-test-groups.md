---
title: Grupos de pruebas de gestión de calidad
description: Este artículo describe cómo crear grupos de prueba, de modo que se puedan usar varias pruebas con pedidos de calidad en Microsoft Dynamics 365 Supply Chain Management.
author: yufeihuang
ms.date: 03/23/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: InventTestGroup
audience: Application User
ms.reviewer: kamaybac
ms.custom: 94003
ms.assetid: a1d9417b-268f-4334-8ab6-8499d6c3acf0
ms.search.region: Global
ms.search.industry: Distribution
ms.author: yufeihuang
ms.search.validFrom: 2020-06-17
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: e7722bc92d8c2bf52d6a798a93f07af44037d4e0
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/03/2022
ms.locfileid: "8857717"
---
# <a name="quality-management-test-groups"></a>Grupos de pruebas de gestión de calidad

[!include [banner](../includes/banner.md)]

Este artículo describe cómo crear grupos de prueba, de modo que se puedan usar varias pruebas con pedidos de calidad en Microsoft Dynamics 365 Supply Chain Management.

Use a página **Grupos de pruebas** para establecer, editar y ver los grupos de pruebas y las pruebas individuales asignadas a ellos. La parte superior de la página muestra los grupos de pruebas y la inferior muestra las pruebas asignadas a un grupo de pruebas seleccionado.

A un grupo de pruebas se asignan varias directivas, como un plan de muestreo, un nivel de calidad aceptable (AQL) y el requisito de prueba destructiva. Luego, al asignar una prueba individual a un grupo de pruebas, defina información adicional, como la secuencia, los documentos, y las fechas de validez. Para una prueba cuantitativa, la información que define también incluye los valores de medida aceptables. Para una prueba cualitativa, la información incluye la variable de prueba y el resultado predeterminado.

El grupo de prueba asignado a un pedido de calidad define el conjunto predeterminado de pruebas que se tienen que realizar sobre el artículo especificado. No obstante, puede agregar, cambiar o eliminar pruebas en el pedido de calidad. Los resultados de prueba se notifican para cada prueba de un pedido de calidad.

Cuando define un grupo de pruebas, puede especificar opcionalmente un muestreo de elementos. Los muestreos de artículos se utilizan para definir la cantidad de producto que se debe probar. Para más información, consulte [Muestreo de elementos de gestión de calidad](quality-item-sampling.md). También puede indicar si las pruebas de un grupo de pruebas son destructivas. En una prueba destructiva, el muestreo del artículo se destruye y la cantidad se elimina del inventario disponible.

## <a name="example-of-a-test-group"></a>Ejemplo de grupo de pruebas

Un fabricante define un grupo de pruebas para cada variación de sus criterios de calidad. Los distintos grupos de pruebas reflejan las diferencias de los planes de muestreo, los conjuntos de pruebas que se deben realizar en conjunto, el AQL y otros factores. Para las pruebas cuantitativas también hay diferencias en los valores de medida aceptables. Para hacer cumplir sus pautas de calidad, la empresa asigna un grupo de pruebas a cada regla que se utiliza para generar automáticamente pedidos de calidad en la página **Asociaciones de calidad**. También asigna un grupo de prueba a los pedidos de calidad que se crean manualmente.

## <a name="create-a-test-group"></a>Crear un grupo de pruebas

Para crear un grupo de pruebas, siga estos pasos.

1. Vaya a **Gestión del inventario \> Configurar \> Control de calidad \> Grupos de prueba**.
1. En el panel de acciones, seleccione **Nuevo** para agregar una fila a la cuadrícula en la parte superior de la página. Entonces establezca los siguientes campos para la fila nueva:

    - **Grupo de pruebas**: introduzca un id. o nombre único para el grupo de pruebas.
    - **Descripción**: escriba una descripción detallada del grupo de pruebas.
    - **Nivel de calidad aceptable**: introduzca el porcentaje total de resultados de pruebas que deben aprobarse para que el grupo de pruebas se considere aprobado.
    - **Muestreo de artículos**: seleccione un muestreo de artículos. Para más información, consulte [Muestreo de elementos de gestión de calidad](quality-item-sampling.md).
    - **Destructivo**: seleccione esta casilla para indicar que el grupo de prueba destruirá los elementos que se prueban.

1. Mientras la nueva fila aún está seleccionada, seleccione la pestaña **General** en la parte superior de la página. Algunas de las configuraciones para el grupo de pruebas que se selecciona en la pestaña **Descripción general** se repiten aquí. Además, puede configurar los siguientes campos para el grupo:

    - **Actualizar el atributo de lote de inventario**: cuando configura esta opción en *Sí* aquí, se establecerá automáticamente en *Sí* para todas las nuevas pruebas que se agrega al grupo de pruebas en la parte inferior de la página.
    - **Actualizar la disposición por lotes**: cuando configura esta opción en *Sí*, si el artículo que se está probando está controlado por lotes, la disposición del lote se actualizará automáticamente con el valor seleccionado en el campo **Disposición de lotes de pedidos de calidad fallidos** o **Disposición de lotes de pedidos de calidad aprobados**.
    - **Disposición de lotes de pedidos de calidad fallidos**: seleccione el código de disposición de lote que debe asignarse cuando falla un pedido de calidad que incluye este grupo de prueba porque no cumple con el AQL.
    - **Disposición de lotes de pedidos de calidad pasados**: seleccione el código de disposición de lote que debe asignarse cuando pasa un pedido de calidad que incluye este grupo de prueba porque cumple con el AQL.
    - **Actualizar el estado del inventario**: cuando configura esta opción en *Sí*, en el caso de que **Estado de inventario** esté habilitado en el grupo de dimensiones de almacenamiento para el artículo que se está probando, el estado se actualizará automáticamente con el estado seleccionado en el campo **Estado de pedido de calidad fallido** o **Estado de pedido de calidad pasado**.
    - **Estado de pedidos de calidad fallidos**: seleccione el estado de inventario que debe asignarse al artículo cuando falla un pedido de calidad que incluye este grupo de prueba porque no cumple con el AQL.
    - **Estado de pedidos de calidad pasados**: seleccione el estado de inventario que debe asignarse al artículo cuando pasa un pedido de calidad que incluye este grupo de prueba porque cumple con el AQL.

## <a name="add-a-qualitative-test-to-a-test-group"></a>Agregar una prueba cualitativa a un grupo de prueba

Para agregar una prueba cualitativa a un grupo de pruebas, siga estos pasos.

1. Vaya a **Gestión del inventario \> Configurar \> Control de calidad \> Grupos de prueba**.
1. En la pestaña **Descripción general** de la parte superior de la página, seleccione el grupo de pruebas al que desea agregar una prueba.
1. En la parte inferior de la página, en la pestaña **Descripción general**, seleccione **Agregar** en la barra de herramientas para agregar una fila a la cuadrícula. Entonces establezca los siguientes campos para la fila nueva:

    - **Número de secuencia**: introduzca un número entero para especificar el orden en el que se deben realizar las pruebas. Las pruebas que tienen números de secuencia más pequeños se ejecutarán antes que las pruebas que tengan números de secuencia más grandes.

        > [!NOTE]
        > Le recomendamos que deje un espacio entre los números de secuencia. Por ejemplo, establezca el campo **Número de secuencia** en *10* para su primera prueba y luego incremente el valor en 10 para cada prueba adicional. De esta forma, puede agregar nuevas pruebas posteriormente sin tener que eliminar y volver a crear las líneas para ponerlas en el orden deseado.

    - **Prueba**: seleccione la prueba que desea realizar. Para las pruebas cualitativas, seleccione una prueba en la que el campo **Tipo** esté establecido en *Opción*.
    - **Entrada en vigor**: seleccione la primera fecha en la que la prueba es válida. Si deja este campo en blanco, no hay límite.
    - **Vencimiento**: seleccione la última fecha en la que la prueba es válida. Si deja este campo en blanco o lo establece en *Nunca*, no hay límite.
    - **Determinación del valor de prueba**: seleccione cómo se debe determinar un NCA cuando se registran varios resultados para la misma prueba. Para una prueba cualitativa, solo se puede seleccionar *Manual*. Si selecciona uno de los otros valores (*Promedio*, *Mínimo*, o *Máximo*), recibirá un mensaje de error cuando guarde el grupo de prueba.
    - **Atributo**: si desea registrar los resultados de la prueba en un atributo de lote, seleccione el atributo aquí y seleccione la casilla **Actualizar el atributo de lote de inventario**.
    - **Actualizar el atributo de lote de inventario**: seleccione esta casilla para registrar los resultados de la prueba para el atributo de lote que está seleccionado en el campo **Atributo**.

1. En la parte inferior de la página, seleccione la pestaña **General**. Algunas de las configuraciones para la prueba seleccionadas en la pestaña **Descripción general** se repiten aquí. Además, puede configurar los siguientes campos para la prueba:

    - **Certificado de informe de análisis**: establezca esta opción en *Sí* para indicar que los resultados de la prueba deben imprimirse en el certificado de análisis (CoA). Este informe se puede generar a partir del pedido de calidad.
    - **Acción en caso de fallo**: seleccione *Aceptar* o *Fallar* para indicar si la prueba debe pasarse o fallar si no se cumple el AQL.
    - **Nivel de calidad aceptable**: introduzca el porcentaje total de resultados de pruebas que deben pasar para que la prueba se considere pasada.

1. En la parte inferior de la página, en la pestaña **Prueba**, configure los siguientes campos:

    - **Variable**: seleccione la variable de prueba para registrar los resultados de una prueba cualitativa.
    - **Resultado predeterminado**: seleccione el resultado predeterminado que se debe registrar para los resultados de la prueba.
    - **Instrumento de prueba**: seleccione el dispositivo que debe utilizarse para la prueba. Si se define un instrumento de prueba, se introduce automáticamente para la prueba en el grupo de pruebas.

1. Cierre la página.

## <a name="add-a-quantitative-test-to-a-test-group"></a>Agregar una prueba cuantitativa a un grupo de pruebas

Para agregar una prueba cuantitativa a un grupo de pruebas, siga estos pasos.

1. Vaya a **Gestión del inventario \> Configurar \> Control de calidad \> Grupos de prueba**.
1. En la pestaña **Descripción general** de la parte superior de la página, seleccione el grupo de pruebas al que desea agregar una prueba.
1. En la parte inferior de la página, en la pestaña **Descripción general**, seleccione **Agregar** en la barra de herramientas para agregar una fila a la cuadrícula. Entonces establezca los siguientes campos para la fila nueva:

    - **Número de secuencia**: introduzca un número entero para especificar el orden en el que se deben realizar las pruebas. Las pruebas que tienen números de secuencia más pequeños se ejecutarán antes que las pruebas que tengan números de secuencia más grandes.

        > [!NOTE]
        > Le recomendamos que deje un espacio entre los números de secuencia. Por ejemplo, establezca el campo **Número de secuencia** en *10* para su primera prueba y luego incremente el valor en 10 para cada prueba adicional. De esta forma, puede agregar nuevas pruebas posteriormente sin tener que eliminar y volver a crear las líneas para ponerlas en el orden deseado.

    - **Prueba**: seleccione la prueba que desea realizar. Para las pruebas cuantitativas, seleccione una prueba en la que el campo **Tipo** esté establecido en *Fracción* o *Entero*.
    - **Entrada en vigor**: seleccione la primera fecha en la que la prueba es válida. Si deja este campo en blanco, no hay límite.
    - **Vencimiento**: seleccione la última fecha en la que la prueba es válida. Si deja este campo en blanco o lo establece en *Nunca*, no hay límite.
    - **Determinación del valor de prueba**: seleccione cómo se debe determinar un NCA cuando se registran varios resultados para la misma prueba. Las opciones disponibles son *Promedio*, *Mínimo*, *Máximo* y *Manual*.
    - **Atributo**: si desea registrar los resultados de la prueba en un atributo de lote, seleccione el atributo aquí y seleccione la casilla **Actualizar el atributo de lote de inventario**.
    - **Actualizar el atributo de lote de inventario**: seleccione esta casilla para registrar los resultados de la prueba para el atributo de lote que está seleccionado en el campo **Atributo**.

1. En la parte inferior de la página, seleccione la pestaña **General**. Algunas de las configuraciones para la prueba seleccionadas en la pestaña **Descripción general** se repiten aquí. Además, puede configurar los siguientes campos para la prueba:

    - **Certificado de informe de análisis**: establezca esta opción en *Sí* para indicar que los resultados de la prueba deben imprimirse en el CoA. Este informe se puede generar a partir del pedido de calidad.
    - **Acción en caso de fallo**: seleccione *Aceptar* o *Fallar* para indicar si la prueba debe pasarse o fallar si no se cumple el AQL.
    - **Nivel de calidad aceptable**: introduzca el porcentaje total de resultados de pruebas que deben pasar para que la prueba se considere pasada.

1. En la parte inferior de la página, en la pestaña **Prueba**, configure los siguientes campos:

    - **Estándar**: introduzca la cantidad (entero o fracción) que se espera para los resultados de la prueba. El valor que introduzca se introducirá de manera predeterminada en los resultados de la prueba. Además, se introducirá automáticamente como un valor predeterminado en los campos **Min** y **Max**.
    - **Min**: introduzca el valor mínimo permitido para los resultados de la prueba. El valor que introduzca debe ser menor que la cantidad establecida en el campo **Estándar**. Cuando actualiza el campo **Min**, el campo **Tolerancia mínima (%)** se actualiza automáticamente. De igual manera, cuando actualiza el campo **Tolerancia mínima (%)**, el campo **Min** se actualiza automáticamente.
    - **Max**: introduzca el valor máximo permitido para los resultados de la prueba. El valor que introduzca debe ser mayor que la cantidad establecida en el campo **Estándar**. Cuando actualiza el campo **Max**, el campo **Tolerancia máxima (%)** se actualiza automáticamente. De igual manera, cuando actualiza el campo **Tolerancia máxima (%)**, el campo **Max** se actualiza automáticamente.
    - **Instrumento de prueba**: seleccione el dispositivo que debe utilizarse para la prueba. Si se define un instrumento de prueba, se introduce automáticamente para la prueba en el grupo de pruebas.

1. Cierre la página.

## <a name="additional-resources"></a>Recursos adicionales

- [Instrumentos de prueba de gestión de calidad](quality-management-processes.md)
- [Pruebas de gestión de calidad](quality-management-processes.md)
- [Variables de prueba de gestión de calidad](quality-management-processes.md)
- [Asociaciones de calidad](quality-management-processes.md)
- [Atributos de lote](../production-control/batch-attributes.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
