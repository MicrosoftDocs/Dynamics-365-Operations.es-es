---
title: "Crear un modelo de configuración de productos"
description: "La necesidad de configurar los productos para cumplir los requisitos especiales se está convirtiendo en la regla en lugar de la excepción, en las relaciones interempresariales y de banca B2C."
author: YuyuScheller
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: PCProductConfigurationModelDetails
audience: Application User
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 75083
ms.assetid: f08072b8-cb0b-43aa-9509-f5ec32caecd9
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: yuyus
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: 869151f2486b7a481e4694cfb6992d0ee2cfc008
ms.openlocfilehash: 5bc19e95266e8f1bec8744da688387dca559373f
ms.contentlocale: es-es
ms.lasthandoff: 06/13/2017


---

# Crear un modelo de configuración de productos
<a id="build-a-product-configuration-model" class="xliff"></a>

[!include[banner](../includes/banner.md)]


La necesidad de configurar los productos para cumplir los requisitos especiales se está convirtiendo en la regla en lugar de la excepción, en las relaciones interempresariales y de banca B2C.

Un fabricante que admite escenarios de configurar a pedido tiene una oportunidad de atender más atentamente a las necesidades del cliente. Además, almacenando mercancías semielaboradas en el formulario de componentes genéricos en lugar del de los productos terminados, el fabricante puede reducir el capital vinculado al inventario.  

Un movimiento correcto de una configuración de las fabricación a existencias a una configuración de configurar a pedido requiere el análisis cuidadoso de las estructuras del producto, la identificación de familias de productos y el componentization. Para reducir el número de piezas y minimizar el número de artículos que están en proceso, es muy importante que se entiendan las interfaces de producto y que ha diseñado para la reutilización.  

Hay varios principios de modelo de configuración de productos, como modelo según las reglas, la dimensión y la limitación. Los estudios muestran que la metodología basada en limitaciones puede reducir el número de líneas del código de modelos por el ajuste de 50 por ciento en comparación con otros principios de modelos. Por lo tanto, esta metodología puede reducir el coste total de la propiedad (TCO). Pasando de un modelo basado en reglas que se basa en el código X++ a un modelo basado en restricciones, deja de ser necesaria una licencia de desarrollador para mantener los modelos de producto.

## Configuración del producto
<a id="product-configuration" class="xliff"></a>
El período de la industrialización ha llevado a grandes logros en producir productos de alta calidad y con muchas características en los precios asequibles. Las economías de escala han hecho posible que la mayoría de las personas en el mundo industrializado compren vehículos, televisiones, aparatos electrodomésticos y otras mercancías que la mayor parte de nosotros consideramos una parte necesaria de nuestra vida cotidiana.  

A medida que muchos productos se han convertido en lujos, se ha creado una necesidad de diferenciarlos. La respuesta inmediata de los fabricantes a este desafío ha sido crear variantes de cada producto, de modo que los clientes tienen más alternativas. Esta estrategia ha llevado a desafíos crecientes de previsión, y también a un aumento de coste de inventario y productos invendidos que se vuelven obsoletos.  

Adoptando una filosofía de configurar a pedido, los fabricantes tienen una oportunidad de satisfacer la demanda del cliente para los productos únicos mientras que reducen o eliminan los artículos de inventario obsoletos. Cuando una filosofía de fabricación a existencias se desplaza a una filosofía de configurar a pedido, un desafío inmediato que aparece es que la necesidad de plazos cortos debe ser equilibrada con niveles de inventario bajos.  

La clave el éxito aquí es analizar atentamente la cartera del producto y buscar modelos de sus características de producto y procesos. El objetivo es identificar componentes genéricos que se pueden fabricar por mismo equipo y usar en todas las variantes.  

El nuevo sistema de características de la configuración de producto incluye una interfaz de usuario (UI) que proporciona una visión general gráfica de la estructura de modelo de configuración de productos, y también un sintaxis declarativo de restricción que no tiene que ser compilado. Por lo tanto, las empresas que desean admitir una práctica de configuración pueden empezar más fácilmente. Como explican las secciones siguientes, un diseñador de producto ya no necesita obtener ayuda de un desarrollador para crear un modelo de configuración de producto, probarlo y lanzarlo a la organización de ventas.

## Creación de un modelo de configuración de productos
<a id="building-a-product-configuration-model" class="xliff"></a>
Hay varios métodos que un usuario puede seguir para crear un modelo de configuración de productos. Una opción es realizar el seguimiento de un flujo secuencial primero creando todos los datos de referencia, como productos maestros, productos únicos y recursos operativos y, a continuación, incluirlos como componentes, líneas de la lista de materiales, operaciones de ruta y otros elementos del modelo de configuración de productos. Como alternativa, puede seleccionar un enfoque más iterativo primero creando el modelo y a continuación agregando datos de referencia al presentarse la necesidad.

### Componentes
<a id="components" class="xliff"></a>

Un modelo de configuración de productos está formado por uno o varios componentes asociados conjuntamente con relaciones del subcomponente. Los componentes se definen una vez y se pueden usar varias veces en uno o más modelos de configuración de productos. Los componentes son los componentes básicos principales de un modelo de configuración de producto, y casi toda la información acerca del modelo está relacionado con ellos.

### Atributos
<a id="attributes" class="xliff"></a>

Cada componente tiene uno o varios atributos que identifica sus propiedades. Los atributos son los que los usuarios eligen durante el proceso de configuración. Los atributos controlan las relaciones de entre componente e intra componente a través de la inclusión en restricciones o cálculos. Con las condiciones que se aplican a las líneas de L. MAT, los atributos se pueden usar para determinar de qué partes físicas consistirá el producto configurado. Además, un atributo puede controlar la propiedad de la línea de L. MAT a través de un mecanismo de asignación. La función similar existe para las operaciones de ruta en relación con la configuración de la inclusión y la propiedad.

### Restricciones de expresión
<a id="expression-constraints" class="xliff"></a>

Use un modelo de configuración de productos basado en limitaciones implica que existen algunas limitaciones cuando el usuario selecciona valores para los distintos atributos. Tales limitaciones se pueden ejecutar como restricciones de expresión usando el idioma de modelo de optimización (OML). Como alternativa, una restricción se puede ejecutar en forma de restricción de tabla.

### Restricciones de tablas
<a id="table-constraints" class="xliff"></a>

Las restricciones de tabla pueden estar definidas por el usuario o por el sistema.  

Una restricción de tabla definida por el usuario es construida por el usuario. El usuario selecciona una combinación de tipos de atributo para representar las columnas de la tabla y luego especifica valores de los dominios de los tipos de atributo seleccionados para formar las filas de la restricción de tabla.  

Una restricción de tabla definida por el sistema se define seleccionando qué tabla de Microsoft Dynamics 365 for Finance and Operations se usará como una referencia y luego seleccionando los campos de esta tabla para formar las columnas de la restricción. Las filas de la restricción de tabla son las filas de la tabla de Finance and Operations que están presentes en el momento de la configuración.  

Una restricción de tablas se incluye en un modelo de configuración de productos al hacer referencia a la definición de la restricción de tabla y un seguimiento de los atributos relevantes en el modelo a las columnas de la restricción de tabla.

### Cálculos
<a id="calculations" class="xliff"></a>

Los cálculos representan un mecanismo para realizar operaciones aritméticas en un modelo de configuración. Por ejemplo, un cálculo puede determinar la duración de un elemento específico de materia prima o el tiempo de procesamiento para una operación de pulido. Los cálculos son imprescindible y determinan el valor para un atributo de destino después de todos los valores de atributo que se incluyen en la expresión de cálculo cuando está disponible.

### Subcomponentes
<a id="subcomponents" class="xliff"></a>

Los subcomponentes representan los nodos en la estructura del modelo de configuración de productos. Para cada relación del subcomponente, una referencia se debe especificar a un producto maestro que tenga la tecnología de configuración de variantes establecida en la configuración basada en restricciones.

### Requisitos de usuario
<a id="user-requirements" class="xliff"></a>

Un requisito de usuario tiene todos los componentes del subcomponente. La única diferencia es que un requisito de usuario no se limita a un producto maestro. El efecto práctico de esta diferencia es que las líneas de L. MAT o operación de ruta que se han definido en el contexto de un requisito de usuario están contraídos en la estructura o la ruta de L. MAT. del componente principal. Este comportamiento es similar al comportamiento de una L. MAT fantasma.

### Líneas de L. MAT
<a id="bom-lines" class="xliff"></a>

Las líneas de L. MAT se incluyen para identificar la L. MAT. de la fabricación para cada componente. Una línea de L. MAT debe hacer referencia a un artículo, y todas las propiedades de artículos se pueden establecer en un valor fijo o asignar a un atributo.

### Operaciones de ruta
<a id="route-operations" class="xliff"></a>

Las operaciones de ruta se incluyen para identificar la ruta de la fabricación. Una operación de ruta debe hacer referencia a una operación definida, y todas las propiedades de la operación se pueden establecer un valor fijo. Todas las propiedades excepto requisitos de recurso se pueden asignar a un atributo en lugar de un valor.

## Validación y prueba de un modelo de configuración de productos
<a id="validating-and-testing-a-product-configuration-model" class="xliff"></a>
La validación de un modelo de configuración de productos se puede producir en varios niveles en el modelo y puede por lo tanto cubrir varios ámbitos. El nivel inferior es para una única restricción de la expresión. En este caso, la validación la realizará normalmente el diseñador de producto para comprobar que la sintaxis de una expresión es correcto.  

Del mismo modo, una condición para una línea de L. MAT o una operación de ruta se puede validar de forma aislada.  

La validación también se puede realizar para una definición de la restricción de tabla definida por el usuario. En este caso, el usuario puede comprobar que los valores especificados para cada campo se encuentran dentro del dominio de los tipos de atributo correspondientes.  

Finalmente, la validación se puede realizar para que un modelo de configuración de producto completo compruebe que la sintaxis completo es correcta, y que se han respetado todas las convenciones de nomenclatura y de modelos.

### Prueba
<a id="testing" class="xliff"></a>

La prueba de un modelo es similar a ejecutar sesión real de configuración. El usuario puede ir a través de las páginas de la configuración y comprobar que la estructura del modelo admite el proceso de configuración. El usuario puede comprobar que los valores de atributos son correctos, y que las descripciones del atributo dirigirán al usuario para seleccionar los valores correctos. Finalmente, después de que una sesión de prueba se completa, el sistema intenta crear la L. MAT. y la ruta que se corresponde con los valores de atributo seleccionados, y enviar un mensaje de error si algo va mal.

### La página de configuración
<a id="the-configuration-page" class="xliff"></a>

Para navegar entre los componentes, haga clic en **Siguiente** o en un componente en el árbol de modelo de configuración de productos para establecer el foco en él.

## Finalizar un modelo para la configuración
<a id="finalizing-a-model-for-configuration" class="xliff"></a>
Cuando un modelo de configuración de productos está listo para ser usado en escenarios de configurar a pedido, una versión debe crearse. Sin embargo, existen varias opciones que pueden mejorar la experiencia de modelos.

### Interfaz de usuario
<a id="user-interface" class="xliff"></a>

La configuración de IU puede modificarse introduciendo grupos de atributos en uno o más subcomponentes. Tal agrupación puede resaltar las relaciones entre los atributos específicos y ayudar al usuario de configuración a identificar el área de producto que está actualmente en el foco.

### Plantillas
<a id="templates" class="xliff"></a>

Una o más plantillas de configuración se pueden crear para acelerar el proceso de configuración. Como alternativa, las plantillas se pueden crear para promocionar combinaciones específicas de atributos, como cuando una campaña de ventas se centra en un conjunto concreto de características de producto.

### Traducciones
<a id="translations" class="xliff"></a>

Si el producto es vendido en diferentes países y regiones, las traducciones se pueden crear para todo el texto que aparecerá en la configuración de IU. Este texto incluye campos no sólo de nombre y de visión general, pero también valores de texto de atributo.

### Versiones
<a id="versions" class="xliff"></a>

La última y más iportante de las etapas en el proceso de finalización es crear una versión del modelo de configuración de productos. La versión representa la relación entre el producto maestro, que puede ser seleccionado para la configuración en una línea de pedido o de presupuesto, y el modelo de configuración de productos. Una versión debe estar aprobada y activada para poder ser usada en una sesión de configuración.

## Ampliar un modelo de configuración de productos con el API
<a id="extending-a-product-configuration-model-through-the-api" class="xliff"></a>
Se ha ejecutado una interfaz de programación dedicado de aplicación (API), de modo que los socios y otros que tienen una licencia del desarrollador pueden ampliar las capacidades de un modelo de configuración de productos. El objetivo principal ha sido establecer un mecanismo que permita a asociados y clientes que usan el configurador de productos existente migrar el código incrustado en los modelos de configurador de productos a la API. De esta manera, pueden migrar sus modelos del configurador de productos a una configuración de producto. Sin embargo, los nuevos asociados y clientes también pueden beneficiarse del uso de API para expandir los nuevos modelos de configuración de productos.

### Clase de PCAdaptor
<a id="pcadaptor-class" class="xliff"></a>

El API se ejecuta mediante un sistema de clases de **PCAdaptor** que exponen la estructura de datos de los modelos de configuración de productos. Una instancia de la clase **PCAdaptor** debe crearse para cada modelo que se extiende. Una vez que una sesión de configuración esté completada, el sistema busca una instancia de este tipo y la ejecuta cuando la encuentra.  

En el diagrama de flujo siguiente se muestra el procesos.  

[![Diagrama de flujo](./media/product_configuration_2.png)](./media/product_configuration_2.png)  

Diagrama de flujo de la API de configuración de productos

## Configuración del producto
<a id="product-configuration" class="xliff"></a>
La configuración de producto se puede realizar desde los siguientes lugares:

-   Línea de pedido de ventas
-   Línea de presupuesto de ventas
-   Línea de pedido de compra
-   Línea de pedido de producción
-   Línea de requisitos de artículos (proyecto)

El propósito de la configuración es crear una variante distinta de producto que cumple el requisito de cliente. Una identificación única de la configuración se crea para cada nueva configuración. Este identificador habilita el seguimiento a través de inventario.

### Varios sitios y empresas vinculadas
<a id="multiple-sites-and-intercompany" class="xliff"></a>

Si la configuración se realiza en un sitio, o incluso una empresa, que es diferente del sitio o la empresa donde tendrá lugar la producción, la L. MAT. y la ruta se crearán para establecer en el sitio del proveedor en la empresa proveedora. La variante del producto se libera en todas las empresas que participan en la cadena de suministro.




