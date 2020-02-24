---
title: Configurar análisis de novedad, frecuencia y monetario (RFM)
description: Este tema explica cómo configurar un análisis de novedad, frecuencia y monetario (RFM) de los clientes.
author: josaw1
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
ms.search.form: MCRRFMDefinition
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: 78943
ms.assetid: 8ff9aac3-5ada-4150-85fd-18901c926d53
ms.search.region: global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.openlocfilehash: c7cb79fa82b579bee01e51cb635597cc5f711a98
ms.sourcegitcommit: 81a647904dd305c4be2e4b683689f128548a872d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/01/2020
ms.locfileid: "3023952"
---
# <a name="set-up-recency-frequency-and-monetary-rfm-analysis"></a>Configurar análisis de novedad, frecuencia y monetario (RFM)

[!include [banner](includes/banner.md)]

Este tema explica cómo configurar un análisis de novedad, frecuencia y monetario (RFM) de los clientes.

El análisis de RFM es una herramienta de marketing que su organización puede usar para evaluar los datos que se generan mediante las compras del cliente. Después de configurar un análisis de RFM, a los clientes se les asigna una puntuación calculada de RFM mientras realizan compras. La puntuación de RFM puede ser una calificación de tres dígitos o un número global, en función de cómo haya configurado el análisis de RFM su organización. Así es cómo funciona la calificación si su organización usa una calificación de tres dígitos para la puntuación:

- El primer dígito es la grado de recencia del cliente, que se refiere a la última vez que un cliente hizo una compra en su organización.
- El segundo dígito es el grado de frecuencia del cliente, que se refiere a con qué frecuencia el cliente realiza compras en su organización.
- El tercer dígito es el grado del importe monetario del cliente, que se refiere a cuánto gasta el cliente cuando realiza compras en su organización.

Por ejemplo, su organización ha configurado las clasificaciones en una escala de 1 a 5, donde 5 es el grado más alto. En este caso, una clasificación de cliente de 535 le indicará la siguiente información acerca del cliente:

- **Grado de proximidad de 5:** el cliente ha comprado recientemente.
- **Grado de frecuencia de 3:** el cliente compra productos de la organización con una frecuencia moderada.
- **Grado monetario de 5**: cuando el cliente realiza una compra, gasta un importe significativo de dinero.

Si su organización usa una calificación global de la puntuación, las puntuaciones se suman. Para el mismo ejemplo, el cliente tiene un puntuación de 13 (5 + 3 + 5).

## <a name="set-up-rfm-analysis-for-the-customers-in-your-organization"></a>Configurar el análisis de RFM para clientes en su organización

1. Vaya a **Centro de llamadas** \> **Periódico** \> **Análisis de RFM**.
2. En la página **Análisis de RFM** , seleccione **Nuevo**. En el campo **Definición de RFM**, especifique un nombre para la definición del RFM. Por ejemplo, podría llamar a la definición RFM-A.
3. Escriba una fecha inicial y una fecha final para esta definición de RFM.
4. En la ficha desplegable **General**, realice lo siguiente:

    - Si cada sección de la puntuación de RFM debe contener un recuento igual de clientes, seleccione la casilla **Distribución equitativa**.
    - Seleccione la casilla **Agregar puntuación** para agregar las tres puntuaciones. Por ejemplo, esto daría al cliente una puntuación de RFM de 13 en lugar de 535.
    - Selecione la casilla **Guardar historial** para requerir que el sistema guarde los datos estadísticos de los clientes para poder utilizarlos para calcular la puntuación de RFM.

5. En la ficha desplegable **Recencia**, realice lo siguiente:

    - En el campo **Divisiones**, especifique el número de divisiones o grupos, que se usarán para calcular la puntuación de recencia de los clientes. Por ejemplo, si tiene 100 clientes, una división de 5 significa que hay 20 clientes para cada cuenta. Los 20 clientes que han realizado compras más recientemente tienen una puntuación de recencia de 5. Los siguientes 20 clientes tienen una puntuación de recencia de 4, y así sucesivamente. Si tiene 50 clientes, 10 clientes tienen una puntuación de novedad de 5, 10 tienen una puntuación de novedad de 4, y así sucesivamente.
    - En el campo **Prioridad**, seleccione qué peso dar al parámetro de recencia en relación con los otros parámetros cuando se calcula la puntuación de RFM para un cliente. Por ejemplo, puede configurar más valor de la puntuación de novedad que para la puntuación monetaria.
    - En el campo **Multiplicador**, especifique el valor por el que multiplicar la puntuación de recencia. Si no escribe ningún valor, la puntuación no se multiplica.
    - En el campo **Periodo**, seleccione el período de tiempo durante en el que se calcula la puntuación de recencia. Por ejemplo, por semana o por mes.

6. En la ficha desplegable **Frecuencia**, realice los siguiente:

    - En el campo **Divisiones**, especifique el número de divisiones o grupos, que se usarán para calcular la puntuación de frecuencia de los clientes.
    - En el campo **Prioridad**, seleccione qué peso dar al parámetro de frecuencia en relación con los otros parámetros cuando se calcula la puntuación de RFM para un cliente.
    - En el campo **Multiplicador**, especifique el valor por el que multiplicar la puntuación de frecuencia. Si no escribe ningún valor, la puntuación no se multiplica.

7. En la ficha desplegable **Monetaria**, realice los siguiente:

    - En el campo **Divisiones**, especifique el número de divisiones o grupos, que se usarán para calcular la puntuación monetaria de los clientes.
    - En el campo **Prioridad**, seleccione qué peso dar al parámetro monetario en relación con los otros parámetros cuando se calcula la puntuación de RFM para un cliente.
    - En el campo **Multiplicador**, especifique el valor por el que multiplicar la puntuación monetaria. Si no escribe ningún valor, la puntuación no se multiplica.
    - En el campo **Bruto/neto**, seleccione si la puntuación monetaria del cliente debe calcularse usando el importe bruto o neto de la factura.
    - Si los importes de devolución de un cliente deben restarse de un cálculo total de la factura del cliente, seleccione la casilla **Restar devoluciones**.

## <a name="view-a-customers-rfm-score"></a>Ver el índice de RFM de un cliente

Use este procedimiento para ver el índice de RFM de un cliente.

1. Vaya a **Centro de llamadas** \> **Diarios** \> **Servicio al cliente**.
2. En la página **Servicio al cliente**, en el panel **Servicio al cliente**, en los campos de búsqueda, seleccione el tipo de palabra clave por el que se dese buscar y escriba el texto de la búsqueda.
3. Selección **Buscar**.
4. En la página **Búsqueda de clientes**, seleccione el registro de cliente que desee y, a continuación haga click en **Seleccionar cliente**.

El índice de RFM se muestra en el grupo **Historial de pedidos** a la derecha de la página **Servicio al cliente**.

## <a name="view-or-clear-the-history-of-an-rfm-analysis-record"></a>Ver o borrar el historial de un registro de análisis de RFM

Use este procedimiento para ver o borrar el historial de un registro de análisis de RFM.

1. Vaya a **Centro de llamadas** \> **Periódico** \> **Análisis de RFM**.
2. En la página **Análisis de RFM**, seleccione el registro que desea ver.
3. Para ver el historial de registros, seleccione la ficha desplegable **Historial**.
4. Para eliminar el historial de registros, seleccione la ficha desplegable **Eliminar Historial**.
