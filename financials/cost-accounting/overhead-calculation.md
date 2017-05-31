---
title: "Cálculo de costes generales"
description: "Este tema describe los procesos típicos para calcular y asignar costes generales."
author: YuyuScheller
manager: AnnBe
ms.date: 04/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: CAMActualVersion, CAMBudgetVersion, CAMOverheadCalculation
audience: Application User
ms.reviewer: annbe
ms.search.scope: Operations, Core
ms.custom: 272163
ms.assetid: 93119afb-47ed-4786-ba44-ba93576d3e28
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: yuyus
ms.dyn365.ops.intro: Version 1611
ms.search.validFrom: 2016-11-30
ms.translationtype: Human Translation
ms.sourcegitcommit: d421b161216d700f7819f1da8c0ca8ad089b5670
ms.openlocfilehash: a24c24f842e4f1b1c7806c2fb2ccbd1329fe4851
ms.contentlocale: es-es
ms.lasthandoff: 05/25/2017


---

# <a name="overhead-calculation"></a>Cálculo de costes generales

[!include[banner](../includes/banner.md)]


Este tema describe los procesos típicos para calcular y asignar costes generales.

<a name="term-definition"></a>Definición del término
---------------

Los costes generales son costes que se contraen para dirigir un negocio, pero que no pueden ser atribuidos directamente a ninguna actividad empresarial, productos, o servicio específicos. Los costes generales proporcionan un soporte fundamental a la generación de actividades rentables. Algunos ejemplos de costes generales son:

-   Alquiler
-   Electricidad
-   Sueldos administrativos

## <a name="overhead-calculation-overview"></a>Visión general del cálculo de costes generales
El cálculo de costes generales ejecuta las directivas de contabilidad de costes en el orden correcto. Puede calcular varias veces los costes generales del mismo período fiscal si se han cambiado las directivas de contabilidad de costes o se han detectado errores específicos. Cada ejecución del cálculo de costes generales se almacena y recibe un identificador de versión único que permite comparar los cálculos de diferentes versiones. Las entradas de costes que el cálculo de costes generales genera reciben una fecha de contabilidad. Esta fecha de contabilidad coincide con la fecha final del período fiscal que se usa en el cálculo. El identificador de versión único consiste en los elementos siguientes:

-   Tipo de versión
-   Fecha y hora
-   Libro mayor de contabilidad de costes
-   Ejercicio
-   Período fiscal

El cálculo de costes generales se ejecuta independientemente de la versión. Por lo tanto, puede calcular la versión de presupuesto antes que la versión real. El cálculo de costes generales consta de cuatro pasos, como se muestra en la siguiente ilustración. En cada paso, se crea una cabecera de diario que tiene entradas del diario. Esta cabecera de diario guarda los datos de entrada para cada paso de cálculo. Las directivas y las reglas se aplican a cada línea de diario, y las entradas de coste se generan como resultado. Por tanto, siempre se tiene rastreabilidad completa. 
[![Cálculo de costes generales](./media/period-cost-calculation.png)](./media/period-cost-calculation.png)

## <a name="calculate-and-allocate-the-electricity-overhead-cost"></a>Calcular y asignar costes generales de electricidad
En la contabilidad financiera, algunos costes, como la electricidad, se registran como suma total. Por lo tanto, no se proporciona una visión de gestión detallada para la contabilidad de costes. En contabilidad de costes, para proporcionar información de gestión correcta en todas las unidades y niveles organizativos, los costes deben fluir por las unidades organizativas. Este flujo se debe basar en cualquier registro preciso de consumo o en una evaluación justa. En la contabilidad general, un coste de la electricidad se puede registrar como se muestra en la tabla siguiente.

<table>
<thead>
<tr>
<th>Fecha contable</th>
<th colspan="2">Centro de coste</th>
<th colspan="2">Cuenta principal</th>
<th>Importe en la divisa de contabilidad</th>
</tr>
</thead>
<tbody>
<tr>
<td>3 de enero de 2017</td>
<td>CC099</td>
<td>Centro de coste predeterminado</td>
<td>10001</td>
<td>Electricidad</td>
<td>10.000,00</td>
</tr>
</tbody>
</table>

### <a name="step-1-process-the-cost-behavior-calculation"></a>Paso 1: Procese el cálculo del comportamiento del coste

De forma predeterminada, cuando las entradas de coste se importan de los datos de origen, reciben la clasificación de comportamiento del coste **Sin ordenar** en la contabilidad de costes. Aplicando reglas de directivas de comportamiento de coste, puede reclasificar entradas de coste como **Coste fijo** o **Coste variable**.

#### <a name="define-the-cost-behavior-rule"></a>Defina la regla de comportamiento del coste

En algunos casos, parte del coste es una cuota fija, y el coste pendiente se basa en el consumo. Las facturas de electricidad coinciden a menudo con esta definición. Tras pagar una cuota fija específica, paga el consumo por kilovatio-hora (Kwh). Por ejemplo, si la cuota de coste fijo es de 1.000,00, la regla de comportamiento del coste se define como sigue:

-   Importe fijo 1.000,00
    -   0 &lt;= 1.000,00 = Fijo
    -   1.000,01 &lt; N = Variable

##### <a name="journal"></a>Diario

<table>
<thead>
<tr>
<th>Diario</th>
<th>Tipo de diario</th>
<th colspan="3">Período de calendario fiscal</th>
<th>Versión</th>
</tr>
</thead>
<tbody>
<tr>
<td>00001</td>
<td>Diario de cálculo de comportamiento de costes</td>
<td>Fiscal</td>
<td>2017</td>
<td>Período 1</td>
<td>Cálculo de costes generales/ 01-02-2017 11:51:00 PM/Contabilidad/2017/Período 1</td>
</tr>
</tbody>
</table>

##### <a name="journal-entries-cost-object-balance-journal-entries"></a>Entradas del diario (entradas de diario para saldo de objeto de costes)

<table>
<thead>
<tr>
<th>Fecha contable</th>
<th colspan="2">Objeto de coste</th>
<th colspan="2">Elemento de coste</th>
<th>Comportamiento de costes</th>
<th>Importe</th>
</tr>
</thead>
<tbody>
<tr>
<td>3 de enero de 2017</td>
<td>CC099</td>
<td>Centro de coste predeterminado</td>
<td>10001</td>
<td>Electricidad</td>
<td>Sin clasificar</td>
<td>10.000,00</td>
</tr>
</tbody>
</table>

##### <a name="cost-entries"></a>Entradas de costes

<table>
<thead>
<tr>
<th colspan="2">Objeto de coste</th>
<th colspan="2">Elemento de coste</th>
<th>Comportamiento de costes</th>
<th>Importe</th>
<th>Fecha contable</th>
</tr>
</thead>
<tbody>
<tr>
<td>CC099</td>
<td>Centro de coste predeterminado</td>
<td>10001</td>
<td>Electricidad</td>
<td>Sin clasificar</td>
<td>10.000,00</td>
<td>3 de enero de 2017</td>
</tr>
<tr>
<td>CC099</td>
<td>Centro de coste predeterminado</td>
<td>10001</td>
<td>Electricidad</td>
<td>Sin clasificar</td>
<td>-10 000,00</td>
<td>31 de enero de 2017</td>
</tr>
<tr>
<td>CC099</td>
<td>Centro de coste predeterminado</td>
<td>10001</td>
<td>Electricidad</td>
<td>Coste fijo</td>
<td>1.000,00</td>
<td>31 de enero de 2017</td>
</tr>
<tr>
<td>CC099</td>
<td>Centro de coste predeterminado</td>
<td>10001</td>
<td>Electricidad</td>
<td>Coste variable</td>
<td>9.000,00</td>
<td>31 de enero de 2017</td>
</tr>
</tbody>
</table>

Para obtener información detallada sobre el comportamiento del coste, consulte Directiva de comportamiento de costes. (Tenga en cuenta que este tema no se ha completado aún, pero pronto se abordará).

### <a name="step-2-process-the-cost-distribution-calculation"></a>Paso 2: Procese el cálculo de distribución de costes

La distribución de costes se usa para redistribuir costes desde un objeto de coste a uno o más objetos de coste aplicando una base relevante de la asignación. La distribución de costes y la asignación de costes difieren en que la distribución de costes siempre se produce en el nivel de elemento de costes principal del coste original.

#### <a name="define-the-cost-distribution-rule"></a>Defina la regla de distribución del coste

En la contabilidad financiera, los costes de electricidad se registran como suma total. En contabilidad de costes, este método no es suficientemente detallado. El coste variable debe distribuirse a los objetos individuales de coste aplicando una base justa. La base de asignación más lógica es el consumo de electricidad (Kwh). Se crea un miembro de dimensión estadística que se denomina Electricity, y se registra el consumo de electricidad. De forma predeterminada, todos los miembros de dimensión estadísticos estarán disponibles como bases de asignación.

<table>
<thead>
<tr>
<th colspan="2">Objeto de coste</th>
<th>Kwh</th>
</tr>
</thead>
<tbody>
<tr>
<td>CC001</td>
<td>RR. HH.</td>
<td>1.000</td>
</tr>
<tr>
<td>CC002</td>
<td>Finanzas</td>
<td>6.000</td>
</tr>
<tr>
<td>CC003</td>
<td>Ensamblado</td>
<td>0</td>
</tr>
</tbody>
</table>

La tabla siguiente muestra el resultado cuando se aplica el consumo de electricidad como base de asignación para los costes variables.

<table>
<thead>
<tr>
<th colspan="2">Objeto de coste</th>
<th>Magnitud</th>
<th>Factor de asignación</th>
<th>Importe</th>
</tr>
</thead>
<tbody>
<tr>
<td>CC001</td>
<td>RR. HH.</td>
<td>1.000</td>
<td>(1.000 ÷ 7000) × 9000,00</td>
<td>1,285.71</td>
</tr>
<tr>
<td>CC002</td>
<td>Finanzas</td>
<td>6.000</td>
<td>(6.000 ÷ 7.000) × 9.000,00</td>
<td>7,714.29</td>
</tr>
<tr>
<td>CC003</td>
<td>Ensamblado</td>
<td>0</td>
<td>(0 ÷ 7000) × 9000,00</td>
<td>0,00</td>
</tr>
</tbody>
</table>

El coste fijo debe distribuirse uniformemente a los objetos individuales de costes que han consumido electricidad. Puede obtener este resultado usando el miembro de dimensión estadístico de electricidad en una base de asignación de la fórmula: (Electricidad &gt; 0,00) La tabla siguiente muestra el resultado cuando el consumo de electricidad se aplica como base de asignación para los costes variables.

<table>
<thead>
<tr>
<th colspan="2">Objeto de coste</th>
<th>Fórmula</th>
<th>Magnitud</th>
<th>Factor de asignación</th>
<th>Importe</th>
</tr>
</thead>
<tbody>
<tr>
<td>CC001</td>
<td>RR. HH.</td>
<td>(1.000 &gt; 0,00)</td>
<td>1</td>
<td>(1 ÷ 2) × 1.000,00</td>
<td>500,00</td>
</tr>
<tr>
<td>CC002</td>
<td>Finanzas</td>
<td>(6.000 &gt; 0,00)</td>
<td>1</td>
<td>(1 ÷ 2) × 1.000,00</td>
<td>500,00</td>
</tr>
<tr>
<td>CC003</td>
<td>Ensamblado</td>
<td>(0 &gt; 0,00)</td>
<td>0</td>
<td>(0 ÷ 2) × 1.000,00</td>
<td>0,00</td>
</tr>
</tbody>
</table>

##### <a name="journal"></a>Diario

<table>
<thead>
<tr>
<th>Diario</th>
<th>Tipo de diario</th>
<th colspan="3">Período de calendario fiscal</th>
<th>Versión</th>
</tr>
</thead>
<tbody>
<tr>
<td>00002</td>
<td>Diario de cálculo de la distribución de costes</td>
<td>Fiscal</td>
<td>2017</td>
<td>Período 1</td>
<td>Cálculo de costes generales/ 01-02-2017 11:51:00 PM/Contabilidad/2017/Período 1</td>
</tr>
</tbody>
</table>

##### <a name="journal-entries-cost-object-balance-journal-entries"></a>Entradas del diario (entradas de diario para saldo de objeto de costes)

<table>
<thead>
<tr>
<th>Fecha contable</th>
<th colspan="2">Objeto de coste</th>
<th colspan="2">Elemento de coste</th>
<th>Comportamiento de costes</th>
<th>Importe</th>
</tr>
</thead>
<tbody>
<tr>
<td>31 de enero de 2017</td>
<td>CC099</td>
<td>Centro de coste predeterminado</td>
<td>10001</td>
<td>Electricidad</td>
<td>Coste fijo</td>
<td>1.000,00</td>
</tr>
<tr>
<td>31 de enero de 2017</td>
<td>CC099</td>
<td>Centro de coste predeterminado</td>
<td>10001</td>
<td>Electricidad</td>
<td>Coste variable</td>
<td>9.000,00</td>
</tr>
</tbody>
</table>

##### <a name="cost-entries"></a>Entradas de costes

<table>
<thead>
<tr>
<th colspan="2">Objeto de coste</th>
<th colspan="2">Elemento de coste</th>
<th>Comportamiento de costes</th>
<th>Importe</th>
<th>Fecha contable</th>
</tr>
</thead>
<tbody>
<tr>
<td>CC099</td>
<td>Centro de coste predeterminado</td>
<td>10001</td>
<td>Electricidad</td>
<td>Coste fijo</td>
<td>-1.000,00</td>
<td>31 de enero de 2017</td>
</tr>
<tr>
<td>CC001</td>
<td>RR. HH.</td>
<td>10001</td>
<td>Electricidad</td>
<td>Coste fijo</td>
<td>500,00</td>
<td>31 de enero de 2017</td>
</tr>
<tr>
<td>CC002</td>
<td>Finanzas</td>
<td>10001</td>
<td>Electricidad</td>
<td>Coste fijo</td>
<td>500,00</td>
<td>31 de enero de 2017</td>
</tr>
<tr>
<td>CC099</td>
<td>Centro de coste predeterminado</td>
<td>10001</td>
<td>Electricidad</td>
<td>Coste variable</td>
<td>-9.000,00</td>
<td>31 de enero de 2017</td>
</tr>
<tr>
<td>CC001</td>
<td>RR. HH.</td>
<td>10001</td>
<td>Electricidad</td>
<td>Coste variable</td>
<td>1,285.71</td>
<td>31 de enero de 2017</td>
</tr>
<tr>
<td>CC002</td>
<td>Finanzas</td>
<td>10001</td>
<td>Electricidad</td>
<td>Coste variable</td>
<td>7,714.29</td>
<td>31 de enero de 2017</td>
</tr>
</tbody>
</table>

Para obtener información detallada sobre la distribución de costes y las bases de asignación, consulte la directiva de distribución de costes y las bases de asignación. (Tenga en cuenta que este tema no se ha completado aún, pero pronto se abordará).

### <a name="step-3-process-the-overhead-rate-calculation"></a>Paso 3: Procese el cálculo de las tasas de costes generales

La tasa de costes generales se usa para cargar uno o varios objetos de coste específicos. El cargo se basa en un índice de coste predeterminado y la magnitud de la base de asignación asignada. 

#### <a name="define-the-overhead-rate"></a>Defina la tasa de costes generales

El objeto de coste CC001 HR contribuye a un conjunto de proyectos internos. Se crea un miembro de dimensión estadística que se denomina proyectos HR para medir la magnitud consumida.

<table>
<thead>
<tr>
<th colspan="2">Objeto de coste</th>
<th>Horas</th>
</tr>
</thead>
<tbody>
<tr>
<td>Proy 1</td>
<td>Proyecto 1</td>
<td>3</td>
</tr>
<tr>
<td>Proy 2</td>
<td>Proyecto 2</td>
<td>1</td>
</tr>
</tbody>
</table>

Una tasa de coste predeterminada para la contribución de los proyectos de coste se ha definido.

<table>
<thead>
<tr>
<th colspan="2">Objeto de coste</th>
<th>Elemento de coste</th>
<th>Comportamiento de costes</th>
<th>Unidades</th>
<th>Índice</th>
</tr>
</thead>
<tbody>
<tr>
<td>CC001</td>
<td>RR. HH.</td>
<td>10001</td>
<td>Coste variable</td>
<td>1</td>
<td>10</td>
</tr>
</tbody>
</table>

La tabla siguiente muestra el resultado cuando los proyectos HR se aplican como base de la asignación.

<table>
<thead>
<tr>
<th colspan="2">Objeto de coste</th>
<th>Magnitud</th>
<th>Elemento de coste</th>
<th>Factor de asignación</th>
<th>Importe</th>
</tr>
</thead>
<tbody>
<tr>
<td>Proy 1</td>
<td>Proyecto 1</td>
<td>3</td>
<td>10001</td>
<td>(3 ÷ 1) × 10,00</td>
<td>30,00</td>
</tr>
<tr>
<td>Proy 2</td>
<td>Proyecto 2</td>
<td>1</td>
<td>10001</td>
<td>(1 ÷ 1) × 10,00</td>
<td>10,00</td>
</tr>
</tbody>
</table>

##### <a name="journal"></a>Diario

<table>
<thead>
<tr>
<th>Diario</th>
<th>Tipo de diario</th>
<th colspan="3">Período de calendario fiscal</th>
<th>Versión</th>
</tr>
</thead>
<tbody>
<tr>
<td>00003</td>
<td>Diario de cálculo de tasas de costes generales</td>
<td>Fiscal</td>
<td>2017</td>
<td>Período 1</td>
<td>Cálculo de costes generales/ 01-02-2017 11:51:00 PM/Contabilidad/2017/Período 1</td>
</tr>
</tbody>
</table>

##### <a name="journal-entries-journal-entries-for-overhead-rate-calculation"></a>Entradas de diario (entradas de diario para cálculo de tasas de costes generales)

<table>
<thead>
<tr>
<th>Fecha contable</th>
<th colspan="2">Objeto de coste</th>
<th>Magnitud</th>
</tr>
</thead>
<tbody>
<tr>
<td>31 de enero de 2017</td>
<td>Proy 1</td>
<td>Proyecto interno 1</td>
<td>3,00</td>
</tr>
<tr>
<td>31 de enero de 2017</td>
<td>Proy 2</td>
<td>Proyecto interno 2</td>
<td>1,00</td>
</tr>
</tbody>
</table>

##### <a name="cost-entries"></a>Entradas de costes

<table>
<thead>
<tr>
<th colspan="2">Objeto de coste</th>
<th colspan="2">Elemento de coste</th>
<th>Comportamiento de costes</th>
<th>Importe</th>
<th>Fecha contable</th>
</tr>
</thead>
<tbody>
<tr>
<td>CC0001</td>
<td>RR. HH.</td>
<td>10001</td>
<td>Electricidad</td>
<td>Coste variable</td>
<td>-30,00</td>
<td>31 de enero de 2017</td>
</tr>
<tr>
<td>Proy 1</td>
<td>Proyecto interno 1</td>
<td>10001</td>
<td>Electricidad</td>
<td>Coste variable</td>
<td>30,00</td>
<td>31 de enero de 2017</td>
</tr>
<tr>
<td>CC001</td>
<td>RR. HH.</td>
<td>10001</td>
<td>Electricidad</td>
<td>Coste variable</td>
<td>-10,00</td>
<td>31 de enero de 2017</td>
</tr>
<tr>
<td>Proy 2</td>
<td>Proyecto interno 2</td>
<td>10001</td>
<td>Electricidad</td>
<td>Coste variable</td>
<td>10,00</td>
<td>31 de enero de 2017</td>
</tr>
</tbody>
</table>

Para obtener información detallada acerca de la directiva de tasa de costes generales, consulte la directiva de tasas de costes generales y las bases de asignación. (Tenga en cuenta que este tema no se ha completado aún, pero pronto se abordará).

### <a name="step-4-process-the-cost-allocation-calculation"></a>Paso 4: Procese el cálculo de asignación de costes

La asignación es utilizada para asignar el saldo de un objeto de coste a otros objetos de coste aplicando una base de asignación. Microsoft Dynamics 365 for Operations admite el método de asignación recíproco. En el método de asignación recíproco, se reconocen completamente los servicios mutuos que los objetos de coste auxiliar intercambian. El sistema determina automáticamente el orden correcto para realizar las asignaciones. El saldo de un objeto de coste se asigna según una única base de asignación. Las asignaciones entre dimensiones de objetos de coste y sus miembros respectivos se admiten. El orden de asignación se controla por unidad de control de costes. [![Método recíproco](./media/reciprocal-method.png)]

#### <a name="define-the-cost-allocation"></a>Defina la asignación de costes

A continuación se indica un ejemplo sencillo que explica cómo puede realizar el seguimiento del flujo de coste. El objeto de coste CC001 HR contribuye a varios objetos de coste. Se crea un miembro de dimensión estadística que se denomina servicios HR para medir la magnitud consumida.

<table>
<thead>
<tr>
<th colspan="2">Objeto de coste</th>
<th>Servicios HR</th>
</tr>
</thead>
<tbody>
<tr>
<td>CC002</td>
<td>Finanzas</td>
<td>35</td>
</tr>
<tr>
<td>CC003</td>
<td>Ensamblado</td>
<td>55</td>
</tr>
<tr>
<td>CC004</td>
<td>Empaquetado</td>
<td>10</td>
</tr>
</tbody>
</table>

El objeto de coste CC002 Finanzas contribuye a varios objetos de coste. Se crea un miembro de dimensión estadística que se denomina Finanzas para medir la magnitud consumida.

<table>
<thead>
<tr>
<th colspan="2">Objeto de coste</th>
<th>Servicios financieros</th>
</tr>
</thead>
<tbody>
<tr>
<td>CC003</td>
<td>Ensamblado</td>
<td>65</td>
</tr>
<tr>
<td>CC004</td>
<td>Empaquetado</td>
<td>35</td>
</tr>
</tbody>
</table>

El objeto de coste CC003 Asamblea contribuye a varios objetos de coste. Se crea un miembro de dimensión estadística que se denomina servicios de Asamblea para medir la magnitud consumida.

<table>
<thead>
<tr>
<th colspan="2">Objeto de coste</th>
<th>Servicios de la asamblea (horas)</th>
</tr>
</thead>
<tbody>
<tr>
<td>Prod 1</td>
<td>Producto 1</td>
<td>60</td>
</tr>
<tr>
<td>Prod 2</td>
<td>Producto 2</td>
<td>20</td>
</tr>
</tbody>
</table>

El objeto de coste CC004 Embalaje contribuye a varios objetos de coste. Se crea un miembro de dimensión estadística que se denomina servicios de Embalaje para medir la magnitud consumida.

<table>
<thead>
<tr>
<th colspan="2">Objeto de coste</th>
<th>Servicios de embalaje (horas)</th>
</tr>
</thead>
<tbody>
<tr>
<td>Prod 1</td>
<td>Producto 1</td>
<td>80</td>
</tr>
<tr>
<td>Prod 2</td>
<td>Producto 2</td>
<td>15</td>
</tr>
</tbody>
</table>

**Nota:** En Dynamics 365 for Operations, las medidas estadísticas como las horas de la producción que un producto consume se pueden deducir de los datos de origen. Para obtener información más detallada acerca de los proveedores de medidas estadísticas, consulte la plantilla de proveedor de estadísticas de medidas. (Tenga en cuenta que este tema todavía no está completado, pero que pronto lo estará). La tabla siguiente muestra el resultado cuando se aplican los servicios HR como base de asignación para el coste total (coste fijo y coste variable).

<table>
<thead>
<tr>
<th colspan="2">Objeto de coste</th>
<th>Magnitud</th>
<th>Factor de asignación</th>
<th>Importe</th>
<th>Comportamiento de costes</th>
</tr>
</thead>
<tbody>
<tr>
<td>CC002</td>
<td>Finanzas</td>
<td>35</td>
<td>(35 ÷ 100) × 500,00</td>
<td>175.00</td>
<td>Coste fijo</td>
</tr>
<tr>
<td>CC003</td>
<td>Ensamblado</td>
<td>55</td>
<td>(55 ÷ 100) × 500,00</td>
<td>275.00</td>
<td>Coste fijo</td>
</tr>
<tr>
<td>CC004</td>
<td>Empaquetado</td>
<td>10</td>
<td>(10 ÷ 100) × 500,00</td>
<td>50,00</td>
<td>Coste fijo</td>
</tr>
<tr>
<td>CC002</td>
<td>Finanzas</td>
<td>35</td>
<td>(35 ÷ 100) × 1.245,71</td>
<td>436.00</td>
<td>Coste variable</td>
</tr>
<tr>
<td>CC003</td>
<td>Ensamblado</td>
<td>55</td>
<td>(55 ÷ 100) × 1.245,71</td>
<td>685.14</td>
<td>Coste variable</td>
</tr>
<tr>
<td>CC004</td>
<td>Empaquetado</td>
<td>10</td>
<td>(10 ÷ 100) × 1.245,71</td>
<td>124.57</td>
<td>Coste variable</td>
</tr>
</tbody>
</table>

La tabla siguiente muestra el resultado cuando se aplican los servicios de Finanzas como base de asignación para el coste total (coste fijo y coste variable).

<table>
<thead>
<tr>
<th colspan="2">Objeto de coste</th>
<th>Magnitud</th>
<th>Factor de asignación</th>
<th>Importe</th>
<th>Comportamiento de costes</th>
</tr>
</thead>
<tbody>
<tr>
<td>CC003</td>
<td>Ensamblado</td>
<td>65</td>
<td>(65 ÷ 100) × (500,00 + 175,00)</td>
<td>438.75</td>
<td>Coste fijo</td>
</tr>
<tr>
<td>CC004</td>
<td>Empaquetado</td>
<td>35</td>
<td>(35 ÷ 100) × (500,00 + 175,00)</td>
<td>236.25</td>
<td>Coste fijo</td>
</tr>
<tr>
<td>CC003</td>
<td>Ensamblado</td>
<td>65</td>
<td>(65 ÷ 100) × (7.714,29 + 436,00)</td>
<td>5,297.69</td>
<td>Coste variable</td>
</tr>
<tr>
<td>CC004</td>
<td>Empaquetado</td>
<td>35</td>
<td>(35 ÷ 100) × (7.714,29 + 436,00)</td>
<td>2,852.60</td>
<td>Coste variable</td>
</tr>
</tbody>
</table>

La tabla siguiente muestra el resultado cuando se aplican los servicios de Asamblea como base de asignación para el coste total (coste fijo y coste variable).

<table>
<thead>
<tr>
<th colspan="2">Objeto de coste</th>
<th>Magnitud</th>
<th>Factor de asignación</th>
<th>Importe</th>
<th>Comportamiento de costes</th>
</tr>
</thead>
<tbody>
<tr>
<td>Prod 1</td>
<td>Producto 1</td>
<td>60</td>
<td>(60 ÷ 80) × (275,00 + 438,75)</td>
<td>535.31</td>
<td>Coste fijo</td>
</tr>
<tr>
<td>Prod 2</td>
<td>Producto 2</td>
<td>20</td>
<td>(20 ÷ 80) × (275,00 + 438,75)</td>
<td>178.44</td>
<td>Coste fijo</td>
</tr>
<tr>
<td>Prod 1</td>
<td>Producto 1</td>
<td>60</td>
<td>(60 ÷ 80) × (5.297,69 + 685,14)</td>
<td>4,487.12</td>
<td>Coste variable</td>
</tr>
<tr>
<td>Prod 2</td>
<td>Producto 2</td>
<td>20</td>
<td>(20 ÷ 80) × (5.297,69 + 685,14)</td>
<td>1,495.71</td>
<td>Coste variable</td>
</tr>
</tbody>
</table>

La tabla siguiente muestra el resultado cuando se aplican los servicios de Embalaje como base de asignación para el coste total (coste fijo y coste variable).

<table>
<thead>
<tr>
<th colspan="2">Objeto de coste</th>
<th>Magnitud</th>
<th>Factor de asignación</th>
<th>Importe</th>
<th>Comportamiento de costes</th>
</tr>
</thead>
<tbody>
<tr>
<td>Prod 1</td>
<td>Producto 1</td>
<td>80</td>
<td>(80 ÷ 95) × (50,00 + 236,25)</td>
<td>241.05</td>
<td>Coste fijo</td>
</tr>
<tr>
<td>Prod 2</td>
<td>Producto 2</td>
<td>15</td>
<td>(15 ÷ 95) × (50,00 + 236,25)</td>
<td>45.20</td>
<td>Coste fijo</td>
</tr>
<tr>
<td>Prod 1</td>
<td>Producto 1</td>
<td>80</td>
<td>(80 ÷ 95) × (2.852,60 + 124,57)</td>
<td>2,507.09</td>
<td>Coste variable</td>
</tr>
<tr>
<td>Prod 2</td>
<td>Producto 2</td>
<td>15</td>
<td>(15 ÷ 95) × (2.852,60 + 124,57)</td>
<td>470.08</td>
<td>Coste variable</td>
</tr>
</tbody>
</table>

##### <a name="journal-entries-cost-object-balance-journal-entries"></a>Entradas del diario (entradas de diario para saldo de objeto de costes)

<table>
<thead>
<tr>
<th>Diario</th>
<th>Tipo de diario</th>
<th colspan="3">Período de calendario fiscal</th>
<th>Versión</th>
</tr>
</thead>
<tbody>
<tr>
<td>00004</td>
<td>Diario de asignación de costes</td>
<td>Fiscal</td>
<td>2017</td>
<td>Período 1</td>
<td>Cálculo de costes generales/ 01-02-2017 11:51:00 PM/Contabilidad/2017/Período 1</td>
</tr>
</tbody>
</table>

##### <a name="journal-lines"></a>Líneas de diario

<table>
<thead>
<tr>
<th>Fecha contable</th>
<th colspan="2">Objeto de coste</th>
<th colspan="2">Elemento de coste</th>
<th>Comportamiento de costes</th>
<th>Importe</th>
</tr>
</thead>
<tbody>
<tr>
<td>31 de enero de 2017</td>
<td>CC001</td>
<td>RR. HH.</td>
<td>10001</td>
<td>Electricidad</td>
<td>Coste fijo</td>
<td>500,00</td>
</tr>
<tr>
<td>31 de enero de 2017</td>
<td>CC001</td>
<td>RR. HH.</td>
<td>10001</td>
<td>Electricidad</td>
<td>Coste variable</td>
<td>1,245.71</td>
</tr>
<tr>
<td>31 de enero de 2017</td>
<td>CC002</td>
<td>Finanzas</td>
<td>10001</td>
<td>Electricidad</td>
<td>Coste fijo</td>
<td>675.00</td>
</tr>
<tr>
<td>31 de enero de 2017</td>
<td>CC002</td>
<td>Finanzas</td>
<td>10001</td>
<td>Electricidad</td>
<td>Coste variable</td>
<td>8,150.29</td>
</tr>
<tr>
<td>31 de enero de 2017</td>
<td>CC003</td>
<td>Ensamblado</td>
<td>10001</td>
<td>Electricidad</td>
<td>Coste fijo</td>
<td>713.75</td>
</tr>
<tr>
<td>31 de enero de 2017</td>
<td>CC003</td>
<td>Ensamblado</td>
<td>10001</td>
<td>Electricidad</td>
<td>Coste variable</td>
<td>5,982.83</td>
</tr>
<tr>
<td>31 de enero de 2017</td>
<td>CC003</td>
<td>Empaquetado</td>
<td>10001</td>
<td>Electricidad</td>
<td>Coste fijo</td>
<td>286.25</td>
</tr>
<tr>
<td>31 de enero de 2017</td>
<td>CC003</td>
<td>Empaquetado</td>
<td>10001</td>
<td>Electricidad</td>
<td>Coste variable</td>
<td>2,977.17</td>
</tr>
<tr>
<td>31 de enero de 2017</td>
<td>Prod 1</td>
<td>Producto 1</td>
<td>10001</td>
<td>Electricidad</td>
<td>Coste fijo</td>
<td>776.36</td>
</tr>
<tr>
<td>31 de enero de 2017</td>
<td>Prod 1</td>
<td>Producto 1</td>
<td>10001</td>
<td>Electricidad</td>
<td>Coste variable</td>
<td>6,994.21</td>
</tr>
<tr>
<td>31 de enero de 2017</td>
<td>Prod 2</td>
<td>Producto 1</td>
<td>10001</td>
<td>Electricidad</td>
<td>Coste fijo</td>
<td>223.64</td>
</tr>
<tr>
<td>31 de enero de 2017</td>
<td>Prod 2</td>
<td>Producto 1</td>
<td>10001</td>
<td>Electricidad</td>
<td>Coste variable</td>
<td>1,965.79</td>
</tr>
</tbody>
</table>

##### <a name="cost-entries"></a>Entradas de costes

<table>
<thead>
<tr>
<th colspan="2">Objeto de coste</th>
<th colspan="2">Elemento de coste</th>
<th>Comportamiento de costes</th>
<th>Importe</th>
<th>Fecha contable</th>
</tr>
</thead>
<tbody>
<tr>
<td>CC001</td>
<td>RR. HH.</td>
<td>10001</td>
<td>Electricidad</td>
<td>Coste fijo</td>
<td>-500,00</td>
<td>31 de enero de 2017</td>
</tr>
<tr>
<td>CC002</td>
<td>Finanzas</td>
<td>10001</td>
<td>Electricidad</td>
<td>Coste fijo</td>
<td>175.00</td>
<td>31 de enero de 2017</td>
</tr>
<tr>
<td>CC003</td>
<td>Ensamblado</td>
<td>10001</td>
<td>Electricidad</td>
<td>Coste fijo</td>
<td>275.00</td>
<td>31 de enero de 2017</td>
</tr>
<tr>
<td>CC004</td>
<td>Empaquetado</td>
<td>10001</td>
<td>Electricidad</td>
<td>Coste fijo</td>
<td>50,00</td>
<td>31 de enero de 2017</td>
</tr>
<tr>
<td>CC001</td>
<td>RR. HH.</td>
<td>10001</td>
<td>Electricidad</td>
<td>Coste variable</td>
<td>-1.245,71</td>
<td>31 de enero de 2017</td>
</tr>
<tr>
<td>CC002</td>
<td>Finanzas</td>
<td>10001</td>
<td>Electricidad</td>
<td>Coste variable</td>
<td>436.00</td>
<td>31 de enero de 2017</td>
</tr>
<tr>
<td>CC003</td>
<td>Ensamblado</td>
<td>10001</td>
<td>Electricidad</td>
<td>Coste variable</td>
<td>685.14</td>
<td>31 de enero de 2017</td>
</tr>
<tr>
<td>CC004</td>
<td>Empaquetado</td>
<td>10001</td>
<td>Electricidad</td>
<td>Coste variable</td>
<td>124.57</td>
<td>31 de enero de 2017</td>
</tr>
<tr>
<td>CC002</td>
<td>Finanzas</td>
<td>10001</td>
<td>Electricidad</td>
<td>Coste fijo</td>
<td>-675,00</td>
<td>31 de enero de 2017</td>
</tr>
<tr>
<td>CC003</td>
<td>Ensamblado</td>
<td>10001</td>
<td>Electricidad</td>
<td>Coste fijo</td>
<td>438.75</td>
<td>31 de enero de 2017</td>
</tr>
<tr>
<td>CC004</td>
<td>Empaquetado</td>
<td>10001</td>
<td>Electricidad</td>
<td>Coste fijo</td>
<td>236.25</td>
<td>31 de enero de 2017</td>
</tr>
<tr>
<td>CC002</td>
<td>Finanzas</td>
<td>10001</td>
<td>Electricidad</td>
<td>Coste variable</td>
<td>-8.150,29</td>
<td>31 de enero de 2017</td>
</tr>
<tr>
<td>CC003</td>
<td>Ensamblado</td>
<td>10001</td>
<td>Electricidad</td>
<td>Coste variable</td>
<td>5,297.69</td>
<td>31 de enero de 2017</td>
</tr>
<tr>
<td>CC004</td>
<td>Empaquetado</td>
<td>10001</td>
<td>Electricidad</td>
<td>Coste variable</td>
<td>2,852.60</td>
<td>31 de enero de 2017</td>
</tr>
<tr>
<td>CC003</td>
<td>Ensamblado</td>
<td>10001</td>
<td>Electricidad</td>
<td>Coste fijo</td>
<td>-713,75</td>
<td>31 de enero de 2017</td>
</tr>
<tr>
<td>Prod 1</td>
<td>Producto 1</td>
<td>10001</td>
<td>Electricidad</td>
<td>Coste fijo</td>
<td>535.31</td>
<td>31 de enero de 2017</td>
</tr>
<tr>
<td>Prod 2</td>
<td>Producto 2</td>
<td>10001</td>
<td>Electricidad</td>
<td>Coste fijo</td>
<td>178.44</td>
<td>31 de enero de 2017</td>
</tr>
<tr>
<td>CC003</td>
<td>Ensamblado</td>
<td>10001</td>
<td>Electricidad</td>
<td>Coste variable</td>
<td>-5.982,83</td>
<td>31 de enero de 2017</td>
</tr>
<tr>
<td>Prod 1</td>
<td>Producto 1</td>
<td>10001</td>
<td>Electricidad</td>
<td>Coste variable</td>
<td>4,487.12</td>
<td>31 de enero de 2017</td>
</tr>
<tr>
<td>Prod 2</td>
<td>Producto 2</td>
<td>10001</td>
<td>Electricidad</td>
<td>Coste variable</td>
<td>1,495.71</td>
<td>31 de enero de 2017</td>
</tr>
<tr>
<td>CC003</td>
<td>Ensamblado</td>
<td>10001</td>
<td>Electricidad</td>
<td>Coste fijo</td>
<td>-286,25</td>
<td>31 de enero de 2017</td>
</tr>
<tr>
<td>Prod 1</td>
<td>Producto 1</td>
<td>10001</td>
<td>Electricidad</td>
<td>Coste fijo</td>
<td>241.05</td>
<td>31 de enero de 2017</td>
</tr>
<tr>
<td>Prod 2</td>
<td>Producto 2</td>
<td>10001</td>
<td>Electricidad</td>
<td>Coste fijo</td>
<td>45.20</td>
<td>31 de enero de 2017</td>
</tr>
<tr>
<td>CC003</td>
<td>Ensamblado</td>
<td>10001</td>
<td>Electricidad</td>
<td>Coste variable</td>
<td>-2.977,17</td>
<td>31 de enero de 2017</td>
</tr>
<tr>
<td>Prod 1</td>
<td>Producto 1</td>
<td>10001</td>
<td>Electricidad</td>
<td>Coste variable</td>
<td>2,507.09</td>
<td>31 de enero de 2017</td>
</tr>
<tr>
<td>Prod 2</td>
<td>Producto 2</td>
<td>10001</td>
<td>Electricidad</td>
<td>Coste variable</td>
<td>470.08</td>
<td>31 de enero de 2017</td>
</tr>
</tbody>
</table>

## <a name="conclusion"></a>Conclusión
En la contabilidad financiera, un coste de 10.000,00 para electricidad se envía a un identificador ficticio de centro de coste. Por lo tanto, los contables de coste sabrán que este coste se debe asignar. En contabilidad de costes, los costes fluyen en las unidades organizativas y los niveles en función de las directivas y las reglas que se aplican. Cada coste se ha asociado con una base de asignación que proporciona la mejor evaluación para la asignación de costes.

<table>
<thead>
<tr>
<th colspan="2" rowspan="2">Elemento de coste</th>
<th colspan="9">Objeto de coste</th>
<th rowspan="2">Total</th>
</tr>
<tr>
<th>CC099</th>
<th>CC001</th>
<th>CC002</th>
<th>CC003</th>
<th>CC004</th>
<th>Proy 1</th>
<th>Proy 2</th>
<th>Prod 1</th>
<th>Prod 2</th>
</tr>
</thead>
<tbody>
<tr>
<td colspan="2">10001 Electricidad</td>
<td style="text-align: right;"><strong>0.00</strong></td>
<td style="text-align: right;"><strong>0.00</strong></td>
<td style="text-align: right;"><strong>0.00</strong></td>
<td style="text-align: right;"><strong>0.00</strong></td>
<td style="text-align: right;"></td>
<td style="text-align: right;"><strong>30.00</strong></td>
<td style="text-align: right;"><strong>10.00</strong></td>
<td style="text-align: right;"><strong>7,770.57</strong></td>
<td style="text-align: right;"><strong>2,189.43</strong></td>
<td style="text-align: right;"><strong>10,000.00</strong></td>
</tr>
<tr>
<td></td>
<td style="text-align: left;">Sin clasificar</td>
<td style="text-align: right;">0,00</td>
<td style="text-align: right;"></td>
<td style="text-align: right;"></td>
<td style="text-align: right;"></td>
<td style="text-align: right;"></td>
<td style="text-align: right;"></td>
<td style="text-align: right;"></td>
<td style="text-align: right;"></td>
<td style="text-align: right;"></td>
<td style="text-align: right;"></td>
</tr>
<tr>
<td style="text-align: right;"></td>
<td style="text-align: left;">Coste fijo</td>
<td style="text-align: right;">0,00</td>
<td style="text-align: right;">0,00</td>
<td style="text-align: right;">0,00</td>
<td style="text-align: right;">0,00</td>
<td style="text-align: right;">0,00</td>
<td style="text-align: right;"></td>
<td style="text-align: right;"></td>
<td style="text-align: right;">776.36</td>
<td style="text-align: right;">223.64</td>
<td style="text-align: right;"><strong>1,000.00</strong></td>
</tr>
<tr>
<td style="text-align: right;"></td>
<td style="text-align: left;">Coste variable</td>
<td style="text-align: right;">000</td>
<td style="text-align: right;">0,00</td>
<td style="text-align: right;">0,00</td>
<td style="text-align: right;">0,00</td>
<td style="text-align: right;">0,00</td>
<td style="text-align: right;">30,00</td>
<td style="text-align: right;">10,00</td>
<td style="text-align: right;">6,994.21</td>
<td style="text-align: right;">1,965.79</td>
<td style="text-align: right;"><strong>9,000.00</strong></td>
</tr>
</tbody>
</table>

> [!NOTE]
> Este tema muestra cómo un artículo de costes principales, 10001 Electricidad, fluye por los objetos de coste. Por tanto, estos gastos generales se asignan al nivel más bajo de la organización. Es decir, los objetos de coste del nivel más bajo son los que soportan el coste. Si necesita un flujo visual del coste entre los objetos de coste, puede usar las reglas de directivas de acumulación de costes para visualizar el flujo del coste. Para obtener información detallada, consulte la política de acumulación de costes. (Tenga en cuenta que este tema no se ha completado aún, pero pronto se abordará).




