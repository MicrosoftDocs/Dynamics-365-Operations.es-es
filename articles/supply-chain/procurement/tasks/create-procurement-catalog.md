--- 
title: "Crear un catálogo de compras"
description: "Esta guía le muestra cómo crear un catálogo de compras."
author: mkirknel
manager: AnnBe
ms.date: 08/23/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Operations
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: df844ba3834972441daa61899294b3e95cac96c1
ms.contentlocale: es-es
ms.lasthandoff: 09/29/2017

---
# <a name="create-a-procurement-catalog"></a>Crear un catálogo de compras

[!include [task guide banner](../../includes/task-guide-banner.md)]

Esta guía le muestra cómo crear un catálogo de compras. Esta tarea la llevaría a cabo normalmente un profesional de compras. También obtendrá información acerca de cómo los empleados pueden utilizar el catálogo al crear una solicitud. Para que pueda crear un catálogo, debe haber una jerarquía de categoría de compras en su sistema. La jerarquía es hereda por el nuevo catálogo, junto con todos los productos que se encuentran en la jerarquía. Puede usar esta guía en la empresa de datos de demostración USMF donde la jerarquía de categoría de compras está disponible, así como los ejemplos usados en los pasos de procedimiento.


## <a name="ensure-that-a-procurement-category-hierarchy-exists"></a>Asegúrese de que existe una jerarquía de categoría de compras
1. Vaya a Adquisición y abastecimiento > Categorías de compras.
    * Una jerarquía de categoría de compras está disponible en la empresa de datos de demostración USMF y los productos se han agregado a la categoría Máquinas de oficina/Equipos informáticos. Si está ejecutando este procedimiento como guía de tareas, necesitará desbloquear la guía si desea desplazarse por la categoría. Si una jerarquía no estaba disponible, la crearía haciendo clic en Nuevo. Esto solo se puede hacer una vez.  
2. Cierre la página.

## <a name="create-a-catalog"></a>Crear un catálogo
1. Vaya a Adquisición y abastecimiento > Catálogos > Catálogos de compras.
2. Haga clic en Nuevo catálogo de compras para abrir el cuadro de diálogo desplegable.
3. En el campo Nombre, escriba un valor.
4. Haga clic en Aceptar
5. En el árbol, expanda “CORP PROCUREMENT CATEGORIES”.
6. En el árbol, expanda "OFFICE MACHINES".
7. En el árbol, seleccione "Equipos informáticos".
    * Los productos de la categoría de compras se muestran en la lista. Si desea agregar un producto a la categoría, necesita hacer esto en la página Jerarquía de categorías de compras o en la página Detalles del artículo.  
    * El Tipo de actualización predeterminada determina si los nuevos productos que se han agregado a la jerarquía de categoría de compras son inmediatamente visibles en el catálogo. Si el tipo de actualización se establece en Dinámico, los cambios serán visibles de inmediato. Si el tipo de actualización es Estático, los nuevos productos solo son visibles para personas que usan el catálogo una vez que se ha vuelto a publicar el catálogo. La acción Publicar está disponible en el Panel de acciones de la parte superior de la página. Si los productos se eliminan de la jerarquía de categoría de compras, el cambio será visible inmediatamente, con independencia del valor en el campo Tipo de actualización predeterminada.  
8. En la lista, busque y seleccione el registro deseado.
9. Haga clic en Ocultar.
10. En el panel de acciones, haga clic en Navegación por categorías.
11. Haga clic en Deshabilitar.
12. En el panel de acciones, haga clic en Navegación por categorías.
13. Haga clic en Habilitar.
14. Haga clic en Activar catálogo.
15. Cierre la página.

## <a name="make-the-catalog-visible"></a>Hacer el catálogo visible
1. Vaya a Adquisición y abastecimiento > Configuración > Directivas > Directivas de compra.
2. Seleccione USMF de directiva de compras.
    * Necesita seleccionar la directiva de compras para la entidad jurídica en la que el trabajador conectado a su perfil de usuario puede pedir productos. En los datos de demostración USMF, el usuario Administrador está conectado a la trabajadora Julia Funderburk y ella pide productos en USMF de manera predeterminada.  
3. En la lista, haga clic en el vínculo de la fila seleccionada.
4. Seleccione el catálogo que acaba de crear.
5. Haga clic en Aceptar
6. Cierre la página.
7. Cierre la página.

## <a name="use-the-catalog"></a>Usar el catálogo
1. Vaya a Adquisición y abastecimiento > Solicitudes de compra > Todas las solicitudes de compra.
2. Haga clic en Nuevo.
3. En el campo Nombre, escriba un valor.
4. Haga clic en Aceptar
5. Haga clic en Agregar productos.
6. En la lista, busque y seleccione el registro deseado.
    * Puede utilizar la jerarquía de categoría de la izquierda o el filtro de la parte superior de la lista para filtrar los productos.  
7. Haga clic en Agregar a las líneas.
8. En la lista, busque y seleccione el registro deseado.
9. Haga clic en Agregar a las líneas.
10. Haga clic en Aceptar


