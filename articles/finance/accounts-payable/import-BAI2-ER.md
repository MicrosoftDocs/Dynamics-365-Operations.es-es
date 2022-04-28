---
title: Configure la importación avanzada de conciliaciones bancarias mediante el uso de informes electrónicos
description: Este tema explica cómo utilizar los informes electrónicos para configurar el proceso avanzado de importación de conciliaciones bancarias para extractos BAI2.
author: panolte
ms.date: 03/30/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: BankStatementFormat
audience: Application User
ms.reviewer: twheeloc
ms.custom: 88433
ms.assetid: 73f3dcf6-040a-44ad-9512-7b3e0d17a571
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-05-31
ms.dyn365.ops.version: AX 10.0.25
ms.openlocfilehash: 39f1d8ba561ab0e36346f1dfb4f70df318c92a37
ms.sourcegitcommit: cf7d4af11bf85638ee831a28ea5ee1a1e041a675
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/04/2022
ms.locfileid: "8544527"
---
# <a name="set-up-advanced-bank-reconciliation-import-by-using-electronic-reporting"></a>Configure la importación avanzada de conciliaciones bancarias mediante el uso de informes electrónicos

[!include [banner](../includes/banner.md)]

La característica Conciliación bancaria avanzada le permite importar extractos bancarios electrónicos y conciliarlos automáticamente con transacciones bancarias en Microsoft Dynamics 365 Finance. En este tema se explica cómo configurar la funcionalidad de importación para los extractos bancarios BAI2.

## <a name="set-up-the-electronic-reporting-configuration"></a>Establecer la configuración de Informes electrónicos

1. Vaya a **Espacios de trabajo \> Informes electrónicos**.
2. En el mosaico para el proveedor de configuración de **Microsoft**, seleccione **Repositorios**.
3. Seleccione **Global** y luego seleccione **Abierto**.
4. Si se debe establecer una conexión con el repositorio, seleccione el vínculo azul en el cuadro de diálogo.
5. En la lista de configuración, busque **Modelo de extracto bancario \> Modelo de extracto bancario de BAI2**.
6. Seleccione el formato **BAI2**.
7. En la ficha desplegable **Versiones**, seleccione la última versión y después seleccione **Importar**.

## <a name="set-up-the-bank-statement-format"></a>Configurar el formato de extracto bancario

1. Vaya a **Gestión de efectivo y bancos \> Configuración \> Configuración de conciliación bancaria avanzada \> Formato de extracto bancario**.
2. Seleccione **Nuevo**.
3. Seleccione los campos **Formato de extracto** y **Nombre**.
4. Seleccione la casilla **Formato de importación electrónica genérica**.
5. Seleccione el campo **Configuración del formato de importación** en el formato **BAI2**.

## <a name="set-up-the-bank-account"></a>Configurar la cuenta bancaria

1. Vaya a **Gestión de efectivo y de banco \> Cuentas bancarias \> Cuentas bancarias**.
2. Abra la cuenta bancaria.
3. En la ficha desplegable **Conciliación**, establezca la opción **Conciliación bancaria avanzada** en **Sí**.
4. Establezca el campo **Formato de extracto** en el formato creado anteriormente, como **BAI2**.

## <a name="import-the-bank-statement"></a>Importar el extracto bancario

1. Vaya a **Gestión de efectivo y bancos \> Conciliación de extracto bancario \> Extractos bancarios**.
2. En la parte superior de la página **Extractos bancarios**, seleccione **Importar extracto**.
3. Establezca el campo **Cuenta bancaria** en la cuenta bancaria del extracto.
4. Establezca el campo **Formato de extracto** en el formato creado anteriormente, como **BAI2**.
5. Seleccione **Examinar** y seleccione el archivo **BAI**.
6. Seleccione **Cargar**.
7. Para importar el archivo seleccionado, seleccione **Aceptar**.
