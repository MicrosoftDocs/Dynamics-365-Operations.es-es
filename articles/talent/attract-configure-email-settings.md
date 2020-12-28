---
title: Configurar parámetros de correo electrónico en Attract
description: En este tema se explica cómo configurar parámetros para correos electrónicos enviado por Microsoft Dynamics 365 Talent - Attract.
author: andreabichsel
manager: AnnBe
ms.date: 06/04/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Talent, Core
ms.custom: 7521
ms.assetid: 3b953d5f-6325-4c9e-8b9b-6ab0458a73f8
ms.search.region: Global
ms.search.industry: ''
ms.author: anbichse
ms.search.validFrom: 2019-06-04
ms.dyn365.ops.version: Talent October 2018 update
ms.openlocfilehash: e641e3f0d1873d91be1a1dc9bc22eb734a2b21d5
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/13/2020
ms.locfileid: "4462441"
---
# <a name="configure-email-settings-in-attract"></a>Configurar parámetros de correo electrónico en Attract

[!include [banner](includes/banner.md)]

La marca establece confianza y le ayuda a crear una relación con los candidatos incluso antes de que soliciten sus puestos. Una percepción positiva de la marca atrae a los mejores talentos y aumenta la fidelidad de los empleados existentes. Microsoft Dynamics 365 Talent: Attract le permite configurar correos electrónicos de modo que reflejen la marca de su empresa. Por tanto, puede proporcionar una experiencia coherente a los candidatos al puesto a medida que avanzan en proceso de solicitud.

Attract le permite realizar estas acciones:

- Defina la configuración de correo electrónico para que se use la cuenta del servicio de correo electrónico de Microsoft Exchange de su empresa. De esta manera, los candidatos sabe que los mensajes de correo electrónico proceden de su empresa. Por ejemplo, puede configurar sus parámetros para que los candidatos reciban correos electrónicos de `recruiting@contoso.com` en lugar de `contoso@microsoft.com`.
- Crear una personalización de marca coherente para todas sus comunicaciones realizadas por correo electrónico mediante la configuración de encabezado y un pie de página globales para las plantillas de correo electrónico. 

> [!NOTE]
> Para configurar Attract de modo que utilice la cuenta de servicio de correo electrónico de su empresa para enviar mensajes de correo electrónico, necesita el complemento de contratación completa.

## <a name="connect-an-email-service-account"></a>Conectar una cuenta de servicio de correo electrónico

Al conectar la cuenta de servicio de correo electrónico de su empresa, puede crear una experiencia de correo electrónico personalizada para sus candidatos al puesto. Si no se conecta a la cuenta de su empresa, Attract utiliza la cuenta de servicio de correo electrónico predeterminada de Microsoft.

1. Seleccione **Configuración** (el símbolo de engranaje en la esquina superior derecha) y, a continuación, seleccione **Centro de administración**.
2. En la pestaña **Configuración de correo electrónico**, en **Cuentas de servicio de correo electrónico**, seleccione **Conectar una cuenta de empresa**.

    ![Conectando la cuenta de servicio de correo electrónico de su empresa en Attract](./media/attract-admin-email-service-accounts.png)

    Para obtener más información sobre cómo crear una cuenta de correo electrónico compartida, consulte [Buzones compartidos en Exchange Online](https://docs.microsoft.com/exchange/collaboration-exo/shared-mailboxes).

3. En la ventana de inicio de sesión de Microsoft, inicie sesión con sus credenciales corporativas.
4. Si aún no ha configurado una cuenta de servicio de correo electrónico, o si desea agregar una nueva, seleccione **Agregar nueva cuenta de servicio** e introduzca su información de correo electrónico. Si ya ha configurado la cuenta de servicio de correo electrónico que desea utilizar, selecciónela.

Cuando la cuenta de servicio de correo electrónico está configurada correctamente, verá que aparece en **Cuentas de servicio de correo electrónico**.

## <a name="disconnect-an-email-service-account"></a>Desconectar una cuenta de servicio de correo electrónico

Si desea dejar de usar el dominio de su empresa en las comunicaciones por correo electrónico a través para Attract, puede desconectar una cuenta de servicio de correo electrónico.

1. Seleccione **Configuración** (el símbolo de engranaje en la esquina superior derecha) y, a continuación, seleccione **Centro de administración**.
2. En la pestaña **Configuración de correo electrónico**, en **Cuentas de servicio de correo electrónico**, seleccione el botón **Más** (tres puntos verticales) junto a la cuenta de servicio de correo electrónico que desea desconectar.
3. Seleccione **Desconectar cuenta de correo electrónico**.

    ![Desconectando la cuenta de servicio de correo electrónico de su empresa](./media/attract-admin-disconnect-email-account.png)

4. Cuando se le pida que confirme lla operación, seleccione **Desconectar**.

    ![Confirmando la desconexión de la cuenta de servicio de correo electrónico de su empresa](./media/attract-admin-email-confirm-disconnect.png)

Si no se conecta a una cuenta de servicio de correo electrónico diferente, los mensajes de correo electrónico enviados desde Attract utilizarán la cuenta de servicio de correo electrónico predeterminada de Microsoft.

## <a name="configure-email-template-settings"></a>Configurar ajustes de plantilla de correo electrónico

Puede cargar una imagen del logotipo de su empresa y otra información como un encabezado de marca para sus correos electrónicos. También puede proporcionar vínculos a su directiva de privacidad y términos de uso en los pies de página del correo electrónico.

> [!NOTE]
> Debe cumplir toda la legislación aplicable de su país o región, y también la del país o región que rige el destinatario del correo electrónico. Esta legislación incluye normativas contra correo no deseado.

1. Seleccione **Configuración** (el símbolo de engranaje en la esquina superior derecha) y, a continuación, seleccione **Centro de administración**.
2. En la pestaña **Configuración de correo electrónico**, en **Configuración de plantilla de correo electrónico**, arrastre la imagen que desea utilizar como encabezado de su correo electrónico en el cuadro de imagen, o haga clic en el cuadro de imagen para buscar el archivo. Para sustituir una imagen existente, primero debe seleccionar **Eliminar** al lado de esta. La imagen debe ser un archivo JPEG, JPG, PNG o SVG. El tamaño recomendado para imágenes es entre 25 y 800 píxeles de ancho, y entre 25 y 150 píxeles de alto. El tamaño máximo del archivo para el encabezado es de 1 megabyte (MB).

    ![Agregando una imagen para el encabezado de correo electrónico de su empresa](./media/attract-admin-email-header.png)

3. En **Su directiva de privacidad para las comunicaciones**, proporcione un vínculo a la directiva de privacidad de su empresa. En **Sus términos y condiciones para las comunicaciones**, proporcione un vínculo a las condiciones de uso de su empresa.

    ![Agregando vínculos a la directiva de privacidad y los términos de uso de su empresa para el pie de página del correo electrónico](./media/attract-admin-email-footer.png)

4. Seleccione **Guardar** para guardar la configuración de plantilla de correo electrónico.
