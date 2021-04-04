---
title: Introducción al complemento de facturación electrónica
description: Este tema proporciona información que le ayudará a comenzar con el complemento de facturación electrónica en Microsoft Dynamics 365 Finance y Dynamics 365 Supply Chain Management.
author: gionoder
manager: AnnBe
ms.date: 02/22/2021
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
ms.openlocfilehash: 56227e031f8205836bcae9ce26006fc8091c2863
ms.sourcegitcommit: 543772ee97efe215cf6f2ec6e092cc1568919f20
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/13/2021
ms.locfileid: "5592559"
---
# <a name="get-started-with-the-electronic-invoicing-add-on"></a>Introducción al complemento de facturación electrónica

[!include [banner](../includes/banner.md)]

Este tema proporciona información que le ayudará a comenzar con el complemento de facturación electrónica.

La siguiente tabla enumera las características de facturación electrónica y los documentos comerciales a los que se puede aplicar.

| Nombre de característica                         | Documento empresarial |
|--------------------------------------|-------------------|
| Facturas electrónicas para Austria (AT)    | <p>Factura de ventas</p><p>Factura de proyecto</p> |
| Factura electrónica para Bélgica (BE)      | <p>Factura de ventas</p><p>Factura de proyecto</p> |
| NF-e brasileño (BR)                  | <p>Modelo de documento fiscal 55</p><p>Carta de corrección</p> |
| NFS-e brasileño ABRASF Curitiba (BR) | Documentos fiscales de servicios |
| Factura electrónica para Dinamarca (DK)       | <p>Factura de ventas</p><p>Factura de proyecto</p> |
| Factura electrónica egipcia (EG)     | <p>Factura de ventas</p><p>Factura de proyecto</p> |
| Factura electrónica para Estonia (EE)     | <p>Factura de ventas</p><p>Factura de proyecto</p> |
| Factura electrónica finlandesa (FI)       | <p>Factura de ventas</p><p>Factura de proyecto</p> |
| Factura electrónica para Francia (FR)       | <p>Factura de ventas</p><p>Factura de proyecto</p> |
| Factura electrónica para Alemania (DE)       | <p>Factura de ventas</p><p>Factura de proyecto</p> |
| FatturaPA (IT)                       | <p>Factura de ventas</p><p>Factura de proyecto</p> |
| Interfactura CFDI mexicana (MX)       | <p>Factura de ventas</p><p>Traslado</p><p>Transferencia de inventario</p><p>Complemento de pago</p> |
| Factura electrónica para Países Bajos (NL)        | <p>Factura de ventas</p><p>Factura de proyecto</p> |
| Factura electrónica para Noruega (NO)    | <p>Factura de ventas</p><p>Factura de proyecto</p> |
| Factura electrónica para España (ES)      | <p>Factura de ventas</p><p>Factura de proyecto</p> |
| Factura electrónica PEPPOL            | <p>Factura de ventas</p><p>Factura de proyecto</p> |

## <a name="prerequisites"></a>Requisitos previos

Antes de que pueda completar los procedimientos de este tema, debe tener preparados los siguientes requisitos previos:

- Configure su Servicio de configuración regulatoria (RCS) y su entorno de Microsoft Dynamics 365 Finance o Dynamics 365 Supply Chain Management para que pueda enviar al complemento de facturación electrónica.
- Cree un entorno de servicio y publíquelo en el complemento de facturación electrónica. Para más información, consulte [Comenzar con la administración del servicio complementario de facturación electrónica](e-invoicing-get-started-service-administration.md).
- Crear una aplicación conectada. Para más información, consulte [Comenzar con la administración del servicio complementario de facturación electrónica](e-invoicing-get-started-service-administration.md).
- Cree un proveedor de configuración para su organización. Para obtener más información, consulte [Crear proveedores de configuración y marcarlos como activos](../../fin-ops-core/dev-itpro/analytics/tasks/er-configuration-provider-mark-it-active-2016-11.md).

## <a name="import-an-electronic-invoicing-feature-from-the-microsoft-configuration-provider"></a>Importar una característica de facturación electrónica desde cualquier proveedor de configuración 

1. Inicie sesión en su cuenta del Servicio de configuración reguladora (RCS).
2. En el espacio de trabajo **Característica de globalización**, en la sección **Características**, seleccione el mosaico **Complemento de facturación electrónica**.
3. Seleccione **Importar** y, a continuación, **Sincronizar**.
4. Filtre la columna **Proveedor de configuración** por el término **Microsoft**.
5. Seleccione el nombre de una característica de facturación electrónica de la tabla al principio de este tema y luego seleccione **Importar**.

## <a name="create-an-electronic-invoicing-feature-under-your-organization-provider"></a>Crear una característica de facturación electrónica para su proveedor de organización

1. En RCS, en la sección **Características**, del espacio de trabajo **Característica de globalización**, seleccione el mosaico **Complemento de facturación electrónica**.
2. Seleccione **Añadir** > **Basado en una característica existente**, y en el campo **Nombre**, introduzca el nombre de la característica de facturación electrónica.
3. En el campo **Descripción**, introduzca una descripción de la característica.
4. En el **Campo de característica base**, seleccione la característica de facturación electrónica importada del proveedor de configuración de Microsoft.
5. Seleccione **Crear característica**.

## <a name="configure-the-electronic-invoicing-feature"></a>Configurar las características de facturación electrónica

Según el país o la región, la característica de facturación electrónica puede requerir una configuración adicional. 

Para conocer los pasos específicos, consulte la documentación "Comenzar" que está disponible para su país o región.

## <a name="configure-the-application-setup"></a>Configurar la aplicación

1. Seleccione la característica de facturación electrónica que creó.
2. En la pestaña **Versión**, verifique que se selecciona la versión **Borrador**.
3. En la pestaña **Configuraciones**, seleccione **Configuración de la aplicación**.

    > [!NOTE]
    > Verifique que su organización esté configurada como el proveedor de configuración **Activo**. Para obtener más información, consulte [Crear proveedores de configuración y marcarlos como activos.](../../fin-ops-core/dev-itpro/analytics/tasks/er-configuration-provider-mark-it-active-2016-11.md).

4. Seleccione **Configuración de características** y luego seleccione **Aplicación conectada**.
5. En la sección **Tipos de documentos electrónicos**, seleccione **Agregar**.
6. Para cada documento comercial que admita la característica, seleccione e introduzca un valor de **Nombre de tabla** de acuerdo con la siguiente tabla.

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

7. Para cada documento comercial que admita la característica, seleccione e introduzca un valor de **Contexto** de acuerdo con la siguiente tabla.

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

8. Para cada documento comercial que admita la característica, seleccione e introduzca un valor de **Asignación de documento empresarial**, de acuerdo con la siguiente tabla.

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

Según el país o la región, la característica de facturación electrónica puede requerir una configuración adicional.

Para conocer los pasos específicos, consulte la documentación "Comenzar" que está disponible para su país o región.

## <a name="deploy-the-electronic-invoicing-feature"></a>Implementar la característica de facturación electrónica

1. En la pestaña **Versiones**, seleccione la versión de la característica de facturación electrónica que desea implementar.
2. Seleccione **Cambiar estado** \> **Completada**.
3. Seleccione **Cambiar estado** \> **Publicar**.
4. Seleccione **Implementar**.
5. Seleccione la opción **Implementar en la aplicación conectada** en **Sí**.
6. En la página **Conectar aplicación**, seleccione la conexión que está asociada con su instancia de Finance o Supply Chain Management.
7. Seleccione la opción **Implementar en entorno de servicio** en **Sí**.
8. En el campo **Entorno de servicio**, seleccione el entorno de servicio complementario de facturación electrónica en el que desea implementar la característica de facturación electrónica.
9. En el campo **Fecha desde**, seleccione la fecha en la que la característica de facturación electrónica debe entrar en vigencia en el complemento de facturación electrónica.
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

- [Visión general del complemento de facturación electrónica](e-invoicing-service-overview.md)
- [Comenzar con la administración de servicios de complemento de facturación electrónica](e-invoicing-get-started-service-administration.md)
- [Introducción al complemento de facturación electrónica para Brasil](e-invoicing-bra-get-started.md)
- [Introducción al complemento de facturación electrónica para México](e-invoicing-mex-get-started.md)
- [Introducción al complemento de facturación electrónica para Italia](e-invoicing-ita-get-started.md)
- [Facturas electrónicas de clientes en Egipto](emea-egy-e-invoices.md)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
