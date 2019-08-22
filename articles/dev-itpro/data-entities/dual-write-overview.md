---
title: Integración casi en tiempo real entre Finance and Operations y Common Data Service
description: Este tema proporciona una visión general de la integración entre Microsoft Dynamics 365 for Finance and Operations y Common Data Service.
author: RamaKrishnamoorthy
manager: AnnBe
ms.date: 07/15/2019
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
ms.search.validFrom: 2019-07-15
ms.openlocfilehash: aa614c8e6a79a3f7a4f8f2f99f1f1bd1a67ac921
ms.sourcegitcommit: efcc0dee8bde5f8f93f6291e7f059ad426843e57
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/31/2019
ms.locfileid: "1797237"
---
# <a name="near-real-time-data-integration-between-finance-and-operations-and-common-data-service"></a>Integración casi en tiempo real entre Finance and Operations y Common Data Service

[!include [banner](../includes/banner.md)]

[!include [preview](../includes/preview-banner.md)]

En el mundo digital actual, los ecosistemas de negocio usan el conjunto Microsoft Dynamics 365 como una unidad. Dado que los datos de personas, clientes, operaciones y de dispositivos de Internet de las cosas (IoT) fluyen en un origen, existe una oportunidad para los bucles de retroalimentación digitales. Para efectuar esta experiencia, la integración entre lsa aplicaciones Dynamics 365 for Finance and Operations y Dynamics 365 para Customer Engagement es esencial. Las aplicaciones de Customer Engagement se construyen sobre Common Data Service. La integración entre los datos de Finance and Operations y Common Data Service permite a las aplicaciones de Customer Engagement comunicarse de forma coherente y fluida con Finance and Operations.

Finance and Operations y Common Data Service proporcionan sincronización de los datos casi en tiempo real entre las aplicaciones de Finance and Operations y Customer Engagement mediante un marco de escritura dual. La cobertura es amplia y abarca 28 áreas expuestas de Finance and Operations. El objetivo es proporcionar una sola experiencia de Dynamics 365 al usuario a través de flujos de datos fluidos que conectan los procesos empresariales entre las aplicaciones.

![Diagrama de visión general de la arquitectura](media/dual-write-overview.jpg)

Las propuestas de valores siguientes están disponibles para los clientes:

+ [Jerarquía organizativa en Common Data Service](dual-write-organization.md)
+ [Concepto de empresa en Common Data Service](dual-write-company.md)
+ [Maestro de clientes integrado](dual-write-customer.md)
+ [Maestro de proveedores integrado](dual-write-vendor.md)
+ Maestro de productos unificado

## <a name="system-requirements"></a>Requisitos del sistema

Los flujos de datos sincrónicos, bidireccionales, casi en tiempo real requieren las versiones siguientes:

+ Microsoft Dynamics 365 for Finance and Operations versión 10.0.4 (julio de 2019) con la actualización de plataforma 28 o posterior.
+ Microsoft Dynamics 365 for Customer Engagement, versión de plataforam 9.1 (4.2) o posterior

## <a name="setup-instructions"></a>Instrucciones de instalación

Siga estos pasos para configurar la integración entre Finance and Operations y Common Data Service.
    
1. Para la configuración del sistema de escritura dual, consulte [guía paso a paso](https://aka.ms/dualwrite-docs) en Anuncio de la vista previa de escritura dual.
2. Descargue e instale la solución en el grupo de Yammer [Integración de Finance and Operations, Common Data Service y Customer Engagement](https://www.yammer.com/dynamicsaxfeedbackprograms/#/threads/inGroup?type=in_group&feedId=66052096). El paquete contiene cinco soluciones:

    + Dynamics365Company
    + CurrencyExchangeRates
    + Dynamics365FinanceAndOperationsCommon
    + Dynamics365FinanceCommon
    + Dynamics365SupplyChainCommon

3. Siga el orden de ejecución para [sincronizar los datos de referencia iniciales](dual-write-initial.md).
4. Si encuentra problemas de sincronización de escritura dual, consulte [Guía de solución de problemas para la integración de datos](dual-write-troubleshooting.md).

> [!IMPORTANT]
> No puede ejecutar la escritura dual y [Cliente potencial a cliente](https://docs.microsoft.com/dynamics365/unified-operations/supply-chain/sales-marketing/accounts-template-mapping-direct) de forma simultánea. Si ejecuta la solución Cliente potencial a cliente, debe desinstalarla. También debe deshabilitar las plantillas de escritura dual de cliente y proveedor que forman parte de la solución Cliente potencial a cliente.
