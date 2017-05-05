---
title: Planificar su plan de cuentas
description: "Este artículo proporciona información que le ayudará a planificar el plan de cuenta para su organización."
author: RobinARH
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: DimensionConfigureAccountStructure, LedgerChartOfAccounts
audience: Application User
ms.reviewer: RobinARH
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 14051
ms.assetid: 10edb129-33f0-4cf9-b2a7-4b7ffa09b229
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 9f4d7fdd8cfa7a540fce219f6ae4792e57dfbe44
ms.openlocfilehash: 34425ecd4b78a134c92a2282576d0d7967d870b3
ms.lasthandoff: 03/31/2017


---

# <a name="plan-your-chart-of-accounts"></a>Planificar su plan de cuentas

[!include[banner](../includes/banner.md)]


Este artículo proporciona información que le ayudará a planificar el plan de cuenta para su organización.

Puede configurar un plan de cuentas para hacer un seguimiento de la información financiera de una organización y mantenerla. El plan de cuentas es un conjunto de cuentas que definen un marco financiero. Para realizar un seguimiento más exhaustivo de las transacciones de estas cuentas, puede agregar segmentos denominados "dimensiones financieras". Por ejemplo, una cuenta de gastos puede incluir dimensiones financieras denominadas Departamento, Centro de coste y Propósito. Las reglas que define el usuario, también denominadas "estructuras contables" y "reglas avanzadas", determinan la forma de vincular las dimensiones financieras a las cuentas principales y a otras dimensiones financieras, así como la forma de introducir transacciones financieras. 

El plan contable es una lista estructurada de las cuentas de contabilidad general de una entidad jurídica. Esta lista se utiliza para preparar informes financieros para autoridades y propietarios. Las cuentas se agrupan en tipos de cuentas que se agregan después en categorías más grandes. En el nivel más general, las cuentas se agrupan en ingresos y costes (cuentas operativas) y activos y pasivos (cuentas de saldo). 

Cualquier entidad jurídica de una organización puede usar y compartir un plan contable. El plan contable utilizado por una entidad jurídica se define en la página **Libro mayor**. 

Estos son algunos de los factores que se deben tener en cuenta la hora de planificar la estructura del plan de cuentas en la organización:

-   Los requisitos de informes del país o región en que está situada la organización
-   Los requisitos de informes de la entidad jurídica
-   El grado de especificación necesario, para las organizaciones externas y para la propia.

Cree el plan de cuentas en la página **Plan de cuentas**. Las cuentas principales se pueden crear desde la página **Plan de cuentas** o la página **Cuentas principales**. Sus cuentas principales no deben usar ninguno de los caracteres especiales que se usan como delimitadores en los planes de cuentas. Si hay un carácter especial igual al delimitador del plan de cuentas, puede haber inestabilidad o puede ser necesario usar siempre búsquedas o elementos emergentes al especificar las combinaciones de las combinaciones y las cuentas. 

Conviene vincular cuentas principales a categorías de cuenta principal, de modo que pueda aprovecharse la ventaja de usar los informes financieros predeterminados sin tener que realizar ninguna modificación. Por lo tanto, puede diseñar y mantener más rápida y fácilmente los informes. 

Use la página **Configurar estructuras contables** para crear estructuras contables. Las estructuras contables definen combinaciones válidas. Las combinaciones, junto con las cuentas principales, forman el plan contable. 

**Anulaciones de entidad jurídica** 

No todas las cuentas principales son válidas para todas las entidades jurídicas, y algunas solo pueden ser relevantes para un período de tiempo específico. En esta situación, puede usarse la sección Anulaciones de entidad jurídica para identificar para qué empresas se debe suspender la cuenta principal, quién es el propietario y el período de tiempo que la dimensión está activa. Las anulaciones en el nivel compartido no pueden ser más restrictivas que las anulaciones en el nivel de entidad jurídica.

Para obtener más información, consulte [Dimensiones financieras](financial-dimensions.md).




