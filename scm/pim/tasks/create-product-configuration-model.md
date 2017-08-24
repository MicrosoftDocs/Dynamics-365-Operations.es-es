--- 
title: "Crear un modelo de configuración de productos"
description: "Este procedimiento muestra cómo crear un modelo de configuración de productos y especificar información básica como atributos y subcomponentes."
author: BibiSp
manager: AnnBe
ms.date: 03/02/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: bibis
ms.search.scope: Operations
ms.search.region: Global
ms.author: bibis
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 55b22d246d6bfa9e8159fb844da95f61fcf07c62
ms.openlocfilehash: da8dd3bbc350c29ce1f7dc22ab3914dfee4b967c
ms.contentlocale: es-es
ms.lasthandoff: 07/28/2017

---
# <a name="create-a-product-configuration-model"></a>Crear un modelo de configuración de productos

[!include[task guide banner](../../includes/task-guide-banner.md)]

Este procedimiento muestra cómo crear un modelo de configuración de productos y especificar información básica como atributos y subcomponentes. La empresa de datos de prueba utilizada para crear este procedimiento es USMF.


## <a name="create-a-product-model"></a>Crear un modelo de producto
1. Haga clic en Definición de modelo de variante del producto.
2. Haga clic en Modelos de configuración del producto.
3. Haga clic en Nuevo.
4. En el campo Nombre, escriba un valor.
5. En el campo Descripción, escriba un valor.
6. En el campo Estrategia de solucionador, seleccione una opción.
    * La estrategia de solucionador determina la manera en que se procesan las restricciones de un modelo de configuración de productos basado en restricciones. Esta selección puede tener un impacto en el rendimiento del modelo de configuración de productos.  
7. En el campo Nombre, escriba un valor.
    * El componente raíz representa el modelo de configuración de productos, pero también se puede usar en otros modelos de productos.  
8. Haga clic en Aceptar
9. En el campo Volver a utilizar configuraciones, seleccione una opción.
    * Si el parámetro Volver a utilizar configuraciones se establece Sí, el sistema comprobará las configuraciones idénticas después de cada sesión y las volverá a utilizar si se encuentra una coincidencia exacta.  

## <a name="add-attributes"></a>Agregar atributos
1. Expanda la sección Atributos.
2. Haga clic en Agregar.
3. En la lista, marque la fila seleccionada.
4. En el campo Nombre, escriba un valor.
5. En el campo Nombre del solucionador, escriba un valor.
    * El solucionador de restricciones usa el nombre del solucionador del configurador de productos. No debe incluir espacios ni caracteres especiales excepto _ (guión bajo).  
6. En el campo Descripción, escriba un valor.
    * El texto de la descripción se muestra al usuario de configuración y puede por tanto servir de ayuda en la selección del valor del atributo correcto.  
7. En el campo Tipo de atributo, especifique o seleccione un valor.
    * El tipo de atributo determina qué valores están disponibles para el atributo.  
8. Active la casilla Incluir en reutilización.
    * Esta opción solo está disponible si se ha seleccionado la opción Volver a utilizar configuraciones. Incluir el atributo en la casilla de volver a utilizar significa que este atributo se considerará cuando el sistema busque una coincidencia exacta.  

## <a name="add-subcomponents"></a>Agregar subcomponentes
1. Expanda la sección Subcomponentes.
2. Haga clic en Agregar.
3. En la lista, marque la fila seleccionada.
4. En el campo Nombre, escriba un valor.
5. En el campo Nombre del solucionador, escriba un valor.
6. En el campo Descripción, escriba un valor.
7. En el campo Componente, especifique o seleccione un valor.
    * Cada subcomponente debe hacer referencia a una definición del componente. Este diseño admite los componentes reutilizables y garantiza que una vez que se ha definido un componente puede usarse en muchos modelos de productos.  
8. Haga clic en Guardar.
9. Haga clic en Detalles de línea de L. MAT.
    * El formulario Detalles de línea de L. MAT permite al usuario seleccionar las propiedades necesarias para el subcomponente. A cada propiedad se le puede dar un valor fijo o asignar a un atributo. La asignación a un atributo hará que la propiedad de la línea de L. MAT obtenga valores diferentes en función de la selección de la configuración.  
10. En el campo Número de artículo, especifique o seleccione un valor.
    * Cada subcomponente representa un producto maestro configurable con tecnología de configuración basada en restricciones. La referencia se realiza a través del código de artículo.  
11. Active la casilla Establecer.
12. Seleccione Sí en el campo Cálculo.
    * La configuración de la opción de cálculo garantiza que se incluirá el producto al ejecutar un cálculo de coste para el producto.  
13. Haga clic en la pestaña Configurar.
14. Active la casilla Establecer.
15. En el campo Cantidad, especifique un número.
    * El campo de cantidad determina cuánto de este producto se consumirá en el producto configurado.  
16. Active la casilla Establecer.
17. En el campo Por serie, especifique un número.
18. Haga clic en Aceptar


