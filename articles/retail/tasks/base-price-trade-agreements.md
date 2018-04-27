--- 
title: Precio base y acuerdos comerciales
description: "Este procedimiento le muestra la creación de acuerdos comerciales de precios de venta específicos de canal."
author: josaw1
manager: AnnBe
ms.date: 11/10/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-365-retail
ms.technology: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Operations, Retail
ms.search.region: Global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: ea07d8e91c94d9fdad4c2d05533981e254420188
ms.openlocfilehash: 81c70921718e41719470c7428c05a9f7ae77354a
ms.contentlocale: es-es
ms.lasthandoff: 02/07/2018

---
# <a name="base-price-and-trade-agreements"></a>Precio base y acuerdos comerciales

[!INCLUDE [task guide banner](../includes/task-guide-banner.md)]

Este procedimiento le muestra la creación de acuerdos comerciales de precios de venta específicos de canal. Este procedimiento usa la empresa de datos de demostración USRT.

1. Vaya a Venta minorista y comercio > Precios y descuentos > Grupos de precios > Todos los grupos de precios.
    * Los grupos de precios son la manera en que los acuerdos comerciales se asignan a los canales específicos. El uso de grupos de precios para asignar acuerdos comerciales a un canal permite precios específicos de canal.  
2. Haga clic en Nuevo.
3. En el campo Grupos de precios, escriba un valor.
4. En el campo Nombre, escriba un valor.
5. Haga clic en Guardar.
6. Cierre la página.
7. Vaya a Venta minorista y comercio > Canales > Tiendas > Todas las tiendas minoristas.
8. En la lista, seleccione "Nueva York"
9. En el panel de acciones, haga clic en Tienda.
10. Haga clic en Grupos de precios.
11. Haga clic en Nuevo.
12. En el campo Grupos de precios, haga clic en el botón desplegable para abrir la búsqueda.
13. En la lista, busque y seleccione el registro deseado.
14. Haga clic en Guardar.
15. Cierre la página.
16. Cierre la página.
17. Vaya a Venta minorista y comercio > Productos y categorías > Productos liberados por categoría.
18. En la lista, haga clic en el vínculo de la fila seleccionada.
19. Haga clic en Editar.
20. Alterne la expansión de la sección Vender.
21. En el campo Precio, escriba un número.
    * Este precio se usa si no se encuentra ningún acuerdo comercial aplicable.  
22. Haga clic en Guardar.
23. En el panel de acciones, haga clic en Vender.
24. Haga clic en Crear acuerdos comerciales.
25. Haga clic en Nuevo.
26. En el campo Nombre, haga clic en el botón desplegable para abrir la búsqueda.
27. En la lista, seleccione "Venta minorista".
    * En los datos de demostración, el nombre de diario "Venta minorista" tiene la relación predeterminado de "Precio (ventas)". Esto significa que todas las nuevas líneas creadas se asignarán de forma predeterminada a los acuerdos comerciales de precio de ventas.  
28. Haga clic en Líneas.
29. En el campo Código de cuenta, seleccione "Grupo".
30. En el campo Selección de cuentas, haga clic en el botón desplegable para abrir la búsqueda.
31. En la lista, busque y seleccione el registro deseado.
    * Esto completará Vincular el grupo de precios a un cana al Acuerdo comercial.  
32. En el campo Relación de artículos, escriba un valor.
33. En el campo Importe en divisa, escriba un número.
34. Active o desactive la casilla Buscar siguiente.
    * Cuando Buscar siguiente se establezca en "Sí", el motor de precios continuará buscando acuerdos comerciales aplicables con un precio de venta menor. Cuando Buscar siguiente se establezca en "No", el motor de precios detendrá la búsqueda y usará el acuerdo comercial.  
35. Haga clic en Registrar.
36. Haga clic en Aceptar
37. Cierre la página.
38. En el panel de acciones, haga clic en Vender.
39. Haga clic en Precio de ventas.


