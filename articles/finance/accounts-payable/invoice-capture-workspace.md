---
title: Espacio de trabajo de la solución Invoice Capture
description: Este artículo proporciona información sobre el área de trabajo de la solución Invoice Capture.
author: sunfzam
ms.date: 09/25/2022
ms.topic: overview
ms.prod: ''
ms.technology: ''
ms.search.form: VendorInvoiceWorkspace, VendInvoiceInfoListPage
audience: Application User
ms.reviewer: twheeloc
ms.custom:
- "13971"
- intro-internal
ms.assetid: 0ec4dbc0-2eeb-423b-8592-4b5d37e559d3
ms.search.region: Global
ms.author: zezhangzhao
ms.search.validFrom: 2022-09-28
ms.dyn365.ops.version: ''
ms.openlocfilehash: 4f3af7abf94542437be6132344d6bb7ffaf33d07
ms.sourcegitcommit: 40c80a617b903c2b26e44b41147e0021c5cb680d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2022
ms.locfileid: "9691190"
---
# <a name="invoice-capture-solution-workspace"></a>Espacio de trabajo de la solución Invoice Capture

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

## <a name="side-by-side-viewer-for-the-invoice-capture-solution"></a>Visor de lado a lado para la solución de Invoice Capture 

La introducción de facturas en el sistema ha sido normalmente un proceso lento y propenso a errores, ya que los empleados deben navegar por varios archivos adjuntos y ventanas para recopilar la información correcta. El visor de documentos en paralelo ayudará a mejorar su experiencia cuando trabaje en facturas, al hacer que el proceso sea más fácil, más eficiente y más preciso.

El visor de documentos en paralelo permite a los usuarios tener el documento original y la factura abiertos uno al lado del otro en la misma ventana. La página de la factura está llena de información que proviene del documento de la factura original. El visor crea la conexión entre los campos de la página de factura y el documento de factura original. El visor también ayuda a los usuarios a encontrar cualquier error que exista en la página de la factura.

### <a name="open-the-side-by-side-viewer"></a>Abrir el visor en paralelo

En Microsoft Dynamics 365 Finance, puede abrir el visor en paralelo desde la lista en la página de resumen o desde la página de lista de facturas. También puede abrirlo tocando dos veces (o haciendo doble clic) en un registro o seleccionando el número de factura.

### <a name="using-the-side-by-side-viewer"></a>Usar el visor en paralelo

#### <a name="manually-review-an-invoice"></a>Revisar manualmente una factura

Un documento de factura que se ha importado puede requerir una revisión manual debido a errores o advertencias. En el visor de lado a lado, el encabezado del documento mostrará un estado de **Importado** y la versión actual será **Versión original**.

Para comenzar a revisar la factura, seleccione **Iniciar revisión**. Todos los campos se vuelven editables. El campo **Estado** se actualiza a **En revisión** y el campo **Versión actual** se actualiza a **Versión modificada**.

#### <a name="view-and-work-with-messages"></a>Ver y trabajar con mensajes

Los usuarios deben iniciar el proceso de revisión desde el panel de mensajes. Los mensajes de error se indican con una X roja, los mensajes de advertencia con un triángulo y los mensajes informativos con un círculo. Los mensajes relacionados con la puntuación de confianza se pueden clasificar como advertencias o errores, según el umbral establecido por el grupo de configuración. Para más información, vea [Grupos de configuración de la solución de Invoice Capture ](invoice-capture-config-group.md).

Los mensajes de advertencia y error se pueden ignorar desde el panel de mensajes, el encabezado de la factura o las líneas de la factura. Después de ignorar un mensaje, ya no aparece como un error o una advertencia, y la factura no fallará en la validación.

- Para ignorar los mensajes del panel de mensajes, seleccione **Pasar por alto**. Para restablecer un mensaje que se ha ignorado, seleccione **Pasar por alto** otra vez. Su tipo luego cambia de error o advertencia a información.
- Para ignorar los mensajes del encabezado de la factura o de la línea de la factura, seleccione **Pasar por alto** en el campo. El símbolo del mensaje desaparece. Sin embargo, reaparecerá si el mensaje se restablece desde el panel de mensajes.

Para mensajes relacionados con campos de encabezado de factura, cuando selecciona el mensaje en el panel de mensajes, el cursor se mueve al campo correspondiente en la sección de encabezado.

#### <a name="proofread-and-edit-fields"></a>Revisar y editar campos

Si el valor de un campo se lee de la factura original a través del reconocimiento óptico de caracteres (OCR), aparece un símbolo en el campo. Si selecciona el símbolo, el visor de documentos se acerca y resalta el lugar desde el que se lee el valor del campo, para ayudarlo a verificar los datos de la factura.

Para restablecer el visor de documentos a su ampliación original, siga uno de estos pasos:

- Seleccione el mismo símbolo que seleccionó anteriormente.
- Seleccione el botón en la esquina superior derecha del visor de documentos.

Edite los campos según sea necesario. Las ediciones se guardan automáticamente cuando el cursor sale de un campo. Un símbolo a la derecha de un campo indica que el campo se ha actualizado manualmente. Cuando se actualice la página, se eliminará el símbolo.

#### <a name="check-an-invoice-to-get-up-to-date-messages"></a>Verifique una factura para obtener mensajes actualizados

Cuando edita un campo, el valor del campo se actualiza, pero no se generan nuevos mensajes de validación. Para obtener mensajes de validación actualizados, seleccione **Comprobar**. Se actualizan los mensajes en el panel de mensajes, en el encabezado de la factura y en las líneas de la factura.

#### <a name="complete-the-review"></a>Completar la revisión

Para completar la revisión, seleccione **Completar revisión**. Se validan las facturas. Si se encuentran errores, el estado del documento permanece **En revisión** y aparece una barra de mensajes. Todos los mensajes en el panel de mensajes y en el encabezado y las líneas de la factura se actualizan automáticamente para proporcionar información sobre las causas de la validación fallida.

Después de corregir todos los errores de bloqueo, se puede completar la revisión. El estado del documento se actualiza a **Revisados** y los campos ya no se pueden editar. Puede reiniciar la revisión seleccionando **Iniciar revisión** otra vez.

#### <a name="generate-a-pending-vendor-invoice-in-finance"></a>Generar una factura de proveedor pendiente en Finance

Para enviar el documento de factura al entorno de Finanzas conectado, seleccione **Generar**. Si falla la generación de la factura, aparece un mensaje de error en una barra de mensajes.

#### <a name="void-an-invoice"></a>Vaciar una factura

Para anular una factura, seleccione **Vacío**. Las facturas anuladas no se pueden revisar y no se muestran en la lista **Las facturas necesitan revisión manual**.

### <a name="validation-logic"></a>Lógica de validación

Algunos campos clave en el visor en paralelo no existen en los datos de preparación de facturas, pero son necesarios para generar facturas pendientes en Finanzas. Estos campos se derivan de una combinación de los datos de preparación de la factura actual y los datos maestros de Finanzas.

Los campos que se deben derivar son **Entidad legal**, **Cuenta de vendedor** y **Número de artículo**. Deben derivarse en el siguiente orden. Si la derivación de un campo falla, el proceso se detiene.

1. **Entidad legal** – La persona jurídica se deriva primero. Si se encuentra una regla de asignación activa para la entidad jurídica, la entidad jurídica se deriva en función del nombre y la dirección de la empresa.
2. **Cuenta de vendedor** – A continuación, la cuenta del proveedor se deriva en función de una regla de asignación activa y una combinación de la entidad jurídica derivada y el nombre y la dirección del proveedor.
3. **Número de artículo** – Finalmente, el nombre del artículo se deriva de la puesta en escena, en base a los siguientes tres tipos de información:

    - Una regla de mapeo configurada
    - La entidad jurídica derivada
    - La cuenta de proveedor derivada

Para ejecutar una validación, seleccione **Comprobar** en el visor de lado a lado. Actualmente, la validación realiza las siguientes comprobaciones:

- **Comprobación obligatoria** – Esta verificación valida los campos obligatorios para el visor de lado a lado. Los usuarios pueden seleccionar qué campos deben ser obligatorios en la página **Ajuste de configuración**.
- **Puntuación de confianza** – Los usuarios pueden establecer el umbral de advertencia y el umbral de error para la puntuación de confianza. Esta comprobación se centra en la puntuación de confianza de OCR que está por debajo de esos umbrales. Se mostrarán mensajes de error o advertencia según el resultado de la validación.
- **Entidad legal** – Esta verificación valida que una entidad legal está en Finanzas. Si la entidad jurídica no existe en el entorno de Finanzas, la validación falla.

Cuando el visor de lado a lado se usa por primera vez y el usuario selecciona **Comprobar**, se ejecutan los procesos de derivación y validación. Si las facturas son precisas, el proceso de validación se ejecuta cuando el usuario selecciona **Revisión completa**. También se ejecuta cuando el usuario selecciona **Generar factura de proveedor**.

El proceso de derivación ocurre antes del proceso de validación y todas las advertencias o errores provienen del proceso de validación. Las advertencias y los errores se registrarán en Finance.
