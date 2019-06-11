---
title: 'Lync Server 2013: Konfigurieren von lync Server in einer standortübergreifenden Umgebung'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring Microsoft Lync Server 2013 in a cross-premises environment
ms:assetid: 700639ec-5264-4449-a8a6-d7386fad8719
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204990(v=OCS.15)
ms:contentKeyID: 48184449
ms.date: 02/21/2017
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 44a47dc3bf3c832819fe431cb0177bfc1a03f330
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34839237"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-microsoft-lync-server-2013-in-a-cross-premises-environment"></a>Konfigurieren von Microsoft lync Server 2013 in einer standortübergreifenden Umgebung

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2017-02-21_

In einer standortübergreifenden Konfiguration sind einige Ihrer Benutzer in einer lokalen Installation von Microsoft lync Server 2013, während andere Benutzer in der Office 365-Version von lync Server verwaltet werden. Um die Server-zu-Server-Authentifizierung in einer standortübergreifenden Umgebung zu konfigurieren, müssen Sie zuerst Ihre lokale Installation von lync Server 2013 so konfigurieren, dass Sie dem Office 365-autorisierungsserver vertraut. Der erste Schritt in diesem Prozess kann durch Ausführen des folgenden Skripts der lync Server-Verwaltungsshell ausgeführt werden:

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

Beachten Sie, dass sich der Bereichsname für einen Mandanten normalerweise vom Namen der Organisation unterscheidet. Der Bereichsname entspricht stattdessen häufig der Mandanten-ID. Aus diesem Grund dient die erste Zeile des Skripts dazu, den Wert der TenantId-Eigenschaft für den angegebenen Mandanten zurückzugeben (in diesem Fall „fabrikam.com“) und den entsprechenden Namen anschließend der Variablen „$TenantId“ zuzuweisen:

    $TenantID = (Get-CsTenant -DisplayName "Fabrikam.com").TenantId

Nachdem das Skript abgeschlossen ist, müssen Sie eine Vertrauensstellung zwischen lync Server 2013 und dem autorisierungsserver sowie eine zweite Vertrauensstellung zwischen Exchange 2013 und dem autorisierungsserver konfigurieren. Das ist nur mithilfe der Microsoft Online Services-Cmdlets möglich.

<div>


> [!NOTE]  
> Wenn Sie die Microsoft Online Services-Cmdlets noch nicht installiert haben, müssen Sie zwei Schritte ausführen, bevor Sie fortfahren können. Laden Sie die 64-Bit-Version des Microsoft Online Services-Anmeldeassistenten herunter, und installieren Sie sie. Nachdem die Installation abgeschlossen ist, laden Sie die 64-Bit-Version des Microsoft Online Services-Moduls für Windows PowerShell herunter, und installieren Sie Sie. Detaillierte Informationen zum Installieren und Verwenden des Microsoft Online Services-Moduls finden Sie auf der Office 365-Website. In diesen Anweisungen erfahren Sie auch, wie Sie das einmalige Anmelden, den Verbund und die Synchronisierung zwischen Office 365 und Active Directory konfigurieren.<BR>Wenn Sie diese Cmdlets nicht installiert haben, schlägt Ihr Skript fehl, weil das Get-CsTenant-Cmdlet nicht verfügbar ist.



</div>

Nachdem Sie Office 365 konfiguriert haben und nachdem Sie Office 365-Dienst Prinzipale für lync Server 2013 und Exchange 2013 erstellt haben, müssen Sie Ihre Anmeldeinformationen bei diesen Dienst Prinzipalen registrieren. Zu diesem Zweck müssen Sie zunächst ein Base64-kodiertes X.509-Zertifikat anfordern, das als CER-Datei gespeichert wird. Dieses Zertifikat wird dann auf die Office 365-Dienst Prinzipale angewendet.

Wenn Sie das X. 509-Zertifikat erhalten haben, starten Sie das Microsoft Online Services-Modul (Klicken Sie auf **Start**, klicken Sie auf **Alle Programme**, klicken Sie auf **Microsoft Online Services**, und klicken Sie dann auf Microsoft Online Services **-Modul für Windows. PowerShell**). Nachdem das Modul Dienste geöffnet wurde, geben Sie Folgendes ein, um das Microsoft Online Windows PowerShell-Modul zu importieren, das die Cmdlets enthält, die zum Verwalten von Dienst Prinzipalen verwendet werden können:

    Import-Module MSOnlineExtended

Wenn das Modul importiert wurde, geben Sie den folgenden Befehl ein, und drücken Sie dann die EINGABETASTE, um eine Verbindung mit Office 365 herzustellen:

    Connect-MsolService

Nach Drücken der EINGABETASTE wird ein Dialogfeld zur Eingabe Ihrer Anmeldeinformationen angezeigt. Geben Sie Ihren Office 365-Benutzernamen und das Kennwort in das Dialogfeld ein, und klicken Sie dann auf OK.

Sobald Sie mit Office 365 verbunden sind, können Sie den folgenden Befehl ausführen, um Informationen zu ihren Dienst Prinzipalen zurückzugeben:

    Get-MsolServicePrincipal

Sie sollten ähnliche Informationen wie die folgenden für alle Ihre Dienstprinzipale erhalten:

    ExtensionData        : System.Runtime.Serialization.ExtensionDataObject
    AccountEnabled       : True
    Addresses            : {}
    AppPrincipalId       : 00000004-0000-0ff1-ce00-000000000000
    DisplayName          : Microsoft Lync Server
    ObjectId             : aada5fbd-c0ae-442a-8c0b-36fec40602e2
    ServicePrincipalName : LyncServer/litwareinc.com
    TrustedForDelegation : True

Der nächste Schritt besteht darin, das X.509-Zertifikat zu importieren, zu codieren und zuzuweisen. Verwenden Sie zum Importieren und Codieren des Zertifikats die folgenden Windows PowerShell-Befehle, wobei Sie sicherstellen möchten, dass der vollständige Dateipfad zu Ihrem. CER-Datei beim Aufrufen der Import-Methode:

    $certificate = New-Object System.Security.Cryptography.X509Certificates.X509Certificate
    $certificate.Import("C:\Certificates\Office365.cer")
    $binaryValue = $certificate.GetRawCertData()
    $credentialsValue = [System.Convert]::ToBase64String($binaryValue)

Nachdem das Zertifikat importiert und codiert wurde, können Sie das Zertifikat ihren Office 365-Dienst Prinzipalen zuweisen. Verwenden Sie dazu zunächst die Get-MsolServicePrincipal-Eigenschaft, um den Wert der AppPrincipalId-Eigenschaft sowohl für den lync-Server als auch für die Microsoft Exchange-Dienst Prinzipale abzurufen. der Wert der AppPrincipalId-Eigenschaft wird verwendet, um den Dienstprinzipal zu identifizieren, dem das Zertifikat zugewiesen wird. Mit dem AppPrincipalId-Eigenschaftswert für lync Server 2013 verwenden Sie den folgenden Befehl, um das Zertifikat der Office 365-Version von lync Server zuzuweisen (die Eigenschaften StartDate und EndDate sollten dem Gültigkeitszeitraum für das Zertifikat entsprechen):

    New-MsolServicePrincipalCredential -AppPrincipalId 00000004-0000-0ff1-ce00-000000000000 -Type Asymmetric -Usage Verify -Value $credentialsValue -StartDate 6/1/2012 -EndDate 5/31/2013

Sie sollten diesen Befehl dann wiederholen, indem Sie dieses Mal den AppPrincipalId-Eigenschaftswert für Exchange 2013 verwenden.

Falls Sie das Zertifikat zu einem späteren Zeitpunkt löschen müssen, rufen Sie dazu zunächst die KeyID für das Zertifikat ab:

    Get-MsolServicePrincipalCredential -AppPrincipalId 00000004-0000-0ff1-ce00-000000000000

Der entsprechende Befehl gibt in etwa folgende Daten zurück:

    Type      : Asymmetric
    Value     : 
    KeyId     : bc2795f3-2387-4543-a95d-f92c85c7a1b0
    StartDate : 6/1/2012 8:00:00 AM
    EndDate   : 5/31/2013 8:00:00 AM
    Usage     : Verify

Sie können das Zertifikat mit einem ähnlichen Befehl wie diesem löschen:

    Remove-MsolServicePrincipalCredential -AppPrincipalId 00000004-0000-0ff1-ce00-000000000000 -KeyId bc2795f3-2387-4543-a95d-f92c85c7a1b0

Neben dem Zuweisen eines Zertifikats müssen Sie auch den Office 365-Dienstprinzipal für Exchange Online konfigurieren, indem Sie den Server Prinzipalnamen für Ihre lokale Version von lync Server 2013 hinzufügen. Dies kann durch Ausführen der folgenden vier Zeilen in einer Microsoft Online Services PowerShell-Sitzung erfolgen:

    Set-MSOLServicePrincipal -AppPrincipalID 00000002-0000-0ff1-ce00-000000000000 -AccountEnabled $true
    
    $lyncSP = Get-MSOLServicePrincipal -AppPrincipalID 00000004-0000-0ff1-ce00-000000000000
    $lyncSP.ServicePrincipalNames.Add("00000004-0000-0ff1-ce00-000000000000/lync.contoso.com")
    Set-MSOLServicePrincipal -AppPrincipalID 00000004-0000-0ff1-ce00-000000000000 -ServicePrincipalNames $lyncSP.ServicePrincipalNames

</div>

<span> </span>

</div>

</div>

</div>

