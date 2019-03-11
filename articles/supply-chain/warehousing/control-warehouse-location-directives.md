---
title: Controlar el trabajo de almacén usando plantillas de trabajo y directivas de ubicación
description: Este tema describe cómo usar plantillas de trabajo y directivas de ubicación para determinar cómo y dónde se realiza el trabajo en el almacén.
author: perlynne
manager: AnnBe
ms.date: 09/21/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSLocDirFailure, WHSLocDirHint, WHSLocDirTable, WHSLocDirTableUOM, WHSRFMenuItem, WHSWork, WHSWorkClass, WHSWorkPool, WHSWorkTemplateTable
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 72921
ms.assetid: 377ab8af-5b0c-4b5e-a387-06ac1e1820c0
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 74e7c36fb912f35252d6e40d17477ac2962cbc23
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/29/2019
ms.locfileid: "325420"
---
# <a name="control-warehouse-work-by-using-work-templates-and-location-directives"></a>Controlar el trabajo de almacén usando plantillas de trabajo y directivas de ubicación

[!include [banner](../includes/banner.md)]

Este tema describe cómo usar plantillas de trabajo y directivas de ubicación para determinar cómo y dónde se realiza el trabajo en el almacén.

Las instrucciones que los trabajadores de almacén reciben en un dispositivo móvil están determinadas por las plantillas de trabajo que se configura en Microsoft Dynamics 365 for Finance and Operations para definir los distintos procesos y tareas de almacén. Las plantillas de trabajo determinan cómo se realiza el trabajo para cada proceso de almacén. Si vincula un directorio de ubicación a plantillas de trabajo, puede ayudar a garantizar que el trabajo se produce en áreas físicas específicas de los almacenes.

## <a name="work-templates"></a>Plantillas de trabajo
La página **Plantillas de trabajo** le permite definir las operaciones de trabajo que se deben realizar en el almacén. Normalmente, las operaciones de trabajo del almacén constan de un par de acciones: un trabajador de almacén recoge inventario disponible en una ubicación y después pone el inventario seleccionado en otra ubicación. 

Las plantillas de trabajo constan de un encabezado y las líneas asociadas. Cada plantilla de trabajo es para un determinado *tipo de pedido de trabajo*. Muchos tipos de pedido de trabajo están asociados con los documentos de origen, como pedidos de ventas o compras. Sin embargo, otros tipos de pedido de trabajo representan procesos independientes de almacén, como recuento cíclico. El *id. del grupo de trabajo* le permite organizar el trabajo en grupos. 

Los ajustes en la definición del encabezado del trabajo se pueden usar para determinar cuándo se debe crear un nuevo elemento de trabajo. Por ejemplo, puede establecer un número máximo de líneas de selcción y un máximo previsto de tiempo de selección. Luego, si el trabajo para un proceso de selección de un pedido de ventas supera cualquiera de estos valores, el trabajo se divide en dos partes. 

Las líneas de trabajo representan las tareas físicas que son necesarias para procesar el trabajo. Por ejemplo, para un proceso de salida de almacén, puede haber una línea de trabajo para seleccionar los artículos dentro del almacén y otra línea para configurar dichos artículos en una zona de espera. Después, puede haber una línea adicional para seleccionar los artículos provisionales de la zona de espera, y otra línea para poner los artículos en un camión como parte del proceso de carga. Puede establecer unn *código directivo* en líneas de la plantilla de trabajo. Un código directivo está vinculado a una ubicación directiva y, por tanto, ayuda a garantizan que el trabajo del almacén se ha procesado en la ubicación correcta en el almacén. 

Puede configurar una consulta para controlar si se usa una determinada plantilla de trabajo. Por ejemplo, puede establecer una limitación para poder utilizar una determinada plantilla solo para el trabajo en un almacén específico. Como alternativa, puede tener varias plantillas que se usan para crear el trabajo para procesar pedidos de venta salientes, en función del origen de venta. El sistema usa el campo **Número de secuencia** para determinar el orden en que las plantillas de trabajo disponibles son evaluadas. Por lo tanto, si tiene una consulta muy específica para una determinada plantilla de trabajo, debe darle un número de secuencia bajo. Dicha consulta se evaluará antes que otras consultas más generales. 

Para detener o poner en pausa un proceso de trabajo, puede usar la configuración **Detener trabajo** en la línea de trabajo. En ese caso, no se le solicitará al trabajador que se está realizando el trabajo que realice la siguiente etapa de trabajo. Para pasar al siguiente paso, dicho trabajador u otro trabajador debe seleccionar el trabajo de nuevo. También puede separar las tareas dentro de un elemento de trabajo mediante un *id. de clase de trabajo* diferente en las líneas de la plantilla de trabajo.

## <a name="location-directives"></a>Directivas de ubicación
Las directivas de ubicación son reglas que ayudan a identifica las ubicaciones de picking y de colocación para el movimiento de inventario. Por ejemplo, en una transacción de pedido de ventas, una directiva de ubicación determina dónde se hará el picking de los artículos y dónde se colocarán los artículos seleccionados. Los directorios de la ubicación constan de un encabezado y las líneas asociadas, y se crean en la página **Directorios de ubicación**. 

En el encabezado, cada directorio de ubicación se debe asociar a un *tipo de pedido de trabajo* que especifica el tipo de transacción de inventario para el cual el directorio se usará, como pedidos de ventas, reabastecimiento o selección de la materia prima. El *tipo de trabajo* especifica si el directorio de la ubicación se usará para seleccionar o colocar el trabajo, o para otro proceso de almacén, como cómputo o cambios de estado del inventario. También debe especificar un *sitio* y un *almacén*. Un *código directivo* que se especifica en el encabezado se puede usar para vincular el directorio de la ubicación a una o varias plantillas de trabajo. 

En cuanto a plantillas de trabajo, puede configurar una consulta para determinar cuándo se usa un directorio concreto de la ubicación. Por ejemplo, puede especificar que cuando el comercio electrónico es el origen de un pedido de ventas, el inventario se debe seleccionar en un área dedicada en el almacén. El sistema usa el campo **Número de secuencia** para determinar el orden en que las directivas disponibles de la ubicación son evaluadas. 

Las líneas directivas de la ubicación establecen restricciones adicionales en la aplicación de las reglas de búsqueda de la ubicación. Puede especificar una cantidad mínima y una cantidad máxima en las que el directorio se debe basar, y puede especificar que el directorio debe ser para una unidad de inventario específica. Por ejemplo, si la unidad de medida es pallets, entonces los artículos en pallets se pueden colocar en una ubicación concreta. También puede especificar si la cantidad se puede dividir entre varias ubicaciones. Como el encabezado de la directiva de ubicación, cada línea directiva de la ubicación tiene un número de secuencia que determina la orden en que las líneas se evalúan. 

Las directivas de la ubicación tienen un nivel de detalle adicional: *acciones de la directiva de la ubicación*. Puede definir varias acciones de las directivas de la ubicación para cada línea. De nuevo, se usa un número de secuencia para determinar el orden en que se evalúan las acciones. En este nivel, puede configurar una consulta para definir cómo encontrar la mejor ubicación en el almacén. También puede usar una configuración de **Estrategia** predefinida para encontrar una ubicación óptima.

## <a name="location-directives-configuration-details"></a>Detalles de configuración de las directivas de la ubicación 

 ### <a name="sequence-number"></a>Número de secuencia
 
Este número indica la secuencia en la que se debe procesar una directiva de ubicación para un tipo de pedido seleccionado. Es posible cambiarla con **Subir** y **Bajar** en el menú.
 
 ### <a name="work-type"></a>Tipo de trabajo
 
Este es el tipo de trabajo que se debe realizar. El tipo de trabajo está disponible según el tipo transacción de inventario seleccionada en el campo **Tipo de solicitud de trabajo**.
-   **Colocar** Tipo de trabajo igual a **Colocar** significa que la directiva de la ubicación va a encontrar la ubicación más adecuada para configurar o colocar el inventario que entra en el sistema, ya sea desde recepciones, producción o ajustes de inventario. También se puede usar para definir una colocación en una ubicación de la etapa o en una ubicación de envío de compuerta final.
-   **Seleccionar**: Un tipo de trabajo igual a **Seleccionar** significa que el almacén va a encontrar la ubicación ideal para reservar físicamente inventario desde (crear trabajo). La selección se podrá completar (la línea de trabajo de la selección se puede cerrar), incluso si el trabajo no se completa. El usuario puede completar la recogida física, que es un paso de la selección. El usuario puede cancelar entonces desde un dispositivo móvil y completar el trabajo posteriormente. Sin embargo, la cabecera del trabajo se cierra cuando la colocación final se completa. 
-   **Recuento, ajustes, personalizar, cambio de estado de inventario, creación de matrículas de entidad de almacén, impresión, cambio de estado, paquete a matrículas de entidad de almacén anidadas** - No se pueden usar en ninguna configuración de la directiva de la ubicación. Esto es una enumeración de modo que no hay ningún filtro conectado al tipo de pedido del trabajo. 

### <a name="directive-code"></a>Código de directiva

Seleccione el código de directiva que se debe asociar a una plantilla de trabajo o de reabastecimiento. En el formulario **Código de la directiva** puede crear nuevos códigos que se pueden usar para las conexiones entre una plantilla de reabastecimiento de la plantilla de trabajo y una directiva de la ubicación. Esto se puede usar también para establecer el vínculo entre cualquier línea de plantilla de trabajo y cualquier directiva de ubicación (como baydoor o ubicación de la etapa).

Tenga en cuenta que si se establece el código, cuando se genera trabajo el sistema no buscará la directiva de la ubicación por secuencia, la búsqueda se realizará por código de directiva. Esto significa que puede ser más específico sobre qué plantilla de ubicación se usa para determinado paso de una plantilla de trabajo, como el ensayo de material. 

### <a name="site"></a>Sitio

El sitio es un campo obligatorio porque la directiva de la ubicación requiere el sitio y el almacén para la que es válida. 

### <a name="warehouse"></a>Almacén

El almacén es un campo obligatorio porque la directiva de la ubicación requiere el sitio y el almacén para la que es válida.

### <a name="multiple-sku"></a>Varios SKU

Esto permite que haya numerosas referencias de almacén (SKU) en una ubicación, como el baydoor. Si se selecciona **SKU múltiple**, la ubicación de colocación se especifica en el trabajo (lo que se espera), pero solo podrá gestionar la colocación de varios artículos (si el trabajo incluye la selección y colocación de varias SKU y no de una sola SKU). Si no selecciona **SKU múltiple**, la ubicación de colocación solo se especificará si la colocación solo tiene un tipo de SKU. Para utilizar ambas acciones, debe especificar dos líneas, una con varias SKU activadas y otra con varias SKU desactivadas. Tienen que tener la misma estructura y configuración. Para las operaciones de colocación, debe tener directivas de la ubicación que sean idénticas, aunque usted no distinga entre SKU únicas y SKU numerosas en el identificador de trabajo. También debe configurar la selección, si tiene un pedido con más de un artículo.

### <a name="sequence-number"></a>Número de secuencia

Especifique la secuencia en la que se procesa la línea de la directiva de ubicación para el tipo de trabajo seleccionado. También puede modificar la secuencia, si es necesario, usando **Subir** y **Bajar**.

### <a name="fromto-quantity"></a>Desde/Hasta cantidad

Esto ofrece la capacidad de especificar un intervalo de cantidades en los casos en que debe seleccionarse la secuencia de la cuadrícula del medio. Puede especificar el intervalo Desde/Hasta en la Cantidad en la unidad respectiva.

### <a name="unit"></a>Unidad

Puede especificar una cantidad mínima y una cantidad máxima en las que el directorio se debe basar, y puede especificar que el directorio debe ser para una unidad de inventario específica. El campo de la unidad en la línea solo se usa para la evaluación de la cantidad.

Al comprobar si la línea directiva de la ubicación es aplicable, esto se basará en la cantidad en la unidad respectiva especificada en la línea directiva de la ubicación. Cada vez que se alcance una línea directiva de la ubicación, el sistema intentará convertir la unidad de la demanda en una unidad especificada en la línea. Si no existe la conversión de UOM, continuará en la línea siguiente. 

### <a name="locate-quantity"></a>Cantidad para localizar

Esta opción solo se usa para la cantidad de colocación/ubicación en el almacén. Es solo para el tipo de trabajo de colocación. Son válidos los siguientes valores:

-   **Cant. de matrícula de entidad de almacenes** - Al evaluar si la cantidad está dentro de los intervalos "Desde" y "Hasta", utilice la cantidad de la matrícula de entidad de almacenes que se recibe.
-   **Cantidad dividida en unidades** - Al evaluar si la cantidad está dentro de los intervalos "Desde" y "Hasta", utilice la cantidad que se divide en unidades durante la transacción específica.
-   **Cantidad restante** - Al evaluar si la cantidad está dentro de los intervalos de cantidades "Desde” y "Hasta", use la cantidad que queda por recibir en la línea de pedido de compra que se está registrando actualmente.
-   **Cantidad esperada** - Al evaluar si la cantidad está dentro de los intervalos de cantidades "Desde” y "Hasta", use la cantidad total de la línea de pedido de compra, sea cual sea la cantidad que ya se haya recibido.

### <a name="restrict-by-unit"></a>Restringir por unidad

Esto permite que una línea directiva de la ubicación se realice específicamente en una unidad de medida o varias unidades de medida. Al reservar una cantidad, si solo desea reservar pallets de un conjunto concreto de ubicaciones, la secuencia de la cuadrícula media limitaría esa secuencia en concreto a "PL" de modo que toda cantidad inferior a un pallet no seleccionase la secuencia. Seleccione **Restringir por unidad** para configurar las unidades. También puede limitar la línea a más de una unidad. Esto solo funciona con directivas de la ubicación del tipo picking. 

### <a name="round-up-to-unit"></a>Redondear por arriba a unidad

Este campo funciona junto con el campo **Restringir por unidad**. Si la línea directiva de la ubicación **Restringir por unidad** se establece en "carcasa", seleccionar **Redondear hasta unidad** indica que el trabajo generado por la directiva para la selección de la materia prima se debe redondear a un múltiplo de una unidad de manipulación (especificada en **Restringir por unidad**). Tenga en cuenta que esto solo funciona para la selección de materias primas y solo con directivas de la ubicación de la selección del tipo.

### <a name="locate-packing-qty"></a>Localizar cantidad de embalaje

Si una cantidad de embalaje se especifica en un pedido de ventas, un pedido de transferencia, o un pedido de producción, esto limita el sistema a seleccionar solo ubicaciones con una cantidad de embalaje en la ubicación. Esto solo funciona con directivas de la ubicación del tipo picking.

### <a name="allow-split"></a>Permitir división

Esto especifica si se permite a una directiva de la ubicación dividir la cantidad que se recibe o se reserva entre varias ubicaciones de almacén, o si la cantidad completa debe estar ubicada en una sola ubicación o reservada en una sola ubicación para crear el trabajo. 

### <a name="sequence-number"></a>Número de secuencia

Est número es la secuencia en la que se debe procesar la directiva de ubicación para el tipo de trabajo seleccionado. Si fuera necesario, puede modificar la secuencia. Sin embargo, sea prudente al usar los números de secuencia, ya que el procesamiento siempre se ejecutará en secuencia. 

### <a name="name"></a>Nombre

Especifique un nombre para la acción de la directiva de ubicación. Asegúrese de ser específico al especificar un nombre.

### <a name="fixed-location-usage"></a>Uso de ubicaciones fijas 

-   **Ubicaciones fijas y no fijas** - La directiva de la ubicación tendrá en cuenta todas las ubicaciones.
-   **Solo ubicaciones fijas para el producto** - La directiva de la ubicación tendrá en cuenta solo las ubicaciones fijas de los productos.
-   **Solo ubicaciones fijas para la variante del producto** - La directiva de la ubicación tendrá en cuenta solo las ubicaciones fijas para las variantes de productos.

### <a name="allow-negative-inventory"></a>Permitir inventario negativo

Active esta opción para permitir inventario negativo en la ubicación de almacén especificada en las directivas de ubicación. 

### <a name="batch-enabled"></a>Habilitado para lotes 

Seleccione esta opción para usar estrategias de lote para los artículos habilitados para lotes. Si se logra una línea donde **Lote habilitado** se establece sin ningún artículo de lote, el proceso continuará en la línea de acción siguiente. 

### <a name="strategy"></a>Estrategia

-   **Consolidar**: Esta estrategia se usa para consolidar artículos en una ubicación concreta cuando ya hay disponibles artículos similares. Esto solo funciona para el tipo de colocación de directiva de ubicación. Una configuración habitual de la colocación será consolidar en la primera línea de acción y, en el segundo intento, consolidar sin colocación. La consolidación de mercancías hace más eficiente la selección posterior.
-   **Cantidad de embalaje de coincidencia** - Esta estrategia se usa para comprobar si una ubicación de picking tiene la cantidad de embalaje especificada. Esto solo funcionará con directivas de ubicación del tipo picking. 
-   **Reserva de lote FEFO**: esta estrategia se usa cuando el inventario se localiza mediante una fecha de vencimiento de lote y se asigna para la reserva de lotes. Esta estrategia solo se puede usar para artículos habilitados para lotes. Esto solo funciona para una directiva de ubicación de tipo de trabajo de picking. 
-   **Redondear por arriba hasta matrícula de entidad de almacén completa** - Esta estrategia se usa para redondear hacia arriba la cantidad de inventario de modo que coincida con la cantidad de matrícula de entidad de almacén (LP) asignada a los artículos que se van a seleccionar. Solo puede usar esta estrategia para el tipo de reabastecimiento de directiva de ubicación del tipo picking. 
-   **Ubicación en blanco sin trabajo entrante**: se usa para localizar ubicaciones vacías. La ubicación se considera como vacía si no tiene ningún inventario físico y ningún trabajo entrante previsto. Esta estrategia se usa solo para un tipo de colocación de directiva de la ubicación. 

### <a name="example-of-the-use-of-location-directives"></a>Ejemplo del uso de las directivas de la ubicación

En este ejemplo, considere un proceso de pedido de compra en el que la directiva de la ubicación debe encontrar capacidad libre dentro de un almacén para los artículos de inventario que acaban de registrarse en el muelle de recepción. Primero, tiene que encontrar capacidad libre dentro del almacén consolidando con el inventario disponible. Si la consolidación no es posible, tendrá que encontrar una ubicación vacía. 

Para esta situación, tiene que definir dos acciones de la directiva de la ubicación. La primera acción de la secuencia debe ser usar la estrategia **Consolidar**, y la segunda debería ser la estrategia **Vaciar la ubicación sin trabajo entrante**. A menos que defina una tercera acción para gestionar una situación de desbordamiento, dos resultados son posibles si no hay capacidad en el almacén: el trabajo puede ser creado aunque no se define ninguna ubicación o el proceso de creación de trabajo puede fallar. El resultado viene determinado por la configuración en la página **Fallos de la directiva de la ubicación**, donde puede decidir si seleccionar la opción **Detener trabajo si falla la directiva de la ubicación** para cada tipo de pedido de trabajo.
