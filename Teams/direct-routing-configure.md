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
- M365-voice
appliesto:
- Microsoft Teams
description: Hier erfahren Sie, wie Sie das direkte Routing des Microsoft Phone-Systems konfigurieren.
ms.openlocfilehash: 3524d3d41db02dbc123700ae259386bb97257bbd
ms.sourcegitcommit: c15ab82834005b9a19247e06488f1f21161fc426
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/13/2019
ms.locfileid: "40020069"
---
# <a name="configure-direct-routing"></a>Konfigurieren von direktem Routing

> [!Tip]
> Schauen Sie sich die folgende Sitzung an, um mehr über die Vorteile des direkten Routings, die Vorgehensweise für die Planung und die Bereitstellung zu erfahren: [Direktes Routing in Microsoft Teams](https://aka.ms/teams-direct-routing)

Wenn Sie dies noch nicht getan haben, lesen Sie [Planen des direkten Routings](direct-routing-plan.md) für Voraussetzungen und zum Überprüfen weiterer Schritte, die Sie ausführen müssen, bevor Sie Ihr Microsoft Phone-System Netzwerk konfigurieren. 

In diesem Artikel wird beschrieben, wie Sie das direkte Routing des Microsoft Phone-Systems konfigurieren. Sie erfahren, wie Sie einen unterstützten Session Border Controller (SBC) mit Direct Routing koppeln und wie Microsoft Teams-Benutzer so konfiguriert werden, dass Sie die direkte Weiterleitung zum Herstellen einer Verbindung mit dem öffentlichen Telefonnetz (PSTN) verwenden. Um die in diesem Artikel erläuterten Schritte ausführen zu können, benötigen Administratoren einige Vertrautheit mit PowerShell-Cmdlets. Weitere Informationen zur Verwendung von PowerShell finden Sie unter [Einrichten Ihres Computers für Windows PowerShell](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell). 

Wir empfehlen, dass Sie sicherstellen, dass Ihr SBC bereits gemäß den Empfehlungen Ihres SBC-Herstellers konfiguriert wurde: 

- [AudioCodes-Bereitstellungsdokumentation](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/direct-routing-for-microsoft-teams)
- [Oracle-Bereitstellungsdokumentation](https://www.oracle.com/industries/communications/enterprise-session-border-controller/microsoft.html)
- [Bereitstellungsdokumentation zur Multifunktionsleisten-Kommunikation](https://ribboncommunications.com/solutions/enterprise-solutions/microsoft-solutions/direct-routing-microsoft-teams-calling)
- [TE-Systems (anynode)-Bereitstellungsdokumentation](https://www.anynode.de/anynode-and-microsoft-teams/)

Sie können Ihr Microsoft Phone-System konfigurieren und Benutzern die Verwendung des direkten Routings ermöglichen und anschließend Microsoft Teams als bevorzugten Anruf Client einrichten, indem Sie die folgenden Verfahren ausführen: 

- [Koppeln des SBC mit einem Microsoft Phone-System und Überprüfen der Kopplung](#pair-the-sbc-to-the-direct-routing-service-of-phone-system)
- [Aktivieren von Benutzern für Direct Routing Service](#enable-users-for-direct-routing-service)
- Sicherstellen, dass Microsoft Teams der bevorzugte Anruf Client für die Benutzer ist

## <a name="pair-the-sbc-to-the-direct-routing-service-of-phone-system"></a>Koppeln des SBC mit dem Direct Routing-Dienst des Telefonsystems 

Im folgenden werden die drei allgemeinen Schritte beschrieben, mit denen Sie den SBC mit der direkten Routing Schnittstelle verbinden oder koppeln können: 

- Herstellen einer Verbindung mit dem **Skype for Business Online** Admin Center mithilfe von PowerShell 
- Koppeln des SBC 
- Überprüfen der Kopplung 

### <a name="connect-to-skype-for-business-online-by-using-powershell"></a>Herstellen einer Verbindung mit Skype for Business Online mithilfe von PowerShell 

Sie können eine mit dem Mandanten verbundene PowerShell-Sitzung verwenden, um den SBC mit der direkten Routing Schnittstelle zu koppeln. Wenn Sie eine PowerShell-Sitzung öffnen möchten, führen Sie die Schritte unter [Einrichten Ihres Computers für Windows PowerShell](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)aus. 
 
Nachdem Sie eine Remote-PowerShell-Sitzung erstellt haben, überprüfen Sie, ob Sie die Befehle zum Verwalten des SBC sehen können. Um die Befehle zu überprüfen, geben Sie in der PowerShell-Sitzung Folgendes ein, oder kopieren/fügen Sie Sie ein, und drücken Sie die EINGABETASTE: 

```
Get-Command *onlinePSTNGateway*
```

Ihr Befehl gibt die vier hier gezeigten Funktionen zurück, mit denen Sie den SBC verwalten können. 

<pre>
CommandType    Name                       Version    Source 
-----------    ----                       -------    ------ 
Function       Get-CsOnlinePSTNGateway    1.0        tmp_v5fiu1no.wxt 
Function       New-CsOnlinePSTNGateway    1.0        tmp_v5fiu1no.wxt 
Function       Remove-CsOnlinePSTNGateway 1.0        tmp_v5fiu1no.wxt 
Function       Set-CsOnlinePSTNGateway    1.0        tmp_v5fiu1no.wxt
</pre>   


### <a name="pair-the-sbc-to-the-tenant"></a>Koppeln des SBC mit dem Mandanten 

Wenn Sie den SBC mit dem Mandanten koppeln möchten, geben Sie in der PowerShell-Sitzung Folgendes ein, und drücken Sie die EINGABETASTE: 

```
New-CsOnlinePSTNGateway -Fqdn <SBC FQDN> -SipSignallingPort <SBC SIP Port> -MaxConcurrentSessions <Max Concurrent Sessions the SBC can handle> -Enabled $true 
```
  > [!NOTE]
  > 1. Es wird dringend empfohlen, im SBC eine maximale Anruf Grenze zu verwenden, die Informationen enthält, die in der SBC-Dokumentation zu finden sind. Der Grenzwert löst eine Benachrichtigung aus, wenn sich der SBC auf der Kapazitäts Ebene befindet.
  > 2. Sie können den SBC nur koppeln, wenn der Domänenteil des FQDN mit einer der in Ihrem Mandanten registrierten Domänen übereinstimmt \*, mit Ausnahme von onmicrosoft.com. Die \*Verwendung von onmicrosoft.com-Domänennamen wird für den Namen des SBC-FQDN nicht unterstützt. Wenn Sie beispielsweise über zwei Domänennamen verfügen:<br/><br/>
  > **contoso**. com<br/>**contoso**. onmicrosoft.com<br/><br/>
  > Für den SBC-Namen können Sie den Namen SBC.contoso.com verwenden. Wenn Sie versuchen, den SBC mit einem Namen SBC. contoso. ABC zu koppeln, lässt das System Sie nicht zu, da die Domäne nicht im Besitz dieses Mandanten ist.<br/>
  > Neben der in Ihrem Mandanten registrierten Domäne ist es wichtig, dass ein Benutzer mit dieser Domäne und eine zugewiesene E3-oder E5-Lizenz vorhanden ist. Wenn dies nicht der Fall ist, wird die folgende Fehlermeldung angezeigt:<br/>
  `Can not use the “sbc.contoso.com” domain as it was not configured for this tenant`.

```
New-CsOnlinePSTNGateway -Identity sbc.contoso.com -Enabled $true -SipSignallingPort 5067 -MaxConcurrentSessions 100 
```
Gibt
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
Es gibt weitere Optionen, die während des kopplungsvorgangs festgesetzt werden können. Im vorherigen Beispiel werden jedoch nur die erforderlichen Mindestparameter angezeigt. 
 
In der folgenden Tabelle sind die zusätzlichen Parameter aufgeführt, die Sie zum Festlegen von ```New-CsOnlinePstnGateway```Parametern für verwenden können.

|Erforderlich?|Name|Beschreibung|Standard|Mögliche Werte|Typ und Einschränkungen|
|:-----|:-----|:-----|:-----|:-----|:-----|
|Ja|FQDN|Der FQDN-Name des SBC |Keine|NoneFQDN-Name, 63-Zeichen begrenzen|Zeichenfolge, Liste der zulässigen und nicht zulässigen Zeichen für [Benennungskonventionen in Active Directory für Computer, Domänen, Websites und OUs](https://support.microsoft.com/help/909264)|
|Nein|MediaBypass |Der vom SBC angegebene Parameter unterstützt die medienumgehung, und der Administrator möchte ihn verwenden.|Keine|Wahr<br/>Falsch|Boolean|
|Ja|SipSignallingPort |Der für die Kommunikation mit Direct Routing Services verwendete Überwachungs Port mithilfe des TLS-Protokolls (Transport Layer Security).|Keine|Beliebiger Port|0 bis 65535 |
|Nein|FailoverTimeSeconds |Bei Festlegung auf 10 (Standardwert) werden ausgehende Anrufe, die nicht innerhalb von 10 Sekunden vom Gateway beantwortet werden, an den nächsten verfügbaren trunk weitergeleitet; Wenn keine zusätzlichen Trunks vorhanden sind, wird der Anruf automatisch gelöscht. In einer Organisation mit langsamen Netzwerken und Gateway-Antworten kann dies potenziell dazu führen, dass Anrufe unnötig fallen. Der Standardwert ist 10.|10|Nummer|Int|
|Nein|ForwardCallHistory |Gibt an, ob Informationen zum Anrufverlauf durch den Trunk weitergeleitet werden. Wenn diese Option aktiviert ist, sendet der Office 365-PSTN-Proxy zwei Überschriften: Verlaufsinformationen und weitergeleitet. Der Standardwert ist **false** ($false). |Falsch|Wahr<br/>Falsch|Boolean|
|Nein|ForwardPAI|Gibt an, ob der PAI-Header (P-Asserted-Identity) zusammen mit dem Anruf weitergeleitet wird. Der PAI-Header bietet eine Möglichkeit, die Identität des Anrufers zu überprüfen. Wenn aktiviert, wird auch der Datenschutz: ID-Header gesendet. Der Standardwert ist **false** ($false).|Falsch|Wahr<br/>Falsch|Boolean|
|Nein|SendSIPOptions |Definiert, ob die SIP-Optionen von einem SBC gesendet werden sollen. Wenn diese Option deaktiviert ist, wird der SBC vom Überwachungs-und Warnungssystem ausgeschlossen. Wir empfehlen dringend, SIP-Optionen zu aktivieren. Der Standardwert ist **wahr**. |Wahr|Wahr<br/>Falsch|Boolean|
|Nein|MaxConcurrentSessions |Wird vom Warnungssystem verwendet. Wenn ein beliebiger Wert gesetzt ist, generiert das Warnungssystem eine Benachrichtigung an den mandantenadministrator, wenn die Anzahl der gleichzeitigen Sitzungen 90% oder höher als dieser Wert ist. Wenn Parameter nicht gesetzt ist, werden die Benachrichtigungen nicht generiert. Das Überwachungssystem meldet jedoch die Anzahl der gleichzeitigen Sitzungen alle 24 Stunden. |NULL|NULL<br/>1 bis 100.000 ||
|Nein|MediaRelayRoutingLocationOverride |Ermöglicht das manuelle auswählen von Pfad für Medien. Beim direkten Routing wird ein Datacenter für Medienpfad basierend auf der öffentlichen IP-Adresse des SBC zugewiesen. Wir wählen immer am nächsten zum SBC-Rechenzentrum aus. In einigen Fällen kann eine öffentliche IP-Adresse beispielsweise aus dem US-Bereich einem SBC in Europa zugewiesen werden. In diesem Fall wird kein optimaler Medienpfad verwendet. Mit diesem Parameter kann der bevorzugte Bereich für den Mediendatenverkehr manuell eingestellt werden. Wir empfehlen, diesen Parameter nur dann festzulegen, wenn die Anrufprotokolle eindeutig darauf hinweisen, dass die automatische Zuweisung des Rechenzentrums für Medienpfad dem SBC-Rechenzentrum nicht am nächsten kommt. |Keine|Landesvorwahl im ISO-Format||
|Nein|Aktiviert|Wird verwendet, um diesen SBC für ausgehende Anrufe zu aktivieren. Kann verwendet werden, um den SBC vorübergehend zu entfernen, während er aktualisiert wird oder während der Wartung. |Falsch|Wahr<br/>Falsch|Boolean|
 
### <a name="verify-the-sbc-pairing"></a>Überprüfen der SBC-Kopplung 

Überprüfen Sie die Verbindung: 
- Überprüfen Sie, ob sich der SBC in der Liste der gekoppelten SBCS befindet. 
- Überprüfen Sie die SIP-Optionen. 
 
#### <a name="validate-if-the-sbc-is-on-the-list-of-paired-sbcs"></a>Überprüfen, ob sich der SBC in der Liste der gekoppelten SBCS befindet 

Nachdem Sie den SBC gekoppelt haben, überprüfen Sie, ob der SBC in der Liste der gekoppelten SBCS vorhanden ist, indem Sie den folgenden Befehl in einer Remote-PowerShell-Sitzung ausführen:`Get-CSOnlinePSTNGateway`

Das gekoppelte Gateway sollte in der Liste angezeigt werden, wie im folgenden Beispiel gezeigt, und überprüfen, ob der Parameter **Enabled** den Wert **true**anzeigt. Eingeben

```
Get-CsOnlinePSTNGateway -Identity sbc.contoso.com  
```
Was zurückgegeben wird:
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

#### <a name="validate-sip-options-flow"></a>Überprüfen des SIP-Options Flusses 

Um die Kopplung mithilfe der ausgehenden SIP-Optionen zu überprüfen, verwenden Sie die SBC-Verwaltungsschnittstelle, und vergewissern Sie sich, dass der SBC 200-OK-Antworten auf die Nachrichten der ausgehenden Optionen erhält.

Wenn für das direkte Routing eingehende Optionen angezeigt werden, wird das Senden von ausgehenden SIP-Optionen Nachrichten an den SBC-FQDN gesendet, der im Feld Kontakt Kopf in der Nachricht eingehende Optionen konfiguriert ist. 

Wenn Sie die Kopplung mithilfe der eingehenden SIP-Optionen überprüfen möchten, verwenden Sie die SBC-Verwaltungsschnittstelle, und sehen Sie, dass der SBC eine Antwort auf die Options Nachrichten sendet, die vom direkten Routing eingehen, und dass der von ihm gesendete Antwortcode 200 OK ist.

## <a name="enable-users-for-direct-routing-service"></a>Aktivieren von Benutzern für Direct Routing Service 

Wenn Sie bereit sind, Benutzer für den direkt Routing Dienst zu aktivieren, führen Sie die folgenden Schritte aus: 

1. Erstellen Sie einen Benutzer in Office 365, und weisen Sie eine Telefonsystem Lizenz zu. 
2. Stellen Sie sicher, dass der Benutzer in Skype for Business Online verwaltet wird. 
3. Konfigurieren Sie die Telefonnummer, und aktivieren Sie Enterprise-VoIP und Voicemail. 
4. Konfigurieren des VoIP-Routings Die Route wird automatisch überprüft.

### <a name="create-a-user-in-office-365-and-assign-the-license"></a>Erstellen eines Benutzers in Office 365 und Zuweisen der Lizenz 

Es gibt zwei Möglichkeiten zum Erstellen eines neuen Benutzers in Office 365. Es wird jedoch empfohlen, dass Ihre Organisation eine Option auswählen und verwenden, um Routingprobleme zu vermeiden: 

- Erstellen Sie den Benutzer im lokalen Active Directory, und synchronisieren Sie ihn mit der Cloud. Weitere Informationen finden Sie unter [integrieren Ihrer lokalen Verzeichnisse in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect).
- Erstellen Sie den Benutzer direkt im Office 365-Administrator Portal. Weitere Informationen finden Sie unter [Hinzufügen von Benutzern einzeln oder in Massen zu Office 365 – Hilfe für Administratoren](https://support.office.com/article/Add-users-individually-or-in-bulk-to-Office-365-Admin-Help-1970f7d6-03b5-442f-b385-5880b9c256ec). 

Wenn Ihre Skype for Business Online-Bereitstellung zusammen mit Skype for Business 2015 oder lync 2010/2013 lokal vorhanden ist, besteht die einzige unterstützte Option darin, den Benutzer in lokales Active Directory zu erstellen und den Benutzer mit der Cloud zu synchronisieren (Option 1). 

Erforderliche Lizenzen: 

- Office 365 Enterprise E3 (einschließlich SFB Aktionsplan2, Exchange Aktionsplan2 und Teams) + Telefon System
- Office 365 Enterprise E5 (einschließlich SFB Aktionsplan2, Exchange Aktionsplan2, Teams und Telefon System) 

Optionale Lizenzen: 

- Anrufplan 
- Audiokonferenzen 

### <a name="ensure-that-the-user-is-homed-in-skype-for-business-online"></a>Sicherstellen, dass der Benutzer in Skype for Business Online verwaltet wird 

Für die direkte Weiterleitung muss der Benutzer in Skype for Business Online verwaltet werden. Sie können dies überprüfen, indem Sie den RegistrarPool-Parameter betrachten. Sie muss einen Wert in der Infra.lync.com-Domäne aufweisen.

1. Herstellen einer Verbindung mit der Remote-PowerShell
2. Geben Sie den folgenden Befehl ein: 

```
Get-CsOnlineUser -Identity "<User name>" | fl RegistrarPool
``` 

### <a name="configure-the-phone-number-and-enable-enterprise-voice-and-voicemail"></a>Konfigurieren Sie die Telefonnummer, und aktivieren Sie Enterprise-VoIP und Voicemail. 

Nachdem Sie den Benutzer erstellt und eine Lizenz zugewiesen haben, besteht der nächste Schritt darin, Ihre Telefonnummer und Voicemail zu konfigurieren. Dies kann in einem Schritt erfolgen. 

So fügen Sie die Telefonnummer hinzu und aktivieren für Voicemail:
 
1. Stellen Sie eine Verbindung mit einer PowerShell-Remotesitzung her. 
2. Geben Sie den folgenden Befehl ein: 
 
```
Set-CsUser -Identity "<User name>" -EnterpriseVoiceEnabled $true -HostedVoiceMail $true -OnPremLineURI tel:<E.164 phone number>
```

Wenn Sie beispielsweise eine Telefonnummer für den Benutzer "Spencer Low" hinzufügen möchten, geben Sie Folgendes ein: 

```
Set-CsUser -Identity "Spencer Low" -OnPremLineURI tel:+14255388797 -EnterpriseVoiceEnabled $true -HostedVoiceMail $true
```

Die verwendete Telefonnummer muss als vollständige E. 164-Telefonnummer mit Landesvorwahl konfiguriert werden. 

  > [!NOTE]
  > Wenn die Telefonnummer des Benutzers lokal verwaltet wird, verwenden Sie die lokale Skype for Business-Verwaltungsshell oder die Systemsteuerung, um die Telefonnummer des Benutzers zu konfigurieren. 

### <a name="configure-voice-routing"></a>Konfigurieren des VoIP-Routings 

Microsoft Phone System verfügt über einen Routingmechanismus, mit dem ein Anruf an einen bestimmten SBC basierend auf folgenden Informationen gesendet werden kann: 

- Als Zahlenmuster bezeichnet 
- Namens Zahlenmuster + bestimmter Nutzer, der den Anruf tätigt
 
SBCS kann als aktiv und als Backup festgelegt werden. Das bedeutet, wenn der SBC, der für dieses Zahlenmuster oder Zahlenmuster + bestimmten Benutzer als aktiv konfiguriert ist, nicht verfügbar ist, werden die Anrufe an eine Sicherungs-SBC weitergeleitet.
 
Das Anrufrouting besteht aus den folgenden Elementen: 
- VoIP-Routing Richtlinie – Container für PSTN-Nutzungen; kann einem Benutzer oder mehreren Benutzern zugewiesen werden 
- PSTN-Nutzungen – Container für sprach Routen und PSTN-Nutzungen; kann in verschiedenen VoIP-Routing Richtlinien freigegeben werden 
- VoIP-Routen – Nummernmuster und Satz von Online-PSTN-Gateways für Anrufe, bei denen die Rufnummer mit dem Muster übereinstimmt 
- Online-PSTN-Gateway – Zeiger auf einen SBC, speichert auch die Konfiguration, die angewendet wird, wenn der Aufruf über den SBC erfolgt, wie z. b. Weiterleiten von P-Asserted-Identity (Pai) oder bevorzugten Codecs; kann zu VoIP-Routen hinzugefügt werden 

#### <a name="creating-a-voice-routing-policy-with-one-pstn-usage"></a>Erstellen einer VoIP-Routing Richtlinie mit einer PSTN-Nutzung 

Das folgende Diagramm zeigt zwei Beispiele für VoIP-Routing Richtlinien im Anruffluss.

**Anruffluss 1 (auf der linken Seite):** Wenn ein Benutzer einen Anruf an + 1 425 XXX XX XX oder + 1 206 XXX XX XX tätigt, wird der Anruf an SBC sbc1.contoso.biz oder sbc2.contoso.biz weitergeleitet. Wenn weder sbc1.contoso.biz noch sbc2.contoso.biz verfügbar sind, wird der Anruf abgebrochen. 

**Anruffluss 2 (rechts):** Wenn ein Benutzer einen Anruf an + 1 425 XXX XX XX oder + 1 206 XXX XX XX tätigt, wird der Anruf zuerst an SBC sbc1.contoso.biz oder sbc2.contoso.biz weitergeleitet. Wenn keine SBC verfügbar ist, wird die Route mit der niedrigeren Priorität ausprobiert (sbc3.contoso.biz und sbc4.contoso.biz). Wenn keine der SBCS verfügbar ist, wird der Anruf abgebrochen. 

![Zeigt Beispiele für VoIP-Routing Richtlinien](media/ConfigDirectRouting-VoiceRoutingPolicyExamples.png)

In beiden Beispielen wird die SBCS in den Routen in zufälliger Reihenfolge erprobt, während der VoIP-Route Prioritäten zugewiesen werden.

  > [!NOTE]
  > Wenn der Benutzer auch keine Microsoft-Anrufplan-Lizenz hat, werden Anrufe an eine beliebige Zahl mit Ausnahme der Zahlen, die mit den Mustern + 1 425 XXX XX XX oder + 1 206 XXX XX XX in der Beispielkonfiguration übereinstimmen, gelöscht. Wenn der Benutzer über eine Callingcard-Lizenz verfügt, wird der Anruf automatisch entsprechend den Richtlinien des Microsoft-Anruf Plans weitergeleitet. 

Der Microsoft-Anrufplan gilt automatisch als letzte Route für alle Benutzer mit der Lizenz für den Microsoft-Anrufplan und erfordert keine zusätzliche Konfiguration des Anruf Routings.

In dem Beispiel, das in der folgenden Abbildung gezeigt wird, wird eine VoIP-Route hinzugefügt, um Anrufe an alle anderen US-amerikanischen und kanadischen Nummern zu senden (Anrufe, die mit dem sogenannten Number-Muster + 1 XXX XXX XX XX gehen).

![Zeigt die VoIP-Routing Richtlinie mit einer dritten Route an](media/ConfigDirectRouting-VoiceRoutingPolicywith3rdroute.png)

Bei allen anderen anrufen wird automatisch Route verwendet, wenn ein Benutzer über beide Lizenzen verfügt (Microsoft Phone System und Microsoft Calling Plan). Wenn nichts den Zahlen Mustern in den vom Administrator erstellten Online-VoIP-Routen entspricht, Route über den Microsoft-Anrufplan.

Wenn der Benutzer nur über ein Microsoft Phone-System verfügt, wird der Anruf abgebrochen, da keine übereinstimmenden Regeln verfügbar sind.

  > [!NOTE]
  > Der Prioritätswert für Route "Other + 1" ist in diesem Fall nicht wichtig, da es nur eine Route gibt, die dem Muster + 1 XXX XXX XX XX entspricht. Wenn ein Benutzer einen Anruf an + 1 324 567 89 89 tätigt und sowohl sbc5.contoso.biz als auch sbc6.contoso.biz nicht zur Verfügung stehen, wird der Anruf abgebrochen.

In der folgenden Tabelle wird die Konfiguration mit drei VoIP-Routen zusammengefasst. In diesem Beispiel sind alle drei Routen Teil derselben PSTN-Nutzung "USA und Kanada".

|**PSTN-Verwendung**|**VoIP-Route**|**Nummernmuster**|**Priorität**|**Sbchttps**|**Beschreibung**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|Nur USA|"Redmond 1"|^\\+ 1 (425\|206) (\d{7}) $|1|sbc1.contoso.biz<br/>sbc2.contoso.biz|Aktive Route für angerufene Nummern + 1 425 XXX XX XX oder + 1 206 XXX XX XX|
|Nur USA|"Redmond 2"|^\\+ 1 (425\|206) (\d{7}) $|2|sbc3.contoso.biz<br/>sbc4.contoso.biz|Sicherungs Route für genannte Nummern + 1 425 XXX XX XX oder + 1 206 XXX XX XX|
|Nur USA|"Andere + 1"|^\\+ 1 (\d{10}) $|3|sbc5.contoso.biz<br/>sbc6.contoso.biz|Route für angerufene Nummern + 1 XXX XXX XX XX (außer + 1 425 XXX XX XX oder + 1 206 XXX XX XX)|
|||||||

Alle Routen sind mit der PSTN-Nutzung "USA und Kanada" verknüpft, und die PSTN-Nutzung ist mit der VoIP-Routing Richtlinie "nur US" verbunden. In diesem Beispiel wird die VoIP-Routing Richtlinie Benutzer Spencer Low zugewiesen.

#### <a name="examples-of-call-routes"></a>Beispiele für Anrufrouten

Im folgenden Beispiel wird gezeigt, wie Sie Routen, PSTN-Nutzungen und Routing Richtlinien konfigurieren, und wir weisen die Richtlinie dem Benutzer zu.

**Schritt 1:** Erstellen Sie die PSTN-Nutzung "USA und Kanada".

Geben Sie in einer Skype for Business-Remote-PowerShell-Sitzung Folgendes ein:

```
Set-CsOnlinePstnUsage -Identity Global -Usage @{Add="US and Canada"}
```

Überprüfen Sie, ob die Verwendung erstellt wurde, indem Sie Folgendes eingeben: 
```
Get-CSOnlinePSTNUsage
``` 
Damit wird eine Liste der Namen zurückgegeben, die möglicherweise abgeschnitten werden:
```
Identity    : Global
Usage       : {testusage, US and Canada, International, karlUsage. . .}
```
Im folgenden Beispiel wird das Ergebnis der Ausführung des PowerShell-Befehls `(Get-CSOnlinePSTNUsage).usage` zum Anzeigen von vollständigen Namen (nicht abgeschnitten) angezeigt.

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

**Schritt 2:** Erstellen Sie in einer PowerShell-Sitzung in Skype for Business Online drei Routen: Redmond 1, Redmond 2 und other + 1, wie in der vorhergehenden Tabelle beschrieben. 

Um die Route "Redmond 1" zu erstellen, geben Sie Folgendes ein:

```
New-CsOnlineVoiceRoute -Identity "Redmond 1" -NumberPattern "^\+1(425|206)
(\d{7})$" -OnlinePstnGatewayList sbc1.contoso.biz, sbc2.contoso.biz -Priority 1 -OnlinePstnUsages "US and Canada"
```

Was zurückgegeben wird:
<pre>
Identity                : Redmond 1
Priority                : 1
Description             :
NumberPattern           : ^\+1(425|206) (\d{7})$
OnlinePstnUsages        : {US and Canada}
OnlinePstnGatewayList   : {sbc1.contoso.biz, sbc2.contoso.biz}
Name                    : Redmond 1
</pre>
Um die Route Redmond 2 zu erstellen, geben Sie Folgendes ein:

```
New-CsOnlineVoiceRoute -Identity "Redmond 2" -NumberPattern "^\+1(425|206)
(\d{7})$" -OnlinePstnGatewayList sbc3.contoso.biz, sbc4.contoso.biz -Priority 2 -OnlinePstnUsages "US and Canada"
```

Zum Erstellen der anderen + 1-Route geben Sie Folgendes ein:

```
New-CsOnlineVoiceRoute -Identity "Other +1" -NumberPattern "^\+1(\d{10})$"
-OnlinePstnGatewayList sbc5.contoso.biz, sbc6.contoso.biz -OnlinePstnUsages "US and Canada"
```

  > [!CAUTION]
  > Stellen Sie sicher, dass Ihr regulärer Ausdruck im NumberPattern-Attribut ein gültiger Ausdruck ist. Sie können es über diese Website testen:[https://www.regexpal.com](https://www.regexpal.com)

In einigen Fällen müssen alle Anrufe an denselben SBC weitergeleitet werden. Verwenden Sie bitte-NumberPattern ". *"

Alle Anrufe an denselben SBC weiterleiten.

```
Set-CsOnlineVoiceRoute -id "Redmond 1" -NumberPattern ".*" -OnlinePstnGatewayList sbc1.contoso.biz
```

Überprüfen Sie, ob Sie die Route ordnungsgemäß `Get-CSOnlineVoiceRoute` konfiguriert haben, indem Sie den PowerShell-Befehl unter Verwendung der folgenden Optionen ausführen:

```
Get-CsOnlineVoiceRoute | Where-Object {($_.priority -eq 1) -or ($_.priority -eq 2) or ($_.priority -eq 4) -Identity "Redmond 1" -NumberPattern "^\+1(425|206) (\d{7})$" -OnlinePstnGatewayList sbc1.contoso.biz, sbc2.contoso.biz -Priority 1 -OnlinePstnUsages "US and Canada"
```
Was zurückgegeben werden sollte:
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

Im Beispiel wurde der Route "Other + 1" automatisch Priorität 4 zugewiesen. 

**Schritt 3:** Erstellen Sie eine VoIP-Routing Richtlinie "nur US", und fügen Sie der Richtlinie die PSTN-Nutzung "USA und Kanada" hinzu.

Geben Sie in einer PowerShell-Sitzung in Skype for Business Online Folgendes ein:

```
New-CsOnlineVoiceRoutingPolicy "US Only" -OnlinePstnUsages "US and Canada"
```

Das Ergebnis wird im folgenden Beispiel gezeigt:

<pre>
Identity            : Tag:US only
OnlinePstnUsages    : {US and Canada}
Description         :
RouteType           : BYOT
</pre>

**Schritt 4:** Erteilen Sie dem Benutzer Spencer Low eine VoIP-Routing Richtlinie mithilfe von PowerShell.

Geben Sie in einer PowerShell-Sitzung in Skype for Business Online Folgendes ein:

```
Grant-CsOnlineVoiceRoutingPolicy -Identity "Spencer Low" -PolicyName "US Only"
```

Überprüfen Sie die Richtlinienzuweisung, indem Sie den folgenden Befehl eingeben:

```
Get-CsOnlineUser "Spencer Low" | select OnlineVoiceRoutingPolicy
```

Was zurückgegeben wird:
<pre>
OnlineVoiceRoutingPolicy
---------------------
US Only
</pre>

#### <a name="creating-a-voice-routing-policy-with-several-pstn-usages"></a>Erstellen einer VoIP-Routing Richtlinie mit mehreren PSTN-Nutzungen

Die zuvor erstellte VoIP-Routing Richtlinie ermöglicht nur Anrufe an Telefonnummern in den USA und Kanada, es sei denn, die Lizenz für den Microsoft-Anrufplan wird dem Benutzer ebenfalls zugewiesen.

Im folgenden Beispiel können Sie die VoIP-Routing Richtlinie "keine Einschränkungen" erstellen. Die Richtlinie verwendet die im vorherigen Beispiel erstellte PSTN-Nutzung "USA und Kanada" sowie die neue PSTN-Nutzung "International" erneut. 

Damit werden alle weiteren Anrufe an SBCS sbc2.contoso.biz und sbc5.contoso.biz weitergeleitet. In den Beispielen, die angezeigt werden, weisen Sie den Benutzern nur die Richtlinie "Spencer Low" und keine Einschränkungen für den Benutzer "John Woods" zu.

Spencer Low – Anrufe, die nur für US-und kanadische Rufnummern zulässig sind. Beim Anrufen in den Redmond-Nummernbereich muss der spezifische SBC-Satz verwendet werden. Nicht-US-Nummern werden nicht weitergeleitet, es sei denn, die Lizenz für den Anrufplan wird dem Nutzer zugewiesen.

John Woods – Anrufe an beliebige Rufnummern zulässig. Beim Anrufen in den Redmond-Nummernbereich muss der spezifische SBC-Satz verwendet werden. Nicht-US-Nummern werden über sbc2.contoso.biz und sbc5.contoso.biz weitergeleitet.

![Zeigt die VoIP-Routing Richtlinie, die dem Benutzer Spencer Low zugewiesen ist.](media/ConfigDirectRouting-VoiceRoutingPolicyAssignedtoSpencerLow.png)

Bei allen anderen anrufen wird automatisch Route verwendet, wenn ein Benutzer über beide Lizenzen verfügt (Microsoft Phone System und Microsoft Calling Plan). Wenn nichts den Zahlen Mustern in den vom Administrator erstellten Online-VoIP-Routen entspricht, Route über den Microsoft-Anrufplan.

Wenn der Benutzer nur über ein Microsoft Phone-System verfügt, wird der Anruf abgebrochen, da keine übereinstimmenden Regeln verfügbar sind.

![Zeigt die dem Benutzer zugewiesenen VoIP-Routing Richtlinien an John Woods](media/ConfigDirectRouting-VoiceRoutingPolicyAssignedtoJohnWoods.png)

Die folgende Tabelle enthält eine Zusammenfassung der Routing Richtlinie "keine Einschränkungen"-Nutzungs Bezeichnungen und VoIP-Routen. 

|**PSTN-Verwendung**|**VoIP-Route**|**Nummernmuster**|**Priorität**|**Sbchttps**|**Beschreibung**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|Nur USA|"Redmond 1"|^\\+ 1 (425\|206) (\d{7}) $|1|sbc1.contoso.biz<br/>sbc2.contoso.biz|Aktive Route für die angerufenen Nummern + 1 425 XXX XX XX oder + 1 206 XXX XX XX|
|Nur USA|"Redmond 2"|^\\+ 1 (425\|206) (\d{7}) $|2|sbc3.contoso.biz<br/>sbc4.contoso.biz|Sicherungs Route für die angerufenen Nummern + 1 425 XXX XX XX oder + 1 206 XXX XX XX|
|Nur USA|"Andere + 1"|^\\+ 1 (\d{10}) $|3|sbc5.contoso.biz<br/>sbc6>. contoso.biz|Route für die angerufenen Nummern + 1 XXX XXX XX XX (außer + 1 425 XXX XX XX oder + 1 206 XXX XX XX)|
|International|International|\d +|4|sbc2.contoso.biz<br/>sbc5.contoso.biz|Route für beliebige Zahlenmuster |


  > [!NOTE]
  > - Die Reihenfolge der PSTN-Nutzungen in VoIP-Routing Richtlinien ist kritisch. Die Verwendungen werden in der angegebenen Reihenfolge angewendet, und wenn bei der ersten Verwendung eine Übereinstimmung gefunden wird, werden andere Verwendungen nie ausgewertet. Die PSTN-Nutzung "International" muss nach der PSTN-Nutzung "nur US" erfolgen. Führen Sie den `Set-CSOnlineVoiceRoutingPolicy` Befehl aus, um die Reihenfolge der PSTN-Verwendungen zu ändern. <br/>Um beispielsweise die Reihenfolge von "USA und Kanada" zuerst und "International" an zweiter Stelle in umgekehrter Reihenfolge zu ändern, führen Sie Folgendes aus:<br/> `Set-CsOnlineVoiceRoutingPolicy -id tag:"no Restrictions" -OnlinePstnUsages @{Replace="International", "US and Canada"}`
 > - Die Priorität für VoIP-Routen "Other + 1" und "International" wird automatisch zugewiesen. Sie haben keine Bedeutung, solange Sie niedrigere Prioritäten als "Redmond 1" und "Redmond 2" haben.

#### <a name="example-of-voice-routing-policy-for-user-john-woods"></a>Beispiel für eine VoIP-Routing Richtlinie für Benutzer John Woods

Die Schritte zum Erstellen der PSTN-Nutzung "International", VoIP-Route "International", "VoIP-Routing-Richtlinie" ohne Einschränkungen, und dann dem Benutzer "John Woods" zuweisen, sind wie folgt.


**Schritt 1**: Erstellen der PSTN-Nutzung "International" 

Geben Sie in einer Remote-PowerShell-Sitzung in Skype for Business Online Folgendes ein:

```
Set-CsOnlinePstnUsage -Identity Global -Usage @{Add="International"}
```

**Schritt 2**: Erstellen der neuen VoIP-Route "International"

```
New-CsOnlineVoiceRoute -Identity "International" -NumberPattern ".*" -OnlinePstnGatewayList sbc2.contoso.biz, sbc5.contoso.biz -OnlinePstnUsages "International"
```
Was zurückgegeben wird:

<pre>
Identity                  : International
Priority                  : 5
Description               :
NumberPattern             : .*
OnlinePstnUsages          : {International}
OnlinePstnGatewayList     : {sbc2.contoso.biz, sbc5.contoso.biz}
Name                      : International
</pre>

**Schritt 3**: Erstellen einer VoIP-Routing Richtlinie "keine Einschränkungen". 

Die PSTN-Nutzung "Redmond 1" und "Redmond" werden in dieser VoIP-Routing Richtlinie wieder verwendet, um eine besondere Behandlung für Anrufe an die Nummer "+ 1 425 XXX XX XX" und "+ 1 206 XXX XX XX" als Orts-oder Lokalgespräche beizubehalten.

   ```
   New-CsOnlineVoiceRoutingPolicy "No Restrictions" -OnlinePstnUsages "US and Canada", "International"
   ```

Notieren Sie sich die Reihenfolge der PSTN-Nutzungen:

a. Wenn ein Anruf an die Nummer "+ 1 425 XXX XX XX" mit den im folgenden Beispiel konfigurierten Verwendungen erfolgt, folgt der Anruf dem in der Verwendung von "USA und Kanada" festgelegten Pfad, und die spezielle Routinglogik wird angewendet. Das bedeutet, dass der Anruf zuerst mithilfe von sbc1.contoso.biz und sbc2.contoso.biz und dann sbc3.contoso.biz und sbc4.contoso.biz als Sicherungs Routen weitergeleitet wird.

b. Wenn die PSTN-Nutzung "International" vor "USA und Kanada" liegt, werden Anrufe nach + 1 425 XXX XX XX als Teil der Routinglogik an sbc2.contoso.biz und sbc5.contoso.biz weitergeleitet. Geben Sie den folgenden Befehl ein:

```
New-CsOnlineVoiceRoutingPolicy "No Restrictions" -OnlinePstnUsages "US and Canada", "International"
```

Was zurückgegeben wird

<pre>
Identity              : International 
OnlinePstnUsages : {US and Canada, International}    
Description      :  
RouteType             : BYOT
</pre>

**Schritt 4**: weisen Sie die VoIP-Routing Richtlinie mit dem folgenden Befehl dem Benutzer "John Woods" zu.

```
Grant-CsOnlineVoiceRoutingPolicy -Identity "John Woods" -PolicyName "No Restrictions”
```

Überprüfen Sie dann die Aufgabe mit dem folgenden Befehl: 

```
Get-CsOnlineUser "John Woods" | Select OnlineVoiceRoutingPolicy
```

Was zurückgegeben wird:

<pre>
OnlineVoiceRoutingPolicy
------------------------
No Restrictions
</pre>

Das Ergebnis ist, dass die VoIP-Richtlinie, die auf die Anrufe von John Woods angewendet wurde, nicht eingeschränkt ist und der Logik des Anruf Routings für USA, Kanada und Auslandsgespräche folgen wird.

## <a name="assign-teams-only-mode-to-users-to-ensure-calls-land-in-microsoft-teams"></a>Zuweisen des Modus "nur Teams" für Benutzer, um sicherzustellen, dass Anrufe in Microsoft Teams landen

Das direkte Routing setzt voraus, dass Benutzer nur im Modus "Teams" angemeldet sind, um sicherzustellen, dass eingehende Anrufe im Team-Client landen. Um Benutzer nur im Modus "Teams" zu platzieren, weisen Sie Ihnen die "UpgradeToTeams"-Instanz von TeamsUpgradePolicy zu. Wenn Ihre Organisation Skype for Business Server oder Skype for Business Online verwendet, lesen Sie den folgenden Artikel zur Interoperabilität von Informationen zwischen Skype und Teams: [Migrations-und Interoperabilitäts Anleitungen für Organisationen, die Teams zusammen mit Skype for Business nutzen](https://docs.microsoft.com/microsoftteams/migration-interop-guidance-for-teams-with-skype). 

## <a name="configuring-sending-calls-directly-to-voicemail"></a>Konfigurieren des direkten Sendens von Anrufen an Voicemail

Mit der direkten Weiterleitung können Sie den Anruf an einen Benutzer beenden und ihn direkt an die Voicemail des Benutzers senden. Wenn Sie den Anruf direkt an Voicemail senden möchten, fügen Sie Opaque = App: Voicemail an den URI-Header der Anforderung an. Beispielsweise "SIP: User@yourdomain. com; Opaque = App: Voicemail".
In diesem Fall erhält der Nutzer der Teams keine Anrufbenachrichtigung, der Anruf wird direkt mit dem Anrufbeantworter des Benutzers verbunden.

## <a name="translate-caller-and-callee-numbers-for-outbound-and-inbound-calls-to-an-alternate-format"></a>Übersetzen von Rufnummern für Anrufer und Anrufer für ausgehende und eingehende Anrufe in ein anderes Format

Manchmal möchten mandantenadministratoren die Anrufer-oder Rufnummernanzeige für ausgehende und/oder eingehende Anrufe basierend auf den von Ihnen erstellten Mustern ändern, um die Interoperabilität mit SBCS zu gewährleisten. Sie können eine Richtlinie für die Übersetzungsregeln festlegen, um die Anrufer-oder Rufnummernanzeige in ein alternatives Format zu übersetzen. Sie können die Richtlinie verwenden, um Zahlen für Folgendes zu übersetzen:

- Eingehende Anrufe: Anrufe von einem PSTN-Endpunkt (Anrufer) an einen Teams-Client (angerufener).
- Ausgehende Anrufe: Anrufe von einem Team-Client (Anrufer) an einen PSTN-Endpunkt (angerufener).

Die Richtlinie wird auf der SBC-Ebene angewendet. Sie können einem SBC mehrere Übersetzungsregeln zuweisen, die in der Reihenfolge angewendet werden, in der Sie angezeigt werden, wenn Sie Sie in PowerShell auflisten. Sie können auch die Reihenfolge der Regeln in der Richtlinie ändern.

Zum Erstellen, ändern, anzeigen und Löschen von Regeln für die Nummern Manipulation verwenden Sie die Cmdlets New-TeamsTranslationRule, Sets-TeamsTranslationRule, Get-TeamsTranslationRule und Remove-TeamsTranslationRule.

Zum zuweisen, konfigurieren und Auflisten von Regeln für die Nummern Manipulation auf SBCS verwenden Sie die Cmdlets [New-CSOnlinePSTNGateway](https://docs.microsoft.com/powershell/module/skype/new-csonlinepstngateway) und [setCSOnlinePSTNGateway](https://docs.microsoft.com/powershell/module/skype/set-csonlinepstngateway) zusammen ```InboundPSTNNumberTranslationRules```mit ```OutboundTeamsNumberTranslationRules```den ```OutboundPSTNNumberTranslationRules``` ```InboundTeamsNumberTranslationRulesList``` ```InboundPSTNNumberTranslationRulesList``` ```OutboundTeamsNumberTranslationRulesList``` ```InboundTeamsNumberTranslationRules```,,,,, ```OutboundPSTNNumberTranslationRulesList``` ,, und Parametern.

### <a name="examples"></a>Beispiele

#### <a name="example-sbc-configuration"></a>Beispiel-SBC-Konfiguration

In den Beispielszenarien führen wir das ```New-CsOnlinePSTNGateway``` Cmdlet aus, um die folgende SBC-Konfiguration zu erstellen.

```
New-CSOnlinePSTNGateway -Identity sbc1.contoso.com -SipSignallingPort 5061 –InboundTeamsNumberTranslationRulesList ‘AddPlus1’, ‘AddE164SeattleAreaCode’ -InboundPSTNNumberTranslationRulesList ‘AddPlus1’ -OnboundPSTNNumberTranslationRulesList ‘AddSeattleAreaCode’,  -OutboundTeamsNumberTranslationRulesList ‘StripPlus1’
```

Die dem SBC zugewiesenen Übersetzungsregeln sind in der folgenden Tabelle zusammengefasst.

|Name  |Muster |Übersetzung  |
|---------|---------|---------|
|AddPlus1     |^ (\d{10}) $          |+1$1          |
|AddE164SeattleAreaCode      |^ (\d{4}) $          | + 1206555 $1         |
|AddSeattleAreaCode    |^ (\d{4}) $          | 425555 $1         |
|StripPlus1    |^ + 1 (\d{10}) $          | $1         |

In diesen Beispielszenarien haben wir zwei Benutzer, Alice und Bob. Alice ist ein Team Benutzer und Ihre Nummer ist + 1 206 555 0100. Bob ist ein PSTN-Benutzer und seine Nummer ist + 1 425 555 0100.

#### <a name="example-1-inbound-call-to-a-ten-digit-number"></a>Beispiel 1: eingehender Anruf an eine zehnstellige Zahl

Bob ruft Alice mit einer nicht-E. 164-zehnstelligen Zahl an. Bob wählt 2065550100, um Alice zu erreichen.
SBC verwendet 2065550100 in den RequestURI und den Headern und 4255550100 im from-Header.

|Header  |Original |Übersetzte Kopfzeile |Parameter und Regel angewendet  |
|---------|---------|---------|---------|
|RequestURI  |Einladen von SIP:2065550100@SBC.contoso.com|Einladen von SIP:+12065550100@SBC.contoso.com|InboundTeamsNumberTranslationRulesList 'AddPlus1'|
|An    |An: \<SIP:2065550100@SBC.contoso.com>|An: \<SIP:+12065550100@SBC.contoso.com>|InboundTeamsNumberTranlationRulesList 'AddPlus1'|
|Von   |Von: \<SIP:4255550100@SBC.contoso.com>|Von: \<SIP:+14255550100@SBC.contoso.com>|InboundPSTNNumberTranslationRulesList 'AddPlus1'|

#### <a name="example-2-inbound-call-to-a-four-digit-number"></a>Beispiel 2: eingehende Anrufe an eine vierstellige Zahl

Bob ruft Alice mit einer vierstelligen Zahl an. Bob wählt 0100, um Alice zu erreichen.
SBC verwendet 0100 in den RequestURI und den Headern und 4255550100 im from-Header.

|Header  |Original |Übersetzte Kopfzeile |Parameter und Regel angewendet  |
|---------|---------|---------|---------|
|RequestURI  |Einladen von SIP:0100@SBC.contoso.com          |Einladen von SIP:+12065550100@SBC.contoso.com           |InboundTeamsNumberTranlationRulesList 'AddE164SeattleAreaCode'        |
|An    |An: \<SIP:0100@SBC.contoso.com>|An: \<SIP:+12065550100@SBC.contoso.com>|InboundTeamsNumberTranlationRulesList 'AddE164SeattleAreaCode'         |
|Von   |Von: \<SIP:4255550100@SBC.contoso.com>|Von: \<SIP:+14255550100@SBC.contoso.com>|InboundPSTNNumberTranlationRulesList 'AddPlus1'        |

#### <a name="example-3-outbound-call-using-a-ten-digit-non-e164-number"></a>Beispiel 3: ausgehender Anruf mit einer zehnstelligen nicht-E. 164-Nummer

Alice ruft Bob mit einer zehnstelligen Zahl an. Alice wählt 425 555 0100, um Bob zu erreichen.
SBC ist für die Verwendung von nicht-E. 164-Nummern für Teams und PSTN-Benutzer konfiguriert.

In diesem Szenario übersetzt ein Wählplan die Nummer vor dem Senden an die direkte Routing Schnittstelle. Wenn Alice in den Teams-Client 425 555 0100 eingibt, wird die Nummer im Länder Wählplan in + 14255550100 übersetzt. Bei den resultierenden Zahlen handelt es sich um eine kumulative Normalisierung der Wähl Plan Regeln und der Übersetzungsregeln für Teams. Die Übersetzungsregeln für Teams entfernen das "+ 1", das vom Wählplan hinzugefügt wurde.

|Header  |Original |Übersetzte Kopfzeile |Parameter und Regel angewendet  |
|---------|---------|---------|---------|
|RequestURI  |Einladen von SIP:+14255550100@SBC.contoso.com          |Einladen von SIP:4255550100@SBC.contoso.com       |OutboundPSTNNumberTranlationRulesList 'StripPlus1'         |
|An    |An: \<SIP:+14255550100@SBC.contoso.com>|An: \<SIP:4255555555@SBC.contoso.com>|OutboundPSTNNumberTranlationRulesList 'StripPlus1'       |
|Von   |Von: \<SIP:+12065550100@SBC.contoso.com>|Von: \<SIP:2065550100@SBC.contoso.com>|OutboundTeamsNumberTranlationRulesList 'StripPlus1'         |

#### <a name="example-4-outbound-call-using-a-four-digit-non-e164-number"></a>Beispiel 4: Outbound-Anruf mit einer vierstelligen nicht-E. 164-Nummer

Alice ruft Bob mit einer vierstelligen Zahl an. Alice verwendet 0100, um Bob von anrufen oder über einen Kontakt zu erreichen.
SBC ist für die Verwendung von nicht-E. 164-vierstelligen Zahlen für Teams-Benutzer und zehnstellige Zahlen für PSTN-Benutzer konfiguriert. In diesem Szenario wird der Wählplan nicht angewendet.

|Header  |Original |Übersetzte Kopfzeile |Parameter und Regel angewendet  |
|---------|---------|---------|---------|
|RequestURI  |Einladen von SIP:0100@SBC.contoso.com           |Einladen von SIP:4255550100@SBC.contoso.com       |InboundTeamsNumberTranlationRulesList 'AddSeattleAreaCode'         |
|An    |An: \<SIP:0100@SBC.contoso.com>|An: \<SIP:4255555555@SBC.contoso.com>|InboundTeamsNumberTranlationRulesList 'AddSeattleAreaCode'       |
|Von   |Von: \<SIP:+12065550100@SBC.contoso.com>|Von: \<SIP:2065550100@SBC.contoso.com>| InboundPSTNNumberTranlationRulesList 'StripPlus1' |

## <a name="see-also"></a>Siehe auch

[Planen von direktem Routing](direct-routing-plan.md)
