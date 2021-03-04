---
title: Configurar listas maestras de tasas
description: Este procedimiento muestra cómo configurar una tasa maestra.
author: ShylaThompson
manager: tfehr
ms.date: 10/16/2020
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: TMSBreakMaster,TMSRateMaster,TMSRateMasterBase,TMSRateBaseType, TMSRouteWorkbench
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: b4cca9fd47a5d8c81d7b8a913d0a467bc113b584
ms.sourcegitcommit: fe7ac653efcb1ac6318083f482394b96ed82b4c7
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/29/2020
ms.locfileid: "4437315"
---
# <a name="set-up-rate-masters"></a>Configurar listas maestras de tasas

[!include [banner](../../includes/banner.md)]

Este procedimiento muestra cómo configurar una tasa maestra. El administrador de logística configura normalmente tasas maestras, en función de los contratos firmados con los transportistas. En este caso, configurará una tasa maestra para una compañía aérea. La empresa de datos de prueba utilizada para crear este procedimiento es USMF.

## <a name="set-up-break-master"></a>Configurar un maestro de interrupción

1. Vaya a **Administración de transporte > Configuración > Clasificación > Maestro de interrupción**. Los maestros de interrupción se usan para definir la estructura de precios y sus puntos de interrupción. La estructura de precios usa precios con niveles basados en dimensiones físicas.  
1. Seleccione **Nuevo**.
1. En el campo **Maestro de interrupción**, especifique un valor.
1. En el campo **Nombre**, escriba un valor.
1. En el campo **Tipo de datos**, seleccione el tipo de datos.
1. En el campo **Comparación**, ingrese el tipo de comparación solicitada (usando operadores).
1. En el campo **Unidad de interrupción** especifique los valores de la unidad de interrupción.
1. En la sección **Detalles**, cree tantas pausas como sea necesario para la estructura de precios.
1. Seleccione **Guardar**.

## <a name="set-up-rate-master"></a>Configuración de tasas maestras

1. Vaya a **Administración de transporte > Configuración > Clasificación > Tasa maestra**.
1. Seleccione **Nuevo**.
1. En el campo **Tasa maestra**, escriba un valor.
1. En el campo **Nombre**, escriba un valor.
1. En el campo **Id. de metadatos de clasificación**, seleccione el botón desplegable para abrir la búsqueda. El identificador de metadatos de clasificación determinará los datos necesarios para la tasa maestra, ya que define los metadatos previstos por el motor de gestión de transporte que usa esta tasa maestra.  
1. Para este ejemplo, seleccione la opción P2P. Esto ya está definido en los datos de demostración.
1. En la lista, seleccione el vínculo de la fila seleccionada.
1. Seleccione **Guardar**.

## <a name="set-up-rate-base"></a>Configuración de la base de tasa

1. Seleccione **Base de tasa**.
    * La base de tasa determina la tasa del transportista, y se puede usar para configurar una estructura de tarifa al estructurar las tasas en los puntos de interrupción definidos en el maestro de interrupción.  
2. Seleccione **Nuevo**.
3. En el campo **Base de tasa**, escriba un valor.
4. En el campo **Nombre**, escriba un valor.
5. En el campo **Maestro de interrupción**, haga clic en el botón desplegable para abrir la búsqueda.
    * Los maestros de interrupción se usan para definir la estructura de precios y sus puntos de interrupción. La estructura de precios usa precios con niveles basados en dimensiones físicas.  
6. Para este ejemplo, use el peso. Esto ya está definido en los datos de demostración.
7. En la lista, seleccione el vínculo de la fila resaltada.
8. Expanda la sección **Detalles**.
9. Seleccione **Nuevo**.
10. En el campo **Código postal de la ubicación de devolución de**, especifique "30301".
11. En el campo **Código postal de la ubicación de devolución a**, especifique "30318".
12. En el campo **País o región de la ubicación de devolución**, escriba "EE. UU.".
13. En el campo **<1.00 Lbs**, escriba "100".
    * Inserte la tasa por libras si el peso total de la carga es inferior a 1 libra.  
14. En el campo **<5.00 Lbs**, escriba "300".
    * Inserte la tasa por libras si el peso total de la carga es inferior a 5 libras.  
15. En el campo **<20.00 Lbs**, escriba "500".
    * Inserte la tasa por libras si el peso total de la carga es inferior a 20 libras.  
16. En el campo **<100.00 Lbs**, escriba "1000".
    * Inserte la tasa por libras si el peso total de la carga es inferior a 100 libras.  
17. En el campo **<1,000.00 Lbs**, escriba "3000".
    * Inserte la tasa por libras si el peso total de la carga es inferior a 1000 libras.  
18. Seleccione **Guardar**.
19. Cierre la página.

## <a name="assign-rate-base"></a>Asignación de la base de tasa

1. Expanda la sección **Asignaciones de base de tasa**.
2. Seleccione **Nuevo**.
    * Puede tener varias asignaciones de base de tasa para cada tasa maestra. Esto permite crear varios puntos de precios distintos para cada transportista, en función de los destinos, los servicios o distintas bases de tasa. En este procedimiento creará solo una asignación de base de tasa.  
3. En el campo **Nombre**, escriba un valor.
4. En el campo **Base de tasa**, haga clic en el botón desplegable para abrir la búsqueda.
5. En la lista, seleccione el vínculo de la fila resaltada.
6. En el campo **Servicio**, seleccione el botón desplegable para abrir la búsqueda.
7. En la lista, busque y seleccione el registro deseado.
8. En la lista, seleccione el vínculo de la fila resaltada.
9. En el campo **Código postal de recogida**, escriba "98052".
    * Especifique desde qué código postal será válida esta asignación de base de tasa.
10. En el campo **País o región de recogida**, escriba "EE. UU.".
11. Seleccione **Guardar**.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]