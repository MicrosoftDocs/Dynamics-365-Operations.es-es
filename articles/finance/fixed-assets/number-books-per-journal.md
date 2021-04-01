---
title: Número de libros por diario
description: Este tema describe la relación entre diarios y libros de activos cuando crea una propuesta de adquisición o depreciación de activos fijos a través de un trabajo por lotes. Puede definir el número máximo de libros que se incluyen para cada adquisición y para depreciación.
author: moaamer
manager: Ann Beebe
ms.date: 11/19/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2020-11-19
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: 7f266e458802e65f0955ae8f8933f9bee2eca972
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2021
ms.locfileid: "5256724"
---
# <a name="number-of-books-per-journal"></a>Número de libros por diario

[!include [banner](../includes/banner.md)]

Este tema describe la relación entre diarios y libros de activos cuando crea una propuesta de adquisición o depreciación de activos fijos a través de un trabajo por lotes. Puede definir el número máximo de libros que se incluyen para cada adquisición y para la depreciación utilizando los campos de la sección **Número de libros por diario**, en la pestaña **General** de la página **Parámetros de activos fijos** (**Activos fijos \> Configurar \> Parámetros de activos fijos**). Estos campos le permiten distribuir el número de libros de activos por diario de adquisiciones y diario de depreciación.

Para una propuesta de adquisición, el valor predeterminado es al menos 10.000 libros. Para una propuesta de depreciación, el valor predeterminado es al menos 2000 libros.

Por ejemplo, si hay 4000 activos fijos y dos libros están asociados con cada activo, un libro se registrará en la capa actual y el otro libro se registrará en la capa de impuestos. Si adquiere 4000 activos fijos mediante el procesamiento por lotes, el trabajo por lotes que crea un diario de adquisición de activos fijos contendrá 4000 libros de activos.

> [!NOTE]
> El diario que se crea seguirá utilizándose hasta que se complete el trabajo por lotes.
>
> Los libros derivados no se incluyen en el número máximo de libros por diario.

Puede utilizar el procesamiento por lotes para ejecutar la depreciación del mismo conjunto de activos adquiridos. Por ejemplo, un trabajo por lotes crea dos diarios de depreciación, cada uno de los cuales consta de 2000 libros de activos. El primer diario contendrá libros asociados con los activos fijos numerados del 1 al 2000. El segundo diario contendrá entonces los libros asociados con los activos fijos numerados del 2001 al 4000.

El trabajo de procesamiento por lotes excluye los libros cerrados. Por ejemplo, en un trabajo por lotes para depreciación, se cierran 10 de los primeros 2000 libros. En este caso, el primer diario contendrá libros asociados con los activos fijos numerados del 1 al 2011. El segundo diario contendrá entonces los libros asociados con los activos fijos numerados del 2012 al 4000.

El límite en la cantidad de libros se aplica si no existen id. de activos duplicados en el mismo diario. Sin embargo, si el id. del activo es el mismo que el id. del libro, se puede exceder el número de libros por diario para mantener el id. del activo en el mismo diario.

Por ejemplo, hay 5001 id. de activos fijos, tres libros están asociados con cada id. de activo fijo y cada libro de activos se publica en la misma capa de registro. Ejecute la depreciación durante tres meses consecutivos, sin resumen.  El diario de depreciación se creará mediante un trabajo por lotes y el sistema creará siete diarios que tienen 667 id. de activos fijos y tres libros para cada id. de activo fijo. El resultado serán 2001 libros. Por lo tanto, en tres meses, habrá 6003 líneas de diario para mantener los mismos id. de activos en el mismo diario. El sistema también creará un diario que tiene 332 id. de activos fijos y tres libros para cada id. de activo fijo. En tres meses, habrá 2988 líneas.

> [!Note] 
> Si se activa el parámetro **Resumir depreciación** al crear una propuesta de depreciación, el valor del campo **Número de libros por diario - Propuesta de depreciación** no surtirá efecto. En este caso, el número de libros por diario es 6000, el límite interno definido.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]