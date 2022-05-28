---
title: Configuración de grupos de registro para impuestos
description: Los impuestos se calculan y registran en las cuentas principales que se especifican en los grupos de registro de los libros de contabilidad.
author: twheeloc
ms.date: 07/01/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: TaxAccountGroup
audience: Application User
ms.reviewer: twheeloc
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: c353a4fbed3af0cd7477c9a1543baaf523da6f11
ms.sourcegitcommit: 5d1772bdeb21a9bec6dc49e64550aaf34127a4e2
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/10/2022
ms.locfileid: "8735766"
---
# <a name="set-up-ledger-posting-groups-for-sales-tax"></a>Configuración de grupos de registro para impuestos

[!include [banner](../../includes/banner.md)]

Los impuestos se calculan y registran en las cuentas principales que se especifican en los grupos de registro de los libros de contabilidad. Los grupos de registro se asocian a cada código de impuestos. Puede establecer grupos de registro individuales para cada código de impuestos, usar un grupo de registro para todos los códigos de impuestos o bien asignar varios grupos de registro a los códigos de impuestos. Esta grabación usa la empresa de demostración DEMF. 

1. Vaya a **Panel de navegación > Módulos > Impuestos > Configuración > Impuestos > Grupos de registro**.
2. Haga clic en **Nuevo**.
3. En el campo **Grupo de registro**, escriba un valor.
4. En el campo **Descripción**, escriba un valor.
5. En el campo **Impuestos repercutidos**, seleccione la cuenta principal para impuestos repercutidos que se pagan a la autoridad fiscal. Los impuestos se cobran en nombre de la autoridad fiscal cuando se venden bienes y servicios gravables.  
6. En el campo de **Impuestos soportados**, seleccione la cuenta principal para impuestos soportados que se reciben de la autoridad fiscal. Los proveedores cobran los impuestos en nombre de la autoridad fiscal cuando les compra bienes y servicios gravables. Este campo no está disponible si está activada la opción Aplicar reglas de tributación de impuestos en la página **Parámetros de contabilidad general**. En su lugar, los impuestos que se pagan a los proveedores se adeudan en la misma cuenta que la compra.   
7. En el campo **Gasto de IVA de importación**, seleccione la cuenta principal para registrar los impuestos deducibles no reclamados o notificados a la autoridad fiscal por los distribuidores como parte del cargo invertido de GST/HST. La opción **Utilizar IVA** tiene que seleccionarse para el **Código de impuestos** en el **Grupo de impuestos** que se usa en la transacción. Este campo no estará disponible si se selecciona la opción **Aplicar reglas de tributación de impuestos** en la página **Parámetros de contabilidad general**.   
8. En el campo **IVA de importación repercutido**, seleccione la cuenta principal para registrar el IVA de importación soportado que se paga a la autoridad fiscal. La opción **Usar IVA** tiene que seleccionarse en **Código de impuestos**, en **Grupo de impuestos** para registrar **Usar IVA**. Si está activada la opción **Aplicar reglas de tributación de impuestos** en los **Parámetros de contabilidad general**, la diferencia se registra en la cuenta de gastos de la transacción.   
9. En el campo de la **Cuenta de liquidación**, seleccione la cuenta principal en la que se registrará el saldo neto de las cuentas contables especificadas en los campos **IVA de importación repercutido** e **Impuestos soportados**. El saldo se creará al ejecutar el trabajo de liquidar y registrar impuestos.  Si la autoridad fiscal para el período de liquidación está asociada con una cuenta de proveedor, el saldo se registrará en la cuenta de proveedor en su lugar.
10. En el campo **Descuento por pronto pago del proveedor**, seleccione la cuenta principal para registrar el descuento por pronto pago para los códigos de impuestos asociados a este grupo de registro. Esto es opcional y, si no se especifica ninguna cuenta, se usará la cuenta principal de **Códigos de descuento por pronto pago**. Puede resultar útil usar cuentas diferentes por cada **Grupo de registro** si se usa la opción Deducir los impuestos del descuento por pronto pago en los Grupos de impuestos.  
11. En el campo **Descuento por pronto pago del cliente**, seleccione la cuenta principal para registrar el descuento por pronto pago para los **Códigos de impuestos** asociados a este **Grupo de registro**. Esto es opcional y, si no se especifica ninguna cuenta, se usará la cuenta principal de **Códigos de descuento por pronto pago**. Puede resultar útil usar cuentas diferentes por cada **Grupo de registro** si se usa la opción Deducir los impuestos del descuento por pronto pago en los **Grupos de impuestos**.  
12. Haga clic en **Guardar**.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
