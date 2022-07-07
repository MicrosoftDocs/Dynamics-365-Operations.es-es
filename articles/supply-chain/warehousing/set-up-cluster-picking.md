---
title: Configurar selección de clústeres
description: En este artículo se describe cómo configurar el picking de clústeres y cómo aplicar la confirmación del artículo con el picking de clústeres.
author: Mirzaab
ms.date: 05/26/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: WHSClusterProfile, WHSRFAutoConfirm, WHSWorkCluster
audience: Application User
ms.reviewer: kamaybac
ms.custom: 269384
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 0ec3de073def2ff63af3c04b5696cbcec4f09948
ms.sourcegitcommit: cfe8fbc202c3eb05d894076fdf99e46704f17365
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/15/2022
ms.locfileid: "9014774"
---
# <a name="set-up-cluster-picking"></a>Configurar selección de clústeres

[!include[banner](../includes/banner.md)]

Este artículo describe cómo permitir a los trabajadores usar sus dispositivos móviles para agrupar el trabajo de picking en clústeres, de forma que puedan seleccionar artículos de una única ubicación para varios pedidos de trabajo al mismo tiempo. A esto se le llama *picking en clúster*.

## <a name="about-cluster-picking"></a>Acerca del picking en clúster

Una vez que los pedidos de trabajo se liberan al almacén, el trabajador puede usar un dispositivo móvil para asignar los pedidos a un clúster. El clúster organizará el trabajo de picking para el trabajador. Cuando un pedido de trabajo se asigna a un clúster, el trabajador debe usar el picking en clúster para realizar el trabajo de picking para el pedido. El trabajador no puede utilizar otros métodos de picking. Si un pedido de trabajo se asigna a un clúster por error, el trabajador debe interrumpir el clúster y reconstruirlo.

Si es necesario, un trabajador puede gastar un clúster a otro trabajador. Esto cambia el estado del clúster a Pasado. Cuando el trabajador usa un dispositivo móvil para indicar que el trabajo de picking y colocación se ha completado, el envío o la carga deben confirmarse en el cliente.

## <a name="enable-cluster-picking"></a>Habilitar selección de clústeres

Para habilitar el picking en clúster, debe configurar lo siguiente:

- **Perfiles de clúster**: especifique si generar automáticamente id. de clúster, el número de posiciones a usar, cuándo interrumpir clústeres y cómo organizar por secuencias y comprobar el trabajo de selección.

- **Plantillas de trabajo**: defina cómo crear el trabajo de selección para la selección de clústeres.

- **Directivas de ubicación**: permite especificar dónde seleccionar los artículos y dónde ponerlos.

- **Elementos de menú del dispositivo móvil**: permite configurar un elemento de menú del dispositivo móvil para usar el trabajo existente realizado mediante picking en clúster. A continuación debe agregar el elemento de menú a un menú del dispositivo móvil para que se muestre en dispositivos móviles.

- **Parámetros de gestión de almacenes**: permite especificar la secuencia numérica que se usará si desea generar identificadores para los clústeres.

## <a name="set-up-a-cluster-profile"></a>Configurar un perfil de clúster

Para establecer un perfil de clúster, siga estos pasos:

1. Haga clic en **Gestión de almacenes** \> **Configuración** \> **Dispositivo móvil** \> **Perfiles de clúster**.

1. Haga clic en **Nuevo** para crear un nuevo perfil.

1. Haga clic en **Crear clúster** y, en **Ordenación de clústeres**, haga clic en **Nuevo** para configurar los criterios de ordenación para el clúster. Los criterios de ordenación controlan el orden en que el trabajador debe realizar el trabajo de picking. Puede agregar tantos criterios como sea necesario.

1. En el campo **Número de secuencia**, especifique un número para definir el orden en que se procesarán los criterios de ordenación.

1. En el campo **Nombre de campo**, seleccione el campo que va a determinar la ordenación. Por ejemplo, si selecciona el campo **WMSLocationId**, el trabajo se ordenará por ubicación.

1. En el campo **Ordenación**, seleccione una de las siguientes opciones.

| **Opción**     | **Descripción**                                                                                                                                                                                                                    |
|----------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **Ascendente**  | El trabajo de picking se ordena de forma ascendente según los criterios de ordenación. Por ejemplo, si usa el campo **WMSLocationId** como criterios de ordenación, y sus identificadores de la ubicación son 1, 2, 3 y 4, se seleccionará la ubicación 4 primero. |
| **Descendente** | El trabajo de picking se ordena de forma descendente según los criterios de ordenación. Por ejemplo, si usa el campo **WMSLocationId** como criterios de ordenación, y sus identificadores de la ubicación son 1, 2, 3 y 4, se seleccionará la ubicación 1 primero. |

## <a name="item-confirmation"></a>Configuración del artículo

Cuando se aplica el picking en clúster, es esencial la confirmación del artículo para comprobar que los artículos se agregan a los clústeres. Puede comprobar los artículos del picking en clúster durante el proceso de picking en clúster. La configuración se basa en la configuración del código de barras del producto.

### <a name="set-up-item-verification-with-cluster-picking"></a>Establecer la comprobación de artículos con picking en clúster

1. Vaya a **Gestión de almacenes** > **Configurar** > **Dispositivo móvil** > **Elementos de menú del dispositivo móvil**.
1. En el panel de la lista, seleccione el elemento del menú que desee configurar.
1. En el Panel de acciones, seleccione **Configuración de confirmación de trabajo**.
1. Realice una de las acciones siguientes:
    - Si ya existe una línea para el **Tipo de trabajo** que desea configurar, selecciónela y luego seleccione **Editar** en el Panel de acciones.
    - Si no existe una línea adecuada, seleccione **Nueva** en el Panel de acciones y luego configure el **Tipo de trabajo** al tipo apropiado.
1. Marque la casilla de verificación **Confirmación del producto** para su línea nueva o seleccionada. Esto permitirá que los trabajadores verifiquen cada pieza de inventario desde el dispositivo móvil.



[!INCLUDE[footer-include](../../includes/footer-banner.md)]