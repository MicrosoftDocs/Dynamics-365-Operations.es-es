---
title: Crear un pedido de compra regido por el presupuesto
description: Use este procedimiento para crear un pedido de compra que se compruebe para ver si hay presupuesto disponible.
author: JennySong-SH
ms.date: 06/15/2020
ms.topic: business-process
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: yanansong
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: aa9777ad3aa487dfb558879335f93f347b8ac749
ms.sourcegitcommit: cfe8fbc202c3eb05d894076fdf99e46704f17365
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/15/2022
ms.locfileid: "9016199"
---
# <a name="create-a-purchase-order-governed-by-budget"></a>Crear un pedido de compra regido por el presupuesto

[!include [banner](../../includes/banner.md)]

Use este procedimiento para crear un pedido de compra que se compruebe para ver si hay presupuesto disponible.

## <a name="review-the-budget-control-configuration"></a>Revisar la configuración de control presupuestario

1. Vaya a **Gestión presupuestaria > Configuración > Control presupuestario > Configuración de control presupuestario**.
1. Seleccione la pestaña **Fondos presupuestarios disponibles**.
1. Seleccione la pestaña **Documentos y diarios**.
1. Seleccione la pestaña **Definir reglas de control presupuestario**.
1. Seleccione la pestaña **Definir grupos presupuestarios**.
1. Cierre la página.

## <a name="create-a-purchase-order"></a>Crear un pedido de compra

1. Vaya a **Adquisición y abastecimiento > Pedidos de compra > Todos los pedidos de compra**.
1. Seleccione **Nuevo**.
1. En el campo **Cuenta de proveedor**, especifique o seleccione un valor.
1. Expanda la ficha desplegable **General**.
1. En el campo de **Fecha de contabilidad**, defina la fecha.
1. Seleccione **Aceptar** para crear el diálogo y abrir el nuevo pedido de compras.
1. En la ficha desplegable **Líneas de pedido de compra**, seleccione **Añadir línea** desde la barra de herramientas para agregar una nueva línea y luego complete la línea según sea necesario para agregar un artículo al pedido.
1. En la barra de herramientas de la ficha desplegable **Líneas de pedido de compra**, seleccione **Operaciones financieras \> Distribuir importes**.
1. En el campo **Cuenta contable**, especifique una cuenta.
1. Cierre la página.

## <a name="perform-budget-checking"></a>Realizar comprobación presupuestaria

1. Continúe trabajando con el pedido de compra al que acaba de agregar una línea.
1. En la barra de herramientas de la ficha desplegable **Líneas de pedido de compra**, seleccione **Operaciones financieras \> Realizar comprobación presupuestaria**.
1. En la barra de herramientas de la ficha desplegable **Líneas de pedido de compra**, seleccione **Operaciones financieras \> Errores o advertencias de la comprobación presupuestaria**.
1. Se abre el cuadro de diálogo **Errores o advertencias de la comprobación presupuestaria**. Compruebe los resultados de la verificación y seleccione **Cerrar** para cerrar el diálogo.

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]