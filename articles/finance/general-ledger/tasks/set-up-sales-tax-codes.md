---
title: Configurar códigos de impuestos
description: Este tema explica cómo configurar códigos de impuestos en Dynamics 365 Finance.
author: twheeloc
ms.date: 09/27/2021
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: TaxTable, TaxData
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: kfend
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 69e2cf9a16fe0e694154cccf9b49944b49c79b90
ms.sourcegitcommit: 23588e66e25c05e989f3212ac519d7016820430a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/13/2022
ms.locfileid: "8565864"
---
# <a name="set-up-sales-tax-codes"></a>Configurar códigos de impuestos

[!include [banner](../../includes/banner.md)]

Este tema explica cómo configurar códigos de impuestos. Los códigos de impuestos se crean para cada impuesto indirecto o arancel que la entidad jurídica está obligada a calcular, recaudar y pagar a las autoridades fiscales.

Esta tarea usa la empresa de demostración USMF.

1. Vaya al **panel de navegación > Impuestos > Impuestos indirectos > Impuestos > Códigos de impuestos**.
2. Seleccione **Nuevo**.
3. En el campo de **código de impuestos**, escriba un valor.
4. En el campo **Nombre**, escriba un valor.
5. Seleccione un **período de liquidación** abriendo la lista desplegable para especificar qué autoridad fiscal y en qué intervalos tienen que notificarse y pagarse estos impuestos.
6. Seleccione un **grupo de registro** para especificar las cuentas principales para registrar los impuestos en contabilidad general.
7. Expanda la ficha desplegable **Cálculo**. Tiene varios campos que controlan cómo se calcularán los importes de impuestos. Complete estos campos según convenga.  
8. En el **Panel de acciones** en la parte superior de la interfaz, seleccione **Código de impuestos**.
9. Seleccione **Valores**.
10. Escriba el valor para este código de impuestos en la columna **valor** .

    En la ficha desplegable **Cálculo**, en el campo **Origen**, si está seleccionado el **Importe por unidad**, el valor se multiplicará por la cantidad de la transacción para calcular el importe de impuestos.  Si el código de impuesto no es un impuesto basado en la unidad, el valor es un porcentaje que se aplica en el origen de este código de impuesto para calcular el importe de impuestos.     

11. Seleccione **Guardar**.
12. Cierre la página.
13. Seleccione **Guardar**.

A partir de Microsoft Dynamics 365 Finance, versión 10.0.22, si está utilizando el [Servicio de impuestos](../../localizations/global-tax-calcuation-service-overview.md) y la característica [**Admitir varios números de registro de IVA**](../../localizations/emea-multiple-vat-registration-numbers.md) está habilitada en el espacio de trabajo **Administración de funciones**, puede usar el campo **Tipo de impuesto** para especificar el tipo del código de impuestos. Los siguientes valores están disponibles:

- IVA estándar
- IVA reducido
- 0 % de IVA
- Especial
- Otra

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
