--- 
title: "Configuración de los costes estándar para el trabajo y los gastos"
description: "Este procedimiento muestra cómo configurar los costes estándar del trabajo y los gastos de un proyecto."
author: KimANelson
manager: AnnBe
ms.date: 02/13/2017
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Service industries
ms.author: knelson
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 55b22d246d6bfa9e8159fb844da95f61fcf07c62
ms.openlocfilehash: 64719b39cb7c0140f1851a87ff49747d2286804c
ms.contentlocale: es-es
ms.lasthandoff: 07/28/2017

---
# <a name="configure-standard-costs-for-labor-and-expenses"></a>Configuración de los costes estándar para el trabajo y los gastos

[!include[task guide banner](../../includes/task-guide-banner.md)]

Este procedimiento muestra cómo configurar los costes estándar del trabajo y los gastos de un proyecto. Esta tarea usa el conjunto de datos USSI.

1. Vaya a Administración de proyectos y contabilidad > Configuración > Precios > Precio de venta (hora).
2. Haga clic en Nuevo.
3. En el campo Fecha de vigencia, especifique una fecha.
4. En el campo Precio de coste, escriba un número.
    * Puede configurar un precio de coste estándar para la categoría del proyecto o puede configurar un precio de coste por número de trabajador, número de proyecto, categoría, fecha o cualquier combinación de los anteriores. El precio de coste que se aplica es el precio de coste con el mayor nivel de detalle.  
5. Haga clic en Guardar.
6. Cierre la página.
7. Vaya a Administración de proyectos y contabilidad > Configuración > Precios > Precio de venta (hora).
8. Haga clic en Nuevo.
9. En el campo Fecha de vigencia, especifique una fecha.
10. En el campo Válido para, seleccione una opción.
11. Escriba un número en el campo Precio.
    * Puede configurar un precio de ventas estándar para las transacciones por horas o para una categoría de proyecto. También puede configurar los precios de ventas por número de trabajador, número de proyecto, categoría, fecha de transacción o cualquier combinación de los anteriores. El precio de venta real, que se aplica cuando un trabajador escribe una transacción en el diario de Horas, es el precio de venta con el mayor nivel de detalle. Por ejemplo, si están establecidos un precio de ventas general y un precio de ventas específico de cada trabajador, se utiliza el precio de ventas específico del trabajador.  
12. Haga clic en Guardar.
13. Cierre la página.
14. Vaya a Administración de proyectos y contabilidad > Configuración > Precios > Precio de coste (gasto).
15. Haga clic en Nuevo.
16. En el campo Fecha de vigencia, especifique una fecha.
17. En el campo Precio de coste, escriba un número.
    * Se pueden rellenar distintos campos, pero éste es el mínimo necesario para guardar el registro.  
18. Haga clic en Guardar.
19. Cierre la página.
20. Vaya a Administración de proyectos y contabilidad > Configuración > Precios > Precio de venta (gasto).
21. Haga clic en Nuevo.
22. En el campo Fecha de vigencia, especifique una fecha.
23. En el campo Válido para, seleccione una opción.
24. Escriba un número en el campo Precio.
    * El precio de venta real, que se aplica cuando un trabajador especifica transacciones de gasto en un diario de gastos, es el precio de ventas con el nivel de detalle más alto. Por ejemplo, si están establecidos un precio general y un precio de ventas específico de cada trabajador, se utiliza el precio de ventas específico del trabajador.  
25. Haga clic en Guardar.


