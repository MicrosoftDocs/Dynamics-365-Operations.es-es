---
title: Crear un grupo de arrendamientos
description: En este tema se explica cómo configurar grupos de arrendamientos. Se requieren grupos de arrendamientos para crear nuevos arrendamientos.
author: moaamer
manager: Ann Beebe
ms.date: 10/28/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: TaxTable
audience: Application User
ms.reviewer: roschlom
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2020-10-28
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: e8ad226e87776615d9c19a239e0fb90b648d9c49
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2021
ms.locfileid: "5210466"
---
# <a name="create-a-lease-group"></a>Crear un grupo de arrendamientos

[!include [banner](../includes/banner.md)]

En este tema se explica cómo configurar grupos de arrendamientos. Se requieren grupos de arrendamientos para crear nuevos arrendamientos. Los libros de arrendamiento están asociados con cada grupo de arrendamientos. Los libros de arrendamiento determinan los libros predeterminados que se deben crear para cada arrendamiento. Puede asignar cuentas específicas a un grupo de arrendamientos en la página **Parámetros de publicación de arrendamientos**.

## <a name="create-a-lease-book-and-add-a-lease-group"></a>Crear un libro de arrendamiento y agregar un grupo de arrendamientos

1. Vaya a **Arrendamiento de activos \> Configuración \> Grupos de arrendamientos**.
2. En el Panel de acciones, seleccione **Nuevo** para agregar un grupo de arrendamientos. Se agrega una línea a la cuadrícula.
3. En la nueva línea, en el campo **Grupo de arrendamientos**, introduzca un valor.
4. En el campo **Descripción**, especifique un valor.

La información que acaba de introducir se agrega al campo **Grupo de arrendamientos** en la página **Agregar arrendamiento**.

## <a name="associate-a-book-with-a-lease-group"></a>Asociar un libro a un grupo de arrendamientos

Después de crear grupos de arrendamientos, puede asignar libros a cada grupo. Cuando crea un arrendamiento y lo asigna a un grupo de arrendamientos, el sistema crea un conjunto de programaciones para cada libro que está asociado con ese grupo de arrendamientos.

> [!NOTE]
> Los libros deben configurarse antes de que puedan asignarse a un grupo de arrendamientos.

1. Vaya a **Arrendamiento de activos \> Configuración \> Grupo de arrendamientos**.
2. Seleccione un grupo de arrendamientos y luego seleccione **Libros**.
3. Seleccione **Nuevo** y luego, en el campo **Tipo de libro**, seleccione el libro para asignar al grupo de arrendamientos. Puede asignar varios libros a un grupo de arrendamientos si un arrendamiento debe contabilizarse de diferentes maneras.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]