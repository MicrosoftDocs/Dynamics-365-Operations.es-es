---
title: Crear una solicitud para consumo
description: En este tema se describe el proceso de crear una solicitud.
author: mkirknel
manager: tfehr
ms.date: 07/09/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Operations
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: acc2cdb9b74cccaefe565b0e2ae8ec4c5f2401c4
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/13/2020
ms.locfileid: "4436721"
---
# <a name="create-a-requisition-for-consumption"></a>Crear una solicitud para consumo

[!include [banner](../../includes/banner.md)]

En este tema se describe el proceso de crear una solicitud. Le muestra diferentes formas de buscar productos en el catálogo de compras y cómo agregar un producto que no esté en el catálogo. Antes de comenzar este procedimiento, debe haber configurado una directiva de compra con Consumo como tipo predeterminado de solicitud. Puede revisar este procedimiento con los datos de prueba de la empresa USMF o utilizar sus propios datos. El procedimiento solo lo puede realizar un perfil de usuario configurado como trabajador. Esta tarea la realiza normalmente un empleado. El rol de seguridad **Empleado** le permitirá realiza las tareas. O bien, si utiliza USMF, puede iniciar sesión como **Alicia**.


## <a name="create-a-new-requisition"></a>Creación de una nueva solicitud
1. Vaya a **Panel de exploración > Módulos > Adquisición y abastecimiento > Solicitudes de compra > Solicitudes de compra preparadas por mí**.
2. Seleccione **Nuevo**.
3. En el campo **Nombre**, indique el nombre de la solicitud.
4. En el campo **Fecha solicitada**, especifique una fecha. De forma predeterminada, la fecha solicitada y la fecha de contabilidad se copian en las líneas de solicitud de compra. También se pueden cambiar a nivel de líneas. La fecha solicitada es la fecha de entrega solicitada.  
5. En el campo **Fecha contable**, escriba una fecha. La fecha de contabilidad se usa para registrar el asiento contable en la contabilidad general y para validar si los fondos presupuestarios están disponibles.  
6. Seleccione **Aceptar**.
7. En el campo **Motivo**, seleccione una opción en el menú desplegable. De forma predeterminada, el motivo de justificación comercial que seleccione aparece para las líneas de solicitud de compra, pero puede cambiar esta configuración en el nivel de línea.  
8. Seleccione el motivo.
9. En el campo de **detalles**, especifique una justificación más descriptiva para la solicitud.

## <a name="add-a-line-to-the-requisition"></a>Adición de una línea a la solicitud
1. Seleccione **Agregar línea**. Existen dos formas de agregar líneas a la solicitud de compra. Si ya sabe cuál es el número de producto o que está el producto que solicita no está en el catálogo de productos, puede agregar la línea directamente mediante **Agregar línea**. La otra manera es usar **Agregar productos** allí donde se puedan usar las funciones de búsqueda y filtrado para buscar artículos en el catálogo de productos.    
2. Seleccione la fila que acaba de crear.
    - El solicitante es el trabajador que ha solicitado el pedido o solicitud.   
    - De forma predeterminada, la persona que prepara la solicitud es el trabajador que la ha solicitado. Tiene que habérsele concedido permiso para preparar una línea de pedido en nombre de otro trabajador. Si dispone de estos permisos, entonces los otros trabajadores aparecerán en esta búsqueda.  
3. En el campo **Código de artículo**, escriba un valor. Los artículos disponibles se limitan según la directiva de acceso a categorías y el catálogo de compras para la entidad jurídica de compra.   
4. En el campo **Cantidad**, especifique un número.

## <a name="add-more-products-to-the-requisition"></a>Adición de más productos a la solicitud
1. Seleccione **Agregar productos**. Esta es la opción con la que se pueden buscar productos en el catálogo de productos.    
2. En el campo **Encontrar nodo de categoría de adquisición**, escriba la primera parte del nombre de la categoría que busca y, a continuación, presione **Entrar**. Por ejemplo, escriba `comput`.  
3. Use el método abreviado de **InvokeDefaultButton**.
4. Use el **Filtro** para filtrar la lista de productos en la categoría seleccionada.
5. Seleccione la tarjeta del producto que desee agregar a la solicitud.
6. Seleccione **Agregar a las líneas**.
7. En el campo **Cantidad**, especifique un número.
8. En el campo **Encontrar nodo de categoría de adquisición**, escriba la primera parte del nombre de la categoría que busca y, a continuación, presione **Entrar**. Por ejemplo, escriba `High` (highlighters).  
9. Use el método abreviado de **InvokeDefaultButton**.
10. Seleccione **Agregar producto sin listar a las líneas** para agregar un producto que no aparece en el catálogo de compras.
11. En el campo **Nombre de producto**, escriba un valor.
12. En el campo **Unidad**, escriba un valor.
13. Seleccione **Aceptar**.
14. En el campo **Descripción de artículo**, agregue una descripción del producto.
15. En el campo **Cantidad**, especifique un número.
16. En el campo **Precio unitario**, escriba un número. Si conoce el precio para un proveedor concreto (el cual se selecciona en el campo de la cuenta de proveedor), dicho precio se puede especificar.   
17. En el campo **Cuenta de proveedor**, abra la lista desplegable para seleccionar una opción. Los proveedores disponibles en este campo dependen de las directivas de compra y el estado del proveedor para la categoría de compra actual. Como alternativa a seleccionar aquí un proveedor, puede seleccionar **Sugerir proveedor**.    
18. En la lista, seleccione el proveedor que desee usar.
19. En el campo **Código de artículo externo**, escriba un valor. Este es un número de referencia para el producto que conoce el proveedor. Por ejemplo, podría ser el número de artículo del producto en el catálogo propio del proveedor.  
20. Seleccione **Aceptar**.

## <a name="distribute-amounts"></a>Distribuir importes
1. Seleccione **Operaciones financieras**.
2. Seleccione **Distribuir importes**. Este proceso muestra cómo distribuir el coste para la primera línea entre dos cuentas. Esto también se puede hacer más tarde, cuando la solicitud se encuentre en revisión.  
3. Seleccione **Dividir** para crear una nueva línea de distribución.
4. En el campo **Cuenta contable**, seleccione el primer centro de coste que debe ser parte del coste.
5. Seleccione la otra línea de distribución.
6. En el campo Cuenta contable, especifique el otro centro de coste.
7. Seleccione **Distribuir de forma equitativa**.
8. Cierre la página.

## <a name="view-line-details"></a>Visualización de detalles de línea
1. Alterne la expansión de la sección **Detalles de línea**.

## <a name="submit-the-requisition"></a>Envío de la solicitud
1. Seleccione **Flujo de trabajo** para abrir el cuadro de diálogo desplegable.
2. Seleccione **Enviar**.
3. Cierre la página.
4. En el campo **Comentario**, escriba una nota para el usuario que aprueba la solicitud.
5. Seleccione **Enviar**.
6. Cierre la página.
7. Actualice la página.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]