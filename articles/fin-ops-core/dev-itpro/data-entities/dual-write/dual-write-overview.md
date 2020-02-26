---
title: Integración de datos casi en tiempo real con Common Data Service
description: Este tema proporciona una visión general de la integración entre Finance and Operations y Common Data Service.
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
ms.openlocfilehash: 1c09b0c0bb695e7695acb7a8821ffb99ae1f6f06
ms.sourcegitcommit: 54baab2a04e5c534fc2d1fd67b67e23a152d4e57
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "3020002"
---
# <a name="near-real-time-data-integration-with-common-data-service"></a>Integración de datos casi en tiempo real con Common Data Service

[!include [banner](../../includes/banner.md)]

[!include [preview-banner](../../includes/preview-banner.md)]

En el mundo digital actual, los ecosistemas de negocio usan las aplicaciones de Microsoft Dynamics 365 como una unidad. Dado que los datos de personas, clientes, operaciones y de dispositivos de Internet de las cosas (IoT) fluyen en un origen, existe una oportunidad para los bucles de retroalimentación digitales. Para efectuar esta experiencia, la integración entre las aplicaciones de Finance and Operations y otras aplicaciones de Dynamics 365 es esencial. Algunas aplicaciones se construyen sobre Common Data Service. La integración entre los datos de las aplicaciones de Finance and Operations con Common Data Service permite que otras aplicaciones se comuniquen de manera coherente y fluida con Finance and Operations.

Las aplicaciones de Finance and Operations y Common Data Service proporcionan sincronización de los datos casi en tiempo real entre las aplicaciones de Finance and Operations y otras aplicaciones de Dynamics 365 mediante un marco de escritura dual. La cobertura es amplia y abarca 28 áreas expuestas de la aplicación. El objetivo es proporcionar una sola experiencia de Dynamics 365 al usuario a través de flujos de datos fluidos que conectan los procesos empresariales entre las aplicaciones.

![Diagrama de visión general de la arquitectura](media/dual-write-overview.jpg)

Las propuestas de valores siguientes están disponibles:

+ [Jerarquía organizativa en Common Data Service](organization-mapping.md)
+ [Concepto de empresa en Common Data Service](company-data.md)
+ [Maestro de clientes integrado](customer-mapping.md)
+ [Libro mayor integrado](ledger-mapping.md)
+ [Experiencia unificada del producto](product-mapping.md)
+ [Maestro de proveedores integrado](vendor-mapping.md)
+ [Sitios y almacenes integrados](sites-warehouses-mapping.md)
+ [Datos fiscales maestros integrados](tax-mapping.md)

## <a name="system-requirements"></a>Requisitos del sistema

Los flujos de datos sincrónicos, bidireccionales, casi en tiempo real requieren las versiones siguientes:

+ Microsoft Dynamics 365 for Finance and Operations versión 10.0.4 (julio de 2019) con la actualización de plataforma 28 o posterior.
+ Microsoft Dynamics 365 for Customer Engagement, versión de plataforam 9.1 (4.2) o posterior

## <a name="setup-instructions"></a>Instrucciones de instalación

Siga estos pasos para configurar la integración entre las aplicaciones de Finance and Operations y Common Data Service.
    
1. Para la configuración del sistema de escritura dual, consulte [guía paso a paso](https://aka.ms/dualwrite-docs) en Anuncio de la vista previa de escritura dual.
2. Descargue e instale la solución desde el grupo de Yammer [Fin Ops e integración de CDS / CE a través de doble escritura](https://www.yammer.com/dynamicsaxfeedbackprograms/#/threads/inGroup?type=in_group&feedId=66052096). El paquete contiene cinco soluciones:

    + Dynamics365Company
    + CurrencyExchangeRates
    + Dynamics365FinanceAndOperationsCommon
    + Dynamics365FinanceCommon
    + Dynamics365SupplyChainCommon

3. Siga el orden de ejecución para [sincronizar los datos de referencia iniciales](initial-sync.md).
4. Si encuentra problemas de sincronización de escritura dual, consulte [Guía de solución de problemas para la integración de datos](dual-write-troubleshooting.md).

> [!IMPORTANT]
> No puede ejecutar la escritura dual y [Cliente potencial a cliente](../../../../supply-chain/sales-marketing/prospect-to-cash.md) de forma simultánea. Si ejecuta la solución Cliente potencial a cliente, debe desinstalarla. También debe deshabilitar las plantillas de escritura dual de cliente y proveedor que forman parte de la solución Cliente potencial a cliente.
