---
title: Audiokonferenzen mit direktem Routing für GCCH und DoD
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
description: Hier erfahren Sie, wie Sie Audiokonferenzen mit direktem Routing in GCCH-und DoD-Umgebungen verwenden können.
ms.openlocfilehash: 8304d18777739b4667c0f47b9dee3e9f8f6dcc38
ms.sourcegitcommit: bfa5b8db4e42e0480542d61fe05716c52016873c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2020
ms.locfileid: "41825653"
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
  New-csHybridTelephoneNumber -TelephoneNumber “+14250000000”
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

### <a name="step-4-assign-audio-conferencing-with-direct-routing-for-gcc-high-or-dod-licenses-to-your-users"></a>Schritt 4: Zuweisen von Audiokonferenzen mit Direct Routing für gcc-höchst-oder DoD-Lizenzen für Ihre Benutzer

Informationen zum Zuweisen von Audiokonferenzen mit direktem Routing für gcc-oder DoD-Lizenzen für Ihre Benutzer finden Sie unter [Zuweisen von Lizenzen zu Benutzern in Office 365 for Business](https://docs.microsoft.com/en-us/office365/admin/subscriptions-and-billing/assign-licenses-to-users).

### <a name="step-5-optional-see-a-list-of-audio-conferencing-numbers-in-teams"></a>Schritt 5: (optional) Anzeigen einer Liste der Audiokonferenz-Nummern in Teams

Wenn Sie die Liste der Audiokonferenz-Nummern Ihrer Organisation anzeigen möchten, wechseln [Sie zu einer Liste der Audiokonferenz-Nummern in Microsoft Teams](see-a-list-of-audio-conferencing-numbers-in-teams.md) .

### <a name="step-6-optional-set-auto-attendant-languages-for-the-audio-conferencing-dial-in-numbers-of-you-organization"></a>Schritt 6: (optional) festlegen der Sprachen der automatischen Telefonzentrale für die Einwahlnummern für Audiokonferenzen Ihrer Organisation

Informationen zum Ändern der Sprachen der Einwahlnummern für Audiokonferenzen in Ihrer Organisation finden Sie unter [Festlegen von Sprachen für die automatische Telefonzentrale für Audiokonferenzen in Microsoft Teams](set-auto-attendant-languages-for-audio-conferencing-in-teams.md) .

### <a name="step-7-optional-change-the-settings-of-the-audio-conferencing-bridge-of-your-organization"></a>Schritt 7: (optional) Ändern der Einstellungen der Audiokonferenz-Brücke in Ihrer Organisation

Informationen zum Ändern der Einstellungen der Audiokonferenz-Brücke in Ihrer Organisation finden Sie unter [Ändern der Einstellungen für eine Audiokonferenz-Brücke](change-the-settings-for-an-audio-conferencing-bridge.md) .

### <a name="step-8-optional-set-the-phone-numbers-included-in-the-meeting-invites-of-the-users-in-your-organization"></a>Schritt 8: (optional) festlegen der Telefonnummern, die in den Besprechungseinladungen der Benutzer in Ihrer Organisation enthalten sind

Informationen zum Ändern der Gruppe von Telefonnummern, die in den Besprechungseinladungen der Benutzer enthalten sind, finden Sie unter [Festlegen der Telefonnummern, die in Einladungen in Microsoft Teams enthalten](set-the-phone-numbers-included-on-invites-in-teams.md) sind.

## <a name="audio-conferencing-capabilities-not-supported-in-audio-conferencing-with-direct-routing-for-gcc-high-and-dod"></a>Audiokonferenzfunktionen, die in Audiokonferenzen nicht unterstützt werden, mit direktem Routing für gcc-höchst-und DoD-Funktionen

Im folgenden finden Sie Audiokonferenzfunktionen, die bei Audiokonferenzen mit direktem Routing für gcc-höchst-und DoD-Funktionen nicht unterstützt werden:

- Eingabe-und Exit-Benachrichtigungen mithilfe der namens Aufzeichnung. Bei Audiokonferenzen mit direktem Routing werden die Eingabe-und Exit-Benachrichtigungen als Töne in der Besprechung abgespielt.

- Richtlinien für ausgehende Anruf Einschränkungen für Audiokonferenzen. Steuerelemente auf Benutzerebene zum Einschränken ausgehender Anrufe gelten nicht für von der direkten Weiterleitung weitergeleitete Anrufe an eingehende Anrufe.

- Deaktivieren Sie die Verwendung von gebührenfreien Nummern für den Besprechungs spezifischen Organisator. Steuerelemente auf Benutzerebene, um die Verwendung von gebührenfreien Nummern für die Teilnahme an den Besprechungen Ihrer Organisation zu beschränken, gelten nicht für Anrufe, die über direktes Routing weitergeleitet werden.

- Senden von Benachrichtigungs-e-Mails an Benutzer, wenn sich Ihre Einstellungen ändern Audiokonferenz-Benachrichtigungs-e-Mails werden für Audiokonferenzen mit direktem Routing für gcc-höchst-und DoD nicht unterstützt.
