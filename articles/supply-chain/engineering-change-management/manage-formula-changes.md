---
title: Gestionar cambios en fórmulas y sus componentes.
description: Este tema describe cómo realizar la gestión de fórmulas y gestionar los cambios para procesar los datos maestros de fabricación.
author: t-benebo
ms.date: 05/19/2021
ms.topic: article
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: benebotg
ms.search.validFrom: 2021-05-19
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: 31953fd29c471e52bd63dbb02c20f5f224c3cae2
ms.sourcegitcommit: fcb8a3419e3597fe855cae9eb21333698518c2c7
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/09/2022
ms.locfileid: "8103053"
---
# <a name="manage-changes-in-formulas-and-their-ingredients"></a>Gestionar cambios en fórmulas y sus componentes.

[!include [banner](../includes/banner.md)]

Si está utilizando las capacidades de fabricación de procesos de Microsoft Dynamics 365 Supply Chain Management, también puede utilizar las capacidades de administración de fórmulas relacionadas para administrar los siguientes cambios:

- **Fórmula y elementos de planificación:** gestione los cambios en los componentes de las fórmulas y sus coproductos y subproductos.
- **Coproductos y subproductos:** edite cantidades y otra información de los coproductos y subproductos en una fórmula.
- **Artículos de peso capturado:** gestione los cambios en los artículos con peso capturado.

## <a name="turn-this-feature-on-or-off"></a>Activar o desactivar esta característica

La funcionalidad descrita en este tema requiere que se activen las características *Administración de cambios de ingeniería* y *Administrar cambios en fórmulas y sus componentes* en su sistema. Para obtener detalles sobre cómo activar o desactivar estas características, consulte [Información general de la gestión de cambios de ingeniería](product-engineering-overview.md).

## <a name="feature-naming-conventions"></a>Convenciones de nomenclatura de funciones

En la documentación y la interfaz de usuario (UI) de Supply Chain Management, la funcionalidad de gestión de cambios se suele denominar *gestión de cambios de ingeniería*, y los productos gestionables generalmente se denominan *productos de ingeniería*. Aunque esta terminología no suele asociarse con la gestión de fórmulas para la fabricación de procesos, debería pensar en la gestión de cambios de ingeniería como una simple gestión de cambios y debería pensar en los productos de ingeniería como productos versionados.

## <a name="work-with-formula-change-management-features"></a>Trabajar con funciones de administración de cambios de fórmulas

La siguiente lista resume cómo se aplican las funciones de administración de cambios de ingeniería a la administración de fórmulas. También proporciona enlaces a más información. Dado que la gestión de cambios de fórmula aprovecha las funciones de gestión de cambios de ingeniería, debe aprender cómo funciona la gestión de cambios de ingeniería en general, de modo que pueda utilizarla para gestionar sus fórmulas y sus componentes.

- **Gestión centralizada de datos de productos**: configure una organización que, a través de un proceso de lanzamiento administrado, garantice que los datos de productos precisos y relevantes estén disponibles para los usuarios de toda la empresa. Para más información, vea [Empresas de ingeniería y reglas de propiedad de datos](engineering-org-data-ownership-rules.md).
- **Control de versiones del producto**: realice un seguimiento de los cambios en los productos a través de las versiones del producto y controle el producto en todas las etapas de la cadena de suministro. De esta manera, puede realizar un seguimiento de los cambios en sus formulaciones. Para más información, vea [Versiones de ingeniería y categorías de productos de ingeniería](engineering-versions-product-category.md).
- **Gestión del ciclo de vida del producto**: administre la visibilidad de los datos del producto en toda la organización y controle la disponibilidad de las versiones del producto en cada etapa de la cadena de suministro. Tiene un control detallado sobre cuándo se puede usar una versión de producto en procesos comerciales específicos y puede crear sus propios estados de ciclo de vida para adaptarse a sus necesidades comerciales. Para más información, vea [Estados y transacciones del ciclo de vida del producto](product-lifecycle-state-transactions.md).
- **Gestión de cambios de fórmula**: los usuarios de su organización pueden solicitar cambios en las fórmulas. Utilice órdenes de cambio para evaluar y documentar el impacto de los cambios propuestos. Agregue flujos de trabajo para administrar el proceso de cambio y el lanzamiento de nuevas versiones del producto y su fórmula. Para más información, ver [Gestionar cambios en productos de ingeniería](engineering-change-management.md).
- **Control de disponibilidad** : use las verificaciones del sistema y la guía del usuario (cuestionarios y listas de verificación) para asegurarse de que todos los datos requeridos del producto se ingresen por completo antes de que se publique el producto. Para obtener más información, consulte [Preparación del producto](product-readiness.md).
- **Funcionalidad de lanzamiento de productos mejorada**: versiones completamente definidas de un producto y su fórmula de una organización (entidad legal) a otras entidades legales. Incluso puede decidir si la información del producto debe revisarse o editarse antes de su publicación. Para obtener más información, consulte [Liberar estructuras de productos](release-product-structure.md).

Tenga en cuenta que la mayoría de los temas a los que se vinculan en la lista anterior proporcionan ejemplos que se basan en listas de materiales (BOM). Sin embargo, las fórmulas funcionan de manera similar. A continuación, se muestran algunos conceptos adicionales que es útil conocer cuando utiliza la gestión de cambios (o solo la gestión de cambios de fórmulas) para administrar fórmulas y listas de materiales:

- Para cada [categoría de ingeniería de producto](engineering-versions-product-category.md), puede especificar el tipo de producción (lista de materiales, fórmula o artículo de planificación). También puede especificar si se requiere soporte de peso capturado para los productos que usan esa categoría.
- Los coproductos y subproductos no son productos de ingeniería. Por lo tanto, no están versionados. Si debe cambiarlos, simplemente cree un nuevo producto. Este enfoque facilita el mantenimiento.
- Puede administrar artículos finales que son listas de materiales y que tienen artículos de fórmula secundarios. La funcionalidad funcionará para cualquier combinación de listas de materiales que contengan fórmulas y / o fórmulas que contengan listas de materiales.
