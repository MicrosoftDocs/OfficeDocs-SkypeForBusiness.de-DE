---
title: Verhalten von Teams-Apps basierend auf Benutzertypen
author: guptaashish
ms.author: guptaashish
ms.reviewer: joglocke
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: Erfahren Sie, wie Apps in Microsoft Teams für Gäste, Verbundbenutzer und anonyme Benutzer unterschiedlich funktionieren.
ms.localizationpriority: high
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
- m365initiative-meetings
appliesto:
- Microsoft Teams
ms.openlocfilehash: 940c021b18c390a7b5c9ec0f8a3325c49c87dae5
ms.sourcegitcommit: 903abff4ce79c10bf1fb936b8ad71f6315a43c18
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/08/2022
ms.locfileid: "67278599"
---
# <a name="behavior-of-microsoft-teams-apps-based-on-types-of-in-meeting-users"></a>Verhalten von Microsoft Teams-Apps basierend auf Typen von Benutzern in der Besprechung

Teams-Apps verhalten sich, wenn Gastbenutzer, externe (Verbundbenutzer) und anonyme Benutzer in einem Teams-Kontext vorhanden sind.

* Ein **Gastbenutzer** ist eine Person, die kein Mitarbeiter, Student oder Mitglied Ihrer Organisation ist. Er verfügt über kein Geschäfts-, Schul- oder Unikonto bei Ihrer Organisation.

* Ein **externer Benutzer (Verbundbenutzer)** stammt aus einer anderen Domäne und hat keinen Zugriff auf die Teams-Ressourcen Ihrer Organisation.

  > [!Note]
  > Einen detaillierteren Vergleich zwischen Gast- und externen Benutzern finden Sie in [der Kommunikation mit Benutzern aus anderen Organisationen](./communicate-with-users-from-other-organizations.md).

* Ein **anonymer Benutzer** ist ein Benutzer, der über einen Link an einer Besprechung teilnimmt. Der Benutzer ist nicht mit seinem Microsoft-Konto oder dem Konto seiner Organisation angemeldet.

## <a name="guests"></a>Gäste

### <a name="install-update-and-delete-for-guests"></a>Installieren, Aktualisieren und Löschen für Gäste

Gäste können Apps nicht in einem freigegebenen Kontext wie einem Chat, Kanal oder einer Besprechung installieren, aktualisieren oder löschen. Gäste können dies in ihrem persönlichen Bereich mithilfe von Nachrichtenerweiterungen und direkten Links tun. Gäste können nicht über die Teams-Desktop-App auf den Teams-App-Store zugreifen, sondern über einen direkten Link auf den Store zugreifen.

### <a name="usage-behavior-and-policy-for-guests"></a>Nutzungsverhalten und Richtlinie für Gäste

Gäste können eine App verwenden, wenn die App von einem systemeigenen Benutzer installiert wurde.

#### <a name="bots-installed-to-a-channel"></a>In einem Kanal installierte Bots

Gäste können den Bot erwähnen und mit adaptiven Karten interagieren.

#### <a name="personal-bots-installed-with-policies"></a>Persönliche Bots, die mit Richtlinien installiert wurden

* Für jede App halten sich Gäste an globale und organisationsweite Berechtigungsrichtlinien, die für die Hostorganisation festgelegt sind. Wenn eine App für die gesamte Hostorganisation blockiert ist, können Gäste die App auch nicht verwenden.
* Jeder Bot, der in der globalen Standard-App-Setuprichtlinie enthalten ist, wird auch für Gäste installiert.
* Nachdem ein Bot installiert wurde, können Bots proaktiv mit Gästen kommunizieren, und Gäste können wieder mit Bots kommunizieren.
* Sie können einen Gast nicht aus der globalen Standard-App-Setuprichtlinie entfernen.
* Um zu verhindern, dass Gast auf Bots zugreift, können Sie weitere App-Setuprichtlinien erstellen, sie internen Benutzern zuweisen und Bots mit den benutzerdefinierten Richtlinien installieren.

## <a name="federated-users"></a>Verbundbenutzer

### <a name="install-update-and-delete-for-federated-users"></a>Installieren, Aktualisieren und Löschen für Verbundbenutzer

Verbundbenutzer können Apps in keinem Kontext installieren, aktualisieren oder löschen, z. B. in einem persönlichen Kontext, Chat, Kanal oder Besprechung. Sie haben keinen Zugriff auf den Teams-App-Store der hostenden Organisation.

### <a name="usage-behavior-and-policy-for-federated-users"></a>Nutzungsverhalten und Richtlinie für Verbundbenutzer

* Personen anderer Organisationen halten sich an die globale (organisationsweite Standard)-Richtlinie der Hostingorganisation.
* Benutzer in der Hostingorganisation können Apps in Besprechungschats mit Personen aus anderen Organisationen hinzufügen. Personen aus anderen Organisationen können keine Apps in Besprechungschats hinzufügen, sondern mit Bots, Registerkarten und Nachrichtenerweiterungen interagieren, sobald sie dem Chat hinzugefügt wurden.
* Nachdem ein Bot in einem Besprechungschat installiert wurde, kann er proaktiv mit Personen aus anderen Organisationen in diesem Chat kommunizieren, und diese Personen können mit bot kommunizieren.
* Die Datenrichtlinien der Hostingorganisation werden angewendet.
* Die Datenfreigabepraktiken von Drittanbieter-Apps, die von der Organisation dieses Benutzers gemeinsam genutzt werden, werden angewendet.

## <a name="anonymous-users"></a>Anonyme Nutzer

### <a name="install-update-and-delete-for-anonymous-users"></a>Installieren, Aktualisieren und Löschen für anonyme Benutzer

Anonyme Benutzer können Apps in Besprechungen nicht installieren, aktualisieren oder löschen.

### <a name="usage-behavior-and-policy-for-anonymous-users"></a>Nutzungsverhalten und Richtlinie für anonyme Benutzer

Anonyme Benutzer können Apps nicht direkt in Besprechungen verwenden. Wenn eine App eine adaptive Karte im Chat sendet, können anonyme Benutzer mit der Karte interagieren. Solche Benutzer können mit Apps in Teams-Besprechungen interagieren, wenn die Berechtigungsrichtlinie auf Benutzerebene die App aktiviert. Anonyme Benutzer erben die globale Standardberechtigungsrichtlinie auf Benutzerebene.

Anonyme Benutzer können nur mit den Apps interagieren, die bereits in einer Besprechung verfügbar sind, aber solche Apps nicht erwerben und verwalten können. Die nativen Benutzer können weiterhin Besprechungs-Apps verwenden, auch wenn die anonymen Benutzer an einer Besprechung teilnehmen.

## <a name="see-also"></a>Siehe auch

* [Anonymen Benutzern die Teilnahme an Besprechungen erlauben](meeting-settings-in-teams.md#allow-anonymous-users-to-join-meetings).
* [Verwalten von App-Setuprichtlinien in Microsoft Teams](teams-app-setup-policies.md).
