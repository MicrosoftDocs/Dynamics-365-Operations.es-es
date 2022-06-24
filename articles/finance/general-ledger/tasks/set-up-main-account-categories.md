---
title: Configurar categorías de cuenta principal
description: En este artículo explica cómo configurar categorías de cuenta principal en Dynamics 365 Finance.
author: aprilolson
ms.date: 08/08/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: MainAccountCategory, MainAccountCategoryLink
audience: Application User
ms.reviewer: twheeloc
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: c48011c9988bdca694851476540db574efef7909
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/03/2022
ms.locfileid: "8879574"
---
# <a name="set-up-main-account-categories"></a>Configurar categorías de cuenta principal

[!include [banner](../../includes/banner.md)]

En este artículo explica cómo configurar categorías de cuenta principal. Las categorías de cuenta principal se usan para los informes predeterminados en los informes financieros y en Power BI. Las categorías de cuenta principal que se crean de forma predeterminada se pueden cambiar de nombre pero no se pueden eliminar. Las categorías de cuentas adicionales se pueden crear y usar para fines de informes y análisis. Este artículo usa la empresa de demostración de USMF.

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


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
