---
title: Certificados y secretos de clientes
description: Este tema explica cómo configurar los secretos y certificados de clientes en Facturación electrónica.
author: dkalyuzh
ms.date: 02/07/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: dkalyuzh
ms.search.validFrom: ''
ms.dyn365.ops.version: ''
ms.openlocfilehash: 1325cad95e9a6dc470691f5f168439fccaaa78e1
ms.sourcegitcommit: ffdb6794746ffe5461f9dcf34ed8e64976d22d2d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/02/2022
ms.locfileid: "8371815"
---
# <a name="customer-certificates-and-secrets"></a>Certificados y secretos de clientes

[!include [banner](../includes/banner.md)]

Si ya tienes una referencia de Microsoft Azure Key Vault en Regulatory Configuration Service (RCS), puede crear referencias a los certificados y secretos de Key Vault. Si no tiene aún una referencia de Key Vault, consulte [Entornos de servicio](e-invoicing-service-environments.md) para obtener información sobre cómo crearla.

## <a name="create-certificates-and-secrets"></a>Crear certificados y secretos

Para crear y configurar certificados y secretos, siga estos pasos.

1. Inicie sesión en su cuenta de RCS.
2. En el espacio de trabajo **Características de globalización**, en la sección **Ambiente**, seleccione el mosaico **Facturación electrónica**.
3. En la página **Configuración de entornos**, en el Panel de acciones, seleccione **Entornos de servicio**.
4. En la página **Entornos de servicio**, en el Panel de acciones, seleccione **Parámetros de Key Vault**.
5. En la página **Parámetros de Key Vault**, seleccione una referencia de Key Vault y, a continuación, en la sección **Certificados**, seleccione **Agregar**.
6. En el campo **Nombre**, especifique el nombre del secreto o certificado de Key Vault. Para obtener más información, consulte [Crear una cuenta de Azure Storage en Azure Portal](e-invoicing-create-azure-storage-account-azure-portal.md).
7. En el campo **Descripción**, escriba una descripción.
8. En el campo **Tipo**, seleccione **Certificado** si hace referencia al certificado que está almacenado en el almacén de claves. Seleccione **Secreto** si hace referencia al secreto que está almacenado en el almacén de claves.
9. Seleccione **Guardar**.

> [!NOTE]
> En algunos escenarios, debe usar certificados públicos que tengan la extensión de nombre de archivo .cer. Sin embargo, Key Vault no admite la importación y el almacenamiento de certificados de este tipo como certificados de Key Vault. En estos escenarios, debe guardar el archivo .cer como una cadena X.509 (.CER) codificada en base 64. Luego, en un secreto de Key Vault, almacene la cadena que aparece entre la línea **COMENZAR CERTIFICADO** la línea **FINALIZAR CERTIFICADO** del archivo. En el entorno de servicio, aún debe crear una referencia al registro de Key Vault y establecer el campo **Tipo** en **Certificado**.

## <a name="create-a-chain-of-certificates"></a>Crear una cadena de certificados

Si las facturas específicas de su país o región requieren una cadena de certificados para aplicar firmas digitales o establecer una conexión segura (Capa de sockets seguros \[SSL\]) a servicios web externos, cree una cadena de certificados donde los certificados estén en el siguiente orden:

1. Certificados raíz
2. Certificados intermedios
3. Certificados de usuario final

Las autoridades de certificación raíz (CA) son una fuente de certificados de confianza. Los certificados de CA intermedios son puentes que vinculan los certificados de usuario final con los certificados de CA raíz.

Para crear y configurar una cadena de certificados, siga estos pasos.

1. En la página **Parámetros de Key Vault**, en el panel de acciones, seleccione **Cadena de certificados**.
2. Seleccione **Nuevo** para crear una cadena de certificados.
3. En el campo **Nombre**, introduzca el nombre de la cadena de certificados.
4. En el campo **Descripción**, escriba una descripción.
5. En la sección **Certificados**, seleccione **Agregar** para agregar un certificado a la cadena.
6. Utilice el botón **Arriba** o **Abajo** para cambiar la posición del certificado en la cadena. Mantenga el certificado raíz de CA en la parte superior de la lista y el certificado de usuario final en la parte inferior.
7. Seleccione **Guardar**.

Puede crear tantas referencias de Key Vault como quiera. Recuerde que el secreto del token de firma de acceso compartido (SAS) de almacenamiento se usa para vincular un entorno de servicio determinado a la referencia de Key Vault. Puede hacer referencia a los certificados y secretos de Key Vault que se almacenan en un almacén de claves que también contiene el secreto para el token de SAS de almacenamiento que usa cuando configura el entorno de servicio.
