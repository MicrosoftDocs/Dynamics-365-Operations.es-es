---
title: Configurar una plantilla de trabajo para pedidos de compra
description: En este tema se describe cómo configurar una plantilla de trabajo simple que se debe usar al ubicar los artículos recibidos.
author: ShylaThompson
manager: tfehr
ms.date: 08/08/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSWorkTemplateTable, SysQueryForm
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 6628936a56619de255ca7dc7b332b5819918c310
ms.sourcegitcommit: 708ca25687a4e48271cdcd6d2d22d99fb94cf140
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/10/2020
ms.locfileid: "3980595"
---
# <a name="set-up-a-work-template-for-purchase-orders"></a>Configurar una plantilla de trabajo para pedidos de compra

[!include [banner](../../includes/banner.md)]

En este tema se describe cómo configurar una plantilla de trabajo simple que se debe usar al ubicar los artículos recibidos. Las plantillas de trabajo determinan el sistema de instrucciones presentadas al trabajador del almacén en un dispositivo móvil al mover artículos desde el área de recepción. Puede utilizar este procedimiento con los datos mencionados en la empresa de datos de demostración USMF. Antes de comenzar esta guía, cree un id. de grupo de trabajo. En este ejemplo, se usa un id. grupo de trabajo denominado Entrada. Este procedimiento va destinado al encargado de almacén.

1. En el panel de navegación, vaya a **Módulos > Gestión de almacenes > Configuración > Trabajo > Plantillas de trabajo**.
2. En el campo **Tipo de orden de trabajo**, seleccione **Pedidos de compra**.

## <a name="create-a-work-template-header"></a>Crear un encabezado de plantilla de trabajo
1. Seleccione **Nuevo**.
2. En el campo **Número de secuencia**, especifique un número. Esta es la secuencia en la que se evalúan las plantillas de trabajo. Si fuera necesario, puede modificar la secuencia.  
3. En el campo **Plantilla de trabajo**, escriba un valor. Este es el identificador único para esta plantilla.  
4. En el campo **Descripción de la plantilla de trabajo**, escriba un valor.
    - La opción **Válido** no se activará hasta que haya completado toda la información que necesita la plantilla y haya seleccionado después **Guardar**.  
    - Una orden de trabajo del tipo **Pedido de compra** no se puede procesar automáticamente, por tanto, deje la opción **Procesar automáticamente** establecida en **No**.  
5. En el campo **Id. del grupo de trabajo**, escriba un valor. Los id. del grupo de trabajo le permiten organizar el trabajo en grupos. El valor que se establece aquí será el valor predeterminado para cualquier trabajo que se crea usando esta plantilla.  
6. En el campo **Prioridad de trabajo**, escriba `1`. Esto indica la importancia del trabajo y el valor que se establece aquí será el predeterminado para los trabajos creados con esta plantilla.  
7. Seleccione **Guardar**. Debe guardar el encabezado de la plantilla de trabajo antes de que el botón **Editar consulta** se vuelva disponible.  

## <a name="set-up-the-query-for-the-work-template"></a>Configurar la consulta para la plantilla de trabajo
1. Seleccione **Editar consulta**. Estableceremos una limitación de que la plantilla solo se puede usar dentro de un almacén específico.  
2. Seleccione **Agregar**.
3. En el campo **Campo** de la nueva fila, escriba `warehouse`.
4. En el campo **Criterios**, escriba un valor.
5. Seleccione **Aceptar**.
6. Seleccione **Sí**.

## <a name="set-work-template-details"></a>Establecer detalles de plantilla de trabajo
1. Seleccione **Nuevo**.
2. En el campo **Tipo de trabajo**, seleccione **Recoger**.
3. En el campo **Identificador de la clase de trabajo**, escriba `purchase`. La clase de trabajo que establece aquí será el valor predeterminado en todas las líneas de trabajo de tipo Seleccionar que se crean con esta plantilla. La clase de trabajo no se puede anular de las líneas de pedido de trabajo. Las clases de trabajo se usan para dirigir y/o para limitar el tipo de líneas de pedido de trabajo que un trabajador de almacén puede procesar en un dispositivo móvil.  
4. Seleccione **Nuevo**.
5. En el campo **Tipo de trabajo**, seleccione **Colocar**.
6. En el campo **Identificador de la clase de trabajo**, escriba un valor. Las instrucciones seleccionar y colocar son un conjunto. Cada conjunto de selección y colocación deben tener la misma clase de trabajo. Use la misma clase de trabajo que se ha proporcionado para la instrucción seleccionar.  
7. Seleccione **Guardar**. Tenga en cuenta que la casilla **Válido** está ahora activada.  

