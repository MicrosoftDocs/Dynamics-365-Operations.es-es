---
title: Configurar parámetros compartidos
description: En este artículo se explica cómo configurar parámetros de recursos humanos entre entidades jurídicas.
author: twheeloc
ms.date: 10/28/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: HcmSharedParameters, HcmPersonnelManagementWorkspace
audience: Application User
ms.custom: 51891
ms.assetid: c7d8f58c-d78a-4035-abbf-2b0ce16109fe
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: c0d8dbca302d90cc402feb4715a6fcc2b935d8b1
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/03/2022
ms.locfileid: "8906193"
---
# <a name="configure-shared-parameters"></a>Configurar parámetros compartidos

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Debe configurar los parámetros compartidos para los registros que se comparten entre empresas, como registros de **Puesto**. En este artículo se explica cómo configurar parámetros de recursos humanos entre entidades jurídicas.

Algunos tipos de registros, como registros de **Puesto**, se comparten entre las empresas. Para estos registros, debe configurar los parámetros compartidos. Por ejemplo, la página **Parámetros compartidos de recursos humanos** sirve para configurar los parámetros de recursos humanos entre entidades jurídicas. 

En la página **Parámetros compartidos de recursos humanos**, los parámetros se agrupan en áreas, en función de su funcionalidad. 

### <a name="settings"></a>Parámetros
En la pestaña **Identificación**, debe seleccionar los tipos de identificación que representan los números de identificación enumerados en la página. Debe configurar tipos de identificación para poder especificar la información de identificación para los trabajadores. La información sobre el número de seguridad social, el número de DNI, el número de identificación de salida y el código de identificación personal se mantiene en la página **Tipo de identificación**. Para definir un nuevo tipo de identificación o revisar la lista de tipos existentes, vaya a **Gestión del personal** &gt; **Vínculos** &gt; **Confirguración** &gt; **Tipos de identificación**. Puede especificar una descripción y un código simples. 

En la pestaña **Secuencias numéricas**, puede seleccionar las secuencias numéricas que se usan para los registros siguientes: **número de personal**, **puesto**, **Id. de solicitud de usuario**, **documento I-9**, **candidato**, **discusión**, **Id. de prestación** y **acción de personal** (si se permite a este tipo de registro). Para mantener las referencias y los códigos de la secuencia numérica, use la página de lista **Secuencias numéricas**. Para buscar esta página, use la fncionalidad de búsqueda de páginas. 

En la pestaña **Puestos**, indique si los nuevos puestos están disponibles para la asignación de forma predeterminada:

- **Siempre:** no puede asignar trabajadores a los nuevos puestos cuando se crean los puestos. Cuando se crean los puestos, la fecha y la hora **Disponibles para la asignación** en la pestaña **General** de la página **Puesto** se cambian automáticamente a la fecha y hora de la creación.
- **Nunca:** no puede asignar trabajadores a los nuevos puestos cuando se crean los puestos. Si selecciona esta opción, debe abrir la página **Posición** para cada nueva posición a medida que esté disponible. Entonces, en la pestaña **General**, ingrese la fecha **Disponible para asignación** para habilitar la asignación de trabajadores.

Sobre la pestaña **Acceso avanzado**, puede restringir el acceso a cierta información o enlaces:

- **Restringir el acceso a la información de los trabajadores** - Seleccione esta función si los usuarios deberían poder ver la información de los empleados solo para las entidades legales a las que tienen acceso y para los empleados que tienen empleo en esas entidades legales.

    Una vez seleccionada esta función, siga estos pasos para establecer los permisos adecuados para cada usuario cuya vista deba restringirse:

    1. Sobre la página **Usuarios**, seleccione un usuario.
    1. Seleccione un rol para el usuario. La opción **Asignar organizaciones** está disponible.
    1. Seleccione **Asignar organizaciones**.
    1. En la nueva página, seleccione **Otorgar acceso a organizaciones específicas de forma individual** y luego seleccione las organizaciones a las que el usuario debe tener acceso.
    1. Repita los pasos 2 a 4 para cada rol adicional que tenga el usuario, incluido el rol de usuario del sistema.

    > [!NOTE]
    > Las empresas a las que tiene acceso un usuario deben coincidir en todos los roles del usuario.

- **Habilitar la vista de compensación entre empresas** - La remuneración de los empleados se asigna por entidad legal de empleo. A veces, un empleado puede trabajar en varias entidades legales al mismo tiempo. Cuando esta función está seleccionada, la compensación para cada entidad legal aparecerá en **Autoservicio para empleados** y **Autoservicio para gerentes** sin necesidad de cambiar de entidad legal. 

[!INCLUDE[footer-include](../includes/footer-banner.md)]
