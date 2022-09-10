---
title: Audiokonferenzen mit Direct Routing, GCCH und DoD
author: MicrosoftHeidi
ms.author: heidip
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
- Microsoft Teams
f1.keywords:
- NOCSH
ms.localizationpriority: medium
description: Admin erfahren, wie Audiokonferenzen mit Direct Routing in GCCH- und DoD-Umgebungen verwendet werden.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: bd467b9da8d296c21d4a0405d651bbaa6b001fd3
ms.sourcegitcommit: 5abfb6f1abe10b6d32cf6eb97a890cf3138ed0e6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/10/2022
ms.locfileid: "67641776"
---
# <a name="audio-conferencing-with-direct-routing-for-gcc-high-and-dod"></a>Audiokonferenzen mit direktem Routing für GCC High und DoD

Audiokonferenzen mit Direct Routing für GCC High und DoD ermöglichen Teilnehmern die Teilnahme an Teams-Besprechungen in Ihrer GCC High- oder DoD-Organisation mithilfe eines Telefongeräts. Besprechungsteilnehmer bevorzugen es möglicherweise, ein Telefongerät für die Teilnahme an Teams-Besprechungen in Szenarien zu verwenden, z. B. wenn die Internetverbindung eingeschränkt ist oder wenn Benutzer unterwegs sind und keinen Zugriff auf Teams haben. Die Teilnehmer können an Besprechungen teilnehmen, indem sie sich entweder bei einer Einwahltelefonnummer für Ihre Organisation einwählen oder die Besprechung an ihr Telefongerät auswählen lassen.

Bei Audiokonferenzen mit Direct Routing für GCC High und DoD verwendet Ihre Organisation ihre eigenen Nummern als Einwahltelefonnummern, und alle Besprechungswählnummern an Telefongeräte werden über Direct Routing weitergeleitet. Um den Dienst zu aktivieren, müssen Organisationen Direct Routing einrichten und Telefonnummern konfigurieren, die als Einwahltelefonnummern verwendet werden können. Die Anforderung zur Verwendung von Direct Routing unterscheidet sich vom Audiokonferenzdienst, der Nicht-GCC High- und Nicht-DoD-Organisationen angeboten wird, in denen die Einwahltelefonnummern von Microsoft bereitgestellt werden.

## <a name="deploy-audio-conferencing-with-direct-routing-for-gcc-high-and-dod"></a>Bereitstellen von Audiokonferenzen mit Direct Routing für GCC High und DoD

### <a name="step-1-get-audio-conferencing-with-direct-routing-for-gcc-high-or-dod-licenses"></a>Schritt 1: Abrufen von Audiokonferenzen mit Direct Routing für GCC High- oder DoD-Lizenzen

Um Audiokonferenzen in GCC High oder DoD verwenden zu können, benötigen Ihre Organisation und die Benutzer in Ihrer Organisation eine Audiokonferenz mit zugewiesener Direct Routing-Lizenz. Hier sind die Lizenzen, die Sie zum Aktivieren von Audiokonferenzen mit Direct Routing für GCC High oder DoD benötigen.

- GCC High: Eine Audiokonferenz – GCC High Tenant-Lizenz für Ihre Organisation und Audiokonferenzen – GCC High-Lizenzen für Ihre Benutzer.

- DoD: Eine Lizenz für Audiokonferenzen – DoD-Mandantenlizenz für Ihre Organisation und Audiokonferenzen – DoD-Lizenzen für Ihre Benutzer.

Zum Aktivieren des Diensts sind eine Mandantenlizenz und mindestens eine Benutzerlizenz erforderlich. Sie können den Dienst nicht nur mit der Mandantenlizenz oder nur mit Benutzerlizenzen aktivieren. Um Dienstlizenzen für Ihren Mandanten und die Benutzer in Ihrer Organisation zu erhalten, wenden Sie sich an Ihr Kontoteam.

> [!IMPORTANT]
> Benutzer können erst dann für Audiokonferenzen mit Direct Routing aktiviert werden, wenn Einwahltelefonnummern eingerichtet wurden. Es wird empfohlen, Benutzern erst Audiokonferenzen mit Direct Routing für GCC High- oder DoD-Lizenzen zuzuweisen, wenn Sie Einwahltelefonnummern wie in diesem Artikel beschrieben einrichten.  Wenn Sie diese Anleitung nicht befolgen, fehlt die Wähltastatur möglicherweise vollständig im Teams-Client.

### <a name="step-2-set-up-direct-routing"></a>Schritt 2: Einrichten von Direct Routing

Informationen zum Einrichten von Direct Routing finden Sie in den folgenden Artikeln:

- [Planen von direktem Routing](direct-routing-plan.md)

- [Konfigurieren von direktem Routing](direct-routing-configure.md)

> [!NOTE]
> Denken Sie beim Einrichten von Direct Routing daran, die in diesen beiden Artikeln beschriebenen GCC High- oder DoD-spezifischen FQDNs und Ports zu verwenden.

### <a name="step-3-set-up-dial-in-phone-numbers"></a>Schritt 3: Einrichten von Einwahltelefonnummern

Einwahlnummern sind die Telefonnummern, die Ihrer Audiokonferenzbrücke zugeordnet sind. Diese Nummern werden von Teilnehmern verwendet, um an Besprechungen teilzunehmen, die von Benutzern in Ihrer Organisation geplant wurden. Diese Nummern sind auch in den Besprechungseinladungen der Benutzer enthalten, die Besprechungen in Ihrer Organisation planen, und auf der Seite "Lokale Nummer suchen".

#### <a name="define-service-phone-numbers-in-your-tenant"></a>Definieren von Diensttelefonnummern in Ihrem Mandanten

Sie können das PowerShell-Cmdlet New-csHybridTelephoneNumber verwenden, um Diensttelefonnummern in Ihrem Mandanten zu definieren, die zum Weiterleiten von Anrufen an den Audiokonferenzdienst über Direct Routing verwendet werden können.

  ```PowerShell
  New-csHybridTelephoneNumber -TelephoneNumber <Phone number in E.164 format>
  ```

Zum Beispiel: 

  ```PowerShell
  New-csHybridTelephoneNumber -TelephoneNumber "+14250000000"
  ```

#### <a name="assign-the-service-phone-numbers-to-the-audio-conferencing-bridge-of-your-organization"></a>Zuweisen der Diensttelefonnummern zur Audiokonferenzbrücke Ihrer Organisation

Mithilfe des PowerShell-Cmdlets "Register-csOnlineDialInConferencingServiceNumber" können Sie der Audiokonferenzbrücke Ihrer Organisation Diensttelefonnummern zuweisen.

  ```PowerShell
  Register-csOnlineDialInConferencingServiceNumber -identity <Telephone number in E.164 format> -BridgeId <Identity of the audio conferencing bridge>
  ```

Sie können die ID Ihrer Audiokonferenzbrücke mit Get-CsOnlineDialInConferencingBridge anzeigen. Zum Beispiel: 

  ```PowerShell
  $b= Get-CsOnlineDialInConferencingBridge
  Register-csOnlineDialInConferencingServiceNumber -identity 14257048060 -BridgeId $b.identity
  ```

### <a name="step-4-define-a-global-voice-routing-policy-to-enable-the-routing-of-outbound-calls-from-meetings"></a>Schritt 4: Definieren einer globalen VoIP-Routingrichtlinie zum Aktivieren des Routings ausgehender Anrufe aus Besprechungen

Das Routing ausgehender Anrufe, die aus von Benutzern in Ihrer Organisation organisierten Besprechungen an das Festnetz getätigt werden, wird durch die globale VoIP-Routingrichtlinie Ihrer Organisation definiert. Wenn in Ihrer Organisation eine globale VoIP-Routingrichtlinie definiert ist, überprüfen Sie, ob die globale VoIP-Routingrichtlinie ausgehende Anrufe an das PSTN zulässt, die von Besprechungen initiiert werden sollen, die von Benutzern in Ihrer Organisation organisiert wurden. Wenn in Ihrer Organisation keine globale VoIP-Routingrichtlinie definiert ist, müssen Sie eine richtlinie definieren, um das Routing ausgehender Anrufe an das PSTN aus Besprechungen zu ermöglichen, die von Benutzern in Ihrer Organisation organisiert wurden. Beachten Sie, dass die globale VoIP-Routingrichtlinie Ihrer Organisation auch für 1:1-Anrufe gilt, die von Benutzern in Ihrer Organisation an das PSTN getätigt werden. Wenn 1:1-Anrufe an das PSTN für Benutzer in Ihrer Organisation aktiviert sind, stellen Sie sicher, dass die globale VoIP-Routingrichtlinie den Anforderungen Ihrer Organisation für beide Arten von Anrufen entspricht.

> [!NOTE]
> Location-Based Routing ist in Microsoft 365 Government Community Cloud (GCC)-Hoch- oder DoD-Bereitstellungen nicht verfügbar. Stellen Sie beim Aktivieren von Audiokonferenzen sicher, dass keine Audiokonferenzbenutzer in der GCC High- oder doD-Umgebung für Location-Based Routing aktiviert sind.

#### <a name="defining-a-global-voice-routing-policy"></a>Definieren einer globalen VoIP-Routingrichtlinie

Eine globale VoIP-Routingrichtlinie kann definiert werden, indem eine PSTN-Nutzung, eine VoIP-Route, eine VoIP-Routingrichtlinie definiert und die neue VoIP-Routingrichtlinie als globale VoIP-Routingrichtlinie Ihrer Organisation zugewiesen wird.

In den folgenden Schritten wird beschrieben, wie Sie eine neue globale VoIP-Routingrichtlinie für eine Organisation ohne Eine definieren. Wenn in Ihrer Organisation bereits VoIP-Routingrichtlinien definiert sind, stellen Sie sicher, dass die folgende Konfiguration nicht mit den vorhandenen VoIP-Routingrichtlinien Ihrer Organisation in Konflikt steht.

Verwenden Sie den folgenden Befehl, um eine neue PSTN-Verwendung in einer PowerShell-Remotesitzung in Teams zu erstellen:

  ```PowerShell
  Set-CsOnlinePstnUsage -Identity Global -Usage @{Add="International"}
  ```

Weitere Informationen finden Sie unter [Set-CsOnlinePstnUsage](/powershell/module/skype/set-csonlinepstnusage).

Verwenden Sie den folgenden Befehl, um eine neue VoIP-Route zu erstellen:

  ```PowerShell
  New-CsOnlineVoiceRoute -Identity "International" -NumberPattern ".*" -OnlinePstnGatewayList sbc1.contoso.biz -OnlinePstnUsages "International"
  ```

Geben Sie beim Definieren einer neuen VoIP-Route für Ihre Organisation ein oder mehrere der PSTN-Online-PSTN-Gateways an, die während der Konfiguration von Direct Routing für Ihre Organisation definiert wurden.

Das Nummernmuster gibt an, welche Anrufe basierend auf der Zieltelefonnummer des Anrufs durch die angegebene Liste von Gateways weitergeleitet werden. Im obigen Beispiel stimmen Anrufe zu allen Zielen auf der Welt mit der VoIP-Route überein. Wenn Sie die Telefonnummern einschränken möchten, die aus den Besprechungen von Benutzern in Ihrer Organisation gewählt werden können, können Sie das Nummernmuster so ändern, dass die VoIP-Route nur den Nummernmustern der zulässigen Ziele entspricht. Wenn keine VoIP-Routen vorhanden sind, die dem Nummernmuster der Zieltelefonnummer eines bestimmten Anrufs entsprechen, wird der Anruf nicht weitergeleitet.

Weitere Informationen finden Sie unter [New-CsOnlineVoiceRoute](/powershell/module/skype/new-csonlinevoiceroute).

Verwenden Sie den folgenden Befehl, um eine neue VoIP-Routingrichtlinie zu erstellen:

  ```PowerShell
  New-CsOnlineVoiceRoutingPolicy "InternationalVoiceRoutingPolicy" -OnlinePstnUsages "International"
  ```

Wenn mehrere PSTN-Verwendungen in der VoIP-Routingrichtlinie definiert werden, werden sie in der Reihenfolge ausgewertet, in der sie definiert sind. Es wird empfohlen, dass die PSTN-Verwendungen in der Reihenfolge der spezifischsten für die allgemeineren im Hinblick auf die Nummernmuster der VoIP-Routen definiert werden, die den PSTN-Verwendungen zugeordnet sind. Wenn z. B. eine PSTN-Verwendung zum Weiterleiten von Anrufen an die USA definiert wurde und eine andere PSTN-Nutzung definiert wurde, um Anrufe an einen anderen Ort der Welt weiterzuleiten, sollte die PSTN-Nutzung für Anrufe an die USA in der VoIP-Routingrichtlinie vor der PSTN-Nutzung aufgeführt werden, um Anrufe an andere Standorte der Welt weiterzuleiten.

Weitere Informationen finden Sie unter [New-CsOnlineVoiceRoutingPolicy](/powershell/module/skype/new-csonlinevoiceroutingpolicy).

Verwenden Sie den folgenden Befehl, um die neue VoIP-Route der globalen VoIP-Routingrichtlinie Ihrer Organisation zuzuweisen:

  ```PowerShell
  Grant-CsOnlineVoiceRoutingPolicy -PolicyName "InternationalVoiceRoutingPolicy" -Global
  ```

Weitere Informationen finden Sie [unter Grant-CsOnlineVoiceRoutingPolicy](/powershell/module/skype/grant-csonlinevoiceroutingpolicy).

Nachdem die globale VoIP-Routingrichtlinie definiert wurde, werden ausgehende Anrufe aus Besprechungen, die von Benutzern in Ihrer Organisation organisiert wurden, anhand der VoIP-Routen ausgewertet, die den PSTN-Verwendungen der globalen VoIP-Routingrichtlinie zugeordnet sind. Die ausgehenden Anrufe werden gemäß der ersten VoIP-Route weitergeleitet, die dem Nummernmuster der gewählten Telefonnummer entspricht.

### <a name="step-5-assign-audio-conferencing-with-direct-routing-for-gcc-high-or-dod-licenses-to-your-users"></a>Schritt 5: Zuweisen von Audiokonferenzen mit Direct Routing für GCC High- oder DoD-Lizenzen zu Ihren Benutzern

Informationen zum Zuweisen von Audiokonferenzen mit Direct Routing für GCC High- oder DoD-Lizenzen finden Sie unter Zuweisen von [Lizenzen zu Benutzern](/microsoft-365/admin/manage/assign-licenses-to-users).

### <a name="step-6-optional-see-a-list-of-audio-conferencing-numbers-in-teams"></a>Schritt 6: (Optional) Anzeigen einer Liste der Audiokonferenznummern in Teams

Um die Liste der Audiokonferenznummern Ihrer Organisation anzuzeigen, wechseln Sie zu ["Eine Liste der Audiokonferenznummern in Microsoft Teams anzeigen](see-a-list-of-audio-conferencing-numbers-in-teams.md)".

### <a name="step-7-optional-set-auto-attendant-languages-for-the-audio-conferencing-dial-in-numbers-of-you-organization"></a>Schritt 7: (Optional) Festlegen der Sprachen der automatischen Telefonzentrale für die Audiokonferenz-Einwahlnummern Ihrer Organisation

Informationen zum Ändern der Sprachen der Einwahlnummern für Audiokonferenzen in Ihrer Organisation finden Sie unter Festlegen der [Sprachen für die automatische Telefonzentrale für Audiokonferenzen in Microsoft Teams](set-auto-attendant-languages-for-audio-conferencing-in-teams.md).

### <a name="step-8-optional-change-the-settings-of-the-audio-conferencing-bridge-of-your-organization"></a>Schritt 8: (Optional) Ändern der Einstellungen der Audiokonferenzbrücke Ihrer Organisation

Informationen zum Ändern der Einstellungen der Audiokonferenzbrücke Ihrer Organisation finden Sie unter [Ändern der Einstellungen für eine Audiokonferenzbrücke](change-the-settings-for-an-audio-conferencing-bridge.md).

### <a name="step-9-optional-set-the-phone-numbers-included-in-the-meeting-invites-of-the-users-in-your-organization"></a>Schritt 9: (Optional) Festlegen der Telefonnummern, die in den Besprechungseinladungen der Benutzer in Ihrer Organisation enthalten sind

Informationen zum Ändern des Satzes von Telefonnummern, die in den Besprechungseinladungen der Benutzer enthalten sind, finden Sie [unter Festlegen der Telefonnummern, die in Einladungen in Microsoft Teams enthalten](set-the-phone-numbers-included-on-invites-in-teams.md) sind.

## <a name="audio-conferencing-capabilities-not-supported-in-audio-conferencing-with-direct-routing-for-gcc-high-and-dod"></a>Audiokonferenzfunktionen werden in Audiokonferenzen mit Direct Routing für GCC High und DoD nicht unterstützt

Im Folgenden sind Audiokonferenzfunktionen aufgeführt, die in Audiokonferenzen mit Direct Routing für GCC High und DoD nicht unterstützt werden:

- Ein- und Ausstiegsbenachrichtigungen mithilfe der Namensaufzeichnung. Bei Audiokonferenzen mit Direct Routing werden Ein- und Ausgangsbenachrichtigungen in der Besprechung als Töne wiedergegeben.

- Deaktivieren Sie die Verwendung von gebührenfreien Nummern für den Besprechungsorganisator. Steuerelemente auf Benutzerebene, um die Verwendung von gebührenfreien Nummern für die Teilnahme an den Besprechungen Ihrer Organisation einzuschränken, gelten nicht für Anrufe, die über Direct Routing weitergeleitet werden.

- Senden von Benachrichtigungs-E-Mails an Benutzer, wenn sich ihre Einstellungen ändern. Audiokonferenzbenachrichtigungs-E-Mails werden für Audiokonferenzen mit Direct Routing für GCC High und DoD nicht unterstützt.
