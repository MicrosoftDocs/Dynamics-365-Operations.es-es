---
title: Configurar parámetros compartidos
description: Debe configurar los parámetros compartidos para los registros que se comparten entre empresas, como registros de puesto. En este artículo se explica cómo configurar parámetros de recursos humanos entre entidades jurídicas.
author: andreabichsel
manager: AnnBe
ms.date: 02/03/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-human-resources
ms.technology: ''
ms.search.form: HcmSharedParameters, HcmPersonnelManagementWorkspace
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Core, Operations, Human Resources
ms.custom: 51891
ms.assetid: c7d8f58c-d78a-4035-abbf-2b0ce16109fe
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 72742c38c3ff25d665bd1a3d0ea54f167dc0693c
ms.sourcegitcommit: ba340f836e472f13f263dec46a49847c788fca44
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2020
ms.locfileid: "3430058"
---
# <a name="configure-shared-parameters"></a>Configurar parámetros compartidos

Debe configurar los parámetros compartidos para los registros que se comparten entre empresas, como registros de puesto. En este artículo se explica cómo configurar parámetros de recursos humanos entre entidades jurídicas.

Algunos tipos de registros, como Registros de puestos, se comparten entre las empresas. Para estos registros, debe configurar los parámetros compartidos. Por ejemplo, puede usar la página **Parámetros compartidos de recursos humanos** para configurar los parámetros de recursos humanos entre entidades jurídicas. 

En la página **Parámetros compartidos de recursos humanos**, los parámetros se agrupan en áreas, en función de su funcionalidad. 

### <a name="previously-released-functionality"></a>Funcionalidad anteriormente liberada
En la pestaña **Identificación**, debe seleccionar los tipos de identificación que representan los números de identificación enumerados en la página. Debe configurar tipos de identificación para poder especificar la información de identificación para los trabajadores. La información sobre el número de seguridad social, el número de DNI, el número de identificación de salida y el código de identificación personal se mantiene en la página **Tipo de identificación**. Para definir un nuevo tipo de identificación o revisar la lista de tipos existentes, haga clic en **Gestión del personal** &gt; **Ficha Vínculos** &gt; **Confirguración** &gt; **Tipos de identificación**. Puede especificar una descripción y un código simples. 

### <a name="if-youre-using-dynamics-365-human-resources"></a>Si usa Dynamics 365 Human Resources
En la pestaña **Identificación**, debe seleccionar los tipos de identificación que representan los números de identificación enumerados en la página. Debe configurar tipos de identificación para poder especificar la información de identificación para los trabajadores. La información sobre el número de seguridad social, el número de DNI, el número de identificación de salida y el código de identificación personal se mantiene en la página **Tipo de identificación**. Para definir un nuevo tipo de identificación o revisar la lista de tipos existentes, haga clic en **Recursos humanos** &gt; **Instalación** &gt; **Tipos de identificación**. Puede especificar una descripción y un código simples. 

En la pestaña **Secuencias numéricas**, puede seleccionar las secuencias numéricas que se usan para los registros siguientes: número de personal, puesto, Id. de solicitud de usuario, documento I-9, candidato, discusión, Id. de prestación y acción de personal (si se permite a este tipo de registro). Para mantener las referencias y los códigos de la secuencia numérica, use la página de lista **Secuencias numéricas**. Para buscar esta página, use la fncionalidad de búsqueda de páginas. 

En la pestaña **Puestos**, indique si los nuevos puestos están disponibles para la asignación de forma predeterminada:

-   **Siempre:** no puede asignar trabajadores a los nuevos puestos cuando se crean los puestos. Cuando se crean los puestos, la fecha y la hora **Disponibles para la asignación** en la pestaña **General** de la página **Puesto** se cambian automáticamente a la fecha y hora de la creación.
-   **Nunca:** no puede asignar trabajadores a los nuevos puestos cuando se crean los puestos. Si selecciona esta opción, también debe abrir la página **Puesto** para cada nuevo puesto a medida que se haga disponible y luego en la pestaña **General**, especificar la fecha **Disponible para la asignación** para habilitar la asignación del trabajador.
