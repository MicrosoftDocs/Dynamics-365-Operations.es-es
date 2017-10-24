---
title: "Configurar un perfil de visión general de recepción de artículos"
description: "Esta tarea se centra en la configuración de un perfil general de llegadas."
author: perlynne
manager: AnnBe
ms.date: 11/14/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: YuyuScheller
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: bis
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: f827b4787506cfdec8b9a91c4a68f3293190158a
ms.openlocfilehash: b971e72febbd78ff7c27ad2029e5061b978dc44e
ms.contentlocale: es-es
ms.lasthandoff: 09/29/2017

---
# <a name="set-up-an-item-arrival-overview-profile"></a>Configurar un perfil de visión general de recepción de artículos

[!include[task guide banner](../../includes/task-guide-banner.md)]

Esta tarea se centra en la configuración de un perfil general de llegadas. El perfil general de llegadas es una recopilación de reglas que se aplicarán cuando un usuario abra la página Visión general de llegadas. Puede utilizar este procedimiento en la empresa de datos de demostración USMF. Este procedimiento normalmente se llevaría a cabo por un empleado de recepción.





1. Vaya a Gestión del inventario > Configuración > Distribución > Perfiles de visión general de llegadas.
2. Haga clic en Nuevo.
    * Dado que casi siempre trabajará en el mismo almacén para descargar cargas completas de camión, debe crear un perfil general de llegadas para simplificar el proceso de registrar los artículos recibidos.  
3. En el campo Nombre de perfil de visión general de llegadas, escriba un valor.
4. En el campo Mostrar líneas, seleccione una opción.
    * Seleccione las líneas que mostrar en las recepciones: Todo: mostrar todas las líneas, independientemente del estado.   En curso: mostrar líneas para recepciones en las que el progreso sea Completo o Parcialmente. Esto significa que, para cada línea, se ha registrado toda la cantidad o una parte en un diario de recepción.   Incompleto: mostrar líneas para recepciones en las que el progreso sea Ninguno o Parcialmente. Esto significa que, para cada línea, se ha registrado toda la cantidad o una parte en un diario de recepción.  
5. Expanda o contraiga la sección Opciones de llegada.
6. En el campo Días hacia adelante, escriba un valor.
    * Esto establece un filtro para mostrar líneas de recepción previstas dentro de los próximos días (según el número que se establezca).  
7. En el campo Días hacia atrás, escriba un valor.
    * Esto establece un filtro para mostrar líneas de recepción previstas para varios días antes de hoy.  
8. En el campo Almacenes, escriba un valor.
    * Aplique un filtro por uno o varios almacenes.  
9. En el campo Modo de entrega, seleccione un valor.
    * Esto establece un filtro para mostrar solo las líneas de recepción con este modo de entrega.  
10. En el campo Nombre, seleccione WHS.
11. En el campo Almacén, seleccione el almacén 24.
    * Este es el almacén predeterminado que se usará para las líneas de recepción registradas que usen este perfil.  
12. En el campo Ubicación, seleccione Baydoor.
    * Esta es la ubicación predeterminada que se usará para las líneas de recepción registradas que usen este perfil.  
13. Expanda o contraiga la sección Detalles de consulta de llegada.
14. En el campo Restringir a sitio, seleccione el sitio 2.
    * Esto establece un filtro para mostrar solo las líneas de recepción con este sitio.  
15. Establezca la opción Pedidos de compra en Sí.
    * Seleccione líneas de recepción de pedidos de compra.  
16. Establezca la opción Pedidos de transferencia en Sí.
    * Seleccione líneas de recepción de pedidos de transferencia.  
17. Haga clic en Guardar.
18. Cierre la página.

