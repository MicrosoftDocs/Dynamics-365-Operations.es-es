---
title: Soporte para múltiples números de registro de IVA en el Suministro Inmediato de Información sobre el IVA (SII) de España
description: Este tema describe el alcance de la función Suministro Inmediato de Información del IVA, SII (Suministro Inmediato de Información del IVA, SII) de España para admitir múltiples números de registro de IVA.
author: liza-golub
ms.date: 10/12/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Spain
ms.author: elgolu
ms.search.validFrom: 2021-01-11
ms.dyn365.ops.version: 10.0.24
ms.openlocfilehash: eb7b485a8727b0aafa6b6200e42b701402a6469b
ms.sourcegitcommit: 9e8d7536de7e1f01a3a707589f5cd8ca478d657b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2021
ms.locfileid: "7647778"
---
# <a name="support-for-multiple-vat-registration-numbers-in-immediate-supply-of-information-on-vat-sii-of-spain"></a>Soporte para múltiples números de registro de IVA en el Suministro Inmediato de Información sobre el IVA (SII) de España

[!include [banner](../includes/banner.md)]

De acuerdo con el R.D. 596/2016 en España, un nuevo sistema de gestión del impuesto sobre el valor agregado (IVA) basado en el Suministro inmediato de información del IVA (\[SII\]) permite una relación bidireccional y automatizada entre la Agencia Estatal de Administración Tributaria (\[AEAT\]) y el contribuyente. En este tema, este sistema se denominará el sistema SII. A partir del 1 de julio de 2017, los contribuyentes sujetos a SII, y otros que lo adopten voluntariamente, deben enviar detalles de sus registros de facturación en un plazo de cuatro días mediante presentación en línea en el sitio web de AEAT.

Para obtener más información sobre el sistema SII de España, consulte el [sitio web oficial del Suministro inmediato de información del IVA (SII)](https://www.agenciatributaria.es/AEAT.internet/en_gb/Inicio/La_Agencia_Tributaria/Campanas/Suministro_Inmediato_de_Informacion_en_el_IVA__SII_/Suministro_Inmediato_de_Informacion_en_el_IVA__SII_.shtml).

Para obtener más información sobre cómo configurar y utilizar la función SII en Microsoft Dynamics 365 Finance, vea [Suministro Inmediato de Información sobre IVA (Suministro Inmediato de Información del IVA, SII)](emea-esp-sii.md).

A partir de la versión 10.0.22 de Finance, si utiliza el servicio [Cálculo de impuestos](global-tax-calcuation-service-overview.md), y la característica [Admite varios números de registro de IVA](emea-multiple-vat-registration-numbers.md) está habilitada en el espacio de trabajo **Gestión de funciones**, puede [Informar los siguientes informes al sistema SII de España de una entidad jurídica que tenga una dirección principal fuera de España](emea-esp-sii.md#multiple-vat):

- 'Libro de registro de facturas Expedidas': **Libro registro de facturas emitidas**
- 'Libro de registro de facturas Recibidas': **Libro registro de facturas recibidas**
