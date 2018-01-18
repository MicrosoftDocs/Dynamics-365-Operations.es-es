---
title: Restricciones de tablas definidas por el usuario o definidas por el sistema
description: "Este artículo explica los dos tipos de restricciones de tablas para componentes en un modelo de configuración de productos: definidos por el usuario y definidos por el sistema. Las restricciones de tablas representan matrices de las combinaciones de atributos permitidas, donde cada fila define un conjunto de valores de atributos posibles."
author: cvocph
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: PCTableConstraintAttachAttributeTree, PCTableConstraintColumnSystem, PCTableConstraintContentUserDef, PCTableConstraintDefinition, PCTableConstraintWizard
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Core, Operations
ms.custom: 19781
ms.assetid: 0a4ea930-b344-43a8-871e-d5cd077892c4
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: yuyus
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: 77333761aee426c6fa2d9261eaa3fda1a76811f0
ms.contentlocale: es-es
ms.lasthandoff: 11/03/2017

---

# <a name="system-defined-and-user-defined-table-constraints"></a>Restricciones de tablas definidas por el usuario o definidas por el sistema

[!include[banner](../includes/banner.md)]


Este artículo explica los dos tipos de restricciones de tablas para componentes en un modelo de configuración de productos: definidos por el usuario y definidos por el sistema. Las restricciones de tablas representan matrices de las combinaciones de atributos permitidas, donde cada fila define un conjunto de valores de atributos posibles.

Las restricciones de tablas representan las matrices de combinaciones de atributos que se permiten para componentes en un modelo de configuración de productos. Cada fila en la tabla define un conjunto de valores de atributo posibles. Puede declarar dos tipos de restricciones en un modelo de configuración de productos:

-   **Restricción de expresión**: cree una expresión que defina relaciones entre atributos para garantizar que solo se puedan seleccionar valores compatibles durante la configuración del producto.
-   **Restricción de tablas**: cree una tabla que defina todas las combinaciones posible para un conjunto concreto de atributos. Hay dos tipos de restricciones de tablas disponibles: restricciones de tablas definidas por el usuario y restricciones de tablas definidas por el sistema.

Este artículo describe las restricciones de tablas que define el usuario y las definidas por el sistema para componentes en un modelo de configuración de productos.

## <a name="user-defined-table-constraints"></a>Restricciones de tablas definidas por el usuario
Una restricción de tablas definida por el usuario es un tipo de matriz que se usa para describir las combinaciones de los valores de atributos definidos mediante los tipos de atributo. Por ejemplo, si fabrica altavoces, puede incluir columnas para el acabado de la caja y la rejilla frontal en la restricción de tablas definida por el usuario. El tipo de atributo para el acabado de la caja tiene cuatro valores, y el tipo de atributo para la rejilla delantera tiene tres valores. Por lo tanto, si no se usan restricciones, existen las combinaciones posibles 4 × 3 = 12. Sin embargo, en este ejemplo, únicamente hay seis combinaciones posibles, tal y como se muestra en la siguiente tabla. Esta información se muestra en la ficha **Combinaciones permitidas** de la página **Editar restricción de tabla**.

| Acabado de la caja | Rejilla delantera |
|----------------|-------------|
| Negro          | Negro       |
| Negro          | Metálico       |
| Roble            | Negro       |
| Palisandro       | Blanco       |
| Blanco          | Negro       |
| Blanco          | Blanco       |

Las restricciones de tablas definidas por el usuario se definen mediante entradas de tabla estática que funciona del mismo modo que una restricción de expresión. Al usar una restricción de tablas definida por el usuario, la ventaja es que las tablas suelen ser más fáciles de crear, comprender y mantener que las restricciones de expresión largas.

## <a name="system-defined-table-constraints"></a>Restricciones de tablas definidas por el sistema
Una restricción de tabla definida por el sistema crea una asignación dinámica entre un tipo de atributo y un campo en una tabla. Cuando una restricción de tabla definida por el sistema se incluye en un modelo de configuración de productos, la asignación garantiza que se mostrarán los datos de la tabla en lugar de los valores del tipo. El resultado es una restricción dinámica, porque el contenido de la tabla se puede modificar (por ejemplo, mediante otros módulos).  

Cuando se crea una restricción de tabla definida por el sistema, se selecciona una tabla, se define opcionalmente la consulta que se debe usar y luego se asocian tipos de atributo a los campos de la tabla seleccionada. Los tipos de campos deben coincidir con los tipos de atributo.  

Para que una restricción de tablas pueda surtir efecto en un modelo de configuración de productos, la restricción de tabla se debe incluir en una restricción en uno de los componentes del modelo. El procedimiento es crear una nueva restricción, seleccionar el tipo de restricción de tabla y seleccionar la definición de la restricción de tabla que usar. Por último, todos los campos de la restricción de tabla se deben asignar a atributos en el modelo de configuración de productos.

<a name="see-also"></a>Consulte también
--------

[Conceptos clave en los modelos de configuración de productos](product-configuration-models.md)




