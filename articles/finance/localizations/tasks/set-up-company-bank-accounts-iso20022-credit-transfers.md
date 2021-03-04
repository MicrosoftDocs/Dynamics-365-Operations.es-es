---
title: Configurar cuentas bancarias de la empresa para transferencias de crédito ISO20022
description: Este procedimiento muestra cómo configurar la información de cuenta bancaria específica de empresa necesaria para generar el archivo de pago.
author: mrolecki
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: BankAccountTable, OMLegalEntity, BankAccountTableLookUp
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: mrolecki
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 5e121ce7d87ee50a4e6b367a170eea4375d64fb3
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/13/2020
ms.locfileid: "4447527"
---
# <a name="set-up-company-bank-accounts-for-iso20022-credit-transfers"></a>Configurar cuentas bancarias de la empresa para transferencias de crédito ISO20022

[!include [banner](../../includes/banner.md)]

Este procedimiento muestra cómo configurar la información de cuenta bancaria específica de empresa necesaria para generar el archivo de pago. Debe configurar la información necesaria para generar el formato de transferencia de crédito ISO 20022 pero en función del formato es posible que se precise otra información, como el identificador de empresa o el código de ordenación. 

La empresa de datos de demostración utilizada para crear este procedimiento es DEMF.

Este es el segundo procedimiento, de cinco, que muestra el proceso de pago del proveedor mediante las configuraciones de informes electrónicos. Este procedimiento es para una función que se ha agregado en la versión 1611 de Dynamics 365 for Operations.


## <a name="set-up-iban-and-swift-code"></a>Configuración del IBAN y el código SWIFT
1. Vaya a Gestión de efectivo y bancos > Cuentas bancarias.
2. Use un filtro rápido para filtrar por el campo Cuenta bancaria, por el valor ''DEMF OPER".
3. Haga clic en DEMF OPER para abrir los detalles de la cuenta bancaria.
4. Haga clic en Editar.
5. Expanda la sección Identificación adicional.
6. En el campo IBAN, escriba ''DE89370400440532013000".
7. En el campo Código SWIFT, escriba "DEUTDEFF".
    * Tenga en cuenta que no requiere SWIFT\BIC para muchos formatos de pago, aunque se recomienda tenerlos registrados para una cuenta bancaria.  
8. Haga clic en Guardar.

## <a name="set-up-bank-account-for-the-legal-entity"></a>Configuración de la cuenta bancaria para la entidad jurídica
1. Vaya a Administración de la organización > Organizaciones > Entidades jurídicas.
2. Haga clic en Editar.
3. Expanda la sección Información de cuenta bancaria.
4. En el campo Cuenta bancaria, especifique o seleccione un valor.
5. Haga clic en Guardar.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]