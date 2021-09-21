---
title: Crear una cuenta de almacenamiento en Azure y un almacén de claves
description: Este tema explica cómo crear una cuenta de almacenamiento de Azure y un almacén de claves.
author: gionoder
ms.date: 08/17/2021
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
ms.openlocfilehash: 23fec7a00d800719e1a7d2c90f9d0977d56be038
ms.sourcegitcommit: baf82100f0aa7d5f5f47c7f54bc155d8a07beab5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/31/2021
ms.locfileid: "7463870"
---
# <a name="create-an-azure-storage-account-and-a-key-vault"></a>Crear una cuenta de almacenamiento en Azure y un almacén de claves

[!include [banner](../includes/banner.md)]

## <a name="prerequisites"></a>Requisitos previos

Antes de que pueda completar los pasos de este tema, debe asegurarse de que se han completado las tareas siguientes:

- Crear un recurso de almacén de claves en Azure. Para obtener información, vea [Acerca de Azure Key Vault](/azure/key-vault/general/overview).
- Cree una cuenta de Azure Storage (Blob Storage). Para más información, vea [Mantenimiento de la cuenta de Azure Storage](/azure/storage/blobs/).

## <a name="overview"></a>Información general

En este tema, completará dos pasos principales:

- Configure la cuenta de almacenamiento de Azure para obtener el URI de la cuenta de almacenamiento.
- Configure el almacén de claves para almacenar el URI de la cuenta de almacenamiento.

## <a name="set-up-the-azure-storage-account-to-get-the-storage-account-uri"></a>Configure la cuenta de almacenamiento de Azure para obtener el URI de la cuenta de almacenamiento

1. Abra la cuenta de almacenamiento que planea usar con la facturación electrónica.
2. Vaya a **Almacenamiento de datos** > **Contenedores** y cree un nuevo contenedor.
3. Introduzca un nombre para el contenedor y establezca el campo **Nivel de acceso público** en **Privado (sin acceso anónimo)**.
4. Abra el contenedor y vaya a **Configuraciones** > **Directiva de acceso**.
5. Seleccione **Agregar política** para agregar una política de acceso almacenada.
6. Seleccione los campos **Identificador** y **Permisos** según corresponda. En el campo **Permisos**, debe seleccionar todos los permisos.

    ![Otorgar permiso de almacenamiento de blobs.](media/e-Invoicing-services-create-azure-resources-grant-blob-permissions.png)

7. Ingrese las fechas de inicio y vencimiento. La fecha de caducidad debería ser futura.
8. Seleccione **Aceptar** para guardar la política y luego guardar los cambios en el contenedor.
9. Vaya a **Ajustes** > **Tokens de acceso compartido** y establezca los valores del campo. 
10. Ingrese las fechas de inicio y finalización. La fecha de finalización debería ser futura.
11. En el campo **Permisos**, seleccione los siguientes permisos: **Leer**, **Agregar**, **Crear**, **Escribir**, **Borrar** y **Lista**. 
12. Seleccione **Generar token SAS y URL**.
13. Copie y almacene el valor en el campo **URL de Blob SAS**. Este valor se utilizará en el siguiente procedimiento y se denominará *URI de firma de acceso compartido*.

## <a name="set-up-the-key-vault-to-store-the-storage-account-uri"></a>Configure el almacén de claves para almacenar el URI de la cuenta de almacenamiento

1. Abra el almacén de claves que tiene intención de usar con la facturación electrónica.
2. Ir **Configuraciones** \> **Misterios** y luego seleccione **Generar/Importar** para crear un nuevo secreto.
3. En la página **Crea un secreto**, en el campo **Opciones de carga**, seleccione **Manual**.
4. Permite escribir el nombre del secreto. Este nombre se utilizará durante la configuración del servicio en el Servicio de configuración reguladora (RCS) y se denominará el *nombre secreto del almacén de claves*.
5. En el campo **Valor**, ingrese el URI de firma de acceso compartido que copió en el procedimiento anterior y luego seleccione **Crear**.
6. Configure la directiva de acceso para conceder a la facturación electrónica el nivel correcto de acceso seguro al secreto que creó. Ir **Configuraciones \> Política de acceso** y seleccione **Agregar política de acceso**.
7. Establezca los permisos secretos para las operaciones **Obtener** y **Lista**.

    ![Otorgar acceso al servicio.](media/e-Invoicing-services-create-azure-resources-grant-service-access.png)

8. Establezca los permisos de certificado para las operaciones **Obtener** y **Lista**.

    ![Otorgar permiso de certificado.](media/e-Invoicing-services-create-azure-resources-grant-certificate-permission.png)

9. En el campo **Seleccionar entidad de seguridad**, seleccione **Ninguna seleccionada**.
10. En el cuadro de diálogo **Entidad de seguridad**, seleccione la entidad de seguridad agregando **Servicio de facturación electrónica**.
11. Seleccione **Agregar** y, a continuación, seleccione **Guardar**.
12. En la página **Visión de conjunto**, copie el valor **Nombre DNS** para el almacén de claves. Este valor se utilizará durante la configuración del servicio en RCS y se denominará *URI del almacén de claves*.

> [!NOTE]
> Para obtener seguridad adicional en la cuenta de almacenamiento, configure Azure Defender for Storage.
> 
> Para más información, vea [Introducción a Azure Defender for Storage](/azure/security-center/defender-for-storage-introduction).


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
