---
title: Verbinden des Session Border Controller (SBC) mit Direct Routing
ms.reviewer: fillipse
ms.author: crowe
author: CarolynRowe
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
ms.localizationpriority: medium
search.appverid: MET150
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
f1.keywords:
- NOCSH
description: Erfahren Sie, wie Sie Ihren SBC mit Teams Phone System Direct Routing konfigurieren und verbinden.
ms.openlocfilehash: 0423c374e903aab2e283ee45bcabf9ceb31ef869
ms.sourcegitcommit: d87991ed2d3e4d70edb048378763a17ff689b710
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/07/2022
ms.locfileid: "66682664"
---
# <a name="connect-your-session-border-controller-sbc-to-direct-routing"></a>Verbinden des Session Border Controller (SBC) mit Direct Routing

In diesem Artikel wird beschrieben, wie Sie einen Session Border Controller (SBC) konfigurieren und mit Direct Routing verbinden.  Dies ist Schritt 1 der folgenden Schritte zum Konfigurieren von Direct Routing:

- **Schritt 1. Verbinden Sie Ihren SBC mit dem Telefonsystem, und überprüfen Sie die Verbindung** (dieser Artikel)
- Schritt 2: [Aktivieren von Benutzern für Direct Routing](direct-routing-enable-users.md)
- Schritt 3: [Konfigurieren der Anrufweiterleitung](direct-routing-voice-routing.md)
- Schritt 4: [Übersetzen von Zahlen in ein alternatives Format](direct-routing-translate-numbers.md)

Informationen zu allen Schritten, die zum Einrichten von Direct Routing erforderlich sind, finden [Sie unter Konfigurieren von Direct Routing](direct-routing-configure.md).

Sie können das [Microsoft Teams Admin Center](#using-the-microsoft-teams-admin-center) oder [PowerShell](#using-powershell) verwenden, um einen SBC zu konfigurieren und mit Direct Routing zu verbinden.

## <a name="using-the-microsoft-teams-admin-center"></a>Verwenden des Microsoft Teams Admin Centers

1. Wechseln Sie im linken Navigationsbereich zu **Voice** > **Direct Routing**, und klicken Sie dann auf die Registerkarte **"SBCs** ".

2. Klicken Sie auf **Hinzufügen**.

3. Geben Sie einen FQDN für den SBC ein. <br><br>Stellen Sie sicher, dass der Domänennamenteil des FQDN mit einer Domäne übereinstimmt, die in Ihrem Mandanten registriert ist, und beachten Sie, dass der `*.onmicrosoft.com` Domänenname für den SBC-FQDN-Domänennamen nicht unterstützt wird. Wenn Sie beispielsweise zwei Domänennamen haben, `contoso.com` und `contoso.onmicrosoft.com`verwenden Sie `sbc.contoso.com` sie als SBC-Namen. Wenn Sie eine Unterdomäne verwenden, stellen Sie sicher, dass diese Unterdomäne auch in Ihrem Mandanten registriert ist. Wenn Sie z. B. verwenden `sbc.service.contoso.com`möchten, muss dies `service.contoso.com` registriert werden.

4. Konfigurieren Sie die folgenden Einstellungen für den SBC basierend auf den Anforderungen Ihrer Organisation. Ausführliche Informationen zu den einzelnen Einstellungen finden Sie unter [SBC-Einstellungen](#sbc-settings).

    ![Screenshot der Seite "SBC hinzufügen" im Microsoft Teams Admin Center.](media/direct-routing-add-sbc.png)

5. Klicken Sie abschließend auf **Speichern**.

## <a name="using-powershell"></a>Verwendung von PowerShell

Um Ihren SBC mit Direct Routing zu verbinden, müssen Sie Folgendes ausführen:

1. [Stellen Sie mithilfe von PowerShell eine Verbindung mit Skype for Business Online](#connect-to-skype-for-business-online-by-using-powershell) her.

2. [Verbinden Sie den SBC mit dem Mandanten](#connect-the-sbc-to-the-tenant).

3. [Überprüfen Sie die SBC-Verbindung](#verify-the-sbc-connection).

### <a name="connect-to-skype-for-business-online-by-using-powershell"></a>Herstellen einer Verbindung mit Skype for Business Online mithilfe von PowerShell

Um den SBC mit der Direct Routing-Schnittstelle zu koppeln, verwenden Sie eine PowerShell-Sitzung, die mit dem Mandanten verbunden ist. Führen Sie zum Öffnen einer PowerShell-Sitzung die unter ["Einrichten ihres Computers für Windows PowerShell](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)" beschriebenen Schritte aus.
 
Überprüfen Sie nach dem Einrichten einer PowerShell-Remotesitzung, ob die Befehle zum Verwalten des SBC angezeigt werden. Um die Befehle zu überprüfen, geben Sie den folgenden Befehl in der PowerShell-Sitzung ein, oder kopieren Sie ihn, und fügen Sie ihn ein, und drücken Sie dann die EINGABETASTE: 

```PowerShell
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

### <a name="connect-the-sbc-to-the-tenant"></a>Verbinden des SBC mit dem Mandanten

Verwenden Sie das Cmdlet [New-CsOnlinePSTNGateway](/powershell/module/skype/new-csonlinepstngateway) , um den SBC mit dem Mandanten zu verbinden. Geben Sie in einer PowerShell-Sitzung Folgendes ein, und drücken Sie dann die EINGABETASTE:

```PowerShell
New-CsOnlinePSTNGateway -Fqdn <SBC FQDN> -SipSignalingPort <SBC SIP Port> -MaxConcurrentSessions <Max Concurrent Sessions the SBC can handle> -Enabled $true
```

  > [!NOTE]
  > 1. Es wird empfohlen, einen maximalen Anrufgrenzwert im SBC mithilfe von Informationen festzulegen, die in der SBC-Dokumentation zu finden sind. Der Grenzwert löst eine Benachrichtigung aus, wenn sich der SBC auf Kapazitätsebene befindet.
  > 2. Sie können den SBC nur verbinden, wenn der Domänenteil seines FQDN mit einer der in Ihrem Mandanten registrierten Domänen übereinstimmt, mit Ausnahme \*von .onmicrosoft.com. Die Verwendung von \*.onmicrosoft.com Domänennamen wird für den SBC-FQDN-Namen nicht unterstützt. Wenn Sie beispielsweise zwei Domänennamen haben, **"contoso.com**" und " **contoso.onmicrosoft.com**", können Sie sbc.contoso.com für den SBC-Namen verwenden. Wenn Sie versuchen, den SBC mit einem Namen wie "sbc.contoso.abc" zu verbinden, lässt das System Sie nicht zu, da die Domäne nicht im Besitz dieses Mandanten ist.<br/>
  > Neben der in Ihrem Mandanten registrierten Domäne ist es wichtig, dass es einen Benutzer mit dieser Domäne und eine zugewiesene E3- oder E5-Lizenz gibt. Andernfalls wird die folgende Fehlermeldung angezeigt:<br/>
  `Can not use the "sbc.contoso.com" domain as it was not configured for this tenant`.
  > 3. Mehrere IPs, die mit demselben FQDN auf der SBC-Seite zugeordnet sind, werden nicht unterstützt.
  > 4. Um unseren Kunden die erstklassige Verschlüsselung bereitzustellen, erzwingt Microsoft die TLS1.2-Verwendung für die Direct Routing-SIP-Schnittstelle.
  > Um Auswirkungen auf den Dienst zu vermeiden, stellen Sie sicher, dass Ihre SBCs für die Unterstützung von TLS1.2 konfiguriert sind und eine Verbindung mithilfe einer der folgenden Verschlüsselungssammlungen herstellen können: TLS_ECDHE_RSA_WITH_AES_256_GCM_SHA384 z. B. ECDHE-RSA-AES256-GCM-SHA384 TLS_ECDHE_RSA_WITH_AES_128_GCM_SHA256 d. h. ECDHE-RSA-AES128-GCM-SHA256 TLS_ECDHE_RSA_WITH_AES_256_CBC_SHA384 d. h. ECDHE-RSA-AES256-SHA384 TLS_ECDHE_RSA_WITH_AES_128_CBC_SHA256 d. h. ECDHE-RSA-AES128-SHA256

Nachfolgend ein Beispiel:

```PowerShell
New-CsOnlinePSTNGateway -Identity sbc.contoso.com -Enabled $true -SipSignalingPort 5067 -MaxConcurrentSessions 100 
```

Gibt Folgendes zurück:

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
> In diesem Beispiel werden nur die mindestens erforderlichen Parameter angezeigt. Es gibt zusätzliche Parameter, die Sie während des Verbindungsprozesses mit dem Cmdlet [New-CsOnlinePSTNGateway](/powershell/module/skype/new-csonlinepstngateway) festlegen können. Weitere Informationen finden Sie unter [SBC-Einstellungen](#sbc-settings).
 
### <a name="verify-the-sbc-connection"></a>Überprüfen der SBC-Verbindung

So überprüfen Sie die Verbindung:

- [Überprüfen Sie, ob sich der SBC in der Liste der gekoppelten SBCs befindet](#check-whether-the-sbc-is-on-the-list-of-paired-sbcs).
- [Überprüfen von SIP-Optionen](#validate-sip-options).
 
#### <a name="check-whether-the-sbc-is-on-the-list-of-paired-sbcs"></a>Überprüfen, ob sich der SBC in der Liste der gekoppelten SBCs befindet

Nachdem Sie den SBC verbunden haben, verwenden Sie das Cmdlet [Get-CsOnlinePSTNGateway](/powershell/module/skype/get-csonlinepstngateway) , um zu überprüfen, ob der SBC in der Liste der gekoppelten SBCs vorhanden ist. Geben Sie In einer PowerShell-Remotesitzung Folgendes ein, und drücken Sie dann die EINGABETASTE:

```PowerShell
Get-CsOnlinePSTNGateway -Identity sbc.contoso.com  
```

Das gekoppelte Gateway sollte in der Liste angezeigt werden, wie im folgenden Beispiel gezeigt, und der Parameter **"Enabled** " sollte den Wert **"True"** anzeigen.

Gibt Folgendes zurück:

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

Um die Kopplung mit ausgehenden SIP-Optionen zu überprüfen, verwenden Sie die SBC-Verwaltungsschnittstelle, und vergewissern Sie sich, dass der SBC 200 OK-Antworten auf die ausgehenden OPTIONS-Nachrichten empfängt.

Wenn direct Routing eingehende OPTIONEN sieht, beginnt es mit dem Senden ausgehender SIP-Optionsnachrichten an den SBC-FQDN, der im Feld "Kontaktkopf" in der eingehenden OPTIONS-Nachricht konfiguriert ist. 

Um die Kopplung mithilfe eingehender SIP-Optionen zu überprüfen, verwenden Sie die SBC-Verwaltungsschnittstelle und sehen, dass der SBC eine Antwort an die OPTIONS-Nachrichten sendet, die von Direct Routing kommen, und dass der Antwortcode, den er sendet, 200 OK ist.

## <a name="sbc-settings"></a>SBC-Einstellungen

In dieser Tabelle sind die Optionen aufgeführt, die Sie für den SBC im Microsoft Teams Admin Center und mithilfe des Cmdlets ["New-CsOnlinePSTNGateway](/powershell/module/skype/new-csonlinepstngateway) " festlegen können.

|Erforderlich?|Teams Admin Center-Einstellung|PowerShell-Parameter|Beschreibung|Standard|Mögliche Werte|Typ und Einschränkungen|
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|Ja|**Hinzufügen eines FQDN für den SBC**|FQDN |Keine|FQDN-Name, maximal 63 Zeichen|String, see the list of allowed and disallowed characters on [Naming conventions in Active Directory for computers, domains, sites, and OUs](https://support.microsoft.com/help/909264)|
|Nein|**Aktiviert**|Aktiviert|Hiermit aktivieren Sie den SBC für ausgehende Anrufe. Sie können dies verwenden, um den SBC vorübergehend aus dem Dienst zu entfernen, während er aktualisiert wird oder während der Wartung. |Falsch|Wahr<br/>Falsch|Boolean|
|Ja|**SIP-Signalisierungsport**|SipSignalingPort |Dies ist der Überwachungsport, der für die Kommunikation mit Direct Routing mithilfe des TLS-Protokolls (Transport Layer) verwendet wird.|Keine|Beliebiger Port|0 bis 65535 |
|Nein|**Senden von SIP-Optionen**|SendSIPOptions |Definiert, ob der SBC SIP-Optionsnachrichten sendet. Es wird dringend empfohlen, diese Einstellung zu aktivieren. Wenn diese Einstellung deaktiviert ist, wird der SBC vom Überwachungs- und Warnungssystem ausgeschlossen.|Wahr|Wahr<br/>Falsch|Boolean|
|Nein|**Anrufverlauf weiterleiten**|ForwardCallHistory |Gibt an, ob Anrufverlaufsinformationen über den Trunk weitergeleitet werden. Wenn Sie diese Option aktivieren, sendet der Microsoft 365-Proxy eine Verlaufsinformationen und eine Kopfzeile mit Bezug. |Falsch|Wahr<br/>Falsch|Boolean|
|Nein|**PaI-Header (Forward P-Asserted-identity)**|ForwardPAI|Gibt an, ob der PAI-Header zusammen mit dem Anruf weitergeleitet wird. Der PAI-Header bietet eine Möglichkeit, die Identität des Anrufers zu überprüfen. Wenn diese Einstellung aktiviert ist, wird auch der Privacy:ID-Header gesendet.|Falsch|Wahr<br/>Falsch|Boolean|
|Nein|**Kapazität für gleichzeitige Anrufe**|MaxConcurrentSessions |Wenn Sie einen Wert festlegen, werden Sie vom Benachrichtigungssystem benachrichtigt, wenn die Anzahl der gleichzeitigen Sitzungen 90 Prozent oder höher als dieser Wert ist. Wenn Sie keinen Wert festlegen, werden keine Warnungen generiert. Das Überwachungssystem meldet jedoch alle 24 Stunden die Anzahl der gleichzeitigen Sitzungen. |Null|Null<br/>1 bis 100.000 ||
|Nein|**Failoverantwortcodes**|FailoverResponseCodes<br>|Wenn Direct Routing als Reaktion auf eine ausgehende Einladung einen 4xx- oder 6xx-SIP-Fehlercode empfängt, gilt der Anruf standardmäßig als abgeschlossen. Ausgehend bedeutet ein Anruf von einem Teams-Client an das PSTN mit Datenverkehrsfluss: Teams-Client -> Direct Routing -> SBC -> Telefonienetzwerk). Wenn Sie einen Failoverantwortcode angeben, erzwingt dies Direct Routing, einen anderen SBC auszuprobieren (wenn ein anderer SBC in der VoIP-Routingrichtlinie des Benutzers vorhanden ist), wenn er die angegebenen Codes empfängt, wenn der SBC aufgrund von Netzwerk- oder anderen Problemen keinen Anruf tätigen kann. Weitere Informationen finden Sie unter [Failover bestimmter SIP-Codes, die vom Session Border Controller (SBC) empfangen wurden](direct-routing-trunk-failover-on-outbound-call.md).|408, 503, 504||Int|
|Nein|**Failoverzeiten (Sekunden)**|FailoverTimeSeconds |Wenn Sie einen Wert festlegen, werden ausgehende Anrufe, die nicht innerhalb der von Ihnen festgelegten Zeit vom Gateway beantwortet werden, an den nächsten verfügbaren Trunk weitergeleitet. Wenn keine zusätzlichen Trunks vorhanden sind, wird der Anruf automatisch abgebrochen. Der Standardwert ist 10 Sekunden. In einer Organisation mit langsamen Netzwerken und Gatewayantworten kann dies dazu führen, dass Anrufe unnötig verworfen werden.|10|Zahl|Int|
|Nein|**Bevorzugtes Land oder bevorzugte Region für Mediendatenverkehr**|MediaRelayRoutingLocationOverride | Gilt nicht für Direct Routing. Dieser Parameter ist für die Verwendung mit verwalteten Netzbetreibern in Anrufplänen reserviert. |Keine|||
|Nein|**SBC unterstützt PIDF/LO für Notrufe**|PidfloSupported|Geben Sie an, ob der SBC das Presence Information Data Format Location Object (PIDF/LO) für Notrufe unterstützt.||||
|Nein| - |MediaBypass|Diese Einstellung gibt an, ob der SBC die Medienumgehung unterstützt und ob Sie ihn für diesen SBC verwenden möchten. |Keine|Wahr<br/>Falsch|Boolean|

## <a name="see-also"></a>Siehe auch

[Planen von direktem Routing](direct-routing-plan.md)

[Konfigurieren von direktem Routing](direct-routing-configure.md)

[Übersicht über PowerShell für Microsoft Teams](teams-powershell-overview.md)
