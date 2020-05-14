---
title: Konfigurieren der Server-zu-Server-Authentifizierung für eine Skype for Business Server Hybridumgebung
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 700639ec-5264-4449-a8a6-d7386fad8719
description: 'Zusammenfassung: Konfigurieren der Server-zu-Server-Authentifizierung für eine Skype for Business Server Hybridumgebung.'
ms.openlocfilehash: 6cc408677af4629d36b577da4ae38cd420195483
ms.sourcegitcommit: d69bad69ba9a9bca4614d72d8f34fb2a0a9e4dc4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/13/2020
ms.locfileid: "44221679"
---
# <a name="configure-server-to-server-authentication-for-a-skype-for-business-server-hybrid-environment"></a><span data-ttu-id="20f18-103">Konfigurieren Sie die Server-zu-Server-Authentifizierung für eine Skype for Business Server Hybridumgebung.</span><span class="sxs-lookup"><span data-stu-id="20f18-103">Configure server-to-server authentication for a Skype for Business Server hybrid environment.</span></span>

<span data-ttu-id="20f18-104">**Zusammenfassung:** Konfigurieren Sie die Server-zu-Server-Authentifizierung für Skype for Business Server Hybridumgebung.</span><span class="sxs-lookup"><span data-stu-id="20f18-104">**Summary:** Configure server-to-server authentication for Skype for Business Server hybrid environment.</span></span>

<span data-ttu-id="20f18-105">In einer Hybrid Konfiguration werden einige Ihrer Benutzer in einer lokalen Installation von Skype for Business Server verwaltet, während andere Benutzer in der Microsoft 365-oder Office 365-Version von Skype for Business Server verwaltet werden.</span><span class="sxs-lookup"><span data-stu-id="20f18-105">In a hybrid configuration, some of your users are homed on an on-premises installation of Skype for Business Server while other users are homed on the Microsoft 365 or Office 365 version of Skype for Business Server.</span></span> <span data-ttu-id="20f18-106">Um die Server-zu-Server-Authentifizierung in einer Hybridumgebung konfigurieren zu können, müssen Sie zunächst Ihre lokale Installation von Skype for Business Server so konfigurieren, dass Sie dem autorisierungsserver vertraut.</span><span class="sxs-lookup"><span data-stu-id="20f18-106">In order to configure server-to-server authentication in a hybrid environment, you must first configure your on-premises installation of Skype for Business Server to trust the authorization server.</span></span> <span data-ttu-id="20f18-107">Der erste Schritt in diesem Prozess kann ausgeführt werden, indem Sie das folgende Skype for Business Server-Verwaltungsshell-Skript ausführen:</span><span class="sxs-lookup"><span data-stu-id="20f18-107">The initial step in this process can be carried out by running the following Skype for Business Server Management Shell script:</span></span>

```PowerShell
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

<span data-ttu-id="20f18-108">Beachten Sie, dass der Bereichsname für einen Mandanten in der Regel nicht mit dem Namen der Organisation identisch ist. Tatsächlich ist der Bereichsname fast immer identisch mit der Mandanten-ID.</span><span class="sxs-lookup"><span data-stu-id="20f18-108">Keep in mind that the realm name for a tenant is typically different than the organization name; in fact, the realm name is almost always the same as the tenant ID.</span></span> <span data-ttu-id="20f18-109">Aus diesem Grund wird die erste Codezeile im Skript verwendet, um den Wert der Mandanten-Eigenschaft für den angegebenen Mandanten (in diesem Fall fabrikam.com) zurückzugeben und diesen Namen dann der Variablen $TenantId zuzuweisen:</span><span class="sxs-lookup"><span data-stu-id="20f18-109">Because of that, the first line in the script is used to return the value of the TenantId property for the specified tenant (in this case, fabrikam.com) and then assign that name to the variable $TenantId:</span></span>

```PowerShell
$TenantID = (Get-CsTenant -Filter {DisplayName -eq "Fabrikam.com"}).TenantId
```

<span data-ttu-id="20f18-110">Um dieses Skript auszuführen, müssen Sie Skype for Business Online PowerShell-Modul installiert haben und mit diesem Modul eine Verbindung mit Ihrem Mandanten herstellen.</span><span class="sxs-lookup"><span data-stu-id="20f18-110">To execute this script, you must have installed Skype for Business Online PowerShell module and connect to your tenant with this module.</span></span> <span data-ttu-id="20f18-111">Wenn Sie diese Cmdlets nicht installiert haben, tritt beim Skript ein Fehler auf, da das Cmdlet Get-CsTenant nicht verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="20f18-111">If you have not installed these cmdlets your script will fail because the Get-CsTenant cmdlet will not be available.</span></span> <span data-ttu-id="20f18-112">Nachdem das Skript abgeschlossen ist, müssen Sie eine Vertrauensstellung zwischen Skype for Business Server und dem autorisierungsserver und eine zweite Vertrauensstellung zwischen Exchange 2013/2016 und dem autorisierungsserver konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="20f18-112">After the script completes, you must then configure a trust relationship between Skype for Business Server and the authorization server, and a second trust relationship between Exchange 2013/2016 and the authorization server.</span></span> <span data-ttu-id="20f18-113">Dies kann nur mithilfe der Microsoft Online Services-Cmdlets erfolgen.</span><span class="sxs-lookup"><span data-stu-id="20f18-113">This can only be done by using the Microsoft Online Services cmdlets.</span></span>

> [!NOTE]
> <span data-ttu-id="20f18-114">Wenn Sie die Microsoft Online Services-Cmdlets nicht installiert haben, müssen Sie Sie mit dem Cmdlet aus dem PowerShell-Repository installieren `install-module MSOnline` .</span><span class="sxs-lookup"><span data-stu-id="20f18-114">If you have not installed the Microsoft Online Services cmdlets, you will need to install it from the PowerShell repository with the cmdlet `install-module MSOnline`.</span></span> <span data-ttu-id="20f18-115">Ausführliche Informationen zum Installieren und Verwenden des Microsoft Online Services-Modul finden Sie auf der Microsoft 365-Website.</span><span class="sxs-lookup"><span data-stu-id="20f18-115">Detailed information for installing and using the Microsoft Online Services Module can be found on the Microsoft 365 web site.</span></span> <span data-ttu-id="20f18-116">In diesen Anweisungen erfahren Sie außerdem, wie Sie einmaliges Anmelden, Partnerverbund und Synchronisierung zwischen Microsoft 365 oder Office 365 und Active Directory konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="20f18-116">These instructions will also tell you how to configure single sign-on, federation, and synchronization between Microsoft 365 or Office 365 and Active Directory.</span></span> 



<span data-ttu-id="20f18-117">Nachdem Sie Microsoft 365 oder Office 365 konfiguriert und Microsoft 365 oder Office 365 Dienst Prinzipale für Skype for Business Server und Exchange 2013 erstellt haben, müssen Sie Ihre Anmeldeinformationen bei diesen Dienst Prinzipalen registrieren.</span><span class="sxs-lookup"><span data-stu-id="20f18-117">After you have configured Microsoft 365 or Office 365, and after you have created Microsoft 365 or Office 365 service principals for Skype for Business Server and Exchange 2013, you will then need to register your credentials with these service principals.</span></span> <span data-ttu-id="20f18-118">Um dies zu erreichen, müssen Sie zunächst ein X. 509 Base64-Zertifikat erhalten, das als gespeichert wurde. CER-Datei.</span><span class="sxs-lookup"><span data-stu-id="20f18-118">In order to do this, you must first obtain an X.509 Base64 certificate saved as a .CER file.</span></span> <span data-ttu-id="20f18-119">Dieses Zertifikat wird dann auf die Microsoft 365-oder Office 365-Dienst Prinzipale angewendet.</span><span class="sxs-lookup"><span data-stu-id="20f18-119">This certificate will then be applied to the Microsoft 365 or Office 365 service principals.</span></span>

<span data-ttu-id="20f18-120">Wenn Sie das X. 509-Zertifikat erhalten haben, öffnen Sie die PowerShell-Konsole, und importieren Sie das Microsoft Online Windows PowerShell-Modul, das die Cmdlets enthält, die zum Verwalten von Dienst Prinzipalen verwendet werden können:</span><span class="sxs-lookup"><span data-stu-id="20f18-120">When you have obtained the X.509 certificate, open PowerShell console and import the Microsoft Online Windows PowerShell module containing the cmdlets that can be used to manage service principals:</span></span>

```PowerShell
Import-Module MSOnline
```

<span data-ttu-id="20f18-121">Wenn das Modul importiert wurde, geben Sie den folgenden Befehl ein, und drücken Sie dann die EINGABETASTE:</span><span class="sxs-lookup"><span data-stu-id="20f18-121">When the module has been imported, type the following command and then press ENTER:</span></span>

```PowerShell
Connect-MsolService
```

<span data-ttu-id="20f18-122">Nachdem Sie die EINGABETASTE gedrückt haben, wird ein Dialogfeld Anmeldeinformationen angezeigt.</span><span class="sxs-lookup"><span data-stu-id="20f18-122">After you press ENTER, a credentials dialog box will appear.</span></span> <span data-ttu-id="20f18-123">Geben Sie im Dialogfeld Ihren Microsoft 365-oder Office 365-Benutzernamen und das Kennwort ein, und klicken Sie dann auf OK.</span><span class="sxs-lookup"><span data-stu-id="20f18-123">Enter your Microsoft 365 or Office 365 user name and password in the dialog box, and then click OK.</span></span>

<span data-ttu-id="20f18-124">Sobald Sie eine Verbindung mit Microsoft 365 oder Office 365 hergestellt haben, können Sie den folgenden Befehl ausführen, um Informationen zu ihren Dienst Prinzipalen zurückzugeben:</span><span class="sxs-lookup"><span data-stu-id="20f18-124">As soon as you are connected to Microsoft 365 or Office 365, you can then run the following command in order to return information about your service principals:</span></span>

```PowerShell
Get-MsolServicePrincipal
```

<span data-ttu-id="20f18-125">Sie sollten für alle Dienst Prinzipale Informationen zurück erhalten, die diesem ähneln:</span><span class="sxs-lookup"><span data-stu-id="20f18-125">You should get back information similar to this for all your service principals:</span></span>

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

<span data-ttu-id="20f18-126">Der nächste Schritt besteht darin, das X. 509-Zertifikat zu importieren, zu codieren und zuzuweisen.</span><span class="sxs-lookup"><span data-stu-id="20f18-126">The next step is to import, encode, and assign the X.509 certificate.</span></span> <span data-ttu-id="20f18-127">Um das Zertifikat zu importieren und zu codieren, verwenden Sie die folgenden Windows PowerShell Befehle, wobei Sie sicherstellen möchten, dass der vollständige Dateipfad angegeben wird. CER-Datei, wenn Sie die Import-Methode aufrufen:</span><span class="sxs-lookup"><span data-stu-id="20f18-127">To import and encode the certificate, use the following Windows PowerShell commands, being sure to specify the complete file path to your .CER file when you call the Import method:</span></span>

```PowerShell
$certificate = New-Object System.Security.Cryptography.X509Certificates.X509Certificate
$certificate.Import("C:\Certificates\Office365.cer")
$binaryValue = $certificate.GetRawCertData()
$credentialsValue = [System.Convert]::ToBase64String($binaryValue) 
```

<span data-ttu-id="20f18-128">Nachdem das Zertifikat importiert und codiert wurde, können Sie das Zertifikat Ihren Microsoft 365-oder Office 365-Dienst Prinzipalen zuweisen.</span><span class="sxs-lookup"><span data-stu-id="20f18-128">After the certificate has been imported and encoded, you can then assign the certificate to your Microsoft 365 or Office 365 service principals.</span></span> <span data-ttu-id="20f18-129">Verwenden Sie dazu zunächst das Get-MsolServicePrincipal, um den Wert der AppPrincipalId-Eigenschaft sowohl für die Skype for Business Server als auch für die Microsoft Exchange Dienst Prinzipale abzurufen; der Wert der AppPrincipalId-Eigenschaft wird verwendet, um den Dienstprinzipal zu identifizieren, dem das Zertifikat zugewiesen wurde.</span><span class="sxs-lookup"><span data-stu-id="20f18-129">To do that, first use the Get-MsolServicePrincipal to retrieve the value of the AppPrincipalId property for both the Skype for Business Server and the Microsoft Exchange service principals; the value of the AppPrincipalId property will be used to identify the service principal being assigned the certificate.</span></span> <span data-ttu-id="20f18-130">Wenn der Wert der AppPrincipalId-Eigenschaft für Skype for Business Server in Hand ist, verwenden Sie den folgenden Befehl, um das Zertifikat der Skype for Business Online-Version zuzuweisen:</span><span class="sxs-lookup"><span data-stu-id="20f18-130">With the AppPrincipalId property value for Skype for Business Server in hand, use the following command to assign the certificate to Skype For Business Online version:</span></span>

```PowerShell
New-MsolServicePrincipalCredential -AppPrincipalId 00000004-0000-0ff1-ce00-000000000000 -Type Asymmetric -Usage Verify -Value $credentialsValue 
```

<span data-ttu-id="20f18-131">Sie sollten dann den Befehl wiederholen, diesmal mit dem AppPrincipalId-Eigenschaftswert für Exchange 2013.</span><span class="sxs-lookup"><span data-stu-id="20f18-131">You should then repeat the command, this time using the AppPrincipalId property value for Exchange 2013.</span></span>

<span data-ttu-id="20f18-132">Wenn Sie dieses Zertifikat später löschen müssen, beispielsweise wenn es abgelaufen ist, können Sie dies tun, indem Sie zunächst die KeyId für das Zertifikat abrufen:</span><span class="sxs-lookup"><span data-stu-id="20f18-132">If you later need to delete that certificate, for example if it has expired, you can do so by first retrieving the KeyId for the certificate:</span></span>

```PowerShell
Get-MsolServicePrincipalCredential -AppPrincipalId 00000004-0000-0ff1-ce00-000000000000
```

<span data-ttu-id="20f18-133">Dieser Befehl gibt Daten wie diese zurück:</span><span class="sxs-lookup"><span data-stu-id="20f18-133">That command will return data like this one:</span></span>

<pre>
Type      : Asymmetric
Value     : 
KeyId     : bc2795f3-2387-4543-a95d-f92c85c7a1b0
StartDate : 6/1/2012 8:00:00 AM
EndDate   : 5/31/2013 8:00:00 AM
Usage     : Verify
</pre>

<span data-ttu-id="20f18-134">Anschließend können Sie das Zertifikat mit einem Befehl wie dem folgenden löschen:</span><span class="sxs-lookup"><span data-stu-id="20f18-134">You can then delete the certificate by using a command similar to this:</span></span>

```PowerShell
Remove-MsolServicePrincipalCredential -AppPrincipalId 00000004-0000-0ff1-ce00-000000000000 -KeyId bc2795f3-2387-4543-a95d-f92c85c7a1b0
```

<span data-ttu-id="20f18-135">Neben dem Zuweisen eines Zertifikats müssen Sie auch den Exchange Online Dienstprinzipal konfigurieren und die lokale Version Skype for Business Server externer Webdienst-URLs als Microsoft 365 oder Office 365 Dienstprinzipal konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="20f18-135">In addition to assigning a certificate, you must also configure the Exchange Online Service Principal and configure your on-premises version of Skype for Business Server external Web services URLs as a Microsoft 365 or Office 365 service principal.</span></span> <span data-ttu-id="20f18-136">Dies kann durch Ausführen der folgenden beiden Befehle erfolgen.</span><span class="sxs-lookup"><span data-stu-id="20f18-136">That can be done by carrying out the following two commands.</span></span> 

<span data-ttu-id="20f18-137">Im folgenden Beispiel ist Pool1ExternalWebFQDN.contoso.com die externe Webdienste-URL für den Skype for Business Server Pool.</span><span class="sxs-lookup"><span data-stu-id="20f18-137">In the following example, Pool1ExternalWebFQDN.contoso.com is the external Web services URL for the Skype for Business Server pool.</span></span> <span data-ttu-id="20f18-138">Wiederholen Sie diese Schritte, um alle externen Webdienste-URLs in der Bereitstellung hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="20f18-138">You should repeat these steps to add all the external Web services URLs in the deployment.</span></span>

```PowerShell
Set-MSOLServicePrincipal -AppPrincipalID 00000002-0000-0ff1-ce00-000000000000 -AccountEnabled $true
$lyncSP = Get-MSOLServicePrincipal -AppPrincipalID 00000004-0000-0ff1-ce00-000000000000
$lyncSP.ServicePrincipalNames.Add("00000004-0000-0ff1-ce00-000000000000/Pool1ExternalWebFQDN.contoso.com")
Set-MSOLServicePrincipal -AppPrincipalID 00000004-0000-0ff1-ce00-000000000000 -ServicePrincipalNames $lyncSP.ServicePrincipalNames
```
