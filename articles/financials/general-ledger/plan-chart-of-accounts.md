---
title: Planificar su plan de cuentas
description: "Este tema proporciona información que le ayudará a planificar el plan de cuentas para su organización."
author: aprilolson
manager: AnnBe
ms.date: 04/02/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: DimensionConfigureAccountStructure, LedgerChartOfAccounts
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.custom: 14051
ms.assetid: 10edb129-33f0-4cf9-b2a7-4b7ffa09b229
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: a8b5a5af5108744406a3d2fb84d7151baea2481b
ms.openlocfilehash: 3f8d97fc42cde9053b0552fc1dfe8e6de0f5e03b
ms.contentlocale: es-es
ms.lasthandoff: 04/13/2018

---

# <a name="plan-your-chart-of-accounts"></a>Planificar su plan de cuentas

[!include [banner](../includes/banner.md)]

Este tema proporciona información que le ayudará a planificar el plan de cuentas para su organización.

Puede configurar un plan de cuentas para hacer un seguimiento de la información financiera de una organización y mantenerla. El plan de cuentas es un conjunto de cuentas que definen un marco financiero. Para realizar un seguimiento más exhaustivo de las transacciones de estas cuentas, puede agregar segmentos. Estos segmentos se conocen como dimensiones financieras. Por ejemplo, una cuenta de gastos puede incluir dimensiones financieras denominadas Departamento, Centro de coste y Propósito. Las reglas que define el usuario determinan la forma de vincular las dimensiones financieras a las cuentas principales y a otras dimensiones financieras, así como la forma de introducir transacciones. Estas reglas definidas por el usuario se conocen como estructuras contables y reglas avanzadas.

El plan contable es una lista estructurada de las cuentas de contabilidad general de una entidad jurídica. Esta lista se utiliza para preparar informes financieros para autoridades y propietarios. Las cuentas se agrupan primero en tipos de cuentas y despuñes se agregan en categorías más grandes. En el nivel más general, las cuentas se agrupan en ingresos y costes (cuentas operativas) y activos y pasivos (cuentas de saldo).

Cualquier entidad jurídica de una organización puede usar y compartir un plan contable. El plan contable utilizado por una entidad jurídica se define en la página **Libro mayor**.

Estos son algunos de los factores que se deben tener en cuenta la hora de planificar la estructura del plan de cuentas en la organización:

- Los requisitos de informes del país o región en que está situada la organización
- Los requisitos de informes de la entidad jurídica
- El grado de especificación necesario, para las organizaciones externas y para la propia.

Cree el plan de cuentas en la página **Plan de cuentas**. Puede crear las cuentas principales desde la página **Plan de cuentas** o la página **Cuentas principales**. Sus cuentas principales no deben usar ninguno de los caracteres especiales que se usan como delimitadores en los planes de cuentas. De lo contrario, es posible que experimente inestabilidad o puede que tenga que utilizar siempre las búsquedas o el cuadro de diálogo al especificar combinaciones de cuentas y dimensiones. Para obtener más información, consulte [Crear una cuenta principal](tasks/create-main-account.md).

> [!NOTE]
> En Microsoft Dynamics for Finance and Operations versión 8.0 (abril de 2018), puede modificar el delimitador del plan de cuentas desde la página **Parámetros de contabilidad general**.

Conviene vincular cuentas principales a categorías de cuenta principal, de modo que pueda aprovecharse la ventaja de usar los informes financieros predeterminados sin tener que realizar ninguna modificación. Por lo tanto, puede diseñar y mantener más rápida y fácilmente los informes.

Cree una estructura contable en la página **Configurar estructuras contables**. Las estructuras contables definen combinaciones válidas. Estas combinaciones, junto con las cuentas principales, forman el plan contable. Para obtener más información, consulte [Crear una estructura contable](tasks/create-account-structures.md).

**Anulaciones de entidad jurídica**

No todas las cuentas principales son válidas para todas las entidades jurídicas y algunas cuentas principales solo pueden ser relevantes para un período específico. En estos casos, puede usar la sección **Anulaciones de entidad jurídica** para identificar las empresas para las que se debe suspender la cuenta principal, el propietario y el período de tiempo que la dimensión está activa. Las anulaciones en el nivel compartido no pueden ser más restrictivas que las anulaciones en el nivel de entidad jurídica.

Para obtener más información, consulte los siguientes temas:

- [Dimensiones financieras](financial-dimensions.md)
- [Crear y asignar estructuras de reglas avanzadas](tasks/create-assign-advanced-rule-structures.md)

