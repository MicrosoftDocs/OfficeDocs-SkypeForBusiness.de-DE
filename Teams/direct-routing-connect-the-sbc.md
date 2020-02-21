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
description: Hier erfahren Sie, wie Sie das direkte Routing des Microsoft Phone-Systems konfigurieren.
ms.openlocfilehash: e86b0397e4c00b892d99a0814579f20ba14e8b59
ms.sourcegitcommit: 0289062510f0791906dab2791c5db8acb1cf849a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/20/2020
ms.locfileid: "42157965"
---
# <a name="connect-your-session-border-controller-sbc-to-direct-routing"></a>Verbinden des Session Border Controllers (SBC) mit Direct Routing 

In diesem Artikel wird beschrieben, wie Sie den SBC (Session Border Controller) mit dem direkten Routing des Telefonsystems verbinden.  Schritt 1 der folgenden Schritte zum Konfigurieren des direkten Routings:

- **Schritt 1. Verbinden Ihres SBC mit dem Telefon System und Überprüfen der Verbindung** (dieser Artikel)
- Schritt 2: [Aktivieren von Benutzern für das direkte Routing](direct-routing-enable-users.md)
- Schritt 3: [Konfigurieren des Anruf Routings](direct-routing-voice-routing.md)
- Schritt 4: [Übersetzen von Zahlen in ein anderes Format](direct-routing-translate-numbers.md) 

Informationen zu allen Schritten, die für das Einrichten des direkten Routings erforderlich sind, finden Sie unter [Konfigurieren des direkten Routings](direct-routing-configure.md).

Um Ihre SBC mit Direct Routing zu verbinden, müssen Sie Folgendes tun: 

1. Stellen Sie mithilfe von PowerShell eine Verbindung mit dem **Skype for Business Online** Admin Center her.            
2. Verbinden Sie den SBC mit dem Mandanten.
3. Überprüfen Sie die Verbindung. 

## <a name="connect-to-skype-for-business-online-by-using-powershell"></a>Herstellen einer Verbindung mit Skype for Business Online mithilfe von PowerShell 

Sie können eine mit dem Mandanten verbundene PowerShell-Sitzung verwenden, um den SBC mit der direkten Routing Schnittstelle zu koppeln. Wenn Sie eine PowerShell-Sitzung öffnen möchten, führen Sie die Schritte unter [Einrichten Ihres Computers für Windows PowerShell](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)aus. 
 
Nachdem Sie eine Remote-PowerShell-Sitzung erstellt haben, überprüfen Sie, ob Sie die Befehle zum Verwalten des SBC sehen können. Um die Befehle zu überprüfen, geben Sie den folgenden Befehl in der PowerShell-Sitzung ein, oder kopieren Sie ihn, und drücken Sie die EINGABETASTE: 

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


## <a name="connect-the-sbc-to-the-tenant"></a>Verbinden des SBC mit dem Mandanten 

Wenn Sie den SBC mit dem Mandanten verbinden möchten, geben Sie in der PowerShell-Sitzung Folgendes ein, und drücken Sie die EINGABETASTE: 

```PowerShell
New-CsOnlinePSTNGateway -Fqdn <SBC FQDN> -SipSignalingPort <SBC SIP Port> -MaxConcurrentSessions <Max Concurrent Sessions the SBC can handle> -Enabled $true 
```
  > [!NOTE]
  > 1. Microsoft empfiehlt die Festlegung eines maximalen Anruf Limits im SBC mithilfe von Informationen, die in der SBC-Dokumentation zu finden sind. Der Grenzwert löst eine Benachrichtigung aus, wenn sich der SBC auf der Kapazitäts Ebene befindet.
  > 2. Sie können den SBC nur koppeln, wenn der Domänenteil des FQDN mit einer der in Ihrem Mandanten registrierten Domänen übereinstimmt \*, mit Ausnahme von onmicrosoft.com. Die \*Verwendung von onmicrosoft.com-Domänennamen wird für den Namen des SBC-FQDN nicht unterstützt. Wenn Sie beispielsweise über zwei Domänennamen verfügen:<br/><br/>
  > **contoso**. com<br/>**contoso**. onmicrosoft.com<br/><br/>
  > Für den SBC-Namen können Sie den Namen SBC.contoso.com verwenden. Wenn Sie versuchen, den SBC mit einem Namen SBC. contoso. ABC zu koppeln, lässt das System Sie nicht zu, da die Domäne nicht im Besitz dieses Mandanten ist.<br/>
  > Neben der in Ihrem Mandanten registrierten Domäne ist es wichtig, dass ein Benutzer mit dieser Domäne und eine zugewiesene E3-oder E5-Lizenz vorhanden ist. Wenn dies nicht der Fall ist, wird die folgende Fehlermeldung angezeigt:<br/>
  `Can not use the “sbc.contoso.com” domain as it was not configured for this tenant`.

```PowerShell
New-CsOnlinePSTNGateway -Identity sbc.contoso.com -Enabled $true -SipSignalingPort 5067 -MaxConcurrentSessions 100 
```
Gibt
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
Es gibt weitere Optionen, die während des Verbindungsprozesses festgesetzt werden können. Im vorherigen Beispiel werden jedoch nur die erforderlichen Mindestparameter angezeigt. 
 
In der folgenden Tabelle sind die zusätzlichen Parameter aufgeführt, die Sie zum Festlegen von ```New-CsOnlinePstnGateway```Parametern für verwenden können.

|Erforderlich?|Name|Beschreibung|Standard|Mögliche Werte|Typ und Einschränkungen|
|:-----|:-----|:-----|:-----|:-----|:-----|
|Ja|FQDN|Der FQDN-Name des SBC |Keine|NoneFQDN-Name, 63-Zeichen begrenzen|Zeichenfolge, Liste der zulässigen und nicht zulässigen Zeichen für [Benennungskonventionen in Active Directory für Computer, Domänen, Websites und OUs](https://support.microsoft.com/help/909264)|
|Nein|MediaBypass |Der vom SBC angegebene Parameter unterstützt die medienumgehung, und der Administrator möchte ihn verwenden.|Keine|Wahr<br/>Falsch|Boolean|
|Ja|SipSignalingPort |Der für die Kommunikation mit Direct Routing Services verwendete Überwachungs Port mithilfe des TLS-Protokolls (Transport Layer Security).|Keine|Beliebiger Port|0 bis 65535 |
|Nein|FailoverTimeSeconds |Bei Festlegung auf 10 (Standardwert) werden ausgehende Anrufe, die nicht innerhalb von 10 Sekunden vom Gateway beantwortet werden, an den nächsten verfügbaren trunk weitergeleitet; Wenn keine zusätzlichen Trunks vorhanden sind, wird der Anruf automatisch gelöscht. In einer Organisation mit langsamen Netzwerken und Gateway-Antworten kann dies potenziell dazu führen, dass Anrufe unnötig fallen. Der Standardwert ist 10.|10|Nummer|Int|
|Nein|ForwardCallHistory |Gibt an, ob Informationen zum Anrufverlauf durch den Trunk weitergeleitet werden. Wenn diese Option aktiviert ist, sendet der Office 365-PSTN-Proxy zwei Überschriften: Verlaufsinformationen und weitergeleitet. Der Standardwert ist **false** ($false). |Falsch|Wahr<br/>Falsch|Boolean|
|Nein|ForwardPAI|Gibt an, ob der PAI-Header (P-Asserted-Identity) zusammen mit dem Anruf weitergeleitet wird. Der PAI-Header bietet eine Möglichkeit, die Identität des Anrufers zu überprüfen. Wenn aktiviert, wird auch der Datenschutz: ID-Header gesendet. Der Standardwert ist **false** ($false).|Falsch|Wahr<br/>Falsch|Boolean|
|Nein|SendSIPOptions |Definiert, ob die SIP-Optionen von einem SBC gesendet werden sollen. Wenn diese Option deaktiviert ist, wird der SBC vom Überwachungs-und Warnungssystem ausgeschlossen. Wir empfehlen dringend, SIP-Optionen zu aktivieren. Der Standardwert ist **wahr**. |Wahr|Wahr<br/>Falsch|Boolean|
|Nein|MaxConcurrentSessions |Wird vom Warnungssystem verwendet. Wenn ein beliebiger Wert gesetzt ist, generiert das Warnungssystem eine Benachrichtigung an den mandantenadministrator, wenn die Anzahl der gleichzeitigen Sitzungen 90% oder höher als dieser Wert ist. Wenn der Parameter nicht gesetzt ist, werden die Benachrichtigungen nicht generiert. Das Überwachungssystem meldet jedoch die Anzahl der gleichzeitigen Sitzungen alle 24 Stunden. |NULL|NULL<br/>1 bis 100.000 ||
|Nein|MediaRelayRoutingLocationOverride |Ermöglicht das manuelle auswählen von Pfad für Medien. Beim direkten Routing wird ein Datacenter für Medienpfad basierend auf der öffentlichen IP-Adresse des SBC zugewiesen. Wir wählen immer am nächsten zum SBC-Rechenzentrum aus. In einigen Fällen kann eine öffentliche IP-Adresse, beispielsweise aus einem US-Bereich, einem SBC in Europa zugewiesen werden. In diesem Fall wird der Medienpfad nicht optimal verwendet. Mit diesem Parameter kann der bevorzugte Bereich für den Mediendatenverkehr manuell eingestellt werden. Microsoft empfiehlt nur das Festlegen dieses Parameters, wenn die Anrufprotokolle deutlich angeben, dass die automatische Zuweisung des Rechenzentrums für Medienpfad dem SBC-Rechenzentrum nicht am nächsten kommt. |Keine|Landesvorwahl im ISO-Format||
|Nein|Aktiviert|Wird verwendet, um diesen SBC für ausgehende Anrufe zu aktivieren. Kann verwendet werden, um den SBC vorübergehend zu entfernen, während er aktualisiert wird, oder während der Wartung. |Falsch|Wahr<br/>Falsch|Boolean|
 
## <a name="verify-the-sbc-connection"></a>Überprüfen der SBC-Verbindung 

So überprüfen Sie die Verbindung: 
- Überprüfen Sie, ob sich der SBC in der Liste der gekoppelten SBCS befindet. 
- Überprüfen Sie die SIP-Optionen. 
 
### <a name="check-if-the-sbc-is-on-the-list-of-paired-sbcs"></a>Überprüfen Sie, ob sich der SBC in der Liste der gekoppelten SBCS befindet. 

Nachdem Sie den SBC verbunden haben, überprüfen Sie, ob der SBC in der Liste der gekoppelten SBCS vorhanden ist, indem Sie den folgenden Befehl in einer Remote-PowerShell-Sitzung ausführen: 

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

### <a name="validate-sip-options-flow"></a>Überprüfen des SIP-Options Flusses 

Um die Kopplung mithilfe der ausgehenden SIP-Optionen zu überprüfen, verwenden Sie die SBC-Verwaltungsschnittstelle, und vergewissern Sie sich, dass der SBC 200-OK-Antworten auf die Nachrichten der ausgehenden Optionen erhält.

Wenn für das direkte Routing eingehende Optionen angezeigt werden, wird das Senden von ausgehenden SIP-Optionen Nachrichten an den SBC-FQDN gesendet, der im Feld Kontakt Kopf in der Nachricht eingehende Optionen konfiguriert ist. 

Wenn Sie die Kopplung mithilfe der eingehenden SIP-Optionen überprüfen möchten, verwenden Sie die SBC-Verwaltungsschnittstelle, und sehen Sie, dass der SBC eine Antwort auf die Options Nachrichten sendet, die vom direkten Routing eingehen, und dass der von ihm gesendete Antwortcode 200 OK ist.


## <a name="see-also"></a>Siehe auch

[Planen von direktem Routing](direct-routing-plan.md)

[Konfigurieren von direktem Routing](direct-routing-configure.md)
