---
title: Ejemplo de configuración del procesamiento de oleadas
description: En este tema proporciona un ejemplo de cómo configurar los criterios que determinan qué trabajo se genera para un almacén cuando se procesa una oleada y si las oleadas se procesan de forma manual o automática.
author: Mirzaab
ms.date: 03/17/2021
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: WHSWaveTemplateTable, InventLocationIdLookup, WHSParameters, ProdParameters, whswavetablecreatenew, WHSWaveTable, WHSWaveAttributes, WHSKanbanWaveTable, WHSWaveTableListPage, WHSKanbanWaveTableListPage
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Distribution
ms.author: mirzaab
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: d462427b85e12a45058a2fdea7901a83d9e85e5a562376dd438c69dec1ee8948
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2021
ms.locfileid: "6769380"
---
# <a name="configure-wave-processing-example"></a>Ejemplo de configuración del procesamiento de oleadas

[!include [banner](../../includes/banner.md)]

En este tema proporciona un ejemplo de cómo configurar los criterios que determinan qué trabajo se genera para un almacén cuando se procesa una oleada y si las oleadas se procesan de forma manual o automática. Especifique los criterios configurando consultas y plantillas de oleada que hagan coincidir una oleada con las líneas emitidas en pedidos de ventas, pedidos de producción o pedidos kanban.

## <a name="enable-sample-data"></a>Habilitar datos de muestra

Para trabajar en este escenario mediante el uso de los registros y valores de muestra que se especifican aquí, debe estar en un sistema donde estén instalados los datos de demostración estándar. También debe seleccionar la entidad legal **USMF** antes de comenzar.

## <a name="example-scenario-configure-wave-processing"></a>Escenario de ejemplo: configurar procesamiento de oleadas

Este escenario de ejemplo recorre muchas de las diversas configuraciones que afectan la forma en que se crean, rellenan, procesan y liberan las oleadas.

1. Vaya a **Panel de exploración > Módulos > Gestión de almacenes > Configurar > Oleadas > Plantillas de oleada**.
1. Seleccione **Nuevo**.
1. En el campo **Nombre de la plantilla de oleada**, escriba un valor. Al configurar una plantilla de oleada, especifica la secuencia en la que las plantillas se conciliarán con las líneas liberadas en pedidos de ventas, pedidos de producción o kanbans. Cuando una línea se libera al almacén o a producción, usa la primera plantilla de oleada para la que cumple los criterios. Se recomienda que configure las plantillas con los criterios más específicos en la parte superior de la lista. Cuanto más amplios sean los criterios, será más probable que una línea cumpla los criterios y esto podría originar líneas asignadas en la oleada incorrecta.  
1. En el campo **Descripción de la plantilla de oleada**, escriba un valor.
1. En el campo **Sitio**, especifique o seleccione un valor. Si está usando USMF, puede seleccionar el sitio 2.  
1. En el campo **Almacén**, especifique o seleccione un valor. Si está usando USMF, puede seleccionar el almacén 24.  
1. Establezca el campo **Automatizar la creación de oleadas** en **Sí**. Active esta opción para crear automáticamente una oleada cuando un pedido de ventas, un pedido de producción o un kanban se libera al almacén.  
1. Establezca la opción **Procesar oleada para su liberación al almacén** en **Sí**. Active esta opción para procesar automáticamente la oleada y crear trabajo cuando una línea se libera al almacén.  
1. Establezca la opción **Liberación automática de oleada** en **Sí**. Active esta opción para liberar la oleada automáticamente. El trabajo de picking se crea y se pone a disposición en los dispositivos móviles.  
1. Establezca la opción **Asignar a oleadas abiertas** en **Sí**. Las líneas se asignan a oleadas basadas en el filtro de consulta de la plantilla de oleada.  
1. Establezca la opción **Procesar la oleada automáticamente al alcanzar el umbral** en **Sí**. Active esta opción para procesar automáticamente la oleada cuando sus valores lleguen a los umbrales del peso, el envío y las líneas especificadas en el grupo de campos **Umbrales de oleada**. Esta opción sólo está disponible si se ha seleccionado **Envío** en el campo **Tipo de plantilla oleada**.  
1. Establezca la opción **Automatizar liberación de trabajo de reabastecimiento** en **Sí**. Seleccione esta opción para crear trabajo de reabastecimiento basado en demandas y libérelo automáticamente. Debe agregar el método de oleada de reabastecimiento en la plantilla de oleada, y crear una plantilla de reabastecimiento usando el tipo **Demanda de oleadas**.  
1. Utilice la configuración en el grupo archivado **Valores predeterminados** para asignar atributos de oleada. Los atributos de oleada actúan como filtros, para restringir el tipo de artículos que pueden usar la oleada. Por ejemplo, podría especificar un grupo de artículos.  
1. Expanda la sección **Métodos** sección y establezca las acciones tomadas por la plantilla de oleada. Los métodos de plantilla de oleada le permiten controlar la secuencia de actividades que atraviesa cada oleada cuando se procesa. Por ejemplo, puede que tenga un método para el reabastecimiento de oleada. Si agrega un método, se muestra automáticamente en la ubicación adecuada de la secuencia de pasos. Si ha configurado la opción **Automatizar liberación de trabajo de reabastecimiento** en **Sí**, debe agregar el método de abastecimiento aquí.  
1. Seleccione **Guardar**.
1. Cierre la página.
1. Vaya a **Gestión de almacenes > Configurar > Parámetros de gestión de inventario y almacenes**.
1. Expanda la sección **Procesamiento de oleada**.
1. En el campo **Grupo de lotes de procesamiento de oleadas**, especifique o seleccione un valor.
1. Establezca la opción **Procesar oleadas en lote** en **Sí**.
1. En el campo **Esperar bloqueo (ms)**, escriba un número. Especifique el tiempo, en milisegundos, que un paso de asignación esperará a un recurso del sistema bloqueado por otro paso de la asignación. Cuando se supere este tiempo, la oleada no se procesará y se mostrará un mensaje de error.  
1. Seleccione **Guardar**.
1. Cierre la página.
1. Vaya a **Panel de exploración > Módulos > Control de producción > Configurar > Parámetros de control de producción**.
1. En el campo **Liberar al almacén**, seleccione una opción.

    Para los pedidos de ventas y las órdenes de kanban, el inventario se debe reservar antes de que el pedido se libere al almacén. Si no, los artículos o las líneas de asignación no se pueden procesar en una oleada. Para los pedidos de producción, también tiene la opción de elegir **Permitir la reserva parcial**. Por ejemplo, esto resulta útil si tiene los materiales que necesita para iniciar una producción y puede esperar hasta que los materiales adicionales estén disponibles para finalizar el proceso. Si selecciona esta opción, debe repetir manualmente el proceso de liberación al almacén cuando los materiales adicionales estén disponibles.
1. Cierre la página.

## <a name="additional-resources"></a>Recursos adicionales

- [Creación y procesamiento de oleadas](../wave-processing.md)

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
