---
title: Übersetzen von Telefonnummern für Direct Routing
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
description: Erfahren Sie, wie Sie Microsoft Phone System Direct Routing konfigurieren.
ms.openlocfilehash: 03abeed954a7760c7c53142380a8ca558c5b3761
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51096375"
---
# <a name="translate-phone-numbers-to-an-alternate-format"></a>Übersetzen von Telefonnummern in ein alternatives Format

In diesem Artikel wird beschrieben, wie Zahlen für ausgehende und eingehende Anrufe in ein alternatives Format übersetzt werden.  Dies ist Schritt 4 der folgenden Schritte zum Konfigurieren von Direct Routing:

- Schritt 1: [Verbinden des SBC mit Microsoft Phone System und Überprüfen der Verbindung](direct-routing-connect-the-sbc.md) 
- Schritt 2: [Aktivieren von Benutzern für Direct Routing, Voicemail und Voicemail](direct-routing-enable-users.md)   
- Schritt 3: [Konfigurieren des Sprachroutings](direct-routing-voice-routing.md)
- **Schritt 4. Übersetzen von Zahlen in ein alternatives Format**   (In diesem Artikel)

Informationen zu allen schritten, die zum Einrichten von Direct Routing erforderlich sind, finden Sie unter [Konfigurieren von Direct Routing](direct-routing-configure.md).

Manchmal möchten Mandantenadministratoren die Nummer für ausgehende und/oder eingehende Anrufe basierend auf den von ihnen erstellten Mustern ändern, um die Interoperabilität mit Session Border Controller (SBCs) sicherzustellen. In diesem Artikel wird beschrieben, wie Sie eine Richtlinie für Zahlenübersetzungsregeln angeben können, um Zahlen in ein alternatives Format zu übersetzen. 

Sie können die Richtlinie Zahlenübersetzungsregeln verwenden, um Zahlen für folgendes zu übersetzen:

- Eingehende Anrufe: Anrufe von einem PSTN-Endpunkt (Anrufer) an einen Teams-Client (Anrufer)
- Ausgehende Anrufe: Anrufe von einem Teams-Client (Anrufer) an einen PSTN-Endpunkt (Anrufer)

Die Richtlinie wird auf SBC-Ebene angewendet. Sie können einem SBC mehrere Übersetzungsregeln zuweisen, die in der Reihenfolge angewendet werden, in der sie angezeigt werden, wenn Sie sie in PowerShell auflisten. Sie können auch die Reihenfolge der Regeln in der Richtlinie ändern.

Verwenden Sie die [Cmdlets New-CsTeamsTranslationRule,](/powershell/module/skype/new-csteamstranslationrule) [Set-CsTeamsTranslationRule,](/powershell/module/skype/set-csteamstranslationrule) [Get-CsTeamsTranslationRule](/powershell/module/skype/get-csteamstranslationrule)und [Remove-CsTeamsTranslationRule,](/powershell/module/skype/remove-csteamstranslationrule) um Regeln zur Bearbeitung von Zahlen zu erstellen, zu ändern, zu anzeigen und zu löschen.

Zum Zuweisen, Konfigurieren und Listennummerieren von Manipulationsregeln auf SBCs verwenden Sie die [Cmdlets New-CSOnlinePSTNGateway](/powershell/module/skype/new-csonlinepstngateway) und [Set-CSOnlinePSTNGateway](/powershell/module/skype/set-csonlinepstngateway) zusammen mit den Parametern InboundTeamsNumberTranslationRules, InboundPSTNNumberTranslationRules, OutboundTeamsNumberTranslationRules, OutboundPSTNNumberTranslationRules, InboundTeamsNumberTranslationRules, InboundPSTNNumberTranslationRules, OutboundTeamsNumberTranslationRules und OutboundPSTNNumberTranslationRules.

> [!NOTE]
> Die maximale Gesamtzahl der Übersetzungsregeln beträgt 400, die maximale Länge des Übersetzungsparameters 100 Symbole, die maximale Länge des Übersetzungsparametermusters 1024 Symbole und die maximale Übersetzungsparameterlänge 256 Symbole.


## <a name="example-sbc-configuration"></a>SBC-Beispielkonfiguration

In diesem Szenario wird das ```New-CsOnlinePSTNGateway``` Cmdlet ausgeführt, um die folgende SBC-Konfiguration zu erstellen:

```PowerShell
New-CSOnlinePSTNGateway -Identity sbc1.contoso.com -SipSignalingPort 5061 –InboundTeamsNumberTranslationRules ‘AddPlus1’, ‘AddE164SeattleAreaCode’ -InboundPSTNNumberTranslationRules ‘AddPlus1’ -OutboundPSTNNumberTranslationRules ‘AddSeattleAreaCode’,  -OutboundTeamsNumberTranslationRules ‘StripPlus1’
```

Die dem SBC zugewiesenen Übersetzungsregeln sind in der folgenden Tabelle zusammengefasst:

|Name  |Muster |Übersetzung  |
|---------|---------|---------|
|AddPlus1     |^(\d {10} )$          |+1$1          |
|AddE164SeattleAreaCode      |^(\d {4} )$          | +1206555$1         |
|AddSeattleAreaCode    |^(\d {4} )$          | 425555$1         |
|StripPlus1    |^+1(\d {10} )$          | $1         |

In den folgenden Beispielen gibt es zwei Benutzer: Alice und Bob. Alice ist ein Teams-Benutzer, dessen Nummer +1 206 555 0100 ist. Bob ist ein PSTN-Benutzer, dessen Nummer +1 425 555 0100 ist.

## <a name="example-1-inbound-call-to-a-ten-digit-number"></a>Beispiel 1: Eingehender Anruf mit einer zehnstelligen Zahl

Bob ruft Alice mit einer zehnstelligen Zahl an, die nicht E.164 ist. Bob wählt 2065550100, um Alice zu erreichen.
SBC verwendet 2065550100 in den Headern RequestURI und An und 4255550100 in der Von-Kopfzeile.


|Kopfzeile  |Original |Übersetzte Kopfzeile |Parameter und angewendete Regel  |
|---------|---------|---------|---------|
|RequestURI  |EINLADEN sip:2065550100@sbc.contoso.com|EINLADEN sip:+12065550100@sbc.contoso.com|EingehendeTeamsNumberTranslationRules 'AddPlus1'|
|An    |An: \<sip:2065550100@sbc.contoso.com>|An: \<sip:+12065550100@sbc.contoso.com>|EingehendeTeamsNumberTranlationRules 'AddPlus1'|
|Von   |Von: \<sip:4255550100@sbc.contoso.com>|Von: \<sip:+14255550100@sbc.contoso.com>|EingehendePSTNNumberTranslationRules 'AddPlus1'|

## <a name="example-2-inbound-call-to-a-four-digit-number"></a>Beispiel 2: Eingehender Anruf zu einer vierstelligen Zahl

Bob ruft Alice mit einer vierstelligen Zahl an. Bob wählt 0100, um Alice zu erreichen.
SBC verwendet 0100 in den Headern RequestURI und An und 4255550100 in der Von-Kopfzeile.


|Kopfzeile  |Original |Übersetzte Kopfzeile |Parameter und angewendete Regel  |
|---------|---------|---------|---------|
|RequestURI  |EINLADEN sip:0100@sbc.contoso.com          |EINLADEN sip:+12065550100@sbc.contoso.com           |EingehendeTeamsNumberTranlationRules 'AddE164SeattleAreaCode'        |
|An    |An: \<sip:0100@sbc.contoso.com>|An: \<sip:+12065550100@sbc.contoso.com>|EingehendeTeamsNumberTranlationRules 'AddE164SeattleAreaCode'         |
|Von   |Von: \<sip:4255550100@sbc.contoso.com>|Von: \<sip:+14255550100@sbc.contoso.com>|EingehendePSTNNumberTranlationRules 'AddPlus1'        |

## <a name="example-3-outbound-call-using-a-ten-digit-non-e164-number"></a>Beispiel 3: Ausgehender Anruf mit einer zehnstelligen Nicht-E.164-Nummer

Alice ruft Bob mit einer zehnstelligen Zahl an. Alice wählt 425 555 0100, um Bob zu erreichen.
SBC ist so konfiguriert, dass nicht E.164 zehnstellige Zahlen für Teams- und PSTN-Benutzer verwendet werden.

In diesem Szenario übersetzt ein Wählplan die Nummer, bevor er an die Direct Routing-Schnittstelle sendet. Wenn Alice im Teams-Client 425 555 0100 einzahlt, wird die Nummer nach dem Länderwahlplan in +14255550100 übersetzt. Die resultierenden Zahlen sind eine kumulierte Normalisierung der Wählplanregeln und der Übersetzungsregeln von Teams. Die Übersetzungsregeln von Teams entfernen das "+1", das vom Wählplan hinzugefügt wurde.


|Kopfzeile  |Original |Übersetzte Kopfzeile |Parameter und angewendete Regel  |
|---------|---------|---------|---------|
|RequestURI  |EINLADEN sip:+14255550100@sbc.contoso.com          |EINLADEN sip:4255550100@sbc.contoso.com       |OutboundPSTNNumberTranlationRules 'StripPlus1'         |
|An    |An: \<sip:+14255550100@sbc.contoso.com>|An: \<sip:4255555555@sbc.contoso.com>|OutboundPSTNNumberTranlationRules 'StripPlus1'       |
|Von   |Von: \<sip:+12065550100@sbc.contoso.com>|Von: \<sip:2065550100@sbc.contoso.com>|OutboundTeamsNumberTranlationRules 'StripPlus1'         |

## <a name="example-4-outbound-call-using-a-four-digit-non-e164-number"></a>Beispiel 4: Ausgehender Anruf mit einer vierstelligen Nicht-E.164-Nummer

Alice ruft Bob mit einer vierstelligen Zahl an. Alice verwendet 0100, um Bob über Anrufe oder über einen Kontakt zu erreichen.
SBC ist für die Verwendung von nicht E.164 vierstelligen Zahlen für Teams-Benutzer und zehnstelligen Zahlen für PSTN-Benutzer konfiguriert. Der Wählplan wird in diesem Szenario nicht angewendet.


|Kopfzeile  |Original |Übersetzte Kopfzeile |Parameter und angewendete Regel  |
|---------|---------|---------|---------|
|RequestURI  |EINLADEN sip:0100@sbc.contoso.com           |EINLADEN sip:4255550100@sbc.contoso.com       |EingehendeTeamsNumberTranlationRules 'AddSeattleAreaCode'         |
|An    |An: \<sip:0100@sbc.contoso.com>|An: \<sip:4255555555@sbc.contoso.com>|EingehendeTeamsNumberTranlationRulesList 'AddSeattleAreaCode'       |
|Von   |Von: \<sip:+12065550100@sbc.contoso.com>|Von: \<sip:2065550100@sbc.contoso.com>| EingehendePSTNNumberTranlationRules 'StripPlus1' |

## <a name="see-also"></a>Mehr dazu

[Planen von direktem Routing](direct-routing-plan.md)

[Konfigurieren von direktem Routing](direct-routing-configure.md)