---
title: Configurar entornos de servicio y aplicaciones conectadas
description: Este artículo proporciona información sobre cómo configurar sus entornos de servicio y aplicaciones conectadas.
author: dkalyuzh
ms.date: 02/09/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.custom:
- "97423"
- intro-internal
ms.assetid: ''
ms.search.region: Global
ms.author: janeaug
ms.search.validFrom: 2020-07-08
ms.dyn365.ops.version: AX 10.0.12
ms.openlocfilehash: c1bb3f784148f04c01223ac4e280a18bacfe0e51
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/03/2022
ms.locfileid: "8853233"
---
# <a name="configure-service-environments-and-connected-applications"></a>Configurar entornos de servicio y aplicaciones conectadas

[!include [banner](../includes/banner.md)]

Este artículo proporciona información sobre cómo configurar sus entornos de servicio y aplicaciones conectadas. Hay tres pasos en este proceso. El paso 1 es obligatorio y los pasos 2 y 3 son opcionales.

## <a name="step-1-create-a-service-environment"></a>Paso 1: Crear un entorno de servicio

Cuando cree su entorno de servicio, defina la lista de usuarios que pueden implementar características de Globalización en él. Opcionalmente, para algunos de los escenarios, defina la lista de aplicaciones externas que pueden comunicarse con el servicio de Facturación Electrónica. Establezca secuencias numéricas si las usará en sus escenarios.

Para completar este paso, consulte [Entornos de servicio](e-invoicing-service-environments.md).

## <a name="step-2-add-certificates-and-secrets"></a>Paso 2: Agregar certificados y secretos

Agregar una referencia a secretos y al almacén de claves de Microsoft Azure para usarlos en sus escenarios. Este paso es obligatorio si las acciones en las canalizaciones de procesamiento utilizan certificados y secretos para la firma digital o la comunicación con servicios web externos.

Para completar este paso, consulte [Certificados y secretos de clientes](e-invoicing-customer-certificates-secrets.md).

## <a name="step-3-configure-connected-applications"></a>Paso 3: Configurar aplicaciones conectadas

Para establecer la comunicación entre aplicaciones Dynamics 365 Finance o Dynamics 365 Supply Chain Management y Facturación electrónica, debe configurar Finance o Supply Chain Management para construir la llamada al servicio de Facturación electrónica y preparar los datos comerciales en una estructura unificada que se puede transformar al formato electrónico requerido. Las aplicaciones también deben procesar correctamente las respuestas del servicio. Puede completar esta configuración directamente en su entorno de Finance o Supply Chain Management, o puede completarla en Regulatory Configuration Service (RCS). Si completa la configuración en RCS, puede implementarla en su entorno de Finance o Supply Chain Management. En este paso, registrará la aplicación conectada para la implementación de parámetros.

Para completar este paso, consulte [Aplicaciones conectadas](e-invoicing-connected-applications.md).
