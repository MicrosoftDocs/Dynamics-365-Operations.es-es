---
title: Crear un catálogo de compras
description: Este tema explica cómo crear un catálogo de compras.
author: kamaybac
ms.date: 07/19/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: ProcCategoryHierarchyManagement, CatProcureCatalogListPage, CatProcureCatalogCreate, CatProcureCatalogEdit, SysPolicyListPage, SysPolicy, CatCatalogPolicyRule, PurchReqTableListPage, PurchReqCreate, PurchReqTable, PurchReqAddItem
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: dabourq
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: a9bec131798a67695bc3ea27cbbdea404d4494382e25e97b2931508ec7d52fca
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2021
ms.locfileid: "6746924"
---
# <a name="create-a-procurement-catalog"></a>Crear un catálogo de compras

[!include [banner](../../includes/banner.md)]

Este tema explica cómo crear un catálogo de compras. Esta tarea la llevaría a cabo normalmente un profesional de compras. También obtendrá información acerca de cómo los empleados pueden utilizar el catálogo al crear una solicitud. Para que pueda crear un catálogo, debe haber una jerarquía de categoría de compras en su sistema. La jerarquía es hereda por el nuevo catálogo, junto con todos los productos que se encuentran en la jerarquía. Puede usar esta guía en la empresa de datos de demostración USMF donde la jerarquía de categoría de compras está disponible, así como los ejemplos usados en los pasos de procedimiento.


## <a name="ensure-that-a-procurement-category-hierarchy-exists"></a>Asegúrese de que existe una jerarquía de categoría de compras
1. Vaya a **Panel de exploración > Módulos > Adquisición y abastecimiento > Categorías de compras**. Una jerarquía de categoría de compras está disponible en los datos de demostración de la empresa USMF y los productos se han agregado a la categoría **Máquinas de oficina/Equipos informáticos**. Si está ejecutando este procedimiento como guía de tareas, necesitará desbloquear la guía si desea desplazarse por la categoría. Si no hubiera una jerarquía disponible, tendría que crearla haciendo clic en **Nuevo**. Esto solo se puede hacer una vez.  
2. Cierre la página.

## <a name="create-a-catalog"></a>Crear un catálogo
1. Vaya a **Panel de exploración > Módulos > Adquisición y abastecimiento > Catálogos > Catálogos de compras**.
2. Seleccione **Nuevo catálogo de compras** para abrir el cuadro de diálogo desplegable.
3. En el campo **Nombre**, escriba un valor.
4. Seleccione **Aceptar**.
5. En el árbol, expanda **CORP PROCUREMENT CATEGORIES**.
6. En el árbol, expanda **OFFICE MACHINES**.
7. En el árbol, seleccione **Computers**.

  - Los productos de la categoría de compras se muestran en la lista. Si desea agregar un producto a la categoría, necesita hacer esto en la página **Jerarquía de categorías de compras** o en la página **Detalles del artículo**.  
  - El tipo de actualización **Predeterminado** determina si los nuevos productos que se han agregado a la jerarquía de categoría de compras son inmediatamente visibles en el catálogo. Si el tipo de actualización se establece en **Dinámico**, los cambios serán visibles de inmediato. Si el tipo de actualización es **Estático**, los nuevos productos solo son visibles para personas que usan el catálogo una vez que se ha vuelto a publicar el catálogo. La acción **Publicar** está disponible en el Panel de acciones de la parte superior de la página. Si los productos se eliminan de la jerarquía de categoría de compras, el cambio será visible inmediatamente, con independencia del valor en el campo **Tipo de actualización predeterminada**.  

8. En el panel de acciones, seleccione **Navegación por categorías** y asegúrese de que la opción **Habilitar** está seleccionada.
9. Seleccione **Activar catálogo**.
10. Cierre la página.

## <a name="make-the-catalog-visible"></a>Hacer el catálogo visible
1. Vaya a **Panel de exploración > Módulos > Adquisición y abastecimiento > Configuración > Directivas > Directivas de compras**.
2. Seleccione **USMF de directiva de compras**. Necesita seleccionar la directiva de compras para la entidad jurídica en la que el trabajador conectado a su perfil de usuario puede pedir productos. En los datos de demostración USMF, el usuario Administrador está conectado a la trabajadora **Julia Funderburk** y ella pide productos en USMF de manera predeterminada.  
3. Seleccione el catálogo que acaba de crear.
4. Seleccione **Aceptar**.

## <a name="use-the-catalog"></a>Usar el catálogo
1. Vaya a **Panel de exploración > Módulos > Adquisición y abastecimiento > Solicitudes de compra > Todas las solicitudes de compra**.
2. Seleccione **Nuevo**.
3. En el campo **Nombre**, escriba un valor.
4. Seleccione **Aceptar**.
5. Seleccione **Agregar productos**.
6. En la lista, busque y seleccione el registro deseado. Puede utilizar la jerarquía de categoría de la izquierda o el filtro de la parte superior de la lista para filtrar los productos.  
7. Seleccione **Agregar a las líneas**.
8. Seleccione **Aceptar**.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]