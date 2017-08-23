--- 
title: "Definir reglas de cobertura para los artículos"
description: La empresa de datos de prueba utilizada para crear este procedimiento es USMF.
author: YuyuScheller
manager: AnnBe
ms.date: 11/11/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Operations
ms.search.region: Global
ms.author: yuyus
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: f01d88149074b37517d00f03d8f55e1199a5198f
ms.openlocfilehash: 3b34d2c35bc96cf75e9e699b835f7bcbbce1312b
ms.contentlocale: es-es
ms.lasthandoff: 07/27/2017

---
# <a name="define-coverage-rules-for-items"></a>Definir reglas de cobertura para los artículos

[!include[task guide banner](../../includes/task-guide-banner.md)]

La empresa de datos de prueba utilizada para crear este procedimiento es USMF. Este procedimiento muestra cómo crear reglas de cobertura y anular opciones de cobertura para un artículo específico. También se muestra cómo especificar parámetros de inventario predeterminados.


## <a name="create-a-coverage-group"></a>Crear un grupo de cobertura
1. Vaya a Grupos de cobertura.
2. Haga clic en Nuevo.
3. En el campo Grupo de cobertura, escriba un valor.
4. En el campo Nombre, escriba un valor.
5. En el campo Calendario, escriba un valor.
    * Elija el calendario que utiliza la planificación maestra para crear sugerencias de reabastecimiento para los artículos en el grupo.  
6. En el campo Código de cobertura, seleccione una opción.
    * Seleccione Requisito para este procedimiento.  
7. En el campo Límite de tiempo de cobertura (días), escriba "90".
    * Para los artículos de este grupo, la planificación maestra creará las sugerencias de reabastecimiento de hasta 90 días en el futuro.  
8. En el campo Días negativos, especifique “1".
9. En el campo Días positivos, especifique “1".
10. Expanda o contraiga la sección Otros.
11. En el campo Días de recepción sumados a la fecha de requisito, especifique “1".
    * Por ejemplo, si el margen de recepción se establece en 1 día y se programa la recepción de una línea de pedido de compra para el 15 de mayo, la planificación maestra calcula la fecha de recepción ajustada como el 16 de mayo.  
12. En el campo Días de emisión deducidos de la fecha de requisito, especifique “1".
    * Por ejemplo, si el margen de seguridad se establece en 1 día y se programa la entrega de una línea del pedido de ventas para el 15 de mayo, la programación maestra calcula la fecha de entrega ajustada como el 14 de mayo.  
13. En el campo Días de administración agregados al plazo del artículo, especifique “1".
14. Haga clic en Guardar.

## <a name="create-a-new-product"></a>Crear un nuevo producto
1. Vaya a Productos emitidos.
2. Haga clic en Nuevo.
3. En el campo Número de producto, escriba un valor.
4. En el campo Nombre de producto, escriba un valor.
5. En el campo Grupo de modelos de artículo, haga clic en el botón desplegable para abrir la búsqueda.
6. En la lista, busque y seleccione el registro deseado.
7. En la lista, haga clic en el vínculo de la fila seleccionada.
8. En el campo Grupo de artículos, haga clic en el botón desplegable para abrir la búsqueda.
9. En la lista, busque y seleccione el registro deseado.
10. En la lista, haga clic en el vínculo de la fila seleccionada.
11. En el campo Grupo de dimensiones de almacenamiento, haga clic en el botón desplegable para abrir la búsqueda.
12. En la lista, busque y seleccione el registro deseado.
13. En la lista, haga clic en el vínculo de la fila seleccionada.
14. En el campo Grupo de dimensiones de seguimiento, haga clic en el botón desplegable para abrir la búsqueda.
15. En la lista, busque y seleccione el registro deseado.
16. En la lista, haga clic en el vínculo de la fila seleccionada.
17. Haga clic en Aceptar

## <a name="setup-default-order-settings"></a>Configuración de ajustes predeterminados de pedido
1. En el panel de acciones, haga clic en Plan.
2. Haga clic en Configuración predeterminada de pedido.
3. En el campo Sitio de compras, escriba el sitio usado como predeterminado cuando se crean los pedidos de compra.
4. En el campo Sitio de inventario, escriba el sitio donde está almacenado el artículo.
5. Expanda o contraiga la sección Inventario.
6. Establezca Múltiplo en “10".
7. Establezca Cantidad mínima de pedido en "10".
8. Establezca Cantidad máxima de pedido en "100".
9. Establezca Cantidad de pedido estándar en "10".
10. En el campo Plazo de compra, especifique un número.
11. Active o desactive la casilla Días laborales.
12. Haga clic en Guardar.
13. En el campo Tipo de pedido predeterminado, seleccione "Pedido de compra".
14. Haga clic en Guardar.
15. Cierre la página.
    * Cierre la página Configuración predeterminada de pedido.  

## <a name="add-an-item-to-a-coverage-group"></a>Agregar un artículo a un grupo de cobertura
1. Expanda o contraiga la sección Plan.
2. En el campo Grupo de cobertura, haga clic en el botón desplegable para abrir la búsqueda.
3. En la lista, busque el grupo de cobertura que ha creado.
4. En la lista, haga clic en el vínculo de la fila seleccionada.

## <a name="create-item-coverage-rules"></a>Crear reglas de cobertura de artículos
1. En el panel de acciones, haga clic en Plan.
2. Haga clic en Cobertura de artículos.
3. Haga clic en Nuevo.
4. Haga clic en la pestaña General.
5. Marque la casilla en el encabezado de Anular configuración de grupo de cobertura.
6. En el campo Límite de tiempo de cobertura (días), escriba "60".
    * Aunque los artículos del grupo de cobertura Requisito se planifiquen con 90 días de adelanto, este artículo se planea con 60 días de adelanto.  
7. En el campo Días negativos, especifique “2".
8. En el campo Días positivos, especifique “2".
9. Haga clic en la pestaña Plazo.
10. Marque la casilla en el encabezado de Compra.
11. En el campo Hora de compra, especifique "5".
12. Haga clic en Guardar.


