---
title: "Terminología de contabilidad de costes"
description: "Este tema define los términos clave que se utilizan en la Contabilidad de costes."
author: YuyuScheller
manager: AnnBe
ms.date: 08/31/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: CAMCostControlWorkspace, CAMCostControlWorkspaceConfiguration
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Core, Operations
ms.custom: 223114
ms.assetid: 1c798592-77d0-4a8f-beaa-9159c75957da
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: yuyus
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: 957acdbbc6bba83b8b2e2b83fdf266524385141d
ms.contentlocale: es-es
ms.lasthandoff: 11/03/2017

---

# <a name="cost-accounting-terminology"></a>Terminología de contabilidad de costes

[!include[banner](../includes/banner.md)]


Este tema define los términos clave que se utilizan en la Contabilidad de costes.

**Base de asignación**

La base de asignación se usa para medir y cuantificar actividades como las horas de maquinaria que se usan, las horas de kilovatio (kWh) consumidas o los metros cuadrado que se ocupan. Se usa como base para asignar costes a uno o más objetos de coste.

**Contabilidad de costes**

La Contabilidad de costes permite recopilar datos de distintas fuentes, como la contabilidad general, los subdiarios, y los presupuestos, así como información estadística. A continuación, puede analizar, resumir y evaluar los datos de coste, de modo que la administración puede tomar las mejores decisiones para las actualizaciones de precios, los presupuestos, el control de costes, etc. Los datos de origen que se usan para el análisis de costes se tratan de forma independiente en la Contabilidad de costes. Por lo tanto, las actualizaciones en Contabilidad de costes no afectan a los datos de origen. Sin embargo, cuando se obtienen los datos de costes de varias fuentes, especialmente al importar las cuentas principales de Contabilidad general a Microsoft Dynamics 365 for Finance and Operations, Enterprise Edition como elementos de costes, hay redundancia de datos, ya que existen los mismos datos en la Contabilidad general y en la Contabilidad de costes. Dicha redundancia es necesaria, ya que la gestión financiera se utiliza para los informes externos y la Contabilidad de costes para los informes internos.

**Libro mayor de contabilidad de costes**

Se define en función del calendario, la divisa y la dimensión del artículo de coste; asimismo, supervisa los procesos y las directivas para medir costes. 

**Entrada de coste**

Las entradas de coste son el resultado de una transferencia mediante los conectores de datos de entradas de contabilidad general, asignaciones de costes y entradas registradas de coste en diarios de costes.

**Objeto de coste**

Cualquier tipo de objeto que se seleccione para el control de costes. Los costes o los ingresos se registran o se asignan directamente en los objetos de coste. Algunos objetos típicos de coste son:

-  Productos
-  Proyectos
-  Departamentos
-  Centros de coste

La administración utiliza objetos de coste para cuantificar costes, pero también para realizar un análisis de la rentabilidad.

**Elemento de coste**

Se usa como función para seguir y clasificar costes. Existen dos tipos de elementos de coste: principales y secundarios.

Los elementos de coste principales representan el flujo de costes de la contabilidad financiera a la contabilidad de costes. La estructura corresponde normalmente a la estructura contable de pérdidas y ganancias en el libro de contabilidad general, donde un elemento de costes puede corresponder a una cuenta principal. No todas las cuentas principales deben ser representadas necesariamente como elementos de coste, en función de las necesidades del negocio. 

Los elementos de coste secundarios representan el flujo de costes interno, ya que estos costes se crean y se usan solo en la Contabilidad de costes. Se usan en reglas de acumulación de costes para agregar costes en depósitos considerables que se usan en el cálculo de costes generales. 

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

**Unidad de control de costes**

Una unidad de control de costes representa la estructura de coste. La estructura determina cómo se gestionan los costes en orden jerárquico entre las dimensiones de objeto de coste y sus respectivos objetos de coste. 

**Distribución de costes**

Se usa para distribuir costes desde un objeto de coste a uno o más objetos de coste aplicando una base relevante de la asignación. La distribución de costes y la asignación de costes difieren en que la distribución de costes siempre se produce en el nivel de elemento de costes principal del coste original y no en un procesamiento recíproco.

**Asignación de costes**

Se usa para asignar el saldo de un objeto de coste a otros objetos de coste aplicando una base de asignación. Finance and Operations admite el método de asignación recíproco. En el método de asignación recíproco, se reconocen completamente los servicios mutuos que los objetos de coste auxiliar intercambian. El sistema determina automáticamente el orden correcto para realizar las asignaciones repetirlo. El saldo de un objeto de coste se asigna según una única base de asignación. Las asignaciones entre dimensiones de objetos de coste y sus miembros respectivos se admiten. El orden de asignación se controla por unidad de control de costes.

**Directiva de asignación de costes**

La directiva de asignación de costes define los importes y las cantidades que se deben asignar. Las reglas de asignación incluyen reglas de origen de la asignación, las cuales determinan los costes asignados, y reglas de asignación de objetivos, que determinan dónde se asignan los costes. Por ejemplo, todos los costes de servicios de las instalaciones son un origen de la asignación que se puede asignar a los distintos departamentos de una organización (es decir, a los objetivos de la asignación).

**Acumulación de costes**

El propósito de las reglas de acumulación de costes es agregar los costes en depósitos considerables. El nivel de agregación lo define el usuario e implica la asignación de un artículo de coste secundario. Si no se usa la acumulación de costes, cada elemento de costes se asigna desde un objeto de coste a otro.

**Directiva del índice de costes**

El índice de costes se usa para calcular el precio por objeto de coste. Para comprender los elementos del precio, puede definir directivas del índice de costes. Existen dos tipos de índices de costes: el índice de costes histórico e índice de costes planificado. Un índice de coste histórico es un índice calculado que se usa como multiplicador para la base de asignación de un objeto de coste. El índice se calcula en función de las asignaciones de coste en el período anterior. Un índice planificado es un índice definido por el usuario.

**Jerarquía de dimensiones**

Existen dos jerarquías de dimensión: jerarquía de categorización y jerarquía de clasificación. El tipo de jerarquía de categorización de dimensiones se usa para fines informativos. Admite solo las dimensiones del elemento de coste. El tipo de jerarquía de clasificación de dimensiones se usa para definir directivas y para fines informativos. Admite todas las dimensiones, como objetos de coste, elementos de coste y dimensiones estadísticas. 

**Conector de datos**

La contabilidad de costes admite la integración de datos de los sistemas de origen mediante los conectores de un conjunto de datos. Están disponibles los siguientes conectores de datos:

-  Transacción importadas (preconfiguradas)
-  Dynamics 365 for Finance and Operations, Enterprise Edition (preconfigurado)
-  Dynamics AX (configuración necesaria)

**Nota:** las transacciones que importó el conector de datos están basadas en entidades de datos.

**Proveedor de datos**

La mayoría de los sistemas de origen pueden proporcionar datos que coincidan con uno o varios orígenes de datos en la contabilidad de costes. Para alinear los datos de los sistemas de origen con el origen de datos de la contabilidad de costes, es necesario configurar un proveedor de datos. La tabla siguiente muestra un listado de proveedores de datos disponibles por conector y origen de datos.

|  **Orígenes de datos** |  **Conector de datos de transacciones importadas** | **Conector de datos de Dynamics 365 for Finance and Operations, Enterprise Edition**  | **Conector de datos de Dynamics AX**  |
|---|---|---|---|
| Miembros de dimensión de elemento de coste  |  Sí | Sí  | Sí  |
|  Miembros de dimensión de objeto de coste |  Sí | Sí  | Sí  |
|  Miembros de dimensión estadística | Sí  | N.º  | N.º  |
|  Contabilidad general | Sí  | Sí  | Sí  |
|  Entradas de presupuesto  | Sí  | Sí  | Sí  |
|  Medidas estadísticas | Sí  | Sí  | Sí  |

**Fórmula**

Las bases de asignación de fórmulas le permiten definir fórmulas avanzadas para lograr la base de asignación correcta. Puede crear manualmente las bases de asignación de fórmulas. Puede usar los siguientes operadores para definir su fórmula.

|  **Símbolos** | **Texto**  |
|---|---|
|  ( ) | Paréntesis  |
|  < |  Más pequeño que |
|  > |  Más grande que |
|  + |  Adición |
|  – |  Resta |
| *  | Multiplicación  |
    
No se admiten las instrucciones tradicionales SI. Sin embargo, puede crear instrucciones y validarlas si son verdaderas.

|  **Validación del informe** | **Resultado**  |
|---|---|
|  a > b| VERDADERO  |
|  a > b |  FALSO |
    
**Costes generales**

Los costes generales hacen referencia a los gastos en curso de operar un negocio. Existen costes que no pueden vincularse directamente a actividades empresariales específicas. Algunos ejemplos de costes generales son:

-   Cuotas de contabilidad
-   Depreciaciones
-   Seguro
-   Interés
-   Cuotas legales
-   Impuestos
-   Costes de servicios

**Tasa de costes generales**

Las tasas se definen según el objeto de coste y el elemento de coste. Existen dos tipos de tasas: la del periodo fiscal y la especificada por el usuario. Las tasas del periodo fiscal se calculan mediante el cálculo de los costes generales. En cambio, una tasa que especifique el usuario puede usarse para asignar el coste entre los objetos de coste de una tasa predeterminada en el cálculo de gastos generales.

**Publicada**

Si configura este campo en Sí, un usuario que esté asignado a uno de los roles siguientes puede ver el informe en el espacio de trabajo Control de costes:

-  Administrador de contabilidad de costes
-  Contable de costes
-  Contable de costes
-  Controlador de objeto de coste

Si configura este campo en No, solo los usuarios que estén asignados a uno de los roles siguientes pueden ver el informe en el espacio de trabajo Control de costes:

-  Administrador de contabilidad de costes
-  Contable de costes
-  Contable de costes

**Dimensión estadística**

Una dimensión estadística y sus miembros se usan para registrar y controlar entradas no monetarias en la contabilidad de costes. Los miembros de dimensión estadística se pueden utilizar con dos propósitos:

-  Como base de asignación en directivas como la distribución de costes o la asignación de costes.
-  Para informar del consumo no monetario.

Una dimensión estadística es la expresión de un recuento o de la suma de una actividad que se puede utilizar como base para las asignaciones o los cálculos de índice de costes. Se crea manualmente o se importa de las sistemas de origen. Los ejemplos de dimensiones estadísticas incluyen el número de empleados, el recuento de software que dispone de licencia en cada dispositivo, el consumo energético de cada equipo o los metros cuadrados para un centro de coste.

**Instrucción**

Las instrucciones son vistas para los administradores responsables del control de los costes. Las instrucciones se definen mediante un controlador de costes, y ofrecen una visión general rápida de los costes reales y los presupuestados, e incluso desviaciones y versiones de cálculo. Un administrador puede conseguir detalles más específicos si es necesario. Para garantizar que los administradores solo vean los datos de los que son responsables, los datos que aparecen en las instrucciones están sujetos a las reglas de acceso.

**Versión**

Las versiones se usan para simular, ver y comparar resultados diferentes. De forma predeterminada, todos los costes reales se ven en una versión base que se conoce como *real*. Para los presupuestos y los cálculos, puede trabajar con tantas versiones como sea necesario. Por ejemplo, puede importar datos de presupuesto en una versión original y después revisar el presupuesto en una versión revisada. Para los cálculos, puede crear varias versiones. En estas diferentes versiones, puede crear cálculos mediante diferentes reglas de cálculo que se aplicarán a la asignación de costes.



