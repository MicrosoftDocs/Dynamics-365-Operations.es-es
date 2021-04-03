---
title: Introducción al complemento de facturación electrónica para Brasil
description: Este tema proporciona información que le ayudará a comenzar con el complemento de facturación electrónica para Brasil en Finance y Supply Chain Management.
author: gionoder
manager: AnnBe
ms.date: 03/12/2021
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
ms.openlocfilehash: eaf9433ad2d9ccf3d3c5632d0f2d4fe772ff8bde
ms.sourcegitcommit: 543772ee97efe215cf6f2ec6e092cc1568919f20
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/13/2021
ms.locfileid: "5592679"
---
# <a name="get-started-with-the-electronic-invoicing-add-on-for-brazil"></a>Introducción al complemento de facturación electrónica para Brasil 

[!include [banner](../includes/banner.md)]

Este tema explica cómo comenzar con el complemento de facturación electrónica para Brasil. Los procedimientos de este tema le guían a través de los pasos de configuración que dependen del país en Regulatory Configuration Services (RCS) y complementa los pasos descritos en el tema [Comenzar con el complemento de facturación electrónica](e-invoicing-get-started.md).

## <a name="country-specific-configuration-for-brazilian-nf-e-br-electronic-invoicing-feature"></a>Configuración específica del país para la función de facturación electrónica brasileña NF-e (BR)

La configuración de la función de facturación electrónica brasileña NF-e (BR) requiere que se completen pasos específicos. Algunos de los parámetros de las configuraciones se publican con valores predeterminados, por lo que deben revisarse y actualizarse para adaptarse mejor a su operación comercial.

### <a name="prerequisites"></a>Requisitos previos

Antes de completar el procedimiento de esta sección, cree una característica de facturación electrónica de factura electrónica brasileña NF-e (BR) para su organización, como se describe en la sección **Crear una característica de facturación electrónica en el proveedor de su organización**, en [Comenzar con el complemento de facturación electrónica](e-invoicing-get-started.md).

1. En RCS, en la sección **Características**, del espacio de trabajo **Característica de globalización**, seleccione el mosaico **Complemento de facturación electrónica**.
2. En la página **Características del complemento de facturación electrónica**, compruebe que esté seleccionada la característica de facturación electrónica **Brasileña NF-e (BR)** que creó.
3. En la pestaña **Versiones**, verifique que esté seleccionada la versión **Borrador**.
4. En la pestaña **Configuraciones**, en la cuadrícula, seleccione **Enviar** y luego seleccione **Editar.**
5. En la pestaña **Acciones**, del grupo de campo **Acciones**, seleccione la acción **(Versión preliminar) Firmar documento xml**.
6. En el grupo de campos **Parámetros**, seleccione **Nombre del certificado**, y en el campo **Valor**, introduzca el nombre del certificado asociado a su parámetro del almacén de claves.
7. En la pestaña **Acciones**, del grupo de campos **Acciones**, seleccione la acción **(Versión preliminar) Llamar al servicio SEFAZ brasileño**.
8. En el grupo de campos **Parámetros**, seleccione el parámetro **Dirección URL**.
9. En el campo **Valor**, si es necesario, revise y actualice la URL de los servicios web publicados por la documentación de SEFAZ para su estado y luego seleccione **Guardar.**
10. En la pestaña **Reglas de aplicabilidad**, en el grupo de campos **Configurar la regla de aplicabilidad**, reviser y actualice el criterio de campo **Estado** según sea necesario para el mismo estado al que se refiere la URL de los servicios web.
11. Seleccione **Guardar** y cierre la página.
12. Para configurar la instalación de la aplicación, consulte [Comenzar con el complemento de facturación electrónica](e-invoicing-get-started.md).

## <a name="country-specific-configuration-of-application-setup-for-brazilian-nf-e-br-electronic-invoicing-feature"></a>Configuración específica del país para la instalación de la aplicación para la característica de facturación electrónica brasileña NF-e (BR)

La configuración de la aplicación para la característica de facturación electrónica brasileña NF-e (BR) requiere que se completen pasos específicos. Complete esos pasos antes de implementar su función de facturación electrónica en su ambiente de servicio de complemento de facturación electrónica.

### <a name="prerequisites"></a>Requisitos previos

Antes de completar el procedimiento de esta sección, cree e inicie la configuración de la aplicación de la característica de facturación electrónica de factura electrónica brasileña NF-e (BR) para su organización, como se describe en la sección **Configurar la instalación de la aplicación** de este tema [Comenzar con el complemento de facturación electrónica](e-invoicing-get-started.md).

1. En RCS, en la sección **Características**, del espacio de trabajo **Característica de globalización**, seleccione el mosaico **Complemento de facturación electrónica**.
2. En la página **Características del complemento de facturación electrónica**, compruebe que esté seleccionada la característica de facturación electrónica **Brasileña NF-e (BR)**.
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
13. Para implementar la función de facturación electrónica, consulte [Comenzar con el complemento de facturación electrónica](e-invoicing-get-started.md).

## <a name="country-specific-configuration-for-brazilian-nfs-e-abrasf-curitiba-br-electronic-invoicing-feature"></a>Configuración específica del país para la función de facturación electrónica brasileña NFS-e ABRASF Curitiba (BR)

La configuración de la función de facturación electrónica brasileña NFS-e ABRASF Curitiba (BR) requiere que se completen pasos específicos. Algunos de los parámetros de las configuraciones se publican con valores predeterminados, por lo que deben revisarse y actualizarse para adaptarse mejor a su operación comercial.

### <a name="prerequisites"></a>Requisitos previos

Antes de completar el procedimiento en esta sección, cree una función de facturación electrónica brasileña NFS-e ABRASF Curitiba (BR) en su organización. Esto se describe en la sección **Configurar la característica de facturación electrónica** en el tema [Comenzar con el complemento de facturación electrónica](e-invoicing-get-started.md).

1. En RCS, en la sección **Características**, del espacio de trabajo **Característica de globalización**, seleccione el mosaico **Complemento de facturación electrónica**.
2. En la página **Características del complemento de facturación electrónica**, compruebe que esté seleccionada la característica de facturación electrónica **Brasileña NFS-e ABRASF Curitiba (BR)** que creó.
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
18. Para configurar la instalación de la aplicación, consulte [Comenzar con el complemento de facturación electrónica](e-invoicing-get-started.md).

## <a name="country-specific-configuration-of-application-setup-for-brazilian-nfs-e-abrasf-curitiba-br-electronic-invoicing-feature"></a>Configuración específica del país de la instalación de la aplicación para la función de facturación electrónica brasileña NFS-e ABRASF Curitiba (BR)

Configurar la instalación de la aplicación para la función de facturación electrónica NFS-e ABRASF Curitiba (BR) brasileña requiere que se completen pasos específicos antes de implementar su función de facturación electrónica en su ambiente de servicio complementario de facturación electrónica.

### <a name="prerequisites"></a>Requisitos previos

Antes de completar el procedimiento de esta sección, cree e inicie una característica de facturación electrónica de factura electrónica brasileña NFS-e ABRASF Curitiba (BR) para su organización, como se describe en la sección **Configurar la instalación de la aplicación** del tema [Comenzar con el complemento de facturación electrónica](e-invoicing-get-started.md).

1. En RCS, en la sección **Características**, del espacio de trabajo **Característica de globalización**, seleccione el mosaico **Complemento de facturación electrónica**.
2. En la página **Características del complemento de facturación electrónica**, compruebe que esté seleccionada la característica de facturación electrónica **Brasileña NFS-e ABRASF Curitiba (BR)**.
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
16. Seleccione **Guardar** y luego vuelva al tema [Comenzar con el complemento de facturación electrónica](e-invoicing-get-started.md) para implementar la función de facturación electrónica.

## <a name="privacy-notice"></a>Aviso de privacidad
Habilitar las características **NF-e Federal, Factura electrónica brasileña (BR)** y el **NFS-e, Factura electrónica del servicio brasileño (ciudad)** puede requerir el envío de datos limitados, incluido el id. de registro fiscal de la organización. Este dato se transmite a agencias de terceros autorizadas por la autoridad tributaria con el fin de enviar facturas electrónicas a esta autoridad tributaria en el formato predefinido requerido para la integración con el servicio web del gobierno. Como administrador, puede activar o desactivar las características **NF-e Federal, Factura electrónica brasileña (BR)** y el **NFS-e, Factura electrónica del servicio brasileño (ciudad)**. En los pasos siguientes se muestra cómo hacer esto: 

1. Vaya a **Administración de la organización** > **Configuración** > **Parámetros de documentos electrónicos**. 
2. En la pestaña **Características**, seleccione la fila que contiene la característica **NF-e Federal, Factura electrónica brasileña (BR)** o la **NFS-e, Factura electrónica del servicio brasileño (ciudad)** y seleccione la característica. Los datos importados de estos sistemas externos a este servicio en línea de Dynamics 365 están sujetos a nuestra [declaración de privacidad](https://go.microsoft.com/fwlink/?LinkId=512132). Consulte las secciones de Aviso de privacidad en la documentación de funciones específicas de cada país o región para obtener más información.

## <a name="additional-resources"></a>Recursos adicionales

- [Visión general del complemento de facturación electrónica](e-invoicing-service-overview.md)
- [Comenzar con la administración de servicios de complemento de facturación electrónica](e-invoicing-get-started-service-administration.md)
- [Comenzar con el complemento de facturación electrónica](e-invoicing-get-started.md)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
