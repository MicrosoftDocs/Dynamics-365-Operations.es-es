---
title: Creación masiva de presupuestos de ventas
description: Este procedimiento muestra cómo crear de manera eficaz presupuestos que ofrecen un conjunto de productos o servicios que se deben enviar a varios clientes.
author: omulvad
manager: tfehr
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SalesQuotationTemplateGroup, SalesQuotationListPage, SalesCreateQuotation, SalesQuotationTable, SysQueryForm, SalesQuickQuote
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 227ff0dd03f8917f4551ce08067ef26c6204b059
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/13/2020
ms.locfileid: "4436653"
---
# <a name="mass-create-sales-quotations"></a>Creación masiva de presupuestos de ventas

[!include [banner](../../includes/banner.md)]

Este procedimiento muestra cómo crear de manera eficaz presupuestos que ofrecen un conjunto de productos o servicios que se deben enviar a varios clientes. Esta creación de presupuesto masiva se basa en las plantillas de presupuesto. Puede ejecutar este procedimiento en sus propios datos o en la empresa de demostración USMF.


## <a name="create-a-quotation-template"></a>Crear una plantilla de presupuesto
1. Vaya a Ventas y marketing > Configuración > Presupuestos > Grupos de plantillas.
2. Haga clic en Nuevo.
3. En el campo Id. de grupo, escriba el id. que desee.
4. En el campo Descripción, escriba un valor.
5. Haga clic en Guardar.
6. Cierre la página.
7. Vaya a Ventas y marketing > Presupuestos de ventas > Todos los presupuestos.
8. Haga clic en Nuevo.
9. En el campo Tipo de cuenta, seleccione 'Cliente'.
10. En el campo Cuenta de cliente, especifique o seleccione un valor.
11. Haga clic en Aceptar
    * Para que un presupuesto se convierta en una plantilla debe realizar pasos de configuración en la cabecera de presupuesto. Esto se debe realizar antes de agregar líneas al presupuesto.   
12. En el panel de acciones, haga clic en Opciones.
13. Haga clic en Cambiar vista.
14. Haga clic en Visualización de encabezado.
15. Expanda la sección Configuración.
16. En el campo Id. de grupo, especifique o seleccione un valor.
17. En el campo Nombre de plantilla, escriba un valor.
18. Seleccione Sí en el campo Activo.
    * Solo las plantillas activas pueden usarse si se aplica una plantilla a un nuevo presupuesto de ventas.  
19. En el panel de acciones, haga clic en Opciones.
20. Haga clic en Cambiar vista.
21. Haga clic en Vista de líneas.
22. En el campo Artículo, especifique o seleccione un valor.
23. En el campo Artículo, escriba un valor.
24. Cierre la página.
25. En el campo Porcentaje de descuento, escriba un número.
26. Haga clic en Agregar línea.
27. En el campo Artículo, especifique o seleccione un valor.
28. En el campo Artículo, escriba un valor.
29. Cierre la página.
30. En el campo Precio unitario, especifique un nuevo precio o cambie el actual.
31. Haga clic en Agregar línea.
32. En el campo Artículo, especifique o seleccione un valor.
33. En el campo Artículo, escriba un valor.
34. Cierre la página.
35. En el campo Cantidad, especifique un número.
36. En el campo Descuento, escriba un número.
37. Haga clic en Guardar.

## <a name="apply-the-template-to-create-a-single-quotation"></a>Aplicar la plantilla para crear un único presupuesto
1. Vaya a Ventas y marketing > Presupuestos de ventas > Todos los presupuestos.
    * Tenga en cuenta que el presupuesto que acaba de crear está marcado como plantilla.  
2. Haga clic en Nuevo.
3. En el campo Tipo de cuenta, seleccione 'Cliente'.
4. En el campo Cuenta de cliente, especifique o seleccione un valor.
5. Expanda la sección Plantilla.
6. En el campo Id. de grupo, especifique o seleccione un valor.
7. En el campo Nombre de plantilla, especifique o seleccione un valor.
8. En el campo Método de cálculo, seleccione “Basado en valores de plantilla”.
9. Haga clic en Aceptar
    * Se ha creado el nuevo presupuesto, en función de los datos y las condiciones de la plantilla.  
10. Cierre la página.
11. Cierre la página.

## <a name="apply-the-template-to-mass-create-quotations"></a>Aplicar la plantilla para crear presupuestos de forma masiva
1. Vaya a Ventas y marketing > Presupuestos de ventas > Actualización de presupuesto > Creación masiva de presupuestos.
2. En el campo Tipo de cuenta, seleccione 'Cliente'.
3. En el campo Id. de grupo, especifique o seleccione un valor.
4. En el campo Nombre de plantilla, especifique o seleccione un valor.
5. En el campo Método de cálculo, seleccione “Basado en valores de plantilla”.
6. Expanda la sección Registros que incluir.
7. Haga clic en Filtro.
8. En el campo Criterios, establezca el filtro para cubrir un intervalo de clientes que desea incluir en esta creación de presupuesto masiva. Utilice el siguiente formato "Customer1..CustomerN.
    * Por ejemplo, podría establecer el filtro en: US-001..US-004  
9. Haga clic en Aceptar
10. Haga clic en Aceptar
11. Vaya a Ventas y marketing > Presupuestos de ventas > Todos los presupuestos.
    * Compruebe que los presupuestos se han creado para todos los clientes especificados en la rutina de actualización masiva, basándose en la plantilla seleccionada.  

