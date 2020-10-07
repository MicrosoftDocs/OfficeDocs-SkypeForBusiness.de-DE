---
title: Netzwerkkonferenz für Audiokonferenzen
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
localization_priority: Normal
f1.keywords:
- NOCSH
ms.custom:
- Audio Conferencing
description: Im folgenden wird die Funktion zum Öffnen der Vorschau für das Netzwerk für Audiokonferenzen beschrieben.
ms.openlocfilehash: 38b8be382ccd1b80002688cdb7fce9aa166efc2c
ms.sourcegitcommit: f9daef3213a305676127cf5140af907e3b96d046
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/07/2020
ms.locfileid: "48369180"
---
# <a name="open-preview-of-on-network-conferencing-for-audio-conferencing"></a>Öffnen der Vorschau von Netzwerk Konferenzen für Audiokonferenzen

Die offene Vorschau auf Netzwerk Konferenzen steht allen Kunden zur Verfügung. Bei Netzwerk Konferenzen können Organisationen eingehende und ausgehende Audiokonferenz-Anrufe an Microsoft-Einwahlnummern über direkte Weiterleitung senden. Diese Funktion ist nicht dazu vorgesehen, die Unterstützung von Audiokonferenzen auf Einwahlnummern von Drittanbietern zu erweitern. Netzwerk Konferenzen werden nicht unterstützt, wenn Sie zum Weiterleiten eingehender Anrufe an den Audio-Konferenzdienst über Einwahlnummern von Drittanbietern verwendet werden.

In diesem Artikel werden die Voraussetzungen und Konfigurationsschritte beschrieben, die zum Aktivieren von Netzwerk Konferenzen für Ihre Organisation erforderlich sind.

> [!IMPORTANT]
> Netzwerk Konferenzen dürfen nicht mit beliebigen Telefongeräten in Indien bereitgestellt werden.
  
## <a name="prerequisites"></a>Voraussetzungen

Bevor Sie Netzwerk Konferenzen konfigurieren, müssen Sie sicherstellen, dass Ihre Organisation die folgenden Voraussetzungen erfüllt: 

- Stellen Sie sicher, dass alle Benutzer in Ihrer Organisation, die für Audiokonferenzen aktiviert oder aktiviert werden, nur im Modus "nur in Teams" aufgeführt sind. Die Weiterleitung von eingehenden und ausgehenden Audiokonferenz-anrufen über Netzwerk Konferenzen wird nur für Teams-Besprechungen unterstützt.

- Weisen Sie allen Benutzern, die eine Netzwerkkonferenz verwenden werden, Audiokonferenz-Lizenzen zu.

- Einrichten des Audio-Konferenz Diensts Weitere Informationen finden Sie unter [Einrichten von Audiokonferenzen für Microsoft Teams](set-up-audio-conferencing-in-teams.md).

- Richten Sie Ihren Session Border Controller (SBC) für die direkte Weiterleitung ein. Weitere Informationen finden Sie unter [Planen des direkten Routings](direct-routing-plan.md) und [Konfigurieren des direkten Routings](direct-routing-configure.md). 

  Wenn Sie die direkte Weiterleitung nur für Audiokonferenzen einrichten, müssen Sie nur "Schritt 1: Verbinden Ihres SBC" für Netzwerk Konferenzen ausführen.
  
## <a name="enable-the-routing-of-dial-in-calls-to-microsoft-audio-conferencing-through-direct-routing"></a>Aktivieren des Routings von Einwahl Anrufen an Microsoft-Audiokonferenzen über direktes Routing 

Wenn Sie Einwahl Anrufe, die von Ihren lokalen Benutzern durch direkte Weiterleitung an den Audiokonferenzdienst durchgeführt werden, weiterleiten möchten, müssen Sie geeignete Routingregeln für Ihre SBCS und Private Branch Exchange (s) (PBX) konfigurieren.

Sie müssen die Telefonanlage ihrer Websites so konfigurieren, dass Anrufe an eine beliebige Dienstnummer der Konferenzbrücke Ihrer Organisation über einen direkten Routing-Stamm weitergeleitet werden.

Sie finden die Dienstnummern im Team Admin Center unter **Besprechungen – > Konferenz Brücken** oder mithilfe des PowerShell-Cmdlets "CsOnlineDialInConferencingBridge" von Skype for Business Online. Weitere Informationen finden Sie in der Liste der [Audiokonferenz-Nummern in Microsoft Teams](see-a-list-of-audio-conferencing-numbers-in-teams.md).

> [!NOTE]
> Dieses Feature steht Benutzern mit der Lizenz für Pay-per-Minute-Audio-Konferenzen nicht zur Verfügung.

## <a name="enable-the-routing-of-teams-meeting-dial-out-calls-through-direct-routing"></a>Aktivieren des Routings von Teams für die Auswahl von Anruf Gesprächen über direktes Routing

In einer Besprechung in Ihrer Organisation werden Anrufe von Teams für die Anruf Besprechung an PSTN-Nummern initiiert, einschließlich Anrufe und Anrufe, um neue Teilnehmer zu einer Besprechung zu führen. 

Sie müssen eine Richtlinie für die Audiokonferenz-Routing Richtlinie mit dem Namen "OnlineAudioConferencingRoutingPolicy" erstellen und zuweisen, um Teams das Einwahl Routing über das direkte Routing zu ermöglichen. 

Die OnlineAudioConferencingRoutingPolicy-Richtlinie entspricht den CsOnlineVoiceRoutingPolicy für 1:1-PSTN-Anrufe über direkte Weiterleitung. Die OnlineAudioConferencingRoutingPolicy-Richtlinie kann mithilfe der folgenden Cmdlets verwaltet werden:

-   Neu – CsOnlineAudioConferencingRoutingPolicy
- Satz-CsOnlineAudioConferencingRoutingPolicy
- Get-CsOnlineAudioConferencingRoutingPolicy
- Grant-CsOnlineAudioConferencingRoutingPolicy
- Remove-CsOnlineAudioConferencingRoutingPolicy

Weitere Informationen zum Routing für das direkte Routing finden Sie unter [Konfigurieren des VoIP-Routings für das direkte Routing](direct-routing-voice-routing.md).


Um das Routing von Anruf Gesprächen über direktes Routing zu aktivieren, müssen Sie folgende Schritte ausführen: 

- Konfigurieren von Richtlinien für die Audiokonferenz-Routing
- Konfigurieren des Routings für die Telefonieanlagen Ihrer Organisation
- Optional Konfigurieren eines Wählplans

Anrufe aus Teams-Besprechungen werden von der standardmäßigen Dienstnummer auf der Konferenzbrücke abgewählt. Weitere Informationen zur Standarddienst Nummer Ihrer Audiokonferenz-Brücke finden Sie unter [Ändern der Telefonnummern auf der Audiokonferenz-Brücke](change-the-phone-numbers-on-your-audio-conferencing-bridge.md).

### <a name="configure-audio-conferencing-routing-policies"></a>Konfigurieren von Richtlinien für die Audiokonferenz-Routing

Die Richtlinie für die OnlineAudioConferencingRoutingPolicy von Audiokonferenzen bestimmt, welche Besprechungs-Dial-Out-Anrufe an Direct Routing-Stämme weitergeleitet werden. Wenn Sie mit der CsOnlineVoiceRoutingPolicy-Richtlinie vertraut sind, funktioniert diese Richtlinie auf eine sehr ähnliche Weise.

Die folgenden Schritte sind erforderlich, um Richtlinien für die Audiokonferenz-Routing Einrichtung einzurichten:
1.  Erstellen von PSTN-Nutzungen
2.  Konfigurieren von VoIP-Routen
3.  Erstellen von VoIP-Routing Richtlinien für Audiokonferenzen
4.  Zuweisen einer Richtlinie zu Ihren Benutzern


#### <a name="create-pstn-usages"></a>Erstellen von PSTN-Nutzungen

PSTN-Nutzungen sind Sammlungen von VoIP-Routen. Wenn ein Auswähl-Anruf aus der Besprechung eines bestimmten Organisators initiiert wird, werden VoIP-Routen verwendet, um den Routingpfad des Anrufs anhand der PSTN-Nutzungen zu ermitteln, die dem Benutzer über die VoIP-Routing Richtlinie des Benutzers zugeordnet sind.

Sie können eine PSTN-Nutzung mithilfe des Cmdlets "festgelegte CsOnlinePstnUsage" erstellen. Beispiel:

```
Set-CsOnlinePstnUsage -Identity Global -Usage @{Add="US and Canada"}
```

#### <a name="configure-voice-routes"></a>Konfigurieren von VoIP-Routen

VoIP-Routen bestimmen das PSTN-Gateway, das zum Weiterleiten eines Anrufs basierend auf der Telefonnummer verwendet werden soll, die von einer Teambesprechung gewählt wird. VoIP-Routen ermitteln das PSTN-Gateway, das zum Weiterleiten eines bestimmten Anrufs verwendet werden soll, indem Sie die von einer Teambesprechung gewählte Telefonnummer mit einem Regex-Muster vergleichen. Beim Erstellen einer VoIP-Route muss die Route mindestens einer PSTN-Nutzung zugeordnet sein.

Mithilfe des Cmdlets "New-CsOnlineVoiceRoute" können Sie eine VoIP-Route erstellen und die Regex und Gateways definieren, die mit der VoIP-Route verknüpft werden sollen. Beispiel:

```
New-CsOnlineVoiceRoute -Identity "Redmond 1" -NumberPattern "^\+1(425|206)(\d{7})$" -OnlinePstnGatewayList sbc1.contoso.biz, sbc2.contoso.biz -Priority 1 -OnlinePstnUsages "US and Canada"
```

#### <a name="create-audio-conferencing-voice-routing-policies"></a>Erstellen von VoIP-Routing Richtlinien für Audiokonferenzen

Audiokonferenz-VoIP-Routing Richtlinien ermitteln die möglichen Routen, die verwendet werden können, um einen Anruf aus den Besprechungen eines Organisators basierend auf der Zieltelefonnummer des Anrufs für die Besprechung zu leiten. Audiokonferenz-VoIP-Routing Richtlinien sind einer oder mehreren PSTN-Nutzungen zugeordnet, die wiederum die möglichen Routen ermitteln, die für die Besprechung von Wähl anrufen der Organisatoren verwendet werden, die der Richtlinie zugeordnet sind.

Mit dem Cmdlet "New-CsOnlineAudioConferencingRoutingPolicy" können Sie eine VoIP-Routing Richtlinie für Audiokonferenzen erstellen. Beispiel:

```
New-CsOnlineAudioConferencingRoutingPolicy "Policy 1" -OnlinePstnUsages "US and Canada"
```

Nachdem die Richtlinie einem Benutzer zugewiesen wurde und ein Anruf aus einer der Besprechungen des Benutzers initiiert wird, werden die VoIP-Routen in den PSTN-Nutzungen, die dem Organisator über die VoIP-Routing Richtlinie des Benutzers zugeordnet sind, ausgewertet. Wenn das Ziel des Anrufs für die Besprechungs Auswahl mit einem Regex in einer der VoIP-Routen übereinstimmt, die dem Organisator zugeordnet sind, wird der Anruf zur Anruf Abwahl an das PSTN-Gateway weitergeleitet, das in der VoIP-Route definiert ist. Wenn das Anruf Ziel des Besprechungs Anrufs nicht mit den VoIP-Routen übereinstimmt, die dem Organisator zugeordnet sind, wird der Anruf zur Anruf Abwahl von Microsoft weitergeleitet.

#### <a name="assign-a-policy-to-your-users"></a>Zuweisen einer Richtlinie zu Ihren Benutzern

Nachdem Sie die Richtlinien für die Audiokonferenz-Routing definiert haben, können Sie Sie nun Benutzern zuweisen. Nachdem ihnen Richtlinien zugewiesen wurden, werden die Anruf Abwahlen für Besprechungen ausgewertet, um deren Routingpfad zu ermitteln. Richtlinien für die Audiokonferenz-Routing werden immer basierend auf dem Organisator der Besprechung ausgewertet, unabhängig vom Benutzer in der Besprechung, der einen Anruf zur Anruf Besprechung initiiert.

Sie können einem Benutzer mithilfe des Cmdlets "Grant-CsOnlineAudioConferencingRoutingPolicy" eine VoIP-Routing Richtlinie für Audiokonferenzen zuweisen. Beispiel:

```
Grant-CsOnlineAudioConferencingRoutingPolicy -Identity "<User Identity>" -PolicyName "Policy 1”
```


### <a name="configure-routing-on-the-telephony-equipment-of-your-organization"></a>Konfigurieren des Routings für die Telefonieanlagen Ihrer Organisation

Auf der Telefonieanlage Ihrer Organisation müssen Sie sicherstellen, dass die durch direkte Weiterleitung geleiteten Wähl Anrufe an das vorgesehene Ziel weitergeleitet werden.


### <a name="optional-configure-a-dial-plan"></a>Optional Konfigurieren eines Wählplans

Bei einem Wählplan handelt es sich um eine Reihe von Normalisierungsregeln, die gewählte Telefonnummern von einem einzelnen Benutzer in ein alternatives Format (in der Regel E. 164) übersetzen, um eine Anruf Autorisierung und ein Anrufrouting zu verwenden.

Standardmäßig können Benutzer von Teams im E. 164-Format, also +, zu PSTN-Nummern wählen \<country code\> \<number\> . Wählpläne können jedoch verwendet werden, um Benutzern die Wahl von Telefonnummern in anderen Formaten zu ermöglichen, beispielsweise vierstellige Durchwahlnummern.

Wenn Sie das Erweiterungs basierte wählen über Netzwerk Konferenzen aktivieren möchten, können Sie die Wählpläne so einrichten, dass Sie mit dem Wählmuster für Durchwahlnummern der Rufnummernbereiche der Telefonnummer Ihrer Organisation übereinstimmen. Informationen zum Einrichten von Wählplänen finden Sie unter [Erstellen und Verwalten von Wähl](create-and-manage-dial-plans.md)Plänen.


## <a name="known-issues-in-open-preview"></a>Bekannte Probleme in der geöffneten Vorschau

Im folgenden finden Sie eine Liste bekannter Probleme, die derzeit in der Open Preview-Version von Netzwerk Konferenzen vorhanden sind. Microsoft arbeitet an der Behebung dieser Probleme.

| Problem | Workaround |
| :--- | :--- |
| Einwahl Anrufe mit anonymen/versteckten Rufnummern Anzeigern, die über Netzwerk Konferenzen weitergeleitet werden, können nicht mit der Besprechung verbunden werden. | Wenn möglich, legen Sie eine Konfiguration in Ihrer Telefonanlage oder SBC fest, um immer eine Rufnummernanzeige für Anrufe zu senden, die über Netzwerk Konferenzen weitergeleitet werden.|
| In einigen Fällen wird die Willkommensnachricht, die den Benutzern beim Einwählen in den Dienst ("Willkommen beim Audiokonferenzdienst...") abgespielt wird, abgeschnitten, und die Benutzer hören nicht das "Willkommen"-Wort.| Zurzeit gibt es keine Problemumgehungen für dieses Problem. |




## <a name="related-topics"></a>Verwandte Themen


