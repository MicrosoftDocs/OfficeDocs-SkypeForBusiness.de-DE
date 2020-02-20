---
title: 'Lync Server 2013: Bereitstellen der lync Windows Store-App'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deploying Lync Windows Store app
ms:assetid: 9e00aaf4-15f9-4356-9ed7-5a58a2bfa043
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ822971(v=OCS.15)
ms:contentKeyID: 50117635
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d27f7a2402fabbc28080ca5efc2532497c93c653
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2020
ms.locfileid: "42147538"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="deploying-lync-windows-store-app-in-lync-server-2013"></a>Bereitstellen der lync Windows Store-App in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2013-12-03_

Bevor Sie die lync Windows Store-App für Benutzer verfügbar machen, müssen Sie sicherstellen, dass Ihre Bereitstellung die [lync Windows Store-App-Anforderungen für lync Server 2013](lync-server-2013-lync-windows-store-app-requirements.md)erfüllt. Ausführliche Informationen zum Konfigurieren von lync Server 2013 zur Unterstützung der lync Windows Store-App finden Sie im NextHop-Blog Artikel "lync Server AutoErmittlung und der lync Windows [https://go.microsoft.com/fwlink/?LinkId=271966](https://go.microsoft.com/fwlink/?linkid=271966)Store-App" unter. Nachdem die Server Umgebung ordnungsgemäß konfiguriert wurde, können Sie Benutzer anweisen, die lync-App aus dem Windows Store herunterzuladen, indem Sie nach "lync" suchen.

<div>

## <a name="enabling-multi-factor-authentication-for-lync-windows-store-app"></a>Aktivieren der mehrstufigen Authentifizierung für lync Windows Store-App

Kumulative Updates für lync Server 2013: Juni 2013 fügt Unterstützung für mehrstufige Authentifizierung für lync Windows Store-App-Clients hinzu. Neben Benutzername und Kennwort können Sie zusätzliche Authentifizierungsmethoden wie Smartcards oder Pins zur Authentifizierung externer Benutzer bei der Anmeldung an lync-Besprechungen benötigen. Zum Aktivieren der mehrstufigen Authentifizierung stellen Sie Active Directory Verbunddienst (AD FS)-Verbundserver bereit und aktivieren die passive Authentifizierung in lync Server 2013. Nachdem AD FS konfiguriert wurde, werden externe Benutzer, die versuchen, an lync-Besprechungen teilzunehmen, mit einer AD FS-mehrstufigen Authentifizierungs Webseite angezeigt, die den Benutzernamen und das Kennwort sowie alle weiteren von Ihnen konfigurierten Authentifizierungsmethoden enthält. .

<div class=" ">


> [!IMPORTANT]  
> Im folgenden sind wichtige Überlegungen aufgeführt, wenn Sie AD FS für die mehrstufige Authentifizierung für die lync Windows Store-App konfigurieren möchten: 
> <UL>
> <LI>
> <P>Lync Server 2013 mit kumulativen Updates für lync Server 2013: Juni 2013 wird mindestens benötigt. Lync 2013 Desktop Clients keine kumulativen Updates für lync Server 2013: Juni 2013 benötigen, scheint es möglicherweise, dass die passive Authentifizierung funktioniert, da sich lync 2013 Clients authentifizieren können. Der Authentifizierungsprozess für lync Windows Store-App-Clients kann jedoch nicht abgeschlossen werden, und es wird keine Benachrichtigung oder Fehlermeldung angezeigt.</P>
> <LI>
> <P>Der Server muss so konfiguriert werden, dass die passive Authentifizierung der einzige verfügbare Authentifizierungstyp ist.</P>
> <LI>
> <P>Wenn Sie Hardwarelastenausgleichs verwenden, aktivieren Sie die Dauerhaftigkeit von Cookies für die Lastenausgleichsmodule, damit alle Anforderungen vom lync Windows Store-App-Client von derselben Front-End-Server verarbeitet werden.</P>
> <LI>
> <P>Wenn Sie eine Vertrauensstellung der vertrauenden Seite zwischen lync Server und AD FS-Servern einrichten, weisen Sie eine Lebensdauer von Token zu, die sich über die maximale Länge ihrer lync-Besprechungen erstrecken kann. Gewöhnlich genügt eine Gültigkeitsdauer des Token von 240 Minuten.</P></LI></UL>



</div>

**Konfigurieren der mehrstufigen Authentifizierung**

1.  Installieren Sie eine Active Directory-Verbunddienste-Verbundserverrolle. Ausführliche Informationen finden Sie im Bereitstellungshandbuch für Active Directory Verbunddienste <https://go.microsoft.com/fwlink/p/?linkid=267511>2,0 unter.

2.  Erstellen von Zertifikaten für AD FS. Weitere Informationen finden Sie im Abschnitt "Verbundserver Zertifikate" des Themas planen und Bereitstellen von AD FS für die Verwendung mit einmaligem Anmelden unter [https://go.microsoft.com/fwlink/p/?LinkId=285376](https://go.microsoft.com/fwlink/p/?linkid=285376).

3.  Führen Sie über die Befehlszeilenschnittstelle Windows PowerShell den folgenden Befehl aus:
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

## <a name="known-issues-that-can-prevent-sign-in"></a>Bekannte Probleme, die die Anmeldung verhindern können

<div>

## <a name="the-time-and-date-are-not-set-accurately-on-the-device-running-lync-windows-store-app"></a>Die Uhrzeit und das Datum werden auf dem Gerät, auf dem die lync Windows Store-App läuft, nicht genau festgelegt.

Die Zeiteinstellung auf dem Gerät muss mit der Zeiteinstellung auf dem Server synchronisiert werden. Dies ist insbesondere für Geräte wie Microsoft Surface und andere Geräte mit Windows RT wichtig, die nicht mit einer Domäne verbunden sind. Um die Uhrzeit auf diesen Geräten automatisch von einem Zeitserver festzulegen, führen Sie den folgenden Befehl an einer Eingabeaufforderung mit erhöhten Rechten auf dem Gerät aus:
```console
w32tm /resync
```
</div>

<div>

## <a name="lync-windows-store-app-cannot-access-the-lync-server-or-services"></a>Lync Windows Store-App kann nicht auf lync Server oder Dienste zugreifen

Die lync Windows Store-App kann möglicherweise nicht über Netzwerkadapter wie 4G LTE-USB-Modems auf lync Server oder-Dienste zugreifen, die sich nicht bei Windows 8 als physikalische Geräte registrieren können. Die lync Windows Store-App hat dieses Problem möglicherweise auch dann, wenn die Desktop-Apps und Browser auf andere Server und Websites zugreifen können.

</div>

<div>

## <a name="lync-windows-store-app-cannot-sign-in-with-lync-server-2010-and-office-communications-server-2007-r2-edge-server"></a>Die lync Windows Store-App kann sich nicht mit lync Server 2010 und Office Communications Server 2007 R2 anmelden Edgeserver

Wenn Ihre Topologie aus lync Server 2010 mit Office Communications Server 2007 R2 Edgeserver besteht, müssen Sie die aktualisierte Version des Topologie-Generators ausführen, die im kumulativen Update für lync Server 2010: July 2013 verfügbar ist. In früheren Versionen des Topologie-Generators wird nicht die erforderliche Zuordnung zu Office Communications Server 2007 Edgeserver erstellt, sodass lync Windows Store-App-Clients sich nicht anmelden können. Die folgenden Schritte sind erforderlich:

1.  Installieren Sie das kumulative Update für lync Server 2010: Juli 2013 auf lync Server 2010 Pools und lync Server 2010 Directors.

2.  Aktualisieren Sie die lync-AutoErmittlungskonfiguration, um anzugeben, dass der externe SIP-Einstiegspfad die Edgeserver-Adresse ist, indem Sie folgendermaßen vorgehen:
    
    1.  Öffnen Sie lync Server-Verwaltungsshell.
    
    2.  Führen Sie den folgenden Befehl aus:
        ```powershell
        Set-CsAutodiscoverConfiguration -ExternalSipClientAccessFqdn <FQDN of server used for external client access> -ExternalSipClientAccessPort 443
        ```
</div>

<div>

## <a name="lync-windows-store-app-cannot-sign-in-due-to-a-certificate-name-validation-failure"></a>Lync Windows Store-App kann sich aufgrund eines Zertifikatsnamen Überprüfungsfehlers nicht anmelden

Ein Anmeldeproblem kann für Office 365 Benutzer auftreten, die nicht die neueste Version der lync Windows Store-App ausgeführt werden. Dieses Problem tritt im Allgemeinen auf, wenn mehrere Domänen verwendet werden (beispielsweise, wenn der SIP-URI **UserA@domainZ.com** ist, die Edgeserver jedoch **SIP.domainX.com**). Um das Problem zu beheben, sollten Benutzer die neueste Version der lync Windows Store-App installieren, die auch Windows 8.1 erfordert.

</div>

</div>

<div>

## <a name="use-lync-windows-store-app-logs-to-troubleshoot-issues"></a>Verwenden von lync Windows Store-App-Protokollen zur Behandlung von Problemen

Sie können die auf dem Gerät generierten Protokolle verwenden, um Probleme zu beheben. Die Protokolle werden im folgenden Ordner gespeichert:

% LocalAppData%\\Pakete\\Microsoft. LyncMX\_8wekyb3d8bbwe\\LocalState\\-Ablaufverfolgung

Bevor Sie die Protokolle von einem Benutzer erhalten, stellen Sie sicher, dass die Protokollierung aktiviert ist, und bitten Sie den Benutzer, die Protokolle zu speichern, damit alle im Arbeitsspeicher gespeicherten Informationen auch in Dateien auf der Festplatte gespeichert werden.

**So aktivieren Sie die Protokollierung**

1.  Öffnen Sie die lync Windows Store-App auf dem Gerät.

2.  Streichen Sie von der rechten Seite des Bildschirms. Wenn Sie eine Maus verwenden, zeigen Sie auf die obere rechte Ecke des Bildschirms, und bewegen Sie dann den Mauszeiger nach unten auf dem Bildschirm.

3.  Wählen Sie **Einstellungen**aus, wählen Sie **Optionen**aus, und legen Sie dann **Diagnoseprotokolle** **auf ein**fest.

4.  Wenn **Diagnoseprotokolle** zuvor deaktiviert waren, müssen Sie lync neu starten. Führen Sie einen der folgenden Schritte aus, um lync neu zu starten:
    
      - Starten Sie das Gerät neu.
    
      - Beenden Sie die lync-Aufgabe, und starten Sie die APP erneut. Um die Aufgabe zu beenden, öffnen Sie den Windows-Task-Manager, wählen Sie **lync**aus, und tippen Sie dann auf **Aufgabe beenden**. Wenn lync nicht aufgeführt ist, tippen Sie auf **Weitere Details** , und suchen Sie unter **Hintergrundprozesse**nach lync.

**So speichern Sie die Protokolle**

1.  Öffnen Sie die lync Windows Store-App auf dem Gerät.

2.  Versuchen Sie, sich anzumelden.

3.  Streichen Sie von der rechten Seite des Bildschirms. Wenn Sie eine Maus verwenden, zeigen Sie auf die obere rechte Ecke des Bildschirms, und bewegen Sie dann den Mauszeiger nach unten auf dem Bildschirm.

4.  Wählen Sie **Einstellungen**aus, wählen Sie **Info**aus, und wählen Sie dann **Protokolle speichern**aus.

</div>

</div>

<span> </span>

</div>

</div>

</div>

