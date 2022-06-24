---
title: Configurar los recursos de Azure para la facturación electrónica
description: Este artículo proporciona una descripción general del proceso para configurar recursos de Microsoft Azure para la facturación electrónica.
author: dkalyuzh
ms.date: 01/26/2022
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
ms.openlocfilehash: c5b7b2ca4d7733fb1c75ded8798655699284fe1a
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/03/2022
ms.locfileid: "8907740"
---
# <a name="set-up-azure-resources-for-electronic-invoicing"></a>Configurar los recursos de Azure para la facturación electrónica

[!include [banner](../includes/banner.md)]

El proceso para configurar recursos de Microsoft Azure para la Facturación electrónica consta de tres pasos. Los dos primeros pasos, "Crear un almacén de claves de Azure en Azure Portal" y "Crear una cuenta de almacenamiento de Azure en Azure Portal", son obligatorios. El tercer paso, "Configurar una conexión de SharePoint", es opcional.

## <a name="create-an-azure-key-vault-in-the-azure-portal"></a>Crear un Azure Key Vault en Azure Portal

Crear un almacén de claves en su suscripción de Azure. Le recomendamos que cree un almacén de claves independiente para Facturación electrónica y que no combine secretos con otras aplicaciones. Cree tantos secretos y certificados como necesite para sus escenarios en documentos electrónicos. Debe crear al menos un secreto para almacenar el token de firma de acceso compartido (SAS) de la cuenta de almacenamiento de Azure que creará en el paso siguiente.

Para obtener información sobre cómo completar este paso, consulte [Cree un Azure Key Vault en Azure Portal](e-invoicing-create-azure-key-vault-azure-portal.md).

## <a name="create-an-azure-storage-account-in-the-azure-portal"></a>Crear una cuenta de Azure Storage en Azure Portal

Eres propietario de todos los documentos y archivos electrónicos que genera el servicio de Facturación electrónica o ingresas al servicio. Esos documentos y archivos se almacenan en una cuenta de almacenamiento de Azure que crea en su suscripción de Azure. El servicio accederá a su cuenta de almacenamiento mediante el token de SAS que se extrae de su secreto de Key Vault.

Para obtener información sobre cómo completar este paso, consulte [Cree una cuenta de almacenamiento de Azure en Azure Portal](e-invoicing-create-azure-storage-account-azure-portal.md).

## <a name="configure-a-sharepoint-connection"></a>Configurar una conexión de SharePoint

En algunos escenarios, es posible que deba guardar archivos electrónicos para SharePoint y recuperarlos de SharePoint. Para asegurarse de que el servicio de Facturación electrónica pueda acceder a sus carpetas de SharePoint, configure el acceso a SharePoint.

Para obtener información sobre cómo completar este paso, consulte [Configurar una conexión de SharePoint](e-invoicing-create-sharepoint-connection.md).
