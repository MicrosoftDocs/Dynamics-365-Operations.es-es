---
title: Configurar cuentas bancarias de empresa para débitos directos ISO20022
description: Esta tarea le explica cómo configurar la información de la cuenta bancaria específica de la empresa necesaria para generar archivos de pago de cliente.
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
ms.openlocfilehash: 652d8aa8f78d9a12ee390d23904f2c94d9bcf684
ms.sourcegitcommit: 57e1dafa186fec77ddd8ba9425d238e36e0f0998
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/18/2020
ms.locfileid: "3144881"
---
# <a name="set-up-company-bank-accounts-for-iso20022-direct-debits"></a>Configurar cuentas bancarias de empresa para débitos directos ISO20022

[!include [banner](../../includes/banner.md)]

Esta tarea le explica cómo configurar la información de la cuenta bancaria específica de la empresa necesaria para generar archivos de pago de cliente. Este procedimiento usa el formato de débito directo ISO 20022 como ejemplo. Otros formatos pueden requerir información de configuración adicional como el identificador de empresa o el código de ordenación.



Esta tarea se creó con los datos de demostración de la empresa DEMF.



Este es el segundo de cinco procedimientos que muestra el proceso de pago del cliente mediante las configuraciones de informes electrónicos.


## <a name="set-up-the-iban-and-swift-codes"></a>Configuración de códigos IBAN y SWIFT
1. Vaya a Gestión de efectivo y bancos > Cuentas bancarias.
2. Use un filtro rápido para filtrar por el campo Cuenta bancaria, por el valor ''DEMF OPER".
3. En la lista, haga clic en el vínculo de la fila seleccionada.
    * Por ejemplo, haga clic en "DEMF OPER" para abrir los detalles de la cuenta bancaria.  
4. Haga clic en Editar.
5. Expanda o contraiga la sección Identificación adicional.
6. Escriba un valor en el campo IBAN.
    * Por ejemplo, escriba "DE89370400440532013000".  
7. En el campo Código SWIFT, escriba un valor.
    * Por ejemplo, especifique "DEUTDEFF".    Tenga en cuenta que no requiere SWIFT\BIC para muchos formatos de pago, aunque se recomienda tenerlos registrados para una cuenta bancaria.  
8. Haga clic en Guardar.

## <a name="set-up-a-bank-account-for-the-legal-entity"></a>Configuración de una cuenta bancaria para la entidad jurídica
1. Vaya a Administración de la organización > Organizaciones > Entidades jurídicas.
2. Haga clic en Editar.
3. Expanda o contraiga la sección Información de cuenta bancaria.
4. En el campo Cuenta bancaria, haga clic en el botón desplegable para abrir la búsqueda.
5. En la lista, haga clic en el vínculo de la fila seleccionada.
    * Por ejemplo, seleccione la cuenta bancaria "DEMF OPER".  
6. Haga clic en Guardar.

