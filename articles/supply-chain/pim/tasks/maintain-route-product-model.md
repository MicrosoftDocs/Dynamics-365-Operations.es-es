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
ms.openlocfilehash: 022db87d0a26efa948a618344ed392ab638b8790
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/01/2021
ms.locfileid: "5817998"
---
# <a name="maintain-route-for-a-product-model"></a>Mantener ruta para un modelo de producto

[!include [banner](../../includes/banner.md)]

La ejecución de este procedimiento requiere que existe un modelo de configuración de producto. Este procedimiento usa el modelo Altavoz superior en la empresa de demostración de datos USMF para guiarle por el proceso.


## <a name="add-a-route-operation"></a>Agregar un nodo de ruta
1. Haga clic en Definición de modelo de variante del producto.
2. Haga clic en Modelos de configuración del producto.
3. En la lista, busque y seleccione el registro deseado.
    * Seleccione el modelo Altavoz superior para este ejercicio.  
4. En la lista, haga clic en el vínculo de la fila seleccionada.
5. Expanda la sección Operaciones de ruta.
6. Haga clic en Agregar.
7. En el campo Nombre, escriba un valor.
8. En el campo Descripción, escriba un valor.
9. Haga clic en Guardar.

## <a name="enter-route-operation-details"></a>Especificar detalles de operación de ruta
1. Haga clic en Detalles de operación de ruta.
2. En el campo Operación, especifique o seleccione un valor.
3. El campo Nº de oper. N. º especifique un número.
    * Los números de operación determinan la secuencia de ruta.  
    * Cada propiedad de una operación de ruta puede obtener un valor estático o se puede asignar a un atributo. La asignación a un atributo dará lugar al valor que se está estableciendo como parte de la configuración.  
4. En el campo Grupo de rutas, especifique o seleccione un valor.
    * El grupo de rutas determina el comportamiento esencial de la gestión de costes, el consumo y la configuración.  
5. Haga clic en la pestaña Configurar.
6. Haga clic en la ficha Tiempos.
7. En el campo Cantidad de proceso, especifique un número.
    * Determine cuántos se procesarán durante una operación.  
8. En el campo Horas/tiempo, especifique un número.
    * Escriba el coeficiente de tiempo.  
9. Active la casilla Establecer.
10. En el campo Tiempo de ejecución, especifique un número.
    * Determine el tiempo de procesamiento para la cantidad que ha especificado.  
11. Haga clic en la ficha Requisitos de recursos.
12. Haga clic en Agregar.
13. En la lista, marque la fila seleccionada.
14. En el campo Tipo de requisito, seleccione una opción.
    * Decida si desea especificar recursos o capacidades específicos que debe poseer.  
15. En el campo Requisito, especifique o seleccione un valor.
16. Haga clic en Aceptar



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]