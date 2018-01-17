---
title: "Miembros de dimensiones estadísticas y plantillas de proveedor de medidas estadísticas"
description: "Este tema proporciona información acerca de miembros de dimensión estadística y plantillas de proveedor de medidas estadísticas. Los miembros de dimensión estadística se pueden usar como base de asignación en directivas como la distribución de costes y la asignación de costes. También se pueden usar para notificar el consumo no monetario del coste."
author: AndersGirke
manager: AnnBe
ms.date: 06/16/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: CAMCostAccountingLedgerSourceEntryProvider, CAMStatisticalDimension, CAMAXStatisticalMeasureProviderTemplate
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Operations, Core
ms.custom: 
ms.assetid: 
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: yuyus
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: 2c0a00b6a1956f1f22a50951308c434c3f0eefc4
ms.contentlocale: es-es
ms.lasthandoff: 11/03/2017

---

# <a name="statistical-dimension-members-and-statistical-measure-provider-templates"></a>Miembros de dimensiones estadísticas y plantillas de proveedor de medidas estadísticas

[!include[banner](../includes/banner.md)]

Una dimensión estadística y sus miembros se usan para registrar y controlar entradas no monetarias en la contabilidad de costes. Los miembros de dimensión estadística se pueden utilizar con dos propósitos:

- Como base de asignación en directivas como la distribución de costes o la asignación de costes
- Para informar del consumo no monetario

## <a name="statistical-dimension"></a>Dimensión estadística

Una dimensión estadística tiene un nombre único y un conjunto de miembros de dimensión únicos. La dimensión estadística se asigna a un identificador de libro mayor de contabilidad de costes. Esta relación vincula a todos los miembros de dimensión estadística correspondientes al libro mayor de contabilidad de costes. Por lo tanto, todas las entradas estadísticas se crearán en el contexto del libro mayor de contabilidad de costes.

> [!NOTE]
> La dimensión estadística puede asignarse a más de un libro mayor de contabilidad de costes.

A continuación se muestra un ejemplo de dimensión estadística.

| Nombre                        | Conector de datos para miembros de dimensión |
|-----------------------------|--------------------------------------|
| Elementos estadísticos compartidos | Miembros de dimensión importados           |

A continuación se muestra un ejemplo de dimensión estadística que se ha asignado a un libro mayor de contabilidad de costes.

| Nombre                  | Divisa de contabilidad | Tipo de cambio | Calendario fiscal | Dimensión de elemento de coste | Dimensión estadística       |
|-----------------------|---------------------|--------------------|-----------------|------------------------|-----------------------------|
| Contabilidad directiva | USD                 | Divisa constante  | Período fiscal   | Elementos de coste compartidos   | Elementos estadísticos compartidos |

## <a name="statistical-dimension-members"></a>Miembros de dimensión estadística

Un miembro de dimensión estadística representa a una entidad para la que desea registrar medidas no monetarias. Estas medidas se pueden usar como base de asignación o solo para informar de valores no monetarios.

Los miembros de dimensión estadística pueden crearse manualmente. Como alternativa, pueden importarse de un archivo utilizando la herramienta de importación y exportación de gestión de datos.

Un miembro de dimensión estadística se convierte automáticamente en base de asignación predefinida. Se puede usar como base de asignación en directivas o como entrada en otros tipos de bases de asignación.

A continuación se muestran algunos ejemplos de miembros de dimensión estadística típicos.

| Nombre de la dimensión estadística  | Elementos estadísticos | Descripción             | Unidad |
|-----------------------------|----------------------|-------------------------|------|
| Elementos estadísticos compartidos | EJC                  | Empleados a jornada completa     | c/u.  |
| Elementos estadísticos compartidos | Electricidad          | Consumo de electricidad | kWh  |
| Elementos estadísticos compartidos | Paquete CC              | Paquete Centro de coste   | Horas |

## <a name="statistical-measure-provider-template"></a>Plantilla de proveedor de medidas estadísticas

Las medidas estadísticas pueden proceder de muchos tipos de fuentes. Microsoft Dynamics 365 for Finance and Operations, Enterprise Edition es una gran fuente para extraer medidas estadísticas. Puede usar una plantilla de proveedor de medidas estadísticas para configurar fácilmente las medidas estadísticas que desea extraer.

La definición de una plantilla de proveedor de medidas estadísticas es genérica y se puede reutilizar en varios miembros de dimensión estadística.

> [!NOTE]
> Todas las tablas que contienen dimensiones financieras se pueden usar como fuente de medidas estadísticas.

**Ejemplo: Recuento de empleados por centro de coste**

El recuento de empleados por centro de coste es una medida estadística que se puede usar para varios fines que proporcionan conocimientos a la directiva:

- Una medida estadística de informes por centro de coste
- Una base de asignación para distintos tipos de gastos
- Tasas de costes internos por centro de coste:

    - Coste por empleado
    - Ingresos por empleado

La tabla HcmEmployment contiene una lista de todos los empleados en la instancia. Esta tabla es una tabla global. Por lo tanto, los registros no están relacionadas con un identificador de área de datos específico.

A continuación se muestra un ejemplo de empleados de la tabla de HcmEmployment.

| Nombre       | Centro de coste | Descripción   | Tipo de trabajador |
|------------|-------------|----|-------------|
| Empleado 1 | CC001       | RR. HH. | Empleado    |
| Empleado 2 | CC002       | FI | Empleado    |
| Empleado 3 | CC002       | FI | Empleado    |
| Empleado 4 | CC003       | TI | Empleado    |
| Empleado 5 | CC003       | TI | Empleado    |
| Empleado 6 | CC002       | FI | Contratista  |

Al crear un registro **Plantilla de proveedor de medidas estadísticas**, debe decidir qué función utilizar:

- **Recuento**: se transfiere un recuento de registros por objeto de coste.
- **Suma**: se transfiere una suma de registros por objeto de coste. (Se requieren el campo **Suma** y el campo **Fecha**).

## <a name="using-the-count-function"></a>Uso de la función de recuento

Por ejemplo, una plantilla de proveedor de medidas estadísticas se puede establecer del modo siguiente.

| Nombre  | Función | Tabla de origen  | Campo de suma      | Campo Fecha     |
|-------|----------|---------------|----------------|----------------|
| EJC  | Cuenta    | HcmEmployment | No aplicable | No aplicable |

También puede agregar uno o varios intervalos para limitar las medidas de la tabla de origen.

En este ejemplo, si desea sólo un recuento de todos los empleados a jornada completa (EJC), puede agregar un intervalo en el campo **Tipo de trabajador**. En el campo **Criterios** , seleccione **Empleado** para limitar el rango de salida del modo siguiente.

**Intervalos**

| Tabla de origen  | Campo       | Criterios |
|---------------|-------------|----------|
| HcmEmployment | Tipo de trabajador | Empleado |

Para poder obtener medidas estadísticas en la contabilidad de costes, debe definir la relación entre la plantilla de proveedor de medidas estadísticas y el miembro de dimensión estadística. Esta relación se crea por libro mayor de contabilidad de costes y versión. La relación consta de un conector de datos y un proveedor de datos. Puede tener varios conectores y proveedores de datos por miembro de dimensión estadística.

> [!NOTE]
> En este ejemplo, crearemos una relación sólo para **Versión real**.

Vaya a **Libro mayor de contabilidad de costes** \> **Versión real** \> **Gestionar** \> **Medidas estadísticas** para establecer la relación. Para esta situación, seleccione el conector de datos **Dynamics 365 for Finance and Operations, Enterprise edition – Medidas estadísticas**, pues deseamos extraer datos de Finance and Operations.

**Origen de datos**

| Nombre        | Conector de datos                                                                     | Miembro de dimensión estadística |
|-------------|------------------------------------------------------------------------------------|------------------------------|
| EJC D365FO | Dynamics 365 for Finance and Operations, Enterprise edition – Medidas estadísticas | EJC                         |

**Configuración del proveedor de datos**

| Nombre de la plantilla estadística |
|---------------------------|
| EJC                      |

Una vez se hayan procesado los datos de origen de la medida estadística, las entradas estadísticas siguientes se crearán en la contabilidad de costes.

**Diario**

| Diario | Tipo de diario                       | Período de calendario fiscal | Año   |  Período  |  Versión | Conector de datos para entradas de origen|
|---------|------------------------------------|------------------------|--------|----------|----------|------------------------------|
| 00001   | Diario de transferencia de entradas estadísticas | Fiscal                 | 2017   | Período 1 | Libro mayor de USMF CA | EJC                   |

**Movimientos de diario de transferencia de entradas estadísticas**

| Fecha contable | Magnitud | Elemento estadístico |   Descripción       | Centro de coste |
|-----------------|-----------|---------------------|---------------------|-------------|
| 31/1/17      | 1,00      | EJC                | Empleados a jornada completa | CC001       |
| 31/1/17      | 2.00      | EJC                | Empleados a jornada completa | CC002       |
| 31/1/17      | 2.00      | EJC                | Empleados a jornada completa | CC003       |

**Entradas estadísticas**

| Objeto de coste |    | Fecha contable | Miembro de dimensión estadística |  Descripción        | Magnitud |
|-------------|----|-----------------|------------------------------|---------------------|-----------|
| CC001       | RR. HH. | 31/1/17      | EJC                         | Empleados a jornada completa | 1,00      |
| CC002       | FI | 31/1/17      | EJC                         | Empleados a jornada completa | 2.00      |
| CC003       | TI | 31/1/17      | EJC                         | Empleados a jornada completa | 2.00      |

Si la base de asignación del miembro de dimensión predefinida de EJC se asigna como base de asignación en una regla de distribución de costes, el coste se distribuirá mediante el siguiente factor de asignación.

| Objeto de coste | Descripción    | Magnitud | Factor de asignación |
|-------------|----|-----------|-------------------|
| CC001       | RR. HH. | 1,00      | (1/5) × Importe    |
| CC002       | FI | 2.00      | (2/5) × Importe    |
| CC003       | TI | 2.00      | (2/5) × Importe    |

## <a name="using-the-sum-function"></a>Uso de la función de suma

Un centro de coste de producción, CC010 (embalaje), es el responsable de empaquetar los productos antes de enviarlos a los clientes. El coste laboral directo se agrega a los productos a través de la lista de materiales (L MAT.) y la ruta. El coste indirecto de ejecutar el centro de coste también se debe asignar a los productos generados. Con frecuencia, la mejor medida estadística para tal asignación es el número de horas de producción registradas por producto dentro del periodo concreto.

La tabla ProdRouteTrans contiene todas las transacciones de mano de obra de la producción por entidad jurídica DataAreadID.

A continuación se muestra un ejemplo de la tabla ProdRouteTrans.

| Referencia        | Número | Operación | Tipo | Hora  | Fecha física | Grupo de productos (dimensión financiera) | Entidad jurídica |
|------------------|--------|-----------|------|-------|---------------|-------------------------------------|--------------|
| Pedido de producción | P0001  | Empaquetado | Hora | 8,00  | 1/1/17    | Zumo de naranja B2B                    | USMF         |
| Pedido de producción | P0001  | Empaquetado | Hora | 8,00  | 2/1/17    | Zumo de naranja B2B                    | USMF         |
| Pedido de producción | P0002  | Empaquetado | Hora | 4,00  | 3/1/17    | Consumidor de zumo de naranja               | USMF         |
| Pedido de producción | P0003  | Empaquetado | Hora | 4,00  | 3/1/17    | Consumidor de zumo de naranja               | USMF         |
| Pedido de producción | P0004  | Reconst.  | Hora | 10,00 | 3/1/17    | Consumidor de zumo de naranja               | USMF         |

Al crear un registro **Plantilla de proveedor de medidas estadísticas**, debe decidir qué función utilizar:

- **Recuento**: se transfiere un recuento de registros por objeto de coste.
- **Suma**: se transfiere una suma de registros por objeto de coste. (Se requieren el campo **Suma** y el campo **Fecha**).

La plantilla de proveedor de medidas estadísticas se puede configurar del modo siguiente.

| Nombre    | Función | Tabla de origen   | Campo de suma | Campo Fecha    |
|---------|----------|----------------|-----------|---------------|
| Paquete CC | Suma      | ProdRouteTrans | Horas     | Fecha física |

También puede agregar intervalos para limitar las medidas de la tabla de origen.

En este ejemplo, si sólo desea la suma de horas relacionadas con el centro de coste Embalaje CC010, puede agregar un intervalo en el campo **Operación** . En el campo **Criterios** , seleccione **Embalaje** para limitar el rango de salida.

**Intervalos**

| Tabla de origen   | Campo     | Criterios  |
|----------------|-----------|-----------|
| ProdRouteTrans | Operación | Empaquetado |

Para poder obtener medidas estadísticas en la contabilidad de costes, debe definir la relación entre la plantilla de proveedor de medidas estadísticas y el miembro de dimensión estadística. Esta relación se crea por libro mayor de contabilidad de costes y versión. La relación consta de un conector de datos y un proveedor de datos. Puede tener varios conectores y proveedores de datos por miembro de dimensión estadística.

> [!NOTE]
> En este ejemplo, crearemos una relación sólo para **Versión real**.

Vaya a **Libro mayor de contabilidad de costes** \> **Versión real** \> **Gestionar** \> **Medidas estadísticas** para establecer la relación. Para esta situación, seleccione el conector de datos **Dynamics 365 for Finance and Operations, Enterprise edition – Medidas estadísticas**, pues deseamos extraer datos de Finance and Operations.

**Origen de datos**

| Nombre           | Conector de datos                                                                     | Miembro de dimensión estadística |
|----------------|------------------------------------------------------------------------------------|------------------------------|
| Paquete CC D365FO | Dynamics 365 for Finance and Operations, Enterprise edition – Medidas estadísticas | Paquete CC                      |

El sistema reconoce que ProdRouteTrans es una tabla en la que cada registro pertenece a una entidad jurídica independiente. Por lo tanto, se le pedirá que seleccione la entidad jurídica de la que deben importarse las transacciones.

**Configuración del proveedor de datos**

| Nombre de la plantilla estadística | Entidad jurídica |
|---------------------------|--------------|
| Paquete CC                   | USMF         |

Una vez se hayan procesado los datos de origen de la medida estadística, las entradas estadísticas siguientes se crearán en la contabilidad de costes.

**Diario**

| Diario | Tipo de diario                     | Período de calendario fiscal | Año   | Período | Versión   |   Conector de datos para entradas de origen  |
|---------|----------------------------------|------------------------|--------|---------|----------------|---------|
| 00002   | Diario de transferencia de entradas estadísticas | Fiscal               | 2017    | Período 1  | Libro mayor de USMF CA | Paquete CC |

**Movimientos de diario de transferencia de entradas estadísticas**

| Fecha contable | Magnitud | Elemento estadístico |  Descripción          | Grupo de productos         |
|-----------------|-----------|---------------------|-----------------------|-----------------------|
| 31/1/17      | 16,00     | Paquete CC             | Paquete Centro de coste | Zumo de naranja B2B      |
| 31/1/17      | 8,00      | Paquete CC             | Paquete Centro de coste | Consumidor de zumo de naranja |

**Entradas estadísticas**

| Objeto de coste           | Fecha contable | Miembro de dimensión estadística |    Descripción        | Magnitud |
|-----------------------|-----------------|------------------------------|-----------------------|-----------|
| Zumo de naranja B2B      | 31/1/17      | Paquete CC                      | Paquete Centro de coste | 16,00     |
| Consumidor de zumo de naranja | 31/1/17      | Paquete CC                      | Paquete Centro de coste | 8,00      |

Si la base de asignación del miembro de dimensión predefinida del Paquete CC se asigna como base de asignación en una regla de distribución de costes, el coste se distribuirá mediante el siguiente factor de asignación.

| Objeto de coste           | Magnitud | Factor de asignación  |
|-----------------------|-----------|--------------------|
| Zumo de naranja B2B      | 16,00     | (16 ÷ 24) × importe |
| Consumidor de zumo de naranja | 8,00      | (8 ÷ 24) × importe  |

## <a name="imported-statistical-measures"></a>Medidas estadísticas importadas

Puede importar medidas estadísticas en la contabilidad de costes utilizando la herramienta de importación y exportación de gestión de datos.

La entidad de datos que se usa para la importación se llama Medidas estadísticas importadas.

> [!NOTE]
> Esta entidad de datos se ha diseñado para permitir un máximo de cinco valores de dimensión únicos por entrada.

El consumo de electricidad se registra en Microsoft Excel mediante el formato predefinido de la entidad de datos. He aquí un ejemplo.

| Fecha contable | Nombre de miembro de dimensión 1 | Nombre de miembro de dimensión 2 | Nombre de miembro de dimensión 5 | Magnitud  | Identificador de origen |
|-----------------|------------------------|------------------------|------------------------|------------|-------------------|
| 31/1/17      | CC001                  |                        |                        | 2,450.00   | Electricidad       |
| 31/1/17      | CC002                  |                        |                        | 4,100.00   | Electricidad       |
| 31/1/17      | CC003                  |                        |                        | 15.000,00  | Electricidad       |

Cuando haya importado los datos mediante la Administración de datos, los datos se guardarán en una tabla provisional de contabilidad de costes. Por lo tanto, los datos importados se pueden usar en varios libros mayores de contabilidad de costes. Una recarga de datos no es necesaria.

Para importar los datos, vaya a **Datos importados** \> **Entidad de datos** \> **Medidas estadísticas importadas**.

| Identificador de origen | Fecha contable | Magnitud  | Nombre de miembro de dimensión 1 | Nombre de miembro de dimensión 2 | Nombre de miembro de dimensión 5 |
|-------------------|-----------------|------------|------------------------|------------------------|------------------------|
| Electricidad       | 31/1/17      | 2,450.00   | CC001                  |                        |                        |
| Electricidad       | 31/1/17      | 4,100.00   | CC002                  |                        |                        |
| Electricidad       | 31/1/17      | 15.000,00  | CC003                  |                        |                        |

Para poder incluir medidas estadísticas en la contabilidad de costes, debe definir la relación entre el identificador de fuentes y el miembro de dimensión estadística. Esta relación se crea por libro mayor de contabilidad de costes y versión. La relación consta de un conector de datos y un proveedor de datos. Puede tener varios conectores y proveedores de datos por miembro de dimensión estadística.

> [!NOTE]
> En este ejemplo, crearemos una relación sólo para **Versión real**.

Vaya a **Libro mayor de contabilidad de costes** \> **Versión real** \> **Gestionar** \> **Medidas estadísticas** para establecer la relación. Para esta situación, seleccione el conector de datos **Medidas estadísticas importadas**, porque los datos se han importado de un sistema de terceros a la contabilidad de costes a través de Excel.

**Origen de datos**

| Nombre        | Conector de datos                | Miembro de dimensión estadística |
|-------------|-------------------------------|------------------------------|
| Electricidad | Medidas estadísticas importadas | Electricidad                  |

**Configuración del proveedor de datos**

| Identificador de origen de importación | Función | Dimensión1   | Dimensión2 | Dimensión5 |
|--------------------------|----------|--------------|------------|------------|
| Electricidad              | Suma      | Centros de coste |            |            |

> [!NOTE]
> Al definir la configuración del proveedor de datos, debe especificar qué dimensiones de objeto de coste deben coincidir con las transacciones importadas. Una vez se hayan procesado los datos de origen de la medida estadística, las entradas estadísticas siguientes se crearán en la contabilidad de costes.

**Diario**

| Diario | Tipo de diario                       | Período de calendario fiscal | Año  | Período  |Versión      |Conector de datos para entradas de origen |
|---------|------------------------------------|------------------------|-------|--------|---------------|-------------|
| 00002   | Diario de transferencia de entradas estadísticas | Fiscal                 | 2017  | Período 1 | Libro mayor de USMF CA | Electricidad |

**Movimientos de diario de transferencia de entradas estadísticas**

| Fecha contable | Magnitud  | Elemento de coste |   Descripción           | Centro de coste |
|-----------------|------------|--------------|-------------------------|-------------|
| 31/1/17      | 2,450.00   | Electricidad  | Consumo de electricidad | CC001       |
| 31/1/17      | 4,100.00   | Electricidad  | Consumo de electricidad | CC002       |
| 31/1/17      | 15.000,00  | Electricidad  | Consumo de electricidad | CC003       |

**Entradas estadísticas**

| Objeto de coste |    | Fecha contable | Miembro de dimensión estadística |      Descripción                   | Magnitud  |
|-------------|----|-----------------|------------------------------|-------------------------|------------|
| CC001       | RR. HH. | 31/1/17      | Electricidad                  | Consumo de electricidad | 2,450.00   |
| CC002       | FI | 31/1/17      | Electricidad                  | Consumo de electricidad | 4,100.00   |
| CC003       | TI | 31/1/17      | Electricidad                  | Consumo de electricidad | 15.000,00  |

Si la base de asignación del miembro de dimensión predefinida de electricidad se asigna como base de asignación en una regla de distribución de costes, el coste se distribuirá mediante el siguiente factor de asignación.

| Objeto de coste |    | Magnitud | Factor de asignación          |
|-------------|----|-----------|----------------------------|
| CC001       | RR. HH. | 2,450.00  | (2450 ÷ 21 550) × Importe  |
| CC002       | FI | 4,100.00  | (4100 ÷ 21 550) × Importe  |
| CC003       | TI | 15.000,00 | (15 000 ÷ 21 550) × Importe |

## <a name="see-also"></a>Consulte también

[Bases de asignación](allocation-bases.md)

