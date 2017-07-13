---
title: "Configurar parámetros de recursos humanos en entidades jurídicas"
description: "Debe configurar los parámetros compartidos para los registros que se comparten entre empresas, como registros de puesto. En este artículo se explica cómo configurar parámetros de recursos humanos entre entidades jurídicas."
author: rschloma
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-365-talent
ms.technology: 
ms.search.form: HcmSharedParameters
audience: Application User
ms.reviewer: rschloma
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 51891
ms.assetid: c7d8f58c-d78a-4035-abbf-2b0ce16109fe
ms.search.region: Global
ms.author: shielas
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Talent July 2017 update
ms.translationtype: Human Translation
ms.sourcegitcommit: f83bc127f7bf3cdceb39a79c1e69f4f7e96f6462
ms.openlocfilehash: 1a23ec184538510527573de8dd334603dc973ae6
ms.contentlocale: es-es
ms.lasthandoff: 06/19/2017


---

# Configurar parámetros de recursos humanos en entidades jurídicas
<a id="set-up-hr-parameters-across-legal-entities" class="xliff"></a>

[!include[banner](includes/banner.md)]


Debe configurar los parámetros compartidos para los registros que se comparten entre empresas, como registros de puesto. En este artículo se explica cómo configurar parámetros de recursos humanos entre entidades jurídicas.

Algunos tipos de registros, como Registros de puestos, se comparten entre las empresas. Para estos registros, debe configurar los parámetros compartidos. Por ejemplo, puede usar la página **Parámetros compartidos de recursos humanos** para configurar los parámetros de recursos humanos entre entidades jurídicas. 

En la página **Parámetros compartidos de recursos humanos**, los parámetros se agrupan en áreas, en función de su funcionalidad. 

### Funcionalidad anteriormente liberada
<a id="previously-released-functionality" class="xliff"></a>
En la pestaña **Identificación**, debe seleccionar los tipos de identificación que representan los números de identificación enumerados en la página. Debe configurar tipos de identificación para poder especificar la información de identificación para los trabajadores. La información sobre el número de seguridad social, el número de DNI, el número de identificación de salida y el código de identificación personal se mantiene en la página **Tipo de identificación**. Para definir un nuevo tipo de identificación o revisar la lista de tipos existentes, haga clic en **Gestión del personal** &gt; **Ficha Vínculos** &gt; **Confirguración** &gt; **Tipos de identificación**. Puede especificar una descripción y un código simples. 

### Si utiliza Dynamics 365 for Talent
<a id="if-youre-using-dynamics-365-for-talent" class="xliff"></a>
En la pestaña **Identificación**, debe seleccionar los tipos de identificación que representan los números de identificación enumerados en la página. Debe configurar tipos de identificación para poder especificar la información de identificación para los trabajadores. La información sobre el número de seguridad social, el número de DNI, el número de identificación de salida y el código de identificación personal se mantiene en la página **Tipo de identificación**. Para definir un nuevo tipo de identificación o revisar la lista de tipos existentes, haga clic en **Recursos humanos** &gt; **Instalación** &gt; **Tipos de identificación**. Puede especificar una descripción y un código simples. 

En la pestaña **Secuencias numéricas**, puede seleccionar las secuencias numéricas que se usan para los registros siguientes: número de personal, puesto, Id. de solicitud de usuario, documento I-9, candidato, discusión, Id. de prestación y acción de personal (si se permite a este tipo de registro). Para mantener las referencias y los códigos de la secuencia numérica, use la página de lista **Secuencias numéricas**. Para buscar esta página, use la fncionalidad de búsqueda de páginas. 

En la pestaña **Puestos**, indique si los nuevos puestos están disponibles para la asignación de forma predeterminada:

-   **Siempre:** no puede asignar trabajadores a los nuevos puestos cuando se crean los puestos. Cuando se crean los puestos, la fecha y la hora **Disponibles para la asignación** en la pestaña **General** de la página **Puesto** se cambian automáticamente a la fecha y hora de la creación.
-   **Nunca:** no puede asignar trabajadores a los nuevos puestos cuando se crean los puestos. Si selecciona esta opción, también debe abrir la página **Puesto** para cada nuevo puesto a medida que se haga disponible y luego en la pestaña **General**, especificar la fecha **Disponible para la asignación** para habilitar la asignación del trabajador.


Consulte también
<a id="see-also" class="xliff"></a>
--------

[Configuración de los parámetros de recursos humanos específicos de la empresa](set-up-company-specific-hr-parameters.md)




