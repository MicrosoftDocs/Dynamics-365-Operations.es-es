---
title: Configurar nombres de diarios de arrendamiento
description: Este tema explica cómo definir nombres de diarios de arrendamiento. Los nombres de los diarios de arrendamiento especifican los diarios en los que se contabilizan las entradas que se originan en Arrendamiento de activos.
author: moaamer
ms.date: 04/12/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: AssetLeasePostingAccounts
audience: Application User
ms.reviewer: roschlom
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2020-10-28
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: 1ea35ec40ddd459e1a9e7641557147e23fe45d3e
ms.sourcegitcommit: b9c2798aa994e1526d1c50726f807e6335885e1a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/13/2021
ms.locfileid: "7343223"
---
# <a name="set-up-lease-journal-names"></a>Configurar nombres de diarios de arrendamiento

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]


Los nombres de los diarios de arrendamiento especifican los diarios en los que se contabilizan las transacciones que se originan en Arrendamiento de activos. Solo los nombres de diarios asignados al tipo de diario **Arrendamiento de activos** aparecen en los campos **Reconocimiento inicial** y **Nombre del diario mensual** de la página **Parámetros de arrendamiento de activos**. Solamente el tipo de diario **Registro de facturas de proveedores** se puede asignar al campo **Nombre del diario de facturas**.

El sistema bloquea la edición de ciertos campos financieros para evitar variaciones entre las transacciones y los programas. Algunos campos que están bloqueados incluyen: **Cuenta**, **Cantidades**, **Dimensiones financieras**, **Divisa** y **Tipo de transacción**. Además, no podrá agregar o eliminar líneas de asientos de diario en los asientos de diario de arrendamiento de activos, ya que esto podría causar variaciones entre los horarios y las transacciones.


Para configurar los nombres de los diarios de arrendamiento, siga estos pasos.

1. Vaya a **Arrendamiento de activos \> Configuración \> Parámetros de arrendamiento de activos**.
2. En la pestaña **General**, en el campo **Nombre del diario de reconocimiento inicial**, seleccione un diario. Todas las entradas del diario de reconocimiento inicial se registrarán en este nombre de diario.
3. En el campo **Nombre de diario de facturas**, seleccione un diario. Si la opción **Pagar al proveedor** está configurada en **Sí** para el libro de arrendamiento, las facturas de pago de arrendamiento y gastos se publicarán en este nombre de diario.
4. En el campo **Nombre de diario de arrendamiento**, seleccione un diario. Todos los movimientos de depreciación, intereses y reclasificación a corto plazo se registrarán en este nombre de diario. Si la opción **Pagar al proveedor** está configurada en **No** para el libro de arrendamiento, las movimientos de pagos de arrendamientos y de pagos de gastos se publicarán en este nombre de diario.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
