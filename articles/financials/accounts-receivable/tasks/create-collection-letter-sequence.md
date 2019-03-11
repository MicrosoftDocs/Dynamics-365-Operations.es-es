---
title: Crear una secuencia de cartas de cobro
description: Use esta guía de tarea para crear una secuencia de cartas de cobro.
author: mikefalkner
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CollectionLetterCourse
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: mfalkner
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: db5264f6d8d7723ff01d13e99728c2bfebcb4515
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/29/2019
ms.locfileid: "311574"
---
# <a name="create-a-collection-letter-sequence"></a>Crear una secuencia de cartas de cobro

[!include [task guide banner](../../includes/task-guide-banner.md)]

Use esta guía de tarea para crear una secuencia de cartas de cobro. Esta tarea usa la empresa de demostración USMF.

1. Vaya a Crédito y cobros > Configuración > Configurar secuencia de cartas de cobro.
2. Haga clic en Nuevo.
3. En el campo Secuencia de la carta de cobro, especifique un identificador de secuencia que represente la secuencia. Se usará cuando se configure un perfil de contabilización.
4. En el campo Descripción, escriba un valor.
    * Las condiciones de pago son opcionales. Si especifica un valor aquí, la factura de la cuota de la carta de cobro usará estas condiciones de pago, en lugar de las condiciones de pago almacenadas con el cliente.  
5. En el campo del código de carta de cobro, seleccione el código para la primera carta de cobro que desee enviar.
    * La primera carta de cobro se crea de acuerdo con la fecha de vencimiento que figura en la factura, el valor especificado para el período de gracia en el campo Días en esta línea y otra información indicada en esta línea.  
6. En el campo Descripción, escriba un valor.
    * La divisa de la cuota se establecerá por defecto en la divisa del cliente. Este código de divisa puede ser diferente de la divisa de la factura.  
7. Haga clic en Agregar para agregar la siguiente carta de cobro que se enviará en la secuencia.
    * En muchos casos, la primera carta de cobro es solo una advertencia. Puede agregar cuotas si es necesario.  
8. En el campo del código de carta de cobro, seleccione la siguiente carta de cobro que se enviará en la secuencia.
9. En el campo Descripción, escriba un valor.
10. En el campo de la cuenta principal, seleccione la cuenta de ingresos que se usará para las cuotas.
11. Especifique la cuota que se cobrará cuando se registre esta carta de cobro.
12. En el campo Grupo de impuestos de artículos, haga clic en el botón desplegable para abrir la búsqueda.
    * Seleccione un grupo de impuestos de artículo si se deben calcular impuestos en la cuota.  
13. En la lista, haga clic en el vínculo de la fila seleccionada.
14. Escriba el saldo vencido mínimo necesario antes de enviar una carta de cobro.
15. Escriba el número de días de gracia que se permitirán.
    * Este es el número de días después de la fecha de vencimiento en el que se puede generar una carta de cobro. La fecha de vencimiento que se usa para el cálculo depende del puesto de la carta de cobro en la secuencia de cartas de cobro:  ⦁  El período de gracia para la carta de cobro 1 es relativo a la fecha de vencimiento de la factura.  ⦁ El período de gracia para las cartas de cobro 2 y superiores depende de la fecha en que la carta de cobro anterior se haya registrado o impreso, en función de la selección en el campo Actualizar código de carta de cobro en la página Parámetros de clientes.  
16. Haga clic en Agregar para agregar la última carta de cobro en la secuencia.
    * Puede agregar hasta cinco códigos de cartas de cobro para la secuencia de la carta de cobro.  
17. En el campo del código de carta de cobro, seleccione la siguiente carta de cobro que se enviará en la secuencia.
18. En el campo Descripción, escriba un valor.
19. En el campo Cuenta principal, especifique los valores deseados.
20. En el campo Cuota en divisa, escriba un número.
21. En el campo Grupo de impuestos de artículos, haga clic en el botón desplegable para abrir la búsqueda.
22. En la lista, haga clic en el vínculo de la fila seleccionada.
23. Especifique un número en el campo Saldo vencido mínimo.
24. En el campo Días, especifique un número.
25. Seleccione esta casilla de verificación para detener otras entregas y facturas adicionales por parte del cliente.
    * Para desbloquear la cuenta, seleccione No en el campo Facturación y entrega en espera en la página Clientes.  
26. Expanda la ficha desplegable Nota.
27. Especifique el texto tal como desea que aparezca en la carta de cobro para el código de carta de cobro seleccionado.
    * Puede traducir este texto a varios idiomas mediante el menú Traducciones encima del cuadro de nota.  

