---
title: Ubicaciones del inventario
description: Las ubicaciones de inventario se usan con el almacenamiento básico (WMS I) para determinar dónde se almacenan los artículos y dónde se seleccionan los artículos desde un almacén de WMS I.
author: perlynne
manager: tfehr
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WMSLocation, WMSBlockingCause
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: 2134
ms.assetid: 69bf6922-4151-447f-b678-4ba95637f54c
ms.search.region: Global
ms.search.industry: Distribution
ms.author: perlynne
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 009106327db971a7fc43a2a3ad233f16eb7ff620
ms.sourcegitcommit: 8cbaeb6443ce47a4c4bc02b5e1a1212eb0056b38
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/22/2020
ms.locfileid: "3829738"
---
# <a name="inventory-locations"></a>Ubicaciones del inventario

[!include [banner](../includes/banner.md)]

Las ubicaciones de inventario se usan con el almacenamiento básico (WMS I) para determinar dónde se almacenan los artículos y dónde se seleccionan los artículos desde un almacén de WMS I.

Este tema se aplica a las características en el módulo de Gestión del inventario. No se aplica a las características en el módulo de Administración de almacenes.

El término ubicación hace referencia al lugar en el que se almacenan los artículos y del que se extraen.

Para cada ubicación, también se puede especificar el lugar en el que se inserta el artículo. De forma predeterminada, coinciden. Los artículos normalmente se insertan y extraen de la misma parte una ubicación, aunque no siempre. Por ejemplo, los artículos almacenados en estanterías de almacenamiento se insertan desde un pasillo y se extraen desde otro. La entrada principal la proporciona el nombre de la ubicación, que normalmente se determina por sus coordenadas: almacén, pasillo, estantería, balda y hueco. Este nombre o id. se puede especificar manualmente o generarse desde las coordenadas de la ubicación (por ejemplo, 01-02-03-4 para el pasillo 1, la estantería 2, la balda 3 y el hueco 4 en la página Ubicaciones de inventario).
Propiedades de ubicación

Una ubicación tiene las siguientes características:
-   Tamaño (alto, ancho, profundidad y, por tanto, volumen)
-   Almacén, pasillo, estantería, balda y posición en hueco
-   Tipo de ubicación (ubicación de almacenaje, ubicación de picking, muelle de llegada, muelle de salida, ubicación de entrada de producción, ubicación de inspección o supermercado kanban)

El texto de comprobación puede usarse en sistemas en línea para comprobar si el operador ha seleccionado la ubicación correcta para un artículo concreto. Este texto de comprobación se puede crear manualmente o de forma predeterminada.

## <a name="sort-codes"></a>Códigos de ordenación
Use códigos de ordenación para optimizar la gestión de líneas de selección, que detallan la información necesaria para los artículos de selección desde el inventario, incluido el pedido de selección. Los códigos de ordenación se pueden especificar por pasillo y otras coordenadas, o bien puede asignarse manualmente para la ubicación.

## <a name="blocked-locations"></a>Ubicaciones bloqueadas
Ocasionalmente, quizás desee indicar que una ubicación está bloqueada durante un período de tiempo, por ejemplo, para permitir las reparaciones. En otras ocasiones, es posible desee indicar el bloqueo de solo la entrada o solo la salida.

## <a name="tree-structure"></a>Estructura en árbol

En la página Ubicaciones de inventario, puede ver la configuración de almacén en una estructura en árbol basada en las coordenadas de ubicaciones de inventario, en un formato de representación definido.

## <a name="maintain-inventory-locations-via-the-warehouse-form"></a>Mantener las ubicaciones de inventario mediante el formulario de almacén

Es posible copiar las ubicaciones de un almacén a otro y crear ubicaciones a través de un asistente. Antes de ejecutar el asistente debe asegurarse de haber definido los nombres de la ubicación predeterminada en la página Almacén.



<a name="additional-resources"></a>Recursos adicionales
--------

[Creación de un nuevo diseño de almacén](tasks/create-new-warehouse-layout.md)
