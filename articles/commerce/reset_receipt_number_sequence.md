---
title: Restablecer números de recibos
description: Este tema describe cómo restablecer los números de recibos que se utilizan para diversas acciones en una fecha deseada (por ejemplo, el ejercicio o el año natural).
author: ShalabhjainMSFT
manager: AnnBe
ms.date: 10/06/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-Commerce
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: josaw
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: Retail, Commerce
ms.author: asharchw
ms.search.validFrom: 2020-01-14
ms.dyn365.ops.version: Application update 10.0.9
ms.openlocfilehash: 97ec85ebccacd3a827e8a016098939134823dceb
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2021
ms.locfileid: "5243704"
---
# <a name="reset-receipt-numbers"></a>Restablecer números de recibo 

[!include [banner](includes/banner.md)]

> [!NOTE]
> Requerimos que seleccione la propiedad **Secuencia independiente** para todos los tipos de recibos en el perfil de funcionalidad antes de usar esta características. Además, la zona horaria del sistema del dispositivo, donde se utiliza el POS, debe coincidir con la zona horaria de la tienda correspondiente. Debido a estas limitaciones, le recomendamos que no utilice esta función en producción mientras trabajamos para solucionar estos problemas en una versión futura. 

Los minoristas generan números de recibos para diversas acciones en la tienda, como transacciones de pago al contado sin entrega a domicilio, transacciones de devolución, pedidos de clientes, presupuestos y pagos. Aunque los minoristas definen sus propios formatos de recibos, algunos países o regiones tienen normativas que imponen restricciones a estos formatos de recibos. Por ejemplo, estas normativas podrían limitar el número de caracteres en el recibo, requerir números de recibos consecutivos, restringir algunos caracteres especiales o requerir un restablecimiento de los números de recibos al comienzo del año. Microsoft Dynamics 365 Commerce hace que el proceso de administración de números de recibos sea muy flexible, para ayudar a los minoristas a cumplir con los requisitos normativos. Este tema explica cómo usar la funcionalidad para restablecer los números de recibos.

En Commerce, los formatos de recibos pueden ser alfanuméricos. Puede poner contenido tanto estático como dinámico en ellos. El contenido estático incluye caracteres alfabéticos, números y caracteres especiales. El contenido dinámico incluye uno o más caracteres que representan información como el número de tienda, el número de terminal, la fecha, el mes, el año y las secuencias numéricas que se incrementan automáticamente. Los formatos se definen en la sección **Numeración del recibo** del perfil de la funcionalidad. La siguiente tabla describe los caracteres que representan el contenido dinámico.

| Caracteres | Descripción |
|------------|-------------|
| S          | El carácter **S** se usa para el número de tienda. Por ejemplo, si una tienda está numerada HOUSTON1, el formato **SSS** muestra "ON1" en el recibo. El formato **SSSSS** muestra "STON1" en el recibo. |
| T          | El carácter **T** se usa para el número de terminal. Por ejemplo, si un terminal está numerado 0001, el formato **TTTT** muestra "0001" en el recibo. |
| C          | El carácter **C** se usa para el número de id. de personal. Por ejemplo, si un miembro del personal tiene un id. de 000160, el formato **CCCC** muestra "0160" en el recibo. |
| ddd        | Los caracteres **ddd** corresponden al día del año, del 1 al 366. Por ejemplo, el 15 de enero, el formato **ddd** muestra "015" en el recibo. |
| MM         | Los caracteres **MM** se usan para el mes de dos dígitos. Por ejemplo, en enero, el formato **MM** muestra "01" en el recibo. |
| DD         | Los caracteres **DD** se usan para el día de dos dígitos del mes. Por ejemplo, el 15 de enero, el formato **DD** muestra "15" en el recibo. |
| YY         | Los caracteres **YY** se usan para el año de dos dígitos. Por ejemplo, en cualquier mes durante el año 2020, el formato **YY** muestra "20" en el recibo. |
| \#         | Un signo de número (**\#**) se utiliza para la numeración secuencial. Por ejemplo, el formato **####** muestra "0001," "0002," "0003," etc., en el recibo. |

Puede restablecer la numeración secuencial del recibo en una fecha específica. Luego, para la primera transacción que se produce después de las 12 de la mañana en la fecha de restablecimiento seleccionada, el sistema restablece la secuencia de números del recibo a 1. También puede especificar si el restablecimiento se produce solo una vez o si se repite todos los años. Si se especifica la periodicidad anual, el restablecimiento se produce automáticamente cada año hasta que el minorista decida detenerlo. 

Para activar el restablecimiento, siga estos pasos.

1. Vaya a **Retail y Commerce \> Configuración de canal \> Configuración de PDV \> Perfiles de PDV \> Perfiles de funcionalidad**.
1. En la ficha desplegable **Numeración del recibo**, seleccione **Restablecer la fecha de restablecimiento de número**.
1. En el cuadro de diálogo desplegable, en el campo **Restablecer fecha**, seleccione una fecha futura en la que debería producirse el restablecimiento.
1. En el campo **Restablecer tipo de recibo**, seleccione **Solo una vez** o **Anual**.
1. Seleccione **Aceptar**.

![Selección de una fecha de restablecimiento de recibos](media/Enable_receipt_reset.png "Selección de una fecha de restablecimiento de recibos")

Después de seleccionar una fecha, aparece en la columna **Siguiente fecha de restablecimiento de número de recibo**. La fecha de restablecimiento se aplica a todos los tipos de transacciones de recibos. Por lo tanto, la secuencia numérica de recibos se restablecerá para todos los tipos de recibos.

Cuando llega la fecha de restablecimiento, el número de recibo se restablece para la primera transacción de cada tipo. Además, en el perfil de funcionalidad, la fecha de restablecimiento se mueve desde la columna **Siguiente fecha de restablecimiento de número de recibo** a la columna **Fecha de restablecimiento de número de recibo actual**. Este cambio indica que si no se usa un registro en la fecha de restablecimiento, el número de recibo se reiniciará la próxima vez que el registro *se* use. Por ejemplo, el 3 de diciembre de 2019, seleccione **1 de enero de 2020** como la fecha de restablecimiento. El 1 de enero, cuando los registros realicen su primera transacción, se restablece el número de recibo. Sin embargo, un registro no se usa en absoluto durante diciembre y enero, pero luego comienza a usarse en febrero. En este caso, debido a que se definió una acción de restablecimiento, el número de recibo para ese registro se reiniciará cuando el registro realice su primera transacción en febrero.

Puede usar la funcionalidad **Borrar fecha de restablecimiento** para borrar futuras fechas de restablecimiento. Sin embargo, si la fecha de restablecimiento tuvo lugar en el pasado, no se puede deshacer. Por lo tanto, el restablecimiento seguirá produciéndose para todos los registros donde no se haya producido aún el restablecimiento.

> [!NOTE]
> En función de la fecha de restablecimiento que seleccione y del formato del recibo, es posible que tenga números de recibos duplicados. Aunque el sistema de punto de venta (PDV) puede manejar estas situaciones, aumentan la cantidad de tiempo que se requiere para procesar las devoluciones, porque los asociados de ventas deben seleccionar entre los recibos duplicados. Pueden producirse otras complicaciones relacionadas con la limpieza de datos si los recibos duplicados no fueron una consecuencia planificada. Por lo tanto, le recomendamos que utilice caracteres de fecha dinámica (por ejemplo, **ddd**, **MM**, **DD** y **YY**) para ayudar a evitar números de recibos duplicados después de un restablecimiento.


[!INCLUDE[footer-include](../includes/footer-banner.md)]