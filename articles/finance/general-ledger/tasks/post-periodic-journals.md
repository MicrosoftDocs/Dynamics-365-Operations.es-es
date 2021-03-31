---
title: Registrar diarios periódicos
description: Los diarios periódicos a veces que se denominan diarios periódicos dado que el importe, el texto y otra información se repiten cada vez que se recupera el diario periódico.
author: aprilolson
manager: AnnBe
ms.date: 06/26/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: LedgerJournalTable, LedgerJournalTransPeriodic, LedgerJournalTransDaily
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 31c801658004f771df6f1ddf70194de131314a64
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2021
ms.locfileid: "5212164"
---
# <a name="post-periodic-journals"></a>Registrar diarios periódicos

[!include [banner](../../includes/banner.md)]

Los diarios periódicos a veces que se denominan diarios periódicos dado que el importe, el texto y otra información se repiten cada vez que se recupera el diario periódico. Al crear el diario periódico, se especifica el intervalo del período para la periodicidad, como días o meses. Esta guía de la tarea creará un diario periódico con una periodicidad mensual.

1. Vaya al **Panel de exploración > Módulos > Contabilidad general > Tareas periódicas > Diarios periódicos**.
2. Haga clic en **Nuevo**.
3. En el campo **Nombre**, especifique o seleccione un valor.
4. En la lista, haga clic en el vínculo de la fila seleccionada.
5. En el campo **Descripción**, escriba un valor. La descripción será el nombre del diario periódico cuando se recupere más adelante, por lo que debe asegurarse de darle un nombre relevante.
6. En el **panel de acciones**, haga clic en **Líneas**. Un diario periódico incluirá normalmente varias líneas de diario. En esta guía de tarea, no obstante, se agregará una sola línea.
7. En el campo **Fecha**, escriba una fecha. El campo **Fecha** contiene la fecha de registro de la siguiente transferencia al diario. Para los diarios que se recuperarán cada mes, se recomienda usar la fecha del mes en que se registraron, normalmente la primera o última fecha del período. Es posible dejar en blanco el campo de fecha y ofrecer una fecha cuando se recupera el diario, mediante el campo Fecha vacía. El campo se actualiza automáticamente a la siguiente fecha que se repite cuando se recuperan las transacciones. 
8. En el campo **Cuenta**, especifique los valores deseados.
9. En el campo **Descripción**, seleccione un valor.
10. Cierre la página.
11. En el campo **Débito**, escriba un número.
12. En el campo **Cuenta de contrapartida**, especifique los valores deseados.
13. En el campo **Unidad**, seleccione "Meses".
14. En el campo **Número de unidades**, escriba "1".
15. En el campo **Última fecha**, escriba una fecha. Especificar la última fecha del período anterior prevendrá que el diario periódico se cree por error en el período inicial incorrecto. La última fecha se actualizará después cada vez que se recupere el diario periódico. 
16. Haga clic en **Guardar**.
17. Vaya a **Panel de exploración > Módulos > Contabilidad general > Entradas del diario > Diarios generales**.
18. Haga clic en **Nuevo**.
19. En el campo **Nombre**, especifique o seleccione un valor.
20. En la lista, busque y seleccione el registro deseado.
21. En la lista, haga clic en el vínculo de la fila seleccionada.
22. En el campo **Descripción**, escriba un valor.
23. En el **panel de acciones**, haga clic en **Líneas**.
24. En el **Panel de acciones**, haga clic en **Diario periódico**.
25. Haga clic en **Recuperar diario**.
26. En el campo **Fecha final**, especifique una fecha. La **fecha final** sirve como fecha de corte para las líneas periódicas del asiento. De acuerdo con la configuración de periodicidad, la última fecha y la fecha final para la misma línea se pueden incluir más de una vez en el diario resultante. La fecha final se actualiza automáticamente según la fecha de sesión de la última vez que la línea periódica se transfirió a un diario. 
27. En el campo **Número de diario periódico**, especifique o seleccione un valor.
28. En la lista, haga clic en el vínculo de la fila seleccionada.
29. Haga clic en **Aceptar**. El diario del período se puede revisar, aprobar o registrar ahora en función del requisito y la configuración.   


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]