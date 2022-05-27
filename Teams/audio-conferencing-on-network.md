---
title: On-Network Conferencing for Audiokonferenz
ms.author: heidip
author: MicrosoftHeidi
manager: serdars
ms.reviewer: oscarr
ms.topic: conceptual
ms.tgt.pltfrm: cloud
audience: admin
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
- M365-collaboration
- m365initiative-meetings
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.custom:
- Audio Conferencing
description: Im Folgenden wird "On-network" für Audiokonferenz beschrieben.
ms.openlocfilehash: 9b986bb8cd4d432c563e60f03e2dcdf496749f36
ms.sourcegitcommit: 296862e02b548f0212c9c70504e65b467d459cc3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/25/2022
ms.locfileid: "65675957"
---
# <a name="on-network-conferencing-for-audio-conferencing"></a>On-Network Conferencing for Audiokonferenz

MitHilfe von On-Network-Konferenzen können Organisationen eingehende und ausgehende Audiokonferenz Anrufe über Direct Routing an Microsoft-Einwahlnummern senden. Diese Funktion soll die Unterstützung von Audiokonferenz nicht auf Einwahlnummern von Drittanbietern erweitern. On-network Conferencing is not supported if it is used to routing inbound calls to the Audiokonferenz service through third party dial-in phone numbers or outbound calls to the PSTN from Microsoft Audiokonferenz Bridge.

In diesem Artikel werden die Voraussetzungen und Konfigurationsschritte beschrieben, die zum Aktivieren von On-Network-Konferenzen für Ihre Organisation erforderlich sind.

> [!IMPORTANT]
> On-network Conferencing must NOT be deployed with any telephony equipment in India.

## <a name="prerequisites"></a>Voraussetzungen

Stellen Sie vor der Konfiguration von On-Network-Konferenzen sicher, dass Ihre Organisation die folgenden Voraussetzungen erfüllt:

- Stellen Sie sicher, dass alle Benutzer in Ihrer Organisation, die für Audiokonferenz aktiviert sind oder aktiviert sind, Teams für alle Besprechungen verwenden. Das Routing eingehender und ausgehender Audiokonferenz Anrufe über On-Network-Konferenzen wird nur für Teams Besprechungen unterstützt.

- Weisen Sie allen Benutzern, die On-Network-Konferenzen verwenden, Audiokonferenz Lizenzen zu.

- Richten Sie den Audiokonferenz-Dienst ein. Weitere Informationen finden Sie unter [Einrichten von Audiokonferenz für Microsoft Teams](set-up-audio-conferencing-in-teams.md).

- Richten Sie Ihren Session Border Controller (SBC) für Direct Routing ein. Weitere Informationen finden Sie unter [Planen von Direct Routing](direct-routing-plan.md) und [Konfigurieren von Direct Routing](direct-routing-configure.md).

  Wenn Sie Direct Routing nur für die Zwecke von Audiokonferenz einrichten, müssen Sie nur "Schritt 1: Verbinden Ihres SBC" für On-Network-Konferenzen ausführen.

## <a name="enable-the-routing-of-dial-in-calls-to-microsoft-audio-conferencing-through-direct-routing"></a>Aktivieren des Routings von Einwahlanrufen an Microsoft Audiokonferenz über Direct Routing

Um Einwahlanrufe Ihrer lokalen Benutzer über Direct Routing an den Audiokonferenz-Dienst weiterzuleiten, müssen Sie geeignete Routingregeln für Ihre SBCs und Private Branch Exchange(s) (PBXs) konfigurieren.

Sie müssen die Telefonieausrüstung Ihrer Standorte so konfigurieren, dass Anrufe an eine beliebige Dienstnummer der Konferenzbrücke Ihrer Organisation über einen Direct Routing-Trunk weitergeleitet werden.

Die Servicenummern finden Sie im Admin Center Teams unter **"Besprechungen > Konferenzbrücken**" oder mithilfe des Skype for Business Online PowerShell-Cmdlets "Get-CsOnlineDialInConferencingBridge". Weitere Informationen finden Sie in einer Liste [der Audiokonferenz Zahlen in Microsoft Teams](see-a-list-of-audio-conferencing-numbers-in-teams.md).

> [!NOTE]
> Dieses Feature ist nicht für Benutzer mit der Audiokonferenz-Lizenz pro Minute verfügbar.

## <a name="enable-the-routing-of-teams-meeting-dial-out-calls-through-direct-routing"></a>Aktivieren des Routings von Teams Besprechungswählanrufen über Direct Routing

Teams Einwahlanrufe für Besprechungen werden von einer Besprechung in Ihrer Organisation an PSTN-Nummern initiiert, einschließlich Anruf-me-at-Anrufen und Anrufen, um neue Teilnehmer zu einer Besprechung zu bringen.

Um Teams Besprechungs-DFÜ-Routing über Direct Routing für Benutzer im Netzwerk zu aktivieren, müssen Sie eine Audiokonferenz Routingrichtlinie namens "OnlineAudioConferencingRoutingPolicy" erstellen und zuweisen.

Die Richtlinie "OnlineAudioConferencingRoutingPolicy" entspricht der CsOnlineVoiceRoutingPolicy für 1:1-PSTN-Anrufe über Direct Routing. Die Richtlinie "OnlineAudioConferencingRoutingPolicy" kann mithilfe der folgenden Cmdlets verwaltet werden:

- New-CsOnlineAudioConferencingRoutingPolicy
- Set-CsOnlineAudioConferencingRoutingPolicy
- Get-CsOnlineAudioConferencingRoutingPolicy
- Grant-CsOnlineAudioConferencingRoutingPolicy
- Remove-CsOnlineAudioConferencingRoutingPolicy

Weitere Informationen zum Routing für Direct Routing finden Sie unter [Konfigurieren von VoIP-Routing für Direct Routing](direct-routing-voice-routing.md).

Um das Routing von Besprechungswählanrufen über Direct Routing zu aktivieren, müssen Sie Folgendes ausführen:

- Konfigurieren Audiokonferenz Routingrichtlinien
- Konfigurieren des Routings auf den Telefoniegeräten Ihrer Organisation
- (Optional) Konfigurieren eines Wählplans

Ausgehende Anrufe aus Teams Besprechungen stammen von der Standarddienstnummer auf der Konferenzbrücke. Weitere Informationen zur Standarddienstnummer Ihrer Audiokonferenz Brücke finden [Sie unter Ändern der Telefonnummern auf Ihrer Audiokonferenz Brücke](change-the-phone-numbers-on-your-audio-conferencing-bridge.md).

### <a name="configure-audio-conferencing-routing-policies"></a>Konfigurieren Audiokonferenz Routingrichtlinien

Die Audiokonferenz Routingrichtlinie "OnlineAudioConferencingRoutingPolicy" bestimmt, welche Ausgehende Besprechungsanrufe an Direct Routing-Trunks weitergeleitet werden. Wenn Sie mit der CsOnlineVoiceRoutingPolicy-Richtlinie vertraut sind, funktioniert diese Richtlinie sehr ähnlich.

Die folgenden Schritte sind erforderlich, um Audiokonferenz Routingrichtlinien einzurichten:

1. Erstellen von PSTN-Verwendungen
1. Konfigurieren von VoIP-Routen
1. Erstellen Audiokonferenz VoIP-Routingrichtlinien
1. Zuweisen einer Richtlinie zu Ihren Benutzern

#### <a name="create-pstn-usages"></a>Erstellen von PSTN-Verwendungen

PSTN-Verwendungen sind Sammlungen von VoIP-Routen. Wenn ein Ausgehender Anruf aus der Besprechung eines bestimmten Organisators initiiert wird, werden VoIP-Routen verwendet, um den Routingpfad des Anrufs basierend auf den PSTN-Verwendungen zu bestimmen, die dem Benutzer über die VoIP-Routingrichtlinie des Benutzers zugeordnet sind.

Sie können eine PSTN-Verwendung mithilfe des Cmdlets "Set-CsOnlinePstnUsage" erstellen. Beispiel:

```powershell
Set-CsOnlinePstnUsage -Identity Global -Usage @{Add="US and Canada"}
```

#### <a name="configure-voice-routes"></a>Konfigurieren von VoIP-Routen

Sprachrouten bestimmen das PSTN-Gateway, das zum Weiterleiten eines Anrufs verwendet werden soll, basierend auf der Telefonnummer, die aus einer Teams Besprechung gewählt wird. VoIP-Routen bestimmen das PSTN-Gateway, das zum Weiterleiten eines bestimmten Anrufs verwendet werden soll, indem die telefonnummer, die aus einer Teams Besprechung gewählt wurde, mit einem regex-Muster übereinstimmt. Beim Erstellen einer VoIP-Route muss die Route einer oder mehreren PSTN-Verwendungen zugeordnet sein.

Mit dem Cmdlet "New-CsOnlineVoiceRoute" können Sie eine VoIP-Route erstellen und die regex und Gateways definieren, die der VoIP-Route zugeordnet werden sollen. Beispiel:

```powershell
New-CsOnlineVoiceRoute -Identity "Redmond 1" -NumberPattern "^\+1(425|206)(\d{7})$" -OnlinePstnGatewayList sbc1.contoso.biz, sbc2.contoso.biz -Priority 1 -OnlinePstnUsages "US and Canada"
```

#### <a name="create-audio-conferencing-voice-routing-policies"></a>Erstellen Audiokonferenz VoIP-Routingrichtlinien

Audiokonferenz VoIP-Routingrichtlinien bestimmen die möglichen Routen, die zum Weiterleiten eines Anrufs aus den Besprechungen eines Organisators verwendet werden können, basierend auf der Zieltelefonnummer des Besprechungswählanrufs. Audiokonferenz VoIP-Routingrichtlinien sind einer oder mehreren PSTN-Verwendungen zugeordnet, die wiederum die möglichen Routen bestimmen, die für die Besprechungswählanrufe der der Richtlinie zugeordneten Organisatoren verwendet werden sollen.

Sie können eine Audiokonferenz VoIP-Routingrichtlinie mithilfe des Cmdlets "New- CsOnlineAudioConferencingRoutingPolicy" erstellen. Beispiel:

```powershell
New-CsOnlineAudioConferencingRoutingPolicy "Policy 1" -OnlinePstnUsages "US and Canada"
```

Nachdem die Richtlinie einem Benutzer zugewiesen wurde und wenn aus einer der Besprechungen des Benutzers ein Besprechungswählanruf initiiert wird, werden die VoIP-Routen in den PSTN-Verwendungen ausgewertet, die dem Organisator über die VoIP-Routingrichtlinie des Benutzers zugeordnet sind. Wenn das Anrufziel für die Besprechungsauswahl einem Regulären Anruf in einer der VoIP-Routen entspricht, die dem Organisator zugeordnet sind, wird der Besprechungswählanruf an das in der VoIP-Route definierte PSTN-Gateway weitergeleitet. Wenn das Ziel des Besprechungswählanrufs keiner der dem Organisator zugeordneten VoIP-Routen entspricht, wird der Besprechungsauswahlanruf von Microsoft weitergeleitet.

#### <a name="assign-a-policy-to-your-users"></a>Zuweisen einer Richtlinie zu Ihren Benutzern

Nachdem die Audiokonferenz Routingrichtlinien definiert wurden, können Sie sie jetzt Benutzern zuweisen. Nachdem ihnen Richtlinien zugewiesen wurden, werden die Ausgehenden Besprechungsanrufe anhand der Richtlinie ausgewertet, um ihren Routingpfad zu ermitteln. Audiokonferenz Routingrichtlinien werden immer basierend auf dem Organisator der Besprechung unabhängig vom Benutzer in der Besprechung ausgewertet, der einen Besprechungswählanruf initiiert.

Mit dem Cmdlet "Grant-CsOnlineAudioConferencingRoutingPolicy" können Sie einem Benutzer eine Audiokonferenz VoIP-Routingrichtlinie zuweisen. Zum Beispiel: 

```powershell
Grant-CsOnlineAudioConferencingRoutingPolicy -Identity "<User Identity>" -PolicyName "Policy 1"
```

### <a name="configure-routing-on-the-telephony-equipment-of-your-organization"></a>Konfigurieren des Routings auf den Telefoniegeräten Ihrer Organisation

Auf den Telefoniegeräten Ihrer Organisation müssen Sie sicherstellen, dass die Besprechungswählanrufe, die über Direct Routing weitergeleitet werden, an das beabsichtigte Ziel im Netzwerk weitergeleitet werden.

### <a name="optional-configure-a-dial-plan"></a>(Optional) Konfigurieren eines Wählplans

Bei einem Wählplan handelt es sich um eine Reihe von Normalisierungsregeln, die gewählte Telefonnummern eines einzelnen Benutzers zu Zwecken der Anrufautorisierung und anrufweiterleitung in ein alternatives Format (in der Regel E.164) übersetzen.

Standardmäßig können Teams Benutzer PSTN-Nummern im E.164-Format, d. h. +\<country code\>\<number\>, anrufen. Wählpläne können jedoch verwendet werden, um Benutzern das Wählen von Telefonnummern in anderen Formaten zu ermöglichen, z. B. 4-stellige Erweiterungen.

Wenn Sie die erweiterungsbasierte Wählhilfe über On-Network-Konferenzen aktivieren möchten, können Sie Wählpläne einrichten, um das Erweiterungswählmuster den Telefonnummernbereichen der Telefonnummer Ihrer Organisation anzupassen. Informationen zum Einrichten von Wählplänen finden [Sie unter "Erstellen und Verwalten von Wählplänen](create-and-manage-dial-plans.md)".

## <a name="related-topics"></a>Verwandte Themen
