---
title: Extensibilidad de enumeración base de género
description: Este artículo proporciona una descripción general de la extensibilidad de la enumeración de base de género (enum).
author: twheeloc
ms.date: 05/23/2022
ms.topic: overview
ms.prod: ''
ms.technology: ''
ms.search.form: HRMParameters, EssWorkspace
audience: Application User
ms.custom:
- "51941"
- intro-internal
ms.assetid: 2cfb061a-a616-4bf9-9d98-9cde00039eec
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2020-03-19
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 61a80c16d24d8fda264340d79ed393db3f635908
ms.sourcegitcommit: 1717ff6af1879c6f3a8360936c42ecf55f86acd0
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/07/2022
ms.locfileid: "9749321"
---
# <a name="gender-base-enum-extensibility"></a>Extensibilidad de enumeración base de género

La enumeración **Género** (enum) ahora es extensible. Este artículo describe los cambios que debe realizar en el código base si planea extender la enumeración **Género**.

## <a name="gender-vs-hcmpersongender"></a>Gender frente a HcmPersonGender

Hay dos enumeraciones para valores de género:

- **Gender** (Plataforma de la aplicación)
- **HcmPersonGender** (PersonnelManagement)

La enumeración **Gender** se usa en todo Microsoft Dynamics 365 Finance, mientras que **HcmPersonGender** es específico de la funcionalidad de gestión del capital humano (HCM). Si está utilizando la funcionalidad HCM y realiza algún cambio en la enumeración **Gender**, debe considerar realizar los mismos cambios en **HcmPersonGender**. Por ejemplo, si agrega **Transgénero** a la enumeración **Gender** también agregará **Transgénero** a la enumeración **HcmPersonGender**.

## <a name="hcmpersongendertranformutil-class"></a>HcmPersonGenderTranformUtil (Clase)

Se ha creado una clase nueva **HcmPersonGenderTranformUtil** para permitir la traducción entre los dos enumeradores base. En esta clase, hay dos métodos: **convertGenderToHcmPersonGender** y **convertHcmPersonGenderToGender**. Debe crear una extensión utilizando la clase **Cadena de mando** o **controladores de eventos** y extienda ambos métodos para asignar nuevos valores que se agregan a cualquier enumeración base.

## <a name="payrollstatewagetaxprepdp-class"></a>PayrollStateWageTaxPrepDP (Clase)

**PayrollStateWageTaxPrepDP** es la clase de proveedor de datos para el informe **Preparación de impuestos estatales sobre la nómina** de SQL Server Reporting Services (SSRS). Para los Estados Unidos, hay tres valores disponibles: **Masculino**, **Femenino**, y **Sin especificar**. En el método **populatePayrollStateWageTaxPrepTmp**, hay una declaración de cambio que se utiliza para asignar el valor de la enumeración **HcmPersonGender** a uno de los tres campos: **IsMale**, **IsFemale**, o **IsUnspecifiedGender**. El valor predeterminado para la declaración de cambio es **IsUnspecifiedGender**. Si agrega cualquier valor a la enumeración **HcmPersonGender** para asignar de manera diferente, debe crear una extensión usando la clase **Cadena de mando** en el método **populatePayrollStateWageTaxPrepTmp** para cambiar el valor según sea necesario.

## <a name="smmoutlooksync_contact-class"></a>smmOutlookSync_Contact (Clase)

La clase de integración **smmOutlookSync_Contact** vincula valores hacia y desde **Outlook** y **Personas de contacto**. **Outlook** admite tres valores: **Masculino**, **Femenino**, y **Sin especificar**. La clase tiene dos métodos para ayudarlo a asignar **Géneros** a **OutlookGenders**. El método predeterminado es **NonSpecific/UnSpecified**. Si crea valores adicionales para la enumeración **Gender**, debe crear una extensión usando la clase **Cadena de mando** sobre ambos métodos para asignar según sea necesario.
