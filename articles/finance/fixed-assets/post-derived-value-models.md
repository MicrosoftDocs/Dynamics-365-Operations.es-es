---
title: Registro con los libros derivados
description: Este artículo describe cómo usar los libros derivados.
author: moaamer
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: AssetBookTable, LedgerJournalTransAsset
audience: Application User
ms.reviewer: kfend
ms.custom: 3421
ms.assetid: f5187c21-eec5-4148-b178-b8a5feff7f23
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: d0270ad1e66193832fb1139fca4439b36b5ffb84
ms.sourcegitcommit: dca54dd3afc7c94795d89c63050b105df2c48e3f
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/15/2022
ms.locfileid: "9682917"
---
# <a name="post-with-derived-books"></a>Registro con los libros derivados

[!include [banner](../includes/banner.md)]

Este artículo describe cómo usar los libros derivados.

Al registrar transacciones para un libro que contiene libros derivados, las transacciones del libro derivado se registran de forma automática en los diarios, pedidos de compra o facturas de servicios. No obstante, si prepara las transacciones del libro principal en el libro de activos fijos, podrá ver y modificar los importes de las transacciones derivadas antes de registrarlos.
-   Algunas cuentas, como las cuentas de proveedor y cliente e impuestos, se actualizan únicamente mediante los registros del libro principal. Las transacciones del libro derivado se contabilizan en las cuentas que se han definido para el libro derivado en la página de Perfiles de contabilización de activos fijos.
-   La adquisición se usa a menudo como el tipo de transacción del libro derivado. Esto se usa cuando el libro y el libro derivado se deben aplicar al activo fijo desde el momento de adquisición del activo fijo.
-   También se pueden aplicar otros valores para el tipo de transacción. Por ejemplo, si el libro principal de los libros derivados tiene los mismos intervalos en relación con la venta o cancelación, todos los tipos de transacción de activos fijos están disponibles para la configuración de un libro derivado.

> [!WARNING]
> La depreciación registrada en el libro derivado será del mismo importe que se registró para el libro principal. Si los métodos de depreciación son distintos entre los libros, no debe generar transacciones de depreciación mediante el proceso derivado. 

## <a name="example"></a>Ejemplo 
La siguiente información describe cómo configurar las transacciones de adquisición con la función del libro derivado.

1.  Crear libros en la página de Libros.
    -   El libro de contabilidad: MV 1, capa de registro actual
    -   El libro con fines tributarios: MV 2, capa de registro de impuestos

2.  En el MV 1, haga clic en la ficha de libros derivados y seleccione MV 2 en el campo Libro y Adquisición en el campo Tipo de transacción.

A continuación, los libros se podrán vincular a activos fijos concretos. 

Cuando una adquisición se registra para un activo fijo con libro MV 1, la adquisición se registra no sólo con el MV 1, sino también con el libro derivado MV 2. El estado de ambos libros de activo fijo se actualizará a Abierto.

> [!NOTE]                                                                                                         
> Si no utiliza los libros derivados, debe registrar la adquisición del activo fijo para el libro MV 1 y el libro VM 2.

Para obtener más información, consulte [Libros derivados](derived-books.md).





[!INCLUDE[footer-include](../../includes/footer-banner.md)]
