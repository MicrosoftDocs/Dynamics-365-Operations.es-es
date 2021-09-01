---
title: Grupos de calidad de artículos
description: Este tema describe cómo usar y crear grupos de calidad de artículos para agrupar productos de manera lógica de modo que puedan asignarse a asociaciones de calidad para la generación automática de pedidos de calidad.
author: rachel-profitt
ms.date: 03/23/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: InventTestQualityGroup, InventTestItemQualityGroup
audience: Application User
ms.reviewer: kamaybac
ms.custom: 94003
ms.assetid: a1d9417b-268f-4334-8ab6-8499d6c3acf0
ms.search.region: Global
ms.search.industry: Distribution
ms.author: raprofit
ms.search.validFrom: 2020-06-17
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 0f26aa50e814a7abb8e7ed3e6a943136578208854a9efb3b8e8d38016917681d
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2021
ms.locfileid: "6781498"
---
# <a name="item-quality-groups"></a>Grupos de calidad de artículos

[!include [banner](../includes/banner.md)]

Un grupo de calidad representa requisitos de prueba comunes para los artículos. Este tema describe cómo usar y crear grupos de calidad de artículos para agrupar productos de manera lógica de modo que puedan asignarse a asociaciones de calidad para la generación automática de pedidos de calidad.

Para configurar, editar y ver los artículos asignados a un grupo de calidad o los grupos de calidad asignados a un artículo, vaya a **Gestión de inventario \> Configuración \> Grupos de calidad**. Cuando haya definido los requisitos de prueba en la página **Grupos de prueba**, puede definir las reglas para generar automáticamente pedidos de calidad. Para simplificar el proceso, no se definen reglas para artículos individuales. En su lugar, puede definir las reglas para un grupo de calidad en la página **Asociaciones de calidad**.

## <a name="example-of-an-item-quality-group"></a>Ejemplo de un grupo de calidad de artículos

Un fabricante compra varias materias primas con los mismos requisitos de prueba para una inspección entrante. Por consiguiente, la empresa define un grupo de calidad y, después, le asigna números de artículo asociados con los materiales sin procesar para ese grupo. Más adelante, la empresa compra un nuevo tipo de materia prima con los mismos requisitos de prueba. En lugar de configurar requisitos de prueba nuevos para el nuevo material, la empresa añade el número de artículo del nuevo material al grupo de calidad existente.

La misma empresa también produce artículos con los mismos requisitos de prueba y envía artículos con los mismos requisitos para las pruebas anteriores al envío. Por consiguiente, la empresa define dos grupos de calidad adicionales y, después, asigna números de artículo pertinentes a cada grupo.

## <a name="create-a-quality-group"></a>Crear un grupo de calidad

Para crear un grupo de calidad, siga estos pasos.

1. Vaya a **Gestión del inventario \> Configurar \> Control de calidad \> Grupos de calidad**.
1. En el Panel de acciones, seleccione **Nuevo** para agregar una fila a la cuadrícula. Entonces establezca los siguientes campos para la fila nueva:

    - **Grupo de calidad**: introduzca un id. o nombre único para el grupo de calidad.
    - **Descripción**: escriba una descripción detallada del grupo de calidad.

1. Cierre la página.

## <a name="manually-add-items-to-a-quality-group"></a>Agregar manualmente artículos a un grupo de calidad

Para agregar artículos manualmente a un grupo de calidad, siga estos pasos.

1. Vaya a **Gestión del inventario \> Configurar \> Control de calidad \> Grupos de calidad**.
1. Seleccione el grupo de calidad al que desea agregar artículos.
1. En el panel de acciones, haga clic en **Artículos**.
1. En la página **Artículos en grupos de calidad**, en el panel de acciones, seleccione **Nuevo** para agregar una fila a la cuadrícula. Luego, para la nueva fila, establezca el campo **Número de artículo** campo en el número de artículo que desea agregar.
1. Repita el paso anterior para cada elemento adicional que deba agregarse.
1. Cierre las páginas.

## <a name="add-multiple-items-to-a-quality-group"></a>Agregar varios artículos a un grupo de calidad

Para agregar varios artículos a un grupo de calidad, siga estos pasos.

1. Vaya a **Gestión del inventario \> Configurar \> Control de calidad \> Grupos de calidad**.
1. Cree o seleccione el grupo de calidad al que desea agregar artículos.
1. En el panel de acciones, haga clic en **Agregar artículos**.
1. En el cuadro de diálogo **Consulta**, introduzca los criterios de filtrado para los elementos que desea agregar. Por ejemplo, puede filtrar todos los artículos de un grupo de artículos específico.
1. Seleccione **Aceptar**.
1. En el cuadro de diálogo **Agregar artículos**, una cuadrícula muestra todos los artículos que coinciden con su consulta. Revise los resultados.

    Si se requieren cambios, seleccione **Seleccionar** para volver al cuadro de diálogo **Consulta** y ajuste su consulta.

1. Cuando los resultados incluyan todos los elementos que desea agregar, seleccione **Aceptar**.
1. Cierre la página.

## <a name="manually-associate-an-item-with-a-quality-group"></a>Asociar manualmente un artículo con un grupo de calidad

Para asociar manualmente un artículo a un grupo de calidad, siga estos pasos.

1. Vaya a **Gestión del inventario \> Configurar \> Control de calidad \> Grupos de calidad de artículos**.
1. En el Panel de acciones, seleccione **Nuevo** para agregar una fila a la cuadrícula. Entonces establezca los siguientes campos para la fila nueva:

    - **Número de artículo**: seleccione el número de artículo a agregar.
    - **Grupo de calidad**: seleccione el grupo de calidad a asignar al artículo.

1. Repita el paso anterior para cada combinación adicional de un artículo y un grupo de calidad que deba agregar.
1. Cierre las páginas.

## <a name="manually-add-a-quality-group-from-the-released-products-page"></a>Agregue manualmente un grupo de calidad desde la página de productos liberados

Para agregar manualmente un grupo de calidad desde la página **Productos liberados**, siga estos pasos.

1. Vaya a **Gestión de información de productos \> Productos \> Productos despachados**.
1. Seleccione el producto al que desea asignar un grupo de calidad.
1. En el panel de acciones, en la pestaña **Administrar inventario**, en el grupo **Calidad**, seleccione **Grupos de calidad de artículos**.
1. En la página **Artículos en grupos de calidad**, en el panel de acciones, seleccione **Nuevo** para agregar una fila a la cuadrícula. Luego, para la nueva fila, establezca el campo **Grupo de calidad** en el grupo de calidad que desea asignar al producto.
1. Repita el paso anterior para cada grupo de calidad adicional que desee asignar al producto.
1. Cierre las páginas.

## <a name="additional-resources"></a>Recursos adicionales

- [Instrumentos de prueba de gestión de calidad](quality-test-instruments.md)
- [Pruebas de gestión de calidad](quality-tests.md)
- [Grupos de pruebas de gestión de calidad](quality-test-groups.md)
- [Variables de prueba de gestión de calidad](quality-test-variables.md)
- [Asociaciones de calidad](quality-associations.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
