---
title: Planificar su plan de cuentas local
description: Este tema proporciona información que le ayudará a planificar el plan de cuentas cuando tenga requisitos legales / locales para su organización.
author: veneva
ms.date: 10/07/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: DimensionConfigureAccountStructure, LedgerChartOfAccounts, LedgerConsolidateAccountGroup, MainAccountConsolidateAccount, DimensionDetails, MainAccountDetails
ROBOTS: ''
audience: Application User
ms.devlang: ''
ms.reviewer: roschlom
ms.tgt_pltfrm: ''
ms.custom: 14051
ms.assetid: 10edb129-33f0-4cf9-b2a7-4b7ffa09b229
ms.search.region: Global
ms.search.industry: ''
ms.author: veneva
ms.search.validFrom: 10/07/2021
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: a99e4ef3355188f574930c1d885e53fcb3134ad1
ms.sourcegitcommit: c4500b626667185643b3a2e7fc3a004d42198d07
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/29/2021
ms.locfileid: "7725184"
---
# <a name="plan-your-local-chart-of-accounts"></a>Planificar su plan de cuentas local

[!include [banner](../includes/banner.md)]

Este tema proporciona información que le ayudará a planificar el plan de cuentas cuando su organización incluya entidades legales que deben cumplir con los requisitos de las localidades específicas donde operan. Este tema utiliza los siguientes términos para describir planes de cuentas:

- **Global** - El plan de cuentas que la organización utiliza a nivel mundial. En la mayoría de los casos, se consolidará en este plan de cuentas.
- **Local** - Un plan de cuentas que utilizan las entidades legales de un país o región específicos.
- **Compartido** - Un plan de cuentas que puede utilizar más de una entidad jurídica. Se pueden compartir tanto el plan de cuentas global como el plan de cuentas local.

Puede crear y compartir varios planes de cuentas. Un plan de cuentas compartido puede ser utilizado por más de una entidad jurídica, pero solo se puede asignar un plan de cuentas a cada entidad jurídica. El plan contable que usa una entidad jurídica se define en la página **Libro mayor**.

Cuando diseñan el plan de cuentas, muchas organizaciones apuntan a un plan de cuentas global. La capacidad de plan de cuentas compartido permite la creación de un plan de cuentas global. La creación y el uso de un único plan de cuentas tiene ventajas. Por ejemplo, la gobernanza y el control, el mantenimiento y la generación de informes son más fáciles.

La mayoría de las organizaciones prefieren un plan de cuentas global y es el tipo más fácil de implementar. Sin embargo, algunas entidades legales requieren un plan de cuentas local por las siguientes razones:

- Requisitos legales locales
- Requisitos de las normas contables locales
- Requisitos del sector
- Requisitos de análisis e informes específicos de la empresa

Si su organización requiere que una entidad legal use un plan de cuentas local, hay dos opciones disponibles para implementarlo:

- Asigne el plan de cuentas global y defina otros medios para cumplir con los requisitos locales.
- Asigne un plan de cuentas local a la entidad jurídica y defina las relaciones con el plan de cuentas global.

La estructura de la organización y la estructura de informes determinan la opción que se utiliza.

[![Diagrama que muestra cómo la estructura de la organización determina si se debe utilizar un plan de cuentas global o local.](./media/local-chart-of-accounts-diagram.png)](./media/local-chart-of-accounts-diagram.png)

Si el plan de cuentas global se asigna a la entidad legal, las siguientes opciones están disponibles para cumplir con los requisitos de informes locales:

- Realizar la consolidación local.
- Utilizar una dimensión financiera para realizar un seguimiento del plan de cuentas local.
- Crear cuentas principales locales en el plan de cuentas global.
- Hacer un mapeo externo al plan de cuentas local.

Si el plan de cuentas local se asigna a la entidad legal, la única opción disponible actualmente para cumplir con los requisitos de informes blobales es la consolidación global.

## <a name="global-chart-of-accounts-assigned-to-a-legal-entity"></a>Plan de cuentas global asignado a una entidad jurídica

Si debe asignar el plan de cuentas global a una entidad legal, hay cuatro opciones disponibles para configurar el sistema, como se describió anteriormente. Para las cuatro opciones, se configura un único plan de cuentas y se vincula a cada entidad jurídica en la página **Libro mayor**. Luego, cada opción utiliza un enfoque diferente para cumplir con los requisitos de localización. Las siguientes secciones describen los pasos de alto nivel para configurar el sistema para los requisitos de localización. También describen las ventajas y desventajas de cada opción.

### <a name="do-local-consolidation"></a>Realizar la consolidación local

La consolidación local es el enfoque recomendado para cumplir con los requisitos del plan de cuentas local y aprovechar la funcionalidad del sistema que fue diseñada para este propósito.

#### <a name="set-up-consolidation-for-a-local-chart-of-accounts"></a>Configurar la consolidación para un plan de cuentas local

1. Cree un plan de cuentas global único que incluya todas las cuentas principales necesarias.
2. En cada entidad legal, asigne el plan de cuentas global en la página **Libro mayor**.
3. Cree una entidad jurídica de consolidación para cada localización necesaria.
4. Siga uno de estos pasos:

    - Si solo se requiere una localización, configure la cuenta de consolidación en la página **Cuenta principal**, o utilice las páginas **Grupos de consolidación** y **Cuentas de consolidación adicionales**.
    - Si se requiere más de una localización, o si tanto el número de cuenta como el nombre de la cuenta requieren traducción, use las páginas **Grupos de consolidación** y **Cuentas de consolidación adicionales** para representar los requisitos de localización.

5. Ejecute el proceso de consolidación para transformar el valor de la entidad jurídica de origen que utiliza el plan de cuentas global a la empresa de consolidación que utiliza el plan de cuentas local.

#### <a name="advantages"></a>Ventajas

- Este enfoque proporciona una forma coherente de trabajar en toda la organización.
- Se realiza una traducción de la posición local.
- Este enfoque admite la traducción tanto del ID de la cuenta principal como del nombre de cada cuenta principal.
- Admite múltiples localizaciones.

#### <a name="disadvantages"></a>Desventajas

- Se crea una empresa de consolidación adicional.
- Se compleeta un proceso de consolidación adicional.
- Este enfoque puede generar informes en el gráfico localizado solo después de que se complete el proceso de consolidación.

### <a name="use-a-financial-dimension-to-track-the-local-chart-of-accounts"></a>Utilizar una dimensión financiera para realizar un seguimiento del plan de cuentas local

Este enfoque utiliza una dimensión financiera donde los valores de la dimensión financiera representan las cuentas principales locales que se requieren para la localización. Funciona bien si solo se requiere una localización. Sin embargo, se vuelve menos utilizable a medida que agrega más localizaciones y dimensiones financieras.

#### <a name="set-up-a-financial-dimension-for-a-local-chart-of-accounts"></a>Configurar una dimensión financiera para un plan de cuentas local

1. Cree un plan de cuentas global único que incluya todas las cuentas principales necesarias.
2. En cada entidad legal, asigne el plan de cuentas global en la página **Libro mayor**.
3. Crear una dimensión financiera que represente el plan de cuentas local.
4. Crear valores de dimensión financiera que representen las cuentas principales en el plan de cuentas local.
5. Actualice la estructura de la cuenta para que incluya la dimensión financiera del "plan de cuentas local".
6. Asegúrese de que la dimensión financiera del "plan de cuentas local" siempre tenga un valor y que no permita un valor en blanco. Considere usar dimensiones derivadas o dimensiones fijas.
7. Cree un conjunto de dimensiones financieras donde la dimensión financiera del "plan de cuentas local" sea la primera dimensión financiera seleccionada. El conjunto de dimensiones financieras se puede utilizar cuando se genera el balance de prueba.

#### <a name="advantages"></a>Ventajas

- Las principales cuentas de los planes de cuentas globales y locales existen a nivel de transacciones. La cuenta principal es global y el valor de la dimensión financiera es local.
- Este enfoque proporciona informes y vistas en tiempo real tanto de la posición financiera global como de la posición financiera local.

#### <a name="disadvantages"></a>Desventajas

- En Parámetros del libro mayor, si el campo **Valores utilizados para la cuenta resumida** está configurado en **Distribuciones contables**, las dimensiones financieras que representan la cuenta principal para el gasto / activo / ingreso se utilizarán incorrectamente para la cuenta de resumen de Cuentas por cobrar y Cuentas por pagar. En su lugar, le recomendamos que establezca el campo en un documento de origen para asegurarse de que se utilizan los valores correctos de la dimensión financiera.
- Si se requieren muchos planes de cuentas locales y se utiliza una dimensión financiera para todos, la lista de valores de dimensión financiera que se utilizan puede resultar larga y difícil de trabajar.
- Si se requieren muchos planes de cuentas locales y se utiliza una dimensión financiera separada para representar cada uno, la usabilidad y el rendimiento del sistema pueden verse afectados cuando se agregan dimensiones financieras y conjuntos de dimensiones financieras.
- Le recomendamos que considere detenidamente la cantidad de dimensiones financieras que necesita, la cantidad de valores en cada una y la cantidad de conjuntos de dimensiones financieras, porque todos estos factores pueden afectar el rendimiento del sistema.

### <a name="create-local-main-accounts-in-the-global-chart-of-accounts"></a>Crear cuentas principales locales en el plan de cuentas global

*Sobre lo que preguntó el editor de textos:* en este enfoque, las cuentas principales locales en el plan de cuentas global incluyen las cuentas principales en el plan de cuentas local en el plan de cuentas global.

*Versión original:* las cuentas principales locales dentro del enfoque de CoA global es que las cuentas principales de CoA local se incluyen en el CoA global.

*Debería decir esto:* en este enfoque, las cuentas principales locales en el plan de cuentas local se incluyen en el plan de cuentas global.


#### <a name="set-up-local-main-accounts-in-the-global-chart-of-accounts"></a>Configurar cuentas principales locales en el plan de cuentas global

1. Cree un plan de cuentas único que incluya las cuentas principales tanto para el plan de cuentas global como para el plan de cuentas local.
2. En cada entidad legal, asigne el plan de cuentas en la página **Libro mayor**.
3. Cree cuentas totales en el plan de cuentas para sumar las cuentas principales que representan el mismo propósito.
4. Cree anulaciones de entidad legal en cada cuenta local para evitar transacciones de otras entidades legales para las que la cuenta local no fue diseñada.
5. Cree anulaciones de entidades legales en cada cuenta global para evitar transacciones de las entidades legales de localización.

#### <a name="advantages"></a>Ventajas

- Una vista en tiempo real de la posición financiera global y la posición financiera local está disponible en informes específicos y en vistas específicas en el sistema, como un informe financiero del balance. También se puede acceder mediante el botón **Período** en la cuenta total.
- No tiene un segmento adicional en la cuenta contable.

#### <a name="disadvantages"></a>Desventajas

- El uso total y la visibilidad de la cuenta son limitados. Por ejemplo, las cuentas totales no son visibles en la página de lista **Balance de prueba**.
- El mantenimiento requiere un esfuerzo adicional.
- La creación de informes financieros requiere un esfuerzo manual adicional.

### <a name="do-external-mapping-to-the-local-chart-of-accounts"></a>Hacer un mapeo externo al plan de cuentas local

La adopción de un plan de cuentas global supone que está administrando el mapeo y las localizaciones fuera del sistema. En este enfoque, solo crea un plan de cuentas global único en Microsoft Dynamics 365 Finance y manejar los requisitos fuera del sistema.

#### <a name="set-up-external-mapping-to-a-local-chart-of-accounts"></a>Configurar una asignación externa al plan de cuentas local

1. Cree un plan de cuentas global único que incluya todas las cuentas principales necesarias.
2. En cada entidad legal, asigne el plan de cuentas global en la página **Libro mayor**.
3. Hacer la asignacón al plan de cuentas local fuera de Finance

#### <a name="advantages"></a>Ventajas

- Este enfoque proporciona formas unificadas de trabajar en toda la organización.

#### <a name="disadvantages"></a>Desventajas

- No hay informes locales disponibles del sistema.
- Este enfoque es propenso a errores cuando se crean informes financieros.

## <a name="local-chart-of-accounts-assigned-to-legal-entity"></a>Plan de cuentas local asignado a la entidad jurídica

Si su organización decide no utilizar un plan de cuentas global en todas las entidades legales, se crea un plan de cuentas independiente para cada plan de cuentas local único. A continuación, cada entidad jurídica se vincula al plan de cuentas correspondiente en la página **Libro mayor**.

### <a name="do-global-consolidation"></a>Realizar la consolidación global

En este enfoque, se utiliza una empresa de consolidación para acumular y combinar los saldos de cada empresa local de origen en el plan de cuentas global combinado en la empresa de consolidación. Este enfoque requiere que mantenga un mapeo de cada plan de cuentas local al plan de cuentas global en la empresa de consolidación.

#### <a name="set-up-global-consolidation"></a>Configurar la consolidación global

1. Cree un plan de cuentas independiente para cada entidad jurídica que tenga un plan de cuentas local diferente. Si alguna entidad legal tiene el mismo plan de cuentas local, solo se requiere un plan de cuentas local y se puede compartir.
2. En cada entidad legal, asigne el plan de cuentas correcto en la página **Libro mayor**.
3. Opcional: Cree un plan de cuentas para el plan de cuentas global de cada empresa de consolidación que tenga un plan de cuentas global diferente.
4. Cree una entidad legal de consolidación para cada nivel de consolidación que se requiera y asigne el plan de cuentas apropiado en la página **Libro mayor**.
5. Siga uno de estos pasos:

    - Si solo se requiere una consolidación, configure la cuenta de consolidación en la página **Cuenta principal**.
    - Si se requiere más de una consolidación, o si tanto el número de cuenta como el nombre de la cuenta requieren traducción, use las páginas **Grupos de consolidación** y **Cuentas de consolidación adicionales** para representar los requisitos del plan de cuentas global.

6. Ejecute el proceso de consolidación para transferir los saldos de las entidades legales locales a la entidad legal consolidada. Esta entidad jurídica consolidada utiliza las cuentas de consolidación que definió en el paso 5.

#### <a name="advantages"></a>Ventajas

- El formato de las normas contables locales se aplica de forma nativa.
- Este enfoque le da al equipo de finanzas local una forma más fácil de trabajar.

#### <a name="disadvantages"></a>Desventajas

- No se dispone de una vista en tiempo real de la posición global.
- Es posible que el proceso de consolidación se ejecute con más frecuencia.

## <a name="additional-resources"></a>Recursos adicionales

- [Planificar su plan de cuentas](plan-chart-of-accounts.md)
- [Configurar libros mayores](configure-ledger.md)
- [Dimensiones financieras y registro](Default-dimensions.md#balancing-dimension)
- [Conjuntos de dimensiones financieras](financial-dimension-sets.md)
- [Información general de consolidación y eliminación](../budgeting/consolidation-elimination-overview.md)
- [Grupos de cuentas de consolidación y cuentas de consolidación adicionales](../budgeting/consolidation-account-groups-consolidation-accounts.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
