---
title: Audiokonferenzen mit Direct Routing, GCCH und DoD
author: cichur
ms.author: v-cichur
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
description: Der Administrator kann erfahren, wie Audiokonferenzen mit Direct Routing in GCCH- und DoD-Umgebungen verwendet werden.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 577a9fe106cb5dae23049404b54433288e350b78
ms.sourcegitcommit: bd7847de9d1402476f8faaeae2ff97ec60d86a1b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/26/2021
ms.locfileid: "51262620"
---
# <a name="audio-conferencing-with-direct-routing-for-gcc-high-and-dod"></a>Audiokonferenzen mit direktem Routing für GCC High und DoD

Audiokonferenzen mit Direct Routing für GCC High und DoD ermöglichen Teilnehmern die Teilnahme an Teams-Besprechungen in Ihrer GCC High- oder DoD-Organisation über ein Telefongerät. Besprechungsteilnehmer verwenden möglicherweise lieber ein Telefongerät, um an Teams-Besprechungen teilzunehmen, z. B. wenn die Internetverbindung eingeschränkt ist oder wenn Benutzer unterwegs sind und keinen Zugriff auf Teams haben. Teilnehmer können sich entscheiden, an Besprechungen teilzunehmen, indem sie sich entweder bei einer Einwahltelefonnummer für Ihre Organisation einwählen oder die Besprechung auf ihr Telefongerät auswählt.

Bei Audiokonferenzen mit Direct Routing für GCC High und DoD verwendet Ihre Organisation eigene Nummern als Einwahltelefonnummern, und alle Besprechungswähler zu Telefongeräten werden über Direct Routing geroutet. Um den Dienst zu aktivieren, müssen Organisationen Direct Routing einrichten und Telefonnummern konfigurieren, die als Einwahltelefonnummern verwendet werden können. Die Anforderung für die Verwendung von Direct Routing ist anders als der Audiokonferenzdienst, der für Organisationen außerhalb von GCC High und Non-DoD angeboten wird, in denen die Einwahltelefonnummern von Microsoft bereitgestellt werden.

## <a name="deploy-audio-conferencing-with-direct-routing-for-gcc-high-and-dod"></a>Bereitstellen von Audiokonferenzen mit Direct Routing für GCC High und DoD

### <a name="step-1-get-audio-conferencing-with-direct-routing-for-gcc-high-or-dod-licenses"></a>Schritt 1: Erhalten von Audiokonferenzen mit Direct Routing für GCC High- oder DoD-Lizenzen 

Um Audiokonferenzen in GCC High oder DoD verwenden zu können, müssen Ihre Organisation und die Benutzer in Ihrer Organisation über eine Lizenz für Audiokonferenzen mit Direct Routing verfügen. Hier sind die Lizenzen, die Sie zum Aktivieren von Audiokonferenzen mit Direct Routing für GCC High oder DoD benötigen.

- GCC High: An Audio Conferencing – GCC High Tenant license for your organization and Audio Conferencing – GCC High licenses for your users.

- DoD: Eine Lizenz für Audiokonferenzen – DoD-Mandanten für Ihre Organisation und Audiokonferenzen – DoD-Lizenzen für Ihre Benutzer.

Zum Aktivieren des Diensts sind eine Mandantenlizenz und mindestens eine Benutzerlizenz erforderlich. Sie können den Dienst nicht nur mit der Mandantenlizenz oder nur mit Benutzerlizenzen aktivieren. Wenn Sie Servicelizenzen für Ihren Mandanten und die Benutzer in Ihrer Organisation erhalten möchten, wenden Sie sich an Ihr Kontoteam.

> [!IMPORTANT]
> Benutzer können für Audiokonferenzen mit Direct Routing erst aktiviert werden, wenn Einwahltelefonnummern eingerichtet sind. Es wird empfohlen, Benutzern erst dann Audiokonferenzen mit Direct Routing für GCC High- oder DoD-Lizenzen zuzuordnen, wenn Sie Einwahltelefonnummern einrichten, wie in diesem Artikel beschrieben.  Wenn Sie diese Anleitung nicht befolgen, fehlt die Wähltaste möglicherweise vollständig im Teams-Client.

### <a name="step-2-set-up-direct-routing"></a>Schritt 2: Einrichten von Direct Routing

Informationen zum Einrichten von Direct Routing finden Sie in den folgenden Artikeln:

- [Planen von direktem Routing](direct-routing-plan.md)

- [Konfigurieren von direktem Routing](direct-routing-configure.md)

> [!NOTE]
> Denken Sie beim Einrichten von Direct Routing daran, die in diesen beiden Artikeln beschriebenen GCC High- oder DoD-spezifischen FQDNs und Ports zu verwenden.

### <a name="step-3-set-up-dial-in-phone-numbers"></a>Schritt 3: Einrichten von Einwahltelefonnummern

Einwahltelefonnummern sind die Telefonnummern, die Ihrer Audiokonferenzbrücke zugeordnet sind. Diese Nummern werden von Teilnehmern verwendet, um an Besprechungen teilzunehmen, die von Benutzern in Ihrer Organisation geplant wurden. Diese Nummern sind auch in den Besprechungsbesprechungen der Benutzer enthalten, die Besprechungen in Ihrer Organisation planen, und auf der Seite "Lokale Nummer suchen".

#### <a name="define-service-phone-numbers-in-your-tenant"></a>Definieren von Diensttelefonnummern in Ihrem Mandanten

Sie können das Cmdlet New-csHybridTelephoneNumber PowerShell verwenden, um Servicetelefonnummern in Ihrem Mandanten zu definieren, die zum Weiterleiten von Anrufen an den Audiokonferenzdienst über Direct Routing verwendet werden können. 

  ```PowerShell
  New-csHybridTelephoneNumber -TelephoneNumber <Phone number in E.164 format>
  ```

Beispiel:
  ```PowerShell
  New-csHybridTelephoneNumber -TelephoneNumber "+14250000000"
  ```

#### <a name="assign-the-service-phone-numbers-to-the-audio-conferencing-bridge-of-your-organization"></a>Zuweisen der Servicetelefonnummern zur Audiokonferenzbrücke Ihrer Organisation

Sie können der Audiokonferenzbrücke Ihrer Organisation Diensttelefonnummern zuweisen, indem Sie das Cmdlet Register-csOnlineDialInConferencingServiceNumber PowerShell verwenden.

  ```PowerShell
  Register-csOnlineDialInConferencingServiceNumber -identity <Telephone number in E.164 format> -BridgeId <Identity of the audio conferencing bridge>
  ```

Sie können die ID Ihrer Audiokonferenzbrücke mit Get-CsOnlineDialInConferencingBridge sehen. Beispiel:

  ```PowerShell
  $b= Get-CsOnlineDialInConferencingBridge
  Register-csOnlineDialInConferencingServiceNumber -identity 14257048060 -BridgeId $b.identity
  ```


### <a name="step-4-define-a-global-voice-routing-policy-to-enable-the-routing-of-outbound-calls-from-meetings"></a>Schritt 4: Definieren einer globalen Voice routing-Richtlinie zum Aktivieren des Routings von ausgehenden Anrufen aus Besprechungen

Das Routing ausgehender Anrufe, die an das PSTN von Besprechungen vorgenommen werden, die von Benutzern in Ihrer Organisation organisiert werden, wird durch die globale Voiceroutingrichtlinie Ihrer Organisation definiert. Wenn in Ihrer Organisation eine globale Voice routingrichtlinie definiert ist, überprüfen Sie bitte, ob die globale Voice routing-Richtlinie die ausgehenden Anrufe an das PSTN zulässt, die von Besprechungen initiiert werden sollen, die von Benutzern in Ihrer Organisation organisiert werden. Wenn in Ihrer Organisation keine globale Voice routingrichtlinie definiert ist, müssen Sie eine richtlinie definieren, um das Routing ausgehender Anrufe an das PSTN von Besprechungen zu ermöglichen, die von Benutzern in Ihrer Organisation organisiert werden. Beachten Sie, dass die globale Sprachroutingrichtlinie Ihrer Organisation auch für 1:1-Anrufe gilt, die von Benutzern in Ihrer Organisation an das PSTN vorgenommen werden. Wenn 1:1-Anrufe an das PSTN für Benutzer in Ihrer Organisation aktiviert sind, stellen Sie sicher, dass die globale Sprachroutingrichtlinie den Anforderungen Ihrer Organisation für beide Arten von Anrufen entspricht. 

> [!NOTE]
> Location-Based Routing ist in Microsoft 365 Government Community Cloud (GCC)-Hoch- oder DoD-Bereitstellungen nicht verfügbar. Stellen Sie beim Aktivieren von Audiokonferenzen sicher, dass keine Benutzer von Audiokonferenzen in der GCC High- oder doD-Umgebung für das Routing Location-Based sind.

#### <a name="defining-a-global-voice-routing-policy"></a>Definieren einer globalen Sprachroutingrichtlinie

Eine globale Sprachroutingrichtlinie kann definiert werden, indem eine PSTN-Nutzung, eine Sprachroute, eine Voiceroutingrichtlinie definiert und die neue Voiceroutingrichtlinie als globale Voiceroutingrichtlinie Ihrer Organisation zugewiesen wird.

In den folgenden Schritten wird beschrieben, wie Sie eine neue globale Voiceroutingrichtlinie für eine Organisation ohne Eine definieren. Wenn in Ihrer Organisation bereits Sprachroutingrichtlinien definiert sind, vergewissern Sie sich, dass die folgende Konfiguration nicht mit den vorhandenen Voice routingrichtlinien Ihrer Organisation in Konflikt steht.

Verwenden Sie den folgenden Befehl, um eine neue PSTN-Verwendung in einer Remote-PowerShell-Sitzung in Skype for Business Online zu erstellen:

  ```PowerShell
  Set-CsOnlinePstnUsage -Identity Global -Usage @{Add="International"}
  ```

Weitere Informationen finden Sie unter [Set-CsOnlinePstnUsage](/powershell/module/skype/set-csonlinepstnusage).

Verwenden Sie zum Erstellen einer neuen Sprachroute den folgenden Befehl:

  ```PowerShell
  New-CsOnlineVoiceRoute -Identity "International" -NumberPattern ".*" -OnlinePstnGatewayList sbc1.contoso.biz -OnlinePstnUsages "International"
  ```

Geben Sie beim Definieren einer neuen Sprachroute für Ihre Organisation ein oder mehrere der PSTN-Online-PSTN-Gateways an, die während der Konfiguration von Direct Routing für Ihre Organisation definiert wurden. 

Das Nummernmuster gibt an, welche Anrufe über die angegebene Liste der Gateways basierend auf der Zieltelefonnummer des Anrufs geroutet werden. Im vorstehenden Beispiel stimmen Anrufe an beliebige Ziele in der Welt mit der Sprachroute überein. Wenn Sie die Telefonnummern einschränken möchten, die aus den Besprechungen der Benutzer in Ihrer Organisation gewählt werden können, können Sie das Nummernmuster so ändern, dass die Sprachroute nur den Nummernmustern der zulässigen Ziele entspricht. Beachten Sie: Wenn keine Sprachrouten dem Nummernmuster der Zieltelefonnummer eines bestimmten Anrufs entsprechen, wird der Anruf nicht geroutet.

Weitere Informationen finden Sie unter [New-CsOnlineVoiceRoute](/powershell/module/skype/new-csonlinevoiceroute).

Verwenden Sie den folgenden Befehl, um eine neue Sprachroutingrichtlinie zu erstellen:

  ```PowerShell
  New-CsOnlineVoiceRoutingPolicy "InternationalVoiceRoutingPolicy" -OnlinePstnUsages "International"
  ```

Wenn in der Sprachroutingrichtlinie mehrere PSTN-Verwendungen definiert werden, werden sie in der Reihenfolge ausgewertet, in der sie definiert sind. Es wird empfohlen, die PSTN-Verwendungen in der Reihenfolge der spezifischsten für die generischen in Bezug auf die Zahlenmuster der den PSTN-Nutzungen zugeordneten Sprachrouten zu definieren. Wenn beispielsweise eine PSTN-Verwendung zum Weiterleiten von Anrufen in die USA definiert wurde und eine andere PSTN-Verwendung zum Weiterleiten von Anrufen an einen beliebigen anderen Ort auf der Welt definiert wurde, sollte die PSTN-Verwendung für Anrufe in die USA in der Sprachroutingrichtlinie vor der PSTN-Verwendung aufgeführt werden, um Anrufe an einen anderen Ort auf der Welt zu weiterleiten.

Weitere Informationen finden Sie unter [New-CsOnlineVoiceRoutingPolicy](/powershell/module/skype/new-csonlinevoiceroutingpolicy).

Verwenden Sie den folgenden Befehl, um der globalen Sprachroutingrichtlinie Ihrer Organisation die neue Sprachroute zuzuordnen:

  ```PowerShell
  Grant-CsOnlineVoiceRoutingPolicy -PolicyName "InternationalVoiceRoutingPolicy" -Global
  ```

Weitere Informationen finden Sie unter [Grant-CsOnlineVoiceRoutingPolicy](/powershell/module/skype/grant-csonlinevoiceroutingpolicy).

Sobald die globale Voiceroutingrichtlinie definiert wurde, werden alle ausgehenden Anrufe aus Besprechungen, die von Benutzern in Ihrer Organisation organisiert werden, anhand der Voicerouten ausgewertet, die den PSTN-Nutzungen der globalen Voiceroutingrichtlinie zugeordnet sind. Die ausgehenden Anrufe werden entsprechend der ersten Sprachroute, die dem Nummernmuster der gewählten Telefonnummer entspricht, geroutet.

### <a name="step-5-assign-audio-conferencing-with-direct-routing-for-gcc-high-or-dod-licenses-to-your-users"></a>Schritt 5: Zuweisen von Audiokonferenzen mit Direct Routing für GCC High- oder DoD-Lizenzen zu Ihren Benutzern

Informationen zum Zuweisen von Audiokonferenzen mit Direct Routing für GCC High- oder DoD-Lizenzen zu Ihrem Benutzer finden Sie unter Zuweisen von [Lizenzen zu Benutzern.](/microsoft-365/admin/manage/assign-licenses-to-users)

### <a name="step-6-optional-see-a-list-of-audio-conferencing-numbers-in-teams"></a>Schritt 6: (Optional) Eine Liste der Nummern für Audiokonferenzen in Teams

Wenn Sie die Liste der Audiokonferenznummern Ihrer Organisation sehen möchten, wechseln Sie zu Eine Liste der [Audiokonferenznummern in Microsoft Teams .](see-a-list-of-audio-conferencing-numbers-in-teams.md)

### <a name="step-7-optional-set-auto-attendant-languages-for-the-audio-conferencing-dial-in-numbers-of-you-organization"></a>Schritt 7: (Optional) Festlegen der automatischen Telefonkonferenzsprachen für die Einwahlnummern für Audiokonferenzen Ihrer Organisation

Informationen zum Ändern der Sprachen der Einwahlnummern für Audiokonferenzen Ihrer Organisation finden Sie unter Festlegen von automatischen Telefonierungssprachen für [Audiokonferenzen in Microsoft Teams.](set-auto-attendant-languages-for-audio-conferencing-in-teams.md)

### <a name="step-8-optional-change-the-settings-of-the-audio-conferencing-bridge-of-your-organization"></a>Schritt 8: (Optional) Ändern der Einstellungen der Audiokonferenzbrücke Ihrer Organisation

Informationen zum Ändern der Einstellungen der Audiokonferenzbrücke Ihrer Organisation finden Sie unter Ändern der Einstellungen für eine [Audiokonferenzbrücke.](change-the-settings-for-an-audio-conferencing-bridge.md)

### <a name="step-9-optional-set-the-phone-numbers-included-in-the-meeting-invites-of-the-users-in-your-organization"></a>Schritt 9: (Optional) Festlegen der Telefonnummern, die in den Besprechungs einladen der Benutzer in Ihrer Organisation enthalten sind

Informationen zum Ändern der Anzahl von Telefonnummern, die in den Besprechungs einladen der Benutzer enthalten sind, finden Sie unter Festlegen der Telefonnummern, die in Einladungen in Microsoft Teams enthalten [sind.](set-the-phone-numbers-included-on-invites-in-teams.md)

## <a name="audio-conferencing-capabilities-not-supported-in-audio-conferencing-with-direct-routing-for-gcc-high-and-dod"></a>Audiokonferenzfunktionen werden in Audiokonferenzen mit Direct Routing für GCC High und DoD nicht unterstützt

Die folgenden Funktionen sind Audiokonferenzen, die in Audiokonferenzen mit Direct Routing für GCC High und DoD nicht unterstützt werden:

- Benachrichtigungen zum Ein- und Beenden mithilfe der Namensaufzeichnung. Bei Audiokonferenzen mit Direct Routing werden Ein- und Ausgangsbenachrichtigungen in der Besprechung als Töne abgespielt.

- Richtlinien für Einschränkungen für ausgehende Anrufe für Audiokonferenzen. Steuerelemente auf Benutzerebene zum Einschränken ausgehender Anrufe gelten nicht für Besprechungsauswahlanrufe, die über direct Routing geroutet werden.

- Deaktivieren Sie die Verwendung gebührenfreier Nummern für den bestimmten Organisator von Besprechungen. Steuerelemente auf Benutzerebene, um die Nutzung gebührenfreier Nummern für die Teilnahme an Besprechungen Ihrer Organisation einzuschränken, gelten nicht für Anrufe, die über das Direct Routing geroutet werden.

- Senden von Benachrichtigungs-E-Mails an Benutzer, wenn sich deren Einstellungen ändern. Benachrichtigungs-E-Mails für Audiokonferenzen werden für Audiokonferenzen mit Direct Routing für GCC High und DoD nicht unterstützt.