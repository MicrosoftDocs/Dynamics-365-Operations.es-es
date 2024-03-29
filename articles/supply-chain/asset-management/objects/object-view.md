---
title: Vista de activos
description: En este artículo se describe la vista de activos en Administración de activos.
author: johanhoffmann
ms.date: 06/26/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: CatProcureCatalogEdit, CatProcureCatalogListPage, EntAssetObjectTree, EntAssetFunctionalLocationTree
audience: Application User
ms.reviewer: kamaybac
ms.custom: 2214
ms.assetid: 2f3e0441-414d-402b-b28b-7ab0d650d658
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 495f3dbf9bab9d550ebdbb7dda52aca80d5ea635
ms.sourcegitcommit: cfe8fbc202c3eb05d894076fdf99e46704f17365
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/15/2022
ms.locfileid: "9017127"
---
# <a name="asset-view"></a>Vista de activos

[!include [banner](../../includes/banner.md)]

 

En este artículo se describe la vista de activos en Administración de activos. La página **Vista de activo** muestra los activos activos y las ubicaciones funcionales en una vista de árbol. Por lo tanto, puede obtener fácilmente una visión general de las relaciones de los activos con las ubicaciones funcionales. Además, puede ver información detallada sobre ubicaciones funcionales, activos y listas de materiales relacionadas (BOM). También puede obtener una visión general rápida de las solicitudes de mantenimiento y órdenes de trabajo activas relacionadas con un activo.

1. Seleccione **Administración de activos** \> **Activos** \> **Vista de activos**.
2. Para cambiar la vista que se muestra en la página, seleccione un nuevo valor en el campo **Vista** .

    > [!NOTE]
    > La vista predeterminada que se mostrará al abrir la página **Vista de activo** depende del valor seleccionado en el campo **Vista** en la pestaña **Activos** de la página **Parámetros de administración de activos** (**Administración de activos** \> **Configuración** \> **Parámetros de administración de activos**).

En el lado derecho de la página, las fichas desplegables muestran los detalles de la vista seleccionada.

La ruta de navegación que aparece sobre la vista de árbol muestra la selección actual en la vista de árbol. Esta ruta de navegación utiliza el formato siguiente:

Id. de ubicación funcional / Id. de ubicación funcional (si hay más de una ubicación técnica) \> Id. de activo / Id. de activo (si hay más de un activo) - Número de artículo.

Si ha seleccionado un activo en la vista de árbol, puede seleccionar **Solicitudes activas** u **Órdenes de trabajo activas** para ver las solicitudes de mantenimiento o las órdenes de trabajo relacionadas con el activo. También puede seleccionar **Abrir** \> **Ubicación técnica**, **Activo** o **L. MAT de activos** para abrir la vista relacionada.

La opción **Ubicaciones funcionales de activo** que puede seleccionar en el campo **Vista** también está disponible en cualquier búsqueda de activos donde pueda seleccionar un activo. La vista de árbol se muestra en una pestaña **Vista de activo**, por ejemplo, donde [crea un activo](../objects/create-an-object.md), crea una solicitud de mantenimiento o bien crea una orden de trabajo.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]