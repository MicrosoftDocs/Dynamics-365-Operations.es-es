---
title: Configurar picking en clúster
description: En este tema se describe cómo configurar el picking de clústeres y cómo aplicar la confirmación del artículo con el picking de clústeres.
author: Mirzaab
manager: tfehr
ms.date: 05/26/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSClusterProfile, WHSRFAutoConfirm, WHSWorkCluster
audience: Application User
ms.reviewer: kamaybac
ms.custom: 269384
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 2b3df8cf5e63fe97925f17001e836a41c703dfc9
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2021
ms.locfileid: "5239239"
---
# <a name="set-up-cluster-picking"></a>Configurar picking en clúster

[!include[banner](../includes/banner.md)]

Este tema describe cómo permitir a los trabajadores usar sus dispositivos móviles para agrupar el trabajo de picking en clústeres, de forma que puedan seleccionar artículos de una única ubicación para varios pedidos de trabajo al mismo tiempo. A esto se le llama *picking en clúster*.

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

1. En un elemento de menú del dispositivo móvil, abra el formulario de configuración para la confirmación del trabajo: **Gestión de almacenes** \> **Gestión de almacén** \> **Configuración** \> **Dispositivo móvil** \> **Elementos de menú del dispositivo móvil**.

1. En el elemento de menú del dispositivo móvil, abra **Configuración de la confirmación de trabajo**. La opción **Confirmación del producto** le permite que se compruebe cada pieza de inventario desde el dispositivo móvil cuando se escanea.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]