---
title: Procesar cartas de cobro
description: En este tema se muestra cómo crear, imprimir y registrar cartas de cobro.
author: ShivamPandey-msft
manager: AnnBe
ms.date: 07/01/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CustPosting, CustCollectionLetterNote
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2018-12-01
ms.dyn365.ops.version: 8.1.3
ms.openlocfilehash: 326d9375670cb4f4990a4f7070bf923a28b2c025
ms.sourcegitcommit: a368682f9cf3897347d155f1a2d4b33e555cc2c4
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/08/2019
ms.locfileid: "1867664"
---
# <a name="process-collection-letters"></a>Procesar cartas de cobro

[!include [banner](../../includes/banner.md)]

En este tema se muestra cómo crear, imprimir y registrar cartas de cobro. Esta tarea usa la empresa de demostración USMF.

## <a name="set-up-a-collection-letter-sequence-on-the-posting-profile"></a>Configurar una secuencia de cartas de cobro en el perfil de registro
1. Vaya a **Panel de navegación > Módulos > Crédito y cobros > Configuración > Perfiles de contabilización del cliente**.
2. Haga clic en **Editar**.
3. Seleccione una secuencia de cartas de cobro en la lista desplegable. Si no desea generar cartas de cobro para las transacciones que usan este perfil de contabilización, deje el campo en blanco.  
4. Expanda la pestaña **Restricciones de tablas** para cambiar la forma en la que se procesan las cartas de cobro. Si este campo está establecido en **Sí**, se crearán las cartas de cobro para este perfil de contabilización.  

## <a name="create-collection-letters"></a>Crear cartas de cobro
1. Vaya a **Panel de navegación > Módulos > Crédito y cobros > Carta de cobro > Crear cartas de cobro**.
2. Seleccione los tipos de transacción para los que desee cartas de cobro. Todas las transacciones abiertas de estos tipos se incluirán en el cálculo.  
3. En el campo **Carta de cobro**, seleccione una opción.
4. En el campo **Fecha de la carta de cobro**, especifique la fecha de la carta de cobro.
5. Seleccione un perfil de contabilización si ha cambiado **"Utilizar el perfil de contabilización desde** a **Seleccionar**. Existen dos opciones de perfil de registro:   

   - **Cuenta**: use el perfil de contabilización asignado a la cuenta de cliente para cada nota de interés.   
   - **Seleccionar**: se usa el perfil de contabilización que seleccione en el campo **Perfil de contabilización**.  

6. Expanda la sección **Registros que incluir**.
7. Seleccione **Filtro**.
8. En el campo **Criterios**, especifique un id. de cliente. Por ejemplo, escriba "US-001".
9. Seleccione **Aceptar**.
10. Seleccione **Aceptar**.

## <a name="print-collection-letters"></a>Imprimir cartas de cobro
1. Vaya a **Panel de navegación > Módulos > Crédito y cobros > Carta de cobro > Revisar y procesar cartas de cobro**.
2. En el campo **Estado**, seleccione **Creado**.
3. En el campo **Impreso**, seleccione **No se ha impreso**.
4. Seleccione **Imprimir**.
5. Seleccione **Nota de la carta de cobro**.
6. En la sección **Parámetros**, especifique la fecha límite para los registros.
7. Expanda la sección **Registros que incluir** y especifique los detalles de la nota de la carta de cobro.
8. Seleccione **Aceptar** para imprimir la carta de cobro.
9. Registre la carta de cobro.

    1. Seleccione **Registrar**.
    1. Escriba la fecha de registro para la carta de cobro.
    1. Expanda la sección **Registros que incluir**.
    1. Seleccione **Aceptar**.
    1. En el campo **Estado**, seleccione **Registrado**.
    1. En el campo **Impreso**, seleccione una opción.

## <a name="control-collection-letters-at-the-customer-level"></a>Supervisar las cartas de cobro a nivel de cliente
También puede configurar las cartas de cobro a nivel de cliente para seguir el código de carta de cobro para cada transacción, pero el procesamiento de la carta de cobro se basará en un único nivel de la carta de cobro que se almacena para el cliente. La única carta de cobro contendrá todas las transacciones que están vencidas para el cliente. Dado que los días de gracia ahora se siguen a nivel de cliente, la siguiente carta de cobro no se registrará hasta que el número de días de gracia haya pasado para la carta de cobro siguiente de la secuencia, aunque las transacciones vencen después de que la última carta de cobro se haya enviado. Esta opción reduce el número de cartas de cobro que enviará por cliente. 

### <a name="set-up-the-customer-to-control-collection-letters-at-the-customer-level"></a>Configurar el cliente para que controle las cartas de cobro a nivel de cliente
1.  Vaya a **Panel de navegación > Módulos > Crédito y cobros > Configuración > Parámetros de clientes** y seleccione la pestaña **Cobros**. 
2.  Cambie el valor de **Cree la carta de cobro por** a **Cliente**. 
3.  Vaya a **Panel de navegación > Módulos > Crédito y cobros > Carta de cobro > Revisar y procesar cartas de cobro**. Solo una carta de cobro se generará para un cliente con todas las transacciones vencidas.

## <a name="ignore-payments-and-credit-memos-when-calculating-the-collection-letter-code"></a>Omitir pagos y notas de crédito al calcular el código de carta de cobro
Si incluye pagos y notas de crédito en las transacciones que se incluirán en las cartas de cobro, puede hacer que haya pagos o notas de crédito que desencadenen una carta de cobro. Puede controlar la manera en que los pagos y los notas de crédito controlan el código de la carta de cobro modificando el valor del parámetro **Omitir pagos y notas de crédito al calcular el código de carta de cobro**. 

Para omitir pagos y notas de crédito al calcular el código de carta de cobro, haga lo siguiente.

1. Vaya a **Panel de navegación > Módulos > Crédito y cobros > Configuración > Parámetros de clientes** y haga clic en la pestaña **Cobros**. 
2. Cambie el valor de **Omitir pagos y notas de crédito al calcular el código de carta de cobro** a **Sí**.
