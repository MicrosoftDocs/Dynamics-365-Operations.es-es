---
title: Crear una cuenta de almacenamiento en Azure y un almacén de claves
description: Este tema explica cómo crear una cuenta de almacenamiento de Azure y un almacén de claves.
author: gionoder
manager: AnnBe
ms.date: 09/22/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: 97423
ms.assetid: ''
ms.search.region: Global
ms.author: janeaug
ms.search.validFrom: 2020-07-08
ms.dyn365.ops.version: AX 10.0.12
ms.openlocfilehash: b8e39539f767cc2944a9a7fdda09121921c64763
ms.sourcegitcommit: 025561f6a21fe8705493daa290f3f6bfb9f1b962
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/23/2020
ms.locfileid: "3836033"
---
# <a name="create-an-azure-storage-account-and-a-key-vault"></a>Crear una cuenta de almacenamiento en Azure y un almacén de claves

[!include [banner](../includes/banner.md)]
[!include [banner](../includes/preview-banner.md)]


El servicio adicional de facturación electrónica asume la responsabilidad de almacenar todos sus datos comerciales en los recursos de Microsoft Azure que son propiedad de su empresa. Para asegurarse de que el servicio funcione correctamente y de que solo el complemento acceda a todos los datos comerciales necesarios y generados por el complemento de facturación electrónica, debe crear dos recursos principales de Azure:

- Una cuenta de almacenamiento de Azure (Blob Storage) para almacenar facturas electrónicas
- Un almacén de claves de Azure para almacenar certificados y el identificador uniforme de recursos (URI) de la cuenta de almacenamiento

> [!NOTE]
> Se debe asignar un recurso de almacén de claves dedicado y un almacenamiento de blobs del cliente específicamente para su uso con el complemento de facturación electrónica.

## <a name="prerequisites"></a>Requisitos previos

Antes de que pueda completar los pasos de este tema, debe asegurarse de que se han completado las tareas siguientes:

- Crear un recurso de almacén de claves en Azure. Para obtener información, vea [Acerca de Azure Key Vault](https://docs.microsoft.com/azure/key-vault/general/overview).
- Cree una cuenta de Azure Storage (Blob Storage). Para más información, vea [Mantenimiento de la cuenta de Azure Storage](https://docs.microsoft.com/azure/storage/blobs/).

## <a name="overview"></a>Información general

En este tema, completará dos pasos principales:

- Configure la cuenta de almacenamiento de Azure para obtener el URI de la cuenta de almacenamiento.
- Configure el almacén de claves para almacenar el URI de la cuenta de almacenamiento.

## <a name="set-up-the-azure-storage-account-to-get-the-storage-account-uri"></a>Configure la cuenta de almacenamiento de Azure para obtener el URI de la cuenta de almacenamiento

1. Abra la cuenta de almacenamiento que planea usar con el complemento de facturación electrónica.
2. Ir **Servicio blob** \> **Contenedores** y cree un nuevo contenedor.
3. Introduzca un nombre para el contenedor y establezca el campo **Nivel de acceso público** en **Privado (sin acceso anónimo)**.
4. Abra el contenedor y vaya a **Configuraciones \> Directiva de acceso**.
5. Seleccione **Agregar política** para agregar una política de acceso almacenada.
6. Seleccione los campos **Identificador** y **Permisos** según corresponda. En el campo **Permisos**, debe seleccionar todos los permisos.

    ![Otorgar permiso de almacenamiento de blobs](media/e-Invoicing-services-create-azure-resources-grant-blob-permissions.png)

7. Ingrese las fechas de inicio y vencimiento. La fecha de caducidad debería ser futura.
8. Seleccione **Aceptar** para guardar la política y luego guardar los cambios en el contenedor.
9. Regrese a la cuenta de almacenamiento y abra **Explorador de almacenamiento (vista previa)**.
10. Haga clic con el botón derecho en el contenedor y luego seleccione **Obtener firma de acceso compartido**.
11. En el cuadro de diálogo **Firma de acceso compartido**, copie y almacene el valor en el campo **URI**. Este valor se utilizará en el siguiente procedimiento y se denominará *URI de firma de acceso compartido*.

    ![Seleccionar y copiar el valor de URI](media/e-Invoicing-services-create-azure-resources-select-and-copy-uri.png)

## <a name="set-up-the-key-vault-to-store-the-storage-account-uri"></a>Configure el almacén de claves para almacenar el URI de la cuenta de almacenamiento

1. Abra el almacén de claves que tiene intención de usar con el complemento de facturación electrónica.
2. Ir **Configuraciones** \> **Misterios** y luego seleccione **Generar/Importar** para crear un nuevo secreto.
3. En la página **Crea un secreto**, en el campo **Opciones de carga**, seleccione **Manual**.
4. Permite escribir el nombre del secreto. Este nombre se utilizará durante la configuración del servicio en el Servicio de configuración reguladora (RCS) y se denominará el *nombre secreto del almacén de claves*.
5. En el campo **Valor**, seleccione **URI de firma de acceso compartido** y luego seleccione **Crear**.
6. Configure la política de acceso para otorgar al complemento de facturación electrónica el nivel correcto de acceso seguro al secreto que creó. Ir **Configuraciones \> Política de acceso** y seleccione **Agregar política de acceso**.
7. Establezca los permisos secretos para las operaciones **Obtener** y **Lista**.

    ![Otorgar acceso al servicio](media/e-Invoicing-services-create-azure-resources-grant-service-access.png)

8. Establezca los permisos de certificado para las operaciones **Obtener** y **Lista**.

    ![Otorgar permiso de certificado](media/e-Invoicing-services-create-azure-resources-grant-certificate-permission.png)

9. En el cuadro de diálogo **Principal**, seleccione el principal agregando **Complemento de facturación electrónica**.
10. Seleccione **Agregar** y luego seleccione **Guardar cambios de Key Vault**.
11. En la página **Visión de conjunto**, copie el valor **Nombre DNS** para el almacén de claves. Este valor se utilizará durante la configuración del servicio en RCS y se denominará *URI del almacén de claves*.
