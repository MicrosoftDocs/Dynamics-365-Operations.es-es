---
title: Permite registrar transacciones de activos fijos a las capas de registro
description: "Este artículo ofrece una visión general de la funcionalidad de la capa de registro para las transacciones de activos fijos."
author: twheeloc
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: AssetBookTable, LedgerJournalTransAsset
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 3001
ms.assetid: 7dabde57-0843-47c3-85ef-f36b6f472e30
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 4bb647cfd3f012efbffa93a81462c538a24ac850
ms.openlocfilehash: 4b112eee303604149c7609972a60c2014d4be423
ms.lasthandoff: 03/31/2017


---

# <a name="post-fixed-asset-transactions-to-posting-layers"></a>Permite registrar transacciones de activos fijos a las capas de registro

Este artículo ofrece una visión general de la funcionalidad de la capa de registro para las transacciones de activos fijos.

Un activo fijo se deprecia de distintas formas y para distintos fines. La depreciación relacionada con los impuestos se calcula usando las reglas actuales de impuestos para lograr la depreciación más alta posible antes de los impuestos, pero la depreciación a efectos de notificación se calcula de acuerdo con los estándares y leyes contables. Los distintos tipos de depreciación se calculan y registran independientemente en las capas de registro.

Cada libro vinculado a un activo fijo se configura para una capa de registro concreta que tiene un objetivo de depreciación general. Existen diez capas de registro: Actual, operaciones, Impuesto y siete niveles personalizados. También puede deshabilitar el registro del libro en la contabilidad general configurando el campo Registrar en el libro mayora No. El campo de Capa de registro se establece automáticamente como Ninguno. Normalmente, los libros que no registran en la contabilidad general se usan para fines de informes de impuestos. Este proporciona la flexibilidad adicional para eliminar las transacciones históricas para el libro de activos, ya que no se han confiadas en la contabilidad general.

Los diarios de activos se definen mediante la página de Nombres de diario en Contabilidad general > Configuración del diario > Nombres de diario. Cada diario en el que puede registrar las depreciaciones se define por su nombre de diario para una capa de registro únicamente. La capa de registro en el diario no se puede cambiar. Esta restricción permite garantizar que las transacciones de cada capa de registro se mantengan aparte. Se debe crear un nombre de diario como mínimo para cada capa de registro. Si utiliza libros que no registran en la contabilidad general, también deberá crear un diario en la capa de registro se establece en ninguno.

Puede especificar las cuentas contables para las transacciones de activos fijos en la página de Perfiles de contabilización de activos fijos. Para cada perfil de registro, debe seleccionar el tipo de transacción y el libro correspondiente, y después designar las cuentas contables. Configurar un registro del perfil de contabilización para cada libro que se envía a la contabilidad general.

> [!NOTE] 
> Mediante los libros derivados, puede registrar transacciones para distintas capas de registro simultáneamente. Puede crear transacciones del libro principal en un diario con la capa de registro correspondiente a la capa de registro del libro. Durante el registro, las transacciones derivadas del libro se registran en sus capas de registro adecuadas.

Para obtener más información, consulte los libros [] (derivados derived-books.md) y [registro con los libros derivados post-derived-value-models.md] ().


