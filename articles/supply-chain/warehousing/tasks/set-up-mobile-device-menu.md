--- 
title: "Configuración de un elemento de menú del dispositivo móvil para completar trabajo del tipo pedido de compra"
description: "Este procedimiento muestra cómo configurar un elemento de menú Dispositivo móvil."
author: ShylaThompson
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: WHSRFMenuItem, WHSRFAutoConfirm, WHSRFMenu
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 0312b8cfadd45f8e59225e9daba78b9e216cff51
ms.openlocfilehash: 326a0039d2769ee5f459a87c302c93604d2379aa
ms.contentlocale: es-es
ms.lasthandoff: 09/14/2018

---
# <a name="set-up-a-mobile-device-menu-item-for-completing-work-of-type-purchase-order"></a>Configuración de un elemento de menú del dispositivo móvil para completar trabajo del tipo pedido de compra

[!include [task guide banner](../../includes/task-guide-banner.md)]

Este procedimiento muestra cómo configurar un elemento de menú Dispositivo móvil. En este ejemplo, el elemento de menú se usa para realizar el trabajo del tipo Pedido de compra. La clase de trabajo asociado al elemento de menú determina qué valor es válido. Puede usar esta guía en la empresa de datos de demostración USMF. Este procedimiento lo suele realizar un director de almacén.


## <a name="create-a-mobile-device-menu-item"></a>Crear un elemento de menú del dispositivo móvil
1. Vaya a Elementos de menú del dispositivo móvil.
2. Haga clic en Nuevo.
3. En el campo Nombre del elemento de menú, escriba un valor.
    * Especifique un valor exclusivo. Por ejemplo, podría escribir PCMover. Recuerde el valor, lo necesitará más adelante.  
4. En el campo Título, escriba un valor.
    * Este es el título que se mostrará en el dispositivo móvil. Por ejemplo, podría escribir Pedido de compra Mover.  
5. En el campo Modo, seleccione Trabajo.
6. Seleccione Sí en el campo Usar trabajo existente.
    * Este elemento de menú del dispositivo móvil se utiliza para realizar el trabajo existente. Por lo tanto, debe establecer este valor en Sí.  
    * El campo Mostrar estado de inventario determina si se mostrará el estado de inventario del inventario disponible para el trabajador del almacén en el dispositivo móvil.  
7. En el campo Dirigido por, seleccione "Agrupamiento del sistema".
    * Al seleccionar algo en el campo Dirigido por, aparecen campos adicionales en la sección General de esta página. Los campos que aparecen dependen de lo que haya seleccionado. Al seleccionar Agrupamiento del sistema, se agregan dos nuevos campos. Estos se explican a continuación.  
8. En el campo Agrupamiento del sistema, seleccione “WorkPoolId”.
    * Cuando los empleados de almacén abran este elemento de menú, se les pedirá que detecten un id. de grupo de trabajo. Todos los pedidos de trabajo con este id. de grupo de trabajo y las líneas de pedido de trabajo con una de las clases de trabajo agregadas a este elemento de menú se enviarán al usuario.  
9. En el campo Etiqueta de agrupamiento del sistema, escriba un valor.
    * Este es el texto que se muestra al usuario en el dispositivo móvil. Por ejemplo, podría escribir Grupo de trabajo.  
10. Seleccione Sí en el campo Anular número de entidad de almacén durante colocación.
    * Esta opción permite a los trabajadores de almacén anular la matrícula de entidad de almacén de destino cuando los artículos se colocan en una ubicación controlada mediante matrícula de entidad de almacén.  
11. Seleccione Sí en el campo Ubicaciones en grupo.
    * Si todas las líneas de colocación del pedido de trabajo comparten la misma ubicación, el usuario recibirá una instrucción Put combinada para todas las líneas.  
    * Id. de plantilla de auditoría: una plantilla de auditoría de trabajo le permite especificar que el proceso de trabajo para un elemento de menú se debe interrumpir a fin de que se pueda realizar otra operación. Por ejemplo, si este elemento de menú es para trabajo de entrada, la plantilla de auditoría puede requerir que el trabajador compruebe la temperatura. El punto en el que se interrumpe el proceso se especifica en la plantilla de auditoría y puede ser, por ejemplo, cuando el trabajo es iniciado o completado, o cuando cambia el estado.  
12. Expanda la sección Clases de trabajo.
13. Haga clic en Nuevo.
14. En el campo Identificador de la clase de trabajo, escriba "Compra".
    * El grupo de trabajo restringe el trabajo para el que se puede utilizar el elemento de menú. En este caso se utilizará para las líneas de pedido de trabajo abiertas que tienen el id. de clase de trabajo de compra.  
15. Haga clic en Guardar.

## <a name="set-up-work-confirmation"></a>Configurar confirmación de trabajo
1. Haga clic en Configuración de la confirmación de trabajo.
2. En el campo Tipo de trabajo, seleccione "Seleccionar".
3. Active la casilla Confirmación automática.
    * La instrucción de trabajo con el tipo de trabajo Seleccionar se confirmará automáticamente. Esta instrucción no se presentará al usuario.  
4. Haga clic en Nuevo.
5. En el campo Tipo de trabajo, seleccione Colocar.
6. Seleccione la casilla Confirmación de la ubicación.
    * Al trabajador de almacén se le pedirá que realice un análisis de confirmación de la ubicación, cuando se coloque el artículo.  
7. Haga clic en Guardar.
8. Cierre la página.
9. Cierre la página.

## <a name="add-the-menu-item-to-a-mobile-device-menu"></a>Agregar el elemento de menú a un menú de dispositivo móvil
1. Vaya a Dispositivo móvil.
2. Haga clic en Editar.
3. Use el filtro rápido para buscar registros. Por ejemplo, filtrar en el campo Nombre con un valor de "entrada".
    * Desea encontrar el menú que utiliza para elementos de menú de entrada. En USMF esto se denomina Entrada.  
4. En el árbol, seleccione "un valor".
5. Haga clic en la flecha que apunta a la derecha.
6. Haga clic en Guardar.
7. Cierre la página.


