---
title: Verbinden Des Session Border Controllers (SBC) mit Direct Routing
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
f1.keywords:
- NOCSH
description: Erfahren Sie, wie Sie Ihr SBC mit dem direkten Routing des Telefonsystems konfigurieren und verbinden.
ms.openlocfilehash: 697f426b9c9dc3215d653520658282fab1787001
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51122249"
---
# <a name="connect-your-session-border-controller-sbc-to-direct-routing"></a>Verbinden Des Session Border Controllers (SBC) mit Direct Routing

In diesem Artikel wird beschrieben, wie Sie einen Session Border Controller (SBC) konfigurieren und mit dem direkten Routing des Telefonsystems verbinden.  Dies ist Schritt 1 der folgenden Schritte zum Konfigurieren von Direct Routing:

- **Schritt 1. Verbinden Sie Ihren SBC mit dem Telefonsystem, und überprüfen Sie die Verbindung** (Dieser Artikel)
- Schritt 2: [Aktivieren von Benutzern für das direkte Routing](direct-routing-enable-users.md)
- Schritt 3: [Konfigurieren des Anrufroutings](direct-routing-voice-routing.md)
- Schritt 4: [Übersetzen von Zahlen in ein alternatives Format](direct-routing-translate-numbers.md)

Informationen zu allen Schritten, die zum Einrichten von Direct Routing erforderlich sind, finden Sie unter [Konfigurieren von Direct Routing](direct-routing-configure.md).

Sie können das [Microsoft Teams Admin Center](#using-the-microsoft-teams-admin-center) oder [PowerShell](#using-powershell) verwenden, um einen SBC mit Direct Routing zu konfigurieren und zu verbinden.

## <a name="using-the-microsoft-teams-admin-center"></a>Verwenden des Microsoft Teams Admin Centers

1. Wechseln Sie im linken Navigationsbereich zu **Voice**  >  **Direct Routing,** und klicken Sie dann auf die Registerkarte **SBCs.**
2. Klicken Sie auf **Hinzufügen**.
3. Geben Sie einen FQDN für den SBC ein. <br><br>Stellen Sie sicher, dass der Domänennamebereich des FQDN einer Domäne entspricht, die in Ihrem Mandanten registriert ist, und beachten Sie, dass der Domänenname für den `*.onmicrosoft.com` SBC FQDN-Domänennamen nicht unterstützt wird. Wenn Sie z. B. zwei Domänennamen haben, `contoso.com` und verwenden Sie als `contoso.onmicrosoft.com` `sbc.contoso.com` SBC-Name. Wenn Sie eine Unterdomäne verwenden, stellen Sie sicher, dass diese Unterdomäne auch in Ihrem Mandanten registriert ist. Wenn Sie beispielsweise verwenden `sbc.service.contoso.com` möchten, muss `service.contoso.com` registriert werden.
4. Konfigurieren Sie die folgenden Einstellungen für den SBC basierend auf den Anforderungen Ihrer Organisation. Details zu den einzelnen Einstellungen finden Sie unter [SBC-Einstellungen.](#sbc-settings)

    ![Screenshot der Seite "SBC hinzufügen" im Microsoft Teams Admin Center](media/direct-routing-add-sbc.png)

5. Klicken Sie abschließend auf **Speichern**.

## <a name="using-powershell"></a>Verwendung von PowerShell

Um Ihre SBC mit Direct Routing zu verbinden, müssen Sie:

1. [Stellen Sie mithilfe von PowerShell eine Verbindung mit Skype for Business Online herzustellen.](#connect-to-skype-for-business-online-by-using-powershell)
2. [Verbinden Sie den SBC mit dem Mandanten.](#connect-the-sbc-to-the-tenant)
3. [Überprüfen Sie die SBC-Verbindung.](#verify-the-sbc-connection)

### <a name="connect-to-skype-for-business-online-by-using-powershell"></a>Herstellen einer Verbindung mit Skype for Business Online mithilfe von PowerShell

Sie können eine mit dem Mandanten verbundene PowerShell-Sitzung verwenden, um den SBC mit der Direct Routing-Schnittstelle zu koppeln. Führen Sie zum Öffnen einer PowerShell-Sitzung die unter Einrichten ihres Computers für [Windows PowerShell.](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)
 
Nachdem Sie eine Remote-PowerShell-Sitzung einrichten, vergewissern Sie sich, dass die Befehle zum Verwalten des SBC angezeigt werden. Um die Befehle zu überprüfen, geben Sie den folgenden Befehl in die PowerShell-Sitzung ein, oder kopieren Sie ihn, fügen Sie ihn ein, fügen Sie ihn ein, und drücken Sie dann die EINGABETASTE: 

```PowerShell
Get-Command *onlinePSTNGateway*
```

Der Befehl gibt die vier hier gezeigten Funktionen zurück, mit deren nen Sie den SBC verwalten können.

<pre>
CommandType    Name                       Version    Source 
-----------    ----                       -------    ------ 
Function       Get-CsOnlinePSTNGateway    1.0        tmp_v5fiu1no.wxt 
Function       New-CsOnlinePSTNGateway    1.0        tmp_v5fiu1no.wxt 
Function       Remove-CsOnlinePSTNGateway 1.0        tmp_v5fiu1no.wxt 
Function       Set-CsOnlinePSTNGateway    1.0        tmp_v5fiu1no.wxt
</pre>

### <a name="connect-the-sbc-to-the-tenant"></a>Verbinden des SBC mit dem Mandanten

Verwenden Sie [das Cmdlet New-CsOnlinePSTNGateway,](/powershell/module/skype/new-csonlinepstngateway) um den SBC mit dem Mandanten zu verbinden. Geben Sie in einer PowerShell-Sitzung Folgendes ein, und drücken Sie dann die EINGABETASTE:

```PowerShell
New-CsOnlinePSTNGateway -Fqdn <SBC FQDN> -SipSignalingPort <SBC SIP Port> -MaxConcurrentSessions <Max Concurrent Sessions the SBC can handle> -Enabled $true
```

  > [!NOTE]
  > 1. Es wird empfohlen, eine maximale Anrufgrenze im SBC mithilfe von Informationen zu setzen, die in der SBC-Dokumentation zu finden sind. Der Grenzwert löst eine Benachrichtigung aus, wenn sich der SBC auf der Kapazitätsebene befindet.
  > 2. Sie können den SBC nur verbinden, wenn der Domänenbereich des FQDNs mit einer der domänen in Ihrem Mandanten registrierten Domänen mit Ausnahme von \* .onmicrosoft.com. Die \* Verwendung onmicrosoft.com -Domänennamen wird für den SBC-FQDN-Namen nicht unterstützt. Wenn Sie beispielsweise über zwei Domänennamen verfügen, **contoso**.com und **contoso**.onmicrosoft.com, können Sie sbc.contoso.com für den SBC-Namen verwenden. Wenn Sie versuchen, den SBC mit einem Namen wie "sbc.contoso.abc" zu verbinden, lässt das System Sie nicht zu, da die Domäne nicht im Besitz dieses Mandanten ist.<br/>
  > Neben der domäne, die in Ihrem Mandanten registriert ist, ist es wichtig, dass es einen Benutzer mit dieser Domäne und eine zugewiesene E3- oder E5-Lizenz gibt. Andern falls nicht, wird die folgende Fehlermeldung angezeigt:<br/>
  `Can not use the "sbc.contoso.com" domain as it was not configured for this tenant`.

Nachfolgend ein Beispiel:

```PowerShell
New-CsOnlinePSTNGateway -Identity sbc.contoso.com -Enabled $true -SipSignalingPort 5067 -MaxConcurrentSessions 100 
```

Gibt zurück:

<pre>
Identity              : sbc.contoso.com 
Fqdn                  : sbc.contoso.com 
SipSignalingPort     : 5067 
FailoverTimeSeconds   : 10 
ForwardCallHistory    : False 
ForwardPai            : False 
SendSipOptions        : True 
MaxConcurrentSessions : 100 
Enabled               : True   
</pre>

> [!NOTE]
> In diesem Beispiel werden nur die erforderlichen Mindestparameter angezeigt. Es gibt zusätzliche Parameter, die Sie mit dem [Cmdlet New-CsOnlinePSTNGateway](/powershell/module/skype/new-csonlinepstngateway) während des Verbindungsprozesses festlegen können. Weitere Informationen finden Sie unter [SBC-Einstellungen](#sbc-settings).
 
### <a name="verify-the-sbc-connection"></a>Überprüfen der SBC-Verbindung

So überprüfen Sie die Verbindung:

- [Überprüfen Sie, ob sich der SBC in der Liste der gekoppelten SBCs befindet.](#check-whether-the-sbc-is-on-the-list-of-paired-sbcs)
- [Überprüfen von SIP-Optionen](#validate-sip-options).
 
#### <a name="check-whether-the-sbc-is-on-the-list-of-paired-sbcs"></a>Überprüfen, ob sich der SBC in der Liste der gekoppelten SBCs befindet

Nachdem Sie die SBC verbunden haben, verwenden Sie das [Get-CsOnlinePSTNGateway-Cmdlet,](/powershell/module/skype/get-csonlinepstngateway) um zu überprüfen, ob der SBC in der Liste der gekoppelten SBCs vorhanden ist. Geben Sie Folgendes in eine Remote-PowerShell-Sitzung ein, und drücken Sie dann die EINGABETASTE:

```PowerShell
Get-CsOnlinePSTNGateway -Identity sbc.contoso.com  
```

Das gekoppelte Gateway sollte in der Liste angezeigt  werden, wie im folgenden Beispiel dargestellt, und der Parameter Aktiviert sollte den Wert **True anzeigen.**

Gibt zurück:

<pre>
Identity              : sbc.contoso.com  
Fqdn                  : sbc.contoso.com
SipSignalingPort     : 5067
CodecPriority         : SILKWB,SILKNB,PCMU,PCMA
ExcludedCodecs        :  
FailoverTimeSeconds   : 10
ForwardCallHistory    : False
ForwardPai            : False
SendSipOptions        : True
MaxConcurrentSessions : 100
Enabled               : True
</pre>

#### <a name="validate-sip-options"></a>Überprüfen von SIP-Optionen

Zum Überprüfen der Kopplung mit ausgehenden SIP-Optionen verwenden Sie die SBC-Verwaltungsschnittstelle, und vergewissern Sie sich, dass der SBC 200 OK-Antworten auf seine ausgehenden OPTIONEN-Nachrichten erhält.

Wenn Direct Routing eingehende OPTIONEN sieht, beginnt es, ausgehende SIP-Optionen-Nachrichten an den SBC-FQDN zu senden, der im Feld "Kontaktkopf" in der Nachricht "Eingehende OPTIONEN" konfiguriert ist. 

Zum Überprüfen der Kopplung mit eingehenden SIP-Optionen verwenden Sie die SBC-Verwaltungsschnittstelle, und sehen Sie, dass der SBC eine Antwort auf die OPTIONS-Nachrichten sendet, die von Direct Routing eingehen, und dass der von ihr gesendete Antwortcode 200 OK ist.

## <a name="sbc-settings"></a>SBC-Einstellungen

In dieser Tabelle sind die Optionen aufgeführt, die Sie für den SBC im Microsoft Teams Admin Center und mithilfe des [Cmdlets New-CsOnlinePSTNGateway](/powershell/module/skype/new-csonlinepstngateway) festlegen können.

|Erforderlich?|Microsoft Teams Admin Center-Einstellung|PowerShell-Parameter|Beschreibung|Standard|Mögliche Werte|Typ und Einschränkungen|
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|Ja|**Hinzufügen eines FQDNs für den SBC**|FQDN |Keine|FQDN-Name, Beschränkung auf 63 Zeichen|Zeichenfolge finden Sie in der Liste der zulässigen und nicht zulässigen Zeichen unter Benennungskonventionen in Active Directory für [Computer, Domänen, Websites und OUs.](https://support.microsoft.com/help/909264)|
|Nein|**Aktiviert**|Aktiviert|Aktivieren Sie den SBC für ausgehende Anrufe. Damit können Sie den SBC vorübergehend aus dem Dienst entfernen, während er aktualisiert wird oder während der Wartung. |Falsch|Wahr<br/>Falsch|Boolean|
|Ja|**SIP-Signalanschluss**|SipSignalingPort |Dies ist der Abhörport, der zum Kommunizieren mit Direct Routing mithilfe des TLS-Protokolls (Transport Layer) verwendet wird.|Keine|Beliebiger Port|0 bis 65535 |
|Nein|**Senden von SIP-Optionen**|SendSIPOptions |Definiert, ob der SBC SIP-Optionsnachrichten sendet. Es wird dringend empfohlen, diese Einstellung zu aktivieren. Wenn diese Einstellung deaktiviert ist, wird der SBC aus dem Überwachungs- und Warnungssystem ausgeschlossen.|Wahr|Wahr<br/>Falsch|Boolean|
|Nein|**Anrufverlauf weiterleiten**|ForwardCallHistory |Gibt an, ob Anrufverlaufsinformationen über den Trunk weitergeleitet werden. Wenn Sie dies aktivieren, sendet der Microsoft 365- oder Office 365-Proxy eine History-Info- und Referred-by-Kopfzeile. |Falsch|Wahr<br/>Falsch|Boolean|
|Nein|**Forward P-Asserted-identity (PA)-Header**|ForwardPAI|Gibt an, ob die KOPFZEILE von PAA zusammen mit dem Anruf weitergeleitet wird. Der PAI-Header bietet eine Möglichkeit, die Identität des Anrufers zu überprüfen. Wenn diese Einstellung an ist, wird auch der Header "Privacy:ID" gesendet.|Falsch|Wahr<br/>Falsch|Boolean|
|Nein|**Gleichzeitige Anrufkapazität**|MaxConcurrentSessions |Wenn Sie einen Wert festlegen, benachrichtigt Sie das Benachrichtigungssystem, wenn die Anzahl der gleichzeitigen Sitzungen 90 Prozent oder höher als dieser Wert ist. Wenn Sie keinen Wert festlegen, werden keine Benachrichtigungen generiert. Das Überwachungssystem gibt jedoch alle 24 Stunden die Anzahl der gleichzeitigen Sitzungen an. |Null|Null<br/>1 bis 100.000 ||
|Nein|**Failoverantwortcodes**|FailoverResponseCodes<br>|Wenn Direct Routing als Reaktion auf eine ausgehende Einladung einen 4xx- oder 6xx-SIP-Fehlercode empfängt, gilt der Anruf als standardmäßig abgeschlossen. Ausgehend bedeutet einen Anruf von einem Teams-Client an das PSTN mit Datenverkehrsfluss: Teams-Client -> Direct Routing -> SBC -> Telefonienetzwerk). Wenn Sie einen Failoverantwortcode angeben, erzwingt dies direct Routing, einen anderen SBC auszuprobieren (wenn ein anderer SBC in der Voiceroutingrichtlinie des Benutzers vorhanden ist), wenn er die angegebenen Codes empfängt, wenn der SBC aufgrund von Netzwerk- oder anderen Problemen keinen Anruf durchführen kann. Weitere Informationen finden Sie unter [Failover bestimmter SIP-Codes, die vom Session Border Controller (SBC) empfangen wurden.](direct-routing-trunk-failover-on-outbound-call.md)|408, 503, 504||Int|
|Nein|**Failoverzeiten (Sekunden)**|FailoverTimeSeconds |Wenn Sie einen Wert festlegen, werden ausgehende Anrufe, die vom Gateway nicht innerhalb der festgelegten Zeit beantwortet werden, an den nächsten verfügbaren Trunk geroutet. Wenn es keine zusätzlichen Trunks gibt, wird der Anruf automatisch verworfen. Der Standardwert beträgt 10 Sekunden. In einer Organisation mit langsamen Netzwerken und Gatewayantworten kann dies dazu führen, dass Anrufe unnötig verworfen werden.|10|Zahl|Int|
|Nein|**Bevorzugtes Land oder eine bevorzugte Region für Mediendatenverkehr**|MediaRelayRoutingLocationOverride |Mithilfe von können Sie Ihr bevorzugtes Land oder Ihre bevorzugte Region manuell für den Mediendatenverkehr festlegen. Wir empfehlen, diese Angabe nur zu setzen, wenn die Anrufprotokolle deutlich angeben, dass die Standardzuordnung des Rechenzentrums für den Medienpfad nicht den Pfad verwendet, der dem SBC-Rechenzentrum am nächsten ist. Standardmäßig weist Direct Routing ein Rechenzentrum basierend auf der öffentlichen IP-Adresse des SBC zu und wählt immer den Pfad aus, der dem SBC-Rechenzentrum am nächsten ist. In einigen Fällen ist der Standardpfad jedoch möglicherweise nicht der optimale Pfad. Mit diesem Parameter können Sie den bevorzugten Bereich für den Mediendatenverkehr manuell festlegen. |Keine|Ländercodes im ISO-Format||
|Nein|**SBC unterstützt PIDF/LO für Notrufe**|PidfloSupported|Geben Sie an, ob der SBC für Notrufe anwesenheitsinformationen-Datenformatspeicherortobjekt (PIDF/LO) unterstützt.||||
|Nein| - |MediaBypass|Diese Einstellung gibt an, ob der SBC die Medienumgehung unterstützt und ob Sie ihn für diesen SBC verwenden möchten. |Keine|Wahr<br/>Falsch|Boolean|

## <a name="see-also"></a>Mehr dazu

[Planen von direktem Routing](direct-routing-plan.md)

[Konfigurieren von direktem Routing](direct-routing-configure.md)

[Übersicht über PowerShell für Microsoft Teams](teams-powershell-overview.md)