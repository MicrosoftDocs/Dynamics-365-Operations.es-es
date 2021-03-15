---
title: Configurar un perfil de visión general de recepción de artículos
description: Este tema se centra en la configuración de un perfil general de llegadas.
author: ShylaThompson
manager: tfehr
ms.date: 07/30/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WMSArrivalOverviewProfile
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Distribution
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 5ecfe132d9b0e096c5fdf015f80a6efb34c9b178
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/15/2021
ms.locfileid: "4961448"
---
# <a name="set-up-an-item-arrival-overview-profile"></a>Configurar un perfil de visión general de recepción de artículos

[!include [banner](../../includes/banner.md)]]

Este tema se centra en la configuración de un perfil general de llegadas. El perfil general de llegadas es una recopilación de reglas que se aplicarán cuando un usuario abra la página Visión general de llegadas. Puede utilizar este procedimiento en la empresa de datos de demostración USMF. Este procedimiento normalmente se llevaría a cabo por un empleado de recepción.

1. En el panel de navegación, vaya a **Módulos > Gestión de inventarios > Configuración > Distribución > Perfiles de visión general de llegadas**.
2. Seleccione **Nuevo**. Dado que casi siempre trabajará en el mismo almacén para descargar cargas completas de camión, debe crear un perfil general de llegadas para simplificar el proceso de registrar los artículos recibidos.  
3. En el campo **Nombre de perfil de visión general de llegadas**, escriba un valor.
4. En el campo **Mostrar líneas**, seleccione una opción. Seleccione las líneas que desee mostrar para las recepciones:  

    - **Todo**: permite mostrar todas las líneas, independientemente de su estado.   
    - **En curso**: permite mostrar líneas para recepciones en las que el progreso sea Completo o Parcialmente. Esto significa que, para cada línea, se ha registrado toda la cantidad o una parte en un diario de recepción.   
    - **Incompleto**: permite mostrar líneas para recepciones en las que el progreso sea Ninguno o Parcialmente. Esto significa que, para cada línea, se ha registrado toda la cantidad o una parte en un diario de recepción.  

5. Expanda o contraiga la sección **Opciones de llegada**.
6. En el campo **Días hacia adelante**, escriba un valor. Esto establece un filtro para mostrar líneas de recepción previstas dentro de los próximos días (según el número que se establezca).  
7. En el campo **Días hacia atrás**, escriba un valor. Esto establece un filtro para mostrar líneas de recepción previstas para varios días antes de hoy.  
8. En el campo **Almacenes**, escriba un valor. Aplique un filtro por uno o varios almacenes.  
9. En el campo **Modo de entrega**, seleccione un valor. Esto establece un filtro para mostrar solo las líneas de recepción con este modo de entrega.  
10. En el campo **Nombre**, seleccione WHS.
11. En el campo **Almacén**, seleccione el almacén 24. Este es el almacén predeterminado que se usará para las líneas de recepción registradas que usen este perfil.  
12. En el campo **Ubicación**, seleccione **Baydoor**. Esta es la ubicación predeterminada que se usará para las líneas de recepción registradas que usen este perfil.  
13. Expanda o contraiga la sección **Detalles de consulta de llegada**.
14. En el campo **Restringir a sitio**, seleccione el sitio 2. Esto establece un filtro para mostrar solo las líneas de recepción con este sitio.  
15. Establezca la opción **Pedidos de compra** en **Sí**. Seleccione líneas de recepción de pedidos de compra.  
16. Establezca la opción Pedidos de **transferencia** en **Sí**. Seleccione líneas de recepción de pedidos de transferencia.  
17. Seleccione **Guardar**.
18. Cierre la página.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]