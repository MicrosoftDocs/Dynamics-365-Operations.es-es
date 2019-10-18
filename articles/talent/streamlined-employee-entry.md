---
title: Entrada y navegación de empleados optimizadas
description: La entrada de datos de los trabajadores en Dynamics 365 Talent se ha ampliado para permitir la entrada rápida para todos los empleados, del pasado, activos o del futuro. El modelo de navegación simplificado/consolidado se ha actualizado para buscar más rápidamente la información relacionada y ver y crear las actualizaciones necesarias.
author: andreabichsel
manager: AnnBe
ms.date: 08/20/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Core, Operations, Talent
ms.custom: 15681
ms.assetid: 6aee97ac-29f7-4b3c-8aa1-c65810de3090
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Talent October 2019 update
ms.openlocfilehash: 40bbb8429355fa18fe12c7cf56f8d58f19766cad
ms.sourcegitcommit: 434dd21450bddcd891aba0555b9853d9ba0afb6f
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/23/2019
ms.locfileid: "2009431"
---
# <a name="streamlined-employee-entry-and-navigation"></a>Entrada y navegación de empleados optimizadas

[!include [banner](includes/banner.md)]

Dynamics 365 Talent permite la especificación eficaz de datos del empleado y del empleo. Puede actualizar rápidamente la información del historial de trabajo para empleados y contratistas del pasado, activos, y del futuro.

También puede permitir una experiencia simplificada de navegación para buscar rápidamente información relacionada y realizar los cambios necesarios. Esta funcionalidad ya está disponible en los entornos de espacio aislado. Para activar esta característica, vaya a **Administración del sistema > vinculos > configuración > Parámetros del sistema > características de vista previa**. Seleccione **Formulario y navegación de trabajador mejorado**. Esto habilitará estos cambios para todos los usuarios. Puede desactivar esta opción en cualquier momento.

## <a name="view-options"></a>Opciones de vista

Puede usar **Opciones de la vista** en el formulario Trabajador para seleccionar cualquier combinación de empleados y de contratistas de una sola lista. Estas opciones le permiten ver trabajadores de entidades jurídicas o de la entidad jurídica a la que está conectadod actualmente. También puede ver los trabajadores activos, pendientes, y que yan salido, y puede limitar los resultados en función del tipo de trabajador (contratista o empleado.) Si está habilitada la seguridad avanzada, sólo verá estos empleados y contratistas en las entidades jurídicas a las que tiene acceso.

Las columnas de la vista de lista cambian en función de sus selecciones. Por ejemplo, al visualizar los empleados que han salido, la fecha final y los códigos de motivo muestran como columnas adicionales en la lista. 

[![Opciones de vista](./media/Worker-view-option.png)](./media/worker-view-option.png)

## <a name="navigation-and-banner"></a>Navegación y banner

Un banner muestra información clave para cada trabajador. El banner para trabajadores activos muestra los siguientes campos:

- **Cargo**
- **Departamento**
- **Tipo de puesto**
- **Tipo de trabajador**
- **Encargado**
- **Entidad jurídica**

El banner para trabajadores que han salido muestra los siguientes campos:

- **Fecha de salida**
- **Motivo**

El banner para trabajadores pendientes muestra los siguientes campos:

- **Cargo**
- **Departamento**
- **Tipo de puesto**
- **Encargado**
- **Fecha de inicio**
- **Entidad jurídica**

El panel de acciones de la página del trabajador se ha reorganizado para incluir menos opciones. La información ahora se organiza en las categorías siguientes: 

- Trabajo
- Persona
- Dejar
- Compensación
- Prestaciones
- Conformidad

Además, una nueva pestaña **Vínculos** en la página principal del trabajador da a los usuarios una ubicación central para tener acceso a toda la información relacionada para un trabajador.

Debido a estos cambios, puede mostrarse información en una ubicación diferente a la que está acostumbrado. Por ejemplo, información de nómina que antes se mostraba en el formulario Trabajador ahora aparece en el panel de acciones en **Compensación > nómina**, y la pestaña **Información personal** ahora tiene un botón **Más información** para ocultar los campos a los que no se accede a menudo.

[![Pancarta](./media/Banner.png)](./media/Banner.png)

## <a name="work-history"></a>Historial laboral

La pestaña **Historial de trabajo** muestra el historial de trabajo en todas las entidades jurídicas y está disponible para trabajadores y contratistas que han salido, están activos, o pendientes. Ahora puede ver todo el historial de trabajo a la vez para las entidades jurídicas a las que tiene acceso. Además, puede editar información para cada una de las entradas del historial de trabajo sin cambiar el contexto de los datos. Puede actualizar toda la información directamente en la página. 

[![Historial laboral](./media/Worker-work-history.png)](./media/Worker-work-history.png)

## <a name="position-history"></a>Historial de puestos

La pestaña **Puestos** en la página principal del trabajador proporciona una vista de todas las posiciones que se han tenido dentro de la organización, incluidas las asignaciones pasadas, presentes cualquier futura asignación. También seguirá pudiendo acceder directamente al historial de puestos del trabajador en el panel de acciones.

[![Puestos](./media/Worker-position-history.png)](./media/Worker-position-history.png)

