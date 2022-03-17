---
title: Introducir datos de factura en el sistema de proveedores mediante un grupo de facturas
description: En este tema se describe cómo utilizar el registro de facturas para crear facturas.
author: abruer
ms.date: 07/31/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: abruer
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: a4768ee6ddbaba8ae5bab5e2f9f7df9239efeb90
ms.sourcegitcommit: 9cbff8a2cdeaf606488fb0044b3de4ab4409c9dc
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/26/2022
ms.locfileid: "8358298"
---
# <a name="key-invoice-data-into-the-ap-system-using-invoice-pool"></a>Introducir datos de factura en el sistema de proveedores mediante un grupo de facturas

[!include [banner](../../includes/banner.md)]

En este tema se describe cómo utilizar el registro de facturas para crear facturas. A continuación use el grupo de facturas para que coincida con la factura de un pedido de compra y para finalizar el gasto en la página de la factura de proveedor.


## <a name="create-a-purchase-order"></a>Crear un pedido de compra
1. En el Panel de exploración, vaya a **Módulos > Proveedores > Pedidos de compra > Pedidos de compra**.
2. Seleccione **Nuevo** para crear un pedido de compra nuevo.
3. En el campo **Cuenta de proveedor**, seleccione un proveedor en la lista desplegable. Por ejemplo, seleccione el proveedor **1001**.
4. Seleccione **Aceptar**.
5. En el campo **Número de artículo**, seleccione el número del artículo de servicios en la lista desplegable. Por ejemplo, **S0001**. El importe neto es 75,00.  Este es el importe que se espera en la factura.  
6. En el panel de acciones, seleccione **Compra.**
7. Seleccione **Confirmar**.

## <a name="create-and-post-and-invoice"></a>Crear y registrar una factura
1. En el panel de exploración, vaya a **Módulos > Proveedores > Facturas > Registro de facturas**.
2. Seleccione **Nuevo**.
3. Abra la búsqueda para seleccionar el nombre del registro de facturas que desea usar.
4. Seleccione el nombre del registro de facturas que desee usar.
5. Seleccione **Líneas** para abrir el registro y especificar las líneas de gastos.
6. En la búsqueda, seleccione un proveedor. Por ejemplo, seleccione el proveedor **1001**.
7. En el campo **Factura**, especifique el número de factura.
8. En el campo **Descripción**, escriba un valor.
9. En el campo **Crédito**, escriba un número.
10. En el campo **Pedido de compra**, abra la lista desplegable para seleccionar el pedido de compra que creó anteriormente.
11. En el campo **Aprobado por**, resalte un aprobador en la lista desplegable y haga clic en **Seleccionar** para seleccione dicho aprobador.
12. Seleccione **Registrar**.

## <a name="open-an-invoice-from-the-pool-and-match-it-to-a-purchase-order-to-complete-the-invoice-process"></a>Abrir una factura del grupo y conciliarla con un pedido de compra para completar el proceso de la factura
1. En el panel de exploración, vaya a **Módulos > Proveedores > Facturas > Grupo de facturas**.
2. Seleccione **Pedido de compra** para crear una factura de proveedor a partir de la factura del grupo.
3. Seleccione la factura que desea revisar.
4. Seleccione **Actualizar estado de conciliación** para completar la conciliación.
5. En el panel de acciones, seleccione **Opciones**.
6. Seleccione **Cambiar vista**.
7. Seleccione **Vista de cuadrícula**.
8. Seleccione **Registrar**.
9. Cierre la página.
10. En el panel de exploración, vaya a **Módulos > Proveedores > Proveedores > Proveedores**.
11. Seleccione el proveedor que estaba en el pedido de compra. Por ejemplo, seleccione el proveedor **1001**.
12. En el panel de acciones, seleccione **Proveedor**.
13. Seleccione **Transacciones**.
14. Seleccione la factura que ha creado. La acumulación de registro de facturas se ha invertido y registrado en la cuenta de gastos apropiada.  



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
