---
title: Verbinden des Session Border Controllers (SBC) mit Direct Routing
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
description: Hier erfahren Sie, wie Sie Ihr SBC-zu-Telefon System-direkt Routing konfigurieren und verbinden.
ms.openlocfilehash: fbcc1d79a4875ba835fc77ea24f6356ded3da894
ms.sourcegitcommit: 6e24ea8aa9cccf8a1a964c8ed414ef5c7de3dc17
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/07/2020
ms.locfileid: "44159036"
---
# <a name="connect-your-session-border-controller-sbc-to-direct-routing"></a>Verbinden des Session Border Controllers (SBC) mit Direct Routing

In diesem Artikel wird beschrieben, wie Sie einen SBC (Session Border Controller) konfigurieren und ihn mit dem direkten Routing des Telefonsystems verbinden.  Schritt 1 der folgenden Schritte zum Konfigurieren des direkten Routings:

- **Schritt 1. Verbinden Ihres SBC mit dem Telefon System und Überprüfen der Verbindung** (dieser Artikel)
- Schritt 2: [Aktivieren von Benutzern für das direkte Routing](direct-routing-enable-users.md)
- Schritt 3: [Konfigurieren des Anruf Routings](direct-routing-voice-routing.md)
- Schritt 4: [Übersetzen von Zahlen in ein anderes Format](direct-routing-translate-numbers.md) 

Informationen zu allen Schritten, die zum Einrichten des direkten Routings erforderlich sind, finden Sie unter [Konfigurieren des direkten Routings](direct-routing-configure.md).

Sie können das [Microsoft Teams Admin Center](#using-the-microsoft-teams-admin-center) oder [PowerShell](#using-powershell) verwenden, um einen SBC mit Direct Routing zu konfigurieren und zu verbinden.

## <a name="using-the-microsoft-teams-admin-center"></a>Verwenden des Microsoft Teams Admin Centers

1. Wechseln Sie in der linken Navigationsleiste zu **VoIP** > **Direct Routing**, und klicken Sie dann auf die Registerkarte **SBCS** .
2. Klicken Sie auf **Hinzufügen**.
3. Geben Sie einen FQDN für den SBC ein. <br><br>Stellen Sie sicher, dass der Domänenname-Teil des FQDN einer Domäne entspricht, die in Ihrem Mandanten registriert ist, `*.onmicrosoft.com` und beachten Sie, dass der Domänenname für den Domänennamen des SBC-FQDN nicht unterstützt wird. Wenn Sie beispielsweise über zwei Domänennamen verfügen `contoso.com` und `contoso.on.microsoft.com`als SBC- `sbc.contoso.com` Namen verwenden.
4. Konfigurieren Sie die folgenden Einstellungen für den SBC basierend auf den Anforderungen Ihrer Organisation. Details zu den einzelnen Einstellungen finden Sie unter [SBC-Einstellungen](#sbc-settings).

    ![Screenshot der Seite "SBC hinzufügen" im Microsoft Teams Admin Center](media/direct-routing-add-sbc.png)

5. Klicken Sie abschließend auf **Speichern**.

## <a name="using-powershell"></a>Verwendung von PowerShell

Um Ihre SBC mit Direct Routing zu verbinden, müssen Sie Folgendes tun:

1. Stellen [Sie mithilfe von PowerShell eine Verbindung mit Skype for Business Online her](#connect-to-skype-for-business-online-by-using-powershell).
2. [Verbinden Sie den SBC mit dem Mandanten](#connect-the-sbc-to-the-tenant).
3. [Überprüfen Sie die SBC-Verbindung](#verify-the-sbc-connection).

### <a name="connect-to-skype-for-business-online-by-using-powershell"></a>Herstellen einer Verbindung mit Skype for Business Online mithilfe von PowerShell

Sie können eine mit dem Mandanten verbundene PowerShell-Sitzung verwenden, um den SBC mit der direkten Routing Schnittstelle zu koppeln. Wenn Sie eine PowerShell-Sitzung öffnen möchten, führen Sie die Schritte unter [Einrichten Ihres Computers für Windows PowerShell](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)aus.
 
Nachdem Sie eine Remote-PowerShell-Sitzung erstellt haben, stellen Sie sicher, dass Sie die Befehle zum Verwalten des SBC sehen können. Um die Befehle zu überprüfen, geben Sie den folgenden Befehl in der PowerShell-Sitzung ein, oder kopieren und fügen Sie ihn ein, und drücken Sie dann die EINGABETASTE: 

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

Verwenden Sie das Cmdlet [New-CsOnlinePSTNGateway](https://docs.microsoft.com/powershell/module/skype/new-csonlinepstngateway) , um den SBC mit dem Mandanten zu verbinden. Geben Sie in einer PowerShell-Sitzung Folgendes ein, und drücken Sie dann die EINGABETASTE:

```PowerShell
New-CsOnlinePSTNGateway -Fqdn <SBC FQDN> -SipSignalingPort <SBC SIP Port> -MaxConcurrentSessions <Max Concurrent Sessions the SBC can handle> -Enabled $true
```

  > [!NOTE]
  > 1. Wir empfehlen, dass Sie im SBC eine maximale Anrufbeschränkung mithilfe der Informationen angeben, die in der SBC-Dokumentation zu finden sind. Der Grenzwert löst eine Benachrichtigung aus, wenn sich der SBC auf der Kapazitäts Ebene befindet.
  > 2. Sie können den SBC nur verbinden, wenn der Domänenteil des FQDN mit einer der in Ihrem Mandanten registrierten Domänen übereinstimmt \*, mit Ausnahme von onmicrosoft.com. Die \*Verwendung von onmicrosoft.com-Domänennamen wird für den Namen des SBC-FQDN nicht unterstützt. Wenn Sie beispielsweise über zwei Domänennamen, " **contoso**. com" und " **contoso**. onmicrosoft.com" verfügen, können Sie SBC. contoso. con für den SBC-Namen verwenden. Wenn Sie versuchen, den SBC mit einem Namen wie SBC. contoso. ABC zu verbinden, lässt das System Sie nicht zu, da die Domäne nicht im Besitz dieses Mandanten ist.<br/>
  > Neben der in Ihrem Mandanten registrierten Domäne ist es wichtig, dass ein Benutzer mit dieser Domäne und eine zugewiesene E3-oder E5-Lizenz vorhanden ist. Wenn dies nicht der Fall ist, wird die folgende Fehlermeldung angezeigt:<br/>
  `Can not use the "sbc.contoso.com" domain as it was not configured for this tenant`.

Nachfolgend ein Beispiel:

```PowerShell
New-CsOnlinePSTNGateway -Identity sbc.contoso.com -Enabled $true -SipSignalingPort 5067 -MaxConcurrentSessions 100 
```

Was zurückgegeben wird:

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
> In diesem Beispiel werden nur die erforderlichen Mindestparameter angezeigt. Es gibt zusätzliche Parameter, die Sie mit dem Cmdlet [New-CsOnlinePSTNGateway](https://docs.microsoft.com/powershell/module/skype/new-csonlinepstngateway) während des Verbindungsprozesses festzulegen können. Weitere Informationen finden Sie unter [SBC-Einstellungen](#sbc-settings).
 
### <a name="verify-the-sbc-connection"></a>Überprüfen der SBC-Verbindung

So überprüfen Sie die Verbindung:

- [Überprüfen Sie, ob sich der SBC in der Liste der gekoppelten SBCS befindet](#check-whether-the-sbc-is-on-the-list-of-paired-sbcs).
- Überprüfen Sie die [SIP-Optionen](#validate-sip-options).
 
#### <a name="check-whether-the-sbc-is-on-the-list-of-paired-sbcs"></a>Überprüfen Sie, ob sich der SBC in der Liste der gekoppelten SBCS befindet.

Nachdem Sie den SBC verbunden haben, verwenden Sie das Cmdlet [Get-CsOnlinePSTNGateway](https://docs.microsoft.com/powershell/module/skype/get-csonlinepstngateway) , um zu überprüfen, ob der SBC in der Liste der gekoppelten SBCS vorhanden ist. Geben Sie in einer Remote-PowerShell-Sitzung Folgendes ein, und drücken Sie dann die EINGABETASTE:

```PowerShell
Get-CsOnlinePSTNGateway -Identity sbc.contoso.com  
```

Das gekoppelte Gateway sollte in der Liste angezeigt werden, wie im folgenden Beispiel gezeigt, und der Parameter **Enabled** sollte den Wert **true**aufweisen.

Was zurückgegeben wird:

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

Um die Kopplung mithilfe der ausgehenden SIP-Optionen zu überprüfen, verwenden Sie die SBC-Verwaltungsschnittstelle, und vergewissern Sie sich, dass der SBC 200-OK-Antworten auf die Nachrichten der ausgehenden Optionen erhält.

Wenn für das direkte Routing eingehende Optionen angezeigt werden, wird das Senden von ausgehenden SIP-Optionen Nachrichten an den SBC-FQDN gesendet, der im Feld Kontakt Kopf in der Nachricht eingehende Optionen konfiguriert ist. 

Wenn Sie die Kopplung mithilfe der eingehenden SIP-Optionen überprüfen möchten, verwenden Sie die SBC-Verwaltungsschnittstelle, und sehen Sie, dass der SBC eine Antwort auf die Options Nachrichten sendet, die vom direkten Routing eingehen, und dass der von ihm gesendete Antwortcode 200 OK ist.

## <a name="sbc-settings"></a>SBC-Einstellungen

In dieser Tabelle sind die Optionen aufgeführt, die Sie für den SBC im Microsoft Teams Admin Center und mithilfe des Cmdlets [New-CsOnlinePSTNGateway](https://docs.microsoft.com/powershell/module/skype/new-csonlinepstngateway) festgelegt haben.

|Erforderlich?|Microsoft Teams Admin Center-Einstellung|PowerShell-Parameter|Beschreibung|Standard|Mögliche Werte|Typ und Einschränkungen|
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|Ja|**Hinzufügen eines FQDN für den SBC**|FQDN |Keine|FQDN-Name, 63-Zeichen begrenzen|Zeichenfolge finden Sie in der Liste der zulässigen und nicht zulässigen Zeichen [für Benennungskonventionen in Active Directory für Computer, Domänen, Websites und OUs](https://support.microsoft.com/help/909264) .|
|Nein|**Aktiviert**|Aktiviert|Verwenden Sie diese Option, um den SBC für ausgehende Anrufe einzuschalten. Sie können diese Option verwenden, um den SBC vorübergehend aus dem Dienst zu entfernen, während er aktualisiert wird oder während der Wartung. |Falsch|Wahr<br/>Falsch|Boolean|
|Ja|**SIP-Signalisierungs-Port**|SipSignalingPort |Hierbei handelt es sich um den Abhör Port, der für die Kommunikation mit Direct Routing mithilfe des TLS-Protokolls (Transport Layer) verwendet wird.|Keine|Beliebiger Port|0 bis 65535 |
|Nein|**SIP-Optionen senden**|SendSIPOptions |Definiert, ob der SBC SIP-Options Nachrichten senden soll. Wir empfehlen Ihnen dringend, diese Einstellung zu aktivieren. Wenn diese Einstellung deaktiviert ist, wird der SBC vom Überwachungs-und Warnungssystem ausgeschlossen.|Wahr|Wahr<br/>Falsch|Boolean|
|Nein|**Anrufverlauf weiterleiten**|ForwardCallHistory |Gibt an, ob die Anrufverlaufs Informationen durch den trunk weitergeleitet werden. Wenn Sie diese Option aktivieren, sendet der Office 365-Proxy eine Verlaufsinformationen-und eine Verweis Kopfzeile. |Falsch|Wahr<br/>Falsch|Boolean|
|Nein|**Forward P-Asserted-Identity (Pai)-Kopfzeile**|ForwardPAI|Gibt an, ob der Pai-Header zusammen mit dem Anruf weitergeleitet wird. Der PAI-Header bietet eine Möglichkeit, die Identität des Anrufers zu überprüfen. Wenn diese Einstellung aktiviert ist, wird auch der Datenschutz: ID-Header gesendet.|Falsch|Wahr<br/>Falsch|Boolean|
|Nein|**Gleichzeitige Anrufkapazität**|MaxConcurrentSessions |Wenn Sie einen Wert setzen, benachrichtigt Sie das Benachrichtigungssystem, wenn die Anzahl der gleichzeitigen Sitzungen 90 Prozent oder höher als dieser Wert ist. Wenn Sie keinen Wert festlegen, werden keine Benachrichtigungen generiert. Das Überwachungssystem meldet jedoch die Anzahl der gleichzeitigen Sitzungen alle 24 Stunden. |NULL|NULL<br/>1 bis 100.000 ||
|Nein|**Failover-Antwortcodes**|FailoverResponseCodes<br>|Wenn das direkte Routing einen 4xx-oder 6xx-SIP-Fehlercode als Antwort auf eine ausgehende Einladung erhält, gilt der Anruf standardmäßig als abgeschlossen. Ausgehend bedeutet, dass ein Anruf von einem Team-Client an das PSTN mit Traffic Flow: Teams Client-> Direct Routing-> SBC->-Telefonie-Netzwerk). Wenn Sie einen Failover-Antwortcode angeben, erzwingt dies das direkte Routing, um einen anderen SBC zu testen (wenn ein anderer SBC in der VoIP-Routing Richtlinie des Benutzers vorhanden ist), wenn er die angegebenen Codes erhält, wenn der SBC aufgrund von Netzwerk-oder anderen Problemen keinen Anruf führen kann. Weitere Informationen finden Sie unter [Failover spezieller SIP-Codes, die vom Session Border Controller (SBC) empfangen](direct-routing-trunk-failover-on-outbound-call.md)werden.|408, 503, 504||Int|
|Nein|**Failover-Zeiten (Sekunden)**|FailoverTimeSeconds |Wenn Sie einen Wert festzulegen, werden ausgehende Anrufe, die nicht vom Gateway innerhalb der von Ihnen festgelegten Zeit beantwortet werden, an den nächsten verfügbaren trunk weitergeleitet. Wenn keine zusätzlichen Trunks vorhanden sind, wird der Anruf automatisch gelöscht. Der Standardwert ist 10 Sekunden. In einer Organisation mit langsamen Netzwerken und Gateway-Antworten kann dies potenziell dazu führen, dass Anrufe unnötig fallen.|10|Zahl|Int|
|Nein|**Bevorzugtes Land oder eine Region für den Medien Verkehr**|MediaRelayRoutingLocationOverride |Hiermit können Sie Ihr bevorzugtes Land oder Ihre bevorzugte Region für den Medien Verkehr manuell einstellen. Wir empfehlen, dies nur festzulegen, wenn die Anrufprotokolle deutlich angeben, dass die Standardzuweisung des Datencenters für den Medienpfad nicht den Pfad verwendet, der dem SBC-Rechenzentrum am nächsten ist. Standardmäßig weist das direkte Routing ein Datacenter basierend auf der öffentlichen IP-Adresse des SBC zu und wählt immer den Pfad aus, der dem SBC-Rechenzentrum am nächsten ist. In einigen Fällen ist der Standardpfad aber möglicherweise nicht der optimale Pfad. Mit diesem Parameter können Sie die bevorzugte Region für den Mediendatenverkehr manuell einstellen. |Keine|Landesvorwahl im ISO-Format||
|Nein|**SBC unterstützt PIDF/Lo für Notrufe**|PidfloSupported|Geben Sie an, ob der SBC für Notrufe das Daten Format Location-Objekt (PIDF/Lo) für Anwesenheitsinformationen unterstützt.||||
|Nein|**Anrufen des Telefons beim Versuch, den Nutzer zu finden**|GenerateRingingWhileLocatingUser|Legen Sie fest, ob ein Audiosignal an den Anrufer abgespielt wird, um anzugeben, dass die Teams den Anruf einrichten. Diese Einstellung gilt nur für das direkte Routing im nicht-Media-Bypass-Modus. Manchmal können eingehende Anrufe aus dem PSTN an Teams-Clients länger dauern als erwartet. In diesem Fall hört der Anrufer möglicherweise nichts, der Team-Client klingelt nicht und der Anruf kann von einigen Telekommunikationsanbietern abgebrochen werden. Diese Einstellung hilft, unerwartete Stille zu vermeiden, die in diesen Szenarien auftreten können.|Wahr|Wahr<br/>Falsch|Boolean|
|Nein| - |MediaBypass|Diese Einstellung gibt an, ob der SBC die medienumgehung unterstützt und ob Sie ihn für diesen SBC verwenden möchten. |Keine|Wahr<br/>Falsch|Boolean|

## <a name="see-also"></a>Siehe auch

[Planen von direktem Routing](direct-routing-plan.md)

[Konfigurieren von direktem Routing](direct-routing-configure.md)

[Übersicht über PowerShell für Microsoft Teams](teams-powershell-overview.md)
