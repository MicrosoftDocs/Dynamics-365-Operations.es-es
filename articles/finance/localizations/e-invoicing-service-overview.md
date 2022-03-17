---
title: Información general sobre facturación electrónica
description: Este tema proporciona información general sobre la Facturación electrónica en Microsoft Dynamics 365 Finance y Dynamics 365 Supply Chain Management.
author: gionoder
ms.date: 01/21/2022
ms.topic: overview
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
ms.openlocfilehash: 23a98706bc2ab0abc2c72e9f20d8e8fbff56b2b9
ms.sourcegitcommit: ffdb6794746ffe5461f9dcf34ed8e64976d22d2d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/02/2022
ms.locfileid: "8371463"
---
# <a name="electronic-invoicing-overview"></a>Información general sobre facturación electrónica

[!include [banner](../includes/banner.md)]

La facturación electrónica para Microsoft Dynamics 365 Finance y Dynamics 365 Supply Chain Management es un servicio multiinquilino hiperescalable que permite el procesamiento configurable de facturas electrónicas y el intercambio de documentos electrónicos configurables. Las reglas de procesamiento e integración son completamente configurables y la lógica se ejecuta fuera de Finance y Supply Chain Management. El servicio está dirigido principalmente al procesamiento de documentos de facturas electrónicas en escenarios de empresa a administración pública. Sin embargo, se puede configurar de forma personalizada para otros fines, como escenarios de empresa a empresa para diferentes tipos de documentos.

La facturación electrónica puede ayudarle a lograr los siguientes objetivos:

- Adopción rápida y sencilla de los requisitos específicos de cada país o región
- Implementaciones estandarizadas de una solución de facturación electrónica
- Trazabilidad mejorada del historial de documentos
- Ciclo de implementación más corto
- Reducción del costo total de propiedad (TCO)
- Configuraciones fácilmente ajustables que no requieren cambios de código
- Empaquetado de configuración simplificado
- Exportación, importación e integración incorporadas, y fácil ampliación en el procesamiento de documentos de factura electrónica
- Fácil reutilización de las mismas configuraciones de exportación, importación e integración en todas las empresas

## <a name="service-availability"></a>Disponibilidad del servicio

Actualmente, la funcionalidad de Facturación electrónica está disponible para los clientes de Finance y Supply Chain Management. Para obtener más información, revise los términos y condiciones de la licencia de su aplicación.

Debido a que la funcionalidad que aborda los requisitos específicos del país o región puede estar limitada en diferentes fases de la versión, siempre debe consultar la documentación más actualizada que resalte la cobertura y el alcance de las soluciones específicas del país o región compatibles.

La facturación electrónica se implementa en las siguientes geografías de Azure:

- Estados Unidos
- Europa
- Asia

> [!NOTE]
> La facturación electrónica no admite implementaciones locales.

## <a name="feature-highlights"></a>Características destacadas

- Integración inmediata con la gestión de Finance y Supply Chain Management
- Experiencia de usuario coherente para la configuración y supervisión del proceso de factura electrónica para todos los países y regiones
- Adopción más rápida, fácil y menos costosa de soluciones de facturación electrónica en nuevos países o regiones
- Configuración del servicio a través de la configuración de las características de globalización y Regulatory Configuration Service (RCS)
- Transformación de datos comerciales en varios formatos de factura electrónica (XML, notación de objetos JavaScript \[JSON\], TXT y valores separados por comas \[CSV\]) mediante el uso de configuraciones que se definen en RCS:

    - Formatos de informes electrónicos que están disponibles para países y regiones donde la configuración para la transformación de facturas electrónicas no está disponible

- Envío configurable de facturas electrónicas a servicios web externos, incluida la gestión de certificaciones a través de firmas digitales:

    - Integración incorporada, fácilmente ampliable y configurable con contenido adicional para varios países y regiones

- Manejo de respuestas de servicios web, incluido el manejo configurable de mensajes de excepción
- Soporte para firmas electrónicas (por ejemplo, firmas electrónicas que usan el algoritmo de firma XMLDSig)
- La capacidad de enviar documentos a correos electrónicos y almacenarlos en SharePoint
- Procesamiento por lotes de mensajes de factura electrónica
- Transformación configurable de documentos entrantes y procesamiento de esos documentos en Finance y Supply Chain Management
- La capacidad de recibir documentos entrantes de canales como correo electrónico y SharePoint

## <a name="privacy-notice"></a>Aviso de privacidad

Habilitar y usar la facturación electrónica puede requerir que se envíen datos limitados. Estos datos incluyen el número de identificación fiscal de la organización. Estos se transmitirán a agencias de terceros autorizadas por las autoridades tributarias para propósitos de enviar facturas electrónicas a esta autoridad tributaria en los formatos predefinidos requeridos para la integración con los servicios web del gobierno. Los datos que se importan de estos sistemas externos a este servicio en línea de Dynamics 365 están sujetos a nuestra [declaración de privacidad](https://go.microsoft.com/fwlink/?LinkId=512132). Para más información, vea la sección "Aviso de privacidad" en la documentación de características específicas de cada país o región.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
