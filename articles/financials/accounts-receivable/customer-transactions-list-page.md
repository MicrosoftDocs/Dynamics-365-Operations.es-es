---
title: "Página de lista de transacciones de cliente"
description: "Este tema proporciona información acerca de la página de lista de transacciones de cliente para Microsoft Dynamics 365 for Finance and Operations."
author: mikefalkner
manager: aolson
ms.date: 08/02/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: CustTrans
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: mikefalkner
ms.search.validFrom: 2017-06-30
ms.dyn365.ops.version: 8.0.4
ms.translationtype: HT
ms.sourcegitcommit: 98ed3378ab05c0c69c9e5b2a82310113a81c2264
ms.openlocfilehash: e828cb292ad48bb4690117b41589b25edcdf28bc
ms.contentlocale: es-es
ms.lasthandoff: 08/31/2018

---

# <a name="customer-transaction-list-page"></a>Página de lista de transacciones de cliente

[!include [banner](../includes/banner.md)]

## <a name="view-settlements"></a>Ver liquidaciones

La pestaña **Ver liquidaciones** en el panel de acciones proporciona un acceso rápido al historial de liquidaciones e información adicional acerca de la transacción de liquidación completa. También puede mostrar transacciones adicionales relacionadas con la transacción seleccionada, ya sea porque formaban parte de la misma liquidación o porque son los pagos que se crearon en el mismo diario de pagos.

1. Seleccione **Clientes \> Clientes**.
2. Seleccione un cliente que tenga transacciones y, a continuación seleccione **Cliente \> Transacciones**.
3. Seleccionar una transacción para investigarla.
4. Seleccione la pestaña **Ver liquidaciones** en el panel de acciones.

    El cuadro de diálogo **Ver liquidaciones** muestra la transacción seleccionada y todos los documentos que se han liquidado con ella. Este cuadro de diálogo es similar a la vista de historial de liquidaciones, pero incluye todos los documentos relacionados. 

5. Puede realizar varias tareas de este cuadro de diálogo. Seleccione uno o más asientos y luego seleccione uno de los menús siguientes:

   - **Ver contabilidad** - Se ven todos los asientos que están relacionados con los documentos seleccionados. Haga clic en **Cerrar** para cerrar el cuadro de diálogo.
   - **Exportar** Exporte los asientos seleccionados a Microsoft Excel.
   - **Ver pagos relacionados** Todas las transacciones del diario de pagos creadas en el diario de pagos relacionado con el documento seleccionado. Además, aparecen todas las liquidaciones relacionadas con los pagos. La etiqueta de este menú también cambia a **Ver liquidaciones**. Seleccione **Ver liquidaciones** para mostrar sólo las transacciones que se mostraron cuando abrió por primera vez el cuadro de diálogo **Ver liquidaciones**.
    - **Liquidar transacciones** Este menú aparece si el documento original seleccionado no se ha liquidado por completo. Al seleccionarlo, el cuadro de diálogo **Liquidar transacciones** aparece, donde puede seleccionar las transacciones que quiere liquidar.
    - **Deshacer liquidación** Este menú aparece si el documento original seleccionado se liquidó por completo. Al seleccionarlo, el cuadro de diálogo **Deshacer liquidación** aparece, donde puede deshacer liquidaciones que se realizaron para dicho documento.
    

