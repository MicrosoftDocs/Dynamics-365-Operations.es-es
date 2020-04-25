---
title: Mover, reemplazar e instalar activos
description: En este tema se explica cómo mover, reemplazar e instalar activos en Administración de activos.
author: josaw1
manager: tfehr
ms.date: 06/26/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CatProcureCatalogEdit, CatProcureCatalogListPage
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: 2214
ms.assetid: 2f3e0441-414d-402b-b28b-7ab0d650d658
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 1e203c9b1cfb61e0a512f678b0c29ff40b9628e8
ms.sourcegitcommit: 4f9912439ff78acf0c754d5bff972c4b85763093
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/02/2020
ms.locfileid: "3216335"
---
# <a name="move-replace-and-install-assets"></a>Mover, reemplazar e instalar activos

[!include [banner](../../includes/banner.md)]

 

En este tema se explica cómo mover, reemplazar e instalar activos en Administración de activos. Puede crear activos individuales que no tienen ninguna relación con otros activos o puede crear una estructura de activos que incluya un activo (activo principal de nivel superior) y activos secundarios relacionados (subactivos). En Admnistración de activos, hay tres enfoques para mover y cambiar la ubicación de un activo:

- **Mover** para mover un activo a otra estructura de activos o a otra ubicación de la misma estructura de activos.
- **Reemplazar** para quitar temporalmente un activo de la estructura de activos de modo que pueda repararse o restaurarse y luego agregar el activo restaurado de nuevo a la estructura de activos. Como alternativa, se puede reemplazar permanentemente un activo utilizado con un nuevo activo.
- **Instalar** para instalar un activo principal y cualquier activo secundario relacionado en una ubicación funcional.

> [!NOTE]
> El activo que se mueve, reemplaza o instala puede estar relacionado con otra ubicación funcional. En ese caso, el activo puede usar dimensiones financieras de la ubicación funcional. En la página **Tipos de ubicaciones funcionales**, configure el control de las dimensiones financieras en las ubicaciones funcionales.

## <a name="move-asset"></a>Mover activo

Utilice la función **Mover activo** para mover un activo a otra estructura de activos o a otra ubicación de la misma estructura de activos. También puede mover un activo de una estructura de activos de modo que se convierta en un activo independiente que no tenga ninguna relación de estructura.

> [!NOTE]
> No use esta función si se están reparando o se están reemplazando temporalmente los activos. En tal caso, use la funcionalidad **Reemplazar activo** que se describe más adelante en este tema.

1. Seleccione **Administración de activos** \> **Común** \> **Activos** \> **Todos los activos** o **Activos activos**.
2. En la lista, seleccione el activo que desea mover. Si el activo tiene activos secundarios, también mueve dichos activos.
3. Seleccione **Mover activo**.
4. Para mover el activo de modo que se convierta en parte de una estructura de activos, seleccione el nuevo activo principal en el campo **Activo principal**. Si está moviendo un activo secundario y desea que sea un activo independiente sin ninguna relación de estructura, deje en blanco del campo **Activo principal**.
5. De manera predeterminada, el campo **Vigencia** se establece automáticamente en la fecha y la hora actuales. Sin embargo, puede seleccionar otra fecha y hora a partir de las cuales sea válido el movimiento.
6. Seleccione **Aceptar**.

## <a name="replace-asset"></a>Reemplazar activo

Use la función **Reemplazar activo** en relación con reparaciones, restauraciones o sustitucioens permanentes de un activo por otro nuevo. Esta función se usa para reemplazar activos secundarios en una estructura de activos. Para los activos principales (es decir, activos fijos que no tienen actualmente un activo principal), esta sustitución se realiza en una ubicación funcional. Para obtener más información sobre cómo reemplazar activos principales en una ubicación funcional, consulte [Instalar activos en ubicaciones funcionales](../functional-locations/install-objects-on-functional-locations.md).

> [!NOTE]
> Si hay un taller de reparación relacionado con el departamento de producción, puede crear ubicaciones funcionales como **Reparación**, **Residuos**y **Almacenamiento** para gestionar la reparación y la sustitución de activos.

1. Seleccione **Administración de activos** \> **Común** \> **Activos** \> **Todos los activos** o **Activos activos**.
2. En la lista, seleccione el activo secundario que se vaya a reemplazar. Si el activo tiene activos secundarios, también reemplaza dichos activos.
3. Seleccione **Reemplazar activo**.

    El campo **Cambio de estructura** muestra la fecha y la hora en las que el activo seleccionado y los activos secundarios relacionados se movieron por última vez en la estructura de activos.

4. En la sección **Activo seleccionado**, en el campo **Ubicación funcional de destino**, seleccione la ubicación funcional a la que se moverá el activo. Por ejemplo, seleccione la ubicación **Reparación** o **Residuos**.

    En la sección **Activo principal**, el campo **Vigencia** muestra la fecha y la hora en las cuales el activo principal y los activos secundarios relacionados se instalaron o movieron por última vez en la ubicación funcional actual.

5. En la sección **Nuevo activo**, en el campo **Activo**, seleccione el activo para insertar como sustitución temporal o permanente del activo seleccionado. Este activo se puede encontrar actualmente en otra ubicación funcional, como **Almacenamiento**.
7. En la sección **Vigente desde**, el campo **Vigencia** se establece automáticamente en la fecha y la hora actuales de manera predeterminada. Sin embargo, puede seleccionar otra fecha y hora a partir de las cuales sea válido el reemplazo.
8. Seleccione **Aceptar**.

## <a name="install-asset"></a>Instalar activo

Use la función **Instalar activo** para instalar una estructura de activos en una ubicación funcional.

> [!NOTE]
> Seleccione siempre un activo principal. El activo principal y los activos secundarios relacionados se mueven a la ubicación funcional seleccionada.

1. Seleccione **Administración de activos** \> **Común** \> **Activos** \> **Todos los activos** o **Activos activos**.
2. En la lista, seleccione el activo principal para instalar en otra ubicación funcional.
3. Seleccione **Instalar activo**.

    La sección **Atributos** muestra los atributos de activos que se configuran en el activo principal.

4. Seleccione la nueva ubicación en el campo **Ubicación funcional**.
5. De manera predeterminada, el campo **Vigencia** se establece automáticamente en la fecha y la hora actuales. Sin embargo, puede seleccionar otra fecha y hora a partir de las cuales sea válida la instalación en la estructura de activos.
6. Seleccione **Aceptar**.
