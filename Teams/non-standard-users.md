---
title: Teams von Apps für Nicht-Standardbenutzer
author: cichur
ms.author: v-cichur
ms.reviewer: joglocke
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: Hier erfahren Sie, wie Microsoft Teams sich in Apps für Nicht-Standardbenutzer verhalten.
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
- m365initiative-meetings
appliesto:
- Microsoft Teams
ms.openlocfilehash: 882fda0be339c8f9869c5b83fbeff3e97d5892ee
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/26/2021
ms.locfileid: "58619401"
---
# <a name="microsoft-teams-apps-behavior-for-non-standard-users"></a>Microsoft Teams von Apps für Nicht-Standardbenutzer

In diesem Artikel wird beschrieben, wie Teams verhalten, wenn Gastbenutzer, externe Benutzer (Partnerbenutzer) und anonyme Benutzer in einem Teams sind.

- Ein **Gastbenutzer** ist eine Person, die kein Mitarbeiter, Schüler/Student oder Mitglied Ihrer Organisation ist. Er verfügt über kein Geschäfts-, Schul- oder Unikonto bei Ihrer Organisation.

- Ein **externer Benutzer (Partnerbenutzer)** gehört zu einer anderen Domäne und hat keinen Zugriff auf die Teams oder Teamressourcen Ihrer Organisation.

  > [!Note]
  > Einen detaillierten Vergleich zwischen Gastbenutzern und externen Benutzern finden Sie unter [Kommunizieren mit Benutzern aus anderen Organisationen.](./communicate-with-users-from-other-organizations.md)

- Ein **anonymer Benutzer** ist ein Konzept in Teams Besprechungen, bei denen der Benutzer über einen Link an der Besprechung teilgetreten ist. Der Benutzer hat sich nicht mit seinem Microsoft- oder Organisationskonto angemeldet.

## <a name="guest-users"></a>Gastbenutzer

### <a name="install-update-and-delete-for-guest-users"></a>Installieren, Aktualisieren und Löschen für Gastbenutzer

Gäste können keine Apps in einem freigegebenen Kontext wie Chat, Kanal oder Besprechung installieren, aktualisieren oder löschen, aber sie können mit Nachrichtenerweiterungen und direkten Links zu ihrem persönlichen Bereich wechseln. Gäste haben keinen Zugriff auf den Teams-App-Store aus der Teams-Desktopanwendung, können aber über einen direkten Link darauf zugreifen.

### <a name="usage-behavior-and-policy-for-guest-users"></a>Nutzungsverhalten und Richtlinie für Gastbenutzer

Gäste können eine App verwenden, wenn die App von einem systemeigenen Benutzer installiert wurde.

#### <a name="bots-installed-to-a-channel"></a>In einem Kanal installierte Bots

Bots können Proaktiv Nachrichten für Gastbenutzer senden, aber Gäste können nicht mit dem Bot interagieren. Gäste können dem Bot keine 1:1-Nachrichten senden, den Bot erwähnen oder mit adaptiven Karten interagieren, die mit dem Bot kommunizieren.

#### <a name="personal-bots-installed-with-policies"></a>Persönliche Bots, die mit Richtlinien installiert wurden

- Gäste müssen globale und organisationsweite Berechtigungsrichtlinien befolgen, die für den Host-Mandanten für jede App festgelegt sind. Wenn eine App für die gesamte Hostorganisation blockiert ist, können Gäste die App auch nicht verwenden.
- Jeder bot, der in der globalen Standard-App-Setuprichtlinie enthalten ist, wird auch für Gäste installiert.
- Nach der Installation eines Bots können Bots proaktiv mit Gästen und Gäste mit Bots kommunizieren.
- Sie können einen Gast nicht aus der globalen Standard-App-Setuprichtlinie entfernen.
- Um zu verhindern, dass Gäste auf Bots zugreifen, können Sie weitere Richtlinien für die App-Einrichtung erstellen, sie internen Benutzern zuweisen und Bots mit den benutzerdefinierten Richtlinien installieren.

## <a name="external-federated-users"></a>Externe Benutzer (Verbundbenutzer)

### <a name="install-update-and-delete-for-external-users"></a>Installieren, Aktualisieren und Löschen für externe Benutzer

Externe Benutzer können in keinem Kontext wie einer persönlichen, einem Chat, einem Kanal oder einer Besprechung Apps installieren, aktualisieren oder löschen. Sie haben keinen Zugriff auf den Teams Store der Hostingorganisation.

### <a name="usage-behavior-and-policy-for-external-users"></a>Verwendungsverhalten und Richtlinie für externe Benutzer

- Personen aus anderen Organisationen halten sich an die globale (organisationsweite Standard)-Richtlinie der Hostingorganisation.
- Benutzer in der Hostingorganisation können Apps in Besprechungschats mit Personen aus anderen Organisationen hinzufügen. Personen aus anderen Organisationen können in Besprechungschats keine Apps hinzufügen, können aber mit Bots, Registerkarten und Nachrichtenerweiterungen interagieren, die dem Chat hinzugefügt wurden.
- Nachdem ein Bot in einem Besprechungschat installiert wurde, kann er proaktiv mit Personen aus anderen Organisationen in diesem Chat kommunizieren, und diese Personen können mit bot kommunizieren.
- Es werden die Datenrichtlinien der Hostingorganisation sowie die Praktiken bei der Datenfreigabe für von der Organisation dieses Benutzers freigegebene Drittanbieter-Apps angewendet.

## <a name="anonymous-users"></a>Anonyme Nutzer

### <a name="install-update-and-delete-for-anonymous-users"></a>Installieren, Aktualisieren und Löschen für anonyme Benutzer

Anonyme Benutzer können in Besprechungen keine Apps installieren, aktualisieren oder löschen.

### <a name="usage-behavior-and-policy-for-anonymous-users"></a>Nutzungsverhalten und Richtlinie für anonyme Benutzer

Anonyme Benutzer können Apps in Besprechungen nicht direkt verwenden. Native Benutzer können Besprechungs-Apps weiterhin verwenden, wenn anonyme Benutzer anwesend sind. Wenn eine App eine adaptive Karte im Chat sendet, können anonyme Benutzer mit der Karte interagieren. Weitere Informationen finden Sie unter Zulassen, [dass anonyme Benutzer an Besprechungen teilnehmen.](meeting-settings-in-teams.md#allow-anonymous-users-to-join-meetings)

Anonyme Benutzer erben die globale Standardberechtigungsrichtlinie auf Benutzerebene. Sie können in Besprechungen in Teams mit Apps interagieren, wenn die App durch die Berechtigungsrichtlinie auf Benutzerebene aktiviert wurde. Anonyme Benutzer können nur mit Apps interagieren, die bereits in einer Besprechung verfügbar sind und diese Apps nicht erwerben und/oder verwalten können.

## <a name="related-topics"></a>Verwandte Themen

[Verwalten von Richtlinien für das App-Setup in Microsoft Teams](teams-app-setup-policies.md)
