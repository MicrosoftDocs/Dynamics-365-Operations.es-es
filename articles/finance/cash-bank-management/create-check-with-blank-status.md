---
title: Crear cheques que tengan el estado en blanco
description: En este artículo se explica cómo crear cheques en blanco para una cuenta bancaria.
author: angelad116
ms.date: 10/24/2022
ms.topic: index-page
ms.prod: ''
ms.technology: ''
ms.search.form: BankChequeTable
audience: Application User
ms.reviewer: twheeloc
ms.custom: 21941
ms.assetid: d7e22bd8-fd0d-47e1-843f-45ab0193ff8d
ms.search.region: Global
ms.author: angelading
ms.search.validFrom: 2019-09-17
ms.dyn365.ops.version: AX 10.0.5
ms.openlocfilehash: 151991b399a30087c484262706e414e4e294bf7f
ms.sourcegitcommit: 0d5c07ba91a9ceb2eeb11db032fd28037216789d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/25/2022
ms.locfileid: "9715437"
---
# <a name="create-checks-that-have-blank-status"></a>Crear cheques que tengan el estado en blanco

[!include [banner](../includes/banner.md)]

En este artículo se explica cómo crear cheques en blanco. Por ejemplo, puede crear un cheque en blanco para registrar un cheque que ha resultado dañado y no se puede usar para el pago.

En la página **Cheques**, realice las tareas de mantenimiento para cheques. Por ejemplo, puede crear nuevos números de cheque y eliminar cheques. También puede crear cheques que tengan el estado **En blanco**. Tras crear cheques en blanco, no se podrán eliminar ni volver a utilizar en el sistema.

> [!NOTE]
> Esta característica está disponible en la página **Cheques** únicamente si se activa la característica **Crear cheques con un estado en blanco en la página Cheques** en la página **Administración de características**. Si la característica no está activada, los cheques con estado **En blanco** solo se pueden crear desde el cuadro de diálogo **Pago mediante cheque** durante el proceso de generación de pago en Proveedores.

Para abrir la página **Cheques**, vaya a **Gestión de efectivo y bancos \> Cuentas bancarias \> Cuentas bancarias** y, a continuación, en el panel de acciones, en la pestaña **Administrar pagos**, en el grupo **Información relacionada**, seleccione **Cheques**. Como alternativa, vaya a **Gestión de efectivo y bancos \> Consultas e informes \> Cheques**.

A continuación, para crear cheques con estado **En blanco**, en el panel de acciones, seleccione **Crear cheques en blanco**. Mientras el sistema está creando cheques en blanco, la cuenta bancaria asociada se desactiva temporalmente. Este comportamiento reduce el riesgo de que se generen pagos a la vez que se crean cheques en blanco. Tras completar el procesamiento, se reactiva la cuenta bancaria asociada.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
