---
title: Componentes de la característica de globalización
description: Este tema proporciona información general sobre los componentes de la característica de globalización.
author: dkalyuzh
ms.date: 02/11/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: dkalyuzh
ms.search.validFrom: ''
ms.dyn365.ops.version: ''
ms.openlocfilehash: 87d7dd231b9ccda7761c91f129659c18039f3299
ms.sourcegitcommit: ffdb6794746ffe5461f9dcf34ed8e64976d22d2d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/02/2022
ms.locfileid: "8371827"
---
# <a name="globalization-feature-components"></a>Componentes de la característica de globalización

[!include [banner](../includes/banner.md)]

Una función de globalización es un conjunto de componentes que definen las reglas para la transformación de datos en configuraciones de informes electrónicos (ER). Estos componentes incluyen instrucciones para procesar documentos electrónicos y luego enviarlos o recibirlos de canales externos. También incluyen condiciones que definen cuándo se debe ejecutar una función para los datos comerciales entrantes.

Todos los componentes dependen unos de otros. Las funciones de globalización facilitan la creación y el mantenimiento de esta dependencia y admiten la gestión del ciclo de vida y el control de versiones del conjunto de componentes.

## <a name="access-electronic-invoicing-feature-components"></a>Acceso a los componentes de la característica de facturación electrónica 

1. Inicie sesión en su cuenta del Servicio de configuración reguladora (RCS).
2. En el espacio de trabajo **Características de globalización**, en la sección **Características**, seleccione el mosaico **Facturación electrónica**.

    Las características de globalización tienen varios componentes. La página **Funciones de facturación electrónica** incluye una pestaña separada para cada componente.

    - **Versión** – Este componente admite la gestión del ciclo de vida de la función. Puede usarlo para administrar el estado de diferentes versiones de la función.
    - **Configuraciones** – Este componente le permite administrar, ver y editar el formato ER relacionado y las configuraciones de asignación de formato que se utilizan en la canalización de procesamiento.
    - **Configuraciones**: este componente permite a los usuarios de servicios de globalización, como un servicio de facturación electrónica, administrar la configuración de la versión de la característica relacionada. Por lo tanto, apoya la construcción flexible de reglas de comunicación y respuestas.
    - **Entornos**: este componente permite a los usuarios de los servicios de globalización, como un servicio de facturación electrónica, gestionar el entorno donde se utiliza la configuración de la versión de la característica. También les permite otorgar autorización a los usuarios que tendrán acceso a la configuración de la versión de funciones.
    - **Organizaciones**: este componente permite a los usuarios compartir la característica con organizaciones externas.
    - **Etiquetas** – Este componente le permite etiquetar funciones que se pueden usar en el proyecto de Globalización para la referencia.
