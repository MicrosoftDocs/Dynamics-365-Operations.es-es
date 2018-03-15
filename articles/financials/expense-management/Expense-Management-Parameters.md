---
title: "Parámetros de gestión de gastos"
description: "Los siguientes parámetros controlan el comportamiento en Gestión de gastos."
author: KimANelson
manager: AnnBe
ms.date: 01/12/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: TrvParameters
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: knelson
ms.search.validFrom: 2017-06-30
ms.dyn365.ops.version: July 2017 update
ms.translationtype: HT
ms.sourcegitcommit: 92a52646063c145d733b9d2960253004e8eab80a
ms.openlocfilehash: 2b3a384a3b9be686b10ce1f181664b0b9bbe9969
ms.contentlocale: es-es
ms.lasthandoff: 03/05/2018

---

# <a name="expense-management-parameters"></a>Parámetros de gestión de gastos

[!include[banner](../includes/banner.md)]

-----------------------------

Los parámetros controlan el comportamiento general en Gestión de gastos.

### <a name="general"></a>General

| **Campo**                                                | **Descripción**                                                 |
|----------------------------------------------------------|---------------------------------------------------------------------|
| **Tarifa estándar de kilometraje**                             | Especifique la tasa de reembolso para los gastos de kilometraje. La tasa se multiplica por el kilometraje especificado en el gasto para calcular el importe reembolsado para los gastos de viaje.                       |
|**Gastos personales pagados por**                             | Seleccione la persona responsable de pagar los importes de la transacción de tarjeta de crédito clasificados como personales.                                                                                                     |
|**Mostrar todo el informe de gastos al volver**               | Seleccione esta opción para mostrar todos los gastos de un informe de gastos cuando vea los detalles del documento original de un asiento específico generado cuando el informe de gastos se registró.              |
|**La autorización previa del viaje es obligatoria**                 | Seleccione esta opción para solicitar que se envíe y se apruebe una solicitud de viaje para que un empleado pueda enviar un informe de gastos.                                                                    |
|**Permitir la edición de distribuciones antes del registro**            | Seleccione si las distribuciones de un informe de gastos se pueden editar antes del registro.                                                                                                                 |
|**Evaluar directivas de gestión de gastos**                     | Seleccione en qué momento se evalúan los gastos para determinar si se ha infringido una directiva de gastos. Los gastos se pueden comprobar para saber si se han producido infracciones cuando se especifica y se guarda la entrada de gastos o cuando el gasto se envía para su aprobación. Las reglas de directivas para los recibos obligatorios se comprobarán cuando se guarde la línea de gastos.                   |
|**Permitir líneas de gastos de empresas vinculadas**                         | Seleccione si desea permitir la entrada de gastos de otras entidades jurídicas en un informe de gastos.                                                                                                          |
|**Permitir la edición del tipo de cambio para los gastos de las tarjetas de crédito** | Seleccione esta opción para permitir que el usuario edite el tipo de cambio para los gastos de tarjeta de crédito importados.                                                                        |
|**Campos de jerarquía de varios niveles para mostrar**                  | Seleccione qué campos del aprobador se mostrarán cuando se establezca el tipo de asignación del flujo de trabajo de informes de gastos para que sea jerarquía y la selección de jerarquía se establece para usar la jerarquía de aprobación de varios niveles de gastos. Cuando la jerarquía de varios niveles de aprobación se usa para el flujo de trabajo, los campos seleccionados se muestran y se pueden editar en el informe de gastos. |
|**Escribir el número de tarjeta de crédito del empleado (actualización de julio de 2017)**     | Seleccione si se puede especificar y guardar un número de 15 o 16 caracteres en el campo **Id. de tarjeta** en la página **Tarjetas de crédito** de un empleado.                                                                          |

### <a name="financial"></a>Financiero

| **Campo**                                                            | **Descripción**     |
|----------------------------------------------------------------------|------------------------------------|
|**Nombre del diario contable**                                         | Seleccione el nombre del diario contable en el que se registran los informes de gastos aprobados.            |
|**Habilitar devolución de impuestos de gastos**                                  | Seleccione esta opción para habilitar la devolución de impuestos de gastos para los gastos aptos. Esta opción no puede habilitarse si se han habilitado las reglas de IVA de importación e impuestos.      |
|**Registrar anticipos inmediatamente**                                     | Seleccione esta opción para publicar un anticipo aprobado si el proceso para pagar y transferir ha finalizado. Si esta opción no está seleccionada, el proceso para pagar y transferir generará un diario general sin registrar. |
|**Fecha de contabilidad correcta durante el registro**                             | Seleccione esta opción para actualizar la fecha de contabilidad al registrar gastos si el período actual está en espera o cerrado. La fecha de contabilidad se establecerá en el siguiente período abierto.   |
|**Permitir la agrupación de transacciones en función de la cuenta de contrapartida especificada en el método de pago**      | Seleccione esta opción para resumir las transacciones de gastos de un informe de gastos, en función de la cuenta de contrapartida especificada en el método de pago para los gastos.   
|**Impuesto incluido**                                                   | Seleccione esta opción para incluir los impuestos en el importe de gastos de forma predeterminada.             |
|**Liberar reservas de gastos de pedidos de viaje en proceso de cierre**            | Active esta opción para liberar fondos con reserva de gasto cuando se cierra una solicitud de viaje aprobada.                                                                                   |
|**Permitir el envío de solicitud de viaje en saturación de presupuesto para registro presupuestario y presupuesto de proyecto** | Seleccione esta opción para permitir que los empleados envíen solicitudes de viaje para su aprobación que superen el presupuesto permitido establecido en registro de presupuesto o el presupuesto permitido para un proyecto.            |
|**Permitir el envío de un informe de gastos en saturación de presupuesto para registro presupuestario y presupuesto de proyecto**    | Seleccione esta opción para permitir que los empleados envíen informes de gastos para su aprobación que superen el presupuesto permitido establecido en registro de presupuesto o el presupuesto permitido para un proyecto.                |
|**Permitir la aprobación de un informe de gastos en saturación de presupuesto solo para registro presupuestario**                | Active esta opción para permitir que los aprobadores aprueben informes de gastos que superen el presupuesto permitido que se ha establecido en el registro de presupuesto.                                                                       |

### <a name="per-diem"></a>Dietas

| **Campo**                             | **Descripción**             |
|---------------------------------------|--------------------------------------------------------------------------------------|
|**Horas mínimas para dietas**           | Especifique el número mínimo de horas predeterminado que debe trabajar un empleado por día para que tenga derecho a recibir dietas para gastos relacionados con un viaje.  Este valor solo se usa como valor predeterminado en el campo de las horas mínimas en los niveles de la tabla de dietas.                                                                                      |
|**Porcentaje de comidas**                          | Defina el porcentaje predeterminado de la dieta para las comidas que se usa para el primer y el último día de los gastos relacionados con un viaje, cuando el campo **Calcular reducción de comida por** se establece en **Tipo de comida al día** o **Número de comidas al día**. La jornada laboral del primer y el último día puede ser mas corta que la jornada laboral estándar. Por lo tanto, el importe de las dietas de estos días puede variar con respecto al importe estándar. Si el porcentaje se establece en 0, las deducciones del primer y el último día serán 0,00. |
|**Porcentaje de hotel**                        | Defina el porcentaje predeterminado de la dieta para los hoteles que se usa para el primer y el último día del gasto relacionado con el viaje. La jornada laboral del primer y el último día puede ser mas corta que la jornada laboral estándar. Por lo tanto, el importe de las dietas de estos días puede variar con respecto al importe estándar. Si el porcentaje se establece en 0, las deducciones del primer y el último día serán 0,00.                                              |
|**Otro porcentaje**                        | Defina el porcentaje predeterminado de la dieta para gastos varios que se usa para el primer y el último día del gasto relacionado con el viaje. La jornada laboral del primer y el último día puede ser mas corta que la jornada laboral estándar. Por lo tanto, el importe de las dietas de estos días puede variar con respecto al importe estándar. Si el porcentaje se establece en 0, las deducciones del primer y el último día serán 0,00.                                                                                                     |
|**Reducción en porcentaje para desayuno** | Especifique el importe de reducción de dietas para desayuno. Por ejemplo, si un empleado recibe un desayuno gratuito, puede reducir el importe de la dieta en un 10%.                               |
|**Reducción en porcentaje para almuerzo**    | Especifique el importe de reducción de dietas para almuerzo. Por ejemplo, si un empleado recibe un almuerzo gratuito, puede reducir el importe de la dieta en un 15%.                                       |
|**Reducción en porcentaje para cena**   | Especifique el importe de reducción de dietas para cena. Por ejemplo, si un empleado recibe una cena gratuita, puede reducir el importe de la dieta en un 25%.                                     |
|**Calcular reducción de comida por**         | Seleccione cómo el sistema debe calcular la reducción de la comida en la dieta seleccionando si la reducción se basa en el tipo de comida por viaje o por día, o si la reducción se basa en el número de comidas permitidas por día.|
|**Redondeo de dietas**                  | Seleccione el tipo de redondeo que se usa para los gastos de las dietas. Si selecciona el redondeo normal, los gastos de las dietas que tengan un importe de 0,50 se redondean hacia arriba a 1,00 y los gastos de las dietas que tengan un importe inferior a 0,50 se redondean hacia abajo a 0,00.                                                                                              |
|**Basar cálculo de dietas en**         | Seleccione si un importe de una dieta se basa en un día de calendario o en un período de 24 horas.       |

### <a name="fax-cover-pages"></a>Portadas de fax

| **Campo**                      | **Descripción**            |
|--------------------------------|-----------------------------------------------------------------------------|
| **Instrucciones**                   | Especifique las instrucciones que deben respetar los empleados durante la creación de una portada de fax que se usa para enviar recibos asociados a un informe de gastos. Haga clic en el botón **Traducciones** para escribir el texto en el idioma específico que se mostrará en función del idioma del usuario. |
|**Id. de usuario (información de código de barras)** | Seleccione esta opción para almacenar un identificador único de empleado en el código de barras que se usa en la portada del fax.                 |
|**Código de barras**                      | Seleccione el código de barras que se usa en la portada de fax. Los códigos de barras 39 y 128 se admiten con la gestión de gastos.               |

### <a name="anti-corruption"></a>Evitar daños

| **Campo**                             | **Descripción**      |
|---------------------------------------|------------------------------------------------------------------------|
|**Mostrar atestación para evitar daños**   | Seleccione esta opción para mostrar el texto anticorrupción al crear un nuevo informe de gastos. Las categorías de gastos específicas se pueden habilitar y requerirán que se seleccione la atestiguación anticorrupción en el informe de gastos. Por ejemplo, una categoría de regalo relacionada con un gasto relativo a un funcionario del gobierno puede requerir que el empleado confirme que el gasto respeta la directiva empresarial relacionada con funcionarios del gobierno. |
|**Mensaje para evitar daños destinado al remitente** | Especifique el texto que se mostrará al empleado al crear un nuevo informe de gastos. Haga clic en el botón **Traducciones** para escribir el texto en el idioma específico que se mostrará en función del idioma del usuario.         |
|**Mensaje para evitar daños destinado al aprobador**  | Especifique el texto que se mostrará al aprobador al crear un nuevo informe de gastos. Haga clic en el botón **Traducciones** para escribir el texto en el idioma específico que se mostrará en función del idioma del usuario.        |

