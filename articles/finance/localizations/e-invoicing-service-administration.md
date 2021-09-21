---
title: Componentes de administración de facturación electrónica
description: Este tema proporciona información sobre los componentes relacionados con la administración de la facturación electrónica.
author: gionoder
ms.date: 08/31/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.custom: 97423
ms.assetid: ''
ms.search.region: Global
ms.author: janeaug
ms.search.validFrom: 2020-07-08
ms.dyn365.ops.version: AX 10.0.12
ms.openlocfilehash: d187e8a03552258099d7021ff056d0726ea60ca1
ms.sourcegitcommit: baf82100f0aa7d5f5f47c7f54bc155d8a07beab5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/31/2021
ms.locfileid: "7463890"
---
# <a name="electronic-invoicing-administration-components"></a>Componentes de administración de facturación electrónica

[!include [banner](../includes/banner.md)]


Este tema proporciona información sobre los componentes relacionados con la administración de la facturación electrónica. También proporciona información sobre cómo configurar el servicio de facturación electrónica.

## <a name="azure"></a>Azure

Utilice Microsoft Azure para crear los secretos para el almacén de claves y la cuenta de almacenamiento. Luego, use los secretos del almacén de claves y el token SAS de la cuenta de almacenamiento en la configuración de la facturación electrónica.

## <a name="lifecycle-services"></a>Lifecycle Services

Utilice Microsoft Dynamics Lifecycle Services (LCS) para habilitar el complemento de facturación electrónica para su proyecto de implementación de LCS.

> [!NOTE]
> La instalación de los complementos en LCS requiere al menos **un entorno de nivel 2**. Para obtener más información sobre planificación de ambientes, consulte [Planificación de ambientes](../../fin-ops-core/fin-ops/imp-lifecycle/environment-planning.md).
 

## <a name="regulatory-configuration-services"></a>Regulatory Configuration Services

Dynamics 365 Regulatory Configuration Services (RCS) es la interfaz que se utiliza para configurar la facturación electrónica. Los recursos, como los entornos y las funciones de facturación electrónica se crean, mantienen y alojan en RCS. Cuando los recursos están listos, se publican en el servicio de facturación electrónica.

Para registrarse en RCS, consulte [Regulatory services](https://marketing.configure.global.dynamics.com/).

Para más información sobre RCS, consulte [Regulatory Configuration Services (RCS): características de globalización](rcs-globalization-feature.md)

### <a name="integration-with-electronic-invoicing"></a>Integración con la facturación electrónica 

Antes de poder utilizar RCS para configurar facturas electrónicas, debe configurar RCS para permitir la comunicación con la facturación electrónica. Puede completar esta configuración en la pestaña **Facturación electrónica** de la página **Parámetros de informes electrónicos**.

#### <a name="service-endpoint"></a><a id='svc-endpoint-uris'></a>Extremo del servicio

La facturación electrónica está disponible en diversas geografías de centros de datos de Azure. La siguiente tabla enumera la disponibilidad por región.


| Geografía de centros de datos de Azure | Identificador URI de extremo de servicio                                                       |
|----------------------------|----------------------------------------------------------------------------|
| Estados Unidos              | <p>https://gw.us-il101.gateway.prod.island.powerapps.com/electronicinvoicing/</p><p>https://gw.us-il102.gateway.prod.island.powerapps.com/electronicinvoicing/</p><p>https://gw.us-il103.gateway.prod.island.powerapps.com/electronicinvoicing/</p><p>https://gw.us-il104.gateway.prod.island.powerapps.com/electronicinvoicing/</p><p>https://gw.us-il105.gateway.prod.island.powerapps.com/electronicinvoicing/</p><p>https://gw.us-il106.gateway.prod.island.powerapps.com/electronicinvoicing/</p><p>https://gw.us-il107.gateway.prod.island.powerapps.com/electronicinvoicing/</p><p>https://gw.us-il108.gateway.prod.island.powerapps.com/electronicinvoicing/</p><p>https://gw.us-il109.gateway.prod.island.powerapps.com/electronicinvoicing</p> |
| Europa                     | <p>https://gw.eu-il101.gateway.prod.island.powerapps.com/electronicinvoicing/</p><p>https://gw.eu-il102.gateway.prod.island.powerapps.com/electronicinvoicing/</p><p>https://gw.eu-il103.gateway.prod.island.powerapps.com/electronicinvoicing/</p><p>https://gw.eu-il104.gateway.prod.island.powerapps.com/electronicinvoicing/</p><p>https://gw.eu-il105.gateway.prod.island.powerapps.com/electronicinvoicing/</p><p>https://gw.eu-il106.gateway.prod.island.powerapps.com/electronicinvoicing/</p><p>https://gw.eu-il107.gateway.prod.island.powerapps.com/electronicinvoicing/</p><p>https://gw.eu-il108.gateway.prod.island.powerapps.com/electronicinvoicing/</p><p>https://gw.eu-il109.gateway.prod.island.powerapps.com/electronicinvoicing/</p><p>https://gw.eu-il110.gateway.prod.island.powerapps.com/electronicinvoicing/</p> |
| Reino Unido             | <p>https://gw.uk-il101.gateway.prod.island.powerapps.com/electronicinvoicing/</p><p>https://gw.uk-il102.gateway.prod.island.powerapps.com/electronicinvoicing/</p> |
| Asia                       | <p>https://gw.as-il101.gateway.prod.island.powerapps.com/electronicinvoicing/</p><p>https://gw.as-il102.gateway.prod.island.powerapps.com/electronicinvoicing/</p> |

### <a name="service-environments"></a>Entornos de servicio

Los entornos de servicio son particiones lógicas que se crean para respaldar la ejecución de las características de globalización de la facturación electrónica. Los secretos de seguridad y los certificados digitales, y la gobernanza (es decir, los permisos de acceso), deben configurarse en el nivel del entorno de servicio.

Los clientes pueden crear tantos entornos de servicio como deseen. Todos los entornos de servicio que crea un cliente son independientes entre sí.

Los entornos de servicio deben crearse y mantenerse en RCS. Cuando los ambientes de servicio están listos, deben publicarse en la facturación electrónica.

#### <a name="service-environment-status"></a>Estado de entornos de servicio

Los entornos de servicio se pueden gestionar a través del estado. Las posibles opciones son:

- **No publicado**: se ha creado el entorno, pero aún no se ha publicado.
- **Publicado**: se ha publicado el ambiente en la facturación electrónica.
- **Cambiado**: se han cambiado los atributos de un entorno publicado, pero los cambios aún no se han publicado.

#### <a name="customer-secrets"></a>Secretos del cliente

El servicio de facturación electrónica es responsable de almacenar todos sus datos comerciales en los recursos de Azure que son propiedad de su empresa. Para asegurarse de que el servicio funcione correctamente y de que solo la facturación electrónica acceda a todos los datos comerciales necesarios y generados por ella, debe crear dos recursos principales de Azure:

- Una cuenta de almacenamiento de Azure (Blob Storage) que almacenará documentos electrónicos, incluidas facturas electrónicas, resultados de transformaciones de documentos y respuestas de servicios web externos.
- Un Azure Key Vault que almacenará certificados y el identificador uniforme de recursos (URI) de la cuenta de almacenamiento (token SAS).


Se debe asignar un Key Vault dedicado y una cuenta de almacenamiento de cliente específicamente para su uso con la facturación electrónica. Para más información, consulte [Crear una cuenta de almacenamiento de Azure y un Key Vault](e-invoicing-create-azure-storage-account-key-vault.md).

Para supervisar el estado de su Key Vault y recibir alertas, configure Azure Monitor para Key Vault. Al habilitar el registro de Key Vault, puede controlar cómo, cuándo y quién accede a sus Key Vaults. Para más información, consulte [Supervisión y alerta para Azure Key Vault](/azure/key-vault/general/alert) y [Cómo habilitar el registro de Key Vault](/azure/key-vault/general/howto-logging?tabs=azure-cli).

Como práctica recomendada, rote periódicamente los secretos. Para obtener más información, consulte [Documentación de secretos](/azure/key-vault/secrets/).

#### <a name="users"></a>Usuarios

Cada entorno de servicio debe enumerar los usuarios que pueden conectarse desde Dynamics 365 Finance y Dynamics 365 Supply Chain Management en la facturación electrónica.

#### <a name="publication"></a>Publicación

Antes de poder utilizarse, los entornos de servicio deben publicarse en la facturación electrónica. Finance and Supply Chain Management solo puede acceder a los entornos publicados. Además, se debe publicar un entorno de servicio antes de que cualquier actualización de sus atributos entre en vigor en el servicio de facturación electrónica.

### <a name="connected-applications"></a>Solicitudes conectadas

Las aplicaciones conectadas son las instancias de Finance y Supply Chain Management a las que quizás desee acceder a través de RCS. Además de la URL de la aplicación y su inquilino, una aplicación conectada contiene las credenciales que permiten que RCS se conecte al entorno.

A través de las aplicaciones conectadas, puede configurar parte de la función de facturación electrónica en Finance y Supply Chain Management para que funcione toda la función de facturación electrónica.

## <a name="finance-and-supply-chain-management"></a>Finance y Supply Chain Management

### <a name="integration-with-electronic-invoicing"></a>Integración con la facturación electrónica

Antes de poder utilizar Finance y Supply Chain Management para emitir facturas electrónicas a través de la facturación electrónica, esta debe configurarse para permitir la comunicación con el servicio.

#### <a name="electronic-invoicing-integration-feature"></a>Característica de integración de facturación electrónica

Para habilitar la comunicación entre Finance y Supply Chain Management y la facturación electrónica, debe activar la característica **Integración de facturación electrónica** en el espacio de trabajo **Gestión de características**.

#### <a name="service-endpoint"></a>Extremo del servicio

El punto de conexión de servicio es la URL donde se encuentra la facturación electrónica. Antes de poder emitir facturas electrónicas, el punto de conexión de servicio debe configurarse en Finance y Supply Chain Management para permitir la comunicación con el servicio.

Para configurar el punto de conexión de servicio, vaya a **Administración de la organización \> Preparar \> Parámetros de documento electrónico** y luego, en la pestaña **Facturación electrónica**, en el campo **URL de putno de conexión**, introduzca la URL apropiada de la tabla en la sección [Punto de conexión de servicio](#svc-endpoint-uris) anterior en este tema.

#### <a name="environments"></a>Entornos

El nombre del entorno que se introduce en Finance y Supply Chain Management hace referencia al nombre del entorno que se crea en RCS y se publica en la facturación electrónica.

El entorno debe configurarse en la pestaña **Facturación electrónica** de la página **Parámetros de documentos electrónicos**. De esa manera, cada solicitud para emitir facturas electrónicas contiene el entorno donde la facturación electrónica puede determinar qué función de facturación electrónica debe procesar la solicitud.

## <a name="additional-resources"></a>Recursos adicionales

- [Configurar facturas electrónicas en RCS](e-invoicing-configuration-rcs.md)
- [Emitir facturas electrónicas en Finance y Supply Chain Management](e-invoicing-issuing-electronic-invoices-finance-supply-chain-management.md)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
