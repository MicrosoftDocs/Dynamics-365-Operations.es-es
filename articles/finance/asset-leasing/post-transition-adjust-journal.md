---
title: Registrar asientos de diario de ajuste de transición en Arrendamiento de activos
description: Este tema describe la funcionalidad que le permite realizar la transición de una cartera de arrendamientos a los nuevos estándares de contabilidad de arrendamientos, Tema de codificación de estándares de contabilidad 842 (ASC 842) y Norma Internacional de Información Financiera 16 (IFRS 16).
author: moaamer
manager: Ann Beebe
ms.date: 10/28/2020
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
ms.search.validFrom: 2020-10-28
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: 51ae41e22507d77f32b8b0f4685cce797fd19cff
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/15/2021
ms.locfileid: "4969562"
---
# <a name="post-transition-adjustment-journal-entries-in-asset-leasing"></a>Registrar asientos de diario de ajuste de transición en Arrendamiento de activos

[!include [banner](../includes/banner.md)]

Este tema describe la funcionalidad que le permite realizar la transición de una cartera de arrendamientos a los nuevos estándares de contabilidad de arrendamientos: Tema 842 de codificación de estándares de contabilidad (ASC 842), que es el estándar en Principios de contabilidad generalmente aceptados en los EE. UU. (US GAAP), y Norma Internacional de Información Financiera 16 (IFRS 16).

Para obtener información sobre cómo configurar un libro para la transición a los nuevos estándares, consulte [Configurar libros de arrendamiento](set-up-lease-books.md).

Cuando crea un asiento de diario de ajuste de transición, se genera un asiento de diario. Esta entrada refleja el impacto en el balance de situación del registro del arrendamiento bajo las nuevas normas en esa fecha. La cuenta de activos apropiada se adeuda por el importe en libros en esa fecha y la cuenta de pasivo se abona. La diferencia se adeuda o abona a las ganancias acumuladas.

Para publicar un ajuste de transición de conformidad con las nuevas normas contables, siga estos pasos.

1. En la página **Resumen de arrendamiento**, seleccione el arrendamiento y luego seleccione **Libros**.
2. En el libro, seleccione **Programación de pagos**.
3. En el cuadro de diálogo **Programación de pagos**, seleccione **Confirmar**. A continuación, cierre el cuadro de diálogo.
4. Seleccione **Ajuste de transición**.

    > [!NOTE]
    > Se puede crear un ajuste de transición solo para los libros de arrendamiento asignados a un libro donde el campo **Libro de transición** está disponible. Si el valor en el campo **Inicio de arrendamiento** es posterior a la fecha de transición, el valor del campo **Ajuste de transición** no se actualizará.

5. Para ver el movimiento de diario, seleccione **Diarios de arrendamiento de activos**.
6. Seleccione el nuevo diario y luego seleccione **Registrar**.