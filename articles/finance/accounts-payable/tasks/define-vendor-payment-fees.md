---
title: Definir cuotas de pagos a proveedores
description: Configuración de cuotas de pago para proveedores.
author: abruer
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: VendPaymFee, VendPaymModeFee, BankAccountTableLookUp
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: abruer
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 404bd1e22caa8098f114a2dcc67dd420509cce2b
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/13/2020
ms.locfileid: "4447444"
---
# <a name="define-vendor-payment-fees"></a>Definir cuotas de pagos a proveedores

[!include [banner](../../includes/banner.md)]

Configuración de cuotas de pago para proveedores. Esta tarea usa la empresa de demostración USMF.

1. Vaya a Proveedores > Configuración de pagos > Cuota de pago.
2. Haga clic en Nuevo.
3. En el campo Id. de cuota, escriba un valor.
    * El identificador de cuota debe describir cuando se usará esta cuota, como "Cuota_EFT".  
4. En el campo Nombre, escriba un valor.
5. En el campo Descripción de cuota, escriba un valor.
    * Agregue una descripción para proporcionar más detalles sobre cuándo se aplica la cuota.  
6. En el campo Cargo, seleccione Proveedor o Libro mayor.
    * Libro mayor se usa cuando la cuota se cobrará a su organización.  Proveedor se usa cuando la cuota se aplicará al proveedor.  
7. Especifique una cuenta principal donde contabilizar como gasto la cuota.
    * Esta opción solo está disponible si se ha seleccionado Libro mayor como opción Cargo.  
8. Seleccione el diario en el que se puede usar esta cuota. 
    * Para una cuota de pago de proveedor, seleccionaría el diario Pagos del proveedor.  
9. Haga clic en Guardar.
10. Haga clic en Configuración de cuota de pago.
    * Continúe con la configuración de la cuota de pago para definir cuándo debe incluirse la cuota de manera predeterminada en el diario seleccionado.  
11. Seleccione Tabla, Grupo o Todo.
    * Tabla se usa para seleccionar una única cuenta bancaria; Grupo se usa para seleccionar un grupo de bancos; y Todo se usa para emplear esta configuración de cuota en todas las cuentas bancarias.  
12. Seleccione un grupo de bancos o una cuenta bancaria.
    * La búsqueda mostrará el grupo de bancos si seleccionó Grupo, y cuentas bancarias si seleccionó Tabla.  
13. Seleccione la forma de pago para cuando se aplique esta cuota.
14. Seleccione la especificación de pago para la forma de pago seleccionada.
    * Especificación del pago se utiliza con formas de pago de transferencia electrónica de fondos.  
15. Seleccione si la cuota es un porcentaje, un importe o un intervalo.
16. Escriba el porcentaje o el importe de la cuota.
    * Si la cuota es un porcentaje, especifique el porcentaje. Si la cuota es un importe, especifique el importe de la cuota. Si la cuota es un intervalo, use la ficha Intervalo para definir las tasas por niveles.  
17. En el campo Divisa de cuota, seleccione la divisa para la que se aplicará la cuota.
    * Esta divisa es para la cuota. La divisa de pago se usa para definir si la regla de cuota se debe aplicar basándose en la divisa de pago. Por ejemplo, su banco puede cobrar una cuota cuando se realiza un pago en euros, pero en el resto de los pagos no se aplica una cuota.  
18. Haga clic en Guardar.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]