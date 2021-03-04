---
title: Secuenciar trabajos de producción para fabricación en procesos
description: Este procedimiento usa productos de pintura como ejemplo para mostrar cómo establecer la secuencia de los pedidos planificados según la prioridad de color y tamaño de paquete.
author: ChristianRytt
manager: tfehr
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ReqTransPo, PMFSeqReqRouteChangesListPage, PMFSeqReqRoute, PMFSeqReqRouteChanges, PMFSeqReqSchedDetailsFactBox, PMFSequenceGroup, PMFSequenceItemTable, PMFSequenceTable, PmfSeqWrkCtrCapRes
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: crytt
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: db2c881f60b6e5251e2bcdf198da9e1c9f39a0e6
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/13/2020
ms.locfileid: "4436811"
---
# <a name="sequence-production-jobs-for-process-manufacturing"></a>Secuenciar trabajos de producción para fabricación en procesos

[!include [banner](../../includes/banner.md)]

Este procedimiento usa productos de pintura como ejemplo para mostrar cómo establecer la secuencia de los pedidos planificados según la prioridad de color y tamaño de paquete. La empresa de datos de prueba utilizada para crear este procedimiento es USPI. Este procedimiento se va a utilizar para el planificador de producción.


## <a name="run-master-planning-for-uspi"></a>Ejecutar planificación maestra para USPI
1. Vaya a Planificación maestra > Planificación maestra > Ejecutar > lanificación maestra.
2. En el campo Plan maestro, haga clic en el botón desplegable para abrir la búsqueda.
3. En la lista, haga clic en el vínculo de la fila seleccionada.
    * Seleccione MasterPlan.  
4. Haga clic en Aceptar
    * Esto inicia la Planificación maestra, incluido el proceso de la secuencia. El proceso puede tardar unos minutos.  

## <a name="view-planned-orders-for-the-paint-products"></a>Ver pedidos planificados para los productos de pintura
1. Vaya a Planificación maestra > Planificación maestra > Pedidos planificados.
2. Expanda el cuadro informativo Detalles del artículo.
3. Expanda el cuadro informativo Detalles de programación.
4. En el campo Plan, haga clic en el botón desplegable para abrir la búsqueda.
5. En la lista, busque y seleccione el registro deseado.
    * Seleccione MasterPlan.  
6. En la lista, haga clic en el vínculo de la fila seleccionada.
7. Use un filtro rápido para filtrar por el campo Código de artículo con el valor 'P300'.
    * Desbloquee para desplazarse a la derecha para ver la fecha de la orden y la fecha de entrega. Observe que estos artículos tienen una fecha de pedido de Hoy y las fechas de entrega para los pedidos planificados no están establecidas en frecuencia tras la prioridad de color y el tamaño del paquete, como se muestra en el nombre del producto. Puede mantener el puntero sobre un número de artículo para ver el nombre del producto y la prioridad.  

## <a name="sequence-planned-orders-for-paint"></a>Establecer en secuencia pedidos planificados para pintura
1. Cierre la página.
2. Vaya a Planificación maestra > Planificación maestra > Pedidos planificados en secuencia.
3. Expanda el cuadro informativo Detalles del artículo.
4. Expanda el cuadro informativo Detalles de programación.
    * Nota: Aquí ve que la fecha y la hora iniciales para los pedidos planificados se establecen en secuencia de acuerdo con el color y el tamaño del paquete dentro de un período de cubo de 28 días. Estos períodos se definen por un número en el campo Campaña. El formulario de pedido planificado secuenciado actúa como el formulario de pedido planificado típico y el planificador de producción puede poner en firme los pedidos planificados aquí.  
5. Marca todas las filas.
6. Haga clic en Aceptar.
    * Esto actualizará los pedidos planificados con la acción de secuencia seleccionada de Posponer o Adelantar.  

## <a name="verify-the-sequence-of-the-planned-orders"></a>Comprobar la secuencia de los pedidos planificados
1. Cierre la página.
2. Vaya a Planificación maestra > Planificación maestra > Pedidos planificados.
3. Expanda el cuadro informativo Detalles del artículo.
4. Expanda el cuadro informativo Detalles de programación.
5. En el campo Plan, haga clic en el botón desplegable para abrir la búsqueda.
6. En la lista, busque y seleccione el registro deseado.
    * Seleccione MasterPlan.  
7. En la lista, haga clic en el vínculo de la fila seleccionada.
8. Use un filtro rápido para filtrar por el campo Código de artículo con el valor 'P300'.
    * Observe que los pedidos se establecen ahora en secuencia según la prioridad de color y tamaño y los pedidos planificados empiezan en la primera fecha de pedido y fecha de entrega. Valide la columna Fecha del pedido o la Fecha inicial en el cuadro desplegable Detalles de programación.  



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]