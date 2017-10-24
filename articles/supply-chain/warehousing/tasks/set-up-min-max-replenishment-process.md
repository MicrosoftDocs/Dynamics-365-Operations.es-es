--- 
title: "Configurar un proceso de reabastecimiento mínimo-máximo"
description: "Este procedimiento le muestra cómo configurar un nuevo proceso de reabastecimiento que usa la estrategia de reabastecimiento mínima/máxima."
author: perlynne
manager: AnnBe
ms.date: 06/07/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: bis
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: perlynne
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 02af5d1beb2d4eb6a7162b47c42854725fbdbec2
ms.contentlocale: es-es
ms.lasthandoff: 09/29/2017

---
# <a name="set-up-a-min-max-replenishment-process"></a>Configurar un proceso de reabastecimiento mínimo-máximo

[!include[task guide banner](../../includes/task-guide-banner.md)]

Este procedimiento le muestra cómo configurar un nuevo proceso de reabastecimiento que usa la estrategia de reabastecimiento mínima/máxima. Cuando el inventario se encuentran por debajo del nivel mínimo, el trabajo se creará para reabastecer la ubicación. El procedimiento también muestra cómo usar ubicaciones de picking fijas para permitir la reposición incluso si el inventario se encuentra por debajo del nivel mínimo, y cómo habilitar el proceso de reabastecimiento para ejecutarse con regularidad mediante un trabajo por lotes. Estas tareas las realizará normalmente el director del almacén. Puede ejecutar este procedimiento en la empresa de datos de demostración USMF con los valores del ejemplo en las notas o puede ejecutarlo en sus propios datos. Si está usando sus propios datos, asegúrese de que tiene un almacén que está habilitado para los procesos de Administración de almacenes.


## <a name="create-a-fixed-picking-location"></a>Crear una ubicación de picking fija
1. Vaya a Gestión de almacenes > Configurar > Almacén > Ubicaciones fijas.
    * Esta es una tarea opcional para el reabastecimiento mínimo-máximo, pero si usa la ubicación de picking fija, esto permite que se reabastezcan las existencias incluso si caen por debajo del nivel mínimo, ya que el sistema puede determinar qué artículos se deben reabastecer, incluso si no queda ninguno.  
2. Haga clic en Nuevo.
3. En el campo Número de artículo, especifique o seleccione un valor.
    * Si está usando USMF, puede seleccionar el artículo A0001.  
4. En el campo Sitio, especifique o seleccione un valor.
    * Si está usando USMF, puede seleccionar el sitio 2.  
5. En el campo Almacén, especifique o seleccione un valor.
    * Si está usando USMF, puede seleccionar el almacén 24.  
6. En el campo Ubicación, especifique o seleccione un valor.
    * Si está usando USMF, puede seleccionar CP-003.  
7. Cierre la página.

## <a name="create-a-replenishment-location-directive"></a>Crear una directiva de ubicación de reabastecimiento
1. Vaya a Gestión de almacenes > Configurar > Directivas de ubicación.
    * Los directorios de ubicación se usan para determinar de dónde se deben seleccionar los artículos en el proceso de reabastecimiento.  
2. En el campo Tipo de pedido de trabajo, seleccione "Reabastecimiento".
3. Haga clic en Nuevo.
4. En el campo Nombre, escriba un valor.
5. En el campo Tipo de trabajo, seleccione "Seleccionar".
6. En el campo Sitio, especifique o seleccione un valor.
    * Si está usando USMF, puede seleccionar el sitio 2.  
7. En el campo Almacén, especifique o seleccione un valor.
    * Si está usando USMF, puede seleccionar el almacén 24.  
8. Haga clic en Guardar.
9. Haga clic en Nuevo.
10. En la lista, marque la fila seleccionada.
11. En el campo Cantidad final, especifique un número.
    * Por ejemplo, puede establecerlo en 9999.  
12. Active la casilla Permitir división.
    * Si selecciona esta opción, el proceso de creación de trabajo permitirá dividir cantidades de línea de trabajo entre múltiples ubicaciones.  
13. Haga clic en Guardar.
14. Haga clic en Nuevo.
15. En la lista, marque la fila seleccionada.
16. En el campo Nombre, escriba un valor.
17. Haga clic en Guardar.
18. Haga clic en Editar consulta.
    * Puede editar esta consulta para agregar restricciones desde las que se puede seleccionar el inventario en el proceso de reabastecimiento. Por ejemplo, podría ser que el inventario solo se debe usar desde el área de almacenaje del almacén.  
19. Haga clic en Aceptar
20. Cierre la página.

## <a name="create-a-replenishment-work-template"></a>Crear una plantilla de trabajo de reabastecimiento
1. Vaya a Gestión de almacenes > Configurar > Trabajo > Plantillas de trabajo.
    * La plantilla de trabajo se usa para guiar al sistema respecto a cómo se debe crear el trabajo de reabastecimiento mínimo o máximo. Como mínimo, debe haber una línea de plantilla de trabajo para un picking y una colocación. La plantilla de trabajo dirá que no es válida hasta que no se haya completado toda la información necesaria.  
2. En el campo Tipo de pedido de trabajo, seleccione "Reabastecimiento".
3. Haga clic en Nuevo.
4. En el campo Plantilla de trabajo, escriba un valor.
5. Haga clic en Guardar.
6. Haga clic en Nuevo.
7. En el campo Tipo de trabajo, seleccione "Seleccionar".
8. En el campo Identificador de la clase de trabajo, especifique o seleccione un valor.
    * Esto se debe ser una clase de trabajo relacionada con el reabastecimiento. Si utiliza USMF, seleccione Reabastecer.  
9. Haga clic en Nuevo.
10. En la lista, marque la fila seleccionada.
11. En el campo Tipo de trabajo, seleccione Colocar.
12. En el campo Identificador de la clase de trabajo, especifique o seleccione un valor.
13. Haga clic en Guardar.
14. Cierre la página.

## <a name="create-a-new-replenishment-template"></a>Crear una nueva plantilla de reabastecimiento
1. Vaya a Administración de almacenes > Configurar > Reabastecimiento > Plantillas de reabastecimiento.
    * La plantilla de reabastecimiento se usa para definir los artículos y las cantidades, y la ubicación para reabastecimiento.  
2. Haga clic en Nuevo.
3. En el campo Plantilla de reabastecimiento, escriba un valor.
    * Asigne un nombre a la plantilla para indicar que es para reabastecimiento mínimo o máximo.  
4. En el campo Descripción, escriba un valor.
5. Active la casilla Permitir demanda de oleadas para usar cantidades sin reservar.
    * Si selecciona esta opción, permite que el reabastecimiento de demanda de oleadas consuma las cantidades relacionadas con el reabastecimiento mínimo o máximo. Por ejemplo, esto podría ser útil si no se procesa inmediatamente el trabajo de reabastecimiento mínimo o máximo, para evitar que se cree el trabajo de reabastecimiento de demanda innecesario.  
6. Haga clic en Nuevo.
7. En el campo Número de secuencia, especifique un número.
8. En el campo Descripción, escriba un valor.
9. En la lista, marque la fila seleccionada.
10. En el campo Unidad de reabastecimiento, especifique o seleccione un valor.
    * Por ejemplo, seleccione uds. Esta configuración es obligatoria. Permite especificar otra unidad de medida para el trabajo de reabastecimiento en comparación con la unidad especificada para los niveles de existencias mínimo y máximo en esta plantilla.  
11. En el campo Plantilla de trabajo, especifique o seleccione un valor.
    * Elija la plantilla de trabajo que ha creado anteriormente.  
12. En el campo Cantidad mínima, escriba un número.
    * Seleccione la cantidad mínima que debe desencandenar el reabastecimiento. Por ejemplo, establezca esto en 50. Es posible dejar este valor establecido en cero, si está reaprovisionando una ubicación fija y la opción Reabastecer solo ubicaciones fijas vacías se establece en Sí. También recomendamos que seleccione la opción Reabastecer solo ubicaciones fijas por motivos de rendimiento.  
13. En el campo Cantidad máxima, escriba un número.
    * Por ejemplo, establezca esto en 100.  
14. En el campo Unidad, especifique o seleccione un valor.
    * Asigne la unidad para las cantidades mínima y máxima. Por ejemplo, establezca esto en uds.  
15. Active la casilla Reabastecer solo ubicaciones fijas vacías.
    * Active esta casilla para reabastecer ubicaciones fijas cuando estén vacías. De lo contrario, solo se reabastecerán las ubicaciones en las que existe una cantidad disponible.  
16. Active la casilla Reabastecer solo ubicaciones fijas.
17. Haga clic en Seleccionar productos.
    * Este es el lugar para definir qué productos se deben reabastecer. Si se selecciona la opción de ubicaciones de picking fijas, también debe definir las ubicaciones en esta consulta. Hay disponibles consultas específicas de variantes además de consultas específicas de productos.  
18. Seleccione la fila Artículos.
19. En el campo Criterios, escriba un valor.
    * Seleccione los artículos que se deben reabastecer en las ubicaciones fijas. Por ejemplo, escriba A* para seleccionar todos los números de artículo que comienzan por A.  
20. Haga clic en Agregar.
    * Agregue la entidad de ubicación (a menos que ya existe) para poder restringir el trabajo de reabastecimiento a las ubicaciones de picking fijas dentro de un área específica del almacén.  
21. En la lista, marque la fila seleccionada.
22. Establezca el campo Tabla en Ubicaciones.
23. En el campo Campo, seleccione Id. de perfil de ubicación.
24. En el campo Criterios, especifique o seleccione un valor.
25. Haga clic en Aceptar
26. Cierre la página.

## <a name="set-the-replenishment-process-to-run-as-a-batch-job"></a>Establecer el proceso de reabastecimiento para que se ejecute como un proceso por lotes
1. Vaya a Administración de almacenes > Reabastecimiento > Reabastecimientos.
    * La página Reabastecimientos le permite configurar el reabastecimiento para que se ejecute como un trabajo por lotes, o para requerir que se inicie manualmente.  
2. Haga clic en Filtro.
3. En la lista, marque la fila seleccionada.
4. En el campo Criterios, especifique o seleccione un valor.
5. Haga clic en Aceptar
6. Expanda la sección Ejecutar en segundo plano.
7. Establezca la opción Procesamiento por lotes en Sí.
8. Haga clic en Periodicidad.
9. Seleccione la opción No hay fecha final.
10. Establezca el patrón de repetición.
    * Por ejemplo, seleccione Días.  
11. Haga clic en Aceptar
12. Haga clic en Aceptar


