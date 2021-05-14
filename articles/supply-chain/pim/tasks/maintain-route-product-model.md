---
title: Mantener ruta para un modelo de producto
description: La ejecución de este procedimiento requiere que existe un modelo de configuración de producto.
author: ShylaThompson
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: DefaultDashboard, EcoResProductVariantMaintainWorkspace, PCProductConfigurationModelListPage, PCProductConfigurationModelDetails, PCRouteOperationDetails, WrkCtrCapabilityLookUp
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 45c6b1e6e75645bb17ce4defa0bca0e6d2131b6e
ms.sourcegitcommit: fa99a36c3d30d0c0577fd3f63ed6bf2f71599e40
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/20/2021
ms.locfileid: "5921274"
---
# <a name="maintain-route-for-a-product-model"></a>Mantener ruta para un modelo de producto

[!include [banner](../../includes/banner.md)]

La ejecución de este procedimiento requiere que existe un modelo de configuración de producto. Este procedimiento usa el modelo Altavoz superior en la empresa de demostración de datos USMF para guiarle por el proceso.

## <a name="add-a-route-operation"></a>Agregar un nodo de ruta

1. Vaya a **Gestión de información de productos \> Productos \> Modelos de configuración del producto**.
1. En la lista, busque y seleccione el registro deseado.
    * Seleccione el modelo Altavoz superior para este ejercicio.  
1. En la lista, seleccione el vínculo de la fila seleccionada.
1. Expanda la sección **Operaciones de ruta**.
1. Seleccione **Agregar**.
1. En el campo **Nombre**, escriba un valor.
1. En el campo **Descripción**, escriba un valor.
1. Seleccione **Guardar**.

## <a name="enter-route-operation-details"></a>Especificar detalles de operación de ruta

1. Seleccione **Detalles de operación de ruta**.
1. En el campo **Operación**, especifique o seleccione un valor.
1. En el campo **N.º oper.** especifique un número.
    * Los números de operación determinan la secuencia de ruta.  
    * Cada propiedad de una operación de ruta puede obtener un valor estático o se puede asignar a un atributo. La asignación a un atributo dará lugar al valor que se está estableciendo como parte de la configuración.  
1. En el campo **Grupo de rutas**, especifique o seleccione un valor.
    * El grupo de rutas determina el comportamiento esencial de la gestión de costes, el consumo y la configuración.  
1. Seleccione la pestaña **Configuración**.
1. Seleccione la pestaña **Veces**.
1. En el campo **Cantidad de proceso**, especifique un número.
    * Determine cuántos se procesarán durante una operación.  
1. En el campo **Horas/tiempo**, especifique un número.
    * Escriba el coeficiente de tiempo.  
1. Seleccione la casilla **Establecer**.
1. En el campo **Tiempo de ejecución**, especifique un número.
    * Determine el tiempo de procesamiento para la cantidad que ha especificado.  
1. Seleccione la ficha **Requisitos de recursos**.
1. Seleccione **Agregar**.
1. En la lista, marque la fila seleccionada.
1. En el campo **Tipo de requisito**, seleccione una opción.
    * Decida si desea especificar recursos o capacidades específicos que debe poseer.  
1. En el campo **Requisito**, especifique o seleccione un valor.
1. Seleccione **Aceptar**.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]