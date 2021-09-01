---
title: Parámetros para la gestión de cambios de ingeniería
description: Este tema explica cómo configurar características de administración de cambios de ingteniería para Microsoft Dynamics 365 Supply Chain Management.
author: t-benebo
ms.date: 09/28/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: benebotg
ms.search.validFrom: 2020-09-28
ms.dyn365.ops.version: Release 10.0.15
ms.openlocfilehash: dbe51e9e44cbdbf71d02e84c3a8634750f45ffa13b213fc1306a1047fb9e0b63
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2021
ms.locfileid: "6725755"
---
# <a name="engineering-change-management-parameters"></a>Parámetros para la gestión de cambios de ingeniería

[!include [banner](../includes/banner.md)]

La página **Parámetros de gestión de cambios de ingeniería** contiene parámetros de configuración que cambian el comportamiento predeterminado relacionado con la estructura del producto de lanzamiento y los procesos de gestión de cambios de ingeniería.

## <a name="open-the-engineering-change-management-parameters-page"></a>Abra la página Parámetros para la gestión de cambios de ingeniería

Para abrir la página **Parámetros de gestión de cambios de ingeniería**, vaya a **Gestión de cambios de ingeniería \> Preparar \> Parámetros de gestión de cambios de ingeniería**. Luego puede configurar los campos como se describe en las secciones restantes de este tema.

## <a name="release-control-tab"></a>Pestaña Control de liberación

La siguiente tabla describe los campos que están disponibles en la pesetañ **Control de liberación** de la página **Parámetros de gestión de cambios de ingeniería**. Estos campos afectan el proceso de estructura del producto de lanzamiento.

| Campo | Descripción |
|---|---|
| Regla de número de artículo | Seleccione cómo se debe definir el número de artículo cuando el producto se entrega a una entidad legal. Seleccione *Número de producto de ingeniería* si el número de producto en la entidad jurídica receptora debe coincidir con el número de producto en la empresa de ingeniería. Seleccione *Secuencia de número de artículo local* si el producto debe tomar el siguiente número en la secuencia numérica para los números de producto en la entidad legal receptora. |
| Regla de nombre de L. MAT | Seleccione cómo se define el nombre de la lista de materiales (BOM) cuando el producto se recibe (libera) en una entidad legal. Seleccione cualquiera *Nombre de ingeniería* o *Recibiendo el número de artículo*. |
| Regla de nombre de ruta | Seleccione cómo se debe definir el nombre de la ruta cuando la ruta de un producto se recibe (libera) en una entidad legal. Seleccione cualquiera *Nombre de ingeniería* o *Recibiendo el número de artículo*. |
| Ejecutar comprobación de L. MAT | Seleccione si se ejecutará una verificación de lista de materiales cuando el producto se reciba (libere) en una entidad legal. |
| Liberar comportamiento de L. MAT inactiva | Seleccione si un producto puede lanzarse si tiene una lista de materiales inactiva. Seleccione *Aceptar*, *Solo advertencia* o *No permitido*. |
| Liberar comportamiento de ruta inactiva | Seleccione si un producto puede lanzarse si tiene una ruta inactiva. Seleccione *Aceptar*, *Solo advertencia* o *No permitido*.|
| Aceptación del producto | Seleccione si se requiere un paso adicional para la aceptación antes de que el producto se pueda lanzar en la entidad legal. Seleccione *Manual* para agregar el paso de aceptación. En este caso, la página **Lanzamientos de productos abiertos** mostrará los productos. Seleccione *Automático* para mostrar el producto directamente en en la entidad jurídica de destino **Productos lanzados** inmediatamente después de que se lanza el producto junto con su estructura de producto de lanzamiento. |

## <a name="engineering-change-management-tab"></a>Ficha Administración de cambios de ingeniería

La siguiente tabla describe los campos que están disponibles en la pesetañ **Administración de cambios de ingeniería** de la página **Parámetros de gestión de cambios de ingeniería**. Estos ajustes afectan el proceso de gestión de cambios de ingeniería.

| Campo | Descripción |
|---|---|
| Categoría | La categoría predeterminada que se utilizará cuando se cree una solicitud de cambio de ingeniería. |
| Prioridad | La prioridad predeterminada que se utilizará cuando se cree una solicitud de cambio de ingeniería. |
| Regla de gravedad | Seleccione cómo se debe establecer la gravedad de una orden de cambio de ingeniería. Seleccione *Manual* si se espera que el usuario ingrese un valor en el campo **Gravedad**. Seleccione *Calcular* para que el sistema calcule el valor del campo **Gravedad** cuando selecciona **Calcular la gravedad** en el Panel de acciones de la orden de cambio de ingeniería. En este caso, el sistema utilizará las reglas de gravedad definidas en la página **Conjunto de reglas de gravedad**. Seleccione *Calcular automáticamente* tener el valor del campo **Gravedad** calculado y completado automáticamente de acuerdo con los conjuntos de reglas de gravedad. |
| Volver a liberar productos afectados | Este campo es aplicable cuando vuelve a lanzar productos a través de una orden de cambio de ingeniería. Puede seleccionar si se deben proponer todos los productos o solo los productos afectados en la caja de diálogo **Lanzamientos**. |
| Niveles de L. MAT para liberar | La profundidad del nivel de la lista de materiales para liberar. Si la lista de materiales tiene más niveles (es decir, si es más profundo) que el valor que se especifica aquí, solo se liberarán los niveles superiores al valor especificado. |


[!INCLUDE[footer-include](../../includes/footer-banner.md)]