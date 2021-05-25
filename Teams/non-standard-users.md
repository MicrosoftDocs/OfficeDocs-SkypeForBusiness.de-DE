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
description: Hier erfahren Sie, wie sich Microsoft Teams in Apps für Nicht-Standardbenutzer verhalten.
localization_priority: Normal
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
- m365initiative-meetings
appliesto:
- Microsoft Teams
ms.openlocfilehash: c27a73928e0740eb325c269fd5ac625fa4c43086
ms.sourcegitcommit: 330e60ff3549cd5cff5b52ad95dc4259e4e8de13
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/24/2021
ms.locfileid: "52628924"
---
# <a name="microsoft-teams-apps-behavior-for-non-standard-users"></a>Microsoft Teams von Apps für Nicht-Standardbenutzer

In diesem Artikel wird beschrieben, wie Teams verhalten, wenn Gastbenutzer, externe Benutzer (Partnerbenutzer) und anonyme Benutzer in einem Teams sind.

- Ein **Gastbenutzer** ist eine Person, die kein Mitarbeiter, Schüler/Student oder Mitglied Ihrer Organisation ist. Er verfügt über kein Geschäfts-, Schul- oder Unikonto bei Ihrer Organisation.

- Ein **externer Benutzer (Partnerbenutzer)** gehört zu einer anderen Domäne und hat keinen Zugriff auf die Teams oder Teamressourcen Ihrer Organisation.

  > [!Note]
  > Einen detaillierten Vergleich zwischen Gastbenutzern und externen Benutzern finden Sie unter [Kommunizieren mit Benutzern aus anderen Organisationen.](./communicate-with-users-from-other-organizations.md)

- Ein **anonymer Benutzer** ist ein Konzept in Teams, bei denen der Benutzer über einen Link an der Besprechung teilgetreten ist. Der Benutzer hat sich nicht mit seinem Microsoft- oder Organisationskonto angemeldet.

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

Externe Benutzer können in keinem Kontext wie einer persönlichen, einem Chat, einem Kanal oder einer Besprechung Apps installieren, aktualisieren oder löschen. Sie haben keinen Zugriff auf den Teams App Store.

### <a name="usage-behavior-and-policy-for-external-users"></a>Verwendungsverhalten und Richtlinie für externe Benutzer

- Externe Benutzer können keine Teams-Apps verwenden, und wenn ein externer Benutzer einem Kontext mit systemeigenen Benutzern hinzugefügt wird, können keine Apps mehr von allen Benutzern (systemeigene und externe Benutzer) verwendet werden.
- Externe Benutzer sind von App-Richtlinien nicht betroffen, da sie ihre Apps nicht Teams können.

## <a name="anonymous-users"></a>Anonyme Nutzer

### <a name="install-update-and-delete-for-anonymous-users"></a>Installieren, Aktualisieren und Löschen für anonyme Benutzer

Anonyme Benutzer können in Besprechungen keine Apps installieren, aktualisieren oder löschen.

### <a name="usage-behavior-and-policy-for-anonymous-users"></a>Nutzungsverhalten und Richtlinie für anonyme Benutzer

Anonyme Benutzer können Apps nicht direkt in Besprechungen verwenden. Native Benutzer können weiterhin Besprechungs-Apps verwenden, wenn anonyme Benutzer anwesend sind. Wenn eine App eine adaptive Karte im Chat sendet, können anonyme Benutzer mit der Karte interagieren. Weitere Informationen finden Sie unter Zulassen, [dass anonyme Benutzer an Besprechungen teilnehmen.](/meeting-settings-in-teams#allow-anonymous-users-to-join-meetings)

Anonyme Benutzer erben die globale Standardberechtigungsrichtlinie auf Benutzerebene. Sie können in Besprechungen in Teams mit Apps interagieren, wenn die App durch die Berechtigungsrichtlinie auf Benutzerebene aktiviert wurde. Anonyme Benutzer können nur mit Apps interagieren, die bereits in einer Besprechung verfügbar sind und diese Apps nicht erwerben und/oder verwalten können.
