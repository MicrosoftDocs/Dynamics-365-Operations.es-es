---
title: Asociar activos fijos con arrendamientos
description: El tema explica cómo asociar un activo fijo existente con un nuevo arrendamiento.
author: moaamer
ms.date: 10/28/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2020-10-28
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: 0e2261755d98ee38564b4b864daf8e79551d1239
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/01/2021
ms.locfileid: "5814089"
---
# <a name="associate-fixed-assets-with-leases"></a>Asociar activos fijos con arrendamientos

[!include [banner](../includes/banner.md)]

El tema explica cómo asociar un activo fijo existente con un nuevo arrendamiento. Cuando asocia un activo fijo con un arrendamiento, el valor del activo por derecho de uso (ROU) en el reconocimiento inicial será el coste de adquisición del activo fijo.

Antes de poder asociar un activo fijo con un arrendamiento, debe crear un registro para el activo fijo en Activos fijos. Entonces, en la página **Resumen de arrendamientos**, debe crear un arrendamiento y vincular el activo a ese arrendamiento.

1. Agregue un arrendamiento siguiendo los pasos de [Agregar o copiar arrendamientos](add-lease.md). En la página **Agregar arrendamiento**, en el campo **Número de activo fijo**, seleccione el activo que aún no se ha adquirido.
2. Seleccione **Libros** y confirme la programación de pagos.
3. Seleccione **Reconocimiento inicial**.
4. Seleccione **Diario de arrendamientos de activos**.

    El asiento de diario de reconocimiento inicial para el arrendamiento carga el activo fijo por el importe que generalmente se carga en la cuenta de activos por derecho de uso.

    Ahora puede ver el tipo de transacción y reservar el activo fijo.

5. Seleccione **Detalles de diario**.
6. Seleccione **Líneas** para ver las líneas individuales del movimiento de diario.
7. Seleccione la línea del diario que contiene el activo y luego seleccione la pestaña **Activos fijos**.

    La pestaña **Activos fijos** muestra el tipo de transacción y el libro. Por defecto, el campo **Tipo de transacción** está configurado en **Adquisición**, y el campo **Libro** se establece en el libro actual del activo fijo.

Después de registrar el movimiento de diario de reconocimiento inicial, la transacción aparece como una transacción de adquisición para el activo fijo. Para ver la tabla de transacciones, vaya a **Activos fijos \> Activos fijos \> Activos fijos**, seleccione el activo apropiado y luego seleccione **Valoraciones**. Debería aparecer que el movimiento de diario de reconocimiento inicial ha creado una transacción de adquisición para el activo fijo especificado.

El activo fijo ahora se puede depreciar utilizando la funcionalidad de depreciación estándar de Activos fijos. Para obtener más información sobre depreciación, consulte [Convenciones y métodos de depreciación](../fixed-assets/depreciation-methods-conventions.md).

> [!NOTE]
> Si asocia un activo fijo con un arrendamiento, los botones **Depreciación de activos** y **Deterioro del arrendamiento** están desactivados en Arrendamiento de activos. Puede ver la depreciación de activos y las transacciones de deterioro de arrendamientos desde Activos fijos. El botón **Transacciones de activos**, que abre un formulario de consulta, también está desactivado. También puede abrir el formulario de consulta **Transacciones de activos** en Activos fijos.  


[!INCLUDE[footer-include](../../includes/footer-banner.md)]