---
title: Condiciones de asignación
description: Este tema proporciona información sobre el uso de términos de asignación en una cuenta principal.
author: rachel-profitt
manager: AnnBe
ms.date: 06/15/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: AccountingDistribution, LedgerAllocationRule, MainAccount, AllocationTerms
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.custom: 17361
ms.assetid: 04c8548a-0af9-492b-954b-946b4f8ca023
ms.search.region: Global
ms.author: raprofit
ms.search.validFrom: 2020-06-15
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 637e12f0deaa53811093a8745bc74dbc19e34f6b
ms.sourcegitcommit: 4676ea9646fa1a182103ecab93e78a69001f0b8d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/21/2020
ms.locfileid: "3613160"
---
# <a name="allocation-terms"></a>Condiciones de asignación

[!include [banner](../includes/banner.md)]

Este tema proporciona información sobre el uso de términos de asignación en una cuenta principal. Los términos de asignación se usan para distribuir importes en varias combinaciones de cuenta contable. Ayudan a garantizar que los gastos o ingresos se cargan en objeto adecuado en contabilidad.

Cada término de asignación que cree en una cuenta principal define el porcentaje de un asiento que se asignará desde una cuenta principal de fuente única y una combinación de dimensiones financieras. Además, usted define la cuenta principal de destino y las dimensiones financieras donde se asignará el importe. 

Cuando define la dimensión financiera de origen para la asignación, puede seleccionar si cada dimensión es específica o inespecífica. Específico indica que la dimensión financiera de la transacción de origen debe coincidir con la dimensión seleccionada. Cuando selecciona no específico, indica que cualquier valor para la dimensión financiera puede contribuir a una coincidencia.

Cuando define la cuenta contable de destino para un término de asignación, debe especificar la cuenta principal a la que está asignando el importe. Puede usar la misma cuenta principal donde se registra la transacción de origen o una cuenta principal diferente. Si se utiliza la misma cuenta principal, aparece una advertencia al guardar el registro. Además de especificar la cuenta principal, también debe especificar las dimensiones de destino. Para cada dimensión, puede especificar si desea conservar el valor de la dimensión financiera de origen o cambiarlo. Si selecciona no, debe seleccionar un nuevo valor para la dimensión financiera. Si selecciona sí, no se especifica información adicional, y el sistema mantendrá las dimensiones financieras originales cuando se registren.

No hay límite para la cantidad de términos de asignación que puede agregar a una cuenta principal; sin embargo, la suma del porcentaje a asignar en un término de asignación no puede superar el valor de 100. Puede crear asignaciones de un valor inferior a 100 por ciento si una parte del importe del comprobante original debe permanecer en las dimensiones financieras de origen. Los términos de asignación se pueden agregar a una cuenta principal como una anulación de entidad legal. Si está utilizando un plan de cuentas compartido, los términos de asignación deben definirse para cada entidad jurídica. Para acceder al botón **Términos de asignación**, primero debe seleccionar la casilla **Asignación** en la anulación de entidad jurídica.

## <a name="allocation-term-example"></a>Ejemplo de término de asignación
Ha definido un centro de costos para su organización llamado CORPORATE con el número 000. Cuando las facturas se contabilizan para gastos de servicios públicos, se codifican en este centro de costos denominado CORPORATE. Su compañía ha definido una regla de que todos los gastos de servicios públicos deben asignarse según un porcentaje a cada uno de los centros de costes individuales. Las otras dimensiones financieras para el departamento y la unidad de negocios se mantendrán igual.

Con este ejemplo, se crearía un nuevo término de asignación para la cuenta principal de gastos por servicios públicos. Se crearía una fila para cada centro de coste con el porcentaje que se asignará. Los **Criterios de selección** para las dimensiones financieras de origen para cada fila serían **Específico** para el **Centro de costes** y el valor se establecería en 000: CORPORATE. Por departamento y unidad de negocio, el **Criterio de selección** sería **Inespecífico**.

En la ficha desplegable **Cuenta contable de destino**, la cuenta principal será la misma cuenta de gastos de servicios públicos y **Mantener dimensiones financieras de origen** se establecerá en **Sí** para **Unidad de negocio** y **Departamento**. La opción **Mantener dimensiones financieras de origen** se establecerá en **No** para **Centro de costes**, y el valor seleccionado será cada centro de coste respectivo al que esté asignando. Si hay tres centros de costes para asignar, entonces se crearían tres registros de términos de asignación. La única diferencia entre cada término de asignación es el centro de costes que se especifica en la cuenta contable de destino.

## <a name="create-an-allocation-term-on-a-main-account"></a>Crear un término de asignación en una cuenta principal

1. En el **Panel de exploración**, vaya a **Módulos > Contabilidad general > Plan contable > Cuentas > Cuentas principales**.
2. En la lista, busque y seleccione el registro deseado.
3. En la ficha desplegable **Entidad jurídica**, seleccione **Agregar**.
4. Seleccione **Empresa** y luego seleccione **Agregar**.
5. Active la casilla **Asignación**.
6. Seleccione **Condiciones de asignación**.
7. Seleccione **Editar** para modificar el registro predeterminado o seleccione **Nuevo** para agregar un registro.
8. En el campo **Porcentaje**, indique el porcentaje de transacciones de asientos que desea asignar.
9. En la ficha desplegable **Dimensión financiera de origen**, en **Criterios de selección** para cada dimensión financiera, seleccione una opción.
    - Si selecciona **Específico**, luego seleccione el valor de la dimensión financiera en el cuadro desplegable de la derecha.
    - Si selecciona **Inespecífico**, no se requiere información adicional para la dimensión financiera.
10. En la ficha desplegable de la cuenta **Libro mayor de destino**, en el campo **Para la cuenta**, seleccione la cuenta principal donde desea asignar el porcentaje de la transacción del asiento.
11. En **Mantener dimensiones financieras de origen** para cada dimensión financiera, seleccione una opción.
    - Si selecciona **No**, luego seleccione el valor de la dimensión financiera en el cuadro desplegable a la derecha donde desea asignar la transacción del comprobante.
    - Si selecciona **Sí**, entonces no se requiere información adicional. El sistema mantendrá el valor en el comprobante original al publicar la asignación.
12. Repita los pasos 7 a 11 para cada asignación adicional. La suma de todas las asignaciones se indica en el campo **Porcentaje total**. Esta cantidad no puede exceder de 100.
13. Cierre todas las páginas.

>[!NOTE] 
> Opcionalmente puede usar el botón **Copiar** para duplicar la asignación seleccionada.

Cuando se crea un término de asignación para una cuenta principal, el sistema contabilizará automáticamente un nuevo comprobante cuando se publique un comprobante que coincida con las dimensiones financieras de origen en los términos de asignación.
