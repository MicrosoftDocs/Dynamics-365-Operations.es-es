---
title: Alta e instalación del servicio de Factura Electrónica
description: Este artículo proporciona información sobre cómo configurar e instalar el servicio de facturación electrónica.
author: gionoder
ms.date: 02/07/2022
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
ms.openlocfilehash: 99f484e5ab8821c78fde776a9d3195dade2a09d5
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/12/2022
ms.locfileid: "9283969"
---
# <a name="sign-up-for-and-install-the-electronic-invoicing-service"></a>Alta e instalación del servicio de Factura Electrónica

[!include [banner](../includes/banner.md)]

Este artículo proporciona información sobre cómo configurar e instalar el servicio de facturación electrónica. Hay cuatro pasos en este proceso. Los pasos del 1 al 3 son obligatorios y el paso 4 es opcional.

### <a name="step-1-sign-up-for-regulatory-configuration-service"></a>Paso 1: Inicie sesión en Regulatory Configuration Service

Regulatory Configuration Service (RCS) proporciona la configuración y experiencia de diseño que se usan para configurar la facturación electrónica. Los recursos, como los entornos y las funciones de facturación electrónica se crean, mantienen y gestionan en RCS. Cuando los recursos están listos, se publican en el servicio de facturación electrónica.

Para más información sobre RCS, consulte [Regulatory Configuration Services (RCS): características de globalización](rcs-globalization-feature.md).

Para registrarse para RCS, vaya a la página [Regulatory Configuration Service](https://marketing.configure.global.dynamics.com/).

### <a name="step-2-install-the-add-in-for-microservices-in-microsoft-dynamics-lifecycle-services"></a>Paso 2: Instalar el complemento para microservicios en Microsoft Dynamics Lifecycle Services

El servicio de Facturación Electrónica es un conjunto de microservicios que se aloja en los centros de datos de Microsoft. Por defecto, los clientes de Dynamics 365 Finance y Dynamics 365 Supply Chain Management no tiene acceso al servicio de Facturación Electrónica. Debe instalarlo como un complemento en Microsoft Dynamics Lifecycle Services (LCS). Al instalar el complemento, su entorno de Finance o Supply Chain Management queda registrado en el registro de aplicaciones que pueden conectarse al servicio de Facturación Electrónica.

Para completar este paso, vea [Instalar el complemento para microservicios en Lifecycle Services](e-invoicing-install-add-in-microservices-lcs.md).

### <a name="step-3-set-up-rcs"></a>Paso 3: Configurar RCS

Debe configurar la integración entre RCS y el servicio de facturación electrónica. También debe configurar los componentes principales.

Para completar este paso, consulte [Configurar el Regulatory Configuration Service (RCS)](e-invoicing-set-up-rcs.md).

### <a name="step-4-microsoft-power-platform-plug-in-admin-reference"></a>Paso 4: Referencia de administrador del complemento de Microsoft Power Platform

Algunos escenarios requieren integración con Dataverse en el ámbito de Microsoft Power Platform.

Actualmente, esta configuración es obligatoria si utilizará soluciones de facturación electrónica para escenarios de facturación electrónica de Indonesia. Sin embargo, es opcional para los escenarios de facturación electrónica de Arabia Saudita. Para más información, consulte [Disponibilidad de funciones de facturación electrónica por país o región](e-invoicing-country-specific-availability.md).

Para completar este paso, consulte la [Referencia de administración de complementos de Microsoft Power Platform](e-invoicing-power-platform-plug-in.md).
