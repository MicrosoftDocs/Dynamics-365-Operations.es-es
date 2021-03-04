---
title: Crear y editar presupuestos de ventas
description: Este procedimiento muestra cómo crear y actualizar un presupuesto de ventas.
author: omulvad
manager: tfehr
ms.date: 06/26/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SalesQuotationListPage, SalesCreateQuotation, SalesQuotationTable, SalesQuotationTotals, SalesQuotationPriceSimulation, SalesQuotationEditLines, SrsReportViewerForm, smmSetNumSeqIfManual, CustTable, SalesTable, CustQuotationConfirmationJournal, CustQuotationJournal, CustSalesLines, SalesQuotationCopying, SalesQuotationDeleteQuotations, SalesQuotationListPagePreviewPane, SalesQuotationTypeGroup
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 73c15b41a4b0979ec79c8dbd8d88627bffcf6ed3
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/13/2020
ms.locfileid: "4436659"
---
# <a name="create-and-edit-sales-quotations"></a>Crear y editar presupuestos de ventas

[!include [banner](../../includes/banner.md)]

Este procedimiento muestra cómo crear y actualizar un presupuesto de ventas. Puede ejecutar este procedimiento en sus propios datos o en la empresa de demostración USMF.


## <a name="create-a-sales-quotation"></a>Crear un presupuesto de ventas
1. Vaya a **Panel de navegación > Módulos > Ventas y marketing > Presupuestos de ventas > Todos los presupuestos**.
2. Haga clic en **Nuevo**.
3. En el campo **Tipo de cuenta**, seleccione "Cliente potencial".
4. En el campo **Cliente potencial**, especifique o seleccione un valor.
5. Expanda la sección **General**. Dado que ha elegido crear un presupuesto del área Ventas y marketing, el tipo se establece automáticamente en "Presupuesto de ventas". Para crear un presupuesto para un proyecto, debe obtener acceso a él en el módulo de **Gestión de proyectos y contabilidad**.
6. Haga clic en **Aceptar**. Los campos y las acciones de las líneas de presupuesto son muy similares a los que se encuentran en las líneas de pedidos de ventas.   Como los pedidos de ventas, los presupuestos se pueden crear para un artículo específico o, cuando no se conoce el número de artículo o no existe en el momento de la creación de presupuestos, los presupuestos se pueden crear para una categoría de ventas.     
7. En el campo **Artículo**, especifique o seleccione un valor.
8. En el campo **Sitio**, escriba un valor.
9. En el campo **Cantidad**, especifique un número. Si hay acuerdos comerciales válidos para el artículo seleccionado en la línea, los precios y los descuentos aplicables se copiarán automáticamente a la línea de presupuesto. Asegúrese de que el campo Precio unitario contiene un valor y también puede especificar valores de descuento si lo desea. 
10. Haga clic en **Guardar**.
11. En el **Panel Acciones**, haga clic en **Presupuesto de ventas**.
12. Haga clic en **Totales**.
13. Haga clic en **Aceptar**.
14. Seleccione la línea del presupuesto de ventas.
15. En el **Panel Acciones**, haga clic en **Presupuesto**.
16. Haga clic en **simulación de precios**.
    - En la página **Ejecutar simulación de precios** puede experimentar con el ajuste de ingresos o rentabilidad previstos de su presupuesto según el precio unitario que desee, el importe del descuento, el porcentaje del descuento, el importe total, el margen o el coeficiente de contribución. Cuando esté satisfecho con las cifras de destino, aplique la sugerencia a la línea de presupuesto y sus campos relacionados con precios se actualizarán en consecuencia.  
    - Puede crear tantas simulaciones de precios como desee. Al hacer clic en **Nuevo**, las condiciones de precios de la línea de presupuesto actual se copian en la página. A continuación puede modificar los valores de cualquiera de los campos relacionados con precios cualquiera con los de destino. Un cambio en uno de los campos accionará el recálculo en todos los demás campos. Para que el sistema calcule el margen de ventas y el coeficiente de contribución, se tiene que conocer el coste unitario del producto. Use la ficha Precios simulados para obtener una vista detallada de los precios originales, los cambios propuestos y su efecto en los totales del presupuesto. Como regla general, cuando una simulación que establece un nuevo importe se aplica a la línea de presupuesto, el sistema vuelve a realizar el cálculo y especifica un valor nuevo en el campo Precio unitario. Si la simulación se basa en un nuevo margen o un nuevo coeficiente de contribución, solo se actualiza el campo Importe neto y el Precio unitario está en blanco. En ambos casos, se eliminará los descuentos que se encontraban en la línea de presupuesto antes de la simulación.
17. En el **Panel Acciones**, haga clic en **Presupuesto**.
18. Haga clic en **Enviar presupuesto**.
19. Seleccione "Sí" en el campo **Imprimir presupuesto**.
20. Haga clic en **Aceptar**. El informe puede tardar un minuto en generarse. No cierre la página hasta que lo haga.

## <a name="update-a-sales-quotation"></a>Actualizar un presupuesto de ventas
1. Vaya a **Panel de navegación > Módulos > Ventas y marketing > Presupuestos de ventas > Todos los presupuestos**.
2. En el **Panel Acciones**, haga clic en **Seguimiento**.
3. Haga clic en **Convertir en cliente**.
4. En el campo **Cuenta de cliente**, escriba un valor.
5. Haga clic en **Comprobar**. Asegúrese de que ve un mensaje que indica que el número de cuenta que ha escrito está libre para usarlo.  
6. Haga clic en **Aceptar**. El sistema ha creado una nueva cuenta de cliente para el cliente potencial en el presupuesto.  
7. Cierre la página.
8. En el **Panel Acciones**, haga clic en **Seguimiento**.
9. Haga clic en **Confirmar**.
10. En el campo **Motivo**, especifique o seleccione un valor.
11. Haga clic en **Aceptar**.
12. En el **Panel Acciones**, haga clic en **General**.
13. Haga clic en **Pedidos de ventas**.
14. Cierre la página.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]