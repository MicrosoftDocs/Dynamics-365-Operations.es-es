---
title: Definición de procesos de recuento de inventario
description: Este tema describe la configuración de procesos de recuento de inventario básicos creando un grupo de recuento y un diario de recuento.
author: MarkusFogelberg
manager: AnnBe
ms.date: 07/26/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: InventCountGroup, InventJournalName, InventParameters, EcoResProductDetailsExtended, InventItemLocation, InventLocationIdLookup
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: mafoge
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: b4f83ae0e33520f1777cea31e2f986af1691bfa1
ms.sourcegitcommit: fcb27d6a46cd544feef34f6ec7607bdd46b0c12b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/18/2020
ms.locfileid: "3145591"
---
# <a name="define-inventory-counting-processes"></a>Definición de procesos de recuento de inventario

[!include [banner](../../includes/banner.md)]

Este tema describe la configuración de procesos de recuento de inventario básicos creando un grupo de recuento y un diario de recuento. También le muestra cómo habilitar directivas de recuento en el nivel de almacén y de artículo. Estas tareas las realizará normalmente el supervisor del almacén. Es requisito previo que haya productos emitidos y almacenes. Si usa una empresa de datos de demostración, puede ejecutar este procedimiento en la empresa USMF con cualquier artículo en existencias.


## <a name="create-a-counting-group"></a>Cree un grupo de recuento.
1. En el Panel de exploración, vaya a **Módulos > Gestión de inventario > Configuración > Desglose del inventario > Grupos de recuento**.
2. Seleccione **Nuevo**.
3. En el campo **Grupo de recuento**, escriba un valor.
4. En el campo **Nombre**, escriba un valor.
5. En el campo **Código de recuento**, seleccione una opción.

    - **Manual**: se incluyen líneas cada vez que se ejecuta el trabajo. Es decir, usted decide el intervalo de recuento para el grupo de recuento.  
    - **Período**: se incluyen líneas para el período en el diario de recuento cuando ha vencido el intervalo del período.  
    - **Sin existencias**: si el inventario disponible llega a cero (0), se generan líneas en el diario de recuento cuando se ejecuta el trabajo. Si el inventario disponible llega a 0 después de un recuento, las líneas se generan la próxima vez que comience el recuento.  
    - **Mínimo**: se insertan líneas en el diario de recuento si el inventario disponible es igual o menor que el mínimo especificado.  
    - Opcional: si se ha especificado **Período en el campo** en el campo **Código de recuento**, debe especificar el intervalo del período en el campo **Período de recuento**. La unidad de los intervalos es días.  
    - Cuando ejecuta el trabajo para crear nuevas líneas en el diario de recuento, se crean nuevas líneas en el intervalo especificado en este campo, independientemente de la frecuencia con la que se ejecute el mismo trabajo. Por ejemplo, si el **Período de recuento** se establece en 7, y las líneas de diario se han generado la última vez para un recuento el 1 de enero, si se inicia otro trabajo el 5 de enero, no han pasado siete días, por lo que no se genera ninguna línea en el diario para ese intervalo de período. Si inicia de nuevo el trabajo el 8 de enero, se generan líneas para el período en el diario de recuento, dado que han transcurrido siete días.  

6. Seleccione **Guardar**.

## <a name="create-a-counting-journal-name"></a>Creación de un nombre de diario de recuento
1. En el Panel de exploración, vaya a **Módulos > Gestión de inventario > Configuración > Nombres de diario > Inventario**.
2. Seleccione **Nuevo**.
3. En el campo **Nombre**, escriba un valor.
4. En el campo **Descripción**, escriba un valor.
5. En el campo **Tipo de diario**, seleccione **Recuento**. Opcional: puede seleccionar otro identificador de serie de asientos si quiere que los identificadores de asientos generados al crear diarios de recuento tengan una secuencia numérica específica. Las series de asientos se crean en la página **Secuencias numéricas**.  
6. En el campo **Nivel de detalle**, seleccione una opción.  

    - Este es el nivel de detalle que se aplica cuando se registra el diario.  
    - Opcional: puede cambiar el valor en el campo Reserva. Este es el método utilizado para reservar artículos durante el recuento.   
    - **Manual**: los artículos se reservan manualmente en el formulario Reserva.  
    - **Automático**: la cantidad del pedido se reserva desde el inventario disponible para el artículo.   
    - **Expansión**: la reserva forma parte de la planificación maestra de la transacción.  

7. Seleccione **Guardar**.

## <a name="set-standard-counting-journal-name"></a>Definición de un nombre de diario de recuento estándar
1. En el panel de exploración, vaya a **Módulos > Gestión del inventario > Configurar > Inventario y parámetros de gestión de inventario y almacenes**.
2. Seleccione la ficha **Diarios**.
3. En el menú desplegable del campo **Recuento**, seleccione el diario que ha creado anteriormente. Este diario será el nombre de diario predeterminado para los diarios de inventario de tipo **Recuento**.  
4. Seleccione la pestaña **General**. Seleccione esta opción para bloquear un artículo durante el proceso de recuento para evitar que se actualicen los albaranes, las listas de selección o los registros de lista de selección.  

## <a name="set-the-counting-policy-for-an-item"></a>Definición de la directiva de recuento para un artículo
1. En el panel de exploración, vaya a **Módulos > Gestión de información de productos > Productos > Productos emitidos**.
2. En la lista, seleccione el vínculo para el número de artículo del producto para el que desee establecer directivas de recuento. Debe seleccionar un artículo que se siga en el inventario. Un producto sin existencias no puede ser contabilizado. Si está usando los datos de demostración USMF, puede seleccionar el artículo A0001.  
3. Seleccione **Editar**.
4. Expanda la sección **Administrar inventario**.
5. En el menú desplegable del campo **Grupo de recuento**, seleccione el grupo de recuento que ha creado anteriormente. Este producto ahora se incluirá cuando se creen líneas de diario de recuento de inventario con este grupo de recuento.  
6. Seleccione **Guardar**.

## <a name="set-the-counting-policy-for-an-item-in-a-specific-warehouse"></a>Definición de la directiva de recuento para un artículo en un almacén especifico
1. En el panel de acciones, seleccione **Administrar inventario**.
2. Seleccione **Artículos de almacén**.
3. Seleccione **Nuevo**.
4. En el menú desplegable del campo **Almacén**, seleccione el almacén para el que desea configurar directivas específicas de recuento.
5. En el menú desplegable del campo **Grupo de recuento**, seleccione un grupo de recuento. Puede seleccionar un grupo de recuento específico que se debe aplicar al artículo del almacén específico seleccionado. Cuando el recuento se realice en ese almacén, esta directiva de recuento anulará la directiva de recuento general para el artículo.  
6. Seleccione **Guardar**.

