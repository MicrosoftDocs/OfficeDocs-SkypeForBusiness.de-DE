---
title: Konfigurieren der Weiterleitung von direkten
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 5/15/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: ''
description: Erfahren Sie, wie Microsoft Phone System direkte Routing konfigurieren.
ms.openlocfilehash: e2f9629de713c363de02124a922b21882853d54d
ms.sourcegitcommit: 92f2fa97c8870f8ad86c6001f2240a74261e2600
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/14/2018
---
# <a name="configure-direct-routing"></a>Konfigurieren der Weiterleitung von direkten

  > [!NOTE]
  > Dies ist eine Vorabversion der Microsoft Phone System direkten Routing.  Produktfunktionen und Dokumentation werden können geändert.

Wenn Sie dies nicht bereits geschehen ist, lesen [Planen direkten Routing](plan-direct-routing.md) für erforderliche Komponenten und zum Überprüfen der anderen Schritte müssen Sie ergreifen, bevor Sie das Telefonsystem Microsoft-Netzwerk konfigurieren. 

  > [!NOTE]
  > Dieses Dokument ist für IT-Experten vorgesehen.  

In diesem Artikel wird beschrieben, wie Microsoft Phone System direkten Routing konfigurieren. Es werden wie eine unterstützte Session Border Controller (SBC) zum direkten Routing Kopplung und zum Konfigurieren von Microsoft-Teams, Benutzer zum direkten Routing Verbindung zu im Public Switched Telephone Network, (PSTN) verwenden. Um die in diesem Artikel erläuterten Schritte ausgeführt haben, benötigen Administratoren mit PowerShell-Cmdlets vertraut. Weitere Informationen zum Verwenden von PowerShell finden Sie unter [Einrichten des Computers für Windows PowerShell](https://technet.microsoft.com/library/dn362831.aspx). 

Es wird empfohlen, dass Sie bestätigen, dass Ihre SBC bereits konfiguriert wurde, wie mithilfe des Herstellers Ihres SBC empfohlen: 

- Dokumentation zur Bereitstellung von AudioCodes 
- Dokumentation zur Bereitstellung von Menüband

Sie können Ihr Telefonsystem Microsoft konfigurieren und Aktivieren von Benutzern mithilfe von Direct Routing, und richten Sie Microsoft-Teams, als bevorzugte aufrufenden Clients anhand der folgenden Verfahren: 

- [Den SBC mit einem Microsoft-Telefonsystem Kopplung und überprüfen die Verbindung](#pair-the-sbc-to-direct-routing-service-of-phone-system)
- [Aktivieren von Benutzern für direkte Routingdienst](#enable-users-for-direct-routing-service)
- [Sicherstellen Sie, dass Microsoft-Teams, die bevorzugte aufrufende Client für die Benutzer ist](#set-microsoft-teams-as-the-preferred-calling-client-for-the-users) 

## <a name="pair-the-sbc-to-direct-routing-service-of-phone-system"></a>Den SBC um Routingdienst von Telefonsystem leiten Kopplung 

Es folgen drei allgemeinen Schritte ausführen, können Sie eine Verbindung herstellen oder Paaren Sie den SBC mit der direkten Routing-Schnittstelle: 

- Verbinden Sie mit **Skype für Business Online** -Verwaltungskonsole mithilfe von PowerShell 
- Paar die SBC 
- Überprüfen der Paarung 

### <a name="connect-to--skype-for-business-online-by-using-powershell"></a>Herstellen einer Verbindung mit Skype für Business Online mithilfe von PowerShell 

Eine PowerShell-Sitzung mit dem Mandanten verbunden können Sie den SBC mit der direkten Routing-Schnittstelle Kopplung. Um eine PowerShell-Sitzung zu öffnen, wenden Sie sich, befolgen Sie die Schritte in [Einrichten des Computers für Windows PowerShell](https://technet.microsoft.com/library/dn362831.aspx). 
 
Nachdem Sie eine PowerShell-Remotesitzung eingerichtet haben, überprüfen Sie, dass Sie die Befehle zum Verwalten des SBC sehen können. Um die Befehle zu überprüfen, geben Sie ein oder kopieren und Einfügen in der folgenden in der PowerShell-Sitzung und drücken Sie die EINGABETASTE: 

```
gcm *onlinePSTNGateway*
```

Der Befehl gibt die hier gezeigten vier Funktionen zurück, mit der Sie die SBCs verwalten können. 

```
CommandType    Name                       Version    Source 
-----------    ----                       -------    ------ 
Function       Get-CsOnlinePSTNGateway    1.0        tmp_v5fiu1no.wxt 
Function       New-CsOnlinePSTNGateway    1.0        tmp_v5fiu1no.wxt 
Function       Remove-CsOnlinePSTNGateway 1.0        tmp_v5fiu1no.wxt 
Function       Set-CsOnlinePSTNGateway    1.0        tmp_v5fiu1no.wxt
```   


### <a name="pair-the-sbc-to-the-tenant"></a>Paar die SBC beziehen, um den Mandanten 

So Paaren Sie die SBC beziehen, um den Mandanten in die PowerShell-Sitzung Folgendes ein, und drücken Sie die EINGABETASTE: 

```
New-CsOnlinePSTNGateway -Fqdn <SBC FQDN> -SipSignallingPort <SBC SIP Port> -MaxConcurrentSessions <Max Concurrent Sessions the SBC can handle> -Enabled $true 
```
  > [!NOTE]
  > 1. Es wird dringend empfohlen festlegen einen Grenzwert für den SBC mit Informationen, die in der Dokumentation SBC gefunden werden kann. Der Grenzwert wird eine Benachrichtigung auslösen, wenn SBC Ebene der Kapazität wird.
  > 2. Sie können nur den SBC mit FQDN, bei denen der Domänenteil des Namens eine der in Ihrem Mandanten entspricht, außer registrierte Domänen Kopplung \*. onmicrosoft.com. Mithilfe von \*. omicrosoft.com Domänennamen wird für die SBC-FQDN-Namen nicht unterstützt. Angenommen, Sie haben zwei Domänennamen:<br/><br/>
  > wobei **ABC**".xyz"<br/>**ABC**. onmicrosoft.com<br/><br/>
  > Für den Namen SBC können Sie den Namen sbc.abc.xyz. Wenn Sie versuchen, den SBC mit einem Namen sbc.xyz.abc Kopplung, wird das System können Sie nicht, wie die Domäne nicht diesen Mandanten gehört.

```
New-CsOnlinePSTNGateway -Identity sbc.contoso.com -Enabled $true -SipSignallingPort 5067 -MaxConcurrentSessions 100 
```
Gibt:
``` 
Identity              : sbc.contoso.com 
Fqdn                  : sbc.contoso.com 
SipSignallingPort     : 5067 
FailoverTimeSeconds   : 10 
ForwardCallHistory    : False 
ForwardPai            : False 
SendSipOptions        : True 
MaxConcurrentSessions : 100 
Enabled               : True   
```
Es sind zusätzliche Optionen, die während der Paarung festgelegt werden können. Im vorherigen Beispiel jedoch nur die mindestens erforderlichen Parameter angezeigt werden. 
 
Die folgende Tabelle enthält die zusätzlichen Parameter, die Sie beim Einrichten von Parametern für *Neu CsOnlinePstnGateway*verwenden können. 

|**Erforderlich?**|**Name**|**Beschreibung**|**Standard**|**Mögliche Werte**|**Typ und Einschränkungen**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|Ja|FQDN|Den Vollqualifizierten Domänennamen der SBC |Keine|NoneFQDN Name, Grenzwert 63 Zeichen|Zeichenfolge, die Liste der zulässigen / nicht zulässigen Zeichen auf [Namenskonventionen in Active Directory für Computer, Domänen, Sites und OUs](https://support.microsoft.com/en-us/help/909264)|
|Nein|MediaBypass |Der Parameter für die zukünftige Verwendung reserviert. Unterstützt die Medienumgehung der Parameter angegeben, der die SBC und der Administrator möchte, um es zu verwenden.|Keine|True<br/>False|Boolescher Wert|
|Ja|SipSignallingPort |Überwachungsport für die Kommunikation mit direktem Routing Services mithilfe des Protokolls Transport Layer Security (TLS) verwendet.|Keine|Alle Ports|zwischen 0 und 65535 |
|Nein|FailoverTimeSeconds |Bei Festlegung auf 10 (Standardwert), ausgehende Anrufe, die vom Gateway nicht innerhalb von 10 Sekunden beantwortet werden an den nächsten verfügbaren Trunk weitergeleitet werden; Wenn keine zusätzlichen Trunks vorhanden sind, wird der Anruf automatisch gelöscht. In einer Organisation mit langsamen Netzwerken und Gateway Antworten möglich, die potenziell Anrufe unnötig gelöscht wird. Der Standardwert ist 10.|10|Number|Int|
|Nein|ForwardCallHistory |Gibt an, ob Informationen zum Anrufverlauf durch den Trunk weitergeleitet werden. Falls aktiviert, sendet der Office 365-PSTN-Proxy zwei Header: "History-Info" und weitergeleitet durch. Der Standardwert ist **"false"** ($False). |False|True<br/>False|Boolescher Wert|
|Nein|ForwardPAI|Gibt an, ob der PAI-Header (P-Asserted-Identity) zusammen mit dem Anruf weitergeleitet wird. Mit dem PAI-Header lässt sich die Identität des Anrufers überprüfen. Der Standardwert ist **"false"** ($False).|False|True<br/>False|Boolescher Wert|
|Nein|SendSIPOptions |Legt fest, ob ein SBC wird oder die SIP-Optionen wird nicht gesendet. Wenn deaktiviert, wird der SBC aus der Überwachung und Warnung System ausgeschlossen werden. Es wird dringend empfohlen, dass Sie SIP-Optionen aktivieren. Standardwert ist **True**. |True|True<br/>False|Boolescher Wert|
|Nein|MaxConcurrentSessions |Wird vom System Warnungen verwendet. Wenn Sie einen beliebigen Wert festgelegt ist, generieren Alarm System eine Benachrichtigung an den mandantenadministrator wird die Anzahl der gleichzeitigen Sitzung 90 % oder höher ist als dieser Wert. Wenn der Parameter nicht festgelegt ist, werden keine Benachrichtigungen generiert. Jedoch meldet das System der Überwachung Anzahl gleichzeitiger Sitzungen alle 24 Stunden. |NULL|NULL<br/>1 bis 100.000 ||
|Nein|Aktiviert *|Zum Aktivieren dieser SBC für ausgehende Anrufe verwendet. Kann verwendet werden, um die SBC vorübergehend zu entfernen, während er aktualisiert wird oder während der Wartung. |False|True<br/>False|Boolescher Wert|
 
### <a name="verify-the-sbc-pairing"></a>Überprüfen Sie die SBC-Verbindung 

Überprüfen Sie die Verbindung aus: 
- Überprüfen Sie, ob in der Liste der kombinierte SBCs der SBC ist. 
- Überprüfen Sie die SIP-Optionen. 
 
#### <a name="validate-if-sbc-is-on-the-list-of-paired-sbcs"></a>Überprüfen Sie, ob in der Liste der kombinierte SBCs SBC ist 

Überprüfen Sie nachdem Sie die SBC Paar, dass der SBC mithilfe des folgenden Befehls in einer remote-PowerShell-Sitzung in der Liste der kombinierte SBCs vorhanden ist:`Get-CSOnlinePSTNGateway`

Kombinierte Gateway sollte in der Liste angezeigt wird, wie im folgenden Beispiel dargestellt, und stellen Sie sicher, dass der Parameter *Enabled* gibt den Wert **True**wird angezeigt. Geben Sie ein:

```
Get-CsOnlinePSTNGateway -Identity sbc.contoso.com  
```
Die zurückgibt:
``` 
Identity              : sbc.contoso.com  
Fqdn                  : sbc.contoso.com 
SipSignallingPort     : 5067 
CodecPriority         : SILKWB,SILKNB,PCMU,PCMA 
ExcludedCodecs        :  
FailoverTimeSeconds   : 10 
ForwardCallHistory    : False 
ForwardPai            : False 
SendSipOptions        : True 
MaxConcurrentSessions : 100 
Enabled               : True 
```

#### <a name="validate-sip-options-flow"></a>Überprüfen Sie die Optionen SIP-Fluss 

Um die Verbindung mit ausgehender SIP-Optionen zu überprüfen, verwenden Sie die SBC-Management-Schnittstelle und sehen Sie, dass der SBC 200 OK-Antworten den ausgehenden Optionen abrufen.
  
Beim direkten Routing Optionen für eingehende Faxe erkennt, wird gestartet senden ausgehende Optionen auf den SBC-FQDN im Feld Kopfzeile Kontakt in der eingehenden Nachricht Optionen konfiguriert. 

Um die Verbindung mit eingehenden SIP-Optionen zu validieren, verwenden Sie die SBC-Management-Schnittstelle und finden Sie, dass der SBC Antwort auf die Optionen für Nachrichten, die von direkten Routing wird und der Antwortcode 200 OK ist.  

## <a name="enable-users-for-direct-routing-service"></a>Aktivieren von Benutzern für direkte Routingdienst 

Wenn Sie so aktivieren Sie Benutzer für die direkte Routingdienst bereit sind, gehen Sie folgendermaßen vor: 

1. Erstellen eines Benutzers in Office 365 und eine Telefon-Lizenz zuweisen. 
2. Stellen Sie sicher, dass der Benutzer in Skype für Business Online verwaltet wird. 
3. Konfigurieren Sie die Telefonnummer ein, und aktivieren Sie Enterprise-VoIP und Voicemail. 
4. Konfigurieren von VoIP-routing. Die Route wird automatisch überprüft.  

### <a name="create-a-user-in-office-365-and-assign-the-license"></a>Erstellen eines Benutzers in Office 365 und Lizenz zuweisen 

Es gibt zwei Optionen zum Erstellen eines neuen Benutzers in Office 365. Jedoch wird empfohlen, dass Ihre Organisation wählen und verwenden eine Option, um routing Probleme zu vermeiden: 

- Erstellen Sie des Benutzers in Active Directory am Standort und synchronisieren Sie den Benutzer in die Cloud zu. Finden Sie unter [integrieren Ihre lokale Verzeichnisse mit Azure Active Directory](https://docs.microsoft.com/en-us/azure/active-directory/connect/active-directory-aadconnect).  
- Erstellen Sie den Benutzer direkt in Office 365-Administrator-Portal. Finden Sie unter [Benutzer einzeln oder in einer Sammeloperation zu Office 365 - Admin Hilfe hinzufügen](https://support.office.com/en-us/article/Add-users-individually-or-in-bulk-to-Office-365-Admin-Help-1970f7d6-03b5-442f-b385-5880b9c256ec). 

  Wenn Sie das System, das mit Skype für Business 2015 oder Lync 2010/2013 lokal vorhanden ist erstellen, ist die einzige unterstützte Option den Benutzer im lokalen Active Directory erstellen und Synchronisieren des Benutzers in die Cloud (Option 1). 

Lizenzen erforderlich: 

- Office 365 Enterprise E3 (einschließlich SfB Plan2, Exchange Plan2 und Teams) + Phone System  
- Office 365 Enterprise E5 (einschließlich SfB Plan2, Exchange Plan2, Teams und Telefonsystem) 

Optional Lizenzen: 

- Plan aufrufen 
- Audiokonferenz 

### <a name="ensure-that-the-user-is-homed-in-skype-for-business-online"></a>Stellen Sie sicher, dass der Benutzer in Skype für Business Online verwaltet wird 

Direktes Routing bewirkt, dass den Benutzer in Skype für Business Online verwaltet werden. Sie können dies überprüfen, anhand des RegistrarPool-Parameters. Es muss einen Wert in der Domäne infra.lync.com verfügen.

1. Verbinden Sie mit remote-PowerShell.
2. Geben Sie den Befehl: 

```
Get-CsOnlineUser -Identity "<User name>" | fl RegistrarPool
``` 

### <a name="configure-the-phone-number-and-enable-enterprise-voice-and-voicemail"></a>Konfigurieren Sie die Telefonnummer ein, und Aktivieren von Enterprise-VoIP und voicemail 

Nachdem Sie den Benutzer erstellt und eine Lizenz zugewiesen haben, besteht der nächste Schritt so konfigurieren Sie ihre Telefonnummer und Voicemail. Dies kann in einem Schritt erfolgen. 

So fügen Sie die Telefonnummer, und für Voicemail aktivieren:
 
1. Verbinden Sie mit einer remote-PowerShell-Sitzung. 
2. Geben Sie den Befehl aus: 
    
```
Set-CsUser -Identity "<User name>" -EnterpriseVoiceEnabled $true -HostedVoiceMail $true -OnPremLineURI tel:+ phone number
```

Um eine Rufnummer für den Benutzer "Software niedrig" hinzuzufügen, würden Sie beispielsweise Folgendes eingeben: 

```
Set-CsUser - “Spencer Low" -OnPremisLineURI tel:+14255388797 -EnterpriseVoiceEnabled $true -HostedVoiceMail $true
```

Die Rufnummer muss als eine vollständige e. 164-Rufnummer mit Ländercode konfiguriert werden. 

  > [!NOTE]
  > Wenn Telefonnummer des Benutzers lokal verwaltet wird, verwenden Sie lokale Skype für Business-Verwaltungsshell oder in der Systemsteuerung so konfigurieren Sie die Telefonnummer des Benutzers an. 

### <a name="configure-voice-routing"></a>Konfigurieren von VoIP-Routing 

Microsoft Telefonsystem hat einen routing Mechanismus, der einen Anruf an eine bestimmte SBC basierend auf gesendet werden können: 

- Nummernmuster aufgerufen 
- Nummernmuster + bestimmte Benutzer, der den Anruf tätigt aufgerufen
 
SBCs können als aktiv und backup festgelegt werden. Das bedeutet, wenn der SBC, der für diese Nummernmuster, oder Nummernmuster + bestimmten Benutzer als aktiv konfiguriert ist nicht verfügbar ist, und klicken Sie dann die Anrufe an eine Sicherung SBC weitergeleitet werden.
 
Anrufrouting aus den folgenden Elementen besteht: 
- VoIP Routing-Richtlinie – Container für PSTN-Verwendungen; kann an einen Benutzer oder mehreren Benutzern zugewiesen werden 
- PSTN-Verwendungen – Container für VoIP-Routen und PSTN-Verwendungen; können in unterschiedlichen VoIP-Routing-Richtlinien gemeinsam genutzt werden 
- VoIP-Routen-Muster und einen Satz von Online PSTN-Gateways für Anrufe verwendet, in dem anrufende Nummer mit dem Muster übereinstimmt 
- Online PSTN-Gateway - Zeiger SBC, speichert auch die Konfiguration, die angewendet wird, wenn der Anruf über den SBC, wie P-Asserted-Identity (PAI) nach vorne oder bevorzugte Codecs platziert wird. VoIP-Routen können hinzugefügt werden 

#### <a name="creating-a-voice-routing-policy-with-one-pstn-usage"></a>Erstellen einer VoIP-Routingrichtlinie mit einem PSTN-Verwendung 

Das folgende Diagramm zeigt zwei Beispiele für VoIP-Routingrichtlinien zurückgegeben in Anruffluss.

**Call Flow 1 (auf der linken Seite):** Wenn ein Benutzer einen Anruf an +1 425 XXX XX XX oder +1 206 XXX XX XX herstellt, wird der Anruf weitergeleitet, um SBC sbc1<span></span>. contoso.biz oder sbc2<span></span>. contoso.biz. Wenn weder sbc1<span></span>. contoso.biz noch sbc2<span></span>. contoso.biz verfügbar sind, wird der Anruf getrennt. 

**Call Flow 2 (auf der rechten Seite):** Wenn ein Benutzer einen Anruf an +1 425 XXX XX XX oder +1 206 XXX XX XX herstellt, wird der Anruf zuerst an SBC sbc1 weitergeleitet<span></span>. contoso.biz oder sbc2<span></span>. contoso.biz. Wenn weder SBC verfügbar ist, wird die Route mit niedrigere Priorität versucht (sbc3<span></span>. contoso.biz und sbc4<span></span>. contoso.biz). Wenn keines der SBCs verfügbar sind, wird der Anruf getrennt. 

![Beispiele für VoIP routing-Richtlinie](../../media/ConfigDirectRouting-VoiceRoutingPolicyExamples.png)

Während der VoIP-Route Prioritäten zugewiesen wird, werden die SBCs in die Routen in beiden Beispielen in zufälliger Reihenfolge getestet.

  > [!NOTE]
  > Wenn der Benutzer auch eine Microsoft aufrufen planen Lizenz besitzt, werden Anrufe an eine andere Zahl mit Ausnahme der Zielrufnummer entsprechen die Muster + +1 425 XXX XX XX oder +1 206 XXX XX XX in der Beispielkonfiguration gelöscht. Wenn der Benutzer eine Lizenz aufrufen planen verfügt, wird der Anruf automatisch entsprechend den Richtlinien von Microsoft aufrufen planen weitergeleitet. 

Microsoft aufrufen planen automatisch als die letzte Route gilt für alle Benutzer mit der Lizenz Microsoft aufrufen planen und erfordert keine zusätzlichen Aufruf Routingkonfiguration.

Im Beispiel in der folgenden Abbildung wird eine VoIP-Route zum Senden von Anrufen an alle anderen USA und Kanada Nummer (Anrufe, die an das gewählte übersetzende + 1 XXX XXX XX XX umgeleitet) hinzugefügt.

![Zeigt VoIP-routing-Richtlinie mit einer dritten route](../../media/ConfigDirectRouting-VoiceRoutingPolicywith3rdroute.png)

Verfügt ein Benutzer sowohl Lizenzen (Microsoft Telefonsystem und Microsoft aufrufen planen), wird für alle Anrufe automatisch Route verwendet. Wenn keine der rufnummernmuster in die der Administrator erstellt online VoIP-Routen, Route über Microsoft aufrufen Plan übereinstimmt.

Wenn der Benutzer nur Microsoft Telefonsystem verfügt, wird der Anruf getrennt, da keine passenden Regeln zur Verfügung stehen.

  > [!NOTE]
  > Die Priorität die Wert für die Route "Andere + 1" ist in diesem Fall unerheblich, wie es ist nur eine Route, die dem Muster + 1 entspricht XXX XXX XX XX. Wenn ein Benutzer einen Anruf an + 1 324 567 89 89 herstellt und sbc5.contoso.biz und sbc6.contoso.biz nicht verfügbar sind, wird der Anruf getrennt.

In der folgenden Tabelle werden die Konfiguration mit drei VoIP-Routen zusammengefasst. In diesem Beispiel werden alle drei Routen Teil der gleichen PSTN-Verwendung "Uns und Kanada" an.

|**PSTN-Verwendung**|**VoIP-route**|**Nummernmuster**|**Priorität**|**SBC**|**Beschreibung**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|UNS nur|"" Redmond "1"|^\\+ 1 (425\|206)(\d{7})$|1|sbc1<span></span>. contoso.biz<br/>sbc2<span></span>. contoso.biz|Aktive Route für gewählte Nummern +1 425 XXX XX XX oder +1 206 XXX XX XX|
|UNS nur|"" Redmond "2"|^\\+ 1 (425\|206)(\d{7})$|2|SBC3<span></span>. contoso.biz<br/>sbc4<span></span>. contoso.biz|Backup Route für die gewählte Nummern +1 425 XXX XX XX oder +1 206 XXX XX XX|
|UNS nur|"Andere + 1"|^\\+ 1 (\d{10}) $|3|sbc5<span></span>. contoso.biz<br/>sbc6<span></span>. contoso.biz|Weiterleiten von zur gewählte Nummern + 1 XXX XXX XX XX (mit Ausnahme von +1 425 XXX XX XX oder +1 206 XXX XX XX)|
|||||||

Alle Routen die PSTN-Verwendung "Uns und Kanada" zugeordnet sind, und die PSTN-Verwendung der VoIP-Routing-Richtlinie "Nur in den USA." zugeordnet ist In diesem Beispiel wird der Benutzer Spencer Low VoIP-routing-Richtlinie zugewiesen.

#### <a name="examples-of-call-routes"></a>Beispiele für anrufrouten

Im folgenden Beispiel wir wird gezeigt, wie Routen, PSTN-Verwendungen und Routing Richtlinien konfigurieren, und weisen wir die Richtlinie für den Benutzer.

**Schritt 1:** Erstellen Sie die PSTN-Verwendung "USA und Kanada".

Geben Sie in einer Skype für Business Remote-PowerShell-Sitzung Folgendes ein:

```
Set-CsOnlinePstnUsage  -Identity Global -Usage @{Add="US and Canada"}
```

Überprüfen Sie, dass die Verwendung durch Eingabe erstellt wurde: 
```
Get-CSOnlinePSTNUsage
``` 
Die eine Liste mit Namen zurückgibt, der abgeschnitten werden kann:
```
  Identity  : Global
  Usage     : {testusage, US and Canada, International, karlUsage. . .}
```
Im folgenden Beispiel sehen Sie das Ergebnis der Ausführung der PowerShell-Befehl *`(Get-CSOnlinePSTNUsage).usage`* vollständige Namen (nicht abgeschnitten) angezeigt.    
```
 testusage
 US and Canada
 International
 karlUsage
 New test env
 Tallinn Lab Sonus
 karlUsage2
 Unrestricted
 Two trunks
  ```

**Schritt 2:** Erstellen Sie in einer PowerShell-Sitzung in Skype für Business Online drei Routen: 1, 2 und andere + 1, Redmond "Redmond", wie in der vorherigen Tabelle. 

Wenn Sie um die Route "" Redmond "1" zu erstellen, geben Sie Folgendes ein:

  ```
  New-CsOnlineVoiceRoute -Identity "Redmond 1" -NumberPattern "^+1(425|206)
  (\d{7})$" -OnlinePstnGatewayList sbc1.contoso.biz, sbc2.contoso.biz -Priority 1 -OnlinePstnUsages "US and Canada"
  ```

Die zurückgibt:
```
Identity                : Redmond 1
Priority            : 1
Description         :
NumberPattern       : ^\+1(425|206) (\d{7})$
OnlinePstnUsages    : {US and Canada}
OnlinePstnGatewayList   : {sbc1.contoso.biz, sbc2.contoso.biz}
Name            : Redmond 1
SuppressCallerId    :
AlternateCallerId   :
```
Um die Route für Redmond 2 zu erstellen, geben Sie Folgendes ein:

```
New-CsOnlineVoiceRoute -Identity "Redmond 2" -NumberPattern "^\+1(425|206)
(\d{7})$" -OnlinePstnGatewayList sbc3.contoso.biz, sbc4.contoso.biz -Priority 2 -OnlinePstnUsages "US and Canada"
```

Um die anderen + 1-Route zu erstellen, geben Sie Folgendes ein:

```
New-CsOnlineVoiceRoute -Identity "Other +1" -NumberPattern "^\+1(\d{10})$"
-OnlinePstnGatewayList sbc5.contoso.biz, sbc6.contoso.biz -OnlinePstnUsages "US and Canada"
```

  > [!CAUTION]
  > Stellen Sie sicher, dass es sich bei Ihren reguläre Ausdruck in das Attribut NumberPattern Ausdruck zulässig ist. Sie können mithilfe dieser Website testen:[https://www.regexpal.com](https://www.regexpal.com)

In einigen Fällen besteht Bedarf für alle Anrufe an den gleichen SBC weitergeleitet. Verwenden Sie - NumberPattern ". *"

- Alle Anrufe an demselben SBC weiterleiten

    ```
    Set-CsOnlineVoiceRoute -id "Redmond 1" -NumberPattern "." 
     -OnlinePstnGatewayList sbc1.contoso.biz
    ```

Überprüfen Sie, ob Sie die Route durch Ausführen von ordnungsgemäß konfiguriert haben die `Get-CSOnlineVoiceRoute` Powershell-Befehl mit der Optionen wie dargestellt: 

```
New-CsOnlineVoiceRoute | Where-Object {($_.priority -eq 1) -or ($_.priority -eq 2) or ($_.priority -eq 4) -Identity "Redmond 1" -NumberPattern "^\+1(425|206) (\d{7})$" -OnlinePstnGatewayList sbc1.contoso.biz, sbc2.contoso.biz -Priority 1 -OnlinePstnUsages "US and Canada"
```
Die zurückgegeben werden soll:
```
Identity            : Redmond 1 
Priority            : 1
Description     : 
NumberPattern       : ^\+1(425|206) (\d{7})$
OnlinePstnUsages    : {US and Canada}    
OnlinePstnGatewayList   : {sbc1.contoso.biz, sbc2.contoso.biz}
Name            : Redmond 1
Identity        : Redmond 2 
Priority            : 2
Description     : 
NumberPattern       : ^\+1(425|206) (\d{7})$
OnlinePstnUsages    : {US and Canada}    
OnlinePstnGatewayList   : {sbc3.contoso.biz, sbc4.contoso.biz}
Name            : Redmond 2
    
Identity        : Other +1 
Priority            : 4
Description     : 
NumberPattern       : ^\+1(425|206) (\d{7})$
OnlinePstnUsages    : {US and Canada}    
OnlinePstnGatewayList   : {sbc5.contoso.biz, sbc6.contoso.biz}
Name            : Other +1
```

Im Beispiel die Route, dass "Andere + 1" automatisch Priorität zugewiesen wurde. 

**Schritt 3:** Erstellen einer VoIP-Routing-Richtlinie "Nur USA" und Hinzufügen der Richtlinie die PSTN-Verwendung "USA und Kanada".

Geben Sie in einer PowerShell-Sitzung in Skype für Business Online Folgendes ein:

```
New-CsOnlineVoiceRoutingPolicy "US Only" -OnlinePstnUsages "US and Canada"
```

In diesem Beispiel wird das Ergebnis gezeigt:

```
Identity        : Tag:US only
OnlinePstnUsages    : {US and Canada}
Description         :
RouteType           : BYOT
```

**Schritt 4:** Dem Benutzer erteilen Sie Spence Low eine VoIP-routing-Richtlinie mithilfe von PowerShell.

- Geben Sie in einer Powershell-Sitzung in Skype für Business Online Folgendes ein:

    ```Grant-CsOnlineVoiceRoutingPolicy -Identity "Spencer Low" -PolicyName "US Only"```

- Überprüfen Sie die Zuordnung der Richtlinie, indem Sie folgenden Befehl eingeben:

```
Get-CsOnlineUser "Spencer Low" | select OnlineVoiceRoutingPolicy
```
Die zurückgibt:
```
OnlineVoiceRoutingPolicy
------------------------
US Only

```

#### <a name="creating-a-voice-routing-policy-with-several-pstn-usages"></a>Erstellen einer VoIP-Routing-Richtlinie mit mehreren PSTN-Verwendungen

Die VoIP-Routing-Richtlinie erstellt ermöglicht zuvor nur Anrufe an externe Telefonnummern in den USA und Kanada –, es sei denn, die Lizenz Microsoft aufrufen planen auch dem Benutzer zugewiesen ist.

Im folgenden Beispiel wird, können Sie die VoIP-Routing-Richtlinie "Ohne Einschränkungen." erstellen Die Richtlinie verwendet die PSTN-Verwendung "Uns und Kanada" erstellt, die im vorherigen Beispiel als auch die neuen PSTN-Verwendung "International". 

Dies leitet alle anderen Aufrufe der SBCs sbc2<span></span>. contoso.biz und sbc5<span></span>. contoso.biz. In den Beispielen, die angezeigt werden Zuweisen von uns nur die Richtlinie für Benutzer "Software niedrig" und keine Einschränkungen für den Benutzer "John Woods".

Software niedrig – zulässig Anrufe nur für die USA und Kanada Zahlen. Beim Aufruf von zu "Redmond" Nummern, muss dem spezifischen Berechtigungssatz SBC verwendet werden. Außerhalb der USA Zahlen werden nicht weitergeleitet werden, es sei denn, die Lizenz planen aufrufen, das dem Benutzer zugewiesen ist.

John Woods – Anrufe an eine beliebige Anzahl zulässig. Beim Aufruf von zu "Redmond" Nummern, muss dem spezifischen Berechtigungssatz SBC verwendet werden. Außerhalb der USA Rufnummern weitergeleitet werden über sbc2<span></span>. contoso.biz und sbc5<span></span>. contoso.biz.

![Zeigt die VoIP-Routingrichtlinie Benutzer Spencer Low zugewiesen ist](../../media/ConfigDirectRouting-VoiceRoutingPolicyAssignedtoSpencerLow.png)

Verfügt ein Benutzer sowohl Lizenzen (Microsoft Telefonsystem und Microsoft aufrufen planen), wird für alle Anrufe automatisch Route verwendet. Wenn keine der rufnummernmuster in die der Administrator erstellt online VoIP-Routen, Route über Microsoft aufrufen Plan übereinstimmt.

Wenn der Benutzer nur Microsoft Telefonsystem verfügt, wird der Anruf getrennt, da keine passenden Regeln zur Verfügung stehen.

![Zeigt die VoIP-Routingrichtlinie Benutzer John Woods zugewiesen ist](../../media/ConfigDirectRouting-VoiceRoutingPolicyAssignedtoJohnWoods.png)

In der folgenden Tabelle werden die routing Richtlinie "No Einschränkungen" Usage Bezeichnungen und VoIP-Routen zusammengefasst. 

|**PSTN-Verwendung**|**VoIP-route**|**Nummernmuster**|**Priorität**|**SBC**|**Beschreibung**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|UNS nur|"" Redmond "1"|^ + 1 (425\|206)(\d{7})$|1|sbc1<span></span>. contoso.biz<br/>sbc2<span></span>. contoso.biz|Aktive Route für angerufenen Zahlen +1 425 XXX XX XX oder +1 206 XXX XX XX|
|UNS nur|"" Redmond "2"|^ + 1 (425\|206)(\d{7})$|2|SBC3<span></span>. contoso.biz<br/>sbc4<span></span>. contoso.biz|Backup Route für angerufenen Zahlen +1 425 XXX XX XX oder +1 206 XXX XX XX|
|UNS nur|"Andere + 1"|^ + 1 (\d{10}) $|3|sbc5<span></span>. contoso.biz<br/>sbc6<span></span>. contoso.biz|Route für angerufenen Zahlen + 1 XXX XXX XX XX (mit Ausnahme von +1 425 XXX XX XX oder +1 206 XXX XX XX)|
|International|International|\d+|4|sbc2<span></span>. contoso.biz<br/>sbc5<span></span>. contoso.biz|Route für alle Nummernmuster |


  > [!NOTE]
  > - Die Reihenfolge der PSTN-Verwendungen in VoIP-Routing-Richtlinien ist wichtig. Die Verwendungen in Reihenfolge angewendet werden, und wenn in der ersten Verwendung eine Übereinstimmung gefunden wird, klicken Sie dann andere Verwendungen werden nie ausgewertet. Die PSTN-Verwendung "International" muss nach der PSTN-Verwendung "Uns nur." platziert werden Führen Sie zum Ändern der Reihenfolge der PSTN-Verwendungen, die `Set-CSOnlineRouteRoutingPolicy` Befehl. <br/>Ändern die Reihenfolge von "Uns und Kanada" beispielsweise vor- und "International" Sekunde bis zu der umgekehrten Reihenfolge ausführen:<br/>   `Set-CsOnlineVoiceRoutingPolicy -id tag:"no Restrictions" -OnlinePstnUsages @{Replace="International", "US and Canada"}`
 > - Die Priorität für "Andere + 1" und "International" VoIP-Routen werden automatisch zugewiesen. Diese nicht von Bedeutung sind, solange sie niedrigere Prioritäten als "" Redmond "1" und "Redmond 2" besitzen

#### <a name="example-of-voice-routing-policy-for-user-john-woods"></a>Beispiel für VoIP-Routing-Richtlinie für den Benutzer John Woods

Die Schritte zum Erstellen von PSTN-Verwendung "International", VoIP-Route "International", VoIP-Routing-Richtlinie "No Einschränkungen,", und klicken Sie dann den Benutzer "John Woods" zuweisen lauten wie folgt.


1.  Erstellen Sie zunächst die PSTN-Verwendung "International". Geben Sie in einer PowerShell-Remotesitzung in Skype für Business Online Folgendes ein:

  ```
  Set-CsOnlinePstnUsage  -Identity Global -Usage @{Add="International"}
  ```

2.  Im nächsten Schritt erstellen Sie die neue VoIP-Route "International".

  ```
  New-CsOnlineVoiceRoute -Identity "International" -NumberPattern "\d+" -OnlinePstnGatewayList sbc2.contoso.biz, sbc5.contoso.biz -OnlinePstnUsages "International"
  ```
  Die zurückgibt:

  ```
  Identity                  : International 
  Priority                      : 5
  Description                   : 
  NumberPattern                 : \d+
  OnlinePstnUsages          : {International}    
  OnlinePstnGatewayList           : {sbc2.contoso.biz, sbc5.contoso.biz}
  Name                            : International
  SupressCallerId           :
  AlternateCallerId         :
  ```
3.  Im nächsten Schritt erstellen Sie eine VoIP-Routing-Richtlinie "Ohne Einschränkungen". Die PSTN-Verwendung "" Redmond "1" und "Redmond" werden in dieser VoIP-Routingrichtlinie besondere Behandlung für Aufrufe von "+1 425 XXX XX XX" und "+1 206 XXX XX XX" als lokale oder am Standort Aufrufe nummerieren beibehalten wiederverwendet werden.

    ```New-CsOnlineVoiceRoutingPolicy "No Restrictions" -OnlinePstnUsages "US and Canada", ”International”```

    Beachten Sie Reihenfolge PSTN-Verwendungen:

    a. Wenn der Anruf an "+ 1425 XXX XX XX" mit der Verwendungen wie im folgenden Beispiel konfiguriert, den Aufruf folgt die Route in Verwendung "Uns und Kanada" festgelegt und die spezielle Routinglogik angewendet werden. Das heißt, wird der Anruf über sbc1 weitergeleitet<span></span>. contoso.biz und sbc2<span></span>. contoso.biz und anschließend sbc3<span></span>. contoso.biz und sbc4<span></span>. contoso.biz als die Sicherungen Routen. 

    b.  Ist "International" PSTN-Verwendung vor "Uns und Kanada", Anrufe an + 1425 XXX XX XX werden an weitergeleitet, sbc2<span></span>. contoso.biz und sbc5<span></span>. contoso.biz als Teil der Routinglogik. Geben Sie den Befehl aus:

    ```New-CsOnlineVoiceRoutingPolicy "No Restrictions" -OnlinePstnUsages "US and Canada", ”International”```

   Die zurückgibt

   ```
   Identity     : International 
   OnlinePstnUsages     : {US and Canada, International}     
   Description      :  
   RouteType        : BYOT
   ```

4.  Weisen Sie die VoIP-routing-Richtlinie für den Benutzer "John Woods" mit dem folgenden Befehl.

  ```
  Grant-CsOnlineVoiceRoutingPolicy -Identity "John Woods" -PolicyName "No Restrictions”
  ```

  Überprüfen Sie anschließend die Zuordnung mit dem Befehl aus:   

  ```
  Get CsOnlineUser “John Woods” | Select OnlineVoiceRoutingPolicy
  ```
  Die zurückgibt:

  ```
  OnlineVoiceRoutingPolicy
  ------------------------
  No Restrictions
  ```

Das Ergebnis ist, dass die VoIP-Richtlinie auf John Woods Anrufe angewendet werden nicht eingeschränkt, und die Logik des Routings ausgehender Anrufe für den Aufruf von USA, Kanada und International verfügbaren vor.

## <a name="enable-calling-for-microsoft-teams"></a>Aktivieren Sie Anrufe für Microsoft-Teams

Bevor ein Benutzer auf die Registerkarte Anrufe in Microsoft-Teams, sehen kann, müssen Sie private Anrufe für den Mandanten in Microsoft-Teams zu aktivieren. Gehen Sie dazu so vor:

1.  Melden Sie sich als mandantenadministrator für das Office 365 Admin Center.
2.  Wechseln Sie zu **Einstellungen und Dienste und -add-ins** , und wählen Sie **Microsoft-Teams**. 
3.  Erweitern Sie **Anrufe und Besprechungen** , und überprüfen Sie, dass **Aufrufen von privaten zulassen** **aktiviert**ist.

    ![Screenshot des privaten aufrufen eingeschaltet zulassen.](../../media/ConfigDirectRouting-CallsandMeetingsDialog.png)

## <a name="set-microsoft-teams-as-the-preferred-calling-client-for-the-users"></a>Festlegen Sie Microsoft-Teams für die Benutzer als bevorzugter Client aufrufende

Direktes Routing leitet Anrufe nur für Microsoft-Teams, müssen Sie sicherstellen, dass Microsoft-Teams, die bevorzugte aufrufende Client für die Benutzer ist. Dies wird durch die TeamsCallingPolicy und die TeamsInteropPolicy gesteuert. 

1. Verwenden Sie das folgende Cmdlet zuerst in einer PowerShell-Remotesitzung in der Skype für Business Online Administrationscenter, welche Richtlinien finden Sie unter der Benutzer zugewiesen wurde. 

  ```
  Get-CsOnlineUser -identity <User Name> | fl *teams*
  ```
 
2. Im nächsten Schritt überprüfen Sie die andere Richtlinieninstanzen. 

  ```
  Get-CsTeamsCallingPolicy
  ``` 
 und 

  ```
  Get-CsTeamsInteropPolicy
  ``` 

Bevor Benutzer Microsoft-Teams, den Dienst verwenden können, sind zusätzliche Schritte, die Sie möglicherweise durchführen müssen, um die aufrufende Richtlinie anwenden und Anrufe zulassen.

### <a name="teams-calling-policy"></a>Aufrufen der Richtlinie Teams

Sie müssen sicherstellen, dass der Benutzer eine TeamsCallingPolicy mit AllowCalling = True. Mit dieser Richtlinie kann die globale Richtlinie in Ihrem Mandanten oder eine bestimmte Richtlinie erteilt dem Benutzer sein. Wenn Sie einem Benutzer eine bestimmte Richtlinie erteilt werden müssen, können Sie das Cmdlet:

```
Grant-CsTeamsCallingPolicy -PolicyName <policy> -Identity <User Name>
```

### <a name="teams-interop-policy"></a>Teams Interop-Richtlinie

Stellen Sie sicher, dass der Benutzer den aufrufenden bevorzugten Client festzulegen, der Microsoft-Teams, verfügt. Dies kann auf zwei Arten erfolgen:

- Der Benutzer festgelegt aufrufenden bevorzugten Client in der Microsoft-Teams, Client.
- Der Benutzer hat eine Richtlinie zugewiesen wurde, die aufrufenden bevorzugten Client festgelegt.

Um eine Richtlinie zuweisen, die Microsoft-Teams, als bevorzugter Client aufrufende festlegt, stellen Sie sicher, dass der Benutzer eine Richtlinie mit CallingDefaultClient eingeholt wurde = Teams. Nachfolgend sehen Sie ein Beispiel-Cmdlet:

```
Grant-CsTeamsInteropPolicy -PolicyName DisallowOverrideCallingTeamsChatTeams -Identity “<User Name>”
```

## <a name="see-also"></a>Siehe auch

[Planen der direkten Routing](plan-direct-routing.md)
