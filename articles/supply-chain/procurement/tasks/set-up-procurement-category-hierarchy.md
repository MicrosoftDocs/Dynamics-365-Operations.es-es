---
title: Configurar una jerarquía de categorías de compras
description: Este procedimiento muestra cómo crear nuevos nodos en una jerarquía de categorías de compras y cómo configurar una categoría de compras para usarla en un proceso de compra.
author: mkirknel
manager: AnnBe
ms.date: 11/06/2017
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Operations
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 01809a8a3256342682d8a9cfb296a355310fe4ed
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/29/2019
ms.locfileid: "334528"
---
# <a name="set-up-a-procurement-category-hierarchy"></a>Configurar una jerarquía de categorías de compras

[!include [task guide banner](../../includes/task-guide-banner.md)]

Este procedimiento muestra cómo crear nuevos nodos en una jerarquía de categorías de compras y cómo configurar una categoría de compras para usarla en un proceso de compra. Estas tareas las realizará normalmente el director de compras. Para poder comenzar este procedimiento, debe haber una jerarquía de categorías de tipo Adquisición. Si usa una empresa de datos de demostración, puede ejecutar este procedimiento en la empresa USMF.


## <a name="add-a-new-procurement-category"></a>Adición de una nueva categoría de compras
1. Vaya a Adquisición y abastecimiento > Categorías de compras.
2. Haga clic en Editar jerarquía de categoría.
    * La jerarquía de la categoría de compras actual se muestra en el lado izquierdo de la página. Va a modificar la jerarquía.  
3. Haga clic en Nodo de categoría nueva.
    * El sistema selecciona el nodo superior de forma predeterminada. Si está ejecutando este procedimiento como guía de tarea, puede hacer clic en el botón Desbloquear y seleccionar otro nodo principal donde insertar su nuevo nodo. Una vez hecho, bloquee la guía de tarea de nuevo y haga clic en Nodo de categoría nueva.  
4. En el campo Nombre, escriba un valor.
5. En el campo Descripción, escriba un valor.
6. En el campo Nombre descriptivo, escriba un valor.
    * El nombre descriptivo es opcional. Se mostrará en las búsquedas de categorías junto con el nombre de la categoría.  
7. Haga clic en Guardar.

## <a name="add-products-to-your-new-procurement-category"></a>Adición de productos a su nueva categoría de compra
1. Vaya a Adquisición y abastecimiento > Categorías de compras.
    * Seleccione el nodo que acaba de agregar. Si está ejecutando este procedimiento como guía de tarea, puede que tenga que desbloquear la guía de tarea para seleccionar el nodo.  
2. Expanda la sección Productos.
3. Haga clic en Agregar para asociar productos con la categoría de adquisición.
4. Seleccione el producto que desea agregar a la categoría de adquisición.
5. Haga clic en la flecha para seleccionar el producto.
6. Seleccione otro producto que agregar a la categoría de adquisición.
7. Haga clic en la flecha para seleccionar el producto.
8. Haga clic en Aceptar

## <a name="add-approved-and-preferred-vendors"></a>Adición de proveedores aprobados y preferidos
1. Alterne la expansión de la sección Proveedores.
2. Haga clic en Agregar.
    * Puede agregar un proveedor a una categoría de compra y especificar si se prefiere a un proveedor para la categoría, o simplemente es un proveedor aprobado. Al eliminar un proveedor de una categoría, el historial de transacciones con el proveedor en la categoría no se eliminarán.   
3. Localice el proveedor que desea agregar a la categoría.
4. Haga clic en la flecha para seleccionar al proveedor.
5. Haga clic en Aceptar
6. Seleccione la fila del proveedor que desee modificar.
7. En el campo Estado del proveedor, seleccione una opción.
    * El ajuste de la selección del proveedor en la regla de la directiva de categoría rige si aparecen disponibles en los pedidos de compra los proveedores preferidos, los aprobados o todos ellos.   

## <a name="add-additional-information-to-the-category"></a>Adición de información adicional a la categoría
1. Expanda la sección Grupos de criterios de evaluación de proveedor.
    * Esta ficha permite definir en relación con qué criterios se deben clasificar los proveedores en la categoría de compra. Para ello, haría clic en Agregar y seleccione un grupo de evaluación de proveedores con los criterios en cuestión.  
2. Expanda la sección Cuestionarios.
    * Esta ficha le permite agregar cuestionarios que aparecerán en el pedido, siempre que se defina el tipo de actividad en Pedido. El solicitante continuación tiene que completar un cuestionario antes de que envíen un pedido de compra del producto o los productos específicos en la categoría de compras.  
3. Expanda la sección Grupos de impuestos de artículos.
4. En el campo Grupo de impuestos de artículos, haga clic en el botón desplegable para abrir la búsqueda.
5. Seleccione un grupo de impuestos.
6. Expanda la sección Página de la categoría.
    * Las páginas de la categoría se crean en la página Jerarquía de categoría. Incluyen información acerca de la categoría de compra, como información sobre el tipo de productos en una categoría, imágenes de productos en una categoría, o anuncios, como los descuentos disponibles en una categoría. La información en una página de categoría aparece en los pedidos de compra.  
7. Cierre la página.

