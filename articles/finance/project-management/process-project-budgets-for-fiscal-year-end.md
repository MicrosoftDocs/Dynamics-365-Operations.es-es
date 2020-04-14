---
title: Transferir presupuestos de proyecto al final del ejercicio
description: Este artículo proporciona información sobre cómo transferir los importes de presupuesto restantes a años futuros y crear detalles de registro de presupuesto.
author: RadhikaRS
manager: AnnBe
ms.date: 03/23/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Service industries
ms.author: v-radsh
ms.dyn365.ops.version: 7
ms.search.validFrom: 2019-01-15
ms.openlocfilehash: 41e985825a24de2d6510938cf3d61715c35f9939
ms.sourcegitcommit: 2ea5ff784500d5be9203e9a1560eabd4fea46f4e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/27/2020
ms.locfileid: "3172339"
---
# <a name="transfer-project-budgets-at-fiscal-year-end"></a>Transferir presupuestos de proyecto al final del ejercicio

[!include [banner](../includes/banner.md)]

Cuando trabaje en un proyecto de varios años, es posible que tenga un presupuesto restante al final del año fiscal. Puede transferir los importes presupuestarios restantes a un año futuro y crear los detalles de registro presupuestarios para las cantidades en las cuentas asociadas de la contabilidad general. Antes de transferir las cantidades restantes, revise y analice las cantidades restantes del presupuesto.

## <a name="review-and-analyze-remaining-budget-amounts"></a>Revisión y análisis de importes presupuestarios restantes

Siga los pasos que se describen a continuación para revisar los importes presupuestarios de fin de año de los proyectos, pero no transferirlos.

1. Vaya a **Gestión de proyectos y contabilidad** > **Periódico** > **Presupuestos** > **Transferir presupuestos**. 
2. En la página **Proceso de traspaso del presupuesto del proyecto**, en la pestaña **Opciones de fin de año**, verifique que **Transferir los importes restantes del presupuesto del proyecto** no está habilitado.
3. En la pestaña **Parámetros**, en el campo **Año de presupuesto del proyecto**, seleccione el ejercicio para el que quiere ver la cantidad restante del presupuesto. 
4. En el campo **Ejercicio de apertura**, seleccione el ejercicio para el que quiere ver la cantidad de presupuesto restante. 
5. En el campo **Del modelo de pronóstico**, seleccione **Presupuesto restante**. 
6. Para incluir proyectos que cumplan los criterios seleccionados y no tengan un presupuesto restante, seleccione **Mostrar cero restante**.  
7. En la pestaña **Seleccionar presupuestos**, seleccione **Recuperar todos los presupuestos** para cargar todos los presupuestos que coincidan con los criterios seleccionados y luego seleccione **Proceso**. 
8. Para diseñar una consulta de base de datos que cargue un conjunto específico de presupuestos en el panel, seleccione **Recuperar presupuestos seleccionados**.

Para obtener más información sobre una línea específica en el panel, seleccione la línea y luego seleccione **Ver detalles del presupuesto** o **Ver cuentas**.

## <a name="carry-forward-remaining-budget-amounts"></a>Transferir importes restantes del presupuesto 

Al procesar los importes presupuestarios restantes, puede decidir crear transacciones de contabilidad general para los importes que se transfieren. Para crear transacciones de contabilidad general, complete los pasos en la sección, [Transferir importes del presupuesto y crear transacciones en la contabilidad general](#carry-forward). 

> [!NOTE]
> Los importes presupuestarios que se transfieren pasan al modelo de previsión seleccionado en la página **Modelos de previsión** como modelo de previsión de transferencia en el formulario .  

## <a name="carry-forward-budget-amounts-and-create-general-ledger-transactions"></a><a name="carry-forward"></a>Transferencia de importes presupuestarios y crear transacciones de contabilidad general

1.  Seleccione **Gestión de proyectos y contabilidad** > **Periódico** > **Presupuestos** > **Transferir presupuestos**. 
2. En la página **Proceso de traspaso del presupuesto del proyecto**, seleccione **Fin de año** y luego habilite **Transferir los importes restantes del presupuesto del proyecto** y **Crear entradas de registro de presupuesto en la contabilidad general**. 
3. En la pestaña **Parámetros**, en el grupo de campos **Parámetros del proyecto**, seleccione lo siguiente:

   - **Año de proyecto de presupuesto**: seleccione el inicio del ejercicio cuyos importes presupuestarios restantes desee ver. 
   - **Ganancias y pérdidas**: crear transacciones de pérdidas y ganancias en la contabilidad general. 
   -  **WIP**: crear transacciones de trabajo en curso (WIP) en la contabilidad general.
   -  **Nómina**: crea transacciones de asignación de nómina en la contabilidad general. 

5. En el grupo de campos **Contabilidad general**, proporcione la siguiente información: 

   - En el campo **Ejercicio de apertura**, seleccione el ejercicio al que desee transferir importes presupuestarios restantes para los proyectos. El valor predeterminado es un año después del valor del campo **Proyecto de de año presupuestario**.
   -  En el campo, **Transferir período** seleccione el período en el que desee crear los detalles de registro presupuestarios en la contabilidad general. Normalmente, se trata del primer período del ejercicio de apertura.

6. En el grupo de campos **Copiar de/a**, proporcione la siguiente información:

   - En el campo **De modelo de previsión**, seleccione el modelo de previsión de presupuesto de proyecto asociado a los importes presupuestarios restantes que desee transferir. 
   - En el campo **A modelo presupuestario de libro mayor** seleccione el modelo presupuestario asociado a los importes presupuestarios que desee transferir a la contabilidad general. 
   -  Seleccione **Transferir divisa de ventas** para usar la divisa de ventas del rpyecto para las transacciones de la contabilidad general que se crean cuando transfiera las cantidades del presupuesto para los proyectos. Cuando la opción no está seleccionada, las transacciones usan la divisa de contabilidad. 
   -  Seleccione **Mostrar cero restante** para incluir proyectos que no tienen importes de presupuesto restantes, pero cumplen con los otros criterios que seleccionó en los proyectos que se muestran en el panel inferior.

7. En la pestaña **Seleccionar presupuestos**, seleccione **Recuperar todos los presupuestos** para cargar todos los presupuestos que coincidan con los criterios que ha seleccionado. Si prefiere diseñar una consulta de base de datos que cargue un conjunto específico de presupuestos de proyecto en el panel, seleccione **Recuperar presupuestos seleccionados**.
8. Active la opción situada al principio de la línea de cada proyecto que desee procesar.

    > [!TIP]
    > Para seleccionar todos o la mayoría de los proyectos, seleccione la marca de verificación en la esquina superior izquierda superior. Para excluir el procesamiento de cualquier proyecto, borre la marca de verificación para ese proyecto.

9. Para transferir los importes presupuestarios restantes de los proyectos seleccionados al ejercicio seleccionado y crear los detalles de registro presupuestarios en la contabilidad general, seleccione **Procesar**.

## <a name="carry-forward-budget-amounts-without-creating-general-ledger-transactions"></a>Transferencia de importes presupuestarios sin crear transacciones de contabilidad general

1. Vaya a **Gestión de proyectos y contabilidad** > **Periódico** > **Presupuestos** > **Transferir presupuestos**.
2. En la página **Proceso de traspaso del presupuesto del proyecto**, en el campo **Opciones de fin de año**, seleccione **Transferir los importes restantes del presupuesto del proyecto**.
3. En el grupò **Parámetros**, en el campo **Año de presupuesto del proyecto**, seleccione el ejercicio para el que quiere ver las cantidades restantes del presupuesto.
4. En el grupo **Copiar de/a**, proporcione la siguiente información:

   - En el campo **De modelo de previsión**, seleccione el modelo de previsión de presupuesto de proyecto asociado a los importes presupuestarios restantes que desee transferir. 
   - Seleccione **Mostrar cero restante** para incluir proyectos que no tengan cantidades de presupuesto restantes pero cumplen el resto de criterios que ha seleccionado.
   - En el grupo **Seleccionar presupuestos**, seleccione **Recuperar todos los presupuestos** para cargar todos los presupuestos que coincidan con los criterios que ha seleccionado. Para diseñar una consulta de base de datos que cargue un conjunto específico de presupuestos de proyecto en el panel, seleccione **Recuperar presupuestos seleccionados**.

5. Active la opción situada al principio de la línea de cada proyecto que desee procesar. 
6. Seleccione **Procesar** para transferir los importes presupuestarios restantes de los proyectos seleccionados al ejercicio seleccionado.

