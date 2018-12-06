---
title: Konfigurieren von Microsoft Lync Server 2013 in einer standortübergreifenden Umgebung
TOCTitle: Konfigurieren von Microsoft Lync Server 2013 in einer standortübergreifenden Umgebung
ms:assetid: 700639ec-5264-4449-a8a6-d7386fad8719
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ204990(v=OCS.15)
ms:contentKeyID: 49294358
ms.date: 02/21/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Konfigurieren von Microsoft Lync Server 2013 in einer standortübergreifenden Umgebung

 

_**Letztes Änderungsdatum des Themas:** 2017-02-21_

In einer standortübergreifenden Konfiguration befinden sich einige Ihrer Benutzer auf einer lokalen Installation von Microsoft Lync Server 2013, während andere Benutzer auf der Office 365-Version von Lync Server verwaltet werden. Für die Konfiguration der Server-zu-Server-Authentifizierung in einer standortübergreifenden Umgebung müssen Sie zunächst Ihre lokale Installation von Lync Server 2013 so konfigurieren, dass sie dem Office 365-Autorisierungsserver vertraut. Der erste Schritt in diesem Prozess kann durch Ausführung des Lync Server-Verwaltungsshell-Skripts erfolgen:

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

Beachten Sie, dass sich der Bereichsname für einen Mandanten normalerweise vom Namen der Organisation unterscheidet. Der Bereichsname entspricht stattdessen häufig der Mandanten-ID. Aus diesem Grund dient die erste Zeile des Skripts dazu, den Wert der TenantId-Eigenschaft für den angegebenen Mandanten zurückzugeben (in diesem Fall "fabrikam.com") und den entsprechenden Namen anschließend der Variablen "$TenantId" zuzuweisen:

    $TenantID = (Get-CsTenant -DisplayName "Fabrikam.com").TenantId

Nachdem das Skript ausgeführt wurde, müssen Sie eine Vertrauensstellung zwischen Lync Server 2013 und dem Autorisierungsserver und eine zweite Vertrauensstellung zwischen Exchange 2013 und dem Autorisierungsserver konfigurieren. Das ist nur mithilfe der Microsoft Online Services-Cmdlets möglich.


> [!NOTE]
> Für den Fall, dass Sie die Microsoft Online Services-Cmdlets nicht installiert haben, müssen Sie zwei Dinge erledigen, bevor Sie fortfahren. Laden Sie zunächst die 64-Bit-Version des Microsoft Online Services-Anmelde-Assistenten herunter und installieren Sie sie. Nach Abschluss der Installation laden Sie die 64-Bit-Version des Microsoft Online Services-Modul für Windows PowerShell herunter und installieren Sie sie. Ausführliche Informationen zur Installation und Verwendung des Microsoft Online Services-Moduls finden Sie auf der Website zu Office 365. Die dort verfügbaren Anweisungen enthalten auch Informationen zur Konfiguration der einmaligen Anmeldung (Single Sign-On, SSO), des Partnerverbunds und der Synchronisierung zwischen Office 365 und Active Directory.<BR>Wenn Sie diese Cmdlets nicht installiert haben, schlägt Ihr Skipt fehl, weil das Get-CsTenant-Cmdlet nicht verfügbar ist.



Nachdem Sie Office 365 konfiguriert haben und nachdem Sie die Office 365-Dienstprinzipale für Lync Server 2013 und Exchange 2013 erstellt haben, müssen Sie Ihre Anmeldeinformationen mit diesen Dienstprinzipalen registrieren. Zu diesem Zweck müssen Sie zunächst ein Base64-kodiertes X.509-Zertifikat anfordern, das als CER-Datei gespeichert ist. Dieses Zertifikat wird dann auf die Office 365-Dienstprinzipale angewendet.

Starten Sie, nachdem Sie das X.509-Zertifikat angefordert haben, das Microsoft Online Services-Modul (klicken Sie auf **Start**, **Alle Programme**, **Microsoft Online Services** und dann auf **Microsoft Online Services-Module für Windows PowerShell**). Geben Sie, nachdem das Services-Modul geöffnet wurde, Folgendes ein, um das Microsoft Online Windows PowerShell-Modul zu importieren, das die für die Verwaltung der Dienstprinzipale verwendbaren Cmdlets enthält:

    Import-Module MSOnlineExtended

Geben Sie, nachdem das Modul importiert wurde, folgenden Befehl ein, und drücken Sie die EINGABETASTE, um die Verbindung mit Office 365 herzustellen:

    Connect-MsolService

Nach dem Drücken der EINGABETASTE wird ein Dialogfeld zur Eingabe Ihrer Anmeldeinformationen angezeigt. Geben Sie Ihren Benutzernamen und Ihr Kennwort für Office 365 in das Dialogfeld ein, und klicken Sie auf "OK".

Sobald die Verbindung mit Office 365 hergestellt wurde, können Sie den folgenden Befehl ausführen, um Informationen zu Ihren Dienstprinzipalen zu erhalten:

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

Der nächste Schritt besteht darin, das X.509-Zertifikat zu importieren, zu codieren und zuzuweisen. Verwenden Sie zum Importieren und Codieren des Zertifikats die folgenden Windows PowerShell-Befehle, und achten Sie dabei darauf, den gesamten Dateipfad in Ihrer CER-Datei anzugeben, wenn Sie die Import-Methode aufrufen:

    $certificate = New-Object System.Security.Cryptography.X509Certificates.X509Certificate
    $certificate.Import("C:\Certificates\Office365.cer")
    $binaryValue = $certificate.GetRawCertData()
    $credentialsValue = [System.Convert]::ToBase64String($binaryValue)

Nachdem das Zertifikat importiert und codiert wurde, können Sie es Ihren Office 365-Dienstprinzipalen zuweisen. Verwenden Sie zu diesem Zweck das Get-MsolServicePrincipal-Cmdlet, um den Wert der AppPrincipalId-Eigenschaft für die Lync Server- als auch Microsoft Exchange-Dienstprinzipale abzurufen. Der Wert der AppPrincipalId-Eigenschaft wird verwendet, um den dem Zertifikat zuzuweisenden Dienstprinzipal anzugeben. Nun, da Sie über den Wert der AppPrincipalId-Eigenschaft für Lync Server 2013 verfügen, verwenden Sie den folgenden Befehl, um das Zertifikat zur Office 365-Version von Lync Server zuzuweisen (die Eigenschaften "StartDate" und "EndDate" sollten die Gültigkeitsdauer des Zertifikats wiedergeben):

    New-MsolServicePrincipalCredential -AppPrincipalId 00000004-0000-0ff1-ce00-000000000000 -Type Asymmetric -Usage Verify -Value $credentialsValue -StartDate 6/1/2012 -EndDate 5/31/2013

Sie sollten den Befehl daraufhin wiederholen und diesmal den AppPrincipalId-Eigenschaftswert für Exchange 2013 verwenden.

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

Neben der Zuweisung eines Zertifikats ist es noch erforderlich, den Exchange Online-Dienstprinzipal zu konfigurieren, und Sie müssen Ihre lokale Version von Lync Server 2013 als einen Office 365-Dienstprinzipal konfigurieren. Führen Sie dazu die folgenden beiden Befehle aus:

    Set-MSOLServicePrincipal -AppPrincipalID 00000002-0000-0ff1-ce00-000000000000 -AccountEnabled $true
    
    $lyncSP = Get-MSOLServicePrincipal -AppPrincipalID 00000004-0000-0ff1-ce00-000000000000
    $lyncSP.ServicePrincipalNames.Add("00000004-0000-0ff1-ce00-000000000000/lync.contoso.com")
    Set-MSOLServicePrincipal -AppPrincipalID 00000004-0000-0ff1-ce00-000000000000 -ServicePrincipalNames $lyncSP.ServicePrincipalNames

