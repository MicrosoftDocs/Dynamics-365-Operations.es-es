---
title: Saldos de apertura que faltan en el cierre de fin de año
description: Este tema explica por qué pueden faltar los saldos de apertura al cerrar un año y cómo reconstruir esos saldos si faltan.
author: kweekley
ms.date: 05/12/2021
ms.topic: index-page
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2020-12-14
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: 4478f2b46f984c97ff01588098d64953dedf476e7f3f76aeecb29a0ff0074b9d
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2021
ms.locfileid: "6735471"
---
# <a name="year-end-close-missing-opening-balances"></a>Saldos de apertura que faltan en el cierre de fin de año

[!include [banner](../includes/banner.md)]

Este tema explica por qué pueden faltar los saldos de apertura al cerrar un año y cómo reconstruir esos saldos si faltan.

### <a name="symptom"></a>Síntoma

¿Por qué no hay saldos iniciales después de ejecutar el cierre de fin de año del libro mayor? 

### <a name="resolution"></a>Resolución

Estas son cosas a comprobar si ha cerrado un año en el libro mayor y luego ha generado un saldo de comprobación que no muestra los saldos de apertura para el próximo ejercicio.

Si el campo **Deshacer cierre anterior** está establecido en **Sí**, se estará deshaciendo el cierre de año anterior para el mismo ejercicio. Al ejecutar un proceso de deshacer el cierre de fin de ejercicio, se eliminarán todas las entradas de los saldos de cierre y apertura, como si nunca se hubiera ejecutado el cierre de fin de ejercicio. Los asientos también se eliminan. El proceso de cierre de fin de ejercicio no se volverá a ejecutar de forma automática. Debe iniciar el proceso de nuevo, pero esta vez actualice la opción **Deshacer cierre anterior** a **No**.

Este escenario se trata en el tema de preguntas frecuentes sobre el cierre de fin de ejercicio. Para más información, consulte [Preguntas frecuentes sobre actividades de fin de ejercicio](faq-year-end-activities.md).

### <a name="symptom"></a>Síntoma

He ejecutado el cierre del ejercicio con la opción **Deshacer cierre anterior** establecida en **No**, y todavía no tengo saldos de apertura para mi ejercicio.

### <a name="resolution"></a>Resolución

En primer lugar, compruebe el estado del trabajo por lotes. El cierre de un ejercicio incluye una serie de tareas diferentes, pero el paso más crítico es la tarea por lotes con la descripción de tarea **Paso 5.0.0**. El registro de las transacciones de apertura y, opcionalmente, las transacciones de cierre de contabilidad general se realizan en este paso. 

[![Lista de historiales de lotes.](./media/yec-mssng-open-blnces-01.png)](./media/yec-mssng-open-blnces-01.png)

Si este paso finalizó correctamente, pero no aparecen los saldos de apertura en la página **Consulta de saldo de comprobación** (**Contabilidad general > Consultas e informes > Saldo de comprobación**), revise los resultados del trabajo por lotes de cierre del ejercicio para ver si el paso Reconstruir saldos se completó correctamente.

[![Resultados del trabajo por lotes de cierre del ejercicio.](./media/yec-mssng-open-blnces-02.png)](./media/yec-mssng-open-blnces-02.png)

Si han aparecido errores en este paso por cualquier motivo, puede ocurrir que las transacciones de apertura (y, opcionalmente, de cierre) se hayan registrado correctamente. Puede verificar que las transacciones de contabilidad general se registraron correctamente utilizando la página **Consulta de transacciones de asientos**, especificando el número de asiento y la fecha proporcionada en el cuadro de diálogo de cierre de ejercicio para el año que cerró (**Libro mayor > Consultas e informes> Transacciones de asientos**).

[![Consulta de transacciones de asientos.](./media/yec-mssng-open-blnces-03.png)](./media/yec-mssng-open-blnces-03.png)

Si los comprobantes de apertura (y, opcionalmente, de cierre) están presentes, no es necesario volver a ejecutar el cierre de fin de ejercicio. En su lugar, consulte la siguiente sección para obtener información sobre cómo avanzar.

### <a name="symptom"></a>Síntoma

El paso "Reconstruir saldos" del cierre de fin de ejercicio produjo errores, entonces ¿debo volver a ejecutar todo el proceso de cierre de ejercicio?

### <a name="resolution"></a>Resolución

El paso Reconstruir saldos actualiza los saldos del libro mayor que se utilizan cuando se genera la Consulta de saldo de comprobación.  Es el paso final del proceso de cierre de ejercicio.  Si este paso es el único con errores, las transacciones del libro mayor se han registrado correctamente.  No es necesario que vuelva a ejecutar el cierre del ejercicio. Puede ejecutar el proceso para reconstruir los saldos manualmente utilizando la página **Conjuntos de dimensiones financieras** (**Libro mayor > Plan de cuentas > Dimensiones> Conjuntos de dimensiones financieras**).

[![Botón Reconstruir saldos en la página Conjuntos de dimensiones financieras.](./media/yec-mssng-open-blnces-04.png)](./media/yec-mssng-open-blnces-04.png)

Si este paso tarda mucho en procesarse, recomendamos revisar las mejores prácticas para los conjuntos de dimensiones financieras, como se describe en [Prácticas recomendadas para actualizar conjuntos de dimensiones financieras](https://community.dynamics.com/365/financeandoperations/b/dynamics-365-finance-blog/posts/best-practices-for-updating-financial-dimension-set-dimension-sets). 

