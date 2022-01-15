---
title: Netzwerkkonferenzen für Audiokonferenzen
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
description: Im Folgenden wird Das Netzwerk für Audiokonferenzen beschrieben.
ms.openlocfilehash: c6820bade333b6672d00e4f52a361280c10c8771
ms.sourcegitcommit: 8f999bd2e20f177c6c6d8b174ededbff43ff5076
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/15/2022
ms.locfileid: "62055665"
---
# <a name="on-network-conferencing-for-audio-conferencing"></a>Netzwerkkonferenzen für Audiokonferenzen

Mit Netzwerkkonferenzen können Organisationen ein- und ausgehende Audiokonferenzanrufe über Direktes Routing an Microsoft-Einwahlnummern senden. Diese Funktion ist nicht dazu gedacht, die Unterstützung von Audiokonferenzen auf Einwahlnummern von Drittanbietern zu erweitern. Netzwerkkonferenzen werden nicht unterstützt, wenn sie verwendet werden, um eingehende Anrufe an den Audiokonferenzdienst über Einwahltelefonnummern von Drittanbietern oder ausgehende Anrufe von Microsoft Audio Conferencing Bridge an das PSTN weiter zu routen.

In diesem Artikel werden die Voraussetzungen und Konfigurationsschritte beschrieben, die erforderlich sind, um On-Network Conferencing für Ihre Organisation zu aktivieren.

> [!IMPORTANT]
> On-network Conferencing must NOT be deployed with any telephony equipment in India.
  
## <a name="prerequisites"></a>Voraussetzungen

Stellen Sie vor dem Konfigurieren von Netzwerkkonferenzen sicher, dass Ihre Organisation die folgenden Voraussetzungen erfüllt:

- Stellen Sie sicher, dass alle Benutzer in Ihrer Organisation, die für Audiokonferenzen aktiviert sind oder aktiviert sind, Teams Für alle Besprechungen verwenden. Das Routing von eingehenden und ausgehenden Audiokonferenzanrufen über Netzwerkkonferenzen wird nur für Teams unterstützt.

- Weisen Sie allen Benutzern, die Eine-Netzwerkkonferenz verwenden werden, Lizenzen für Audiokonferenzen zu.

- Einrichten des Audiokonferenzdiensts Weitere Informationen finden Sie unter [Einrichten von Audiokonferenzen für Microsoft Teams.](set-up-audio-conferencing-in-teams.md)

- Richten Sie Ihren Session Border Controller (SBC) für direktes Routing ein. Weitere Informationen finden Sie unter [Planen von Direct-Routing und](direct-routing-plan.md) Konfigurieren von [Direct-Routing.](direct-routing-configure.md)

  Wenn Sie Direct-Routing nur für Audiokonferenzen einrichten, müssen Sie für Netzwerkkonferenzen nur "Schritt 1: Verbinden Ihr SBC" abschließen.
  
## <a name="enable-the-routing-of-dial-in-calls-to-microsoft-audio-conferencing-through-direct-routing"></a>Aktivieren des Routings von Einwahlanrufen an Microsoft Audio Conferencing über Direct Routing

Wenn Sie Einwahlanrufe Ihrer lokalen Benutzer über Direct Routing an den Audiokonferenzdienst weiterleiten möchten, müssen Sie geeignete Routingregeln für Ihre SBCs und PBXs (Private Branch Exchange) konfigurieren.

Sie müssen die Telefonieausrüstung Ihrer Standorte so konfigurieren, dass Anrufe an eine beliebige Servicenummer der Konferenzbrücke Ihrer Organisation über einen Direct Routing-Trunk weiterleiten.

Sie finden die Leistungsnummern im Teams Admin Center unter **Meetings -> Conferencing Bridges** oder mithilfe des Skype for Business Online PowerShell-Cmdlets Get-CsOnlineDialInConferencingBridge. Weitere Informationen finden Sie in einer Liste der [Audiokonferenznummern in Microsoft Teams.](see-a-list-of-audio-conferencing-numbers-in-teams.md)

> [!NOTE]
> Diese Funktion steht Benutzern mit einer Lizenz für Audiokonferenzen mit Minutenzahl nicht zur Verfügung.

## <a name="enable-the-routing-of-teams-meeting-dial-out-calls-through-direct-routing"></a>Aktivieren des Routings von Teams von Einwahlanrufen in Besprechungen über Direct Routing

Teams Auswählanrufe von Besprechungen werden innerhalb einer Besprechung in Ihrer Organisation zu PSTN-Nummern initiiert, einschließlich Der Anruf-me-at-Anrufe und Anrufe, um neue Teilnehmer zu einer Besprechung zu bringen.

Zum Aktivieren Teams des Routings von Besprechungen über Direktes Routing an Benutzer im Netzwerk müssen Sie eine Routingrichtlinie für Audiokonferenzen mit dem Namen "OnlineAudioConferencingRoutingPolicy" erstellen und zuweisen.

Die Richtlinie OnlineAudioConferencingRoutingPolicy entspricht der CsOnlineVoiceRoutingPolicy für 1:1 PSTN-Anrufe über Direct Routing. Die OnlineAudioConferencingRoutingPolicy-Richtlinie kann mithilfe der folgenden Cmdlets verwaltet werden:

-   New-CsOnlineAudioConferencingRoutingPolicy
- Set-CsOnlineAudioConferencingRoutingPolicy
- Get-CsOnlineAudioConferencingRoutingPolicy
- Grant-CsOnlineAudioConferencingRoutingPolicy
- Remove-CsOnlineAudioConferencingRoutingPolicy

Weitere Informationen zum Routing für Direct-Routing finden Sie unter [Konfigurieren von Voice Routing für Direct-Routing.](direct-routing-voice-routing.md)

Um das Routing von Anrufanrufen für Besprechungen über Direct Routing zu ermöglichen, müssen Sie:

- Konfigurieren von Routingrichtlinien für Audiokonferenzen
- Konfigurieren des Routings für die Telefoniegeräte Ihrer Organisation
- (Optional) Konfigurieren eines Wählplans

Anrufanrufe aus Teams Besprechungen werden von der Standarddienstnummer in der Konferenzbrücke angestellt. Weitere Informationen zur Standarddienstnummer Ihrer Audiokonferenzbrücke finden Sie unter Ändern der Telefonnummern für Ihre [Audiokonferenzbrücke.](change-the-phone-numbers-on-your-audio-conferencing-bridge.md)

### <a name="configure-audio-conferencing-routing-policies"></a>Konfigurieren von Routingrichtlinien für Audiokonferenzen

Die Routingrichtlinie OnlineAudioConferencingRoutingPolicy für Audiokonferenzen bestimmt, welche Anrufe aus einer Besprechung an Direct Routing-Trunks geroutet werden. Wenn Sie mit der CsOnlineVoiceRoutingPolicy-Richtlinie vertraut sind, funktioniert diese Richtlinie auf sehr ähnliche Weise.

Die folgenden Schritte sind zum Einrichten von Routingrichtlinien für Audiokonferenzen erforderlich:

1. Erstellen von PSTN-Nutzungen
1. Konfigurieren von Sprachrouten
1. Erstellen von Richtlinien für das Routing von Audiokonferenz-Voice
1. Zuweisen einer Richtlinie zu Benutzern

#### <a name="create-pstn-usages"></a>Erstellen von PSTN-Nutzungen

PSTN-Nutzungen sind Sammlungen von Sprachrouten. Wenn ein Ausgehendanruf aus der Besprechung eines bestimmten Organisators initiiert wird, werden Sprachrouten verwendet, um den Routingpfad des Anrufs basierend auf den PSTN-Nutzungen zu ermitteln, die dem Benutzer über die Sprachroutingrichtlinie des Benutzers zugeordnet sind.

Sie können eine PSTN-Verwendung mithilfe des Cmdlets "Set-CsOnlinePstnUsage" erstellen. Beispiel:

```powershell
Set-CsOnlinePstnUsage -Identity Global -Usage @{Add="US and Canada"}
```

#### <a name="configure-voice-routes"></a>Konfigurieren von Sprachrouten

Sprachrouten bestimmen das PSTN-Gateway, das für die Route eines Anrufs verwendet werden soll, basierend auf der Telefonnummer, die von einer Besprechung aus Teams wird. Sprachrouten bestimmen das PSTN-Gateway, das zum Routen eines bestimmten Anrufs verwendet werden soll, indem die von einer Teams-Besprechung gewählte Telefonnummer mit einem regex-Muster abgestimmt wird. Beim Erstellen einer Sprachroute muss die Route einer oder mehreren PSTN-Nutzungen zugeordnet sein.

Mit dem Cmdlet "New-CsOnlineVoiceRoute" können Sie eine Sprachroute erstellen und die regex- und Gateways definieren, die der Sprachroute zugeordnet werden sollen. Beispiel:

```powershell
New-CsOnlineVoiceRoute -Identity "Redmond 1" -NumberPattern "^\+1(425|206)(\d{7})$" -OnlinePstnGatewayList sbc1.contoso.biz, sbc2.contoso.biz -Priority 1 -OnlinePstnUsages "US and Canada"
```

#### <a name="create-audio-conferencing-voice-routing-policies"></a>Erstellen von Richtlinien für das Routing von Audiokonferenz-Voice

Richtlinien für die Sprachroutingrichtlinien für Audiokonferenzen bestimmen die möglichen Routen, die zum Weiterleiten eines Anrufs verwendet werden können, der von den Besprechungen eines Organisators stammt, basierend auf der Zieltelefonnummer des Ausgehenden Anrufs. Richtlinien für das Routing von Audiokonferenz-Voice werden einer oder mehreren PSTN-Nutzungen zugeordnet, die wiederum die möglichen Routen bestimmen, die für die Einwahlanrufe von Besprechungen der Organisatoren verwendet werden sollen, die der Richtlinie zugeordnet sind.

Sie können eine Sprachroutingrichtlinie für Audiokonferenzen mithilfe des Cmdlets "New- CsOnlineAudioConferencingRoutingPolicy" erstellen. Beispiel:

```powershell
New-CsOnlineAudioConferencingRoutingPolicy "Policy 1" -OnlinePstnUsages "US and Canada"
```

Nachdem die Richtlinie einem Benutzer zugewiesen wurde und wenn ein Anruf beim Wählen einer Besprechung von einer der Benutzerbesprechungen initiiert wird, werden die Sprachrouten in den PSTN-Nutzungen, die dem Organisator über die Sprachroutingrichtlinie des Benutzers zugeordnet sind, ausgewertet. Wenn das Ziel des Anrufziels für ein Anwählen der Besprechung einem regex in einer der dem Organisator zugeordneten Sprachrouten entspricht, wird der Anruf vom Organisator an das pstN-Gateway geroutet, das in der Sprachroute definiert ist. Wenn das Ziel des Anrufziels für den Einwahlanruf einer Besprechung keinem der dem Organisator zugeordneten Sprachrouten zu entsprechen, wird der Anruf aus der Besprechung von Microsoft geroutet.

#### <a name="assign-a-policy-to-your-users"></a>Zuweisen einer Richtlinie zu Benutzern

Nachdem die Routingrichtlinien für Audiokonferenzen definiert wurden, können Sie sie nun Benutzern zuweisen. Nachdem ihnen Richtlinien zugewiesen wurden, werden die Anrufanrufe für Besprechungen ausgewertet, um ihren Routingpfad zu bestimmen. Routingrichtlinien für Audiokonferenzen werden immer basierend auf dem Organisator der Besprechung unabhängig vom Benutzer in der Besprechung ausgewertet, der einen Anruf vom Organisator initiiert.

Sie können einem Benutzer eine Sprachroutingrichtlinie für Audiokonferenzen zuweisen, indem Sie das Cmdlet "Grant-CsOnlineAudioConferencingRoutingPolicy" verwenden. Zum Beispiel: 

```powershell
Grant-CsOnlineAudioConferencingRoutingPolicy -Identity "<User Identity>" -PolicyName "Policy 1”
```

### <a name="configure-routing-on-the-telephony-equipment-of-your-organization"></a>Konfigurieren des Routings auf den Telefoniegeräten Ihrer Organisation

Auf der Telefonieausrüstung Ihrer Organisation müssen Sie sicherstellen, dass Anrufe, die über Direct Routing geroutet werden, an das vorgesehene Ziel im Netzwerk geroutet werden.

### <a name="optional-configure-a-dial-plan"></a>(Optional) Konfigurieren eines Wählplans

Bei einem Wählplan handelt es sich um eine Reihe von Normalisierungsregeln, mit der die von einem einzelnen Benutzer gewählten Telefonnummern zum Zweck der Anrufautorisierung und Anrufrouting in ein alternatives Format (normalerweise E.164) übersetzt werden.

Standardmäßig können Teams PSTN-Nummern im E.164-Format wählen, d. h. + \<country code\> \<number\> . Wählpläne können jedoch verwendet werden, um Benutzern das Wählen von Telefonnummern in anderen Formaten zu ermöglichen, z. B. vierstellige Erweiterungen.

Wenn Sie durchwahlbasiertes Wählen über On-Network-Konferenzen aktivieren möchten, können Sie Wählpläne so einrichten, dass das Durchwahlmuster den Telefonnummernbereichen der Telefonnummern Ihrer Organisation entspricht. Informationen zum Einrichten von Wählplänen finden Sie unter [Erstellen und Verwalten von Wählplänen.](create-and-manage-dial-plans.md)

## <a name="related-topics"></a>Verwandte Themen
