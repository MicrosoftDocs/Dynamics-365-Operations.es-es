---
title: Orientación sobre cómo configurar la doble escritura
description: Este artículo describe los escenarios que son compatibles con la configuración de doble escritura.
author: RamaKrishnamoorthy
ms.date: 06/28/2022
ms.topic: article
audience: Application User, IT Pro
ms.reviewer: tfehr
ms.search.region: global
ms.author: ramasri
ms.search.validFrom: 2020-01-06
ms.openlocfilehash: 15dfb609b5e25b4faf2b913cc2310df71c88a74d
ms.sourcegitcommit: 6781fc47606b266873385b901c302819ab211b82
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/02/2022
ms.locfileid: "9111261"
---
# <a name="guidance-for-dual-write-setup"></a>Orientación sobre cómo configurar la doble escritura

[!include [banner](../../includes/banner.md)]

[!include [preview-banner](../../includes/preview-banner.md)]



Puede configurar una conexión de doble escritura entre entorno de finanzas y operaciones y uno de Dataverse.

+ Un **entorno de finanzas y operaciones** proporciona la plataforma subyacente para las **aplicaciones de finanzas y operaciones** (por ejemplo, Microsoft Dynamics 365 Finance, Dynamics 365 Supply Chain Management, Dynamics 365 Commerce y Dynamics 365 Human Resources).
+ Un **entorno Dataverse** proporciona la plataforma subyacente para **aplicaciones de interacción con el cliente** (Dynamics 365 Sales, Dynamics 365 Customer Service, Dynamics 365 Column Service, Dynamics 365 Marketing y Dynamics 365 Project Service Automation).


> [!IMPORTANT]
> El módulo Human Resources en Dynamics 365 Finance admite conexiones de escritura dual, pero la aplicación Dynamics 365 Human Resources no lo hace.

El mecanismo de configuración varía, dependiendo de su suscripción y el entorno:

+ Para nuevas instancias de aplicaciones de finanzas y operaciones, la configuración de una conexión de doble escritura comienza en Microsoft Dynamics Lifecycle Services (LCS). Si tiene una licencia para Microsoft Power Platform, obtendrá un entorno nuevo Dataverse entorno si su inquilino no tiene uno.
+ Para instancias existentes de aplicaciones de finanzas y operaciones, la configuración de una conexión de doble escritura comienza en el entorno de finanzas y operaciones.

Antes de comenzar la doble escritura en una entidad, puede ejecutar una sincronización inicial para procesar los datos existentes en ambos lados: las aplicaciones de finanzas y operaciones y las aplicaciones de Customer Engagement. Puede omitir la sincronización inicial si no necesita sincronizar datos entre los dos entornos.

Una sincronización inicial le permite copiar datos existentes de una aplicación a otra de forma bidireccional. Hay varios escenarios de configuración diferentes según los entornos que ya tenga y el tipo de datos que haya en ellos.

Se admiten los siguientes escenarios de configuración:

+ [Una nueva instancia de aplicación de finanzas y operaciones y una nueva instancia de aplicación de Customer Engagement](#new-new)
+ [Una nueva instancia de aplicación de finanzas y operaciones y una instancia de aplicación de Customer Engagement existente](#new-existing)
+ [Una nueva instancia de aplicación de finanzas y operaciones que tenga datos y una nueva instancia de aplicación de Customer Engagement](#new-data-new)
+ [Una nueva instancia de aplicación de finanzas y operaciones que tenga datos de demostración y una instancia de aplicación de Customer Engagement existente](#new-data-existing)
+ [Una instancia de aplicación de finanzas y operaciones existente y una nueva instancia de aplicación de Customer Engagement](#existing-new)
+ [Una instancia de aplicación de finanzas y operaciones existente y una instancia de aplicación de Customer Engagement existente](#existing-existing)

## <a name="a-new-finance-and-operations-app-instance-and-a-new-customer-engagement-app-instance"></a><a id="new-new"></a>Una nueva instancia de aplicación de finanzas y operaciones y una nueva instancia de aplicación de Customer Engagement

Para configurar una conexión de doble escritura entre una nueva instancia de aplicación de finanzas y operaciones que no tiene datos y una nueva instancia de aplicación de Customer Engagement, siga los pasos de [Configuración de doble escritura de Lifecycle Services](lcs-setup.md). Cuando se completa la configuración de la conexión, las siguientes acciones ocurren automáticamente:

- Se aprovisiona un entorno de finanzas y operaciones nuevo y vacío.
- Se aprovisiona una nueva instancia vacía de aplicación de Customer Engagement, donde se instala la solución CRM primaria.
- Se establece una conexión de doble escritura para los datos de la compañía DAT.
- Los mapas de tablas están habilitados para la sincronización en vivo.

Ambos entornos están listos para la sincronización de datos en vivo.

## <a name="a-new-finance-and-operations-app-instance-and-an-existing-customer-engagement-app-instance"></a><a id="new-existing"></a>Una nueva instancia de aplicación de finanzas y operaciones y una instancia de aplicación de Customer Engagement existente

Para configurar una conexión de doble escritura entre una nueva instancia de aplicación de finanzas y operaciones que no tiene datos y una instancia de aplicación de Customer Engagement existente, siga los pasos de [Configuración de doble escritura de Lifecycle Services](lcs-setup.md). Cuando se completa la configuración de la conexión, las siguientes acciones ocurren automáticamente:

- Se aprovisiona un entorno de finanzas y operaciones nuevo y vacío.
- Se establece una conexión de doble escritura para los datos de la compañía DAT.
- Los mapas de tablas están habilitados para la sincronización en vivo.

Ambos entornos están listos para la sincronización de datos en vivo.

Para sincronizar los datos existentes de Dataverse con la aplicación de finanzas y operaciones, siga estos pasos.

1. Cree una nueva empresa en la aplicación de finanzas y operaciones.
2. Agregue la compañía a la configuración de conexión de doble escritura.
3. [Arranque](bootstrap-company-data.md) los datos Dataverse mediante el uso de un código de empresa de tres letras de la Organización Internacional de Normalización (ISO).
4. Ejecute la funcionalidad **Sincronización inicia** para las tablas para las que desea sincronizar datos.

Para obtener enlaces a un ejemplo y un enfoque alternativo, consulte la sección [Ejemplo](#example) más adelante en este artículo.

## <a name="a-new-finance-and-operations-app-instance-that-has-data-and-a-new-customer-engagement-app-instance"></a><a id="new-data-new"></a>Una nueva instancia de aplicación de finanzas y operaciones que tenga datos y una nueva instancia de aplicación de Customer Engagement

Para configurar una conexión de doble escritura entre una nueva instancia de aplicación de finanzas y operaciones que tiene datos de demostración y una nueva instancia de aplicación de Customer Engagement, siga los pasos de la sección [Una nueva instancia de aplicación de finanzas y operaciones y una nueva instancia de aplicación de Customer Engagement](#new-new) más arriba en este artículo. Cuando finalice la configuración de la conexión, si desea sincronizar los datos de demostración con la aplicación de Customer Engagement, siga estos pasos.

1. Abre la aplicación de finanzas y operaciones desde la página LCS, inicie sesión y luego vaya a **Gestión de datos \> Doble escritura**.
2. Ejecute la funcionalidad **Sincronización inicia** para las tablas para las que desea sincronizar datos.

Para obtener enlaces a un ejemplo y un enfoque alternativo, consulte la sección [Ejemplo](#example).

## <a name="a-new-finance-and-operations-app-instance-that-has-data-and-an-existing-customer-engagement-app-instance"></a><a id="new-data-existing"></a>Una nueva instancia de aplicación de finanzas y operaciones que tenga datos de demostración y una instancia de aplicación de Customer Engagement existente

Para configurar una conexión de doble escritura entre una nueva instancia de aplicación de finanzas y operaciones que tiene datos de demostración y una instancia de aplicación de Customer Engagement existente, siga los pasos de la sección [Una nueva instancia de aplicación de finanzas y operaciones y una instancia de aplicación de Customer Engagement existente](#new-existing) más arriba en este artículo. Cuando finalice la configuración de la conexión, si desea sincronizar los datos de demostración con la aplicación de Customer Engagement, siga estos pasos.

1. Abre la aplicación de finanzas y operaciones desde la página LCS, inicie sesión y luego vaya a **Gestión de datos \> Doble escritura**.
2. Ejecute la funcionalidad **Sincronización inicia** para las tablas para las que desea sincronizar datos.

Para sincronizar los datos existentes de Dataverse con la aplicación de finanzas y operaciones, siga estos pasos.

1. Cree una nueva empresa en la aplicación de finanzas y operaciones.
2. Agregue la compañía a la configuración de conexión de doble escritura.
3. [Arranque](bootstrap-company-data.md) los datos Dataverse mediante el uso de un código ISO de empresa de tres letras.
4. Ejecute la funcionalidad **Sincronización inicia** para las tablas para las que desea sincronizar datos.

Para obtener enlaces a un ejemplo y un enfoque alternativo, consulte la sección [Ejemplo](#example).

## <a name="an-existing-finance-and-operations-app-instance-and-a-new-customer-engagement-app-instance"></a><a id="existing-new"></a>Una instancia de aplicación de finanzas y operaciones existente y una nueva instancia de aplicación de Customer Engagement

La configuración de una conexión de doble escritura entre una instancia existente de una aplicación de finanzas y operaciones y una instancia nueva de aplicación de Customer Engagement se realiza en el entorno de Finance and Operations.

1. [Configurar la conexión desde la aplicación de finanzas y operaciones](enable-dual-write.md).
2. Ejecute la funcionalidad **Sincronización inicia** para las tablas para las que desea sincronizar datos.

Para obtener enlaces a un ejemplo y un enfoque alternativo, consulte la sección [Ejemplo](#example).

## <a name="an-existing-finance-and-operations-app-instance-and-an-existing-customer-engagement-app-instance"></a><a id="existing-existing"></a>Una instancia de aplicación de finanzas y operaciones existente y una instancia de aplicación de Customer Engagement existente

La configuración de una conexión de doble escritura entre una instancia existente de una aplicación de finanzas y operaciones y una instancia de aplicación de Customer Engagement existente se realiza en el entorno de Finance and Operations.

1. [Configurar la conexión desde la aplicación de finanzas y operaciones](enable-dual-write.md).
2. Para sincronizar lo datos existentes de Dataverse con la aplicación de finanzas y operaciones, [arranque](bootstrap-company-data.md) los datos de Dataverse mediante el uso de un código de empresa ISO de tres letras.
3. Ejecute la funcionalidad **Sincronización inicia** para las tablas para las que desea sincronizar datos.

Para obtener enlaces a un ejemplo y un enfoque alternativo, consulte la sección [Ejemplo](#example).

## <a name="example"></a>Ejemplo

Por ejemplo, consulte [Habilitar la asignación de tablas Clientes V3—Contactos](enable-entity-map.md#enable-table-map)

Para obtener un enfoque alternativo basado en volúmenes de datos en cada entidad en la que hay que ejecutar una sincronización inicial, consulte [Consideraciones para la sincronización inicial](initial-sync-guidance.md).


[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]
