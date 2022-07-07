---
title: Evaluación de estado
description: En este artículo se explica cómo crear una plantilla y un registro de evaluación de condiciones para un activo en Administración de activos.
author: johanhoffmann
ms.date: 06/26/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: CatProcureCatalogEdit, CatProcureCatalogListPage, EntAssetObjectCondition, EntAssetConditionTemplate
audience: Application User
ms.reviewer: kamaybac
ms.custom: 2214
ms.assetid: 2f3e0441-414d-402b-b28b-7ab0d650d658
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: c43424a0955d7a046186e8a4120c050990df6060
ms.sourcegitcommit: cfe8fbc202c3eb05d894076fdf99e46704f17365
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/15/2022
ms.locfileid: "9015067"
---
# <a name="condition-assessment"></a>Evaluación de estado

[!include [banner](../../includes/banner.md)]

 

En este artículo se explica cómo crear una plantilla y un registro de evaluación de condiciones para un activo en Administración de activos. La evaluación de condiciones se realiza a intervalos regulares, y el objetivo principal es crear y mantener datos de condiciones en activos. Visto desde la perspectiva del mantenimiento preventivo, es importante supervisar la información esencial, como el estado actual, y el tiempo de vida restante. Además, si realiza la evaluación de condiciones periódicamente podrá controlar y comparar las condiciones en la maquinaria de la fábrica.

La evaluación de condiciones se puede utilizar para medir y supervisar muchas condiciones de sus equipos. Por ejemplo, puede medir las vibraciones de la maquinaria. Una vez que haya registrado medidas de vibración en Administración de activos para distintos tipos de equipo, puede buscar la evaluación registrada más reciente y ver medidas de vibración.

La evaluación de condiciones se crea en los activos. Debe configurar una plantilla de la evaluación de condiciones en un tipo de activo antes de realizar el procedimiento de evaluación de condiciones. La razón para utilizar plantillas para la evaluación de condiciones es evitar la variación de los datos de condiciones en activos similares. La secuencia para configurar y usar la evaluación de condiciones en Administración de activos es la siguiente: primero debe configurar las plantillas necesarias de la evaluación de condiciones. A continuación, debe asociar las plantillas con los tipos de activos del formulario **Tipos de activos**. Por último, puede crear registros de evaluación de condiciones en un activo en el formulario **Activo**.

## <a name="create-a-condition-assessment-template"></a>Crear una plantilla de evaluación de condiciones

1. Seleccione **Administración de activos** > **Configuración** > **Tipos de activos** > **Evaluación de condiciones**.
2. Seleccionar **Nuevo** para crear una plantilla nueva.
3. Inserte un identificador para la plantilla en el campo **Plantilla**.
4. Inserte un nombre para la plantilla en el campo **Nombre**.
5. En la ficha desplegable **Líneas de evaluación de condiciones**, agregue las líneas que necesita para la evaluación de condiciones, incluida la selección del tipo y la unidad de medida de la condición.
6. En la ficha desplegable **Tipos de activos**, agregue los tipos de activos que deben usar la plantilla de evaluación de condiciones.
7. En los campos **Líneas** y **Tipos de activos** del grupo **Detalles** en la parte superior de la pantalla, verá el número de líneas de evaluación y tipos de activos relacionados con la plantilla de evaluación de condiciones seleccionada.


## <a name="create-condition-assessment-registration-on-an-asset"></a>Crear un registro de evaluación de condiciones en un activo

1. Seleccione **Administración de activos** > **Activos** > **Todos los activos**.
2. En la lista, seleccione el activo para el que desea crear un registro de evaluación de condiciones.
3. En la pestaña **General**, haga clic en **Evaluación de condiciones**.
4. Haga clic en **Nuevo** para crear un registro nuevo.
5. Seleccione la fecha para la evaluación de condiciones en el campo **Fecha**.
6. Seleccione el nombre del trabajador que realizó el registro de la evaluación de condiciones en el campo **Trabajador**.
7. En el campo **Líneas** verá el número de líneas de evaluación configuradas en la evaluación de condiciones.
8. Seleccione una plantilla para la evaluación de condiciones en el campo **Plantilla**. El nombre de la plantilla se inserta automáticamente en el campo **Nombre**, y las líneas de registro relacionadas se insertarán en la ficha desplegable **Líneas de evaluación de condiciones**.
9. Puede insertar notas relacionadas con la evaluación de condiciones seleccionada en la ficha desplegable **Notas**.
10. Para cada línea de la evaluación de condiciones, inserte datos de medida en el campo **Valor**.
11. Puede insertar un comentario relacionado con la línea de registro seleccionada en la ficha desplegable **Líneas de evaluación de condiciones** > campo **Comentarios**. Si agrega un comentario a una línea, la casilla **Comentario** se selecciona automáticamente.

Tras un registro de evaluación de condiciones en un activo, puede imprimir un informe de evaluación de condiciones.

>[!NOTE]
>También puede registrar la evaluación de condiciones en una orden de trabajo (**Administración de activos** > **Órdenes de trabajo** > **Todas las órdenes de trabajo**, botón  > **Evaluación de condiciones**).


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]