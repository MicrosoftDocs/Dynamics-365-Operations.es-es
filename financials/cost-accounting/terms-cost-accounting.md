---
title: "Terminología de contabilidad de costes"
description: "Este tema define los términos clave que se utilizan en la Contabilidad de costes."
author: YuyuScheller
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: CAMCostControlWorkspace, CAMCostControlWorkspaceConfiguration
audience: Application User
ms.search.scope: Operations, Core
ms.custom: 223114
ms.assetid: 1c798592-77d0-4a8f-beaa-9159c75957da
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: yuyus
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.translationtype: Human Translation
ms.sourcegitcommit: fd3392eba3a394bd4b92112093c1f1f9b894426d
ms.openlocfilehash: 76c5d4b3a118747246eeb7ca0db69532af04bf9c
ms.contentlocale: es-es
ms.lasthandoff: 04/25/2017


---

# <a name="cost-accounting-terminology"></a>Terminología de contabilidad de costes

[!include[banner](../includes/banner.md)]


Este tema define los términos clave que se utilizan en la Contabilidad de costes.

**Contabilidad de costes**

La Contabilidad de costes permite recopilar datos de distintas fuentes, como la contabilidad general, los subdiarios, y los presupuestos, así como información estadística. A continuación, puede analizar, resumir y evaluar los datos de coste, de modo que la administración puede tomar las mejores decisiones para las actualizaciones de precios, los presupuestos, el control de costes, etc. Los datos de origen que se usan para el análisis de costes se tratan de forma independiente en la Contabilidad de costes. Por lo tanto, las actualizaciones en Contabilidad de costes no afectan a los datos de origen. Sin embargo, cuando se obtienen los datos de costes de varias fuentes, especialmente al importar las cuentas principales de Contabilidad general a Microsoft Dynamics 365 for Operations como elementos de costes, hay redundancia de datos, ya que existen los mismos datos en la Contabilidad general y en la Contabilidad de costes. Dicha redundancia es necesaria, ya que la gestión financiera se utiliza para los informes externos y la Contabilidad de costes para los informes internos.

**Libro mayor de contabilidad de costes**

El libro mayor de la contabilidad de costes es un marco especializado que determina cómo los procesos, los valores y las cantidades se especifican y se muestran para un área específica en la Contabilidad de costes. El libro mayor de la contabilidad de costes define procesos y reglas para calcular costes en objetos de coste. Maneja transacciones de coste y gestiona los documentos que registran los cambios en los valores y las cantidades que producen las transacciones de costes.

**Entrada de coste**

Las entradas de coste son el resultado de una transferencia mediante los conectores de datos de entradas de contabilidad general, asignaciones de costes y entradas registradas de coste en diarios de costes.

**Objeto de coste**

Los objetos de coste son cualquier tipo de objeto a los que se asignan los costes. A continuación se muestran algunos objetos típicos de coste:

-   Productos
-   Proyectos
-   Recursos
-   Departamentos
-   Centros de coste
-   Regiones geográficas

La administración utiliza objetos de coste para cuantificar costes, pero también para realizar un análisis de la rentabilidad.

**Elemento de coste**

Los elementos de coste se utilizan como una función para realizar un seguimiento y para categorizar a dónde fluyen los costes. Existen dos tipos de elementos de coste: costes principales y costes secundarios. **Costes principales** Los elementos de coste principales representan el flujo de costes de la contabilidad financiera a la contabilidad de costes. La estructura del elemento de coste corresponde a la estructura de la cuenta de pérdidas y ganancias en la contabilidad general, donde un elemento de costes puede corresponder a una cuenta principal. No todas las cuentas principales deben ser representadas necesariamente como elementos de coste, en función de las necesidades del negocio. A continuación se muestran algunos ejemplos de elementos de coste principales:

-   Costes de mercancías vendidas (COG)
-   Costes indirectos de material
-   Costes de personal
-   Costes de energía

**Elemento de costes secundario** 

Los elementos de coste secundarios representan el flujo de costes interno, ya que estos costes se crean y se usan solo en la Contabilidad de costes. Los elementos de costes secundarios ayudan a garantizar que el origen de los costes pueda seguirse. Dichos elementos de costes se utilizan en asignaciones de costes y cálculos de gastos generales. A continuación se muestran algunos ejemplos de elementos de coste secundarios:

-   Costes de producción
-   Gastos generales de producción, materiales y marketing

**Unidad de control de costes**

Una unidad de control de costes representa la estructura de coste. Debe estar asociada a las dimensiones de objeto de coste en un libro mayor de la contabilidad de costes.

**Versión**

Las versiones se usan para simular, ver y comparar resultados diferentes. De forma predeterminada, todos los costes reales se ven en una versión base que se conoce como *real*. Para los presupuestos y los cálculos, puede trabajar con tantas versiones como sea necesario. Por ejemplo, puede importar datos de presupuesto en una versión original y después revisar el presupuesto en una versión revisada. Para los cálculos, puede crear varias versiones. En estas diferentes versiones, puede crear cálculos mediante diferentes reglas de cálculo que se aplicarán a la asignación de costes.

**Extracto**

Las instrucciones son vistas para los administradores responsables del control de los costes. Las instrucciones se definen por un controlador de coste, y ofrecen una visión general rápida de los costes reales y los presupuestados, e incluso desviaciones y versiones de cálculo. Para ayudar a garantizar que los administradores ven solo los datos de los que son responsables, los datos que aparecen en las instrucciones están sujetos a las reglas de acceso.

**Conector de datos**

Los datos se pueden importar en la Contabilidad de costes desde sistemas externos mediante los conectores de datos. Por ejemplo, puede importar las estructuras contables, las dimensiones, las entradas de contabilidad general y las entradas de presupuesto. Puede usar los conectores de datos configurados previamente o los personalizados para importar datos y crear conexiones de datos.

**Clasificación de costes**

La clasificación de costes agrupa los costes según sus características compartidas. Por ejemplo, los costes se pueden agrupar por elementos, rastreabilidad y comportamiento.

-   **Por elementos**: materiales, trabajo y gastos.
-   **Por rastreabilidad**: costes directos e indirectos. Los costes directos se asignan directamente a los objetos de coste. Los costes indirectos no son directamente detectables a los objetos de coste. Los costes indirectos se asignan a objetos de coste.
-   **Por comportamiento**: fijo, variable y semivariable.

**Comportamiento de costes**

El comportamiento del coste clasifica los costes según el comportamiento en relación a los cambios en las actividades empresariales clave. Para controlar los costes de forma eficaz, la administración debe comprender el comportamiento del coste. Hay tres tipos de patrones de comportamiento de los costes: fijo, variable y semivariable.

- **Coste fijo** Un coste fijo es un coste que no varía a corto plazo, independientemente de los cambios en el nivel de actividad. Por ejemplo, un coste fijo puede ser un gasto básico de explotación de un negocio, como el alquiler, que no se verá afectado incluso si el nivel de actividad aumenta o disminuye.

- **Coste variable** Un coste variable cambia de acuerdo a los cambios en el nivel de actividad. Por ejemplo, un coste específico de material directo está asociado a cada producto que se vende. Cuantos más productos se vendan, más coste de material directo habrá.

- **Coste semivariable** Los costes semivariables son costes parcialmente fijos y parcialmente variables. Por ejemplo, una cuota de acceso a Internet incluye una cuota mensual estándar de acceso y una cuota de uso de banda ancha. La cuota mensual estándar de acceso es un coste fijo, mientras que la cuota de uso de banda ancha es un coste variable.

**Costes generales**

Los costes generales hacen referencia a los gastos en curso de operar un negocio. Existen costes que no pueden vincularse directamente a actividades empresariales específicas. Algunos ejemplos de costes generales son:

-   Cuotas de contabilidad
-   Depreciaciones
-   Seguro
-   Interés
-   Cuotas legales
-   Impuestos
-   Costes de servicios

**Asignación de costes**

La asignación de costes es el proceso de asignación y atribución, en función de las causas originales de los costes comunes. Se asignan los importes de costes y las cantidades de un objeto de coste a uno o más objetos de coste distintos. Por ejemplo, todos los costes de servicios de las instalaciones se asignan a los distintos departamentos que usan el edificio de oficinas común.

**Directiva de asignación de costes**

La directiva de asignación de costes define los importes y las cantidades que se deben asignar. Las reglas de asignación incluyen reglas de origen de la asignación, las cuales determinan los costes asignados, y reglas de asignación de objetivos, que determinan dónde se asignan los costes. Por ejemplo, todos los costes de servicios de las instalaciones son un origen de la asignación que se puede asignar a los distintos departamentos de una organización (es decir, a los objetivos de la asignación).

**Base de asignación**

La base de asignación es la base que se puede utilizar para medir y cuantificar actividades, como las horas de maquinaria que se usan, las horas de kilovatio que se consumen, las horas de trabajo directo que se emplean o los metros cuadrados que se ocupan. Se usa para asignar costes a uno o más objetos de coste.

**Principio de asignación**

Uno de los principios de asignación es asignar el coste por índice de costes. Puede elegir asignar costes con el índice real del período o con un índice histórico. La asignación que utiliza el método recíproco ayuda a garantizar que la base de asignación viene determinada por una serie de ecuaciones simultáneas antes de que la asignación se haga mediante el índice real del período.

**Acumulación de costes**

El propósito de la acumulación de costes es incluir todos los costes de un objeto de coste concreto. El nivel de agrupación está definido por el usuario. Mediante el uso de la acumulación de costes, puede agregar elementos de costes que se deben asignar desde un objeto de coste a otro. Cuando la acumulación de costes no se utiliza, cada elemento de costes se asigna desde un objeto de coste a otro.

**Directiva del índice de costes**

El índice de costes se usa para calcular el precio por objeto de coste. Para comprender los elementos del precio, puede definir directivas del índice de costes. Existen dos tipos de índices de costes: el índice de costes histórico e índice de costes planificado. Un índice de coste histórico es un índice calculado que se usa como multiplicador para la base de asignación de un objeto de coste. El índice se calcula en función de las asignaciones de coste en el período anterior. Un índice planificado es un índice definido por el usuario.

**Jerarquía de dimensiones**

Las jerarquías dimensionales se usan como estructuras de informes al definir las reglas para la asignación, el índice de costes y la acumulación de costes, ver los extractos o los datos de Microsoft Excel y definir el acceso a los datos agregados. Existen dos jerarquías de dimensión: jerarquía de categorización y jerarquía de clasificación. Una jerarquía de categorización se define a partir de elementos de costes, mientras que una jerarquía de clasificación se define a partir de objetos de coste.

**Dimensión estadística**

Una dimensión estadística es la expresión de un recuento o de la suma de un objeto que se puede utilizar como base para las asignaciones o los cálculos de índice de costes. Se crea manualmente o se importa de las sistemas de origen. Los ejemplos de dimensiones estadísticas incluyen el número de empleados, el recuento de software que dispone de licencia en cada dispositivo, el consumo energético de cada equipo o los metros cuadrados para un centro de coste.

**Entrada estadística**

Las entradas estadísticas mantienen la suma registrada o el valor de recuento para una dimensión estadística concreta. La suma registrada o el valor de recuento también se conocen como magnitud.




