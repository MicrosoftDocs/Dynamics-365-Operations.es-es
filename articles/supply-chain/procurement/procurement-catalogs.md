---
title: Visión general de catálogos de compras
description: Este artículo describe, en un nivel superior, la manera en que los responsables de compras pueden configurar y mantener catálogos de compras. Los catálogos de compras definen los artículos y servicios que los empleados de las empresas puedan pedir para su uso interno.
author: RichardLuan
manager: tfehr
ms.date: 07/25/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CatProcureCatalogEdit, CatProcureCatalogListPage, CatDisplayProductRelationAdd
audience: Application User
ms.reviewer: kamaybac
ms.custom: 2214
ms.assetid: 2f3e0441-414d-402b-b28b-7ab0d650d658
ms.search.region: Global
ms.author: riluan
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: fcbe55adfc834b6170ca4c2a242d6bff5264ac8a
ms.sourcegitcommit: deac22ba5377a912d93fe408c5ae875706378c2d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/16/2021
ms.locfileid: "5019788"
---
# <a name="procurement-catalogs-overview"></a>Visión general de catálogos de compras

[!include [banner](../includes/banner.md)]

Este artículo describe, en un nivel superior, la manera en que los responsables de compras pueden configurar y mantener catálogos de compras. Los catálogos de compras definen los artículos y servicios que los empleados de las empresas puedan pedir para su uso interno.

Los encargados de compras pueden crear y mantener los catálogos de los artículos y servicios que se pueden comprar para uso interno en una organización. Una vez configurados los catálogos, los empleados de las empresas pueden crear solicitudes de compra para pedirlos. Los catálogos se pueden usar para aplicar directivas de compra, de modo que los empleados puedan pedir solo los artículos y servicios que se permiten para la entidad jurídica de compra. Cuando se crea un catálogo de compras, deberá tener en cuenta las siguientes tareas:

-   Configure la jerarquía de categorías de compras antes de crear el catálogo.
-   Determine qué productos desea que puedan pedir los empleados. Puede mostrar u ocultar productos específicos en un nodo del catálogo o puede mostrar u ocultar todos los productos en un nodo.
-   Determine cuántos catálogos de compras necesita. El acceso al catálogo de compras viene determinado por la regla de directiva del catálogo configurada para la entidad jurídica y la unidad operativa a la que se ha asignado un empleado.

Varios factores determinan los productos que los empleados pueden solicitar y las categorías de compras que pueden usar al crear solicitudes de compra:

-   La regla de directivas de acceso de la categoría en la directiva de compras determina qué categorías de compras están disponibles en la solicitud de compra. Si no se define ninguna regla, todas las categorías de compras están disponibles.
-   Los empleados solo pueden solicitar un producto si se encuentra en el catálogo de compras activo para la organización y si está en un nodo habilitado y no oculto. El producto también deberá estar en una categoría a la que un empleado concreto tiene acceso de acuerdo con la regla de directivas de acceso de categorías.
-   La regla de directivas de catálogo especifica el catálogo que se usa. Si no se define ninguna regla de directivas de catálogo, la regla de acceso de categorías solo determina los productos que un empleado puede pedir en la solicitud.

## <a name="prerequisites"></a>Requisitos previos
En la tabla siguiente se describen las tareas que se deben completar para que un responsable de compras pueda crear un catálogo de compras:

| Tarea                                                | Función               | Descripción                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                             |
|-----------------------------------------------------|--------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Configure una jerarquía de categorías de compras.            | Director de compras | Las jerarquías de categorías de compras clasifican los artículos o las transacciones para la creación de informes y análisis. Si usa una jerarquía de categorías de compras, las empresas administrarán de forma estratégica las categorías, los productos, los proveedores y otros factores de compras desde una ubicación central. Se define una única jerarquía de categorías de compras para una organización completa. El catálogo se basa en la jerarquía de categorías de compras: las categorías de la jerarquía se convierten en nodos en el catálogo. En el catálogo se incluyen los proveedores y los productos. |
| Agregue proveedores y productos a las categorías de compras. | Director de compras | Una vez creada la jerarquía de categorías de compras de la organización, cada una de las categorías de compras se podrá asociar a proveedores específicos, productos, etc. Estas asociaciones se copian automáticamente en el catálogo.                                                                                                                                                                                                                                                                                           |

## <a name="setting-up-a-catalog"></a>Configuración de un catálogo
Una vez cumplidos los requisitos previos, puede configurar los catálogos. Puede crear un catálogo que use toda la organización o varios catálogos que usen las distintas divisiones de la organización. Si crea un catálogo para toda la organización, el acceso al catálogo está controlado por las reglas de directiva de compras.  

El catálogo define qué productos están disponibles cuando se crean las solicitudes de compra, pero puede usar reglas de directivas de acceso de categorías para aplicar restricciones adicionales. Dado que los nodos de un catálogo son categorías de compras, se pueden eliminar con una regla de directivas de acceso de categorías. En este caso, los productos de esa categoría no están disponibles para que los empleados los usen en las solicitudes. Defina las reglas de directivas de acceso de categorías en la página **Directivas de compra**. En la tabla siguiente se describen las tareas que se deben completar para configurar un catálogo.

| Tarea                                                   | Función             | Descripción                                                                                                                                                                                                                                                                                                                  |
|--------------------------------------------------------|------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Cree un nuevo catálogo.                                  | Agente de compras | Al crear un catálogo, debe especificar un nombre y una descripción para el catálogo. También define si el catálogo se actualiza de forma manual o automática, y especificar el propietario del catálogo.                                                                                                                                      |
| Controle si los productos están disponibles en el catálogo. | Agente de compras | Dado que los productos se heredan de las categorías de compras, todos aparecen en los nodos adecuados del catálogo. Puede controlar si todos los productos de un nodo se ocultarán o se mostrarán cuando el catálogo se use en una solicitud de compra. También puede controlar si los productos individuales de un nodo se ocultarán o se mostrarán. |
| Publique el catálogo.                                   | Agente de compras | Para que un catálogo esté disponible para que los empleados lo usen en una solicitud, debe definir una regla de directivas de catálogo para el catálogo, definir el estado del catálogo como **Activo** y publicar el catálogo. También puede desactivar los catálogos que ya no desee tener a disposición de los usuarios.                                              |

Las actualizaciones se publican de forma manual o automática en función de la opción seleccionada para el catálogo en el campo **Tipo de actualización predeterminada** en la página **Catálogos**. Los siguientes tipos de actualización predeterminados están a disposición de los catálogos:

-   **Dinámica**: el catálogo se actualiza automáticamente siempre que haya cambiado.
-   **Estática**: los catálogos se deben actualizar de forma manual.
-   **Ambas**: si el catálogo incluye categorías de productos que tienen el tipo de actualización predeterminada **Estática**, se debe actualizar manualmente cuando se actualizan estas categorías. Si el catálogo incluye categorías de productos que tienen el tipo de actualización predeterminada **Dinámica**, se actualiza automáticamente siempre que haya cambiado.


<a name="additional-resources"></a>Recursos adicionales
--------

[Configurar una jerarquía de categorías de compras](tasks/set-up-procurement-category-hierarchy.md)



