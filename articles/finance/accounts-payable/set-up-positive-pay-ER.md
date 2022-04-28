---
title: Configurar y generar archivos de pago positivos mediante el uso de Informes electrónicos
description: Este tema explica cómo configurar un pago positivo mediante el uso de Informes electrónicos.
author: panolte
ms.date: 03/20/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: BankPositivePayFormat
audience: Application User
ms.reviewer: twheeloc
ms.custom: 88433
ms.assetid: 73f3dcf6-040a-44ad-9512-7b3e0d17a571
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2016-05-31
ms.dyn365.ops.version: AX 7.0.1
ms.openlocfilehash: 43dd1a9cba1fe8df5cff26fe76af7e2957a0d6a4
ms.sourcegitcommit: cf7d4af11bf85638ee831a28ea5ee1a1e041a675
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/04/2022
ms.locfileid: "8544517"
---
# <a name="set-up-positive-pay-files-by-using-electronic-reporting"></a>Configurar archivos de pago positivos mediante el uso de Informes electrónicos

Configure los pagos positivos para generar una lista electrónica de cheques que se proporcionan al banco. A continuación, cuando el cheque se envía al banco, el banco lo compara con la lista de cheques. Si el cheque coincide con un cheque de la lista, el banco lo compensa. Si el cheque no coincide con un cheque en la lista, el banco lo retiene para su revisión.

## <a name="set-up-the-electronic-reporting-configuration"></a>Establecer la configuración de Informes electrónicos

1. Vaya a **Espacios de trabajo \> Informes electrónicos**.
2. En el mosaico para el proveedor de configuración de **Microsoft**, seleccione **Repositorios**.
3. Seleccione **Global** y luego seleccione **Abierto**.
4. Si se debe establecer una conexión con el repositorio, seleccione el vínculo azul en el cuadro de diálogo.
5. En la lista de configuración, busque y seleccione **Modelo de pago positivo \> Formato de pago positivo**.
6. En la ficha desplegable **Versiones**, seleccione la última versión y después seleccione **Importar**.

## <a name="set-up-a-positive-pay-format"></a>Configurar un formato de pago positivo

1. Vaya a **Gestión de efectivo y bancos \> Configuración \> Formatos de pago positivo**.
2. Seleccione **Nuevo**.
3. Seleccione los campos **Formato de pago** y **Descripción**.
4. Seleccione la casilla **Formato de exportación electrónica genérica**.
5. Seleccione el campo **Configuración del formato de exportación** en **Formato de pago positivo**.

## <a name="assign-a-positive-pay-format-to-a-bank-account"></a>Asignar un formato de pago positivo a una cuenta bancaria

1. Vaya a **Gestión de efectivo y de banco \> Cuentas bancarias \> Cuentas bancarias**.
2. Abra la cuenta bancaria.
3. En la ficha desplegable **General**, establezca el campo **Formato de pago positivo** en el formato que se creó anteriormente.
4. Establezca el campo **Fecha de inicio de pago positivo** en la fecha actual.

## <a name="generate-a-positive-pay-file"></a>Generar archivo de pago positivo

1. Vaya a **Gestión de efectivo y de banco \> Cuentas bancarias \> Cuentas bancarias**.
2. Abra una cuenta bancaria para la que esté configurado el pago positivo.
3. Seleccione **Administrar pagos \> Pago positivo \> Archivo de pago positivo**.
4. Seleccione el campo **Fecha límite**. Las comprobaciones que se generaron antes de esta fecha se incluirán.

El archivo XML resultante se descargará.
