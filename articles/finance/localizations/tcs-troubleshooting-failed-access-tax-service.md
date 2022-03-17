---
title: Error al acceder al servicio de impuestos
description: En este tema se explica cómo solucionar problemas de un error al acceder el servicio de cálculo de Impuestos.
author: hangwan
ms.date: 03/04/2022
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: TaxIntegrationTaxServiceParameters
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: hangwan
ms.search.validFrom: 02/16/2022
ms.dyn365.ops.version: Version 10.0.21
ms.openlocfilehash: 48a75cd0c1d91c3b3d9c3fb2e6cab93a76756532
ms.sourcegitcommit: b80692c3521dad346c9cbec8ceeb9612e4e07d64
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/05/2022
ms.locfileid: "8388562"
---
# <a name="failed-to-access-tax-service"></a>Error al acceder al servicio de impuestos

[!include [banner](../includes/banner.md)]

[!include [banner](../includes/preview-banner.md)]

Este tema explica cómo solucionar el error "Error al acceder al servicio de impuestos" del servicio de Cálculo de impuestos.

## <a name="symptoms"></a>Síntomas

En Microsoft Dynamics 365 Finance, usted va a **Impuesto** \> **Configuración** \> **Configuración de impuestos** \> **Parámetros del servicio de impuestos**. En la pestaña **General**, habilite la opción **Habilitar cálculo de impuestos**. Si luego intenta seleccionar un valor en el campo **Nombre de configuración de funciones**, se produce un error. El mensaje de error dice: "Error al acceder al servicio de impuestos".

## <a name="cause"></a>Causa

Este error se produce porque Finance no puede acceder al servicio de cálculo de impuestos.

## <a name="resolution"></a>Resolución 

1. Inicie sesión en Microsoft Dynamics LifeCycle Services (LCS).
2. En la página **Entorno**, en la pestaña **Complementos de entorno**, encuentre el artículo **Cálculo de impuestos** y revisar su estado. El estado debe ser **Instalando** o **Instalado**. Si el complemento del servicio de cálculo de impuestos no está instalado, recibirá el error.

## <a name="mitigation"></a>Mitigación

1. En LCS en la página **Finance**, en la sección **Integración de Power Platform**, seleccione **Instalar un nuevo complemento**.
2. Desplácese hasta la parte inferior de la página y seleccione el complemento **Cálculo de impuestos** para instalarlo.
3. Regrese a su entorno de Finance e intente acceder al servicio de Cálculo de impuestos.

> [!NOTE]
> Antes de instalar el servicio de Cálculo de impuestos, revise los [Requisitos previos del Servicio de Cálculo de Impuestos](global-get-started-with-tax-calculation-service.md#prerequisites).
> 
> Si no puede instalar el complemento porque la sección **Integración de Power platform** no está disponible, consulte [Descripción general del complemento](../../fin-ops-core/dev-itpro/power-platform/add-ins-overview.md). Si aún encuentra el error después de instalar el complemento, comuníquese con el administrador del sistema.
