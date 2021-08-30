---
title: Cálculo de TDS en facturas desde la página de facturas de servicios
description: Este tema explica cómo calcular los impuestos deducidos en el origen (TDS) en facturas mediante la página de facturas de servicios.
author: kailiang
ms.date: 02/12/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
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
ms.openlocfilehash: c543876c48eca55eaaa6fd67585ec357dfea276ffbf8abad3c28c6f4cf29f782
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2021
ms.locfileid: "6750373"
---
# <a name="tds-calculation-on-invoices-from-the-free-text-invoice-page"></a>Cálculo de TDS en facturas desde la página de facturas de servicios

[!include [banner](../includes/banner.md)]

Este tema explica cómo calcular los impuestos deducidos en el origen (TDS) en facturas mediante la página de **Facturas de servicios**.

1. Vaya a **Clientes \> Facturas \> Todas las facturas de servicios**.

    [![Página de facturas de servicios.](./media/apac-ind-TDS-57-1.png)](./media/apac-ind-TDS-57-1.png)

2. Seleccione **Nuevo** para crear una factura de servicios y especificar los detalles necesarios.
3. Seleccione la pestaña **Factura**. En la sección **Grupo de retención de impuestos**, el campo **Naturaleza del evaluado** muestra la categoría de naturaleza del evaluado del cliente.
4. En el campo **Grupo TDS**, revise o cambie el grupo TDS predeterminado definido para el cliente.

    > [!NOTE]
    > Cuando selecciona un valor en el campo **Grupo TDS**, el campo **Grupo TDS** deja de estar disponible. TDS se calcula solo si se ha establecido la opción **Calcular retención de impuestos** en **Sí** para el cliente en la página **Todos los clientes**.

5. En la pestaña **Información de impuestos**, en la sección **Información de la empresa**, en el campo **Nombre**, seleccione el nombre de la empresa para una dirección alternativa que se ha configurado para la empresa.

    En la sección **Retención de impuestos**, el campo **Número de cuenta de impuestos (TAN)** muestra el número de cuenta de impuestos (TAN) de la empresa seleccionada.

6. En la pestaña **Líneas de factura**, cree líneas de factura e introduzca los detalles necesarios.

    En la sección **Grupo de retención de impuestos**, el campo **Número de cuenta de impuestos (TAN)** muestra el TAN y el campo **Grupo TDS** muestra el grupo TDS.

7. Seleccione **Retención de impuestos** para abrir la página **Transacciones de retención temporal de impuestos**. La parte superior de esta página tiene los siguientes campos:

    - **Retención de importe total de impuestos**: el total de TDS calculado para la transacción para el grupo de TDS.
    - **Valor**: el porcentaje total utilizado para calcular TDS para la transacción. El porcentaje total se basa en la fórmula que se define para los códigos de impuestos TDS y que se adjunta al grupo TDS.
    - **Importe total de la retención de impuestos ajustada**: el importe total de TDS ajustado para todos los códigos de impuestos en el grupo TDS.
    - **TDS**: una casilla seleccionada indica que un grupo de TDS está adjunto a la transacción.

    Los campos en las pestañas **Información general**, **General** e **Ajuste** muestran el importe de TDS calculado y los detalles del importe de TDS ajustado para cada código de impuestos de TDS adjunto al grupo de TDS.

8. Seleccione **Umbral** para abrir la página **Umbral**, donde puede revisar el límite de umbral que se define para el componente de impuestos de TDS que está adjunto a un código de impuestos de TDS específico.
9. Seleccione **Diseñador de fórmulas** para abrir la página **Diseñador de fórmulas**, donde puede revisar la fórmula que se define para un código de impuestos de TDS específico.
10. Registre la factura de servicio. El importe de TDS que se calcula para la factura de servicios se registra en la cuenta de cliente que se define para cada código de impuestos de TDS en el grupo de TDS. Las cuentas de clientes para los códigos de impuestos TDS se definen en la página **Códigos de retención de impuestos**.
11. Seleccione **Retención de impuestos registrados** para abrir la página **Transacciones de retención de impuestos**. El campo **Valor** muestra el porcentaje total utilizado para calcular TDS para la transacción.

    Los campos de las pestañas **Información general**, **General** e **Importe** muestran los importes de TDS que se calcularon en las líneas de factura.

12. Revise la información de cálculo de TDS para cada código de impuestos de TDS adjunto al grupo de TDS.
