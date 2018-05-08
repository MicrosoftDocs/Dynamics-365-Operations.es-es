---
title: Equilibrio por lotes
description: En este tema se describe el proceso de equilibrio por lotes.
author: johanhoffmann
manager: AnnBe
ms.date: 03/15/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: BOMTable
audience: Application User
ms.reviewer: bis
ms.search.scope: Core, Operations
ms.custom: 1705903
ms.assetid: 427e01b3-4968-4cff-9b85-1717530f72e4
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 8.0.0
ms.translationtype: HT
ms.sourcegitcommit: a8b5a5af5108744406a3d2fb84d7151baea2481b
ms.openlocfilehash: 7d00df6263530ba9fff4c246cb3593cd607f6719
ms.contentlocale: es-es
ms.lasthandoff: 04/13/2018

---

# <a name="batch-balancing"></a>Equilibrio por lotes

[!include [banner](../includes/banner.md)]

En este tema se describe cómo se admite el proceso de equilibrio por lotes. 

Ver [vídeo sobre equilibrio por lotes en Microsoft Dynamics 365 for Finance and Operations](https://www.youtube.com/watch?v=4SNLWsU9KyI&feature=youtu.be)

En el proceso de equilibrio por lotes, la cantidad de ingredientes que va a utilizar en un lote de producción se calcula a partir de la concentración de ingredientes activos en lotes de producto seleccionados.

<a name="products-that-have-an-active-ingredient"></a>Productos que tienen un ingrediente activo
---------------------------------------

Un producto se puede definir por su concentración de un ingrediente activo. El ingrediente activo de un producto se modela mediante un atributo de lote especifico de un producto que tiene un valor mínimo, un valor máximo y un nivel objetivo.

El nivel objetivo de un atributo de lote representa el porcentaje estimado de un ingrediente activo de un producto. Los valores mínimo y máximo representan la desviación aceptada del nivel objetivo. Se pueden utilizar, por ejemplo, como una tolerancia aceptada para lotes en la recepción de producto.

Un producto solo puede tener un ingrediente activo. Para especificar el ingrediente activo de un producto, primero debe definir un atributo de lote específico del producto. A continuación, asocie el atributo como un atributo base del producto.

En el nivel de producto, también debe especificar cómo debe registrarse el nivel del ingrediente activo para un lote del producto: como parte del proceso de recepción de compra o como parte de un proceso de pedido de calidad.

Para asociar un atributo base a un producto, se requiere la siguiente configuración:

-   El producto debe estar controlado por lote. Para crear un producto controlado por lote, debe asignar a un grupo de dimensión de seguimiento al producto que tiene una dimensión del lote activo.

-   El atributo que indica los niveles del ingrediente se debe definir como un atributo de lote específico del producto para el producto.

Puede buscar y editar el valor real del ingrediente activo para un lote en la página **Atributos de lote de inventario**. 

-  Seleccione **Gestión del inventario** \> **Consultas e informes** \> **Dimensiones de seguimiento** \> **Lotes** \> **Atributos de lote de inventario**.

<a name="ingredient-types-and-how-they-interact-in-the-batch-balancing-process"></a>Tipos del ingrediente y cómo interactúan en el proceso de equilibrio por lotes
---------------------------------------------------------------------

Una línea de fórmula que se crea puede tener uno de estos tipos de ingredientes:

-   Sin ordenar

-   Activos

-   Compensando

-   Relleno

El resto de esta sección proporciona ejemplos que muestran cómo funciona cada tipo de ingrediente. Los ejemplos se basan en la siguiente fórmula con un tamaño de lote total de 100 litros.

| **Tipo de ingrediente** | **Código de artículo** | **Cantidad de línea de fórmula** | **Unidad** |
|---------------------|-----------------|---------------------------|----------|
| Sin ordenar                | C               | 20                        | Litro    |
| Activos              | B               | 30                        | Litro    |
| Compensando        | C               | 10                        | Litro    |
| Relleno              | J               | 40                        | Litro    |

### <a name="active"></a>Activos

Cuando un producto con un atributo base se agrega a una línea de fórmula, se conoce como *ingrediente activo* de la fórmula. Los pedidos de lote con fórmulas que incluyen ingredientes activos se pueden usar para el proceso de equilibrio por lotes. Para cada ingrediente de la fórmula, el proceso de equilibrio por lotes calcula la cantidad necesaria para generar el producto. La estimación de cantidades se basa en la concentración de ingredientes activos en los lotes seleccionados.

**Ejemplo**

El ingrediente B tiene el atributo base X y un nivel objetivo de 30, y se incluye en una fórmula que requiere 30 litros de ingrediente B por cada 100 litros del producto. Se crea un pedido de lote con un tamaño de lote de 100 litros. Se inicia el pedido de lote, y durante el proceso de equilibrio por lotes, el usuario selecciona un lote de ingrediente B con un nivel de potencia de 35. Puesto que el nivel de potencia de 35 es mayor que el nivel objetivo de 30, la cantidad equilibrada de ingrediente B se reduce mediante el coeficiente de valor de potencia para el nivel objetivo del lote, que se multiplica por la cantidad estimada. El cálculo de la cantidad equilibrada tiene este aspecto:

(30 ÷ 35) × 30 litros = 25,71 litros

| **Código de artículo** | **Tipo de ingrediente** | **Cantidad estimada** | **Cantidad equilibrada** | **Cantidad activa** | **Unidad** | **Valor base** |
|-----------------|---------------------|------------------------|-----------------------|---------------------|----------|----------------|
| C               | Sin ordenar                | 20                     | 20                    |                     | Litro    |                |
| B               | Activos              | 30                     | 25,71                 | 9,00                | Litro    | 30,00          |
| C               | Compensando        | 10                     | 14,72                 |                     | Litro    |                |
| J               | Relleno              | 40                     | 39,57                 |                     | Litro    |                |

### <a name="none"></a>Sin ordenar

Al aplicar el proceso de equilibrio por lotes cuando el tipo del ingrediente es **Ninguno**, la cantidad estimada y la cantidad equilibrada de la línea de fórmula en el pedido de lote son iguales.

**Ejemplo**

El ingrediente A se asigna a un ingrediente del tipo **Ninguno** y se agrega a una fórmula para un producto terminado. La fórmula requiere 10 litros del ingrediente A por cada 100 litros de producto terminado. Cuando un pedido de lote requiere 200 litros, la cantidad estimada y la cantidad equilibrada del ingrediente A se calculan como 20 litros.

### <a name="compensating"></a>Compensando

Un ingrediente de compesación puede compensar o complementar el efecto del ingrediente activo de un producto. Por lo tanto, la cantidad de un ingrediente de compesación que se consume depende de la potencia del producto:

-   **Efecto de oposición**: si la cantidad de ingrediente activo es mayor que la anticipada, debe agregar menos ingrediente de compensación.

-   **Efecto complementario**: si la cantidad de ingrediente activo es menor que la anticipada, debe agregar más ingrediente de compensación.

La relación entre un ingrediente activo y un ingrediente complementario se configura en la página **Principio de compensación**.

Siga estos pasos para configurar las relaciones entre ingredientes.

1.  Seleccione **Gestión de información de productos** \> **Facturas y materiales y fórmulas** \> **Fórmulas**, abra una línea de fórmula y, a continuación, seleccione **Ingredientes** para abrir la página **Principio de compensación**.

2.  Seleccione la línea que representa un principio de compensación y, a continuación, seleccione el ingrediente activo que desea compensar.

>   En el principio de compensación, introduzca también un factor de compensación positivo o negativo para especificar cuánto compensar y si el principio debe ser de oposición o complementario. Un factor positivo indica un efecto complementario y un factor negativo indica un efecto de oposición.

**Ejemplo**

El ingrediente B es un ingrediente activo que tiene el atributo base X y un nivel objetivo de 30. Se incluye una fórmula que requiere 30 litros de ingrediente B por cada 100 litros de producto. El ingrediente C es un ingrediente de compensación y se incluye una cantidad de 10 en la misma fórmula. Se configura un factor de compensación de 1,10 para el principio de compensación. Por lo tanto, la cantidad equilibrada del ingrediente de compensación se reducirá por la diferencia entre la cantidad equilibrada del ingrediente activo y la cantidad necesaria estimada multiplicada por 1,10.

En el ejemplo para el tipo de ingrediente **Activo**, la cantidad equilibrada del ingrediente activo requerido se calcula como 25,71 y la cantidad necesaria estimada se calcula como 30. En este caso, la cantidad equilibrada del ingrediente de compensación se calculará de la siguiente manera:

1.  La diferencia entre la cantidad estimada y equilibrada se determina:

>   25,71 – 30 = –4,29

2.  El resultado se multiplica por el factor de compensación.

>   4,29 × 1,10 = –4,72

3.  La cantidad de compensación estimada se reduce por –4,72 para determinar la cantidad de compensación equilibrada:

>   10 – (–4,72) = 14,72

Puesto que 1,10 es un factor de compensación positivo, este principio de compensación tiene un efecto complementario. En este caso, el ingrediente activo es más potente de lo esperado. Por lo tanto, se requiere más del ingrediente de compensación.

### <a name="filler"></a>Relleno

Un *ingrediente de relleno* es un ingrediente neutral que se usa para lograr la cantidad de salida deseada del producto terminado. Los ajustes de las cantidades de relleno se calculan en función de variaciones en el ingrediente activo y el ingrediente de compensación en comparación con la cantidad estándar.

**Ejemplo**

Ha formulado un producto que incluye los ingredientes A, B, C y D para un tamaño de fórmula de 100 litros. Ha calculado la cantidad equilibrada de todos los tipos de ingredientes, excepto el tipo de ingrediente **Relleno** que se usa en una línea.
La cantidad equilibrada del ingrediente de relleno se calcula como la diferencia entre el tamaño de lote de 100 litros y la suma de ingredientes A, B y C:

100 – (20 + 25,71 + 14,72) = 39,57

<a name="the-batch-balancing-process"></a>El proceso de equilibrio por lotes
---------------------------

El proceso de equilibrio por lotes se realiza desde la página **Equilibrio por lotes** .
Seleccione **Gestión de costes** \> **Pedidos de lote** y, a continuación, en la pestaña **Proceso**, seleccione **Equilibrio por lotes**. El equilibrio por lotes está disponible para los pedidos por lote que tengan un estado **Iniciado**.

En general, el equilibrio por lotes se puede aplicar a pedidos de lote si la fórmula tenga al menos una línea de fórmula en la que el tipo de ingrediente es **Activo**. (Para la excepción a esta regla, consulte la sección "Pedidos de lote que no son aplicables para el equilbrio por lotes" más adelante en este tema.)

El proceso de equilibrio por lotes se puede dividir en dos subprocesos:

1.  Equilibrar ingredientes del lote

2.  Confirmar y liberar la fórmula

### <a name="balance-batch-ingredients"></a>Equilibrar ingredientes del lote

En el subproceso Equilibrar ingredientes del lote, la cantidad de ingredientes que va a utilizar para el lote de producción se calcula a partir de los lotes seleccionados que tienen ingredientes activos. Como norma, el cálculo se puede completar si hay una cobertura total de todos los ingredientes. No puede equilibrar solo una parte del lote que está configurada para producir el pedido de lote.

[!NOTE]
No puede guardar un cálculo y completar posteriormente el proceso de equilibrio por lotes. Si cierra la página **Equilibrio por lotes**, debe repetir el cálculo para completar el proceso.

### <a name="confirm-and-release-the-formula"></a>Confirmar y liberar la fórmula

Después de que se hayan calculado las cantidades de los ingredientes, puede confirmar y liberar la fórmula. El proceso de lanzamiento varía en función de si los productos están habilitados para los procesos de gestión de almacenes:

-   Si un producto está habilitado para los procesos de gestión de almacenes, la línea de fórmula se libera al almacén según los principios para los procesos de gestión de almacenes. La línea de fórmula se libera en cantidades que coinciden con las cantidades equilibradas, y se libera para los lotes específicos que se seleccionan para los ingredientes activos.

> [!NOTE]
>   Las líneas de fórmula se pueden liberar al almacén solo como parte del proceso de equilibrio por lotes. Aunque haya otras opciones para liberar materiales para la producción al almacén, esas opciones no se pueden usar para las líneas de fórmula.

-   Si un producto no está habilitado para los procesos de gestión de almacenes, se crea una lista de selección de producción para el producto cuando confirma y libera la fórmula.

En una fórmula única, puede combinar productos que están habilitados para los procesos de gestión de almacenes y productos que no están habilitados para los procesos de gestión de almacenes. Cuando se incluyen los dos tipos de productos en una fórmula, los productos que se habilitan para los procesos de gestión de almacenes se liberan al almacén. Para los productos que no están habilitados para los procesos de gestión de almacenes, se crea una lista de selección cuando se confirma y libera la fórmula.

### <a name="batch-orders-that-arent-applicable-for-batch-balancing"></a>Pedidos de lote que no se aplican al equilibrio por lotes

Existe una excepción a la regla de que los pedidos de lote se pueden aplicar al equilibrio por lotes si la fórmula tiene al menos una línea de fórmula en la que el tipo de ingrediente es **Activo**.

Si una fórmula contiene un ingrediente activo para un producto que está habilitado para los procesos de gestión de almacenes, pero el número de lote está debajo de la ubicación en la jerarquía de reservas, el pedido de lote no se aplica al equilibrio por lotes.

Un pedido de lote que no se aplica al equilibrio por lotes pasa por el ciclo de proceso habitual para los pedidos de lote.

