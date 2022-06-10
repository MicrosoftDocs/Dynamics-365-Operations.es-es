---
title: Configure la importación avanzada de conciliaciones bancarias mediante el uso de informes electrónicos
description: Este tema explica cómo utilizar Informes electrónicos para configurar el proceso avanzado de importación de conciliaciones bancarias.
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
ms.openlocfilehash: 30530a9870ba2ff0546237d2698d1675afa78104
ms.sourcegitcommit: 2b4ee1fe05792332904396b5f495d74f2a217250
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/18/2022
ms.locfileid: "8770205"
---
# <a name="set-up-advanced-bank-reconciliation-import-by-using-electronic-reporting"></a>Configure la importación avanzada de conciliaciones bancarias mediante el uso de informes electrónicos

[!include [banner](../includes/banner.md)]

La característica Conciliación bancaria avanzada le permite importar extractos bancarios electrónicos y conciliarlos automáticamente con transacciones bancarias en Microsoft Dynamics 365 Finance. En este tema se explica cómo configurar la funcionalidad de importación para los extractos bancarios. La configuración de la importación del extracto bancario varía en función del formato de su extracto bancario electrónico. Microsoft Dynamics 365 Finance admite tres formatos de extractos bancarios: ISO20022, MT940 y BAI2. 

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


## <a name="examples-of-bank-statement-formats-and-technical-layouts"></a>Ejemplos de diseños técnicos y formatos de extracto bancario
A continuación se presentan definiciones de diseño técnico de archivo de importación de conciliación bancaria avanzada y tres archivos de ejemplo de extracto bancario relacionados: [Importar ejemplos de archivo](//download.microsoft.com/download/8/e/c/8ec8d2d0-eb8c-41fb-ad8c-f01a4d670a44/Dynamics365FinanceAdvancedBankStatementLayouts.xlsx)  

| Definición de diseño técnico                             | Archivo de ejemplo de extracto bancario          |
|---------------------------------------------------------|--------------------------------------|
| DynamicsAXMT940Layout | [MT940StatementExample](//download.microsoft.com/download/2/d/c/2dcc4e55-ddc8-4a74-b79c-250fae201c3c/mt940StatementExample.txt)     |
| DynamicsAXISO20022Layout | [ISO20022StatementExample](https://nam06.safelinks.protection.outlook.com/?url=https%3A%2F%2Fdownload.microsoft.com%2Fdownload%2F1%2F5%2F5%2F155d84ed-c250-48f3-b0b1-c5a431e7855b%2FISO20022-MultipleStatements.xml&data=04%7C01%7CRobert.Schlomann%40microsoft.com%7C30d0c233cb6546547d0a08d8f4965edc%7C72f988bf86f141af91ab2d7cd011db47%7C1%7C0%7C637528273956712775%7CUnknown%7CTWFpbGZsb3d8eyJWIjoiMC4wLjAwMDAiLCJQIjoiV2luMzIiLCJBTiI6Ik1haWwiLCJXVCI6Mn0%3D%7C1000&sdata=3VzvLZK%2BO8PjuI7XVdC6rD2j3nUJfteo7zFp%2B1s9BwM%3D&reserved=0)             |
| DynamicsAXBAI2Layout    | [BAI2StatementExample](//download.microsoft.com/download/1/1/6/11693f57-bfc1-4993-a274-5fb978be70fa/BAI2StatementExample.txt)     |

