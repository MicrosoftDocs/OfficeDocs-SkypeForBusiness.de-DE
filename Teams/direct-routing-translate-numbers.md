---
title: Übersetzen von Telefonnummern für die direkte Weiterleitung
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
ms.openlocfilehash: 7d48e9163dd5927cbeddf4a4104d2382e69e7e2b
ms.sourcegitcommit: f9daef3213a305676127cf5140af907e3b96d046
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/07/2020
ms.locfileid: "48369160"
---
# <a name="translate-phone-numbers-to-an-alternate-format"></a>Übersetzen von Telefonnummern in ein anderes Format

In diesem Artikel wird beschrieben, wie Sie zahlen für ausgehende und eingehende Anrufe in ein alternatives Format übersetzen.  Dies ist Schritt 4 der folgenden Schritte zum Konfigurieren des direkten Routings:

- Schritt 1: [Verbinden des SBC mit dem Microsoft Phone-System und Überprüfen der Verbindung](direct-routing-connect-the-sbc.md) 
- Schritt 2: [Aktivieren von Benutzern für Direct Routing, Voicemail und Voicemail](direct-routing-enable-users.md)   
- Schritt 3: [Konfigurieren des VoIP-Routings](direct-routing-voice-routing.md)
- **Schritt 4. Übersetzen von Zahlen in ein alternatives Format**   (dieser Artikel)

Informationen zu allen Schritten, die für das Einrichten des direkten Routings erforderlich sind, finden Sie unter [Konfigurieren des direkten Routings](direct-routing-configure.md).

Manchmal möchten mandantenadministratoren die Nummer für ausgehende und/oder eingehende Anrufe basierend auf den von Ihnen erstellten Mustern ändern, um die Interoperabilität mit Session Border Controllers (SBCS) zu gewährleisten. In diesem Artikel wird beschrieben, wie Sie eine Richtlinie für die Nummernübersetzung angeben können, um Zahlen in ein alternatives Format zu übersetzen. 

Sie können die Richtlinien für die Zahlen Übersetzung verwenden, um Zahlen für Folgendes zu übersetzen:

- Eingehende Anrufe: Anrufe von einem PSTN-Endpunkt (Anrufer) an einen Teams-Client (angerufener)
- Ausgehende Anrufe: Anrufe von einem Team-Client (Anrufer) an einen PSTN-Endpunkt (angerufener)

Die Richtlinie wird auf der SBC-Ebene angewendet. Sie können einem SBC mehrere Übersetzungsregeln zuweisen, die in der Reihenfolge angewendet werden, in der Sie angezeigt werden, wenn Sie Sie in PowerShell auflisten. Sie können auch die Reihenfolge der Regeln in der Richtlinie ändern.

Zum Erstellen, ändern, anzeigen und Löschen von Regeln für die Nummern Manipulation verwenden Sie die Cmdlets [New-CsTeamsTranslationRule](https://docs.microsoft.com/powershell/module/skype/new-csteamstranslationrule), [Sets-CsTeamsTranslationRule](https://docs.microsoft.com/powershell/module/skype/set-csteamstranslationrule), [Get-CsTeamsTranslationRule](https://docs.microsoft.com/powershell/module/skype/get-csteamstranslationrule)und [Remove-CsTeamsTranslationRule](https://docs.microsoft.com/powershell/module/skype/remove-csteamstranslationrule) .

Verwenden Sie die Cmdlets [New-CSOnlinePSTNGateway](https://docs.microsoft.com/powershell/module/skype/new-csonlinepstngateway) und [setCSOnlinePSTNGateway](https://docs.microsoft.com/powershell/module/skype/set-csonlinepstngateway) zusammen mit den Parametern InboundTeamsNumberTranslationRules, InboundPSTNNumberTranslationRules, OutboundTeamsNumberTranslationRules, OutboundPSTNNumberTranslationRules, InboundTeamsNumberTranslationRules, InboundPSTNNumberTranslationRules, OutboundTeamsNumberTranslationRules und OutboundPSTNNumberTranslationRules, um Nummern Manipulations Regeln für SBCS zuzuweisen, zu konfigurieren und zu Listen.

> [!NOTE]
> Die maximale Gesamtzahl der Übersetzungsregeln lautet 400, die maximale Länge des Übersetzungs Parameters ist 100-Symbole, die maximale Länge des Translation-Parameter-Musters ist 1024-Symbole, und die maximale Übersetzungsparameter-Übersetzungs Länge beträgt 256-Symbole.


## <a name="example-sbc-configuration"></a>Beispiel-SBC-Konfiguration

Für dieses Szenario wird das ```New-CsOnlinePSTNGateway``` Cmdlet ausgeführt, um die folgende SBC-Konfiguration zu erstellen:

```PowerShell
New-CSOnlinePSTNGateway -Identity sbc1.contoso.com -SipSignalingPort 5061 –InboundTeamsNumberTranslationRules ‘AddPlus1’, ‘AddE164SeattleAreaCode’ -InboundPSTNNumberTranslationRules ‘AddPlus1’ -OutboundPSTNNumberTranslationRules ‘AddSeattleAreaCode’,  -OutboundTeamsNumberTranslationRules ‘StripPlus1’
```

Die dem SBC zugewiesenen Übersetzungsregeln sind in der folgenden Tabelle zusammengefasst:

|Name  |Muster |Übersetzung  |
|---------|---------|---------|
|AddPlus1     |^ (\d {10} ) $          |+1$1          |
|AddE164SeattleAreaCode      |^ (\d {4} ) $          | + 1206555 $1         |
|AddSeattleAreaCode    |^ (\d {4} ) $          | 425555 $1         |
|StripPlus1    |^ + 1 (\d {10} ) $          | $1         |

In den folgenden Beispielen gibt es zwei Benutzer: Alice und Bob. Alice ist ein Team Benutzer, dessen Nummer + 1 206 555 0100 ist. Bob ist ein PSTN-Benutzer, dessen Nummer + 1 425 555 0100 ist.

## <a name="example-1-inbound-call-to-a-ten-digit-number"></a>Beispiel 1: eingehender Anruf an eine zehnstellige Zahl

Bob ruft Alice mit einer nicht-E. 164-zehnstelligen Zahl an. Bob wählt 2065550100, um Alice zu erreichen.
SBC verwendet 2065550100 in den RequestURI und den Headern und 4255550100 im from-Header.


|Header  |Original |Übersetzte Kopfzeile |Parameter und Regel angewendet  |
|---------|---------|---------|---------|
|RequestURI  |Einladen von SIP:2065550100@SBC.contoso.com|Einladen von SIP:+12065550100@SBC.contoso.com|InboundTeamsNumberTranslationRules 'AddPlus1'|
|An    |An: \<sip:2065550100@sbc.contoso.com>|An: \<sip:+12065550100@sbc.contoso.com>|InboundTeamsNumberTranlationRules 'AddPlus1'|
|Von   |Von: \<sip:4255550100@sbc.contoso.com>|Von: \<sip:+14255550100@sbc.contoso.com>|InboundPSTNNumberTranslationRules 'AddPlus1'|

## <a name="example-2-inbound-call-to-a-four-digit-number"></a>Beispiel 2: eingehende Anrufe an eine vierstellige Zahl

Bob ruft Alice mit einer vierstelligen Zahl an. Bob wählt 0100, um Alice zu erreichen.
SBC verwendet 0100 in den RequestURI und den Headern und 4255550100 im from-Header.


|Header  |Original |Übersetzte Kopfzeile |Parameter und Regel angewendet  |
|---------|---------|---------|---------|
|RequestURI  |Einladen von SIP:0100@SBC.contoso.com          |Einladen von SIP:+12065550100@SBC.contoso.com           |InboundTeamsNumberTranlationRules 'AddE164SeattleAreaCode'        |
|An    |An: \<sip:0100@sbc.contoso.com>|An: \<sip:+12065550100@sbc.contoso.com>|InboundTeamsNumberTranlationRules 'AddE164SeattleAreaCode'         |
|Von   |Von: \<sip:4255550100@sbc.contoso.com>|Von: \<sip:+14255550100@sbc.contoso.com>|InboundPSTNNumberTranlationRules 'AddPlus1'        |

## <a name="example-3-outbound-call-using-a-ten-digit-non-e164-number"></a>Beispiel 3: ausgehender Anruf mit einer zehnstelligen nicht-E. 164-Nummer

Alice ruft Bob mit einer zehnstelligen Zahl an. Alice wählt 425 555 0100, um Bob zu erreichen.
SBC ist für die Verwendung von nicht-E. 164-Nummern für Teams und PSTN-Benutzer konfiguriert.

In diesem Szenario übersetzt ein Wählplan die Nummer vor dem Senden an die direkte Routing Schnittstelle. Wenn Alice in den Teams-Client 425 555 0100 eingibt, wird die Nummer im Länder Wählplan in + 14255550100 übersetzt. Bei den resultierenden Zahlen handelt es sich um eine kumulative Normalisierung der Wähl Plan Regeln und der Übersetzungsregeln für Teams. Die Übersetzungsregeln für Teams entfernen das "+ 1", das vom Wählplan hinzugefügt wurde.


|Header  |Original |Übersetzte Kopfzeile |Parameter und Regel angewendet  |
|---------|---------|---------|---------|
|RequestURI  |Einladen von SIP:+14255550100@SBC.contoso.com          |Einladen von SIP:4255550100@SBC.contoso.com       |OutboundPSTNNumberTranlationRules 'StripPlus1'         |
|An    |An: \<sip:+14255550100@sbc.contoso.com>|An: \<sip:4255555555@sbc.contoso.com>|OutboundPSTNNumberTranlationRules 'StripPlus1'       |
|Von   |Von: \<sip:+12065550100@sbc.contoso.com>|Von: \<sip:2065550100@sbc.contoso.com>|OutboundTeamsNumberTranlationRules 'StripPlus1'         |

## <a name="example-4-outbound-call-using-a-four-digit-non-e164-number"></a>Beispiel 4: Outbound-Anruf mit einer vierstelligen nicht-E. 164-Nummer

Alice ruft Bob mit einer vierstelligen Zahl an. Alice verwendet 0100, um Bob von anrufen oder über einen Kontakt zu erreichen.
SBC ist für die Verwendung von nicht-E. 164-vierstelligen Zahlen für Teams-Benutzer und zehnstellige Zahlen für PSTN-Benutzer konfiguriert. In diesem Szenario wird der Wählplan nicht angewendet.


|Header  |Original |Übersetzte Kopfzeile |Parameter und Regel angewendet  |
|---------|---------|---------|---------|
|RequestURI  |Einladen von SIP:0100@SBC.contoso.com           |Einladen von SIP:4255550100@SBC.contoso.com       |InboundTeamsNumberTranlationRules 'AddSeattleAreaCode'         |
|An    |An: \<sip:0100@sbc.contoso.com>|An: \<sip:4255555555@sbc.contoso.com>|InboundTeamsNumberTranlationRulesList 'AddSeattleAreaCode'       |
|Von   |Von: \<sip:+12065550100@sbc.contoso.com>|Von: \<sip:2065550100@sbc.contoso.com>| InboundPSTNNumberTranlationRules 'StripPlus1' |

## <a name="see-also"></a>Weitere Informationen

[Planen von direktem Routing](direct-routing-plan.md)

[Konfigurieren von direktem Routing](direct-routing-configure.md)
