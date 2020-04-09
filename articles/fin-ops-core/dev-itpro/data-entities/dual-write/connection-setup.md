---
title: Escenarios admitidos para la configuración de doble escritura
description: Este tema describe los escenarios que son compatibles con la configuración de doble escritura.
author: RamaKrishnamoorthy
manager: AnnBe
ms.date: 01/06/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User, IT Pro
ms.reviewer: rhaertle
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: ramasri
ms.dyn365.ops.version: ''
ms.search.validFrom: 2020-01-06
ms.openlocfilehash: d7ff514768ee8e4797b591da89e190a855385885
ms.sourcegitcommit: 68f1485de7d64a6c9eba1088af63bd07992d972d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/27/2020
ms.locfileid: "3172863"
---
# <a name="supported-scenarios-for-dual-write-setup"></a>Escenarios admitidos para la configuración de doble escritura

[!include [banner](../../includes/banner.md)]

[!include [preview-banner](../../includes/preview-banner.md)]

Puede configurar una conexión de doble escritura entre entorno de Finance and Operations y uno de Common Data Service.

+ Un **entorno de Finance and Operations** proporciona la plataforma subyacente para las **aplicaciones de Finance and Operations** (por ejemplo, Microsoft Dynamics 365 Finance, Dynamics 365 Supply Chain Management, Dynamics 365 Retail y Dynamics 365 Human Resources).
+ Un **entorno Common Data Service** proporciona la plataforma subyacente para **aplicaciones basadas en modelos en Dynamics 365** (Dynamics 365 Sales, Dynamics 365 Customer Service, Dynamics 365 Field Service, Dynamics 365 Marketing y Dynamics 365 Project Service Automation).

El mecanismo de configuración varía, dependiendo de su suscripción y el entorno.

+ Para nuevas instancias de aplicaciones de Finance and Operations, la configuración de una conexión de doble escritura comienza en Microsoft Dynamics Lifecycle Services (LCS). Si tiene una licencia para Microsoft Power Platform, obtendrá un entorno nuevo Common Data Service entorno si su inquilino no tiene uno.
+ Para instancias existentes de aplicaciones Finance and Operations, la configuración de una conexión de doble escritura comienza en el entorno Finance and Operations.

Se admiten los siguientes escenarios de configuración:

+ [Una instancia de aplicación Finance and Operations nueva y una instancia de aplicación basada en modelos nueva](#new-new)
+ [Una instancia de aplicación Finance and Operations nueva y una instancia de aplicación basada en modelos ya existente](#new-existing)
+ [Una instancia de aplicación Finance and Operations nueva que tenga datos de demostración y una instancia de aplicación basada en modelos nueva](#new-demo-new)
+ [Una instancia de aplicación Finance and Operations nueva que tenga datos de demostración y una instancia de aplicación basada en modelos ya existente](#new-demo-existing)
+ [Una instancia de aplicación Finance and Operations ya existente y una instancia de aplicación basada en modelos nueva o ya existente](#existing-existing)

## <a name="a-new-finance-and-operations-app-instance-and-a-new-model-driven-app-instance"></a><a id="new-new"></a>Una instancia de aplicación Finance and Operations nueva y una instancia de aplicación basada en modelos nueva

Para configurar una conexión de doble escritura entre una nueva instancia de aplicación Finance and Operations que no tiene datos y una nueva instancia de una aplicación basada en modelos en Dynamics 365, siga los pasos en [Configuración de doble escritura de Lifecycle Services](lcs-setup.md). Cuando se completa la configuración de la conexión, las siguientes acciones ocurren automáticamente:

- Se aprovisiona un entorno de Finance and Operations nuevo y vacío.
- Se aprovisiona una nueva instancia vacía de una aplicación basada en modelos, donde se instala la solución CRM primaria.
- Se establece una conexión de doble escritura para los datos de la compañía DAT.
- Los mapas de entidades están habilitados para la sincronización en vivo.

Ambos entornos están listos para la sincronización de datos en vivo.

## <a name="a-new-finance-and-operations-app-instance-and-an-existing-model-driven-app-instance"></a><a id="new-existing"></a>Una instancia de aplicación Finance and Operations nueva y una instancia de aplicación basada en modelos ya existente

Para configurar una conexión de doble escritura entre una nueva instancia de aplicación Finance and Operations que no tiene datos y una instancia ya existente de una aplicación basada en modelos en Dynamics 365, siga los pasos en [Configuración de doble escritura de Lifecycle Services](lcs-setup.md). Cuando se completa la configuración de la conexión, las siguientes acciones ocurren automáticamente:

- Se aprovisiona un entorno de Finance and Operations nuevo y vacío.
- Se establece una conexión de doble escritura para los datos de la compañía DAT.
- Los mapas de entidades están habilitados para la sincronización en vivo.

Ambos entornos están listos para la sincronización de datos en vivo.

Para sincronizar los datos existentes de Common Data Service con la aplicación Finance and Operations, siga estos pasos.

1. Cree una nueva empresa en la aplicación Finance and Operations.
2. Agregue la compañía a la configuración de conexión de doble escritura.
3. [Arranque](bootstrap-company-data.md) los datos Common Data Service mediante el uso de un código de empresa de tres letras de la Organización Internacional de Normalización (ISO).

Debido a que la doble escritura está en modo de sincronización en vivo, los datos de Common Data Service comienzan a fluir automáticamente a la aplicación Finance and Operations.

## <a name="a-new-finance-and-operations-app-instance-that-has-demo-data-and-a-new-model-driven-app-instance"></a><a id="new-demo-new"></a>Una instancia de aplicación Finance and Operations nueva que tenga datos de demostración y una instancia de aplicación basada en modelos nueva

Para configurar una conexión de doble escritura entre una nueva instancia de aplicación Finance and Operations que tiene datos de demostración y una nueva instancia de una aplicación basada en modelos en Dynamics 365, siga los pasos en la sección [Una instancia de aplicación Finance and Operations nueva y una nueva instancia de aplicación basada en modelos](#new-new) anterior en este tema. Cuando finalice la configuración de la conexión, si desea sincronizar los datos de demostración con la aplicación basada en modelos, siga estos pasos.

1. Abre la aplicación Finance and Operations desde la página LCS, inicie sesión y luego vaya a **Gestión de datos \> Doble escritura**.
2. Ejecute la funcionalidad **Sincronización inicia** para las entidades para las que desea sincronizar datos.

## <a name="a-new-finance-and-operations-app-instance-that-has-demo-data-and-an-existing-model-driven-app-instance"></a><a id="new-demo-existing"></a>Una instancia de aplicación Finance and Operations nueva que tenga datos de demostración y una instancia de aplicación basada en modelos ya existente

Para configurar una conexión de doble escritura entre una nueva instancia de aplicación Finance and Operations que tiene datos de demostración y una instancia ya existente de una aplicación basada en modelos en Dynamics 365, siga los pasos en la sección [Una instancia de aplicación Finance and Operations nueva y una instancia de aplicación basada en modelos ya existente](#new-existing) anterior en este tema. Cuando finalice la configuración de la conexión, si desea sincronizar los datos de demostración con la aplicación basada en modelos, siga estos pasos.

1. Abre la aplicación Finance and Operations desde la página LCS, inicie sesión y luego vaya a **Gestión de datos \> Doble escritura**.
2. Ejecute la funcionalidad **Sincronización inicia** para las entidades para las que desea sincronizar datos.

Para sincronizar los datos existentes de Common Data Service con la aplicación Finance and Operations, siga estos pasos.

1. Cree una nueva empresa en la aplicación Finance and Operations.
2. Agregue la compañía a la configuración de conexión de doble escritura.
3. [Arranque](bootstrap-company-data.md) los datos Common Data Service mediante el uso de un código ISO de empresa de tres letras.

Debido a que la doble escritura está en modo de sincronización en vivo, los datos de Common Data Service comienzan a fluir automáticamente a la aplicación Finance and Operations.

## <a name="an-existing-finance-and-operations-app-instance-and-a-new-or-existing-model-driven-app-instance"></a><a id="existing-existing"></a>Una instancia de aplicación Finance and Operations ya existente y una instancia de aplicación basada en modelos nueva o ya existente

La configuración de una conexión de doble escritura entre una instancia existente de una aplicación Finance and Operations y una instancia nueva o existente de una aplicación basada en modelos en Dynamics 365 se produce en el entorno de Finance and Operations.

1. Configure la conexión desde la aplicación Finance and Operations.
2. Para sincronizar lo datos existentes de Common Data Service con la aplicación Finance and Operations, [arranque](bootstrap-company-data.md) los datos Common Data Service mediante el uso de un código de empresa ISO de tres letras.

Debido a que la doble escritura está en modo de sincronización en vivo, los datos de Common Data Service comienzan a fluir automáticamente a la aplicación Finance and Operations.
