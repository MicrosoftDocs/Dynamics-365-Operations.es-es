---
title: Configuración forma de pago para transferencias de crédito ISO20022
description: Este procedimiento muestra cómo configurar la forma de pago de la transferencia de crédito ISO20022 del proveedor o cualquier otro tipo de pago mediante informes electrónicos para generar un archivo.
author: mrolecki
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: VendPaymMode
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: mrolecki
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 7f87cc0dfa47295f047ef97732f60733c362ca4066d9070418322b34934e3ce3
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2021
ms.locfileid: "6773669"
---
# <a name="set-up-method-of-payment-for-iso20022-credit-transfer"></a>Configuración forma de pago para transferencias de crédito ISO20022

[!include [banner](../../includes/banner.md)]

Este procedimiento muestra cómo configurar la forma de pago de la transferencia de crédito ISO20022 del proveedor o cualquier otro tipo de pago mediante informes electrónicos para generar un archivo. 

Antes de completar esta tarea, debe exportar las configuraciones de formato y configurar las cuentas de pago.

Esta tarea se creó con la empresa de datos de demostración DEMF.

Este es el tercer procedimiento, de cinco, que muestra el proceso de pago del proveedor mediante las configuraciones de informes electrónicos. Este procedimiento es para una función que se ha agregado en la versión 1611 de Dynamics 365 for Operations.

1. Vaya a Proveedores > Configuración de pagos > Formas de pago.
2. Use el filtro rápido para buscar registros. Por ejemplo, filtre por el campo Forma de pago, por el valor "SEPA CT".
3. Haga clic en Editar.
4. En el campo Período, seleccione Total.
5. En el campo Tipo de pago, seleccione Pago electrónico.
6. Expanda la sección Formatos de archivo.
7. Seleccione Sí en el campo Informes electrónicos genéricos.
8. En el campo Configuración de formato de exportación, especifique o seleccione un valor.
    * En la lista, seleccione el valor de transferencia de crédito ISO20022 (DE). Si la lista está vacía, no hay ninguna configuración de formato de exportación de pago de proveedor importada y activa.  
9. En el campo Tipo de cuenta, seleccione Banco.
10. En el campo Cuenta de pago, especifique los valores "DEMF OPER".
11. Haga clic en Guardar.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]