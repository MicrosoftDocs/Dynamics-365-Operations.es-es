---
title: Integrar la administración de activos con activos fijos.
description: Este tema explica cómo integrar los módulos de Administración de activos y Activos fijos, para que pueda vincular activos fijos con activos de mantenimiento.
author: kamaybac
ms.date: 04/17/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: dabourq
ms.search.validFrom: 2020-04-17
ms.dyn365.ops.version: Release 10.0.11
ms.openlocfilehash: 63ab3e772d54c7d27ade1c0cef07f275f49a143ad382fe618035117bca2cd43d
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2021
ms.locfileid: "6746289"
---
# <a name="integrate-asset-management-with-fixed-assets"></a>Integrar la administración de activos con activos fijos.

[!include [banner](../../includes/banner.md)]

Al integrar los módulos **Administración de activos** y **Activos fijos**, puede vincular los activos fijos con los activos de mantenimiento. Los usuarios de Activos fijos pueden crear un activo de mantenimiento a partir de un activo fijo nuevo o existente, y los usuarios de Administración de activos pueden asociar un activo de mantenimiento con un activo fijo existente. Esta característica también facilita a los usuarios de Activos fijos ver los costos que se registraron en las órdenes de trabajo para los activos de mantenimiento relacionados.

> [!NOTE]
> En este tema, *activos de mantenimiento* son los activos del módulo **Administración de activos** y *Activos fijos* son los activos del módulo **Activos fijos**.

## <a name="set-a-default-location-for-new-maintenance-assets-that-are-created-from-fixed-assets-optional"></a>Establecer una ubicación predeterminada para los nuevos activos de mantenimiento que se crean a partir de activos fijos (opcional)

Esta configuración opcional permite establecer una ubicación funcional predeterminada para los nuevos activos de mantenimiento que se crean a partir de activos fijos. Por lo general, completa esta configuración solo una vez, si es que la completa.

Para completar la configuración, siga estos pasos.

1. Vaya a **Administración de activos \> Configuración \> Parámetros de administración de activos**.
1. En la ficha **Activos fijos**, en el campo **Ubicación funcional**, seleccione la ubicación predeterminada.
1. En el panel de acciones, seleccione **Guardar**.

## <a name="work-with-integrated-maintenance-assets-and-fixed-assets"></a>Trabajar con activos de mantenimiento y activos fijos

Esta sección proporciona una colección de procedimientos que muestran varias formas en que puede trabajar con las funciones integradas de Administración de activos y Activos fijos.

### <a name="associate-an-existing-maintenance-asset-with-a-fixed-asset"></a>Asociar un activo de mantenimiento existente con un activo fijo

Para asociar un activo de mantenimiento existente con un activo fijo, siga estos pasos.

1. Vaya a **Administración de activos \> Activos \> Todos los activos** (o **Activos activos**).
1. Seleccione un activo.
1. En la ficha desplegable **Activo fijo**, en el campo **Número de activo fijo**, seleccione un activo fijo existente.
1. En el panel de acciones, seleccione **Guardar**.

### <a name="view-the-fixed-asset-that-is-associated-with-a-selected-maintenance-asset"></a>Ver el activo fijo asociado con un activo de mantenimiento seleccionado

Para ver el activo fijo asociado con un activo de mantenimiento seleccionado, siga estos pasos.

1. Vaya a **Administración de activos \> Activos \> Todos los activos** (o **Activos activos**).
1. Seleccione un activo.
1. En la ficha desplegable **Activo fijo**, en el campo **Número de activo fijo**, seleccione el vínculo.

    Se abre la página **Activos fijos** para el activo seleccionado. (Normalmente, esta página se encuentra en **Activos fijos \> Activos fijos \> Activos fijos**).

### <a name="view-the-maintenance-asset-that-is-associated-with-a-selected-fixed-asset"></a>Ver el activo de mantenimiento asociado con un activo fijo seleccionado

Para ver el activo de mantenimiento asociado con un activo fijo seleccionado, siga estos pasos.

1. Vaya a **Activos fijos \> Activos fijos \> Activos fijos**.
1. Seleccione un activo.
1. En el panel de acciones, en la ficha **Administración de activos**, en el grupo **Vista**, seleccione **Activo de mantenimiento**.

    Se abre la página **Activo de mantenimiento** para el activo asociado con el activo fijo seleccionado. (Normalmente, esta página se encuentra en **Administración de activos \> Activos \> Todos los activos**).

### <a name="view-maintenance-costs-that-are-associated-with-a-fixed-asset"></a>Ver los costos de mantenimiento asociados con un activo fijo

Las órdenes de trabajo de administración de activos pueden contabilizarse para activos de mantenimiento y cada una de esas órdenes de trabajo generalmente tiene un costo. Cuando un activo fijo está asociado con un activo de mantenimiento, puede ir directamente desde el activo fijo para ver los costos relacionados.

Para ver los costos de mantenimiento asociados con un activo fijo, siga estos pasos.

1. Vaya a **Activos fijos \> Activos fijos \> Activos fijos**.
1. Seleccione un activo.
1. En el panel de acciones, en la ficha **Administración de activos**, en el grupo **Vista**, seleccione **Costo de mantenimiento**.

    Se abre la página **Costo de mantenimiento** y muestra los costos relacionados.

### <a name="create-a-new-maintenance-asset-for-an-existing-fixed-asset"></a><a name="new-maintenance-from-fixed"></a>Crear un activo de mantenimiento nuevo para un activo fijo existente

Para crear un activo de mantenimiento nuevo para un activo fijo existente, siga estos pasos.

1. Vaya a **Activos fijos \> Activos fijos \> Activos fijos**.
1. Seleccione un activo.
1. En el panel de acciones, en la ficha **Administración de activos**, en el grupo **Nuevo**, seleccione **Crear activo de mantenimiento**. (Si esta opción no está disponible, un activo de mantenimiento ya podría estar asociado con el activo fijo seleccionado).
1. Termine de crear el activo como se describe en [Crear un activo](../objects/create-an-object.md).

### <a name="create-a-new-fixed-asset-and-add-a-new-maintenance-asset-for-it"></a>Crear un activo fijo nuevo y agregar un activo de mantenimiento nuevo para él

Para crear un activo fijo nuevo y agregar un activo de mantenimiento nuevo para este, siga estos pasos.

1. Vaya a **Activos fijos \> Activos fijos \> Activos fijos**.
1. En el panel de acciones, haga clic en **Nueva**.
1. Termine de crear el activo fijo como se describe en [Crear un activo fijo](../../../finance/fixed-assets/tasks/create-fixed-asset.md).
1. En el panel de acciones, en la ficha **Administración de activos**, en el grupo **Nuevo**, seleccione **Crear activo de mantenimiento**.
1. Termine de crear el activo como se describe en [Crear un activo](../objects/create-an-object.md).

### <a name="remove-the-association-between-two-assets"></a>Eliminar la asociación entre dos activos

En algunos casos, es posible que deba desasociar un activo de mantenimiento de su activo fijo. Por ejemplo, si quiere [crear un nuevo activo de mantenimiento](#new-maintenance-from-fixed) a partir de un activo fijo, primero debe eliminar cualquier asociación existente.

Para eliminar una asociación existente entre un activo de mantenimiento y un activo fijo, siga estos pasos.

1. Vaya a **Administración de activos \> Activos \> Todos los activos** (o **Activos activos**).
1. Busque y abra el activo fijo.
1. En la ficha desplegable **Activo fijo**, borre el valor del campo **Ubicación funcional**.
1. En el panel de acciones, seleccione **Guardar**.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]