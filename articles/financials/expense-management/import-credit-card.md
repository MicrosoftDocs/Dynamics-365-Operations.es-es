---
title: Importar y mantener transacciones de tarjeta de crédito
description: En este tema se explica cómo importar y mantener transacciones de tarjeta de crédito relacionadas con los gastos. Puede configurar estas transacciones para importarlas automáticamente en una programación recurrente o bien, puede importar manualmente las transacciones cada vez si fuera necesario.
author: KimANelson
manager: AnnBe
ms.date: 01/12/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: TrvPbsMainDataLines
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.custom: 274023
ms.assetid: 3605eda1-a7ed-4675-8031-5279c5a8f5e4
ms.search.region: Global
ms.author: knelson
ms.dyn365.ops.version: Version 1611
ms.search.validFrom: 2016-11-30
ms.openlocfilehash: 9674cf495b7fdd40d8672580b9d10e9ebe626bb0
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/15/2019
ms.locfileid: "1565122"
---
# <a name="import-and-maintain-credit-card-transactions"></a>Importar y mantener transacciones de tarjeta de crédito

[!include [banner](../includes/banner.md)]

Puede configurar las transacciones de la tarjeta de crédito relacionadas con gastos para que se importen de forma automática en una programación recurrente. Como alternativa, puede importar las transacciones de forma manual si fuera necesario. Las transacciones de tarjeta de crédito se importan a través de la entidad de datos de transacciones de tarjeta de crédito.

Para obtener más información acerca de las entidades de datos, consulte [Entidades de datos](../../dev-itpro/data-entities/data-entities.md).

## <a name="import-credit-card-transactions"></a>Importar transacciones de tarjeta de crédito

1. En la página **Transacciones de tarjeta de crédito**, seleccione **Importar transacciones**. Si es la primera vez que abre la opción de gestión de datos, el sistema actualizará la lista de entidades de datos antes de que pueda continuar.
2. En el campo **Nombre**, escriba una descripción única del trabajo de importación.
3. En el campo **Formato de datos de origen**, seleccione el formato del archivo que contiene las transacciones de la tarjeta de crédito que se importarán.
4. Seleccione **Cargar** y, a continuación, busque y seleccione el archivo que quiera importar.
5. Una vez cargado el archivo, valide la asignación del archivo de transacción de la tarjeta de crédito y las columnas de la entidad de datos de las transacciones de la tarjeta de crédito; para ello, seleccione el vínculo **Ver asignación** en el icono. Si hay errores de asignación o si tiene que cambiar la asignación, realice los cambios de asignación desde la pestaña **Visualización de asignación** o **Detalles de la asignación**.
6. Para automatizar las transacciones de la tarjeta de crédito, seleccione **Crear un trabajo de datos recurrente**. Es entonces cuando puede establecer la recurrencia que definirá con qué frecuencia se importarán las transacciones de la tarjeta de crédito. Cuando haya terminado, haga clic en **Aceptar**.
7. Para importar el archivo seleccionado, seleccione **Importar**.
8. Si se produce algún error durante la importación, puede consultar el registro de ejecución o los datos provisionales para ver qué errores debe corregir para garantizar una importación correcta.

> [!NOTE]
> Si debe importar más de un formato de archivo, debe crear trabajos de importación separados para cada tipo de formato.

## <a name="reassign-the-credit-card-transactions-for-terminated-employees"></a>Reasignar transacciones de la tarjeta de crédito de empleados despedidos

Una vez finaliza un registro de empleado, la cuenta Active Directory Domain Services de ese empleado se deshabilita. Sin embargo, es posible que haya transacciones de tarjeta de crédito que todavía deban ser calculadas y reembolsadas. Desde la página **Transacciones de tarjeta de crédito** puede reasignar el empleado de cualquier transacción de tarjeta de crédito cuyo empleado asociado haya sido despedido.

Seleccione una o más transacciones de tarjeta de crédito y, a continuación, seleccione **Volver a asignar las transacciones**. A continuación puede seleccionar otro empleado para asignarle esas transacciones de tarjeta de crédito. Tras reasignar las transacciones de tarjeta de crédito, se pueden seleccionar para un informe de gastos y podrá pagarlas mediante el proceso habitual para el reembolso del informe de gastos.
