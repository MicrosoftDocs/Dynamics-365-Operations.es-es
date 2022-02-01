---
title: Servicios de globalización de Dynamics 365
description: Este tema proporciona información general de los servicios de globalización de Microsoft Dynamics 365.
author: JaneA07
ms.date: 04/12/2021
ms.topic: overview
ms.prod: ''
ms.technology: ''
ms.search.form: RCS, Regulatory Configuration Services, Localization, Electronic invoicing, Tax calculation
audience: Application User
ms.reviewer: kfend
ms.custom:
- "97423"
- intro-internal
ms.assetid: ''
ms.search.region: Global
ms.author: janeaug
ms.search.validFrom: 2020-02-01
ms.dyn365.ops.version: AX 10.0.9
ms.openlocfilehash: 1dfe88bf6eb0cf479f8febd8a599b165b71d932d
ms.sourcegitcommit: 3754d916799595eb611ceabe45a52c6280a98992
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/15/2022
ms.locfileid: "7986000"
---
# <a name="dynamics-365-globalization-services"></a>Servicios de globalización de Dynamics 365

[!include [banner](../includes/banner.md)]

Los siguientes servicios de globalización se pueden configurar para ampliar las capacidades que existen en algunos servicios de Microsoft Dynamics 365 Online:

- **Regulatory Configuration Service (RCS)** admite la configuración de diferentes tipos de documentos e informes electrónicos. RCS proporciona una versión mejorada del diseñador de informes electrónicos (ER) donde el depósito de configuración es un servicio independiente. Para más información, consulte : [Regulatory Configuration Service](rcs-overview.md).
- **Facturacion electronica** reúne formatos configurables para transformaciones, firmas digitales e integraciones configurables para conectividad con servicios web externos, incluida la certificación y el manejo de respuestas. Para más información, vea [Facturación electrónica](e-invoicing-service-overview.md).
- **Cálculo de impuestos** proporciona una mayor flexibilidad al admitir múltiples ID de impuestos, determinación de códigos de impuestos, el diseñador de cálculo de impuestos y un motor de tiempo de ejecución para cumplir con las complejas regulaciones fiscales en todo el mundo. Para obtener más información, consulte [Cálculo de impuestos](global-tax-calcuation-service-overview.md).

Estos servicios de globalización brindan integración inmediata con los siguientes servicios en línea de Dynamics 365.

| Servicio en línea | RCS | Facturación electrónica | Cálculo de impuestos (versión preliminar) |
|----------------|-----|----------------------|---------------------------|
| Dynamics 365 Finance | Sí | Sí | Sí | 
| Dynamics 365 Supply Chain Management | Sí | Sí | Sí | 
| Dynamics 365 Project Operations | Sí | Sí | No aplicable | 
| Dynamics 365 Commerce | Sí | No aplicable | No aplicable | 

> [!NOTE]
> Debido a las diferencias en la disponibilidad de las ubicaciones geográficas de Azure (geos) para RCS, la configuración de este servicio puede hacer que los datos del cliente se transfieran fuera de la ubicación geográfica seleccionada para el servicio en línea de Dynamics 365 correspondiente. Para obtener más información, consulte [Dynamics 365 y Power Platform: Disponibilidad, ubicación de los datos, idioma y localización](https://aka.ms/rcs/D365Productavailabilityguide).