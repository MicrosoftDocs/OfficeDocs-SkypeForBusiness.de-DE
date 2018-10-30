---
title: Bereitstellen der Lync-Windows Store-App
TOCTitle: Bereitstellen der Lync-Windows Store-App
ms:assetid: 9e00aaf4-15f9-4356-9ed7-5a58a2bfa043
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ822971(v=OCS.15)
ms:contentKeyID: 52056417
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Bereitstellen der Lync-Windows Store-App

 

_**Letztes Änderungsdatum des Themas:** 2016-12-08_

Bevor Sie die Windows Store-App für Lync für die Benutzer zur Verfügung stellen, müssen Sie sicherstellen, dass Ihre Bereitstellung den [Anforderungen für Lync Windows Store-App](lync-server-2013-lync-windows-store-app-requirements.md) gerecht wird. Details zur Konfiguration von Lync Server 2013 für die Unterstützung von Windows Store-App für Lync finden Sie im NextHop Blog-Artikel "Lync Server Autodiscover and the Lync Windows Store App" unter [http://go.microsoft.com/fwlink/?LinkId=271966](http://go.microsoft.com/fwlink/?linkid=271966) (in Englisch). Nachdem die Serverumgebung ordnungsgemäß konfiguriert wurde, können Sie die Benutzer anweisen, die Lync-App aus dem Windows Store herunterzuladen, indem sie nach "Lync" suchen.

## Aktivieren der mehrstufigen Authentifizierung für die Windows Store-App für Lync

Mit Kumulatives Update für Lync Server 2013: Juni 2013 wird die mehrstufige Authentifizierung für Windows Store-App für Lync-Clients unterstützt. Zusätzlich zu Benutzername und Kennwort können Sie zusätzliche Authentifizierungsmethoden erforderlich machen, beispielsweise Smartcards oder PINs, um externen Benutzer zu authentifizieren, wenn sie sich bei Lync-Besprechungen anmelden. Sie können die mehrstufige Authentifizierung aktivieren, indem Sie Active Directory-Verbunddienste-Verbundserver bereitstellen und die passive Authentifizierung in Lync Server 2013 aktivieren. Nach der Konfiguration von Active Directory-Verbunddiensten werden externe Benutzer, die versuchen, sich bei Lync-Besprechungen anzumelden, auf einer Webseite mit Informationen zur mehrstufigen Authentifizierung für Active Directory-Verbunddienste angezeigt, die den Benutzernamen und das Kennwortniveau zusammen mit den zusätzlichen von Ihnen konfigurierten Authentifizierungsmethoden enthält.


> [!IMPORTANT]
> Im Folgenden finden Sie wichtige Erwägungen, wenn Sie planen, Active Directory-Verbunddienste für die mehrstufige Authentifizierung in Windows Store-App für Lync zu konfigurieren: 
> <UL>
> <LI>
> <P>Die Mindestvoraussetzung ist Lync Server 2013 mit Kumulatives Update für Lync Server&nbsp;2013: Juni&nbsp;2013. Für Lync 2013-Desktopclients ist Kumulatives Update für Lync Server&nbsp;2013: Juni&nbsp;2013 nicht erforderlich, also kann der Eindruck entstehen, dass die passive Authentifizierung funktioniert, da Lync 2013-Clients in der Lage sind, die Authentifizierung durchzuführen. Das Authentifizierungsverfahren für Windows Store-App für LyncClients kann jedoch nicht erfolgreich abgeschlossen werden, und es wird weder eine Benachrichtigung, noch eine Fehlermeldung angezeigt.</P>
> <LI>
> <P>Der Server muss so konfiguriert sein, dass die passive Authentifizierung der einzige angebotene Authentifizierungstyp ist.</P>
> <LI>
> <P>Wenn Sie Hardwaregeräte zum Lastenausgleich verwenden, aktivieren Sie die Dauerhaftigkeit von Cookies auf den Geräten zum Lastenausgleich, sodass alle Anforderungen des Windows Store-App für Lync-Clients vom selben Front-End-Server verarbeitet werden.</P>
> <LI>
> <P>Wenn Sie eine Vertrauensstellung der vertrauenden Seite zwischen Lync Server und Active Directory-Verbunddienste-Servern einrichten, weisen Sie eine Gültigkeitsdauer des Token zu, die die maximale Länge Ihrer Lync-Besprechungen umfasst. Gewöhnlich genügt eine Gültigkeitsdauer des Token von 240 Minuten.</P></LI></UL>



**Konfigurieren der mehrstufigen Authentifizierung**

1.  Installieren Sie eine Active Directory-Verbunddienste-Verbundserverrolle. Details können Sie dem Bereitstellungshandbuch für AD FS 2.0 unter [http://go.microsoft.com/fwlink/?linkid=267511\&clcid=0x407](http://go.microsoft.com/fwlink/?linkid=267511%26clcid=0x407) entnehmen.

2.  Erstellen Sie Zertifikate für AD FS. Weitere Informationen finden Sie im Abschnitt "Verbundserverzertifikate" des Themas "Planen und Bereitstellen von AD FS für die Verwendung beim einmaligen Anmelden" unter [http://go.microsoft.com/fwlink/p/?LinkId=285376](http://go.microsoft.com/fwlink/p/?linkid=285376).

3.  Führen Sie aus der Windows PowerShell-Befehlszeilenschnittstelle den folgenden Befehl aus:
    
        add-pssnapin Microsoft.Adfs.powershell

4.  Richten Sie durch Ausführen des folgenden Befehls eine Partnerschaft ein:
    
        Add-ADFSRelyingPartyTrust -Name ContosoApp -MetadataURL https://lyncpool.contoso.com/passiveauth/federationmetadata/2007-06/federationmetadata.xml

5.  Legen Sie die folgenden vertrauenswürdigen Parteienregeln fest:
    
        $IssuanceAuthorizationRules = '@RuleTemplate = "AllowAllAuthzRule" => issue(Type = "http://schemas.contoso.com/authorization/claims/permit", Value = "true");'$IssuanceTransformRules = '@RuleTemplate = "PassThroughClaims" @RuleName = "Sid" c:[Type == "http://schemas.contoso.com/ws/2008/06/identity/claims/primarysid"]=> issue(claim = c);'

       &nbsp;
    
        Set-ADFSRelyingPartyTrust -TargetName ContosoApp -IssuanceAuthorizationRules $IssuanceAuthorizationRules -IssuanceTransformRules $IssuanceTransformRules

       &nbsp;
    
        Set-CsWebServiceConfiguration -UseWsFedPassiveAuth $true -WsFedPassiveMetadataUri https://dc.contoso.com/federationmetadata/2007-06/federationmetadata.xml

## Bekannte Probleme, die eine Anmeldung verhindern können

## Datum und Uhrzeit sind auf dem Gerät, auf dem Windows Store-App für Lync ausgeführt wird, nicht ordnungsgemäß konfiguriert

Die Zeiteinstellung auf dem Gerät muss mit der Zeiteinstellung auf dem Lync-Server synchronisiert sein. Dies ist besonders wichtig für Geräte wie Microsoft Surface und andere Geräte, auf denen Windows RT ausgeführt wird und die nicht einer Domäne beigetreten sind. Um die Uhrzeit auf diesen Geräten automatisch über einen Zeitserver einzustellen, führen Sie den folgenden Befehl an einer erweiterten Befehlseingabeaufforderung auf dem Gerät aus :

    w32tm /resync

## Windows Store-App für Lync kann nicht auf den Lync-Server oder auf Dienste zugreifen

Windows Store-App für Lync ist möglicherweise nicht in der Lage, über Netzwerkadapter wie 4G LTE USB-Modems auf den Lync-Server oder auf Dienste zuzugreifen, die in Windows 8 nicht als physische Geräte registriert sind. In Windows Store-App für Lync tritt dieses Problem möglicherweise auch dann auf, wenn Desktop-Apps und Browsers in der Lage sind, auf andere Server und Websites zuzugreifen.

## Die Lync-Windows Store-App kann sich nicht beim Lync Server 2010- und Office Communications Server 2007 R2-Edgeserver anmelden

Wenn Ihre Topologie aus Lync Server 2010 mit Office Communications Server 2007 R2-Edgeserver besteht, müssen Sie die aktualisierte Version des Topologie-Generators ausführen, der mit dem kumulativen Updaten von Lync Server 2010 aus Juli 2013 bereitsteht. Frühere Versionen des Topologie-Generators sind nicht in der Lage, die erforderliche Zuordnung zum Office Communications Server 2007-Edgeserver zu erstellen, sodass sich Lync-Windows Store-App-Clients nicht anmelden können. In diesem Fall sind die folgenden Schritte erforderlich:

1.  Installieren Sie das kumulative Update für Lync Server 2010 aus Juli 2013 auf den Lync Server 2010-Pools und den Lync Server 2010-Directors.

2.  Aktualisieren Sie die Konfiguration der Lync-AutoErmittlung so, dass der externe SIP-Eintrittpunkt gleich der Edgeserveradresse ist. Gehen Sie dazu wie folgt vor:
    
    1.  Öffnen Sie Lync Server-Verwaltungsshell.
    
    2.  Führen Sie den folgenden Befehl aus:
        
            Set-CsAutodiscoverConfiguration -ExternalSipClientAccessFqdn <FQDN of server used for external client access> -ExternalSipClientAccessPort 443

## Die Lync Windows Store-App kann wegen eines Fehlers bei der Überprüfung des Zertifikatnamens nicht angemeldet werden

Für Office 365-Benutzer, bei denen nicht die neueste Version von Windows Store-App für Lync ausgeführt wird, kann ein Anmeldeproblem auftreten. Zu diesem Problem kommt es im Allgemeinen bei der Verwendung mehrerer Domänen (zum Beispiel wenn der SIP-URI **userA@domainZ.com** ist, der Edgeserver aber **sip.domainX.com** ist). Zum Beheben des Problems sollten Benutzer die neueste Version von Windows Store-App für Lync installieren, für die auch Windows 8.1 erforderlich ist.

## Verwenden der Windows Store-App für Lync-Protokollen für die Problembehandlung

Sie können die auf dem Gerät generierten Protokolle für die Problembehandlung verwenden. Die Protokollen sind im folgendem Ordner gespeichert:

%LocalAppData%\\Packages\\Microsoft.LyncMX\_8wekyb3d8bbwe\\LocalState\\Tracing

Bevor Sie die Protokolle von einem Benutzer anfordern, überprüfen Sie, ob die Protokollierung aktiviert ist, und bitten Sie die Benutzer dann, die Protokolle zu speichern, sodass alle im Arbeitsspeicher gespeicherten Informationen ebenfalls in Dateien auf der Festplatte gespeichert werden.

**So aktivieren Sie die Protokollierung**

1.  Öffnen Sie Windows Store-App für Lync auf dem Gerät.

2.  Wischen Sie vom rechten Bildschirmrand aus. Wenn Sie eine Maus verwenden, zeigen Sie auf die obere rechte Ecke des Bildschirms, und bewegen Sie dann den Mauszeiger über den Bildschirm nach unten.

3.  Wählen Sie **Einstellungen** \> **Optionen** aus, und legen Sie dann **Diagnoseprotokolle** auf **Ein** fest.

4.  Wenn **Diagnoseprotokolle** zuvor deaktiviert war, müssen Sie Lync neu starten. Gehen Sie folgendermaßen vor, um Lync neu zu starten:
    
      - Starten Sie das Gerät neu.
    
      - Beenden Sie die Lync-Task, und starten Sie die App erneut. Öffnen Sie zum Beenden der Task den Windows Task-Manager, wählen Sie **Lync** aus, und tippen Sie dann auf **Task beenden**. Wenn Lync nicht aufgelistet ist, tippen Sie auf **Mehr Details**, und wählen Sie dann unter **Hintergrundprozesse** "Lync" aus

**So speichern Sie die Protokolle**

1.  Öffnen Sie Windows Store-App für Lync auf dem Gerät.

2.  Versuchen Sie, sich anzumelden.

3.  Wischen Sie vom rechten Bildschirmrand aus. Wenn Sie eine Maus verwenden, zeigen Sie auf die obere rechte Ecke des Bildschirms, und bewegen Sie dann den Mauszeiger über den Bildschirm nach unten.

4.  Wählen Sie **Einstellungen** \> **Info** \> **Protokolle speichern** aus.

