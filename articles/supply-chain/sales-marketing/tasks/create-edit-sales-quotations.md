--- 
title: Crear y editar presupuestos de ventas
description: "Este procedimiento muestra cómo crear y actualizar un presupuesto de ventas."
author: omulvad
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: SalesQuotationListPage, SalesCreateQuotation, SalesQuotationTable, SalesQuotationTotals, SalesQuotationPriceSimulation, SalesQuotationEditLines, SrsReportViewerForm, smmSetNumSeqIfManual, CustTable, SalesTable
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: omulvad
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: f56b495131836689395a2124d5a834579e1646b7
ms.contentlocale: es-es
ms.lasthandoff: 09/29/2017

---
# <a name="create-and-edit-sales-quotations"></a>Crear y editar presupuestos de ventas

[!include [task guide banner](../../includes/task-guide-banner.md)]

Este procedimiento muestra cómo crear y actualizar un presupuesto de ventas. Puede ejecutar este procedimiento en sus propios datos o en la empresa de demostración USMF.


## <a name="create-a-sales-quotation"></a>Crear un presupuesto de ventas
1. Vaya a Ventas y marketing > Presupuestos de ventas > Todos los presupuestos.
2. Haga clic en Nuevo.
3. En el campo Tipo de cuenta, seleccione "Cliente potencial".
4. En el campo Cliente potencial, especifique o seleccione un valor.
5. Expanda la sección General.
    * Dado que ha elegido crear un presupuesto del área Ventas y marketing, el tipo se establece automáticamente en Presupuesto de ventas. Para crear un presupuesto para un proyecto, debe obtener acceso a él en el módulo de Gestión de proyectos y contabilidad.   
6. Haga clic en Aceptar
    * Los campos y las acciones de las líneas de presupuesto son muy similares a los que se encuentran en las líneas de pedidos de ventas.   Como los pedidos de ventas, los presupuestos se pueden crear para un artículo específico o, cuando no se conoce el número de artículo o no existe en el momento de la creación de presupuestos, los presupuestos se pueden crear para una categoría de ventas.  
7. En el campo Artículo, especifique o seleccione un valor.
8. En el campo Artículo, escriba un valor.
9. Cierre la página.
10. En el campo Cantidad, especifique un número.
    * Si hay acuerdos comerciales válidos para el artículo seleccionado en la línea, los precios y los descuentos aplicables se copiarán automáticamente a la línea de presupuesto. Asegúrese de que el campo Precio unitario contiene un valor y también puede especificar valores de descuento si lo desea.  
11. Haga clic en Guardar.
12. En el panel de acciones, haga clic en Presupuesto de ventas.
13. Haga clic en Totales.
14. Haga clic en Aceptar
15. Haga clic en Línea de presupuesto de venta.
16. Haga clic en Precios.
    * En la página Ejecutar simulación de precios puede experimentar con el ajuste de ingresos o rentabilidad previstos de su presupuesto según el precio unitario que desee, el importe del descuento, el porcentaje del descuento, el importe total, el margen o el coeficiente de contribución.   Cuando esté satisfecho con las cifras de destino, aplique la sugerencia a la línea de presupuesto y sus campos relacionados con precios se actualizarán en consecuencia.  
    * Puede crear tantas simulaciones de precios como desee. Al hacer clic en Nuevo, las condiciones de precios de la línea de presupuesto actual se copian en la página. A continuación puede modificar los valores de cualquiera de los campos relacionados con precios cualquiera con los de destino. Un cambio en uno de los campos accionará el recálculo en todos los demás campos. Para que el sistema calcule el margen de ventas y el coeficiente de contribución, se tiene que conocer el coste unitario del producto. Use la ficha Precios simulados para obtener una vista detallada de los precios originales, los cambios propuestos y su efecto en los totales del presupuesto.   Como regla general, cuando una simulación que establece un nuevo importe se aplica a la línea de presupuesto, el sistema vuelve a realizar el cálculo y especifica un valor nuevo en el campo Precio unitario. Si la simulación se basa en un nuevo margen o un nuevo coeficiente de contribución, solo se actualiza el campo Importe neto y el Precio unitario está en blanco. En ambos casos, se eliminará los descuentos que se encontraban en la línea de presupuesto antes de la simulación.  
17. Cierre la página.
18. En el panel de acciones, haga clic en Presupuesto.
19. Haga clic en Enviar presupuesto.
20. Seleccione Sí en el campo Imprimir presupuesto.
21. Haga clic en Aceptar
    * El informe puede tardar un minuto en generarse. No cierre la página hasta que lo haga.  
22. Cierre la página.

## <a name="update-a-sales-quotation"></a>Actualizar un presupuesto de ventas
1. En el panel de acciones, haga clic en Seguimiento.
2. Haga clic en Convertir en cliente.
3. En el campo Cuenta de cliente, escriba un valor.
4. Haga clic en Comprobar.
    * Asegúrese de que ve un mensaje que indica que el número de cuenta que ha escrito está libre para usarlo.  
5. Haga clic en Aceptar
    * El sistema ha creado una nueva cuenta de cliente para el cliente potencial en el presupuesto.  
6. Cierre la página.
7. En el panel de acciones, haga clic en Seguimiento.
8. Haga clic en Confirmar.
9. En el campo Motivo, especifique o seleccione un valor.
10. Haga clic en Aceptar
11. En el panel de acciones, haga clic en General.
12. Haga clic en Pedidos de ventas.
13. Cierre la página.


