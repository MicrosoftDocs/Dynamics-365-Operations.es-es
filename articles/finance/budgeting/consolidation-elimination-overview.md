---
title: Visión general de consolidación y eliminación
description: En este artículo se proporciona información general sobre el proceso de consolidación y eliminación. Incluye respuestas a algunas preguntas frecuentes.
author: aprilolson
manager: AnnBe
ms.date: 01/11/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: LedgerConsolidate
audience: Application User
ms.reviewer: roschlom
ms.custom: 13151
ms.assetid: 9d8f55cb-b2cf-4e01-89cf-0e21f5c8ae1f
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: ee029e6cf1f271c5839e8d0dc1b1e4b7f91fb9a2
ms.sourcegitcommit: f51ef395f0c0cb2203ce26b4091bbf0296e7916e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/05/2021
ms.locfileid: "5120488"
---
# <a name="consolidation-and-elimination-overview"></a>Visión general de consolidación y eliminación

[!include [banner](../includes/banner.md)]

En este artículo se proporciona información general sobre el proceso de consolidación y eliminación. Incluye respuestas a algunas preguntas frecuentes.

A consolidar datos, los resultados financieros para varias compañías filiales se combinan en resultados para una compañía única y consolidada. Las filiales pueden encontrarse en diferentes versiones o sistemas, es posible que no sean de propiedad completa y pueden usar distintas divisas. Hay varias opciones para consolidar datos:

-   **Consolidar en línea**: esta opción consolida los saldos diarios por las cuentas y las dimensiones seleccionadas, y los guarda en una empresa de consolidación.
-   **Informes financieros**: esta opción permite la consolidación de transacciones y de saldos, y se puede generar en cualquier momento. Se puede crear varios niveles de jerarquías y se pueden ver varias divisas de notificación.
-   **Consolidar con importación**: esta opción importa saldos en una empresa de consolidación.
-   **Exportación de saldos de compañía**: esta opción proporciona un archivo de exportación de saldos de empresa. El archivo se puede importar a continuación en otros casos o sistemas. Los informes financieros también se pueden usar para exportar los saldos a un archivo de Microsoft Excel.

Las eliminaciones se pueden notificar de varias formas:

-   Las reglas de eliminación se pueden configurar en el sistema y después procesar durante el proceso de consolidación o mediante una propuesta de eliminación. Las reglas se pueden registrar a cualquier empresa que tengan la opción **Usar para el proceso de eliminación financiera** seleccionada en la configuración de la entidad jurídica.
-   Se puede crear y usar una empresa independiente para determinar y registrar manualmente transacciones de eliminación. Esta empresa se puede usar en el proceso de consolidación o en informes financieros.
-   Las cuentas y las dimensiones financieras que se usan para determinar la actividad de empresas vinculadas se pueden filtrar por una definición de fila o de columna en los informes financieros, y se pueden utilizar capacidades completas. Una columna o una fila calculada se puede usar a continuación para quitar las cuentas y las dimensiones financieras del total consolidado.

Hay muchos escenarios de consolidación y cada método puede administrar los escenarios de diferentes maneras.

## <a name="frequently-asked-questions"></a>Preguntas frecuentes
1.  Prefiero registrar eliminaciones en una base de datos. ¿Cuáles son mis opciones?

Tiene varias opciones. Puede usar la opción **Consolidar en línea** e incluir eliminaciones durante el proceso o como propuesta. Las transacciones se registrarán en la empresa de consolidación. Como alternativa, puede tener una empresa independiente en la que crea manualmente las eliminaciones y, a continuación, usar dicha empresa en informes financieros o en el proceso de consolidación.

2.  Necesitamos nuestros resultados consolidados en varias divisas de notificación.

La opción **Informes financieros** tiene divisas de notificación ilimitadas. Los datos se traducen durante la generación de informes, en función del tipo de cambio y del método de conversión de la divisa que se establecen en la cuenta principal. Sin embargo, dado que la opción **Consolidar en línea** solo tiene una divisa de notificación, se requiere una empresa consolidada para cada divisa de notificación si usa esa opción. La opción **Informes financieros** es el método recomendado.

3.  Quiero ver el detalle de transacciones para cada empresa.

La opción **Informes financieros** es la solución, ya que el detalle de transacciones se puede ver para tantas empresas como se incluyen en la definición del organigrama.

4.  Estamos usando la planificación o el control presupuestarios, y se deben consolidar.

La opción **Informes financieros** es la solución para consolidar los datos de planificación presupuestaria o de control presupuestario.

5.  Nuestras filiales se extienden por todo el mundo y tienen varios planes de cuentas. ¿Cuál es el mejor método para consolidar nuestros datos?

Tiene varias opciones cuando debe administrar varios planes de cuentas. Puede usar la opción **Consolidar en línea** y, a continuación, elegir usar la cuenta de consolidación que está definida en la cuenta principal o un grupo de cuentas de consolidación. También puede usar la opción **Informes financieros**, incluir varios vínculos a las dimensiones financieras de la definición de filas y asignar las cuentas.

6.  Requerimos varios niveles de consolidación. Es decir, primero consolidamos todas nuestras filiales europeas a la libra británica (GBP). Después, tomamos esos datos y traducimos el importe consolidado a dólares americanos. ¿Cómo podemos hacer esto?

Cuando se requieren varios niveles de consolidación y se usan distintas divisas en cada nivel, debe usar la opción **Consolidar en línea**. Se deben crear varias empresas de consolidación que difieran en sus divisas de contabilidad y notificación. La consolidación se debe ejecutar varias veces. La opción **Informes financieros** siempre convierte de la divisa de contabilidad de cada empresa de origen a la divisa seleccionada.

7.  Tenemos filiales en otro sistema. ¿Cómo podemos consolidarlas?

Utilice la opción **Consolidar con importación** para llevar los saldos a una empresa de consolidación.

8.  Algunas de nuestras filiales no son de propiedad completa. ¿Cuál es el mejor método para consolidarlas?

Tiene varias opciones para las filiales de propiedad parcial. Mediante la opción **Informes financieros**, puede definir una definición del organigrama y la propiedad. También puede usar una fila o columna calculada para representar el importe de propiedad parcial. Puede mostrar incluso el interés minoritario como su propia fila de un informe. También puede usar la opción **Consolidar en línea**. La pestaña **Entidades jurídicas** tiene una columna **Propiedad**, donde puede definir el porcentaje propiedad de la empresa matriz.

9.  Nuestra organización debe mostrar consolidaciones por unidad de negocio o desea usar las jerarquías organizativas.

La opción **Informes financieros** es la solución. Las jerarquías organizativas que tienen entidades jurídicas o dimensiones financieras en ellas se pueden notificar en Informes financieros. También puede crear sus propias jerarquías multinivel mediante una definición del organigrama que tenga una combinación de entidades jurídicas y valores de dimensión.

10. Tenemos más de una instancia del sistema.

Puede consolidar los datos con la opción **Exportación de saldos de compañía** para exportar desde una instancia y, a continuación, usar la opción **Consolidar con importación** en la otra instancia.

11. ¿Puedo hacer una consolidación con mi presupuesto en estado **BORRADOR**? 
            
No podrá procesar ni completar sus presupuestos en la empresa de consolidación. Recomendamos utilizar Financial Reporting para consolidar los borradores de presupuestos.

Para obtener más información, consulte [Revalorización de divisa en una empresa de consolidación](../general-ledger/currency-revaluation-consolidation-company.md).


