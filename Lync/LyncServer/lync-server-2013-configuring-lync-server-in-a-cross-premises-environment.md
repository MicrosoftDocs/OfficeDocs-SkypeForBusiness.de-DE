---
title: 'Lync Server 2013: Konfigurieren von lync Server in einer standortübergreifenden Umgebung'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring Microsoft Lync Server 2013 in a cross-premises environment
ms:assetid: 700639ec-5264-4449-a8a6-d7386fad8719
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204990(v=OCS.15)
ms:contentKeyID: 48184449
ms.date: 02/21/2017
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7dcbdb7ac12dcb8fc768a1f9e537622d01191b8f
ms.sourcegitcommit: d69bad69ba9a9bca4614d72d8f34fb2a0a9e4dc4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/13/2020
ms.locfileid: "44221729"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configuring-microsoft-lync-server-2013-in-a-cross-premises-environment"></a>Konfigurieren von Microsoft lync Server 2013 in einer standortübergreifenden Umgebung

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2017-02-21_

In einer standortübergreifenden Konfiguration werden einige Ihrer Benutzer in einer lokalen Installation von Microsoft lync Server 2013 verwaltet, während andere Benutzer in der Microsoft 365-oder Office 365-Version von lync Server verwaltet werden. Um die Server-zu-Server-Authentifizierung in einer standortübergreifenden Umgebung konfigurieren zu können, müssen Sie zunächst Ihre lokale Installation von lync Server 2013 so konfigurieren, dass Sie dem Microsoft 365-autorisierungsserver vertraut. Der erste Schritt in diesem Prozess kann durch Ausführen des folgenden lync Server-Verwaltungsshell Skripts ausgeführt werden:

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

Beachten Sie, dass der Bereichsname für einen Mandanten in der Regel nicht mit dem Namen der Organisation identisch ist. Tatsächlich ist der Bereichsname fast immer identisch mit der Mandanten-ID. Aus diesem Grund wird die erste Codezeile im Skript verwendet, um den Wert der Mandanten-Eigenschaft für den angegebenen Mandanten (in diesem Fall fabrikam.com) zurückzugeben und diesen Namen dann der Variablen $TenantId zuzuweisen:

    $TenantID = (Get-CsTenant -DisplayName "Fabrikam.com").TenantId

Nachdem das Skript abgeschlossen ist, müssen Sie eine Vertrauensstellung zwischen lync Server 2013 und dem autorisierungsserver und eine zweite Vertrauensstellung zwischen Exchange 2013 und dem autorisierungsserver konfigurieren. Dies kann nur mithilfe der Microsoft Online Services-Cmdlets erfolgen.

<div>


> [!NOTE]  
> Wenn Sie die Microsoft Online Services-Cmdlets nicht installiert haben, müssen Sie zwei Schritte ausführen, bevor Sie fortfahren können. Laden Sie zuerst die 64-Bit-Version des Microsoft Online Services-Anmelde-Assistenten herunter, und installieren Sie Sie. Laden Sie nach Abschluss der Installation die 64-Bit-Version des Microsoft Online Services-Modul für Windows PowerShell herunter, und installieren Sie es. Ausführliche Informationen zum Installieren und Verwenden des Microsoft Online Services-Modul finden Sie auf der Microsoft 365-oder Office 365-Website. In diesen Anweisungen erfahren Sie außerdem, wie Sie einmaliges Anmelden, Partnerverbund und Synchronisierung zwischen Microsoft 365 oder Office 36 und Active Directory konfigurieren.<BR>Wenn Sie diese Cmdlets nicht installiert haben, tritt beim Skript ein Fehler auf, da das Cmdlet Get-CsTenant nicht verfügbar ist.



</div>

Nachdem Sie Microsoft 365 konfiguriert haben und nachdem Sie Microsoft 365 oder Office 365 Dienst Prinzipale für lync Server 2013 und Exchange 2013 erstellt haben, müssen Sie Ihre Anmeldeinformationen bei diesen Dienst Prinzipalen registrieren. Um dies zu erreichen, müssen Sie zuerst ein X. 509-Base64-Objekt abrufen, das als gespeichert wird. CER-Datei. Dieses Zertifikat wird dann auf die Microsoft 365-oder Office 365-Dienst Prinzipale angewendet.

Wenn Sie das X. 509-Zertifikat erhalten haben, starten Sie das Microsoft Online Services-Modul (Klicken Sie im **Startmenü**auf **Alle Programme**, klicken Sie auf **Microsoft Online Services**, und klicken Sie dann auf **Microsoft Online Services-Modul für Windows PowerShell**). Geben Sie nach dem Öffnen des Moduls Dienste Folgendes ein, um das Microsoft Online Windows PowerShell-Modul zu importieren, das die Cmdlets enthält, die zum Verwalten von Dienst Prinzipalen verwendet werden können:

    Import-Module MSOnlineExtended

Wenn das Modul importiert wurde, geben Sie den folgenden Befehl ein, und drücken Sie dann die EINGABETASTE, um eine Verbindung mit Microsoft 365 herzustellen:

    Connect-MsolService

Nachdem Sie die EINGABETASTE gedrückt haben, wird ein Dialogfeld Anmeldeinformationen angezeigt. Geben Sie im Dialogfeld Ihren Microsoft 365-oder Office 365-Benutzernamen und das Kennwort ein, und klicken Sie dann auf OK.

Sobald Sie mit Microsoft 365 verbunden sind, können Sie den folgenden Befehl ausführen, um Informationen zu ihren Dienst Prinzipalen zurückzugeben:

    Get-MsolServicePrincipal

Sie sollten für alle Dienst Prinzipale Informationen zurück erhalten, die diesem ähneln:

    ExtensionData        : System.Runtime.Serialization.ExtensionDataObject
    AccountEnabled       : True
    Addresses            : {}
    AppPrincipalId       : 00000004-0000-0ff1-ce00-000000000000
    DisplayName          : Microsoft Lync Server
    ObjectId             : aada5fbd-c0ae-442a-8c0b-36fec40602e2
    ServicePrincipalName : LyncServer/litwareinc.com
    TrustedForDelegation : True

Der nächste Schritt besteht darin, das X. 509-Zertifikat zu importieren, zu codieren und zuzuweisen. Um das Zertifikat zu importieren und zu codieren, verwenden Sie die folgenden Windows PowerShell Befehle, wobei Sie sicherstellen möchten, dass der vollständige Dateipfad angegeben wird. CER-Datei, wenn Sie die Import-Methode aufrufen:

    $certificate = New-Object System.Security.Cryptography.X509Certificates.X509Certificate
    $certificate.Import("C:\Certificates\Office365.cer")
    $binaryValue = $certificate.GetRawCertData()
    $credentialsValue = [System.Convert]::ToBase64String($binaryValue)

Nachdem das Zertifikat importiert und codiert wurde, können Sie das Zertifikat Ihren Microsoft 365-Dienst Prinzipalen zuweisen. Verwenden Sie dazu zunächst das Get-MsolServicePrincipal, um den Wert der AppPrincipalId-Eigenschaft sowohl für die lync Server als auch für die Microsoft Exchange Dienst Prinzipale abzurufen; der Wert der AppPrincipalId-Eigenschaft wird verwendet, um den Dienstprinzipal zu identifizieren, dem das Zertifikat zugewiesen wurde. Wenn der Wert der AppPrincipalId-Eigenschaft für lync Server 2013 in der Hand ist, verwenden Sie den folgenden Befehl, um das Zertifikat der Microsoft 365-Version von lync Server zuzuweisen (die StartDate-und EndDate-Eigenschaften sollten dem Gültigkeitszeitraum für das Zertifikat entsprechen):

    New-MsolServicePrincipalCredential -AppPrincipalId 00000004-0000-0ff1-ce00-000000000000 -Type Asymmetric -Usage Verify -Value $credentialsValue -StartDate 6/1/2012 -EndDate 5/31/2013

Sie sollten dann den Befehl wiederholen, diesmal mit dem AppPrincipalId-Eigenschaftswert für Exchange 2013.

Wenn Sie das Zertifikat zu einem späteren Zeitpunkt löschen müssen, können Sie dies zunächst durch Abrufen des KeyId für das Zertifikat tun:

    Get-MsolServicePrincipalCredential -AppPrincipalId 00000004-0000-0ff1-ce00-000000000000

Dieser Befehl gibt Daten wie diese zurück:

    Type      : Asymmetric
    Value     : 
    KeyId     : bc2795f3-2387-4543-a95d-f92c85c7a1b0
    StartDate : 6/1/2012 8:00:00 AM
    EndDate   : 5/31/2013 8:00:00 AM
    Usage     : Verify

Anschließend können Sie das Zertifikat mit einem Befehl wie dem folgenden löschen:

    Remove-MsolServicePrincipalCredential -AppPrincipalId 00000004-0000-0ff1-ce00-000000000000 -KeyId bc2795f3-2387-4543-a95d-f92c85c7a1b0

Neben dem Zuweisen eines Zertifikats müssen Sie auch den Microsoft 365-Dienstprinzipal für Exchange Online konfigurieren, indem Sie den Server Prinzipalnamen für Ihre lokale Version von lync Server 2013 hinzufügen. Dies kann durch Ausführen der folgenden vier Zeilen in einer Microsoft Online Services PowerShell-Sitzung erfolgen:

    Set-MSOLServicePrincipal -AppPrincipalID 00000002-0000-0ff1-ce00-000000000000 -AccountEnabled $true
    
    $lyncSP = Get-MSOLServicePrincipal -AppPrincipalID 00000004-0000-0ff1-ce00-000000000000
    $lyncSP.ServicePrincipalNames.Add("00000004-0000-0ff1-ce00-000000000000/lync.contoso.com")
    Set-MSOLServicePrincipal -AppPrincipalID 00000004-0000-0ff1-ce00-000000000000 -ServicePrincipalNames $lyncSP.ServicePrincipalNames

</div>

<span> </span>

</div>

</div>

</div>

