---
title: Espacio de trabajo para la gestión bancaria
description: Este artículo proporciona información acerca del espacio de trabajo Gestión bancaria. Este espacio de trabajo muestra la información relacionada con las cuentas bancarias de la empresa.
author: angelad116
ms.date: 01/12/2018
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: BankTreasurerWorkspace
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: angelading
ms.search.validFrom: 2017-06-30
ms.dyn365.ops.version: July 2017 update
ms.openlocfilehash: f9880928281e704edcd24a75f99d4562761b7c82
ms.sourcegitcommit: 0b7a034e644f4d93fe55c7baca5a3f89dbe56898
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/14/2022
ms.locfileid: "9151563"
---
# <a name="bank-management-workspace"></a>Espacio de trabajo para la gestión bancaria

[!include [banner](../includes/banner.md)]

El espacio de trabajo **Gestión bancaria** muestra la información relacionada con las cuentas bancarias de la empresa. Este espacio de trabajo incluye un vista **Resumen** y una página **Análisis** . La vista **Resumen** muestra las fichas del resumen, la información de cuentas bancarias, un gráfico de saldos e información relacionada. La página de **Análisis** utiliza las capacidades de Microsoft Power BI para mostrar representaciones visuales relacionadas con los saldos de la cuenta bancaria.

## <a name="summary-view"></a>Vista de resumen

### <a name="summary"></a>Resumen

Los mosaicos en la sección **Resumen** ofrecen una visión general de las cuentas bancarias y acceso rápido a las páginas que utiliza con mayor frecuencia. La información de conciliación bancaria es específica de las funcionalidades avanzadas de conciliación bancaria. La información solo se incluye para aquellas cuentas bancarias que tengan la opción **Conciliación bancaria avanzada** establecida en **Sí** en la página **Cuenta bancaria**. En la sección **Resumen** , puede importar archivos bancarios electrónicos para las cuentas bancarias en todas las entidades jurídicas.

### <a name="bank-accounts"></a>Cuentas bancarias

Cada cuenta bancaria en la entidad jurídica se representa mediante una tarjeta en la sección **Cuentas bancarias**. Se muestran los saldos actuales y puede explorar en profundidad las transacciones que componen dicho importe de saldo de resumen. El importe de **Transacciones puente** también le permite explorar en profundidad las transacciones que componen dicho importe de resumen. Las transacciones puente son las transacciones pendientes que se han registrado con la funcionalidad de puente, pero que aún no se han borrado. El importe de **Saldo pendiente** es el saldo actual menos las transacciones puente o pendientes.

La tarjeta también muestra cuando la cuenta bancaria se concilió por última vez. Se muestra esta información solo si la conciliación bancaria avanzada está habilitada para la cuenta bancaria.

### <a name="balance"></a>Saldo

El gráfico **Saldo** muestra la información histórica del saldo de la cuenta bancaria seleccionada en la sección **Cuentas bancarias** o un resumen de la información histórica de saldo para todas las cuentas bancarias en la entidad jurídica. Esta información está disponible para varios períodos: la semana actual, el mes actual, el año actual, los últimos cinco años y todos los períodos (el historial completo de la cuenta bancaria). 

Si está viendo el gráfico **Saldo** para una sola cuenta bancaria, los saldos históricos se muestran en la divisa de la cuenta bancaria. Si está viendo el gráfico para todas las cuentas bancarias en la entidad jurídica, los saldos históricos se muestran en la divisa de contabilidad.

La información sobre cuándo los datos se actualizaron por última vez aparece en la parte superior del gráfico. Puede actualizar los datos según necesite.

### <a name="related-information"></a>Información relacionada

En la sección **Información relacionada**, puede abrir la página **Diario general** para completar las transferencias bancarias. También puede abrir rápidamente las páginas **Transacciones bancarias** y **Transacciones puente** .

## <a name="analytics-view"></a>Vista de análisis

La página **Análisis** proporciona métricas importantes sobre las cuentas bancarias de la empresa actual. Las visualizaciones siguientes están disponibles en la página:

-   Saldo bancario total en divisa del sistema
-   Saldo por entidad jurídica
-   Saldo real de hoy frente al saldo previsto en la divisa de la cuenta bancaria
-   Saldo por cuenta bancaria
-   Saldo por divisa

Puede ver los análisis del banco en todas las empresas en el espacio de trabajo **Visión general del efectivo para todas las empresas**. Para obtener más información, consulte [Contenido de Power BI de visión general de efectivo](Cash-Overview-Power-BI-content.md).


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
