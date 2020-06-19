---
title: Planificación maestra con acuerdos comerciales de compra
description: Este tema describe cómo Optimización de planificación puede encontrar el proveedor y/o el tiempo de entrega de un pedido planificado, en función del mejor precio o tiempo de entrega que se encuentra en los acuerdos comerciales de compra.
author: ChristianRytt
manager: tfehr
ms.date: 06/29/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ReqCreatePlanWorkspace
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2020-05-29
ms.dyn365.ops.version: AX 10.0.12
ms.openlocfilehash: b302c5ace34a11a53a98c733b59633a11a463bfa
ms.sourcegitcommit: 3fa1e8583003a90ba486f757c3826b139e1b3f73
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/02/2020
ms.locfileid: "3421540"
---
# <a name="master-planning-with-purchase-trade-agreements"></a>Planificación maestra con acuerdos comerciales de compra

[!include [banner](../../includes/banner.md)]

Este tema describe cómo Optimización de planificación puede encontrar el proveedor y/o el tiempo de entrega de un pedido planificado, en función del mejor precio o tiempo de entrega que se encuentra entre todos los acuerdos comerciales de compra que se han especificado para un producto determinado.

## <a name="turn-on-the-purchase-trade-agreements-for-planning-optimization-feature"></a>Active los acuerdos comerciales de compra para la característica Optimización de planificación

Antes de poder usar esta característica debe estar activada en su sistema. Los administradores pueden usar el espacio de trabajo [Administración de características](../../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) para verificar el estado de la característica y activarla si es necesario. Allí, la característica se enumera de la siguiente manera:

- **Módulo:** *Planificación maestra*
- **Nombre de característica:** *Acuerdos comerciales de compra para Optimización de planificación*

## <a name="prepare-your-system-to-evaluate-purchase-trade-agreements-during-master-planning"></a>Prepare su sistema para evaluar los acuerdos comerciales de compra durante la planificación maestra

Siga estos pasos para configurar su sistema para aplicar Optimización de planificación, que evalúa los acuerdos comerciales de compra.

1. Vaya a **Planificación maestra \> Configuración \> Parámetros de planificación maestra**. En la pestaña **Pedidos planificados**, en la sección **Proveedor**, establezca los siguientes valores:

    - **Encontrar acuerdo comercial**: establezca esta opción en **Sí** para incluir acuerdos comerciales de compra en la planificación maestra.
    - **Criterio de búsqueda**: seleccione el factor que desea priorizar para cada acuerdo comercial de compra, o sea **Plazo de ejecución mínimo** o **Precio unitario más bajo**.

1. Vaya a **Adquisiciones y abastecimiento \> Preparar \> Precios y descuentos \> Activar precio/descuento** y asegúrese de que la opción **Proveedor** está establecida en **Sí**.
1. Vaya a **Gestión de información de producto \> Preparar \> Dimensión y grupos variantes \> Grupos de dimensiones de almacenamiento** y seleccione un grupo de dimensiones de almacenamiento que se aplique a los productos para los que la planificación maestra debe evaluar los acuerdos comerciales de compra. Asegúrese de que cada dimensión de almacenamiento relevante de este grupo tenga una marca de verificación en la columna **Para precios de compra**. Repita este paso para todos los demás grupos de dimensiones de almacenamiento relevantes.

## <a name="prepare-a-released-product-to-evaluate-purchase-trade-agreements-during-master-planning"></a>Prepare un producto despachado para evaluar los acuerdos comerciales de compra durante la planificación maestra

Una vez que su sistema esté preparado como se describe en la sección anterior, debe seguir estos pasos para asegurarse de que cada producto que desea usar con esta característica esté configurado correctamente.

1. Vaya a **Panel de navegación \> Productos \> Productos despachados** y abra un producto objetivo.
1. En la ficha desplagable **Compra**, asegúrese de que no haya ningún proveedor asignado en el campo **Proveedor**.
1. En el panel Acciones, en la pestaña **Plan**, en el grupo **Cobertura**, seleccione **Cobertura de artículos** para abrir la página **Cobertura de artículos** para el producto seleccionado. Compruebe los siguientes ajustes:

    - En la pestaña **General**, puede configurar anulaciones de proveedor. Si desea que Optimización de planificación use acuerdos comerciales de compra para seleccionar un proveedor, debe evitar las anulaciones de proveedores borrando la casilla **Usar configuración específica**.
    - En la pestaña **Tiempo de espera**, puede configurar anulaciones del tiempo de entrega. Si desea que Optimización de planificación use acuerdos comerciales de compra para seleccionar plazos de entrega, debe evitar las anulaciones del plazo de entrega. Desactive la casilla de verificación para cada tipo de tiempo de entrega que desee seleccionar mediante acuerdos comerciales de compra (**Compra**, **Producción** y/o **Transferir**).

1. Cierre la página **Cobertura del artículo** para volver a la página de detalles del producto seleccionado.
1. En el panel Acciones, en la pestaña **Plan**, en el grupo **Pronóstico**, seleccione **Previsión de suministro** para abrir la página **Previsión de suministro**. Asegúrese de que ninguna fila que se muestra aquí tenga un valor en la columna **Cuenta de proveedor**.
1. Cierre la página **Previsión de suministro** para volver a la página de detalles del producto seleccionado.
1. En el panel Acciones, en la pestaña **Compra**, en el grupo **Acuerdos de compra**, seleccione **Ver acuerdos comerciales**. Asegúrese de que se enumeren todos los acuerdos comerciales de compra relevantes. También asegúrese de que la opción **No tener en cuenta el tiempo de entrega** esté establecida en **No** para cada acuerdo en el que desea que Optimización de planificación use el tiempo de entrega especificado para ese acuerdo.
1. En el panel Acciones, en la pestaña **Plan**, en el grupo **Configuración de pedidos**, seleccione **Configuración de pedidos predeterminada** para abrir la página **Configuración de pedidos predeterminada** para el producto seleccionado. En la ficha desplegable **Pedido de compra**, consulte el valor del campo **Tiempo de entrega de compra**. Si no se define una anulación del tiempo de entrega de la cobertura de artículos, Optimización de planificación utilizará este valor cuando seleccione acuerdos comerciales donde la opción **No tener en cuenta el tiempo de entrega** está establecida en **Sí**. Por lo tanto, debe ajustar este valor según requiera.
1. Repita este procedimiento para cada producto relevante.

> [!NOTE]
> La divisa de la línea del acuerdo comercial de compra debe coincidir con la divisa del proveedor seleccionado. La planificación maestra solo incluirá información de las líneas de acuerdos comerciales de compra donde la divisa coincida con la divisa del proveedor.

## <a name="examples-of-how-planning-optimization-finds-vendor-and-lead-times"></a>Ejemplos de cómo Optimización de planificación encuentra proveedores y plazos de entrega

La siguiente tabla proporciona ejemplos que muestran cómo varias configuraciones para un producto despachado y sus acuerdos comerciales de compra asociados afectan los valores que se encuentran para el pedido de compra planificado resultante. Los valores en **negrita** de las dos columnas más a la derecha son los valores seleccionados por Optimización de planificación. Los valores en ***negrita y cursiva*** de las otras columnas son las configuraciones que produjeron los valores resultantes para cada fila.

| Producto despachado: Proveedor | Configuración de pedido predeterminada: tiempo de entrega | Cobertura del artículo: anulación de proveeedor | Cobertura del artículo: anulación de tiempo de entrega | Acuerdo comercial: proveedor | Acuerdo comercial: plazo de entrega | Acuerdo comercial: pasar por alto plazo de entrega | Proveedor resultante | Plazo de entrega resultante |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
| ***US001*** | ***1*** | Nº | Nº | US003 | 3 | Nº | **US001** | **1** |
| US001 | 1 | ***Sí: US002*** | ***Sí: 2*** | US003 | 3 | Nº | **US002** | **2** |
| *(En blanco)* | 1 | Nº | Nº | ***US003*** | ***3*** | Nº | **US003** | **3** |
| *(En blanco)* | ***1*** | Nº | Nº | ***US003*** | 3 | Sí | **US003** | **1** |
| *(En blanco)* | ***1*** | ***Sí: US002*** | Nº | US003 | 3 | Nº | **US002** | **1** |
| *(En blanco)* | ***1*** | ***Sí: US002*** | Nº | US003 | 3 | Nº | **US002** | **1** |
| *(En blanco)* | 1 | Nº | Sí: 2 | ***US003*** | ***3*** | Nº | **US003** | **3** |
| *(En blanco)* | 1 | Nº | ***Sí: 2*** | ***US003*** | 3 | Sí | **US003** | **2** |

## <a name="additional-resources"></a>Recursos adicionales

[Acuerdos de compra](../../procurement/purchase-agreements.md)
