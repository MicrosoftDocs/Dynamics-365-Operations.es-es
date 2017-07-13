---
title: "Visión general de la firma electrónica"
description: "En este artículo se proporciona una visión general de las firmas electrónicas y se describe cómo pueden usarse en Microsoft Dynamics 365 for Finance and Operations."
author: maertenm
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: SIGParameters, SIGProcSetup, SIGReasonCode
audience: Application User
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 13611
ms.assetid: 98dc6b79-1895-45d8-9dd1-2c8a351b58af
ms.search.region: Global
ms.author: maertenm
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: 298ac47e2253f8add1aa3938dda15afe186afbeb
ms.openlocfilehash: 0cebd30a560ff033efab89c2055827b62cf31576
ms.contentlocale: es-es
ms.lasthandoff: 06/20/2017


---

# Visión general de la firma electrónica
<a id="electronic-signature-overview" class="xliff"></a>

[!include[banner](../includes/banner.md)]


En este artículo se proporciona una visión general de las firmas electrónicas y se describe cómo pueden usarse en Microsoft Dynamics 365 for Finance and Operations.

¿Qué es una firma electrónica?
<a id="what-is-an-electronic-signature" class="xliff"></a>
--------------------------------

Una firma electrónica confirma la identidad de una persona que va a comenzar o aprobar un proceso informático. En algunos sectores, una firma electrónica es tan vinculante legalmente como una firma escrita. Las firmas electrónicas son un requisito de cumplimiento de directivas para determinados sectores regulados, como el farmacéutico, alimentación, aeroespacial y defensa. También son necesarias para el cumplimiento de las directivas de 21 CFR Parte 11 que se publicaron por la Food and Drug Administration (FDA) en los Estados Unidos. **Nota:** Una firma electrónica por sí misma no es lo mismo que una firma digital. Una firma electrónica es simplemente un sustituto de la firma manuscrita, mientras que una firma digital proporciona medidas de seguridad adicionales. Una firma digital puede ayudar a identificar si otro usuario o proceso han manipulado los datos. Una firma digital también puede verificarse y esta verificación no la puede rechazar el propietario del certificado que se usó para firmar los datos. Como se describe a continuación, las firmas electrónicas en Microsoft Dynamics 365 for Finance and Operations han integrado la funcionalidad de la firma digital.

## Firmas electrónicas en Dynamics 365 for Finance and Operations
<a id="electronic-signatures-in-dynamics-365-for-finance-and-operations" class="xliff"></a>
En Finance and Operations, puede usar firmas electrónicas para procesos empresariales críticos. Algunos procesos llevan integrada la capacidad de firma electrónica. También puede crear requisitos de firma personalizados para cualquier tabla o campo de la base de datos. Las firmas electrónicas han integrado la funcionalidad de la firma digital. Cada usuario que firma documentos debe obtener un certificado criptográfico válido. Cuando se firma un documento, se valida la clave privada que está asociada al certificado. Finance and Operations almacena la información de firma electrónica en un registro para proporcionar una traza de auditoría. Para configurar las firmas electrónicas, consulte [Configuración de firmas electrónicas (Guía de tareas)](http://ax.help.dynamics.com/en/wiki/set-up-electronic-signatures/).

## Usuarios que requieren el acceso a las firmas electrónicas
<a id="users-who-require-access-to-electronic-signatures" class="xliff"></a>
Existen tres tipos de usuarios que necesitan normalmente acceso de seguridad a las firmas electrónicas: administradores de firma electrónica, firmantes y auditores de firma electrónica.

### Administrador de firma electrónica
<a id="electronic-signature-administrator" class="xliff"></a>

El administrador de firma electrónica configura los requisitos de firma, configura los parámetros generales y los aprobadores, y recibe alertas cuando las firmas no se pueden verificar. De forma predeterminada, un usuario que pertenezca al rol de seguridad **Director de tecnología de la información** tiene permiso para administrar las firmas electrónicas.

### Firmante
<a id="signer" class="xliff"></a>

Un firmante proporciona firmas electrónicas para documentos y procesos que requieren firmas. De forma predeterminada, un usuario que pertenezca al rol de seguridad **Usuario de sistema** tiene permiso para firmar documentos electrónicamente. **Nota**: El firmante puede requerir permisos adicionales para que se conceda acceso a los datos que están relacionados con el documento o el proceso que se está firmando. Un usuario que cambie datos y necesite firmar para validar los cambios, debe tener permiso para modificar los datos. Un usuario que firma en nombre de otro usuario quizás no requiera acceso a los datos. Un ejemplo de este tipo de usuario es un supervisor que firma para validar los cambios de un empleado.

### Auditor de firma electrónica
<a id="electronic-signature-auditor" class="xliff"></a>

El auditor de firma electrónica revisa el registro de la base de datos y el registro de revisión de firma que está disponible en el registro de la base de datos. De forma predeterminada, un usuario que pertenezca al rol de seguridad **Director de tecnología de la información** tiene permiso para auditar las firmas electrónicas. Si usa un rol distinto de **Director de tecnología de la información**, asegúrese de que el rol tenga asignados los siguientes privilegios:

-   Ver errores de firmas electrónicas
-   Ver registro de base de datos

## Firmar documentos electrónicamente
<a id="signing-documents-electronically" class="xliff"></a>
### Obtener un certificado
<a id="get-a-certificate" class="xliff"></a>

Antes de firmar documentos electrónicamente en Finance and Operations, debe solicitar un certificado. **Nota:** Finance and Operations usa las características de Microsoft SQL Server para crear certificados y permitir firmar electrónicamente. No se requiere ningún certificado o infraestructura de clave pública (PKI) adicional. Cuando solicita un certificado, se crea una clave pública y una clave privada para usted en la base de datos de Finance and Operations. La clave privada se encripta mediante una contraseña que sólo usted conoce. Cuando firma un documento electrónicamente, su identidad se verifica al introducir la contraseña. Para solicitar un certificado, en la página **Opciones**, en la pestaña **Cuentas** , haga clic en **Obtener certificado**. Debe escribir y confirmar la contraseña que usará para firmar. La contraseña se usa para proteger su clave privada y autorizar el uso de su certificado. Esta contraseña no se almacena en la base de datos y no está disponible para nadie, ni siquiera para el administrador de Finance and Operations. Si olvida la contraseña conectada a su certificado, éste debe ser restablecido. Si restablecer el certificado, no se verán afectados los documentos que haya firmado con el certificado anterior. Para restablecer el certificado, en la página **Opciones**, haga clic en **Restablecer certificado**.

### Firmar un documento electrónicamente
<a id="sign-a-document-electronically" class="xliff"></a>

Cuando realice un cambio que requiera una firma electrónica se mostrará la página **Firmar documento**.

1.  En la página **Firmar documento**, haga clic en la pestaña **Documento** para revisar las modificaciones del documento.
2.  En la ficha **Firma**, seleccione un código de motivo.
3.  Escriba un comentario, si se requiere uno.
4.  Si su Id. de usuario no aparece en el campo **Firmante**, selecciónelo en la lista.
5.  Escriba su ubicación, si esta información es necesaria.
6.  Haga clic en **Aceptar**.

### Firmar por los cambios de otro usuario
<a id="sign-for-another-users-changes" class="xliff"></a>

En ocasiones, puede querer que un usuario firme los cambios realizados por otro usuario. Por ejemplo, puede que se requiera que un supervisor firme las modificaciones que determinados empleados realicen en las listas de materiales (L. MAT). Use este procedimiento para designar un usuario de Finance and Operations como firmante por otro usuario. **Nota:** Cuando un usuario firma por los cambios de otro, la firma debe proporcionarse en la estación de trabajo del usuario que realizó la modificación. El usuario no puede guardar los cambios hasta que se proporcione la firma. Para designar aprobadores, siga estos pasos.

1.  En la página **Opciones**, en la pestaña **Cuentas** , haga clic en **Designar aprobador**.
2.  En el campo **Id. del aprobador**, seleccione el Id. del usuario que debe firmar por los cambios de otro usuario.
3.  En el campo **Firmar para id. de usuario**, seleccione el Id. del usuario cuyos cambios deberán firmarse.





