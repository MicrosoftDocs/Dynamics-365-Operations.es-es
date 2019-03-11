---
title: Configurar lógica de creación de contenedores
description: Este procedimiento describe cómo automatizar la creación de contenedores de cargas en Administración de almacenes.
author: ShylaThompson
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSWaveTemplateTable, InventLocationIdLookup, WHSContainerType, WHSContainerGroup, WHSContainerizationTable, WHSContainerizationBreak, WHSCreateContainerBreak
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: mirzaab
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 56fc6adc2a0eeb5b824089ff4b1b781f3a99a34c
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/29/2019
ms.locfileid: "321694"
---
# <a name="set-up-containerization"></a>Configurar lógica de creación de contenedores

[!include [task guide banner](../../includes/task-guide-banner.md)]

Este procedimiento describe cómo automatizar la creación de contenedores de cargas en Administración de almacenes. La creación de contenedores automatizada crea contenedores y el trabajo de picking para envíos cuando se procesa una oleada y las líneas de trabajo se pueden dividir en cantidades que se ajusten a los contenedores. Esto ayuda a los trabajadores de almacén a seleccionar los artículos directamente en el contenedor elegido. En comparación con el proceso de embalaje manual, las tareas como la creación de contenedores, la asignación de artículos y el cierre de contenedores se automatizan por el sistema. Este procedimiento usa la empresa de demostración USM y lo lleva a cabo un director de almacén.


## <a name="set-up-a-wave-template"></a>Configurar una plantilla de oleada
1. Vaya a Gestión de almacenes > Configurar > Oleadas > Plantillas de oleada.
2. Haga clic en Nuevo.
3. En el campo Nombre de la plantilla de oleada, escriba un valor.
4. En el campo Descripción de la plantilla de oleada, escriba un valor.
5. En el campo Sitio, especifique o seleccione un valor.
6. En el campo Almacén, especifique o seleccione un valor.
7. Expanda la sección Métodos.
    * En el panel Métodos de selección se muestran los métodos para el tipo de plantilla de oleada seleccionado. La plantilla de oleada debe incluir el método de creación de contenedores.  
8. En la lista, busque y seleccione el registro deseado.
9. En el campo Código de paso de oleada, escriba un valor.
    * Especifique un código de paso de oleada para el método agregado, que puede ser cualquier código. Es posible agregar el método más de una vez y asignar diferentes códigos de paso de oleada. Para ello, seleccione Repetible para este método en la página Métodos de procesamiento de oleada.  
10. Haga clic en Guardar.
11. Cierre la página.

## <a name="set-up-a-container-type"></a>Configure un tipo de contenedor.
1. Vaya a Administración de almacenes > Configurar > Contenedores > Tipos de contenedor.
    * Puede definir sus contenedores en la página Tipos de contenedor. Puede configurar las dimensiones físicas de los contenedores, incluida la tara, el peso máximo, el volumen máximo, la longitud máxima, el ancho y el alto. En este ejemplo, tenemos tres tamaños diferentes de cajas.  
2. Haga clic en Nuevo.
3. En el campo Código de tipo de contenedor, escriba un valor.
4. En el campo Tara, escriba un número.
5. Escriba un número en el campo Peso máximo.
6. En el campo Volumen, escriba un número.
7. En el campo Longitud, especifique un número.
8. En el campo Ancho, escriba un número.
9. En el campo Alto, escriba un número.
10. En el campo Descripción, escriba un valor.
11. Haga clic en Guardar.
12. Haga clic en Nuevo.
13. En el campo Código de tipo de contenedor, escriba un valor.
14. En el campo Descripción, escriba un valor.
15. En el campo Tara, escriba un número.
16. Escriba un número en el campo Peso máximo.
17. En el campo Volumen, escriba un número.
18. En el campo Longitud, especifique un número.
19. En el campo Ancho, escriba un número.
20. En el campo Alto, escriba un número.
21. Haga clic en Guardar.
22. Haga clic en Nuevo.
23. En el campo Código de tipo de contenedor, escriba un valor.
24. En el campo Descripción, escriba un valor.
25. En el campo Tara, escriba un número.
26. Escriba un número en el campo Peso máximo.
27. En el campo Volumen, escriba un número.
28. En el campo Longitud, especifique un número.
29. En el campo Ancho, escriba un número.
30. En el campo Alto, escriba un número.
31. Haga clic en Guardar.
32. Cierre la página.

## <a name="set-up-a-container-group"></a>Configurar un grupo de contenedores
1. Vaya a Administración de almacenes > Configurar > Contenedores > Grupos de contenedores.
2. Haga clic en Nuevo.
    * Puede configurar grupos lógicos de tipos de contenedores. Para cada grupo, puede especificar la secuencia en la que se deben empaquetar los contenedores y el porcentaje de relleno de los contenedores. Las dimensiones del artículo se usan para determinar si cabrá en el contenedor. Se usa el contenedor que se encuentra más cercano a las dimensiones de tamaño del artículo. Si tiene varios tipos de contenedor en un grupo, se recomienda que organice la secuencia por tamaños, de modo que el contenedor más grande sea el primero, número 1 en la secuencia, y el contenedor más pequeño el último.    
3. En el campo Id. de grupo de contenedores, escriba un valor.
4. En el campo Descripción, escriba un valor.
5. Haga clic en Nuevo.
6. En la lista, marque la fila seleccionada.
7. En el campo Tipo de contenedor, especifique o seleccione un valor.
8. Haga clic en Nuevo.
9. En la lista, marque la fila seleccionada.
10. En el campo Tipo de contenedor, especifique o seleccione un valor.
11. Haga clic en Nuevo.
12. En la lista, marque la fila seleccionada.
13. En el campo Tipo de contenedor, especifique o seleccione un valor.
14. Haga clic en Guardar.
15. Cierre la página.

## <a name="set-up-a-container-build-template"></a>Configurar una plantilla de creación de contenedores
1. Vaya a Administración de almacenes > Configurar > Contenedores > Plantillas de creación de contenedores.
2. Haga clic en Nuevo.
    * La plantilla de creación de contenedores se basa en cuáles de los procesos de creación de contenedores se realizan. Cada plantilla de creación de contenedores define un proceso de creación de contenedores que se usará por una plantilla de oleada. La opción Editar consulta le permite definir las condiciones en las que se procesará la plantilla seleccionada. Por ejemplo, puede que desee ejecutar solo la creación de contenedores para clientes, productos o almacenes específicos, o puede agregar los intervalos de consultas correspondientes a la plantilla. El campo Código de paso de oleada es cómo una plantilla de creación de contenedores se vincula a los pasos de una plantilla de oleada. Cuando se ejecuta una oleada, determina qué plantilla de creación de contenedores se usan para iniciar la creación de contenedores. El campo Tipos de consulta base determina qué embalar y en qué se basará la consulta del filtro.  
3. En la lista, marque la fila seleccionada.
4. En el campo Id. de plantilla de contenedor, escriba un valor.
5. En el campo Id. de grupo de contenedores, especifique o seleccione un valor.
6. En el campo Código de paso de oleada, escriba un valor.
7. Active la casilla Permitir selecciones divididas.
8. Haga clic en Guardar.
9. Haga clic en Restricciones de combinación de contenedor.
    * Las interrupciones de lógica de combinación le permiten configurar reglas para embalar líneas de asignación en contenedores. Por ejemplo, si agrega el campo Número de artículo, cuando los artículos se asignen a los contenedores, se crearán un nuevo contenedor cuando haya un nuevo número de artículo. Esto evitará que los trabajadores embalen líneas de asignación para dos clientes diferentes en el mismo contenedor.  
10. Haga clic en Nuevo.
11. En el campo Tabla, seleccione una opción.
12. En el campo Selección de campo, especifique o seleccione un valor.
13. Haga clic en Aceptar

