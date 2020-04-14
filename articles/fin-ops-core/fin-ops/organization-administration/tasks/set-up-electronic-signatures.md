---
title: Configuración de firmas electrónicas
description: Sírvase de este procedimiento para configurar firmas electrónicas.
author: maertenm
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SysConfiguration, SIGParameters, SIGReasonCode, SIGProcSetup
audience: Application User
ms.reviewer: sericks
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: maertenm
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 0b8b248481f04856fe15dadbc245caae5330ef8f
ms.sourcegitcommit: 57e1dafa186fec77ddd8ba9425d238e36e0f0998
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/18/2020
ms.locfileid: "3140545"
---
# <a name="set-up-electronic-signatures"></a>Configuración de firmas electrónicas

[!include [banner](../../includes/banner.md)]

Sírvase de este procedimiento para configurar firmas electrónicas. Una firma electrónica confirma la identidad de una persona que va a comenzar o aprobar un proceso informático. La empresa de datos de demostración utilizada para crear este procedimiento es DAT.


## <a name="enable-the-electronic-signature-configuration-key"></a>Activación de la clave de configuración de firma electrónica
1. Vaya a Administración del sistema > Configuración > Configuración de licencias.
2. En el árbol, expanda Administración.
    * Compruebe que se haya seleccionado la casilla Firma electrónica.  
    * Si la casilla Firma electrónica no está activada, debe activar el modo de mantenimiento. Para habilitar el modo de mantenimiento en este entorno, ejecute el trabajo de mantenimiento desde Lifecycle Services o use la herramienta Deployment.Setup de manera local.  
3. Cierre la página.

## <a name="set-up-electronic-signature-parameters"></a>Configuración de parámetros de firma electrónica
1. Vaya a Administración de la organización > Configuración > Firma electrónica > Parámetros de firma electrónica.
2. Haga clic en Editar.
3. En el campo Aviso, escriba un valor.
    * Escriba el aviso que recibirán los firmantes cuando se requiera una firma. Puede escribir el texto que desee. Normalmente, este texto le explica al usuario lo que quiere decir firmar un documento electrónicamente.  
    * Si desea escribir el texto del aviso en otros idiomas, haga clic en el botón Traducciones.  
4. Haga clic en Guardar.
5. Cierre la página.

## <a name="set-up-reason-codes-for-electronic-signatures"></a>Configuración de códigos de motivo para firmas electrónicas
1. Vaya a Administración de la organización > Configuración > Firma electrónica > Códigos de motivo de firma electrónica.
2. Haga clic en Nuevo.
    * Debe configurar códigos de motivo antes de usar las firmas electrónicas. Se requerirá un código de motivo válido cuando se firme un documento.     Un firmante selecciona un código de motivo para indicar el propósito de una firma electrónica. Por ejemplo, un código de motivo se podría usar para indicar la aprobación legal.  
3. En el campo Código de motivo, escriba un valor.
4. En el campo Descripción, escriba un valor.
    * Especifique códigos de motivo adicionales, si es necesario.  
5. Haga clic en Guardar.
6. Cierre la página.

## <a name="require-electronic-signatures-for-existing-processes"></a>Obligación de usar firmas electrónicas para procesos existentes
1. Vaya a Administración de la organización > Configuración > Firma electrónica > Requisitos de firma electrónica.
2. En la lista, busque y seleccione el registro deseado.
    * Seleccione un proceso que requiera firmas electrónicas.  
3. Active o desactive la casilla de verificación Se requiere firma.
    * Repita estos pasos para cada proceso que requiera firmas electrónicas.  
4. Haga clic en Guardar.

## <a name="create-a-custom-requirement-for-electronic-signatures"></a>Creación de un requisito personalizado para firmas electrónicas
1. Haga clic en Nuevo.
2. Active o desactive la casilla de verificación Se requiere firma.
3. En el campo Nombre, especifique un nombre para el proceso que requiera firmas electrónicas.
4. En el campo Nombre de tabla, haga clic en el botón desplegable para abrir la búsqueda.
5. En la lista, localice y seleccione la tabla donde se almacenan los datos que deben firmarse.
6. En la lista, haga clic en el vínculo de la fila seleccionada.
7. En el campo Nombre de campo, haga clic en el botón desplegable para abrir la búsqueda.
8. En la lista, localice y seleccione el campo de la tabla que desea supervisar.
9. En la lista, haga clic en el vínculo de la fila seleccionada.
    * Indique cuando se requiere una firma.     Seleccione Siempre si se requiere una firma cada vez que se modifican los datos en el campo.     Seleccione Sólo si solo se requiere una firma en determinadas condiciones. Si selecciona Sólo, también debe seleccionar una de las siguientes opciones: Al insertar un registro, Al actualizar un registro o Al eliminar un registro.  
10. Haga clic en Guardar.
11. Cierre la página.

