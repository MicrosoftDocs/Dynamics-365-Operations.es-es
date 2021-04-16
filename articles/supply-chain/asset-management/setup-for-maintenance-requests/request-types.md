---
title: Tipos de solicitudes de mantenimiento
description: En este tema se explica cómo configurar tipos de solicitudes de mantenimiento en Administración de activos.
author: johanhoffmann
ms.date: 07/26/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2019-07-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 4ff80b2f3e23f46467b8a2fe7a2abd805e5e3a20
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/01/2021
ms.locfileid: "5808505"
---
# <a name="maintenance-request-types"></a>Tipos de solicitudes de mantenimiento

[!include [banner](../../includes/banner.md)]

 

Los tipos de solicitudes de mantenimiento se usan para clasificar las solicitudes de mantenimiento. Por ejemplo, puede que tenga tipos de solicitudes de mantenimiento relacionados con el mantenimiento preventivo y el mantenimiento correctivo. O bien puede tener un tipo de solicitud de mantenimiento especial que se use para administrar la reparación de los activos (reparación interna).

Un tipo de solicitud de mantenimiento define la afiliación con un grupo de estados de ciclo de vida de solicitud de mantenimiento (modelo de ciclo de vida de mantenimiento). Los modelos de ciclo de vida de solicitud de mantenimiento definen los estados de ciclo de vida que se pueden establecer para una solicitud de mantenimiento. (Ejemplos de estados de ciclo de vida de solicitud de mantenimiento son **Creada**, **Activa** y **Finalizada**).

1. Seleccione **Administración de activos** \> **Configuración** \> **Solicitudes de mantenimiento** \> **Tipos de solicitudes de mantenimiento**.
2. Seleccione **Nuevo** para crear un tipo de solicitud de mantenimiento.
3. En el campo **Tipo de solicitud de mantenimiento** , especifique un identificador para el tipo de solicitud de mantenimiento.
4. Escriba un nombre en el campo **Nombre**.
5. En el FastTab **General**, en el campo **Modelo de ciclo de vida de solicitud de mantenimiento**, seleccione un modelo de ciclo de vida de solicitud de mantenimiento.
6. En el campo **Tipo de orden de trabajo**, seleccione un tipo de orden de trabajo. Cuando una solicitud de mantenimiento se convierte en una orden de trabajo, la orden de trabajo obtiene automáticamente el tipo de orden de trabajo relacionado con el tipo de solicitud de mantenimiento.

La ilustración siguiente muestra un ejemplo de la página **Tipos de solicitud de mantenimiento**.

![Página de tipos de solicitudes de mantenimiento](media/07-setup-for-requests.png)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]