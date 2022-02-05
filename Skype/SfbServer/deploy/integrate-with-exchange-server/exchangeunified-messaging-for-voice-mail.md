---
title: Konfigurieren Exchange Server Unified Messaging für Skype for Business Server Voicemail
ms.reviewer: null
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 2/11/2019
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
  - NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.assetid: 1be9c4f4-fd8e-4d64-9798-f8737b12e2ab
description: 'Zusammenfassung: Konfigurieren Exchange Server Unified Messaging für Skype for Business Server Voicemail.'
---

# <a name="configure-exchange-server-unified-messaging-for-skype-for-business-server-voice-mail"></a>Konfigurieren Exchange Server Unified Messaging für Skype for Business Server Voicemail
 
**Zusammenfassung:** Konfigurieren sie Exchange Server Unified Messaging für Skype for Business Server Voicemail.
  
Skype for Business Server ermöglicht es Ihnen, Voicemailnachrichten in Exchange Server 2016 oder Exchange Server 2013 zu speichern. Diese Voicemailnachrichten werden dann als E-Mail-Nachrichten in den Postfächern Ihrer Benutzer angezeigt. 

> [!NOTE]
> Exchange unified messaging as previously known is no longer available in Exchange 2019, but you can still use Telefonsystem to record voicemail messages and then leave the recording in a user's Exchange mailbox. Weitere Informationen finden Sie [unter Plan Cloud-Voicemail Service](../../../sfbhybrid/hybrid/plan-cloud-voicemail.md).
  
Wenn Sie die Server-zu-Server-Authentifizierung zwischen Skype for Business Server und Exchange Server 2016 oder Exchange Server 2013 bereits konfiguriert haben, können Sie Unified Messaging einrichten. Dazu müssen Sie zunächst einen neuen Unified Messaging-Wählplan für Ihre Exchange Server erstellen und zuweisen. Beispielsweise konfigurieren diese beiden Befehle (die in der Exchange Verwaltungsshell ausgeführt werden) einen neuen dreistelligen Wählplan für Exchange:
  
```powershell
New-UMDialPlan -Name "RedmondDialPlan" -VoIPSecurity "Secured" -NumberOfDigitsInExtension 3 -URIType "SipName" -CountryOrRegionCode 1
Set-UMDialPlan "RedmondDialPlan" -ConfiguredInCountryOrRegionGroups "Anywhere,*,*,*" -AllowedInCountryOrRegionGroups "Anywhere"
```

Im ersten Befehl im Beispiel geben der Parameter "VoIPSecurity" und der Parameterwert "Secured" an, dass der Signalkanal mithilfe von TLS (Transport Layer Security) verschlüsselt wird. Der URI-Typ "SipName" gibt an, dass Nachrichten unter Verwendung des SIP-Protokolls gesendet und empfangen werden, und der Wert "1" für "CountryOrRegionCode" gibt an, dass der Wählplan für die USA gilt.
  
Im zweiten Befehl gibt der an den Parameter "ConfiguredInCountryOrRegionGroups" übergebene Parameterwert die länderinternen Gruppen an, die mit diesem Wählplan verwendet werden können. Der Parameterwert "Anywhere,\*"\*\* legt Folgendes fest:
  
- Gruppenname ("Anywhere")
    
- AllowedNumberString (\*ein Platzhalterzeichen, das angibt, dass eine beliebige Zahlenzeichenfolge zulässig ist)
    
- DialNumberString (\*ein Platzhalterzeichen, das angibt, dass eine gewählte Nummer zulässig ist)
    
- TextComment (\*ein Platzhalterzeichen, das angibt, dass textbefehle zulässig sind)
    
> [!NOTE]
> Durch das Erstellen eines neuen Wählplans wird auch eine Standardpostfachrichtlinie erstellt. 
  
Nach dem Erstellen und Konfigurieren des neuen Wählplans müssen Sie den neuen Wählplan zu Ihrem Unified Messaging-Server hinzufügen und dann den Startmodus dieses Servers ändern. Insbesondere müssen Sie den Startmodus auf "Dual" festlegen. Sie können beide Aufgaben in der Exchange Verwaltungsshell ausführen:
  
```powershell
Set-UmService -Identity "atl-exchangeum-001.litwareinc.com" -DialPlans "RedmondDialPlan" -UMStartupMode "Dual"
```

Nachdem der Unified Messaging-Server konfiguriert wurde, sollten Sie als Nächstes das Cmdlet Enable-ExchangeCertificate ausführen, um sicherzustellen, dass Ihr Exchange Zertifikat auf den Unified Messaging-Dienst angewendet wird:
  
```powershell
Enable-ExchangeCertificate -Server "atl-umserver-001.litwareinc.com" -Thumbprint "EA5A332496CC05DA69B75B66111C0F78A110D22d" -Services "SMTP","IIS","UM"
```

Nachdem das Zertifikat ordnungsgemäß zugewiesen wurde, müssen Sie den MsExchangeUM-Dienst auf dem Unified Messaging-Server beenden und neu starten. Dieser Dienst muss jedes Mal beendet und neu gestartet werden, wenn der Startmodus geändert wurde.
  
Wenn die Konfiguration des UM-Servers abgeschlossen ist, können Sie den UM-Anrufrouter konfigurieren:
  
```powershell
Set-UMCallRouterSettings -Server "atl-exchange-001.litwareinc.com" -UMStartupMode "Dual" -DialPlans "RedmondDialPlan" 
Enable-ExchangeCertificate -Server "atl-umserver-001.litwareinc.com" -Thumbprint "45BAA32496CC891169B75B9811320F78A1075DDA" -Services "IIS","UMCallRouter"
```

Da der Startmodus geändert wurde, müssen Sie den MsExchangeUMCR-Dienst auf dem Computer mit dem UM-Anrufrouter beenden und neu starten.
  
Erstellen Sie zum Abschließen der Unified Messaging-Einrichtung eine UM-Postfachrichtlinie, und aktivieren Sie dann mit dieser Richtlinie Benutzer für Unified Messaging. Sie können eine Postfachrichtlinie mit folgendem Befehl erstellen:
  
```powershell
New-UMMailboxPolicy -Name "RedmondMailboxPolicy" -AllowedInCountryOrRegionGroups "Anywhere"
```

Sie können für einen Benutzer Unified Messaging mit einem Befehl wie diesem aktivieren:
  
```powershell
Enable-UMMailbox -Extensions 100 -SIPResourceIdentifier "kenmyer@litwareinc.com" -Identity "litwareinc\kenmyer" -UMMailboxPolicy "RedmondMailboxPolicy"
```

Im vorhergehenden Befehl steht der Parameter "Extensions" für die Durchwahlnummer des Benutzers. In diesem Beispiel besitzt der Benutzer die Durchwahl 100.
  
Nach dem Aktivieren des Postfachs sollte der Benutzer "kenmyer@litwareinc.com" Exchange Unified Messaging verwenden können. Sie können überprüfen, ob der Benutzer eine Verbindung mit Exchange UM herstellen kann, indem Sie das Cmdlet ["Test-CsExUMConnectivity](/powershell/module/skype/test-csexumconnectivity)" in der Skype for Business Server-Verwaltungsshell ausführen:
  
```powershell
$credential = Get-Credential "litwareinc\kenmyer"
Test-CsExUMConnectivity -TargetFqdn "atl-cs-001.litwareinc.com" -UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential
```

Wenn ein zweiter Benutzer ist, für den Unified Messaging aktiviert wurde, können Sie mit dem Cmdlet [Test-CsExUMVoiceMail](/powershell/module/skype/test-csexumvoicemail) sicherstellen, dass dieser zweite Benutzer eine Voicemailnachricht für den ersten Benutzer hinterlassen kann.
  
```powershell
$credential = Get-Credential "litwareinc\pilar"
Test-CsExUMVoiceMail -TargetFqdn "atl-cs-001.litwareinc.com" -ReceiverSipAddress "sip:kenmyer@litwareinc.com" -SenderSipAddress "sip:pilar@litwareinc.com" -SenderCredential $credential
```



## <a name="configuring-unified-messaging-on-microsoft-exchange-server"></a>Konfigurieren von Unified Messaging auf Microsoft Exchange Server 
> [!IMPORTANT]
> Wenn Sie Exchange Unified Messaging (UM) verwenden möchten, um Anrufbeantwortungs-, Outlook Voice Access- oder automatische Telefonzentralendienste für Enterprise-VoIP Benutzer bereitzustellen, lesen Sie ["Plan for Exchange Unified Messaging integration in Skype for Business](../../plan-your-deployment/integrate-with-exchange/unified-messaging.md)", und folgen Sie dann den Anweisungen in diesem Abschnitt. 

Um Exchange Unified Messaging (UM) für die Arbeit mit Enterprise-VoIP zu konfigurieren, müssen Sie die folgenden Aufgaben ausführen:

- Konfigurieren von Zertifikaten auf dem Server, auf dem Exchange Unified Messaging (UM)-Dienste ausgeführt werden
  > [!NOTE]
  > Fügen Sie alle Clientzugriffs- und Postfachserver allen UM-SIP-URI-Wählplänen hinzu. Wenn dies nicht der Fall ist, funktioniert das Routing ausgehender Anrufe nicht wie erwartet. 
- Erstellen Sie nach Bedarf einen oder mehrere UM-SIP-URI-Wählpläne zusammen mit den Telefonnummern für den Abonnentenzugriff, und erstellen Sie dann entsprechende L-Wählpläne.

- Verwenden Sie das skript exchucutil.ps1 für Folgendes:
    - Erstellen von UM-IP-Gateways
    - Erstellen von UM-Sammelanschlüssen
    - Erteilen Sie Skype for Business Server Berechtigung zum Lesen von UM Active Directory Domain Services-Objekten.
- Erstellen sie ein UM-Objekt für die automatische Telefonzentrale.
- Erstellen sie ein Abonnentenzugriffsobjekt.
- Erstellen Sie einen SIP-URI für jeden Benutzer, und verknüpfen Sie Benutzer mit einem UM-SIP-URI-Wählplan.

### <a name="requirements-and-recommendations"></a>Anforderungen und Empfehlungen

Bevor Sie beginnen, wird in der Dokumentation in diesem Abschnitt davon ausgegangen, dass Sie die folgenden Exchange Rollen bereitgestellt haben: Clientzugriff und Postfach. In Microsoft Exchange Server wird Exchange UM als Dienst auf diesen Servern ausgeführt.

Beachten Sie auch Folgendes:
- Wenn Exchange UM in mehreren Gesamtstrukturen installiert ist, müssen die Exchange Server Integrationsschritte für jede UM-Gesamtstruktur ausgeführt werden. Darüber hinaus muss jede UM-Gesamtstruktur so konfiguriert werden, dass sie der Gesamtstruktur vertraut, in der Skype for Business Server bereitgestellt wird, und die Gesamtstruktur, in derSkype for Business Server bereitgestellt wird, muss so konfiguriert sein, dass sie jeder UM-Gesamtstruktur vertraut.
- Integrationsschritte werden sowohl für die Exchange Server Rollen, auf denen Unified Messaging-Dienste ausgeführt werden, als auch auf dem Server, auf dem Skype for Business Server ausgeführt wird, ausgeführt. Führen Sie die Exchange Server Integrationsschritte für Unified Messaging aus, bevor Sie die Integrationsschritte für Lync Server 2013 ausführen.
  > [!NOTE]
  > Informationen dazu, welche Integrationsschritte auf welchen Servern und mit welchen Administratorrollen ausgeführt werden, finden Sie in der [Übersicht über den Bereitstellungsprozess für die Integration von lokalem Unified Messaging und Skype for Business](../../plan-your-deployment/integrate-with-exchange/deployment-overview.md). 

Die folgenden Tools müssen auf jedem Server verfügbar sein, auf dem Exchange UM ausgeführt wird:
- Exchange-Verwaltungsshell
- Das Skript exchucutil.ps1, mit dem die folgenden Aufgaben ausgeführt werden:
    - Erstellt ein UM-IP-Gateway für jeden Skype for Business Server.
    - Erstellen eines Sammelanschlusses für jedes Gateway. Der Pilotbezeichner jeder Sammelanschlüsse gibt den UM-SIP-URI-Wählplan an, der vom Front-End-Pool oder Standard Edition Server verwendet wird, der dem Gateway zugeordnet ist.
    - Gewährt Skype for Business Server Berechtigung zum Lesen Exchange UM-Objekte in Active Directory Domain Services.



### <a name="configure-unified-messaging-on-microsoft-exchange-with-exchucutilps1"></a>Konfigurieren von Unified Messaging auf Microsoft Exchange mit ExchUCUtil.ps1 

Wenn Sie Microsoft Skype for Business Server in Exchange Unified Messaging (UM) integrieren, müssen Sie das skript ExchUcUtil.ps1 in der Shell ausführen. Das Skript "ExchUcUtil.ps1" führt Folgendes aus:

- Erstellt ein UM-IP-Gateway für jeden Skype for Business Server Pool.

> [!IMPORTANT]
> Das ExchUCUtil.ps1-Skript erstellt ein oder mehrere UM-IP-Gateways. Sie müssen ausgehende Anrufe für alle UM-IP-Gateways deaktivieren, außer dem einen Gateway, das durch das Skript erstellt wurde. Dazu gehört auch das Deaktivieren von ausgehenden Anrufen auf UM-IP-Gateways, die vor dem Ausführen des Skripts erstellt wurden. 

- Es erstellt einen UM-Sammelanschluss für jedes UM-IP-Gateway. Der Pilotbezeichner jeder Sammelanschlüsse gibt den UM-SIP-URI-Wählplan an, der vom Skype for Business Server Front-End-Pool oder Standard Edition Servers verwendet wird, der dem UM-IP-Gateway zugeordnet ist.
- Gewährt Skype for Business Server Berechtigung zum Lesen von Active Directory UM-Containerobjekten wie UM-Wählplänen, automatischen Telefonzentralen, UM-IP-Gateways und UM-Sammelanschlüssen.
  > [!IMPORTANT]
  > Jede UM-Gesamtstruktur muss so konfiguriert sein, dass sie der Gesamtstruktur vertraut, in der Skype for Business Server bereitgestellt wird, und die Gesamtstruktur, in der Skype for Business Server 2013 bereitgestellt wird, muss so konfiguriert werden, dass jeder UM-Gesamtstruktur vertraut wird. Wenn Exchange UM in mehreren Gesamtstrukturen installiert ist, müssen die Exchange Server Integrationsschritte für jede UM-Gesamtstruktur ausgeführt werden, oder Sie müssen die Skype for Business Server Domäne angeben. Beispiel: ExchUcUtil.ps1 –Forest:\<lync-domain-controller-fqdn>. 

### <a name="use-the-shell-to-run-the-exchucutilps1-script"></a>Ausführen des Skripts "ExchUcUtil.ps1" mithilfe der Shell

Führen Sie das Skript ExchUcUtil.ps1 auf jedem Exchange Server in Ihrer Organisation aus, der sich in derselben Topologie wie Skype for Business Server befindet. Sie können das Skript in der Shell auf einem Postfachserver oder über die Windows Remote-PowerShell auf einem Clientzugriffsserver ausführen. Wenn Sie das Skript auf einem Clientzugriffsserver in Ihrer Organisation ausführen, leitet der Clientzugriffsserver die Windows Remote-PowerShell-Sitzung über einen Proxy an einen Postfachserver in der Organisation weiter.
> [!IMPORTANT]
> Das ExchUCUtil.ps1-Skript erstellt ein oder mehrere UM-IP-Gateways. Sie müssen ausgehende Anrufe für alle UM-IP-Gateways deaktivieren, außer dem einen Gateway, das durch das Skript erstellt wurde. Dazu gehört auch das Deaktivieren von ausgehenden Anrufen auf UM-IP-Gateways, die vor dem Ausführen des Skripts erstellt wurden. Informationen zum Deaktivieren von ausgehenden Anrufen auf UM-IP-Gateways finden Sie unter Deaktivieren Sie ausgehende Anrufe für UM-IP-gateways.[!IMPORTANT]
> Sie benötigen die Berechtigungen der Rolle "Exchange-Organisationsverwaltung" oder müssen ein Mitglied der Sicherheitsgruppe "Exchange-Organisationsadministratoren" sein, um das Skript auszuführen. 

1. Öffnen Sie die Exchange-Verwaltungsshell.
2. Geben Sie an der C:\Windows\System32-Eingabeaufforderung **"cd \<drive letter>:\Program Files\Microsoft\Exchange Server\V15\Scripts>.ExchUcUtil.ps1**" ein, und drücken Sie die EINGABETASTE.

#### <a name="how-do-you-know-this-worked"></a>Woher wissen Sie, dass dieses Verfahren erfolgreich war?

Gehen Sie folgendermaßen vor, um zu überprüfen, ob das Skript "ExchUcUtul.ps1" erfolgreich abgeschlossen wurde:
- Verwenden Sie das Cmdlet Get-UMIPGateway oder die Exchange-Verwaltungskonsole, um die neu erstellten UM-IP-Gateways anzuzeigen.
- Verwenden Sie das Cmdlet Get-UMHuntGroup oder die Exchange-Verwaltungskonsole, um die neu erstellten UM-Sammelanschlüsse anzuzeigen.

### <a name="configure-certificates-on-the-server-running-exchange-server-unified-messaging"></a>Konfigurieren von Zertifikaten auf dem Server, auf dem Exchange Server Unified Messaging ausgeführt wird
 
Wenn Sie Exchange Unified Messaging (UM) bereitgestellt haben, wie unter Planning for Exchange Unified Messaging integration in Skype for Business Server in der Planungsdokumentation beschrieben, und Sie Exchange UM-Features für Enterprise-VoIP  Benutzer in Ihrer Organisation können die folgenden Verfahren verwenden, um das Zertifikat auf dem Server zu konfigurieren, auf dem Exchange UM ausgeführt wird.

> [!IMPORTANT]
> Bei internen Zertifikaten müssen sowohl die Server, auf denen Skype for Business Server ausgeführt wird, als auch die Server, auf denen Microsoft Exchange ausgeführt wird, vertrauenswürdige Stammzertifizierungsstellenzertifikate aufweisen, die sich gegenseitig als vertrauenswürdig vertrauenswürdig gelten. Die Zertifizierungsstelle kann entweder identisch oder eine andere Zertifizierungsstelle sein, solange auf den Servern das Stammzertifikat der Zertifizierungsstelle in ihrem Zertifikatspeicher der vertrauenswürdigen Stammzertifizierungsstelle registriert ist. 

Die Exchange Server muss mit einem Serverzertifikat konfiguriert werden, um eine Verbindung mit Skype for Business Server herstellen zu können:
1. Laden Sie das Zertifizierungsstellenzertifikat für den Exchange Server-Computer herunter.
2. Installieren Sie das Zertifizierungsstellenzertifikat für den Exchange Server-Computer.
3. Vergewissern Sie sich, dass sich die Zertifizierungsstelle in der Liste der vertrauenswürdigen Stammzertifizierungsstellen des Computers mit Exchange Server befindet.
4. Erstellen Sie eine Zertifikatanforderung für den Computer mit Exchange Server, und installieren Sie das Zertifikat. 
5. Weisen Sie das Zertifikat für den Computer mit Exchange Server zu.


**So laden Sie das Zertifizierungsstellenzertifikat herunter:**

1. Klicken Sie auf dem Server, auf dem Exchange UM ausgeführt wird, auf **"Start**", klicken Sie auf **"Ausführen**", geben **Sie\<name of your Issuing CA Server> http:///certsrv** ein, und klicken Sie dann auf **"OK**".
2. Klicken Sie unter "Aufgabe auswählen" auf " **Zertifizierungsstellenzertifikat, Zertifikatkette oder CRL herunterladen**".
3. Wählen **Sie unter "Zertifizierungsstellenzertifikat, Zertifikatkette oder CRL herunterladen**" die **Codierungsmethode für Basis 64** aus, und klicken Sie dann auf **"Zertifizierungsstellenzertifikat herunterladen**".
   > [!NOTE]
   > In diesem Schritt können Sie auch Distinguished Encoding Rules (DER)-Codierung angeben. Beachten Sie Folgendes, wenn Sie die DER-Codierung auswählen: Der Dateityp im nächsten Schritt dieses Verfahrens und in Schritt 10 unter **So installieren Sie das Zertifizierungsstellenzertifikat** ist P7B und nicht CER. 
4. Klicken Sie im Dialogfeld **Dateidownload** auf **Speichern**, und speichern Sie die Datei auf der Festplatte des Servers. (Die Datei hat entweder die Dateierweiterung CER oder P7B. Dies richtet sich nach der Codierung, die Sie im vorherigen Schritt gewählt haben.)

**So installieren Sie das Zertifizierungsstellenzertifikat:**

1. Öffnen Sie auf dem Server, auf dem Exchange UM ausgeführt wird, die Microsoft Management Console (MMC), indem Sie auf **"Start**", "**Ausführen**", "**mmc**" in das Feld "Öffnen" und dann auf "**OK**" klicken.
2. Klicken Sie im Menü **Datei** auf **Snap-In hinzufügen/entfernen** und dann auf **Hinzufügen**.
3. Klicken Sie im Feld **Eigenständiges Snap-In hinzufügen** auf **Zertifikate** und anschließend auf **Hinzufügen**.
4. Klicken Sie im Dialogfeld **Zertifikat-Snap-In** auf **Computerkonto** und anschließend auf **Weiter**.
5. Überprüfen Sie im Dialogfeld " **Computer auswählen** ", ob das Kontrollkästchen **"Lokaler Computer: (der Computer, auf dem diese Konsole ausgeführt wird) aktiviert ist** , und klicken Sie dann auf **Fertig stellen**.
6. Klicken Sie auf **Schließen** und dann auf **OK**. 
7. Erweitern Sie in der Konsolenstruktur den Eintrag **Zertifikate (Lokaler Computer)** und dann **Vertrauenswürdige Stammzertifizierungsstellen**, und klicken Sie anschließend auf **Zertifikate**.
8. Klicken Sie mit der rechten Maustaste auf **Zertifikate**, und klicken Sie dann auf **Alle Tasks** und **Importieren**.
9. Klicken Sie auf **Weiter**. 
10. Klicken Sie auf **Durchsuchen**, um auf die Datei zuzugreifen, und klicken Sie dann auf **Weiter**. (Die Datei hat entweder die Dateierweiterung CER oder P7B. Dies richtet sich nach der Codierung, die Sie in Schritt 3 unter **So laden Sie das Zertifizierungsstellenzertifikat herunter** gewählt haben.)
11. Klicken Sie im folgenden Speicher auf **"Alle Zertifikate** platzieren".
12. Klicken Sie auf **Durchsuchen**, und wählen Sie **Vertrauenswürdige Stammzertifizierungsstellen** aus. 
13. Klicken Sie auf **Weiter**, um die Einstellungen zu überprüfen, und klicken Sie dann auf **Fertig stellen**. 


**So überprüfen Sie, ob die Zertifizierungsstelle in der Liste der vertrauenswürdigen Stammzertifizierungsstellen enthalten ist:**

1. Erweitern Sie auf dem Server, auf dem Exchange UM ausgeführt wird, in MMC Zertifikate (lokaler Computer), Vertrauenswürdige Stammzertifizierungsstellen, und klicken Sie dann auf "Zertifikate".
2. Überprüfen Sie im Detailbereich, ob Ihre Zertifizierungsstelle in der Liste der vertrauenswürdigen Zertifizierungsstellen aufgeführt ist.