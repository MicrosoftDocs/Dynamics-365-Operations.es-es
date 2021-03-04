---
title: Crear un activo fijo
description: En este tema se explica cómo crear un nuevo registro de activo fijo desde la página de lista de activos fijos.
author: moaamer
manager: AnnBe
ms.date: 07/01/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: AssetTable, AssetBook
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 481bdb55b813dad5366f382ae35d8345b0e67d9f
ms.sourcegitcommit: a9efbd69f2670fd6ba0ad0babf304fc206d01249
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/06/2020
ms.locfileid: "4447833"
---
# <a name="create-a-fixed-asset"></a>Crear un activo fijo

[!include [banner](../../includes/banner.md)]

En este tema se explica cómo crear un nuevo registro de activo fijo desde la página de lista **Activos fijos**.

El sistema asigna el número de activo, basado la secuencia numérica que se asigna al grupo de activos fijos. Si utiliza la plantilla de activos fijos para importar activos a través del complemento de Microsoft Excel, o si utiliza otro trabajo de importación, el sistema creará automáticamente registros de activos fijos e incrementará el número de activo.

Para crear manualmente un registro de activo, siga estos pasos.

1. Vaya a **Panel de navegación \> Módulos \> Activos fijos \> Activos fijos \> Activos fijos**.
2. En el **Panel de acciones**, seleccione **Nueva**.
3. En el campo **Grupo de activos fijos**, escriba o seleccione un valor. Se usará el valor predeterminado para **Número** si ha habilitado la funcionalidad **Enumerar automáticamente los activos** fijos en los **parámetros de activos fijos** y en el **grupo de activos fijos**. Si no lo ha hecho, debe escribir un número único para identificar el activo fijo.
4. En el campo **Nombre**, escriba un valor. Especifique la información adicional que su empresa necesite para este activo.
5. En el **Panel de acciones**, seleccione **Libros**.
6. En el campo **Fecha de adquisición**, escriba una fecha.
7. En el campo **Precio de adquisición**, escriba un número.

    - Introduzca la la información adicional que su empresa necesite para este libro.
    - Introduzca la información adicional que necesite su empresa para los libros restantes.

8. Cierre la página.

También puede importar activos fijos a través del complemento de Excel o ejecutando un trabajo de importación desde el espacio de trabajo **Administración de datos**. Antes de ejecutar la importación, especifique los valores de los campos obligatorios en la plantilla.

Si no definió el número de activo fijo en la plantilla del complemento de Excel o en Administración de datos, el sistema crea un número de activo fijo para cada activo importado e incrementa automáticamente la secuencia numérica para cada uno. Sin embargo, si importa activos y define números de activos en la plantilla, el sistema **no** incrementa automáticamente la secuencia numérica. En este caso, es posible que un administrador tenga actualizar manualmente la secuencia numérica. Si definió el número de activo fijo en la plantilla del complemento de Excel, el sistema utiliza el número de activo fijo definido e incrementa la secuencia numérica.

> [!NOTE]                                                                                                         
> Después de contabilizar la depreciación, los campos **Puesto en servicio** y **Fecha de ejecución de la depreciación** se bloquearán en la página **Libro**. Además, ninguno de los campos se actualizará desde la entidad de datos.

> [!WARNING]
> El registro de activos fijos no se eliminará si las transacciones se registraron en el libro asociado o si el activo fijo recién creado se introduce en una línea de diario pero no se registra. 


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]