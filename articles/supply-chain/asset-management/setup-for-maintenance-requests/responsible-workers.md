---
title: Trabajadores de mantenimiento responsables
description: En este tema se explica cómo configurar trabajadores de mantenimiento responsables en Administración de activos.
author: josaw1
manager: tfehr
ms.date: 07/26/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: EntAssetWorkerResponsible
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: riluan
ms.search.validFrom: 2019-07-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: ad6b1757952fb0e5b970f82f75d99919a7f0745e
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2021
ms.locfileid: "5261174"
---
# <a name="responsible-maintenance-workers"></a>Trabajadores de mantenimiento responsables

[!include [banner](../../includes/banner.md)]

 

Los trabajadores de mantenimiento responsables pueden estar relacionados con tipos de activos, activos, ubicaciones funcionales, categorías de tipo de trabajo de mantenimiento, tipos de trabajo de mantenimiento, variantes de tipos de trabajo de mantenimiento y oficios. Se pueden usar en órdenes de trabajo y en solicitudes de mantenimiento para indicar una preferencia sobre los trabajadores de mantenimiento que se deben responsables de una orden de trabajo. (Sin embargo, esos trabajadores de mantenimiento no son necesariamente los mismos trabajadores programados para realizar la orden de trabajo). El uso de esta función es opcional. Por ejemplo, puede usarse para seleccionar los trabajadores o grupos de trabajadores responsables para tipos o áreas de trabajo específicos.

Durante el ciclo de vida de una orden de trabajo o el ciclo de vida de una solicitud de mantenimiento, los trabajadores de mantenimiento responsables se pueden modificar o actualizar. Este cambio o actualización puede estar relacionado, por ejemplo, con un cambio del estado del ciclo de vida de la solicitud de mantenimiento o el estado del ciclo de vida de la orden de trabajo.

La configuración de la página **Trabajadores de mantenimiento responsables** *no* se utiliza durante la programación de la orden de trabajo.

> [!NOTE]
> En Administración de activos, también puede configurar trabajadores del mantenimiento *preferidos* que pueden asignarse a órdenes de trabajo durante la programación de estas.

Para poder configurar los trabajadores de mantenimiento responsables, debe configurar los trabajadores y grupos de trabajadores de mantenimiento que deben estar disponibles para la selección. Para obtener información sobre cómo configurar trabajadores y grupos de trabajadores de mantenimiento, consulte [Trabajadores de mantenimiento y grupos de trabajadores](../setup-for-objects/workers-and-worker-groups.md).

## <a name="set-up-responsible-maintenance-workers"></a>Configurar trabajadores de mantenimiento responsables

1. Seleccione **Administración de activos** \> **Configuración** \> **Trabajadores** \> **Trabajadores de mantenimiento responsables**.
2. Seleccione **Nuevo** para crear un registro.
3. Primero cree una configuración de trabajador de mantenimiento responsable o un grupo de trabajadores de mantenimiento responsables predeterminados donde solo establezca el campo **Grupo de trabajadores de mantenimiento responsables** y/o **Trabajador responsable** . Deje en blanco los campos restantes. Esta configuración predeterminada se usará durante la programación de la orden de trabajo si hay ninguna otra combinación más específica que coincida con el contenido de la orden de trabajo.

    > [!NOTE]
    > Durante la creación de una solicitud de mantenimiento, cuando un trabajador de mantenimiento responsable o un grupo de trabajadores de mantenimiento responsables pasan a estar disponibles para su selección en la página **Todas las solicitudes de mantenimiento**, Administración de activos recorre todos los registros de trabajadores de mantenimiento responsables para buscar una coincidencia. Comprueba siempre primero la combinación más específica. Es decir, Administración de activos primero busca una coincidencia para el campo **Oficio**. Si no se encuentra ninguna coincidencia, comprueba si hay una coincidencia para el campo **Variante de tipo de trabajo de mantenimiento**. Si no se encuentra ninguna coincidencia, comprueba si hay una coincidencia para el campo **Tipo de trabajo de mantenimiento**, y así sucesivamente. Como puede ver en el diseño de la página, este comportamiento significa que, para encontrar la combinación más específica, Administración de activos comprueba cada registro de derecha a izquierda en busca de una coincidencia (primero **Oficio**, después **Variante de tipo de trabajo de mantenimiento**, después **Tipo de trabajo de mantenimiento**, **Categoría de tipo de trabajo de mantenimiento**, **Ubicación funcional**, **Activo** y finalmente **Tipo de activo**). Si no se encuentra ninguna coincidencia, se utiliza el registro predeterminado que no tiene ninguna selección en esos siete campos.

La ilustración siguiente muestra un ejemplo de la página **Trabajadores de mantenimiento responsables**.

![Página de trabajadores de mantenimiento responsables](media/08-setup-for-requests.png)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]