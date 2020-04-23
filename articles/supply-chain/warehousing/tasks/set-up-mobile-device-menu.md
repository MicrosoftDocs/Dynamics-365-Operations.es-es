---
title: Configuración de un elemento de menú del dispositivo móvil para completar trabajo del tipo pedido de compra
description: En este tema se muestra cómo configurar un elemento de menú Dispositivo móvil.
author: ShylaThompson
manager: tfehr
ms.date: 08/02/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSRFMenuItem, WHSRFAutoConfirm, WHSRFMenu
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 905094ae4e76fadbebea1892ec20427f32e3e71d
ms.sourcegitcommit: 4f9912439ff78acf0c754d5bff972c4b85763093
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/02/2020
ms.locfileid: "3216836"
---
# <a name="set-up-a-mobile-device-menu-item-for-completing-work-of-type-purchase-order"></a>Configuración de un elemento de menú del dispositivo móvil para completar trabajo del tipo pedido de compra

[!include [banner](../../includes/banner.md)]

En este tema se muestra cómo configurar un elemento de menú Dispositivo móvil. En este ejemplo, el elemento de menú se usa para realizar el trabajo del tipo Pedido de compra. La clase de trabajo asociado al elemento de menú determina qué valor es válido. Puede usar esta guía en la empresa de datos de demostración USMF. Este procedimiento lo suele realizar un director de almacén.


## <a name="create-a-mobile-device-menu-item"></a>Crear un elemento de menú del dispositivo móvil
1. Vaya a **Elementos de menú del dispositivo móvil** introduciéndolo en la barra de la búsqueda.
2. Seleccione **Nuevo**.
3. En el campo **Nombre del elemento de menú**, escriba un valor. Especifique un valor exclusivo. Por ejemplo, podría escribir `POMove`. Recuerde el valor, lo necesitará más adelante.  
4. En el campo **Título**, escriba un valor. Este es el título que se mostrará en el dispositivo móvil. Por ejemplo, podría escribir `PO Move`.  
5. En el campo **Modo**, seleccione **Trabajo**.
6. Seleccione **Sí** en el campo **Usar trabajo existente**.
    - Este elemento de menú del dispositivo móvil se utiliza para realizar el trabajo existente. Por lo tanto, debe establecer este valor en **Sí**.  
    - El campo **Mostrar estado de inventario** determina si se mostrará el estado de inventario del inventario disponible para el trabajador del almacén en el dispositivo móvil.  
7. En el campo **Dirigido por**, seleccione **Agrupamiento del sistema**. Al seleccionar algo en el campo **Dirigido por**, aparecen campos adicionales en la sección **General** de esta página. Los campos que aparecen dependen de lo que haya seleccionado. Al seleccionar **Agrupamiento del sistema**, se agregan dos nuevos campos. Estos se explican a continuación.  
8. En el campo **Agrupamiento del sistema**, seleccione **WorkPoolId**. Cuando los empleados de almacén abran este elemento de menú, se les pedirá que detecten un id. de grupo de trabajo. Todos los pedidos de trabajo con este id. de grupo de trabajo y las líneas de pedido de trabajo con una de las clases de trabajo agregadas a este elemento de menú se enviarán al usuario.  
9. En el campo **Etiqueta de agrupamiento del sistema**, escriba un valor. Este es el texto que se muestra al usuario en el dispositivo móvil. Por ejemplo, podría escribir **Grupo de trabajo**.  
10. Seleccione **Sí** en el campo **Anular número de entidad de almacén durante colocación**. Esta opción permite a los trabajadores de almacén anular la matrícula de entidad de almacén de destino cuando los artículos se colocan en una ubicación controlada mediante matrícula de entidad de almacén.  
11. Seleccione **Sí** en el campo **Ubicaciones en grupo**.
    - Si todas las líneas de colocación del pedido de trabajo comparten la misma ubicación, el usuario recibirá una instrucción Put combinada para todas las líneas. 
    - Id. de plantilla de auditoría: una plantilla de auditoría de trabajo le permite especificar que el proceso de trabajo para un elemento de menú se debe interrumpir a fin de que se pueda realizar otra operación. Por ejemplo, si este elemento de menú es para trabajo de entrada, la plantilla de auditoría puede requerir que el trabajador compruebe la temperatura. El punto en el que se interrumpe el proceso se especifica en la plantilla de auditoría y puede ser, por ejemplo, cuando el trabajo es iniciado o completado, o cuando cambia el estado.  
12. Expanda la sección **Clases de trabajo**.
13. Seleccione **Nuevo**.
14. En el campo **Identificador de la clase de trabajo**, escriba `Purchase`. El grupo de trabajo restringe el trabajo para el que se puede utilizar el elemento de menú. En este caso se utilizará para las líneas de pedido de trabajo abiertas que tienen el id. de clase de trabajo de compra.  
15. Seleccione **Guardar**.

## <a name="set-up-work-confirmation"></a>Configurar confirmación de trabajo
1. Seleccione **Configuración de la confirmación de trabajo**.
2. En el campo **Tipo de trabajo**, seleccione **Recoger**.
3. Seleccione la casilla **Confirmación automática**. La instrucción de trabajo con el tipo de trabajo Seleccionar se confirmará automáticamente. Esta instrucción no se presentará al usuario.  
4. Seleccione **Nuevo**.
5. En el campo **Tipo de trabajo**, seleccione 'Colocar'.
6. Seleccione la casilla **Confirmación de la ubicación**. Al trabajador de almacén se le pedirá que realice un análisis de confirmación de la ubicación, cuando se coloque el artículo.  
7. Seleccione **Guardar**.

## <a name="add-the-menu-item-to-a-mobile-device-menu"></a>Agregar el elemento de menú a un menú de dispositivo móvil
1. Vaya al menú **Dispositivo móvil** introduciéndolo en la barra de la búsqueda.
2. Seleccione **Editar**.
3. Use el filtro rápido para buscar registros. Por ejemplo, aplique un filtro en el campo **Nombre** con un valor de **entrada**. Desea encontrar el menú que utiliza para elementos de menú de entrada. En USMF esto se denomina **Entrada**.  
4. En el árbol, seleccione **un valor**.
5. Seleccione la flecha que apunta a la derecha.
6. Seleccione **Guardar**.
7. Cierre la página.
