--- 
title: Procesar cartas de cobro
description: "Este procedimiento muestra cómo crear, imprimir y registrar cartas de cobro."
author: ShivamPandey-msft
manager: AnnBe
ms.date: 10/23/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Operations
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: dc837ea6513992a5f94e48baa366e279df297866
ms.contentlocale: es-es
ms.lasthandoff: 09/29/2017

---
# <a name="process-collection-letters"></a>Procesar cartas de cobro

[!include [task guide banner](../../includes/task-guide-banner.md)]

Este procedimiento muestra cómo crear, imprimir y registrar cartas de cobro. Esta tarea usa la empresa de demostración USMF.


## <a name="set-up-a-collection-letter-sequence-on-the-posting-profile"></a>Configurar una secuencia de cartas de cobro en el perfil de registro
1. Vaya a Crédito y cobros > Configuración > Perfiles de contabilización del cliente.
2. Haga clic en Editar.
    * Seleccione una secuencia de cartas de cobro en la lista desplegable. Si no desea generar cartas de cobro para las transacciones que usan este perfil de contabilización, deje el campo en blanco.  
    * La ficha Restricciones de tablas le permite cambiar la forma en la que se procesan las cartas de cobro. Si este campo está establecido en Sí, se crearán las cartas de cobro para este perfil de contabilización.  
3. Cierre la página.

## <a name="create-collection-letters"></a>Crear cartas de cobro
1. Vaya a Crédito y cobros > Carta de cobro > Crear cartas de cobro.
    * Debe seleccionar los tipos de transacción para los que desee cobrar cartas. Todas las transacciones abiertas de estos tipos se incluirán en el cálculo.  
2. En el campo Carta de cobro, seleccione una opción.
3. Escriba la fecha de la carta de cobro.
    * Hay dos opciones para el perfil de contabilización: Cuenta: se usa el perfil de contabilización asignado a la cuenta del cliente para cada nota de interés.   Seleccionar: se usa el perfil de contabilización que seleccione en el campo Perfil de contabilización.  
    * Seleccione un perfil de contabilización si ha cambiado "Utilizar el perfil de contabilización desde" a "Seleccionar".  
4. Expanda la sección Registros que incluir.
5. Haga clic en Filtro.
6. En el campo Criterios, escriba una id. de cliente. Por ejemplo, escriba "US-001".
7. Haga clic en Aceptar
8. Haga clic en Aceptar

## <a name="print-collection-letters"></a>Imprimir cartas de cobro
1. Vaya a Crédito y cobros > Carta de cobro > Revisar y procesar cartas de cobro.
2. En el campo Estado, seleccione Creado.
3. En el campo Impreso, seleccione No se ha impreso.
4. Haga clic en Imprimir.
5. Haga clic en Nota de la carta de cobro.
6. Expanda la sección Registros que incluir.
7. Especificar la fecha límite para los registros
8. Haga clic en Aceptar para imprimir la carta de cobro.

## <a name="post-the-collection-letter"></a>Registrar la carta de cobro
1. Haga clic en Registrar.
2. Escriba la fecha de registro para la carta de cobro.
3. Expanda la sección Registros que incluir.
4. Haga clic en Aceptar
5. En el campo Estado, seleccione Registrada.
6. En el campo Impreso, seleccione una opción.


