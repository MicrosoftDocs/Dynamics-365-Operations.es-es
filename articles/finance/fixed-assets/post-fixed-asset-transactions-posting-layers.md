---
title: Registrar las transacciones de activos fijos para registrar capas
description: Este artículo ofrece una visión general de la funcionalidad de la capa de registro para las transacciones de activos fijos.
author: moaamer
manager: AnnBe
ms.date: 04/25/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: AssetBookTable, LedgerJournalTransAsset
audience: Application User
ms.reviewer: roschlom
ms.custom: 3001
ms.assetid: 7dabde57-0843-47c3-85ef-f36b6f472e30
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 9a52374d52b3dcd435c79033d462a2982316a68b
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2021
ms.locfileid: "5240867"
---
# <a name="post-fixed-asset-transactions-to-posting-layers"></a>Registrar las transacciones de activos fijos para registrar capas

[!include [banner](../includes/banner.md)]

Este artículo ofrece una visión general de la funcionalidad de la capa de registro para las transacciones de activos fijos.

Un activo fijo se deprecia de distintas formas y para distintos fines. La depreciación relacionada con los impuestos se calcula usando las reglas actuales de impuestos para lograr la depreciación más alta posible antes de los impuestos, pero la depreciación a efectos de notificación se calcula de acuerdo con los estándares y leyes contables. Los distintos tipos de depreciación se calculan y registran independientemente en las capas de registro.

Cada libro vinculado a un activo fijo se configura para una capa de registro concreta que tiene un objetivo de depreciación general. Existen diez capas de registro: Actual, operaciones, Impuesto y siete niveles personalizados. También puede deshabilitar el registro del libro en la contabilidad general configurando el campo Registrar en el libro mayora No. El campo de Capa de registro se establece automáticamente como Ninguno. Normalmente, los libros que no se registran en la contabilidad general se usan para fines de informes tributarios. Este método proporciona flexibilidad adicional para eliminar las transacciones históricas para el libro de activos, ya que no se han asignado a la contabilidad general.

Los diarios de activos se definen mediante la página de Nombres de diario en Contabilidad general > Configuración del diario > Nombres de diario. Cada diario en el que puede registrar las depreciaciones se define por su nombre de diario para una capa de registro únicamente. La capa de registro del diario no se puede cambiar. Esta restricción permite garantizar que las transacciones de cada capa de registro se mantengan aparte. Se debe crear un nombre de diario como mínimo para cada capa de registro. Si utiliza libros que no se registran en la contabilidad general, también deberá crear un diario en el que la capa de registro se establezca en Ninguno.

Puede especificar las cuentas contables para las transacciones de activos fijos en la página de Perfiles de contabilización de activos fijos. Para cada perfil de registro, debe seleccionar el tipo de transacción y el libro correspondiente, y después designar las cuentas contables. Configurar un registro del perfil de contabilización para cada libro que se envía a la contabilidad general.

El activo fijo se puede introducir en documentos que solo respalden la capa de registro **Actual**, como **Pedido de compra**, **Factura de proveedor pendiente**, **Órdenes de venta** o **Factura de texto libre**. Al seleccionar un id. de activo fijo en cualquiera de esos documentos, el libro de activos se filtra con el libro de la capa de registro **Actual** y se completará automáticamente durante el registro cuando el sistema valide que la capa de registro de activos fijos es **Actual**. Si esa validación no se puede completar, el proceso de registro se detendrá. 

> [!NOTE] 
> El uso de libros derivados le permite registrar transacciones para distintas capas de registro simultáneamente. Las transacciones del libro principal se crean en un diario o documento de origen, donde la capa de registro corresponde a la capa de registro del libro. Durante el registro, las transacciones derivadas del libro se registrarán en sus capas de registro adecuadas. 


Para obtener más información, consulte [Libros derivados](derived-books.md) y [Registrar con los libros derivados](post-derived-value-models.md).





[!INCLUDE[footer-include](../../includes/footer-banner.md)]