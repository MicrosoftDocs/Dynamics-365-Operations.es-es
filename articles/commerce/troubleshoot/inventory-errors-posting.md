---
title: Errores de registro de extractos debido a conflictos de actualización o inventario no disponible
description: Este artículo proporciona posibles soluciones para problemas relacionados con el inventario durante la publicación de estados de cuenta en Microsoft Dynamics 365 Commerce.
author: Shajain
ms.date: 12/19/2022
ms.topic: Troubleshooting
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: shajain
ms.search.validFrom: 2021-01-31
ms.openlocfilehash: cebb890b42def6e9b002b01be63266b88bfc35a4
ms.sourcegitcommit: 4ad87483ba0bfea3e04fdb7e578d8abc34e607a4
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/20/2022
ms.locfileid: "9887635"
---
# <a name="statement-posting-errors-due-to-unavailable-inventory-or-update-conflicts"></a>Errores de registro de extractos debido a conflictos de actualización o inventario no disponible

[!include [banner](../../includes/banner.md)]

Este artículo proporciona posibles soluciones para problemas relacionados con el inventario durante la publicación de estados de cuenta en Microsoft Dynamics 365 Commerce.

## <a name="description"></a>Description

Durante la publicación de transacciones comerciales, es posible que reciba mensajes de error relacionados con problemas de inventario o conflictos de actualización.

### <a name="inventory-issues-error-message"></a>Mensaje de error de problemas de inventario

Si encuentra problemas de inventario, el mensaje de error que recibe se parecerá a este ejemplo:

> xx no se puede seleccionar ya que solamente yy está(n) disponible(s) en el inventario

### <a name="update-conflict-error-messages"></a>Actualizar mensajes de error de conflicto

Se puede producir un conflicto de actualización cuando el método de valoración de inventario es *coste estándar* o *media móvil*. Debido a que ambos métodos son métodos de cálculo de costos perpetuos, el costo final se determina en el momento de la contabilización.

Si está usando el método *media móvil*, el mensaje de error de conflicto de actualización que recibe se parece a este ejemplo:

> No se espera el valor de inventario xx.xx después del cálculo de gasto proporcional

Si está usando el método *coste estándar*, el mensaje de error de conflicto de actualización que recibe se parece a este ejemplo:

> El coste estándar no coincide con el valor del inventario financiero después de la actualización. Valor = xx.xx, Cant. = yy.yy, Coste estándar = zz.zz

## <a name="resolutions"></a>Soluciones

### <a name="workaround-for-the-inventory-error"></a>Solución para el error de inventario

Puede mitigar el error de inventario actualizando manualmente el inventario del artículo o habilitando el inventario negativo físico para el grupo de modelos de artículos asociado con el artículo en Commerce Headquarters.

Para una experiencia de publicación coherente, Microsoft recomienda habilitar el inventario negativo físico para el grupo de modelos de artículos. En algunos casos es posible que no se puedan registrar extractos a menos que haya habilitado un inventario físico negativo.

Por ejemplo, no hay inventario disponible para un artículo, pero un cajero devuelve el artículo y luego lo vuelve a agregar a la misma transacción a un precio reducido para imitar una igualación de precios. En este caso, tanto la transacción de devolución como la transacción de venta se incluirán en la misma declaración del pedido de un solo cliente. Sin embargo, debido a que no hay garantía de que la línea de devolución (que aumenta el inventario) se registre antes de que se registre la línea de ventas (que reduce el inventario), pueden ocurrir errores de inventario. Si se activa el inventario negativo físico en este escenario, el registro de transacción no se verá afectado negativamente, y el sistema refleja correctamente el inventario.

#### <a name="enable-negative-physical-inventory-for-an-item-model-group"></a>Habilitar inventario físico negativo para un grupo de modelos de artículos

Para habilitar el inventario físico negativo para un grupo de modelos de artículos en Commerce Headquarters, siga estos pasos.

1. Vaya a **Gestión del inventario \> Configuración \> Inventario**
1. En el panel de navegación de la izquierda, seleccione el grupo de modelo de artículo.
1. En la sección **Políticas de inventario**, en **Inventario negativo**, seleccione la casilla de verificación **Inventario negativo físico**.

![Inventario negativo físico habilitado.](./media/Physical_Negative_Inventory.png)

### <a name="workaround-for-the-update-conflict-error"></a>Solución para el error de conflicto de actualización

Para conocer posibles soluciones para corregir el error de conflicto de actualización, consulte [Se produce un conflicto de actualización cuando el método de valoración del inventario es el costo estándar o el promedio móvil](/troubleshoot/dynamics-365/supply-chain/costing/update-conflict-standard-cost-moving-average-inventory-valuation).

> [!NOTE]
> Para el error de conflicto de actualización, no es necesario que elimine los pedidos de los clientes que se generaron mediante el paso de publicación de agregación. Después de implementar las soluciones alternativas sugeridas, el estado de cuenta debe publicarse si vuelve a intentar publicar el estado de cuenta.
