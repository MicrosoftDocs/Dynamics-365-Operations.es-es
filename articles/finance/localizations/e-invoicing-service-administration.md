---
title: Componentes de administración del complemento de facturación electrónica
description: Este tema proporciona información sobre los componentes relacionados con la administración del complemento de facturación electrónica.
author: gionoder
manager: AnnBe
ms.date: 01/28/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
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
ms.openlocfilehash: 6f630ebb694217c3bd52378a649933a670c090f2
ms.sourcegitcommit: e88c96d1cb817a22db81856cadb563c095ab2671
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/02/2021
ms.locfileid: "5104435"
---
# <a name="electronic-invoicing-add-on-administration-components"></a>Componentes de administración del complemento de facturación electrónica

[!include [banner](../includes/banner.md)]
[!include [banner](../includes/preview-banner.md)]

Este tema proporciona información sobre los componentes relacionados con la administración del complemento de facturación electrónica. También proporciona información sobre cómo configurar el servicio adicional de facturación electrónica.

## <a name="azure"></a>Azure

Utilice Microsoft Azure para crear los secretos para el almacén de claves y la cuenta de almacenamiento. Luego utilice los secretos en la configuración del complemento de Facturación electrónica.

## <a name="lifecycle-services"></a>Lifecycle Services

Utilice Microsoft Dynamics Lifecycle Services (LCS) para habilitar el complemento de los microservicios para su proyecto de implementación de LCS.

En LCS, seleccione el mosaico **Gestión de funciones de versión preliminar** y luego active la característica **Servicio de facturación electrónica**.

## <a name="regulatory-configuration-services"></a>Regulatory Configuration Services

Dynamics 365 Regulatory Configuration Services (RCS) es la interfaz para configurar el complemento de facturación electrónica. Los recursos, como los entornos y las funciones de facturación electrónica se crean, mantienen y alojan en RCS. Cuando los recursos están listos, se publican en el servicio adicional de facturación electrónica.

Para más información sobre RCS, consulte [Regulatory Configuration Services (RCS): características de globalización](rcs-globalization-feature.md)

### <a name="integration-with-the-electronic-invoicing-add-on"></a>Integración con el complemento de facturación electrónica

Antes de poder utilizar RCS para configurar facturas electrónicas, debe configurar RCS para permitir la comunicación con el complemento de facturación electrónica. Complete esta configuración en la pestaña **Complemento de facturación electrónica** de la página **Parámetros de informes electrónicos**.

#### <a name="service-endpoint"></a>Extremo del servicio

La URL del punto de conexión del complemento de facturación electrónica puede variar según la geografía del centro de datos de Azure. La siguiente tabla enumera la disponibilidad por región:

| Geografía de centros de datos de Azure | URL de extremo de servicio                                                       |
|----------------------------|----------------------------------------------------------------------------|
| Este de EE. UU.                    | `https://electronicinvoicing.eus-il301.gateway.prod.island.powerapps.com/` |
| Oeste de EE. UU.                    | `https://electronicinvoicing.wus-il301.gateway.prod.island.powerapps.com/` |
| Norte de la UE                   | `https://electronicinvoicing.neu-il301.gateway.prod.island.powerapps.com/` |
| Oeste de la UE                    | `https://electronicinvoicing.weu-il301.gateway.prod.island.powerapps.com/` |

#### <a name="application-id"></a>Id. de la aplicación

El id. de la aplicación es el id. de la aplicación de complemento de facturación electrónica. En este caso, el valor es fijo: **0cdb527f-a8d1-4bf8-9436-b352c68682b2**.

#### <a name="lcs-environment-id"></a>Id. de entorno LCS

El id. del entorno de LCS es el id. de la suscripción LCS de su organización.

### <a name="service-environments"></a>Entornos de servicio

Los entornos de servicio son particiones lógicas que se crean para respaldar la ejecución de las funciones de facturación electrónica del complemento de facturación electrónica. Los secretos de seguridad y los certificados digitales, y la gobernanza (es decir, los permisos de acceso), deben configurarse en el nivel del entorno de servicio.

Los clientes pueden crear tantos entornos de servicio como deseen. Todos los entornos de servicio que crea un cliente son independientes entre sí.

Los entornos de servicio deben crearse y mantenerse en RCS. Cuando los entornos de servicio están listos, deben publicarse en el complemento de facturación electrónica.

#### <a name="service-environment-status"></a>Estado de entornos de servicio

Los entornos de servicio se pueden gestionar a través del estado. Las posibles opciones son:

- **No publicado**: se ha creado el entorno, pero aún no se ha publicado.
- **Publicado**: se ha publicado el entorno en el complemento de facturación electrónica.
- **Cambiado**: se han cambiado los atributos de un entorno publicado, pero los cambios aún no se han publicado.

#### <a name="customer-secrets"></a>Secretos del cliente

El servicio adicional de facturación electrónica es responsable de almacenar todos sus datos comerciales en los recursos de Azure que son propiedad de su empresa. Para asegurarse de que el servicio funcione correctamente y de que solo el complemento acceda a todos los datos comerciales requeridos y generados por el complemento de facturación electrónica, debe crear dos recursos principales de Azure:

- Una cuenta de almacenamiento de Azure (Blob Storage) que almacenará facturas electrónicas
- Un almacén de claves de Azure que almacenará certificados y el identificador uniforme de recursos (URI) de la cuenta de almacenamiento

> [!NOTE]
> Se debe asignar un almacén de claves dedicado y una cuenta de almacenamiento de cliente específicamente para su uso con el complemento de facturación electrónica.

Para más información, consulte [Crear cuenta de almacenamiento de Azure y un almacén de claves](e-invoicing-create-azure-storage-account-key-vault.md).

#### <a name="users"></a>Usuarios

Cada entorno de servicio debe enumerar los usuarios que pueden conectarse desde Dynamics 365 Finance y Dynamics 365 Supply Chain Management en el complemento de facturación electrónica.

#### <a name="publication"></a>Publicación

Antes de poder utilizarse, los entornos de servicio deben publicarse en el complemento de facturación electrónica. Finance and Supply Chain Management solo puede acceder a los entornos publicados. Además, se debe publicar un entorno de servicio antes de que cualquier actualización de sus atributos entre en vigor en el servicio de facturación electrónica.

### <a name="connected-applications"></a>Solicitudes conectadas

Las aplicaciones conectadas son las instancias de Finance y Supply Chain Management a las que quizás desee acceder a través de RCS. Además de la URL de la aplicación y su inquilino, una aplicación conectada contiene las credenciales que permiten que RCS se conecte al entorno.

A través de las aplicaciones conectadas, puede configurar parte de la función de facturación electrónica en Finance y Supply Chain Management para que funcione toda la función de facturación electrónica.

## <a name="finance-and-supply-chain-management"></a>Finance y Supply Chain Management

### <a name="integration-with-electronic-invoicing-add-on"></a>Integración con el complemento de facturación electrónica

Antes de poder utilizar Finance y Supply Chain Management para emitir facturas electrónicas a través del complemento de facturación electrónica, el complemento debe configurarse para permitir la comunicación con el servicio.

#### <a name="electronic-invoicing-add-on-integration-feature"></a>Característica de integración del complemento de facturación electrónica

Para habilitar la comunicación entre Finance y Supply Chain Management y el complemento de facturación electrónica, debe activar la característica **Integración complementaria de facturación electrónica** en el espacio de trabajo **Gestión de funciones**.

#### <a name="service-endpoint"></a>Extremo del servicio

El punto de conexión de servicio es la URL donde se encuentra el complemento de facturación electrónica. Antes de poder emitir facturas electrónicas, el punto de conexión de servicio debe configurarse en Finance y Supply Chain Management para permitir la comunicación con el servicio.

Para configurar el punto de conexión de servicio, vaya a **Administración de la organización \> Preparar \> Parámetro de documento electrónico** y luego, en la pestaña **Servicios de envío**, en el campo **URL del complemento de facturación electrónica**, introduzca la URL como se describe en la sección **Punto de conexión de servicio**.

#### <a name="environments"></a>Entornos

El nombre del entorno que se introduce en Finance y Supply Chain Management hace referencia al nombre del entorno que se crea en RCS y se publica en el complemento de facturación electrónica.

El entorno debe configurarse en la pestaña **Servicios de envío** de la página **Parámetro de documento electrónico**, de modo que cada solicitud para emitir facturas electrónicas contenga el entorno donde el complemento de facturación electrónica pueda determinar qué función de facturación electrónica debe procesar la solicitud.

## <a name="additional-resources"></a>Recursos adicionales

- [Configurar facturas electrónicas en RCS](e-invoicing-configuration-rcs.md)
- [Emitir facturas electrónicas en Finance y Supply Chain Management](e-invoicing-issuing-electronic-invoices-finance-supply-chain-management.md)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]