---
title: Dividir un activo fijo
description: En este tema se explica cómo dividir un porcentaje de un libro de activos a un nuevo libro de activos.
author: saraschi2
ms.date: 08/06/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: AssetTable, AssetBook, AssetSplit, AssetBookLookup, LedgerJournalTable, LedgerJournalTransAsset
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 1ac7bc9ae9040f9668c36c570be795ebeb7c6970049ff911b1caeadd06f31d0a
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2021
ms.locfileid: "6778999"
---
# <a name="split-a-fixed-asset"></a>Dividir un activo fijo

[!include [banner](../../includes/banner.md)]

En este tema se explica cómo dividir un porcentaje de un libro de activos a un nuevo libro de activos. Usa el rol de contable y los datos de prueba de USMF.

## <a name="create-a-new-fixed-asset"></a>Crear un activo fijo nuevo

1. En el panel de exploración, vaya a **Módulos \> Activos fijos \> Activos fijos \> Activos fijos**.
2. Seleccione **Nuevo**.
3. En el campo **Grupo de activos fijos**, escriba o seleccione un valor. Anote el número de activo fijo que se va a usar en el proceso de división más adelante.
4. En el campo **Nombre**, escriba un valor.
5. Cierre el formulario.

## <a name="split-a-fixed-asset"></a>Dividir un activo fijo

Antes de dividir un activo totalmente depreciado, hay que cambiar manualmente el estado del libro de activos de **Cerrado** a **Abierto**. Este paso es necesario porque el estado del libro debe ser **Abierto** si se van a contabilizar transacciones para el activo (por ejemplo, para una venta de cancelación). También debe activr el parámetro **Permitir múltiples transacciones en un asiento** en la pestaña **General** de la página **Parámetros del libro mayor**. Una vez que se cambia el estado del libro de activos y se han permitido múltiples transacciones dentro de un asiento, complete los siguientes pasos para dividir el activo.

1. En la lista, busque y seleccione el vínculo del activo fijo para dividir.
2. Seleccione **Libros**. Seleccione el libro para dividir el nuevo activo.
3. Seleccione **Funciones**.
4. Seleccione **Dividir activo fijo**.
5. En el campo **Hasta activo fijo**, escriba o seleccione un valor.
6. En el campo **Al libro**, seleccione el botón desplegable para abrir la búsqueda.
7. En el campo **Fecha de transacción**, especifique una fecha.
8. En el campo **Porcentaje**, especifique un número.
9. En el campo **Nombre del diario**, especifique o seleccione un valor.
10. Seleccione **Aceptar**.

## <a name="post-the-journal-transaction"></a>Registrar la transacción de diario

1. En el panel de navegación, vaya a **Módulos \> Activos fijos \> Entradas del diario \> Diario de activos fijos**.
2. En la lista, seleccione el diario creado con el proceso de la división.
3. Seleccionar **Líneas**.

    - Compruebe las líneas de diario creadas.
    - Se creó una transacción de ajuste de adquisición para que el activo original reduzca el valor en el porcentaje especificado durante el proceso de la división.
    - Se crea una transacción de adquisición del nuevo activo para el mismo importe.

4. Seleccione **Registrar**.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]