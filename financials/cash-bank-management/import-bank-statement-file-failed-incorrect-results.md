---
title: "Solución de problemas de la importación de archivos de extractos bancarios"
description: "Es importante que el archivo de extracto bancario del banco coincida con el diseño admitido por Microsoft Dynamics 365 for Finance and Operations, Enterprise Edition. Debido a los estrictos estándares para extractos bancarios, la mayoría de las integraciones funcionarán correctamente. Sin embargo, a veces, el archivo de extracto no se puede importar o tiene resultados incorrectos. Normalmente, estos problemas son originados por pequeñas diferencias en el archivo de extracto bancario. En este artículo se explica cómo corregir estas diferencias y resolver los problemas."
author: twheeloc
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 141273
ms.assetid: 3ee2f32b-02aa-420b-8990-e6aa5fc6bda3
ms.search.region: global
ms.author: saraschi
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: 869151f2486b7a481e4694cfb6992d0ee2cfc008
ms.openlocfilehash: 33b7a499caf9292e44c155a0e1bd6a8929558be5
ms.contentlocale: es-es
ms.lasthandoff: 06/13/2017


---

# Solución de problemas de la importación de archivos de extractos bancarios
<a id="bank-statement-file-import-troubleshooting" class="xliff"></a>

[!include[banner](../includes/banner.md)]


Es importante que el archivo de extracto bancario del banco coincida con el diseño admitido por Microsoft Dynamics 365 for Finance and Operations, Enterprise Edition. Debido a los estrictos estándares para extractos bancarios, la mayoría de las integraciones funcionarán correctamente. Sin embargo, a veces, el archivo de extracto no se puede importar o tiene resultados incorrectos. Normalmente, estos problemas son originados por pequeñas diferencias en el archivo de extracto bancario. En este artículo se explica cómo corregir estas diferencias y resolver los problemas.

¿Qué es el error?
<a id="what-is-the-error" class="xliff"></a>
------------------

Tras intentar importar un archivo de extracto bancario, vaya al historial de trabajos de administración de datos y sus detalles de ejecución para encontrar el error. El error puede resultar de ayuda al señalar la instrucción, el saldo o la línea de extracto. Sin embargo, es poco probable que proporcione suficiente información para ayudarle a identificar el campo o el elemento que está ocasionando el problema.

## ¿Cuáles son las diferencias?
<a id="what-are-the-differences" class="xliff"></a>
Compare la definición del diseño de archivos de banco con la definición de importación de Finance and Operations y observe los posibles diferencias en los campos y elementos. Compare el archivo de extracto bancario con el archivo de muestra relacionado de Finance and Operations. En los archivos ISO20022 las diferencia se verán fácilmente.

## Transformaciones
<a id="transformations" class="xliff"></a>
Normalmente, el cambio se debe realizar en una de tres transformaciones. Cada transformación se escribe para un estándar específico.

| Nombre del recurso                                         | Nombre de archivo                          |
|-------------------------------------------------------|------------------------------------|
| BankStmtImport\_BAI2CSV\_to\_BAI2XML\_xslt            | BAI2CSV-to-BAI2XML.xslt            |
| BankStmtImport\_ISO20022XML\_to\_Reconciliation\_xslt | ISO20022XML-to-Reconciliation.xslt |
| BankStmtImport\_MT940TXT\_to\_MT940XML\_xslt          | MT940TXT-to-MT940XML.xslt          |

## Depuración de transformaciones
<a id="debugging-transformations" class="xliff"></a>
### Ajustar los archivos BAI2 y MT940
<a id="adjust-the-bai2-and-mt940-files" class="xliff"></a>

Los archivos BAI2 y MT940 son archivos basados en texto y requieren un ajuste para habilitar la depuración del Lenguaje de transformación basado en hojas de estilo (XSLT). El programa realiza este ajuste cuando se importa un archivo.

1.  Cree un archivo XML y copie el siguiente texto en él.

        <Batch><![CDATA[PASTESTATEMENTFILEHERE
        ]]></Batch>

2.  Copie el contenido del archivo de extracto bancario y péguelo en el archivo XML de modo que reemplace **PASTESTATEMENTFILEHERE**.

### Depurar XSLT
<a id="debug-the-xslt" class="xliff"></a>

Para obtener más información, consulte <https://msdn.microsoft.com/en-us/library/ms255605.aspx>.

1.  Inicie Microsoft Visual Studio.
2.  Crear una aplicación de consola.
3.  Abra el XSLT adecuado.
4.  Haga clic en el XLST y su página de propiedades.
5.  Establezca la entrada en la ubicación del archivo del extracto bancario.
6.  Defina una ubicación y un nombre de archivo para la salida.
7.  Establezca los puntos de interrupción necesarios.
8.  En el menú, haga clic en **XML** &gt; **Iniciar depuración de XSLT**.

### Aplicar formato a la salida de XSLT
<a id="format-the-xslt-output" class="xliff"></a>

Cuando se ejecuta la transformación, crea un archivo de salida que pueda ver en Visual Studio. Use Ctrl+A, Ctrl+K y Ctrl+D para dar formato rápidamente al archivo de salida.

### Ajustar la transformación
<a id="adjust-the-transformation" class="xliff"></a>

Ajuste la transformación para obtener el elemento o el campo adecuado en el archivo de extracto bancario. A continuación, asigne ese campo o artículo al elemento de Finance and Operations adecuado.

### Indicador de débito o crédito
<a id="debitcredit-indicator" class="xliff"></a>

A veces, los débitos se pueden importar como créditos y los créditos se pueden importar como débitos. Para resolver este problema, debe cambiar el XSLT adecuado. Si los extractos bancarios proceden de varios bancos, asegúrese de que todos usen el mismo enfoque de débito/crédito o cree transformaciones independientes.

-   Plantilla GetAmountCreditDebitIndicator de BAI2XML-to-Reconciliation.xlst
-   Plantilla GetCreditDebit de ISO20022XML-to-Reconcilation.xslt
-   Plantilla GetCreditDebitIndicator de MT940XML-to-Reconcilation.xslt

## Ejemplos de diseños técnicos y formatos de extracto bancario
<a id="examples-of-bank-statement-formats-and-technical-layouts" class="xliff"></a>
En la tabla siguiente se muestran ejemplos de las definiciones de diseño técnico para los archivos de importación de conciliación bancaria avanzados y tres archivos de ejemplo de extracto bancario relacionados. Puede descargar los archivos de ejemplo y los diseños técnicos desde: https://mbs.microsoft.com/customersource/northamerica/AX/learning/documentation/how-to-articles/exofbankstfotechlayouts  


| Definición de diseño técnico                             | Archivo de ejemplo de extracto bancario          |
|---------------------------------------------------------|--------------------------------------|
| DynamicsAXMT940Layout                                   | MT940StatementExample                |
| DynamicsAXISO20022Layout                                | ISO20022StatementExample             |
| DynamicsAXBAI2Layout                                    | BAI2StatementExample                 |






