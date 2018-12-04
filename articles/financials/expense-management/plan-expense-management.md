---
title: "Configurar la gestión de gastos"
description: "En este artículo se describen las consideraciones y las decisiones que debe realizar durante el proceso de planificación, antes de configurar Gestión de gastos en Microsoft Dynamics 365 for Finance and Operations."
author: KimANelson
manager: AnnBe
ms.date: 08/29/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: GlobalCategory, ProjCategory, TrvLocations, TrvParameters, TrvPaymethod, TrvPerDiems
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.custom: 23001
ms.assetid: aa3fd14d-7e94-4603-985f-ca26d6f860ea
ms.search.region: Global
ms.author: knelson
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: a0739304723d19b910388893d08e8c36a1f49d13
ms.openlocfilehash: c87909d9eb3a4d717e0c40289353da0267a51f60
ms.contentlocale: es-es
ms.lasthandoff: 03/26/2018

---

# <a name="configure-expense-management"></a>Configurar la gestión de gastos

[!include [banner](../includes/banner.md)]

En este tema se describen las consideraciones y las decisiones que debe realizar durante el proceso de planificación, antes de configurar Gestión de gastos en Microsoft Dynamics 365 for Finance and Operations. En el área Gestión de gastos, puede almacenar información sobre los métodos de pago, los pedidos de viaje, los informes de gastos y las directivas, entre otros elementos.

Dado que muchas de las decisiones que realiza al planificar su configuración para la gestión de gastos se basan en la jerarquía y la estructura financiera de su organización, debe hacer referencia a los documentos de planificación para esas áreas.

## <a name="intercompany-expenses"></a>Gastos de empresas vinculadas

Al habilitar los gastos de empresas vinculadas, permite a las entidades jurídicas y a los empleados incurrir en gastos en nombre de otra entidad jurídica, y realizar el cobro a la entidad jurídica de empleo dentro de su organización. Por ejemplo, un empleado de una entidad jurídica A completa un proyecto para la entidad jurídica B, y el proyecto incurre en gastos relacionados con un viaje. Si se habilitan los gastos de empresas vinculadas, el empleado puede entonces archivar un informe de gastos que se enviará a la entidad jurídica B; esos gastos debe pagarlos la entidad jurídica A. Si su organización no tiene varias entidades jurídicas, no necesitará habilitar los gastos de empresas vinculadas.

**Decisión:** ¿Desea habilitar gastos de empresas vinculadas?

## <a name="financial-management"></a>Administración financiera

La gestión de gastos se integra totalmente con la administración financiera de la organización. Gran parte de la configuración de la gestión de gastos se basará en las decisiones que haya realizado sobre las finanzas de su organización. Las siguientes secciones describen varias áreas que requieren planificación y decisiones basadas en la orientación y las decisiones financieras de su organización del equipo de dirección.

### <a name="per-diems"></a>Dietas

Debe definir las dietas de empleado que ofrece su organización. Dado que las dietas se suelen usar para satisfacer gastos como comidas, alojamiento y otros gastos incidentales, puede crear reglas para las retribuciones de dietas para que ofrece su organización. Las tarifas de dietas se pueden basar en la época del año, el destino del viaje o ambos. Al definir una regla de dietas, puede especificar la retención de un porcentaje de la tarifa de dietas si el trabajador recibe comidas o servicios complementarios. También puede definir niveles de tabla de dietas para establecer el mínimo o máximo de horas durante las que se puede aplicar la tarifa de dietas al viaje del trabajador.

**Decisiones:**

- Reglas de dietas predeterminadas para el primer y el último día:

    - ¿Cuál es el número mínimo de horas que un empleado puede reclamar para un día y recibir aún dietas?
    - ¿Hay una reducción del importe que se ofrece para comidas el primer y el último día? Si existe una reducción, ¿cuál es el porcentaje de la misma?
    - ¿Hay una reducción del importe que se ofrece para un hotel el primer y el último día? Si existe una reducción, ¿cuál es el porcentaje de la misma?
    - ¿Hay una reducción del importe que se ofrece para otros gastos generados el primer y el último día? Si existe una reducción, ¿cuál es el porcentaje de la misma?

- Reglas de dietas predeterminadas:

    - ¿Hay una reducción del porcentaje en el permiso de dietas para cada comida si, por ejemplo, la comida es gratuita? Si existe una reducción, ¿cuál es el porcentaje de reducción de cada comida?
    - ¿La reducción de la comida se calcula por día, por viaje o por el número de comidas al día?
    - ¿Es necesario redondear los importes de las dietas de forma normal o deben redondearse hacia arriba?
    - ¿Las dietas se calculan en un período de 24 horas o en un día de calendario?

- Reglas de dietas basadas en la ubicación:

    - ¿Las tarifas de dietas cambian según la ubicación? ¿Qué ubicaciones están incluidas?
    - Si las tarifas de dietas varían según la ubicación, teniendo en cuenta cada ubicación, ¿qué porcentaje del importe se proporciona según los siguientes tipos de gastos?:

        - Comidas
        - Hotel
        - Otros gastos

### <a name="expense-management-journals-and-accounts"></a>Cuentas y diarios de gestión de gastos

La gestión de gastos requiere que use varios diarios y cuentas. Debe decidir, por ejemplo, si se usa la misma cuenta para anticipos y conflictos de tarjeta de crédito.

**Decisiones:**

- ¿En qué diario contable se registran los informes de gastos aprobados?
- ¿Qué cuenta se usa para anticipos?
- ¿Se deben registrar los anticipos inmediatamente?

### <a name="payment-methods"></a>Métodos de pago

Cuando permite a los empleados incurrir en gastos en nombre de su negocio, debe definir los métodos de pago que se permiten usar a los empleados. Por ejemplo, puede que permitir a los empleados usar efectivo o una tarjeta de crédito corporativa. También puede permitir a los empleados usar tarjetas de crédito personales y después reembolsar a los empleados. Debe tomar las siguientes decisiones para cada método de pago que habilite.

**Decisiones:**

- ¿Qué métodos de pago se permiten?
- ¿Quién posee los gastos del método de pago?
- ¿Hay un tipo de cuenta de contrapartida? Si hay un tipo de cuenta de contrapartida, ¿cuál es?
- Si hay una cuenta de contrapartida, ¿cuál es la cuenta?
- Si el método de pago es una tarjeta de crédito, ¿debe usarse el método de pago solo con transacciones importadas?

### <a name="expense-categories-and-shared-categories"></a>Categorías de gastos y categorías compartidas

Cuando los empleados crean un informe de gastos, cada gasto que registran se debe asociar a una categoría de gastos. Las categorías de gastos se derivan de las categorías compartidas que se pueden compartir en las entidades jurídicas de la organización. Estas categorías también se pueden compartir en la gestión de proyectos y la contabilidad, en función de cómo se define la organización. En función de la definición de su organización y la orientación del equipo de implementación, determine si las categorías que se utilizan en la gestión de gastos deberán usarse solo en administrar gastos o si se deben compartir entre la administración del proyecto, la contabilidad y la administración de gastos. Tenga en cuenta que estas categorías se pueden compartir entre el proyecto y los gastos o el proyecto y la producción, pero no entre el gasto y la producción. Debe tomar las siguientes decisiones para cada categoría de gastos.

**Decisiones:**

- ¿Cuál es la categoría de gasto? Estos ejemplos incluyen categorías de vuelos, hoteles o kilometraje.
- ¿Se puede usar también esta categoría de gastos en la gestión del proyecto y la contabilidad?
- ¿Cuál es el tipo de gasto?
- ¿Cuál es el método de pago predeterminado para la categoría de gastos?
- ¿Los gastos de la categoría de gastos deben estar detallados?
- ¿Cuál es la principal cuenta predeterminada para la categoría de gastos?
- ¿Qué es el grupo de impuestos de artículos predeterminado para la categoría de gastos?
- ¿Se permiten métodos de pago adicionales para la categoría de gastos? Si se permiten los métodos de pago adicionales, ¿cuáles pueden ser?
- ¿Hay subcategorías en esta categoría de gastos? Si hay subcategorías, también debe tomar las decisiones siguientes:

    - ¿Se excluye cualquiera de las subcategorías de la devolución de impuestos?
    - ¿Cuál es el grupo de impuestos de artículos de las subcategorías?

Si esta categoría de gastos también se usa en la gestión de proyectos y la contabilidad, responda las preguntas restantes. Si no, vaya a la sección siguiente.

- ¿Qué cuentas de costes se usarán para lo siguientes gastos?

    - Coste
    - Asignación de nóminas
    - Trabajo en proceso - Valor de coste
    - Coste-artículo
    - Trabajo en proceso - Valor de coste - Artículo
    - Pérdida acumulada
    - Trabajo en proceso - Pérdida acumulada

- ¿Qué cuentas de ingresos se usarán para lo siguiente?

    - Ingresos facturados
    - Ingresos acumulados-valor de ventas
    - Trabajo en proceso-valor de ventas
    - Ingresos acumulados-producción
    - Trabajo en proceso-producción
    - Ingresos acumulados-ganancias
    - Trabajo en proceso - ganancias
    - Ingresos acumulados-suscripción
    - Trabajo en proceso - suscripción

### <a name="taxes"></a>Impuestos

Para los impuestos relacionados con gastos, debe determinar qué se incluye o se permite en los informes de gastos.

**Decisiones:**

- ¿Los impuestos se incluyen en los importes de gastos?
- ¿Se debe habilitar la devolución de impuestos en los gastos?

    > [!NOTE]
    > Si al planificar el libro de contabilidad general decidió aplicar los impuestos de los Estados Unidos y las reglas del IVA de importación, no puede habilitar la opción de devolución de impuestos en los gastos. (Para aplicar los impuestos de los Estados Unidos y las reglas del IVA de importación, establezca la opción **Aplicar reglas de tributación de impuestos** en **Sí**).

## <a name="policies"></a>Directivas

Al crear directivas de informes de gastos, su organización ahorrará tiempo y dinero cuando los empleados generen gastos en su nombre. Las directivas le garantizan que los empleados se ajustan al presupuesto, proporcionan toda la información necesaria y gastan dinero solo si es necesario. Debe tomar las siguientes decisiones para cada directiva de informe de gastos y cada directiva de aprobación de informe de gastos que cree.

**Decisiones:**

- ¿Cuál es el nombre de la directiva?
- ¿Para qué es la directiva de gastos?
- Si decidió anteriormente habilitar los gastos de empresas vinculadas, ¿a qué empresas de su organización se aplicará esta directiva?
- ¿Cuándo entrará en vigor la directiva?
- ¿Cuándo expira la directiva?
- ¿Cuál es la regla de directivas?
- ¿Cuál es el resultado de la regla de directivas?

