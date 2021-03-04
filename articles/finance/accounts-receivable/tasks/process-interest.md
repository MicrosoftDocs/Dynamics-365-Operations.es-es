---
title: Procesar interés
description: Este procedimiento muestra cómo crear, imprimir y registrar notas de interés.
author: ShivamPandey-msft
manager: AnnBe
ms.date: 08/08/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CustPosting, SysQueryForm, CustInterestNote, SrsReportViewerForm
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 093fbd23f9fcaf62db9988a98a94b8cebf582768
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/13/2020
ms.locfileid: "4447626"
---
# <a name="process-interest"></a>Procesar interés

[!include [banner](../../includes/banner.md)]

Este procedimiento muestra cómo crear, imprimir y registrar notas de interés. Esta tarea usa la empresa de demostración USMF.


## <a name="set-up-interest-on-the-posting-profile"></a>Configuración del interés en el perfil de contabilización
1. En el **Panel de navegación**, vaya a **Módulos > Crédito y cobros > Configuración > Perfiles de contabilización del cliente**.
2. Haga clic en **Editar**.
3. En la **Ficha desplegable Configuración**, en el campo **Código de interés**, seleccione un código de interés de la lista desplegable. Si no desea que se calcule el interés para las transacciones que usan este perfil de contabilización, deje el campo en blanco. La ficha desplegable **Restricciones de tablas** le permite cambiar la forma en la que se procesa el interés. Si este campo está establecido en Sí, se calculará el interés para este perfil de contabilización.  

## <a name="calculate-interest"></a>Calcular interés
1. En el **Panel de navegación**, vaya a **Módulos > Crédito y cobros > Interés > Crear notas de interés**.
2. Debe seleccionar los tipos de transacción para los que desee calcular el interés. Todas las transacciones abiertas de estos tipos se incluirán en el cálculo.  
3. Si establece **Interés** en "Sí", calculará el interés sobre el interés. Es posible que desee comprobar las normas que rigen el cálculo de interés sobre el interés antes de incluir estas transacciones.  
4. En el campo **Fecha inicial**, especifique una fecha desde la que se calculará el interés. Si no se especifica una **Fecha inicial**, todas las notas de interés no registradas se cancelarán, y el interés se volverá a calcular a partir de la fecha de transacción.
5. En el campo **Fecha final**, especifique una fecha hasta la que se calculará el interés.
6. En el campo **Utilizar el perfil de contabilización desde**, seleccione una opción. Existen tres opciones de perfil de registro:
    - Cuenta: use el perfil de contabilización asignado a la cuenta de cliente para cada nota de interés. 
    - Seleccionar: se usa el perfil de contabilización que seleccione en el campo Perfil de contabilización.
    - Transacción: se usa el perfil de contabilización individual de las transacciones en las que se calcula el interés para cada nota de interés. Las transacciones que no tengan un perfil de contabilización asignado usarán el perfil de registro que se especifica en el área Impuestos y contabilidad del formulario Parámetros de clientes.  
7. Expanda la ficha desplegable **Registros que incluir**.
8. Haga clic en **Filtro.**
9. En el campo **Criterios**, especifique un id. de cliente. Por ejemplo, escriba "US-001".
6. Haga clic en **Aceptar**.
7. Haga clic en **Aceptar**.

## <a name="print-interest-notes"></a>Imprimir notas de interés
1. En el **Panel de navegación**, vaya a **Módulos > Crédito y cobros > Interés > Revisar y procesar notas de interés**.
2. En el campo **Estado**, seleccione "Creado".
3. En el campo **Impreso**, seleccione "No se ha impreso".
4. Haga clic en **Imprimir**.
5. Expanda la ficha desplegable **Registros que incluir**.
6. Haga clic en **Aceptar**.
7. Cierre la página.

## <a name="post-the-interest-note"></a>Registro de la nota de interés
1. Seleccione una nota de interés lista para registrar (estado Creado).
2. Haga clic en **Registrar**.
3. Especifique la fecha de registro para la nota de interés. Seleccione Sí para crear una transacción de contabilidad general para cada nota de interés. Si no selecciona Sí, el interés de todas las notas de interés para el cliente se acumula y se registra en la contabilidad general en una transacción.  
4. Expanda la ficha desplegable **Registros que incluir**.
5. Haga clic en **Aceptar**.
6. En el campo **Estado**, seleccione "Registrado".



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]