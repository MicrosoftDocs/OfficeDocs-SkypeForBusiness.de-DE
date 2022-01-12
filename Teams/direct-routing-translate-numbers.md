---
title: Übersetzen von Telefonnummern für das direkte Routing
ms.reviewer: ''
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
description: Hier erfahren Sie, wie Sie Microsoft-Telefon System Direct Routing konfigurieren.
ms.openlocfilehash: 2e94da39c23c10a912f4b3f0433467439b5ecf77
ms.sourcegitcommit: a969502c0a5237caf041d7726f4f1edefdd75b44
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2022
ms.locfileid: "61766368"
---
# <a name="translate-phone-numbers-to-an-alternate-format"></a>Übersetzen von Telefonnummern in ein alternatives Format

In diesem Artikel wird beschrieben, wie Nummern für ausgehende und eingehende Anrufe in ein alternatives Format übersetzt werden.  Dies ist Schritt 4 der folgenden Schritte zum Konfigurieren von Direct-Routing:

- Schritt 1: [Verbinden des SBC mit Microsoft-Telefon System und Überprüfen der Verbindung](direct-routing-connect-the-sbc.md) 
- Schritt 2: [Aktivieren von Benutzern für Direct Routing, Voicemail und Voicemail](direct-routing-enable-users.md)   
- Schritt 3: [Konfigurieren von Voice Routing](direct-routing-voice-routing.md)
- **Schritt 4. Übersetzen von Zahlen in ein alternatives Format**   (in diesem Artikel)

Informationen zu allen zum Einrichten von Direct-Routing erforderlichen Schritten finden Sie unter [Konfigurieren von Direct-Routing.](direct-routing-configure.md)

Manchmal möchten Mandantenadministratoren die Nummer für ausgehende und/oder eingehende Anrufe basierend auf den Mustern ändern, die sie erstellt haben, um die Interoperabilität mit Session Border Controller (SBCs) sicherzustellen. In diesem Artikel wird beschrieben, wie Sie eine Richtlinie für Zahlenübersetzungsregeln festlegen können, um Zahlen in ein alternatives Format zu übersetzen. 

Sie können die Richtlinie Regeln für die Zahlenübersetzung verwenden, um Zahlen wie folgt zu übersetzen:

- Eingehende Anrufe: Anrufe von einem PSTN-Endpunkt (Anrufer) an einen Teams (Anrufer)
- Ausgehende Anrufe: Anrufe von einem Teams-Client (Anrufer) an einen PSTN-Endpunkt (Anrufer)

Die Richtlinie wird auf SBC-Ebene angewendet. Sie können einem SBC mehrere Übersetzungsregeln zuweisen, die in der Reihenfolge angewendet werden, in der sie angezeigt werden, wenn Sie sie in PowerShell auflisten. Sie können auch die Reihenfolge der Regeln in der Richtlinie ändern.

Verwenden Sie zum Erstellen, Ändern, Anzeigen und Löschen von Regeln zur Bearbeitung von Zahlen die [Cmdlets New-CsTeamsTranslationRule,](/powershell/module/skype/new-csteamstranslationrule) [Set-CsTeamsTranslationRule,](/powershell/module/skype/set-csteamstranslationrule) [Get-CsTeamsTranslationRule](/powershell/module/skype/get-csteamstranslationrule)und [Remove-CsTeamsTranslationRule.](/powershell/module/skype/remove-csteamstranslationrule)

Zum Zuweisen, Konfigurieren und Auflisten von Manipulationsregeln für Rufnummern auf SBCs verwenden Sie die Cmdlets [New-CSOnlinePSTNGateway](/powershell/module/skype/new-csonlinepstngateway) und [Set-CSOnlinePSTNGateway](/powershell/module/skype/set-csonlinepstngateway) zusammen mit den Parametern InboundTeamsNumberTranslationRules, InboundPSTNNumberTranslationRules, OutboundTeamsNumberTranslationRules, OutboundPSTNNumberTranslationRules, InboundTeamsNumberTranslationRules, InboundPSTNNumberTranslationRules, OutboundTeamsNumberTranslationRules.

> [!NOTE]
> Die maximale Gesamtanzahl an Übersetzungsregeln beträgt 400, die maximale Länge von Übersetzungsparameternamen 100 Symbole, die maximale Länge des Übersetzungsparametermusters beträgt 1024 Symbole und die maximale Länge der Übersetzungsparameter von 256 Symbolen.


## <a name="example-sbc-configuration"></a>SBC-Beispielkonfiguration

In diesem Szenario wird das ```New-CsOnlinePSTNGateway``` Cmdlet ausgeführt, um die folgende SBC-Konfiguration zu erstellen:

```PowerShell
New-CSOnlinePSTNGateway -Identity sbc1.contoso.com -SipSignalingPort 5061 –InboundTeamsNumberTranslationRules ‘AddPlus1’, ‘AddE164SeattleAreaCode’ -InboundPSTNNumberTranslationRules ‘AddPlus1’ -OutboundPSTNNumberTranslationRules ‘AddSeattleAreaCode’,‘StripPlus1’  -OutboundTeamsNumberTranslationRules ‘StripPlus1’
```

Die dem SBC zugewiesenen Übersetzungsregeln sind in der folgenden Tabelle zusammengefasst:

|Name  |Muster |Übersetzung  |
|---------|---------|---------|
|AddPlus1     |^(\d {10} )$          |+1$1          |
|AddE164SeattleAreaCode      |^(\d {4} )$          | +1206555$1         |
|AddSeattleAreaCode    |^(\d {4} )$          | 425555$1         |
|StripPlus1    |^+1(\d {10} )$          | $1         |

In den folgenden Beispielen gibt es zwei Benutzer: Andrea und Robert. Andrea ist ein Teams Benutzer, dessen Zahl +1 206 555 0100 ist. Bob ist ein PstN-Benutzer, dessen Telefonnummer +1 425 555 0100 ist.

## <a name="example-1-inbound-call-to-a-ten-digit-number"></a>Beispiel 1: Eingehender Anruf an eine zehnstellige Nummer

Robert ruft Andrea mit einer nicht E,164-stelligen zehnstelligen Nummer an. Bob wählt einen 2065550100, um Andrea zu erreichen.
SBC verwendet 2065550100 in den Headern RequestURI und To und 4255550100 in der From-Kopfzeile.


|Kopfzeile  |Original |Übersetzte Kopfzeile |Angewendete Parameter und Regeln  |
|---------|---------|---------|---------|
|RequestURI  |Einladen sip:2065550100@sbc.contoso.com|EINLADEN sip:+12065550100@sbc.contoso.com|InboundTeamsNumberTranslationRules 'AddPlus1'|
|AN    |AN: \<sip:2065550100@sbc.contoso.com>|AN: \<sip:+12065550100@sbc.contoso.com>|InboundTeamsNumberTranlationRules 'AddPlus1'|
|VON   |VON: \<sip:4255550100@sbc.contoso.com>|VON: \<sip:+14255550100@sbc.contoso.com>|InboundPSTNNumberTranslationRules 'AddPlus1'|

## <a name="example-2-inbound-call-to-a-four-digit-number"></a>Beispiel 2: Eingehender Anruf an eine vierstellige Nummer

Bob ruft Andrea mit einer vierstelligen Nummer an. Bob wählt 0100, um Andrea zu erreichen.
SBC verwendet 0100 in den Headern RequestURI und To, 4255550100 in der From-Kopfzeile.


|Kopfzeile  |Original |Übersetzte Kopfzeile |Angewendete Parameter und Regeln  |
|---------|---------|---------|---------|
|RequestURI  |Einladen sip:0100@sbc.contoso.com          |EINLADEN sip:+12065550100@sbc.contoso.com           |InboundTeamsNumberTranlationRules 'AddE164SeattleAreaCode'        |
|AN    |AN: \<sip:0100@sbc.contoso.com>|AN: \<sip:+12065550100@sbc.contoso.com>|InboundTeamsNumberTranlationRules 'AddE164SeattleAreaCode'         |
|VON   |VON: \<sip:4255550100@sbc.contoso.com>|VON: \<sip:+14255550100@sbc.contoso.com>|InboundPSTNNumberTranlationRules 'AddPlus1'        |

## <a name="example-3-outbound-call-using-a-ten-digit-non-e164-number"></a>Beispiel 3: Ausgehender Anruf mit einer zehnstelligen Nicht-E.164-Nummer

Andrea ruft Bob mit einer zehnstelligen Nummer an. Andrea wählt 425 555 0100, um Bob zu erreichen.
SBC ist für die Verwendung von nicht E.164 zehnstelligen Nummern sowohl für Teams als Teams PSTN-Benutzer konfiguriert.

In diesem Szenario übersetzt ein Wählplan die Nummer vor dem Senden an die Direct Routing-Schnittstelle. Wenn Andrea 425 555 0100 in den Teams-Client ein gibt, wird die Nummer vom Wählplan des Landes in +14255550100 übersetzt. Die resultierenden Zahlen sind eine kumulierte Normalisierung der Wählplanregeln und Teams Übersetzungsregeln. Durch Teams Übersetzungsregeln wird das vom Wählplan hinzugefügte "+1" entfernt.


|Kopfzeile  |Original |Übersetzte Kopfzeile |Angewendete Parameter und Regeln  |
|---------|---------|---------|---------|
|RequestURI  |EINLADEN sip:+14255550100@sbc.contoso.com          |EINLADEN sip:4255550100@sbc.contoso.com       |OutboundPSTNNumberTranlationRules 'StripPlus1'         |
|AN    |AN: \<sip:+14255550100@sbc.contoso.com>|AN: \<sip:4255555555@sbc.contoso.com>|OutboundPSTNNumberTranlationRules 'StripPlus1'       |
|VON   |VON: \<sip:+12065550100@sbc.contoso.com>|VON: \<sip:2065550100@sbc.contoso.com>|OutboundTeamsNumberTranlationRules 'StripPlus1'         |

## <a name="example-4-outbound-call-using-a-four-digit-non-e164-number"></a>Beispiel 4: Ausgehender Anruf mit einer vierstelligen Nicht-E.164-Nummer

Andrea ruft Bob mit einer vierstelligen Nummer an. Andrea verwendet 0100, um Bob über Anrufe oder mithilfe eines Kontakts zu erreichen.
SBC ist so konfiguriert, dass für Teams-Benutzer nicht E.164-Nummern und für Benutzer im öffentlichen Telefonnetz zehnstellige Nummern verwendet werden. Der Wählplan wird in diesem Szenario nicht angewendet.


|Kopfzeile  |Original |Übersetzte Kopfzeile |Angewendete Parameter und Regeln  |
|---------|---------|---------|---------|
|RequestURI  |Einladen sip:0100@sbc.contoso.com           |EINLADEN sip:4255550100@sbc.contoso.com       |InboundTeamsNumberTranlationRules 'AddSeattleAreaCode'         |
|AN    |AN: \<sip:0100@sbc.contoso.com>|AN: \<sip:4255555555@sbc.contoso.com>|InboundTeamsNumberTranlationRulesList 'AddSeattleAreaCode'       |
|VON   |VON: \<sip:+12065550100@sbc.contoso.com>|VON: \<sip:2065550100@sbc.contoso.com>| InboundPSTNNumberTranlationRules 'StripPlus1' |

## <a name="see-also"></a>Mehr dazu

[Planen von direktem Routing](direct-routing-plan.md)

[Konfigurieren von direktem Routing](direct-routing-configure.md)
