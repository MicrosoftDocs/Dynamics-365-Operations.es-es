--- 
title: "Configurar una directiva de ubicación para apartar un pedido de trabajo"
description: "Este procedimiento muestra cómo configurar una directiva de ubicación sencilla."
author: BibiSp
manager: AnnBe
ms.date: 11/14/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: bis
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: bis
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 45e1e54c807597d4d5ff7370748012cbf28c1c6b
ms.contentlocale: es-es
ms.lasthandoff: 09/29/2017

---
# <a name="set-up-a-location-directive-for-purchase-order-put-away"></a>Configurar una directiva de ubicación para apartar un pedido de trabajo

[!include[task guide banner](../../includes/task-guide-banner.md)]

Este procedimiento muestra cómo configurar una directiva de ubicación sencilla. El ejemplo que se muestra crea una directiva de ubicación que se usará para determinar dónde colocar los artículos recibidos para un pedido de compra. Puede reproducir esta guía de tarea con los datos mencionados usando para ello la empresa de demostración USMF. Condiciones previas: necesita crear un código de disposición. En este procedimiento usamos un código de disposición llamado Relabel. Si está creando una directiva de ubicación en sus propios datos, debe haber configurado la gestión de almacenes avanzada para su almacén y sus artículos.  Este procedimiento va destinado al encargado de almacén.

1. Vaya a Gestión de almacenes > Configurar > Directivas de ubicación.
2. En el campo Tipo de pedido de trabajo, seleccione Pedidos de compra.

## <a name="create-a-location-directive-header"></a>Creación de un encabezado de directiva de ubicación
1. Haga clic en Nuevo.
2. En el campo Número de secuencia, especifique un número.
    * Esta es la secuencia en la que se debe procesar la directiva de ubicación para el tipo de trabajo seleccionado. Puede modificar la secuencia, si fuera necesario.  
3. En el campo Nombre, escriba un valor.
    * Este es el identificador único para esta directiva.  
4. En el campo Tipo de trabajo, seleccione Colocar.
    * Seleccione el tipo de trabajo que se debe realizar. Para la directiva con tipo pedido de trabajo Pedido de compra, Colocar es el único valor admitido.  
5. En el campo Sitio, escriba un valor.
6. En el campo Almacén, escriba un valor.
    * Deje en blanco el código de la directiva.  Los códigos de las directivas se usan para vincular una línea de pedido de trabajo del tipo Colocar en una directiva concreta. En los pedidos de compra, la ubicación de la última línea de pedido de trabajo de tipo Colocar se resuelve antes de determinar la plantilla de trabajo. Por lo tanto, no es posible conectar la última línea de una plantilla de trabajo con una directiva específica.   
7. En el campo Código de disposición, escriba un valor.
    * El código de disposición limita el uso de la directiva de ubicación, de modo que la directiva de ubicación solo se usa si el trabajador del almacén especifica este valor concreto durante el registro del artículo mediante un dispositivo móvil.  
8. Haga clic en Guardar.

## <a name="edit-the-query-for-directive"></a>Edición de la consulta de la directiva
1. Haga clic en Editar consulta.
    * El uso de esta directiva está limitado ya a usarse con artículos registrados en el almacén y con el código de disposición especificados. Puede agregar otras restricciones mediante la consulta.  
2. Haga clic en Aceptar

## <a name="add-directive-lines"></a>Adición de líneas de directiva
1. Haga clic en Nuevo.
    * Esta es la secuencia en la que se procesan las líneas de la directiva de ubicación para el tipo de trabajo seleccionado. Puede modificar la secuencia, si fuera necesario.  
2. En el campo Cantidad inicial, especifique un número.
    * Esta es la cantidad inferior para la que es válida esta línea de directiva.  
3. En el campo Cantidad final, especifique un número.
4. En el campo Unidad, escriba un valor.
    * La unidad en la que se expresa Cantidad inicial y Cantidad final. Si deja este campo en blanco, se utilizará la unidad de inventario del artículo.  
5. En el campo Cantidad para localizar, seleccione una opción.
    * Ninguno o Cantidad de matrícula de entidad de almacén: la cantidad registrada en cada matrícula de entidad de almacén. Cantidad dividido en unidades: la cantidad total registrada. Cantidad restante: la cantidad que queda por registrar desde la línea de pedido de compra. Cantidad esperada: la cantidad total especificada en la línea de pedido de compra.  
6. Active o desactive la casilla Restringir por unidad.
    * Si selecciona esta opción y especifica la unidad en la página Restringir por unidad, solo los artículos con esa unidad de medida se pueden colocar en la ubicación. Por ejemplo, si la unidad de medida es PL (pallets), solo los artículos en pallets se pueden colocar en una ubicación especificada.  
7. Active o desactive la casilla Permitir división.
    * Esto permite a la directiva dividir la cantidad entre varias ubicaciones.  
8. Haga clic en Guardar.

## <a name="restrict-the-directive-line-to-a-specific-unit"></a>Restricción de la línea directiva a una unidad específica
1. Haga clic en Restringir por unidad.
    * Este botón solo está disponible si presiona Guardar después de seleccionar la casilla Restringir por unidad.  
2. En el campo Unidad, escriba un valor.
3. Cierre la página.

## <a name="add-a-location-directive-action-line"></a>Adición de una línea de acción de directiva de ubicación
1. Haga clic en Nuevo.
    * Esta es la secuencia en la que se procesan las líneas de acción de la directiva de ubicación para el tipo de trabajo seleccionado. Puede modificar la secuencia, si fuera necesario.  
2. En el campo Nombre, escriba un valor.
    * Este es el identificador único para esta acción de directiva.  
3. En el campo Uso de ubicaciones fijas, seleccione una opción.
    * Ubicaciones fijas y no fijas: todas las ubicaciones no fijas son válidas, así como la propia ubicación fija del producto, dentro del rango específico en la consulta.  Solo ubicaciones fijas para el producto: las ubicaciones fijas para el producto son válidas, así como todas las variantes de producto comparten el mismo conjunto de ubicaciones fijas. Solo ubicaciones fijas para la variante del producto: solo son válidas las ubicaciones fijas especificadas para cada variante del producto.  
4. En el campo Estrategia, seleccione una opción.
    * Los pedidos de trabajo del tipo Pedido de compra admiten las estrategias siguientes: Ninguna: el artículo se coloca en la primera ubicación que se encuentra. Consolidar: el artículo se configura en una ubicación donde ya estén disponibles otros artículos similares. Ubicación vacía sin trabajo entrante: el artículo se coloca en la primera ubicación vacía que se encuentra. Una ubicación se considera vacía si no tiene ningún inventario físico y ningún trabajo entrante previsto.  
5. Haga clic en Guardar.

## <a name="edit-the-query-for-directive-action-line"></a>Edición de la consulta de la línea de acción de la directiva
1. Haga clic en Editar consulta.
2. Haga clic en Agregar.
3. En el campo Campo, escriba "Id. de perfil de ubicación".
    * En este ejemplo, restringiremos las ubicaciones posibles mediante un identificador de perfil de ubicación.  
4. En el campo Criterios, escriba un valor.
5. Haga clic en Aceptar
    * Puede continuar agregando líneas de directivas y acciones de directivas hasta que haya cubierto todas las situaciones posibles del almacén.  


