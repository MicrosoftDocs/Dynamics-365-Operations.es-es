---
title: Administrar usuarios socios comerciales en sitios web de comercio electrónico B2B mediante Dynamics 365 Sales
description: Este artículo describe cómo usar Microsoft Dynamics 365 Sales para administrar las aprobaciones de socios comerciales para sitios web de empresa a empresa (B2B) para Dynamics 365 Commerce.
author: ShalabhjainMSFT
ms.date: 02/16/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User, IT Pro
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: shajain
ms.search.validFrom: 2022-01-31
ms.dyn365.ops.version: 10.0.21
ms.search.industry: retail
ms.search.form: ''
ms.openlocfilehash: d178e619fca7915286181aa803376cd564f60a26
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/12/2022
ms.locfileid: "9278661"
---
# <a name="manage-business-partner-users-on-b2b-e-commerce-websites-using-dynamics-365-sales"></a>Administrar usuarios socios comerciales en sitios web de comercio electrónico B2B mediante Dynamics 365 Sales

[!include [banner](../../includes/banner.md)]

Este artículo describe cómo usar Microsoft Dynamics 365 Sales para administrar las aprobaciones de socios comerciales para sitios web de empresa a empresa (B2B) para Dynamics 365 Commerce. Las organizaciones que ya han invertido en la solución Dynamics 365 Sales pueden usar sus conceptos de cliente potencial y oportunidad para el proceso de aprobación de socios comerciales de comercio electrónico B2B.

Para obtener información básica sobre el proceso de aprobación de socios comerciales B2B, consulte [Administrar usuarios socios comerciales en sitios web de comercio electrónico B2B](manage-b2b-users.md).

Los socios comerciales potenciales pueden iniciar el proceso de incorporación a un sitio web de comercio electrónico B2B enviando una solicitud de incorporación a través de un vínculo en el sitio web B2B. Después de enviar la solicitud y los trabajos relevantes (como **P-0001** y **Sincronizar pedidos y canalizar solicitudes**) se ejecuten en la sede de Commerce, la solicitud de incorporación se guarda en la página **Todos los clientes potenciales** en la sede de Commerce. El proceso de aprobación de clientes potenciales de socios comerciales se puede completar en Sales.

Una vez habilitada la integración entre Sales y Commerce, la creación de un cliente potencial de socio comercial en Commerce provoca la creación de un *cliente potencial* en Sales.

La siguiente ilustración muestra un ejemplo de una página de creación de clientes potenciales para un cliente potencial de socio comercial en Sales.

![Página de creación de clientes potenciales en Dynamics 365 Sales.](../media/LeadInSales.png)

En la ilustración, la sección **Contacto** muestra la persona que envió la solicitud de incorporación y la sección **Compañía** muestra la organización. Una nota en la sección **Escala de tiempo** indica que el cliente potencial fue generado por la infraestructura de doble escritura. Debido a que fue creado por la infraestructura de doble escritura, este cliente potencial no aparecerá en la lista desplegable **Mis clientes potenciales abiertos**. En su lugar, aparecerá en una nueva vista denominada **Todos los clientes potenciales de comercio B2B**.

Según el proceso estándar de calificación de clientes potenciales en Sales, cuando un usuario "califica" el cliente potencial, se crea un registro de *oportunidad*, uno de *contacto* y uno de *cuenta*. La infraestructura de doble escritura se utiliza para escribir el contacto y los registros de cuenta en Commerce. El contacto se crea como cliente de tipo *persona* y se crea la empresa como cliente de tipo *organización*. Si un usuario selecciona **Cerrar como ganada** para la oportunidad, el cliente potencial es aprobado en Commerce. La aprobación de un cliente potencial hace que se cree una jerarquía de clientes.

Todos los procesos comerciales restantes ocurren en Commerce. Estos procesos incluyen el envío de correo electrónico al socio comercial, la definición de la gestión del límite de crédito para los usuarios y la adición de más usuarios al sitio B2B. Sin embargo, si un usuario descalifica al cliente potencial o marca la oportunidad como perdida en lugar de calificar al cliente potencial, este mismo en Commerce se marca como rechazado y se envía un correo electrónico de rechazo al solicitante.

## <a name="enable-integration-between-sales-and-commerce"></a>Habilitar la integración entre Sales y Commerce

La integración entre Sales y Commerce se basa en la infraestructura de doble escritura. Por lo tanto, la doble escritura debe estar habilitada y funcionando, de modo que los clientes que se crean en un sistema se escriban en el otro sistema. Para obtener más información sobre la infraestructura de doble escritura, consulte [Información general sobre la doble escritura](/dynamics365/fin-ops-core/dev-itpro/data-entities/dual-write/dual-write-overview).

Una vez completada la configuración de doble escritura, el socio que se va a implementar puede ir a [Microsoft AppSource](https://appsource.microsoft.com/) y buscar la solución que se llama [Soluciones de Commerce de doble escritura](https://partner.microsoft.com/dashboard/commercial-marketplace/offers/7ca1d8c9-dc79-4cb7-a82e-8dc96a25acca/overview). Instale el paquete con el asistente de instalación estándar y luego pruébelo creando un cliente potencial en un sitio B2B. Después de crear el cliente potencial, verifique que la solicitud que se muestra en **Todos los clientes potenciales** aparece en Commerce y, a continuación, compruebe que el cliente potencial se muestra como cliente potencial en Sales.

## <a name="additional-resources"></a>Recursos adicionales

[Administrar usuarios socios comerciales en sitios web de comercio electrónico B2B](manage-b2b-users.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
