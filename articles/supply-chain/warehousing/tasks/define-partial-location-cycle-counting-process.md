---
title: Definir proceso de recuento cíclico de ubicaciones parcial
description: Al usar planes de recuento cíclico para crear trabajos de recuento, puede dirigir las operaciones de recuento en curso solicitando que solo los productos específicos y las variantes de producto se cuenten en lugar de todos los inventarios disponibles en la ubicación.
author: Mirzaab
ms.date: 06/23/2017
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: WHSRFMenuItemCycleCount, WHSCycleCountPlan, WHSCycleCountPlanListPage, WHSWorkTemplateTable
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 7c179b7f6e0b8546e20204a971cb2951c7b62d7b
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/29/2021
ms.locfileid: "7579985"
---
# <a name="define-partial-location-cycle-counting-process"></a>Definir proceso de recuento cíclico de ubicaciones parcial 

[!include [banner](../../includes/banner.md)]

Al usar planes de recuento cíclico para crear trabajos de recuento, puede dirigir las operaciones de recuento en curso solicitando que solo los productos específicos y las variantes de producto se cuenten en lugar de todos los inventarios disponibles en la ubicación. Al filtrar según productos específicos, el responsable del almacén puede reducir los costes generales de revisión, ayudar a evitar errores de consolidación y ahorrar tiempo. Normalmente, un administrador de almacén realiza las tareas de configuración. Puede explorar este procedimiento en los datos de la empresa de demostración USMF o utilizar sus propios datos.


## <a name="create-a-cycle-counting-work-template"></a>Cree una plantilla de trabajo de recuento cíclico
1. Vaya a Gestión de almacenes > Configurar > Trabajo > Plantillas de trabajo.
2. En el campo Tipo de pedido de trabajo, seleccione "Recuento cíclico".
3. Haga clic en Nuevo.
4. En el campo Número de secuencia, especifique un número.
    * El criterio de ordenación es del número más pequeño al número más grande. El valor debe ser mayor que 0 (cero).  
5. En la lista, marque la fila seleccionada.
6. En el campo Plantilla de trabajo, escriba un valor.
7. En el campo Descripción de la plantilla de trabajo, escriba un valor.
8. En el campo Id. del grupo de trabajo, especifique o seleccione un valor.
9. En el campo Prioridad de trabajo, especifique un número.
10. Haga clic en Guardar.
11. Haga clic en Nuevo.
12. En la lista, marque la fila seleccionada.
13. En el campo Tipo de trabajo, seleccione "Recuento".
14. En el campo Identificador de la clase de trabajo, especifique o seleccione un valor.
15. Haga clic en Guardar.
16. Haga clic en Saltos de línea de trabajo.
17. Haga clic en Nuevo.
18. En el campo Número de secuencia, especifique un número.
    * El criterio de ordenación es del número más pequeño al número más grande. El valor debe ser mayor que 0 (cero).  
19. Haga clic en Guardar.
20. Cierre la página.
21. Cierre la página.

## <a name="create-a-cycle-counting-plan"></a>Cree un plan de recuento cíclico
1. Vaya a Administración de almacenes > Configuración > Recuento de ciclos > Planes de recuento cíclico.
2. Haga clic en Nuevo.
3. En el campo Id. de plan de recuento cíclico, escriba un valor.
4. En el campo Descripción, escriba un valor.
5. En el campo Número máximo de recuentos cíclicos, especifique un número.
6. En el campo Plantilla de trabajo, especifique o seleccione un valor.
7. Haga clic en Nuevo.
8. En el campo Número de secuencia, especifique un número.
    * El criterio de ordenación es del número más pequeño al número más grande. El valor debe ser mayor que 0 (cero).  
9. En el campo Descripción, escriba un valor.
10. Haga clic en Guardar.
11. Haga clic en Definir consulta de producto.
12. En la lista, marque la fila seleccionada.
13. En el campo Criterios, especifique o seleccione un valor.
14. Haga clic en Aceptar
15. Cierre la página.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]