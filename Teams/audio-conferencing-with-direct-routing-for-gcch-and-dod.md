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
description: Administratoren erfahren, wie Sie Audiokonferenzen mit Direct Routing in GGCH- und DoD-Umgebungen verwenden.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 818b36e379532e361fd3991b002bc899156af056
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2021
ms.locfileid: "49812915"
---
# <a name="audio-conferencing-with-direct-routing-for-gcc-high-and-dod"></a>Audiokonferenzen mit direktem Routing für GCC High und DoD

Audiokonferenzen mit direktem Routing für GCC High und DoD ermöglichen teilnehmern die Teilnahme an Teambesprechungen in Ihrer GCC High- oder DoD-Organisation über ein Telefongerät. Besprechungsteilnehmer bevorzugen möglicherweise ein Telefongerät, um an Teambesprechungen teilzunehmen, wenn beispielsweise die Internetverbindung eingeschränkt ist oder Benutzer unterwegs sind und keinen Zugriff auf Teams haben. Teilnehmer können an Besprechungen teilnehmen, indem sie sich entweder bei einer Einwahltelefonnummer für Ihre Organisation einwählen oder die Besprechung an ihrem Telefongerät anrufen lassen.

Mit Audiokonferenzen mit Direct Routing für GCC High und DoD verwendet Ihre Organisation eigene Nummern als Einwahltelefonnummern, und alle Einwahlkonferenzen zu Telefongeräten werden über direktes Routing geroutet. Um den Dienst zu aktivieren, müssen Organisationen Direct Routing einrichten und Telefonnummern konfigurieren, die als Einwahltelefonnummern verwendet werden können. Die Anforderung zur Verwendung von Direct Routing ist anders als der Audiokonferenzdienst, der für Organisationen ohne GCC High und Non-DoD angeboten wird, bei denen die Einwahltelefonnummern von Microsoft bereitgestellt werden.

## <a name="deploy-audio-conferencing-with-direct-routing-for-gcc-high-and-dod"></a>Bereitstellen von Audiokonferenzen mit direktem Routing für GCC High und DoD

### <a name="step-1-get-audio-conferencing-with-direct-routing-for-gcc-high-or-dod-licenses"></a>Schritt 1: Erhalten von Audiokonferenzen mit Direct Routing für GCC High- oder DoD-Lizenzen 

Um Audiokonferenzen in GCC High oder DoD verwenden zu können, müssen Ihre Organisation und die Benutzer in Ihrer Organisation über eine Lizenz für Audiokonferenzen mit Direct Routing verfügen. Hier sind die Lizenzen, die Sie zum Aktivieren von Audiokonferenzen mit Direct Routing für GCC High oder DoD benötigen.

- GCC High: An Audio Conferencing – GCC High Tenant license for your organization and Audio Conferencing - GCC High licenses for your users.

- DoD: Eine Audiokonferenz – DoD-Mandantenlizenz für Ihre Organisation und Audiokonferenzen – DoD-Lizenzen für Ihre Benutzer.

Zum Aktivieren des Diensts sind eine Mandantenlizenz und mindestens eine Benutzerlizenz erforderlich. Sie können den Dienst nicht nur mit der Mandantenlizenz oder nur mit Benutzerlizenzen aktivieren. Wenn Sie Servicelizenzen für Ihren Mandanten und die Benutzer in Ihrer Organisation erhalten möchten, wenden Sie sich an Ihr Kontoteam.

> [!IMPORTANT]
> Benutzer können für Audiokonferenzen mit Direct Routing erst aktiviert werden, wenn Einwahltelefonnummern eingerichtet sind. Es wird empfohlen, Benutzern erst dann Audiokonferenzen mit Direct Routing für GCC High- oder DoD-Lizenzen zuzuordnen, wenn Sie Einwahltelefonnummern wie in diesem Artikel beschrieben einrichten.

### <a name="step-2-set-up-direct-routing"></a>Schritt 2: Einrichten des direkten Routings

Informationen zum Einrichten von Direct Routing finden Sie in den folgenden Artikeln:

- [Planen von direktem Routing](direct-routing-plan.md)

- [Konfigurieren von direktem Routing](direct-routing-configure.md)

> [!NOTE]
> Denken Sie beim Einrichten des direkten Routings daran, die in diesen beiden Artikeln beschriebenen GCC High- oder DoD-spezifischen FQDNs und Ports zu verwenden.

### <a name="step-3-set-up-dial-in-phone-numbers"></a>Schritt 3: Einrichten von Einwahltelefonnummern

Einwahltelefonnummern sind die Telefonnummern, die Ihrer Audiokonferenzbrücke zugeordnet sind. Diese Nummern werden von Teilnehmern verwendet, um an Besprechungen teilzunehmen, die von Benutzern in Ihrer Organisation geplant wurden. Diese Nummern sind auch in den Besprechungsteilnehmern der Benutzer enthalten, die Besprechungen in Ihrer Organisation planen, und auf der Seite "Lokale Rufnummer suchen".

#### <a name="define-service-phone-numbers-in-your-tenant"></a>Definieren von Servicetelefonnummern in Ihrem Mandanten

Sie können das Cmdlet "New-csHybridTelephoneNumber PowerShell" verwenden, um Servicetelefonnummern in Ihrem Mandanten zu definieren, die zum Weiterleiten von Anrufen an den Audiokonferenzdienst über Direct Routing verwendet werden können. 

  ```PowerShell
  New-csHybridTelephoneNumber -TelephoneNumber <Phone number in E.164 format>
  ```

Beispiel:
  ```PowerShell
  New-csHybridTelephoneNumber -TelephoneNumber "+14250000000"
  ```

#### <a name="assign-the-service-phone-numbers-to-the-audio-conferencing-bridge-of-your-organization"></a>Zuweisen der Servicetelefonnummern zur Audiokonferenzbrücke Ihrer Organisation

Sie können der Audiokonferenzbrücke Ihrer Organisation Servicetelefonnummern zuweisen, indem Sie das Cmdlet Register-csOnlineDialInConferencingServiceNumber PowerShell verwenden.

  ```PowerShell
  Register-csOnlineDialInConferencingServiceNumber -identity <Telephone number in E.164 format> -BridgeId <Identity of the audio conferencing bridge>
  ```

Sie können die ID Ihrer Audiokonferenzbrücke mithilfe von Get-CsOnlineDialInConferencingBridge sehen. Beispiel:

  ```PowerShell
  $b= Get-CsOnlineDialInConferencingBridge
  Register-csOnlineDialInConferencingServiceNumber -identity 14257048060 -BridgeId $b.identity
  ```


### <a name="step-4-define-a-global-voice-routing-policy-to-enable-the-routing-of-outbound-calls-from-meetings"></a>Schritt 4: Definieren einer globalen Voiceroutingrichtlinie zum Aktivieren des Routings ausgehender Anrufe von Besprechungen

Das Routing ausgehender Anrufe, die über Besprechungen, die von Benutzern in Ihrer Organisation organisiert werden, an das PSTN erfolgt, ist durch die globale Voiceroutingrichtlinie Ihrer Organisation definiert. Wenn für Ihre Organisation eine richtlinie für globales Voicerouting definiert ist, stellen Sie sicher, dass die Richtlinie für globales Voicerouting ausgehende Anrufe an das PSTN zulässt, die aus Besprechungen initiiert werden sollen, die von Benutzern in Ihrer Organisation organisiert werden. Wenn in Ihrer Organisation keine Richtlinie für globales Voicerouting definiert ist, müssen Sie eine richtlinie definieren, um das Routing ausgehender Anrufe an das PSTN von Besprechungen zu ermöglichen, die von Benutzern in Ihrer Organisation organisiert werden. Beachten Sie, dass die globale Voiceroutingrichtlinie Ihrer Organisation auch für 1:1-Anrufe von Benutzern in Ihrer Organisation an das FESTNETZ gilt. Wenn 1:1-Anrufe an das Festnetz für Benutzer in Ihrer Organisation aktiviert sind, stellen Sie sicher, dass die Richtlinie für globales Voicerouting die Anforderungen Ihrer Organisation für beide Arten von Anrufen erfüllt. 

> [!NOTE]
> Location-Based Routing ist in Bereitstellungen mit dem High- oder DoD-Speicher der Microsoft 365 Government Community Cloud (GCC) nicht verfügbar. Stellen Sie beim Aktivieren von Audiokonferenzen sicher, dass keine Benutzer von Audiokonferenzen in der GCC High- oder der DoD-Umgebung für das Routing Location-Based sind.

#### <a name="defining-a-global-voice-routing-policy"></a>Definieren einer globalen Voiceroutingrichtlinie

Eine globale Voiceroutingrichtlinie kann definiert werden, indem Sie eine PSTN-Verwendung, eine Sprachroute und eine Sprachroutingrichtlinie definieren und die neue Voiceroutingrichtlinie als globale Voiceroutingrichtlinie Ihrer Organisation zuweisen.

Die folgenden Schritte beschreiben, wie Sie eine neue globale Voiceroutingrichtlinie für eine Organisation ohne Eine definieren. Wenn in Ihrer Organisation bereits Richtlinien für das Voicerouting definiert sind, stellen Sie sicher, dass die folgende Konfiguration nicht mit den vorhandenen Voiceroutingrichtlinien Ihrer Organisation in Konflikt steht.

Verwenden Sie den folgenden Befehl, um eine neue PstN-Verwendung in einer Remote-PowerShell-Sitzung in Skype for Business Online zu erstellen:

  ```PowerShell
  Set-CsOnlinePstnUsage -Identity Global -Usage @{Add="International"}
  ```

Weitere Informationen finden Sie unter ["Set-CsOnlinePstnUsage".](https://docs.microsoft.com/powershell/module/skype/set-csonlinepstnusage)

Verwenden Sie den folgenden Befehl, um eine neue Sprachroute zu erstellen:

  ```PowerShell
  New-CsOnlineVoiceRoute -Identity "International" -NumberPattern ".*" -OnlinePstnGatewayList sbc1.contoso.biz -OnlinePstnUsages "International"
  ```

Geben Sie beim Definieren einer neuen Sprachroute für Ihre Organisation ein oder mehrere PSTN Online-PSTN-Gateways an, die für Ihre Organisation während der Konfiguration von Direct Routing definiert wurden. 

Das Nummernmuster gibt basierend auf der Zieltelefonnummer des Anrufs an, welche Anrufe über die angegebene Liste der Gateways geroutet werden. Im vorstehenden Beispiel stimmen Anrufe an beliebige Ziele in der Welt mit der Sprachroute überein. Wenn Sie die Telefonnummern einschränken möchten, die aus Besprechungen von Benutzern in Ihrer Organisation gewählt werden können, können Sie das Nummernmuster so ändern, dass die Sprachroute nur den Nummernmustern der zulässigen Ziele entspricht. Beachten Sie, dass keine Sprachrouten, die dem Nummernmuster der Zieltelefonnummer eines bestimmten Anrufs entsprechen, nicht geroutet werden.

Weitere Informationen finden Sie unter ["New-CsOnlineVoiceRoute".](https://docs.microsoft.com/powershell/module/skype/new-csonlinevoiceroute)

Verwenden Sie den folgenden Befehl, um eine neue Sprachroutingrichtlinie zu erstellen:

  ```PowerShell
  New-CsOnlineVoiceRoutingPolicy "InternationalVoiceRoutingPolicy" -OnlinePstnUsages "International"
  ```

Wenn mehrere PstN-Nutzungen in der Sprachroutingrichtlinie definiert werden, werden sie in der Reihenfolge ausgewertet, in der sie definiert sind. Es wird empfohlen, die PstN-Nutzungen in der Reihenfolge der spezifischesten für allgemeinere Benutzer in Bezug auf die Nummernmuster der Sprachrouten zu definieren, die mit den PstN-Nutzungen verknüpft sind. Wenn z. B. eine Verwendung des öffentlichen Telefonnetz zum Weiterleiten von Anrufen in die USA definiert wurde und eine andere Nutzung des öffentlichen Telefonnetz zum Weiterleiten von Anrufen an einen beliebigen anderen Ort auf der Welt definiert wurde, sollte die PstN-Nutzung für Anrufe in die VEREINIGTEn Staaten vor der Verwendung des PstNs in der Richtlinie für das Sprachrouting aufgeführt werden, um Anrufe an beliebige andere Standorte auf der Welt weiterleiten zu können.

Weitere Informationen finden Sie unter ["New-CsOnlineVoiceRoutingPolicy".](https://docs.microsoft.com/powershell/module/skype/new-csonlinevoiceroutingpolicy)

Um die neue Sprachroute der globalen Voiceroutingrichtlinie Ihrer Organisation zuzuordnen, verwenden Sie den folgenden Befehl:

  ```PowerShell
  Grant-CsOnlineVoiceRoutingPolicy -PolicyName "InternationalVoiceRoutingPolicy" -Global
  ```

Weitere Informationen finden Sie unter [Grant-CsOnlineVoiceRoutingPolicy.](https://docs.microsoft.com/powershell/module/skype/grant-csonlinevoiceroutingpolicy)

Nachdem die Richtlinie für globales Voicerouting definiert wurde, werden alle ausgehenden Anrufe aus Besprechungen, die von Benutzern in Ihrer Organisation organisiert werden, anhand der Sprachrouten ausgewertet, die den PstN-Nutzungen der globalen Voiceroutingrichtlinie zugeordnet sind. Die ausgehenden Anrufe werden entsprechend der ersten Sprachroute geroutet, die dem Nummernmuster der gewählten Telefonnummer entspricht.

### <a name="step-5-assign-audio-conferencing-with-direct-routing-for-gcc-high-or-dod-licenses-to-your-users"></a>Schritt 5: Zuweisen von Audiokonferenzen mit Direct Routing für GCC High- oder DoD-Lizenzen zu Ihren Benutzern

Informationen zum Zuweisen von Audiokonferenzen mit Direct Routing für GCC High- oder DoD-Lizenzen zu Einem Benutzer finden Sie unter "Zuweisen von [Lizenzen zu Benutzern".](https://docs.microsoft.com/microsoft-365/admin/manage/assign-licenses-to-users)

### <a name="step-6-optional-see-a-list-of-audio-conferencing-numbers-in-teams"></a>Schritt 6: (Optional) Eine Liste der Nummern für Audiokonferenzen in Teams

Wenn Sie die Liste der Audiokonferenznummern Ihrer Organisation sehen möchten, wechseln Sie zu einer Liste der Audiokonferenznummern [in Microsoft Teams.](see-a-list-of-audio-conferencing-numbers-in-teams.md)

### <a name="step-7-optional-set-auto-attendant-languages-for-the-audio-conferencing-dial-in-numbers-of-you-organization"></a>Schritt 7: (Optional) Festlegen der Sprachen für die automatische Telefonkonferenz für die Einwahlnummern Ihrer Organisation

Informationen zum Ändern der Sprachen der Einwahlnummern für Audiokonferenzen Ihrer Organisation finden Sie unter "Festlegen der Sprachen für die automatische Telefonkonferenz [in Microsoft Teams".](set-auto-attendant-languages-for-audio-conferencing-in-teams.md)

### <a name="step-8-optional-change-the-settings-of-the-audio-conferencing-bridge-of-your-organization"></a>Schritt 8: (Optional) Ändern der Einstellungen der Audiokonferenzbrücke Ihrer Organisation

Informationen zum Ändern der Einstellungen der Audiokonferenzbrücke Ihrer Organisation finden Sie unter Ändern der Einstellungen für eine [Audiokonferenzbrücke.](change-the-settings-for-an-audio-conferencing-bridge.md)

### <a name="step-9-optional-set-the-phone-numbers-included-in-the-meeting-invites-of-the-users-in-your-organization"></a>Schritt 9: (Optional) Festlegen der Telefonnummern, die in den Besprechungsteilnehmern der Benutzer in Ihrer Organisation enthalten sind

Informationen zum Ändern der Telefonnummern, die in den Besprechungsteilnehmern der Benutzer in Ihrer Organisation enthalten sind, finden Sie unter "Festlegen der Telefonnummern, die in Einladungen in Microsoft Teams enthalten [sind".](set-the-phone-numbers-included-on-invites-in-teams.md)

## <a name="audio-conferencing-capabilities-not-supported-in-audio-conferencing-with-direct-routing-for-gcc-high-and-dod"></a>Audiokonferenzfunktionen werden in Audiokonferenzen mit Direct Routing für GCC High und DoD nicht unterstützt

Es folgen Audiokonferenzfunktionen, die in Audiokonferenzen mit direktem Routing für GCC High und DoD nicht unterstützt werden:

- Benachrichtigungen beim Ein- und Beenden mithilfe der Namensaufzeichnung Bei Audiokonferenzen mit direktem Routing werden Eingangs- und Ausgangsbenachrichtigungen in der Besprechung als Töne abgespielt.

- Einschränkungsrichtlinien für ausgehende Anrufe für Audiokonferenzen. Steuerelemente auf Benutzerebene zum Einschränken ausgehender Anrufe gelten nicht für Ausgehende Anrufe in Besprechungen, die über direktes Routing geroutet werden.

- Deaktivieren Sie die Verwendung von gebührenfreien Nummern für den Organisator von Besprechungen. Steuerelemente auf Benutzerebene zum Einschränken der Verwendung von gebührenfreien Nummern für die Teilnahme an Besprechungen in Ihrer Organisation gelten nicht für Anrufe, die über direct Routing geroutet werden.

- Senden von Benachrichtigungs-E-Mails an Benutzer, wenn sich deren Einstellungen ändern. E-Mails für Audiokonferenzbenachrichtigungen werden für Audiokonferenzen mit Direktes Routing für GCC High und DoD nicht unterstützt.
