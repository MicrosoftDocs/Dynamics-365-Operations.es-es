---
title: Visión general de las versiones de gestión de costes
description: Este artículo proporciona información acerca de las versiones de gestión de costes, cómo mantenerlas y los tipos de datos que se pueden incluir en ellas. El propósito principal de una versión de gestión de costes es contener los registros de costes acerca de los artículos, las categorías de coste y las fórmulas de cálculo de los costes indirectos.
author: JennySong-SH
ms.date: 07/25/2019
ms.topic: overview
ms.prod: ''
ms.technology: ''
ms.search.form: BOMCalcDialog, BOMCalcTable, CostingVersion
audience: Application User
ms.reviewer: kamaybac
ms.custom:
- "54532"
- intro-internal
ms.assetid: cd239da5-f434-4d1b-8196-5414c888d76d
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: yanansong
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 7f83c35872c769ffd14894aaacc729b031d76504
ms.sourcegitcommit: 9166e531ae5773f5bc3bd02501b67331cf216da4
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/03/2022
ms.locfileid: "8670536"
---
# <a name="costing-versions-overview"></a>Visión general de las versiones de gestión de costes

[!include [banner](../includes/banner.md)]

Este artículo proporciona información acerca de las versiones de gestión de costes, cómo mantenerlas y los tipos de datos que se pueden incluir en ellas. El propósito principal de una versión de gestión de costes es contener los registros de costes acerca de los artículos, las categorías de coste y las fórmulas de cálculo de los costes indirectos.

Una versión de gestión de costes puede tener uno o varios propósitos, en función de los datos que contenga. El propósito principal de una versión de gestión de costes es contener los registros de costes acerca de los artículos, las categorías de coste y las fórmulas de cálculo de los costes indirectos. Además, puede contener un conjunto de registros de costes estándar o de costes planificados basados en el tipo de gestión de costes asignado a la versión de gestión de costes.

## <a name="costing-versions-for-standard-or-planned-costs"></a>Versiones de gestión de costes para costes estándar o planificados
### <a name="standard-costs"></a>Costes estándar

Una versión de gestión de costes puede admitir un modelo de inventario de costes estándar para artículos y contener un conjunto de registros de costes estándar y procesos de fabricación. Los datos de coste acerca de los procesos de fabricación se expresan desde el punto de vista de categorías de coste para operaciones de enrutamiento y fórmulas de cálculo para gastos generales de fabricación.

### <a name="planned-costs"></a>Costes planificados

Una versión de gestión de costes puede contener un conjunto de registros de costes planificados acerca de los artículos y procesos de fabricación. La versión de gestión de costes con costes planificados suele usarse para admitir simulaciones de cálculo de costes como, por ejemplo, simular cómo afectan los cambios de coste al material comprado o el efecto de los procesos de fabricación sobre los costes calculados de artículos fabricados. Los registros de costes de artículo para los costes planificados también se pueden usar para admitir un modelo de inventario de coste real al proporcionar los valores iniciales de los costes de los artículos. Estos valores incluyen el cálculo de los costes planificados para los artículos fabricados.

## <a name="entering-costs"></a>Introducción de costes
El mantenimiento de los datos de los registros de costes dentro de una versión de gestión de costes implica la especificación de costes para artículos comprados y para artículos que se transfieren entre sitios. Un mantenimiento adicional de datos implica la especificación de costes para categorías de costes asociadas a operaciones de ruta, la especificación de fórmulas de cálculo para los costes indirectos que reflejen los gastos generales de fabricación, así como el cálculo de costes para artículos fabricados. 

Los datos de coste de artículo en una versión de gestión de costes incluirán uno o más registros de costes para cada artículo. La primera vez que se especifica un registro de coste de artículo, presenta un estado **Pendiente** y una fecha de vigencia prevista. Al activar el registro de costes de artículo, se actualiza el estado a **Activo** y la fecha de vigencia a la fecha de activación. Diferentes registros de costes de artículo pueden reflejar sitios, fechas de vigencia o estados diferentes. Al calcular los costes para artículos fabricados para una fecha futura, el cálculo de la lista de materiales (L. MAT.) usa registros de costes con la fecha de vigencia pertinente, independientemente de si el estado es **Pendiente** o **Activo**. El registro de costes activo actual de un artículo se usa para estimar los costes de la orden de producción y evaluar las transacciones de inventario bajo un modelo de inventario de gestión de costes. El mantenimiento de los registros de costes para las categorías de costes y las fórmulas de cálculo de costes indirectos es similar al mantenimiento de registros de costes. 

Dos directivas de bloqueo para una versión de gestión de costes determinan si los costes pendientes se pueden mantener y si el coste pendiente se puede activar. Use las directivas de bloqueo para permitir mantener datos y, a continuación, impedirlo para los registros de costes dentro de una versión de gestión de costes. 

Una versión de gestión de costes también puede contener datos acerca de los precios de ventas de artículo o precios de compra para el cálculo de L. MAT.

## <a name="item-sales-prices-for-bom-calculations"></a>Precios de venta de artículos para cálculos de listas de materiales
La razón principal para incluir datos sobre precios de venta es conservar el precio de venta calculado del artículo fabricado. El precio de ventas calculado se podrá analizar para determinar cómo los componentes, las operaciones de ruta y los gastos generales contribuyen al coste y al precio de venta. 

El siguiente motivo para contener datos sobre precios de venta es definir los registros de los precios de venta de los componentes. De esta forma, estos registros se pueden usar para calcular el precio de venta de los artículos fabricados. Primero se define el modelo de precio de venta incrustado en un grupo de cálculo de lista de materiales y se asigna el grupo de cálculo de lista de materiales a los artículos adquiridos. Después, al realizar cálculos de listas de materiales que usen los costes planificados, se selecciona un modelo de precio de coste del grupo de cálculo de la lista de materiales. 

Si no, los registros de precios de venta de los artículos solo se utilizan como información de referencia, independientemente de que se especifiquen manualmente o se calculen. Si activa el registro de precio de venta de un artículo, podrá actualizar el precio de venta base del artículo. No obstante, el precio de venta base no es específico del sitio y se puede sobrescribir manualmente. El precio de venta base del artículo se utiliza como precio de venta predeterminado en los pedidos y presupuestos de venta.

## <a name="item-purchase-prices-for-bom-calculations"></a>Precios de compra de artículos para cálculos de listas de materiales
La razón principal para activar datos de precios de venta es definir los registros de precio de compra de los artículos componentes, de forma que estos registros se puedan utilizar para calcular los costes de los artículos fabricados. Los registros de precios de compra de artículo deben especificarse manualmente. 

Para habilitar el contenido sobre el precio de compra, primero se debe definir un grupo de cálculo de lista de materiales que contenga un modelo de precio de coste para el precio de compra del artículo y, a continuación, se debe asignar el grupo de cálculo de lista de materiales a los artículos comprados. Posteriormente, utilizará un modelo de precio de coste para el grupo de cálculo de lista de materiales al efectuar cálculos de lista de materiales que usen costes planificados para calcular el precio de venta de los artículos fabricados. 

Los registros de precio de compra de los artículos se utilizan también como información de referencia. Al cambiar el estado del registro de precio de compra de un artículo de **Pendiente** a **Activo**, se puede actualizar el precio de compra base del artículo. No obstante, el precio de compra base no es específico del sitio y se puede sobrescribir manualmente. El precio de compra base del artículo se usa como precio de compra predeterminado en los pedidos de compra.





[!INCLUDE[footer-include](../../includes/footer-banner.md)]