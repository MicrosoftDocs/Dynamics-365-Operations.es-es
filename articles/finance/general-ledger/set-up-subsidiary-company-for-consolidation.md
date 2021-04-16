---
title: Configurar una entidad jurídica subsidiaria para consolidación
description: Este tema explica cómo trabajar con planes de cuentas para empresas de consolidación.
author: jinniew
ms.date: 10/30/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: jiwo
ms.search.validFrom: 2020-10-31
ms.dyn365.ops.version: 8.0.1
ms.openlocfilehash: 15050310f355ece683b00a00be9552d32aded17b
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/01/2021
ms.locfileid: "5832859"
---
# <a name="set-up-a-subsidiary-legal-entity-for-consolidation"></a>Configurar una entidad jurídica subsidiaria para consolidación

[!include [banner](../includes/banner.md)]

El método utilizado para preparar las cuentas de las filiales para su consolidación depende, en parte, de hasta qué punto la estructura del plan contable en la entidad jurídica filial refleja el de la consolidada.

Antes de iniciar una consolidación como parte del cierre de un período, realice las actividades de preparación para dicho cierre, pero no cierre las cuentas de la filial hasta que se complete la consolidación. Para obtener más información sobre el cierre de los períodos, consulte [Cerrar la contabilidad general al final del período](close-general-ledger-at-period-end.md) y [Cerrar el año fiscal](tasks/close-fiscal-year.md).

> [!NOTE]
>  Le recomendamos que utilice Management Reporter para Microsoft Dynamics 365 Finance para combinar los resultados financieros de múltiples entidades jurídicas en un formato consolidado. Management Reporter le permite crear informes financieros consolidados en todas las entidades jurídicas, utilizar Excel para importar datos de consolidación de otros orígenes y traducir importes a cualquier número de divisas de notificación sin tener que ejecutar el proceso de consolidación en Dynamics 365 Finance.

## <a name="map-subsidiary-main-accounts-to-consolidated-main-accounts"></a>Asignar cuentas principales de filiales a cuentas principales consolidadas

Si el plan contable de la entidad jurídica filial no sigue el de la consolidada, puede asignar las cuentas principales de la filial a las cuentas principales de la entidad jurídica consolidada.

1. En la *entidad jurídica subsidiaria*, vaya a **Contabilidad general \> Configuración** \> **Plan de cuentas \> Plan de cuentas**.
2. Seleccione un plan de cuentas. En la ficha desplegable **Cuentas principales**, seleccione una cuenta principal y, a continuación, seleccione **Editar**.
3. Seleccione cada una de las cuentas principales de la filial que haya que asignar a una cuenta principal consolidada. En la ficha desplegable **General**, en el campo **Cuenta de consolidación**, introduzca la cuenta de la entidad jurídica consolidada a la que se transferirán el saldo o las transacciones de la cuenta principal de la filial seleccionada. Puede especificar la misma cuenta principal consolidada para varias cuentas de filial.

    > [!NOTE]
    > Si los tipos de cuenta principal de las cuentas asignadas de una filial difieren de los de las cuentas de la entidad jurídica consolidada, los valores de las cuentas con un tipo de cuenta principal **Total** se sobrescribirán durante la consolidación.

4. Elabore para la entidad jurídica consolidada informes y estados financieros basados en dimensiones financieras. Siga estos pasos para asignar las dimensiones financieras que se utilizan en las cuentas subsidiarias a las dimensiones financieras de la entidad jurídica consolidada:

    1. En la *entidad jurídica subsidiaria*, vaya a **Contabilidad general \> Configuración \> Dimensiones financieras \> Dimensiones financieras**, seleccione una dimensión financiera y, a continuación, seleccione **Valores de dimensión financiera**.
    2. Seleccione el valor de la dimensión financiera que desea asignar un valor diferente de la dimensión financiera en la entidad jurídica consolidada.
    3. En la ficha desplegable **General**, en el campo **Dimensión de grupo**, introduzca la dimensión financiera en la entidad jurídica consolidada. Durante la consolidación, esta dimensión financiera se asignará a las transacciones y los saldos que utilicen la dimensión financiera seleccionada de la entidad jurídica filial. Las dimensiones financieras que especifique aquí se deben utilizar en la entidad jurídica consolidada. Puede asignar la dimensión financiera que se utilizará como la de grupo para varias dimensiones financieras de la filial.

5. Si va a realizar una consolidación en línea, siga estos pasos para asegurarse de que las transferencias se realicen de la forma deseada:

    1. En la *entidad jurídica consolidada*, vaya a **Contabilidad general \> Periódico \> Consolidar \> Consolidar \[Exportar a\]** para abrir la página **Consolidar \[En línea\]**.
    2. En la ficha **Criterios**, active la casilla **Usar cuenta de consolidación**.
    3. En la pestaña **Dimensiones financieras**, seleccione las dimensiones financieras adecuadas.
    4. En cada dimensión financiera seleccionada, especifique un número en el campo **Orden de segmentos** para indicar el orden en que deben mostrarse las dimensiones.

## <a name="maintain-the-same-chart-of-accounts-in-the-subsidiary-and-consolidated-legal-entities"></a>Mantener el mismo plan contable en las entidades jurídicas consolidadas y filiales

Las cuentas principales de la entidad jurídica filial pueden tener los mismos números de cuenta y la misma estructura para el plan contable que las cuentas principales de la entidad jurídica consolidada. En este caso, no es necesario asignar manualmente las cuentas principales de la filial a las de la consolidada.

Antes de comenzar la consolidación, siga estos pasos.

1. En la *entidad jurídica consolidada*, vaya a **Contabilidad general \> Periódico \> Consolidar \> Consolidar \[Exportar a\]** para abrir la página **Consolidar \[En línea\]**.
2. Active la casilla **Usar cuenta de consolidación**. Durante la consolidación, las transacciones y los saldos se transfieren automáticamente a la cuenta correcta.

> [!NOTE]
> Si las cuentas no corresponden, se detendrá la consolidación y recibirá un mensaje.

## <a name="create-a-chart-of-accounts-for-the-consolidated-legal-entity-based-on-an-existing-chart-of-accounts"></a>Creación de un plan contable para la entidad jurídica consolidada, basado en un plan contable existente

Puede realizar la consolidación incluso si no se ha creado aún un plan contable para la entidad jurídica consolidada.

- Si ha planeado la estructura contable que desea usar en la entidad jurídica consolidada, podrá asignar las cuentas de una filial a su estructura.
- Si no asigna ninguna cuenta de la filial, las cuentas de la entidad jurídica consolidada se crearán automáticamente cuando se transfieran los datos de la filial a la consolidada. Estas cuentas se basan en la cuenta principal. Los datos posteriores se acumulan en las cuentas de la entidad jurídica consolidada con el mismo número de cuenta que las de la filial.

Independientemente de si se han asignado cuentas, desactive la casilla **Usar cuenta de consolidación** de la página **Consolidar** en la entidad jurídica consolidada antes de ejecutar este tipo de consolidación.

> [!NOTE]
> Este método se puede usar para crear un plan contable en la entidad jurídica consolidada a partir de planes contables de una de las filiales. (Para obtener más información, consulte [Grupos de cuentas de consolidación y cuentas de consolidación adicionales](../budgeting/consolidation-account-groups-consolidation-accounts.md)). A continuación, asigne un principio de conversión de consolidación adecuado a cada cuenta principal consolidada y ejecute la consolidación para todas las entidades jurídicas filiales.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]