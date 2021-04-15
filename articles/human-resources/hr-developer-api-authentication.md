---
title: Autentificación
description: Este artículo proporciona información general sobre cómo autenticar con la interfaz de programación de aplicaciones (API) de datos de Microsoft Dynamics 365 Human Resources.
author: andreabichsel
ms.date: 02/03/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 3dffe1db98ba39fde2229e69bc70bdbf113ff6ad
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/31/2021
ms.locfileid: "5793690"
---
# <a name="authentication"></a>Autentificación

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Este artículo proporciona información general sobre cómo autenticar con la interfaz de programación de aplicaciones (API) de datos de Microsoft Dynamics 365 Human Resources.

## <a name="overview"></a>Visión general

La API de datos para Recursos Humanos es una implementación de OData. Para obtener más información, consulte [Open Data Protocol (OData)](../fin-ops-core/dev-itpro/data-entities/odata.md).

Su aplicación debe autenticar como autor de llamada autorizado para que la API atienda las solicitudes de su aplicación.

## <a name="fundamentals"></a>Conceptos fundamentales

Para llamar a la API de datos, su aplicación debe adquirir un token de acceso de la plataforma de identidad de Microsoft. El token de acceso contiene información sobre su aplicación y el permiso que tiene para llamar a recursos de Recursos humanos.

### <a name="access-token"></a>Token de acceso

Los tokens de acceso emitidos por la plataforma de identidad de Microsoft son tokens web (JWT) de JavaScript Object Notation (JSON) codificados en base64. Contienen información (notificaciones) que la API de datos (y otras API web que están protegidas por la plataforma de identidad de Microsoft) utilizan para validar a la persona que llama y asegurarse de que la persona que llama tenga los permisos correctos para realizar la operación que solicita. Durante las llamadas, puede tratar los tokens de acceso como opacos. Siempre debe transmitir tokens de acceso a través de un canal seguro, como Transport Layer Security (TLS) y Hypertext Transfer Protocol Secure (HTTPS).

Este es un ejemplo de un token de acceso emitido por la plataforma de identidad de Microsoft.

```jwt
EwAoA8l6BAAU7p9QDpi/D7xJLwsTgCg3TskyTaQAAXu71AU9f4aS4rOK5xoO/SU5HZKSXtCsDe0Pj7uSc5Ug008qTI+a9M1tBeKoTs7tHzhJNSKgk7pm5e8d3oGWXX5shyOG3cKSqgfwuNDnmmPDNDivwmi9kmKqWIC9OQRf8InpYXH7NdUYNwN+jljffvNTewdZz42VPrvqoMH7hSxiG7A1h8leOv4F3Ek/oeJX6U8nnL9nJ5pHLVuPWD0aNnTPTJD8Y4oQTp5zLhDIIfaJCaGcQperULVF7K6yX8MhHxIBwek418rKIp11om0SWBXOYSGOM0rNNN59qNiKwLNK+MPUf7ObcRBN5I5vg8jB7IMoz66jrNmT2uiWCyI8MmYDZgAACPoaZ9REyqke+AE1/x1ZX0w7OamUexKF8YGZiw+cDpT/BP1GsONnwI4a8M7HsBtDgZPRd6/Hfqlq3HE2xLuhYX8bAc1MUr0gP9KuH6HDQNlIV4KaRZWxyRo1wmKHOF5G5wTHrtxg8tnXylMc1PKOtaXIU4JJZ1l4x/7FwhPmg9M86PBPWr5zwUj2CVXC7wWlL/6M89Mlh8yXESMO3AIuAmEMKjqauPrgi9hAdI2oqnLZWCRL9gcHBida1y0DTXQhcwMv1ORrk65VFHtVgYAegrxu3NDoJiDyVaPZxDwTYRGjPII3va8GALAMVy5xou2ikzRvJjW7Gm3XoaqJCTCExN4m5i/Dqc81Gr4uT7OaeypYTUjnwCh7aMhsOTDJehefzjXhlkn//2eik+NivKx/BTJBEdT6MR97Wh/ns/VcK7QTmbjwbU2cwLngT7Ylq+uzhx54R9JMaSLhnw+/nIrcVkG77Hi3neShKeZmnl5DC9PuwIbtNvVge3Q+V0ws2zsL3z7ndz4tTMYFdvR/XbrnbEErTDLWrV6Lc3JHQMs0bYUyTBg5dThwCiuZ1evaT6BlMMLuSCVxdBGzXTBcvGwihFzZbyNoX+52DS5x+RbIEvd6KWOpQ6Ni+1GAawHDdNUiQTQFXRxLSHfc9fh7hE4qcD7PqHGsykYj7A0XqHCjbKKgWSkcAg==
```

Para llamar a la API de datos, adjunte el token de acceso como token de portador al encabezado de autorización en su solicitud HTTP. He aquí un ejemplo.

```HTTP
HTTP/1.1
Authorization: Bearer EwAoA8l6BAAU ... 7PqHGsykYj7A0XqHCjbKKgWSkcAg==
Host: https://{cluster}.hr.talent.dynamics.com
GET https://{cluster}.hr.talent.dynamics.com/namespaces/{namespace_guid}/data/JobTypes
```

## <a name="register-a-new-application-by-using-the-azure-portal"></a>Registre una aplicación nueva mediante el portal de Azure

1. Inicie sesión en el [portal de Microsoft Azure](https://portal.azure.com) con una cuenta profesional o educativa, o una cuenta de Microsoft personal.

2. Si su cuenta le da acceso a más de un inquilino, seleccione su cuenta en la esquina superior derecha y configure su sesión de portal en el inquilino de Azure Active Directory (Azure AD) que desee.

3. En el panel izquierdo, seleccione el servicio de **Azure Active Directory** y luego seleccione **Registros de aplicaciones \> Nuevo registro**.

4. Cuando aparezca la página **Registrar una aplicación**, introduzca la información de registro de su aplicación:

    - **Nombre**: introduzca un nombre de aplicación significativo que se mostrará a los usuarios de la aplicación.
    - **Tipos de cuenta admitidos** : seleccione los tipos de cuentas que su aplicación debería admitir.

        | Tipos de cuenta admitidos | Descripción |
        |-------------------------|-------------|
        | Cuentas en el directorio de esta organización solo | Seleccione esta opción si está creando una aplicación de línea de negocio. Esta opción no está disponible a menos que esté registrando la aplicación en un directorio.<p>Esta opción está asignada a **inquilino único de Azure AD**.</p><p>Esta opción es la predeterminada a menos que esté registrando la aplicación fuera de un directorio. En ese caso, la opción predeterminada es **cuentas de Microsoft personales y multiinquilino de Azure AD**.</p> |
        | Cuentas en cualquier directorio de organización | Seleccione esta opción para tener como objetivos todos los clientes empresariales y educativos.<p>Esta opción está asignada a **solo multiinquilino de Azure AD**.</p><p>Si registró la aplicación como **solo inquilino único de Azure AD**, puede usar la hoja **Autenticación** para actualizarla a **solo multiinquilino de Azure AD** y luego de nuevo a **solo inquilino único de Azure AD**.</p> |
        | Cuentas en cualquier cuenta de Microsoft personal y directorio de organización | Seleccione esta opción para dirigirse al conjunto más amplio de clientes.<p>Esta opción se asigna a **cuentas de Microsoft personales y multiinquilino de Azure AD**.</p><p>Si ha registrado la aplicación como **cuentas de Microsoft personal y multiinquilino de Azure AD**, no puede cambiar esta configuración en la interfaz de usuario (IU). En su lugar, debe usar el editor de manifiesto de la aplicación para cambiar los tipos de cuenta admitidos.</p> |

    - **URI de redireccionamiento (opcional)**: seleccione el tipo de aplicación que está creando: **Web** o **Cliente público (móvil y de escritorio)**. A continuación, introduzca el URI de redireccionamiento (o URL de respuesta) para la aplicación.

        - Para aplicaciones web, proporcione la URL base de la aplicación. Por ejemplo, `http://localhost:31544` podría ser la URL de una aplicación web que se ejecuta en su máquina local. A continuación, los usuarios usan esta dirección URL para iniciar sesión en una aplicación cliente web.
        - Para aplicaciones de cliente público, proporcione el URI que Azure AD utiliza para devolver respuestas de token. Introduzca un valor específico para su aplicación, como `myapp://auth`.

        Para ver ejemplos específicos de aplicaciones web o aplicaciones nativas, consulte los tutoriales rápidos en [Plataforma de identidad de Microsoft (anteriormente, Azure Active Directory para desarrolladores)](https://docs.microsoft.com/azure/active-directory/develop/#quickstarts).

5. En **Permisos de API**, seleccione **Agregar un permiso**. Después, en la **API que usa mi organización**, busque **Dynamics 365 Human Resources** y agregue el permiso **usuario\_interpretación** a su aplicación. El id. de aplicación para Recursos Humanos es f9be0c49-aa22-4ec6-911a-c5da515226ff. Use este id. para asegurarse de haber elegido la aplicación correcta.

6. Seleccione **Registrar**.

   [![Registro de una aplicación nueva en el portal de Azure](media/api-new-app-registration-expanded.png)](media/api-new-app-registration-expanded.png#lightbox)

Azure AD asigna un id. de aplicación único (id. de cliente) a su aplicación y lo lleva a la página **Visión general** para su aplicación. Para agregar más capacidades a su aplicación, puede seleccionar otras opciones de configuración, como opciones como marcas y para certificados y secretos.

## <a name="retrieving-an-access-token"></a>Recuperación de un token de acceso

Los detalles de cómo recuperar un token de acceso para llamar a la API de datos de Recursos Humanos dependerán de las tecnologías que esté utilizando para desarrollar su aplicación cliente. Por ejemplo, podría estar [probando con una utilidad de terceros](../fin-ops-core/dev-itpro/data-entities/third-party-service-test.md) (como Postman), desarrollando una aplicación de consola C# o un servicio web, o creando un cliente javascript/TypeScript.

Aplicación de cliente C# de ejemplo:
```C#
using System;
using System.Net.Http;
using System.Threading.Tasks;

// requires appropriate NuGet package references in the project
using Microsoft.IdentityModel.Clients.ActiveDirectory;

namespace TalentODataPoC
{
    class Program
    {
        // prereq: This client app must be registered in Azure Active Directory. The app must be
        // registered as requiring permission to the Dynamics 365 for Talent API (with the Dynamics
        // HCM Workload delegated permission).
        static string clientId = "4fc703ef-672c-4e2c-813f-2f9d29d726db"; // This value should be obtained from AAD and must match your registered app
        static string talentNamespaceUri = "";

        public static async Task CallTalentODataService()
        {
            // authority URI
            UriBuilder uri = new UriBuilder("https://login.microsoftonline.com/common");
            AuthenticationContext authenticationContext = new AuthenticationContext(uri.ToString());

            // request token for the resource we want to access (Human Resources). This will authenticate
            // the user and return an access token containing claims for the authenticated user.
            var authResult = await authenticationContext.AcquireTokenAsync(
                "http://hr.talent.dynamics.com", /*Talent app id or resource URI*/
                clientId, /*registered client app id*/
                new Uri("https://localhost"), /*redirect URI, as registered in your AAD app*/
                new PlatformParameters(PromptBehavior.SelectAccount));

            // create the authorization header, which needs to be passed in the Header of the HTTP Requests to Talent
            string authHeader = authResult.CreateAuthorizationHeader();

            // HINT: paste the JWT into https://jwt.ms to decode and view it
            Console.Write("authHeader: ");
            Console.WriteLine(authHeader);
            Console.WriteLine();

            HttpClient client = new HttpClient();
            client.DefaultRequestHeaders.Add("Authorization", authHeader);

            string s;

            Console.Write("Talent Namespace URI: ");
            Console.WriteLine(talentNamespaceUri);
            Console.WriteLine();

            // call the OData service to get JobType data from Talent
            var resultOdata = await client.GetAsync(talentNamespaceUri + "data/JobTypes");
            s = await resultOdata.Content.ReadAsStringAsync();
            Console.WriteLine(s);
            Console.WriteLine();
        }

        static void Main(string[] args)
        {
            Console.WriteLine();

            // if the user passes in a single parameter, assume it is the namespaceUri for Talent
            if (args.Length == 1)
            {
                talentNamespaceUri = args[0];
            } else if (args.Length == 0)
            {
                Console.WriteLine("Enter Talent URL including namespace.");
                Console.WriteLine("Example: https://aos-rts-sf-21454f9d830-prod-westus2.hr.talent.dynamics.com/namespaces/2328af1a-2d45-4c6a-99e3-12a4c3867dcf/");
                Console.Write("> ");
                talentNamespaceUri = Console.ReadLine();
                if (!talentNamespaceUri.EndsWith("/"))
                {
                    talentNamespaceUri = talentNamespaceUri + "/";
                }
            } else
            {
                Console.WriteLine("Unexpected Arguments");
                System.Environment.Exit(1);
            }

            Task t = Program.CallTalentODataService();
            t.Wait();
        }
    }
}
```

Una vez que haya recuperado un token de acceso, pasará el token en el encabezado de Autorización como un token de portador con cada solicitud que envíe a la API de datos, como se ha descrito anteriormente.


[!INCLUDE[footer-include](../includes/footer-banner.md)]