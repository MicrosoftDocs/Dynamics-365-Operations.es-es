---
title: Cambiar o reasignar un calendario de libro mayor
description: Este tema explica cómo cambiar el calendario que está asignado actualmente a un libro mayor y cómo asignar un nuevo calendario al libro mayor.
author: kweekley
ms.date: 05/07/2021
ms.topic: index-page
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2021-5-07
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: 25777a5b807921acc13338116627e9356fe62a20
ms.sourcegitcommit: 04e6c1c9400e1b582180cf3e0e4767434e736c26
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/05/2022
ms.locfileid: "8711642"
---
# <a name="change-or-reassign-a-ledger-calendar"></a>Cambiar o reasignar un calendario de libro mayor

[!include [banner](../includes/banner.md)]

Este tema explica cómo cambiar el calendario que está asignado actualmente a un libro mayor y cómo asignar un nuevo calendario al libro mayor.

## <a name="issue"></a>Problema

En algún momento, las empresas deben cambiar el calendario existente asignado a un libro mayor o asignar un nuevo calendario.

## <a name="resolution"></a>Resolución

Hay dos escenarios de cambio o reasignación un calendario de libro mayor. El primer escenario conlleva el cambio de un calendario existente que ya está asignado al libro mayor. El segundo escenario implica la creación de un nuevo calendario y su asignación al libro mayor. Ambos cambios se pueden realizar en cualquier momento, incluso después de haber registrado transacciones en el libro mayor.

### <a name="change-an-existing-fiscal-calendar"></a>Cambiar un calendario fiscal existente

Para cambiar un calendario existente que está asignado a su libro mayor, vaya a **Libro mayor \> Configuración del libro mayor \> Libro mayor** y seleccione el vínculo del calendario fiscal para abrir la página **Calendarios de libro mayor**.

Existen límites en los cambios que se pueden realizar en un calendario. Por ejemplo, puede cambiar las fechas de inicio y finalización de los *periodos* en un año, pero no puede cambiar las fechas de inicio y finalización de un *año* del calendario.

Para cambiar los períodos en un año, seleccione el calendario y el año adecuados. Primero, utilice el botón **Eliminar período** para eliminar algunos de los períodos operativos existentes o todos ellos. Pueden eliminarse todos los períodos operativos, excepto el primero. A continuación, utilice el botón **Dividir período** para dividir el período o períodos restantes en nuevos períodos, introduciendo una fecha de inicio apropiada para el período siguiente.

Después de cambiar los períodos de un calendario, debe ejecutar el proceso **Volver a calcular los períodos del libro mayor** en cada entidad jurídica (empresa) a la que está asignado el calendario. Aunque ningún mensaje de advertencia le recuerda que debe completar este paso, el proceso de recálculo es necesario para actualizar el período asignado a cada transacción registrada en el libro mayor. Para ejecutar el proceso de recálculo, seleccione **Recalcular los períodos del libro mayor**, en la página **Configuración del libro mayor** de cada empresa.

Si no se ejecuta el proceso de recálculo, es posible que los saldos de las transacciones de un saldo de comprobación o informe financiero puedan estar incluidos incorrectamente en los períodos. En este caso, puede corregir los saldos en cualquier momento, ejecutando el proceso de recálculo.

### <a name="assign-a-new-fiscal-calendar"></a>Asignar un nuevo calendario fiscal

Para asignar un nuevo calendario fiscal, vaya a **Libro mayor \> Configuración del libro mayor \> Libro mayor** y seleccione **Editar** para poner la página **Libro mayor** en modo de edición. Después, en el campo **Calendario fiscal**, seleccione un nuevo calendario fiscal.

Después de cambiar el calendario fiscal de un libro mayor, debe ejecutar **Recalcular los períodos del libro mayor**. Cuando asigna un nuevo calendario fiscal a un libro mayor, un mensaje le recuerda que debe completar este paso. Aunque el mensaje parezca indicar que el proceso de recálculo es opcional, no lo es. Es necesario actualizar el período que se asigna a cada transacción registrada en el libro mayor. Para ejecutar el proceso de recálculo, seleccione **Recalcular los períodos del libro mayor**, en la página **Configuración del libro mayor**.

Si no se ejecuta el proceso de recálculo, es posible que los saldos de las transacciones de un saldo de comprobación o informe financiero puedan estar incluidos incorrectamente en los períodos. En este caso, puede corregir los saldos en cualquier momento, ejecutando el proceso de recálculo.
