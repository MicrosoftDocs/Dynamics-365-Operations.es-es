---
title: Crear modelos de previsión para presupuestos de proyectos
description: Este tema describe cómo crear un modelo de previsión para los presupuestos restantes.
author: RadhikaRS
manager: AnnBe
ms.date: 04/24/2020
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
ms.openlocfilehash: 07e540f23a668b40a54906a67d87552fe991825a
ms.sourcegitcommit: 5de75c61c33e57c813944f1ab6100aceb020d432
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/29/2020
ms.locfileid: "3321788"
---
# <a name="create-forecast-models-for-project-budgets"></a>Crear modelos de previsión para presupuestos de proyectos 

[!include [banner](../includes/banner.md)]

Este tema describe cómo crear un modelo de previsión para los presupuestos restantes. Un proyecto sujeto a control presupuestario usa dos tipos de presupuesto: original y restante. Al crear un presupuesto de proyecto, debe especificar los modelos de previsión del presupuesto original y restante que se crearon en la página **Modelos de previsión**. Los presupuestos de proyecto basados en los modelos especificados se crean al comprometer el presupuesto de proyecto.

> [!NOTE]
> Un modelo de previsión que se use para el control presupuestario no puede tener un submodelo ni usarse como tal.

1. Seleccione **Gestión de proyectos y contabilidad** > **Configurar** > **Previsiones**  > **Modelos de previsión**.
2. Seleccione **Nuevo** para crear un nuevo modelo de previsión y, a continuación, especifique un número de id. de modelo y un nombre para el nuevo modelo. 
3. Seleccione la opción **Detenido** al valor **Sí** para evitar cualquier cambio en las líneas de previsión del modelo de previsión. 
4. Si las líneas de previsión asociadas al modelo generaran previsiones de flujo de efectivo en la contabilidad general, establezca **Incluir en previsiones de flujo de efectivo** en **Sí**. 
5. Para usar la fecha del proyecto como la fecha de la factura, establezca **Fecha de factura prevista** en **Sí**. 
6. En el campo **Tipo de presupuesto**, seleccione uno de los siguientes tipos de modelo:

   - **Presupuesto original**: use los importes de presupuesto original comprometidos al crear y aprobar el presupuesto inicial.
   - **Presupuesto restante**: use los importes de presupuesto restantes durante la vida del proyecto. Los saldos de este modelo de previsión se reducen con las transacciones reales y aumentan o disminuyen con las revisiones presupuestarias.
   - **Transferir**: use los importes de presupuesto a transferir para el proyecto. La transferencia es un proceso opcional que se puede ejecutar para transferir importes de presupuesto sin usar de un ejercicio a otro.

7. Configure las siguientes opciones según sea necesario:

   - Para usar la fecha del proyecto como la fecha de la factura, establezca **Fecha de factura prevista** en Sí.
   - Habilite **Previsión con WIP** para pronosticar en función del trabajo en curso (WIP) y luego seleccione el tipo de WIP. 
   - Puede mantener el valor predeterminado **Tipo de presupuesto** como **Ninguno** o introducir un nuevo tipo. El tipo de presupuesto no se puede cambiar después de cambiar un registro.     
    > [!NOTE]
    > Si cambia el tipo de presupuesto predeterminado, todas las demás opciones no estarán disponibles para las actualizaciones y no podrá reutilizar este modelo de previsión. 
   


 

