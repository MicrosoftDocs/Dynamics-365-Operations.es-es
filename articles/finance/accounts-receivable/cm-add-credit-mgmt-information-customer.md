---
title: Agregar información de administración de crédito para los clientes
description: En este tema se explica cómo agregar información de administración de crédito para un cliente.
author: mikefalkner
manager: AnnBe
ms.date: 09/04/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: roschloma
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: mfalkner
ms.search.validFrom: ''
ms.dyn365.ops.version: ''
ms.openlocfilehash: 872d129494b815d6dbf88cc9f84b4e80723a8d6d
ms.sourcegitcommit: 1d5a4f70a931e78b06811add97c1962e8d93689b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/13/2020
ms.locfileid: "3124332"
---
# <a name="add-credit-management-information-for-customers"></a>Agregar información de administración de crédito para los clientes

[!include [banner](../includes/banner.md)]

Después de configurar los parámetros que controlan la administración de crédito, puede agregar más detalles para cada cliente. Estos detalles controlan los procesos de administración de crédito y también proporcionan información adicional que ayuda a los miembros del equipo de cobros a administrar los clientes.

## <a name="customer-information"></a>Información cliente

Puede agregar los detalles de clientes en la pestaña **Crédito y cobros** de la página **Todos los clientes** (**Clientes \> Clientes \> Todos los clientes**).

1. Establezca la opción **Límite de crédito ilimitado** en **Sí** si el cliente no debe estar limitado por pruebas de límite de crédito.
2. Establezca la opción **Excluir de administración de crédito** en **Sí** para excluir al cliente de las acciones que suelen producirse durante los procesos de administración de crédito.
3. Seleccione el grupo de administración de crédito para el cliente.
4. Para calcular el límite de crédito en la divisa del cliente, en el campo **Límite de crédito en la divisa del cliente**, introduzca el límite de crédito del cliente. El límite de crédito en la divisa de la empresa se convertirá con los tipos de cambio definidos por el tipo de cambio del límite de crédito que se selecciona en los parámetros de administración de crédito.
5. En el campo **Última fecha de revisión**, introduzca la fecha en la un administrador de crédito revisó por última vez el límite de crédito del cliente.
6. En el campo **Próxima fecha de revisión programada**, introduzca la fecha en la que está programada una revisión y actualización del crédito del cliente.
7. En el campo **Límite de crédito elegible**, introduzca el límite de crédito más alto que se puede asignar al cliente, en función de la revisión del historial de crédito de ese cliente. El límite de crédito elegible puede diferir del límite de crédito que se muestra en la ficha desplegable **Crédito y cobros**.
8. En el campo **Divisa del límite de crédito elegible**, introduzca la divisa del límite de crédito elegible.
9. En el campo **Fecha del límite de crédito elegible**, introduzca la fecha en la que se creó el límite de crédito elegible.
10. En el campo **Estado de la cuenta de crédito**, introduzca el estado de la cuenta de crédito del cliente.
11. En el campo **Razón para el estado**, introduzca el motivo asociado al estado de cuenta.
12. Establezca la opción **Con agencia** en **Sí** para indicar que el cliente está actualmente asignado a una agencia de crédito. La finalidad de este valor es meramente informativa. No se utiliza en ningún proceso de administración de crédito.
13. Seleccione la opción **Título retenido** en **Sí** para indicar que un título está retenido para la empresa. La finalidad de este valor es meramente informativa. No se utiliza en ningún proceso de administración de crédito.
14. En el campo **Fecha de inicio del negocio**, introduzca la fecha en la que el cliente empezó a hacer negocios. Esta información se usa para crear puntuaciones de riesgo.
15. En el campo **Cliente desde**, introduzca la fecha en la que que se procesaron las primeras transacciones para el cliente. Esta información se usa para crear puntuaciones de riesgo.
16. Escriba notas que el equipo de crédito pueda usar para evaluar mejor la solvencia del cliente.

Tenga en cuenta que parte de la información que se muestra en la página **Cliente** es creada por otro proceso:

- El campo **Fecha de vencimiento del límite de crédito** muestra la fecha de vencimiento del límite de crédito. Si no configura este campo, el límite de crédito del cliente no vencerá.
- El campo **Fecha del límite de crédito** muestra la fecha de vencimiento en la que se creó el límite de crédito. Este campo se actualiza cada vez que se ajusta el límite de crédito.
- Los límites de crédito temporales anulan el límite de crédito de un cliente por un período definido. Se utilizan en lugar del límite de crédito para calcular el límite de crédito total. Esta información solo se muestra si hay un límite de crédito activo. Puede agregar límites de crédito temporales a través de ajustes de límite de crédito.
- El campo **Seguros y garantías** muestra el valor total del seguro y las garantías que pueden aumentar el límite de crédito para el cliente.
- El campo **Límite de crédito total** muestra el límite de crédito final para el cliente. El límite de crédito total incluye seguros y garantías, así como límites de crédito temporales.

## <a name="temporary-credit-limits"></a>Límites de crédito temporales

Los límites de crédito temporales anulan los límite de crédito de cliente por un período definido. Puede agregar límites de crédito temporales mediante ajustes de límite de crédito. Los ajustes del límite de crédito permiten a los administradores de crédito actualizar los límites de crédito y las fechas de vencimiento de un solo cliente, un grupo de clientes o todos los clientes, a través de un proceso de contabilización.

Puede crear entradas de ajuste de límite de crédito en la página **Ajustes de límite de crédito** (**Administración de crédito \> Ajustes de límite de crédito \> Ajustes de límite de crédito**).

## <a name="create-insurance-policies-and-guarantees"></a>Crear pólizas de seguro y garantías

Puede crear una o más pólizas de seguro y garantías para cada cliente. Podrá usarlos posteriormente para calcular la exposición de su empresa cuando ofrece crédito a un cliente. Las pólizas de seguro y las garantías también se pueden incluir en el límite de crédito para un cliente.

Puede crear pólizas de seguro y garantías en la página **Todos los clientes** (**Clientes \> Clientes \> Todos los clientes**). Seleccione un cliente que tenga transacciones y, a continuación, en el panel de acciones, en la pestaña **Administración de crédito**, seleccione **Seguro y garantías**.

> [!NOTE]
> En el siguiente procedimiento va a seleccionar una aseguradora o garante de la libreta de direcciones global. Por lo tanto, antes de comenzar este procedimiento, debe asegurarse de que se hayan agregado las aseguradoras y los garantes a la libreta de direcciones global.

1. En el campo **Identificador**, introduzca **Garantía** o **Seguro**.
2. En el campo **Tipo de garantía/seguro**, seleccione uno de los tipos de garantía o seguro que configuró previamente.
3. En el campo **Aseguradora/garante**, seleccione la aseguradora o el garante de la libreta de direcciones global. 
4. Si seleccionó **Seguro** en el campo **Identificador**, en el campo **Tipo de cobertura de póliza**, seleccione uno de los tipos de cobertura que configuró previamente. No puede seleccionar un tipo de cobertura de póliza para una garantía.
5. En el campo **Identificación**, introduzca el identificador de la póliza. Este identificador suele ser un número de póliza.
6. En el campo **Vigencia**, introduzca la fecha de inicio de la póliza de seguro o la garantía.
7. En el campo **Vigencia**, introduzca la fecha de vigencia de la póliza de seguro o la garantía. vence.
8. En el campo **Valor**, introduzca el valor de la póliza de seguro o la garantía. Este valor es el valor total de la póliza.
9. En el campo **Divisa**, seleccione la divisa del valor de la póliza. 
10. En el campo **Actualizar límite de crédito**, especifique un porcentaje entre **0** y **100**. Este porcentaje se aplicará al valor de la póliza y el importe resultante se usará para aumentar el límite de crédito que se usa en los cálculos de límite de crédito. El valor calculado se muestra en **Límite total de crédito, seguros y garantías** en la ficha desplegable **Crédito y cobros** de la página **Clientes**.

    Este es un ejemplo:

    - El límite de crédito (A) es de 100 000.
    - El valor de la póliza (B) es de 50 000.
    - El porcentaje de **Actualizar límite de crédito** (C) es del 50,00.
    
    En este caso, el límite de crédito efectivo es 125 000 (= A + \[B × C\]).

11. Active la casilla **Incluido en la exposición** para reducir el límite de crédito que se utiliza en los cálculos de límite de crédito por el valor total de la póliza. Si esta casilla está activada, el valor que se calcula cuando se especifica el porcentaje de **Actualizar límite de crédito** no se utilizará en los cálculos de límite de crédito.

    Este es un ejemplo:

    - El límite de crédito (A) es de 100 000.
    - El valor de la póliza (B) es de 50 000.
    - El porcentaje de **Actualizar límite de crédito** (C) es del 50,00.

    En este caso, el límite de crédito efectivo es 125 000 (= A + \[B × C\]).
    
    Sin embargo, si activa la casilla **Incluido en la exposición**, se quita el valor de **Actualizar límite de crédito** de 50 000 (= 50,00 por ciento de 100 000), y el valor de exposición es de 75 000 (= A + \[B × C\] - B).
