---
title: Editar dimensiones financieras para transacciones minoristas
description: En este tema se describe cómo editar dimensiones financieras para transacciones minoristas en Microsoft Dynamics 365 Commerce.
author: josaw1
ms.date: 11/04/2020
ms.topic: index-page
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ed0f77f7-3609-4330-bebd-ca3134575216
ms.search.region: global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2018-11-15
ms.dyn365.ops.version: ''
ms.openlocfilehash: ff16d8e2e75a877e5ca7de604c7915e908473da6
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/31/2021
ms.locfileid: "5792714"
---
# <a name="edit-financial-dimensions-for-retail-transactions"></a>Editar dimensiones financieras para transacciones minoristas

[!include [banner](../includes/banner.md)]

En este tema se describe cómo editar dimensiones financieras para transacciones minoristas en Microsoft Dynamics 365 Commerce.

## <a name="edit-financial-dimensions"></a>Editar dimensiones financieras

Para editar dimensiones financieras para transacciones minoristas en la sede central de Commerce, siga estos pasos.

1. Abra la página **Configuración de dimensiones financieras para la integración de aplicaciones**.
1. Seleccione el registro **Integración de dimensiones predeterminadas** activo.
1. En la ficha desplegable **Dimensiones financieras**, asegúrese de que todas las dimensiones que desea editar en la hoja de cálculo de Excel estén presentes en la lista **Seleccionado**. Para obtener más información, consulte [Entidades de datos](https://docs.microsoft.com/dynamics365/fin-ops-core/dev-itpro/financial/financial-dimension-configuration-integration#data-entities).
1. Descargue y abra el archivo de Excel en la página **Extractos**, la página **Transacciones comerciales** o el icono **Errores de validación de transacciones** en el espacio de trabajo **Operaciones financieras de tienda**.
1. Para cambiar la dimensión financiera de la transacción, seleccione **Diseño** y, a continuación, el símbolo del lápiz junto a la fila **Transacción (auditable)**.
1. Busque y seleccione el campo **FinancialDimensionDisplayValue**, elija una celda en la parte del encabezado de la hoja de cálculo de Excel y luego seleccione **Agregar etiqueta**.
1. Seleccione una celda debajo de la celda que seleccionó en el paso anterior, elija **Agregar valor** y, a continuación, seleccione **Actualizar**. Las dimensiones financieras se agregan a la hoja de cálculo de Excel y luego se pueden editar y publicar.
1. Para cambiar las dimensiones en las líneas de transacción, seleccione la fila **Transacciones de ventas (auditables)**, seleccione el símbolo del lápiz y luego repita los pasos 6 y 7.
1. Para cambiar las dimensiones en las líneas de pago, seleccione la fila **Transacciones de pago (auditables)**, elija el símbolo del lápiz y luego repita los pasos 6 y 7.

## <a name="additional-resources"></a>Recursos adicionales

[Editar y auditar transacciones de gestión de efectivo y pago al contado sin entrega a domicilio](edit-cash-trans.md)

[Editar y auditar transacciones de pedidos de cliente asincrónicas y pedidos en línea](edit-order-trans.md)

[Crear un libro de trabajo de Excel para editar transacciones minoristas](create-excel-edit.md)

[Agregar campos a un libro de trabajo de Excel para editar transacciones minoristas](add-fields-excel.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]