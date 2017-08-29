---
title: "Configuración de crédito y cobros"
description: "En este artículo se explica cómo configurar la funcionalidad de cobros."
author: ShivamPandey-msft
manager: AnnBe
ms.date: 08/22/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: CustCollectionsActivitiesListPage
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 14031
ms.assetid: dcc6da2f-9af5-4f1d-abaa-b72967b66979
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 1982e495f740d6061b9574aa9f40f38180e8d110
ms.openlocfilehash: 76937aacbc1925603766299168ec2d4090bd161b
ms.contentlocale: es-es
ms.lasthandoff: 08/03/2017

---

# <a name="set-up-credit-and-collections"></a>Configuración de crédito y cobros

[!include[banner](../includes/banner.md)]


En este artículo se explica cómo configurar la funcionalidad de cobros.

<a name="set-up-aging-period-definitions"></a>Configurar definiciones del período de vencimiento
-------------------------------

Configure una definición de período de vencimiento. El período de vencimiento define las columnas que aparecen en las páginas de lista **Saldos vencidos**, **Actividades de cobros** y **Casos de cobros**. También define los períodos que aparecen en la página **Cobros**. Si un grupo de clientes está configurado, se usará la definición del período de vencimiento del grupo. Si no se ha configurado ningún grupo, se usará la definición de período de vencimiento predeterminada especificada en la página **Parámetros de clientes**. Si no se especifica ninguna definición de período de vencimiento predeterminada, se usa la primera definición de período de vencimiento de la página **Definiciones de período de vencimiento**.

## <a name="create-an-aging-snapshot"></a>Crear una instantánea de vencimientos
Cree registros de instantánea de vencimientos para todos los clientes o para los clientes de un grupo de clientes. La información de la instantánea de vencimientos aparece en la página de lista **Saldos vencidos** y en la página **Cobros**. Debe crear una instantánea de vencimientos antes de poder usar la página de lista. La página de lista muestra información para aquellos clientes para los que se haya creado una instantánea de vencimientos.

## <a name="optional-set-up-customer-pools"></a>Opcional: configurar secciones de clientes
Puede configurar grupos de clientes para representar grupos de clientes. Puede usar los grupos de clientes como filtros para la información del cliente que se muestra en las páginas de lista **Cobros**, en la página **Cobros**, o al crear instantáneas de vencimientos.

## <a name="optional-create-a-collections-team"></a>Opcional: crear un equipo de cobros
Si varias personas de su organización realizan trabajos de cobros, puede configurar un equipo de cobros. Puede seleccionar el equipo en la página **Parámetros de clientes**. Si no crea un equipo de cobros, se creará uno automáticamente cuando configure agentes de cobros en la página **Agente de cobros**.

## <a name="set-up-a-collections-case-category"></a>Configurar una categoría de caso de cobros
Si organiza los cobros usando casos, configure una categoría de caso de tipo **Cobros**. Esta configuración solo es necesaria si se desea usar la función de casos en la página **Cobros**.

## <a name="set-up-journal-names-settlement-writeoff-and-nsf"></a>Configurar nombres de diarios (liquidación, amortización y NSF)
Configure los nombres de diario que se usan al procesar transacciones en la página **Cobros**. En este procesamiento se incluye la liquidación de y la cancelación de transacciones y el procesamiento de pagos de fondos insuficientes (NSF).

| Descripción | Tipo de diario     |
|-------------|------------------|
| Liquidación  | Cobros |
| Cancelación   | Diaria            |
| NSF         | Cobros |

## <a name="set-up-a-reason-code-for-writeoff-transactions"></a>Configurar un código de motivo para transacciones de cancelación
Configure el código de motivo predeterminado que se usa cuando se cancelan transacciones en la página **Cobros**. Puede cambiar el código durante el proceso de cancelación.

## <a name="set-up-a-folder-for-email-attachments-and-create-email-templates"></a>Configurar una carpeta para los datos adjuntos de correo electrónico y crear plantillas de correo electrónico
Si va a enviar mensajes de correo electrónico desde la página **Cobros** con adjuntos de Microsoft Excel, puede crear plantillas de correo electrónico opcionales para estos mensajes.

## <a name="set-up-accounts-receivable-parameters-for-collections"></a>Configuración de parámetros de clientes para cobros
Configure los parámetros de clientes que aparecen en la ficha **Cobros**.

## <a name="optional-set-up-collections-agents"></a>Opcional: configurar agentes de cobros
Si varias personas de su organización realizan trabajos de cobros, puede configurar agentes de cobros. Un agente de cobros es un trabajador configurado como usuario en la página **Relaciones del usuario**. Puede asignar grupos de clientes (consultas de cliente) a agentes de cobros para ayudar a los agentes a organizar su trabajo. Los agentes de cobros se agregan al equipo seleccionado en la página **Parámetros de clientes**. Si no hay un equipo seleccionado en esa página, se creará un nuevo equipo llamado **Cobros**, y los agentes de cobros se agregarán a dicho equipo.

## <a name="set-up-a-writeoff-account"></a>Configurar una cuenta de cancelación
Configure la cuenta de cancelación que se use para la entrada correspondiente en la contabilidad general cuando se cancele una transacción. Esta cuenta se almacena en el perfil de contabilización del cliente.

## <a name="set-up-nsf-information-for-bank-accounts"></a>Configurar información NSF para cuentas bancarias
Actualice las cuentas bancarias de modo que tengan el diario correcto cuando los pagos NSF se identifiquen en la página **Cobros**. En la ficha **Gestión de divisas**, en el campo **Diario de pagos sin fondos suficientes (NSF)**, seleccione un diario de pagos.

## <a name="set-up-outlook-settings-for-users-of-the-collections-page"></a>Configuración de parámetros de Outlook para usuarios de la página Cobros
Antes de que los trabajadores puedan crear actividades o enviar mensajes de correo electrónico mediante la página **Cobros**, debe comprobar que la clave de configuración **Sincronización con Microsoft Outlook** esté seleccionada y que la sincronización de Outlook esté configurada para estos trabajadores.

## <a name="set-up-email-and-address-settings-for-collections-customer-contacts"></a>Configurar los parámetros de correo electrónico y de dirección para los contactos de cliente de cobros
Configure direcciones de correo electrónico para los contactos de cliente si desea enviar mensajes de correo electrónico a los contactos desde la página **Cobros**. El contacto de cobros se usa como contacto predeterminado en la página **Cobros**. Puede configurar una dirección de extracto para un cliente si los extractos deben usar una dirección distinta a la principal. 

En la ficha desplegable **Crédito y cobros** de un cliente, en el campo **Contacto de cobros**, seleccione la persona de la organización del cliente que trabaja con su agente de cobros. Esta persona se usa como contacto predeterminado en la página **Cobros**, y es la persona a la que se enviarán los mensajes de correo electrónico. 

> [!NOTE] 
> Si no se especifica un contacto de cobros para un cliente, se usará el contacto principal del cliente. Si no se especifica un contacto principal, los mensajes de correo electrónico se enviarán a la primera dirección que aparezca en la página **Contactos**.

## <a name="set-up-email-settings-for-salespeople"></a>Configurar los parámetros de correo electrónico para los vendedores
Configure direcciones de correo electrónico para los vendedores si desea enviar mensajes de correo electrónico a los vendedores desde la página **Cobros**. Configure una dirección de correo electrónico para cada representante de ventas de cada grupo de ventas de la comisión. El representante de ventas que tenga la opción **Contacto** activada es el vendedor predeterminado al que se enviarán los mensajes de correo electrónico. 

Si no se especifica un representante de ventas, se usará el vendedor principal de la organización del cliente. Si no se especifica un vendedor principal, los mensajes de correo electrónico se enviarán al primer vendedor que aparezca en la página.


Para obtener más información, consulte los siguientes temas:

 - [Crear una secuencia de cartas de cobro](tasks/create-collection-letter-sequence.md)
 
 - [Procesar cartas de cobro](tasks/process-collection-letters.md)
 
 - [Revisar información de cobros](tasks/review-collections-information.md)


