---
title: Configuración de créditos bancarios y perfiles de contabilización para cartas de garantía
description: Esta tarea crea instalaciones bancarias y un perfil de contabilización necesario para procesar una carta de garantía.
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
ms.openlocfilehash: 0987ae1e9cfbb1e2d2a957a5fd1ad82257292c0a
ms.sourcegitcommit: 81bb8e51951395be3f18f45212e47e6c41656f6a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/23/2022
ms.locfileid: "9804111"
---
# <a name="set-up-bank-facilities-and-posting-profiles-for-letters-of-guarantee"></a>Configuración de créditos bancarios y perfiles de contabilización para cartas de garantía

[!include [banner](../../includes/banner.md)]

Esta tarea crea instalaciones bancarias y un perfil de contabilización necesario para procesar una carta de garantía.



Esta tarea usa la empresa de demostración USMF. 




## <a name="general-ledger-parameter"></a>Parámetro de contabilidad general
1. Vaya a **Gestión de efectivo y bancos > Configurar > Parámetros de gestión de efectivo y bancos**.
2. Expanda la sección **Documento bancario**.
3. Seleccione la opción **Habilitar carta de garantía**.
4. En el campo **Diario de transacción**, haga clic en el botón desplegable para abrir la búsqueda.
5. En la lista, busque y seleccione el registro deseado.
6. En la lista, haga clic en el vínculo de la fila seleccionada.
7. Haga clic en la pestaña **Secuencias numéricas**.
    * Definición del código de secuencia numérica para el número de la carta de garantía y las referencias de transacción de la carta de garantía  
8. Haga clic en **Guardar**.
9. Cierre la página.

## <a name="create-bank-facility"></a>Creación de instalaciones bancarias
1. Vaya a **Gestión de efectivo y bancos > Configuración > Instalaciones bancarias**.
2. Haga clic en **Nuevo**.
3. En el campo **Grupo de instalaciones**, especifique el nombre del grupo de instalaciones bancarias para la transacción de la carta de garantía.
4. En el campo **Descripción**, escriba un valor.
5. Haga clic en **Guardar**.
6. Haga clic en la pestaña **Tipos de instalación**.
7. Haga clic en **Nuevo**.
8. En el campo **Tipo de instalación**, escriba el nombre del tipo de instalación bancaria relacionado con el contrato de instalaciones bancarias.
9. En el campo **Descripción**, escriba un valor.
10. En el campo **Grupo de instalaciones**, haga clic en el botón desplegable para abrir la búsqueda.
11. En la lista, busque y seleccione el registro deseado.
12. En la lista, haga clic en el vínculo de la fila seleccionada.
13. En el campo **Naturaleza de la instalación**, seleccione una opción.
14. Haga clic en **Guardar**.
15. Cierre la página.

## <a name="bank-posting-profile"></a>Perfil de contabilización de banco
1. Vaya a **Gestión de efectivo y bancos > Configuración > Perfil de registro de documentos bancarios**.
2. Haga clic en **Nuevo**.
3. En el campo **Número de grupo/cuenta**, haga clic en el botón desplegable para abrir la búsqueda.
4. En la lista, busque y seleccione el registro deseado.
5. En la lista, haga clic en el vínculo de la fila seleccionada.
6. En el campo **Liquidar cuenta**, seleccione la cuenta principal para realizar el pago.
7. En el campo **Cuenta de gastos**, seleccione la cuenta de las transacciones de gastos.
8. En el campo **Cuenta de márgenes**, seleccione la cuenta para la transacción de márgenes.
9. En el campo **Cuenta de liquidación**, seleccione la cuenta de liquidación para la transacción de la carta de garantía. 
10. Haga clic en **Guardar**.
11. Cierre la página.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
