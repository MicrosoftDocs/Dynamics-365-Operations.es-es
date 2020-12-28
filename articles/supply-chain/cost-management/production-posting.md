---
title: Registro de la producción
description: Este artículo proporciona información sobre los distintos tipos de registros en el proceso de producción.
author: AndersGirke
manager: tfehr
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: InventItemGroup, ProjCategory, WrkCtrResourceGroup, WrkCtrTable
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: 54591
ms.assetid: 0917fe64-f643-46ae-98ff-5013b266a067
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: b7214575e1eb3289224446ae5dd9d40221f054f8
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/13/2020
ms.locfileid: "4436937"
---
# <a name="production-posting"></a>Registro de la producción

[!include [banner](../includes/banner.md)]

Este artículo proporciona información sobre los distintos tipos de registros en el proceso de producción.

Las actividades de registro de producción siguen a los procesos de producción que se describen en las siguientes secciones.

## <a name="material-consumption"></a>Lista de selección
Los materiales se registran como consumidos durante la producción cuando se registra el diario de lista de selección de producción. Este proceso genera transacciones de emisión que reducen el inventario disponible. En los parámetros de producción, puede especificar si el valor de las materias primas en proceso (trabajo en curso \[WIP\]) se deben registrar en el libro mayor. El valor de las materias primas en curso se registra después en una cuenta dedicada de la lista de selección y en una cuenta de contrapartida de lista de selección dedicada.

## <a name="time-consumption"></a>Consumo de tiempo
El tiempo que los trabajadores invierten en trabajos de producción se registra en el diario de tarjeta de ruta o en el diario de tarjeta de trabajo. Cuando se registran estos diarios, se procesa un registro contable en una cuenta dedicada para recursos en curso (trabajo en curso). Este registro representa el valor de tiempo invertido en el pedido de producción. Después de que el pedido de producción se registre como terminado, se liquidarán las cuentas de trabajo en curso.

## <a name="reporting-finished-goods-and-error-quantities"></a>Notificación de productos terminados y cantidades de error
Cuando un pedido de producción se notifica como terminado, la cantidad de productos terminados que se haya completado se actualiza en la gestión de inventarios a través del diario Notificar como terminado. Si utiliza contabilidad de trabajo en curso, lo cual se puede configurar en los parámetros de producción, se crea un diario contable para reducir las cuentas de trabajo en curso y aumentar el inventario de productos terminados. El diario usa el coste estándar definido para el producto.

## <a name="ending-the-production-order"></a>Finalización del pedido de producción
Antes de completar un pedido de producción, se calculan los costes reales para la cantidad producida. Todos los costes estimados de material, mano de obra y gastos generales se invierten y sustituyen por los costes reales. El coste total del artículo terminado se carga desde la cuenta de recepción de inventario y se abona a la cuenta de emisiones de inventario. Si activa la casilla de verificación **Cierre final** al ejecutar el cálculo de costes, el estado de pedido de producción cambia a **Finalizado**. Este estado evita que los costes adicional se registren de forma inadvertida para un pedido de producción finalizado. Puede especificar que el valor de las cantidades equivocadas que se notifiquen como terminadas se asigne a las cantidades correctas notificadas como terminadas. También puede especificar que el valor de las cantidades equivocadas se debe registrar en una cuenta residual dedicada.

## <a name="controlling-the-level-of-ledger-posting"></a>Control del nivel de registro contable
En **Parámetros de control de producción**, puede usar el campo **Registro contable** para definir el nivel de registro contable para los procesos de producción. Los siguientes valores están disponibles:

-   **Artículo y recurso**: use las cuentas contables configuradas en los grupos de artículos para materias primas y productos terminados. El trabajo en curso para el consumo de tiempo se toma del recurso o del grupo de recursos de las operaciones de ruta.
-   **Artículo y categoría**: use las cuentas contables configuradas en los grupos de artículos para materias primas y productos terminados. El trabajo en curso para el consumo de tiempo se toma de las categorías de coste asociadas a las operaciones de ruta.
-   **Grupos de producción**: use las cuentas contables configuradas en los grupos de producción para el material y el consumo de tiempo. Los grupos de producción se asocian con los productos emitidos y se copian a los pedidos de producción cuando se crean esos pedidos. El registro en los pedidos de producción seguirá entonces los grupos de producción asociados al pedido de producción.

**Nota:** si se utiliza el método estándar para calcular el coste del artículo terminado, las transacciones finales lo reflejan. Si los costes reales y los costes calculados utilizando el método estándar varían, la diferencia se registra en la cuenta que muestra las pérdidas o beneficios.



