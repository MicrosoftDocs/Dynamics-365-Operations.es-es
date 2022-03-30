---
title: Calcular TDS en facturas usando diarios
description: Este tema enumera los pasos para calcular los impuestos deducidos en el origen (TDS) en diarios.
author: kailiang
ms.date: 02/12/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.custom: 15721
ms.assetid: b4b406fa-b772-44ec-8dd8-8eb818a921ef
ms.search.region: Global
ms.author: kailiang
ms.search.validFrom: 2021-02-12
ms.dyn365.ops.version: AX 10.0.17
ms.openlocfilehash: 5e7654a4e593ab5328077deb571d6e2220fd1385
ms.sourcegitcommit: 6dc2b877cf8ea9185a07964ec05c5ddb7a78471b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2022
ms.locfileid: "8407620"
---
# <a name="calculate-tds-on-invoices-using-journals"></a>Calcular TDS en facturas usando diarios

[!include [banner](../includes/banner.md)]

Este tema enumera los pasos para calcular los impuestos deducidos en el origen (TDS) en diarios.

Empiece por abrir la página **Diarios generales** (**Contabilidad general > Entradas del diario > Diarios generales**).

[![Diarios generales.](./media/apac-ind-TDS-57.png)](./media/apac-ind-TDS-57.png)

1. Cree líneas de diario utilizando los formularios de diario que se enumeran en la tabla. Seleccione el tipo de cuenta y el tipo de cuenta de contrapartida e introduzca el importe de la transacción. 

   > [!NOTE]
   > En la página **Diario de aprobación de facturas**, seleccione **Encontrar asientos** y seleccione facturas para calcular TDS. Consulte las facturas creadas en la página **Registro de facturas** o en la página **Econtrar asientos**.  

2. En la pestaña **General** de la página **Asiento del diario**, consulte o modifique el grupo TDS predeterminado definido para el proveedor o cliente en el campo **Grupo TDS**. El importe de TDS que se calcula en las líneas de diario se basa en la fórmula definida para los códigos de impuestos de TDS que se enumeran en el campo **Grupo TDS**. 

   > [!NOTE]
   > El campo **Grupo de retención de impuestos** y el campo **Grupo TCS** no están disponibles cuando selecciona un grupo TDS en el campo **Grupo TDS**. El campo **Grupo de retención de impuestos** está disponible solo en la página **Diario general**. Los TDS se calculan solo si se ha seleccionado la casilla **Calcular retención de impuestos** para el proveedor o cliente en las páginas **Todos los proveedores** o **Todos los clientes**.   

3. Seleccione la pestaña **Información de impuestos**. Seleccione direcciones alternativas de una empresa que estén configuradas para la empresa en este campo si fuera necesario. Puede ver el nombre de la empresa en el campo **Nombre**, que está en el grupo de campo **Información de la empresa**. 

4. Consulte la naturaleza de la categoría del evaluado del proveedor o cliente en el campo **Naturaleza del evaluado**, que está en el grupo de campo **Retención de impuestos**. En el campo **Número de cuenta de impuestos** (**TAN**), consulte el TAN del nombre de la empresa seleccionada que se muestra.  

5. Seleccione **Retención de impuestos** en el menú **Retención de impuestos** para abrir la página **Transacciones de retención temporal de impuestos**. Se muestran los siguientes campos en el panel superior de la página **Transacciones de retención temporal de impuestos**.

   - **Retención de importe total de impuestos**: el total de TDS calculado para la transacción para el grupo de TDS.

   - **Valor**: el porcentaje total utilizado para calcular TDS para la transacción. El porcentaje total se basa en la fórmula que se define para los códigos de impuestos TDS adjuntos al grupo TDS.

   - **Importe total de la retención de impuestos ajustada**: el importe total de TDS ajustado para todos los códigos de impuestos en el grupo TDS.

   - **TDS**: si se selecciona, se adjunta un grupo de TDS a la transacción.

  Los campos en las pestañas **Información general**, **General** y **Ajuste** en la página **Transacciones de retención temporal de impuestos** muestra la cantidad de TDS calculada y los detalles de la cantidad de TDS ajustada para cada código de impuestos de TDS adjunto al grupo de TDS.

6. Seleccione **Umbral** para abrir la página **Umbral**. Consulte el límite de umbral y el límite de umbral de excepción definidos para el componente de impuestos de TDS adjunto a un código de impuestos de TDS específico en esta página.

   Seleccione **Diseñador de fórmulas** para abrir el formulario **Diseñador de fórmulas**. Consulte la fórmula definida para un código de impuestos TDS específico en esta página. Cierre las páginas **Diseñador de fórmulas** y **Transacciones de retención temporal de impuestos** para volver a la página **Asiento del diario**.

8. Especifique los otros detalles. Valide y registre el diario. La cantidad de TDS que se calcula en las facturas de compra se registra en la cuenta de proveedor. El importe de TDS que se calcula en las facturas de ventas se registra en la cuenta de cliente que se define para cada código de impuestos de TDS en el grupo de TDS. Las cuentas de proveedores o de clientes para los códigos de impuestos TDS se definen en la página **Códigos de retención de impuestos**.

9. Seleccione **Retención de impuestos registrados** para abrir la página **Transacciones de retención de impuestos**. Puede ver el porcentaje total utilizado para calcular TDS para la transacción en el campo **Valor**.

   Los campos en las pestañas **Información general**, **General** e **Importe** en la página Transacciones de retención de impuestos muestran la cantidad de TDS calculada y los detalles de la cantidad de TDS ajustada para cada código de impuestos de TDS adjunto al grupo de TDS.
