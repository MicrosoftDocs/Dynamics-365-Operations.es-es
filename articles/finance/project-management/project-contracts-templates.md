---
title: Sincronizar los contratos de proyectos y los proyectos directamente desde Project Service Automation a Finance and Operations
description: En este tema se describen las plantillas y las tareas subyacentes que se usan para sincronizar proyectos y contratos de proyectos directamente de Microsoft Dynamics 365 Project Service Automation a Dynamics 365 Finance.
author: KimANelson
manager: AnnBe
ms.date: 09/09/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 87983
ms.assetid: b454ad57-2fd6-46c9-a77e-646de4153067
ms.search.region: Global
ms.author: knelson
ms.search.validFrom: 2017-12-13
ms.dyn365.ops.version: AX 7.3.0
ms.openlocfilehash: 76c62f3a503ff2a8c93143390fc91ef81fbf7d0f
ms.sourcegitcommit: 2460d0da812c45fce67a061386db52e0ae46b0f3
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/30/2019
ms.locfileid: "2250470"
---
# <a name="synchronize-project-contracts-and-projects-directly-from-project-service-automation-to-finance-and-operations"></a>Sincronizar los contratos de proyectos y los proyectos directamente desde Project Service Automation a Finance and Operations

[!include[banner](../includes/banner.md)]

En este tema se describen las plantillas y las tareas subyacentes que se usan para sincronizar proyectos y contratos de proyectos directamente de Dynamics 365 Project Service Automation a Dynamics 365 Finance.

> [!NOTE] 
> Si utiliza , Enterprise Edition 7.3.0, debe instalar KB 4074835.

## <a name="data-flow-for-project-service-automation-to-finance"></a>Flujo de datos de Project Service Automation a Finance

> [!NOTE]
> Para poder usar la solución de integración de Project Service Automation a Finance, debe estar familiarizado con la función de integración de datos de Dynamics 365.

La solución de integración de Project Service Automation a Finance usa la característica de integración de datos para sincronizar datos a través de las instancias de Project Service Automation y de Finance. La plantilla de integración que está disponible con la característica de integración de datos habilita el flujo de datos sobre los contratos de proyectos, los proyectos, las líneas de contratos de proyectos y los hitos de la línea del contrato de proyecto de Project Service Automation a Finance.

La ilustración siguiente muestra cómo se sincronizan los datos entre Project Service Automation y Finance.

[![Flujo de datos para la integración de Project Service Automation con Finance](./media/ProjectsAndContractsFlow.JPG)](./media/ProjectsAndContractsFlow.JPG)

## <a name="templates-and-tasks"></a>Plantillas y tareas

Para obtener acceso a las plantillas disponibles, en el centro de administración de Microsoft PowerApps, seleccione **Proyectos** y, a continuación, en la esquina superior derecha, seleccione **Nuevo proyecto** para seleccionar plantillas públicas.

Las plantillas y las tareas subyacentes siguientes se usan para sincronizar los contratos de proyectos y los proyectos desde Project Service Automation a Finance:

### <a name="integrating-with-dynamics-365-project-service-automation-v2x"></a>Integración con la versión 2.x de Dynamics 365 Project Service Automation
- **Nombre de la plantilla en la integración de datos:** proyectos y contratos (PSA a Fin and Ops)
- **Nombre de las tareas en el proyecto:**

    - Contratos de proyecto PSA a Fin and Ops
    - Proyectos PSA a Fin and Ops
    - Líneas de contratos de proyecto PSA a Fin and Ops
    - Hitos de líneas de contratos de proyecto PSA a Fin and Ops
  
### <a name="integrating-with-dynamics-365-project-service-automation-v3x"></a>Integración con la versión 3.x de Dynamics 365 Project Service Automation
Hay un cambio de esquema en Project Service Automation que afecta a la plantilla del hito de la línea del contrato de proyecto y se requiere usar la versión 2 de la plantilla para integrar la versión 3.x de Project Service Automation con Dynamics 365.

- **Nombre de la plantilla en la integración de datos:** proyectos y contratos (versión 3.x de PSA a Fin and Ops), versión 2
- **Nombre de las tareas en el proyecto:**

    - Contratos de proyecto PSA a Fin and Ops
    - Proyectos PSA a Fin and Ops
    - Líneas de contratos de proyecto PSA a Fin and Ops
    - Hitos de líneas de contratos de proyecto PSA a Fin and Ops

Antes de que se produzca la sincronización de contratos de proyecto y de proyectos, debe sincronizar las cuentas.

## <a name="entity-set"></a>Conjunto de entidades

| Project Service Automation       | Finanzas                                                |
|----------------------------------|--------------------------------------------------------|
| Pedidos                           | Entidad de integración de contrato de proyecto                |
| Proyectos                         | Entidad de integración para proyecto                         |
| Líneas de pedido                      | Entidad de integración para línea de contrato de proyecto           |
| Hitos de línea de contrato de proyecto | Entidad de integración para hito de línea de contrato de proyecto |

## <a name="entity-flow"></a>Flujo de la entidad

Los contratos de proyectos se administran en Project Service Automation y se sincronizan con Finance como contratos de proyectos. Como parte de la plantilla de integración, puede configurar el origen de la integración en Finance para el contrato de proyecto.

Los proyectos de tiempo y material y proyectos de precio fijo se administran en Project Service Automation y se sincronizan con Finance como proyectos. Como parte de la plantilla de integración, puede configurar el origen de la integración en Finance para el proyecto.

Las líneas de contratos de proyectos se administran en Project Service Automation y se sincronizan con Finance como reglas de facturación de contratos de proyectos. Si el método de facturación difiere del tipo de proyecto predeterminado, la sincronización actualiza el tipo de proyecto para el proyecto de línea de contrato y el grupo de proyectos.

Los hitos de las líneas de contratos de proyectos se administran en Project Service Automation y se sincronizan con Finance como hitos de reglas de facturación de contratos de proyectos.

## <a name="project-service-automation-to-finance-integration-solution"></a>Solución de integración de Project Service Automation con Finance

El campo **Identificador de contrato de proyecto** está disponible en la página **Contratos de proyecto**. Este campo se ha convertido en una clave natural y única para admitir la integración.

Cuando se crea un nuevo contrato de proyecto, si todavía no existe un valor **ID de contrato de proyecto**, se genera automáticamente mediante una secuencia numérica. El valor consiste en **ORD**, seguido por una secuencia numérica que aumenta y después un sufijo de seis caracteres. Este es un ejemplo: **ORD-01022-Z4M9Q0**.

El campo **Número de proyecto** está disponible en la página **Proyectos**. Este campo se ha convertido en una clave natural y única para admitir la integración.

Cuando se crea un nuevo proyecto, si todavía no existe un valor **Número de proyecto** , se genera automáticamente mediante una secuencia numérica. El valor consiste en **PRJ**, seguido por una secuencia numérica que aumenta y después un sufijo de seis caracteres. Este es un ejemplo: **PRJ-01049-CCNID0**.

Cuando la solución de integración de Project Service Automation a Finance se aplica, un script de actualización establece el campo **Id. de contrato de proyecto** de los contratos de proyectos existentes y el campo **Número de proyecto** de los proyectos existentes en Project Service Automation.

## <a name="prerequisites-and-mapping-setup"></a>Condiciones previas y configuración de asignación

- Antes de que se produzca la sincronización de contratos de proyecto y de proyectos, debe sincronizar las cuentas.
- En su conjunto de conexiones, agregue una asignación del campo clave de la integración de **msdyn\_organizationalunits** en **msdyn\_name \[Nombre\]**. Es posible que necesite primero agregar un proyecto al conjunto de conexión. Para obtener más información, consulte [Integrar datos en Common Data Service para aplicaciones](https://docs.microsoft.com/powerapps/administrator/data-integrator).
- En su conjunto de conexiones, agregue una asignación del campo clave de la integración de **msdyn\_projects** en **msdynce\_projectnumber \[Número de proyecto\]**. Es posible que necesite primero agregar un proyecto al conjunto de conexión. Para obtener más información, consulte [Integrar datos en Common Data Service para aplicaciones](https://docs.microsoft.com/powerapps/administrator/data-integrator).
- **SourceDataID** para los contratos de proyecto y los proyectos se puede actualizar a un valor distinto o quitar de la asignación. El valor de la plantilla predeterminada es **Project Service Automation**.
- La asignación **PaymentTerms** debe ser actualizada de modo que refleje condiciones de pago válidas en Finance. También puede quitar la asignación de la tarea de proyecto. La asignación de valor predeterminado tiene valores predeterminados para los datos de prueba. En la tabla siguiente se muestran los valores de Project Service Automation.

    | Valor | Descripción   |
    |-------|---------------|
    | 1     | Neto 30        |
    | 2     | 2% 10, Net 30 |
    | 3     | Neto 45        |
    | 4     | Neto 60        |

## <a name="power-query"></a>Power Query

Debe usar Microsoft Power Query for Excel para filtrar los datos si se cumplen las siguientes condiciones:

- Tiene pedidos de ventas en Dynamics 365 Sales.
- Tiene varias unidades organizativas en Project Service Automation y estas unidades organizativas se asignarán a varias entidades jurídicas en Finance.

Si debe usar Power Query, siga estas instrucciones:

- La plantilla de proyectos y contratos (PSA a Fin and Ops) tiene un filtro predeterminado que incluye solo pedidos de ventas del tipo **Elemento de trabajo (msdyn\_ordertype = 192350001)**. Este filtro contribuye a garantizar que los contratos de proyecto no se creen para pedidos de ventas en Finance. Si crea su propia plantilla, debe agregar este filtro.
- Debe crear un filtro Power Query que incluya solo a las organizaciones de contrato que deben sincronizarse con la entidad jurídica del conjunto de conexión de integración. Por ejemplo, los contratos de proyecto que tiene con la unidad organizativa del contrato de Contoso EE. UU se deben sincronizar con la entidad jurídica de USSI, pero los contratos de proyecto que tiene con las unidades organizativas de Contoso Global se deben sincronizar con la entidad jurídica de USMF. Si no añade este filtro a su equivalencia de tareas, todos los contratos de proyecto se sincronizarán con la entidad jurídica que se define para el conjunto de conexiones, independientemente de la unidad organizativa del contrato.

## <a name="template-mapping-in-data-integration"></a>Asignación de la plantilla en la integración de datos

> [!NOTE] 
> Los campos **CustomerReference**, **AddressCity**, **AddressCountryRegionID**, **AddressDescription**, **AddressLine1**, **AddressLine2**, **AddressState** y **AddressZipCode** no se incluyen en la asignación predeterminada de contratos de proyecto. Puede agregar las asignaciones si necesita que estos datos se sincronicen para los contratos de proyecto.
>
> Los campos **Description**, **ParentID**, **ProjectGroup**, **ProjectManagerPersonnelNumber** y **ProjectType** no se incluyen en la asignación predeterminada de los proyectos. Puede agregar las asignaciones si necesita que estos datos se sincronicen para los proyectos.

Las siguientes ilustraciones muestran ejemplos de asignaciones de tareas de plantillas en la integración de datos. La asignación muestra la información de campo que se sincronizará de Project Service Automation a Finance.

[![Asignación de la plantilla](./media/ProjectContractTemplateMapping.JPG)](./media/ProjectContractTemplateMapping.JPG)

[![Asignación de la plantilla](./media/ProjectTemplateMapping.JPG)](./media/ProjectTemplateMapping.JPG)

[![Asignación de la plantilla](./media/ProjectContractLinesMapping.JPG)](./media/ProjectContractLinesMapping.JPG)

[![Asignación de la plantilla](./media/ProjectContractLineMilestonesMapping.JPG)](./media/ProjectContractLineMilestonesMapping.JPG)

#### <a name="project-contract-line-milestone-mapping-in-the-projects-and-contracts-psa-3x-to-dynamics---v2-template"></a>Asignación del hito de línea del contrato en la plantilla Proyectos y contratos (PSA 3.x a Dynamics), versión 2:

[![Asignación de la plantilla](./media/ProjectContractLineMilestoneMapping_v2.jpg)](./media/ProjectContractLineMilestoneMapping_v2.jpg)
