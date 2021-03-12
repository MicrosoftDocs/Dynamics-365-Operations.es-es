---
title: Cerrar el ejercicio
description: Este procedimiento describe el proceso de cierre de fin de año que transfiere los saldos a un nuevo ejercicio.
author: aprilolson
manager: AnnBe
ms.date: 07/11/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: LedgerParameters, LedgerFiscalCloseGroup, LedgerFiscalCloseAddLedger, SysLookupMultiSelectGrid, LedgerFiscalCloseRunGroup
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: b82cc7e4077a1bd50eab30f234c2f63c79e81d84
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/15/2021
ms.locfileid: "4994699"
---
# <a name="close-the-fiscal-year"></a>Cerrar el ejercicio

[!include [banner](../../includes/banner.md)]

Este procedimiento describe el proceso de cierre de fin de año que transfiere los saldos a un nuevo ejercicio.


## <a name="validate-year-end-close-parameters"></a>Valide los parámetros de cierre de fin de año
1. Vaya a **Panel de exploración > Módulos > Contabilidad general > Configuración de contabilidad > Parámetros de contabilidad general**.
2. Expanda la sección **Cierre del ejercicio**.
3. Seleccione "Sí" o "No" para la opción **Eliminar el asiento de cierre y apertura y generar uno nuevo**.
    
    Si ya ha cerrado el año fiscal y el cierre de fin de año se ejecuta de nuevo, este valor es importante. Si se establece en Sí, el asiento del cierre de fin de año anterior se borrará y se creará un nuevo asiento para todas las cuentas con saldos iniciales. Si se establece en No, se conservará el asiento anterior y solo se creará un nuevo asiento para ajustar las entradas que se han registrado después del último cierre de fin de año.

4. Seleccione "Sí" o "No" para la opción **Crear el asiento de cierre al lanzar el proceso de transacciones de cierre / apertura**.

    Si se establece en Sí, se crean dos transacciones. Un asiento se crea en el ejercicio que se cierra para llevar los saldos de las cuentas contables de Pérdidas y Ganancias a cero y un segundo asiento se crea en el ejercicio siguiente para los saldos iniciales. Si se establece en No, se crea un asiento único en el ejercicio siguiente para saldos iniciales.  

5. Seleccione "Sí" o "No" para la opción **Establecer el estado del ejercicio en Cerrado de forma permanente**.

    Si se establece en Sí, el estado del ejercicio se fijará en Cerrado de forma permanente.  Debido a que un año cerrado de forma permanente no se puede volver a abrir, ser recomienda establecer esta opción en No.  

6. Seleccione "Sí" o "No" para la opción **Decidir si completar un número de asiento durante el cierre de fin de año**.

    Si se establece en Sí, deberá especificarse un número de asiento manualmente durante el proceso de cierre de fin de año. No se usa ninguna secuencia numérica para generar dicho número de asiento. Se recomienda elegir Sí.  

7. Cierre la página.
8. Vaya a **Contabilidad general > Cierre de período > Cierre de fin de año**.
9. Haga clic en **Nuevo** para crear una plantilla de cierre de fin de año.

    Se puede crear una plantilla para un grupo de entidades jurídicas para ejecutar el cierre de fin de año. Esta plantilla se puede volver a usar un año tras otro.  

10. En el campo **Nombre del grupo**, especifique un nombre de plantilla de cierre de fin de año.
11. En el campo **Calendario fiscal**, seleccione el ejercicio para el que se va a crear la plantilla.

    Solo las entidades jurídicas que utilizan el mismo ejercicio se pueden agrupar en la plantilla de cierre de fin de año. Esto se debe a que el cierre de fin de año se hace seleccionando un ejercicio, no una fecha.  

12. En el **panel de acciones**, haga clic en **Guardar**.
13. En la sección **Entidades jurídicas**, haga clic en **Agregar** para seleccionar las entidades jurídicas para esta plantilla.
    
    Las entidades jurídicas se pueden agregar al seleccionar las entidades jurídicas o seleccionando una jerarquía organizativa.  Sólo se agregan las entidades jurídicas con la jerarquía organizativa con el mismo calendario fiscal seleccionado.  

14. Seleccione las entidades jurídicas o la jerarquía organizativa.
15. Haga clic en **Aceptar**.
16. Seleccione "Sí" o "No" en **Transferir dimensiones de balance de situación**.

    Es una práctica recomendada establecer esta opción en Sí para las cuentas de balance de situación. Esto mantendrá las dimensiones financieras de las transacciones registradas al crear los saldos iniciales para las cuentas de balance de situación. Para las cuentas de pérdidas y ganancias, puede seleccionar mantener las dimensiones financieras (Cerrar todo) cuando los saldos se mueven a las ganancias retenidas o puede seleccionar que las dimensiones financieras se reemplacen con un valor de la dimensión diferente (Cerrar uno). Si elige Cerrar uno, puede definir un valor de dimensión concreto para cada dimensión o incluso optar por dejarlo en blanco.  

17. Haga clic en **Guardar**.
18. Inicie el cierre de fin de año eligiendo **Ejecutar cierre fiscal** en el **panel de acciones**. El cierre de fin de año se ejecutará para la plantilla seleccionada.  
19. Seleccione todas o un subconjunto de entidades jurídicas de la plantilla para el que ejecutar el cierre de fin de año.

    En la primera ejecución del cierre de fin de año, para obtener los saldos iniciales la mayoría de las organizaciones pueden elegir ejecutar el cierre de fin de año para todas las entidades jurídicas dentro de la plantilla. Si después ajusta entradas, puede elegir ejecutar el cierre de fin de año para solo las entidades jurídicas que requieren ajustes.  

20. Haga clic en **Aceptar**.
21. Seleccione el ejercicio para el que ejecutar el cierre de fin de año.
22. En el campo **Asiento**, escriba un valor. Es una práctica recomendada incluir el ejercicio en el número de asiento para facilitar la búsqueda del asiento de cierre de fin de año que se crea.  
23. El cierre de fin de año se ejecuta en lote de forma predeterminada. Es una práctica recomendada para los procesos de larga ejecución que se ejecuten en modo de lotes. Suele ser uno de estos procesos y ese es el motivo por el que el valor predeterminado es utilizar el modo de lotes.  
24. Haga clic en **Aceptar**.

