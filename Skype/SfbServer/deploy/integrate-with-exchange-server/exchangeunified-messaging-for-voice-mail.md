---
title: Konfigurieren von Exchange Server Unified Messaging für Voicemail on Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
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
description: 'Zusammenfassung: Konfigurieren von Exchange Server Unified Messaging für Skype for Business Server-Voicemail.'
ms.openlocfilehash: affaf5eb25b755d51d4ce47dd75834b6704d7610
ms.sourcegitcommit: b1229ed5dc25a04e56aa02aab8ad3d4209559d8f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2020
ms.locfileid: "41797066"
---
# <a name="configure-exchange-server-unified-messaging-for-skype-for-business-server-voice-mail"></a>Konfigurieren von Exchange Server Unified Messaging für Voicemail on Skype for Business Server
 
**Zusammenfassung:** Konfigurieren Sie Exchange Server Unified Messaging für Skype for Business Server-Voicemail.
  
Skype for Business Server ermöglicht Ihnen, Voicemail-Nachrichten in Exchange Server 2016 oder Exchange Server 2013 zu speichern. Diese Sprachnachrichten werden dann als e-Mail-Nachrichten in den Posteingängen Ihrer Benutzer angezeigt. 

> [!NOTE]
> Exchange Unified Messaging, wie zuvor bekannt, steht in Exchange 2019 nicht mehr zur Verfügung, Sie können aber weiterhin Voicemail-Nachrichten mit dem Telefon System aufzeichnen und die Aufzeichnung dann im Exchange-Postfach eines Benutzers belassen. Weitere Informationen finden Sie unter [Planen des Cloud Voicemail-Diensts](../../../sfbhybrid/hybrid/plan-cloud-voicemail.md) .
  
Wenn Sie die Server-zu-Server-Authentifizierung bereits zwischen Skype for Business Server und Exchange Server 2016 oder Exchange Server 2013 konfiguriert haben, können Sie Unified Messaging einrichten. Dazu müssen Sie zuerst einen neuen Unified Messaging-Wählplan auf dem Exchange-Server erstellen und zuweisen. So konfigurieren diese beiden Befehle (die in der Exchange-Verwaltungsshell ausgeführt werden) einen neuen dreistelligen Wählplan für Exchange:
  
```powershell
New-UMDialPlan -Name "RedmondDialPlan" -VoIPSecurity "Secured" -NumberOfDigitsInExtension 3 -URIType "SipName" -CountryOrRegionCode 1
Set-UMDialPlan "RedmondDialPlan" -ConfiguredInCountryOrRegionGroups "Anywhere,*,*,*" -AllowedInCountryOrRegionGroups "Anywhere"
```

Im ersten Befehl im Beispiel gibt der VoIPSecurity-Parameter und der Parameterwert "gesichert" an, dass der Signalisierungskanal mithilfe von Transport Layer Security (TLS) verschlüsselt wird. Der URI-Typ „SipName“ gibt an, dass Nachrichten unter Verwendung des SIP-Protokolls gesendet und empfangen werden, und der Wert „1“ für „CountryOrRegionCode“ gibt an, dass der Wählplan für die USA gilt.
  
Im zweiten Befehl gibt der an den Parameter „ConfiguredInCountryOrRegionGroups“ übergebene Parameterwert die länderinternen Gruppen an, die mit diesem Wählplan verwendet werden können. Der Parameterwert "Anywhere;\*\*,\*" legt Folgendes fest:
  
- Gruppenname („Anywhere“)
    
- AllowedNumberString (\*, ein Platzhalterzeichen, das angibt, dass eine beliebige Zahlen Zeichenfolge zulässig ist)
    
- DialNumberString (\*, ein Platzhalterzeichen, das angibt, dass eine gewählte Nummer zulässig ist)
    
- Textcomment (\*ein Platzhalterzeichen, das angibt, dass ein beliebiger Textbefehl zulässig ist)
    
> [!NOTE]
> Die Erstellung eines neuen Wählplans sorgt zusätzlich für die Erstellung einer standardmäßigen Postfachrichtlinie. 
  
Nachdem Sie den neuen Wählplan erstellt und konfiguriert haben, müssen Sie den neuen Wählplan dem Unified Messaging-Server hinzufügen und dann den Startmodus dieses Servers ändern. insbesondere müssen Sie den Startmodus auf "Dual" einstellen. Sie können diese beiden Aufgaben in der Exchange-Verwaltungsshell ausführen:
  
```powershell
Set-UmService -Identity "atl-exchangeum-001.litwareinc.com" -DialPlans "RedmondDialPlan" -UMStartupMode "Dual"
```

Nachdem der Unified Messaging-Server konfiguriert wurde, müssen Sie als nächstes das Cmdlet Enable-ExchangeCertificate ausführen, um sicherzustellen, dass Ihr Exchange-Zertifikat auf den Unified Messaging-Dienst angewendet wird:
  
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
  
Erstellen Sie zum Abschließen der Unified Messaging-Einrichtung eine UM-Postfachrichtlinie und aktivieren Sie dann mit dieser Richtlinie Benutzer für Unified Messaging. Sie können eine Postfachrichtlinie mit folgendem Befehl erstellen:
  
```powershell
New-UMMailboxPolicy -Name "RedmondMailboxPolicy" -AllowedInCountryOrRegionGroups "Anywhere"
```

Sie können Unified Messaging für einen Benutzer mit einem Befehl wie dem folgenden aktivieren:
  
```powershell
Enable-UMMailbox -Extensions 100 -SIPResourceIdentifier "kenmyer@litwareinc.com" -Identity "litwareinc\kenmyer" -UMMailboxPolicy "RedmondMailboxPolicy"
```

Im vorherigen Befehl steht der Parameter „Extensions“ für die Durchwahlnummer des Benutzers. In diesem Beispiel besitzt der Benutzer die Durchwahl 100.
  
Nach dem Aktivieren des Postfachs sollte der Benutzer „kenmyer@litwareinc.com“ Exchange Unified Messaging verwenden können. Sie können überprüfen, ob der Benutzer eine Verbindung mit Exchange um herstellen kann, indem Sie das Cmdlet [Test-CsExUMConnectivity](https://docs.microsoft.com/powershell/module/skype/test-csexumconnectivity?view=skype-ps) in der Skype for Business Server-Verwaltungsshell ausführen:
  
```powershell
$credential = Get-Credential "litwareinc\kenmyer"
Test-CsExUMConnectivity -TargetFqdn "atl-cs-001.litwareinc.com" -UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential
```

Wenn ein zweiter Benutzer vorhanden ist, für den Unified Messaging aktiviert wurde, können Sie mit dem Cmdlet [Test-CsExUMVoiceMail](https://docs.microsoft.com/powershell/module/skype/test-csexumvoicemail?view=skype-ps) sicherstellen, dass dieser zweite Benutzer eine Voicemailnachricht für den ersten Benutzer hinterlassen kann.
  
```powershell
$credential = Get-Credential "litwareinc\pilar"
Test-CsExUMVoiceMail -TargetFqdn "atl-cs-001.litwareinc.com" -ReceiverSipAddress "sip:kenmyer@litwareinc.com" -SenderSipAddress "sip:pilar@litwareinc.com" -SenderCredential $credential
```



## <a name="configuring-unified-messaging-on-microsoft-exchange-server"></a>Konfigurieren von Unified Messaging auf Microsoft Exchange Server 
> [!IMPORTANT]
> Wenn Sie Exchange Unified Messaging (um) zum Bereitstellen von Anrufbeantwortung, Outlook Voice Access oder automatischen Telefonzentralen für Enterprise-VoIP-Benutzer verwenden möchten, lesen Sie [Planen der Integration von Exchange Unified Messaging in Skype for Business](../../plan-your-deployment/integrate-with-exchange/unified-messaging.md), und folgen Sie dann den Anweisungen in diesem Abschnitt. 

Um Exchange Unified Messaging (um) für die Arbeit mit Enterprise-VoIP zu konfigurieren, müssen Sie die folgenden Aufgaben ausführen:

- Konfigurieren von Zertifikaten auf dem Server mit Exchange Unified Messaging (um)-Diensten
  > [!NOTE]
  > Fügen Sie allen um-SIP-URI-Wählplänen alle Client Zugriffs-und Postfachserver hinzu. Wenn dies nicht der Fall ist, funktioniert das Routing für ausgehende Anrufe nicht wie erwartet. 
- Erstellen Sie bei Bedarf einen oder mehrere um-SIP-URI-Wählpläne zusammen mit den Telefonnummern für den Abonnenten Zugriff, und erstellen Sie dann die entsprechenden L-Wählpläne.

- Verwenden Sie das exchucutil. ps1-Skript für folgende Zwecke:
    - Erstellen von um-IP-Gateways
    - Erstellen von um-Sammelanschlüssen
    - Erteilen Sie Skype for Business Server-Berechtigung zum Lesen von um-Active Directory-Domänendienste-Objekten.
- Erstellen Sie ein Objekt der automatischen UM-Telefonzentrale.
- Erstellen Sie ein Teilnehmerzugriffs Objekt.
- Erstellen Sie einen SIP-URI für jeden Benutzer, und verknüpfen Sie Benutzer mit einem um-SIP-URI-Wählplan.

### <a name="requirements-and-recommendations"></a>Anforderungen und Empfehlungen

Bevor Sie beginnen, wird in der in diesem Abschnitt aufgeführten Dokumentation davon ausgegangen, dass Sie die folgenden Exchange-Rollen bereitgestellt haben: Client Zugriff und Postfach. In Microsoft Exchange Server wird Exchange um als Dienst auf diesen Servern ausgeführt.

Beachten Sie außerdem Folgendes:
- Wenn Exchange um in mehreren Gesamtstrukturen installiert ist, müssen die Exchange Server-Integrationsschritte für jede um-Gesamtstruktur ausgeführt werden. Darüber hinaus muss jede um-Gesamtstruktur so konfiguriert sein, dass Sie der Gesamtstruktur vertraut, in der der Skype for Business-Server bereitgestellt wird, und die Gesamtstruktur in whichSkype for Business Server muss so konfiguriert sein, dass Sie jeder um-Gesamtstruktur vertraut.
- Die Integrationsschritte erfolgen sowohl für die Exchange-Serverrollen, auf denen Unified Messaging-Dienste ausgeführt werden, als auch auf dem Server, auf dem Skype for Business Server ausgeführt wird. Sie sollten die Exchange Server Unified Messaging-Integrationsschritte ausführen, bevor Sie die lync Server 2013-Integrationsschritte ausführen.
  > [!NOTE]
  > Informationen dazu, welche Integrationsschritte für welche Server und welche Administratorrollen ausgeführt werden, finden Sie unter Übersicht über den [Bereitstellungsprozess für die Integration von lokalen Unified Messaging und Skype for Business](../../plan-your-deployment/integrate-with-exchange/deployment-overview.md). 

Die folgenden Tools müssen auf jedem Server mit Exchange um verfügbar sein:
- Exchange-Verwaltungsshell
- Das Skript exchucutil. ps1, in dem die folgenden Aufgaben ausgeführt werden:
    - Erstellt ein um-IP-Gateway für jeden Skype for Business-Server.
    - Erstellt einen Sammelanschluss für jedes Gateway. Die Pilotkennung der einzelnen Sammelanschlüsse gibt den um-SIP-URI-Wählplan an, der vom Front-End-Pool oder Standard Edition-Server verwendet wird, der dem Gateway zugeordnet ist.
    - Erteilt die Skype for Business Server-Berechtigung zum Lesen von Exchange um-Objekten in Active Directory-Domänendiensten.



### <a name="configure-unified-messaging-on-microsoft-exchange-with-exchucutilps1"></a>Configure Unified Messaging on Microsoft Exchange with ExchUCUtil.ps1 

Wenn Sie Microsoft Skype for Business Server mit Exchange Unified Messaging (um) integrieren, müssen Sie das ExchUcUtil. ps1-Skript in der Shell ausführen. Das ExchUcUtil. ps1-Skript führt die folgenden Aktionen aus:

- Erstellt ein um-IP-Gateway für jeden Skype for Business-Server Pool.

> [!IMPORTANT]
> Das ExchUcUtil. ps1-Skript erstellt mindestens ein um-IP-Gateway. Sie müssen ausgehende Anrufe auf allen um-IP-Gateways deaktivieren, mit Ausnahme eines Gateways, das vom Skript erstellt wurde. Dies umfasst das Deaktivieren von ausgehenden Anrufen für um-IP-Gateways, die vor dem Ausführen des Skripts erstellt wurden. 

- Erstellt einen um-Sammelanschluss für jedes um-IP-Gateway. Die Pilotkennung der einzelnen Sammelanschlüsse gibt den um-SIP-URI-Wählplan an, der vom Skype for Business Server-Front-End-Pool oder Standard Edition-Server verwendet wird, der dem um-IP-Gateway zugeordnet ist.
- Erteilt Skype for Business Server-Berechtigung zum Lesen von Active Directory um-Containerobjekten wie um-Wählpläne, automatischen Telefonzentralen, um-IP-Gateways und um-Sammelanschlüssen.
  > [!IMPORTANT]
  > Jede um-Gesamtstruktur muss so konfiguriert sein, dass Sie der Gesamtstruktur vertraut, in der Skype for Business Server bereitgestellt wird, und die Gesamtstruktur, in der Skype for Business Server 2013 bereitgestellt wird, muss so konfiguriert sein, dass Sie jeder um-Gesamtstruktur vertraut Wenn Exchange um in mehreren Gesamtstrukturen installiert ist, müssen die Exchange Server-Integrationsschritte für jede um-Gesamtstruktur ausgeführt werden, oder Sie müssen die Skype for Business Server-Domäne angeben. Beispiel: ExchUcUtil. ps1 – Forest: <lync-Domänencontroller-FQDN>. 

### <a name="use-the-shell-to-run-the-exchucutilps1-script"></a>Verwenden der Shell zum Ausführen des ExchUcUtil. ps1-Skripts

Führen Sie das ExchUcUtil. ps1-Skript auf einem beliebigen Exchange-Server in Ihrer Organisation aus, der sich in derselben Topologie wie Skype for Business Server befindet. Sie können das Skript auf einem Postfachserver mithilfe der Shell ausführen, oder Sie können das Skript mithilfe der Remote-Windows PowerShell auf einem Client Zugriffsserver ausführen. Wenn Sie das Skript auf einem Clientzugriffsserver in Ihrer Organisation ausführen, wird der Clientzugriffsserver die Remote-Windows PowerShell-Sitzung an einen Postfachserver in der Organisation weiterleiten.
> [!IMPORTANT]
> Das ExchUcUtil. ps1-Skript erstellt mindestens ein um-IP-Gateway. Sie müssen ausgehende Anrufe auf allen um-IP-Gateways deaktivieren, mit Ausnahme eines Gateways, das vom Skript erstellt wurde. Dies umfasst das Deaktivieren von ausgehenden Anrufen für um-IP-Gateways, die vor dem Ausführen des Skripts erstellt wurden. Informationen zum Deaktivieren von ausgehenden Anrufen auf einem um-IP-Gateway finden Sie unter Deaktivieren von ausgehenden Anrufen für um-IP-Gateways. 
> [!IMPORTANT]
> Sie müssen über die Berechtigungen der Exchange-Organisations Verwaltungsrolle verfügen oder ein Mitglied der Sicherheitsgruppe Exchange-Organisationsadministratoren sein, um das Skript ausführen zu können. 

1. Öffnen Sie die Exchange-Verwaltungsshell.
2. Geben Sie an der Eingabeaufforderung von "c/c" den **Buchstaben CD \<-Laufwerk> ein: \Programme\Microsoft Server\V15\Scripts>. ExchUcUtil. ps1**aus, und drücken Sie dann die EINGABETASTE.

#### <a name="how-do-you-know-this-worked"></a>Woher wissen Sie, ob dies funktioniert hat?

Gehen Sie wie folgt vor, um zu überprüfen, ob das ExchUcUtul. ps1-Skript erfolgreich abgeschlossen wurde:
- Verwenden Sie das Cmdlet Get-UMIPGateway oder EAC, um das neue um-IP-Gateway oder die erstellten Gateways anzuzeigen.
- Verwenden Sie das Cmdlet "Get-UMHuntGroup" oder "EAC", um den neuen um-Sammelanschluss oder die erstellten Gruppen anzuzeigen.

### <a name="configure-certificates-on-the-server-running-exchange-server-unified-messaging"></a>Konfigurieren von Zertifikaten auf dem Server mit Exchange Server Unified Messaging
 
Wenn Sie Exchange Unified Messaging (um) bereitgestellt haben, wie unter Planen der Integration von Exchange Unified Messaging in Skype for Business Server in der Planning-Dokumentation beschrieben, und Sie Exchange um-Features für Enterprise-VoIP-Benutzer in Ihrem Organisation können Sie die folgenden Verfahren verwenden, um das Zertifikat auf dem Server mit Exchange um zu konfigurieren.

> [!IMPORTANT]
> Für interne Zertifikate müssen sowohl die Server, auf denen Skype for Business Server ausgeführt wird, als auch die Server, auf denen Microsoft Exchange ausgeführt wird, vertrauenswürdige Stammzertifizierungsstellen Zertifikate besitzen, die gegenseitig vertraut sind. Die Zertifizierungsstelle (Certification Authority, ca) kann entweder dieselbe oder eine andere Zertifizierungsstelle sein, sofern die Server das Stammzertifikat der Zertifizierungsstelle im Zertifikatspeicher der vertrauenswürdigen Stammzertifizierungsstelle registriert haben. 

Der Exchange-Server muss mit einem Server Zertifikat konfiguriert sein, um eine Verbindung mit Skype for Business Server herstellen zu können:
1. Laden Sie das Zertifizierungsstellenzertifikat für den Exchange-Server herunter.
2. Installieren Sie das Zertifizierungsstellenzertifikat für den Exchange-Server.
3. Überprüfen Sie, ob sich die Zertifizierungsstelle in der Liste der vertrauenswürdigen Stammzertifizierungsstellen des Exchange-Servers befindet.
4. Erstellen Sie eine Zertifikatanforderung für den Exchange-Server, und installieren Sie das Zertifikat. 
5. Weisen Sie das Zertifikat für den Exchange-Server zu.


**So laden Sie das CA-Zertifikat herunter:**

1. Klicken Sie auf dem Server, auf dem Exchange um ausgeführt wird, auf **Start**, klicken Sie auf **Ausführen**, geben Sie **http://\<Namen des ausstellenden CA-Servers>/certsrv**ein, und klicken Sie dann auf **OK**.
2. Klicken Sie unter Aufgabe auswählen auf **Zertifizierungsstellenzertifikat, Zertifikatkette oder CRL Herunterladen**.
3. Wählen Sie unter **Download eines Zertifizierungsstellenzertifikats, einer Zertifikatkette oder einer CRL** **die Option Encoding method to base 64**aus, und klicken Sie dann auf**CA-Zertifikat herunterladen**.
   > [!NOTE]
   > Sie können in diesem Schritt auch die Codierungsregeln (Distinguished Encoding Rules, der) angeben. Wenn Sie der Codierung auswählen, lautet der Dateityp im nächsten Schritt dieses Verfahrens und in Schritt 10 der **Installation des Zertifizierungsstellenzertifikats** P7B statt. cer. 
4. Klicken Sie im Dialogfeld **Datei Download** auf **Speichern**, und speichern Sie die Datei auf der Festplatte auf dem Server. (Abhängig von der Codierung, die Sie im vorherigen Schritt ausgewählt haben, weist die Datei entweder eine CER-oder eine P7B-Dateierweiterung auf.)

**So installieren Sie das CA-Zertifikat:**

1. Öffnen Sie auf dem Server, auf dem Exchange um ausgeführt wird, Microsoft Management Console (MMC), indem Sie auf **Start**klicken, auf **Ausführen**klicken, **MMC** in das Feld Öffnen eingeben und dann auf **OK**klicken.
2. Klicken Sie im Menü **Datei** auf **Snap-in hinzufügen/entfernen**, und klicken Sie dann auf **Hinzufügen**.
3. Klicken Sie im Feld **eigenständige Snap-Ins hinzufügen** auf **Zertifikate**, und klicken Sie dann auf **Hinzufügen**.
4. Klicken Sie im Dialogfeld **Zertifikat-Snap-In** auf **Computerkonto** und anschließend auf **Weiter**.
5. Überprüfen Sie im Dialogfeld **Computer auswählen** , ob das Kontrollkästchen **lokaler Computer: (Computer, auf dem diese Konsole ausgeführt wird)** aktiviert ist, und klicken Sie dann auf **Fertig stellen**.
6. Klicken Sie auf **Schließen**, und klicken Sie dann auf **OK**. 
7. Erweitern Sie in der Konsolenstruktur **Zertifikate (lokaler Computer)**, erweitern Sie **Vertrauenswürdige Stammzertifizierungsstellen**, und klicken Sie dann auf **Zertifikate**.
8. Klicken Sie mit der rechten Maustaste auf **Zertifikate**, klicken Sie auf **alle Aufgaben**, und klicken Sie auf **importieren**.
9. Klicken Sie auf **Weiter**. 
10. Klicken Sie auf **Durchsuchen** , um nach der Datei zu suchen, und klicken Sie dann auf **weiter**. (Abhängig von der Codierung, die Sie in Schritt 3 **zum Herunterladen des CA-Zertifikats**ausgewählt haben, wird die Datei entweder eine CER-oder eine P7B-Dateierweiterung aufweisen.
11. Klicken Sie im folgenden Store auf **alle Zertifikate** speichern.
12. Klicken Sie auf **Durchsuchen**, und wählen Sie dann **Vertrauenswürdige Stammzertifizierungsstellen**aus. 
13. Klicken Sie auf **weiter** , um die Einstellungen zu überprüfen, und klicken Sie dann auf **Fertig stellen**. 


**So überprüfen Sie, ob sich die Zertifizierungsstelle in der Liste der vertrauenswürdigen Stammzertifizierungsstellen befindet:**

1. Erweitern Sie auf dem Server, auf dem Exchange um ausgeführt wird, in MMC Zertifikate (lokaler Computer), erweitern Sie vertrauenswürdige Stammzertifizierungsstellen, und klicken Sie dann auf Zertifikate.
2. Überprüfen Sie im Detailbereich, ob sich Ihre Zertifizierungsstelle in der Liste der vertrauenswürdigen CAS befindet.


