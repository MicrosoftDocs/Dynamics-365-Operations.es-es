---
title: Comenzar con la facturación electrónica
description: Este tema proporciona información que le ayudará a comenzar con la facturación electrónica en Microsoft Dynamics 365 Finance y Dynamics 365 Supply Chain Management.
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
ms.openlocfilehash: cf553f2ffecf18859b88932e68360231ca46410f
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/01/2021
ms.locfileid: "5840133"
---
# <a name="get-started-with-electronic-invoicing"></a>Comenzar con la facturación electrónica

[!include [banner](../includes/banner.md)]

Este tema proporciona información que le ayudará a comenzar con la facturación electrónica. Este tema le guía a través de los pasos de configuración comunes en Regulatory Configuration Services (RCS) y Dynamics 365 Finance y proporciona los pasos que debe seguir para enviar documentos comerciales y revisar los resultados del procesamiento.

## <a name="prerequisites"></a>Requisitos previos

Antes de que pueda completar los procedimientos de este tema, debe tener preparados los siguientes requisitos previos:

- Configure Microsoft Dynamics Lifecycle Services (LCS), Regulatory Configuration Service (RCS) y su ambiente de Microsoft Dynamics 365 Finance o Dynamics 365 Supply Chain Management. Para más información, consulte [Comenzar con la administración de la facturación electrónica](e-invoicing-get-started-service-administration.md).
- Cree un proveedor de configuración para su organización. Para obtener más información, consulte [Crear proveedores de configuración y marcarlos como activos](../../fin-ops-core/dev-itpro/analytics/tasks/er-configuration-provider-mark-it-active-2016-11.md).

## <a name="import-an-electronic-invoicing-feature-from-the-microsoft-configuration-provider"></a>Importar una característica de facturación electrónica desde cualquier proveedor de configuración 

1. Inicie sesión en su cuenta del Servicio de configuración reguladora (RCS).
2. En el espacio de trabajo **Características de globalización**, en la sección **Características**, seleccione el mosaico **Facturación electrónica**.
3. Seleccione **Importar** y, a continuación, **Sincronizar**.
4. Filtre la columna **Proveedor de configuración** por el término **Microsoft**.
5. Seleccione el nombre de una característica de facturación electrónica de la tabla al principio de este tema y luego seleccione **Importar**.

## <a name="create-an-electronic-invoicing-feature-under-your-organization-provider"></a>Crear una característica de facturación electrónica para su proveedor de organización

1. En RCS, en la sección **Características** del espacio de trabajo **Característica de globalización**, seleccione el mosaico **Facturación electrónica**.
2. Seleccione **Añadir** > **Basado en una característica existente**, y en el campo **Nombre**, introduzca el nombre de la característica de facturación electrónica.
3. En el campo **Descripción**, introduzca una descripción de la característica.
4. En el **Campo de característica base**, seleccione la característica de facturación electrónica importada del proveedor de configuración de Microsoft.
5. Seleccione **Crear característica**.

## <a name="country-specific-configuration-for-electronic-invoicing-feature"></a>Configuración específica del país para la función de facturación electrónica

Según el país o la región, la característica de facturación electrónica puede requerir una configuración específica. 

Para conocer los pasos específicos, consulte la documentación "Comenzar" que está disponible para su país o región.

## <a name="import-the-model-mapping-configurations-from-electronic-reporting"></a>Importar las configuraciones de asignación de modelo desde informes electrónicos

1. En RCS, seleccione el espacio de trabajo **Informes electrónicos**.
2. En la lista de proveedores de configuración de **Microsoft**, seleccione **Repositorios**.
3. Seleccione **Global** y en el Panel de acciones, seleccione **Abrir**.
4. Importe las configuraciones de asignación de modelo de acuerdo con la siguiente tabla, por nombre de característica.

| Nombre de característica                         | Configuración de asignación del modelo ER |
|--------------------------------------|-----------------------------|
| Facturas electrónicas para Austria (AT)    | <p>Modelo de contexto de factura de cliente</p><p>Modelo de factura</p> |
| Factura electrónica para Bélgica (BE)      | <p>Modelo de contexto de factura de cliente</p><p>Modelo de factura</p> |
| NF-e brasileño (BR)                  | <p>Modelo de contexto de factura de cliente</p><p>Documentos fiscales</p><p>Modelo de mensaje de respuesta</p> |
| NFS-e brasileño ABRASF Curitiba (BR) | <p>Modelo de contexto de factura de cliente</p><p>Documentos fiscales</p><p>Modelo de mensaje de respuesta</p> |
| Factura electrónica para Dinamarca (DK)       | <p>Modelo de contexto de factura de cliente</p><p>Modelo de factura</p> |
| Factura electrónica egipcia (EG)     | <p>Modelo de contexto de factura de cliente</p><p>Modelo de factura</p><p>Modelo de mensaje de respuesta</p> |
| Factura electrónica para Estonia (EE)     | <p>Modelo de contexto de factura de cliente</p><p>Modelo de factura</p> |
| Factura electrónica finlandesa (FI)       | <p>Modelo de contexto de factura de cliente</p><p>Modelo de factura</p> |
| Factura electrónica para Francia (FR)       | <p>Modelo de contexto de factura de cliente</p><p>Modelo de factura</p> |
| Factura electrónica para Alemania (DE)       | <p>Modelo de contexto de factura de cliente</p><p>Modelo de factura</p> |
| FatturaPA (IT)                       | <p>Modelo de contexto de factura de cliente</p><p>Modelo de factura</p> |
| Interfactura CFDI mexicana (MX)       | <p>Modelo de contexto de factura de cliente</p><p>Modelo de factura</p><p>Modelo de mensaje de respuesta</p> |
| Factura electrónica para Países Bajos (NL)        | <p>Modelo de contexto de factura de cliente</p><p>Modelo de factura</p> |
| Factura electrónica para Noruega (NO)    | <p>Modelo de contexto de factura de cliente</p><p>Modelo de factura</p> |
| Factura electrónica para España (ES)      | <p>Modelo de contexto de factura de cliente</p><p>Modelo de factura</p> |
| Factura electrónica PEPPOL            | <p>Modelo de contexto de factura de cliente</p><p>Modelo de factura</p> |


## <a name="configure-the-application-setup"></a>Configurar la aplicación

1. Seleccione la característica de facturación electrónica que creó.
2. En la pestaña **Configuraciones**, seleccione **Configuración de la aplicación**.
3. En el campo **Conectar aplicación**, seleccione la conexión que está asociada con su instancia de Finance o Supply Chain Management.
4. En la sección **Tipos de documentos electrónicos**, seleccione **Agregar**.
5. Seleccione e introduzca un valor **Nombre de tabla** de acuerdo con la siguiente tabla.

    | Nombre de característica                         | Documento empresarial | Nombre de la tabla |
    |--------------------------------------|-------------------|------------|
    | Facturas electrónicas para Austria (AT)    | <p>Factura de ventas</p><p>Factura de proyecto</p> | <p>Diario de facturas del cliente</p><p>Factura de proyecto</p> |
    | Factura electrónica para Bélgica (BE)      | <p>Factura de ventas</p><p>Factura de proyecto</p> | <p>Diario de facturas del cliente</p><p>Factura de proyecto</p> |
    | NF-e brasileño (BR)                  | <p>Documento fiscal</p><p>Carta de corrección</p> | Documento fiscal |
    | NFS-e brasileño ABRASF Curitiba (BR) | Documentos fiscales de servicios | Documento fiscal |
    | Factura electrónica para Dinamarca (DK)       | <p>Factura de ventas</p><p>Factura de proyecto</p> | <p>Diario de facturas del cliente</p><p>Factura de proyecto</p> |
    | Factura electrónica egipcia (EG)     | <p>Factura de ventas</p><p>Factura de proyecto</p> | <p>Diario de facturas del cliente</p><p>Factura de proyecto</p> |
    | Factura electrónica para Estonia (EE)     | <p>Factura de ventas</p><p>Factura de proyecto</p> | <p>Diario de facturas del cliente</p><p>Factura de proyecto</p> |
    | Factura electrónica finlandesa (FI)       | <p>Factura de ventas</p><p>Factura de proyecto</p> | <p>Diario de facturas del cliente</p><p>Factura de proyecto</p> |
    | Factura electrónica para Francia (FR)       | <p>Factura de ventas</p><p>Factura de proyecto</p> | <p>Diario de facturas del cliente</p><p>Factura de proyecto</p> |
    | Factura electrónica para Alemania (DE)       | <p>Factura de ventas</p><p>Factura de proyecto</p> | <p>Diario de facturas del cliente</p><p>Factura de proyecto</p> |
    | FatturaPA (IT)                       | <p>Factura de ventas</p><p>Factura de proyecto | <p>Diario de facturas del cliente</p><p>Factura de proyecto</p> |
    | Interfactura CFDI mexicana (MX)       | <p>Factura de ventas</p><p>Traslado</p><p>Transferencia de inventario</p><p>Complemento de pago</p> | Diario de facturas del cliente |
    | Factura electrónica para Países Bajos (NL)        | <p>Factura de ventas</p><p>Factura de proyecto</p> | <p>Diario de facturas del cliente</p><p>Factura de proyecto</p> |
    | Factura electrónica para Noruega (NO)    | <p>Factura de ventas</p><p>Factura de proyecto</p> | <p>Diario de facturas del cliente</p><p>Factura de proyecto</p> |
    | Factura electrónica para España (ES)      | <p>Factura de ventas</p><p>Factura de proyecto</p> | <p>Diario de facturas del cliente</p><p>Factura de proyecto</p> |
    | Factura electrónica PEPPOL            | <p>Factura de ventas</p><p>Factura de proyecto</p> | <p>Diario de facturas del cliente</p><p>Factura de proyecto</p> |

7. Seleccione e introduzca un valor de contexto para cada nombre de tabla que cree, de acuerdo con la siguiente tabla.

    | Nombre de característica                         | Documento empresarial | Contexto |
    |--------------------------------------|-------------------|---------|
    | Facturas electrónicas para Austria (AT)    | <p>Factura de ventas</p><p>Factura de proyecto</p> | <p>Modelo de contexto de factura de cliente: contexto de factura de cliente</p><p>Modelo de contexto de factura de cliente: contexto de factura de proyecto</p> |
    | Factura electrónica para Bélgica (BE)      | <p>Factura de ventas</p><p>Factura de proyecto</p> | <p>Modelo de contexto de factura de cliente: contexto de factura de cliente</p><p>Modelo de contexto de factura de cliente: contexto de factura de proyecto</p> |
    | NF-e brasileño (BR)                  | <p>Documento fiscal</p><p>Carta de corrección</p> | <p>Modelo de contexto de factura de cliente: contexto de documento fiscal</p><p>Modelo de contexto de factura de cliente: contexto de carta de corrección FD</p> |
    | NFS-e brasileño ABRASF Curitiba (BR) | Documentos fiscales de servicios| Modelo de contexto de factura de cliente: contexto de documento fiscal |
    | Factura electrónica para Dinamarca (DK)       | <p>Factura de ventas</p><p>Factura de proyecto</p> | <p>Modelo de contexto de factura de cliente: contexto de factura de cliente</p><p>Modelo de contexto de factura de cliente: contexto de factura de proyecto</p> |
    | Factura electrónica egipcia (EG)     | <p>Factura de ventas</p><p>Factura de proyecto</p> | <p>Modelo de contexto de factura de cliente: contexto de factura de cliente</p><p>Modelo de contexto de factura de cliente: contexto de factura de proyecto</p> |
    | Factura electrónica para Estonia (EE)     | <p>Factura de ventas</p><p>Factura de proyecto</p> | <p>Modelo de contexto de factura de cliente: contexto de factura de cliente</p><p>Modelo de contexto de factura de cliente: contexto de factura de proyecto</p> |
    | Factura electrónica finlandesa (FI)       | <p>Factura de ventas</p><p>Factura de proyecto</p> | <p>Modelo de contexto de factura de cliente: contexto de factura de cliente</p><p>Modelo de contexto de factura de cliente: contexto de factura de proyecto</p> |
    | Factura electrónica para Francia (FR)       | <p>Factura de ventas</p><p>Factura de proyecto</p> | <p>Modelo de contexto de factura de cliente: contexto de factura de cliente</p><p>Modelo de contexto de factura de cliente: contexto de factura de proyecto</p> |
    | Factura electrónica para Alemania (DE)       | <p>Factura de ventas</p><p>Factura de proyecto</p> | <p>Modelo de contexto de factura de cliente: contexto de factura de cliente</p><p>Modelo de contexto de factura de cliente: contexto de factura de proyecto</p> |
    | FatturaPA (IT)                       | <p>Factura de ventas</p><p>Factura de proyecto</p> | <p>Modelo de contexto de factura de cliente: contexto de factura de cliente</p><p>Modelo de contexto de factura de cliente: contexto de factura de proyecto</p> |
    | Interfactura CFDI mexicana (MX)       | <p>Factura de ventas</p><p>Traslado</p><p>Transferencia de inventario</p><p>Complemento de pago</p> | Modelo de contexto de factura de cliente: contexto de factura de cliente |
    | Factura electrónica para Países Bajos (NL)        | <p>Factura de ventas</p><p>Factura de proyecto</p> | <p>Modelo de contexto de factura de cliente: contexto de factura de cliente</p><p>Modelo de contexto de factura de cliente: contexto de factura de proyecto</p> |
    | Factura electrónica para Noruega (NO)    | <p>Factura de ventas</p><p>Factura de proyecto</p> | <p>Modelo de contexto de factura de cliente: contexto de factura de cliente</p><p>Modelo de contexto de factura de cliente: contexto de factura de proyecto</p> |
    | Factura electrónica para España (ES)      | <p>Factura de ventas</p><p>Factura de proyecto</p> | <p>Modelo de contexto de factura de cliente: contexto de factura de cliente</p><p>Modelo de contexto de factura de cliente: contexto de factura de proyecto</p> |
    | Factura electrónica PEPPOL            | <p>Factura de ventas</p><p>Factura de proyecto</p> | <p>Modelo de contexto de factura de cliente: contexto de factura de cliente</p><p>Modelo de contexto de factura de cliente: contexto de factura de proyecto</p> |

8. Para cada nombre de tabla y contexto, seleccione e introduzca un valor de asignación de documento empresarial de acuerdo con la siguiente tabla.

    | Nombre de característica                         | Documento empresarial | Asignación de documentos empresariales |
    |--------------------------------------|-------------------|---------------------------|
    | Facturas electrónicas para Austria (AT)    | <p>Factura de ventas</p><p>Factura de proyecto</p> | <p>Asignación del modelo de factura: factura de cliente</p><p>Asignación del modelo de factura: factura de proyecto</p> |
    | Factura electrónica para Bélgica (BE)      | <p>Factura de ventas</p><p>Factura de proyecto</p> | <p>Asignación del modelo de factura: factura de cliente</p><p>Asignación del modelo de factura: factura de proyecto</p> |
    | NF-e brasileño (BR)                  | <p>Documento fiscal</p><p>Carta de corrección</p> | <p>Asignación de documentos fiscales: asignación de documentos fiscales</p><p>Asignación de documentos fiscales: asignación de cartas de corrección</p> |
    | NFS-e brasileño ABRASF Curitiba (BR) | Documentos fiscales de servicios | Asignación de documentos fiscales: asignación de documentos fiscales |
    | Factura electrónica para Dinamarca (DK)       | <p>Factura de ventas</p><p>Factura de proyecto</p> | <p>Asignación del modelo de factura: factura de cliente</p><p>Asignación del modelo de factura: factura de proyecto</p> |
    | Factura electrónica egipcia (EG)     | <p>Factura de ventas</p><p>Factura de proyecto</p> | <p>Asignación del modelo de factura: factura de cliente</p><p>Asignación del modelo de factura: factura de proyecto</p> |
    | Factura electrónica para Estonia (EE)     | <p>Factura de ventas</p><p>Factura de proyecto</p> | <p>Asignación del modelo de factura: factura de cliente</p><p>Asignación del modelo de factura: factura de proyecto</p> |
    | Factura electrónica finlandesa (FI)       | <p>Factura de ventas</p><p>Factura de proyecto</p> | <p>Asignación del modelo de factura: factura de cliente</p><p>Asignación del modelo de factura: factura de proyecto</p> |
    | Factura electrónica para Francia (FR)       | <p>Factura de ventas</p><p>Factura de proyecto</p> | <p>Asignación del modelo de factura: factura de cliente</p><p>Asignación del modelo de factura: factura de proyecto</p> |
    | Factura electrónica para Alemania (DE)       | <p>Factura de ventas</p><p>Factura de proyecto</p> | <p>Asignación del modelo de factura: factura de cliente</p><p>Asignación del modelo de factura: factura de proyecto</p> |
    | FatturaPA (IT)                       | <p>Factura de ventas</p><p>Factura de proyecto</p> | <p>Asignación del modelo de factura: factura de cliente</p><p>Asignación del modelo de factura: factura de proyecto</p> |
    | Interfactura CFDI mexicana (MX)       | <p>Factura de ventas</p><p>Traslado</p><p>Transferencia de inventario</p><p>Complemento de pago</p> | Asignación del modelo de factura: factura de cliente |
    | Factura electrónica para Países Bajos (NL)        | <p>Factura de ventas</p><p>Factura de proyecto</p> | <p>Asignación del modelo de factura: factura de cliente</p><p>Asignación del modelo de factura: factura de proyecto</p> |
    | Factura electrónica para Noruega (NO)    | <p>Factura de ventas</p><p>Factura de proyecto</p> | <p>Asignación del modelo de factura: factura de cliente</p><p>Asignación del modelo de factura: factura de proyecto</p> |
    | Factura electrónica para España (ES)      | <p>Factura de ventas</p><p>Factura de proyecto</p> | <p>Asignación del modelo de factura: factura de cliente</p><p>Asignación del modelo de factura: factura de proyecto</p> |
    | Factura electrónica PEPPOL            | <p>Factura de ventas</p><p>Factura de proyecto</p> | <p>Asignación del modelo de factura: factura de cliente</p><p>Asignación del modelo de factura: factura de proyecto</p> |


## <a name="country-specific-configuration-of-application-setup"></a>Configuración específica del país de la instalación de la aplicación

Según el país o la región, la instalación de la aplicación puede requerir una configuración específica. 

Para conocer los pasos específicos, consulte la documentación "Comenzar" que está disponible para su país o región.

## <a name="deploy-the-electronic-invoicing-feature-to-service-environment"></a>Implementar la característica de facturación electrónica en el entorno del servicio

1. En la pestaña **Versiones**, seleccione la versión de la característica de facturación electrónica que desea implementar.
2. Seleccione **Cambiar estado** \> **Completada**.
3. Seleccione **Cambiar estado** \> **Publicar**.
4. Seleccione **Implementar**.
5. Seleccione la opción **Implementar en la aplicación conectada** en **No**.
6. Seleccione la opción **Implementar en entorno de servicio** en **Sí**.
7. En el campo **Entorno de servicio**, seleccione el entorno de servicio de facturación electrónica en el que desea implementar la característica de facturación electrónica.
8. En el campo **Fecha desde**, seleccione la fecha en la que la característica de facturación electrónica debe entrar en vigencia en la facturación electrónica.
9. Seleccione **Aceptar**.

## <a name="deploy-the-electronic-invoicing-feature-to-connected-application"></a>Implementar la característica de facturación electrónica en aplicaciones conectadas

1. En la pestaña **Versiones**, seleccione una versión de la característica de facturación electrónica que desea implementar.
4. Seleccione **Implementar**.
5. Seleccione la opción **Implementar en la aplicación conectada** en **Sí**.
6. En el campo **Conectar aplicación**, seleccione la conexión que está asociada con su instancia de Finance o Supply Chain Management.
7. Establezca la opción **Implementar en entorno de servicio** en **No**.
10. Seleccione **Aceptar**.

## <a name="turn-on-the-electronic-invoicing-feature-in-finance-or-supply-chain-management"></a>Active la característica de facturación electrónica en Finance o Supply Chain Management

1. Inicie sesión en Finance o Supply Chain Management y verifique que se encuentra en la entidad jurídica correcta.
2. Vaya a **Administración de la organización** \> **Configuración** \> **Parámetros de documentos electrónicos**.
3. En la pestaña **Características**, seleccione la función específica del país o región para activar la característica de facturación electrónica para Finance o Supply Chain Management. La siguiente tabla proporciona una lista de las funciones de facturación electrónica disponibles para países o regiones específicos. 

    | Nombre de característica                                          | País/región  |
    |-------------------------------------------------------|-----------------|
    | Facturas electrónicas para Austria (AT)                     | Austria         |
    | Factura electrónica para Bélgica (BE)                       | Bélgica         |
    | Factura electrónica de México CFDI (MX)                  | México          |
    | Factura electrónica para Dinamarca (DK)                        | Dinamarca         |
    | Factura electrónica para Países Bajos (NL)                         | Países Bajos |
    | Factura electrónica egipcia (EG)                      | Egipto           |
    | Factura electrónica para Estonia (EE)                      | Estonia         |
    | Factura electrónica para Finlandia (FI)                       | Finlandia         |
    | Factura electrónica para Francia (FR)                        | Francia          |
    | Factura electrónica para Alemania (DE)                        | Alemania         |
    | Factura electrónica para Italia (IT)                       | Italia           |
    | NF-e federal: factura electrónica para Brasil (BR)      | Brasil          |
    | NFS-e: factura electrónica de servicios para Brasil (ciudad)   | Brasil          |
    | Factura electrónica para Noruega (NO)                     | Noruega          |
    | Factura electrónica PEPPOL                             | Global          |
    | Factura electrónica para España (ES)                       | España           |

4. Seleccione **Guardar**.

## <a name="issue-electronic-invoices"></a>Emitir facturas electrónicas

1. Vaya a **Administración de la organización** \> **Periódico** \> **Documentos electrónicos** \> **Enviar documentos electrónicos**.
2. En la ficha desplegable **Registro a incluir**, seleccione **Filtro**.
3. Seleccione **Añadir** para agregar un nombre de tabla al filtro de consulta.
4. Seleccione la tabla que contiene las facturas.

    > [!NOTE]
    > El nombre de la tabla debe aparecer en la tabla, en la sección [Configurar la instalación de la aplicación](#configure-the-application-setup) anterior de este tema.

5. Seleccione el nombre del campo a partir de la tabla que desee consultar.
6. Introduzca el nombre de la tabla y el nombre del campo para los criterios de consulta.
7. Repita los pasos 5 y 6 para agregar más campos y criterios a la consulta y luego seleccione **Aceptar**.
8. Seleccione **Aceptar**.

## <a name="view-submission-logs"></a>Ver registros de envío

1. Vaya a **Administración de la organización** \> **Periódico** \> **Documentos electrónicos** \> **Registro de envío de documentos electrónicos**.
2. En el campo **Tipo de Documento**, seleccione la tabla que contiene las facturas.

    > [!NOTE]
    > El nombre de la tabla debe aparecer en la tabla, en la sección [Configurar la instalación de la aplicación](#configure-the-application-setup) anterior de este tema.

3. Seleccione una factura en la cuadrícula y luego seleccione **Consultar** \> **Detalles de envío**.


## <a name="related-topics"></a>Temas relacionados

- [Información general sobre facturación electrónica](e-invoicing-service-overview.md)
- [Comenzar con la administración de servicios de facturación electrónica](e-invoicing-get-started-service-administration.md)
- [Comenzar con la facturación electrónica para Brasil](e-invoicing-bra-get-started.md)
- [Comenzar con la facturación electrónica para México](e-invoicing-mex-get-started.md)
- [Comenzar con la facturación electrónica para Italia](e-invoicing-ita-get-started.md)
- [Facturas electrónicas de clientes en Egipto](emea-egy-e-invoices.md)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
