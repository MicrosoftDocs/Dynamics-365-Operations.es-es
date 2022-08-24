---
title: Firmar archivo .appx MPOS con el certificado de firma codificado
description: Este artículo explica cómo registrarse para MPOS con un certificado de firma de código.
author: josaw1
ms.date: 05/27/2022
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: josaw
ms.search.region: Global
ms.author: josaw
ms.search.validFrom: 2019-09-2019
ms.custom: 28021
ms.openlocfilehash: bcf558b4b375078ed24777417e92b1c852f4c0eb
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/12/2022
ms.locfileid: "9282816"
---
# <a name="sign-the-mpos-appx-file-with-a-code-signing-certificate"></a>Firmar archivo .appx MPOS con el certificado de firma codificado

[!include [banner](../includes/banner.md)]

Para instalar Modern POS (MPOS), debe firmar la aplicación MPOS con un certificado de firma de código de un proveedor confiable e instalar el mismo certificado en todas las máquinas donde MPOS está instalado en la carpeta raíz confiable para el usuario actual.

Para firmar la aplicación MPOS con un certificado, use una de estas opciones en el archivo **Retail SDK\\Build tool\\Customization.settings**:

- Agregue la parte de tarea de archivo seguro de los pasos de creación de Azure DevOps y cargue el certificado para proteger la tarea del archivo. Utilice la variable de ruta de salida de la tarea de archivo seguro como un parámetro en el archivo Customization.settings.

    > [!NOTE]
    > La tarea Archivo seguro no admite un certificado protegido con contraseña. Debe eliminar la contraseña antes de cargar esta tarea. Debido a que el certificado se carga en la tarea del sistema de archivos seguro en Azure, puede quitar la contraseña solo para este paso. Sin embargo, debe analizar la eliminación de la contraseña con sus expertos en seguridad para determinar si esta es la acción correcta para su proyecto. No elimine la contraseña del certificado para otros escenarios.
- Utilice un certificado que esté en el sistema de archivos. Para hacer esto, descargue o genere un certificado y colóquelo en el sistema de archivos donde se ejecuta la compilación. El agente hospedado por Microsoft o el usuario de compilación deben tener acceso a esta ruta y archivo.
- Use la huella digital para buscar el certificado en la tienda e inicie sesión con ese certificado.

## <a name="use-a-secure-file-task-for-universal-windows-platform-app-signing"></a>Use una tarea de archivo seguro para la firma de aplicaciones de la plataforma universal de Windows

> [!NOTE]
> También puede usar Azure Key Vault para almacenar el certificado y usar la herramienta de firma de Azure para firmar el archivo .appx de Modern POS y los instaladores de autoservicio. Para ejemplos de secuencias de comandos de canalización e información adicional, consulte [Configure una canalización de compilación en Azure DevOps para generar paquetes de autoservicio Retail](build-pipeline.md#set-up-a-build-pipeline-in-azure-devops-to-generate-retail-self-service-packages).

El uso de una tarea de archivo seguro es el enfoque recomendado para la firma de aplicaciones de la plataforma universal de Windows (UWP). Para obtener más información sobre la firma de paquetes, consulte [Configurar la firma de paquetes](/windows/uwp/packaging/auto-build-package-uwp-apps#configure-package-signing). Este proceso se muestra en la imagen siguiente.

![Flujo de firma de la aplicación MPOS.](media/POSSigningFlow.png)

> [!NOTE]
> Actualmente, el paquete OOB solo admite la firma del archivo .appx, los diferentes instaladores de autoservicio como MPOIS, RSSU y HWS no están firmados por este proceso. Debe firmarlo manualmente con SignTool u otras herramientas de firma. El certificado utilizado para firmar el archivo .appx debe estar instalado en la máquina donde está instalado Modern POS.

## <a name="steps-to-configure-the-certificate-for-signing-in-azure-pipelines"></a>Pasos para configurar el certificado para iniciar sesión en Azure Pipelines

### <a name="certificate-in-the-file-systemsecure-location"></a>Certificado en el sistema de archivo/ubicación segura

Descargue la [tarea DownloadFile](/visualstudio/msbuild/downloadfile-task) y agréguela como primer paso en el proceso de compilación. La ventaja de usar la tarea de archivo seguro es que el archivo se cifra y se coloca en el disco durante la compilación sin importar si la canalización de compilación se realiza correctamente, falla o se cancela. El archivo se elimina de la ubicación de descarga una vez que se completa el proceso de compilación.

1. Descargue y agregue la tarea Archivo seguro como primer paso en la canalización de compilación de Azure. Puede descargar la tarea Archivo seguro desde [DownloadFile](https://marketplace.visualstudio.com/items?itemName=automagically.DownloadFile).
1. Cargue el certificado en la tarea Archivo seguro y configure el Nombre de referencia en Variables de salida, como se muestra en la siguiente imagen.
    > [!div class="mx-imgBorder"]
    > ![Tarea Archivo seguro.](media/SecureFile.png)
1. Cree una nueva variable en Azure Pipelines seleccionando **Nueva variable** bajo la pestaña **Variables**.
1. Proporcione un nombre para la variable en el campo de valor, por ejemplo, **MySigningCert**.
1. Guarde la variable.
1. Abra el archivo **Customization.settings** de **RetailSDK\\BuildTools** y actualice el **ModernPOSPackageCertificateKeyFile** con el nombre de la variable creada en la canalización (paso 3). Por ejemplo:

    ```Xml
    <ModernPOSPackageCertificateKeyFile Condition="'$(ModernPOSPackageCertificateKeyFile)' ==''">$(MySigningCert)</ModernPOSPackageCertificateKeyFile>
    ```
    Este paso es obligatorio si el certificado no está protegido con contraseña. Si el certificado está protegido con contraseña, continúe con los siguientes pasos.
    
1. Si desea colocar una marca de tiempo en el archivo MPOS .appx al firmarlo con un certificado, abra el archivo **Retail SDK\\Build tool\\Customization.settings** y actualice la variable **ModernPOSPackageCertificateTimestamp** con el proveedor de marca de tiempo (por ejemplo, `http://timestamp.digicert.com`).
1. En la pestaña **Variables** de la canalización, agregue una nueva variable de texto seguro. Establezca el nombre en **MySigningCert.secret** y establezca el valor de la contraseña para el certificado. Seleccione el icono de candado para proteger la variable.
1. Agregue una tarea **Guión de Powershell** a la canalización (después de Descargar archivo seguro y antes del paso Crear). Proporcione el nombre para **mostrar** y establezca el Tipo como **En línea**. Copie y pegue lo siguiente en la sección del script.

    ```powershell
    Write-Host "Start adding the PFX file to the certificate store."
    $pfxpath = '$(MySigningCert.secureFilePath)'
    $secureString = ConvertTo-SecureString "$(MySigningCert.secret)" -AsPlainText -Force
    Import-PfxCertificate -FilePath $pfxpath -CertStoreLocation Cert:\CurrentUser\My -Password $secureString
    ```

1. Abra el archivo **Customization.settings** de **RetailSDK\\BuildTools** y actualice **ModernPOSPackageCertificateThumbprint** con el valor de la huella digital del certificado.

    ```Xml
       <ModernPOSPackageCertificateThumbprint Condition="'$(ModernPOSPackageCertificateThumbprint)' == ''"></ModernPOSPackageCertificateThumbprint>
    ```
 
Para obtener detalles sobre cómo obtener la huella digital de un certificado, consulte [recuperar la huella digital de un certificado](/dotnet/framework/wcf/feature-details/how-to-retrieve-the-thumbprint-of-a-certificate#to-retrieve-a-certificates-thumbprint). 

## <a name="download-or-generate-a-certificate-to-sign-the-mpos-app-manually-using-msbuild-in-sdk"></a>Descargue o genere un certificado para firmar la aplicación MPOS manualmente usando msbuild en SDK

Si se usa un certificado descargado o generado para firmar la aplicación MPOS, entonces actualice el nodo **ModernPOSPackageCertificateKeyFile** del archivo **BuildTools\\Customization.settings** para apuntar a la ubicación del archivo pfx (**$(SdkReferencesPath)\\appxsignkey.pfx**). Por ejemplo:

```xml
<ModernPOSPackageCertificateKeyFile Condition="'$(ModernPOSPackageCertificateKeyFile)' ==''">$(SdkReferencesPath)\appxsignkey.pfx</ModernPOSPackageCertificateKeyFile>
```

En este caso, el nombre del archivo del certificado es **appxsignkey.pfx**, ubicado en la carpeta **Retail SDK\\Reference**.

## <a name="use-thumbprint-to-sign-the-mpos-app"></a>Usar la huella digital para registrar la aplicación MPOS

Si usa la huella digital para firmar la aplicación MPOS, instale el certificado localmente. Actualice el valor de la huella digital en el nodo **ModernPOSPackageCertificateThumbprint** del archivo **BuildTools\\Customization.settings**.

Esta opción funcionará si el usuario de compilación es un usuario local. Sin embargo, si está utilizando los agentes de Azure DevOps para generar la compilación, es posible que el agente no tenga permiso para acceder al almacén de certificados para usar el certificado para firmar o que la máquina de compilación no tenga el certificado instalado. En este caso, la solución consiste en cambiar el usuario de compilación a un usuario local e instalar el certificado en el cuadro. Sin embargo, esta opción no funcionará si no tiene acceso de administrador al cuadro.

> [!NOTE]
> Si se utiliza el archivo .pfx o la opción de tarea Archivo seguro para firmar la aplicación, deje el nodo **ModernPOSPackageCertificateThumbprint** de **Customization.settings** vacío. Si se utiliza la opción de huella digital, deje **ModernPOSPackageCertificateKeyFile** vacío. Si se actualizan ambos valores, la compilación fallará.

### <a name="certification-renewal"></a>Renovación de la certificación

### <a name="renew-a-certificate-from-trusted-ca"></a>Renovar un certificado de CA de confianza

Póngase en contacto con su autoridad certificadora (CA) para el proceso de renovación del certificado. Para un certificado de confianza, no se requiere ninguna acción en el lado de MPOS.

### <a name="renew-a-self-signed-certificate"></a>Renovar un certificado autofirmado

No utilice el certificado de muestra disponible en Retail SDK para producción. Solo puede usarse con fines de desarrollo. El certificado de muestra de Contoso no se puede renovar y el certificado de muestra incluido en Retail SDK versión 10.0.16 o anterior caducará el 31 de diciembre de 2020. Si este certificado, o un certificado autofirmado, se ha utilizado para firmar un Modern POS personalizado, existe una gran posibilidad de que Modern POS no funcione correctamente después de esta fecha.
 
### <a name="impact"></a>Impacto
 
Si lo anterior es cierto para usted, el problema que encontrará es que el instalador no podrá ejecutarse después del 31 de diciembre de 2020. Dependiendo de las políticas de TI corporativas utilizadas, es posible que Modern POS no pueda funcionar. Es fundamental que pruebe esto cambiando la fecha temporalmente a una fecha futura, para determinar el impacto en su organización.
 
### <a name="steps-to-determine-the-issue"></a>Pasos para determinar el problema
 
1.  Use la configuración de Windows para cambiar el reloj de la computadora a una fecha y hora en el año 2021.
2.  Verifique que Modern POS se pueda abrir, se pueda iniciar sesión y se pueda completar una transacción.
3.  Verifique que el instalador de autoservicio de Modern POS se pueda ejecutar y, de ser así, la instalación se completará correctamente.
4.  Regrese la configuración del reloj de Windows a la fecha y hora correctas.
 
Si puede completar todos estos pasos sin problemas, podrá operar con el certificado actual después del 31 de diciembre de 2020.  
 
### <a name="steps-going-forward"></a>Pasos de aquí en adelante 

Se recomienda encarecidamente que renueve el certificado utilizado anteriormente. Le recomendamos encarecidamente que obtenga un nuevo certificado. Para ello, debe realizar una de las acciones siguientes:
 
- **Privilegiado** - Obtener un certificado de firma de código de una autoridad de certificación de confianza.

- **No preferido** - Generar un certificado de firma de código autofirmado para usar. Por lo general, esto se usa solo con fines de desarrollo dentro de un dominio y no se recomienda para producción. 

- **Disponible como solución temporal** - Usar el certificado de firma de código de Contoso renovado. Por lo general, esto se usa con fines de prueba, por lo que no se recomienda implementarlo en producción.
 
A continuación, genere un nuevo paquete de POS moderno personalizado que esté firmado con este certificado obtenido de una de las acciones anteriores. Según el certificado, debe seguir uno de los pasos siguientes:
 
- Si utiliza un nuevo certificado de confianza (o un nuevo certificado autofirmado), deberá instalar un nuevo certificado en cada dispositivo. Después de eso, debe tomar el paquete Modern POS recién creado (instalador), desinstalar la aplicación existente y luego reinstalar el nuevo paquete Modern POS. Deberá realizar una activación de dispositivo de Modern POS en cada dispositivo.

- Si usa el certificado de Contoso renovado, deberá instalar el nuevo certificado en cada dispositivo e instalar el paquete Modern POS (instalador). No es necesario que desinstale, sin embargo, debe volver a instalarlo en el dispositivo. Tenga en cuenta que no se requerirá la activación del dispositivo de Modern POS. Esta opción es una solución temporal. Solo use esta opción para evitar la reactivación y resolver el problema antes de obtener un nuevo certificado de confianza.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
