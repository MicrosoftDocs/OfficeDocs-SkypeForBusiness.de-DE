---
title: Audio Conferencing with Direct Routing, GCCH and DoD
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
description: Der Administrator kann erfahren, wie Sie Audio conferencing (Audiokonferenz) mit Direct Routing in GCCH- und DoD-Umgebungen verwenden.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 4daea8636ce99ed711d7fd982cd42eb9aa8c6b93
ms.sourcegitcommit: b39bd1de0219a9e3a3b0c97fc485c9578ddb643c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/01/2021
ms.locfileid: "53230582"
---
# <a name="audio-conferencing-with-direct-routing-for-gcc-high-and-dod"></a>Audiokonferenzen mit direktem Routing für GCC High und DoD

Audiokonferenzen mit Direct Routing für GCC High und DoD ermöglichen Teilnehmern die Teilnahme an Teams-Besprechungen in Ihrer GCC High- oder DoD-Organisation über ein Telefongerät. Besprechungsteilnehmer bevorzugen möglicherweise ein Telefongerät für die Teilnahme an Teams-Besprechungen in Szenarien, z. B. wenn die Internetverbindung eingeschränkt ist oder Benutzer unterwegs sind und keinen Zugriff auf Teams. Teilnehmer können an Besprechungen teilnehmen, indem sie sich entweder bei einer Einwahltelefonnummer für Ihre Organisation einwählen oder die Besprechung auf ihrem Telefongerät anrufen lassen.

Mit Audiokonferenzen mit Direct Routing für GCC High und DoD verwendet Ihre Organisation eigene Nummern als Einwahltelefonnummern, und alle Einwahlkonferenzen an Telefongeräte werden über Direct Routing geroutet. Um den Dienst zu aktivieren, müssen Organisationen Direct Routing einrichten und Telefonnummern konfigurieren, die als Einwahltelefonnummern verwendet werden können. Die Anforderung zur Verwendung von Direct Routing ist anders als der Audiokonferenzdienst, der für Nicht-GCC High- und Nicht-DoD-Organisationen angeboten wird, bei denen die Einwahltelefonnummern von Microsoft bereitgestellt werden.

## <a name="deploy-audio-conferencing-with-direct-routing-for-gcc-high-and-dod"></a>Bereitstellen von Audiokonferenzen mit Direct Routing für GCC High und DoD

### <a name="step-1-get-audio-conferencing-with-direct-routing-for-gcc-high-or-dod-licenses"></a>Schritt 1: Erhalten von Audiokonferenzen mit Direct Routing für GCC High- oder DoD-Lizenzen 

Wenn Sie Audiokonferenzen in GCC High oder DoD verwenden möchten, müssen Ihre Organisation und die Benutzer in Ihrer Organisation über eine Lizenz für Audiokonferenzen mit Direct Routing verfügen. Hier sind die Lizenzen, die Sie benötigen, um Audiokonferenzen mit Direct Routing für GCC High oder DoD zu aktivieren.

- GCC Hoch: Eine Audiokonferenz – GCC Lizenz für hohe Mandanten für Ihre Organisation und Audiokonferenzen – GCC Hohe Lizenzen für Ihre Benutzer.

- DoD: Eine Lizenz für Audiokonferenzen – DoD Tenant für Ihre Organisation und Audiokonferenz – DoD-Lizenzen für Ihre Benutzer.

Zum Aktivieren des Diensts sind eine Mandantenlizenz und mindestens eine Benutzerlizenz erforderlich. Sie können den Dienst nicht nur mit der Mandantenlizenz oder nur mit Benutzerlizenzen aktivieren. Wenn Sie Servicelizenzen für Ihren Mandanten und die Benutzer in Ihrer Organisation erhalten möchten, wenden Sie sich an Ihr Kontoteam.

> [!IMPORTANT]
> Benutzer können erst dann für Audiokonferenzen mit Direct Routing aktiviert werden, wenn Einwahltelefonnummern eingerichtet wurden. Es wird empfohlen, Benutzern erst dann Audiokonferenzen mit Direct Routing für GCC High oder DoD-Lizenzen zuzuordnen, wenn Sie Einwahltelefonnummern wie in diesem Artikel beschrieben eingerichtet haben.  Wenn Sie diese Anleitung nicht befolgen, fehlt die Wähltaste möglicherweise vollständig im Teams Client.

### <a name="step-2-set-up-direct-routing"></a>Schritt 2: Einrichten von Direct Routing

Informationen zum Einrichten von Direct Routing finden Sie in den folgenden Artikeln:

- [Planen von direktem Routing](direct-routing-plan.md)

- [Konfigurieren von direktem Routing](direct-routing-configure.md)

> [!NOTE]
> Denken Sie beim Einrichten von Direct Routing daran, die GCC High- oder DoD-spezifischen FQDNs und Ports zu verwenden, die in diesen beiden Artikeln beschrieben werden.

### <a name="step-3-set-up-dial-in-phone-numbers"></a>Schritt 3: Einrichten von Einwahltelefonnummern

Einwahltelefonnummern sind die Telefonnummern, die Ihrer Audiokonferenzbrücke zugeordnet sind. Diese Nummern werden von Teilnehmern verwendet, um an Besprechungen teilzunehmen, die von Benutzern in Ihrer Organisation geplant wurden. Diese Nummern sind auch in den Besprechungsterminen der Benutzer enthalten, die Besprechungen in Ihrer Organisation planen und auf der Seite "Lokale Rufnummer suchen".

#### <a name="define-service-phone-numbers-in-your-tenant"></a>Definieren von Servicetelefonnummern in Ihrem Mandanten

Sie können das PowerShell-Cmdlet New-csHybridTelephoneNumber verwenden, um Servicetelefonnummern in Ihrem Mandanten zu definieren, mit deren Hilfe Anrufe über Direct Routing an den Audiokonferenzdienst weiterleiten werden können. 

  ```PowerShell
  New-csHybridTelephoneNumber -TelephoneNumber <Phone number in E.164 format>
  ```

Beispiel:
  ```PowerShell
  New-csHybridTelephoneNumber -TelephoneNumber "+14250000000"
  ```

#### <a name="assign-the-service-phone-numbers-to-the-audio-conferencing-bridge-of-your-organization"></a>Zuweisen der Servicetelefonnummern zur Audiokonferenzbrücke Ihrer Organisation

Sie können der Audiokonferenzbrücke Ihrer Organisation Servicetelefonnummern zuweisen, indem Sie das PowerShell-Cmdlet Register-csOnlineDialInConferencingServiceNumber verwenden.

  ```PowerShell
  Register-csOnlineDialInConferencingServiceNumber -identity <Telephone number in E.164 format> -BridgeId <Identity of the audio conferencing bridge>
  ```

Sie können die ID Ihrer Audiokonferenzbrücke mithilfe von Get-CsOnlineDialInConferencingBridge sehen. Beispiel:

  ```PowerShell
  $b= Get-CsOnlineDialInConferencingBridge
  Register-csOnlineDialInConferencingServiceNumber -identity 14257048060 -BridgeId $b.identity
  ```


### <a name="step-4-define-a-global-voice-routing-policy-to-enable-the-routing-of-outbound-calls-from-meetings"></a>Schritt 4: Definieren einer globalen Voiceroutingrichtlinie zum Aktivieren des Routings ausgehender Anrufe von Besprechungen

Das Routing ausgehender Anrufe an das PSTN von Besprechungen, die von Benutzern in Ihrer Organisation organisiert werden, wird durch die globale Voiceroutingrichtlinie Ihrer Organisation definiert. Wenn für Ihre Organisation eine globale Voiceroutingrichtlinie definiert ist, überprüfen Sie, ob die globale Voiceroutingrichtlinie ausgehende Anrufe an das PSTN zulässt, die aus Besprechungen initiiert werden sollen, die von Benutzern in Ihrer Organisation organisiert wurden. Wenn für Ihre Organisation keine globale Voiceroutingrichtlinie definiert ist, müssen Sie eine richtlinie definieren, um das Routing ausgehender Anrufe von Besprechungen an das PSTN zu ermöglichen, die von Benutzern in Ihrer Organisation organisiert werden. Beachten Sie, dass die globale Voiceroutingrichtlinie Ihrer Organisation auch für 1:1-Anrufe gilt, die von Benutzern in Ihrer Organisation an das PSTN vorgenommen werden. Wenn 1:1-Anrufe bei der PSTN-Verbindung für Benutzer in Ihrer Organisation aktiviert sind, stellen Sie sicher, dass die globale Voiceroutingrichtlinie den Anforderungen Ihrer Organisation an beide Arten von Anrufen entspricht. 

> [!NOTE]
> Location-Based Routing ist in Bereitstellungen mit hohen Microsoft 365 Government Community Cloud (GCC) oder DoD nicht verfügbar. Stellen Sie beim Aktivieren von Audiokonferenzen sicher, dass keine Audiokonferenzbenutzer in der GCC High- oder DoD-Umgebung für das Routing Location-Based sind.

#### <a name="defining-a-global-voice-routing-policy"></a>Definieren einer globalen Voiceroutingrichtlinie

Eine globale Voice Routing-Richtlinie kann definiert werden, indem eine PSTN-Nutzung, eine Voiceroute und eine Voice Routing-Richtlinie definiert und die neue Voice Routing-Richtlinie als globale Voice Routing-Richtlinie Ihrer Organisation zugewiesen wird.

Die folgenden Schritte beschreiben, wie Sie eine neue globale Voiceroutingrichtlinie für eine Organisation ohne Richtlinie definieren. Wenn in Ihrer Organisation bereits Sprachroutingrichtlinien definiert sind, stellen Sie sicher, dass die folgende Konfiguration nicht mit den vorhandenen Voice Routingrichtlinien Ihrer Organisation in Konflikt steht.

Um eine neue PSTN-Verwendung in einer PowerShell-Remotesitzung in Skype for Business Online zu erstellen, verwenden Sie den folgenden Befehl:

  ```PowerShell
  Set-CsOnlinePstnUsage -Identity Global -Usage @{Add="International"}
  ```

Weitere Informationen finden Sie unter [Set-CsOnlinePstnUsage.](/powershell/module/skype/set-csonlinepstnusage)

Verwenden Sie zum Erstellen einer neuen Sprachroute den folgenden Befehl:

  ```PowerShell
  New-CsOnlineVoiceRoute -Identity "International" -NumberPattern ".*" -OnlinePstnGatewayList sbc1.contoso.biz -OnlinePstnUsages "International"
  ```

Geben Sie beim Definieren einer neuen Voiceroute für Ihre Organisation ein oder mehrere PSTN-Online-PSTN-Gateways an, die während der Konfiguration von Direct Routing für Ihre Organisation definiert wurden. 

Das Nummernmuster gibt an, welche Anrufe basierend auf der Zieltelefonnummer des Anrufs über die angegebene Liste der Gateways geroutet werden. Im vorstehenden Beispiel stimmen Anrufe an Ziele in der Welt mit der Sprachroute überein. Wenn Sie die Telefonnummern einschränken möchten, die aus Besprechungen von Benutzern in Ihrer Organisation gewählt werden können, können Sie das Nummernmuster so ändern, dass die Sprachroute nur den Nummernmustern der zulässigen Ziele entspricht. Beachten Sie: Wenn keine Sprachrouten mit dem Nummernmuster der Zieltelefonnummer eines bestimmten Anrufs übereinstimmen, wird der Anruf nicht geroutet.

Weitere Informationen finden Sie unter [New-CsOnlineVoiceRoute.](/powershell/module/skype/new-csonlinevoiceroute)

Verwenden Sie zum Erstellen einer neuen Voice Routing-Richtlinie den folgenden Befehl:

  ```PowerShell
  New-CsOnlineVoiceRoutingPolicy "InternationalVoiceRoutingPolicy" -OnlinePstnUsages "International"
  ```

Wenn in der Sprachroutingrichtlinie mehrere PSTN-Nutzungen definiert sind, werden sie in der Reihenfolge ausgewertet, in der sie definiert sind. Es wird empfohlen, die PSTN-Nutzungen in der Reihenfolge der spezifischesten für die allgemeineren in Bezug auf die Nummernmuster der Sprachrouten, die den PSTN-Nutzungen zugeordnet sind, zu definieren. Wenn beispielsweise eine PSTN-Nutzung zum Weiterleiten von Anrufen an die USA und eine andere PSTN-Nutzung zum Weiterleiten von Anrufen an einen beliebigen anderen Ort weltweit definiert wurde, sollte die PSTN-Nutzung für Anrufe in die USA in der Sprachroutingrichtlinie vor der PSTN-Nutzung aufgeführt sein, um Anrufe an andere Standorte in der Welt weiter zu routen.

Weitere Informationen finden Sie unter [New-CsOnlineVoiceRoutingPolicy.](/powershell/module/skype/new-csonlinevoiceroutingpolicy)

Um die neue Voiceroute der globalen Voiceroutingrichtlinie Ihrer Organisation zuzuordnen, verwenden Sie den folgenden Befehl:

  ```PowerShell
  Grant-CsOnlineVoiceRoutingPolicy -PolicyName "InternationalVoiceRoutingPolicy" -Global
  ```

Weitere Informationen finden Sie unter [Grant-CsOnlineVoiceRoutingPolicy.](/powershell/module/skype/grant-csonlinevoiceroutingpolicy)

Nachdem die globale Voiceroutingrichtlinie definiert wurde, werden alle ausgehenden Anrufe, die von Benutzern in Ihrer Organisation organisiert werden, anhand der Voicerouten ausgewertet, die den PSTN-Verwendungen der globalen Voiceroutingrichtlinie zugeordnet sind. Die ausgehenden Anrufe werden gemäß der ersten Sprachroute geroutet, die dem Nummernmuster der gewählten Telefonnummer entspricht.

### <a name="step-5-assign-audio-conferencing-with-direct-routing-for-gcc-high-or-dod-licenses-to-your-users"></a>Schritt 5: Zuweisen von Audiokonferenzen mit Direct Routing für GCC High- oder DoD-Lizenzen zu Ihren Benutzern

Informationen zum Zuweisen von Audiokonferenzen mit Direct Routing für GCC High- oder DoD-Lizenzen finden Sie unter Zuweisen von [Lizenzen zu Benutzern.](/microsoft-365/admin/manage/assign-licenses-to-users)

### <a name="step-6-optional-see-a-list-of-audio-conferencing-numbers-in-teams"></a>Schritt 6: (Optional) Sie sehen eine Liste der Audiokonferenznummern in Teams

Wenn Sie die Liste der Audiokonferenznummern Ihrer Organisation sehen möchten, wechseln Sie zu Eine Liste der [Audiokonferenznummern in Microsoft Teams.](see-a-list-of-audio-conferencing-numbers-in-teams.md)

### <a name="step-7-optional-set-auto-attendant-languages-for-the-audio-conferencing-dial-in-numbers-of-you-organization"></a>Schritt 7: (Optional) Festlegen der Sprachen der automatischen Telefonhalter für die Einwahlnummern für Audiokonferenzen Ihrer Organisation

Informationen zum Ändern der Sprachen der Einwahlnummern für Audiokonferenzen Ihrer Organisation finden Sie unter Festlegen der Sprachen für die automatische Telefonkonferenz [in Microsoft Teams.](set-auto-attendant-languages-for-audio-conferencing-in-teams.md)

### <a name="step-8-optional-change-the-settings-of-the-audio-conferencing-bridge-of-your-organization"></a>Schritt 8: (Optional) Ändern der Einstellungen der Audiokonferenzbrücke Ihrer Organisation

Informationen zum Ändern der Einstellungen der Audiokonferenzbrücke Ihrer Organisation finden Sie unter Ändern der Einstellungen für eine [Audiokonferenzbrücke.](change-the-settings-for-an-audio-conferencing-bridge.md)

### <a name="step-9-optional-set-the-phone-numbers-included-in-the-meeting-invites-of-the-users-in-your-organization"></a>Schritt 9: (Optional) Festlegen der Telefonnummern, die in den Besprechungsteilnehmern der Benutzer in Ihrer Organisation enthalten sind

Informationen zum Ändern der Telefonnummern, die in den Besprechungsanrufen der Benutzer enthalten sind, sind in Ihrer Organisation enthalten. Informationen dazu finden Sie unter Festlegen der In Einladungen enthaltenen Telefonnummern [in Microsoft Teams.](set-the-phone-numbers-included-on-invites-in-teams.md)

## <a name="audio-conferencing-capabilities-not-supported-in-audio-conferencing-with-direct-routing-for-gcc-high-and-dod"></a>Audiokonferenzfunktionen werden in Audiokonferenzen mit Direct Routing für GCC High und DoD nicht unterstützt

Im Folgenden werden Audiokonferenzfunktionen, die in Audiokonferenzen mit Direct Routing für GCC High und DoD nicht unterstützt werden:

- Benachrichtigungen beim Ein- und Beenden mithilfe der Namensaufzeichnung. Bei Audiokonferenzen mit Direct Routing werden Eingangs- und Ausgangsbenachrichtigungen in der Besprechung als Töne abgespielt.

- Deaktivieren Sie die Verwendung gebührenfreier Telefonnummern für den jeweiligen Organisator von Besprechungen. Steuerelemente auf Benutzerebene, die die Nutzung gebührenfreier Nummern für die Teilnahme an Besprechungen in Ihrer Organisation einschränken, gelten nicht für Anrufe, die über Direct Routing geroutet werden.

- Senden von Benachrichtigungs-E-Mails an Benutzer, wenn sich deren Einstellungen ändern. Benachrichtigungs-E-Mails für Audiokonferenzen werden für Audiokonferenzen mit Direct Routing für GCC High und DoD nicht unterstützt.
