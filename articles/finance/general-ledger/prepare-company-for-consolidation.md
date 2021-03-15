---
title: Preparar una entidad jurídica para el proceso de consolidación
description: En una consolidación, se recopilan transacciones de varios conjuntos de cuentas de entidades jurídicas en un único conjunto de cuentas de entidades jurídicas. Este tema explica cómo preparar una entidad jurídica para una consolidación.
author: jinniew
manager: AnnBe
ms.date: 10/30/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: jiwo
ms.search.validFrom: 2018-10-30
ms.dyn365.ops.version: 8.0.1
ms.openlocfilehash: f6fce69724945448f961769dd383d1047a5d13c4
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/15/2021
ms.locfileid: "4990318"
---
# <a name="prepare-a-legal-entity-for-the-consolidation-process"></a>Preparar una entidad jurídica para el proceso de consolidación

[!include [banner](../includes/banner.md)]

En una consolidación, se recopilan transacciones de varios conjuntos de cuentas de entidades jurídicas en un único conjunto de cuentas de entidades jurídicas. Este tema explica cómo preparar una entidad jurídica para una consolidación.

> [!NOTE]
> Le recomendamos que utilice Management Reporter para Microsoft Dynamics 365 Finance para combinar los resultados financieros de múltiples entidades jurídicas en un formato consolidado. Management Reporter le permite crear informes financieros consolidados en todas las entidades jurídicas, utilizar Excel para importar datos de consolidación de otros orígenes y traducir importes a cualquier número de divisas de notificación sin tener que ejecutar el proceso de consolidación en Dynamics 365 Finance.

Puede imprimir informes, como informes financieros, desde la entidad jurídica consolidada. Sin embargo, no puede usar la entidad jurídica consolidada para las transacciones diarias.

Puede consolidar datos de las entidades jurídicas que usen distintas bases de datos que la entidad jurídica consolidada. Este proceso de consolidación se denomina *consolidación de importación*. Como alternativa, las entidades jurídicas pueden usar la misma base de datos que la entidad jurídica consolidada. Este proceso de consolidación se denomina *consolidación en línea*.

La entidad jurídica consolidada recopila los resultados y los saldos de las filiales. Para preparar una entidad jurídica consolidada para una consolidación, siga estos pasos.

1. Vaya a **Contabilidad general \> Configuración \> Organización \> Entidades jurídicas**.
2. Seleccione **Nuevo** para crear la entidad jurídica que va a consolidar.
3. Active la casilla **Usar para proceso de consolidación financiera** y, a continuación, introduzca la información sobre la entidad jurídica consolidada. Asegúrese de introducir esta información exactamente como desea que aparezca en los informes financieros para la entidad jurídica consolidada.
4. Cierre la página.
5. Seleccione la entidad jurídica consolidada en el campo de la esquina superior derecha de la página y, a continuación, seleccione **Aceptar**.
6. Vaya a **Contabilidad general \> Configuración \> Contabilidad**.
7. Seleccione el plan de cuentas, el calendario fiscal, la divisa de contabilidad, una divisa de notificación opcional y el tipo de cambio predeterminado para la entidad jurídica consolidada. 
8. Vaya a **Contabilidad general \> Configuración \> Divisa \> Tipos de cambio de divisas**.
9. Configure los tipos de cambio de divisa en períodos relevantes para las divisas de las entidades jurídicas filiales.
10. Cierre la página.
11. Si la entidad jurídica consolidada tiene filiales que utilicen las divisas extranjeras, siga estos pasos:

    1. Vaya a **Contabilidad general \> Configuración \> Registro \> Cuentas para transacciones automáticas**.
    2. En el campo **Tipo de registro**, seleccione una cuenta apropiada:

        - Si la entidad jurídica tiene subsidiarias extranjeras que son financiera u operativamente interdependientes con la entidad jurídica principal, seleccione una cuenta apropiada para el tipo de registro **Cuenta de pérdidas y ganancias para las diferencias de consolidación**.
        - Si está consolidando una filial que sea financieramente y operacionalmente independiente de la entidad jurídica principal, o una entidad jurídica que contenga los resultados de varias filiales que sean financieramente y operacionalmente independientes de la entidad jurídica principal, y si utiliza métodos de conversión para consolidar los datos, seleccione una cuenta adecuada para el tipo de registro **Cuenta de saldo para diferencias de consolidación**.

    3. En el campo **Cuenta principal**, seleccione las cuentas principales que deben usarse para los ajustes de revalorización de divisa extranjera.
    4. Cierre la página.

    Si crea la entidad jurídica consolidada previamente en un período, puede revalorizar los importes en divisa extranjera mientras que los tipos de cambio cambian durante el período de consolidación.

Ya está configurada la entidad jurídica consolidada para el trabajo periódico **Consolidar**. Puede realizar una consolidación de importación o una consolidación en línea.

- Para hacer una consolidación de importación, vaya a **Contabilidad general \> Periódico \> Consolidar \> Consolidar \[Importar de\]**.
- Para realizar una consolidación en línea vaya a **Contabilidad general \> Periódico \> Consolidar \> Consolidar \[En línea\]**.

> [!NOTE]
> Para poder procesar la consolidación, debe preparar las entidades jurídicas filiales para la consolidación. Para obtener más información, consulte [Configurar una entidad jurídica filial para la consolidación](set-up-subsidiary-company-for-consolidation.md).


[!INCLUDE[footer-include](../../includes/footer-banner.md)]