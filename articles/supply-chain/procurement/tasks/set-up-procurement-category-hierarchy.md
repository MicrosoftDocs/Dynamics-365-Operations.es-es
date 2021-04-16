---
title: Configurar una jerarquía de categorías de compras
description: Este procedimiento muestra cómo crear nuevos nodos en una jerarquía de categorías de compras y cómo configurar una categoría de compras para usarla en un proceso de compra.
author: kamaybac
ms.date: 06/21/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: dabourq
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 206dd5dc8f332268fe7665d84b005b5a7bfd1f9a
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/01/2021
ms.locfileid: "5837714"
---
# <a name="set-up-a-procurement-category-hierarchy"></a>Configurar una jerarquía de categorías de compras

[!include [banner](../../includes/banner.md)]

Este procedimiento muestra cómo crear nuevos nodos en una jerarquía de categorías de compras y cómo configurar una categoría de compras para usarla en un proceso de compra. Estas tareas las realizará normalmente el director de compras. Para poder comenzar este procedimiento, debe haber una jerarquía de categorías de tipo Adquisición. Si usa una empresa de datos de demostración, puede ejecutar este procedimiento en la empresa USMF.


## <a name="add-a-new-procurement-category"></a>Adición de una nueva categoría de compras
1. Vaya a **Panel de exploración > Módulos > Adquisición y abastecimiento > Entrega > Categorías de adquisición**.
2. En el panel Acciones, seleccione **Editar jerarquía de categoría**. La jerarquía de la categoría de compras actual se muestra en el lado izquierdo de la página. Va a modificar la jerarquía.  
3. En el panel Acciones, seleccione **Nuevo nodo de categoría**. El sistema selecciona el nodo superior de forma predeterminada. Si está ejecutando este procedimiento como guía de tarea, puede hacer clic en el botón Desbloquear y seleccionar otro nodo principal donde insertar su nuevo nodo. Una vez hecho, bloquee la guía de tarea de nuevo y haga clic en Nodo de categoría nueva.  
4. En el campo **Nombre**, escriba un valor.
5. En el campo **Descripción**, escriba un valor.
6. En el campo **Nombre descriptivo**, escriba un valor. El nombre descriptivo es opcional. Se mostrará en las búsquedas de categorías junto con el nombre de la categoría.  
7. Seleccione **Guardar**.

## <a name="add-products-to-your-new-procurement-category"></a>Adición de productos a su nueva categoría de compra
1. Vaya a **Adquisición y abastecimiento > Entrega > Categorías de compras**. Seleccione el nodo que acaba de agregar. Si está ejecutando este procedimiento como guía de tarea, puede que tenga que desbloquear la guía de tarea para seleccionar el nodo.  
2. Expanda la sección **Productos**.
3. Seleccione **Agregar** para asociar productos con la categoría de adquisición.
4. Seleccione los productos que desea agregar a la categoría de adquisición.
5. Seleccione la flecha para agregar los productos a la tabla **Seleccionado**.
6. Seleccione **Aceptar**.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]