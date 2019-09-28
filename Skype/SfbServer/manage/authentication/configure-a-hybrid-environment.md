---
title: Konfigurieren der Server-zu-Server-Authentifizierung für eine Skype for Business Server-Hybridumgebung
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 700639ec-5264-4449-a8a6-d7386fad8719
description: 'Zusammenfassung: Konfigurieren der Server-zu-Server-Authentifizierung für eine Skype for Business Server-Hybridumgebung'
ms.openlocfilehash: 2879a1acc35a2c8928a95af913476c26028d6e6c
ms.sourcegitcommit: 1721acdd507591d16a4e766b390b997979d985e5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/27/2019
ms.locfileid: "37305771"
---
# <a name="configure-server-to-server-authentication-for-a-skype-for-business-server-hybrid-environment"></a><span data-ttu-id="dcc10-103">Konfigurieren Sie die Server-zu-Server-Authentifizierung für eine Skype for Business Server-Hybridumgebung.</span><span class="sxs-lookup"><span data-stu-id="dcc10-103">Configure server-to-server authentication for a Skype for Business Server hybrid environment.</span></span>

<span data-ttu-id="dcc10-104">**Zusammenfassung:** Konfigurieren der Server-zu-Server-Authentifizierung für die Skype for Business Server-Hybridumgebung</span><span class="sxs-lookup"><span data-stu-id="dcc10-104">**Summary:** Configure server-to-server authentication for Skype for Business Server hybrid environment.</span></span>

<span data-ttu-id="dcc10-105">In einer Hybrid Konfiguration sind einige Ihrer Benutzer in einer lokalen Installation von Skype for Business Server beheimatet, während andere Benutzer in der Office 365-Version von Skype for Business Server verwaltet werden.</span><span class="sxs-lookup"><span data-stu-id="dcc10-105">In a hybrid configuration, some of your users are homed on an on-premises installation of Skype for Business Server while other users are homed on the Office 365 version of Skype for Business Server.</span></span> <span data-ttu-id="dcc10-106">Um die Server-zu-Server-Authentifizierung in einer Hybridumgebung zu konfigurieren, müssen Sie zuerst Ihre lokale Installation von Skype for Business Server so konfigurieren, dass Sie dem Office 365-autorisierungsserver vertraut.</span><span class="sxs-lookup"><span data-stu-id="dcc10-106">In order to configure server-to-server authentication in a hybrid environment, you must first configure your on-premises installation of Skype for Business Server to trust the Office 365 authorization server.</span></span> <span data-ttu-id="dcc10-107">Der erste Schritt in diesem Prozess kann durchführen des folgenden Skype for Business Server-Verwaltungsshell-Skripts erfolgen:</span><span class="sxs-lookup"><span data-stu-id="dcc10-107">The initial step in this process can be carried out by running the following Skype for Business Server Management Shell script:</span></span>

```
$TenantID = (Get-CsTenant -Filter {DisplayName -eq "Fabrikam.com"}).TenantId

$sts = Get-CsOAuthServer microsoft.sts -ErrorAction SilentlyContinue

   if ($sts -eq $null)
      {
         New-CsOAuthServer microsoft.sts -MetadataUrl "https://accounts.accesscontrol.windows.net/$TenantId/metadata/json/1"
      }
   else
      {
         if ($sts.MetadataUrl -ne  "https://accounts.accesscontrol.windows.net/$TenantId/metadata/json/1")
            {
               Remove-CsOAuthServer microsoft.sts
               New-CsOAuthServer microsoft.sts -MetadataUrl "https://accounts.accesscontrol.windows.net/$TenantId/metadata/json/1"
            }
        }

$exch = Get-CsPartnerApplication microsoft.exchange -ErrorAction SilentlyContinue

if ($exch -eq $null)
   {
      New-CsPartnerApplication -Identity microsoft.exchange -ApplicationIdentifier 00000002-0000-0ff1-ce00-000000000000 -ApplicationTrustLevel Full -UseOAuthServer
    }
else
    {
       if ($exch.ApplicationIdentifier -ne "00000002-0000-0ff1-ce00-000000000000")
          {
             Remove-CsPartnerApplication microsoft.exchange
             New-CsPartnerApplication -Identity microsoft.exchange -ApplicationIdentifier 00000002-0000-0ff1-ce00-000000000000 -ApplicationTrustLevel Full -UseOAuthServer 
          }
       else
          {
             Set-CsPartnerApplication -Identity microsoft.exchange -ApplicationTrustLevel Full -UseOAuthServer
          }
   }

Set-CsOAuthConfiguration -ServiceName 00000004-0000-0ff1-ce00-000000000000
```

<span data-ttu-id="dcc10-p102">Beachten Sie, dass sich der Bereichsname für einen Mandanten normalerweise vom Namen der Organisation unterscheidet. Der Bereichsname entspricht stattdessen häufig der Mandanten-ID. Aus diesem Grund dient die erste Zeile des Skripts dazu, den Wert der TenantId-Eigenschaft für den angegebenen Mandanten zurückzugeben (in diesem Fall „fabrikam.com“) und den entsprechenden Namen anschließend der Variablen „$TenantId“ zuzuweisen:</span><span class="sxs-lookup"><span data-stu-id="dcc10-p102">Keep in mind that the realm name for a tenant is typically different than the organization name; in fact, the realm name is almost always the same as the tenant ID. Because of that, the first line in the script is used to return the value of the TenantId property for the specified tenant (in this case, fabrikam.com) and then assign that name to the variable $TenantId:</span></span>

```
$TenantID = (Get-CsTenant -Filter {DisplayName -eq "Fabrikam.com"}).TenantId
```

<span data-ttu-id="dcc10-110">Damit Sie dieses Skript ausführen können, müssen Sie das Skype for Business Online PowerShell-Modul installiert haben und mit diesem Modul eine Verbindung mit Ihrem Mandanten herstellen.</span><span class="sxs-lookup"><span data-stu-id="dcc10-110">To execute this script, you must have installed Skype for Business Online PowerShell module and connect to your tenant with this module.</span></span> <span data-ttu-id="dcc10-111">Wenn Sie diese Cmdlets nicht installiert haben, schlägt Ihr Skript fehl, weil das Get-CsTenant-Cmdlet nicht verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="dcc10-111">If you have not installed these cmdlets your script will fail because the Get-CsTenant cmdlet will not be available.</span></span> <span data-ttu-id="dcc10-112">Nachdem das Skript abgeschlossen ist, müssen Sie eine Vertrauensstellung zwischen Skype for Business Server und dem autorisierungsserver sowie eine zweite Vertrauensstellung zwischen Exchange 2013/2016 und dem autorisierungsserver konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="dcc10-112">After the script completes, you must then configure a trust relationship between Skype for Business Server and the authorization server, and a second trust relationship between Exchange 2013/2016 and the authorization server.</span></span> <span data-ttu-id="dcc10-113">Das ist nur mithilfe der Microsoft Online Services-Cmdlets möglich.</span><span class="sxs-lookup"><span data-stu-id="dcc10-113">This can only be done by using the Microsoft Online Services cmdlets.</span></span>

> [!NOTE]
> <span data-ttu-id="dcc10-114">Wenn Sie die Microsoft Online Services-Cmdlets noch nicht installiert haben, müssen Sie Sie im PowerShell-Repository mit dem Cmdlet `install-module MSOnline`installieren.</span><span class="sxs-lookup"><span data-stu-id="dcc10-114">If you have not installed the Microsoft Online Services cmdlets, you will need to install it from the PowerShell repository with the cmdlet `install-module MSOnline`.</span></span> <span data-ttu-id="dcc10-115">Detaillierte Informationen zum Installieren und Verwenden des Microsoft Online Services-Moduls finden Sie auf der Office 365-Website.</span><span class="sxs-lookup"><span data-stu-id="dcc10-115">Detailed information for installing and using the Microsoft Online Services Module can be found on the Office 365 web site.</span></span> <span data-ttu-id="dcc10-116">In diesen Anweisungen erfahren Sie auch, wie Sie das einmalige Anmelden, den Verbund und die Synchronisierung zwischen Office 365 und Active Directory konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="dcc10-116">These instructions will also tell you how to configure single sign-on, federation, and synchronization between Office 365 and Active Directory.</span></span> 



<span data-ttu-id="dcc10-117">Nachdem Sie Office 365 konfiguriert haben und nachdem Sie Office 365-Dienst Prinzipale für Skype for Business Server und Exchange 2013 erstellt haben, müssen Sie Ihre Anmeldeinformationen bei diesen Dienst Prinzipalen registrieren.</span><span class="sxs-lookup"><span data-stu-id="dcc10-117">After you have configured Office 365, and after you have created Office 365 service principals for Skype for Business Server and Exchange 2013, you will then need to register your credentials with these service principals.</span></span> <span data-ttu-id="dcc10-118">Um dies zu erreichen, müssen Sie zuerst ein X. 509-Base64-Zertifikat abrufen, das als. CER-Datei.</span><span class="sxs-lookup"><span data-stu-id="dcc10-118">In order to do this, you must first obtain an X.509 Base64 certificate saved as a .CER file.</span></span> <span data-ttu-id="dcc10-119">Dieses Zertifikat wird dann auf die Office 365-Dienst Prinzipale angewendet.</span><span class="sxs-lookup"><span data-stu-id="dcc10-119">This certificate will then be applied to the Office 365 service principals.</span></span>

<span data-ttu-id="dcc10-120">Wenn Sie das X. 509-Zertifikat erhalten haben, öffnen Sie die PowerShell-Konsole, und importieren Sie das Microsoft Online Windows PowerShell-Modul, das die Cmdlets enthält, die zum Verwalten von Dienst Prinzipalen verwendet werden können:</span><span class="sxs-lookup"><span data-stu-id="dcc10-120">When you have obtained the X.509 certificate, open PowerShell console and import the Microsoft Online Windows PowerShell module containing the cmdlets that can be used to manage service principals:</span></span>

```
Import-Module MSOnline
```

<span data-ttu-id="dcc10-121">Wenn das Modul importiert wurde, geben Sie den folgenden Befehl ein, und drücken Sie dann die EINGABETASTE, um eine Verbindung mit Office 365 herzustellen:</span><span class="sxs-lookup"><span data-stu-id="dcc10-121">When the module has been imported, type the following command and then press ENTER in order to connect to Office 365:</span></span>

```
Connect-MsolService
```

<span data-ttu-id="dcc10-122">Nach Drücken der EINGABETASTE wird ein Dialogfeld zur Eingabe Ihrer Anmeldeinformationen angezeigt.</span><span class="sxs-lookup"><span data-stu-id="dcc10-122">After you press ENTER, a credentials dialog box will appear.</span></span> <span data-ttu-id="dcc10-123">Geben Sie Ihren Office 365-Benutzernamen und das Kennwort in das Dialogfeld ein, und klicken Sie dann auf OK.</span><span class="sxs-lookup"><span data-stu-id="dcc10-123">Enter your Office 365 user name and password in the dialog box, and then click OK.</span></span>

<span data-ttu-id="dcc10-124">Sobald Sie mit Office 365 verbunden sind, können Sie den folgenden Befehl ausführen, um Informationen zu ihren Dienst Prinzipalen zurückzugeben:</span><span class="sxs-lookup"><span data-stu-id="dcc10-124">As soon as you are connected to Office 365, you can then run the following command in order to return information about your service principals:</span></span>

```
Get-MsolServicePrincipal
```

<span data-ttu-id="dcc10-125">Sie sollten ähnliche Informationen wie die folgenden für alle Ihre Dienstprinzipale erhalten:</span><span class="sxs-lookup"><span data-stu-id="dcc10-125">You should get back information similar to this for all your service principals:</span></span>

<pre>
ExtensionData        : System.Runtime.Serialization.ExtensionDataObject
AccountEnabled       : True
Addresses            : {}
AppPrincipalId       : 00000004-0000-0ff1-ce00-000000000000
DisplayName          : Skype for Business Server
ObjectId             : aada5fbd-c0ae-442a-8c0b-36fec40602e2
ServicePrincipalName : SkypeForBusinessServer/litwareinc.com
TrustedForDelegation : True
</pre>

<span data-ttu-id="dcc10-126">Der nächste Schritt besteht darin, das X.509-Zertifikat zu importieren, zu codieren und zuzuweisen.</span><span class="sxs-lookup"><span data-stu-id="dcc10-126">The next step is to import, encode, and assign the X.509 certificate.</span></span> <span data-ttu-id="dcc10-127">Verwenden Sie zum Importieren und Codieren des Zertifikats die folgenden Windows PowerShell-Befehle, wobei Sie sicherstellen möchten, dass der vollständige Dateipfad zu Ihrem. CER-Datei beim Aufrufen der Import-Methode:</span><span class="sxs-lookup"><span data-stu-id="dcc10-127">To import and encode the certificate, use the following Windows PowerShell commands, being sure to specify the complete file path to your .CER file when you call the Import method:</span></span>

```
$certificate = New-Object System.Security.Cryptography.X509Certificates.X509Certificate
$certificate.Import("C:\Certificates\Office365.cer")
$binaryValue = $certificate.GetRawCertData()
$credentialsValue = [System.Convert]::ToBase64String($binaryValue)
```

<span data-ttu-id="dcc10-128">Nachdem das Zertifikat importiert und codiert wurde, können Sie das Zertifikat ihren Office 365-Dienst Prinzipalen zuweisen.</span><span class="sxs-lookup"><span data-stu-id="dcc10-128">After the certificate has been imported and encoded, you can then assign the certificate to your Office 365 service principals.</span></span> <span data-ttu-id="dcc10-129">Verwenden Sie dazu zunächst die Get-MsolServicePrincipal-Eigenschaft, um den Wert der AppPrincipalId-Eigenschaft sowohl für den Skype for Business-Server als auch für die Microsoft Exchange-Dienst Prinzipale abzurufen. der Wert der AppPrincipalId-Eigenschaft wird verwendet, um den Dienstprinzipal zu identifizieren, dem das Zertifikat zugewiesen wird.</span><span class="sxs-lookup"><span data-stu-id="dcc10-129">To do that, first use the Get-MsolServicePrincipal to retrieve the value of the AppPrincipalId property for both the Skype for Business Server and the Microsoft Exchange service principals; the value of the AppPrincipalId property will be used to identify the service principal being assigned the certificate.</span></span> <span data-ttu-id="dcc10-130">Wenn der Wert der AppPrincipalId-Eigenschaft für Skype for Business Server in der Hand ist, verwenden Sie den folgenden Befehl, um das Zertifikat der Skype for Business Online-Version zuzuweisen:</span><span class="sxs-lookup"><span data-stu-id="dcc10-130">With the AppPrincipalId property value for Skype for Business Server in hand, use the following command to assign the certificate to Skype For Business Online version:</span></span>

```
New-MsolServicePrincipalCredential -AppPrincipalId 00000004-0000-0ff1-ce00-000000000000 -Type Asymmetric -Usage Verify -Value $credentialsValue 
```

<span data-ttu-id="dcc10-131">Sie sollten diesen Befehl dann wiederholen, indem Sie dieses Mal den AppPrincipalId-Eigenschaftswert für Exchange 2013 verwenden.</span><span class="sxs-lookup"><span data-stu-id="dcc10-131">You should then repeat the command, this time using the AppPrincipalId property value for Exchange 2013.</span></span>

<span data-ttu-id="dcc10-132">Wenn Sie dieses Zertifikat später löschen müssen, beispielsweise wenn es abgelaufen ist, können Sie dies tun, indem Sie zunächst den KeyId für das Zertifikat abrufen:</span><span class="sxs-lookup"><span data-stu-id="dcc10-132">If you later need to delete that certificate, for example if it has expired, you can do so by first retrieving the KeyId for the certificate:</span></span>

```
Get-MsolServicePrincipalCredential -AppPrincipalId 00000004-0000-0ff1-ce00-000000000000
```

<span data-ttu-id="dcc10-133">Der entsprechende Befehl gibt in etwa folgende Daten zurück:</span><span class="sxs-lookup"><span data-stu-id="dcc10-133">That command will return data like this one:</span></span>

<pre>
Type      : Asymmetric
Value     : 
KeyId     : bc2795f3-2387-4543-a95d-f92c85c7a1b0
StartDate : 6/1/2012 8:00:00 AM
EndDate   : 5/31/2013 8:00:00 AM
Usage     : Verify
</pre>

<span data-ttu-id="dcc10-134">Sie können das Zertifikat mit einem ähnlichen Befehl wie diesem löschen:</span><span class="sxs-lookup"><span data-stu-id="dcc10-134">You can then delete the certificate by using a command similar to this:</span></span>

```
Remove-MsolServicePrincipalCredential -AppPrincipalId 00000004-0000-0ff1-ce00-000000000000 -KeyId bc2795f3-2387-4543-a95d-f92c85c7a1b0
```

<span data-ttu-id="dcc10-135">Neben dem Zuweisen eines Zertifikats müssen Sie auch den Exchange Online-Dienstprinzipal konfigurieren und die lokale Version der externen Skype for Business Server-URLs als Office 365-Dienstprinzipal konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="dcc10-135">In addition to assigning a certificate, you must also configure the Exchange Online Service Principal and configure your on-premises version of Skype for Business Server external Web services URLs as an Office 365 service principal.</span></span> <span data-ttu-id="dcc10-136">Dies kann durch Ausführen der folgenden beiden Befehle erfolgen.</span><span class="sxs-lookup"><span data-stu-id="dcc10-136">That can be done by carrying out the following two commands.</span></span> 

<span data-ttu-id="dcc10-137">Im folgenden Beispiel ist Pool1ExternalWebFQDN.contoso.com die externe Webdienste-URL für den Skype for Business-Server Pool.</span><span class="sxs-lookup"><span data-stu-id="dcc10-137">In the following example, Pool1ExternalWebFQDN.contoso.com is the external Web services URL for the Skype for Business Server pool.</span></span> <span data-ttu-id="dcc10-138">Wiederholen Sie diese Schritte, um alle externen Webdienste-URLs in der Bereitstellung hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="dcc10-138">You should repeat these steps to add all the external Web services URLs in the deployment.</span></span>

```
Set-MSOLServicePrincipal -AppPrincipalID 00000002-0000-0ff1-ce00-000000000000 -AccountEnabled $true
$lyncSP = Get-MSOLServicePrincipal -AppPrincipalID 00000004-0000-0ff1-ce00-000000000000
$lyncSP.ServicePrincipalNames.Add("00000004-0000-0ff1-ce00-000000000000/Pool1ExternalWebFQDN.contoso.com")
Set-MSOLServicePrincipal -AppPrincipalID 00000004-0000-0ff1-ce00-000000000000 -ServicePrincipalNames $lyncSP.ServicePrincipalNames
```
