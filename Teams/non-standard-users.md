---
title: Teams Das Verhalten von Apps basierend auf Benutzertypen
author: guptaashish
ms.author: guptaashish
ms.reviewer: joglocke
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: Erfahren Sie, wie sich Apps in Microsoft Teams für unterschiedliche Benutzertypen verhalten.
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
- m365initiative-meetings
appliesto:
- Microsoft Teams
ms.openlocfilehash: a407564986d5e4c758d39e2684e5c068539bb9dc
ms.sourcegitcommit: 1d990582e2deb5f55ba9adada3e17377f792a141
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/19/2022
ms.locfileid: "64922466"
---
# <a name="microsoft-teams-apps-behavior-based-on-types-of-users"></a>Microsoft Teams Das Verhalten von Apps basierend auf Benutzertypen

Teams Apps verhalten sich, wenn Gastbenutzer, externe Benutzer (Verbundbenutzer) und anonyme Benutzer in einem Teams Kontext vorhanden sind.

* Ein **Gastbenutzer** ist eine Person, die kein Mitarbeiter, Student oder Mitglied Ihrer Organisation ist. Er verfügt über kein Geschäfts-, Schul- oder Unikonto bei Ihrer Organisation.

* Ein **externer Benutzer (Verbundbenutzer)** gehört zu einer anderen Domäne und hat keinen Zugriff auf die Teams oder Teamressourcen Ihrer Organisation.

  > [!Note]
  > Einen detaillierteren Vergleich zwischen Gastbenutzern und externen Benutzern [finden Sie in der Kommunikation mit Benutzern aus anderen Organisationen](./communicate-with-users-from-other-organizations.md).

* Ein **anonymer Benutzer** ist ein Konzept in Teams Besprechungen, in denen der Benutzer über einen Link an der Besprechung teilgenommen hat. Der Benutzer hat sich nicht mit seinem Microsoft- oder Organisationskonto angemeldet.

## <a name="guest-users"></a>Gastbenutzer

### <a name="install-update-and-delete-for-guest-users"></a>Installieren, Aktualisieren und Löschen für Gastbenutzer

Gäste können Apps nicht in einem freigegebenen Kontext installieren, aktualisieren oder löschen, z. B. einen Chat, Kanal oder eine Besprechung, aber sie können mithilfe von Nachrichtenerweiterungen und direkten Links zu ihrem persönlichen Bereich wechseln. Gäste haben keinen Zugriff auf den Teams App Store über die Teams Desktopanwendung, aber sie können über einen direkten Link darauf zugreifen.

### <a name="usage-behavior-and-policy-for-guest-users"></a>Nutzungsverhalten und Richtlinie für Gastbenutzer

Gäste können eine App verwenden, wenn die App von einem systemeigenen Benutzer installiert wurde.

#### <a name="bots-installed-to-a-channel"></a>In einem Kanal installierte Bots

Gastbenutzer können den Bot erwähnen und mit adaptiven Karten interagieren.

#### <a name="personal-bots-installed-with-policies"></a>Persönliche Bots, die mit Richtlinien installiert wurden

* Gäste halten sich an globale und organisationsweite Berechtigungsrichtlinien, die für den Hostmandanten für jede App festgelegt sind. Wenn eine App für die gesamte Hostorganisation blockiert ist, können Gäste die App auch nicht verwenden.
* Jeder Bot, der in der globalen Standard-App-Setuprichtlinie enthalten ist, wird auch für Gäste installiert.
* Nachdem ein Bot installiert wurde, können Bots proaktiv mit Gästen kommunizieren, und Gäste können wieder mit Bots kommunizieren.
* Sie können einen Gast nicht aus der globalen Standard-App-Setuprichtlinie entfernen.
* Um zu verhindern, dass Gast auf Bots zugreift, können Sie weitere App-Setuprichtlinien erstellen, sie internen Benutzern zuweisen und Bots mit den benutzerdefinierten Richtlinien installieren.

## <a name="external-federated-users"></a>Externe Benutzer (Verbundbenutzer)

### <a name="install-update-and-delete-for-external-users"></a>Installieren, Aktualisieren und Löschen für externe Benutzer

Externe Benutzer können Apps in keinem Kontext installieren, aktualisieren oder löschen, z. B. in einem persönlichen, Chat, Kanal oder einer Besprechung. Sie haben keinen Zugriff auf den Teams App Store der Hostorganisation.

### <a name="usage-behavior-and-policy-for-external-users"></a>Nutzungsverhalten und Richtlinie für externe Benutzer

* Personen aus anderen Organisationen halten sich an die globale (organisationsweite Standard)-Richtlinie der Hostingorganisation
* Benutzer in der Hostingorganisation können Apps in Besprechungschats mit Personen aus anderen Organisationen hinzufügen. Personen aus anderen Organisationen können keine Apps in Besprechungschats hinzufügen, aber mit Bots, Registerkarten und Nachrichtenerweiterungen interagieren, sobald sie dem Chat hinzugefügt wurden.
* Nachdem ein Bot in einem Besprechungschat installiert wurde, kann er proaktiv mit Personen aus anderen Organisationen in diesem Chat kommunizieren, und diese Personen können mit bot kommunizieren.
* Die Datenrichtlinien der Hostingorganisation sowie die Datenfreigabepraktiken von Drittanbieter-Apps, die von der Organisation dieses Benutzers gemeinsam genutzt werden, werden angewendet.

## <a name="anonymous-users"></a>Anonyme Nutzer

### <a name="install-update-and-delete-for-anonymous-users"></a>Installieren, Aktualisieren und Löschen für anonyme Benutzer

Anonyme Benutzer können Apps in Besprechungen nicht installieren, aktualisieren oder löschen.

### <a name="usage-behavior-and-policy-for-anonymous-users"></a>Nutzungsverhalten und Richtlinie für anonyme Benutzer

Anonyme Benutzer können Apps nicht direkt in Besprechungen verwenden. Anonyme Benutzer erben die globale Standardberechtigungsrichtlinie auf Benutzerebene. Wenn eine App eine adaptive Karte im Chat sendet, können anonyme Benutzer mit der Karte interagieren. Solche Benutzer können in Teams Besprechungen mit Apps interagieren, wenn die App durch die Berechtigungsrichtlinie auf Benutzerebene aktiviert wird.

Anonyme Benutzer können nur mit den Apps interagieren, die bereits in einer Besprechung verfügbar sind, und solche Apps nicht erwerben und verwalten. Die nativen Benutzer können weiterhin Besprechungs-Apps verwenden, auch wenn die anonymen Benutzer an einer Besprechung teilnehmen.

## <a name="see-also"></a>Siehe auch

* [Anonymen Benutzern die Teilnahme an Besprechungen erlauben](meeting-settings-in-teams.md#allow-anonymous-users-to-join-meetings).
* [Verwalten von App-Setuprichtlinien in Microsoft Teams](teams-app-setup-policies.md).
