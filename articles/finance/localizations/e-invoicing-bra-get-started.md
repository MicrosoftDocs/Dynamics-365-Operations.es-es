---
title: Comenzar con la facturación electrónica para Brasil
description: Este tema proporciona información que le ayudará a comenzar con la facturación electrónica para Brasil en Finance y Supply Chain Management.
author: gionoder
ms.date: 03/29/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.custom: intro-internal
ms.assetid: ''
ms.search.region: Global
ms.author: janeaug
ms.search.validFrom: 2020-07-08
ms.dyn365.ops.version: AX 10.0.12
ms.openlocfilehash: 82bbf806d207af0b15406e4bec516420db7f2c06
ms.sourcegitcommit: 3754d916799595eb611ceabe45a52c6280a98992
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/15/2022
ms.locfileid: "7984862"
---
# <a name="get-started-with-electronic-invoicing-for-brazil"></a>Comenzar con la facturación electrónica para Brasil 

[!include [banner](../includes/banner.md)]

Este tema proporciona información que le ayudará a comenzar con la facturación electrónica para Brasil. El tema le guía a través de los pasos de configuración que dependen del país en Regulatory Configuration Services (RCS) y complementa los pasos descritos en el tema [Comenzar con la facturación electrónica](e-invoicing-get-started.md).

## <a name="country-specific-configuration-for-brazilian-nf-e-br-electronic-invoicing-feature"></a>Configuración específica del país para la función de facturación electrónica brasileña NF-e (BR)

Algunos de los parámetros de la **Característica de facturación electrónica brasileña NF-e (BR)** se publican con valores predeterminados. Revise los valores y, si es necesario, actualícelos para que reflejen mejor sus necesidades de operación comercial antes de implementar la función de facturación electrónica en el entorno del servicio.

Esta sección complementa la sección **Configuración específica del país para la característica de facturación electrónica** en el tema [Comenzar con la de facturación electrónica](e-invoicing-get-started.md).

1. En RCS, en la sección **Características** del espacio de trabajo **Característica de globalización**, seleccione el mosaico **Facturación electrónica**.
2. En la página **Características de facturación electrónica**, compruebe que esté seleccionada la característica de facturación electrónica **Brasileña NF-e (BR)** que creó.
3. En la pestaña **Versiones**, verifique que esté seleccionada la versión **Borrador**.
4. En la pestaña **Configuraciones**, en la cuadrícula, seleccione **Enviar** y luego seleccione **Editar.**
5. En la pestaña **Acciones**, del grupo de campo **Acciones**, seleccione la acción **(Versión preliminar) Firmar documento xml**.
6. En el grupo de campos **Parámetros**, seleccione **Nombre del certificado**, y en el campo **Valor**, introduzca el nombre del certificado asociado a su parámetro del almacén de claves.
7. En la pestaña **Acciones**, del grupo de campos **Acciones**, seleccione la acción **(Versión preliminar) Llamar al servicio SEFAZ brasileño**.
8. En el grupo de campos **Parámetros**, seleccione el parámetro **Dirección URL**.
9. En el campo **Valor**, si es necesario, revise y actualice la URL de los servicios web publicados por la documentación de SEFAZ para su estado y luego seleccione **Guardar.**
10. En la pestaña **Reglas de aplicabilidad**, en el grupo de campos **Configurar regla de aplicabilidad**, revise y actualice el criterio de campo **Estado** según sea necesario para el mismo estado al que se refiere la URL de los servicios web.
11. Seleccione **Guardar** y cierre la página.
12. Para implementar la función de facturación electrónica en el ambiente del servicio, consulte [Comenzar con la facturación electrónica](e-invoicing-get-started.md).

## <a name="country-specific-configuration-of-application-setup-for-brazilian-nf-e-br-electronic-invoicing-feature"></a>Configuración específica del país para la instalación de la aplicación para la característica de facturación electrónica brasileña NF-e (BR)

Complete estos pasos antes de implementar la configuración de la aplicación en su aplicación conectada Finance o Supply Chain Management.

Esta sección complementa la sección **Configuración específica del país para la instalación de la aplicación** en el tema [Comenzar con la facturación electrónica](e-invoicing-get-started.md).

1. En RCS, en la sección **Características** del espacio de trabajo **Característica de globalización**, seleccione el mosaico **Facturación electrónica**.
2. En la página **Características de facturación electrónica**, compruebe que esté seleccionada la característica de facturación electrónica **Brasileña NF-e (BR)**.
3. En la pestaña **Versiones**, verifique que esté seleccionada la versión **Borrador**.
4. En la pestaña **Configuraciones**, seleccione **Configuración de la aplicación** y, en el campo **Aplicación conectada**, seleccione la aplicación donde desea implementar.
5. En el campo **Nombre de tabla**, compruebe que esté seleccionado **Encabezado del documento fiscal**.
6. Seleccione **Tipos de respuesta** y luego seleccione **Nuevo**.
7. En el campo **Tipo de respuesta**, introduzca "Respuesta" como valor fijo y, en el campo **Descripción**, introduzca "Descripción".
8. En el campo **Estado de envío**, seleccione **Pendiente**.
9. En el campo **Asignación de modelos**, seleccione **Asignación de modelos desde mensaje de respuesta**, con **(Versión preliminar) Formato de importación de mensaje de respuesta** y luego seleccione **Guardar**.
10. Seleccione **Nuevo** y, en el campo **Tipo de respuesta**, introduzca "ResponseData" como valor fijo y, en el campo **Descripción**, introduzca "Descripción".
11. En el campo **Estado de envío**, seleccione **Pendiente**.
12. En el campo **Asignación de modelos**, seleccione **Importación de datos de respuesta**, con **(Versión preliminar) Formato de importación de datos de respuesta NF-e** y luego seleccione **Guardar**.
13. Para implementar la configuración de la aplicación en la aplicación conectada Finance o Supply Chain, consulte [Comenzar con la facturación electrónica](e-invoicing-get-started.md).

## <a name="country-specific-configuration-for-brazilian-nfs-e-abrasf-curitiba-br-electronic-invoicing-feature"></a>Configuración específica del país para la función de facturación electrónica brasileña NFS-e ABRASF Curitiba (BR)

Algunos de los parámetros de la **Característica de facturación electrónica brasileña NFS-e ABRASF Curitiba (BR)** se publican con valores predeterminados. Revise y, si es necesario, actualice los valores para que se adapten mejor a sus necesidades de operación comercial antes de implementar la función de facturación electrónica en el entorno del servicio.

Esta sección complementa la sección **Configuración específica del país para la característica de facturación electrónica** en el tema [Comenzar con la de facturación electrónica](e-invoicing-get-started.md).

1. En RCS, en la sección **Características** del espacio de trabajo **Característica de globalización**, seleccione el mosaico **Facturación electrónica**.
2. En la página **Características de facturación electrónica**, compruebe que esté seleccionada la característica de facturación electrónica **Brasileña NFS-e ABRASF Curitiba (BR)** que creó.
3. En la pestaña **Versiones** compruebe que esté seleccionada la versión **Borrador** y, en la pestaña **Configuraciones** de la cuadrícula, seleccione **Enviar**.
4. Seleccione **Editar** y, en la pestaña **Acciones** del grupo de campos **Acciones**, seleccione la primera aparición de **(Versión preliminar) Firmar documento xml**.
5. En el grupo de campos **Parámetros**, seleccione **Nombre de certificado**.
6. En el campo **Valor**, introduzca el nombre del certificado asociado a su parámetro del almacén de claves.
7. En el grupo de campos **Acciones**, seleccione la segunda aparición de **(Versión preliminar) Documento Signxml**.
8. En el grupo de campos **Parámetros**, seleccione **Nombre de certificado**.
9. En el campo **Valor**, introduzca el nombre del certificado asociado a su parámetro del almacén de claves.
10. En la pestaña **Acciones**, del grupo de campos **Acciones**, seleccione la acción **(Versión preliminar) Llamar al servicio SEFAZ brasileño**.
11. En el grupo de campos **Parámetros**, seleccione el parámetro **Dirección URL**.
12. En el campo **Valor**, si es necesario, revise y actualice la URL de los servicios web publicados por el departamento de impuestos para la ciudad de Curitiba y luego seleccione **Guardar.**
13. En la pestaña **Configuraciones**, en la cuadrícula, seleccione **Consultar** y luego seleccione **Editar.**
14. En la pestaña **Acciones**, del grupo de campos **Acciones**, seleccione la acción **(Versión preliminar) Llamar al servicio SEFAZ brasileño**.
15. En el grupo de campos **Parámetros**, seleccione el parámetro **Dirección URL**.
16. En el campo **Valor**, si es necesario, revise y actualice la URL de los servicios web publicados por el departamento de impuestos para la ciudad de Curitiba.
17. Seleccione **Guardar** y, a continuación, cierre la página.
18. Para implementar la función de facturación electrónica en el ambiente del servicio, consulte [Comenzar con la facturación electrónica](e-invoicing-get-started.md).

## <a name="country-specific-configuration-of-application-setup-for-brazilian-nfs-e-abrasf-curitiba-br-electronic-invoicing-feature"></a>Configuración específica del país de la instalación de la aplicación para la función de facturación electrónica brasileña NFS-e ABRASF Curitiba (BR)

Complete estos pasos antes de implementar la configuración de la aplicación en su aplicación conectada Finance o Supply Chain Management.

Esta sección complementa la sección **Configuración específica del país para la instalación de la aplicación** en el tema [Comenzar con la facturación electrónica](e-invoicing-get-started.md).

1. En RCS, en la sección **Características** del espacio de trabajo **Característica de globalización**, seleccione el mosaico **Facturación electrónica**.
2. En la página **Características de facturación electrónica**, compruebe que esté seleccionada la característica de facturación electrónica **Brasileña NFS-e ABRASF Curitiba (BR)**.
3. En la pestaña **Versiones** compruebe que esté seleccionada la versión **Borrador** y, en la pestaña **Configuraciones** de la cuadrícula, seleccione **Configuración de aplicación**.
4. En el campo **Aplicación conectada**, seleccione la aplicación donde desea implementar.
5. En el campo **Nombre de tabla**, compruebe que esté seleccionado el encabezado del documento fiscal.
6. Seleccione **Tipos de respuesta** y elija **Nuevo**.
7. En el campo **Tipo de respuesta**, introduzca "ABRASFCuritibaSubmitResponse" como valor fijo y, en el campo **Descripción**, introduzca "Descripción".
8. En el campo **Estado de envío**, seleccione **Pendiente**.
9. En el campo **Asignación de modelos**, seleccione **Importar mensaje de respuesta**, con **(Versión preliminar) Importación de mensaje de respuesta NFS-e ABRASF Curitiba** y luego seleccione **Guardar**.
10. Seleccione **Nuevo** y, en el campo **Tipo de respuesta**, introduzca "ABRASFCuritibaSubmitResponseData" y, en el campo **Descripción**, introduzca "Descripción".
11. En el campo **Estado de envío**, seleccione **Pendiente**.
12. En el campo **Asignación de modelos**, seleccione **Importación de datos de respuesta**, con **(Versión preliminar) Formato de importación de datos de respuesta NFS-e ABRASF (BR)** y luego seleccione **Guardar**.
13. Seleccione **Nuevo** y, en el campo **Tipo de respuesta**, introduzca "ABRASFCuritibaInquireResponse" y, en el campo **Descripción**, introduzca "Descripción".
14. En el campo **Estado de envío**, seleccione **Pendiente**.
15. En el campo **Asignación de modelos**, seleccione **Importar mensaje de respuesta**, con **(Versión preliminar) Importación de mensaje de respuesta NFS-e ABRASF Curitiba (BR).**
16. Seleccione **Guardar** y cierre la página.
17. Para implementar la configuración de la aplicación en la aplicación conectada Finance o Supply Chain, consulte [Comenzar con la facturación electrónica](e-invoicing-get-started.md).

## <a name="privacy-notice"></a>Aviso de privacidad
Habilitar las características **NF-e Federal, Factura electrónica brasileña (BR)** y el **NFS-e, Factura electrónica del servicio brasileño (ciudad)** puede requerir el envío de datos limitados, incluido el id. de registro fiscal de la organización. Este dato se transmite a agencias de terceros autorizadas por la autoridad tributaria con el fin de enviar facturas electrónicas a esta autoridad tributaria en el formato predefinido requerido para la integración con el servicio web del gobierno. Como administrador, puede activar o desactivar las características **NF-e Federal, Factura electrónica brasileña (BR)** y el **NFS-e, Factura electrónica del servicio brasileño (ciudad)**. En los pasos siguientes se muestra cómo hacer esto: 

1. Vaya a **Administración de la organización** > **Configuración** > **Parámetros de documentos electrónicos**. 
2. En la pestaña **Características**, seleccione la fila que contiene la característica **NF-e Federal, Factura electrónica brasileña (BR)** o la **NFS-e, Factura electrónica del servicio brasileño (ciudad)** y seleccione la característica. Los datos importados de estos sistemas externos a este servicio en línea de Dynamics 365 están sujetos a nuestra [declaración de privacidad](https://go.microsoft.com/fwlink/?LinkId=512132). Consulte las secciones de Aviso de privacidad en la documentación de características específicas de cada país o región para obtener más información.

## <a name="additional-resources"></a>Recursos adicionales

- [Información general sobre facturación electrónica](e-invoicing-service-overview.md)
- [Comenzar con la administración de servicios de facturación electrónica](e-invoicing-get-started-service-administration.md)
- [Comenzar con la facturación electrónica](e-invoicing-get-started.md)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
