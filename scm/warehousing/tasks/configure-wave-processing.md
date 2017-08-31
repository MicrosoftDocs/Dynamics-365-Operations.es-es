--- 
title: Configurar procesamiento de oleadas
description: "En esta guía se describe cómo configurar los criterios que determinan qué trabajo se genera para un almacén cuando se procesa una oleada y si las oleadas se procesan manual o automáticamente."
author: YuyuScheller
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
ms.author: mirzaab
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 9b947a02be981155053e33a4ef20e19bf2a194a5
ms.openlocfilehash: 50988c689995dbb957af760c9c2c3b823f557c86
ms.contentlocale: es-es
ms.lasthandoff: 07/27/2017

---
# <a name="configure-wave-processing"></a>Configurar procesamiento de oleadas

[!include[task guide banner](../../includes/task-guide-banner.md)]

En esta guía se describe cómo configurar los criterios que determinan qué trabajo se genera para un almacén cuando se procesa una oleada y si las oleadas se procesan manual o automáticamente. Especifique los criterios configurando consultas y plantillas de oleada que hagan coincidir una oleada con las líneas emitidas en pedidos de ventas, pedidos de producción o pedidos kanban. El procesamiento de oleadas se usa en almacenes que usan la funcionalidad del módulo Administración de almacenes, y no los que usan la funcionalidad del módulo Gestión del inventario. Puede ejecutar este procedimiento en la empresa USMF de los datos de prueba.

1. Vaya a Gestión de almacenes > Configurar > Oleadas > Plantillas de oleada.
2. Haga clic en Nuevo.
3. En el campo Nombre de la plantilla de oleada, escriba un valor.
    * Al configurar una plantilla de oleada, especifica la secuencia en la que las plantillas se conciliarán con las líneas liberadas en pedidos de ventas, pedidos de producción o kanbans. Cuando una línea se libera al almacén o a producción, usa la primera plantilla de oleada para la que cumple los criterios. Se recomienda que configure las plantillas con los criterios más específicos en la parte superior de la lista. Cuanto más amplios sean los criterios, será más probable que una línea cumpla los criterios y esto podría originar líneas asignadas en la oleada incorrecta.  
4. En el campo Descripción de la plantilla de oleada, escriba un valor.
5. En el campo Sitio, especifique o seleccione un valor.
    * Si está usando USMF, puede seleccionar el sitio 2.  
6. En el campo Almacén, especifique o seleccione un valor.
    * Si está usando USMF, puede seleccionar el almacén 24.  
7. Establezca el campo Automatizar la creación de oleadas en Sí.
    * Active esta opción para crear automáticamente una oleada cuando un pedido de ventas, un pedido de producción o un kanban se libera al almacén.  
8. Establezca la opción Procesar oleada para su liberación al almacén en Sí. 
    * Active esta opción para procesar automáticamente la oleada y crear trabajo cuando una línea se libera al almacén.  
9. Establezca la opción Liberación automática de oleada en Sí. 
    * Active esta opción para liberar la oleada automáticamente. El trabajo de picking se crea y se pone a disposición en los dispositivos móviles.  
10. Establezca la opción Asignar a oleadas abiertas en Sí. 
    * Las líneas se asignan a oleadas basadas en el filtro de consulta de la plantilla de oleada.  
11. Establezca la opción Procesar la oleada automáticamente al alcanzar el umbral en Sí. 
    * Active esta opción para procesar automáticamente la oleada cuando sus valores lleguen a los umbrales del peso, el envío y las líneas especificadas en el grupo de campos Umbrales de oleada. Esta opción sólo está disponible si se ha seleccionado Envío en el campo Tipo de plantilla oleada.  
12. Establezca la opción Automatizar liberación de trabajo de reabastecimiento en Sí. 
    * Seleccione esta opción para crear trabajo de reabastecimiento basado en demandas y libérelo automáticamente. Debe agregar el método de oleada de reabastecimiento en la plantilla de oleada, y crear una plantilla de reabastecimiento del tipo Demanda de oleadas.  
13. Expanda la sección Métodos.
    * Los métodos de plantilla de oleada le permiten controlar la secuencia de actividades que atraviesa cada oleada cuando se procesa. Por ejemplo, puede que tenga un método para el reabastecimiento de oleada. Si agrega un método, se muestra automáticamente en la ubicación adecuada de la secuencia de pasos. Si ha configurado la opción Automatizar liberación de trabajo de reabastecimiento en sí, debe agregar el método de abastecimiento aquí.  
    * Los atributos de oleada actúan como filtros, para restringir el tipo de artículos que pueden usar la oleada. Por ejemplo, podría especificar un grupo de artículos.  
14. Haga clic en Guardar.
15. Cierre la página.
16. Vaya a Gestión de almacenes > Configurar > Parámetros de gestión de inventario y almacenes.
17. Expanda la sección Procesamiento de oleada.
18. En el campo Grupo de lotes de procesamiento de oleadas, especifique o seleccione un valor.
19. Establezca la opción Procesar oleadas en lote en Sí.
20. En el campo Esperar bloqueo (ms), escriba un número.
    * Especifique el tiempo, en milisegundos, que un paso de asignación esperará a un recurso del sistema bloqueado por otro paso de la asignación. Cuando se supere este tiempo, la oleada no se procesará y se mostrará un mensaje de error.  
21. Haga clic en Guardar.
22. Cierre la página.
23. Vaya a Control de producción > Configurar > Parámetros de control de producción.
24. En el campo Liberar al almacén, seleccione una opción.
    * Para los pedidos de ventas y las órdenes de kanban, el inventario se debe reservar antes de que el pedido se libere al almacén. Si no, los artículos o las líneas de asignación no se pueden procesar en una oleada. Para los pedidos de producción, también tiene la opción de elegir Permitir la reserva parcial. Por ejemplo, esto resulta útil si tiene los materiales que necesita para iniciar una producción, y puede esperar hasta que los materiales adicionales estén disponibles para finalizar el proceso. Si selecciona esta opción, debe repetir manualmente el proceso de liberación al almacén cuando los materiales adicionales estén disponibles.  
25. Cierre la página.


