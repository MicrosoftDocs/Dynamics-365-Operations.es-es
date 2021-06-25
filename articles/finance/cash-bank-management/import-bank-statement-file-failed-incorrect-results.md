---
title: Solución de problemas de la importación de archivos de extractos bancarios
description: Es importante que el archivo de extracto bancario del banco coincida con el diseño admitido por Microsoft Dynamics 365 Finance. Debido a los estrictos estándares para extractos bancarios, la mayoría de las integraciones funcionarán correctamente. Sin embargo, a veces, el archivo de extracto no se puede importar o tiene resultados incorrectos. Normalmente, estos problemas son originados por pequeñas diferencias en el archivo de extracto bancario. En este artículo se explica cómo corregir estas diferencias y resolver los problemas.
author: panolte
ms.date: 03/29/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: BankStatementFormat
audience: Application User
ms.reviewer: roschlom
ms.custom: 141273
ms.assetid: 3ee2f32b-02aa-420b-8990-e6aa5fc6bda3
ms.search.region: global
ms.author: panolte
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 14f0e480b93e663f81db5a1edb2ae71b559bb05e
ms.sourcegitcommit: ff09736563d3cd2bc74c7664edd1767b218401cb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2021
ms.locfileid: "6188569"
---
# <a name="bank-statement-file-import-troubleshooting"></a>Solución de problemas de la importación de archivos de extractos bancarios

[!include [banner](../includes/banner.md)]

Es importante que el archivo de extracto bancario del banco coincida con el diseño admitido por Microsoft Dynamics 365 Finance. Debido a los estrictos estándares para extractos bancarios, la mayoría de las integraciones funcionarán correctamente. Sin embargo, a veces, el archivo de extracto no se puede importar o tiene resultados incorrectos. Normalmente, estos problemas son originados por pequeñas diferencias en el archivo de extracto bancario. En este artículo se explica cómo corregir estas diferencias y resolver los problemas.

## <a name="what-is-the-error"></a>¿Qué es el error?

Tras intentar importar un archivo de extracto bancario, vaya al historial de trabajos de administración de datos y sus detalles de ejecución para encontrar el error. El error puede resultar de ayuda al señalar la instrucción, el saldo o la línea de extracto. Sin embargo, es poco probable que proporcione suficiente información para ayudarle a identificar el campo o el elemento que está ocasionando el problema.

> [!NOTE]
> Los extractos bancarios importados pueden superponerse solo en un momento determinado del tiempo.  Por ejemplo, si un extracto finaliza a las 12:00 a. m. del 1 de enero de 2021, la fecha de inicio del siguiente extracto puede ser las 12:00 a. m. del 1 de enero de 2021 12:00:00 a. m.

## <a name="what-are-the-differences"></a>¿Cuáles son las diferencias?
Compare la definición del diseño de archivos de banco con la definición de importación de Finance y observe los posibles diferencias en los campos y elementos. Compare el archivo de extracto bancario con el archivo de muestra relacionado de Finance. En los archivos ISO20022 las diferencia se verán fácilmente.

## <a name="time-zone-differences-on-imported-bank-statements"></a>Diferencias de zona horaria de extractos bancarios importados
Los valores de fecha y hora en el archivo de importación pueden ser distintos de los valores de fecha y hora que se muestran en Finance and Operations. Para evitar esta discrepancia, especifique una preferencia de zona horaria en la página **Configurar orígenes de datos**. Para obtener más información sobre cómo especificar una preferencia de zona horaria, consulte [Configurar el proceso avanzado de importación de conciliación bancaria](set-up-advanced-bank-reconciliation-import-process.md).

## <a name="transformations"></a>Transformaciones
Normalmente, el cambio se debe realizar en una de tres transformaciones. Cada transformación se escribe para un estándar específico.

| Nombre del recurso                                         | Nombre de archivo                          |
|-------------------------------------------------------|------------------------------------|
| BankStmtImport\_BAI2CSV\_to\_BAI2XML\_xslt            | BAI2CSV-to-BAI2XML.xslt            |
| BankStmtImport\_ISO20022XML\_to\_Reconciliation\_xslt | ISO20022XML-to-Reconciliation.xslt |
| BankStmtImport\_MT940TXT\_to\_MT940XML\_xslt          | MT940TXT-to-MT940XML.xslt          |

## <a name="debugging-transformations"></a>Depuración de transformaciones
### <a name="adjust-the-bai2-and-mt940-files"></a>Ajustar los archivos BAI2 y MT940

Los archivos BAI2 y MT940 son archivos basados en texto y requieren un ajuste para habilitar la depuración del Lenguaje de transformación basado en hojas de estilo (XSLT). El programa realiza este ajuste cuando se importa un archivo.

1.  Cree un archivo XML y copie el siguiente texto en él.

    ```xml
    <Batch><![CDATA[PASTESTATEMENTFILEHERE
        ]]></Batch>
    ```
    
2.  Copie el contenido del archivo de extracto bancario y péguelo en el archivo XML de modo que reemplace **PASTESTATEMENTFILEHERE**.

### <a name="debug-the-xslt"></a>Depurar XSLT

Para obtener más información, vea <https://msdn.microsoft.com/library/ms255605.aspx>.

1.  Iniciar Microsoft Visual Studio.
2.  Crear una aplicación de consola.
3.  Abra el XSLT adecuado.
4.  Haga clic en el XLST y su página de propiedades.
5.  Establezca la entrada en la ubicación del archivo del extracto bancario.
6.  Defina una ubicación y un nombre de archivo para la salida.
7.  Establezca los puntos de interrupción necesarios.
8.  En el menú, haga clic en **XML** &gt; **Iniciar depuración de XSLT**.

### <a name="format-the-xslt-output"></a>Aplicar formato a la salida de XSLT

Cuando se ejecuta la transformación, crea un archivo de salida que pueda ver en Visual Studio. Use Ctrl+A, Ctrl+K y Ctrl+D para dar formato rápidamente al archivo de salida.

### <a name="adjust-the-transformation"></a>Ajustar la transformación

Ajuste la transformación para obtener el elemento o el campo adecuado en el archivo de extracto bancario. A continuación, asigne ese campo o artículo al elemento de Finance adecuado.

### <a name="debitcredit-indicator"></a>Indicador de débito o crédito

A veces, los débitos se pueden importar como créditos y los créditos se pueden importar como débitos. Para resolver este problema, debe cambiar el XSLT adecuado. Si los extractos bancarios proceden de varios bancos, asegúrese de que todos usen el mismo enfoque de débito/crédito o cree transformaciones independientes.

-   Plantilla GetAmountCreditDebitIndicator de BAI2XML-to-Reconciliation.xlst
-   Plantilla GetCreditDebit de ISO20022XML-to-Reconcilation.xslt
-   Plantilla GetCreditDebitIndicator de MT940XML-to-Reconcilation.xslt

## <a name="examples-of-bank-statement-formats-and-technical-layouts"></a>Ejemplos de diseños técnicos y formatos de extracto bancario
En la tabla siguiente se muestran ejemplos de las definiciones de diseño técnico para los archivos de importación de conciliación bancaria avanzados y tres archivos de ejemplo de extracto bancario relacionados. Puede descargar los archivos de ejemplo y los diseños técnicos aquí: [Ejemplos de archivos de importación](//download.microsoft.com/download/8/e/c/8ec8d2d0-eb8c-41fb-ad8c-f01a4d670a44/Dynamics365FinanceAdvancedBankStatementLayouts.xlsx)  

| Definición de diseño técnico                             | Archivo de ejemplo de extracto bancario          |
|---------------------------------------------------------|--------------------------------------|
| DynamicsAXMT940Layout                                   | [MT940StatementExample](//download.microsoft.com/download/2/d/c/2dcc4e55-ddc8-4a74-b79c-250fae201c3c/mt940StatementExample.txt)                |
| DynamicsAXISO20022Layout                                | [ISO20022StatementExample](https://nam06.safelinks.protection.outlook.com/?url=https%3A%2F%2Fdownload.microsoft.com%2Fdownload%2F1%2F5%2F5%2F155d84ed-c250-48f3-b0b1-c5a431e7855b%2FISO20022-MultipleStatements.xml&data=04%7C01%7CRobert.Schlomann%40microsoft.com%7C30d0c233cb6546547d0a08d8f4965edc%7C72f988bf86f141af91ab2d7cd011db47%7C1%7C0%7C637528273956712775%7CUnknown%7CTWFpbGZsb3d8eyJWIjoiMC4wLjAwMDAiLCJQIjoiV2luMzIiLCJBTiI6Ik1haWwiLCJXVCI6Mn0%3D%7C1000&sdata=3VzvLZK%2BO8PjuI7XVdC6rD2j3nUJfteo7zFp%2B1s9BwM%3D&reserved=0)             |
| DynamicsAXBAI2Layout                                    | [BAI2StatementExample](//download.microsoft.com/download/1/1/6/11693f57-bfc1-4993-a274-5fb978be70fa/BAI2StatementExample.txt)                 |







[!INCLUDE[footer-include](../../includes/footer-banner.md)]
