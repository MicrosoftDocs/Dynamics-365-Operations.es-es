--- 
title: Configurar listas maestras de tasas
description: "Este procedimiento muestra cómo configurar una tasa maestra."
author: BibiSp
manager: AnnBe
ms.date: 11/11/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: bis
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: bis
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: b7c02e5a6f5eeee270ca4b6f91e90f7799c2ca11
ms.contentlocale: es-es
ms.lasthandoff: 09/29/2017

---
# <a name="set-up-rate-masters"></a>Configurar listas maestras de tasas

[!INCLUDE [task guide banner](../../includes/task-guide-banner.md)]

Este procedimiento muestra cómo configurar una tasa maestra. El administrador de logística configura normalmente tasas maestras, en función de los contratos firmados con los transportistas. En este caso, configurará una tasa maestra para una compañía aérea. La empresa de datos de prueba utilizada para crear este procedimiento es USMF.


## <a name="set-up-rate-master"></a>Configuración de tasas maestras
1. Vaya a Administración de transporte > Configuración > Clasificación > Tasa maestra.
2. Haga clic en Nuevo.
3. En el campo Tasa maestra, escriba un valor.
4. En el campo Nombre, escriba un valor.
5. En el campo Id. de metadatos de clasificación, haga clic en el botón desplegable para abrir la búsqueda.
    * El identificador de metadatos de clasificación determinará los datos necesarios para la tasa maestra, ya que define los metadatos previstos por el motor de TMS que usa esta tasa maestra.  
6. Para este ejemplo, seleccione la opción P2P.
7. En la lista, haga clic en el vínculo de la fila seleccionada.
8. Haga clic en Guardar.

## <a name="set-up-rate-base"></a>Configuración de la base de tasa
1. Haga clic en Base de tasa.
    * La base de tasa determina la tasa del transportista, y se puede usar para configurar una estructura de tarifa al estructurar las tasas en los puntos de interrupción definidos en el maestro de interrupción.  
2. Haga clic en Nuevo.
3. En el campo Base de tasa, escriba un valor.
4. En el campo Nombre, escriba un valor.
5. En el campo Maestro de interrupción, haga clic en el botón desplegable para abrir la búsqueda.
    * Los maestros de interrupción se usan para definir la estructura de precios y sus puntos de interrupción. La estructura de precios usa precios con niveles basados en dimensiones físicas.  
6. Para este ejemplo, use el peso.
7. En la lista, haga clic en el vínculo de la fila seleccionada.
8. Expanda la sección Detalles.
9. Haga clic en Nuevo.
10. En el campo Código postal de la ubicación de devolución de, especifique "30301".
11. En el campo Código postal de la ubicación de devolución a, especifique "30318".
12. En el campo País o región de la ubicación de devolución, escriba "EE. UU.".
13. En el campo <1.00 Lbs, escriba "100".
    * Inserte la tasa por libras si el peso total de la carga es inferior a 1 libra.  
14. En el campo <5,00 Lbs, escriba "300".
    * Inserte la tasa por libras si el peso total de la carga es inferior a 5 libras.  
15. En el campo <20,00 Lbs, escriba "500".
    * Inserte la tasa por libra si el peso total de la carga es inferior a 20 libras.  
16. En el campo <100,00 Lbs, escriba "1000".
    * Inserte la tasa por libra si el peso total de la carga es inferior a 100 libras.  
17. En el campo <1000,00 Lbs, escriba "3000".
    * Inserte la tasa por libra si el peso total de la carga es inferior a 1000 libras.  
18. Haga clic en Guardar.
19. Cierre la página.

## <a name="assign-rate-base"></a>Asignación de la base de tasa
1. Expanda la sección Asignaciones de base de tasa.
2. Haga clic en Nuevo.
    * Puede tener varias asignaciones de base de tasa para cada tasa maestra. Esto permite crear varios puntos de precios distintos para cada transportista, en función de los destinos, los servicios o distintas bases de tasa. En este procedimiento creará solo una asignación de base de tasa.  
3. En el campo Nombre, escriba un valor.
4. En el campo Base de tasa, haga clic en el botón desplegable para abrir la búsqueda.
5. En la lista, haga clic en el vínculo de la fila seleccionada.
6. En el campo Servicio, haga clic en el botón desplegable para abrir la búsqueda.
7. En la lista, busque y seleccione el registro deseado.
8. En la lista, haga clic en el vínculo de la fila seleccionada.
9. En el campo Código postal de recogida, escriba "98052".
    * Especifique desde qué código postal será válida esta asignación de base de tasa.    
10. En el campo País o región de recogida, escriba "EE. UU.".
11. Haga clic en Guardar.


