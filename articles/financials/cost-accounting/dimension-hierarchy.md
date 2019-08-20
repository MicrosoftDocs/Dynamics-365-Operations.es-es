---
title: Jerarquía de dimensiones
description: Este tema proporciona información sobre las jerarquías de dimensiones. Use una jerarquía de dimensiones para definir la estructura del informe, las directivas de coste y configurar la seguridad en la contabilidad de costes.
author: AndersGirke
manager: AnnBe
ms.date: 06/16/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CAMDimensionHierarchy,
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: shylaw
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: eb28ee4bdde937b5a23a4ad87122358e9cabe256
ms.sourcegitcommit: 8b4b6a9226d4e5f66498ab2a5b4160e26dd112af
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/01/2019
ms.locfileid: "1841546"
---
# <a name="dimension-hierarchy"></a>Jerarquía de dimensiones

[!include [banner](../includes/banner.md)]

Este tema proporciona información sobre las jerarquías de dimensiones. Use una jerarquía de dimensiones para definir la estructura del informe, las directivas de coste y configurar la seguridad en la contabilidad de costes.  

## <a name="overview"></a>Información general

Las jerarquías de dimensión se usan en distintas ubicaciones en contabilidad de costes. Una jerarquía de dimensiones permite definir la siguiente información:

-  La estructura de notificación que encaja en los requisitos de la organización
-  Directivas de costes
-  La configuración de seguridad

A continuación se muestra un ejemplo de una jerarquía de dimensiones.

![Ejemplo de una jerarquía de dimensiones](./media/dimension-hierarchy.png)

Una jerarquía de dimensión se puede crear para los siguientes tipos de dimensión:

-  Dimensiones de elemento de coste
-  Dimensiones de objeto de coste
-  Dimensiones estadísticas

> [!NOTE]
> - Puede crear varias jerarquías de dimensiones para la misma dimensión si se requieren distintas perspectivas.
> - Una jerarquía de dimensión se puede asociar solo a una dimensión.
> - Una jerarquía de dimensión puede tener niveles ilimitados en su estructura. Todos los niveles estarán disponibles en el espacio de trabajo **Control de costes**. Cuando se usa Microsoft Excel o Microsoft Power BI para fines de notificación, solo los primeros 15 niveles de la jerarquía de dimensiones se exportan. Esta limitación existe porque Excel y Power BI requieren un esquema fijo.
> - Jerarquía de dimensiones no tiene una fecha de vigencia. Por lo tanto, los cambios en una jerarquía de dimensiones se guardan inmediatamente en el registro y no se puede comparar de fecha de antes y de después.

## <a name="dimension-hierarchy-type"></a>Tipo de jerarquía de dimensión

Al crear una nueva jerarquía de dimensiones, debe seleccionar un tipo de jerarquía. Vaya a **Contabilidad de costes** > **Dimensiones** > **Jerarquías de dimensiones**. Haga clic en **Nuevo** y seleccione un tipo de la jerarquía de dimensiones. Puede seleccionar **Jerarquía de categorización de dimensiones** o **Jerarquía de clasificación de dimensiones**.

### <a name="dimension-categorization-hierarchy"></a>Jerarquía de categorización de dimensiones

El tipo **Jerarquía de categorización de dimensiones** se usa para fines informativos. Admite solo las dimensiones del elemento de coste. Cuando selecciona este tipo, se aplicarán las siguientes reglas:

-  Un miembro de la dimensión se puede asociar más de una vez en la estructura de la jerarquía.
-  Puede colocar un miembro de dimensión de elemento de coste en distintos nodos asignando un comportamiento de coste al nodo de hoja.

### <a name="dimension-classification-hierarchy"></a>Jerarquía de clasificación de dimensiones

El tipo **Jerarquía de clasificación de dimensiones** se usa para definir reglas y fines de notificación. Admite todas las dimensiones, como objetos de coste, elementos de coste y dimensiones estadísticas. Cuando seleccione este tipo, un miembro de la dimensión se puede asociar solo una vez en la estructura de la jerarquía.

## <a name="create-and-maintain-a-dimension-hierarchy"></a>Crear y mantener las jerarquías dimensiones

Una jerarquía de dimensiones se crea como estructura de árbol que tiene relaciones de nodo y nodo de hoja.

-  Uno nodo puede tener 1:_n_ subnodos.
-  Un nodo no puede tener subnodos y nodos de hoja asignados a la vez.
-  Un nodo de hoja solo se puede asignar en el nivel inferior de la jerarquía.

### <a name="example"></a>Ejemplo

Una empresa pequeña tiene la estructura organizativa siguiente, donde los recursos de finanzas y recursos humanos son departamentos de Administración y ensamblaje y empaquetado son departamentos de Producción.

![Ejemplo de una estructura de organización](./media/dimension-hierarchy-org.png)

Una dimensión de objetos de coste representa todos los centros de coste de la organización.

- Dimensión de objeto de coste
    - Centros de coste

La dimensión de objeto de coste que representa todos los centros de coste se puede configurar como se muestra aquí.

| Centros de coste | Descripción |
|--------------|-------------|
| CC001        | RR. HH.          |
| CC002        | Finanzas     |
| CC003        | Impuesto         |
| CC007        | AR/AP       |
| CC005        | Ensamblado    |
| CC006        | Empaquetado   |

Una dimensión de elementos de coste representa todos los elementos de coste de la organización.

- Dimensión de elemento de coste
    - Elementos de coste

La dimensión de elementos de coste que representa todos los elementos de coste se puede configurar como se muestra aquí.

| Elementos de coste | Descripción |
|---------------|-------------|
| 10001         | Electricidad |
| 10010         | Limpieza    |
| 10011         | Calefacción     |
| 40001         | COGS        |

Una jerarquía de dimensión que cumple los requisitos de generación de informes de la organización se puede establecer como se muestra aquí.

**Detalles de jerarquía de dimensión**

| Nombre de jerarquía de dimensión | Dimensión    | Nombre de tipo de jerarquía de dimensión      | Jerarquía de listas de acceso |
|--------------------------|--------------|------------------------------------|-----------------------|
| Organización             | Centros de coste | Jerarquía de clasificación de dimensiones | N.º                    |

La jerarquía de dimensión para informar se puede configurar como se muestra aquí.

|                   | Intervalos de miembros de dimensión   |                         |
|-------------------|---------------------------|-------------------------|
| **Nodos**         | **Desde miembro de dimensión** | **Hasta miembro de dimensión** |
| Organización      |                           |                         |
| &nbsp;&nbsp;Administrador         |                           |                         |
|&nbsp;&nbsp;&nbsp;&nbsp;Finanzas   | CC002                     | CC003                   |
|                   | CC007                     | CC007                   |
| &nbsp;&nbsp;&nbsp;&nbsp;RR. HH.        | CC001                     | CC001                   |
| &nbsp;&nbsp;Producción    |                           |                         |
| &nbsp;&nbsp;&nbsp;&nbsp;Empaquetado | CC005                     | CC005                   |
| &nbsp;&nbsp;&nbsp;&nbsp;Ensamblado  | CC006                     | CC006                   |

Una jerarquía de dimensión que cumple los requisitos de la directiva se puede establecer como se muestra aquí.

**Detalles de jerarquía de dimensión**

| Nombre de jerarquía de dimensión | Dimensión     | Nombre de tipo de jerarquía de dimensión      |
|--------------------------|---------------|------------------------------------|
| Comportamiento de costes            | Elementos de coste | Jerarquía de clasificación de dimensiones |

La jerarquía de dimensión para la directiva se puede configurar como se muestra aquí.

|                   | Intervalos de miembros de dimensión   |                         |
|-------------------|---------------------------|-------------------------|
| **Nodos**         | **Desde miembro de dimensión** | **Hasta miembro de dimensión** |
| Comportamiento de costes     |                           |                         |
| &nbsp;&nbsp;Coste fijo    | 10001                     | 10011                   |
|&nbsp;&nbsp;Coste variable | 40001                     | 40010                   |

> [!NOTE]
> En **Intervalos de miembros de dimensión**, un nodo puede contener 1: intervalos de miembros de dimensión _n_. Puede insertar los identificadores de miembro de dimensión que aún no existen como miembros de dimensión. Este enfoque hace que la jerarquía sea resistente para el futuro.  

### <a name="copy-a-hierarchy"></a>Copiar una jerarquía

Puede copiar una jerarquía de dimensiones actual como punto de partida para una nueva jerarquía de dimensiones. Este método puede ser de utilidad si desea comparar la jerarquía de dimensiones anterior con una nueva jerarquía de dimensiones.

### <a name="rearrange-nodes-in-a-hierarchy"></a>Reorganizar los nodos en una jerarquía

Puede mover un nodo hacia arriba y hacia abajo dentro de su nivel actual en la estructura. De esta manera, puede reorganizar el orden de los nodos para las notificaciones en el espacio de trabajo **Control de costes**.

Se mueve un nodo a una nueva ubicación en la jerarquía seleccionando el nodo de destino. Existen dos formas de mover un nodo:

- **Mover hacia abajo**: mueva el nodo seleccionado desde su posición actual en la jerarquía e insértelo el nodo **debajo** del nodo objetivo seleccionado.
- **Mover hacia arriba**: mueva el nodo seleccionado desde su posición actual en la jerarquía e insértelo el nodo **detrás** del nodo objetivo seleccionado en su nivel de la jerarquía.

> [!NOTE] 
> El orden de los nodos no se mantiene al exportar datos a Excel o Power BI, ya que estas herramientas usan una clasificación alfanumérica predeterminada. Debe cambiar manualmente el orden.

## <a name="define-dimension-hierarchies-for-reporting"></a>Definir las jerarquías de dimensiones para notificaciones

Las jerarquías de dimensiones son importantes para las notificaciones. Le permiten definir la estructura específica que encaja en la organización individual. Las agregaciones realizadas en el nodo de la jerarquía de dimensiones permiten a las partes interesadas a cualquier nivel de la organización ver cualquier nivel.

Las jerarquías de dimensiones están disponibles en las herramientas de notificación siguientes. Este enfoque garantiza la coherencia en la estructura de informes.

- Espacio de trabajo **Control de costes** (cliente):

    - Controlado por la configuración

- Espacio de trabajo **Control de costes** (aplicación móvil):

    - Controlado por la configuración

- Excel

    - Proporciona la opción para seleccionar las jerarquías de dimensiones por definición de exportación:

        - Una jerarquía de dimensiones de elementos de coste (obligatorio)
        - Una jerarquía de dimensiones de objetos de coste (opcional)
        - Una jerarquía de dimensiones estadística (opcional)

- Power BI:

    - Todas las jerarquías de dimensión están disponibles.
    
Si crea informes mediante Excel o Power BI, solo los primeros 15 niveles de las jerarquías de dimensiones se exportan. Esta limitación existe porque se requiera un esquema fijo en Excel y Power BI. Si una jerarquía tiene más de 15 niveles, los niveles adicionales no se exportan. La tabla normalizada contiene un registro para cada miembro de la dimensión en la jerarquía. Por lo tanto, se produce la agregación automatizada. Este comportamiento ayuda a garantizar que los saldos de los niveles 15 disponibles en la jerarquía sean aún así correctos.

El siguiente ejemplo muestra el aspecto de una jerarquía de dimensiones en la estructura de informes.

| Jerarquía de dimensión de objeto de coste - Nivel 1 | Jerarquía de dimensión de objeto de coste - Nivel 2 | Jerarquía de dimensión de objeto de coste - Nivel 3 | Jerarquía de dimensión de objeto de coste - Nivel 4 | Jerarquía de dimensión de objeto de coste - Nivel 15 |
|-------------------------------------------|-------------------------------------------|-------------------------------------------|-------------------------------------------|--------------------------------------------|
| Organización                              | Administrador                                     | Finanzas                                   | CC002                                     |                                            |
| Organización                              | Administrador                                     | Finanzas                                   | CC003                                     |                                            |
| Organización                              | Administrador                                     | Finanzas                                   | CC007                                     |                                            |
| Organización                              | Administrador                                     | RR. HH.                                        | CC001                                     |                                            |
| Organización                              | Producción                                | Empaquetado                                 | CC005                                     |                                            |
| Organización                              | Producción                                | Ensamblado                                  | CC006                                     |                                            |

### <a name="update-the-dimension-hierarchies-that-are-used-for-reporting"></a>Actualizar las jerarquías de dimensiones que se usan para informes 

Con el tiempo, las jerarquías de dimensiones que se usan en las herramientas de informes anteriormente indicadas tendrán que actualizarse. Puede actualizar jerarquías de dimensiones actualizando el cliente.

- Espacio de trabajo **Control de costes** (cliente)
- Espacio de trabajo **Control de costes** (aplicación móvil)

Las actualizaciones de las jerarquías de dimensiones se seleccionan cada 24 horas mediante un trabajo almacenado en memoria caché previamente. Una vez que se actualicen los datos exportados, las jerarquías de dimensiones actualizadas estarán disponibles en las siguientes herramientas:

- Excel
- Power BI

> [!NOTE] 
> Para activar manualmente una actualización de la memoria caché de la jerarquía de dimensiones, puede crear una nueva exportación a Excel para la jerarquía de dimensiones o jerarquías que se van a actualizar.

## <a name="define-dimension-hierarchies-for-cost-policies"></a>Definir las jerarquías de dimensiones para directivas de costes

La contabilidad de costes consta de varias directivas donde se definen reglas detalladas. Debe definir una o varias jerarquías de dimensiones para las directivas siguientes:

- Comportamiento de costes
- Distribución de costes
- Asignación de costes
- Acumulación de costes

Las jerarquías de dimensiones hacen que sea sencillo crear reglas. Para evitar tener que crear reglas para cada miembro de la dimensión, puede aprovechar las agregaciones de los miembros de las dimensiones que suministran por niveles de la jerarquía de dimensiones. Si tiene reglas que se solapan, debe definir reglas específicas que el sistema tendrá en cuenta cuando realice el cálculo de gastos generales.

### <a name="example-define-a-cost-behavior-policy"></a>Ejemplo: Definir una directiva de comportamiento de costes

Se crea una nueva directiva de comportamiento de costes y las jerarquías de dimensiones adecuadas se asignan a la directiva, como se muestra aquí.

**Directiva de comportamiento de costes**

| Nombre de directiva   | Jerarquía de dimensión de elemento de coste | Jerarquía de dimensión de objeto de coste | Divisa de contabilidad |
|---------------|----------------------------------|---------------------------------|---------------------|
| Comportamiento de costes | Comportamiento de costes                    | Organización                    | USD                 |

**Reglas**

| Nodo de jerarquía de dimensión de elemento de coste | Nodo de jerarquía de dimensión de objeto de coste | Porcentaje fijo | Importe fijo | Válido desde | Válido hasta |
|---------------------------------------|--------------------------------------|------------------|--------------|------------|----------|
| Coste fijo                            | Organización                         | 100,00           | 0,00         | 1/1/2017   | Nunca    |
| 10001                                 | Organización                         | 0,00             | 150,00       | 1/1/2017   | Nunca    |
| 10001 (\*)                             | Finanzas                              |                  | 50,00        | 1/1/2017   | Nunca    |
| Comportamiento de costes o coste variable (\*\*)   | Organización                         | 0,00             | 0,00         | 1/1/2017   | Nunca    |

\* El nodo de coste variable no es necesario. Si un coste no se clasifica como coste fijo, debe ser un coste variable.

\*\* Una regla detallada se crea para la combinación de miembro de elemento de coste 10001 y todos los miembros de objeto de coste que se agregan en el nivel de la jerarquía de las finanzas (CC002, CC003, CC007).

Las reglas precedentes muestran la flexibilidad que ofrecen las jerarquías de dimensiones. Al definir reglas de alto nivel, puede ayudar a minimizar el mantenimiento. Puede definir reglas detalladas para que se ajusten a un objetivo empresarial específico.

Si se actualizan las jerarquías de dimensiones que se usan en las reglas, el sistema muestra automáticamente las actualizaciones.

Si un nivel de granularidad en las reglas no se requiere más, la regla puede vencer.

Por ejemplo, una regla específica del comportamiento de coste para el nodo de la jerarquía de dimensiones de objetos de coste de finanzas ya no es necesaria. En este caso, haga clic en **Vencimiento de regla** para hacer que la regla venza.

| Nodo de jerarquía de dimensión de elemento de coste | Nodo de jerarquía de dimensión de objeto de coste | Porcentaje fijo | Importe fijo | Válido desde | Válido hasta  |
|---------------------------------------|--------------------------------------|------------------|--------------|------------|-----------|
| Coste fijo                            | Organización                         | 100,00           | 0.00         | 1/1/2017   | Nunca     |
| 10001                                 | Organización                         | 0.00             | 150,00       | 1/1/2017   | Nunca     |
| 10001                                 | Finanzas                              |                  | 50,00        | 1/1/2017   | 20/1/2017 |
| Comportamiento de costes o coste variable        | Organización                         | 0.00             | 0.00         | 1/1/2017   | Nunca     |

Cualquier cálculo de gastos generales que se ejecute después del 20 de enero de 2017, no considera más esta regla.

> [!NOTE] 
> Los campos **Válido desde** y **Válido hasta** son fechas y horas con vigencia Puede vencer la regla y ejecutar un nuevo cálculo de gastos generales en el mismo día.

## <a name="define-dimension-hierarchies-for-security-setup"></a>Definir las jerarquías de dimensiones para configurar la seguridad

Los datos de la contabilidad de costes se deben poner a disposición de todos los administradores responsables de una unidad de notificación. En terminología de contabilidad de costes, una unidad de notificación se representa como un objeto de coste o conjunto de objetos de coste.

Potencialmente, todos los administradores podrán tener acceso a datos empresariales confidenciales, como los ingresos y los márgenes. Por lo tanto, es importante que configure la seguridad, de modo que los administradores solo vean los datos que les resulten relevantes. Para ayudar a controlar la seguridad de los datos, defina las jerarquías de dimensiones.

- El uso de jerarquías de dimensiones se aplica solo si el valor de la< dimensión seleccionado en la referencia de la jerarquía de dimensiones es un objeto de costes.
- Solo una jerarquía de dimensiones se puede habilitar por dimensión de objeto de coste en la jerarquía de la lista de acceso.

**Detalles de jerarquía de dimensión**

| Nombre de jerarquía de dimensión | Dimensión    | Nombre de tipo de jerarquía de dimensión      | Jerarquía de listas de acceso |
|--------------------------|--------------|------------------------------------|-----------------------|
| Organización             | Centros de coste | Jerarquía de clasificación de dimensiones | **Sí**               |

Un nuevo FastTab **Usuarios** está disponible en el diseñador de jerarquías. Aquí, puede insertar uno o más identificadores de usuarios en cada nodo de la jerarquía.

|                 | Usuarios            | Intervalos de miembros de dimensión   |                         |
|-----------------|------------------|---------------------------|-------------------------|
| **Nodos**       | **Id. de usuario**      | **Desde miembro de dimensión** | **Hasta miembro de dimensión** |
| Organización    | Benjamin, Claire |                           |                         |
| &nbsp;&nbsp;Administrador         | Abril            |                           |                         |
| &nbsp;&nbsp;&nbsp;&nbsp;Finanzas   | Alicia           | CC002                     | CC003                   |
|                 |                  | CC007                     | CC007                   |
| &nbsp;&nbsp;&nbsp;&nbsp;RR. HH.        | Arnie            | CC001                     | CC001                   |
| &nbsp;&nbsp;Producción    | David            |                           |                         |
| &nbsp;&nbsp;&nbsp;&nbsp;Empaquetado | Ellen            | CC005                     | CC005                   |
| &nbsp;&nbsp;&nbsp;&nbsp;Ensamblado  | Chris            | CC006                     | CC006                   |

> [!NOTE] 
> Los contables de coste debe asignarse al nivel superior de la jerarquía, de modo que puedan ver todas las entradas de contabilidad de costes.

Para habilitar la jerarquía de la lista de acceso y sus configuraciones de seguridad, vaya a **Contabilidad de costes** > **Configuración** > **Parámetros** > **General**. Seleccione el parámetro **Habilitar acceso de visualización para los miembros de dimensión de objeto de coste**

Los valores para la jerarquía de listas de acceso se utilizan para controlar los datos que se muestran en siguientes áreas:

- Espacio de trabajo **Control de costes** (cliente):

    - Los datos de los formularios que se usan para explorar las situaciones

- Espacio de trabajo **Control de costes** (aplicación móvil):

    - Saldos en tarjetas

- Power BI:

    - Datos que se muestran en las visualizaciones de Power BI
    - Visualización de los datos de Power BI que se insertarán en el cliente de Microsoft Dynamics 365 for Finance and Operations

> [!NOTE] 
> - Antes de que la jerarquía de listas de acceso pueda afectar a los datos de Power BI, se deben emparejar la jerarquía de listas de acceso y la seguridad en Power BI. Para obtener más información, consulte [Configurar la seguridad del paquete del contenido de contabilidad de costes](../../dev-itpro/analytics/setup-security-cost-accounting-content-pack.md).
> - La jerarquía de la lista de acceso no ayuda a proteger la exportación de datos a Excel. Por lo tanto, esa herramienta de informes solo se debe usar por contables y administradores de costes que deban tener acceso completo para ver los datos.
