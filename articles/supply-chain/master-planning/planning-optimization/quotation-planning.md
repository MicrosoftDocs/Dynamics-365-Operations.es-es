---
title: Planes basados en presupuestos y solicitudes de presupuesto
description: Este artículo describe cómo configurar la planificación maestra para considerar cotizaciones y solicitudes de cotización (RFQ) cuando genera pedidos planificados.
author: t-benebo
ms.date: 09/20/2022
ms.topic: article
ms.search.form: SalesQuotationListPage, ReqPlanSched, SalesQuotationTable, smmOpportunityTable
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: benebotg
ms.search.validFrom: 2022-09-20
ms.dyn365.ops.version: 10.0.30
ms.openlocfilehash: eaeb3c26a562c1daebe8296b26077ee5a3223e4d
ms.sourcegitcommit: 3e04f7e4bc0c29c936dc177d5fa11761a58e9a02
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2022
ms.locfileid: "9690105"
---
# <a name="plan-based-on-quotations-and-rfqs"></a>Plan basado en presupuestos y solicitudes de presupuesto

[!include [banner](../../includes/banner.md)]

Las cotizaciones y las solicitudes de cotizaciones (RFQ) representan pedidos futuros posibles o incluso probables. Por lo tanto, tiene sentido considerarlos durante la planificación maestra, de modo que se pueda planificar un suministro adicional en función de las RFQ existentes y la probabilidad de que cada cotización se convierta en un pedido real. Este artículo describe cómo configurar la planificación maestra para considerar cotizaciones y RFQ cuando genera pedidos planificados.

## <a name="set-up-master-planning-to-consider-sales-quotations-andor-rfqs"></a>Configure la planificación maestra para considerar cotizaciones de ventas y/o RFQ

Use el siguiente procedimiento para configurar la planificación maestra para considerar cotizaciones de ventas y/o RFQ.

1. Vaya a **Planificación maestra \> Configurar \> Planes \> Planes maestros**.
1. Seleccione un plan existente en el panel de lista o seleccione **Nuevo** en el Panel de acciones para crear uno nuevo.
1. En la ficha rápida **General**, establezca los siguientes campos:

    - **Incluir cotizaciones de venta** – Establezca esta opción en *Sí* para tener en cuenta las ofertas de venta cuando se ejecuta el plan actual. Configúrela en *No* para ignorarlos.
    - **Probabilidad %** – Establecer el nivel mínimo de confianza que se requiere para que una cotización se incluya en la planificación maestra. El cálculo de la planificación maestra incluirá todas las cotizaciones que se crearon a partir de oportunidades que tienen este porcentaje de probabilidad o superior. Para incluir todas las cotizaciones, incluidas las cotizaciones que no tienen ninguna probabilidad asignada o ninguna oportunidad asociada, establezca este campo en *0* (cero). Para obtener más información sobre las probabilidades de cotizaciones, consulte la siguiente sección.
    - **Incluir solicitudes de cotización** – Establezca esta opción en *Sí* para tener en cuenta RFQ cuando se ejecuta el plan actual. Configúrela en *No* para ignorarlos. Si elige considerar las RFQ, el sistema creará órdenes de compra planificadas para ellas, pero no especificará el proveedor hasta que se resuelva la RFQ. Los pedidos de compra planificados que se crean para las RFQ pueden afectar las cantidades de otros pedidos planificados.

1. Continúe configurando su plan maestro de la manera habitual.

## <a name="assign-and-view-probabilities-for-quotations"></a>Asignar y ver probabilidades para cotizaciones

Como se mencionó en la sección anterior, un plan maestro considerará solo las cotizaciones que cumplan o excedan el umbral de probabilidad que se define para el plan (si se define un umbral). Sin embargo, la probabilidad no se establece directamente en cada cotización. En cambio, se hereda de la oportunidad que se usó para generar la cotización. Por lo tanto, las cotizaciones que se crean directamente en la página **Todas las cotizaciones** no tendrán una probabilidad asignada a ellos o una oportunidad asociada a ellos, y nunca serán considerados por la planificación maestra (a menos que el campo **% de probabilidad** se establezca en *0* \[cero\]). Para que se le asigne una probabilidad, se debe generar una cotización a partir de una oportunidad.

### <a name="create-a-quotation-from-an-opportunity"></a>Crear cotización a partir de una oportunidad

Utilice el siguiente procedimiento para asignar una probabilidad a una oportunidad y luego cree una cotización a partir de esa oportunidad.

1. Vaya a **Ventas y marketing \> Relaciones \> Clientes potenciales \> Todos los clientes potenciales**.
1. Seleccione una oportunidad existente o seleccione **Nuevo** en el panel de acciones para crear una nueva.
1. Rellene la página de la oportunidad para identificar la oportunidad que desee. Asegúrese de configurar el campo **Probabilidad** con un valor apropiado. Solo los planes maestros que están configurados para buscar probabilidades de este valor o superior considerarán las cotizaciones que se generan a partir de esta oportunidad.
1. En el panel Acciones, seleccione **Guardar**.
1. En el Panel de acciones, en la pestaña **Oportunidad**, en el grupo **Nuevo**, seleccione **Cotización** o **Cotización del proyecto**, dependiendo del tipo de cotización que desee crear.
1. En el cuadro de diálogo **Crear cotización**, establezca los valores de los campos según sea necesario y, a continuación, seleccione **Aceptar**.
1. Se crea y abre una nueva cotización. Sobre la ficha desplegable **Líneas**, use la barra de herramientas para agregar líneas de ventas o líneas de proyecto según sea necesario para definir el contenido de la cotización.
1. En el panel Acciones, seleccione **Guardar**. A continuación, cierre la cotización.

### <a name="view-the-probability-that-is-assigned-to-a-quotation"></a>Ver la probabilidad que se le asigna a una cotización

La única forma de ver la probabilidad asignada a una cotización es abrir la oportunidad que se utilizó para crear esa cotización, como se describe en el siguiente procedimiento.

1. Vaya a **Ventas y marketing \> Presupuestos de ventas \> Todos los presupuestos**.
1. Si el **Id. de oportunidad** no se muestra (está oculta en una instalación predeterminada), siga estos pasos para mostrarla temporalmente. (Alternativamente, para mantener la columna **Id. de oportunidad** disponible, cree una [vista guardada](../../../fin-ops-core/fin-ops/get-started/saved-views.md?toc=/dynamics365/supply-chain/toc.json) que la incluya).

    1. Seleccione y mantenga presionado (o haga clic con el botón derecho) en la cuadrícula y luego seleccione **Insertar columnas**.
    1. En el cuadro de diálogo **Insertar columnas**, busque la fila donde **Campo** se establece en *Oportunidad* y seleccione la casilla de verificación **Seleccionar** para esa fila.
    1. Seleccione **Actualizar** para agregar la columna seleccionada a la página **Todas las cotizaciones**.

1. En la cuadrícula, busque la fila de la cotización correspondiente. Entonces, en la columna **Id. de oportunidad**, seleccione el valor para esa fila.

    > [!NOTE]
    > Si está buscando una cotización de proyecto, es posible que deba seleccionar el encabezado de columna **Tipo de cotización** y borre su filtro. En una instalación predeterminada, este filtro está configurado para que solo se muestren las cotizaciones de ventas.

1. Se abre la oportunidad relacionada. Ahora puede ver y editar el valor **Probabilidad** como usted requiere.
