---
title: 'Lync Server 2013: Bereitstellen der lync Windows Store-App'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Deploying Lync Windows Store app
ms:assetid: 9e00aaf4-15f9-4356-9ed7-5a58a2bfa043
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ822971(v=OCS.15)
ms:contentKeyID: 50117635
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: eef2e96b1e58bb9a92b2dc9748624d38f605965f
ms.sourcegitcommit: 30ed4457d7004ba732372fee11a6f0b1baf48e05
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/08/2020
ms.locfileid: "40971240"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deploying-lync-windows-store-app-in-lync-server-2013"></a>Bereitstellen der lync Windows Store-App in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2013-12-03_

Bevor Sie die lync Windows Store-App für Benutzer verfügbar machen, stellen Sie sicher, dass Ihre Bereitstellung die [lync Windows Store-App-Anforderungen für lync Server 2013](lync-server-2013-lync-windows-store-app-requirements.md)erfüllt. Details zum Konfigurieren von lync Server 2013 zur Unterstützung der lync Windows Store-App finden Sie im NextHop-Blog Artikel "lync Server-AutoErmittlung und der lync Windows [http://go.microsoft.com/fwlink/?LinkId=271966](http://go.microsoft.com/fwlink/?linkid=271966)Store-App" unter. Nachdem Sie die Server Umgebung ordnungsgemäß konfiguriert haben, können Sie die Benutzer anweisen, die lync-App aus dem Windows Store herunterzuladen, indem Sie nach "lync" suchen.

<div>

## <a name="enabling-multi-factor-authentication-for-lync-windows-store-app"></a>Aktivieren der mehrstufigen Authentifizierung für die lync Windows Store-App

Kumulative Updates für lync Server 2013: Juni 2013 fügt Unterstützung für die mehrstufige Authentifizierung für lync Windows Store-App-Clients hinzu. Zusätzlich zu Benutzername und Kennwort können Sie zusätzliche Authentifizierungsmethoden wie Smartcards oder Pins anfordern, um externe Benutzer bei der Anmeldung bei lync-Besprechungen zu authentifizieren. Zum Aktivieren der mehrstufigen Authentifizierung stellen Sie den Active Directory Federation Service (AD FS)-Verbundserver bereit, und aktivieren Sie die passive Authentifizierung in lync Server 2013. Nach der Konfiguration von AD FS werden externe Benutzer, die versuchen, an lync-Besprechungen teilzunehmen, mit einer AD FS-Website mit mehrstufiger Authentifizierung angezeigt, die die Herausforderung Benutzername und Kennwort zusammen mit allen weiteren von Ihnen konfigurierten Authentifizierungsmethoden enthält. .

<div class=" ">


> [!IMPORTANT]  
> Im folgenden sind wichtige Überlegungen zu berücksichtigen, wenn Sie die Konfiguration von AD FS für die mehrstufige Authentifizierung für die lync Windows Store-App planen: 
> <UL>
> <LI>
> <P>Lync Server 2013 mit kumulativen Updates für lync Server 2013: Juni 2013 ist mindestens erforderlich. Lync 2013-Desktop Clients erfordern keine kumulativen Updates für lync Server 2013: Juni 2013, daher kann es vorkommen, dass die passive Authentifizierung funktioniert, weil lync 2013-Clients authentifiziert werden können. Der Authentifizierungsprozess für lync Windows Store-App-Clients wird jedoch nicht abgeschlossen, und es wird keine Benachrichtigung oder Fehlermeldung angezeigt.</P>
> <LI>
> <P>Der Server muss so konfiguriert sein, dass die passive Authentifizierung der einzige von Ihnen bereitgestellte Authentifizierungstyp ist.</P>
> <LI>
> <P>Wenn Sie Hardwarelastenausgleichs verwenden, aktivieren Sie die Beibehaltung von Cookies auf den Lastenausgleichsgeräten, damit alle Anforderungen vom lync Windows Store-App-Client vom gleichen Front-End-Server verarbeitet werden.</P>
> <LI>
> <P>Wenn Sie eine vertrauende Vertrauensstellung zwischen lync Server und AD FS-Servern einrichten, weisen Sie eine Lebensdauer von Token zu, die lang genug ist, um die maximale Länge ihrer lync-Besprechungen zu überspannen. Normalerweise genügt eine Tokengültigkeitsdauer von 240 Minuten.</P></LI></UL>



</div>

**So konfigurieren Sie die mehrstufige Authentifizierung**

1.  Installieren Sie eine AD FS-Verbundserverrolle. Ausführliche Informationen finden Sie im Bereitstellungshandbuch für Active Directory-Verbund <http://go.microsoft.com/fwlink/p/?linkid=267511>Dienste 2,0 unter.

2.  Erstellen Sie Zertifikate für AD FS. Weitere Informationen finden Sie im Abschnitt "Verbundserver Zertifikate" im Abschnitt Planen und Bereitstellen von AD FS für die Verwendung mit dem Thema für einmaliges [http://go.microsoft.com/fwlink/p/?LinkId=285376](http://go.microsoft.com/fwlink/p/?linkid=285376)anmelden unter.

3.  Führen Sie über die Windows PowerShell-Befehlszeilenschnittstelle den folgenden Befehl aus:
    ```powershell
    add-pssnapin Microsoft.Adfs.powershell
    ```
4.  Richten Sie durch Ausführen des folgenden Befehls eine Partnerschaft ein:
    ```powershell
    Add-ADFSRelyingPartyTrust -Name ContosoApp -MetadataURL https://lyncpool.contoso.com/passiveauth/federationmetadata/2007-06/federationmetadata.xml
    ```
5.  Legen Sie die folgenden vertrauenswürdigen Parteienregeln fest:
    
       ```powershell
        $IssuanceAuthorizationRules = '@RuleTemplate = "AllowAllAuthzRule" => issue(Type = "http://schemas.contoso.com/authorization/claims/permit", Value = "true");'$IssuanceTransformRules = '@RuleTemplate = "PassThroughClaims" @RuleName = "Sid" c:[Type == "http://schemas.contoso.com/ws/2008/06/identity/claims/primarysid"]=> issue(claim = c);'
       ```
    
       ```powershell
        Set-ADFSRelyingPartyTrust -TargetName ContosoApp -IssuanceAuthorizationRules $IssuanceAuthorizationRules -IssuanceTransformRules $IssuanceTransformRules
       ```
    
       ```powershell
        Set-CsWebServiceConfiguration -UseWsFedPassiveAuth $true -WsFedPassiveMetadataUri https://dc.contoso.com/federationmetadata/2007-06/federationmetadata.xml
       ```

</div>

<div>

## <a name="known-issues-that-can-prevent-sign-in"></a>Bekannte Probleme, die eine Anmeldung verhindern können

<div>

## <a name="the-time-and-date-are-not-set-accurately-on-the-device-running-lync-windows-store-app"></a>Die Uhrzeit und das Datum sind auf dem Gerät, auf dem die lync Windows Store-App ausgeführt wird, nicht genau eingestellt.

Die Zeiteinstellung auf dem Gerät muss mit der Zeiteinstellung auf dem Server synchronisiert werden. Dies ist besonders wichtig für Geräte wie Microsoft Surface und andere Geräte mit Windows RT, die nicht mit einer Domäne verbunden sind. Wenn Sie die Uhrzeit auf diesen Geräten automatisch von einem Zeitserver einstellen möchten, führen Sie den folgenden Befehl an einer Eingabeaufforderung mit erhöhten Rechten auf dem Gerät aus:
```console
w32tm /resync
```
</div>

<div>

## <a name="lync-windows-store-app-cannot-access-the-lync-server-or-services"></a>Lync Windows Store-App kann nicht auf lync-Server oder-Dienste zugreifen

Die lync Windows Store-App kann möglicherweise nicht über Netzwerkadapter, wie etwa 4G LTE-USB-Modems, auf lync-Server oder-Dienste zugreifen, die nicht bei Windows 8 als physikalische Geräte registriert sind. Bei der lync Windows Store-App kann dieses Problem auftreten, selbst wenn die Desktop-Apps und Browser auf andere Server und Websites zugreifen können.

</div>

<div>

## <a name="lync-windows-store-app-cannot-sign-in-with-lync-server-2010-and-office-communications-server-2007-r2-edge-server"></a>Lync Windows Store-App kann sich nicht mit lync Server 2010 und Office Communications Server 2007 R2 Edge-Server anmelden

Wenn Ihre Topologie aus lync Server 2010 mit Office Communications Server 2007 R2 Edge Server besteht, müssen Sie die aktualisierte Version des Topologie-Generators ausführen, die im kumulativen Update für lync Server 2010: Juli 2013 verfügbar ist. In früheren Versionen des Topologie-Generators wird nicht die erforderliche Zuordnung zu Office Communications Server 2007-Edgeserver erstellt, sodass sich lync Windows Store-App-Clients nicht anmelden können. Die folgenden Schritte sind erforderlich:

1.  Installieren Sie das kumulative Update für lync Server 2010: Juli 2013 in lync Server 2010-Pools und lync Server 2010-Directors.

2.  Aktualisieren Sie die lync-AutoErmittlungskonfiguration, um anzugeben, dass der externe SIP-Einstiegspunkt die Edgeserver-Adresse ist, indem Sie wie folgt vorgehen:
    
    1.  Öffnen Sie die Lync Server-Verwaltungsshell.
    
    2.  Führen Sie den folgenden Befehl aus:
        ```powershell
        Set-CsAutodiscoverConfiguration -ExternalSipClientAccessFqdn <FQDN of server used for external client access> -ExternalSipClientAccessPort 443
        ```
</div>

<div>

## <a name="lync-windows-store-app-cannot-sign-in-due-to-a-certificate-name-validation-failure"></a>Die lync Windows Store-App kann aufgrund eines Zertifikatsnamen-Validierungsfehlers nicht angemeldet werden.

Ein Anmeldeproblem kann für Office 365-Benutzer auftreten, die nicht die neueste Version der lync Windows Store-App ausführen. Dieses Problem tritt in der Regel bei der Verwendung mehrerer Domänen auf (beispielsweise, wenn der SIP-URI **UserA@domainZ.com** ist, der Edgeserver aber **SIP.domainX.com**ist). Um das Problem zu beheben, sollten Benutzer die neueste Version der lync Windows Store-App installieren, für die auch Windows 8,1 erforderlich ist.

</div>

</div>

<div>

## <a name="use-lync-windows-store-app-logs-to-troubleshoot-issues"></a>Verwenden von lync Windows Store-App-Protokollen zur Behandlung von Problemen

Sie können die auf dem Gerät generierten Protokolle verwenden, um Probleme zu beheben. Die Protokolle werden im folgenden Ordner gespeichert:

% LocalAppData%\\Pakete\\Microsoft. LyncMX\_8wekyb3d8bbwe\\LocalState\\-Ablaufverfolgung

Bevor Sie die Protokolle eines Benutzers abrufen, stellen Sie sicher, dass die Protokollierung aktiviert ist, und bitten Sie den Benutzer, die Protokolle zu speichern, damit alle im Arbeitsspeicher gespeicherten Informationen auch in Dateien auf der Festplatte gespeichert werden.

**So aktivieren Sie die Protokollierung**

1.  Öffnen Sie die lync Windows Store-App auf dem Gerät.

2.  Wischen Sie auf der rechten Seite des Bildschirms. Wenn Sie eine Maus verwenden, zeigen Sie auf die obere rechte Ecke des Bildschirms, und bewegen Sie dann den Mauszeiger nach unten auf dem Bildschirm.

3.  Wählen Sie **Einstellungen**aus, wählen Sie **Optionen**aus, und legen Sie dann **Diagnoseprotokolle** auf **ein**.

4.  Wenn **Diagnoseprotokolle** zuvor deaktiviert wurden, müssen Sie lync erneut starten. Führen Sie eine der folgenden Aktionen aus, um lync erneut zu starten:
    
      - Starten Sie das Gerät neu.
    
      - Beenden Sie die lync-Aufgabe, und starten Sie die APP erneut. Um die Aufgabe zu beenden, öffnen Sie den Windows Task-Manager, wählen Sie **lync**aus, und tippen Sie dann auf **Aufgabe beenden**. Wenn lync nicht aufgeführt ist, tippen Sie auf **Weitere Details** , und suchen Sie unter **Hintergrundprozesse**nach lync.

**So speichern Sie die Protokolle**

1.  Öffnen Sie die lync Windows Store-App auf dem Gerät.

2.  Versuchen Sie, sich anzumelden.

3.  Wischen Sie auf der rechten Seite des Bildschirms. Wenn Sie eine Maus verwenden, zeigen Sie auf die obere rechte Ecke des Bildschirms, und bewegen Sie dann den Mauszeiger nach unten auf dem Bildschirm.

4.  Wählen Sie **Einstellungen**aus, wählen Sie **Info**aus, und wählen Sie dann **Protokolle speichern**aus.

</div>

</div>

<span> </span>

</div>

</div>

</div>

