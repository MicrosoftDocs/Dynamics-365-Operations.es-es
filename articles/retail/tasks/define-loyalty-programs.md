--- 
title: "Definir programas de fidelización"
description: "Este procedimiento muestra cómo configurar un programa de fidelización con dos niveles de fidelización."
author: jashanno
manager: AnnBe
ms.date: 11/14/2017
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-retail
ms.technology: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Retail
ms.author: jashanno
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 8bbdbf882f6f73d03be0a036cb975109396e4a0d
ms.openlocfilehash: 4bc90da445765ab662fe920a3230681959469a90
ms.contentlocale: es-es
ms.lasthandoff: 11/14/2017

---
# <a name="define-loyalty-programs"></a>Definir programas de fidelización

[!include[task guide banner](../includes/task-guide-banner.md)]

Este procedimiento muestra cómo configurar un programa de fidelización con dos niveles de fidelización. Este procedimiento usa la empresa de datos de demostración USRT.

1. Vaya a Venta al por menor y Comercio > .. > Programas de fidelización.
2. Haga clic en Nuevo.
3. En el campo Nombre, escriba un valor.
4. En el campo Descripción, escriba un valor.
5. Haga clic en Agregar línea.
6. En el campo Nivel, escriba un número.
7. En el campo Nivel, escriba un nombre para el nivel de fidelización.
8. En el campo Descripción, escriba un valor.
9. En el campo Intervalo de fechas, haga clic en el botón desplegable para abrir la búsqueda.
    * Este intervalo de fechas debe ampliarse al futuro. Por ejemplo, si el intervalo de fechas que se selecciona para el nivel oro es un período de un año, los clientes que reúnan los requisitos del nivel oro pueden recibir las recompensas asignadas al nivel oro durante un año. Si el cliente vuelve a reunir los criterios del nivel oro mientras se encuentran en ese nivel, la fecha en la que expira el nivel se amplía otro año, desde la fecha en que vuelve a reunir los criterios.  
10. En la lista, haga clic en el vínculo de la fila seleccionada.
11. Haga clic en Agregar línea.
12. En el campo Nivel, escriba un número.
13. En el campo Nivel, escriba un nombre para el nivel de fidelización.
14. En el campo Descripción, escriba un valor.
15. En el campo Intervalo de fechas, haga clic en el botón desplegable para abrir la búsqueda.
16. En la lista, haga clic en el vínculo de la fila seleccionada.
17. Haga clic en Guardar.
18. En la lista, busque y seleccione el registro deseado.
    * Las reglas de nivel definen el número mínimo de un punto de recompensa que se necesita obtener durante un período de tiempo para poder participar en el nivel.  
19. Expanda la sección Reglas de nivel.
20. Haga clic en Nuevo.
    * Puede tener más de una regla de nivel por nivel. Por ejemplo, podría tener tres criterios diferentes para obtener un nivel; gastar 500 USD en un mes, gastar 1000 USD durante un año y tener 20 transacciones en un año. Para ello, necesitaría crear tres reglas de nivel.  
21. En el campo Punto de recompensa, haga clic en el botón desplegable para abrir la búsqueda.
    * Esto debe ser un punto de recompensa de fidelización no canjeable.  
22. En la lista, haga clic en el vínculo de la fila seleccionada.
23. Especifique un número en el campo Mínimo de puntos emitidos.
    * Para el nivel inferior, si todos los clientes pueden reunir los criterios simplemente con la participación en el programa, especifique "0".  
24. En el campo Intervalo de fecha de evaluación, haga clic en el botón desplegable para abrir la búsqueda.
    * Este intervalo de fechas debe ampliarse al pasado. Solo los puntos obtenidos durante este intervalo de fechas se contarán para lograr el valor mínimo de puntos emitidos.  
25. En la lista, haga clic en el vínculo de la fila seleccionada.
26. Haga clic en Guardar.
27. En la lista, busque y seleccione el registro deseado.
28. Haga clic en Nuevo.
29. En el campo Punto de recompensa, haga clic en el botón desplegable para abrir la búsqueda.
30. En la lista, haga clic en el vínculo de la fila seleccionada.
31. Especifique un número en el campo Mínimo de puntos emitidos.
32. En el campo Intervalo de fecha de evaluación, haga clic en el botón desplegable para abrir la búsqueda.
    * Este intervalo de fechas debe ampliarse al pasado.  
33. En la lista, haga clic en el vínculo de la fila seleccionada.
34. Haga clic en Guardar.
35. Haga clic en Grupos de precios.
    * Si desea dar descuentos de fidelización a los clientes, deberá asignar uno o más grupos de precios al programa de fidelización y asignar grupos de precios a los descuentos. Es una práctica recomendada no mezclar grupos de precios en diferentes tipos de entidades de descuentos.  Por ejemplo, no use el mismo grupo de precios para un descuento de fidelización y un descuento de canal.  
36. En el campo Grupo de precios, haga clic en el botón desplegable para abrir la búsqueda.
    * El vínculo Grupos de precios de la parte superior de la página es para el programa de fidelización. El vínculo Grupos de precios de la ficha desplegable Niveles de programa es solo para un nivel de fidelización específico.  
37. En la lista, haga clic en el vínculo de la fila seleccionada.
38. Haga clic en Guardar.
39. Cierre la página.
40. Haga clic en Guardar.


