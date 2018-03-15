---
title: "Claves de configuración y entidades de datos"
description: "Este tema describe la relación entre las claves de configuración y las entidades de datos en Microsoft Dynamics 365 for Finance and Operations, Enterprise Edition."
author: Sunil-Garg
manager: AnnBe
ms.date: 01/01/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-platform
ms.technology: 
audience: Application user
ms.reviewer: margoc
ms.search.scope: Operations
ms.custom: 25341
ms.assetid: 8e214c95-616b-4ee1-b5a4-fa5ce5147f2c
ms.search.region: Global
ms.author: sunilg
ms.search.validFrom: 2018-01-01
ms.dyn365.ops.version: Platform update 13
ms.translationtype: HT
ms.sourcegitcommit: af7f9a373496eee4df354d5dd9e5a25c51317c43
ms.openlocfilehash: f9ea932b48d57baad4b4ab66069191ebd7cbbd6c
ms.contentlocale: es-es
ms.lasthandoff: 02/27/2018

---

# <a name="configuration-keys-and-data-entities"></a>Claves de configuración y entidades de datos

[!include[banner](../includes/banner.md)]

Antes de usar entidades de datos para importar o exportar datos, le recomendamos que determina primero el impacto de las claves de configuración en las entidades de datos que tiene previsto utilizar. 

Para obtener más información acerca de las claves de configuración en Finance and Operations, vea el [Informe de códigos de licencia y claves de configuración](../sysadmin/license-codes-configuration-keys-report.md).

### <a name="configuration-key-assignments"></a>Asignaciones de clave de configuración
Las claves de configuración se pueden asignar a uno o todos los artefactos siguientes.
-   Entidades de datos
-   Tablas usadas como orígenes de datos
-   Campos de tabla
-   Campos de entidad de datos

La siguiente tabla resume cómo los valores de la clave de configuración en los distintos artefactos que subyacen a un objeto cambian el comportamiento esperado del objeto.

| Valor de clave de configuración en entidad de datos | Valor de clave de configuración en tabla | Valor de clave de configuración en campo de tabla | Clave de configuración en campo de entidad de datos | Comportamiento esperado                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                         |
|-----------------------------------|-----------------------------|-----------------------------------|---------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Deshabilitadas                          | No evaluado               | No evaluado                     | No evaluado                   | Si la clave de configuración para la entidad de datos está deshabilitada, la entidad de datos no será funcional. No importa si las claves de configuración en las tablas y campos subyacentes están habilitados o deshabilitados.                                                                                                                                                                                                                                                                                                                                          |
| Habilitado                           | Deshabilitadas                    | No evaluado                     | No evaluado                   | Si la clave de configuración para una entidad de datos está habilitada, el marco de gestión de datos comprueba la clave de configuración en cada una de las tablas subyacentes. Si la clave de configuración para un tabla está deshabilitada, esta tabla no estará disponible en la entidad de datos para uso funcional. Si se deshabilita la clave de configuración de una tabla, los valores de la clave de configuración de la tabla y la entidad de datos no se evalúan. Si la tabla principal de la entidad tiene su clave de configuración deshabilitada, el sistema actuará como si se deshabilitase la clave de configuración de la entidad. |
| Habilitado                           | Habilitado                     | Deshabilitadas                          | No evaluado                   | Si la clave de configuración para una entidad de datos está habilitada, y se habilitan las claves de configuración de las tablas subyacentes, el marco de gestión de datos comprobará la clave de configuración en los campos de las tablas. Si la clave de configuración para un campo está deshabilitada, ese campo no estará disponible en la entidad de los datos para un uso funcional incluso si el campo de la entidad de datos correspondiente tiene la clave de configuración habilitada.                                                                                                                                   |
| Habilitado                           | Habilitado                     | Habilitado                           | Deshabilitadas                        | Si la clave de configuración está habilitada en los otros niveles, pero la clave de configuración del campo de la entidad no está habilitada, el campo no estará disponible para su uso en la entidad de datos.                                                                                                                                                                                                                                                                                                                                                                          |

> [!NOTE]
> Si una entidad tiene otra entidad como origen de datos, la semántica anterior se aplica de forma recursiva.

### <a name="entity-list-refresh"></a>Actualización de lista de entidades
Cuando se actualiza la lista de entidades, el marco de gestión de datos crea los metadatos de la clave de configuración para el uso del tiempo de ejecución. Estos metadatos se generan mediante la lógica descrita anteriormente. Le recomendamos encarecidamente que espere a que la actualización de la lista de entidades se complete antes de usar trabajos y entidades en el marco de gestión de datos. Si no espera, puede que no se actualicen los metadatos de la clave de configuración y podrían provocar resultados inesperados. Cuando se está actualizando la lista de entidades, el mensaje siguiente se muestra en la página de lista de entidades.

![Actualización de lista de entidades](./media/Entity_refresh_list.png)

### <a name="data-entity-list-page"></a>Página de lista de entidad de datos
La página de lista de entidad de datos en el espacio de trabajo de Gestión de datos muestra los valores de la clave de configuración para las entidades. Comience desde esta página para comprender el impacto de las claves de configuración en la entidad de datos.
Esta información se muestra con los metadatos que se generan durante la actualización de la entidad. La columna de la clave de configuración muestra el nombre de la clave de configuración que está asociada a la entidad de datos. Si esta columna se deja en blanco significa que no hay clave de configuración asociada a la entidad de datos. La columna de estado de la clave de configuración muestra la estado de la clave de configuración. Si tiene una marca de verificación, significa que la clave está habilitada. Si está en blanco, significa que la clave está deshabilitada o que no hay ninguna clave asociada.

![Página de lista de entidades](./media/Data_entity_list_page.png)

### <a name="target-fields"></a>Campos objetivo
El siguiente paso es explorar en la entidad de datos para ver el impacto de las claves de configuración en las tablas y los campos. El formulario de campos objetivo para una entidad de datos muestra la clave de configuración y la información del estado de la clave para las tablas y campos en la entidad de datos.  Si la propia entidad de datos tiene su clave de configuración deshabilitada, se muestra un mensaje de advertencia que indica que las tablas y los campos en los formularios de campos objetivo para esta entidad no estarán disponibles en absoluto independientemente de su estado de clave de configuración.

![Campos objetivo](./media/Target_fields_1.png)

### <a name="child-entities"></a>Entidades secundarias 
Algunas entidades tienen otras entidades como orígenes de datos, o bien son entidades de datos compuestas: la información de clave de configuración para estas entidades se muestra en el formulario de entidades secundario. Utilice este formulario de forma similar a la página de la lista de entidades descrita anteriormente. El formulario de campos objetivo par la entidad secundaria también se comporta como se describe anteriormente.

![Campos objetivo](./media/Target_fields_2.png)

### <a name="using-data-entities"></a>Uso de entidades de datos
Tras comprender el impacto completo, en su caso, de las claves de configuración en las entidades de datos que desee utilizar, ahora puede seguir usando las entidades de datos agregándolas a los proyectos de datos. 

### <a name="run-time-validations-for-configuration-keys"></a>Validaciones de tiempo de ejecución para las claves de configuración
Mediante los metadatos de la clave de configuración creados durante la lista de actualización de entidades, las validaciones del tiempo de ejecución se llevan a cabo en los siguientes casos de uso.

-   Cuando una entidad de datos se agrega a un trabajo

-   Cuando los clics del usuario se ‘validan‘ en la lista de entidades

-   Cuando el usuario carga un paquete de datos en un proyecto de datos

-   Cuando el usuario carga una plantilla en un proyecto de datos

-   Cuando se carga un proyecto de datos existente

-   Cuando se carga una plantilla en un proyecto de datos

-   Antes de que se ejecute el trabajo de exportación/importación (lote, sin lote, recurrente, OData)

-   Cuando el usuario genera la asignación

-   Cuando el usuario asigna campos en la interfaz de usuario de asignación

-   Cuando el usuario agrega solo 'campos importables'


### <a name="managing-configuration-key-changes"></a>Gestionar cambios de claves de configuración
Cada vez que actualice las claves de configuración en la entidad, tabla o nivel de campo, debe actualizarse la lista de entidades en el marco de gestión de datos. Este proceso garantiza que el marco recoja los últimos valores de la clave de configuración. Hasta que se actualice la lista de entidades, aparecerá el siguiente mensaje de advertencia en la página de lista de entidades. Los cambios de clave de configuración actualizados surtirán efecto inmediatamente después de que se actualice la lista de entidades. Le recomendamos que valide los proyectos y trabajos de datos existentes para asegurarse de que funcionan como se espera después de que se pongan en vigor los cambios de claves de configuración.

![Campos objetivo](./media/Target_fields_3.png)


