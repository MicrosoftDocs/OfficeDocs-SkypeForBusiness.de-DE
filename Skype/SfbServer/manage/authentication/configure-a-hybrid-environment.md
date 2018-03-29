---
title: Konfigurieren einer Hybridumgebung in Skype for Business Server 2015
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.date: 1/31/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 700639ec-5264-4449-a8a6-d7386fad8719
description: 'Zusammenfassung: Konfigurieren von Skype für Business Server 2015 in einer hybridumgebung.'
ms.openlocfilehash: e31338647338854b260c9f8935cac4dde69df490
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/28/2018
---
# <a name="configure-a-hybrid-environment-in-skype-for-business-server-2015"></a><span data-ttu-id="fe7b2-103">Konfigurieren einer Hybridumgebung in Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="fe7b2-103">Configure a hybrid environment in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="fe7b2-104">**Zusammenfassung:** Konfigurieren von Skype für Business Server 2015 in einer hybridumgebung.</span><span class="sxs-lookup"><span data-stu-id="fe7b2-104">**Summary:** Configure Skype for Business Server 2015 in a hybrid environment.</span></span>
  
<span data-ttu-id="fe7b2-105">In einer hybridkonfiguration sind einige Ihrer Benutzer, die sich in einer lokalen Installation von Skype für Business Server 2015, während andere Benutzer auf der Office 365-Version von Skype für Business Server verwaltet werden.</span><span class="sxs-lookup"><span data-stu-id="fe7b2-105">In a hybrid configuration, some of your users are homed on an on-premises installation of Skype for Business Server 2015 while other users are homed on the Office 365 version of Skype for Business Server.</span></span> <span data-ttu-id="fe7b2-106">Um die Server-zu-Server-Authentifizierung in einer hybridumgebung konfigurieren, müssen Sie zuerst Ihrer lokalen Installation von Skype für Business Server 2015 Vertrauenswürdigkeit des Office 365-Autorisierung-Servers konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="fe7b2-106">In order to configure server-to-server authentication in a hybrid environment, you must first configure your on-premises installation of Skype for Business Server 2015 to trust the Office 365 authorization server.</span></span> <span data-ttu-id="fe7b2-107">Der erste Schritt in diesem Prozess kann durch Ausführen der folgenden Skype für Business Server-Verwaltungsshell-Skripts durchgeführt werden:</span><span class="sxs-lookup"><span data-stu-id="fe7b2-107">The initial step in this process can be carried out by running the following Skype for Business Server Management Shell script:</span></span>
  
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

<span data-ttu-id="fe7b2-p102">Beachten Sie, dass sich der Bereichsname für einen Mandanten normalerweise vom Namen der Organisation unterscheidet. Der Bereichsname entspricht stattdessen häufig der Mandanten-ID. Aus diesem Grund dient die erste Zeile des Skripts dazu, den Wert der TenantId-Eigenschaft für den angegebenen Mandanten zurückzugeben (in diesem Fall „fabrikam.com“) und den entsprechenden Namen anschließend der Variablen „$TenantId“ zuzuweisen:</span><span class="sxs-lookup"><span data-stu-id="fe7b2-p102">Keep in mind that the realm name for a tenant is typically different than the organization name; in fact, the realm name is almost always the same as the tenant ID. Because of that, the first line in the script is used to return the value of the TenantId property for the specified tenant (in this case, fabrikam.com) and then assign that name to the variable $TenantId:</span></span>
  
```
$TenantID = (Get-CsTenant -DisplayName "Fabrikam.com").TenantId
```

<span data-ttu-id="fe7b2-110">Nach Abschluss des Skripts müssen Sie dann eine Vertrauensstellung zwischen Skype für Business Server 2015 und den autorisierungsserver und eine zweite Vertrauensstellung zwischen Exchange 2013 und den autorisierungsserver konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="fe7b2-110">After the script completes, you must then configure a trust relationship between Skype for Business Server 2015 and the authorization server, and a second trust relationship between Exchange 2013 and the authorization server.</span></span> <span data-ttu-id="fe7b2-111">Das ist nur mithilfe der Microsoft Online Services-Cmdlets möglich.</span><span class="sxs-lookup"><span data-stu-id="fe7b2-111">This can only be done by using the Microsoft Online Services cmdlets.</span></span>
  
> [!NOTE]
> <span data-ttu-id="fe7b2-112">Falls Sie die Microsoft Online Services-Cmdlets nicht installiert haben, müssen Sie zunächst zwei Dinge erledigen, bevor Sie fortfahren.</span><span class="sxs-lookup"><span data-stu-id="fe7b2-112">If you have not installed the Microsoft Online Services cmdlets, you will need to do two things before proceeding.</span></span> <span data-ttu-id="fe7b2-113">Laden Sie die 64-Bit-Version des Microsoft Online Services-Anmeldeassistenten herunter, und installieren Sie sie.</span><span class="sxs-lookup"><span data-stu-id="fe7b2-113">First, download and install the 64-bit version of the Microsoft Online Services Sign-in Assistant.</span></span> <span data-ttu-id="fe7b2-114">Nach Abschluss der Installation herunterladen und Installieren der 64-Bit-Version von der Microsoft Online Services-Modul für Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="fe7b2-114">After installation is complete, download and install the 64-bit version of the Microsoft Online Services Module for Windows PowerShell.</span></span> <span data-ttu-id="fe7b2-115">Ausführliche Informationen zum Installieren und Verwenden der Microsoft Online Services-Modul finden Sie auf der Office 365-Website.</span><span class="sxs-lookup"><span data-stu-id="fe7b2-115">Detailed information for installing and using the Microsoft Online Services Module can be found on the Office 365 web site.</span></span> <span data-ttu-id="fe7b2-116">Diese Anweisungen auch informiert Sie, wie Sie einmaliges Anmelden, Verbund und die Synchronisierung zwischen dem Office 365 und Active Directory konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="fe7b2-116">These instructions will also tell you how to configure single sign-on, federation, and synchronization between Office 365 and Active Directory.</span></span> 
  
<span data-ttu-id="fe7b2-117">Wenn Sie diese Cmdlets nicht installiert haben, schlägt Ihr Skript fehl, weil das Get-CsTenant-Cmdlet nicht verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="fe7b2-117">If you have not installed these cmdlets your script will fail because the Get-CsTenant cmdlet will not be available.</span></span>
  
<span data-ttu-id="fe7b2-118">Nachdem Sie Office 365 konfiguriert haben, und Sie Office 365-Dienstprinzipale für Skype für Business Server 2015 und Exchange 2013 erstellt haben, müssen Sie dann Ihre Anmeldeinformationen mit diesen dienstprinzipalen zu registrieren.</span><span class="sxs-lookup"><span data-stu-id="fe7b2-118">After you have configured Office 365, and after you have created Office 365 service principals for Skype for Business Server 2015 and Exchange 2013, you will then need to register your credentials with these service principals.</span></span> <span data-ttu-id="fe7b2-119">Zu diesem Zweck müssen Sie zunächst ein Base64-kodiertes X.509-Zertifikat anfordern, das als CER-Datei gespeichert wird.</span><span class="sxs-lookup"><span data-stu-id="fe7b2-119">In order to do this, you must first obtain an X.509 Base64 saved as a .CER file.</span></span> <span data-ttu-id="fe7b2-120">Dieses Zertifikat wird dann auf die Office 365-Dienst-Prinzipale angewendet werden.</span><span class="sxs-lookup"><span data-stu-id="fe7b2-120">This certificate will then be applied to the Office 365 service principals.</span></span>
  
<span data-ttu-id="fe7b2-121">Wenn Sie das x. 509-Zertifikat abgerufen haben, starten Sie den Microsoft Online Services-Modul (klicken Sie auf **Start**, klicken Sie auf **Alle Programme**, klicken Sie auf **Microsoft Online Services**, und klicken Sie dann auf **Microsoft Online Services-Modul für Windows PowerShell**).</span><span class="sxs-lookup"><span data-stu-id="fe7b2-121">When you have obtained the X.509 certificate, start the Microsoft Online Services Module (click **Start**, click **All Programs**, click **Microsoft Online Services**, and then click **Microsoft Online Services Module for Windows PowerShell**).</span></span> <span data-ttu-id="fe7b2-122">Nachdem das Modul Dienste geöffnet wurde, geben Sie den folgenden zum Importieren des Microsoft Online Windows PowerShell-Moduls mit den Cmdlets, die zum Verwalten von Dienstprinzipale verwendet werden können:</span><span class="sxs-lookup"><span data-stu-id="fe7b2-122">After the Services Module opens, type the following to import the Microsoft Online Windows PowerShell module containing the cmdlets that can be used to manage service principals:</span></span>
  
```
Import-Module MSOnlineExtended
```

<span data-ttu-id="fe7b2-123">Wenn das Modul importiert wurde, geben Sie den folgenden Befehl ein, und drücken Sie die EINGABETASTE, um zu Office 365 zu verbinden:</span><span class="sxs-lookup"><span data-stu-id="fe7b2-123">When the module has been imported, type the following command and then press ENTER in order to connect to Office 365:</span></span>
  
```
Connect-MsolService
```

<span data-ttu-id="fe7b2-124">Nach Drücken der EINGABETASTE wird ein Dialogfeld zur Eingabe Ihrer Anmeldeinformationen angezeigt.</span><span class="sxs-lookup"><span data-stu-id="fe7b2-124">After you press ENTER, a credentials dialog box will appear.</span></span> <span data-ttu-id="fe7b2-125">Geben Sie im Dialogfeld Ihre Office 365-Benutzernamen und das Kennwort ein, und klicken Sie dann auf OK.</span><span class="sxs-lookup"><span data-stu-id="fe7b2-125">Enter your Office 365 user name and password in the dialog box, and then click OK.</span></span>
  
<span data-ttu-id="fe7b2-126">Sobald Sie zu Office 365 verbunden sind, können Sie den folgenden Befehl, um die Rückgabe von Informationen über Ihre Dienstprinzipale ausführen:</span><span class="sxs-lookup"><span data-stu-id="fe7b2-126">As soon as you are connected to Office 365, you can then run the following command in order to return information about your service principals:</span></span>
  
```
Get-MsolServicePrincipal
```

<span data-ttu-id="fe7b2-127">Sie sollten ähnliche Informationen wie die folgenden für alle Ihre Dienstprinzipale erhalten:</span><span class="sxs-lookup"><span data-stu-id="fe7b2-127">You should get back information similar to this for all your service principals:</span></span>
  
```
ExtensionData        : System.Runtime.Serialization.ExtensionDataObject
AccountEnabled       : True
Addresses            : {}
AppPrincipalId       : 00000004-0000-0ff1-ce00-000000000000
DisplayName          : Skype for Business Server
ObjectId             : aada5fbd-c0ae-442a-8c0b-36fec40602e2
ServicePrincipalName : SkypeForBusinessServer/litwareinc.com
TrustedForDelegation : True
```

<span data-ttu-id="fe7b2-128">Der nächste Schritt besteht darin, das X.509-Zertifikat zu importieren, zu codieren und zuzuweisen.</span><span class="sxs-lookup"><span data-stu-id="fe7b2-128">The next step is to import, encode, and assign the X.509 certificate.</span></span> <span data-ttu-id="fe7b2-129">Zum Importieren und das Zertifikat zu codieren, verwenden Sie die folgenden Windows PowerShell-Befehle, wird den vollständige Pfad zum Angeben der. CER-Datei beim Aufrufen der Import-Methode:</span><span class="sxs-lookup"><span data-stu-id="fe7b2-129">To import and encode the certificate, use the following Windows PowerShell commands, being sure to specify the complete file path to your .CER file when you call the Import method:</span></span>
  
```
$certificate = New-Object System.Security.Cryptography.X509Certificates.X509Certificate
$certificate.Import("C:\Certificates\Office365.cer")
$binaryValue = $certificate.GetRawCertData()
$credentialsValue = [System.Convert]::ToBase64String($binaryValue)
```

<span data-ttu-id="fe7b2-130">Nachdem das Zertifikat importiert und codiert wurde, können Sie dann das Zertifikat für Ihre Office 365-Dienstprinzipale zuweisen.</span><span class="sxs-lookup"><span data-stu-id="fe7b2-130">After the certificate has been imported and encoded, you can then assign the certificate to your Office 365 service principals.</span></span> <span data-ttu-id="fe7b2-131">Klicken Sie dazu zunächst mit dem das Get-MsolServicePrincipal zum Abrufen des Werts der AppPrincipalId-Eigenschaft für die Skype für Business Server und die Microsoft Exchange-Dienst-Prinzipale; der Wert der AppPrincipalId-Eigenschaft wird verwendet werden, um den Dienstprinzipal zugewiesen wird, das Zertifikat zu identifizieren.</span><span class="sxs-lookup"><span data-stu-id="fe7b2-131">To do that, first use the Get-MsolServicePrincipal to retrieve the value of the AppPrincipalId property for both the Skype for Business Server and the Microsoft Exchange service principals; the value of the AppPrincipalId property will be used to identify the service principal being assigned the certificate.</span></span> <span data-ttu-id="fe7b2-132">Mit der AppPrincipalId-Eigenschaft Wert für Skype für Business Server 2015 Umwelt; verwenden den folgenden Befehl, um das Zertifikat für die Office 365-Version von Skype für Business Server zuzuweisen:</span><span class="sxs-lookup"><span data-stu-id="fe7b2-132">With the AppPrincipalId property value for Skype for Business Server 2015 in hand, use the following command to assign the certificate to the Office 365 version of Skype for Business Server:</span></span>
  
```
New-MsolServicePrincipalCredential -AppPrincipalId 00000004-0000-0ff1-ce00-000000000000 -Type Asymmetric -Usage Verify -Value $credentialsValue 
```

<span data-ttu-id="fe7b2-133">Sie sollten den Befehl dann diesmal den AppPrincipalId-Eigenschaftswert für Exchange 2013 mit wiederholen.</span><span class="sxs-lookup"><span data-stu-id="fe7b2-133">You should then repeat the command, this time using the AppPrincipalId property value for Exchange 2013.</span></span>
  
<span data-ttu-id="fe7b2-134">Falls Sie das Zertifikat zu einem späteren Zeitpunkt löschen müssen, rufen Sie dazu zunächst die KeyID für das Zertifikat ab:</span><span class="sxs-lookup"><span data-stu-id="fe7b2-134">If you later need to delete that certificate, you can do so by first retrieving the KeyId for the certificate:</span></span>
  
```
Get-MsolServicePrincipalCredential -AppPrincipalId 00000004-0000-0ff1-ce00-000000000000
```

<span data-ttu-id="fe7b2-135">Der entsprechende Befehl gibt in etwa folgende Daten zurück:</span><span class="sxs-lookup"><span data-stu-id="fe7b2-135">That command will return data like this one:</span></span>
  
```
Type      : Asymmetric
Value     : 
KeyId     : bc2795f3-2387-4543-a95d-f92c85c7a1b0
StartDate : 6/1/2012 8:00:00 AM
EndDate   : 5/31/2013 8:00:00 AM
Usage     : Verify
```

<span data-ttu-id="fe7b2-136">Sie können das Zertifikat mit einem ähnlichen Befehl wie diesem löschen:</span><span class="sxs-lookup"><span data-stu-id="fe7b2-136">You can then delete the certificate by using a command similar to this:</span></span>
  
```
Remove-MsolServicePrincipalCredential -AppPrincipalId 00000004-0000-0ff1-ce00-000000000000 -KeyId bc2795f3-2387-4543-a95d-f92c85c7a1b0
```

<span data-ttu-id="fe7b2-137">Zusätzlich zum Zuweisen eines Zertifikats, müssen Sie auch Konfigurieren der Exchange Online Service Principal und Konfigurieren Ihrer lokalen Version von Skype für Business Server 2015 externen Webdienst-URLs als ein Office 365-Dienstprinzipal.</span><span class="sxs-lookup"><span data-stu-id="fe7b2-137">In addition to assigning a certificate, you must also configure the Exchange Online Service Principal and configure your on-premises version of Skype for Business Server 2015 external Web services URLs as an Office 365 service principal.</span></span> <span data-ttu-id="fe7b2-138">Kann erfolgen, indem Sie die folgenden zwei Befehle ausführen.</span><span class="sxs-lookup"><span data-stu-id="fe7b2-138">That can be done by carrying out the following two commands.</span></span> 
  
<span data-ttu-id="fe7b2-139">Im folgenden Beispiel wird die lync.contoso.com externen Webdienste-URL für die Skype für Business Server-Pool.</span><span class="sxs-lookup"><span data-stu-id="fe7b2-139">In the following example, lync.contoso.com is the external Web services URL for the Skype for Business Server pool.</span></span> <span data-ttu-id="fe7b2-140">Wiederholen Sie die folgenden Schritte aus, um alle externen Web Services-URLs in der Bereitstellung hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="fe7b2-140">You should repeat these steps to add all the external Web services URLs in the deployment.</span></span>
  
```
Set-MSOLServicePrincipal -AppPrincipalID 00000002-0000-0ff1-ce00-000000000000 -AccountEnabled $true

$lyncSP = Get-MSOLServicePrincipal -AppPrincipalID 00000004-0000-0ff1-ce00-000000000000
$lyncSP.ServicePrincipalNames.Add("00000004-0000-0ff1-ce00-000000000000/lync.contoso.com")
Set-MSOLServicePrincipal -AppPrincipalID 00000004-0000-0ff1-ce00-000000000000 -ServicePrincipalNames $lyncSP.ServicePrincipalNames
```