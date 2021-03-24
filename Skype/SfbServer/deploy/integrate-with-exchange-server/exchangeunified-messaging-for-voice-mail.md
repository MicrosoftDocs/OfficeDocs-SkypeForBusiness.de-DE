---
title: Konfigurieren Exchange Server Unified Messaging für Skype for Business Server Voicemail
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 2/11/2019
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 1be9c4f4-fd8e-4d64-9798-f8737b12e2ab
description: 'Zusammenfassung: Konfigurieren Exchange Server Unified Messaging für Skype for Business Server-Voicemail.'
ms.openlocfilehash: 24bad46103433f6af9caebbe1894b1b3b2aa83d9
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51109821"
---
# <a name="configure-exchange-server-unified-messaging-for-skype-for-business-server-voice-mail"></a>Konfigurieren Exchange Server Unified Messaging für Skype for Business Server Voicemail
 
**Zusammenfassung:** Konfigurieren Exchange Server Unified Messaging für Skype for Business Server Voicemail.
  
Mit Skype for Business Server können Sie Voicemailnachrichten in Exchange Server 2016 oder Exchange Server 2013 speichern. Diese Voicemailnachrichten werden dann als E-Mail-Nachrichten in den Posteingangen Ihrer Benutzer angezeigt. 

> [!NOTE]
> Exchange Unified Messaging, wie zuvor bekannt, ist in Exchange 2019 nicht mehr verfügbar, Sie können jedoch weiterhin das Telefonsystem verwenden, um Voicemailnachrichten zu erfassen und die Aufzeichnung dann im Exchange-Postfach eines Benutzers zu be lassen. Weitere [Informationen finden Sie unter Plan Cloud Voicemail service.](../../../sfbhybrid/hybrid/plan-cloud-voicemail.md)
  
Wenn Sie die Server-zu-Server-Authentifizierung zwischen Skype for Business Server und Exchange Server 2016 oder Exchange Server 2013 bereits konfiguriert haben, können Sie Unified Messaging einrichten. Dazu müssen Sie zunächst einen neuen Unified Messaging-Wählplan für Ihre Exchange Server. Beispielsweise konfigurieren diese beiden Befehle (ausgeführt in der Exchange-Verwaltungsshell) einen neuen 3-stelligen Wählplan für Exchange:
  
```powershell
New-UMDialPlan -Name "RedmondDialPlan" -VoIPSecurity "Secured" -NumberOfDigitsInExtension 3 -URIType "SipName" -CountryOrRegionCode 1
Set-UMDialPlan "RedmondDialPlan" -ConfiguredInCountryOrRegionGroups "Anywhere,*,*,*" -AllowedInCountryOrRegionGroups "Anywhere"
```

Im ersten Befehl im Beispiel geben der Parameter VoIPSecurity und der Parameterwert "Secured" an, dass der Signalkanal mithilfe von Transport Layer Security (TLS) verschlüsselt wird. Der URI-Typ "SipName" gibt an, dass Nachrichten unter Verwendung des SIP-Protokolls gesendet und empfangen werden, und der Wert "1" für "CountryOrRegionCode" gibt an, dass der Wählplan für die USA gilt.
  
Im zweiten Befehl gibt der an den Parameter "ConfiguredInCountryOrRegionGroups" übergebene Parameterwert die länderinternen Gruppen an, die mit diesem Wählplan verwendet werden können. Der Parameterwert "Anywhere, \* , , " legt Folgendes \* \* fest:
  
- Gruppenname ("Anywhere")
    
- AllowedNumberString ( , ein Platzhalterzeichen, das angibt, dass \* eine beliebige Zahlenzeichenfolge zulässig ist)
    
- DialNumberString ( , ein Platzhalterzeichen, das angibt, dass eine beliebige gewählte \* Nummer zulässig ist)
    
- TextComment ( \* , ein Platzhalterzeichen, das angibt, dass ein beliebiger Textbefehl zulässig ist)
    
> [!NOTE]
> Durch das Erstellen eines neuen Wählplans wird auch eine Standardpostfachrichtlinie erstellt. 
  
Nach dem Erstellen und Konfigurieren des neuen Wählplans müssen Sie dem Unified #A0 den neuen Wählplan hinzufügen und dann den Startmodus dieses Servers ändern. Insbesondere müssen Sie den Startmodus auf "Dual" festlegen. Sie können beide Aufgaben in der Exchange-Verwaltungsshell ausführen:
  
```powershell
Set-UmService -Identity "atl-exchangeum-001.litwareinc.com" -DialPlans "RedmondDialPlan" -UMStartupMode "Dual"
```

Nachdem der Unified Messaging-Server konfiguriert wurde, sollten Sie das cmdlet Enable-ExchangeCertificate ausführen, um sicherzustellen, dass Ihr Exchange-Zertifikat auf den Unified Messaging-Dienst angewendet wird:
  
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
  
Nach dem Aktivieren des Postfachs sollte der Benutzer "kenmyer@litwareinc.com" Exchange Unified Messaging verwenden können. Sie können überprüfen, ob der Benutzer eine Verbindung mit Exchange UM herstellen kann, indem Sie das [Cmdlet Test-CsExUMConnectivity](/powershell/module/skype/test-csexumconnectivity?view=skype-ps) in der Skype for Business Server Management Shell ausführen:
  
```powershell
$credential = Get-Credential "litwareinc\kenmyer"
Test-CsExUMConnectivity -TargetFqdn "atl-cs-001.litwareinc.com" -UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential
```

Wenn ein zweiter Benutzer ist, für den Unified Messaging aktiviert wurde, können Sie mit dem Cmdlet [Test-CsExUMVoiceMail](/powershell/module/skype/test-csexumvoicemail?view=skype-ps) sicherstellen, dass dieser zweite Benutzer eine Voicemailnachricht für den ersten Benutzer hinterlassen kann.
  
```powershell
$credential = Get-Credential "litwareinc\pilar"
Test-CsExUMVoiceMail -TargetFqdn "atl-cs-001.litwareinc.com" -ReceiverSipAddress "sip:kenmyer@litwareinc.com" -SenderSipAddress "sip:pilar@litwareinc.com" -SenderCredential $credential
```



## <a name="configuring-unified-messaging-on-microsoft-exchange-server"></a>Konfigurieren von Unified Messaging auf Microsoft Exchange Server 
> [!IMPORTANT]
> Wenn Sie Exchange Unified Messaging (UM) zum Bereitstellen von Anrufbeantwortungs-, Outlook Voice Access- oder automatischen Telefonkonferenzdiensten für Enterprise-VoIP-Benutzer verwenden möchten, lesen Sie [Plan for Exchange Unified Messaging integration in Skype for Business,](../../plan-your-deployment/integrate-with-exchange/unified-messaging.md)und befolgen Sie dann die Anweisungen in diesem Abschnitt. 

Zum Konfigurieren von Exchange Unified Messaging (UM) für die Enterprise-VoIP müssen Sie die folgenden Aufgaben ausführen:

- Konfigurieren von Zertifikaten auf dem Server mit Exchange Unified Messaging (UM)-Diensten
  > [!NOTE]
  > Fügen Sie allen UM-SIP-URI-Wählplänen alle Clientzugriffs- und Postfachserver hinzu. Andern falls nicht, funktioniert das Routing ausgehender Anrufe nicht wie erwartet. 
- Erstellen Sie nach Bedarf einen oder mehrere UM-SIP-URI-Wählpläne zusammen mit den Telefonnummern für den Teilnehmerzugriff, und erstellen Sie dann entsprechende L-Wählpläne.

- Verwenden Sie das exchucutil.ps1 Skript für:
    - Erstellen von UM-IP-Gateways
    - Erstellen von UM-Sammelanschlüssen
    - Erteilen Sie Skype for Business Server die Berechtigung zum Lesen von UM Active Directory Domain Services-Objekten.
- Erstellen Sie ein automatisches UM-Attendant-Objekt.
- Erstellen Sie ein Abonnentenzugriffsobjekt.
- Erstellen Sie einen SIP-URI für jeden Benutzer, und verknüpfen Sie Benutzer mit einem UM-SIP-URI-Wählplan.

### <a name="requirements-and-recommendations"></a>Anforderungen und Empfehlungen

Bevor Sie beginnen, wird in der Dokumentation in diesem Abschnitt davon ausgegangen, dass Sie die folgenden Exchange-Rollen bereitgestellt haben: Clientzugriff und Postfach. In Microsoft Exchange Server wird Exchange UM als Dienst auf diesen Servern ausgeführt.

Beachten Sie auch Folgendes:
- Wenn Exchange UM in mehreren Gesamtstrukturen installiert ist, müssen die Exchange Server für jede UM-Gesamtstruktur ausgeführt werden. Darüber hinaus muss jede UM-Gesamtstruktur so konfiguriert sein, dass sie der Gesamtstruktur vertraut, in der Skype for Business Server bereitgestellt wird, und die Gesamtstruktur, in derSkype for Business Server bereitgestellt wird, muss so konfiguriert sein, dass jeder UM-Gesamtstruktur vertraut wird.
- Integrationsschritte werden sowohl für die Exchange Server ausgeführt, in denen Unified Messaging-Dienste ausgeführt werden, als auch auf dem Server, auf dem Skype for Business Server ausgeführt wird. Sie sollten die Schritte Exchange Server Unified Messaging-Integration ausführen, bevor Sie die Lync Server 2013-Integrationsschritte ausführen.
  > [!NOTE]
  > Informationen dazu, welche Integrationsschritte auf welchen Servern und von welchen Administratorrollen ausgeführt werden, finden Sie unter  [Deployment process overview for integrating on-premises Unified Messaging and Skype for Business](../../plan-your-deployment/integrate-with-exchange/deployment-overview.md). 

Die folgenden Tools müssen auf jedem Server mit Exchange UM verfügbar sein:
- Exchange-Verwaltungsshell
- Das Skript exchucutil.ps1, mit dem die folgenden Aufgaben ausgeführt werden:
    - Erstellt ein UM-IP-Gateway für jeden Skype for Business Server.
    - Erstellen eines Sammelanschlusses für jedes Gateway. Die Pilot-ID jeder Sammelsuche gibt den UM-SIP-URI-Wählplan an, der vom Front-End-Pool oder Standard Edition-Server verwendet wird, der dem Gateway zugeordnet ist.
    - Erteilt Skype for Business Server die Berechtigung zum Lesen von Exchange UM-Objekten in Active Directory-Domänendiensten.



### <a name="configure-unified-messaging-on-microsoft-exchange-with-exchucutilps1"></a>Konfigurieren von Unified Messaging in Microsoft Exchange mit ExchUCUtil.ps1 

Wenn Sie Microsoft Skype for Business Server in Exchange Unified Messaging (UM) integrieren, müssen Sie das ExchUcUtil.ps1 in der Shell ausführen. Das Skript "ExchUcUtil.ps1" führt Folgendes aus:

- Erstellt ein UM-IP-Gateway für jeden Skype for Business Server-Pool.

> [!IMPORTANT]
> Das ExchUCUtil.ps1-Skript erstellt ein oder mehrere UM-IP-Gateways. Sie müssen ausgehende Anrufe für alle UM-IP-Gateways deaktivieren, außer dem einen Gateway, das durch das Skript erstellt wurde. Dazu gehört auch das Deaktivieren von ausgehenden Anrufen auf UM-IP-Gateways, die vor dem Ausführen des Skripts erstellt wurden. 

- Es erstellt einen UM-Sammelanschluss für jedes UM-IP-Gateway. Die Pilot-ID jeder Sammelsuche gibt den UM-SIP-URI-Wählplan an, der vom Skype for Business Server-Front-End-Pool oder Standard Edition-Server verwendet wird, der dem UM-IP-Gateway zugeordnet ist.
- Erteilt Skype for Business Server die Berechtigung zum Lesen von Active Directory UM-Containerobjekten wie UM-Wählplänen, automatischen Telefonieren, UM-IP-Gateways und UM-Sammel sammelgruppen.
  > [!IMPORTANT]
  > Jede UM-Gesamtstruktur muss so konfiguriert sein, dass sie der Gesamtstruktur vertraut, in der Skype for Business Server bereitgestellt wird, und die Gesamtstruktur, in der Skype for Business Server 2013 bereitgestellt wird, muss so konfiguriert sein, dass sie jeder UM-Gesamtstruktur vertraut. Wenn Exchange UM in mehreren Gesamtstrukturen installiert ist, müssen die Exchange Server Integrationsschritte für jede UM-Gesamtstruktur ausgeführt werden, oder Sie müssen die Skype for Business Server-Domäne angeben. Beispiel: ExchUcUtil.ps1 -Forest:<lync-domain-controller-fqdn>. 

### <a name="use-the-shell-to-run-the-exchucutilps1-script"></a>Ausführen des Skripts "ExchUcUtil.ps1" mithilfe der Shell

Führen Sie das ExchUcUtil.ps1 auf einem beliebigen Exchange-Server in Ihrer Organisation aus, der sich in derselben Topologie wie Skype for Business Server befinden. Sie können das Skript in der Shell auf einem Postfachserver oder über die Windows Remote-PowerShell auf einem Clientzugriffsserver ausführen. Wenn Sie das Skript auf einem Clientzugriffsserver in Ihrer Organisation ausführen, leitet der Clientzugriffsserver die Windows Remote-PowerShell-Sitzung über einen Proxy an einen Postfachserver in der Organisation weiter.
> [!IMPORTANT]
> Das ExchUCUtil.ps1-Skript erstellt ein oder mehrere UM-IP-Gateways. Sie müssen ausgehende Anrufe für alle UM-IP-Gateways deaktivieren, außer dem einen Gateway, das durch das Skript erstellt wurde. Dazu gehört auch das Deaktivieren von ausgehenden Anrufen auf UM-IP-Gateways, die vor dem Ausführen des Skripts erstellt wurden. Informationen zum Deaktivieren von ausgehenden Anrufen auf UM-IP-Gateways finden Sie unter Deaktivieren Sie ausgehende Anrufe für UM-IP-gateways. 
> [!IMPORTANT]
> Sie benötigen die Berechtigungen der Rolle "Exchange-Organisationsverwaltung" oder müssen ein Mitglied der Sicherheitsgruppe "Exchange-Organisationsadministratoren" sein, um das Skript auszuführen. 

1. Öffnen Sie die Exchange-Verwaltungsshell.
2. Geben Sie an der C:\Windows\System32-Eingabeaufforderung **cd \<drive letter> :\Programme\Microsoft\Exchange Server\V15\Scripts>.ExchUcUtil.ps1** ein, und drücken Sie dann die EINGABETASTE.

#### <a name="how-do-you-know-this-worked"></a>Woher wissen Sie, dass dieses Verfahren erfolgreich war?

Gehen Sie folgendermaßen vor, um zu überprüfen, ob das Skript "ExchUcUtul.ps1" erfolgreich abgeschlossen wurde:
- Verwenden Sie das Cmdlet Get-UMIPGateway oder die Exchange-Verwaltungskonsole, um die neu erstellten UM-IP-Gateways anzuzeigen.
- Verwenden Sie das Cmdlet Get-UMHuntGroup oder die Exchange-Verwaltungskonsole, um die neu erstellten UM-Sammelanschlüsse anzuzeigen.

### <a name="configure-certificates-on-the-server-running-exchange-server-unified-messaging"></a>Konfigurieren von Zertifikaten auf dem Server, auf dem Exchange Server Unified Messaging ausgeführt wird
 
Wenn Sie Exchange Unified Messaging (UM) bereitgestellt haben, wie unter Planning for Exchange Unified Messaging integration in Skype for Business Server in der Planungsdokumentation beschrieben, und Sie exchange UM-Features für Enterprise-VoIP-Benutzer in Ihrer Organisation bereitstellen möchten, können Sie die folgenden Verfahren verwenden, um das Zertifikat auf dem Server zu konfigurieren, auf dem Exchange UM ausgeführt wird.

> [!IMPORTANT]
> Bei internen Zertifikaten müssen sowohl die Server mit Skype for Business Server als auch die Server, auf denen Microsoft Exchange ausgeführt wird, über vertrauenswürdige Stammzertifizierungsstellezertifikate verfügen, die gegenseitig vertrauenswürdig sind. Die Zertifizierungsstelle kann entweder dieselbe oder eine andere Zertifizierungsstelle sein, solange auf den Servern das Stammzertifikat der Zertifizierungsstelle im Zertifikatspeicher der vertrauenswürdigen Stammzertifizierungsstelle registriert ist. 

Die Exchange Server muss mit einem Serverzertifikat konfiguriert werden, um eine Verbindung mit Skype for Business Server herzustellen:
1. Laden Sie das Zertifizierungsstellenzertifikat für den Exchange Server-Computer herunter.
2. Installieren Sie das Zertifizierungsstellenzertifikat für den Exchange Server-Computer.
3. Vergewissern Sie sich, dass sich die Zertifizierungsstelle in der Liste der vertrauenswürdigen Stammzertifizierungsstellen des Computers mit Exchange Server befindet.
4. Erstellen Sie eine Zertifikatanforderung für den Computer mit Exchange Server, und installieren Sie das Zertifikat. 
5. Weisen Sie das Zertifikat für den Computer mit Exchange Server zu.


**So laden Sie das Zertifizierungsstellenzertifikat herunter:**

1. Klicken Sie auf dem Server mit Exchange UM auf **Start,** klicken Sie auf **Ausführen,** geben Http:// **\<name of your Issuing CA Server> /certsrv** ein, und klicken Sie dann auf **OK**.
2. Klicken Sie unter Aufgabe auswählen auf **Zertifizierungsstellenzertifikat, Zertifikatkette oder Zertifikatsperrliste herunterladen.**
3. Wählen **Sie unter Zertifizierungsstellenzertifikat, Zertifikatkette** oder Zertifikatsperrliste herunterladen die Option **Encoding Method to Base 64** aus, und klicken Sie dann auf Zertifizierungsstellenzertifikat **herunterladen.**
   > [!NOTE]
   > Sie können in diesem Schritt auch die Codierung von Distinguished Encoding Rules (DER) angeben. Beachten Sie Folgendes, wenn Sie die DER-Codierung auswählen: Der Dateityp im nächsten Schritt dieses Verfahrens und in Schritt 10 unter **So installieren Sie das Zertifizierungsstellenzertifikat** ist P7B und nicht CER. 
4. Klicken Sie im Dialogfeld **Dateidownload** auf **Speichern**, und speichern Sie die Datei auf der Festplatte des Servers. (Die Datei hat entweder die Dateierweiterung CER oder P7B. Dies richtet sich nach der Codierung, die Sie im vorherigen Schritt gewählt haben.)

**So installieren Sie das Zertifizierungsstellenzertifikat:**

1. Öffnen Sie auf dem Server mit Exchange UM die Microsoft Management Console (MMC), indem Sie auf **Start** klicken, auf **Ausführen** klicken, **mmc** in das Feld Öffnen eingeben und dann auf **OK klicken.**
2. Klicken Sie im Menü **Datei** auf **Snap-In hinzufügen/entfernen** und dann auf **Hinzufügen**.
3. Klicken Sie im Feld **Eigenständiges Snap-In hinzufügen** auf **Zertifikate** und anschließend auf **Hinzufügen**.
4. Klicken Sie im Dialogfeld **Zertifikat-Snap-In** auf **Computerkonto** und anschließend auf **Weiter**.
5. Überprüfen Sie **im** Dialogfeld Computer auswählen, ob das Kontrollkästchen Lokaler **Computer: (Computer,** auf dem diese Konsole ausgeführt wird) aktiviert ist, und klicken Sie dann auf **Fertig stellen.**
6. Klicken Sie auf **Schließen** und dann auf **OK**. 
7. Erweitern Sie in der Konsolenstruktur den Eintrag **Zertifikate (Lokaler Computer)** und dann **Vertrauenswürdige Stammzertifizierungsstellen**, und klicken Sie anschließend auf **Zertifikate**.
8. Klicken Sie mit der rechten Maustaste auf **Zertifikate**, und klicken Sie dann auf **Alle Tasks** und **Importieren**.
9. Klicken Sie auf **Weiter**. 
10. Klicken Sie auf **Durchsuchen**, um auf die Datei zuzugreifen, und klicken Sie dann auf **Weiter**. (Die Datei hat entweder die Dateierweiterung CER oder P7B. Dies richtet sich nach der Codierung, die Sie in Schritt 3 unter **So laden Sie das Zertifizierungsstellenzertifikat herunter** gewählt haben.)
11. Klicken **Sie im** folgenden Speicher auf Alle Zertifikate platzieren.
12. Klicken Sie auf **Durchsuchen**, und wählen Sie **Vertrauenswürdige Stammzertifizierungsstellen** aus. 
13. Klicken Sie auf **Weiter**, um die Einstellungen zu überprüfen, und klicken Sie dann auf **Fertig stellen**. 


**So überprüfen Sie, ob sich die Zertifizierungsstelle in der Liste der vertrauenswürdigen Stammzertifizierungsstellen befindet:**

1. Erweitern Sie auf dem Server mit Exchange UM in MMC Zertifikate (lokaler Computer), erweitern Sie Vertrauenswürdige Stammzertifizierungsstellen, und klicken Sie dann auf Zertifikate.
2. Überprüfen Sie im Detailbereich, ob Ihre Zertifizierungsstelle in der Liste der vertrauenswürdigen Zertifizierungsstellen aufgeführt ist.