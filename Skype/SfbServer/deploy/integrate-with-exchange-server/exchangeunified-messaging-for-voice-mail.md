---
title: Konfigurieren von Exchange Server Unified Messaging für Voicemail on Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/11/2019
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 1be9c4f4-fd8e-4d64-9798-f8737b12e2ab
description: 'Zusammenfassung: Konfigurieren Sie Exchange Server Unified Messaging für Skype für Voicemail Business Server.'
ms.openlocfilehash: 76a73c396657d98871a0238fe840e08016bccf13
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "33894344"
---
# <a name="configure-exchange-server-unified-messaging-for-skype-for-business-server-voice-mail"></a>Konfigurieren von Exchange Server Unified Messaging für Voicemail on Skype for Business Server
 
**Zusammenfassung:** Konfigurieren von Exchange Server Unified Messaging für Skype für Voicemail Business Server.
  
Skype für Business Server können Sie Voicemail-Nachrichten in Exchange Server 2016 oder Exchange Server 2013 gespeichert haben. Diese Voicemailnachrichten werden dann als e-Mail-Nachrichten in die Posteingänge der Benutzer angezeigt. 

> [!NOTE]
> Exchange Unified Messaging als zuvor bekannt ist nicht mehr verfügbar im Exchange 2019, jedoch können Sie weiterhin Telefonsystem aufzeichnen Voicemailnachrichten verwenden und lassen Sie die Aufzeichnung klicken Sie dann im Exchange-Postfach eines Benutzers. Weitere Informationen finden Sie unter [Planen von Cloud-Voicemail-Dienst](../../../sfbhybrid/hybrid/plan-cloud-voicemail.md) .
  
Wenn Sie die Server-zu-Server-Authentifizierung zwischen Skype für Business Server und Exchange Server 2016 oder Exchange Server 2013 bereits konfiguriert haben, sind Sie bereit, So richten Sie unified messaging. Hierzu müssen Sie zuerst erstellen und zuweisen ein neuen Wählplans für unified messaging auf Ihrem Exchange Server. Diese beiden Befehle (von in der Exchange-Verwaltungsshell ausgeführt) konfigurieren beispielsweise einen neuen 3 Ziffer Wählplan für Exchange:
  
```
New-UMDialPlan -Name "RedmondDialPlan" -VoIPSecurity "Secured" -NumberOfDigitsInExtension 3 -URIType "SipName" -CountryOrRegionCode 1
Set-UMDialPlan "RedmondDialPlan" -ConfiguredInCountryOrRegionGroups "Anywhere,*,*,*" -AllowedInCountryOrRegionGroups "Anywhere"
```

In der ersten gibt Befehl im Beispiel wird der VoIPSecurity-Parameter und der Wert des Parameters "Gesichert", dass der signalkanal mithilfe von Transport Layer Security (TLS) verschlüsselt werden. Der URI-Typ „SipName“ gibt an, dass Nachrichten unter Verwendung des SIP-Protokolls gesendet und empfangen werden, und der Wert „1“ für „CountryOrRegionCode“ gibt an, dass der Wählplan für die USA gilt.
  
Im zweiten Befehl gibt der an den Parameter „ConfiguredInCountryOrRegionGroups“ übergebene Parameterwert die länderinternen Gruppen an, die mit diesem Wählplan verwendet werden können. Der Wert des Parameters "Anywhere,\*,\*,\*" legt Folgendes fest:
  
- Gruppenname („Anywhere“)
    
- AllowedNumberString (\*, ein Platzhalterzeichen, das angibt, dass eine beliebige Nummernzeichenfolge zulässig ist)
    
- DialNumberString (\*, ein Platzhalterzeichen, das angibt, dass eine beliebige gewählte Nummer zulässig ist)
    
- TextComment (\*, ein Platzhalterzeichen, das angibt, dass alle Textbefehl zulässig ist)
    
> [!NOTE]
> Die Erstellung eines neuen Wählplans sorgt zusätzlich für die Erstellung einer standardmäßigen Postfachrichtlinie. 
  
Nach dem Erstellen und Konfigurieren des neuen Wählplans müssen Sie das neue Wählplan an Ihre unified messaging-Server aus, und ändern Sie den Startmodus des betreffenden Servers hinzufügen. Insbesondere müssen Sie den Startmodus zu "Dual" festlegen. Sie können diese beiden Aufgaben aus in der Exchange-Verwaltungsshell ausführen:
  
```
Set-UmService -Identity "atl-exchangeum-001.litwareinc.com" -DialPlans "RedmondDialPlan" -UMStartupMode "Dual"
```

Nach dem Konfigurieren der unified messaging-Servers sollten Sie als Nächstes ausführen das Cmdlet Enable-ExchangeCertificate, um sicherzustellen, dass Ihre Exchange-Zertifikat auf den unified messaging-Dienst angewendet wird:
  
```
Enable-ExchangeCertificate -Server "atl-umserver-001.litwareinc.com" -Thumbprint "EA5A332496CC05DA69B75B66111C0F78A110D22d" -Services "SMTP","IIS","UM"
```

Nachdem das Zertifikat ordnungsgemäß zugewiesen wurde, müssen Sie den MsExchangeUM-Dienst auf dem Unified Messaging-Server beenden und neu starten. Dieser Dienst muss jedes Mal beendet und neu gestartet werden, wenn der Startmodus geändert wurde.
  
Wenn die Konfiguration des UM-Servers abgeschlossen ist, können Sie den UM-Anrufrouter konfigurieren:
  
```
Set-UMCallRouterSettings -Server "atl-exchange-001.litwareinc.com" -UMStartupMode "Dual" -DialPlans "RedmondDialPlan" 
Enable-ExchangeCertificate -Server "atl-umserver-001.litwareinc.com" -Thumbprint "45BAA32496CC891169B75B9811320F78A1075DDA" -Services "IIS","UMCallRouter"
```

Da der Startmodus geändert wurde, müssen Sie den MsExchangeUMCR-Dienst auf dem Computer mit dem UM-Anrufrouter beenden und neu starten.
  
Erstellen Sie zum Abschließen der Unified Messaging-Einrichtung eine UM-Postfachrichtlinie und aktivieren Sie dann mit dieser Richtlinie Benutzer für Unified Messaging. Sie können eine Postfachrichtlinie mit folgendem Befehl erstellen:
  
```
New-UMMailboxPolicy -Name "RedmondMailboxPolicy" -AllowedInCountryOrRegionGroups "Anywhere"
```

Sie können Unified Messaging für einen Benutzer mit einem Befehl wie dem folgenden aktivieren:
  
```
Enable-UMMailbox -Extensions 100 -SIPResourceIdentifier "kenmyer@litwareinc.com" -Identity "litwareinc\kenmyer" -UMMailboxPolicy "RedmondMailboxPolicy"
```

Im vorherigen Befehl steht der Parameter „Extensions“ für die Durchwahlnummer des Benutzers. In diesem Beispiel besitzt der Benutzer die Durchwahl 100.
  
Nach dem Aktivieren des Postfachs sollte der Benutzer „kenmyer@litwareinc.com“ Exchange Unified Messaging verwenden können. Sie können überprüfen, ob der Benutzer mit Exchange UM verbinden kann, indem das Cmdlet [Test-CsExUMConnectivity](https://docs.microsoft.com/powershell/module/skype/test-csexumconnectivity?view=skype-ps) von innerhalb der Skype für Business Server-Verwaltungsshell ausgeführt:
  
```
$credential = Get-Credential "litwareinc\kenmyer"
Test-CsExUMConnectivity -TargetFqdn "atl-cs-001.litwareinc.com" -UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential
```

Wenn ein zweiter Benutzer vorhanden ist, für den Unified Messaging aktiviert wurde, können Sie mit dem Cmdlet [Test-CsExUMVoiceMail](https://docs.microsoft.com/powershell/module/skype/test-csexumvoicemail?view=skype-ps) sicherstellen, dass dieser zweite Benutzer eine Voicemailnachricht für den ersten Benutzer hinterlassen kann.
  
```
$credential = Get-Credential "litwareinc\pilar"
Test-CsExUMVoiceMail -TargetFqdn "atl-cs-001.litwareinc.com" -ReceiverSipAddress "sip:kenmyer@litwareinc.com" -SenderSipAddress "sip:pilar@litwareinc.com" -SenderCredential $credential
```



## <a name="configuring-unified-messaging-on-microsoft-exchange-server"></a>Konfigurieren von Unified Messaging auf Microsoft Exchange Server 
> [!IMPORTANT]
> Wenn Sie Exchange Unified Messaging (UM) verwenden, um die Anrufbeantwortung, Outlook Voice Access oder automatische telefonzentralendienste für Enterprise-VoIP-Benutzer bereitstellen möchten, lesen Sie [Exchange Unified Messaging-Integration in Skype für Unternehmen planen](../../plan-your-deployment/integrate-with-exchange/unified-messaging.md), und folgen Sie den die Anweisungen in diesem Abschnitt. 

Um Exchange Unified Messaging (UM) arbeiten mit Enterprise-VoIP konfigurieren, benötigen Sie die folgenden Aufgaben ausführen:

- Konfigurieren von Zertifikaten auf dem Server mit Exchange Unified Messaging (UM) services
  > [!NOTE]
  > Fügen Sie alle Clientzugriffs- und Postfachservern an alle UM-SIP-URI-Wählpläne. Wenn nicht, des Routings ausgehender Anrufe als nicht funktionsfähig zu erwarten. 
- Erstellen Sie mindestens einen UM-SIP-URI-Wählpläne, zusammen mit den Telefonnummern für den Teilnehmerzugriff nach Bedarf, und erstellen Sie entsprechende L-Wählpläne.

- Verwenden Sie das Skript ExchUCUtil. ps1:
    - Erstellen von UM-IP-Gateways.
    - UM-Sammelanschlüsse zu erstellen.
    - Erteilen Sie Skype für Business Server-Berechtigung zum Lesen von UM Active Directory-Domänendienste-Objekten.
- Erstellen eines UM-telefonzentralenobjekts.
- Erstellen eines Objekts für Abonnenten.
- Erstellen Sie einen SIP-URI für jeden Benutzer und Zuordnen von Benutzern zu einem UM-SIP-URI-Wählplan.

### <a name="requirements-and-recommendations"></a>Anforderungen und Empfehlungen

Bevor Sie beginnen, wird in die Dokumentation in diesem Abschnitt davon ausgegangen, dass Sie die folgenden Exchange-Serverrollen bereitgestellt haben: Clientzugriffs- und Postfachserver. In Microsoft Exchange Server führt Exchange UM als Dienst auf diesen Servern.

Beachten Sie auch Folgendes:
- Wenn Exchange UM in mehreren Gesamtstrukturen installiert ist, müssen die Exchange Server-Integrationsschritte für jede UM-Gesamtstruktur ausgeführt werden. Darüber hinaus muss jede UM-Gesamtstruktur die Gesamtstruktur vertrauen, in dem Skype für Business Server bereitgestellt wird, und die Gesamtstruktur in WhichSkype für Business Server bereitgestellt wird konfiguriert werden muss, um jedes UM-Gesamtstruktur-Vertrauensstellung, konfiguriert werden.
- Integrationsschritte werden ausgeführt auf beide den Exchange Server-Rollen, auf dem Unified Messaging-Dienste ausgeführt werden, und klicken Sie auf dem Server mit Skype für Business Server. Führen Sie vor dem Ausführen der Lync Server 2013-Integrationsschritte der Exchange Server Unified Messaging-Integrationsschritte.
  > [!NOTE]
  > Um herauszufinden, welche Integrationsschritte auf welchen Servern und von welchen Administratorrollen durchgeführt werden, finden Sie unter [Übersicht über den Bereitstellungsprozess für die Integration lokaler Unified Messaging und Skype für Unternehmen](../../plan-your-deployment/integrate-with-exchange/deployment-overview.md). 

Die folgenden Tools müssen auf jedem Server mit Exchange UM verfügbar sein:
- Exchange-Verwaltungsshell
- Das Skript ExchUCUtil. ps1, das die folgenden Aufgaben ausführt:
    - Erstellt ein UM-IP-Gateway für jeden Skype für Business Server.
    - Erstellt einen Sammelanschluss für jedes Gateway. Die pilot-ID jedes Sammelanschlusses gibt den UM-SIP-URI-Wählplan verwendet vom Front-End-Pool oder Standard Edition-Server, der dem Gateway zugeordnet ist.
    - Skype für Business Server-Berechtigung zum Lesen von Exchange UM-Objekten in Active Directory-Domänendienste gewährt.



### <a name="configure-unified-messaging-on-microsoft-exchange-with-exchucutilps1"></a>Configure Unified Messaging on Microsoft Exchange with ExchUCUtil.ps1 

Bei der Integration von Microsoft Skype für Business Server mit Exchange Unified Messaging (UM) müssen Sie das Skript ExchUCUtil. ps1 in der Shell ausführen. Das Skript ExchUCUtil. ps1 bewirkt Folgendes:

- Erstellt ein UM-IP-Gateway für jeden Skype für Business Server-Pool.

> [!IMPORTANT]
> Das Skript ExchUCUtil. ps1 erstellt mindestens einen UM-IP-Gateways. Sie müssen ausgehende Anrufe auf alle UM-IP-Gateways mit Ausnahme von einem Gateway deaktivieren, die das Skript erstellt. Dazu gehören, deaktivieren ausgehende Anrufe für UM-IP-Gateways, die erstellt wurden, bevor Sie das Skript ausgeführt wurde. 

- Erstellt einen um-Sammelanschluss für jedes UM-IP-Gateway. Die pilot-ID jedes Sammelanschlusses gibt den UM-SIP-URI-Wählplan wird von der Skype für Business Server-Front-End-Pool oder Standard Edition-Server, die mit dem UM-IP-Gateway zugeordnet ist.
- Gewährt Skype für die Berechtigung zum Lesen von Active Directory-UM-Containerobjekten wie UM einwählen, Pläne, automatischen Telefonzentralen, UM-IP-Gateways, und UM-Sammelanschlüsse Business Server.
  > [!IMPORTANT]
  > Jede UM-Gesamtstruktur muss konfiguriert sein, damit vertraut die Gesamtstruktur, in dem Skype für Business Server bereitgestellt wird, und die Gesamtstruktur, in der Skype für Business Server 2013 bereitgestellt wird, muss als vertrauenswürdig, jede UM-Gesamtstruktur konfiguriert werden. Wenn Exchange UM in mehreren Gesamtstrukturen installiert ist, die Exchange Server-Integrationsschritte müssen für jede UM-Gesamtstruktur ausgeführt werden, oder Sie müssen die Skype für Business Server-Domäne angeben. Beispielsweise ExchUCUtil. ps1 – Gesamtstruktur: <lync-Domäne-Controller-Fqdn>. 

### <a name="use-the-shell-to-run-the-exchucutilps1-script"></a>Verwenden der Shell zum Ausführen des Skripts ExchUCUtil. ps1

Führen Sie das ExchUCUtil. ps1-Skript auf allen Exchange-Servern in Ihrer Organisation, die in die gleiche Topologie wie Skype für Business Server ist. Führen Sie das Skript aus einem Postfachserver mit der Shell, oder Sie können das Skript mithilfe von Windows PowerShell-Remotesitzungen auf einem Clientzugriffsserver ausführen. Wenn Sie das Skript auf einem Clientzugriffsserver in Ihrer Organisation ausführen, der Clientzugriffsserver wird Proxy die Remote Windows PowerShell-Sitzung auf einem Postfachserver in der Organisation.
> [!IMPORTANT]
> Das Skript ExchUCUtil. ps1 erstellt mindestens einen UM-IP-Gateways. Sie müssen ausgehende Anrufe auf alle UM-IP-Gateways mit Ausnahme von einem Gateway deaktivieren, die das Skript erstellt. Dazu gehören, deaktivieren ausgehende Anrufe für UM-IP-Gateways, die erstellt wurden, bevor Sie das Skript ausgeführt wurde. Um ausgehende Anrufe auf einem UM-IP-Gateway zu deaktivieren, finden Sie unter ausgehende Anrufe für UM-IP-Gateways deaktivieren. 
> [!IMPORTANT]
> Sie müssen über die Berechtigungen der Rolle Exchange Organization Management verfügen oder Mitglied der Sicherheitsgruppe "Exchange-Organisationsadministratoren" zum Ausführen des Skripts sein. 

1. Öffnen Sie die Exchange-Verwaltungsshell.
2. Geben Sie an der Eingabeaufforderung C:\Windows\System32 **cd \<Letter>:\Program Files\Microsoft\Exchange Server\V15\Scripts> Laufwerk. ExchUCUtil. ps1**, und drücken Sie dann die EINGABETASTE.

#### <a name="how-do-you-know-this-worked"></a>Wissen woher Sie?

Zum bestätigen, dass das Skript ExchUcUtul.ps1 erfolgreich abgeschlossen wurde, führen Sie folgende Schritte aus:
- Verwenden Sie das Cmdlet Get-UMIPGateway oder der Exchange-Verwaltungskonsole zum Anzeigen der neuen UM-IP-Gateway oder Gateways, die erstellt wurden.
- Verwenden Sie das Cmdlet Get-UMHuntGroup oder der Exchange-Verwaltungskonsole, um anzuzeigen, die neuen um-Sammelanschluss oder Gruppen, die erstellt wurden.

### <a name="configure-certificates-on-the-server-running-exchange-server-unified-messaging"></a>Konfigurieren von Zertifikaten auf dem Server mit Exchange Server Unified Messaging
 
Wenn Sie Exchange Unified Messaging (UM), wie unter Planning for Exchange Unified Messaging-Integration in Skype für Business Server in der Planungsdokumentation beschrieben bereitgestellt haben, und Sie Exchange UM für Enterprise-VoIP-Benutzern in Features bereitstellen möchten Ihre Organisation, die folgenden Verfahren können Sie das Zertifikat auf dem Server mit Exchange UM konfigurieren.

> [!IMPORTANT]
> Für interne Zertifikate den Servern mit Skype für Business Server und den Servern mit Microsoft Exchange müssen Stammzertifikate Zertifizierungsstelle als vertrauenswürdig eingestuft haben, die sich gegenseitig vertrauenswürdig sind. Die Zertifizierungsstelle (CA) kann die gleiche oder eine andere Zertifizierungsstelle, sein, solange die Server die Zertifizierungsstelle-Stammzertifikat im Zertifikatspeicher für ihre vertrauenswürdigen Stammzertifizierungsstellen registriert haben. 

Der Exchange-Server muss, um eine Verbindung mit Skype für Business Server mit einem Serverzertifikat konfiguriert werden:
1. Laden Sie das Zertifizierungsstellenzertifikat für den Exchange-Server.
2. Installieren Sie das Zertifizierungsstellenzertifikat für den Exchange-Server.
3. Stellen Sie sicher, dass die Zertifizierungsstelle in der Liste der vertrauenswürdigen Stammzertifizierungsstellen des Exchange-Servers befindet.
4. Erstellen Sie eine zertifikatanforderung für den Exchange-Server, und installieren Sie das Zertifikat. 
5. Weisen Sie das Zertifikat für den Exchange-Server.


**So laden Sie das Zertifizierungsstellenzertifikat herunter:**

1. Auf dem Server, auf dem Exchange UM ausgeführt wird, klicken Sie auf **Start**, klicken Sie auf **Ausführen**, geben **http://\<Domänennamen für Ihre Zertifizierungsstelle ausstellen Server>/certsrv ein**, und klicken Sie dann auf **OK**.
2. Klicken Sie unter Wählen Sie Task aus, klicken Sie auf **Download einer Zertifizierungsstellen-Zertifikat, Zertifikatkette oder einer Zertifikatsperrliste**.
3. Klicken Sie unter **einer Zertifizierungsstellen-Zertifikat, Zertifikatkette oder einer Zertifikatsperrliste herunterladen**Kodierungsmethode **für Base 64**aus, und klicken Sie dann auf**Download des Zertifizierungsstellenzertifikats**.
   > [!NOTE]
   > Sie können auch die Distinguished Encoding Rules (DER) in diesem Schritt Codierung angeben. Wenn Sie wählen Sie aus DER Codierung, des Dateityps im nächsten Schritt dieses Verfahrens und in 10 **zum Installieren der Zertifizierungsstellen-Zertifikat Schritt** ist p7b und nicht CER. 
4. Klicken Sie im Dialogfeld **Dateidownload** klicken Sie auf **Speichern**, und speichern Sie die Datei auf der Festplatte auf dem Server. (Die Datei müssen entweder eine CER oder einer Erweiterung der P7B-Datei, je nach der Codierung, dass Sie im vorherigen Schritt ausgewählt haben.)

**So installieren Sie das Zertifizierungsstellenzertifikat:**

1. Öffnen Sie auf dem Server mit Exchange UM Microsoft Management Console (MMC) durch Klicken Sie auf **Start**, auf **Ausführen**klicken, im Feld Öffnen den **Befehl Mmc** eingeben und dann auf **OK**.
2. Klicken Sie im Menü **Datei** auf **Snap-In hinzufügen/entfernen**auf, und klicken Sie dann auf **Hinzufügen**.
3. Klicken Sie im Feld **Eigenständiges Snap-In hinzufügen** auf **Zertifikate**und klicken Sie dann auf **Hinzufügen**.
4. Klicken Sie im Dialogfeld **Zertifikat-Snap-In** auf **Computerkonto** und anschließend auf **Weiter**.
5. Überprüfen Sie im Dialogfeld **Computer auswählen** , ob die **lokalen Computer: (Computer, auf diese Konsole ausgeführt wird)** das Kontrollkästchen aktiviert ist, und klicken Sie dann auf **Fertig stellen**.
6. Klicken Sie auf **Schließen**, und klicken Sie dann auf **OK**. 
7. In der Konsolenstruktur den Knoten Sie **Zertifikate (lokaler Computer)**, erweitern Sie **Vertrauenswürdige Stammzertifizierungsstellen**, und klicken Sie dann auf **Zertifikate**.
8. Maustaste auf **Zertifikate**, klicken Sie auf **Alle Tasks**, und klicken Sie auf **Importieren**.
9. Klicken Sie auf **Weiter**. 
10. Klicken Sie auf **Durchsuchen** , um die Datei zu suchen, und klicken Sie dann auf **Weiter**. (Die Datei wird ein CER oder einer P7B-Datei-Erweiterung, je nach der Codierung, dass Sie in Schritt 3 des **, laden Sie das Zertifizierungsstellen-Zertifikat**ausgewählt haben.
11. Klicken Sie auf die **Option alle Zertifikate** in folgendem Speicher speichern.
12. Klicken Sie auf **Durchsuchen**, und wählen Sie **Vertrauenswürdige Stammzertifizierungsstellen**aus. 
13. Klicken Sie auf **Weiter** , um die Einstellungen zu überprüfen, und klicken Sie dann auf **Fertig stellen**. 


**So überprüfen, dass die Zertifizierungsstelle in der Liste der vertrauenswürdigen Stammzertifizierungsstellen aufgeführt ist:**

1. Klicken Sie auf dem Server mit Exchange UM in MMC den Knoten Sie Zertifikate (lokaler Computer), erweitern Sie vertrauenswürdige Stammzertifizierungsstellen, und klicken Sie dann auf Zertifikate.
2. Im Detailbereich stellen Sie sicher, dass Ihre Zertifizierungsstelle in der Liste der vertrauenswürdigen Zertifizierungsstellen ist.


