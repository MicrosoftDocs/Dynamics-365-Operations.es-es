---
title: Configurar categorías de cuenta principal
description: En este tema explica cómo configurar categorías de cuenta principal en Dynamics 365 Finance.
author: aprilolson
manager: AnnBe
ms.date: 08/08/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: MainAccountCategory, MainAccountCategoryLink
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 9e0a015283064af2287013bccc065b4467a308c5
ms.sourcegitcommit: 57e1dafa186fec77ddd8ba9425d238e36e0f0998
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/18/2020
ms.locfileid: "3144798"
---
# <a name="set-up-main-account-categories"></a>Configurar categorías de cuenta principal

[!include [banner](../../includes/banner.md)]

En este tema explica cómo configurar categorías de cuenta principal. Las categorías de cuenta principal se usan para los informes predeterminados en los informes financieros y en Power BI. Las categorías de cuenta principal que se crean de forma predeterminada se pueden cambiar de nombre pero no se pueden eliminar. Las categorías de cuentas adicionales se pueden crear y usar para fines de informes y análisis. En este tema tarea se utiliza la empresa de demostración USMF.

## <a name="create-a-main-account-category"></a>Crear una categoría de cuenta principal
1. En el panel de navegación, vaya a **Módulos > Contabilidad general > Plan de cuentas > Cuentas > Categorías de cuenta principal**.
2. Seleccione **Nuevo**.
3. En el campo **Categoría de cuenta principal**, especifique un nombre único.
4. En el **campo Descripción**, especifique una descripción para la categoría de cuenta principal.
5. En el campo **Tipo de cuenta principal**, seleccione el tipo de cuenta principal que se vinculará a la categoría.

## <a name="link-main-accounts-to-account-category"></a>Vincular cuentas principales a categoría de cuenta
1. Haga clic en **Vincular cuentas principales**.
2. En la lista, seleccione las cuentas principales para asignar a la categoría de cuenta principal marcando las casillas de la columna **Vinculada**. La asignación de cuentas principales a una categoría de cuenta principal agregará los saldos de las cuentas cuando se use esa categoría para análisis e informes financieros.  
3. Active o desactive la opción **Vinculada** para elegir las cuentas principales.
4. Seleccione **Aceptar**.
5. Seleccione **Sí**.
