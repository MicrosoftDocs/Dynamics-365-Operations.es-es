---
title: Configuración de los costes estándar para el trabajo y los gastos
description: Este tema explica cómo configurar los costes estándar del trabajo y los gastos de un proyecto.
author: KimANelson
manager: AnnBe
ms.date: 08/02/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ProjCostPriceHour, ProjSalesPriceHour, ProjCostPriceExpense, ProjSalesPriceCost
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Service industries
ms.author: knelson
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 51bbe52d70bae11cb0c95e9544f951f0fcc605f5
ms.sourcegitcommit: 57e1dafa186fec77ddd8ba9425d238e36e0f0998
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/18/2020
ms.locfileid: "3140102"
---
# <a name="configure-standard-costs-for-labor-and-expenses"></a>Configuración de los costes estándar para el trabajo y los gastos

[!include [banner](../../includes/banner.md)]

Este tema explica cómo configurar los costes estándar del trabajo y los gastos de un proyecto. Esta tarea usa el conjunto de datos USSI.

1. En el panel de exploración, vaya a **Módulos > Administración de proyectos y contabilidad > Configuración > Precios > Precio de coste (hora)**.
2. Seleccione **Nuevo**.
3. En el campo **Fecha de vigencia**, especifique una fecha.
4. En el campo **Precio de coste**, escriba un número. Puede configurar un precio de coste estándar para la categoría del proyecto o puede configurar un precio de coste por número de trabajador, número de proyecto, categoría, fecha o cualquier combinación de los anteriores. El precio de coste que se aplica es el precio de coste con el mayor nivel de detalle.  
5. Seleccione **Guardar**.
6. En el panel de exploración, vaya a **Módulos > Administración de proyectos y contabilidad > Configuración > Precios > Precio de venta (hora)**.
7. Seleccione **Nuevo**.
8. En el campo **Fecha de vigencia**, especifique una fecha.
9. En el campo **Válido para**, seleccione una opción.
10. Escriba un número en el campo **Precio**. Puede configurar un precio de ventas estándar para las transacciones por horas o para una categoría de proyecto. También puede configurar los precios de ventas por número de trabajador, número de proyecto, categoría, fecha de transacción o cualquier combinación de los anteriores. El precio de venta real, que se aplica cuando un trabajador escribe una transacción en el diario de Horas, es el precio de venta con el mayor nivel de detalle. Por ejemplo, si están establecidos un precio de ventas general y un precio de ventas específico de cada trabajador, se utiliza el precio de ventas específico del trabajador.  
11. Seleccione **Guardar**.
12. Cierre la página.
13. En el panel de exploración, vaya a **Módulos > Administración de proyectos y contabilidad > Configuración > Precios > Precio de coste (gasto)**.
14. Seleccione **Nuevo**.
15. En el campo **Fecha de vigencia**, especifique una fecha.
16. En el campo **Precio de coste**, escriba un número. Se pueden rellenar distintos campos, pero éste es el mínimo necesario para guardar el registro.  
17. Seleccione **Guardar**.
18. En el panel de exploración, vaya a **Módulos > Administración de proyectos y contabilidad > Configuración > Precios > Precio de ventas (gasto)**.
19. Seleccione **Nuevo**.
20. En el campo **Fecha de vigencia**, especifique una fecha.
21. En el campo **Válido para**, seleccione una opción.
22. Escriba un número en el campo **Precio**. El precio de venta real, que se aplica cuando un trabajador especifica transacciones de gasto en un diario de gastos, es el precio de ventas con el nivel de detalle más alto. Por ejemplo, si están establecidos un precio general y un precio de ventas específico de cada trabajador, se utiliza el precio de ventas específico del trabajador.  
23. Seleccione **Guardar**.

