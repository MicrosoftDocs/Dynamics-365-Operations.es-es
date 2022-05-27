---
title: Crear y enviar un flujo de trabajo de presupuesto de proyecto
description: Este procedimiento muestra cómo crear y mostrar el presupuesto para un proyecto.
author: GalynaFedorova
ms.date: 11/22/2021
ms.topic: article
ms.search.form: ProjProjectsListPage, ProjTable, ProjBudget, WorkflowSubmitDialog
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: gfedorova
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: e554fb578371f52f665ef348d6fa81fd27196a9e
ms.sourcegitcommit: 9166e531ae5773f5bc3bd02501b67331cf216da4
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/03/2022
ms.locfileid: "8671040"
---
# <a name="create-and-submit-a-project-budget-workflow"></a>Crear y enviar un flujo de trabajo de presupuesto de proyecto

[!include [banner](../../includes/banner.md)]

Cuando crea un presupuesto de proyecto, puede especificar los ingresos y los costes calculados para el proyecto y usar los valores para controlar las transacciones de proyecto reales. El presupuesto de proyecto requiere que todos los presupuestos y revisiones originales pasen por un flujo de trabajo del proyecto para su aprobación. El flujo de trabajo incrementa su control sobre el presupuesto y crea un registro de historial de cambios. Después de [crear un proyecto](/dynamicsax-2012/appuser-itpro/create-a-project), utilice este procedimiento para crear y enviar el presupuesto.

1. Vaya a **Módulos** > **Gestión de proyectos y contabilidad** > **Proyectos** > **Todos los proyectos**.
1. En la lista de proyectos, seleccione el proyecto.
1. En la página de detalles del proyecto, seleccione la pestaña **Plan**.
1. En el grupo **Presupuesto**, seleccione **Presupuesto del proyecto**.
1. En la ficha desplegable **General**, especifique la información siguiente:
   - En el cuadro **Descripción**, escriba un valor.
   - Seleccione la opción para **Presupuesto original**.
   - Seleccione la opción para **Presupuesto restante**.
1. Ampliar la ficha desplegable **Costes** y seleccione **Nuevo**. Luego, realice los siguientes ajustes:
   - Seleccione una opción para **Tipo de transacción**.
   - Seleccione una **Categoría** apropiada.
   - Ingrese un valor en **Presupuesto original**.
1. Amplíe la ficha desplegable **Ingresos** y seleccione **Nuevo**. Luego, realice los siguientes ajustes:
   - Seleccione una opción para **Tipo de transacción**.
   - Seleccione una **Categoría**.
   - Ingrese un valor para **Presupuesto original**.
1. Seleccione **Guardar**.
1. Seleccione **Flujo de trabajo \> Enviar**.
1. En la página **Revisar flujo de trabajo del presupuesto original: enviar**, ingrese un **Comentario** y seleccione **Enviar**.
