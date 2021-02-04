---
title: Verbinden des Session Border Controllers (SBC) mit dem direkten Routing
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
description: Erfahren Sie, wie Sie Ihren SBC konfigurieren und mit dem direkten Routing des Telefonsystems verbinden.
ms.openlocfilehash: e20ab921e8f01d8beea15f0b1dd8a50e229f4e91
ms.sourcegitcommit: 5c33ca450a3215b9bf3c5da8bb3c9ef1a715a1a2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2021
ms.locfileid: "50099445"
---
# <a name="connect-your-session-border-controller-sbc-to-direct-routing"></a>Verbinden des Session Border Controllers (SBC) mit dem direkten Routing

In diesem Artikel wird beschrieben, wie Sie einen Session Border Controller (SBC) konfigurieren und mit dem direkten Routing des Telefonsystems verbinden.  Dies ist Schritt 1 der folgenden Schritte zum Konfigurieren des direkten Routings:

- **Schritt 1. Verbinden Des SBC mit dem Telefonsystem und Überprüfen der Verbindung** (dieser Artikel)
- Schritt 2: [Aktivieren von Benutzern für das direkte Routing](direct-routing-enable-users.md)
- Schritt 3: [Konfigurieren der Anrufrouting](direct-routing-voice-routing.md)
- Schritt 4: [Übersetzen von Zahlen in ein alternatives Format](direct-routing-translate-numbers.md) 

Informationen zu allen schritten, die zum Einrichten von Direct Routing erforderlich sind, finden Sie unter ["Konfigurieren des direkten Routings".](direct-routing-configure.md)

Sie können das [Microsoft Teams Admin Center](#using-the-microsoft-teams-admin-center) oder [PowerShell](#using-powershell) verwenden, um einen SBC zu konfigurieren und mit Direct Routing zu verbinden.

## <a name="using-the-microsoft-teams-admin-center"></a>Verwenden des Microsoft Teams Admin Centers

1. Wechseln Sie in der linken Navigationsleiste zu **Voice** Direct Routing, und klicken Sie dann auf die Registerkarte  >   **"SBCs".**
2. Klicken Sie auf **Hinzufügen**.
3. Geben Sie einen FQDN für den SBC ein. <br><br>Stellen Sie sicher, dass der Domänenname des FQDN einer Domäne entspricht, die in Ihrem Mandanten registriert ist, und denken Sie daran, dass der Domänenname für den Domänennamen des `*.onmicrosoft.com` SBC-FQDNs nicht unterstützt wird. Wenn Sie z. B. zwei Domänennamen haben und `contoso.com` `contoso.onmicrosoft.com` ", verwenden Sie `sbc.contoso.com` als SBC-Name". Wenn Sie eine Unterdomäne verwenden, stellen Sie sicher, dass diese Unterdomäne auch in Ihrem Mandanten registriert ist. Wenn Sie z. B. verwenden `sbc.service.contoso.com` möchten, müssen `service.contoso.com` Sie registriert sein.
4. Konfigurieren Sie die folgenden Einstellungen für den SBC basierend auf den Anforderungen Ihrer Organisation. Details zu den einzelnen Einstellungen finden Sie unter ["SBC-Einstellungen".](#sbc-settings)

    ![Screenshot der Seite "SBC hinzufügen" im Microsoft Teams Admin Center](media/direct-routing-add-sbc.png)

5. Klicken Sie abschließend auf **Speichern**.

## <a name="using-powershell"></a>Verwendung von PowerShell

Um Ihr SBC mit Direct Routing zu verbinden, müssen Sie:

1. [Stellen Sie mithilfe von PowerShell eine Verbindung](#connect-to-skype-for-business-online-by-using-powershell)mit Skype for Business Online herzustellen.
2. [Verbinden Sie den SBC mit dem Mandanten.](#connect-the-sbc-to-the-tenant)
3. [Überprüfen Sie die SBC-Verbindung.](#verify-the-sbc-connection)

### <a name="connect-to-skype-for-business-online-by-using-powershell"></a>Herstellen einer Verbindung mit Skype for Business Online mithilfe von PowerShell

Sie können eine mit dem Mandanten verbundene PowerShell-Sitzung verwenden, um den SBC mit der Direct-Routing-Schnittstelle zu koppeln. Zum Öffnen einer PowerShell-Sitzung führen Sie die schritte aus, die unter "Einrichten Ihres Computers für die [Windows PowerShell.](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)
 
Überprüfen Sie nach dem Einrichten einer Remote-PowerShell-Sitzung, ob die Befehle zum Verwalten des SBC angezeigt werden. Um die Befehle zu überprüfen, geben Sie in der PowerShell-Sitzung den folgenden Befehl ein. Sie können den Befehl auch kopieren und einfügen, und drücken Sie dann die EINGABETASTE: 

```PowerShell
Get-Command *onlinePSTNGateway*
```

Der Befehl gibt die vier hier gezeigten Funktionen zurück, mit deren Sie den SBC verwalten können.

<pre>
CommandType    Name                       Version    Source 
-----------    ----                       -------    ------ 
Function       Get-CsOnlinePSTNGateway    1.0        tmp_v5fiu1no.wxt 
Function       New-CsOnlinePSTNGateway    1.0        tmp_v5fiu1no.wxt 
Function       Remove-CsOnlinePSTNGateway 1.0        tmp_v5fiu1no.wxt 
Function       Set-CsOnlinePSTNGateway    1.0        tmp_v5fiu1no.wxt
</pre>

### <a name="connect-the-sbc-to-the-tenant"></a>Verbinden des SBC mit dem Mandanten

Verwenden Sie [das Cmdlet "New-CsOnlinePSTNGateway",](https://docs.microsoft.com/powershell/module/skype/new-csonlinepstngateway) um den SBC mit dem Mandanten zu verbinden. Geben Sie in einer PowerShell-Sitzung Folgendes ein, und drücken Sie dann die EINGABETASTE:

```PowerShell
New-CsOnlinePSTNGateway -Fqdn <SBC FQDN> -SipSignalingPort <SBC SIP Port> -MaxConcurrentSessions <Max Concurrent Sessions the SBC can handle> -Enabled $true
```

  > [!NOTE]
  > 1. Es wird empfohlen, eine maximale Anrufgrenze im SBC mithilfe von Informationen in der SBC-Dokumentation zu setzen. Der Grenzwert löst eine Benachrichtigung aus, wenn sich der SBC auf der Kapazitätsebene befindet.
  > 2. Sie können nur dann eine Verbindung mit dem SBC herstellen, wenn der Domänenteil des FQDNs einer der im Mandanten registrierten Domänen mit Ausnahme von \* ".onmicrosoft.com" onmicrosoft.com. Die \* Verwendung onmicrosoft.com A0 wird für den Namen des SBC-FQDNs nicht unterstützt. Wenn Sie beispielsweise zwei Domänennamen haben, **"contoso.com"** und **"contoso.onmicrosoft.com",** können Sie "sbc.contoso.con" als SBC-Namen verwenden. Wenn Sie versuchen, den SBC mit einem Namen wie "sbc.contoso.abc" zu verbinden, lässt das System dies nicht zu, da die Domäne nicht im Besitz dieses Mandanten ist.<br/>
  > Zusätzlich zur in Ihrem Mandanten registrierten Domäne ist es wichtig, dass es einen Benutzer mit dieser Domäne und einer zugewiesenen E3- oder E5-Lizenz gibt. Andern falls nicht, wird die folgende Fehlermeldung angezeigt:<br/>
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
> In diesem Beispiel werden nur die mindestens erforderlichen Parameter angezeigt. Es gibt weitere Parameter, die Sie während des Verbindungsprozesses mit dem [Cmdlet "New-CsOnlinePSTNGateway"](https://docs.microsoft.com/powershell/module/skype/new-csonlinepstngateway) festlegen können. Weitere Informationen finden Sie unter ["SBC-Einstellungen".](#sbc-settings)
 
### <a name="verify-the-sbc-connection"></a>Überprüfen der SBC-Verbindung

So überprüfen Sie die Verbindung:

- [Überprüfen Sie, ob sich der SBC in der Liste der gekoppelten SBCs befindet.](#check-whether-the-sbc-is-on-the-list-of-paired-sbcs)
- [Überprüfen Sie die SIP-Optionen.](#validate-sip-options)
 
#### <a name="check-whether-the-sbc-is-on-the-list-of-paired-sbcs"></a>Überprüfen, ob sich der SBC in der Liste der gekoppelten SBCs befindet

Nachdem Sie die SBC verbunden haben, verwenden Sie das [Cmdlet "Get-CsOnlinePSTNGateway",](https://docs.microsoft.com/powershell/module/skype/get-csonlinepstngateway) um zu überprüfen, ob der SBC in der Liste der gekoppelten SBCs enthalten ist. Geben Sie Folgendes in einer Remote-PowerShell-Sitzung ein, und drücken Sie dann die EINGABETASTE:

```PowerShell
Get-CsOnlinePSTNGateway -Identity sbc.contoso.com  
```

Das gekoppelte Gateway sollte in der Liste angezeigt werden, wie im folgenden Beispiel gezeigt, und der Parameter **"Enabled"** sollte den Wert **"True" enthalten.**

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

Um die Kopplung mithilfe von ausgehenden SIP-Optionen zu überprüfen, verwenden Sie die SBC-Verwaltungsschnittstelle, und vergewissern Sie sich, dass der SBC 200 OK-Antworten auf die ausgehenden OPTIONEN empfängt.

Wenn Direct Routing eingehende OPTIONEN sieht, beginnt es mit dem Senden ausgehender SIP Optionsnachrichten an den SBC-FQDN, der im Kopfzeilenfeld des Kontakts in der Nachricht mit den eingehenden OPTIONEN konfiguriert ist. 

Um die Kopplung mithilfe eingehender SIP-Optionen zu überprüfen, verwenden Sie die SBC-Verwaltungsschnittstelle, und überprüfen Sie, ob der SBC eine Antwort auf die OPTIONSnachrichten sendet, die von Direct Routing eintreffen, und dass der gesendete Antwortcode "200 OK" ist.

## <a name="sbc-settings"></a>SBC-Einstellungen

In dieser Tabelle sind die Optionen aufgeführt, die Sie für SBC im Microsoft Teams Admin Center und mithilfe des [Cmdlets "New-CsOnlinePSTNGateway"](https://docs.microsoft.com/powershell/module/skype/new-csonlinepstngateway) festlegen können.

|Erforderlich?|Microsoft Teams Admin Center (Einstellung)|PowerShell-Parameter|Beschreibung|Standard|Mögliche Werte|Typ und Einschränkungen|
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|Ja|**Hinzufügen eines FQDNs für den SBC**|FQDN |Keine|FQDN-Name, Beschränkung auf 63 Zeichen|Zeichenfolge finden Sie in der Liste der zulässigen und unzulässigen Zeichen zu Benennungskonventionen in Active Directory für [Computer, Domänen, Websites und Organisations-E-Mail-aktivierte Benutzer.](https://support.microsoft.com/help/909264)|
|Nein|**Aktiviert**|Aktiviert|Wird verwendet, um den SBC für ausgehende Anrufe zu aktivieren. Damit können Sie den SBC während der Aktualisierung oder während der Wartung vorübergehend aus dem Dienst entfernen. |Falsch|Wahr<br/>Falsch|Boolean|
|Ja|**SIP Signaling Port**|SipSignalingPort |Dies ist der Lauschport, der für die Kommunikation mit Direct Routing mithilfe des TLS (Transport Layer)-Protokolls verwendet wird.|Keine|Beliebiger Port|0 bis 65535 |
|Nein|**Senden von SIP-Optionen**|SendSIPOptions |Definiert, ob der SBC Nachrichten mit den SIP-Optionen sendet. Es wird dringend empfohlen, diese Einstellung zu aktivieren. Wenn diese Einstellung deaktiviert ist, wird der SBC aus dem Überwachungs- und Warnungssystem ausgeschlossen.|Wahr|Wahr<br/>Falsch|Boolean|
|Nein|**Anrufverlauf weiterleiten**|ForwardCallHistory |Gibt an, ob Anrufverlaufsinformationen über den Trunk weitergeleitet werden. Wenn Sie dies aktivieren, sendet der Microsoft 365- oder Office 365-Proxy eine Verlaufsinfo und eine Kopfzeile mit "Verwiesen von". |Falsch|Wahr<br/>Falsch|Boolean|
|Nein|**Header "Forward P-Asserted-identity (ÜBERSCHRIFTEN)"**|ForwardPAI|Gibt an, ob der HEADER VON IHNEN zusammen mit dem Anruf weitergeleitet wird. Der PAI-Header bietet eine Möglichkeit, die Identität des Anrufers zu überprüfen. Wenn diese Einstellung ist, wird auch der Header "Privacy:ID" gesendet.|Falsch|Wahr<br/>Falsch|Boolean|
|Nein|**Kapazität gleichzeitiger Anrufe**|MaxConcurrentSessions |Wenn Sie einen Wert festlegen, benachrichtigt Sie das Warnungssystem, wenn die Anzahl von gleichzeitigen Sitzungen 90 Prozent oder höher als dieser Wert ist. Wenn Sie keinen Wert festlegen, werden keine Warnungen generiert. Das Überwachungssystem wird jedoch alle 24 Stunden die Anzahl von gleichzeitigen Sitzungen melden. |Null|Null<br/>1 bis 100.000 ||
|Nein|**Failoverantwortcodes**|FailoverResponseCodes<br>|Wenn Direct Routing als Reaktion auf eine ausgehende Einladung einen 4xx- oder 6xx-SIP-Fehlercode empfängt, gilt der Anruf standardmäßig als abgeschlossen. Ausgehend bedeutet einen Anruf von einem Teamclient beim PSTN mit Datenverkehrsfluss: Teams-Client -> Direct Routing -> SBC ->-Telefonienetzwerk). Wenn Sie einen Failoverantwortcode angeben, zwingt dies Direct Routing, einen anderen SBC auszuprobieren (wenn ein anderer SBC in der Voiceroutingrichtlinie des Benutzers vorhanden ist), wenn er die angegebenen Codes empfängt, wenn der SBC aufgrund von Netzwerk- oder anderen Problemen keinen Aufruf ausführen kann. Weitere Informationen finden Sie unter Failover bestimmter SIP-Codes, die vom [Session Border Controller (SBC) empfangen werden.](direct-routing-trunk-failover-on-outbound-call.md)|408, 503, 504||Int|
|Nein|**Failoverzeiten (Sekunden)**|FailoverTimeSeconds |Wenn Sie einen Wert festlegen, werden ausgehende Anrufe, die nicht innerhalb der von Ihnen festgelegten Zeit vom Gateway beantwortet werden, an den nächsten verfügbaren Trunk geroutet. Wenn es keine zusätzlichen Trunks gibt, wird der Anruf automatisch verworfen. Der Standardwert ist 10 Sekunden. In einer Organisation mit langsamen Netzwerken und Gatewayantworten kann dies dazu führen, dass Anrufe unnötig verworfen werden.|10|Zahl|Int|
|Nein|**Bevorzugtes Land oder die bevorzugte Region für Medienverkehr**|MediaRelayRoutingLocationOverride |Verwenden Sie diese Option, um Ihr bevorzugtes Land oder Ihre bevorzugte Region für den Medienverkehr manuell zu festlegen. Diese Angabe wird nur empfohlen, wenn die Anrufprotokolle eindeutig angeben, dass die Standardzuordnung des Rechenzentrums für den Medienpfad nicht den Pfad verwendet, der dem Rechenzentrum am nächsten liegt. Standardmäßig weist Direct Routing ein Rechenzentrum basierend auf der öffentlichen IP-Adresse des SBC zu und wählt immer den Pfad aus, der dem SBC-Rechenzentrum am nächsten ist. In einigen Fällen ist der Standardpfad jedoch möglicherweise nicht der optimale Pfad. Mit diesem Parameter können Sie die bevorzugte Region für den Medienverkehr manuell festlegen. |Keine|Ländercodes im ISO-Format||
|Nein|**SBC unterstützt PIDF/LO für Notrufe**|PidfloSupported|Geben Sie an, ob der SBC für Notrufe das Location Object (PIDF/LO) für Anwesenheitsinformationen (Presence Information Data Format Location Object, PIDF/LO) unterstützt.||||
|Nein|**Telefon anrufen, während versucht wird, den Benutzer zu finden**|GenerateRingingWhileLocatingUser|Legen Sie fest, ob ein Audiosignal für den Anrufer abgespielt wird, um anzugeben, dass Teams den Anruf anruft. Diese Einstellung gilt nur für das direkte Routing im Nicht-Medienumgehungsmodus. Manchmal dauern eingehende Anrufe aus dem PSTN an die Teams-Clients länger als erwartet. In diesem Fall hört der Anrufer möglicherweise nichts, der Teams-Client klingelt nicht, und der Anruf wird möglicherweise von einigen Telekommunikationsanbietern storniert. Diese Einstellung hilft, unerwartete Stille zu vermeiden, die in diesen Szenarien auftreten können.|Wahr|Wahr<br/>Falsch|Boolean|
|Nein| - |MediaBypass|Diese Einstellung gibt an, ob der SBC die Medienumgehung unterstützt und ob Sie ihn für diesen SBC verwenden möchten. |Keine|Wahr<br/>Falsch|Boolean|

## <a name="see-also"></a>Siehe auch

[Planen von direktem Routing](direct-routing-plan.md)

[Konfigurieren von direktem Routing](direct-routing-configure.md)

[Übersicht über PowerShell für Microsoft Teams](teams-powershell-overview.md)
