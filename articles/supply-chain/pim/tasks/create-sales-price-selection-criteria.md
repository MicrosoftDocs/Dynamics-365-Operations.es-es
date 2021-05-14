---
title: Crear criterios de selección de precios de venta
description: Este procedimiento muestra cómo crear un criterio de selección del precio de ventas para los modelos de precio de ventas basados en atributos.
author: ShylaThompson
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: DefaultDashboard, EcoResProductVariantMaintainWorkspace, PCProductConfigurationModelListPage, PCPriceModelSelectionCriteria, SysQueryForm, SysQueryTableLookUp, SysQueryFieldLookUp
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 69d22c3321beaa2667ee20bff00acd746714b993
ms.sourcegitcommit: fa99a36c3d30d0c0577fd3f63ed6bf2f71599e40
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/20/2021
ms.locfileid: "5920540"
---
# <a name="create-sales-price-selection-criteria"></a>Crear criterios de selección de precios de venta

[!include [banner](../../includes/banner.md)]

Este procedimiento muestra cómo crear un criterio de selección del precio de ventas para los modelos de precio de ventas basados en atributos. Este procedimiento requiere que haya al menos un modelo de precio de ventas disponible. Este ejemplo usa el modelo de precio para el modelo de precio de ventas de la solución Altavoz en la empresa de los datos de demostración USMF. Normalmente, un responsable de productos utiliza este procedimiento.

## <a name="add-a-new-criterion-for-an-existing-sales-price-model"></a>Agregue un nuevo criterio para un modelo de precio de ventas existente

1. Vaya a **Gestión de información de productos \> Productos \> Modelos de configuración del producto**.
1. En la lista, seleccione la fila del modelo de producto de la solución Altavoz, pero no seleccione el vínculo del nombre del modelo.
1. En el panel de acciones, haga clic en **Modelo**.
1. Seleccione **Criterios de modelo de precio**.
1. Seleccione **Nuevo**.
1. En el campo **Nombre**, escriba 'Grupo de clientes 10'.
    * El nombre del criterio del modelo de precios se usa para ayudar a identificar los criterios de selección subyacentes.  
1. En el campo **Modelo de precio**, especifique o seleccione un valor.
1. En el campo **Tipo de pedido**, seleccione *Pedido de ventas*.
    * El tipo de pedido determina los campos de base de datos que estarán disponibles para la consulta de selección.  
1. Especifique una fecha en el campo **Válido desde**.
1. En el campo **Vence el**, especifique una fecha.
1. Seleccione **Guardar**.

## <a name="create-the-query-for-the-selection-criteria"></a>Cree la consulta para los criterios de selección

1. Seleccione **Editar**.
2. En el campo **Tabla**, seleccione *Clientes*.
3. En el campo **Campo**, seleccione *Grupo de clientes*.
    * En este ejemplo, utilizaremos un grupo de clientes específico para los criterios de selección.  
4. En el campo **Criterios**, seleccione *Grupo de clientes 10*.
5. Seleccione **Aceptar**.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]