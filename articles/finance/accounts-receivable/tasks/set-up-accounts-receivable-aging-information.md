---
title: Configurar y generar información de vencimiento de clientes
description: Esta guía le ayudará a configurar una definición de período de vencimiento, vencer saldos de cliente y ver los saldos en la lista Saldos vencidos para mostrar la página Cobros.
author: abruer
ms.date: 07/11/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: CustVendReportInterval, CustAgingSnapshot, CustCollectionsPoolsListPage, CustCollections
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: roschlom
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 996fb289c32a1819103fd67ffddc940dfd2870fb
ms.sourcegitcommit: 408786b164b44bee4e16ae7c3d956034d54c3f80
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/05/2021
ms.locfileid: "7753569"
---
# <a name="set-up-and-generate-accounts-receivable-aging-information"></a>Configurar y generar información de vencimiento de clientes

[!include [banner](../../includes/banner.md)]

Esta guía le ayudará a configurar una definición de período de vencimiento, vencer saldos de cliente y ver los saldos en la lista Saldos vencidos para mostrar la página Cobros. Esta grabación usa la empresa de demostración USMF.


## <a name="create-an-aging-period-definition"></a>Crear una definición de período de vencimiento
1. Vaya a **Panel de navegación > Módulos > Crédito y cobros > Configuración > Definiciones de período de vencimiento**.
2. Haga clic en **Nuevo**.
3. En el campo **Definición de período de vencimiento**, escriba un valor.
4. En el campo **Descripción**, escriba un valor.
5. Haga clic en **Agregar abajo** para insertar un nuevo período de vencimiento.
6. En el campo **Período**, escriba la descripción para mostrar en los informes de vencimiento.
7. En el campo **Unidad**, escriba un número.
8. En el campo **Intervalo**, seleccione una opción. El período contable coincide con el período del calendario contable. Los valores de día, semana, mes, trimestre y años definen el tamaño del intervalo del tipo de fecha. Ilimitado selecciona todas las transacciones antes o después del período anterior en función de si es el primer período o el último.  
9. En el campo **Vencimiento**, seleccione una opción.
10. Seleccione el período en la parte superior de la cuadrícula. Actualice la descripción para describir el período más antiguo en la definición de período de vencimiento.
11. En el campo **Período**, escriba la nueva descripción del período de vencimiento.
12. Cierre la página.

## <a name="age-the-balances"></a>Calcular el vencimiento de los saldos
1. Vaya a **Crédito y cobros > Tareas periódicas > Calcular vencimientos de saldos de clientes**.
2. En el campo **Definición de período de vencimiento**, seleccione la definición de período de vencimiento que ha creado.
    + Puede tener una instantánea activa para cada definición de período de vencimiento.  
    + Se procesan todos los clientes de forma predeterminada. Puede usar esta selección para calcular una sola sección de cobros de clientes.  
    + Seleccione la fecha de la transacción que usará para el vencimiento.  
    + Seleccione la fecha “a partir de” para el vencimiento. El valor predeterminado es la fecha actual pero, si cambia este campo a la fecha seleccionada, podrá seleccionar la fecha que desee. Para el procesamiento por lotes, use la fecha de hoy.  
3. Expanda el intervalo **Empresa**. Puede seleccionar las empresas que se incluirán en la instantánea. La empresa actual está seleccionada de forma predeterminada.
4. Haga clic en **Aceptar** para procesar la instantánea. Llevará algún tiempo, así que espere a que desaparezca el control deslizante y compruebe el centro de mensajes para ver si hay algún mensaje.

## <a name="view-the-balances-on-the-aged-balances-list-and-on-the-collection-page"></a>Ver los saldos en la lista de saldos vencidos y en la página de cobros
1. Vaya a **Crédito y cobros > Cobros > Saldos vencidos**. La página de lista muestra el saldo del cliente. El icono de vencimiento muestra el período de vencimiento de la transacción más antigua.  
2. Seleccione un cliente con saldo.
3. Expanda el área del cuadro informativo **Vencimiento** para ver los saldos vencidos. La definición de período de vencimiento para el cuadro informativo se toma de la definición de período de vencimiento predeterminada que se haya especificado en los parámetros. Puede cambiarse mediante el menú Cobrar.  



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
