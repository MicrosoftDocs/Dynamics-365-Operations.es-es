---
title: "Formatos de archivo para métodos de pago"
description: "Este tema describe los dos métodos para obtener los formatos de archivo que se pueden usar para las formas de pago."
author: ShylaThompson
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: CustPaymMode, VendPaymMode
audience: Application User
ms.search.scope: Operations, Core
ms.custom: 262514
ms.assetid: 72ea2018-5a49-419c-93d0-755e5ff2722f
ms.search.region: Belgium, France, Germany, Norway, Spain, Sweden, Switzerland
ms.author: v-lenest
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
translationtype: Human Translation
ms.sourcegitcommit: f707d45290682e79ee439ba0d504852429defa90
ms.openlocfilehash: 54af22f1f2ec779bf947ae584a3ae09c20e6a364
ms.lasthandoff: 03/31/2017


---

# <a name="file-formats-for-methods-of-payment"></a>Formatos de archivo para métodos de pago

Este tema describe los dos métodos para obtener los formatos de archivo que se pueden usar para las formas de pago.

Existen dos métodos que puede utilizar para recopilar los formatos de archivo para usarlas con formas de pago, los formatos de archivo electrónicos de (ER) que informan o los formatos de archivo X++. Al configurar un método de pago para un cliente o proveedor, se indica qué formatos de archivo y normas se deben usar para los pagos y la manera en la que los pagos se procesarán. Puede seleccionar entre los siguientes tipos de formatos:

-   Exportar
-   Importar
-   Devolución
-   Envío

### <a name="method-1-electronic-reporting-file-formats"></a>Método 1: Formatos de archivo electrónicos de informes

Para los formatos de archivo que se basan en la configuración de ER, debe importar las configuraciones de servicios (LCS) del ciclo de vida. Para obtener más información, consulte [las configuraciones electrónicas de informes de la descarga de servicios] del ciclo de vida (/dynamics365/operations/dev-itpro/analytics/download-electronic-reporting-configuration-lcs). Tras importar las configuraciones de informes para dichos formatos de archivo, los formatos importados estarán disponibles para seleccionarlas en ** las formas de pago ** la página. El proceso para importar y seleccionar los formatos de archivo para Europa es similar al procedimiento para Japón. <!---For more details, see [Enable the JBA payment file format](https://ax.help.dynamics.com/en/wiki/enable-the-jba-payment-file-format/).-->

### <a name="method-2-x-file-formats"></a>Método 2: Formatos de archivo X++

A los formatos de archivo para que se basan en código X++, siga estos pasos.

1.  Ir ** las formas de pago ** a la página.
2.  En ** los formatos de archivo ** la ficha desplegable, haga clic en ** ** configuración.
3.  Seleccione la ficha que corresponde con el tipo de formato de archivo.
4.  Seleccione un formato de archivo disponible de ** ** lo muestran y mueven ** ** seleccionado en la lista con el control de la flecha.
5.  Cierre ** los formatos de archivo para métodos de pago ** la página.
6.  En ** los formatos de archivo ** la ficha desplegable, seleccione el formato de archivo que se debe usar para el método de pago del campo de formato de archivo apropiado. Las opciones generales electrónicas del informe se deben establecer ** ningún ** para los formatos de archivo X++.



