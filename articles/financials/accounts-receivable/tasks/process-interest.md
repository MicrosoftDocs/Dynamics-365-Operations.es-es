---
title: Procesar interés
description: Este procedimiento muestra cómo crear, imprimir y registrar notas de interés.
author: ShivamPandey-msft
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CustPosting, SysQueryForm, CustInterestNote, SrsReportViewerForm
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: c5652a38684061914f895d7f8b82999c9840fd63
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/15/2019
ms.locfileid: "1549615"
---
# <a name="process-interest"></a>Procesar interés

[!include [task guide banner](../../includes/task-guide-banner.md)]

Este procedimiento muestra cómo crear, imprimir y registrar notas de interés. Esta tarea usa la empresa de demostración USMF.


## <a name="set-up-interest-on-the-posting-profile"></a>Configuración del interés en el perfil de contabilización
1. Vaya a Crédito y cobros > Configuración > Perfiles de contabilización del cliente.
2. Haga clic en Editar.
    * Seleccione un código de interés en la lista desplegable. Si no desea que se calcule el interés para las transacciones que usan este perfil de contabilización, deje el campo en blanco.  
    * La ficha Restricciones de tablas le permite cambiar la forma en la que se procesa el interés. Si este campo está establecido en Sí, se calculará el interés para este perfil de contabilización.  

## <a name="calculate-interest"></a>Calcular interés
1. Vaya a Crédito y cobros > Interés > Crear notas de interés.
    * Debe seleccionar los tipos de transacción para los que desee calcular el interés. Todas las transacciones abiertas de estos tipos se incluirán en el cálculo.  
    * Si selecciona Interés, calculará el interés sobre el interés. Es posible que desee comprobar las normas que rigen el cálculo de interés sobre el interés antes de incluir estas transacciones.  
    * El interés se calculará a partir de esta fecha hasta "Fecha final". Si no se especifica una "Fecha final", todas las notas de interés no registradas se cancelarán, y el interés se volverá a calcular a partir de la fecha de transacción.  
2. Especifique la fecha de la nota de interés.
    * Hay tres opciones para el perfil de contabilización: Cuenta: se usa el perfil de contabilización asignado a la cuenta del cliente para cada nota de interés.   Seleccionar: se usa el perfil de contabilización que seleccione en el campo Perfil de contabilización.   Transacción: se usa el perfil de contabilización individual de las transacciones en las que se calcula el interés para cada nota de interés. Las transacciones que no tengan un perfil de contabilización asignado usarán el perfil de registro que se especifica en el área Impuestos y contabilidad del formulario Parámetros de clientes.  
    * Seleccione un perfil de contabilización aquí si ha cambiado "Utilizar el perfil de contabilización desde" a "Seleccionar".  
3. Expanda o contraiga la sección Registros que incluir.
4. Haga clic en Filtro.
5. En el campo Criterios, especifique un Id. de cliente. Por ejemplo, escriba "US-001".
6. Haga clic en Aceptar
7. Haga clic en Aceptar

## <a name="print-interest-notes"></a>Imprimir notas de interés
1. Vaya a Crédito y cobros > Interés > Revisar y procesar notas de interés.
2. En el campo Estado, seleccione Creado.
3. En el campo Impreso, seleccione No se ha impreso.
4. Haga clic en Imprimir.
5. Expanda o contraiga la sección Registros que incluir.
6. Haga clic en Aceptar
7. Cierre la página.

## <a name="post-the-interest-note"></a>Registro de la nota de interés
1. Seleccione una nota de interés lista para registrar (estado Creado).
2. Haga clic en Registrar.
3. Especifique la fecha de registro para la nota de interés.
    * Seleccione Sí para crear una transacción de contabilidad general para cada nota de interés.     Si no selecciona Sí, el interés de todas las notas de interés para el cliente se acumula y se registra en la contabilidad general en una transacción.  
4. Expanda o contraiga la sección Registros que incluir.
5. Haga clic en Aceptar
6. En el campo Estado, seleccione Registrada.

