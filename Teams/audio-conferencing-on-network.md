---
title: Netzwerkkonferenzen für Audiokonferenzen
ms.author: crowe
author: CarolynRowe
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
localization_priority: Normal
f1.keywords:
- NOCSH
ms.custom:
- Audio Conferencing
description: Im Folgenden werden die Open Preview-Funktionen für On-Network für Audiokonferenzen beschrieben.
ms.openlocfilehash: d6df81cc077c69fdeb4246d682797d2ebb26b875
ms.sourcegitcommit: 950387da2a2c094b7580bcf81ae5d8b6dfba0d6b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2021
ms.locfileid: "51637837"
---
# <a name="open-preview-of-on-network-conferencing-for-audio-conferencing"></a>Open Preview of On-network Conferencing for Audio Conferencing

Die Open Preview of On-network Conferencing ist für alle Kunden verfügbar. Mithilfe von Netzwerkkonferenzen können Organisationen eingehende und ausgehende Audiokonferenzanrufe über Direct Routing an Microsoft-Einwahlnummern senden. Diese Funktion dient nicht dazu, die Unterstützung von Audiokonferenzen auf Einwahlnummern von Drittanbietern zu erweitern. Netzwerkkonferenzen werden nicht unterstützt, wenn sie verwendet werden, um eingehende Anrufe an den Audiokonferenzdienst über Einwahlnummern von Drittanbietern oder ausgehende Anrufe über die Microsoft Audio Conferencing Bridge an das PSTN weiter zu senden. 

In diesem Artikel werden die Voraussetzungen und Konfigurationsschritte beschrieben, die zum Aktivieren von Netzwerkkonferenzen für Ihre Organisation erforderlich sind.

> [!IMPORTANT]
> Netzwerkkonferenzen dürfen nicht mit Telefoniegeräten in Indien bereitgestellt werden.
  
## <a name="prerequisites"></a>Voraussetzungen

Stellen Sie vor dem Konfigurieren von Netzwerkkonferenzen sicher, dass Ihre Organisation die folgenden Voraussetzungen erfüllt: 

- Stellen Sie sicher, dass alle Benutzer in Ihrer Organisation, die für Audiokonferenzen aktiviert oder aktiviert sind, Teams für alle Besprechungen verwenden. Das Routing von eingehenden und ausgehenden Audiokonferenzanrufen über Netzwerkkonferenzen wird nur für Teams-Besprechungen unterstützt.

- Weisen Sie allen Benutzern, die In-Network Conferencing verwenden, Lizenzen für Audiokonferenzen zu.

- Richten Sie den Audiokonferenzdienst ein. Weitere Informationen finden Sie unter [Einrichten von Audiokonferenzen für Microsoft Teams.](set-up-audio-conferencing-in-teams.md)

- Richten Sie Ihren Session Border Controller (SBC) für direktes Routing ein. Weitere Informationen finden Sie unter [Planen von Direct Routing und](direct-routing-plan.md) Konfigurieren von Direct [Routing](direct-routing-configure.md). 

  Wenn Sie Direct Routing nur für Audiokonferenzen einrichten, müssen Sie nur "Schritt 1: Verbinden Ihres SBC" für Netzwerkkonferenzen abschließen.
  
## <a name="enable-the-routing-of-dial-in-calls-to-microsoft-audio-conferencing-through-direct-routing"></a>Aktivieren des Routings von Einwahlanrufen an Microsoft Audio Conferencing über Direct Routing 

Zum Weiterleiten von Einwahlanrufen ihrer lokalen Benutzer an den Audiokonferenzdienst über Direct Routing müssen Sie geeignete Routingregeln für Ihre SBCs und Private Branch Exchange(s) (PBXs) konfigurieren.

Sie müssen die Telefoniegeräte Ihrer Websites so konfigurieren, dass Anrufe an eine beliebige Servicenummer der Konferenzbrücke Ihrer Organisation über einen Direct Routing-Trunk weiterleiten.

Sie finden die Servicenummern im Teams Admin Center unter **Besprechungen -> Conferencing Bridges** oder über das Skype for Business Online PowerShell-Cmdlet Get-CsOnlineDialInConferencingBridge. Weitere Informationen finden Sie in einer Liste der Nummern für [Audiokonferenzen in Microsoft Teams.](see-a-list-of-audio-conferencing-numbers-in-teams.md)

> [!NOTE]
> Dieses Feature steht Benutzern mit der Lizenz für Audiokonferenzen mit Minutenzahl nicht zur Verfügung.

## <a name="enable-the-routing-of-teams-meeting-dial-out-calls-through-direct-routing"></a>Aktivieren des Routings von Auswahlanrufen für Teams-Besprechungen über Direct Routing

Auswählanrufe für Teams-Besprechungen werden innerhalb einer Besprechung in Ihrer Organisation an PSTN-Nummern initiiert, einschließlich Anrufe bei Anrufen und Anrufen, um neue Teilnehmer zu einer Besprechung zu bringen. 

Um das Routing von Teams-Besprechungen über Direct Routing für Benutzer im Netzwerk zu aktivieren, müssen Sie eine Routingrichtlinie für Audiokonferenzen mit dem Namen "OnlineAudioConferencingRoutingPolicy" erstellen und zuweisen. 

Die OnlineAudioConferencingRoutingPolicy-Richtlinie entspricht der CsOnlineVoiceRoutingPolicy für 1:1-PSTN-Anrufe über Direct Routing. Die OnlineAudioConferencingRoutingPolicy-Richtlinie kann mithilfe der folgenden Cmdlets verwaltet werden:

-   New-CsOnlineAudioConferencingRoutingPolicy
- Set-CsOnlineAudioConferencingRoutingPolicy
- Get-CsOnlineAudioConferencingRoutingPolicy
- Grant-CsOnlineAudioConferencingRoutingPolicy
- Remove-CsOnlineAudioConferencingRoutingPolicy

Weitere Informationen zum Routing für Direct Routing finden Sie unter [Konfigurieren von Voice routing für Direct Routing](direct-routing-voice-routing.md).


Um das Routing von Besprechungswählanrufen über Direct Routing zu aktivieren, müssen Sie: 

- Konfigurieren von Routingrichtlinien für Audiokonferenzen
- Konfigurieren des Routings auf den Telefoniegeräten Ihrer Organisation
- (Optional) Konfigurieren eines Wählplans

Einwahlanrufe aus Teams-Besprechungen werden über die Standarddienstnummer auf der Konferenzbrücke angezeigt. Weitere Informationen zur Standarddienstnummer Ihrer Audiokonferenzbrücke finden Sie unter Ändern der Telefonnummern auf der [Audiokonferenzbrücke.](change-the-phone-numbers-on-your-audio-conferencing-bridge.md)

### <a name="configure-audio-conferencing-routing-policies"></a>Konfigurieren von Routingrichtlinien für Audiokonferenzen

Die Routingrichtlinie für Audiokonferenzen OnlineAudioConferencingRoutingPolicy bestimmt, welche Besprechungsauswahlanrufe an Direct Routing-Trunks geroutet werden. Wenn Sie mit der CsOnlineVoiceRoutingPolicy-Richtlinie vertraut sind, funktioniert diese Richtlinie auf sehr ähnliche Weise.

Zum Einrichten von Routingrichtlinien für Audiokonferenzen sind die folgenden Schritte erforderlich:
1.  Erstellen von PSTN-Verwendungen
2.  Konfigurieren von Sprachrouten
3.  Erstellen von Audiokonferenz-Voiceroutingrichtlinien
4.  Zuweisen einer Richtlinie zu Ihren Benutzern


#### <a name="create-pstn-usages"></a>Erstellen von PSTN-Verwendungen

PSTN-Nutzungen sind Sammlungen von Sprachrouten. Wenn ein Auswahlanruf von der Besprechung eines bestimmten Organisators initiiert wird, werden Sprachrouten verwendet, um den Routingpfad des Anrufs basierend auf den PSTN-Nutzungen zu bestimmen, die dem Benutzer über die Voice routing policy des Benutzers zugeordnet sind.

Sie können eine PSTN-Verwendung mithilfe des Cmdlets "Set-CsOnlinePstnUsage" erstellen. Beispiel:

```powershell
Set-CsOnlinePstnUsage -Identity Global -Usage @{Add="US and Canada"}
```

#### <a name="configure-voice-routes"></a>Konfigurieren von Sprachrouten

Sprachrouten bestimmen das PSTN-Gateway, das verwendet werden soll, um einen Anruf basierend auf der Telefonnummer weiter zu führen, die von einer Teams-Besprechung gewählt wird. Sprachrouten bestimmen das PSTN-Gateway, das zum Routen eines bestimmten Anrufs verwendet werden soll, indem die telefonnummer, die aus einer Teams-Besprechung mit einem regex-Muster gewählt wurde, übereinstimmen. Beim Erstellen einer Sprachroute muss die Route einer oder mehreren PSTN-Nutzungen zugeordnet sein.

Sie können eine Sprachroute erstellen und die Regex- und Gateways definieren, die der Sprachroute zugeordnet werden sollen, indem Sie das Cmdlet "New-CsOnlineVoiceRoute" verwenden. Beispiel:

```powershell
New-CsOnlineVoiceRoute -Identity "Redmond 1" -NumberPattern "^\+1(425|206)(\d{7})$" -OnlinePstnGatewayList sbc1.contoso.biz, sbc2.contoso.biz -Priority 1 -OnlinePstnUsages "US and Canada"
```

#### <a name="create-audio-conferencing-voice-routing-policies"></a>Erstellen von Audiokonferenz-Voiceroutingrichtlinien

Audiokonferenz-Voiceroutingrichtlinien bestimmen die möglichen Routen, die zum Weiterleiten eines Anrufs verwendet werden können, der aus den Besprechungen eines Organisators stammt, basierend auf der Zieltelefonnummer des Einwahlanrufs der Besprechung. Audiokonferenz voice routing policies are associated to one or more PSTN usages, which s s turn, determine the possible routes that will be attempted to be used for the meeting dial-out calls of the organizers associated to the policy.

Sie können eine Audiokonferenz-Voiceroutingrichtlinie mithilfe des Cmdlets "New- CsOnlineAudioConferencingRoutingPolicy" erstellen. Beispiel:

```powershell
New-CsOnlineAudioConferencingRoutingPolicy "Policy 1" -OnlinePstnUsages "US and Canada"
```

Nachdem die Richtlinie einem Benutzer zugewiesen wurde und wenn ein Besprechungswählanruf aus einer der Besprechungen des Benutzers initiiert wird, werden die Sprachrouten in den PSTN-Nutzungen ausgewertet, die dem Organisator über die Voiceroutingrichtlinie des Benutzers zugeordnet sind. Wenn das Ziel des Besprechungswählziels einem Regex in einer der Sprachrouten entspricht, die dem Organisator zugeordnet sind, wird der Besprechungsauswahlanruf an das in der Sprachroute definierte PSTN-Gateway geroutet. Wenn das Ziel des Besprechungswählziels keinem der dem Organisator zugeordneten Sprachrouten zustimme, wird der Besprechungswählanruf von Microsoft umgeroutet.

#### <a name="assign-a-policy-to-your-users"></a>Zuweisen einer Richtlinie zu Ihren Benutzern

Nachdem die Routingrichtlinien für Audiokonferenzen definiert wurden, können Sie sie jetzt Benutzern zuweisen. Nachdem ihnen Richtlinien zugewiesen wurden, werden die Besprechungswählanrufe ausgewertet, um deren Routingpfad zu ermitteln. Routingrichtlinien für Audiokonferenzen werden immer basierend auf dem Organisator der Besprechung unabhängig vom Benutzer in der Besprechung ausgewertet, der einen Besprechungswählanruf initiiert.

Sie können einem Benutzer eine Audiokonferenz-Voiceroutingrichtlinie zuweisen, indem Sie das Cmdlet "Grant-CsOnlineAudioConferencingRoutingPolicy" verwenden. Beispiel:

```powershell
Grant-CsOnlineAudioConferencingRoutingPolicy -Identity "<User Identity>" -PolicyName "Policy 1”
```


### <a name="configure-routing-on-the-telephony-equipment-of-your-organization"></a>Konfigurieren des Routings auf den Telefoniegeräten Ihrer Organisation

Auf den Telefoniegeräten Ihrer Organisation müssen Sie sicherstellen, dass die über Direct Routing gerouteten Besprechungswählanrufe an das beabsichtigte Ziel im Netzwerk geroutet werden.


### <a name="optional-configure-a-dial-plan"></a>(Optional) Konfigurieren eines Wählplans

Ein Wählplan ist eine Reihe von Normalisierungsregeln, die wählte Telefonnummern eines einzelnen Benutzers zu Zwecken der Anrufautorisierung und Anrufrouting in ein alternatives Format (normalerweise E.164) übersetzen.

Standardmäßig können Teams-Benutzer pstn-Nummern im E.164-Format, d. h. +, \<country code\> \<number\> auswählen. Wählpläne können jedoch verwendet werden, um Benutzern das Wählen von Telefonnummern in anderen Formaten zu ermöglichen, z. B. vierstellige Erweiterungen.

Wenn Sie die erweiterungsbasierte Wählverbindung über Netzwerkkonferenzen aktivieren möchten, können Sie Wählpläne so einrichten, dass das Durchwahlmuster den Telefonnummernbereichen der Telefonnummer Ihrer Organisation entspricht. Informationen zum Einrichten von Wählplänen finden Sie unter [Erstellen und Verwalten von Wählplänen.](create-and-manage-dial-plans.md)


## <a name="known-issues-in-open-preview"></a>Bekannte Probleme in Der Vorschau öffnen

Im Folgenden finden Sie eine Liste der bekannten Probleme, die derzeit in der Open Preview-Version von On-Network-Konferenzen auftreten. Microsoft arbeitet an der Lösung dieser Probleme.

| Problem | Problemumgehung |
| :--- | :--- |
| Einwahlanrufe mit anonymen/ausgeblendeten Anrufer-IDs, die über Netzwerkkonferenzen geroutet werden, können nicht mit der Besprechung verbunden werden. | Legen Sie nach Möglichkeit eine Konfiguration in Ihrer PBX oder SBC so vor, dass immer eine Anrufer-ID für Anrufe gesendet wird, die über Netzwerkkonferenzen geroutet werden.|
| In einigen Fällen wird die Begrüßungsnachricht, die Benutzern bei der Einwahl beim Dienst ("Willkommen beim Audiokonferenzdienst...") angezeigt wird, abgeschnitten, und die Benutzer hören nicht das Wort "Willkommen".| Derzeit gibt es keine Problemumgehungen für dieses Problem. |




## <a name="related-topics"></a>Verwandte Themen


