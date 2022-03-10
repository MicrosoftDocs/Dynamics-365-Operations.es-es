---
title: Área de trabajo de planificación de la carga
description: Este tema describe cómo trabajar con el banco de trabajo de creación de carga.
author: Henrikan
ms.date: 10/30/2020
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: TMSLoadBuildWorkbench,TMSLoadBuildTemplateCreate,TMSLoadBuildStrategy,TMSLoadBuildTemplateApply
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Distribution
ms.author: henrikan
ms.search.validFrom: 2020-10-30
ms.dyn365.ops.version: 10.0.15
ms.openlocfilehash: 306ca4f77d9c1d4879d750992e51c8b83917839e
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/29/2021
ms.locfileid: "7574866"
---
# <a name="load-building-workbench"></a>Área de trabajo de planificación de la carga

[!include [banner](../../includes/banner.md)]

El banco de trabajo de construcción de carga le permite aplicar estrategias de construcción de carga cuando crea cargas.

## <a name="create-a-load-building-strategy"></a>Crear una estrategia de creación de carga

Utiliza estrategias de construcción de carga para generar cargas automáticamente. Esta capacidad puede resultar beneficiosa en las siguientes situaciones:

- Si envía regularmente un conjunto específico de productos, las estrategias de carga le ayudarán a ahorrar tiempo, ya que no tiene que generar la misma carga cada vez.
- Si desea evitar cargas medio llenas para maximizar la eficiencia, las estrategias de carga pueden ayudar a llenar cada carga tanto como sea posible.

Una clase de estrategia de construcción de carga que se denomina `TMSLoadBuildingVolumeStrategy` proporciona una estrategia de construcción de carga que se denomina *Estrategia de construcción de carga basada en volumen*. Esta estrategia le permite usar los valores máximos que se especifican para la altura y el peso de la plantilla de carga o bien, puede reemplazar los ajustes especificando valores nuevos. Esta estrategia es la única estrategia que se incluye de fábrica. (Sin embargo, es posible que tenga algunas estrategias personalizadas).

Para usar la estrategia incluida *Estrategia de construcción de carga basada en volumen*, selecciónela en el campo **Estrategia de construcción de carga** en la página **Banco de trabajo de construcción de carga** (**Gestión de transporte &gt; Planificación &gt; Banco de trabajo de construcción de carga**).

Para crear una estrategia de creación de carga, siga estos pasos.

1. Ir **Gestión de transporte &gt; Preparar &gt; Creación de carga &gt; Estrategias de construcción de carga**.
1. En el panel de acciones, seleccione **Generar lista de clases** para asegurarse de tener las últimas versiones de todas las clases disponibles.
1. En el panel de acciones, haga clic en **Nueva**.
1. Ingrese un nombre único para la estrategia, seleccione la clase de estrategia de construcción de carga para ella e ingrese una descripción.
1. En el panel Acciones, seleccione **Guardar**.
1. En el panel Acciones, seleccione **Parámetros**.
1. Sobre la página **Parámetros de estrategia de construcción de carga**, seleccione **Capacidad de volumen** en la lista y luego, en el campo **Valor**, ingrese el porcentaje de la capacidad de volumen total de la carga que se debe aplicar para la nueva estrategia de construcción de carga.
1. Seleccione **Capacidad de volumen** en la lista y luego, en el campo **Valor**, ingrese el porcentaje de la capacidad de peso total de la carga que se debe aplicar para la nueva estrategia de construcción de carga.
1. Cierre la página **Parámetros de estrategia de construcción de carga**.
1. Cierre la página **Estrategias de construcción de carga**.

Ahora puede asignar la estrategia de creación de carga a una plantilla de creación de carga. Alternativamente, puede usarlo directamente en el banco de trabajo de planificación de carga.

## <a name="use-a-load-building-strategy-in-the-load-building-workbench"></a>Utilice una estrategia de creación de carga en el banco de trabajo de creación de carga

1. Vaya a **Administración de transporte &gt; Planificación &gt; Área de trabajo de planificación de la carga**.
1. Siga uno de estos pasos:

    - Seleccione una estrategia en el campo **Estrategia de construcción de carga**.
    - Si ha definido una plantilla de creación de carga y le ha asignado la estrategia de creación de carga, en el Panel de acciones, en la pesaña **Administrar plantillas**, seleccione **Aplicar plantilla**. Entonces, en el cuadro de diálogo desplegable **Aplicar plantilla de construcción de carga**, seleccione una plantilla en el campo **Cargar el nombre de la plantilla de construcción**.

1. En la ficha desplegable **Secuencia de carga de plantillas**, seleccione una o más [plantillas de carga](load-template.md). El banco de trabajo intentará encajar la carga en este tipo de contenedores, en la secuencia que se especifica aquí. Por lo general, debe colocar los contenedores más pequeños al principio de la lista para asegurarse de que se seleccione primero el contenedor más pequeño posible.
1. En el panel de acciones, seleccione **Proponer cargas**.
1. Revise las cargas propuestas y las líneas de carga propuestas.
1. En el panel de acciones, seleccione **Crear cargas** para crear cargas que se basan en las líneas del documento de origen en la ficha desplegable **Líneas de carga propuestas**.
1. Cierre la página **Workbench de construcción de carga**.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]