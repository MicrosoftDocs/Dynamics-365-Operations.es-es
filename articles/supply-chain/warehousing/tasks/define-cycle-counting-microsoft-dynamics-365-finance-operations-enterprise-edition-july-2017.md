--- 
title: "Definir el recuento cíclico"
description: "La cuenta de ciclo es un proceso de almacén que puede usar para revisar artículos de inventario disponibles."
author: MarkusFogelberg
manager: AnnBe
ms.date: 06/23/2017
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Operations
ms.search.region: Global
ms.author: mafoge
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: f9cdb0a7de0199363279c53e817c98085b31fe6b
ms.contentlocale: es-es
ms.lasthandoff: 09/29/2017

---
# <a name="define-cycle-counting"></a>Definir el recuento cíclico 

[!include [task guide banner](../../includes/task-guide-banner.md)]

La cuenta de ciclo es un proceso de almacén que puede usar para revisar artículos de inventario disponibles. Esta grabación de tarea muestra cómo configurar el valor predeterminado de prioridad de trabajo de recuento; cómo habilitar un elemento de menú de dispositivo móvil para procesar operaciones de selección y recuento; cómo habilitar un activador de umbral de recuento cuando una ubicación quede vacía; cómo habilitar un plan de recuento cíclico para un artículo específico dentro de un almacén concreto. Normalmente, estas tareas las realiza el administrador de almacén. Puede explorar este procedimiento en los datos de la empresa de demostración USMF o utilizar sus propios datos.


## <a name="set-the-priority-of-counting-work"></a>Definición de la prioridad del trabajo de recuento
1. Vaya a Gestión de almacenes > Configurar > Parámetros de gestión de inventario y almacenes.
2. Haga clic en la ficha Recuento cíclico.
3. En el campo Prioridad de trabajo de recuento cíclico predeterminado, especifique un número.
    * Este paso cambia la prioridad del trabajo de recuento cíclico en comparación con otros tipos de trabajo en el almacén. Si especifica un número menor al número de otros tipos de trabajo, aumenta la prioridad de trabajo de recuento cíclico.  
4. Haga clic en Guardar.
5. Cierre la página.

## <a name="enable-the-mobile-device"></a>Habilitar el dispositivo móvil
1. Vaya a Gestión de almacenes > Configurar > Dispositivo móvil > Elementos de menú del dispositivo móvil.
2. Haga clic en Nuevo.
3. En el campo Nombre del elemento de menú, escriba un valor.
4. En el campo Título, escriba un valor.
5. En el campo Modo, seleccione Trabajo.
6. Defina la opción Usar trabajo existente en Sí.
    * Cuando establece esta opción en Sí, el sistema buscará trabajo existente cuando se use el elemento de menú de dispositivo móvil.  
7. En el campo Dirigido por, seleccione Dirigido por el sistema.
    * Cuando se selecciona "Dirigido por el sistema", se dirigirá al trabajador del almacén a abrir el trabajo que está en las clases definidas de trabajo. (Crearemos estas clases de trabajo después.)  
8. Expanda o contraiga la sección Clases de trabajo.
    * A continuación, crearemos dos clases de trabajo que se usarán con este elemento de menú de dispositivo móvil. Cuando se use el elemento de menú, se consultarán estas clases de trabajo y se mostrará al usuario el trabajo con la prioridad más alta.  
9. Haga clic en Nuevo.
10. En el campo Identificador de la clase de trabajo, seleccione un valor.
11. Haga clic en Nuevo.
12. En el campo Identificador de la clase de trabajo, seleccione un valor.
13. Haga clic en Guardar.
14. Cierre la página.
15. Vaya a Gestión de almacenes > Configurar > Dispositivo móvil > Menú del dispositivo móvil.
16. En la lista, busque y seleccione el registro deseado.
17. En el árbol, seleccione "el elemento de menú que acaba de crear".
18. Haga clic en Editar.
19. Haga clic en la flecha para agregar el elemento de menú al menú.
20. Haga clic en Guardar.

## <a name="create-a-counting-threshold"></a>Crear un umbral de recuento
1. Vaya a Administración de almacenes > Configuración > Recuento de ciclos > Umbrales de recuento cíclico.
2. Haga clic en Nuevo.
3. En el campo Id. de umbral de recuento cíclico, escriba un valor.
4. Defina la opción Procesar recuento cíclico inmediatamente en Sí.
5. En el campo Descripción, escriba un valor.
6. Haga clic en Guardar.
7. Haga clic en Seleccionar ubicaciones.
8. En la lista, marque la fila seleccionada.
9. En el campo Criterios, seleccione un valor.
10. Haga clic en Aceptar
11. Cierre la página.

## <a name="create-a-cycle-count-plan"></a>Crear un plan de recuento cíclico
1. Vaya a Administración de almacenes > Configuración > Recuento de ciclos > Planes de recuento cíclico.
2. Haga clic en Nuevo.
3. En el campo Id. de plan de recuento cíclico, escriba un valor.
4. En el campo Descripción, escriba un valor.
5. En el campo Número máximo de recuentos cíclicos, especifique un número.
6. Haga clic en Guardar.
7. Haga clic en Seleccionar ubicaciones.
8. En la lista, marque la fila seleccionada.
9. En el campo Criterios, seleccione un valor.
10. Haga clic en Aceptar
11. En el campo Días entre recuentos cíclicos, especifique un número.
    * Por ejemplo, si el valor en el campo Días entre recuentos cíclicos es 5, el trabajo de recuento cíclico se creará cada cinco días. Sin embargo, si el trabajo de recuento cíclico se procesa el día tres, el siguiente trabajo de recuento cíclico se creará cinco días después del último recuento cíclico procesado, el día 8.  
12. Haga clic en Guardar.
13. Haga clic en Nuevo.
14. En el campo Número de secuencia, especifique un número.
    * La ordenación es del número más pequeño al número más grande. El valor debe ser mayor que 0 (cero).  
15. En la lista, marque la fila seleccionada.
16. En el campo Descripción, escriba un valor.
17. Haga clic en Guardar.
18. Haga clic en Definir consulta de producto.
19. En la lista, marque la fila seleccionada.
20. En el campo Criterios, especifique o seleccione un valor.
21. Haga clic en Aceptar
22. Cierre la página.


