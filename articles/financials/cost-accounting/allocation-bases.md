---
title: "Bases de asignación"
description: "Este tema proporciona información sobre las bases de asignación. Las bases de asignación son componentes principales en contabilidad de costes y se usan principalmente para asignar costes generales."
author: AndersGirke
manager: AnnBe
ms.date: 05/24/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: CAMDimensionMember
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Core, Operations
ms.custom: 223174
ms.assetid: 
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: yuyus
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: 63f39a6c06a0c6b5df901f7aa4235aab3c4ac06e
ms.contentlocale: es-es
ms.lasthandoff: 11/03/2017

---

# <a name="allocation-bases"></a>Bases de asignación 

[!INCLUDE [banner](../includes/banner.md)]

Una base de asignación es la base sobre la que la contabilidad de costes asigna costes generales. Una base de asignación puede ser una cantidad, como las horas de maquinaria que se usan, horas de kilovatio (kWh) consumidas o los metros cuadrado que se ocupan. Las bases de asignación se usan principalmente para asignar costes generales al inventario que va a producir. Por ejemplo, un departamento de TI asigna los gastos según el número de equipos que utilice cada departamento.

Hay tres tipos de bases de asignación en la contabilidad de costes:

- Bases de asignación de miembros de dimensión predefinida
- Bases de asignación de la jerarquía
- Bases de asignación de la fórmula

## <a name="predefined-dimension-member-allocation-bases"></a>Bases de asignación de miembros de dimensión predefinida

Las bases de asignación de miembro de dimensión predefinida se crean automáticamente cuando se crea un miembro de dimensión de los siguientes tipos:

- Miembros de dimensión estadística
- Miembros de dimensión de elemento de coste

> [!NOTE]
> Las bases de asignación de miembro de dimensión predefinida que se basan en un miembro de dimensión de elemento de coste consideran solo los valores del proveedor del origen de datos, como la contabilidad general o el presupuesto.

### <a name="example-1-use-a-cost-element-dimension-member-as-the-allocation-base"></a>Ejemplo 1: Use un miembro de dimensión de elemento de coste como base de la asignación
Este ejemplo muestra cómo crear una regla de asignación de costes para asignar el elemento de coste 10002 (seguro del empleado) al saldo que se registra en el elemento de coste 10001 (salarios). La regla de asignación se define en función de la proporción de salarios de cada departamento con respecto a los salarios totales. (¡Es necesario revisar!)

En la contabilidad general, el plan de cuentas se define como sigue.

| Plan contable | Cuenta principal | Descripción        | Tipo de cuenta principal |
|------------------|--------------|--------------------|-------------------|
| Compartido           | 10001        | Salarios           | Gastos           |
| Compartido           | 10002        | Seguro de empleado | Gastos           |

Define una dimensión de elemento de coste y configura el conector de datos. Una vez se hayan importado los datos, las entradas siguientes se crean en la contabilidad de costes.

**Miembros de dimensión de elemento de coste**

| Nombre de la dimensión de elemento de coste | Elemento de coste |  Descripción       | Tipo    |
|-----------------------------|--------------|--------------------|---------|
| Elementos de coste               | 10001        | Salarios           | Principal |
| Elementos de coste               | 10002        | Seguro de empleado | Principal |

**Bases de asignación de miembros de dimensión predefinida** 

| Nombre  | Descripción        | Dimensión de elemento de coste |
|-------|--------------------|------------------------|
| 10001 | Salarios           | Elementos de coste          |
| 10002 | Seguro de empleado | Elementos de coste          |

En la contabilidad general, se han registrado las entradas siguientes:

- Las entradas que muestran la cuenta principal de salarios provienen de sistema de nóminas y se envían a los centros de coste.
- El gasto para el seguro de empleados se registra manualmente a un centro de coste predeterminado.

| Fecha contable | Centro de coste |  Descripción        | Cuenta principal |  Descripción       | Importe en la divisa de contabilidad |
|-----------------|-------------|---------------------|--------------|--------------------|-------------------------------|
| 03-01-2017      | CC001       | RR. HH.                  | 10001        | Salarios           | 2.000,00                      |
| 03-01-2017      | CC002       | FI                  | 10001        | Salarios           | 5.000,00                      |
| 03-01-2017      | CC003       | TI                  | 10001        | Salarios           | 3.000,00                      |
| 03-01-2017      | CC099       | Centro de coste predeterminado | 10002        | Seguro de empleado | 1.000,00                      |

Una vez se hayan procesado los datos de origen de la contabilidad general, las entradas siguientes se crean en la contabilidad de costes.

**Entradas de costes**

| Objeto de coste |  Descripción        | Elemento de coste  |  Descripción       | Comportamiento de costes   |Importe|Fecha contable|
|-------------|---------------------|---------------|--------------------|-----------------|------|---------------|
| CC001       | RR. HH.                  | 10001         | Salarios           | Sin clasificar    |2.000,00|  03-01-2017    |
| CC002       | FI                  | 10001         | Salarios           | Sin clasificar    |5.000,00|     03-01-2017         |
| CC003       | TI                  | 10001         | Salarios           | Sin clasificar    |3.000,00|      03-01-2017        |
| CC099       | Centro de coste predeterminado | 10002         | Seguro de empleado | Sin clasificar    |1.000,00|      03-01-2017       |

Este ejemplo simplificado, se crea una regla de asignación de costes para asignar el elemento de coste 10002 (seguro del empleado) relativo al saldo que se registra en el elemento de coste 10001 (salarios).

**Regla de distribución de costes**

| Nodo de jerarquía de dimensión de objeto de coste | Nodo de jerarquía de dimensión de elemento de coste | Comportamiento de costes | Base de asignación |
|--------------------------------------|---------------------------------------|---------------|-----------------|
| CC099                                | 10002                                 | Sin clasificar  | 10001           |

**Realizar cálculo de costes generales**

Una vez que el elemento de coste 10001 (salarios) se aplique como base de asignación, el resultado del cálculo de gastos generales es como sigue.

| Objeto de coste | Descripción | Magnitud |   Factor de asignación         | Importe |
|-------------|-------------|-----------|-----------------------------|--------|
| CC001       | RR. HH.          | 2.000     | (2000 ÷ 10 000) × 1000,00 | 200,00 |
| CC002       | FI          | 5.000     | (5000 ÷ 10 000) × 1000,00 | 500,00 |
| CC003       | TI          | 3.000     | (3000 ÷ 10 000) × 1000,00 | 300,00 |

**Diario**

| Diario | Tipo de diario                          | Período de calendario fiscal | Año | Período   | Versión                                                                 |
|---------|---------------------------------------|------------------------|------|----------|-------------------------------------------------------------------------|
| 00001   | Diario de cálculo de la distribución de costes | Fiscal                 | 2017 | Período 1 | Cálculo de costes generales/ 01-02-2017 11:51:00 PM/Contabilidad/2017/Período 1 |

**Movimientos de diario para saldo de objeto de costes**

| Fecha contable | Objeto de coste | Descripción         | Elemento de coste | Descripción        | Comportamiento de costes |  Importe  |
|-----------------|-------------|---------------------|--------------|--------------------|---------------|----------|
| 31-01-2017      | CC099       | Centro de coste predeterminado | 10002        | Seguro de empleado | Sin clasificar  | 1.000,00 |

**Entradas de costes**

| Objeto de coste |  Descripción        | Elemento de coste |    Descripción     | Comportamiento de costes | Importe    | Fecha contable |
|-------------|---------------------|--------------|--------------------|---------------|-----------|-----------------|
| CC099       | Centro de coste predeterminado | 10002        | Seguro de empleado | Sin clasificar  | -1.000,00 | 31-01-2017      |
| CC001       | RR. HH.                  | 10002        | Seguro de empleado | Sin clasificar  | 200,00    | 31-01-2017      |
| CC002       | FI                  | 10002        | Seguro de empleado | Sin clasificar  | 500,00    | 31-01-2017      |
| CC099       | TI                  | 10002        | Seguro de empleado | Sin clasificar  | 300,00    | 31-01-2017      |

### <a name="example-2-use-a-statistical-dimension-member-as-the-allocation-base"></a>Ejemplo 2: Use un miembro de dimensión estadística como base de la asignación

Los miembros de la dimensión estadística se pueden usar como bases de asignación para definir directivas o para notificar el consumo no monetario de los objetos de coste. Puede crear manualmente miembros de dimensión estadística o importarlos desde un archivo utilizando la herramienta de importación o exportación de administración de datos.

**Miembros de dimensión estadística**

| Nombre de la dimensión estadística | Elemento estadístico | Descripción               | Unidad |
|----------------------------|---------------------|---------------------------|------|
| Elementos estadísticos       | EJC                 | Empleados a jornada completa       | c/u   |
| Elementos estadísticos       | Electricidad         | Consumo de electricidad   | kWh  |

Cuando se guarda un miembro de dimensión estadística, se crea un registro correspondiente en las bases de asignación de miembro de dimensión predefinida.

**Bases de asignación de miembros de dimensión predefinida**

| Nombre        | Descripción             | Dimensión de elemento estadístico |
|-------------|-------------------------|-------------------------------|
| EJC         | Empleados a jornada completa     | Elementos estadísticos          |
| Electricidad | Consumo de electricidad | Elementos estadísticos          |

Las medidas estadísticas pueden provenir de varios orígenes:

- El consumo eléctrico se puede medir con los contadores instalados en las distintas áreas de la empresa.
- Las tablas contienen medidas estadísticas. Por ejemplo, la tabla de HcmEmployment contiene una lista de todos los empleados y los centros de coste para los que trabajan.

| Nombre       | Centro de coste |  Descripción  | Tipo de trabajador |
|------------|-------------|----|-------------|
| Empleado A | CC001       | RR. HH. | Empleado    |
| Empleado B | CC002       | FI | Empleado    |
| Empleado C | CC002       | FI | Empleado    |
| Empleado D | CC003       | TI | Empleado    |
| Empleado F | CC003       | TI | Empleado    |

> [!NOTE]
> Todas las tablas que contienen dimensiones financieras se pueden usar como orígenes para medidas estadísticas.

La contabilidad de costes admite una recopilación de medidas estadísticas mediante las conexiones de datos siguientes:

- Herramienta de importación o exportación de la administración de datos
- Medidas estadísticas

Para extraer medidas estadísticas del sistema, se requiere una plantilla de proveedor de medidas estadísticas. Para obtener más información, vea la plantilla de proveedor de medidas estadísticas (Se agregará un vínculo una vez que se escriba este tema.)

**Plantillas de proveedor de medidas estadísticas**

| Nombre  | Función | Tabla de origen  | Campo de suma      | Campo Fecha     |
|-------|----------|---------------|----------------|----------------|
| EJC | Cuenta    | HcmEmployment | No aplicable | No aplicable |

Una vez se hayan procesado los datos de origen de la medida estadística, las entradas siguientes se crearán en la contabilidad de costes.

**Entradas estadísticas**

| Objeto de coste | Descripción      | Fecha contable | Miembro de dimensión estadística | Descripción         | Magnitud |
|-------------|------------------|-----------------|------------------------------|---------------------|-----------|
| CC001       | RR. HH.               | 31-01-2017      | EJC                        | Empleados a jornada completa | 1,00      |
| CC002       | FI               | 31-01-2017      | EJC                        | Empleados a jornada completa | 2.00      |
| CC003       | TI               | 31-01-2017      | EJC                        | Empleados a jornada completa | 2.00      |

A continuación se muestra un ejemplo de una regla de distribución de costes cuando la base de asignación de miembro de la dimensión predefinida del EJC se asigna a la base de asignación que contiene.

| Objeto de coste | Descripción  | Magnitud | Factor de asignación |
|-------------|------|-----------|-------------------|
| CC001       | RR. HH.   | 1,00      | (1/5) × Importe    |
| CC002       | FI   | 2.00      | (2/5) × Importe    |
| CC003       | TI   | 2.00      | (2/5) × Importe    |

Puede usar la entidad de datos de medidas estadísticas importada para importar las medidas estadísticas a la contabilidad de costes. También puede usar la herramienta de importación o exportación de administración de datos. En Excel, el consumo de la electricidad se registra el modo siguiente.

| Fecha contable | Miembro de dimensión | Magnitud | Identificador de origen |
|-----------------|------------------|-----------|-------------------|
| 31-01-2017      | CC001            | 2,450.00  | Electricidad       |
| 31/1/17      | CC002            | 4,100.00  | Electricidad       |
| 31-01-2017      | CC003            | 15.000,00 | Electricidad       |

Una vez se hayan procesado los datos de origen de la medida estadística, las entradas siguientes se crearán en la contabilidad de costes.

**Entradas estadísticas**

| Objeto de coste |    | Fecha contable | Miembro de dimensión estadística |    Descripción          | Magnitud |
|-------------|----|-----------------|------------------------------|-------------------------|-----------|
| CC001       | RR. HH. | 31/1/17      | Electricidad                  | Consumo de electricidad | 2,450.00  |
| CC002       | FI | 31/1/17      | Electricidad                  | Consumo de electricidad | 4,100.00  |
| CC003       | TI | 31-01-2017      | Electricidad                  | Consumo de electricidad | 15.000,00 |

A continuación se muestra un ejemplo de una regla de distribución de costes cuando la base de asignación de miembro de la dimensión predefinida de electricidad se asigna a la base de asignación que contiene.

| Objeto de coste | Descripción  | Magnitud | Factor de asignación          |
|-------------|------|-----------|----------------------------|
| CC001       | RR. HH.   | 2,450.00  | (2450 ÷ 21 550) × Importe  |
| CC002       | FI   | 4,100.00  | (4100 ÷ 21 550) × Importe  |
| CC003       | TI   | 15.000,00 | (15 000 ÷ 21 550) × Importe |

## <a name="hierarchy-allocation-bases"></a>Bases de asignación de la jerarquía

Los contables de coste pueden crear manualmente las bases de asignación de la jerarquía aplicando un nodo de jerarquía de dimensiones de objeto de coste a una base de asignación existente. De esta manera, puede limitar el intervalo de la base de asignación del miembro de la dimensión predefinida original. Una base de asignación de miembro de dimensión predefinida se puede usar para crear varias bases de asignación de la jerarquía. Los intervalos se pueden mantener en la jerarquía de dimensión del objeto de coste que está asociado a las bases de asignación de la jerarquía.

### <a name="example-hierarchy-allocation-bases-that-are-based-on-full-time-employees-in-the-organization"></a>Ejemplo: bases de asignación de la jerarquía que se basan en empleados a jornada completa en la organización
A continuación se muestra un ejemplo de una jerarquía de dimensiones de objetos de coste que se puede crear para describir una organización simplificada.

| Nombre de jerarquía | Nivel de nodo 0 | Nivel de nodo 1 | Nivel de nodo 2 | Miembros de dimensión |
|----------------|--------------|--------------|--------------|-------------------|
| Organización   | Directora financiera          | CFO          | FICO         | CC001             |
| Organización   | Directora financiera          | CFO          | RR. HH.           | CC002             |
| Organización   | Directora financiera          | CIO          | TI           | CC003             |

La base de asignación de miembro de la dimensión predefinida de EJC que se creó en la sección anterior contiene las entradas siguientes.

**Entradas estadísticas**

| Objeto de coste | Descripción  | Fecha contable | Miembro de dimensión estadística | Descripción | Magnitud |
|-------------|------|-----------------|------------------------------|---------------------|-----------|
| CC001       | RR. HH.   | 31-01-2017      | EJC                        | Empleados a jornada completa | 1,00      |
| CC002       | FI   | 31-01-2017      | EJC                        | Empleados a jornada completa | 2.00      |
| CC003       | TI   | 31-01-2017      | EJC                        | Empleados a jornada completa | 2.00      |

Se debe distribuir un coste entre los centros de coste responsables ante el director financiero (CFO) de la organización. Se ha confirmado que la proporción correcta de asignación es el número de empleados a jornada completa (EJC) por centro de coste.

**Bases de asignación de la jerarquía**

| Nombre                  | Base de asignación | Jerarquía de dimensión de objeto de coste | Nodo de jerarquía de dimensión de objeto de coste |
|-----------------------|-----------------|---------------------------------|--------------------------------------|
| Número de EJC en CFO | EJC           | Organización                    | CFO                                  |

La función de vista previa le permite validar la base de asignación de la jerarquía creada, en función de las entradas estadísticas en el sistema.

**Detalles de base de asignación**

| Objeto de coste | Descripción  |  Magnitud |
|-------------|------|------------|
| CC001       | RR. HH.   | 1,00       |
| CC002       | FI   | 2.00       |

A continuación se muestra un ejemplo de una regla de distribución de costes cuando el número de EJC en la base de asignación de la jerarquía del CFO se asigna a la base de asignación que contiene.

| Objeto de coste | Descripción  | Magnitud | Factor de asignación |
|-------------|------|-----------|-------------------|
| CC001       | RR. HH.   | 1,00      | (1/3) × Importe    |
| CC002       | FI   | 2.00      | (2/3) × Importe    |

## <a name="formula-allocation-bases"></a>Bases de asignación de la fórmula

Las bases de asignación de fórmulas le permiten definir fórmulas avanzadas para lograr la base de asignación correcta. Puede crear manualmente las bases de asignación de fórmulas.

Al crear una base de asignación de la fórmulas, puede seleccionar la dimensión estadística y la dimensión de elementos coste debe ser la base para la fórmula. Todas las bases de asignación que se obtienen de las dimensiones previamente seleccionados se pueden usar en una base de asignación de la fórmula.

> [!NOTE]
> Las bases de asignación definida de fórmulas definidas anteriormente se pueden usar para definir una nueva base de la asignación de fórmulas.

En los factores de la base de asignación de fórmulas, cree un alias y asócielo a una base de asignación o a una constante. Los alias se utilizan para definir la fórmula.

Puede usar los siguientes operadores para definir su fórmula.

| Símbolos | Texto           |
|---------|----------------|
| ( )     | Paréntesis    |
| \<      | Más pequeño que   |
| \>      | Más grande que    |
| +       | Adición       |
| –       | Resta    |
| \*      | Multiplicación |

No se admiten las instrucciones tradicionales **SI**. Sin embargo, puede crear instrucciones y validarlas si son verdaderas.

| Instrucción | Validación | Resultado |
|-----------|------------|--------|
| a \> b    | VERDADERO       | 1      |
| a \> b    | FALSO      | 0      |

### <a name="example-1-a-simple-formula"></a>Ejemplo 1: Una fórmula simple

Las cuentas de electricidad suelen constar de dos partes:

- Una cuota fija para conectarla a la cuadrícula
- Coste que está asociado al consumo por la kWh

La base de asignación de miembro de la dimensión predefinida de electricidad ya se ha definido y contiene estos valores.

**Entradas estadísticas**

| Objeto de coste | Nombre | Fecha contable | Miembro de dimensión estadística | Descripción             | Magnitud |
|-------------|------|-----------------|------------------------------|-------------------------|-----------|
| CC001       | RR. HH.   | 31/1/17      | Electricidad                  | Consumo de electricidad | 2,450.00  |
| CC002       | FI   | 31/1/17      | Electricidad                  | Consumo de electricidad | 4,100.00  |
| CC003       | TI   | 31-01-2017      | Electricidad                  | Consumo de electricidad | 15.000,00 |

Si la cuota fija se debe expandir ahora de forma uniforme sobre los objetos que consumen la electricidad, tiene dos opciones para asignar los costes:

- Cree una nueva base predefinida de asignación, con electricidad corregida, y después aplique una medida estadística de 1,00 para cada objeto de coste que consumió electricidad.
- Crear una base de la asignación de fórmulas, con electricidad corregida, que aproveche la base de asignación predefinida de electricidad que ya se definió en el sistema. La ventaja de esta opción es que los datos deben cargarse en la contabilidad del costes tan solo para un miembro de dimensión estadística de electricidad.

**Base de asignación de la fórmula** 

| Nombre              | Dimensión de elemento de coste | Dimensión estadística | Fórmula |
|-------------------|------------------------|-----------------------|---------|
| Electricidad corregida |                        | Elementos estadísticos  |         |

Antes de que el campo **Fórmula** se pueda rellenar, debe especificar el alias que se usará en la fórmula.

**Fórmula - Factores de la base de asignación**

| Alias | Constante | Base de asignación |
|-------|----------|-----------------|
| un     |          | Electricidad     |
| b     | 0,01     |                 |

Tenga en cuenta que 0 (cero) no está admitido como constante.

**Base de asignación de la fórmula**

| Nombre              | Dimensión de elemento de coste | Dimensión estadística | Fórmula |
|-------------------|------------------------|-----------------------|---------|
| Electricidad corregida |                        | Elementos estadísticos  | a \> b  |

La función de vista previa le permite validar la base de asignación de fórmulas creada, en función de las entradas estadísticas en el sistema.

**Detalles de base de asignación**

| Objeto de coste | Descripción  | Fórmula           | Magnitud |
|-------------|------|-------------------|-----------|
| CC001       | RR. HH.   | 2.450,00 \> 0,01  | 1,00      |
| CC002       | FI   | 4.100,00 \> 0,01  | 1,00      |
| CC003       | TI   | 15.000,00 \> 0,01 | 1,00      |

A continuación se muestra un ejemplo de una regla de distribución de costes cuando la base de asignación la fórmula de electricidad se asigna a la base de asignación que contiene.

**Factor de asignación de magnitud de objeto de coste**

| Objeto de coste | Nombre | Magnitud |  Factor de asignación |
|-------------|------|-----------|--------------------|
| CC001       | RR. HH.   | 1,00      | (1/3) × Importe     |
| CC002       | FI   | 1,00      | (1/3) × Importe     |
| CC003       | TI   | 1,00      | (1/3) × Importe     |

### <a name="example-2-an-advanced-formula"></a>Ejemplo 2: Una fórmula avanzada
Para este ejemplo, el coste de la electricidad no debe seguir solamente la electricidad real que se consume en kWh. La dirección desea incorporar incentivos para hacer disminuir el uso de electricidad. 

| Regla              | Índice | 
|-------------------|------|
| a <= 10 000,00 kWh | 0.75 |
| a > 10 000,00 kWh  | 1.15 |

Se crea una nueva base de asignación de fórmulas (uso de electricidad).

**Base de asignación de la fórmula**

| Nombre              | Dimensión de elemento de coste | Dimensión estadística | Fórmula |
|-------------------|------------------------|-----------------------|---------|
| Uso de electricidad |                        | Elementos estadísticos  |         |

Antes de que el campo **Fórmula** se pueda rellenar, debe especificar el alias que se usará en la fórmula.

**Fórmula - Factores de la base de asignación**

| Alias | Constante  | Base de asignación |
|-------|-----------|-----------------|
| un     |           | Electricidad     |
| b     | 10.000,00 |                 |
| c     | 0.75      |                 |
| d     | 1.15      |                 |

**Base de asignación de la fórmula**

| Nombre              | Dimensión de elemento de coste | Dimensión estadística | Fórmula                                                    |
|-------------------|------------------------|-----------------------|------------------------------------------------------------|
| Electricidad corregida |                        | Elementos estadísticos  | ((a \> b) × ((b × c) + (a – b) × d)) + ((a \<= b] × a × c) |

La función de vista previa le permite validar la base de asignación de fórmulas creada, en función de las entradas estadísticas en el sistema.

**Detalles de base de asignación**

| Objeto de coste |    | Fórmula                                                                                                                             | Magnitud |
|-------------|----|-------------------------------------------------------------------------------------------------------------------------------------|-----------|
| CC001       | RR. HH. | ((2450,00 \> 10 000,00) × ((10 000,00 × 0,75) + (2 450,00 – 10 000,00) × 1,15)) + ((2 450,00 \<= 10 000,00) × 2 450,00 × 0,75)     | 1,837.50  |
| CC002       | FI | ((4100,00 \> 10 000,00) × ((10 000,00 × 0,75) + (4100,00 – 10 000,00) × 1,15)) + ((4100,00 \<= 10 000,00) × 4100,00 × 0,75)     | 3,075.00  |
| CC003       | TI | ((15 000,00 \> 10 000,00) × ((10 000,00 × 0,75) + (15 000,00 – 10 000,00) × 1,15)) + ((15 000,00 \<= 10 000,00) × 15 000,00 × 0,75) | 1,3250.00 |

A continuación ofrecen más detalles de la fórmula para CC003 (TI):

((15 000,00 \> 10 000,00) × ((10 000,00 × 0,75) + (15 000,00 – 10 000,00) × 1,15)) + ((15 000,00 \<= 10 000,00) × 15 000,00 × 0,75) = 13 250,00

(1 × (7 500,00 + 5 000,00 × 1,15)) + (0 × 15 000,00 × 0,75)            

1 × 7 500,00 + 5 750,00 + 0 

A continuación se muestra un ejemplo de una regla de distribución de costes cuando la base de asignación la fórmula de electricidad corregida se asigna a la base de asignación que contiene.


| Objeto de coste | Descripción | Magnitud |        Factor de asignación         |
|-------------|-------------|-----------|----------------------------------|
|    CC001    |     RR. HH.      | 1,837.50  | (1 837,50 ÷ 18 162,50) × Importe  |
|    CC002    |     FI      | 3,075.00  | (3075,00 ÷ 18162,50) × Importe  |
|    CC003    |     TI      | 13,250.00 | (13 250,00 ÷ 18 162,50) × Importe |


