--- 
title: "Configuración de grupos de contabilidad para impuestos"
description: Los impuestos se calculan y registran en las cuentas principales que se especifican en los grupos de registro.
author: twheeloc
manager: AnnBe
ms.date: 10/26/2017
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Operations
ms.search.region: Global
ms.author: vstehman
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: ef3cad6538d9efbd1c1881f4b7d771382d9b1ba8
ms.openlocfilehash: e50fc2b6b8f4cd91e9a5593297fff2e9a6ef5525
ms.contentlocale: es-es
ms.lasthandoff: 10/26/2017

---
# <a name="set-up-ledger-posting-groups-for-sales-tax"></a>Configuración de grupos de contabilidad para impuestos

[!INCLUDE [task guide banner](../../includes/task-guide-banner.md)]

Los impuestos se calculan y registran en las cuentas principales que se especifican en los grupos de registro. Los grupos de registro se asocian a cada código de impuestos. Puede establecer grupos de registro individuales para cada código de impuestos, usar un grupo de registro para todos los códigos de impuestos o bien asignar varios grupos de registro a los códigos de impuestos. Esta grabación usa la empresa de demostración DEMF. 

1. Vaya a Impuestos > Configuración > Impuestos > Grupos de registro.
2. Haga clic en Nuevo.
3. En el campo Grupos de registro.
4. En el campo Descripción, escriba un valor.
5. En el campo de impuestos repercutidos, seleccione la cuenta principal para impuestos repercutidos que se pagan a la autoridad fiscal.
    * Los impuestos se cobran en nombre de la autoridad fiscal cuando se venden bienes y servicios gravables.  
6. En el campo de impuestos soportados, seleccione la cuenta principal para impuestos soportados que se reciben de la autoridad fiscal.
    * Los proveedores cobran los impuestos en nombre de la autoridad fiscal cuando les compra bienes y servicios gravables. Este campo no está disponible si está activada la opción Aplicar reglas de tributación de impuestos en la página Parámetros de contabilidad general. En su lugar, los impuestos que se pagan a los proveedores se adeudan en la misma cuenta que la compra.   
7. En el campo de gastos de impuestos, seleccione la cuenta principal para registrar los impuestos deducibles no reclamados o notificados a la autoridad fiscal por los distribuidores como parte del cargo invertido de GST/HST.
    * La opción de IVA de importación tiene que seleccionarse para el código de impuestos en el grupo de impuestos que se usa en la transacción.  Este campo no está disponible si está activada la opción Aplicar reglas de tributación de impuestos en la página Parámetros de contabilidad general.   
8. En el campo de IVA de importación repercutido, seleccione la cuenta principal para registrar el IVA de importación soportado que se paga a la autoridad fiscal.
    * La opción de IVA de importación tiene que seleccionarse en el código de impuestos del grupo de impuestos para registrar el IVA de importación. Si está activada la opción Aplicar reglas de tributación de impuestos en los parámetros de contabilidad general, la diferencia se registra en la cuenta de gastos de la transacción.   
9. En el campo de la cuenta de liquidación, seleccione la cuenta principal en la que se registrará el saldo neto de las cuentas contables especificadas en los campos IVA de importación repercutido e Impuestos soportados.
    * El saldo se creará al ejecutar el trabajo Liquidar y registrar impuestos.  Si la autoridad fiscal para el período de liquidación está asociada con una cuenta de proveedor, el saldo se registra en la cuenta de proveedor en su lugar.   
10. En el campo de descuento por pronto pago del proveedor, seleccione la cuenta principal para registrar el descuento por pronto pago para los códigos de impuestos asociados a este grupo de registro.
    * Esto es opcional y, si no se especifica ninguna cuenta, se usará la cuenta principal de códigos de descuento por pronto pago. Puede resultar útil usar cuentas diferentes por cada grupo de registro si se usa la opción Deducir los impuestos del descuento por pronto pago en los grupos de impuestos.  
11. En el campo de descuento por pronto pago del cliente, seleccione la cuenta principal para registrar el descuento por pronto pago para los códigos de impuestos asociados a este grupo de registro.
    * Esto es opcional y, si no se especifica ninguna cuenta, se usará la cuenta principal de códigos de descuento por pronto pago. Puede resultar útil usar cuentas diferentes por cada grupo de registro si se usa la opción Deducir los impuestos del descuento por pronto pago en los grupos de impuestos.  
12. Haga clic en Guardar.


