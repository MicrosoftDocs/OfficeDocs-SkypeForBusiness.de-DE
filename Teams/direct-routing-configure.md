---
title: Konfigurieren von direktem Routing
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
localization_priority: Normal
search.appverid: MET150
ms.collection:
- Teams_ITAdmin_Help
- M365-voice
appliesto:
- Microsoft Teams
description: Erfahren Sie, wie Sie das direkte Routing für das Microsoft-Telefonsystem konfigurieren.
ms.openlocfilehash: d1a763f150004b5c558dd311dd54ed6975dcb0c1
ms.sourcegitcommit: 6b73b89f29a0eabbd9cdedf995d5325291594bac
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2019
ms.locfileid: "37018768"
---
# <a name="configure-direct-routing"></a>Konfigurieren von direktem Routing

> [!Tip]
> Schauen Sie sich die folgende Sitzung mit Informationen zu den Vorteilen von Direct Routing sowie dessen Planung und Bereitstellung an: [Direct Routing in Microsoft Teams](https://aka.ms/teams-direct-routing)

Lesen Sie [Planen des direkten Routings](direct-routing-plan.md), falls Sie dies noch nicht getan haben, um weitere Informationen zu Voraussetzungen und weiteren Schritten zu erhalten, die Sie ausführen müssen, bevor Sie das Netzwerk Ihres Microsoft-Telefonsystems konfigurieren. 

In diesem Artikel wird beschrieben, wie Sie das direkte Routing für das Microsoft-Telefonsystem konfigurieren. Sie erfahren, wie Sie einen unterstützten Session Border Controller (SBC) mit Direct Routing koppeln und wie Microsoft Teams-Benutzer für die Verwendung von Direct Routing konfiguriert werden, um eine Verbindung mit dem öffentlichen Telefonfestnetz (PSTN) herzustellen. Um die in diesem Artikel beschriebenen Schritte ausführen zu können, müssen Administratoren mit PowerShell-Cmdlets vertraut sein. Weitere Informationen zur Verwendung von PowerShell finden Sie unter [Einrichten Ihres Computers für Windows PowerShell](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell). 

Sie sollten sich unbedingt vergewissern, dass Ihr SBC bereits gemäß der Empfehlung Ihres SBC-Herstellers konfiguriert wurde: 

- [AudioCodes-Bereitstellungsdokumentation](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/direct-routing-for-microsoft-teams)
- [Oracle-Bereitstellungsdokumentation](https://www.oracle.com/industries/communications/enterprise-session-border-controller/microsoft.html)
- [Ribbon Communications-Bereitstellungsdokumentation](https://ribboncommunications.com/solutions/enterprise-solutions/microsoft-solutions/direct-routing-microsoft-teams-calling)
- [TE-Systems (anynode)-Bereitstellungsdokumentation](https://www.anynode.de/anynode-and-microsoft-teams/)

Sie können Ihr Microsoft-Telefonsystem konfigurieren und Benutzern die Verwendung des direkten Routings ermöglichen und dann anhand der folgenden Vorgehensweisen Microsoft Teams als bevorzugten Anrufclient einrichten: 

- [Koppeln des SBC mit einem Microsoft-Telefonsystem und Überprüfen der Kopplung](#pair-the-sbc-to-the-direct-routing-service-of-phone-system)
- [Aktivieren von Benutzern für den Direct Routing-Dienst](#enable-users-for-direct-routing-service)
- Sicherstellen, dass Microsoft Teams der bevorzugte Anrufclient für die Benutzer ist

## <a name="pair-the-sbc-to-the-direct-routing-service-of-phone-system"></a>Koppeln des SBC mit dem Direct Routing-Dienst des Telefonsystems 

Nachstehend finden Sie die drei allgemeinen Schritte, mit denen Sie den SBC mit der Direct Routing-Schnittstelle verbinden oder koppeln können: 

- Herstellen einer Verbindung mit dem **Skype for Business Online** Admin Center mithilfe von PowerShell 
- Koppeln des SBC 
- Überprüfen der Kopplung 

### <a name="connect-to-skype-for-business-online-by-using-powershell"></a>Herstellen einer Verbindung mit Skype for Business Online mithilfe von PowerShell 

Sie können eine PowerShell-Sitzung verwenden, die mit dem Mandanten verbunden ist, um den SBC mit der Direct Routing-Schnittstelle zu koppeln. Wenn Sie eine PowerShell-Sitzung öffnen möchten, führen Sie die Schritte unter [Einrichten Ihres Computers für Windows PowerShell](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell) aus. 
 
Nachdem Sie eine PowerShell-Remotesitzung eingerichtet haben, überprüfen Sie, ob Sie die Befehle zum Verwalten des SBC sehen können. Um die Befehle zu überprüfen, geben Sie in der PowerShell-Sitzung Folgendes ein, und drücken Sie dann die EINGABETASTE: 

```
Get-Command *onlinePSTNGateway*
```

Der Befehl gibt die vier hier gezeigten Funktionen zurück, mit denen Sie den SBC verwalten können. 

<pre>
CommandType    Name                       Version    Source 
-----------    ----                       -------    ------ 
Function       Get-CsOnlinePSTNGateway    1.0        tmp_v5fiu1no.wxt 
Function       New-CsOnlinePSTNGateway    1.0        tmp_v5fiu1no.wxt 
Function       Remove-CsOnlinePSTNGateway 1.0        tmp_v5fiu1no.wxt 
Function       Set-CsOnlinePSTNGateway    1.0        tmp_v5fiu1no.wxt
</pre>   


### <a name="pair-the-sbc-to-the-tenant"></a>Koppeln des SBC an den Mandanten 

Um den SBC mit dem Mandanten zu koppeln, geben Sie in der PowerShell-Sitzung Folgendes ein, und drücken Sie dann die EINGABETASTE: 

```
New-CsOnlinePSTNGateway -Fqdn <SBC FQDN> -SipSignallingPort <SBC SIP Port> -MaxConcurrentSessions <Max Concurrent Sessions the SBC can handle> -Enabled $true 
```
  > [!NOTE]
  > 1. Es wird dringend empfohlen, mithilfe der Informationen in der SBC-Dokumentation im SBC einen maximalen Anrufgrenzwert festzulegen. Der Grenzwert löst eine Benachrichtigung aus, wenn der SBC die Kapazität erreicht hat.
  > 2. Sie können den SBC nur dann koppeln, wenn der Domänenanteil des FQDN mit einer der Domänen übereinstimmt, die in Ihrem Mandanten registriert sind, mit Ausnahme von \*.onmicrosoft.com. Die Verwendung von \*.onmicrosoft.com-Domänennamen wird für FQDN-Namen des SBC nicht unterstützt. Wenn Sie beispielsweise über zwei Domänennamen verfügen:<br/><br/>
  > **contoso**.com<br/>**contoso**.onmicrosoft.com<br/><br/>
  > Sie können den Namen „sbc.contoso.com“ für den SBC-Namen verwenden. Wenn Sie versuchen, den SBC mit dem Namen „sbc.contoso.abc“ zu koppeln, lässt das System dies nicht zu, da diese Domäne nicht Eigentümer dieses Mandanten ist.<br/>
  > Zusätzlich zu der Domäne, die in Ihrem Mandanten registriert ist, ist es wichtig, dass ein Benutzer mit dieser Domäne und eine zugewiesene E3- oder E5-Lizenz vorhanden sind. Andernfalls wird folgender Fehler angezeigt:<br/>
  `Can not use the “sbc.contoso.com” domain as it was not configured for this tenant`.

```
New-CsOnlinePSTNGateway -Identity sbc.contoso.com -Enabled $true -SipSignallingPort 5067 -MaxConcurrentSessions 100 
```
Rückgabewerte:
<pre>
Identity              : sbc.contoso.com 
Fqdn                  : sbc.contoso.com 
SipSignallingPort     : 5067 
FailoverTimeSeconds   : 10 
ForwardCallHistory    : False 
ForwardPai            : False 
SendSipOptions        : True 
MaxConcurrentSessions : 100 
Enabled               : True   
</pre>
Während des Kopplungsprozesses können zusätzliche Optionen festgelegt werden. Im vorherigen Beispiel werden jedoch nur die minimal erforderlichen Parameter angezeigt. 
 
In der folgenden Tabelle sind die zusätzlichen Parameter aufgelistet, die Sie zum Festlegen von Parametern für `New-CsOnlinePstnGateway` verwenden können.

|Pflichtfeld?|Name|Beschreibung|Standard|Mögliche Werte|Typ und Einschränkungen|
|:-----|:-----|:-----|:-----|:-----|:-----|
|Ja|FQDN|Der FQDN-Name des SBC |Keiner|NoneFQDN-Name, Begrenzung 63 Zeichen|Zeichenfolge, Liste der zulässigen und nicht zulässigen Zeichen in [Benennungskonventionen in Active Directory für Computer, Domänen, Websites und OUs](https://support.microsoft.com/help/909264)|
|Nein|MediaBypass |Der Parameter ist zur zukünftigen Verwendung reserviert. Der vom SBC angegebene Parameter unterstützt die Medienumgehung, und der Administrator möchte diese verwenden.|Keiner|Wahr<br/>False|Boolesch|
|Ja|SipSignallingPort |Überwachungsport für die Kommunikation mit Direct Routing-Diensten über das TLS-Protokoll (Transport Layer Security).|Keiner|Beliebiger Port|0 bis 65535 |
|Nein|FailoverTimeSeconds |Beim Standardwert „True“ werden ausgehende Anrufe, die nicht innerhalb von zehn Sekunden vom Gateway angenommen werden, an das nächste verfügbare Gateway weitergeleitet. Wenn keine zusätzlichen Trunks vorhanden sind, wird der Anruf automatisch getrennt. In einer Organisation mit langsamen Netzwerken und Gatewayreaktionen kann dies dazu führen, dass Anrufe unnötig getrennt werden. Der Standardwert ist 10.|10|Zahl|Int|
|Nein|ForwardCallHistory |Gibt an, ob Informationen zum Anrufverlauf durch den Trunk weitergeleitet werden. Wenn diese Option aktiviert ist, sendet der Office 365-PSTN-Proxy zwei Header: „History-info“ und „Referred-By“. Der Standardwert ist **False** ($False). |False|Wahr<br/>False|Boolesch|
|Nein|ForwardPAI|Gibt an, ob der P-Asserted-Identity (PAI)-Header zusammen mit dem Anruf weitergeleitet wird. Der PAI-Header bietet eine Möglichkeit zum Überprüfen der Identität des Anrufers. Wenn diese Option aktiviert ist, wird auch der Header „Privacy:ID“ gesendet. Der Standardwert ist **False** ($False).|False|Wahr<br/>False|Boolesch|
|Nein|SendSIPOptions |Definiert, ob ein SBC die SIP-Optionen sendet oder nicht. Wenn diese Option deaktiviert ist, wird der SBC vom Überwachungs-und Benachrichtigungssystem ausgeschlossen. Es wird dringend empfohlen, dass Sie die SIP-Optionen aktivieren. Der Standardwert ist **True**. |Wahr|Wahr<br/>False|Boolesch|
|Nein|MaxConcurrentSessions |Wird vom Benachrichtigungssystem verwendet. Wenn ein Wert festgelegt ist, wird vom Benachrichtigungssystem eine Benachrichtigung an den Mandantenadministrator generiert, wenn die Anzahl der gleichzeitigen Sitzungen 90 % oder höher als dieser Wert ist. Wenn der Parameter nicht festgelegt ist, werden keine Benachrichtigungen generiert. Das Überwachungssystem meldet jedoch alle 24 Stunden die Anzahl von gleichzeitigen Sitzungen. |Null|Null<br/>1 bis 100.000 ||
|Nein|MediaRelayRoutingLocationOverride |Hiermit können Sie den Pfad für Medien manuell auswählen. Beim direkten Routing wird ein Rechenzentrum für den Medienpfad zugewiesen, der auf der öffentlichen IP des SBC basiert. Wir wählen immer das dem SBC-Rechenzentrum nächstgelegene Rechenzentrum aus. In einigen Fällen kann eine öffentliche IP-Adresse, z. B. aus einem amerikanischen Bereich, einem SBC in Europa zugewiesen werden. In diesem Fall wird nicht der optimale Medienpfad verwendet. Dieser Parameter ermöglicht das manuelle Festlegen der bevorzugten Region für den Mediendatenverkehr. Es wird empfohlen, diesen Parameter nur festzulegen, wenn die Anrufprotokolle deutlich erkennen lassen, dass die automatische Zuordnung des Rechenzentrums für den Medienpfad dem SBC-Rechenzentrum nicht das nächstgelegene Rechenzentrum des SBC-Rechenzentrums ist. |Keiner|Ländercodes im ISO-Format||
|Nein|Aktiviert|Wird verwendet, um diesen SBC für ausgehende Anrufe zu aktivieren. Kann verwendet werden, um den SBC vorübergehend zu entfernen, während er aktualisiert wird, oder während der Wartung. |False|Wahr<br/>False|Boolesch|
 
### <a name="verify-the-sbc-pairing"></a>Überprüfen der SBC-Kopplung 

Überprüfen Sie die Verbindung: 
- Überprüfen Sie, ob sich der SBC in der Liste der gekoppelten SBCs befindet. 
- Überprüfen Sie die SIP-Optionen. 
 
#### <a name="validate-if-the-sbc-is-on-the-list-of-paired-sbcs"></a>Überprüfen, ob sich der SBC in der Liste der gekoppelten SBCs befindet 

Überprüfen Sie nach der Kopplung des SBC, ob der SBC in der Liste der gekoppelten SBCS vorhanden ist, indem Sie den folgenden Befehl in einer PowerShell-Remotesitzung ausführen: `Get-CSOnlinePSTNGateway`

Das gekoppelte Gateway sollte wie im Beispiel unten in der Liste angezeigt werden und überprüfen, dass für den Parameter *Aktiviert* der Wert **True** angezeigt wird. Geben Sie Folgendes ein:

```
Get-CsOnlinePSTNGateway -Identity sbc.contoso.com  
```
Dadurch wird Folgendes zurückgegeben:
<pre>
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
</pre>

#### <a name="validate-sip-options-flow"></a>Überprüfen des SIP-Optionsflusses 

Um die Kopplung mithilfe ausgehender SIP-Optionen zu überprüfen, verwenden Sie die SIP-Verwaltungsschnittstelle, und bestätigen Sie, dass der SBC „200 OK“-Antworten auf seine ausgehenden OPTIONS-Nachrichten empfängt.

Wenn das direkte Routing eingehende OPTIONS-Nachrichten sieht, sendet es ausgehende SIP-OPTIONS-Nachrichten an den SBC-FQDN, der im Headerfeld „Kontakt“ in der eingehenden OPTIONS-Nachricht konfiguriert ist. 

Verwenden Sie zum Überprüfen der Kopplung mithilfe der eingehenden SIP-Optionen die SBC-Verwaltungsoberfläche, und stellen Sie sicher, dass der SBC eine Antwort auf die OPTIONS-Nachrichten sendet, die von Direct Routing eintreffen, und dass der gesendete Antwortcode „200 OK“ lautet.

## <a name="enable-users-for-direct-routing-service"></a>Aktivieren von Benutzern für den Direct Routing-Dienst 

Führen Sie die folgenden Schritte aus, wenn Sie bereit sind, die Benutzer für den Direct Routing-Dienst zu aktivieren: 

1. Erstellen Sie einen Benutzer in Office 365, und weisen Sie eine Telefonsystemlizenz zu. 
2. Stellen Sie sicher, dass der Benutzer in Skype for Business Online verwaltet wird. 
3. Konfigurieren Sie die Telefonnummer, und aktivieren Sie Enterprise-VoIP und Voicemail. 
4. Konfigurieren Sie das VoIP-Routing. Die Route wird automatisch überprüft.

### <a name="create-a-user-in-office-365-and-assign-the-license"></a>Erstellen Sie einen Benutzer in Office 365, und weisen Sie die Lizenz zu. 

Es gibt zwei Optionen für das Erstellen eines neuen Benutzers in Office 365. Es wird jedoch empfohlen, dass sich Ihre Organisation für eine Option entscheidet, um Routingprobleme zu vermeiden: 

- Erstellen Sie den Benutzer im lokalen Active Directory, und synchronisieren Sie den Benutzer mit der Cloud. Weitere Informationen finden Sie unter [Integrieren Ihrer lokalen Verzeichnisse in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect).
- Erstellen Sie den Benutzer direkt im Office 365-Administratorportal. Weitere Informationen finden Sie unter [Hinzufügen von einzelnen Benutzern oder Massenhinzufügen von Benutzern zu Office 365 – Administratorhilfe](https://support.office.com/article/Add-users-individually-or-in-bulk-to-Office-365-Admin-Help-1970f7d6-03b5-442f-b385-5880b9c256ec). 

Wenn Ihre Skype for Business Online-Bereitstellung gemeinsam mit Skype for Business 2015 oder Lync 2010/2013 lokal vorhanden ist, besteht die einzige unterstützte Option darin, den Benutzer im lokalen Active Directory zu erstellen und ihn mit der Cloud zu synchronisieren (Option 1). 

Erforderliche Lizenzen: 

- Office 365 Enterprise E3 (einschließlich SfB Plan2, Exchange Plan 2 und Teams) + Telefonsystem
- Office 365 Enterprise E5 (einschließlich SfB Plan2, Exchange Plan 2 und Teams) + Telefonsystem 

Optionale Lizenzen: 

- Anrufplan 
- Audiokonferenzen 

### <a name="ensure-that-the-user-is-homed-in-skype-for-business-online"></a>Stellen Sie sicher, dass der Benutzer in Skype for Business Online verwaltet wird. 

Direct Routing setzt voraus, dass der Benutzer in Skype for Business Online verwaltet wird. Sie können dies überprüfen, indem Sie sich den Parameter „RegistrarPool“ ansehen. Er muss einen Wert in der Domäne „infra.lync.com“ aufweisen.

1. Stellen Sie eine Verbindung zu Remote-PowerShell her.
2. Geben Sie den folgenden Befehl aus: 

```
Get-CsOnlineUser -Identity "<User name>" | fl RegistrarPool
``` 

### <a name="configure-the-phone-number-and-enable-enterprise-voice-and-voicemail"></a>Konfigurieren Sie die Telefonnummer, und aktivieren Sie Enterprise-VoIP und Voicemail. 

Nachdem Sie den Benutzer erstellt und eine Lizenz zugewiesen haben, besteht der nächste Schritt darin, die Telefonnummer und die Voicemail zu konfigurieren. Dies kann in einem Schritt erfolgen. 

So fügen Sie die Telefonnummer hinzu und aktivieren diese für Voicemail:
 
1. Stellen Sie eine Verbindung zu einer PowerShell-Sitzung her. 
2. Geben Sie den folgenden Befehl ein: 
 
```
Set-CsUser -Identity "<User name>" -EnterpriseVoiceEnabled $true -HostedVoiceMail $true -OnPremLineURI tel:<E.164 phone number>
```

Um beispielsweise eine Rufnummer für den Benutzer „Spencer Low“ hinzuzufügen, geben Sie Folgendes ein: 

```
Set-CsUser -Identity "Spencer Low" -OnPremLineURI tel:+14255388797 -EnterpriseVoiceEnabled $true -HostedVoiceMail $true
```

Die verwendete Rufnummer muss als vollständige E.164-Rufnummer mit Ländervorwahl konfiguriert werden. 

  > [!NOTE]
  > Wenn die Telefonnummer des Benutzers lokal verwaltet wird, können Sie die Telefonnummer des Benutzers mithilfe der lokalen Skype for Business-Verwaltungsshell oder über die Systemsteuerung konfigurieren. 

### <a name="configure-voice-routing"></a>Konfigurieren des VoIP-Routing 

Das Microsoft-Telefonsystem verfügt über einen Routingmechanismus, der die Übermittlung eines Anrufs an einen bestimmten SBC basierend auf Folgendem ermöglicht: 

- Muster der angerufenen Nummer 
- Muster der angerufenen Nummer + spezifischer Benutzer, der den Anruf tätigt
 
SBCs können als aktiv und als Backup festgelegt werden. Dies bedeutet: Wenn der SBC, der für dieses Nummernmuster oder für dieses Nummernmuster und den spezifischen Benutzer als aktiv konfiguriert wurde, nicht verfügbar ist, werden die Anrufe an einen Backup-SBC weitergeleitet.
 
Das Anrufrouting besteht aus den folgenden Elementen: 
- VoIP-Routingrichtlinie – Container für PSTN-Verwendungen; kann einem Benutzer oder mehreren Benutzern zugewiesen werden 
- PSTN-Verwendungen – Container für VoIP-Routen und PSTN-Verwendungen; kann in unterschiedlichen VoIP-Routing Richtlinien gemeinsam genutzt werden 
- VoIP-Routen – Nummernmuster und Gruppe von Online-PSTN-Gateways, die für Anrufe verwendet werden sollen, wenn die Anrufnummer mit dem Muster übereinstimmt 
- Online-PSTN-Gateway – Zeiger auf einen SBC, speichert außerdem die Konfiguration, die angewendet wird, wenn der Anruf über den SBC platziert wird, z. B. "P-Asserted-Identity (PAI)" oder „bevorzugte Codecs“; kann zu VoIP-Routen hinzugefügt werden 

#### <a name="creating-a-voice-routing-policy-with-one-pstn-usage"></a>Erstellen einer VoIP-Routingrichtlinie mit einer PSTN-Verwendung 

Das folgende Diagramm zeigt zwei Beispiele für VoIP-Routingrichtlinien im Anrufverlauf.

**Anrufverlauf 1 (links):** Wenn ein Benutzer einen Anruf an + 1 425 XXX XX XX oder + 1 206 XXX XX XX tätigt, wird der Anruf an den SBC „sbc1.contoso.biz“ oder „sbc2.contoso.biz“ weitergeleitet. Wenn weder „sbc1.contoso.biz“ noch „sbc2.contoso.biz“ verfügbar ist, wird der Anruf getrennt. 

**Anrufverlauf 2 (rechts):** Wenn ein Benutzer einen Anruf an + 1 425 XXX XX XX oder + 1 206 XXX XX XX tätigt, wird der Anruf zuerst an den SBC „sbc1.contoso.biz“ oder „sbc2.contoso.biz“ weitergeleitet. Wenn einer der SBCs nicht verfügbar ist, wird die Route mit der niedrigeren Priorität versucht (sbc3.contoso.biz und sbc4.contoso.biz). Wenn keiner der SBCS verfügbar ist, wird der Anruf getrennt. 

![Zeigt Beispiele für die VoIP-Routingrichtlinien](media/ConfigDirectRouting-VoiceRoutingPolicyExamples.png)

In beiden Beispielen werden die SBCs in den Routen in zufälliger Reihenfolge versucht, während der VoIP-Route Prioritäten zugewiesen werden.

  > [!NOTE]
  > Sofern der Benutzer nicht auch eine Lizenz für den Microsoft-Anrufplan hat, werden Anrufe an eine beliebige Nummer (mit Ausnahme von Nummern, die den Mustern +1 425 XXX XX XX oder +1 206 XXX XX XX in der Beispielkonfiguration entsprechen) getrennt. Wenn der Benutzer über eine Anrufplanlizenz verfügt, wird der Anruf automatisch gemäß den Richtlinien des Microsoft-Anrufplans geleitet. 

Der Microsoft-Anrufplan gilt automatisch als letzte Route für alle Benutzer mit der Microsoft-Anrufplanlizenz, und es ist keine zusätzliche Konfiguration für das Anrufrouting erforderlich.

In dem Beispiel in dem folgenden Diagramm wird eine VoIP-Route zum Senden von Anrufen an alle anderen US-amerikanischen und kanadischen Nummern hinzugefügt (Nummern, die dem Nummernmuster +1 XXX XXX XX XX entsprechen).

![Zeigt die VoIP-Routing Richtlinie mit einer dritten Route](media/ConfigDirectRouting-VoiceRoutingPolicywith3rdroute.png)

Für alle anderen Anrufe wird (wenn ein Benutzer sowohl eine Lizenz für das Microsoft-Telefonsystem als auch für den Microsoft-Anrufplan hat) die automatische Route verwendet. Wenn es keine Übereinstimmung mit Nummernmustern in den vom Administrator erstellten Online-VoIP-Routen gibt, erfolgt die Weiterleitung über den Microsoft-Anrufplan.

Wenn der Benutzer nur das Microsoft-Telefonsystem hat, wird der Anruf getrennt, da keine übereinstimmenden Regeln verfügbar sind.

  > [!NOTE]
  > In diesem Fall spielt der Prioritätswert für "Andere + 1" keine Rolle, da es nur eine Route gibt, die dem Muster + 1 XXX XXX XX XX entspricht. Wenn ein Benutzer einen Anruf an + 1 324 567 89 89 tätigt und weder „sbc5.contoso.biz“ noch „sbc6.contoso.biz“ verfügbar ist, wird der Anruf getrennt.

Die folgende Tabelle enthält eine Zusammenfassung der Konfiguration mit drei VoIP-Routen. In diesem Beispiel sind alle drei Routen Teil derselben PSTN-Verwendung "USA und Kanada".

|**PSTN-Verwendung**|**VoIP-Route**|**Nummernmuster**|**Priorität**|**SBC**|**Beschreibung**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|Nur USA|"Redmond 1"|^\\+1(425\|206)(\d{7})$|1|sbc1.contoso.biz<br/>sbc2.contoso.biz|Aktive Route für angerufene Nummern + 1 425 XXX XX XX oder + 1 206 XXX XX XX|
|Nur USA|"Redmond 2"|^\\+1(425\|206)(\d{7})$|2|sbc3.contoso.biz<br/>sbc4.contoso.biz|Backup-Route für angerufene Nummern + 1 425 XXX XX XX oder + 1 206 XXX XX XX|
|Nur USA|"Andere +1"|^\\+1(\d{10})$|3|sbc5.contoso.biz<br/>sbc6.contoso.biz|Route für angerufene Nummern +1 XXX XXX XX XX (mit Ausnahme von +1 425 XXX XX XX oder +1 206 XXX XX XX)|
|||||||

Alle Routen sind der PSTN-Verwendung „USA und Kanada“ zugeordnet, und die PSTN-Verwendung ist der VoIP-Routingrichtlinie „Nur USA“ zugeordnet. In diesem Beispiel wird die VoIP-Routingrichtlinie dem Benutzer Spencer Low zugewiesen.

#### <a name="examples-of-call-routes"></a>Beispiele für Anrufrouten

Im folgenden Beispiel wird gezeigt, wie Routen, PSTN-Verwendungen und Routingrichtlinien konfiguriert werden. Außerdem wird die Richtlinie dem Benutzer zugewiesen.

**Schritt 1:** Erstellen Sie die PSTN-Verwendung „USA und Kanada“.

Geben Sie in einer Skype for Business-PowerShell-Remotesitzung Folgendes ein:

```
Set-CsOnlinePstnUsage -Identity Global -Usage @{Add="US and Canada"}
```

Überprüfen Sie, ob die Verwendung erstellt wurde, indem Sie Folgendes eingeben: 
```
Get-CSOnlinePSTNUsage
``` 
Dadurch wird eine Liste von Namen zurückgegeben, die möglicherweise abgeschnitten sind:
```
  Identity  : Global
  Usage     : {testusage, US and Canada, International, karlUsage. . .}
```
Im nachstehenden Beispiel sehen Sie das Ergebnis der Ausführung des PowerShell-Befehls `(Get-CSOnlinePSTNUsage).usage` zum Anzeigen von vollständigen Namen (nicht abgeschnitten). 
<pre>
 testusage
 US and Canada
 International
 karlUsage
 New test env
 Tallinn Lab Sonus
 karlUsage2
 Unrestricted
 Two trunks
</pre>

**Schritt 2:** Erstellen Sie in einer PowerShell-Sitzung in Skype for Business Online drei Routen: „Redmond 1“, „Redmond 2“ und „Andere +1“, wie in der vorherigen Tabelle beschrieben. 

Zum Erstellen der Route „Redmond 1“ geben Sie Folgendes ein:

  ```
  New-CsOnlineVoiceRoute -Identity "Redmond 1" -NumberPattern "^\+1(425|206)
  (\d{7})$" -OnlinePstnGatewayList sbc1.contoso.biz, sbc2.contoso.biz -Priority 1 -OnlinePstnUsages "US and Canada"
  ```

Dadurch wird Folgendes zurückgegeben:
<pre>
Identity                : Redmond 1
Priority            : 1
Description         :
NumberPattern       : ^\+1(425|206) (\d{7})$
OnlinePstnUsages    : {US and Canada}
OnlinePstnGatewayList   : {sbc1.contoso.biz, sbc2.contoso.biz}
Name            : Redmond 1
</pre>
Zum Erstellen der Route „Redmond 2“ geben Sie Folgendes ein:

```
New-CsOnlineVoiceRoute -Identity "Redmond 2" -NumberPattern "^\+1(425|206)
(\d{7})$" -OnlinePstnGatewayList sbc3.contoso.biz, sbc4.contoso.biz -Priority 2 -OnlinePstnUsages "US and Canada"
```

Zum Erstellen der Route „Andere +1“ geben Sie Folgendes ein:

```
New-CsOnlineVoiceRoute -Identity "Other +1" -NumberPattern "^\+1(\d{10})$"
-OnlinePstnGatewayList sbc5.contoso.biz, sbc6.contoso.biz -OnlinePstnUsages "US and Canada"
```

  > [!CAUTION]
  > Stellen Sie sicher, dass Ihr regulärer Ausdruck im NumberPattern-Attribut einen gültigen Ausdruck darstellt. Sie können ihn auf dieser Website testen: [https://www.regexpal.com](https://www.regexpal.com)

In einigen Fällen müssen alle Anrufe an den gleichen SBC geleitet werden. Verwenden Sie in diesem Fall -NumberPattern ".*"

- Weiterleiten aller Anrufe an den gleichen SBC

    ```
    Set-CsOnlineVoiceRoute -id "Redmond 1" -NumberPattern ".*" 
     -OnlinePstnGatewayList sbc1.contoso.biz
    ```

Überprüfen Sie, ob Sie die Route korrekt konfiguriert haben, indem Sie den PowerShell-Befehl `Get-CSOnlineVoiceRoute` mithilfe der folgenden Optionen ausführen: 

```
Get-CsOnlineVoiceRoute | Where-Object {($_.priority -eq 1) -or ($_.priority -eq 2) or ($_.priority -eq 4) -Identity "Redmond 1" -NumberPattern "^\+1(425|206) (\d{7})$" -OnlinePstnGatewayList sbc1.contoso.biz, sbc2.contoso.biz -Priority 1 -OnlinePstnUsages "US and Canada"
```
Dadurch sollte Folgendes zurückgegeben werden:
<pre>
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
NumberPattern       : ^\+1(\d{10})$
OnlinePstnUsages    : {US and Canada}    
OnlinePstnGatewayList   : {sbc5.contoso.biz, sbc6.contoso.biz}
Name            : Other +1
</pre>

In diesem Beispiel wurde der Route "Andere + 1" automatisch die Priorität 4 zugewiesen. 

**Schritt 3:** Erstellen Sie eine VoIP-Routingrichtlinie „Nur USA“, und fügen Sie der Richtlinie die PSTN-Verwendung „USA und Kanada“ hinzu.

Geben Sie in einer PowerShell-Sitzung in Skype for Business Online Folgendes ein:

```
New-CsOnlineVoiceRoutingPolicy "US Only" -OnlinePstnUsages "US and Canada"
```

Das Ergebnis ist in diesem Beispiel zu sehen:

<pre>
Identity        : Tag:US only
OnlinePstnUsages    : {US and Canada}
Description         :
RouteType           : BYOT
</pre>

**Schritt 4:** Gewähren Sie dem Benutzer Spencer Low mithilfe von PowerShell eine VoIP-Routingrichtlinie.

- Geben Sie in einer PowerShell-Sitzung in Skype for Business Online Folgendes ein:

    ```Grant-CsOnlineVoiceRoutingPolicy -Identity "Spencer Low" -PolicyName "US Only"```

- Überprüfen Sie die Richtlinienzuweisung, indem Sie den folgenden Befehl eingeben:

```
Get-CsOnlineUser "Spencer Low" | select OnlineVoiceRoutingPolicy
```
Dadurch wird Folgendes zurückgegeben:
<pre>
    OnlineVoiceRoutingPolicy
    ---------------------
    US Only
</pre>

#### <a name="creating-a-voice-routing-policy-with-several-pstn-usages"></a>Erstellen einer VoIP-Routingrichtlinie mit mehreren PSTN-Verwendungen

Die zuvor erstellte VoIP-Routingrichtlinie lässt nur Anrufe an Telefonnummern in den USA und Kanada zu – es sei denn, dem Benutzer wurde auch die Microsoft-Anrufplanlizenz zugewiesen.

Im folgenden Beispiel können Sie die VoIP-Routingrichtlinie "Keine Einschränkungen" erstellen. Die Richtlinie verwendet die im vorherigen Beispiel erstellte PSTN-Verwendung „USA und Kanada“ sowie die neue PSTN-Verwendung „International“. 

Dadurch werden alle anderen Anrufe an den SBCS „sbc2.contoso.biz“ und „sbc5.contoso.biz“ weitergeleitet. In den gezeigten Beispielen wird dem Benutzer „Spencer Low“ die Richtlinie „Nur USA“ und dem Benutzer „John Woods die Richtlinie „Keine Einschränkungen“ zugewiesen.

Spencer Low – Es sind nur Anrufe an US-amerikanische und kanadische Rufnummern zulässig. Bei Anrufen an eine Nummer aus dem Redmond-Nummernbereich muss die spezifische Gruppe von SBCs verwendet werden. Nicht US-Nummern werden nicht weitergeleitet, es sei denn, die Anrufplanlizenz ist dem Benutzer zugewiesen.

John Woods – Es sind Anrufe an beliebige Nummern zulässig. Bei Anrufen an eine Nummer aus dem Redmond-Nummernbereich muss die spezifische Gruppe von SBCs verwendet werden. Nicht US-Nummern werden über „sbc2.contoso.biz“ und „sbc5.contoso.biz“ geleitet.

![Zeigt die dem Benutzer Spencer Low zugewiesene VoIP-Routingrichtlinie](media/ConfigDirectRouting-VoiceRoutingPolicyAssignedtoSpencerLow.png)

Für alle anderen Anrufe wird (wenn ein Benutzer sowohl eine Lizenz für das Microsoft-Telefonsystem als auch für den Microsoft-Anrufplan hat) die automatische Route verwendet. Wenn es keine Übereinstimmung mit Nummernmustern in den vom Administrator erstellten Online-VoIP-Routen gibt, erfolgt die Weiterleitung über den Microsoft-Anrufplan.

Wenn der Benutzer nur das Microsoft-Telefonsystem hat, wird der Anruf getrennt, da keine übereinstimmenden Regeln verfügbar sind.

![Zeigt die dem Benutzer John Woods zugewiesene VoIP-Routingrichtlinie](media/ConfigDirectRouting-VoiceRoutingPolicyAssignedtoJohnWoods.png)

Die folgende Tabelle enthält eine Zusammenfassung der Verwendungen der Routingrichtlinie „Keine Einschränkungen“ und VoIP-Routen. 

|**PSTN-Verwendung**|**VoIP-Route**|**Nummernmuster**|**Priorität**|**SBC**|**Beschreibung**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|Nur USA|"Redmond 1"|^\\+1(425\|206)(\d{7})$|1|sbc1.contoso.biz<br/>sbc2.contoso.biz|Aktive Route für angerufene Nummern + 1 425 XXX XX XX oder + 1 206 XXX XX XX|
|Nur USA|"Redmond 2"|^\\+1(425\|206)(\d{7})$|2|sbc3.contoso.biz<br/>sbc4.contoso.biz|Backup-Route für angerufene Nummern + 1 425 XXX XX XX oder + 1 206 XXX XX XX|
|Nur USA|"Andere +1"|^\\+1(\d{10})$|3|sbc5.contoso.biz<br/>sbc6>.contoso.biz|Route für angerufene Nummern +1 XXX XXX XX XX (mit Ausnahme von +1 425 XXX XX XX oder +1 206 XXX XX XX)|
|International|International|\d +|4|sbc2.contoso.biz<br/>sbc5.contoso.biz|Route für ein beliebiges Nummernmuster |


  > [!NOTE]
  > - Die Reihenfolge der PSTN-Verwendungen in VoIP-Routingrichtlinien ist wichtig. Die Verwendungen werden in der angegebenen Reihenfolge angewendet, und wenn eine Übereinstimmung in der ersten Verwendung gefunden wird, werden keine anderen Verwendungen ausgewertet. Die PSTN-Verwendung „International“ muss nach der PSTN-Nutzung „Nur USA“ platziert werden. Wenn Sie die Reihenfolge der PSTN-Verwendungen ändern möchten, führen Sie den Befehl `Set-CSOnlineVoiceRoutingPolicy` aus. <br/>Um beispielsweise die Reihenfolge von „USA und Kanada“ an erster Stelle und „International“ an zweiter Stelle umkehren möchten, führen Sie beispielsweise den folgenden Befehl aus:<br/> `Set-CsOnlineVoiceRoutingPolicy -id tag:"no Restrictions" -OnlinePstnUsages @{Replace="International", "US and Canada"}`
 > - Die Priorität für die VoIP-Routen „Andere + 1“ und „International“ wird automatisch zugewiesen. Sie spielt keine Rolle, solange Sie niedrigere Prioritäten als „Redmond 1“ und „Redmond 2“ haben.

#### <a name="example-of-voice-routing-policy-for-user-john-woods"></a>Beispiel der dem Benutzer John Woods zugewiesene VoIP-Routingrichtlinie

Die Schritte zum Erstellen der PSTN-Verwendung „International“, der VoIP-Route „International“, der VoIP-Routingrichtlinie „Keine Einschränkungen“ und zum Zuweisen dieser Richtlinie zum Benutzer „John Woods“ sind wie folgt:


1. Erstellen Sie zuerst die PSTN-Verwendung „International“. Geben Sie in einer PowerShell-Remotesitzung in Skype for Business Online Folgendes ein:

   ```
   Set-CsOnlinePstnUsage -Identity Global -Usage @{Add="International"}
   ```

2. Erstellen Sie als nächstes die neue VoIP-Route „International“.

   ```
   New-CsOnlineVoiceRoute -Identity "International" -NumberPattern ".*" -OnlinePstnGatewayList sbc2.contoso.biz, sbc5.contoso.biz -OnlinePstnUsages "International"
   ```
   Dadurch wird Folgendes zurückgegeben:

   <pre>
   Identity                  : International 
   Priority                      : 5
   Description                   : 
   NumberPattern                 : .*
   OnlinePstnUsages          : {International} 
   OnlinePstnGatewayList           : {sbc2.contoso.biz, sbc5.contoso.biz}
   Name                            : International
   </pre>
3. Als Nächstes erstellen Sie eine VoIP-Routingrichtlinie „Keine Einschränkungen“. Die PSTN-Verwendungen „Redmond 1“ und „Redmond“ werden in dieser VoIP-Routingrichtlinie wiederverwendet, um eine spezielle Behandlung für Anrufe an die Nummer "+ 1 425 XXX XX XX" und "+ 1 206 XXX XX XX" als lokale Anrufe beizubehalten.

```
New-CsOnlineVoiceRoutingPolicy "No Restrictions" -OnlinePstnUsages "US and Canada", "International"
```

    Take note of the order of PSTN Usages:

    a. If a call made to number "+1 425 XXX XX XX" with the usages configured as in the following example, the call follows the route set in "US and Canada" usage and the special routing logic is applied. That is, the call is routed using sbc1.contoso.biz and sbc2.contoso.biz first, and then sbc3.contoso.biz and sbc4.contoso.biz as the backup routes. 

    b.  If "International" PSTN usage is before "US and Canada," calls to +1 425 XXX XX XX are routed to sbc2.contoso.biz and sbc5.contoso.biz as part of the routing logic. Enter the command:

    ```New-CsOnlineVoiceRoutingPolicy "No Restrictions" -OnlinePstnUsages "US and Canada", "International"```

   Dadurch wird Folgendes zurückgegeben:

  <pre>
   Identity     : International 
   OnlinePstnUsages     : {US and Canada, International}     
   Description      :  
   RouteType        : BYOT
  </pre>

4. Weisen Sie dem Benutzer „John Woods“ mithilfe des folgenden Befehls die VoIP-Routingrichtlinie zu.

   ```
   Grant-CsOnlineVoiceRoutingPolicy -Identity "John Woods" -PolicyName "No Restrictions”
   ```

   Überprüfen Sie dann die Zuweisung mithilfe des folgenden Befehls: 

   ```
   Get-CsOnlineUser "John Woods" | Select OnlineVoiceRoutingPolicy
   ```
   Dadurch wird Folgendes zurückgegeben:

<pre>
    OnlineVoiceRoutingPolicy
    ------------------------
    No Restrictions
</pre>

Das Ergebnis ist, dass die VoIP-Richtlinie, die auf die Anrufe von John Woods angewendet wird, keine Einschränkungen aufweist und der Logik der Anrufweiterleitung folgt, die für USA, Kanada und internationale Gespräche verfügbar ist.

## <a name="assign-teams-only-mode-to-users-to-ensure-calls-land-in-microsoft-teams"></a>Ordnen Sie den Benutzern den Modus „Nur Teams“ zu, um sicherzustellen, dass Anrufe in Microsoft Teams eingehen.

Das direkte Routing erfordert, dass sich die Benutzer im Modus „Nur Teams“ befinden, um sicherzustellen, dass eingehende Anrufe im Team-Client eingehen. Um Benutzer im Modus „Nur Teams“ zu setzen, weisen Sie ihnen die Instanz "UpgradeToTeams" von TeamsUpgradePolicy zu. Falls Ihre Organisation Skype for Business Server oder Skype for Business Online verwendet, lesen Sie den folgenden Artikel für Informationen zur Interoperabilität zwischen Skype und Teams: [Anleitung zur Migration und Interoperabilität für Unternehmen, die Teams zusammen mit Skype for Business verwenden](https://docs.microsoft.com/microsoftteams/migration-interop-guidance-for-teams-with-skype). 


## <a name="see-also"></a>Siehe auch

[Planen von direktem Routing](direct-routing-plan.md)
