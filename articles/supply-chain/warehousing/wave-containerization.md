---
title: Creación de contenedores
description: Este tema describe cómo automatizar la creación de contenedores de cargas. La creación de contenedores automatizada crea contenedores y el trabajo de picking para los envíos cuando se procesa una oleada.
author: Mirzaab
ms.date: 03/08/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: WHSWaveTemplateTable, InventLocationIdLookup, WHSContainerType, WHSContainerGroup, WHSContainerizationTable, WHSContainerizationBreak, WHSCreateContainerBreak, WHSContainerStructure, WHSContainerTable, WHSContainerizatonHistory, WHSContainerPackingPolicyChange, WHSManifestShipmentContainers, WHSAllowedContainerTypeGroup, WHSPostMethod, WHSContainerCreateDialog, WHSContainerCloseDiag, WHSContainer
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2021-03-08
ms.dyn365.ops.version: Release 10.0.18
ms.openlocfilehash: 88e38989e3d3e46d0c43779659bc6ea2e29f08e2
ms.sourcegitcommit: 8e846b52763f90d2232ec7d427839f4722570bce
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/22/2021
ms.locfileid: "6292746"
---
# <a name="containerization"></a>Creación de contenedores

[!include [banner](../includes/banner.md)]

Este tema describe cómo automatizar la creación de contenedores de cargas. La creación de contenedores automatizada crea contenedores y el trabajo de picking para los envíos cuando se procesa una oleada.

Para configurar la creación de contenedores, cree lo siguiente:

- **Tipo de contenedor**: defina las características físicas de los contenedores. Use tipos del contenedor para empaquetar artículos de inventario en un tipo y un tamaño específicos de embalaje, como huecos o pallets.
- **Grupos de contenedores**: cree grupos de tipos de contenedores que sean similares. Por ejemplo, un grupo de contenedor puede incluir tipos de contenedores que tengan dimensiones de tamaño similares. Un grupo de contenedores especifica la secuencia en la que se empaquetan los contenedores, y el porcentaje de relleno de cada contenedor.
- **Plantilla de construcción de contenedores**: cree plantillas que definan reglas para la creación de contenedores. Por ejemplo, reglas para mezclar inventario y otras estrategias de embalaje.
- **Plantillas de oleada**: configure una o más plantillas de oleadas para crear el trabajo de picking para la creación de contenedores.

## <a name="create-wave-templates-for-containerization"></a>Crear plantillas de oleada para la creación de contenedores

Debe configurar una o más plantillas de oleada de envío para la creación de contenedores. Las plantillas de oleada incluyen criterios que determinan lo siguiente:

- Cómo procesar oleadas. Puede ser de forma manual o automática.
- Cómo crear trabajo de picking. Esto se determina por los métodos de oleada. La plantilla de oleada debe incluir el método **creación de contenedores**.
- Cómo hacer coincidir artículos o líneas de asignación con una oleada.

Para obtener más información, vea [Plantillas de oleada](wave-templates.md).

## <a name="create-container-types"></a>Crear tipos de contenedor

Use tipos de contenedor para crear descripciones de contenedores, incluidos los valores máximos para las dimensiones de tamaño físicas y la capacidad de peso. Cuando se procesa una oleada en contenedor, los contenedores se crean en función de la información del tipo de contenedor.

Para configurar un tipo de contenedor, siga estos pasos:

1. Vaya a **Administración de almacenes** \> **Configurar** \> **Contenedores** \> **Tipos de contenedor**.
1. Seleccione **Nuevo** para crear un nuevo tipo de contenedor.
1. Escriba un identificador único (id.) y una descripción para el tipo de contenedor.
1. En el campo **Peso tara** , especifique el peso real o estimado del contenedor.
1. En el campo **Peso máximo**, especifique el peso máximo que el contenedor puede soportar.
1. En los campos **Volumen máximo de contenerización**, **Longitud máxima de contenedorización**, **Ancho máximo de contenedorización**, y **Altura máxima de contenedorización**, especifique las dimensiones físicas del contenedor.

    > [!NOTE]
    > Los valores de la longitud y la anchura son intercambiables. Esto significa que puede girar los artículos lateralmente, o bien en el eje X, si es necesario. Por ejemplo, si la longitud son 2 pies, y la anchura es de 1 pie, puede cambiar la longitud a 1 pie y a la anchura a 2 pies. Tenga en cuenta que esto no se aplica a la dimensión de altura. No puede cambiar el valor de la altura para girar un artículo verticalmente.

1. Seleccione los valores de atributo personalizados para el contenedor en los campos para atributos. Los atributos son valores personalizados que se usan para filtrar u ordenar artículos basados en un valor que de otro modo no se encuentra disponible. Por ejemplo, si desea empaquetar los artículos para un cliente concreto, puede crear un atributo para el nombre del cliente. Puede crear atributos en la página **Atributos de contenedor**.

## <a name="create-container-groups"></a>Crear grupos de contenedores

Puede configurar grupos lógicos de tipos de contenedores. Para cada grupo, puede especificar la secuencia en la que empaquetar los contenedores y el porcentaje de los contenedores que se va a rellenar. Las dimensiones de tamaño del artículo determinan si cabrá en un contenedor. Se usa el contenedor que se encuentra más cercano a las dimensiones de tamaño del artículo. Si tiene varios tipos de contenedor en un grupo, se recomienda que organice la secuencia por tamaños, de modo que el contenedor más grande sea el primero, número 1 en la secuencia, y el contenedor más pequeño el último.

Para configurar un grupo de contenedores, siga estos pasos:

1. Vaya a **Administración de almacenes** \> **Configurar** \> **Contenedores** \> **Grupos de contenedores**.
1. Seleccione **Nuevo** para crear un grupo de contenedores.
1. Escriba un identificador único y una descripción para el grupo de contenedores.
1. En la ficha desplegable **Detalles**, seleccione **Nuevo** para agregar un tipo de contenedor al grupo.
1. En el campo **Tipo de contenedor**, seleccione un tipo de contenedor.
1. Seleccione **Mover arriba** o **Mover abajo** para especificar la secuencia en la que se empaquetan los tipos de contenedores.

## <a name="create-container-build-templates"></a>Crear plantillas de creación de contenedores

Puede configurar reglas para el proceso de creación de contenedores, como reglas de la mezcla de inventario y otras estrategias de embalaje. Por ejemplo, puede configurar una regla de modo que los trabajadores no puedan empaquetar las líneas de asignación que representen los pedidos de ventas de diferentes clientes en el mismo contenedor.

Para configurar una plantilla de creación de contenedores, siga estos pasos.

1. Vaya a **Administración de almacenes** \> **Configurar** \> **Contenedores** \> **Plantilla de creación de contenedores**.
1. Cree una nueva plantilla de creación de contenedores.
1. En los campos **Nombre de creación de contenedor** y **Número de secuencia**, especifique el nombre de la plantilla de creación de contenedores y el pedido que está relacionado con las líneas de asignación.

    > [!NOTE]
    > El sistema aplicará la primera plantilla para la que la línea de la asignación cumpla los criterios de consulta. Por lo tanto, configure la plantilla con los criterios más específicos en la parte superior de la lista. Cuanto más amplios sean los criterios, será más probable que una línea de asignación cumpla los criterios. Esto puede originar líneas que estén asignadas al contenedor incorrecto. Si es necesario, puede seleccionar **Mover arriba** o **Mover abajo** para cambiar la secuencia de plantillas.

1. En el campo **Identificador de grupo de contenedores**, seleccione el grupo de contenedor del que desea crear los contenedores.
1. En el campo **Tipos de consulta base**, seleccione el tipo de consulta que determinará el embalaje y en qué se basará la consulta del filtro. Las siguientes opciones están disponibles:

      - **Línea de asignación de ventas**: líneas de asignación del paquete que se crean para pedidos de ventas.
      - **Línea de asignación de transferencia**: líneas de asignación del paquete que se crean para transferir pedidos.
      - **Contenedor**: empaquete un contenedor que se haya creado previamente en el proceso de creación de contenedores. Por ejemplo, esto se usa para anidar contenedores.

        > [!NOTE]
        > Para usar los contenedores de anidamiento, debe convertir el método de creación de contenedores en repetible. Para obtener más información, vea [Plantillas de oleada](wave-templates.md).

1. En la ficha desplegable **General**, en el campo **Código de paso de oleada**, especifique el identificador único del método de proceso de oleada que vincula la plantilla de creación del contenedor con los pasos de una plantilla de oleada.
1. Seleccione la casilla **Permite elecciones divididas** para permitir que los trabajadores empaqueten artículos de un pedido de trabajo en contenedores independientes. Esto requiere que toda la cantidad quepa en el contenedor. Siempre se utilizará la unidad de medida mayor de la línea de asignación.
1. En el campo **Empaquetar por unidad**, seleccione la unidad de medida que representará el contenedor. Por ejemplo, puede indicar que un caso es un contenedor. Si empaqueta por unidad de medida, tampoco puede especificar un grupo de contenedores porque la unidad de medida es el contenedor.
1. En el campo **Estrategia de embalaje de contenedor**, seleccione la estrategia de embalaje que se va a utilizar. Las siguientes opciones están disponibles:

    > [!NOTE]
    > La estrategia solo se aplica en las líneas de asignación de ventas y en las líneas de asignación de transferencia.

      - **Empaquetar en todos los contenedores abiertos**: el sistema evalúa si la línea de asignación cabrá en algún contenedor que se haya creado durante el ciclo de creación de contenedores.
      - **Embalar solo en el contenedor actual**: el sistema solo evalúa si la línea de asignación cabrá en el contenedor creado más recientemente.

    Para obtener más información y ejemplos que muestran cómo trabajar con estrategias de embalaje de contenedores, consulte [Estrategias de embalaje de contenedores](container-packing-strategy-overview.md).

1. Para configurar reglas para la asignación de líneas de embalaje en contenedores, seleccione **Mezclar interrupciones de lógica**. Por ejemplo, puede crear una regla que permita a los trabajadores embalar líneas de asignación para dos artículos diferentes en el mismo contenedor. Para definir una regla de combinación, siga estos pasos:

    1. En la página **Mezclar rupturas lógicas**, seleccione **Nuevo**.
    1. En el campo **Tabla**, seleccione la tabla que contiene el campo para usar como criterio para la interrupción de lógica de combinación.
    1. En el campo **Seleccionar campo**, seleccione el campo que se utilizará como criterio para la interrupción de lógica de combinación.
    1. Repita estos pasos hasta que haya agregado todos los criterios para la interrupción lógica de combinación.

    > [!NOTE]
    > Si usa lógica de combinación, se recomienda clasificar por los mismos campos en la consulta de los criterios del filtro. Esto reducirá el número de contenedores que se creen.
