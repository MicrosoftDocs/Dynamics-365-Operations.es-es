---
title: Contenido de Power BI de facturación de suscripción
description: Este artículo describe lo que se incluye en el contenido de facturación de suscripción de Microsoft Power BI.
author: JodiChristiansen
ms.date: 04/13/2022
ms.topic: article
audience: Application User
ms.reviewer: twheeloc
ms.search.region: Global
ms.author: jchrist
ms.search.validFrom: 2021-04-13
ms.openlocfilehash: 6cee01eb5b8bb8296b6e7f638b565c999ccc023e
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/03/2022
ms.locfileid: "8849971"
---
# <a name="subscription-billing-power-bi-content"></a>Contenido de Power BI de facturación de suscripción

[!include[banner](../includes/banner.md)]

Este artículo describe lo que se incluye en el contenido de facturación de suscripción de Microsoft Power BI. Explica cómo obtener acceso a los informes Power BI y proporciona información acerca del modelo de datos y las entidades que se utilizan para generar el contenido. 

## <a name="overview"></a>Información general

El contenido de facturación de suscripción de Power BI se creó contenido para empleados y administradores de facturación de suscripciones. Proporciona métricas de facturación de suscripciones clave, como ingresos periódicos mensuales (MRR) para programaciones de facturación y el saldo decreciente y la información de reparto para las programaciones de aplazamiento. Utiliza los datos de las programaciones de facturación y las programaciones de aplazamiento para brindar una descripción general de los ingresos y ganancias periódicos.

El contenido de Power BI tiene las siguientes tres pestañas que proporcionan un total de cuatro informes analíticos: 

- **Análisis - MRR** – Esta pestaña proporciona el informe **Facturación mensual periódica** y el informe **Detalles de programación de facturación**.
- **Analítica - Reparto** – Esta pestaña proporciona el informe **Reparto de ingresos**.
- **Análisis - Saldo decreciente** – Esta pestaña proporciona el informe **Saldo decreciente**.

## <a name="view-data-on-the-analytical-reports"></a>Ver datos en los informes analíticos

Antes de que pueda ver los datos en los informes analíticos debe ejecutar un proceso periódico que genere los datos de informes para cada informe. Estos datos que requieren los informes deben generarse porque no se almacenan directamente en la base de datos. 

1. Vaya a **Facturación de suscripción \> Facturación periódica del contrato \> Tareas periódicas \> Procesamiento por lotes de informe de análisis MRR** y siga estos pasos:

    1. Introduzca un intervalo de fechas de no más de tres años.
    2. Opcional: configure un trabajo de proceso por lotes periódico para actualizar periódicamente los datos.
    3. Seleccione **Aceptar**.

2. Una vez que el trabajo por lotes haya terminado de ejecutarse, vaya a **Administracion del sistema \> Configuración \> Almacén de entidades** y actualice la medida agregada **Informe MRR**. 
3. Vaya a **Facturación de suscripción \> Aplazamientos de ingresos y gastos \> Tareas periódicas \> Procesamiento por lotes de informe de análisis de repartos** y siga estos pasos:

    1. Introduzca una fecha de inicio y una fecha de finalización que no abarquen más de 26 períodos. 
    2. Si desea ver la cantidad prevista de períodos anteriores en el período actual, configure la opción **Importes pasados previstos en el período actual** como **Sí**.
    3. Opcional: configure un trabajo de proceso por lotes periódico para actualizar periódicamente los datos.
    4. Seleccione **Aceptar**. 

4. Una vez que el trabajo por lotes haya terminado de ejecutarse, vaya a **Administracion del sistema \> Configuración \> Almacén de entidades** y actualice la medida agregada **Informe de repartos**.
5. Vaya a **Facturación de suscripción \> Aplazamientos de ingresos y gastos \> Tareas periódicas \> Procesamiento por lotes de informe analítico de saldo decreciente** y siga estos pasos:

    1. Introduzca una fecha de inicio y una fecha de finalización que no abarquen más de 26 períodos. 
    2. Si desea ver la cantidad prevista de períodos anteriores en el período actual, configure la opción **Importes pasados previstos en el período actual** como **Sí**.
    3. Opcional: configure un trabajo de proceso por lotes periódico para actualizar periódicamente los datos.
    4. Seleccione **Aceptar**.

6. Una vez que el trabajo por lotes haya terminado de ejecutarse, vaya a **Administracion del sistema \> Configuración \> Almacén de entidades** y actualice la medida agregada **Informe de saldo decreciente**.

## <a name="accessing-the-power-bi-content"></a>Acceso al contenido de Power BI

El contenido de facturación de suscripción de Power BI se muestra en el espacio de trabajo **Facturación de suscripción**.
