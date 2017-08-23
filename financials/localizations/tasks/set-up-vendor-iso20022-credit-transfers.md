--- 
title: "Configurar proveedores y cuentas bancarias de los proveedores para las transferencias de crédito ISO20022"
description: "Este procedimiento muestra cómo configurar el proveedor y la información de cuenta bancaria específica de proveedor necesarios para Transferencia de crédito ISO20022 o para cualquier otra generación del archivo de pago del proveedor."
author: mrolecki
manager: AnnBe
ms.date: 10/24/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Operations
ms.search.region: Global
ms.author: mrolecki
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: f01d88149074b37517d00f03d8f55e1199a5198f
ms.openlocfilehash: 147d8fa82bf15c984ad263cada42789038fa7371
ms.contentlocale: es-es
ms.lasthandoff: 07/27/2017

---
# <a name="set-up-vendors-and-vendor-bank-accounts-for-iso20022-credit-transfers"></a>Configurar proveedores y cuentas bancarias de los proveedores para las transferencias de crédito ISO20022

[!include[task guide banner](../../includes/task-guide-banner.md)]

Este procedimiento muestra cómo configurar el proveedor y la información de cuenta bancaria específica de proveedor necesarios para Transferencia de crédito ISO20022 o para cualquier otra generación del archivo de pago del proveedor. 

La empresa de datos de demostración utilizada para crear este procedimiento es DEMF.
Este es el cuarto procedimiento, de cinco, que muestra el proceso de pago del proveedor mediante las configuraciones de informes electrónicos. Este procedimiento es para una función que se ha añadido en la versión 1611 de Dynamics 365 for Operations.


## <a name="set-up-bank-details"></a>Configuración de detalles bancarios
1. Vaya a Proveedores > Proveedores > Todos los proveedores.
2. Use el filtro rápido para buscar registros. Por ejemplo, filtre por el campo Cuenta de proveedor, por el valor "DE-001".
3. Haga clic en DE-001 para abrir los detalles del proveedor.
4. En el panel de acciones, haga clic en Proveedor.
5. Haga clic en Cuentas bancarias.
6. Haga clic en Editar.
    * Si no hay ninguna cuenta bancaria disponible, necesita crear una nueva.  
7. En el campo Código SWIFT, escriba "COBADEFFXXX".
8. En el campo IBAN, escriba ''DE36200400000628808808".
9. Cierre la página.

## <a name="set-up-a-method-of-payment-for-the-vendor"></a>Configuración de un método de pago para el proveedor
1. Haga clic en Editar.
2. Expanda o contraiga la sección Pago.
3. En el campo Forma de pago, haga clic en el botón desplegable para abrir la búsqueda.
4. En la lista, haga clic en el vínculo de la fila SEPA CT.
5. Haga clic en Guardar.


