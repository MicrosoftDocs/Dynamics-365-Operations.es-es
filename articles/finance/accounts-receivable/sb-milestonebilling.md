---
title: Plantillas de hitos
description: Este artículo explica cómo configurar la funcionalidad de facturación por hitos en la facturación de suscripción.
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
ms.openlocfilehash: d3c2cf751e4998c73bc3816e5b81e8d5963c8e53
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/03/2022
ms.locfileid: "8856781"
---
# <a name="milestone-billing"></a>Facturación por hitos

[!include [banner](../includes/banner.md)]

Este artículo explica cómo definir plantillas para la funcionalidad de facturación por hitos en la facturación de suscripción. Para cada línea en la plantilla de hitos, puede definir el porcentaje o la cantidad de asignación. A continuación, puede asignar la plantilla de hitos a los elementos del programa de facturación que utilizan la funcionalidad de facturación por hitos.

## <a name="add-a-template"></a>Agregar una plantilla

Para agregar una plantilla de hitos, siga estos pasos.

1. Vaya a **Facturación de suscripción\> Facturación de contratos periódicos\> Configuración\> Plantillas de hitos**.
2. Seleccione **Nuevo**.
3. En el campo **Plantilla por hitos**, especifique un identificador único para la nueva plantilla.
4. En el campo **Descripción**, escriba una descripción.
5. En el campo **Método de asignación**, seleccione un método de asignación.
6. Opcional: En el campo **Cantidad total**, especifique la cantidad total para la plantilla.
7. Para añadir una línea, seleccione **Agregar**. A continuación, en el campo **Número de artículo**, seleccione el número de artículo para la nueva línea.
8. Siga uno de estos pasos, según el valor seleccionado en el campo **Método de asignación**:

    - Si seleccionó **Porcentaje** como método de asignación, en el campo **Porcentaje** especifique el porcentaje de asignación para cada línea. Si especifica porcentajes, la suma de porcentajes que se muestra en el campo **Porcentaje total** debe ser igual a **100**.
    - Si seleccionó **Importe variable** como método de asignación, en el campo **Importe** especifique el importe para cada línea.
    - Si seleccionó **Importe igual** como método de asignación, no tiene que especificar una cantidad. Cada línea se actualizará con el porcentaje y el importe correctos, según la cantidad de elementos que se agreguen a la plantilla.

9. Seleccione **Guardar**.

## <a name="delete-a-template"></a>Eliminar plantilla

Para eliminar una plantilla de hitos, siga estos pasos.

1. Seleccione una o más líneas a eliminar y seleccione **Eliminar**.
2. Haga clic en **Sí** cuando se le solicita que confirme la selección.

## <a name="milestone-template-fields"></a>Campos de plantilla de hitos

La página **Plantilla de hitos** contiene los siguientes campos.

| Campo | Description |
|-------|-------------| 
| Plantilla de hitos | El identificador único de la plantilla de hitos. |
| Description | La descripción de la plantilla de hitos. |
| Método de asignación | <p>Seleccione el método de asignación:</p><ul><li>**Porcentaje completado** – Se utiliza un valor de finalización acumulativo para cada línea.</li><li>**Porcentaje** – Se puede especificar una cantidad porcentual para la asignación. La suma de todos los porcentajes debe ser igual a 100.</li><li>**Importe variable** – Se puede especificar una cantidad para la asignación. El importe de la asignación se especifica en el nivel de transacción.</li><li>**Importe igual** – Los porcentajes de asignación se calculan automáticamente y se dividen por igual entre los elementos de la plantilla.</li></ul> |
| Importe total | Especifique el importe del hito para la plantilla. |
| **Líneas** | |
| Número de artículo | Seleccione el número de artículo para la plantilla de hitos. |
| Nombre de producto | Nombre del artículo. |
| Porcentaje | <p>Especifique el porcentaje de asignación para la línea:</p><ul><li>Si el campo **Método de asignación** se establece en **Porcentaje**, especifique el porcentaje de la línea.</li><li>Si el campo **Método de asignación** se establece en **Importe igual**, el porcentaje se divide automáticamente en porcentajes iguales, en función del número de elementos de la plantilla.</li></ul><p>La suma de todos los porcentajes debe ser igual a 100.</p><p>Si un valor **Importe total** se especifica en el encabezado y usted cambia el valor **Porcentaje** para la línea, el valor **Importe** se actualiza. Por el contrario, si cambia el valor **Importe**, el valor **Porcentaje** se actualiza.</p> |
| Importe | <p>El importe de la asignación para la línea:</p><ul><li>Si el campo **Método de asignación** se establece en **Importe variable**, especifique el importe para la línea.</li><li>Si el campo **Método de asignación** se establece en **Importe igual**, el importe se divide automáticamente en importes iguales, según el número de elementos de la plantilla y el valor **Importe total** que se especifica en el encabezado.</li></ul><p>La suma de todos los importes debe ser igual al valor **Importe total** que se especifica en el encabezado.</p><p>Si un valor **Importe total** se especifica en el encabezado y usted cambia el valor **Importe** para la línea, el valor **Porcentaje** se actualiza. Por el contrario, si cambia el valor **Porcentaje**, el valor **Importe** se actualiza.</p> |
| **Totales** | |
| Porcentaje total | La suma de porcentajes. La suma de todos los porcentajes debe ser igual a 100. |
| Importe total | La suma de valores **Importe** para todas las líneas. Esta suma debe ser igual al valor **Importe total** que se especifica en el encabezado. |
| Importe pendiente | El importe restante. El valor se calcula como el valor **Importe total** del encabezado menos la suma de los valores **Importe** para todas las líneas.|

## <a name="milestone-allocation"></a>Asignación por hitos

Antes de comenzar a utilizar la funcionalidad de hitos, debe completar estas tareas.

1. Agregue una o más plantillas de hitos.
2. Crear un grupo de programación de facturación. Especifique **Hito** como tipo de elemento y seleccione una plantilla.
3. En la página **Configuración del artículo** (**Facturación de suscripción\> Facturación de contratos periódicos\> Configuración\> Elementos**), seleccione una relación de artículo y una plantilla de hitos para la configuración de artículos.

Una vez que haya creado las plantillas de hitos, los grupos de programación de facturación y los artículos, puede crear una programación de facturación que use la funcionalidad de hitos.

Para configurar una programación de facturación que utilice hitos, siga estos pasos.

1. Desde la lista **Programaciones de facturación (todas/activas)** en la página **Programaciones de facturación**, seleccione **Nueva**.
2. En la página **Todas las programaciones de facturación**, cree una nueva programación de facturación y especifique una cuenta de cliente y una fecha de inicio.
3. En la sección **Líneas de programación de facturación**, seleccione **Agregar línea**. A continuación, agregue un número de artículo y configure el campo **Tipo de artículo** en **Hito**.

    Si se configura una plantilla de hitos predeterminada para el artículo, los eventos de hitos se agregan automáticamente a las líneas de la programación de facturación. Las fechas de finalización están en blanco para las líneas de hitos.

    Si no se configura una plantilla de hitos para el artículo, seleccione **Asignación de hitos**. Entonces, en la página **Asignación de hitos**, seleccione una plantilla de hitos y realice las actualizaciones necesarias. Luego seleccione **Cerrar** para volver a la programación de facturación y terminar de crear la programación de facturación.

4. Para crear facturas para la programación de facturación, debe actualizar la fecha de finalización de cada evento hito. Para una sola programación de facturación, puede actualizar la fecha de finalización del evento hito en las líneas de la programación de facturación. Para actualizar varias programaciones de facturación, seleccione **Actualizar proceso de fecha de finalización**.
5. Después de actualizar la fecha de finalización, puede crear la factura. Para un programa de facturación único, seleccione **Generar factura** en la página **Todas las programaciones de facturación**. Para crear facturas para varias programaciones de facturación, seleccione **Generar factura** o **Generar procesamiento por lotes de facturas** bajo **Tareas periódicas**.

## <a name="edit-milestone-allocation-on-a-billing-schedule-line"></a>Editar la asignación de hitos en una línea de programación de facturación

Para editar la asignación de hitos en una línea de programación de facturación, siga estos pasos.

1. En la página **Programaciones de facturación**, **Programaciones de facturación (todas/activas)**, en el campo **Número de programación**, seleccione el número de la programación de facturación.
2. En la sección **Líneas de programación de facturación**, introduzca un artículo, especifique **Hito** como elemento y seleccione **Asignación de hitos**.
3. En el campo **Plantilla de hitos**, seleccione una plantilla de hitos.
4. Seleccione **Procesar**. Las líneas de la plantilla de hitos se agregan automáticamente a las líneas de programación de facturación.

## <a name="milestone-allocation-fields"></a>Campos de asignación por hitos

La página **Asignación de hitos** contiene los siguientes campos.

| Campo | Description |
|-------|-------------|
| Artículo primario | El número de artículo del primario. |
| Precio total | <p>El precio total del artículo. El valor corresponde al valor **Importe neto** de la línea de programación de facturación.</p></p>Para un elemento primario de hito, el valor predeterminado es el **Importe total** que se especifica para la plantilla de hitos. Si el importe total es 0 (cero), el valor predeterminado es el **Importe neto** de la línea de programación de facturación.</p> |
| Plantilla de hitos | El identificador de la plantilla de hitos del artículo de la línea. |
| Descripción de la plantilla | La descripción de la plantilla de hitos. |
| Método de asignación | El método de asignación que se utiliza para la plantilla de hitos. |
| **Líneas** | Los valores predeterminados para todas las líneas se basan en la plantilla de hitos seleccionada. Puede cambiarlos como sea necesario. |
| Número de artículo | El número de artículo para la plantilla de asignación de hitos. |
| Nombre de producto | Nombre de producto. |
| Porcentaje | <p>El porcentaje de asignación para la línea. La suma de todos los porcentajes debe ser igual a 100.</p><p>Si cambia el valor **Porcentaje**, el valor **Importe neto** para la línea se actualiza. Por el contrario, si cambia el valor **Importe neto**, el valor **Porcentaje** se actualiza.</p> |
| Importe neto | <p>El importe de la asignación para la línea. La suma de todos los importes netos para todas las líneas debe ser igual al valor **Precio total** que se especifica en el encabezado.</p><p>Si cambia el valor **Importe neto** para la línea, **Porcentaje** se actualiza. Por el contrario, si cambia el valor **Porcentaje**, el valor **Importe neto** se actualiza.</p> |
| **Totales** | |
| Porcentaje total | La suma de valores **Porcentaje** para todas las líneas. Esta suma debe ser igual a 100. |
| Importe total | La suma de los valores **Importe neto** para todas las líneas. Esta suma debe ser igual al valor **Precio total** que se especifica en el encabezado. |
| Importe pendiente | El importe restante. El valor se calcula como el valor **Precio total** del encabezado menos la suma de los valores **Importe neto** para todas las líneas. El importe final debe ser 0 (cero). |
