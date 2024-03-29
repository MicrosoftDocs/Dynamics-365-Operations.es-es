---
title: Crear una cuenta de Azure Storage en Azure Portal
description: Este artículo explica cómo crear una cuenta de almacenamiento de Azure para Facturación electrónica.
author: gionoder
ms.date: 02/14/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: gionoder
ms.search.validFrom: ''
ms.dyn365.ops.version: ''
ms.custom: ''
ms.assetid: ''
ms.search.form: ''
ms.openlocfilehash: 5eca23985c48f4e577bd4567cc2e324df5aa9690
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/12/2022
ms.locfileid: "9291648"
---
# <a name="create-an-azure-storage-account-in-the-azure-portal"></a>Crear una cuenta de Azure Storage en Azure Portal

[!include [banner](../includes/banner.md)]

Todos los archivos electrónicos que se generan por el servicio de Facturación electrónica o van al servicio durante el procesamiento se almacenan en sus contenedores de cuentas de almacenamiento de Microsoft Azure. Para asegurarse de que la Facturación electrónica pueda obtener acceso a esos contenedores, debe proporcionar el token de firma de acceso compartido (SAS) de la cuenta de almacenamiento al servicio de Facturación electrónica. Además, para garantizar que el token se almacene de forma segura, no proporcione el token de SAS directamente. En su lugar, guárdelo en un almacén de claves de Azure y proporcione un secreto de Azure Key Vault.

1. Abra la cuenta de almacenamiento que planea usar con el servicio de Facturación electrónica.
2. Vaya a **Configuración** \> **Configuración** y asegúrese de que el parámetro **Permitir el acceso público a blobs** está establecido en **Habilitado**.
3. Vaya a **Almacenamiento de datos** \> **Contenedores** y cree un contenedor.
4. Introduzca un nombre para el contenedor y establezca el campo **Nivel de acceso público** en **Privado (sin acceso anónimo)**.
5. Abra el nuevo contenedor y vaya a **Configuración** \> **Directiva de acceso**.
6. Seleccione **Agregar política** para agregar una política de acceso almacenada.
7. Establezca el campo **Identificador** según corresponda.
8. En el campo **Permisos**, seleccione todos los permisos.

    ![Todos los permisos seleccionados en el campo Permisos en el cuadro de diálogo Agregar directiva.](media/e-invoicing-azure-1.png)

9. Ingrese las fechas de inicio y finalización. La fecha de finalización debería ser futura.
10. Seleccione **Aceptar** para guardar la política y luego guardar los cambios en el contenedor.
11. Vaya a **Configuración** \> **Tokens de acceso compartido** y establezca los valores del campo.
12. Ingrese las fechas de inicio y finalización. La fecha de finalización debería ser futura.
13. En el campo **Permisos**, seleccione los siguientes permisos:

    - Leer
    - Agregar
    - Crear
    - Escribir
    - Quitar
    - Lista

14. Seleccione **Generar token SAS y URL**.
15. Copie y almacene el valor en el campo **URL de Blob SAS**. Este valor se utilizará posteriormente en este procedimiento y se denominará *URI de firma de acceso compartido*.
16. Abra el almacén de claves que tiene intención de usar con la facturación electrónica.
17. Ir **Configuración** \> **Secretos** y seleccione **Generar/Importar** para crear un secreto.
18. En la página **Crea un secreto**, en el campo **Opciones de carga**, seleccione **Manual**.
19. Permite escribir el nombre del secreto. Este nombre se utilizará durante la configuración del servicio en el Regulatory Configuration Service (RCS) y se denominará el *nombre secreto del almacén de claves*. Para más información sobre cómo configurar RCS, consulte [Configurar Regulatory Configuration Service (RCS)](e-invoicing-set-up-rcs.md).
20. En el campo **Valor**, especifique el URI de firma de acceso compartido que copió anteriormente.
21. Seleccione **Crear**.
