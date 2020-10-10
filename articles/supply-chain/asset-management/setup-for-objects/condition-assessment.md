---
title: Evaluación de condiciones
description: En este tema se explica cómo crear una plantilla y un registro de evaluación de condiciones para un activo en Administración de activos.
author: josaw1
manager: tfehr
ms.date: 06/26/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CatProcureCatalogEdit, CatProcureCatalogListPage, EntAssetObjectCondition, EntAssetConditionTemplate
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: 2214
ms.assetid: 2f3e0441-414d-402b-b28b-7ab0d650d658
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 774c788959c5ebea69b4d22c886ac673f50b97f5
ms.sourcegitcommit: c986d5234b81d31cc6d054298be6f6ec92c1754c
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/25/2020
ms.locfileid: "3889802"
---
# <a name="condition-assessment"></a>Evaluación de condiciones

[!include [banner](../../includes/banner.md)]

 

En este tema se explica cómo crear una plantilla y un registro de evaluación de condiciones para un activo en Administración de activos. La evaluación de condiciones se realiza a intervalos regulares, y el objetivo principal es crear y mantener datos de condiciones en activos. Visto desde la perspectiva del mantenimiento preventivo, es importante supervisar la información esencial, como el estado actual, y el tiempo de vida restante. Además, si realiza la evaluación de condiciones periódicamente podrá controlar y comparar las condiciones en la maquinaria de la fábrica.

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

1. Seleccione **Administración de activos** > **Común** > **Activos** > **Todos los activos**.
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
>También puede registrar la evaluación de condiciones en una orden de trabajo (**Administración de activos** > **Común** > **Órdenes de trabajo** > **Todas las órdenes de trabajo** >  botón **Evaluación de condiciones**.)
