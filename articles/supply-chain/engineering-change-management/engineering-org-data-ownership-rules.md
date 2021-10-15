---
title: Compañías de ingeniería y reglas de propiedad de datos
description: Este tema explica cómo puede utilizar una o más empresas de ingeniería para garantizar que los datos maestros de los productos se creen y mantengan de forma centralizada. Una empresa de ingeniería representa a la empresa que posee los productos de ingeniería y sus datos relevantes para la ingeniería.
author: t-benebo
ms.date: 09/28/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: EngChgEngineeringOrganization
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: benebotg
ms.search.validFrom: 2020-09-28
ms.dyn365.ops.version: 10.0.15
ms.openlocfilehash: 1a05ad1a9d24239e2659c1ffecc21e5e186b1e96
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/29/2021
ms.locfileid: "7572922"
---
# <a name="engineering-companies-and-data-ownership-rules"></a>Compañías de ingeniería y reglas de propiedad de datos

[!include [banner](../includes/banner.md)]

## <a name="engineering-companies-and-operational-companies"></a>Empresas de ingeniería y empresas operativas

Para asegurarse de que los datos maestros de los productos se creen y mantengan de forma centralizada, puede utilizar uno o más *empresas de ingenieria*. Una empresa de ingeniería posee los productos de ingeniería y sus datos relevantes para la ingeniería. Siempre está conectado a (basado en) una *entidad legal* existente, que también es una empresa. A través de esta conexión, el sistema establece un punto de entrada central para todos los datos relevantes de ingeniería para productos de ingeniería en la empresa de ingeniería. En este punto de entrada central, se crean productos de ingeniería y se mantienen los datos relevantes para la ingeniería. A partir de él, los productos de ingeniería y los datos relevantes para la ingeniería se enviarán a *empresas operativas*, que son otras entidades legales. (Para obtener más información sobre la gestión de versiones, consulte [Liberar estructuras de productos](release-product-structure.md) .) Estas empresas operativas utilizarán los datos de ingeniería tal como han sido diseñados por la empresa de ingeniería. Todos los datos logísticos son mantenidos localmente por cada empresa de ingeniería y empresa operativa.

Para crear una empresa de ingeniería, vaya a **Gestión de cambios de ingeniería \> Preparar \> Organizaciones de ingeniería**. Seleccione **Nuevo**, introduzca un nombre para la empresa de ingeniería y seleccione la empresa existente (entidad jurídica) en la que se basa.

Si se está integrando con sistemas externos de gestión del ciclo de vida del producto (PLM), debe crear una unidad de negocio (tipo de empresa) que se convertirá en una empresa externa.

## <a name="engineering-product-categories-and-engineering-companies"></a>Categorías de producto de ingeniería y empresas de ingeniería

Las *categorías de productos de ingeniería* ayudan a garantizar que los productos de ingeniería se creen de acuerdo con las reglas comerciales de su empresa y se comporten según sea necesario. Para obtener más información sobre categorías de productos de ingeniería, consulte [Versiones de ingeniería y categorías de productos de ingeniería](engineering-versions-product-category.md).

Cada categoría de productos de ingeniería pertenece a una empresa de ingeniería específica y solo puede crear productos que pertenezcan a esa empresa. Asimismo, el derecho a mantener un producto de ingeniería también pertenece a la empresa que está asociada con la categoría de productos de ingeniería de ese producto.

## <a name="data-that-is-owned-by-the-engineering-company"></a>Datos que son propiedad de la empresa de ingeniería

Dado que la empresa de ingeniería posee los datos relevantes para la ingeniería, controla los siguientes procesos:

- **Creación de productos de ingeniería:** Cada empresa de ingeniería solo puede crear nuevos productos de ingeniería que se basen en una categoría de productos de ingeniería de su propiedad. En algunos casos, las empresas operativas mantienen sus propios datos locales relacionados con esos productos.
- **Creación de versiones de ingeniería:** Cuando una empresa crea un nuevo producto de ingeniería, el sistema crea automáticamente una versión de ingeniería inicial para él. Solo la empresa de ingeniería propietaria podrá crear nuevas versiones de ese producto.
- **Creación y mantenimiento de atributos de ingeniería:** Cuando una empresa crea un nuevo producto de ingeniería, el sistema añade automáticamente sus atributos. Solo la empresa de ingeniería propietaria podrá crear y mantener los valores para esos atributos. Para obtener más información sobre los atributos de ingeniería, consulte [Atributos de ingeniería y búsqueda de atributos de ingeniería](engineering-attributes-and-search.md).
- **Creación y mantenimiento de listas de materiales (BOM) que están conectadas a las versiones de ingeniería:** La empresa de ingeniería propietaria puede conectar directamente una lista de materiales a una versión de producto de ingeniería. Cuando estas listas de materiales se entregan a otras entidades legales, los cambios en los datos de ingeniería de las listas de materiales se limitan de las siguientes maneras:

    - La empresa operativa no puede eliminar las líneas de lista de materiales liberadas.
    - Los campos de ingeniería en las líneas de la lista de materiales son de solo lectura para la empresa operativa. Todos los demás campos son campos de implementación logística y pueden ser editados por la empresa operativa.
    - La empresa operativa puede agregar líneas de lista de materiales a la misma lista de materiales. De esta manera, puede agregar adiciones locales, como materiales de empaque o fluidos lubricantes.
    - La empresa operativa puede agregar una lista de materiales local completamente nueva. Este cambio puede ser necesario en casos en los que, por ejemplo, no se proporcione una lista de materiales durante el lanzamiento. La empresa operativa es propietaria y mantiene estas listas de materiales locales. Para obtener más información sobre la gestión de versiones, consulte [Liberar estructuras de productos](release-product-structure.md).
    - Todas las listas de materiales locales y las líneas de listas de materiales se conservan cuando la empresa de ingeniería actualiza su lista de materiales.

- **Creación y mantenimiento de rutas que están conectadas a las versiones de ingeniería:** La empresa de ingeniería puede conectar directamente una ruta a cada versión de ingeniería. Cuando estas rutas se entregan a otras entidades legales, los cambios en los datos de las rutas se limitan de las siguientes maneras:

    - Las otras entidades legales no pueden eliminar los datos de ingeniería en las rutas.
    - Las otras entidades legales pueden agregar operaciones a la ruta. De esta manera, pueden agregar pasos de ruta local.
    - Las empresas operativas pueden agregar rutas locales completamente nuevas. Este cambio puede ser necesario si, por ejemplo, no ha incluido rutas durante el lanzamiento. Las empresas operativas poseen y mantienen estas rutas locales. Para obtener más información sobre la gestión de versiones, consulte [Liberar estructuras de productos](release-product-structure.md).
    - Todos los cambios que se realizan localmente se conservan cuando las actualizaciones de la empresa de ingeniería se publican nuevamente en las rutas.

- **Creación y mantenimiento de documentos de ingeniería:** La empresa de ingeniería puede adjuntar documentos de ingeniería a cada versión de ingeniería.

    - Cuando estos documentos se entregan a otras entidades legales, los documentos están protegidos de ser eliminados por la empresa operativa.
    - Otras entidades legales pueden agregar documentos locales completamente nuevos. La empresa operativa es propietaria y mantiene estos documentos locales.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]