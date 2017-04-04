---
title: "Visión general de conciliación bancaria avanzada"
description: "La conciliación bancaria avanzado le permite importe extractos bancarios electrónicos automáticamente y que los ha conciliado con transacciones bancarias en Microsoft Dynamics 365 para las operaciones.  En este artículo se explicará la configuración de los procesos de conciliación."
author: twheeloc
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 98303
ms.assetid: ae071f04-f038-4b17-812d-0a241ed15521
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 3b16ef53f9fb57a6663db0be1f7e0a57471db2fb
ms.openlocfilehash: c2fc9e858f61d7d0122393bbf306ba64ac3659b8
ms.lasthandoff: 03/31/2017


---

# <a name="advanced-bank-reconciliation-overview"></a>Visión general de conciliación bancaria avanzada

La conciliación bancaria avanzado le permite importe extractos bancarios electrónicos automáticamente y que los ha conciliado con transacciones bancarias en Microsoft Dynamics 365 para las operaciones.  En este artículo se explicará la configuración de los procesos de conciliación.  

Existen varios piezas que deben estar configurados antes de utilizar la funcionalidad avanzada de conciliación bancaria. Para obtener más información sobre la importación del extracto bancario de creación, consulte configuración [el proceso de importación] del extracto bancario (setup-advanced-bank-reconciliation-import-process.md).  Los requisitos para la configuración del proceso de conciliación detallados son continuación.

## <a name="transaction-codes"></a>Códigos de transacción
Los códigos de transacción se pueden usar como parte de las reglas coincidentes de conciliación bancaria.  Los códigos de transacción ayudarán a coincidir sólo los mismos tipos de transacciones entre las Dynamics 365 para las operaciones y el extracto bancario.  Para hacer este tipo de coincidencia, es necesario definir los tipos de transacción utilizados para las transacciones bancarias de las Dynamics 365 para las operaciones continuación, asigna los tipos a los códigos de transacción del extracto usados por el banco.  Definen en los tipos de transacción para Dynamics 365 para las transacciones bancarias de las operaciones en ** tipo de transacción bancaria ** la página.  Aquí también se define la cuenta principal que se utilizará para los registros asociadas a ese tipo de transacción. 

Una vez que sus Dynamics 365 para los códigos de transacciones bancarias de las operaciones se definen a continuación, asigna a los códigos de transacciones utilizados en sus extractos bancarios electrónicos.  Este proceso de asignación se realiza mediante ** asignación del código de transacción ** la página.  La asignación del código de transacción se completa de forma independiente para cada cuenta bancaria.

## <a name="matching-rules-and-matching-rule-sets"></a>Reglas de coincidencia y conjuntos de reglas de coincidencia
Las reglas coincidentes le permiten definir los criterios para la conciliación automática entre Dynamics 365 para las transacciones bancarias de las operaciones y las transacciones del extracto bancario.  La configuración de reglas coincidentes es ** realizado en las reglas coincidentes de conciliación ** página.  Para obtener más información, consulte [las reglas coincidentes] de conciliación bancaria de la configuración (setup-bank-reconciliation-matching-rules.md). 

Los conjuntos de la regla coincidente para definir un grupo de reglas coincidentes que se ejecuten a en pedido durante el proceso de conciliación bancaria.  Los conjuntos de la regla coincidente en ** los conjuntos de la regla coincidente de conciliación ** la página.

## <a name="cash-and-bank-management-parameters"></a>Parámetros de gestión de efectivo y bancos
Hay varios parámetros específicos en el proceso de conciliación bancaria ** avanzado en los parámetros de gestión de efectivo y bancos ** la página.  ** Importe de línea de extracto de presentación en débito/crédito ** los cambios la vista de los importes en ** extracto bancario ** la página.  Si se selecciona esta opción, los importes de transacción del extracto bancario se mostrarán en columnas independientes de crédito y débito.  Si no se selecciona, los importes de transacción del extracto bancario se mostrarán en un solo importe de la columna con el signo adecuado. 

Las opciones de validación establecidas en la página de los parámetros selecciones anulan las establecidas en reglas coincidentes.  Por ejemplo, no puede manual o automáticamente los documentos de la coincidencia más allá de la diferencia de la fecha establecida en la página de los parámetros.  Además, si se selecciona la opción ** valide la asignación del tipo de transacción **, los tipos de transacción deben asignarse entre Dynamics 365 para las operaciones transacción bancaria y la transacción del extracto bancario para las transacciones manualmente o automáticamente coincidan. 

También debe configurar las secuencias numéricas necesarias en ** los parámetros de gestión de efectivo y bancos ** la página.  ** En las secuencias numéricas ** la ficha, establezca los códigos de secuencia numérica para la descarga ** identificador, identificador de la instrucción, conciliar el identificador, y la conciliación bancaria ** las referencias.

## <a name="bank-account-reconciliation-options"></a>Opciones de conciliación de cuenta bancaria
Debe habilitar la conciliación bancaria avanzado para la cuenta bancaria.  Existen varias opciones adicionales disponibles en ** cuenta bancaria ** la página una vez que se habilita la funcionalidad avanzada de conciliación bancaria. 

** Use los extractos bancarios como confirmación de pago electrónico ** la funcionalidad integrada la funcionalidad de conciliación bancaria con los estados de pago electrónico.  Cuando se habilita esto, un documento bancario se creará automáticamente para el estado de pago electrónico se establece en ** ** registrado.  Además, deben actualizar el estado de un pago electrónico de ** registrado ** a ** recibido ** después de que se coincida con el pago, conciliado, y enviado. 

** Nombre de cuenta del banco en instrucciones ** el campo es el nombre utilizado para la cuenta bancaria en sus extractos bancarios electrónicos.  Dicho nombre al determinar qué transacciones a importar para una cuenta bancaria de un extracto que puede contener información para varias cuentas bancarias. 

La opción ** concilie tras importar ** validará automáticamente el extracto bancario, crea una nueva conciliación bancaria y hoja de cálculo, y ejecutar el conjunto predeterminado de la regla coincidente.  Esta funcionalidad automatiza el proceso hasta el punto de las transacciones que se deben conciliadas manualmente.  El valor de la cuenta bancaria predeterminado será el importar.


