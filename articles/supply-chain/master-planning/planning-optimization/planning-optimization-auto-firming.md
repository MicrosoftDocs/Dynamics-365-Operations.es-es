---
title: Puesta en firme automática con la optimización de la planificación
description: Este tema explica cómo usar la puesta en firme automática con la optimización de la planificación.
author: ChristianRytt
manager: tfehr
ms.date: 11/05/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ReqCreatePlanWorkspace
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2019-11-30
ms.dyn365.ops.version: AX 10.0.7
ms.openlocfilehash: 81c26b8a99f86d663d91ac4f549987262c0541ad
ms.sourcegitcommit: 68092ed283bfbb7b6f611cce1b62c791f9b6a208
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/30/2020
ms.locfileid: "3323540"
---
# <a name="auto-firming-with-planning-optimization"></a>Puesta en firme automática con la optimización de la planificación

[!include [banner](../../includes/banner.md)]

La puesta en firme automática permite poner en firme (es decir, enviar) los pedidos planificados como parte del proceso de planificación maestra. Cuando se ponen en firme los pedidos planificados, se transforman en pedidos de compra reales, pedidos de transferencia o pedidos de producción. Cuando se usa la optimización de la planificación, los pedidos planificados se ponen en firme durante una planificación maestra ejecutada cuando la fecha del pedido (es decir, la fecha inicial) está dentro del límite de tiempo para la puesta en firme.

> [!NOTE]
> La puesta en firme automática de un pedido de compra planificado solo puede producirse si el artículo se asocia a un proveedor.

## <a name="turn-on-auto-firming"></a>Desactivar la puesta en firme automática

Para activar la puesta en firme automática, siga estos pasos.

1. En el espacio de trabajo **Administración de características**, en la pestaña **Nuevo**, seleccione **Puesta en firme para la optimización de la planificación** en la lista. Si la característica no aparece en la pestaña **Nuevo**, mire en las pestañas **No habilitado** y **Todo**.
1. Seleccione **Habilitar ahora**. Como alternativa, seleccione **Programación** y el tiempo en que desea que la función esté activada.

## <a name="set-up-the-firming-time-fence"></a>Configurar el límite de tiempo de la puesta en firme

El límite de tiempo de puesta en firme se calcula en adelante desde la fecha de ejecución de programación maestra. Está definido por el número de días que especifique. Puede controlar el límite de tiempo de puesta en firme de las siguientes formas:

- Para definir el límite de tiempo de puesta en firme predeterminado para un grupo de cobertura, vaya **Planificación maestra** \> **Configuración** \> **Cobertura** \> **Grupos de cobertura**, y seleccione un grupo de cobertura. A continuación, en la pestaña desplegable **Otro**, en el campo **Límite de tiempo de puesta en firme automática (días)**, especifique el número de días.
- Para sobrescribir el límite de tiempo de puesta en firme que se define para el grupo de cobertura para un artículo específico, vaya **Gestión de información de productos** \> **Productos emitidos**, después del panel de acciones seleccione **Plan** y después seleccione **Cobertura de artículos**. A continuación, en la pestaña **General** , seleccione **Límite de tiempo de la anulación** y en el campo **Límite de tiempo de puesta en firme automática (días)**, especifique el número de días.
- Para sobrescribir el límite de tiempo de consolidación que se define para el grupo de cobertura y la cobertura de artículos para un plan maestro específico, vaya a **Planificación maestra** \> **Configuración** \> **Planes maestros** y seleccione un plan maestro. A continuación, en la pestaña desplegable **Límite de tiempo en días**, establezca **Congelar** en **Sí** y escriba en número de días.

Si se activa la puesta en firme automática para la ejecución del plan maestro que usa la optimización de la planificación, el proceso de puesta en firme automática se realiza de acuerdo con la configuración de la puesta en firme automática. Si la puesta en firme automática está activada, o si la planificación se inicia desde la página **Requisitos netos**, se omite el proceso de puesta en firme automática.

## <a name="planning-optimization-vs-the-built-in-supply-chain-management-planning-engine"></a>Optimización de la planificación comparada con el motor de planificación de Supply Chain Management

La optimización de la planificación y el motor de planificación que se integra en Microsoft Dynamics 365 Supply Chain Management pueden utilizarse en pedidos planificaos de puesta en firme automática. Sin embargo, existen algunas diferencias importantes. Por ejemplo, mientras que la optimización de la planificación utiliza la fecha del pedido (es decir, la fecha inicial) para determinar qué pedidos planificados desea poner en firme, el motor de planificación de Supply Chain Management usa la fecha de requisito (es decir, la fecha final). A continuación se indica un resumen de las diferencias.

**Optimización de planificación**

- La puesta en firme automática se basa en la fecha del pedido (fecha inicial).
- Dado que la fecha del pedido (fecha inicial) activa la puesta en firme, no tiene que tener e cuenta el plazo como parte del límite de tiempo de la puesta en firme.
- Si desea poner en firme todos los pedidos que deben iniciarse durante la semana actual, el límite de tiempo de la puesta en firme debe ser una semana.

**Motor de planificación de Supply Chain Management integrado**

- La puesta en firme automática en la fecha de requisito (fecha final).
- Para ayudar a garantizar que los pedidos se ponen en firme a tiempo, el límite de tiempo de puesta en firme debe ser superior al plazo.
- Si desea poner en firme todos los pedidos que deben iniciarse durante la semana actual, el límite de tiempo de la puesta en firme debe ser el plazo más una semana.
