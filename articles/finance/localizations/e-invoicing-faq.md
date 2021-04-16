---
title: Preguntas frecuentes sobre facturación electrónica
description: Este tema proporciona información sobre las preguntas frecuentes sobre facturación electrónica.
author: gionoder
ms.date: 03/17/2021
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
ms.dyn365.ops.version: AX 10.0.17
ms.openlocfilehash: 41cddcdad5043ec314a94dda67f4f2e9de406cac
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/01/2021
ms.locfileid: "5840181"
---
# <a name="electronic-invoicing-faq"></a>Preguntas frecuentes sobre facturación electrónica

[!include [banner](../includes/banner.md)]

Este tema proporciona respuestas a las preguntas frecuentes sobre facturación electrónica. La facturación electrónica amplía las capacidades de facturación electrónica que existen en Dynamics 365 Finance, Dynamics 365 Supply Chain Management y Dynamics 365 Project Operations. 

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

## <a name="does-electronic-invoicing-support-the-on-premises-installations-of-finance-supply-chain-management-and-project-operations"></a>¿La facturación electrónica es compatible con las instalaciones locales de Finance, Supply Chain Management y Project Operations? 

La plataforma actual no permite el uso de la versión local y no hay planes para admitirla en el futuro.

## <a name="does-electronic-invoicing-interface-with-the-vendor-import-automation-feature"></a>¿La facturación electrónica interactúa con la característica de automatización de importación de proveedores?

No. Hay planes para esta interfaz, pero no hay una escala de tiempo planificada. Cuando esté previsto, las fechas se anunciarán en los [Planes de lanzamiento](https://docs.microsoft.com/dynamics365/release-plans/).

## <a name="how-does-electronic-invoicing-handle-file-attachments-into-the-electronic-invoice-is-a-sharepoint-server-needed-when-embedding-pdf-files-into-the-xml-file"></a>¿Cómo maneja la facturación electrónica los archivos adjuntos en la factura electrónica? ¿Es necesario un servidor de SharePoint al incrustar archivos PDF en el archivo XML?

Los archivos adjuntos a la factura electrónica se manejan como datos binarios incrustados en un elemento XML. No es necesario un servidor de SharePoint para incrustar archivos PDF, pero el archivo adjunto debe almacenarse en el sistema de gestión de documentos de Finance, Supply Chain Management y Project Operations.

## <a name="is-electronic-invoicing-available-according-to-the-regulations-of-my-countryregion"></a>¿Está disponible la facturación electrónica conforme a las regulaciones de mi país o región?

La facturación electrónica es una plataforma de microservicios que estará disponible a nivel mundial.

Microsoft planea publicar los formatos e integraciones de facturas electrónicas para los países con localización funcional por parte de Microsoft. Para más información, consulte [Disponibilidad de funciones de facturación electrónica](e-invoicing-configuration-rcs.md#availability-of-electronic-invoicing-features).

Si el formato de facturación electrónica para su país o región no aparece en la lista, la plataforma intentará contemplar este escenario en el futuro. Aún puede beneficiarse de las capacidades de configuración que tiene la facturación electrónica y configurar el formato de facturación electrónica usted mismo, o puede trabajar con un socio/ISV para configurarlos para su organización.

## <a name="is-dynamics-365-for-regulatory-services-a-new-module-like-human-resources-or-project-operations-that-is-linked-to-finance-or-supply-chain-management-are-there-extra-costs-for-that"></a>¿Es Dynamics 365 para Regulatory Services un módulo nuevo como Human Resources o Project Operations que está vinculado a Finance o Supply Chain Management? ¿Hay costos adicionales por eso?

Dynamics 365 para Regulatory Services (RCS) es un servicio en la nube para configurar recursos de globalización. RCS es gratuito para todos los titulares de licencias de Finance, Supply Chain Management y Project Operations.

Para registrarse en RCS, vaya a <https://marketing.configure.global.dynamics.com/>.

Para más información, consulte [Regulatory Configuration Services (RCS): características de globalización](rcs-globalization-feature.md).

## <a name="do-i-need-to-sign-up-to-get-electronic-invoicing--or-just-turn-it-on-in-feature-management"></a>¿Necesito registrarme para obtener la facturación electrónica o simplemente activarla en Administración de funciones?

Si tiene una licencia para Finance, Supply Chain Management y Project Operations, consulte [Comenzar con la administración de servicios de facturación electrónica](e-invoicing-get-started-service-administration.md) para suscribirse a la facturación Electrónica.

## <a name="does-electronic-invoicing-work-with-tier-1-virtual-machines-what-is-the-minimal-required-environment"></a>¿La facturación electrónica funciona con máquinas virtuales de nivel 1? ¿Cuál es el entorno mínimo requerido?

La integración con la facturación electrónica requiere al menos una máquina virtual de nivel 2 para alojar Finance o Supply Chain Management. Para obtener más información sobre planificación de ambientes, consulte [Planificación de ambientes](../../fin-ops-core/fin-ops/imp-lifecycle/environment-planning.md).

## <a name="does-electronic-invoicing-have-a-test-mode-for-testing-invoice-submission"></a>¿La facturación electrónica tiene un modo de prueba para probar el envío de facturas?

Esto se puede lograr mediante la configuración. Para probar el envío de facturas, puede conectarse a Finance o Supply Chain Management desde un entorno de prueba de aceptación de usuarios (UAT) y enviar las facturas de prueba. La facturación electrónica admite la configuración de certificados digitales de prueba y, en el caso de facturas electrónicas que requieran aprobación digital, la configuración de una URL de los servicios web de prueba publicados por las autoridades fiscales.

## <a name="is-there-any-documentation-about-the-out-of-box-country-specific-electronic-invoicing-features"></a>¿Existe alguna documentación sobre las funciones de facturación electrónica específicas del país listas para usar?

Sí. Para obtener información sobre la disponibilidad de las características de facturación electrónica y los formatos que admiten, consulte [Disponibilidad de características de facturación electrónica](e-invoicing-configuration-rcs.md#availability-of-electronic-invoicing-features).

> [!NOTE] 
> Si no encontró la respuesta que buscaba, envíe su pregunta por correo electrónico al Equipo de Desarrollo de Producto, a <D365EInvoicePreview@microsoft.com>. Nos comunicaremos con usted o mejoraremos la cobertura de estas preguntas frecuentes.
