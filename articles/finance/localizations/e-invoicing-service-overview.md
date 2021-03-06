---
title: Información general sobre facturación electrónica
description: Este tema proporciona información sobre cómo configurar la facturación electrónica en Microsoft Dynamics 365 Finance y Dynamics 365 Supply Chain Management.
author: gionoder
ms.date: 03/29/2021
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
ms.openlocfilehash: a6a8ea3fcad980dc02f489e07a7b21fe1c1b5a5a
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/01/2021
ms.locfileid: "5839989"
---
# <a name="electronic-invoicing-overview"></a>Información general sobre facturación electrónica

[!include [banner](../includes/banner.md)]

La facturación electrónica para Microsoft Dynamics 365 Finance y Dynamics 365 Supply Chain Management es un servicio multiinquilino hiperescalable que permite el procesamiento configurable de documentos de facturas electrónicas y el intercambio de documentos configurables. Las reglas de procesamiento e integración son completamente configurables y la lógica se ejecuta fuera de Finance y Supply Chain Management. El servicio está dirigido principalmente al procesamiento de facturas electrónicas en escenarios de empresa a gobierno, pero se puede configurar a medida para otros fines.

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

Para utilizar la facturación electrónica, debe instalarla desde su proyecto en Microsoft Dynamics Lifecycle Services (LCS). A continuación, siga el procedimiento de configuración para activar la integración con Finance o Supply Chain Management. Para obtener más información, vea [Introducción a la facturación electrónica](e-invoicing-get-started.md).

## <a name="service-availability"></a><a name="availability"></a>Disponibilidad del servicio

Actualmente, la facturación electrónica está disponible para los clientes a través del programa de versión preliminar y, en la siguiente fase, el servicio estará disponible para todos. Debido a que la funcionalidad que aborda los requisitos específicos del país o región puede estar limitada en diferentes fases de la versión, siempre debe consultar la documentación más actualizada que resalte la cobertura y el alcance de las soluciones específicas del país o región compatibles.

La facturación electrónica se implementa en las siguientes geografías de Azure:

- Estados Unidos
- Europa

> [!NOTE]
> La facturación electrónica no admite implementaciones locales.

## <a name="extended-configurability"></a>Configurabilidad ampliada

La facturación electrónica se puede utilizar en escenarios en los que debe crear y enviar un documento electrónico a las partes designadas. Está diseñado específicamente para ejecutar un flujo configurable de acciones de procesamiento, según los datos recibidos. Las opciones de configuración que están disponibles en Finance and Supply Chain Management se limitan a la transformación de documentos. El servicio amplía estas opciones agregando las integraciones configurables que están disponibles en él. Además, todas las funcionalidades de factura electrónica que estaban disponibles anteriormente, como la Nota fiscal electrónica brasileña (NF-e), el Comprobante Fiscal Digital por Internet mexicano (CFDI), u otro Lenguaje Universal de Negocios de Europa Occidental (UBL) / Público Pan-Europeo Las funcionalidades de Adquisición en línea (PEPPOL) utilizarán configuraciones para exportar e importar y permitir integraciones con servicios web externos.

## <a name="feature-highlights"></a>Características destacadas

- Integración inmediata con la gestión de Finance y Supply Chain management
- Experiencia de usuario consistente para la configuración y monitoreo del proceso de factura electrónica para todos los países o regiones
- Adopción más rápida, fácil y menos costosa de soluciones de facturación electrónica en nuevos países o regiones
- Configuración del servicio a través del Servicio de configuración regulatoria (RCS) y la configuración de la característica de globalización
- Transformación de datos comerciales en varios formatos de factura electrónica (XML, notación de objetos JavaScript \[JSON\], TXT y valores separados por comas \[CSV\]) mediante el uso de configuraciones que se definen en RCS:

    - Formatos de informes electrónicos que están disponibles para países o regiones donde la configuración para la transformación de facturas electrónicas no está disponible

- Envío configurable de facturas electrónicas a servicios web externos, incluida la gestión de certificaciones a través de firmas digitales:

    - Integración incorporada, fácilmente ampliable y configurable con contenido adicional para varios países o regiones

    > [!NOTE]
    > Actualmente, se admite un número limitado de envíos directos. Para obtener más información, consulte la sección [Disponibilidad de servicio](#availability) descrita anteriormente en este tema. El soporte se ampliará en el futuro.

- Manejo de respuestas de servicios web, incluido el manejo de mensajes de excepción configurables
- Soporte para firmas electrónicas (por ejemplo, mediante el uso del algoritmo de firma XMLDSig)
- Procesamiento por lotes de mensajes de factura electrónica

## <a name="architecture-and-data-flow"></a>Arquitectura y flujo de datos

Cuando se instala la facturación electrónica desde LCS y se completa la configuración requerida en todas las aplicaciones requeridas, se establece una conexión segura. El servicio se encuentra actualmente en centros de datos de Estados Unidos y Europa. Por lo tanto, la ubicación del servicio puede diferir de la ubicación de la instancia relacionada de Finance o Supply Chain Management. Después de completar la configuración de la facturación electrónica y activar la integración, cada vez que se envía una factura electrónica, los datos maestros y los datos transaccionales que están relacionados con un documento específico se envían a la facturación electrónica.

> [!NOTE]
> Si su factura electrónica o cualquier otro documento contiene datos personales, verifique que el uso de esta característica cumpla con el Reglamento General de Protección de Datos (GDPR) y otras regulaciones relacionadas con la transferencia de datos personales.

### <a name="high-level-description-of-the-data-flow"></a>Descripción de alto nivel del flujo de datos

1. El cliente envía un documento comercial canónico al servicio.
2. Según la información de contexto que se recibe del cliente, el servicio selecciona el flujo de procesamiento aplicable.
3. El servicio ejecuta las acciones de procesamiento. Estas acciones pueden incluir transformar el documento comercial en una factura electrónica, aplicar una firma electrónica y enviar el documento a un servicio web externo.
4. Todos los documentos recibidos y procesados se almacenan en Azure Blob Storage del cliente.
5. Todos los certificados y secretos de inquilinos que se usaron para el procesamiento se almacenan en el almacén de claves de Azure del cliente.
6. El servicio proporciona información bajo demanda al cliente sobre el estado de procesamiento del documento comercial que se envió.
7. El cliente recibe información sobre la ejecución del procesamiento completado y pone a disposición toda la información del registro. También hace que el documento creado o recibido durante el procesamiento de flujo esté disponible.

La siguiente ilustración muestra cómo fluyen los datos hacia y desde la facturación electrónica.

![Flujo de datos para la facturación electrónica](media/e-invoicing-service-data-flow-diagram-overview.png)

## <a name="privacy-notice"></a>Aviso de privacidad
Habilitar y usar la facturación electrónica puede requerir el envío de datos limitados, que incluyen el ID de registro fiscal de la organización. Este será transmitido a agencias de terceros autorizadas por las autoridades tributarias para propósitos de enviar facturas electrónicas a esta autoridad tributaria en los formatos predefinidos requeridos para la integración con los servicios web del gobierno. Los datos importados de estos sistemas externos a este servicio en línea de Dynamics 365 están sujetos a nuestra [declaración de privacidad](https://go.microsoft.com/fwlink/?LinkId=512132). Consulte las secciones de Aviso de privacidad en la documentación de características específicas de cada país o región para obtener más información.

## <a name="additional-resources"></a>Recursos adicionales
- [Administración de servicios](e-invoicing-service-administration.md)
- [Configurar facturas electrónicas en RCS](e-invoicing-configuration-rcs.md)
- [Emitir facturas electrónicas en Finance y Supply Chain Management](e-invoicing-issuing-electronic-invoices-finance-supply-chain-management.md)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
