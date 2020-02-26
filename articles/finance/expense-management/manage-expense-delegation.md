---
title: Administrar delegación de gastos
description: Un usuario delegado de gastos puede crear y administrar informes de gastos en nombre de otro empleado de la organización.
author: KimANelson
manager: AnnBe
ms.date: 01/10/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: TrvParameters
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: knelson
ms.search.validFrom: 2020-01-10
ms.dyn365.ops.version: 10.0.9
ms.openlocfilehash: d792daa56d468830b56eb395fadda582b3b5bad6
ms.sourcegitcommit: 6a70f9ac296158edd065d52a12703b3ce85ce5ee
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/03/2020
ms.locfileid: "3015376"
---
# <a name="manage-expense-delegation"></a>Administrar delegación de gastos

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]


Un usuario delegado de gastos puede crear y administrar informes de gastos en nombre de otro empleado de la organización.

## <a name="configuring-expense-delegation"></a>Configuración de delegación de gastos

Para configurar un usuario como delegado de gastos, vaya a **Gestión de gastos > Configuración > General > Delegados** para abrir la página **Delegados**. Seleccione **Nuevo** y luego seleccione el empleado que tendrá un delegado definido. Introduzca el alias del usuario delegado y la fecha de inicio y finalización del período de delegación.

## <a name="managing-expense-delegation-on-behalf-of-another-employee"></a>Gestión de la delegación de gastos en nombre de otro empleado

Si la clave de gestión de características **Habilitar página de lista de delegados de gastos** está habilitada, la página de lista **Gastos delegados a mí** estará disponible navegando a **Gestión de gastos > Mis gastos > Gastos delegados a mí**.

Un usuario delegado puede filtrar y buscar rápidamente en los informes de gastos existentes que se han delegado al usuario. El usuario también puede crear rápidamente un nuevo informe de gastos en nombre de otros usuarios haciendo clic en **Nuevo informe de gastos**.

Los usuarios delegados también pueden crear y administrar informes de gastos en nombre de otros empleados navegando a **Gestión de gastos > Mis gastos > Informes de gastos** y haciendo clic en el botón **Abrir los gastos de otro usuario**.
