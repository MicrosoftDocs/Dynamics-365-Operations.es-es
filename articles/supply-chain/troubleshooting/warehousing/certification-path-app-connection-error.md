---
title: Error de ruta de certificación al configurar la conexión de la aplicación
description: Si la aplicación Warehouse Management muestra el error "No se encontró el ancla de confianza para la ruta de certificación", use esta página para resolver o solucionar el problema.
author: ivanv-microsoft
ms.date: 06/24/2021
ms.topic: troubleshooting
ms.search.form: WMA
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: ivanv
ms.search.validFrom: 2021-06-24
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: e4a36874ac4982c9c92a7dcc17c13c7c7c02bf8c
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/07/2021
ms.locfileid: "7477527"
---
# <a name="trust-anchor-for-certification-path-not-found-when-setting-up-app-connection"></a>No se encontró el ancla de confianza para la ruta de certificación al configurar la conexión de la aplicación

## <a name="symptoms"></a>Síntomas

Al intentar conectarse a Supply Chain Management, la aplicación Warehouse Management puede mostrarle el siguiente mensaje de error:

> java.security.cert.certPathValidatorException: no se encuentra el ancla de confianza para la ruta de certificación.

Este problema puede afectar a dispositivos con las siguientes propiedades:

- **versión del sistema operativo**: Android 4.4.x (como Zebra TC55). Este no es un problema en los últimas versiones de Android.
- **Ubicación de Supply Chain Management**: nube
- **Modo de conexión**: secreto del cliente o certificado

## <a name="possible-cause"></a>Causa posible

Es posible que Microsoft haya actualizado los certificados SSL del servidor utilizados por Supply Chain Management. Como resultado, el certificado raíz y/o uno de los certificados intermedios pueden haber cambiado, por lo que el nuevo certificado no está en la lista de certificados del sistema de confianza para el dispositivo móvil. Versiones más recientes de Android actualiza automáticamente las listas de certificados de confianza, pero Android 4.4.x no lo hace.

## <a name="resolution"></a>Resolución

Para solucionar el roblema, realice una de las siguiente acciones:

- Utilice la solución alternativa que se describe en la siguiente sección para actualizar cada dispositivo relevante.
- *Podría* ser posible ponerse en contacto con Zebra o Google para obtener una actualización de los certificados de la autoridad de certificación (CA) de confianza del sistema. Sin embargo, no lo hemos confirmado.
- Si es posible, considere reemplazar los dispositivos más antiguos con dispositivos que ejecuten una versión más reciente de Android (donde los certificados de CA de confianza se actualizan automáticamente).

### <a name="workaround"></a>Solución alternativa

#### <a name="step-1-export-the-new-root-certificate-from-supply-chain-management"></a>Paso 1: Exportar el nuevo certificado raíz de Supply Chain Management

Descargue manualmente el nuevo certificado raíz usando su navegador de Internet haciendo lo siguiente:

1. Inicie sesión en Dynamics Supply Chain Management y abra la página principal.

1. En la barra de direcciones de su navegador, seleccione el icono de candado para abrir el cuadro de diálogo **La ubicación es segura**.
1. En el cuadro de diálogo, seleccione **Certificado (válido)** para abrir la ventana **Certificado** para ese certificado.
1. Abra la pestaña **Ruta de certificación** de la ventana **Certificado**.
1. Seleccione el certificado superior que se muestra en la jerarquía. (este es el certificado raíz).
1. Abra la pestaña **Detalles** de la ventana **Certificado**.
1. Seleccione el botón **Copiar a archivo** en la parte inferior de la pestaña **Detalles**.
1. Se abre el **Asistente de exportación de certificados**. Seleccione **Siguiente** para continuar.
1. La página **Formato de archivo de exportación** se abre. Seleccione **DER binario codificado X.509 (.CER)**. Luego seleccione **Siguiente** para continuar.
1. La página **Archivos para exportar** se abre, especifique un nombre de archivo y una ubicación. Luego seleccione **Siguiente** para continuar.
1. Se abre la página **Completar el asistente de exportación de certificados**, que muestra el resultado de la exportación. Seleccione **Fin**.

#### <a name="step-2-install-the-downloaded-certificate-onto-the-affected-devices"></a>Paso 2: instale el certificado descargado en los dispositivos afectados

Instale el certificado descargado haciendo lo siguiente:

1. Transfiera el certificado que descargó en el paso anterior al dispositivo que desea actualizar. Por ejemplo, puede utilizar una tarjeta SD o una conexión de red para que el archivo esté disponible en su dispositivo.
1. Abra la configuración de seguridad de su dispositivo y elija la opción de menú para instalar un certificado desde un archivo. (Los pasos exactos para esto varían según el dispositivo y la versión del sistema operativo).
1. El nuevo certificado debería aparecer ahora en la pestaña **Usuario** para certificados de confianza.
1. Repita este procedimiento para cada dispositivo afectado.
