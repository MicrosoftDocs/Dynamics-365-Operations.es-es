---
title: "Directiva de acumulación de costes y cálculo de costes generales"
description: "Este tema proporciona información sobre cómo determinar el nivel correcto de elementos de coste secundarios y crear reglas de acumulación que se ajusten a los informes de la organización y la rastreabilidad de costes."
author: AndersGirke
manager: AnnBe
ms.date: 06/16/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: CAMCostRollupRule, CAMDimensionHierarchy
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Core, Operations
ms.custom: 
ms.assetid: 
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: yuyus
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: 044a943eeba91f5dbebd4dcd70bc8152c4109037
ms.contentlocale: es-es
ms.lasthandoff: 11/03/2017

---

# <a name="cost-rollup-policy-and-overhead-calculation"></a>Directiva de acumulación de costes y cálculo de costes generales 

[!INCLUDE [banner](../includes/banner.md)]

La contabilidad de costes permite obtener detalles sobre cómo en el flujo de costes está relacionado con los productos y los servicios que se entregan en una organización. Para ver la transparencia de los costes, es esencial lograr una asignación de costes entre los objetos de coste basada en una base de asignación adecuada. De forma predeterminada, la asignación de costes se consigue para el elemento de costes principal, lo que se desea en algunos casos, pero tiene ciertas implicaciones que deben considerarse.

-   Los objetos de coste auxiliares terminan con un saldo de cero para el elemento de coste principal después del cálculo de gastos generales.

-   El volumen de entradas de coste generado por el cálculo de gastos generales puede ser muy alto.

-   No se puede supervisar el flujo de coste entre los objetos de coste.

Para evitar estas implicaciones, la contabilidad de costes le permite configurar la asignación de costes para se ajuste a los requisitos de generación de informes ejecutivos de la organización. Este tema describe cómo puede determinar el nivel correcto de elementos de coste secundarios y crear reglas de acumulación que se ajusten a los informes de la organización y la rastreabilidad de costes.

> [!NOTE]
> Puede cambiar las configuraciones si cambian los requisitos de los informes.

## <a name="example-of-cost-rollup-policy-setup"></a>Ejemplo de configuración de la directiva de acumulación de costes

Imagine que una organización tiene la siguiente estructura con 4 centros de coste.

![Ejemplo de una estructura de organización](./media/dimension-hierarchy-org.png)

**Dimensión de objeto de coste**

| Centros de coste | Descripción          |
|--------------|-----------|
| CC001        | RR. HH.        |
| CC002        | Finanzas   |
| CC003        | Ensamblado  |
| CC004        | Empaquetado |

**Dimensión de elemento de coste**

| Elementos de coste | Descripción | Tipo    |
|---------------|-------------|---------|
| 1001          | Electricidad | Principal |
| 1002          | Salarios    | Principal |
| 1003          | Publicidad | Principal |

Una jerarquía de dimensión que cumple los requisitos de generación de informes de la organización se puede establecer del modo siguiente.

**Detalles de jerarquía de dimensión**

| Nombre de jerarquía de dimensión | Dimensión    | Nombre de tipo de jerarquía de dimensión      | Jerarquía de listas de acceso |
|--------------------------|--------------|------------------------------------|-----------------------|
| Organización             | Centros de coste | Jerarquía de clasificación de dimensiones | N.º                    |

**Jerarquía de dimensiones**

|              | Intervalos de miembros de dimensión |                     |
|--------------|-------------------------|---------------------|
| **Nodos**        | **Desde miembro de dimensión**   | **Hasta miembro de dimensión** |
| Organización |                         |                     |
| &nbsp;&nbsp;Administrador             |                         |                     |
| &nbsp;&nbsp;&nbsp;&nbsp;Finanzas              | CC001                   | CC001               |
| &nbsp;&nbsp;&nbsp;&nbsp;RR. HH.               | CC002                   | CC002               |
| &nbsp;&nbsp;Producción               |                         |                     |
| &nbsp;&nbsp;&nbsp;&nbsp;Empaquetado              | CC003                   | CC003               |
| &nbsp;&nbsp;&nbsp;&nbsp;Ensamblado             | CC004                   | CC004               |

Una jerarquía de dimensión que cumple los requisitos de la directiva se puede establecer del modo siguiente.

**Detalles de jerarquía de dimensión**

| Nombre de jerarquía de dimensión | Dimensión     | Nombre de tipo de jerarquía de dimensión      |
|--------------------------|---------------|------------------------------------|
| Informe de pérdidas y ganancias  | Elementos de coste | Jerarquía de clasificación de dimensiones |

**Jerarquía de dimensiones**

|                         | Intervalos de miembros de dimensión |                     |
|-------------------------|-------------------------|---------------------|
| Nodos                   | Desde miembro de dimensión   | Hasta miembro de dimensión |
| Informe de pérdidas y ganancias |                         |                     |
| &nbsp;&nbsp;&nbsp;&nbsp;Coste primario                    | 10001                   | 10003               |

Una vez que se procesen las entradas de contabilidad general, el saldo de la entrada de coste según el objeto tiene este aspecto.

|                      | **Objeto de coste** |           |           |           | **Total**     |
|----------------------|-----------------|-----------|-----------|-----------|---------------|
| **Elemento de coste**     | **CC001**       | **CC002** | **CC003** | **CC004** |               |
| **1001 Electricidad** | 100,00          | 200,000    | 6.000,00  | 2.000,00  | **8.300,00**  |
| **1002: Salarios**    | 10.000,00       | 10.000,00 | 8.000,00  | 6.500,00  | **34.500,00** |
| **1003: Publicidad** | 0.00            | 4.000,00  | 0.00      | 0.00      | **4.000,00**  |
|                      | 10.100,00       | 14.200,00 | 14.000,00 | 8.500,00  | **46.800,00** |

**Dimensión estadística**

| Elementos estadísticos |    Descripción   |
|----------------------|------------------|
| SE-1                 | Servicios HR      |
| SE-2                 | Servicios financieros |

El objeto de coste CC001 RR. HH. contribuye a los servicios de RR. HH. para varios objetos de coste.

Los servicios de RR. HH. son consumidos por la siguiente distribución de la magnitud.

| Objeto de coste | Descripción |   Servicios HR |
|-------------|-------------|----|
| CC002       | Finanzas     | 35 |
| CC003       | Ensamblado    | 55 |
| CC004       | Empaquetado   | 10 |

El objeto de coste CC002 Finanzas contribuye a varios objetos de coste.

Los servicios financieros son consumidos por la siguiente distribución de la magnitud.

| Objeto de coste |   Descripción    |  Servicios financieros   |
|-------------|------------------|----|
| CC003       | Ensamblado         | 65 |
| CC004       | Empaquetado        | 35 |

Las directivas de asignación de costes se puede establecer del modo siguiente.

| Nombre de directiva | Descripción     | Jerarquía de dimensión de objeto de coste | Dimensión estadística | Dimensión de elemento de coste |
|-------------|-----------------|---------------------------------|-----------------------|------------------------|
| 2017        | Asignación de costes | Organización                    | Elementos estadísticos  | Elementos de coste          |

Las reglas de asignación de costes se puede establecer del modo siguiente.

| Nodo de jerarquía de dimensión de objeto de coste | Comportamiento de costes | Base de asignación        |
|--------------------------------------|---------------|------------------------|
| CC001                                | Total         | **Servicios RR. HH.**        |
| CC002                                | Total         | **Servicios financieros** |

<a name="brhow-cost-flows-between-cost-centers"></a><br>Cómo el coste fluye entre los centros de coste 
---------------------------------------------------

Si desea obtener información sobre cómo el coste fluye entre los centros de coste de la organización, puede crear elementos de coste del tipo **Secundario** para cada centro de coste. Estos artículos de coste se usarán para transferir los saldos entre los centros de coste durante el cálculo de gastos generales.

Los miembros de la dimensión de elementos de coste se puede establecer del modo siguiente.

| Elementos de coste | Tipo          |               |
|---------------|---------------|---------------|
| 1001          | Electricidad   | Principal       |
| 1002          | Salarios      | Principal       |
| 1003          | Publicidad   | Principal       |
| **SC-CC001**  | **RR. HH.**        | **Secundario** |
| **SC-CC002**  | **Finanzas**   | **Secundario** |
| **SC-CC003**  | **Ensamblado**  | **Secundario** |
| **SC-CC004**  | **Empaquetado** | **Secundario** |

La jerarquía de dimensión **Informe de pérdidas y ganancias** debe actualizarse con los nuevos miembros de dimensión de modo que la jerarquía de dimensiones contenga los datos correctos que se pueden usar para definir el informe de errores y directivas.

**Detalles de jerarquía de dimensión**

| Nombre de jerarquía de dimensión | Dimensión     | Nombre de tipo de jerarquía de dimensión      |
|--------------------------|---------------|------------------------------------|
| Informe de pérdidas y ganancias  | Elementos de coste | Jerarquía de clasificación de dimensiones |

**Jerarquía de dimensiones**

|                         | Intervalos de miembros de dimensión |                     |
|-------------------------|-------------------------|---------------------|
| Nodos                   | Desde miembro de dimensión   | Hasta miembro de dimensión |
| Informe de pérdidas y ganancias |                         |                     |
| &nbsp;&nbsp;&nbsp;&nbsp;Coste primario                        | 10001                   | 10003               |
| &nbsp;&nbsp;&nbsp;&nbsp;Coste secundario                         | **SC-CC001**            | **SC-CC004**        |

Cree una **Directiva de acumulación de costes** donde cada centro de coste se asigne a un elemento de coste correspondiente del tipo **Secundario**.

**Directivas de acumulación de costes**

| Nombre de directiva | Descripción | Jerarquía de dimensión de objeto de coste | Jerarquía de dimensión de elemento de coste |
|-------------|-------------|---------------------------------|----------------------------------|
| 2017        | Flujo de costes   | Organización                    | Informe de pérdidas y ganancias          |

**Reglas de acumulación de costes**

| Nodo de jerarquía de dimensión de objeto de coste | Nodo de jerarquía de dimensión de elemento de coste | Elemento de costes secundario |
|--------------------------------------|---------------------------------------|------------------------|
| CC001                                | Informe de pérdidas y ganancias               | **SC-CC001**           |
| CC002                                | Informe de pérdidas y ganancias               | **SC-CC002**           |
| CC003                                | Informe de pérdidas y ganancias               | **SC-CC003**           |
| CC004                                | Informe de pérdidas y ganancias               | **SC-CC004**           |

## <a name="perform-overhead-calculation"></a>Realizar cálculo de costes generales

**Diario**

| Diario | Tipo de diario            | Período de calendario fiscal | Año | Período | Versión       |
|---------|-------------------------|------------------------|------|--------|---------------|
| 00002   | Diario de asignación de costes | Fiscal                 | 2017    | Período 1 | Cálculo de costes generales/ 01-02-2017 11:51:00 PM/Contabilidad/2017/Período 1 |

El sistema ahora aplicará la **Directiva de acumulación de costes** cuando cree las **Movimientos de diario para saldo de objeto de costes**.

**Movimientos de diario para saldo de objeto de costes**

| Fecha contable | Objeto de coste | Descripción  | Elemento de coste | Descripción |  Importe |
|-----------------|-------------|--------------|----------|-----------|-----------|
| 31-01-2017      | CC001       | RR. HH.           | SC-CC001 | RR. HH.        | 10.100,00 |
| 31-01-2017      | CC002       | Finanzas      | SC-CC002 | Finanzas   | 17.735,00 |
| 31-01-2017      | CC003       | Ensamblado     | SC-CC003 | Ensamblado  | 31.082,75 |
| 31-01-2017      | CC004       | Empaquetado    | SC-CC004 | Empaquetado | 15.717,25 |

> [!NOTE]
> Las entradas del diario se crean en función de las reglas en la **Directiva de acumulación de costes** si existe una directiva. El saldo mostrado es el saldo del cálculo de gastos generales.

La página **Detalles de movimiento de diario de saldo de costes de objetos de costes** a la que se accede a las entradas del diario muestra cómo se obtiene el saldo.

**Ejemplo: El movimiento de diario para el objeto de coste CC002 Finanzas**

**Detalles de movimiento de diario de saldo de costes de objetos de costes**

| Miembro de dimensión de elemento de coste | Descripción |  Importe   |
|-------------------------------|-------------|-----------|
| 1001                          | Electricidad | 200,000    |
| 1002                          | Salarios    | 10.000,00 |
| 1003                          | Publicidad | 4.000,00  |
| SC-CC001                      | RR. HH.          | 3.535,00  |

**Entradas de coste generadas por cálculo de gastos generales**

| Objeto de coste | Descripción  | Elemento de coste   | Descripción  |        Importe     |       Fecha contable     |
|-------------|--------------|----------|-----------------|-------------|------------|
| CC001       | RR. HH.           | SC-CC001 | RR. HH.              | \- 10.100,00 | 31-01-2017 |
| CC002       | Finanzas      | SC-CC001 | RR. HH.              | 3.535,00    | 31-01-2017 |
| CC003       | Ensamblado     | SC-CC001 | RR. HH.              | 5.555,00    | 31-01-2017 |
| CC004       | Empaquetado    | SC-CC001 | RR. HH.              | 1.010,00    | 31-01-2017 |
| CC002       | Finanzas      | SC-CC002 | Finanzas         | \- 17.735,00 | 31-01-2017 |
| CC003       | Ensamblado     | SC-CC002 | Finanzas         | 11.527,75   | 31-01-2017 |
| CC004       | Empaquetado    | SC-CC002 | Finanzas         | 6.207,25    | 31-01-2017 |

Después de que se complete el **Cálculo de costes generales**, puede notificar los resultados mediante herramientas como Microsoft SharePoint Workspace, Excel o Power BI.

## <a name="view-reporting-in-excel"></a>Ver los informes en Excel 

Las jerarquías de dimensión le permiten ver datos en distintos niveles de agregado.

A continuación se muestra un ejemplo de un informe PowerPivot en Excel.

| **Informe de pérdidas y ganancias** | **Objeto de coste** |                |               |               |  **Total**    |
|-----------------------------|-----------------|----------------|---------------|---------------|---------------|
|                             | **CC001**       | **CC002**      | **CC003**     | **CC004**     |               |
| **Coste primario**            | **10.100,00**   | **14.200,00**  | **14.000,00** | **8.500,00**  | **46.800,00** |
| &nbsp;&nbsp;&nbsp;&nbsp; 1001                            | 100,00          | 200,000         | 6.000,00      | 2.000,00      | **8.300,00**  |
| &nbsp;&nbsp;&nbsp;&nbsp; 1002                            | 10.000,00       | 10.000,00      | 8.000,00      | 6.500,00      | **34.500,00** |
|&nbsp;&nbsp;&nbsp;&nbsp; 1003                             | 0.00            | 4.000,00       | 0.00          | 0.00          | **4.000,00**  |
|**Coste secundario**                            | **-10.100,00**  | **-14.200,00** | **17.082.75** | **7.217,25**  | **0,00**      |
|&nbsp;&nbsp;&nbsp;&nbsp;SC-CC001                            | \- 10.100,00     | 3.535,00       | 5.555,00      | 1.010,00      | **0,00**      |
|&nbsp;&nbsp;&nbsp;&nbsp;SC-CC002                             | 0.00            | \- 17.735,00    | 11.527,75     | 6.207,25      | **0,00**      |
|&nbsp;&nbsp;&nbsp;&nbsp;SC-CC003                            | 0.00            | 0.00           | 0.00          | 0.00          | 0.00          |
|&nbsp;&nbsp;&nbsp;&nbsp;SC-CC004                             | 0.00            | 0.00           | 0.00          | 0.00          | 0.00          |
| **Total**                   | **0,00**        | **0,00**       | **31.082,75** | **15.717,25** | **46.800,00** |

Al usar la **Directiva de acumulación de costes** y los **Elementos de coste de tipo secundario** puede abanador el coste principal por objeto de coste para el informe interno como el coste principal que resta después del **Cálculo de costes generales**.

Si el mismo ejemplo se hubiera realizado sin crear la **Directiva de acumulación de costes**, el resultado del informe aparecía como sigue. El coste fluye correctamente pero la rastreabilidad y exploración sobre cómo fluye el coste entre los centros de coste se pierden.

| **Informe de pérdidas y ganancias** | **Objeto de coste** |           |               |               |          **Total**  |
|-----------------------------|-----------------|-----------|---------------|---------------|---------------|
|                             | **CC001**       | **CC002** | **CC003**     | **CC004**     |               |
| **Coste primario**            | **0,00**        | **0,00**  | **31.082,75** | **15.717,25** | **46.800,00** |
|&nbsp;&nbsp;&nbsp;&nbsp; 1001                              | 0.00            | 0.00      | 6.207,75      | 2.092,25      | **8.300,00**  |
| &nbsp;&nbsp;&nbsp;&nbsp; 1002                             | 0.00            | 0.00      | 22.275,00     | 12.225,00     | **34.500,00** |
|&nbsp;&nbsp;&nbsp;&nbsp; 1003                              | 0.00            | 0.00      | 2600,00       | 1.400,00      | **4.000,00**  |
|**Coste secundario**                            | **0,00**        | **0,00**  | **0,00**      | **0,00**      | **0,00**      |
|&nbsp;&nbsp;&nbsp;&nbsp; SC-CC001                             | 0.00            | 0.00      | 0.00          | 0.00          | **0,00**      |
|&nbsp;&nbsp;&nbsp;&nbsp; SC-CC002                             | 0.00            | 0.00      | 0.00          | 0.00          | **0,00**      |
|&nbsp;&nbsp;&nbsp;&nbsp; SC-CC003                             | 0.00            | 0.00      | 0.00          | 0.00          | 0.00          |
|&nbsp;&nbsp;&nbsp;&nbsp; SC-CC004                             | 0.00            | 0.00      | 0.00          | 0.00          | 0.00          |
| **Total**                   | **0,00**        | **0,00**  | **31.082,75** | **15.717,25** | **46.800,00** |

En función de los requisitos de generación de informes y rastreabilidad en su organización, puede determinar el nivel correcto de elementos de coste secundarios y crear reglas de acumulación que se ajusten a sus necesidades.

La clara separación entre **Asignación de costes** y **Directivas de acumulación de costes** proporciona flexibilidad para crear actualizaciones continuas sin que esto repercuta recíprocamente.



## <a name="see-also"></a>Consulte también
-  [Dimensiones de objeto de coste](cost-objects.md)
-  [Dimensiones de elemento de coste](cost-elements.md)
-  [Jerarquías de dimensiones](dimension-hierarchy.md)
-  [Cálculo de costes generales](overhead-calculation.md)

