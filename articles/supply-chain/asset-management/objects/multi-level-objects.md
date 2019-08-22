---
title: Activos de varios niveles
description: Este tema explica cómo crear y eliminar activos de varios niveles.
author: josaw1
manager: AnnBe
ms.date: 06/26/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CatProcureCatalogEdit, CatProcureCatalogListPage
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 2214
ms.assetid: 2f3e0441-414d-402b-b28b-7ab0d650d658
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 0f38253317ed8f06318fc501511ca5263a614e20
ms.sourcegitcommit: 747bcd25ce7c6c20ce9eaa0027e730f74d4fd6aa
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/23/2019
ms.locfileid: "1783569"
---
# <a name="multi-level-assets"></a>Activos de varios niveles

[!include [banner](../../includes/banner.md)]

[!include [banner](../../includes/preview-banner.md)]

Este tema explica cómo crear y eliminar activos de varios niveles. Puede crear activos y subactivos relacionados en una estructura en árbol jerárquica. De esta manera, puede mostrar las relaciones y dependencias entre los activos. Los trabajos de mantenimiento pueden estar relacionadas con todos los niveles de la estructura de árbol. También se pueden crear estadísticas para un nivel individual o como suma de todos los niveles de subactivos.

En la página de lista **Todos los activos** (**Administración de activos** \> **Común** \> **Activos** \> **Todos los activos**), la columna **Activo** muestra los activos por orden jerárquico. La columna **Principal** muestra el elemento principal relacionado. Además, si los activos y los subactivos ya se han creado, la sección **Árbol de activos** en el panel **Información relacionada** se muestra los activos en una estructura de árbol.

Para obtener información sobre cómo crear un activo, consulte [Crear un activo](../objects/create-an-object.md). Para crear un subactivo, seleccione el activo principal en el campo **Principal** del FastTab **General**.

## <a name="copy-an-asset-or-asset-structure"></a>Copiar un activo o una estructura de activos

Si su empresa tiene varias estructuras de activos similares, puede usar la función Copiar de Administración de activos para crearlas rápidamente.

1. Seleccione **Administración de activos** \> **Común** \> **Activos** \> **Todos los activos**.
2. En la página de lista **Todos los activos**, seleccione el activo para copiar. Por ejemplo, si desea copiar la estructura de activos completa, incluidos los subactivos, seleccione un activo principal.
3. Seleccione **Copiar activo**. En la sección **Copiar de**, el campo **Activo** está configurado con el activo que seleccionó en la página de lista.
4. En la sección **Copiar a**, en el campo **Activo**, escriba el nombre del nuevo activo.
5. Si el activo que está creando si es parte de una estructura de activos existente, en la sección **Activo principal**, en el campo **Activo**, seleccione un identificador principal.
6. Seleccione **Aceptar**. La nueva estructura de activos se muestra en la página de lista **Todos los activos**. Todos los atributos de activo, planes de mantenimiento y rondas de mantenimiento relacionadas con el activo que ha copiado se transfieren al nuevo activo o estructura de activos.

Al copiar una estructura de activos, los subactivos de la nueva estructura tienen el mismo nombre que los subactivos que ha copiado. Una vez que el procedimiento de copia se complete, puede cambiar fácilmente el nombre y otros parámetros del activo. Seleccione el activo en la página de lista **Todos los activos** y seleccione el botón **Editar**.

> [!NOTE]
> Al copiar un activo o una estructura de activos, se restablece el estado de ciclo de vida de los nuevos activos en el estado definido como estado de ciclo de vida inicial de los activos. La ubicación funcional se restablece a la ubicación funcional predeterminada.

## <a name="delete-an-asset-or-asset-structure"></a>Eliminar un activo o una estructura de activos

Si un activo tiene subactivos relacionados, puede eliminarlo solo si no hay solicitudes de mantenimiento, trabajos de órdenes de trabajo, registros de errores o evaluaciones de estado registrados en ninguno de los activos.

1. En la página de lista **Todos los activos**, seleccione el activo para eliminar.
2. Seleccione **Eliminar**.

> [!NOTE]
> Si no puede eliminar un activo mediante este procedimiento, otro modo de gestionar la eliminación es configurar un estado de ciclo de vida del activo con este propósito. Por ejemplo, puede configurar un estado de ciclo de vida **Desechado** o **Eliminado** en la página **Estados del ciclo de vida de activo**.
