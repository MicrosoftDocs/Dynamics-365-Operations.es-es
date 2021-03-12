---
title: Cargar plantillas
description: Este tema describe cómo configurar plantillas de carga y cómo asociar una plantilla de carga a una nueva carga.
author: Henrikan
manager: ''
ms.date: 10/30/2020
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSLoadTemplate
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Distribution
ms.author: henrikan
ms.search.validFrom: 2020-10-30
ms.dyn365.ops.version: 10.0.15
ms.openlocfilehash: 0a4070a1dd5d53bb502ba2ab0c91dbdc90ded34d
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/15/2021
ms.locfileid: "5005061"
---
# <a name="load-templates"></a>Cargar plantillas

Cuando crea una nueva carga, puede asignar una plantilla de carga. La plantilla de carga contiene información sobre el equipo y sobre medidas como la altura, el ancho, la profundidad y el volumen de la carga.

Este tema describe cómo configurar plantillas de carga y cómo asociar una plantilla de carga a una nueva carga.

## <a name="set-up-a-load-template"></a>Configurar una plantilla de carga

1. Ir **Gestión de transporte \> Preparar \> Creación de carga \> Plantilla de carga**.
1. En el panel de acciones, seleccione **Nuevo** para agregar una nueva plantilla o **Editar** para editar una plantilla existente.
1. En la fila de la plantilla nueva o existente, configure los siguientes campos:

    - **ID de plantilla de carga** – Introduzca un identificador único para la plantilla de carga.
    - **Equipo** - Seleccione el equipo que se debe utilizar para enviar la carga.
    - **Altura de carga**, **Ancho de carga** y **Profundidad de carga** - Ingrese las dimensiones de la carga.
    - **Max. volumen de carga permitido** y **Max. peso de carga permitido** - Introduzca el volumen y el peso máximos permitidos de la carga.
    - **Peso bruto máximo permitido** - Ingrese el peso bruto máximo permitido de la carga. Un peso bruto de la carga incluye la tara actual y el peso de carga máximo.
    - **Número máximo de bultos permitidos** - Ingrese el número máximo de bultos que puede contener la carga.
    - **Carga de pila en el piso** - Seleccione esta casilla de verificación para usar la carga de piso. En un escenario de carga de planta, las cajas están apiladas del suelo al techo y de pared a pared dentro del contenedor, para maximizar la capacidad interior.

1. En el panel Acciones, seleccione **Guardar**.

## <a name="associate-a-load-template-with-a-new-load"></a>Asociar una plantilla de carga con una nueva carga

1. Vaya a **Administración de transporte \> Planificación \> Área de trabajo de planificación de la carga**.
1. En la parte superior de la página, seleccione una de las siguientes pestañas, según el tipo de documento de origen para el que está creando una carga: **Envíos**, **Líneas de venta**, **Líneas de transferencia** o **Líneas de orden de compra**. 
1. Seleccione el documento específico para planificar la carga.
1. En el panel de acciones, en la ficha **Suministro y demanda**, en el grupo **Agregar**, seleccione **A una carga nueva**.
1. En el cuadro de diálogo **Cargar plantilla**, en el campo **Cargar Id. de plantilla**, seleccione la plantilla para aplicar.
1. Seleccione **Aceptar** para aplicar la plantilla.
