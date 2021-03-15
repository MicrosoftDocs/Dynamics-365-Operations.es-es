---
title: Visión general de los modelos de configuración de productos
description: En este artículo se definen los términos y conceptos relevantes para los modelos de configuración de productos. Los modelos de configuración de productos permiten crear una estructura de producto genérico que se puede utilizar para configurar muchas variantes de producto para un solo producto.
author: cvocph
manager: tfehr
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: PCProductConfigurationModelDetails, PCProductConfigurationModelListPage, PCModalWaitDialog, PCTemplateConfigurationManager, PCConfigurationUIGrouping
audience: Application User
ms.reviewer: kamaybac
ms.custom: 4031
ms.assetid: 70b968e8-e550-4731-823d-d713b8910f7b
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: e82eb3fcfe4347b7faa4c775e9909a792e2b9baf
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/15/2021
ms.locfileid: "4983325"
---
# <a name="product-configuration-models-overview"></a>Visión general de los modelos de configuración de productos

[!include [banner](../includes/banner.md)]

En este artículo se definen los términos y conceptos relevantes para los modelos de configuración de productos. Los modelos de configuración de productos permiten crear una estructura de producto genérico que se puede utilizar para configurar muchas variantes de producto para un solo producto.

Los modelos de configuración de productos se crean para representar una estructura de producto genérica. Tras configurar un modelo de configuración de productos, puede configurar una variante única de producto que tenga una lista de materiales (L. MAT.) y una ruta únicas. Los modelos de configuración de producto utilizan restricciones declarativas y cálculos obligatorios para gestionar las relaciones y las limitaciones entre distintas variantes de producto. Puede configurar los artículos en los pedidos de ventas, presupuestos de ventas, pedidos de compra y pedidos de producción. En la tabla siguiente se describen los conceptos y términos basados en restricciones de tabla.
<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td>Componentes</td>
<td>Los componentes son los componentes básicos principales de un modelo de configuración de productos. Los componentes se muestran en una estructura de árbol en la página <strong>Detalles del modelo de configuración de productos basados en restricciones</strong>. Los componentes pueden contener los siguientes elementos:
<ul>
<li>Atributos</li>
<li>Restricciones</li>
<li>Cálculos</li>
<li>Subcomponentes</li>
<li>Requisitos de usuario</li>
<li>Líneas de L. MAT</li>
<li>Operaciones de ruta</li>
</ul></td>
</tr>
<tr class="even">
<td>Atributos</td>
<td>Los atributos describen todas las características del modelo de configuración de productos. Puede usar atributos para especificar las características que se pueden seleccionar cuando se configura un producto único. Los atributos se usan en restricciones y condiciones. Cuando los atributos se crean y se agregan a un modelo de configuración de productos, se hace referencia a los tipos de atributos relacionados. Un valor predeterminado se puede establecer para un atributo. El valor predeterminado se usa en la interfaz de usuario (IU) de configuración cuando se configura el modelo de configuración de productos. Puede especificar que un atributo es obligatorio, de solo lectura u oculto.
<ul>
<li><strong>Obligatorio</strong>: se debe establecer un valor para el atributo cuando se configura el producto.</li>
<li><strong>Solo lectura</strong>: el valor del atributo se muestra durante una sesión de configuración, pero no se puede modificar.</li>
<li><strong>Oculto</strong>: el valor del atributo se incluye en restricciones y condiciones, pero no se muestra durante una sesión de configuración.</li>
</ul>
También puede especificar una condición para los atributos. Si se cumple la condición, se debe especificar un valor para el atributo obligatorio. Las condiciones son las expresiones que se deben cumplir para que se incluyan los atributos, las líneas de L. MAT y las operaciones de ruta en un modelo de configuración de productos. Todo atributo al que se haga referencia en una condición pasará a ser obligatorio. Le recomendamos que seleccione los atributos como opción obligatoria en la pestaña <strong>Atributos</strong>, para que así sea más fácil identificar los atributos obligatorios. Los valores de atributos forman una parte importante de la reutilización de las configuraciones. El sistema usa valores de atributo para determinar si existe una configuración que coincida con las selecciones que un usuario ha realizado durante una sesión de configuración.</td>
</tr>
<tr class="odd">
<td>Tipos de atributo</td>
<td>Los tipos de atributo especifican el conjunto de tipos de datos para atributos que se usan en un modelo de configuración de productos. Se usan los siguientes tipos de atributo:
<ul>
<li><strong>Entero</strong> con o sin un rango</li>
<li><strong>Decimal</strong></li>
<li><strong>Texto</strong> con o son una lista fija</li>
<li><strong>Booleano</strong></li>
</ul>
Si el tipo de atributo es <strong>Booleano</strong>, <strong>Entero</strong> con rango, o <strong>Texto</strong> con una lista fija, el conjunto de valores está disponible cuando se configura un modelo de configuración de productos. <strong>Nota:</strong> el solucionador de configuraciones de productos reconoce solo los tipos de atributos siguientes: <strong>Booleano</strong>, <strong>Texto</strong> con una lista fija y <strong>Entero</strong> con un rango. Por lo tanto, solo se pueden usar estos tipos de atributo en condiciones y restricciones de expresión.</td>
</tr>
<tr class="even">
<td>Restricciones</td>
<td>Las restricciones describen las restricciones de la configuración del modelo de producto. Las restricciones se usan para garantizar que solo se seleccionan los valores válidos cuando se está configurando un producto. Las restricciones pueden ser restricciones de expresión o restricciones de tabla:
<ul>
<li>Las restricciones de expresión se pueden usar solamente para el componente con el que están relacionados. Las restricciones de expresión de un componente pueden hacer referencia a los atributos de los subcomponentes del componente. El solucionador de configuraciones de productos se usa para resolver restricciones, y el usuario debe usar la sintaxis del solucionador para escribir las restricciones. Para obtener más información, consulte el vínculo del tema sobre restricciones de expresiones y de tabla.</li>
<li>Las restricciones de tabla deben definirse antes de poder aplicarse a un componente en un modelo de configuración de productos. Las restricciones de tabla pueden ser definidas por el usuario o definidas por el sistema. Una restricción de tabla definida por el usuario es un tipo de matriz que se puede usar para describir el conjunto de combinaciones de los valores de atributos definidos por los tipos de atributo. Por ejemplo, si se producen altavoces, la matriz para la restricción de tabla definida por el usuario puede tener columnas para el acabado del altavoz y la rejilla.</li>
</ul>
<strong>Ejemplo</strong> Los altavoces están disponibles en cuatro acabados: negro, roble, palisandro y blanco. Los altavoces pueden tener una de tres rejillas delanteras: negro, metálico o blanco. El acabado en negro está disponible para todas las rejillas, pero los otros acabados están limitados a rejillas específicas. La tabla siguiente muestra un ejemplo de la información que se muestra en la ficha <strong>Combinaciones permitidas</strong> de la página ficha de la página <strong>Editar restricción de tabla</strong>.
<table>
<thead>
<tr class="header">
<th>Acabado de la caja</th>
<th>Rejilla delantera</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Negro</td>
<td>Negro</td>
</tr>
<tr class="even">
<td>Negro</td>
<td>Metálico</td>
</tr>
<tr class="odd">
<td>Negro</td>
<td>Blanco</td>
</tr>
<tr class="even">
<td>Roble</td>
<td>Negro</td>
</tr>
<tr class="odd">
<td>Palisandro</td>
<td>Blanco</td>
</tr>
<tr class="even">
<td>Blanco</td>
<td>Negro</td>
</tr>
<tr class="odd">
<td>Blanco</td>
<td>Blanco</td>
</tr>
</tbody>
</table>
Una restricción de tabla definida por el sistema representa una asignación entre un tipo de atributo y un campo en una tabla de Supply Chain Management. Una restricción de tabla definida por el sistema vincula dinámicamente el tipo de atributo al campo. El vínculo permite al atributo en un modelo de configuración de productos reflejar los datos del campo en la tabla de Supply Chain Management.</td>
</tr>
<tr class="odd">
<td>Cálculos</td>
<td>Los cálculos representan un suplemento a las restricciones. Puede usar un cálculo para realizar operaciones aritméticas de tipo <strong>Decimal</strong> y <strong>Entero</strong>, u operaciones lógicas que impliquen atributos de <strong>Texto</strong> con una lista fija y tipos <strong>Booleano</strong>. Un cálculo tiene un atributo de destino que guardará el resultado de la expresión de cálculo. La expresión de cálculo se crea mediante el editor de expresiones.</td>
</tr>
<tr class="even">
<td>Subcomponentes</td>
<td>Los subcomponentes reflejan la estructura de árbol del modelo de configuración de productos. Puede usar subcomponentes para crear la estructura del modelo de configuración de productos. Los subcomponentes hacen referencia a los componentes existentes. Por lo tanto, los subcomponentes promueven la reutilización de componentes en varios modelos de configuración de productos. En la página <strong>Detalles de línea de L. MAT.</strong> para un subcomponente, puede seleccionar un valor único para el subcomponente. También puede seleccionar un atributo para el que se seleccione el valor cuando se configure el modelo de configuración de productos. Para incluir un producto como componente o subcomponente, debe especificar la siguiente información en la página<strong> Crear producto</strong> al crear el producto:
<ul>
<li>En el campo <strong>Tipo de producto</strong>, seleccione <strong>Artículo</strong>.</li>
<li>En el campo <strong>Subtipo de producto</strong>, seleccione <strong>Producto maestro</strong>.</li>
<li>En el campo <strong>Tecnología de configuración</strong>, seleccione <strong>Configuración basada en restricciones</strong>.</li>
</ul>
Puede ver si se puede usar un producto emitido como componente o subcomponente en la ficha <strong>General</strong> de la página <strong>Detalles de producto emitido</strong>. Si <strong>Configuración basada en restricciones</strong> se ha seleccionado en el campo <strong>Tecnología de configuración</strong>, el producto se puede usar como componente o subcomponente. Puede ocultar subcomponentes para que no le aparezcan al usuario durante una sesión de configuración. También se ocultan los atributos, los subcomponentes y los requisitos de usuario que están relacionados con el subcomponente.</td>
</tr>
<tr class="odd">
<td>Requisitos de usuario</td>
<td>Los requisitos de usuario representa una abstracción entre los requisitos de usuario y los componentes y los atributos específicos. No es posible asignar un requisito de usuario a un artículo. Por ejemplo, un cliente compra un sistema de centro de entretenimiento. El representante de ventas podría preguntar el tamaño de la sala donde el cliente piensa instalar el sistema, a fin de determinar cuántos vatios se requieren. En este ejemplo, el tamaño de la sala puede ser un requisito de usuario que ayuda a determinar el valor de atributo adecuado para un componente específico. Puede ocultar los requisitos de usuario para que no le aparezcan al usuario durante una sesión de configuración. También se ocultan los atributos, los subcomponentes y los requisitos de usuario que están relacionados con el requisito de usuario. Puede escribir una condición para controlar si se puede ocultar un requisito de usuario. Debe escribir la condición con la sintaxis del lenguaje de modelado de optimización (OML).</td>
</tr>
<tr class="even">
<td>Líneas de L. MAT</td>
<td>Las líneas de L. MAT representan los materiales individuales de los componentes del modelo de configuración de productos. En la página <strong>Detalles de línea de L. MAT.</strong>, todos los artículos están disponibles para seleccionarse. Se puede agregar una condición a la línea de lista de materiales de modo que las líneas de lista de materiales seleccionadas para una variante de producto único pueden variar, en función de la selección del usuario cuando se configura el modelo de configuración de productos. Las condiciones son las expresiones que se deben cumplir para que se incluyan los atributos, las líneas de L. MAT y las operaciones de ruta en un modelo de configuración de productos. En la página <strong>Detalles de línea de L. MAT.</strong> puede seleccionar un valor distinto. También puede asignar un atributo para el cual se seleccione el valor cuando se configure el modelo de configuración de productos.</td>
</tr>
<tr class="odd">
<td>Operaciones de ruta</td>
<td>En la página <strong>Detalles de operación de ruta</strong> puede seleccionar un valor distinto. También puede asignar un atributo para el cual se seleccione el valor cuando se configure el modelo de configuración de productos. Las condiciones se escriben como restricciones de expresión. Las condiciones son las expresiones que se deben cumplir para que se incluyan los atributos, las líneas de L. MAT y las operaciones de ruta en un modelo de configuración de productos.</td>
</tr>
</tbody>
</table>







[!INCLUDE[footer-include](../../includes/footer-banner.md)]