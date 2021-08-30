---
title: Preguntas frecuentes sobre facturación electrónica
description: Este tema proporciona información sobre las preguntas frecuentes sobre facturación electrónica.
author: gionoder
ms.date: 04/21/2021
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
ms.dyn365.ops.version: AX 10.0.17
ms.openlocfilehash: 2d4e7c79c83b9d60469c2b87a7b9120e0d4c13a695badfb2254a85cee629c933
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2021
ms.locfileid: "6770521"
---
# <a name="electronic-invoicing-faq"></a>Preguntas más frecuentes sobre la facturación electrónica

[!include [banner](../includes/banner.md)]

Este tema proporciona respuestas a las preguntas frecuentes sobre e servicio de facturación electrónica. La facturación electrónica amplía las capacidades de facturación electrónica que existen en Dynamics 365 Finance, Dynamics 365 Supply Chain Management y Dynamics 365 Project Operations. 

## <a name="what-is-important-about-electronic-invoicing-and-why-should-it-matter-to-my-organization"></a>¿Qué es importante en la facturación electrónica y por qué debería importarle a mi organización?

La complejidad operativa y el riesgo continúan intensificándose a medida que las organizaciones crecen a nivel mundial y expanden su presencia en todas las regiones. Mantener el cumplimiento y adaptarse a las normativas que cambian con frecuencia es un desafío creciente, de particular importancia cuando se trata de la facturación. La facturación ha sido tradicionalmente cara y propensa a errores, ya que las empresas se basan en documentos en papel y procesos manuales intensivos.  

Las organizaciones han comenzado a alejarse de las facturas en papel para reducir los costos y acelerar el proceso de un extremo a otro. Las administraciones públicas están recurriendo cada vez más a la facturación electrónica como un componente clave de la digitalización fiscal. Al exigir a las organizaciones que envíen digitalmente información fiscal en tiempo real a las autoridades fiscales, los gobiernos pueden minimizar la evasión y manipulación fiscales y reducir el fraude. 

El mundo está cambiando al procesamiento de documentos sin papel y, sin implementar la facturación electrónica, los clientes pueden correr el riesgo de problemas de cumplimiento, costes innecesarios y quedarse por detrás de sus competidores. 

## <a name="doesnt-finance-supply-chain-management-and-project-operations-already-include-electronic-invoicing-functionality-what-value-does-this-provide-to-me-as-a-customer"></a>¿Finance, Supply Chain Management y Project Operations ya incluyen la funcionalidad de facturación electrónica? ¿Qué valor me aporta esto como cliente? 

La facturación electrónica amplía las capacidades de facturación electrónica que existen en Finance, Supply Chain Management y Project Operations. La funcionalidad también simplifica el cumplimiento de los estándares de facturación electrónica más recientes y proporciona experiencias coherentes para diferentes geografías en el procesamiento e intercambio de facturas electrónicas. Las capacidades de facturación electrónica desbloquean una serie de beneficios que incluyen: 

   - Adopción más rápida y sencilla de los requisitos específicos de cada país o región.
   - Estandarización de implementaciones de solución de facturación electrónica. 
   - Trazabilidad mejorada del procesamiento de facturas electrónicas.  
   - Mantenimiento más sencillo para cumplir con los requisitos legales cambiantes y las prácticas comerciales locales. 
   - Envasado de solución simplificado.
   - Capacidades de escalado para un gran volumen de documentos enviados que dan como resultado una respuesta más rápida.
   - Capacidad para compartir sus soluciones con otras empresas.

## <a name="does-electronic-invoicing-service-support-the-on-premises-installations-of-finance-supply-chain-management-and-project-operations"></a>¿El servicio de facturación electrónica es compatible con las instalaciones locales de Finance, Supply Chain Management y Project Operations? 

La plataforma actual no permite el uso de la versión local y no hay planes para admitirla en el futuro.

## <a name="does-electronic-invoicing-service-interface-with-the-vendor-import-automation-feature"></a>¿El servicio de facturación electrónica interactúa con la característica de automatización de importación de proveedores?

No. Hay planes para esta interfaz, pero no hay una escala de tiempo planificada. Cuando esté previsto, las fechas se anunciarán en los [Planes de lanzamiento](/dynamics365/release-plans/).

## <a name="how-does-electronic-invoicing-service-handle-file-attachments-into-the-electronic-invoice-is-a-sharepoint-server-needed-when-embedding-pdf-files-into-the-xml-file"></a>¿Cómo maneja el servicio de facturación electrónica los archivos adjuntos en la factura electrónica? ¿Es necesario un servidor de SharePoint al incrustar archivos PDF en el archivo XML?

Los archivos adjuntos a la factura electrónica se manejan como datos binarios incrustados en un elemento XML. No es necesario un servidor de SharePoint para incrustar archivos PDF, pero el archivo adjunto debe almacenarse en el sistema de gestión de documentos de Finance, Supply Chain Management y Project Operations.

## <a name="is-electronic-invoicing-service-available-according-to-the-regulations-of-my-countryregion"></a>¿Está disponible e servicio de facturación electrónica conforme a las regulaciones de mi país o región?

El servicio de facturación electrónica es una plataforma de microservicios que estará disponible a nivel mundial.

Microsoft planea publicar los formatos e integraciones de facturas electrónicas para los países con localización funcional por parte de Microsoft. Para más información, consulte [Disponibilidad de funciones de facturación electrónica](e-invoicing-configuration-rcs.md#availability-of-electronic-invoicing-features).

Si el formato de facturación electrónica para su país o región no aparece en la lista, la plataforma intentará contemplar este escenario en el futuro. Aún puede beneficiarse de las capacidades de configuración que tiene la facturación electrónica y configurar el formato de facturación electrónica usted mismo, o puede trabajar con un socio/ISV para configurarlos para su organización.

## <a name="is-dynamics-365-for-regulatory-services-a-new-module-like-human-resources-or-project-operations-that-is-linked-to-finance-or-supply-chain-management-are-there-extra-costs-for-that"></a>¿Es Dynamics 365 para Regulatory Services un módulo nuevo como Human Resources o Project Operations que está vinculado a Finance o Supply Chain Management? ¿Hay costos adicionales por eso?

Dynamics 365 para Regulatory Services (RCS) es un servicio en la nube para configurar recursos de globalización. RCS es gratuito para todos los titulares de licencias de Finance, Supply Chain Management y Project Operations.

Para registrarse en RCS, vaya a <https://marketing.configure.global.dynamics.com/>.

Para más información, consulte [Regulatory Configuration Services (RCS): características de globalización](rcs-globalization-feature.md).

## <a name="do-i-need-to-sign-up-to-get-electronic-invoicing-service-or-just-turn-it-on-in-feature-management"></a>¿Necesito registrarme para obtener el servicio de facturación electrónica o simplemente activarla en Administración de funciones?

Si tiene una licencia para Finance, Supply Chain Management y Project Operations, consulte [Comenzar con la administración de servicios de facturación electrónica](e-invoicing-get-started-service-administration.md) para suscribirse a la facturación Electrónica.

## <a name="does-electronic-invoicing-service-work-with-tier-1-virtual-machines-what-is-the-minimal-required-environment"></a>¿El servicio de facturación electrónica funciona con máquinas virtuales de nivel 1? ¿Cuál es el entorno mínimo requerido?

La integración con el servicio de facturación electrónica requiere al menos una máquina virtual de nivel 2 para alojar Finance o Supply Chain Management. Para obtener más información sobre planificación de ambientes, consulte [Planificación de ambientes](../../fin-ops-core/fin-ops/imp-lifecycle/environment-planning.md).

## <a name="does-electronic-invoicing-service-have-a-test-mode-for-testing-invoice-submission"></a>¿El servicio de facturación electrónica tiene un modo de prueba para probar el envío de facturas?

Esto se puede lograr mediante la configuración. Para probar el envío de facturas, puede conectarse a Finance o Supply Chain Management desde un entorno de prueba de aceptación de usuarios (UAT) y enviar las facturas de prueba. La facturación electrónica admite la configuración de certificados digitales de prueba y, en el caso de facturas electrónicas que requieran aprobación digital, la configuración de una URL de los servicios web de prueba publicados por las autoridades fiscales.

## <a name="is-there-any-documentation-about-the-out-of-box-country-specific-electronic-invoicing-features"></a>¿Existe alguna documentación sobre las funciones de facturación electrónica específicas del país listas para usar?

Sí. Para obtener información sobre la disponibilidad de las características de facturación electrónica y los formatos que admiten, consulte [Disponibilidad de características de facturación electrónica](e-invoicing-configuration-rcs.md#availability-of-electronic-invoicing-features).

## <a name="does-the-electronic-invoicing-service-allow-a-legal-entity-in-finance-or-supply-chain-management-that-is-configured-for-a-specific-country-to-consume-electronic-invoicing-features-from-different-countryregions"></a>¿El servicio de facturación electrónica permite que una entidad legal de Finance o Supply Chain Management que esté configurada para un país específico consuma características de facturación electrónica de diferentes países o regiones?

Sí. Las funciones de facturación electrónica se pueden utilizar para procesar envíos de documentos comerciales independientemente del país de la entidad jurídica, si se cumple lo siguiente:

   - El documento comercial que se genera utiliza la asignación del modelo de documento apropiado.
   - Existe una coincidencia entre el documento comercial y las reglas de aplicabilidad configuradas en la función de facturación electrónica.

## <a name="does-the-electronic-invoicing-service-use-the-same-configuration-and-design-experience-provided-by-the-electronic-reporting-module-in-finance-and-supply-chain-management"></a>¿El servicio de facturación electrónica utiliza la misma experiencia de configuración y diseño proporcionada por el módulo de informes electrónicos en Finance y Supply Chain Management? 

Sí. Las mismas herramientas de diseño que se utilizan en el módulo de informes electrónicos (ER) en Finance y Supply Chain Management se utilizan para crear y configurar la asignación del modelo de datos y las configuraciones de formato de archivo. Estas herramientas de diseño también se utilizan en Regulatory Configuration Services (RCS) para crear y configurar la asignación del modelo de datos y las configuraciones de formato de archivo que se utilizan en la configuración de las funciones de facturación electrónica.

## <a name="can-the-applicability-rules-be-extended-and-configured-so-that-they-arent-tied-to-any-specific-parameter-such-as-a-legal-entity"></a>¿Se pueden extender y configurar las reglas de aplicabilidad para que no estén vinculadas a ningún parámetro específico, como una entidad jurídica?

Sí. Las reglas de aplicabilidad son completamente configurables. Puede agregar o eliminar cláusulas, crear operaciones lógicas y agrupar y desagrupar cláusulas. Para obtener más información, consulte [Reglas de aplicabilidad](e-invoicing-configuration-rcs.md?toc=/dynamics365/finance/toc.json#applicability-rules).

## <a name="does-the-electronic-invoicing-service-support-adding-other-er-format-configurations-to-generate-other-types-of-documents-does-it-support-sending-the-documents-electronically-to-customers-such-as-a-delivery-note"></a>¿El servicio de facturación electrónica admite la adición de otras configuraciones de formato ER para generar otros tipos de documentos? ¿Admite el envío de documentos a los clientes de forma electrónica, como una nota de entrega?

Puede utilizar otras configuraciones de formato ER para producir los archivos de salida deseados. Sin embargo, la configuración del formato ER debe derivarse de la misma asignación del modelo de factura ER que está configurada en Finance o Supply Chain Management para generar documentos comerciales. La facturación electrónica no admite el envío del archivo de salida directamente al cliente como una transacción EDI.

## <a name="does-the-electronic-invoicing-service-support-exchanging-electronic-invoices-with-customers-does-it-support-configuring-different-invoice-formats-for-the-same-invoice"></a>¿El servicio de facturación electrónica admite el intercambio de facturas electrónicas con los clientes? ¿Admite la configuración de diferentes formatos de factura para la misma factura?

La capacidad de recibir e importar facturas electrónicas de proveedores está en la hoja de ruta, pero actualmente no se admite el envío automático de facturas electrónicas a los clientes.

## <a name="does-the-electronic-invoicing-service-extend-to-support-exchanging-edi-messages-with-other-companies"></a>¿Se extiende el servicio de facturación electrónica para admitir el intercambio de mensajes EDI con otras empresas?

El enfoque del servicio de facturación electrónica es intercambiar tipos de mensajes de facturas electrónicas impulsados por los requisitos de cumplimiento normativo. Recibir e importar facturas electrónicas de proveedores está en la hoja de ruta, pero el envío de archivos de facturas electrónicas a los clientes actualmente no es compatible de forma inmediata, excepto en escenarios donde enviar la factura electrónica al cliente es un requisito normativo.

## <a name="does-the-electronic-invoicing-service-support-importing-or-merging-customizations-made-in-the-er-format-configurations-from-the-legacy-electronic-invoicing-feature"></a>¿El servicio de facturación electrónica admite la importación o combinación de personalizaciones realizadas en las configuraciones de formato ER desde la función de facturación electrónica heredada?

Puede reutilizar configuraciones de formato de ER en el servicio de facturación electrónica. Sin embargo, la configuración del formato ER debe derivarse de la misma asignación del modelo de factura ER que la característica de factura electrónica está diseñada para usar, y que está configurado en Finance o Supply Chain Management para generar los documentos comerciales.

## <a name="does-the-electronic-invoicing-service-support-issuing-electronic-invoices-from-custom-made-tables-if-so-how-do-you-create-the-er-data-model-configurations-for-these-new-tables-and-entities"></a>¿El servicio de facturación electrónica admite la emisión de facturas electrónicas para tablas creadas a medida? Si es así, ¿cómo se crean las configuraciones del modelo de datos ER para estas nuevas tablas y entidades?

Sí. Sin embargo, requiere personalizar la asignación del modelo de factura y agregar las referencias necesarias a las tablas hechas a medida, o dependiendo de la complejidad, crear una nueva asignación del modelo de factura.

## <a name="does-the-electronic-invoicing-service-support-different-web-service-endpoints"></a>¿El servicio de facturación electrónica admite diferentes puntos de conexión de servicio web?

La facturación electrónica admite diferentes puntos de conexión de servicios web. Puede utilizar la integración configurable con los servicios web REST o una serie de integraciones de servicios web parametrizados y específicos del país. Se pueden configurar diferentes puntos de conexión para los mismos servicios web y API utilizando diferentes versiones de configuraciones. Para obtener más información, consulte [Lista de parámetros por acción](e-invoicing-setup.md#list-of-parameters-by-action).

## <a name="is-electronic-invoicing-integrated-with-the-various-invoice-operators-apis-from-the-nordic-countries-or-should-that-be-handled-on-a-case-by-case-basis"></a>¿La facturación electrónica está integrada con las API de los distintos operadores de facturación de los países nórdicos, o debería tratarse caso por caso?

Microsoft amplía continuamente la cobertura funcional para proporcionar integraciones listas para usar mediante el uso de las funciones de facturación electrónica. Para obtener más información sobre los formatos y las integraciones compatibles, consulte [Disponibilidad de funciones de facturación electrónica](e-invoicing-configuration-rcs.md?toc=/dynamics365/finance/toc.json#availability-of-electronic-invoicing-features).

> [!NOTE] 
> Si no encontró la respuesta que buscaba, envíe su pregunta por correo electrónico al Equipo de Desarrollo de Producto, a <D365EInvoicePreview@microsoft.com>. Nos comunicaremos con usted o mejoraremos la cobertura de estas preguntas frecuentes.
