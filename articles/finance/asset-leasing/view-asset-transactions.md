---
title: Ver transacciones de pasivos, activos y gastos
description: Este artículo explica cómo ver las transacciones de un activo arrendado. Estas transacciones incluyen transacciones de pasivo por arrendamiento y transacciones de gastos de ejecución que se han registrado.
author: moaamer
ms.date: 04/12/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: SysQueryForm
audience: Application User
ms.reviewer: kfend
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2020-10-28
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: 552b5a6044950c4dd7547a5239c1b3f7d355dbce
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/03/2022
ms.locfileid: "8906424"
---
# <a name="view-liability-asset-and-expense-transactions"></a>Ver transacciones de pasivos, activos y gastos

[!include [banner](../includes/banner.md)]

Este artículo explica cómo ver las transacciones de un activo arrendado. Estas transacciones incluyen transacciones de pasivo por arrendamiento y transacciones de gastos de ejecución que se han registrado. Los valores en libros del activo de pasivo y por derecho de uso (ROU) se utilizan en varios informes. También se utilizan para calcular valores de ajuste.

## <a name="liability-transactions"></a>Transacciones de pasivos

Para ver las transacciones de pasivos por arrendamiento, seleccione un arrendamiento en la página **Resumen de arrendamientos** y luego seleccione **Libros** para abrir los libros que se adjuntan al registro de arrendamiento. Después de que se haya registrado un reconocimiento inicial, una factura o un diario de intereses, seleccione **Transacciones de pasivo**.

La página **Transacciones de pasivo** muestra las transacciones que aumentan o disminuyen el pasivo por arrendamiento. Los importes negativos de esta página representan transacciones de crédito en la aplicación estándar. Cualquier acumulación de intereses se muestra como valores negativos y aumenta el pasivo por arrendamiento total. Cualquier ajuste de arrendamiento se muestra como valores positivos o negativos, dependiendo de la naturaleza y el impacto del libro de arrendamiento. El saldo total neto actual del pasivo por arrendamiento para el arrendamiento seleccionado se muestra en la parte inferior izquierda de la página.

## <a name="asset-transactions"></a>Transacciones de activos

Para ver las transacciones de activos por arrendamiento, seleccione un arrendamiento en la página **Resumen de arrendamientos** y luego seleccione **Libros** para abrir los libros de arrendamiento adjuntos al registro de arrendamiento. A continuación, seleccione **Transacciones de activos**.

La página **Transacciones de activos** muestra las transacciones que aumentan o disminuyen el activo de arrendamiento y las cuentas de depreciación acumulada. Los débitos se muestran como valores positivos y los créditos se muestran como valores negativos, como en la página **Transacciones de pasivos**. El reconocimiento inicial publicado y el siguiente de la depreciación acumulada se muestran en la parte inferior izquierda de la página como saldo de activos. 

## <a name="expenses-transactions"></a>Transacciones de gastos

Para ver las transacciones de gastos por arrendamiento, seleccione un arrendamiento en la página **Resumen de arrendamientos** y luego seleccione **Libros** para abrir los libros de arrendamiento adjuntos al registro de arrendamiento. A continuación, seleccione **Transacciones de gastos**.

La página **Transacciones de gastos** muestra todos los gastos que se han registrado contra el arrendamiento, como los gastos por intereses, los gastos de depreciación y los gastos a cargo del arrendatario en un arrendamiento de capital.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
