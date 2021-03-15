---
title: Grupos para cálculos de lista de materiales
description: Este artículo proporciona información acerca de los grupos de cálculo para listas de materiales y de cómo configurarlos. Para ejecutar un cálculo de L. MAT, debe configurar los grupos de cálculo y asignarlos a artículos individuales o establecer un grupo de cálculo predeterminado. La configuración del cálculo del grupo de cálculo se utiliza a continuación como valores predeterminados en la página Cálculo de L. MAT en el momento del cálculo de L. MAT.
author: AndersGirke
manager: tfehr
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: BOMCalcGroup, BOMCalcTable, BOMCalcTrans, InventItemPrice
audience: Application User
ms.reviewer: kamaybac
ms.custom: 94063
ms.assetid: 63e1b7dc-c2c5-41b0-81ed-e3e02d1b39e0
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 1978873601608b5d2b67fa4229f61afa46d7e5cb
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/15/2021
ms.locfileid: "5011906"
---
# <a name="bom-calculations-groups"></a>Grupos de cálculo de lista de materiales

[!include [banner](../includes/banner.md)]

Este artículo proporciona información acerca de los grupos de cálculo para listas de materiales y de cómo configurarlos. Para ejecutar un cálculo de L. MAT, debe configurar los grupos de cálculo y asignarlos a artículos individuales o establecer un grupo de cálculo predeterminado. La configuración del cálculo del grupo de cálculo se utiliza a continuación como valores predeterminados en la página Cálculo de L. MAT en el momento del cálculo de L. MAT. 

Se requiere un grupo de cálculo predeterminado en la página **Parámetros de gestión de inventario y almacenes** o un grupo de cálculo específico de producto en la página **Detalles de producto emitido**. El sistema busca primero la configuración del grupo de cálculo en la página **Detalles de producto emitido**. Si no encuentra un grupo de cálculo allí, busca en la página **Parámetros de gestión de inventario y almacenes**. Si el sistema no encuentra un grupo de cálculo, el usuario recibe un mensaje de error durante el cálculo. Un grupo de cálculo contiene directivas para el modelo de precio de coste, el modelo de precio de venta y la lista de comprobación de las advertencias. La configuración del cálculo del grupo de cálculo se utiliza como valores predeterminados en la página **Cálculo de L. MAT** en el momento del cálculo de L. MAT.

## <a name="purposes-of-bom-calculation-groups"></a>Propósitos de los grupos de cálculo de L. MAT
Asigne un grupo de cálculo de L. MAT a artículos por varios motivos:

-   Al establecer el campo **Modelo de precio de coste**, indica el origen de los datos de contribución de costes de un componente adquirido durante el cálculo del coste planificado de un artículo fabricado. Algunos fabricantes calculan los costes planificados mediante los acuerdos comerciales de precio de compra de los componentes adquiridos u otra base de coste, como los registros de precios de compra de la versión de gestión de costes.
-   Al establecer el campo **Modelo del precio de ventas**, indicar cómo se utilizan los datos del artículo para calcular un precio de venta recomendado. Puede especificar el precio de venta del artículo o el grupo de costes. Algunos fabricantes desean calcular el precio de venta recomendado para los artículos fabricados. El precio de venta calculado puede reflejar el método de valoración de precio de coste medio que se basa en el registro de precios de venta de los componentes. De forma alternativa, el precio de venta calculado puede reflejar método de valoración de coste más un margen que se basa en el coste del componente y el porcentaje de ganancias aplicable, que se asocia al grupo de costes del artículo.
-   Al usar el campo **Detener la expansión**, indica que un artículo fabricado debe considerarse como un artículo comprado para acumulación de costes en los cálculos de L. MAT. Los escenarios típicos incluyen cuando los artículos comprados son, en ocasiones, fabricados o cuando los artículos fabricados se adquieren actualmente. Inicialmente, se designará el artículo como un artículo fabricado con el fin de definir la información de L. MAT. y de ruta, así como para admitir los pedidos de producción en relación con el artículo. Sin embargo, la marca **Detener la expansión** impide que los cálculos de costes utilicen la L. MAT y ruta del artículo. En su lugar, el cálculo de L. MAT utiliza los costes especificados de los artículos.

## <a name="calculation-groups"></a>Grupos de cálculo
Los grupos de cálculo se definen en **Configuración de directivas de coste predeterminado** en Gestión de costes. Los grupos de cálculo que se asignan a artículos le permiten especificar cómo se origina para el cálculo el coste o el precio de venta de los componentes, como se describe en el grupo de cálculo. En la página **Grupos de cálculo**, puede definir un modelo de precio de coste, un modelo de precio de coste alternativo, un modelo de precio de venta y advertencias.

### <a name="cost-price-model"></a>Modelo de precio de coste

Hay cuatro opciones para el campo **Modelo de precio de coste**:

-   **Precio de coste del artículo**: se utiliza el precio de coste de la tabla **Producto emitido** o la combinación de dimensiones de artículo como el precio de coste.
-   **Precio de compra del artículo**: se utiliza el precio de compra del campo **Precio de coste** de la pestaña **Compra** de la página **Lista de productos emitidos**.
-   **Acuerdos comerciales**: puede configurar los acuerdos comerciales para ciertas combinaciones de artículos y proveedores, o para sitios específicos. A continuación, al seleccionar aquí la opción **Acuerdos comerciales**, se usará el acuerdo comercial que se ha creado para el precio de compra junto con el elemento y el sitio.
-   **Precio de inventario**: el valor de inventario actual del artículo se utiliza para calcular el coste unitario en el cálculo de L. MAT. Un precio de coste unitario se calcula únicamente si la cantidad registrada y la cantidad física son superiores a 0 (cero).

### <a name="alternative-cost-price"></a>Precio de costes alternativo

El campo **Precio de costes alternativo** tiene las mismas opciones que el campo **Modelo de precio de coste**. Sin embargo, este campo se utiliza solo cuando no se encuentra un precio en el modelo de precio de coste principal.

### <a name="sales-price-model"></a>Modelo del precio de ventas

Hay dos opciones para el cálculo del campo **Precios de ventas**:

-   **Grupo de costes**: cuando se selecciona esta opción, el precio de venta se calcula en función del precio de coste y el porcentaje de configuración de ganancias del grupo de costes.
-   **Precio de venta del artículo**: al seleccionar esta opción, se usa el precio de ventas de la ficha desplegable **Vender** de la tabla Producto emitido.

### <a name="stop-explosion"></a>Detener la expansión

La casilla **Detener la expansión** se utiliza para indicar cuándo se debe tratar un artículo fabricado como un artículo de compra. Normalmente, dejará la casilla **Detener la expansión** desactivada. Al activar esta casilla, indica que un artículo fabricado se debe tratar como un componente de compra en lugar de componente fabricado para el cálculo de L. MAT. En función del sitio, el coste del artículo se puede calcular también mediante cálculos de L. MAT. La expansión pedidos de producción y pedidos de compra planificados se detiene en la lista de materiales cuyos componentes están asociados con el grupo de cálculo para el que está activada la casilla **Detener la expansión**. La programación maestra genera los pedidos planificados en la propia L. MAT, no en los artículos que se incluyen en la L. MAT. Básicamente, al activar esta casilla, se especifica que no se agregará un coste en el cálculo de L. MAT para los artículos con este grupo de cálculo.

### <a name="warnings"></a>Avisos

En la ficha desplegable **Advertencias**, se seleccionan las opciones de los mensajes de advertencia que los usuarios deben recibir cuando realizan cálculos de L. MAT. 

Por ejemplo, si activa la casilla **No hay L. MAT**, el usuario recibe una advertencia si no se encuentra ninguna versión de L. MAT activa para uno de los componentes o el producto principal para el que se ejecuta el cálculo de L. MAT. Si activa la casilla **No hay ruta**, el usuario recibe una advertencia si no se encuentra ninguna versión de ruta activa. Si utiliza recursos en sus rutas y operaciones, puede indicar al sistema que compruebe dichos recursos. A continuación, si no se encuentra un recurso en todas las líneas de la ruta activa, el usuario recibe una advertencia. 

También puede verificar y comprobar para el consumo. El consumo es la cantidad en una ruta determinada. Normalmente, representa la cantidad de tiempo necesaria para realizar una operación específica durante un proceso de producción. Puede comprobar si un artículo no tiene ningún precio de coste. Si no hay ningún precio de coste activo para un elemento, no se agrega ningún coste en el cálculo de L. MAT. 

También puede comprobar y verificar el vencimiento del precio de coste. Por ejemplo, escriba **60** para indicar que el precio de coste de unidad se debe volver a evaluar después de 60 días. Si se alcanza este límite, el sistema genera una advertencia. Por ejemplo, se introdujo un precio de coste para un artículo en enero de este año. Si ahora es agosto, lo que supone más de 60 días tras la introducción del precio de coste, el usuario recibe una advertencia cuando se ejecuta el cálculo de L. MAT. Puede especificar un porcentaje en el campo **Margen de contribución mínima**. Este valor indica el punto en el que no se cumple el margen de contribución mínima. Si no se cumple el margen de contribución para un componente concreto, el usuario recibe una advertencia. Por tanto, este campo ayuda a garantizar que no debilita los costes y la rotación adicional que se pueden requerir sus artículos.

### <a name="default-setup-in-inventory-and-warehouse-management-parameters"></a>Configuración predeterminada en los parámetros de gestión de almacenes

Dado que se requieren grupos de cálculo para poder ejecutar cálculos, debe configurar un grupo de cálculo predeterminado en los parámetros de Gestión de inventarios. Esta configuración permite a las empresas tener una configuración estándar de grupo de costes y ganancias para todos los artículos. A continuación, si un artículo concreto tiene requisitos de cálculo especiales, el usuario puede asignar a un grupo de cálculo diferente a ese artículo. Normalmente, puede establecer grupos de cálculo en artículos del componente de la L. MAT en lugar de los artículos de la L. MAT. Sin embargo, cuando se muestran mensajes de advertencia, se pueden aplicar grupos de cálculo. Un grupo de cálculo que está asignado a artículos reemplaza el valor predeterminado que se configura en los parámetros de Gestión de inventarios. 

Puede configurar el parámetro predeterminado en **Gestión de costes** &gt; **Configuración de directivas de contabilidad de inventario** &gt; **Parámetros** &gt; **Contabilidad de inventario** &gt; **Grupo de cálculo**. Al establecer una configuración de grupo de configuración predeterminado, también puede configurar las condiciones de las advertencias que les aparecen a los usuarios durante el proceso de cálculo de L. MAT, si los componentes seleccionados pueden provocar errores de cálculo.

### <a name="view-warning-messages-on-the-complete-page"></a>Ver mensajes de advertencia en la página Completado

Un cálculo de L. MAT genera mensajes de advertencia. Puede ver las advertencias acerca de un artículo seleccionado. Por ejemplo, en Ventas y marketing, cree un nuevo pedido de ventas para el artículo D0001. A continuación, en la línea de pedido de ventas, en el menú **Actualizar línea**, haga clic en **Calcular basándose en L. MAT/fórmula** para ver los detalles de cálculos y las advertencias. También puede ver los resultados de cálculos de L. MAT en la página **Completado**. Para los mensajes de advertencia, solo se aplican dos condiciones de advertencia a los artículos fabricados, y cuatro condiciones de advertencia a todos los artículos:
-   Indica que el artículo fabricado no tiene una L. MAT. activa.
-   Indica que el artículo fabricado no tiene una ruta activa.
-   Identifica cuando un artículo de la línea de L. MAT. tiene una cantidad de 0 (cero).
-   Identifica cuando el artículo de una línea de L. MAT. tiene un coste de 0 (cero) o cuando no tiene un registro de coste.
-   Identifica cuando el artículo de una línea de L. MAT tiene un coste obsoleto. La advertencia refleja una comparación de la fecha de cálculo con los días especificados del vencimiento máximo de coste.
-   Identifica cuando el artículo de una línea de L. MAT tiene un porcentaje de rentabilidad inferior al deseado.

Puede definir varios grupos de cálculo de L. MAT, en función de los requisitos para las variaciones en los mensajes de advertencia. Por ejemplo, podría ser suficiente un grupo de cálculo de L. MAT que tenga condiciones de advertencia de una L. MAT activa, una cantidad de componente de 0 (cero) y un coste de componente de 0 (cero). Al iniciarse un cálculo de L. MAT, puede anular las condiciones de advertencia asociadas al grupo de cálculo de L. MAT. También puede agregar o eliminar condiciones de advertencia. Por ejemplo, si la situación actual no implica datos de rutas, puede ser necesario eliminar la condición de advertencia sobre una ruta activa. **Nota:** Tiempo y asistencia incluye una página **Grupos de cálculo**, pero la página no tiene relación con los grupos de cálculo de L. MAT. En Tiempo y asistencia, los trabajadores pueden estar asignados a grupos de cálculo que reflejan la agrupación de los trabajadores que están asociados al mismo supervisor o director. El supervisor o director puede efectuar los cálculos de los registros de los trabajadores de forma automática o manual.





[!INCLUDE[footer-include](../../includes/footer-banner.md)]