---
title: Configuración de créditos bancarios y perfiles de contabilización para créditos documentarios
description: Este procedimiento le muestra cómo crear un perfil de registro e instalaciones bancarias, necesario para procesar cartas de crédito.
author: kweekley
ms.date: 11/15/2022
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: BankParameters, DefaultDashboard, BankDocumentSetup, BankDocumentPosting
audience: Application User
ms.reviewer: twheeloc
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 7fe5b2ba43c4fcb4855c742bdb6f8209ebd92d68
ms.sourcegitcommit: cf6b764824bd1cf2c0dde6d37ddd0a7abab87ff0
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/16/2022
ms.locfileid: "9779472"
---
# <a name="set-up-bank-facilities-and-posting-profiles-for-letter-of-credit"></a>Configuración de créditos bancarios y perfiles de contabilización para créditos documentarios

[!include [banner](../../includes/banner.md)]

Este procedimiento le muestra cómo crear un perfil de registro e instalaciones bancarias, necesario para procesar cartas de crédito. 

Esta tarea usa la empresa de demostración USMF.


## <a name="general-ledger-parameter"></a>Parámetro de contabilidad general
1. Vaya a **Gestión de efectivo y bancos > Configurar > Parámetros de gestión de efectivo y bancos**.
2. Expanda la sección **Documento bancario**.
3. Seleccione la opción **Habilitar créditos documentarios de importación**.
4. Seleccione la opción **Habilitar créditos documentarios de exportación**.
5. Haga clic en **Guardar**.
6. Cierre la página.

## <a name="create-bank-facility"></a>Creación de instalaciones bancarias
1. Vaya a **Gestión de efectivo y bancos > Configuración > Instalaciones bancarias**.
2. Haga clic en **Nuevo**.
3. En el campo **Grupo de instalaciones**, indique el nombre del grupo de instalaciones bancarias.
4. En el campo **Descripción**, escriba la descripción del grupo de instalaciones bancarias.
5. Haga clic en **Guardar**.
6. Haga clic en la pestaña **Tipos de instalación**.
7. Haga clic en **Nuevo**.
8. En el campo **Tipo de instalación**, especifique un código único.
9. En el campo **Descripción**, escriba un valor.
10. En el campo **Grupo de instalaciones**, haga clic en el botón desplegable para abrir la búsqueda.
11. En la lista, busque y seleccione el registro deseado.
12. En la lista, haga clic en el vínculo de la fila seleccionada.
13. En el campo **Naturaleza de la instalación**, seleccione la naturaleza de las instalaciones bancarias.
14. Haga clic en **Guardar**.
15. Cierre la página.

## <a name="bank-posting-profile"></a>Perfil de contabilización de banco
1. Vaya a **Gestión de efectivo y bancos > Configuración > Perfil de registro de documentos bancarios**.
2. Haga clic en **Nuevo**.
3. En el campo **Número de grupo/cuenta**, haga clic en el botón desplegable para abrir la búsqueda.
4. En la lista, busque y seleccione el registro deseado.
5. En la lista, haga clic en el vínculo de la fila seleccionada.
6. Seleccione la cuenta principal de liquidación.
    * Esta cuenta se usa para calcular la previsión de flujo de efectivo.  
7. En el campo **Cuenta de gastos**, seleccione la cuenta de las transacciones de gastos.
8. En el campo **Cuenta de márgenes**, seleccione la cuenta de las transacciones de márgenes.
    * Al registrar el margen de apertura, se crea un adeudo en la cuenta. Al registrar el pago, se realiza un abono.  
9. Haga clic en **Guardar**.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
