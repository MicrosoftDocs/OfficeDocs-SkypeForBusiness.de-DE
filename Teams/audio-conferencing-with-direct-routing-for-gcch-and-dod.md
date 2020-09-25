---
title: Audiokonferenzen mit Direct Routing, GCCH und DoD
author: LanaChin
ms.author: v-lanac
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.collection:
- M365-voice
- M365-collaboration
search.appverid: MET150
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
f1.keywords:
- NOCSH
localization_priority: Normal
description: Der Administrator kann sich mit der Verwendung von Audiokonferenzen in GCCH-und DoD-Umgebungen vertraut machen.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 34fcb84ee0e5126188f47a4ccc231c04ffd093b2
ms.sourcegitcommit: 8924cd77923ca321de72edc3fed04425a4b13044
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "48262492"
---
# <a name="audio-conferencing-with-direct-routing-for-gcc-high-and-dod"></a>Audiokonferenzen mit direktem Routing für GCC High und DoD

Audiokonferenz mit direktem Routing für gcc-höchst-und DoD ermöglicht Teilnehmern, mithilfe eines telefongeräts an Teams-Besprechungen in ihrer gcc-oder DoD-Organisation teilzunehmen. Besprechungsteilnehmer möchten möglicherweise ein Telefongerät verwenden, um an Teams-Besprechungen in Szenarien teilzunehmen, beispielsweise wenn die Internetkonnektivität limitiert ist oder wenn Benutzer unterwegs sind und keinen Zugriff auf Teams haben. Teilnehmer können an Besprechungen teilnehmen, indem Sie entweder eine Einwahl Telefonnummer für Ihre Organisation einwählen oder die Besprechung auf Ihrem Telefongerät anrufen.

Bei Audiokonferenzen mit direktem Routing für gcc-höchst-und DoD verwendet Ihre Organisation eigene Nummern als Einwahlnummern, und alle Auswahlen von Besprechungen zu Telefongeräten werden über direkte Weiterleitung geroutet. Um den Dienst zu aktivieren, müssen Organisationen Direktes Routing einrichten und Telefonnummern konfigurieren, die als Einwahl Telefonnummern verwendet werden können. Die Anforderung zur Verwendung des direkten Routings unterscheidet sich vom Audiokonferenzdienst, der für nicht-gcc-Organisationen mit hoher und nicht-DoD-Funktion angeboten wird, bei denen die Einwahl Telefonnummern von Microsoft bereitgestellt werden.

## <a name="deploy-audio-conferencing-with-direct-routing-for-gcc-high-and-dod"></a>Bereitstellen von Audiokonferenzen mit direktem Routing für gcc-höchst-und DoD

### <a name="step-1-get-audio-conferencing-with-direct-routing-for-gcc-high-or-dod-licenses"></a>Schritt 1: Abrufen von Audiokonferenzen mit Direct Routing für gcc-Lizenzen für höhere oder DoD-Lizenzen 

Wenn Sie Audiokonferenzen in gcc-höchst-oder DoD verwenden möchten, müssen Ihre Organisation und die Benutzer in Ihrer Organisation über eine Audiokonferenz mit zugewiesener Direct Routing-Lizenz verfügen. Hier sind die Lizenzen, die Sie benötigen, um Audiokonferenzen mit Direct Routing für gcc-höchst-oder DoD zu aktivieren.

- Gcc-höchst: eine Audio-Conferencing-gcc-Lizenz für Ihre Organisation und Audiokonferenz-gcc-Lizenzen für Ihre Benutzer.

- DoD: eine Audio Conferencing-DoD-Mandanten Lizenz für Ihre Organisation und Ihre Audio-Conferencing-DoD-Lizenzen für Ihre Benutzer.

Zum Aktivieren des Diensts sind eine Mandanten Lizenz und mindestens eine Benutzerlizenz erforderlich. Sie können den Dienst nur mit der Mandanten Lizenz oder nur mit Benutzerlizenzen aktivieren. Wenden Sie sich an Ihr Konto Team, um Dienstlizenzen für Ihren Mandanten und die Benutzer in Ihrer Organisation zu erhalten.

> [!IMPORTANT]
> Benutzer können für Audiokonferenzen mit direktem Routing erst dann aktiviert werden, wenn Einwahl Telefonnummern eingerichtet sind. Es wird empfohlen, dass Sie keine Audiokonferenzen mit direktem Routing für gcc-hoch-oder DoD-Lizenzen an Benutzer zuweisen, bis Sie Einwahl Telefonnummern wie in diesem Artikel beschrieben einrichten.

### <a name="step-2-set-up-direct-routing"></a>Schritt 2: Einrichten des direkten Routings

Informationen zum Einrichten des direkten Routings finden Sie in den folgenden Artikeln:

- [Planen von direktem Routing](direct-routing-plan.md)

- [Konfigurieren von direktem Routing](direct-routing-configure.md)

> [!NOTE]
> Denken Sie beim Einrichten des direkten Routings daran, die in diesen beiden Artikeln beschriebenen "gcc-hoch"-oder DoD-spezifischen FQDNs und Ports zu verwenden.

### <a name="step-3-set-up-dial-in-phone-numbers"></a>Schritt 3: Einrichten von Einwahl Telefonnummern

Einwahl Telefonnummern sind die Telefonnummern, die ihrer Audiokonferenz-Brücke zugeordnet sind. Diese Nummern werden von Teilnehmern verwendet, um an Besprechungen teilzunehmen, die von Benutzern in Ihrer Organisation geplant wurden. Diese Nummern sind auch in den Besprechungseinladungen der Benutzer enthalten, die Besprechungen in Ihrer Organisation planen, und auf der Seite "Ortsnummer suchen".

#### <a name="define-service-phone-numbers-in-your-tenant"></a>Definieren von Service-Telefonnummern in Ihrem Mandanten

Sie können das PowerShell-Cmdlet New-csHybridTelephoneNumber verwenden, um Dienst Rufnummern in Ihrem Mandanten zu definieren, die zum Weiterleiten von Anrufen an den Audiokonferenzdienst über direktes Routing verwendet werden können. 

  ```PowerShell
  New-csHybridTelephoneNumber -TelephoneNumber <Phone number in E.164 format>
  ```

Beispiel:
  ```PowerShell
  New-csHybridTelephoneNumber -TelephoneNumber "+14250000000"
  ```

#### <a name="assign-the-service-phone-numbers-to-the-audio-conferencing-bridge-of-your-organization"></a>Zuweisen der Telefonnummern für den Service zur Audiokonferenz-Brücke Ihrer Organisation

Mithilfe des PowerShell-Cmdlets Register-csOnlineDialInConferencingServiceNumber können Sie der Audiokonferenz-Brücke Ihrer Organisation Service-Telefonnummern zuweisen.

  ```PowerShell
  Register-csOnlineDialInConferencingServiceNumber -identity <Telephone number in E.164 format> -BridgeId <Identity of the audio conferencing bridge>
  ```

Sie können die ID Ihrer Audiokonferenz-Bridge mithilfe von Get-CsOnlineDialInConferencingBridge anzeigen. Beispiel:

  ```PowerShell
  $b= Get-CsOnlineDialInConferencingBridge
  Register-csOnlineDialInConferencingServiceNumber -identity 14257048060 -BridgeId $b.identity
  ```


### <a name="step-4-define-a-global-voice-routing-policy-to-enable-the-routing-of-outbound-calls-from-meetings"></a>Schritt 4: Definieren einer globalen VoIP-Routing Richtlinie zum Aktivieren des Routings von ausgehenden Anrufen aus Besprechungen

Das Routing von ausgehenden Anrufen, die an das PSTN über von den Benutzern in Ihrer Organisation organisierte Besprechungen durchgeführt werden, wird durch die globale VoIP-Routing Richtlinie Ihrer Organisation definiert. Wenn in Ihrer Organisation eine globale VoIP-Routing Richtlinie definiert ist, überprüfen Sie, ob die globale VoIP-Routing Richtlinie die ausgehenden Anrufe an das PSTN zulässt, die von den von Benutzern in Ihrer Organisation organisierten Besprechungen initiiert werden sollen. Wenn in Ihrer Organisation keine globale VoIP-Routing Richtlinie definiert ist, müssen Sie eine Definition definieren, um die Weiterleitung von ausgehenden Anrufen an das PSTN aus Besprechungen zu ermöglichen, die von Benutzern in Ihrer Organisation organisiert werden. Beachten Sie, dass die globale VoIP-Routing Richtlinie Ihrer Organisation auch für Einzel Anrufe an das PSTN von Benutzern in Ihrer Organisation gilt. Wenn eins-zu-eins-Anrufe an das PSTN für Benutzer in Ihrer Organisation aktiviert sind, stellen Sie sicher, dass die globale VoIP-Routing Richtlinie die Anforderungen Ihrer Organisation für beide Anrufarten erfüllt. 

> [!NOTE]
> Standortbasiertes Routing steht in den Microsoft 365 Government Community Cloud (gcc)-oder DoD-Bereitstellungen nicht zur Verfügung. Stellen Sie beim Aktivieren von Audiokonferenzen sicher, dass keine Audiokonferenz-Benutzer in den gcc-oder DoD-Umgebungen für standortbasiertes Routing aktiviert sind.

#### <a name="defining-a-global-voice-routing-policy"></a>Definieren einer globalen VoIP-Routing Richtlinie

Eine globale VoIP-Routing Richtlinie kann definiert werden, indem eine PSTN-Nutzung, eine VoIP-Route, eine VoIP-Routing Richtlinie und die neue VoIP-Routing Richtlinie als globale VoIP-Weiterleitungs Richtlinie Ihrer Organisation zugewiesen werden.

In den folgenden Schritten wird beschrieben, wie Sie eine neue globale VoIP-Routing Richtlinie für eine Organisation ohne einen definieren. Wenn in Ihrer Organisation bereits VoIP-Routing Richtlinien definiert sind, stellen Sie sicher, dass die folgende Konfiguration nicht in Konflikt mit den vorhandenen VoIP-Routing Richtlinien Ihrer Organisation steht.

Zum Erstellen einer neuen PSTN-Nutzung in einer Remote-PowerShell-Sitzung in Skype for Business Online verwenden Sie den folgenden Befehl:

  ```PowerShell
  Set-CsOnlinePstnUsage -Identity Global -Usage @{Add="International"}
  ```

Weitere Informationen finden Sie unter [Satz-CsOnlinePstnUsage](https://docs.microsoft.com/powershell/module/skype/set-csonlinepstnusage).

Verwenden Sie zum Erstellen einer neuen VoIP-Route den folgenden Befehl:

  ```PowerShell
  New-CsOnlineVoiceRoute -Identity "International" -NumberPattern ".*" -OnlinePstnGatewayList sbc1.contoso.biz -OnlinePstnUsages "International"
  ```

Wenn Sie eine neue VoIP-Route für Ihre Organisation definieren, geben Sie ein oder mehrere der PSTN-Online-PSTN-Gateways an, die während der Konfiguration des direkten Routings für Ihre Organisation definiert wurden. 

Das Zahlenmuster gibt an, welche Anrufe über die angegebene Liste der Gateways basierend auf der Zieltelefonnummer des Anrufs weitergeleitet werden. Im obigen Beispiel Stimmen Anrufe an alle Zielorte der Welt mit der VoIP-Route überein. Wenn Sie die Telefonnummern einschränken möchten, die aus den Besprechungen von Benutzern in Ihrer Organisation gewählt werden können, können Sie das Zahlenmuster so ändern, dass die VoIP-Route nur den Zahlen Mustern der zulässigen Ziele entspricht. Beachten Sie bitte, dass der Anruf nicht weitergeleitet wird, wenn keine VoIP-Routen vorhanden sind, die dem Zahlenmuster der Zielrufnummer eines bestimmten Anrufs entsprechen.

Weitere Informationen finden Sie unter [New-CsOnlineVoiceRoute](https://docs.microsoft.com/powershell/module/skype/new-csonlinevoiceroute).

Verwenden Sie zum Erstellen einer neuen VoIP-Routing Richtlinie den folgenden Befehl:

  ```PowerShell
  New-CsOnlineVoiceRoutingPolicy "InternationalVoiceRoutingPolicy" -OnlinePstnUsages "International"
  ```

Wenn in der VoIP-Routing Richtlinie mehrere PSTN-Nutzungen definiert sind, werden Sie in der Reihenfolge ausgewertet, in der Sie definiert sind. Es wird empfohlen, dass die PSTN-Verwendungen in der Reihenfolge der spezifischsten für die generischen Ausdrücke definiert sind, was die Zahlenmuster der VoIP-Routen anbelangt, die mit den PSTN-Nutzungen verknüpft sind. Wenn beispielsweise eine PSTN-Nutzung für die Weiterleitung von Anrufen in die USA definiert wurde und eine andere PSTN-Nutzung für die Weiterleitung von Anrufen an einen anderen Ort in der Welt definiert wurde, sollte die PSTN-Nutzung für Anrufe in die Vereinigten Staaten in der VoIP-Routing Richtlinie vor der PSTN-Nutzung aufgeführt werden, um Anrufe an einen anderen Ort in der weltweiter zuleiten.

Weitere Informationen finden Sie unter [New-CsOnlineVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csonlinevoiceroutingpolicy).

Verwenden Sie den folgenden Befehl, um die neue VoIP-Route der globalen VoIP-Routing Richtlinie Ihrer Organisation zuzuweisen:

  ```PowerShell
  Grant-CsOnlineVoiceRoutingPolicy -PolicyName "InternationalVoiceRoutingPolicy" -Global
  ```

Weitere Informationen finden Sie unter [Grant-CsOnlineVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csonlinevoiceroutingpolicy).

Nachdem die globale VoIP-Routing Richtlinie definiert wurde, werden ausgehende Anrufe aus Besprechungen, die von Benutzern in Ihrer Organisation organisiert werden, anhand der VoIP-Routen ausgewertet, die den PSTN-Nutzungen der globalen VoIP-Routing Richtlinie zugeordnet sind. Die ausgehenden Anrufe werden entsprechend der ersten VoIP-Route weitergeleitet, die dem Nummernmuster der gewählten Telefonnummer entspricht.

### <a name="step-5-assign-audio-conferencing-with-direct-routing-for-gcc-high-or-dod-licenses-to-your-users"></a>Schritt 5: Zuweisen von Audiokonferenzen mit Direct Routing für gcc-höchst-oder DoD-Lizenzen für Ihre Benutzer

Informationen zum Zuweisen von Audiokonferenzen mit Direct Routing für gcc-Lizenzen für höhere oder DoD-Lizenzen für Ihren Benutzer finden Sie unter [Zuweisen von Lizenzen zu Benutzern](https://docs.microsoft.com/microsoft-365/admin/manage/assign-licenses-to-users).

### <a name="step-6-optional-see-a-list-of-audio-conferencing-numbers-in-teams"></a>Schritt 6: (optional) Anzeigen einer Liste der Audiokonferenz-Nummern in Teams

Wenn Sie die Liste der Audiokonferenz-Nummern Ihrer Organisation anzeigen möchten, wechseln [Sie zu einer Liste der Audiokonferenz-Nummern in Microsoft Teams](see-a-list-of-audio-conferencing-numbers-in-teams.md).

### <a name="step-7-optional-set-auto-attendant-languages-for-the-audio-conferencing-dial-in-numbers-of-you-organization"></a>Schritt 7: (optional) festlegen der Sprachen der automatischen Telefonzentrale für die Einwahlnummern für Audiokonferenzen Ihrer Organisation

Informationen zum Ändern der Sprachen der Einwahlnummern für Audiokonferenzen in Ihrer Organisation finden Sie unter [Festlegen von Sprachen für die automatische Telefonzentrale für Audiokonferenzen in Microsoft Teams](set-auto-attendant-languages-for-audio-conferencing-in-teams.md).

### <a name="step-8-optional-change-the-settings-of-the-audio-conferencing-bridge-of-your-organization"></a>Schritt 8: (optional) Ändern der Einstellungen der Audiokonferenz-Brücke in Ihrer Organisation

Informationen zum Ändern der Einstellungen der Audiokonferenz-Brücke in Ihrer Organisation finden Sie unter [Ändern der Einstellungen für eine Audiokonferenz-Brücke](change-the-settings-for-an-audio-conferencing-bridge.md).

### <a name="step-9-optional-set-the-phone-numbers-included-in-the-meeting-invites-of-the-users-in-your-organization"></a>Schritt 9: (optional) festlegen der Telefonnummern, die in den Besprechungseinladungen der Benutzer in Ihrer Organisation enthalten sind

Informationen zum Ändern der Gruppe von Telefonnummern, die in den Besprechungseinladungen der Benutzer enthalten sind, finden Sie unter [Festlegen der Telefonnummern, die in Einladungen in Microsoft Teams enthalten](set-the-phone-numbers-included-on-invites-in-teams.md)sind.

## <a name="audio-conferencing-capabilities-not-supported-in-audio-conferencing-with-direct-routing-for-gcc-high-and-dod"></a>Audiokonferenzfunktionen, die in Audiokonferenzen nicht unterstützt werden, mit direktem Routing für gcc-höchst-und DoD-Funktionen

Im folgenden finden Sie Audiokonferenzfunktionen, die bei Audiokonferenzen mit direktem Routing für gcc-höchst-und DoD-Funktionen nicht unterstützt werden:

- Eingabe-und Exit-Benachrichtigungen mithilfe der namens Aufzeichnung. Bei Audiokonferenzen mit direktem Routing werden die Eingabe-und Exit-Benachrichtigungen als Töne in der Besprechung abgespielt.

- Richtlinien für ausgehende Anruf Einschränkungen für Audiokonferenzen. Steuerelemente auf Benutzerebene zum Einschränken ausgehender Anrufe gelten nicht für von der direkten Weiterleitung weitergeleitete Anrufe an eingehende Anrufe.

- Deaktivieren Sie die Verwendung von gebührenfreien Nummern für den Besprechungs spezifischen Organisator. Steuerelemente auf Benutzerebene, um die Verwendung von gebührenfreien Nummern für die Teilnahme an den Besprechungen Ihrer Organisation zu beschränken, gelten nicht für Anrufe, die über direktes Routing weitergeleitet werden.

- Senden von Benachrichtigungs-e-Mails an Benutzer, wenn sich Ihre Einstellungen ändern Audiokonferenz-Benachrichtigungs-e-Mails werden für Audiokonferenzen mit direktem Routing für gcc-höchst-und DoD nicht unterstützt.
