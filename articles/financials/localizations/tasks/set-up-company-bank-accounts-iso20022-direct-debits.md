--- 
title: "Configurar cuentas bancarias de empresa para débitos directos ISO20022"
description: "Esta tarea le explica cómo configurar la información de la cuenta bancaria específica de la empresa necesaria para generar archivos de pago de cliente."
author: mrolecki
manager: AnnBe
ms.date: 11/14/2016
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
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: f827b4787506cfdec8b9a91c4a68f3293190158a
ms.openlocfilehash: 6b61495342b18d6dbadb36d8ca146f5a68ba9f6c
ms.contentlocale: es-es
ms.lasthandoff: 09/29/2017

---
# <a name="set-up-company-bank-accounts-for-iso20022-direct-debits"></a>Configurar cuentas bancarias de empresa para débitos directos ISO20022

[!include[task guide banner](../../includes/task-guide-banner.md)]

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


