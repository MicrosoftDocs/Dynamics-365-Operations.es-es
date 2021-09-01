---
title: Informes de costos de aterrizaje
description: Este tema describe cómo encontrar y utilizar los distintos tipos de informes que están disponibles para el módulo de costos de entrega.
author: sherry-zheng
ms.date: 02/01/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: SysOperationTemplateForm
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: chuzheng
ms.search.validFrom: 2021-02-21
ms.dyn365.ops.version: Release 10.0.17
ms.openlocfilehash: ea60826ddfd9553ba16c22f077d65732bf08e18fa079c6311431d35dd9aaa99f
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2021
ms.locfileid: "6765499"
---
# <a name="landed-cost-reports"></a>Informes de costos de aterrizaje

[!include [banner](../../includes/banner.md)]

## <a name="outstanding-invoices"></a>Facturas pendientes

El informe de facturas pendientes contiene una lista de todas las facturas pendientes de los distintos niveles de costos asociados con cada viaje. Se utiliza para conciliar el viaje y los costos del viaje junto con la lista de transacciones del libro mayor de forma regular. Una vez que se han facturado los gastos generales, se eliminan del informe.

Para generar un informe de facturas destacadas, siga estos pasos.

1. Ir **Coste de aterrizaje \> Informes \> Seguimiento \> Facturas pendientes**.
1. En el cuadro de diálogo **Facturas pendientes**, en el campo **Como en la fecha**, especifique una fecha. Cualquier factura que estuviera pendiente en o antes de esa fecha se incluirá en la salida.
1. En **Mostrar**, seleccione una de las siguientes opciones:

    - **Costo no facturado** - Incluya los costos de los envíos facturados que tienen un valor de costo estimado pero no un costo real.
    - **Stock no facturado** - Incluya los costos que se han facturado, pero para los que aún no se ha recibido la orden de compra.
    - **Todo no facturado** - Incluir los resultados de la opción **Costo no facturado** y la opción **Stock no facturado**.

1. Establezca la opción **Incluir nuevos costos** en *Sí* para incluir los costos que aún no tienen un costo real y para los que no se ha recibido el inventario. Si lo configura en *No*, el informe incluirá solo los costos que se hayan facturado.
1. En la sección **Vista**, habilite cada tipo de detalle que desee incluir en el informe.
1. Como lo hace con otros tipos de informes en Microsoft Dynamics 365 Supply Chain Management, utilice la ficha desplegable **Destino** para seleccionar el formato de salida del informe.
1. Como lo hace con otros tipos de informes en Supply Chain Management, utilice la ficha desplegable **Registros para incluir** para limitar aún más los registros que se incluirán en el informe.
1. Haga clic en **Aceptar** para generar el informe.

## <a name="activityprovider-analysis-reports"></a>Informes de análisis de actividad/proveedor

Los informes de análisis de actividad / proveedor le permiten revisar la precisión de sus estimaciones de tiempo para cada proveedor.

Para generar un informe de análisis de actividad/proveedor, siga estos pasos.

1. Según el tipo de informe que desee crear, siga uno de estos pasos:

    - Ir **Coste de aterrizaje \> Informes \> Análisis de actividad/proveedor por actividad**. En este caso, las estimaciones de tiempo se agruparán por actividad.
    - Ir **Coste de aterrizaje \> Informes \> Análisis de actividad/proveedor por proveedor**. En este caso, las estimaciones de tiempo se agruparán por proveedor.

    Aparece el cuadro de diálogo **Análisis de actividad/proveedor por actividad** o el cuadro de diálogo **Análisis de actividad / proveedor por proveedor**. Ambos cuadros de diálogo ofrecen las mismas opciones.

1. Como lo hace con otros tipos de informes en Supply Chain Management, utilice la ficha desplegable **Destino** para seleccionar el formato de salida del informe.
1. Como lo hace con otros tipos de informes en Supply Chain Management, utilice la ficha desplegable **Registros para incluir** para limitar aún más los registros que se incluirán en el informe.
1. Haga clic en **Aceptar** para generar el informe.

## <a name="voyage-costing-reports"></a>Informes de costeo de viajes

Los informes de costeo del viaje muestran el costo de los artículos y los costos de importación por folio, contenedor de envío o viaje, según las opciones que seleccione al generar el informe. Cada informe de costeo de viaje le permite ver el costo estimado de un viaje en comparación con el costo real, y se puede desglosar por varios factores de identificación.

Para generar un informe de gestión de costos de viaje, siga estos pasos.

1. Según el tipo de informe que desee crear, siga uno de estos pasos:

    - Ir **Coste de aterrizaje \> Informes \> Gestión de costes \> Gestión de costes de viaje por costo individual**. En este caso, la opción de costo individual mostrará los costos de importación por área de costo por código de tipo de costo.
    - Ir **Coste de aterrizaje \> Informes \> Gestión de costes \> Gestión de costes de viaje por categoría de informe**. En este caso, el costo de importación se desglosará en las distintas categorías de informes. Los tipos de costos se agrupan por categorías de informes.

    Aparece el cuadro de diálogo **Gestión de costes de viaje por costo individual** o el cuadro de diálogo **Gestión de costes por categoría de informes**. Estos cuadros de diálogo son similares. Cualquier diferencia se indica en el resto de este procedimiento.

1. Si abrió **Costeo de viajes por categoría de informes**, en el campo **Costo**, seleccione uno de los siguientes valores:

    - **Valor de coste** - El valor se calcula utilizando los costos de automóviles o se crea manualmente en el área de costos.
    - **Estimado** - Una vez recibida la mercancía, se establece el coste estimado.
    - **Real** - Después de que se haya facturado el pedido, el costo real se establece en el costo de la factura.
    - **Mejor** - El sistema utilizará cualquiera de las tres opciones anteriores que sea más precisa. (Le recomendamos que seleccione esta opción).

1. Establezca la opción **Por artículo** en *Sí* para mostrar el costo de cada artículo. Defina *No* para mostrar los costos por viaje.
1. En la sección **Vista**, seleccione las categorías para desglosar el costo.
1. En la sección **Dimensiones**, seleccione las dimensiones que desee incluir en el informe.
1. Como lo hace con otros tipos de informes en Supply Chain Management, utilice la ficha desplegable **Destino** para seleccionar el formato de salida del informe.
1. Como lo hace con otros tipos de informes en Supply Chain Management, utilice la ficha desplegable **Registros para incluir** para limitar aún más los registros que se incluirán en el informe.
1. Haga clic en **Aceptar** para generar el informe.

## <a name="shipping-container-receipts-list"></a>Lista de recepciones del contenedor de envío

La lista de recibos del contenedor de envío contiene todas las cantidades no recibidas que vencen en la fecha prevista o antes. El personal del almacén puede utilizar este informe para identificar los productos esperados en un contenedor de envío. También se puede utilizar para validar manualmente las mercancías a medida que se reciben en un contenedor de envío.

Para generar una lista de recibos de contenedores de envío, siga estos pasos.

1. Ir **Coste de aterrizaje \> Informes \> Seguimiento \> Lista de recibos de contenedores de envío**.
1. En **Lista de recibos de contenedores de envío**, en el campo **Fecha esperada**, especifique una fecha. Cualquier cantidad no recibida en o antes de esa fecha se incluirá en la salida.
1. En la sección **Dimensiones**, seleccione las dimensiones que desee incluir en el informe.
1. Como lo hace con otros tipos de informes en Supply Chain Management, utilice la ficha desplegable **Destino** para seleccionar el formato de salida del informe.
1. Como lo hace con otros tipos de informes en Supply Chain Management, utilice la ficha desplegable **Registros para incluir** para limitar aún más los registros que se incluirán en el informe.
1. Haga clic en **Aceptar** para generar el informe.

## <a name="expected-delivery-report"></a>Informe de entrega prevista

El informe de entrega prevista contiene información básica sobre el viaje, el contenedor de envío, el folio, los artículos y la fecha prevista de entrega.

Para generar un informe de entregas esperadas, siga estos pasos.

1. Ir **Coste de aterrizaje \> Informes \> Seguimiento \> Entrega esperada**.
1. En el cuadro de diálogo **Entrega esperada**, en el campo **Fecha esperada**, seleccione la fecha en la que se espera la entrega de la mercancía al almacén de destino final. Cualquier línea de viaje que tenga una fecha prevista en o antes de esa fecha, y que aún no se haya recibido, se incluirá en la salida.
1. Opcional: en **Cuenta de vendedor**, seleccione una cuenta de proveedor para incluir solo las entregas de un proveedor específico.
1. En la sección **Dimensiones**, seleccione las dimensiones que desee incluir en el informe.
1. Como lo hace con otros tipos de informes en Supply Chain Management, utilice la ficha desplegable **Destino** para seleccionar el formato de salida del informe.
1. Como lo hace con otros tipos de informes en Supply Chain Management, utilice la ficha desplegable **Registros para incluir** para limitar aún más los registros que se incluirán en el informe.
1. Haga clic en **Aceptar** para generar el informe.
