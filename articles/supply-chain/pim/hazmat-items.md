---
title: Materiales peligrosos en productos, pedidos, envíos y cargas
description: Este tema explica cómo establecer las propiedades de los materiales peligrosos para los productos despachados, cómo establecer límites de existencias para los artículos peligrosos y cómo incluir materiales peligrosos en un pedido de venta, envío o carga.
author: dasani-madipalli
manager: tfehr
ms.date: 06/10/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: damadipa
ms.search.validFrom: 2020-06-10
ms.dyn365.ops.version: Release 10.0.11
ms.openlocfilehash: 3836273b1c782fe80172443f4d4c29001ccea83a
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/15/2021
ms.locfileid: "5007675"
---
# <a name="hazardous-materials-in-products-orders-shipments-and-loads"></a>Materiales peligrosos en productos, pedidos, envíos y cargas

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

Este tema explica cómo establecer las propiedades de los materiales peligrosos para los productos despachados, cómo establecer límites de existencias para los artículos peligrosos y cómo incluir materiales peligrosos en un pedido de venta, envío o carga.

## <a name="set-hazardous-material-specifications-for-products"></a>Establecer especificaciones de materiales peligrosos para productos

Después de haber definido una regulación de materiales peligrosos y configurado los códigos de referencia relacionados como se describe en [Configurar materiales peligrosos](hazmat-setup.md), puede asociar esta información con artículos despachados. El texto del envío de los documentos de envío se extraerá de la información sobre materiales peligrosos de los artículos despachados.

Como parte del proceso de asociar un artículo despachado con un material peligroso, debe especificar el código de regulación y el material. Se pueden asociar diferentes códigos de reglamentación con un artículo, según los modos de transporte, y puede asociar múltiples reglamentaciones y códigos de material a cada artículo.

Para configurar un producto despachado como material peligroso, siga estos pasos.

1. Vaya a **Gestión de información de productos \> Productos \> Productos despachados**.
1. Seleccione o cree un producto para abrir su página **Detalles de producto**.
1. En la ficha desplegable **Administrar inventario**, configure la opción **Material peligroso** en **Sí**. Esta configuración identifica el artículo como mercancía peligrosa y se utiliza cuando se imprime la documentación de envío.
1. En el Panel Acciones, en la pestaña **Administrar inventario**, en el grupo **Conformidad**, seleccione **Artículo de material peligroso**.
1. Complete la página **Artículo de material peligroso** para el elemento seleccionado utilizando los campos que se describen en las siguientes subsecciones.

### <a name="item-hazardous-materials-header"></a>Encabezado de artículo de material peligroso

La siguiente tabla describe los campos que están disponibles en la parte superior de la página **Artículo de material peligroso**.

| Campo | Descripción |
|---|---|
| código de artículo | El producto despachado con el que está trabajando. |
| Código normativo | Seleccione la regulación de materiales peligrosos que se aplica al producto. El reglamento define cómo se crea el texto de envío impreso para un artículo y los modos de entrega asociados. Una vez asignado, el código no se puede editar en esta página. Sin embargo, puede asignar un nuevo código de regulación seleccionando **Nuevo**. |
| Código de material | (Opcional) Seleccione el código de material peligroso que se aplica al producto. El código de material proporciona una plantilla que incluye valores predeterminados para muchos otros campos de esta página. Cuando selecciona un código, todas sus especificaciones de materiales peligrosos se copiarán en el producto actual. Sin embargo, el sistema primero le solicita que confirme que los datos del material del artículo deben completarse desde el código de material. |
| Código de grupo | (Opcional) Seleccione el código de grupo de clasificación de material peligroso que se aplica al producto. Respecto al campo **Código de material**, cuando selecciona un código, todas sus especificaciones de materiales peligrosos se copiarán en el producto actual. Sin embargo, el sistema primero le solicita que confirme que los datos de grupo de clase del artículo deben completarse desde el código de grupo. |

### <a name="descriptions-fasttab"></a><a name="hazmat-description"></a>Ficha desplegable Descripciones

En la tabla siguiente se describen los campos disponibles en la ficha desplegable **Descripciones**.

| Campo | Descripción |
|---|---|
| Nombre de envío correcto | Introduzca la descripción estándar para el material, según lo especificado por la regulación aplicable. Puede proporcionar traducciones para este valor en la ficha desplegable **Traducción del texto del envío del artículo**, como se describe en la siguiente sección. |
| Nombre técnico | Seleccione el nombre común o genérico del material. Este nombre puede ser un nombre que su empresa utiliza internamente para el material. |
| N.O.S. | Seleccione esta casilla de verificación para indicar que el valor **Nombre de envío adecuado** es un nombre de envío no específico (NOS) para el artículo. N.O.S. Los nombres de envío se utilizan para grupos de productos químicos y materiales similares que tienen usos finales específicos, pero que pueden no estar enumerados por su nombre en la tabla de materiales peligrosos de una regulación específica. |

### <a name="item-ship-text-translation-fasttab"></a>Ficha desplegable de traducción de texto de envío de artículos

La ficha desplegable **Traducción del texto del envío del artículo** contiene una cuadrícula que muestra traducciones de los valores **Nombre de envío adecuado** que se definen para el idioma principal en la ficha desplegable **Descripciones**. Estas traducciones se pueden utilizar en el envío de texto impreso para uno o más idiomas adicionales.

En la tabla siguiente se describen los campos disponibles en la ficha desplegable **Traducción de texto de envío de artículos**.


| Campo | Descripción |
|---|---|
| Idioma | El código de idioma que usa la fila. Por ejemplo, **pt-br** indica portugués brasileño. |
| Texto de impresión de envío | El valor traducido **Nombre de envío adecuado** en el idioma que usa la fila. |

Para agregar o editar una traducción, seleccione **Traducciones** sobre la rejilla para abrir la página **Traducciones**. Luego siga uno de estos pasos:

- En el Panel Acciones, seleccione **Agregar** para agregar una nueva traducción. Seleccione el idioma que desea agregar y luego, en el campo **Texto traducido**, introduzca el texto traducido.
- Para editar una traducción existente, seleccione un idioma de destino en el campo **Idioma** y edite el texto traducido en el campo **Texto traducido**, según sea necesario.

### <a name="material-management-fasttab"></a>Ficha desplegable <a name="material-management"></a>Gestión de materiales

En la tabla siguiente se describen los campos disponibles en la ficha desplegable **Gestión de materiales**.

| Campo | Descripción |
|---|---|
| Clase | Seleccione la clase de material peligroso a la que pertenece el producto, según define la normativa a la que se ajusta. Debe asignar una división y una clase a cada producto que incluya materiales peligrosos. |
| Descripción | La descripción que se define para la clase que se selecciona en el campo **Clase**. Este campo es de sólo lectura. |
| División | Seleccione la división de material peligroso a la que pertenece el producto, según define la normativa a la que se ajusta. La división es un subconjunto de la clase. Debe asignar una división y una clase a cada producto que incluya materiales peligrosos. |
| Identificación | Seleccione el código de identificación de material peligroso. Normalmente, este código se basa en un estándar de las Naciones Unidas (ONU). |
| Grupo de embalaje | Seleccione el grupo de embalaje que se aplica al artículo actual. |
| Descripción | La descripción que se define para el grupo que se selecciona en el campo **Grupo de embalaje**. Este campo es de sólo lectura. |
| Descripciones de embalaje | Seleccione el código de descripción de embalaje aplicable. Este código hace referencia a una descripción que indica cómo se debe empaquetar el producto. |
| Etiquetas de materiales peligrosos | Seleccione un código que haga referencia a la etiqueta de mercancías peligrosas correspondiente que debe aplicarse al producto. |
| Cantidad limitada | Establezca esta opción en **Sí** para informar el peso total del producto que se incluye en cada carga y en cada línea de carga. |
| Cantidad | Introduzca la cantidad de material peligroso en el producto, en la unidad especificada. Este valor se utilizará para calcular la puntuación total de materiales peligrosos para cargas y envíos que incluyen el producto. |
| Multiplicador | Introduzca el multiplicador que se aplica cuando se calcula la puntuación de material peligroso para cada línea de carga que incluye el producto. Este valor está especificado por la normativa aplicable, de acuerdo con el tipo de material peligroso que contiene el producto. |
| Unidad | Seleccione la unidad de medida que se aplica a la cantidad de material peligroso en el producto, como se especifica en el campo **Cantidad**. Este valor se utilizará para calcular la puntuación total de materiales peligrosos para cargas y envíos que incluyen el producto. |

#### <a name="how-the-hazardous-material-score-is-calculated"></a>Cómo se calcula la puntuación de material peligroso

Varios de los valores que se especifican en la ficha desplegable **Gestión de materiales** de un producto se utiliza para calcular una *puntuación de material peligroso* para cada línea de carga que incluye ese producto. La puntuación se calcula mediante la fórmula siguiente:

Puntuación de material peligroso = *&lt;LineQty&gt;* × *&lt;HazmatQty&gt;* × *&lt;UnitConversion&gt;* × *&lt;Multiplicador&gt;*

Esta es una explicación de la fórmula:

- *&lt;LineQty&gt;* es la cantidad de producto que se especifica para una línea de carga.
- *&lt;HazmatQty&gt;* es la cantidad de material peligroso que se especifica para un producto en el campo **Cantidad** de la ficha desplegable **Gestión de materiales**.
- *&lt;UnitConversion&gt;* es un factor de conversión para convertir entre la unidad que se utiliza para la cantidad de la línea de carga y la unidad que se especifica para un producto en el campo **Unidad** de la ficha desplegable **Gestión de materiales**.
- *&lt;Multiplicador&gt;* es el multiplicador que se especifica para un producto en el campo **Multiplicador** de la ficha desplegable **Gestión de materiales**.

Esta puntuación se notifica para cada línea de carga que contiene un producto donde se especifican estos valores. Para obtener más información, consulte las secciones [Envíos que incluyen materiales peligrosos](#hazmat-shipments) y [Cargas que incluyen materiales peligrosos](#hazmat-loads) posteriores de este tema.

#### <a name="how-the-hazardous-material-weight-is-calculated"></a>Cómo se calcula el peso del material peligroso

Las cargas y líneas de carga que contienen productos donde la opción **Cantidad limitada** de la ficha desplegable **Gestión de materiales** está establecida en **Sí** mostrarán el peso total del material peligroso, como se describe en las secciones [Envíos que incluyen materiales peligrosos](#hazmat-shipments) y [Cargas que incluyen materiales peligrosos](#hazmat-loads) posteriores de este tema. El peso del material peligroso se calcula mediante la fórmula siguiente:

Peso del material peligroso = *&lt;LineQty&gt;* × *&lt;ProductWeight&gt;* × *&lt;UnitConversion&gt;*

Esta es una explicación de la fórmula:

- *&lt;LineQty&gt;* es la cantidad de producto que se especifica para una línea de carga.
- *&lt;ProductWeight&gt;* es el peso neto que se especifica para el producto, en la unidad de inventario que se especifica para el producto.
- *&lt;UnitConversion&gt;* es un factor de conversión para convertir entre la unidad que se usa para la cantidad de la línea de carga y la unidad de inventario que se usa para *&lt;ProductWeight&gt;*.

### <a name="transport-information-fasttab"></a>Ficha desplegable Información de transporte

En la tabla siguiente se describen los campos disponibles en la ficha desplegable **Información de transporte**.

| Campo | Descripción |
|---|---|
| Categoría de transporte | Seleccione la categoría de transporte relacionada. |
| Código de túnel | Seleccione el código de restricción de túnel relacionado para el artículo. |
| Estiba de material peligroso | Seleccione el código de referencia que se utiliza para el manejo de la estiba del flete marítimo cuando el artículo se envía por flete marítimo. |
| Tipo de avión | Seleccione la restricción de aeronave que se aplica al material cuando se envía por transporte aéreo. |
| Embalaje: solamente avión de carga | Según el valor seleccionado en el campo **Tipo de aeronave**, seleccione el código de instrucciones de embalaje que se aplica cuando el producto solo puede enviarse por avión de carga. |
| Embalaje: avión de pasajeros y carga | Según el valor seleccionado en el campo **Tipo de aeronave**, seleccione el código de instrucciones de embalaje que se aplica cuando el producto solo puede enviarse por avión de carga o pasajeros. |
| IATA Star | Establezca esta opción en **Sí** para indicar que las especificaciones de transporte aéreo que se introducen en esta ficha desplegable están relacionadas con el estándar de mercancías peligrosas de la Asociación Internacional de Transporte Aéreo (IATA). La finalidad de este campo es meramente informativa. |
| Respuesta de emergencia | Seleccione el código que hace referencia a las instrucciones para manipular el material en caso de emergencia. |

### <a name="environmental-information-fasttab"></a>Ficha desplegable de información medioambiental

En la tabla siguiente se describen los campos disponibles en la ficha desplegable **Información medioambiental**.

| Campo | Descripción |
|---|---|
| Peligroso para el medio ambiente | Establezca esta opción en **Sí** para indicar que el producto es peligroso para el medioambiente. Utilice este campo para sus propios informes. |
| Contaminante marino | Establezca esta opción en **Sí** para indicar que el producto es contaminante marino. Utilice este campo para sus propios informes. |

## <a name="set-stock-limits-for-hazardous-products"></a><a name="stock-limits"></a>Establecer límites de existencias de productos peligrosos

Por razones de seguridad, es posible que deba limitar la cantidad total de un producto determinado que se puede mantener en existencias en un solo lugar. Para establecer límites de existencias para un producto despachado, siga estos pasos.

1. Vaya a **Gestión de información de productos \> Productos \> Productos despachados**.
1. Seleccione un producto para abrir su página **Detalles de producto despachado**.
1. En el Panel Acciones, en la pestaña **Administrar inventario**, en el grupo **Cumplimiento**, seleccione **Detalles de informes**.
1. En los campos **Límite de existencias peligrosas** y **Límite de advertencia de peligro**, establezca los valores adecuados para el producto seleccionado.

El informe **Límite de existencias de materiales peligrosos** le permite monitorear los niveles de existencias de los materiales peligrosos en las ubicaciones de su almacén, para asegurarse de que permanezcan por debajo de los límites de seguridad que se establecen aquí. Para más información, consulte [Informe de límite de existencias de materiales peligrosos](hazmat-reports.md#stock-limit-report).

## <a name="sales-order-transactions-that-include-hazardous-materials"></a>Transacciones de pedidos de venta que incluyen materiales peligrosos

Para incluir un producto clasificado como material peligroso en un pedido de venta, debe asociar el transportista de envío relevante con el pedido de venta. Abra el pedido de venta y luego, en la ficha desplegable **Entrega**, establezca los campos **Transportista de envío** y **Servicio de transportista** según sea necesario.

El identificador del transportista también está asociado al modo de entrega. Por lo tanto, debe asegurarse de que esta información esté alineada con la regulación de materiales peligrosos. En otras palabras, el modo de entrega que se especifica en la regulación de materiales peligrosos debe coincidir con las especificaciones en el encabezado del pedido de venta. De esta manera, la regulación, el transportista y el servicio están conectados a las líneas de envío que se utilizan en un pedido de venta.

Una vez finalizado un pedido de venta y listo para enviarse, se puede enviar al almacén para indicar la transferencia entre las operaciones de venta y de almacén.

## <a name="shipments-that-include-hazardous-materials"></a><a name="hazmat-shipments"></a>Envíos que incluyen materiales peligrosos

### <a name="view-hazardous-material-scores-for-each-shipment-line"></a>Ver puntuaciones de materiales peligrosos para cada línea de envío

La página **Detalles del envío** de un envío muestra el peso total del material peligroso y los valores de puntuación que se han calculado para cada línea de carga que se incluye en ese envío. Para ver las puntuaciones y los pesos, siga estos pasos.

1. Vaya a **Gestión de almacenes \> Envíos \> Todos los envíos**.
1. Seleccione un envío para abrir su página **Detalles de envío**.
1. En la pestaña **Líneas de carga**, inspeccione las líneas. Para cada línea, verá los cálculos de materiales peligrosos en los siguientes campos:

    - **Puntos de materiales peligrosos**: este campo muestra la puntuación de materiales peligrosos para la línea de carga. El valor se calcula de acuerdo con las reglas y valores que se han establecido según la normativa aplicable y en la configuración de producto enviada. El cálculo toma la cantidad de la línea de carga y hace referencia al multiplicador de la [configuración de gestión de materiales](#material-management) para el producto despachado.
    - **Cantidad limitada de peso neto**: para los productos que están marcados como productos de cantidad limitada debido a su contenido de material peligroso, este campo muestra el peso neto total del contenido peligroso que se incluye en la línea de carga. El cálculo se basa en los productos que están marcados como materiales peligrosos en la configuración del producto despachado. Si un artículo está marcado como un artículo de cantidad limitada, el cálculo toma la cantidad de cada línea de carga y hace referencia al peso de la [configuración de gestión de materiales](#material-management) para el producto despachado.

### <a name="check-for-compatibility-among-hazardous-materials-that-are-included-in-a-shipment"></a>Compruebe la compatibilidad entre los materiales peligrosos que se incluyen en un envío

El sistema puede evaluar si todos los materiales peligrosos que se incluyen en un envío son adecuados para enviarse juntos. Para evaluar la compatibilidad, el sistema verifica el grupo de compatibilidad que se asigna a cada producto que se incluye en el envío. Para más información, consulte [Grupos de compatibilidad de materiales peligrosos](hazmat-setup.md#compatibility-groups).

Para ejecutar la comprobación de compatibilidad, siga estos pasos.

1. Vaya a **Gestión de almacenes \> Envíos \> Todos los envíos**.
1. Seleccione un envío para abrir su página **Detalles de envío**.
1. En el Panel Acciones, en la ficha **Envíos**, en el grupo **Acciones**, seleccione **Comprobación de compatibilidad**.

Recibe un mensaje que le informa de los resultados de la comprobación.

## <a name="loads-that-include-hazardous-materials"></a><a name="hazmat-loads"></a>Cargas que incluyen materiales peligrosos

### <a name="view-hazardous-material-scores-for-each-load-line"></a>Ver las puntuaciones de materiales peligrosos para cada línea de carga

La página **Detalles de carga** de una carga muestra el peso total del material peligroso y los valores de puntuación que se han calculado para esa carga y para cada línea de carga. Para ver las puntuaciones y los pesos, siga estos pasos.

1. Vaya a **Gestión de almacenes \> Envíos \> Todas las cargas**.
1. Seleccione una carga para abrir su página **Detalles de carga**. (También puede abrir los detalles de la carga seleccionando un vínculo de un envío relacionado).
1. En la ficha desplegable **Carga**, puede revisar las puntuaciones y los pesos totales de materiales peligrosos para toda la carga, inspeccionando los siguientes campos:

    - **Puntos de materiales peligrosos**: este campo muestra la puntuación de materiales peligrosos de la carga. El valor se calcula de acuerdo con las reglas y valores que se han establecido según la normativa aplicable y en la configuración de producto enviada. El cálculo toma la cantidad incluida en la carga y hace referencia al multiplicador de la [configuración de gestión de materiales](#material-management) para el producto despachado.
    - **Cantidad limitada de peso neto**: para los productos que están marcados como productos de cantidad limitada debido a su contenido de material peligroso, este campo muestra el peso neto total del contenido peligroso que se incluye en la carga. El cálculo se basa en los productos que están marcados como materiales peligrosos en la configuración del producto despachado. Si un artículo está marcado como un artículo de cantidad limitada, el cálculo toma la cantidad de cada carga y hace referencia al peso de la [configuración de gestión de materiales](#material-management) para el producto despachado.

1. Para revisar las puntuaciones y los pesos de líneas individuales, seleccione la ficha desplegable **Líneas de carga**. Los valores que se proporcionan para cada línea se parecen a los valores que se proporcionan para toda la carga, como se describe en el paso anterior.

### <a name="check-for-compatibility-among-hazardous-materials-that-are-included-in-a-load"></a>Comprobar la compatibilidad entre los materiales peligrosos que se incluyen en una carga

El sistema puede evaluar si todos los materiales peligrosos que se incluyen en una carga son adecuados para enviarse juntos. Para evaluar la compatibilidad, el sistema comprueba el grupo de compatibilidad que se asigna a cada producto que se incluye en la carga. Para más información, consulte [Grupos de compatibilidad de materiales peligrosos](hazmat-setup.md#compatibility-groups).

Para ejecutar la comprobación de compatibilidad, siga estos pasos.

1. Vaya a **Gestión de almacenes \> Envíos \> Todas las cargas**.
1. Seleccione un envío para abrir su página **Detalles de carga**. (También puede abrir los detalles de la carga seleccionando un vínculo de un envío relacionado).
1. En el Panel Acciones, en la pestaña **Cargas**, en el grupo **Acciones**, seleccione **Comprobación de compatibilidad**.

Recibe un mensaje que le informa de los resultados de la comprobación.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]