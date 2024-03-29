---
title: Configurar la facturación electrónica
description: Este artículo proporciona una descripción general del proceso para instalar y configurar la facturación electrónica.
author: gionoder
ms.date: 02/28/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: gionoder
ms.search.validFrom: ''
ms.dyn365.ops.version: ''
ms.custom: ''
ms.assetid: ''
ms.search.form: ''
ms.openlocfilehash: de94843c1e98a8788375bd41def587a64baea07d
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/12/2022
ms.locfileid: "9272191"
---
# <a name="electronic-invoicing-setup"></a>Configurar la facturación electrónica

[!include [banner](../includes/banner.md)]

Este artículo proporciona una descripción general del proceso para instalar y configurar la facturación electrónica. Debe completar los pasos de configuración en el orden que se especifica aquí. Si un paso es obligatorio, pero lo omite, la funcionalidad no funcionará correctamente y se producirán varios errores durante los pasos posteriores o cuando utilice la funcionalidad. 

Antes de comenzar, asegúrese de que todos los componentes principales estén configurados correctamente, que se haya registrado en el Regulatory Configuration Service (RCS) y tenga una instancia de RCS, y que el complemento de facturación electrónica esté instalado para su Microsoft Microsoft Dynamics 365 Finance o el entorno Dynamics 365 Supply Chain Management. Para obtener más información, vea [Configurar e instalar la facturación electrónica](e-invoicing-install-add-in-microservices-lcs.md).

A continuación, configure los recursos de Azure que requiere Facturación electrónica para hacer su trabajo. Para más información, consulte [Configurar recursos de Azure para la facturación electrónica](e-invoicing-set-up-azure-resources.md).

Después de configurar los componentes principales, trabaje con RCS para configurar los componentes lógicos principales de Facturación electrónica. Primero, defina la cantidad de entornos de servicio que mantendrá. De esta forma, define la partición de configuración y datos lógicos para asegurarse de tener un límite entre un entorno de desarrollo o prueba y los entornos de producción. Para configurar su proceso de desarrollo de manera flexible, es posible que necesite varios entornos de prueba y desarrollo independientes. Además de definir entornos de servicio, establezca un enlace a sus aplicaciones comerciales, como Finance o Supply Chain Management, directamente desde RCS para configurar los parámetros que se requieren para el correcto funcionamiento con Facturación electrónica. Para obtener más información sobre los entornos, consulte [Entornos de servicio](e-invoicing-service-environments.md).

Una vez que todo esté configurado, puede crear sus propias funciones de globalización que definen diferentes escenarios para procesar documentos electrónicos y transformar datos, o para importar los documentos desde el repositorio global. Para obtener más información sobre cómo trabajar con características de Globalización, consulte [Trabajar con características de Globalización](e-invoicing-working-globalization-features.md).

Si sus escenarios requieren integración con correo electrónico o SharePoint para procesar documentos electrónicos entrantes, consulte [Procesamiento de documentos electrónicos entrantes](e-invoicing-process-incoming-electronic-documents.md) para obtener información sobre cómo configurar y usar esos canales.
