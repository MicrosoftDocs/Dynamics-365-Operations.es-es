---
title: Lista de funciones de impuestos vacía en los parámetros de cálculo de impuestos
description: Este tema explica cómo solucionar un problema en el que la lista de funciones de impuestos en la página de parámetros de cálculo de impuestos está vacía.
author: wangchen
ms.date: 03/04/2022
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: TaxIntegrationTaxServiceParameters
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: wangchen
ms.search.validFrom: 2021-10-26
ms.dyn365.ops.version: Version 10.0.21
ms.openlocfilehash: 5b87499042c9c4bfe76e182b170adf4f1cfeac4b
ms.sourcegitcommit: b80692c3521dad346c9cbec8ceeb9612e4e07d64
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/05/2022
ms.locfileid: "8388563"
---
# <a name="empty-tax-feature-list-in-tax-calculation-parameters"></a>Lista de funciones de impuestos vacía en los parámetros de cálculo de impuestos

[!include [banner](../includes/banner.md)]

[!include [banner](../includes/preview-banner.md)]

## <a name="symptom"></a>Síntoma

Publicó una característica en el Regulatory Configuration Service (RCS), para que pueda usarla en Microsoft Dynamics 365 Finance. Sin embargo, cuando abra Finance, vaya a **Impuestos** \> **Configuración** \> **Configuración de impuestos** \> **Parámetros de cálculo de impuestos** e intente seleccionar un valor en el campo **Nombre de configuración de funciones**, la lista de valores está vacía.

## <a name="reason"></a>Motivo

Este problema generalmente ocurre porque su entorno de Finance y el entorno de RCS no están bajo el mismo inquilino.

### <a name="rcs-tenant"></a>Inquilino RCS

Siga estos pasos para encontrar el identificador de su inquilino RCS.

1. Copie la URL completa de RCS. Por ejemplo, la URL puede ser `https://rcs-rts-sf-ed22b5aeea8-int-westus2.configure.global.int.dynamics.com/namespaces/817ff7a0-0d77-4aba-9360-3c9749e2c5de/?cmp=dat&mi=RCSFeatureDomainsWorkspace`.
2. Abra una ventana del navegador de InPrivate, pegue la URL de RCS en la barra de direcciones y luego seleccione **Entrar**. Se le dirige a la página de inicio de sesión, donde puede encontrar el ID de inquilino de RCS. Por ejemplo, si la URL de la página de inicio de sesión es `https://login.microsoftonline.com/d335a570-a05b-4bc5-8eb3-c42c65f9560d`, el ID de inquilino es la información que aparece tras `https://login.microsoftonline.com/`, o **d335a570-a05b-4bc5-8eb3-c42c65f9560d**.

### <a name="finance-environment-tenant-id"></a>Identificación de inquilino de Finance para su entorno

Para encontrar el ID de inquilino para su entorno de Finance, siga los mismos pasos que siguió para buscar el inquilino de RCS. Sin embargo, copie y pegue la URL completa de su entorno de Finance en lugar de la URL completa de RCS.

## <a name="resolution"></a>Resolución

Si los dos identificadores de inquilinos difieren, se encuentra con el problema que se describe en este tema. Si son iguales, se está encontrando con un problema no relacionado. En este caso, le recomendamos que contacte con el Soporte técnico de Microsoft.

### <a name="solution-1"></a>Solución 1

Inicie sesión en su entorno de RCS en el mismo arrendatario en el que está conectado su entorno de Finance. A continuación, cree y publique la característica de impuestos.

### <a name="solution-2"></a>Solución 2

Comparta la característica de impuestos con el arrendatario de Finance en RCS.

1. En RCS, vaya a **Funciones de globalización** \> **Cálculo de impuestos**.
2. Seleccione la función para compartir y, a continuación, en la pestaña **Organizaciones**, seleccione **Compartir con**.
3. En el campo **Nombre de dominio de la organización**, escriba un nombre. Por ejemplo, ingrese **contoso.onmicrosoft.com**.
4. Seleccione **Compartir**.

![Compartir con el cuadro de diálogo desplegable de organización externa.](media/ShareTaxFeature.png)
