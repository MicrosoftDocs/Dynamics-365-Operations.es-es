---
title: Crear un código de interés con un intervalo
description: Los códigos de interés se pueden configurar para calcular diferentes importes de interés basados en un intervalo de valores.
author: ShivamPandey-msft
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: Interest, CustInterestRange
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 2d76ae320ee43a473b64afe311876cc94b953b20
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/29/2019
ms.locfileid: "367648"
---
# <a name="create-an-interest-code-with-a-range"></a>Crear un código de interés con un intervalo

[!include [task guide banner](../../includes/task-guide-banner.md)]

Los códigos de interés se pueden configurar para calcular diferentes importes de interés basados en un intervalo de valores. Este procedimiento le mostrará cómo agregar un código de interés y agregarle un intervalo.

1. Vaya a Crédito y cobros > Interés > Configurar códigos de interés.
2. Haga clic en Nuevo.
3. En el campo Código del interés, especifique el nombre del código de interés.
4. En el campo Descripción, especifique una descripción para el código de interés.
5. Seleccione Mes.
6. Expanda la sección Ganancias.
7. Expanda las ganancias por sección de divisa.
8. En el campo Cuenta de registro de libro mayor, especifique los valores deseados.
9. En campo Interés por intervalo, seleccione "Meses".
10. Haga clic en Agregar.
11. En el campo Descripción, especifique una descripción para esta divisa e intervalo.
12. Haga clic en Guardar.
13. Haga clic en Intervalos.
14. Haga clic en Nuevo.
15. Especifique el Valor inicial como 0 y especifique el porcentaje de interés al mes que se usará para calcular el interés. Para nuestro ejemplo, es 1,5.
16. Haga clic en Nuevo.
17. Especifique el siguiente Valor inicial como 4, que es el primer mes en que calculará un nuevo importe de interés.
18. Especifique el porcentaje de interés al mes que se usará para calcular el interés que empieza el mes 4. Para este ejemplo, es 2.0.
19. Haga clic en Nuevo.
20. Especifique el siguiente Valor inicial como 7, que es el siguiente mes en que calculará un nuevo importe de interés.
21. Especifique el porcentaje de interés al mes que se usará para calcular el interés que empieza el mes 7. Para este ejemplo, es 2.5.
22. Haga clic en Cerrar para completar la configuración.

