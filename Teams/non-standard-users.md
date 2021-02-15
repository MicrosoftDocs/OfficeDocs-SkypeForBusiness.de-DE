---
title: Verhalten von Teams-Apps für nicht standardmäßige Benutzer
author: cichur
ms.author: v-cichur
ms.reviewer: joglocke
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: Erfahren Sie, wie sich Apps in Microsoft Teams für Nicht-Standardbenutzer verhalten.
localization_priority: Normal
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
- m365initiative-meetings
appliesto:
- Microsoft Teams
ms.openlocfilehash: 683ba9a20c51a23fa1468c07407a389c23dba507
ms.sourcegitcommit: 75ccb8cda9e6dd900df93a2d856ff5f7682ac623
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/14/2021
ms.locfileid: "50237498"
---
# <a name="microsoft-teams-apps-behavior-for-non-standard-users"></a>Verhalten von Microsoft Teams-Apps für nicht standardmäßige Benutzer

In diesem Artikel wird beschrieben, wie sich Apps in Teams verhalten, wenn Gastbenutzer, externe Benutzer (Partner) und anonyme Benutzer in einem Teams-Kontext vorhanden sind.

- Ein **Gastbenutzer** ist eine Person, die kein Mitarbeiter, Schüler/Student oder Mitglied Ihrer Organisation ist. Er verfügt über kein Geschäfts-, Schul- oder Unikonto bei Ihrer Organisation.

- Ein **externer Benutzer (Partnerbenutzer)** gehört einer anderen Domäne an und hat keinen Zugriff auf die Teams oder Teamressourcen Ihrer Organisation.

>[!Note]
> Einen detaillierten Vergleich zwischen Gästen und externen Benutzern finden Sie unter ["Kommunikation mit Benutzern aus anderen Organisationen".](https://docs.microsoft.com/microsoftteams/communicate-with-users-from-other-organizations)

- Ein **anonymer Benutzer** ist ein Konzept in Teams-Besprechungen, bei dem der Benutzer der Besprechung über einen Link beigetreten ist. Der Benutzer hat sich nicht mit seinem Microsoft- oder Organisationskonto angemeldet.

## <a name="guest-user-access"></a>Gastbenutzerzugriff

### <a name="install-update-and-delete-for-guest-users"></a>Installieren, Aktualisieren und Löschen für Gastbenutzer

Gäste können keine Apps in einem freigegebenen Kontext wie einem Chat, Kanal oder einer Besprechung installieren, aktualisieren oder löschen. Sie können Apps in ihrem persönlichen Bereich mithilfe von Nachrichtenerweiterungen und direkten Links installieren, aktualisieren oder löschen. Gäste haben keinen Zugriff auf den Teams-App-Store.

### <a name="usage-behavior-and-policy-for-guest-users"></a>Nutzungsverhalten und Richtlinie für Gastbenutzer

Gäste können eine App verwenden, wenn die App von einem systemeigenen Benutzer installiert wurde.

Bots können Gastbenutzer proaktiv über Nachrichten senden, Gäste können jedoch nicht mit dem Bot interagieren. Gäste können dem Bot keine 1:1-Nachrichten senden, den Bot @erwähnen oder mit adaptiven Karten interagieren, die mit dem Bot kommunizieren.

Gäste halten sich an die globalen und organisationsweiten Berechtigungsrichtlinien, die für den Host-Mandanten für jede App festgelegt sind. (Mit anderen Worten: Wenn eine App für die gesamte Hostorganisation blockiert ist, können Gäste die App auch nicht verwenden.)

Setuprichtlinien gelten nicht für Gastbenutzer. Dies bedeutet, dass durch den Administrator angeheftet App aus der Standardrichtlinie keine Gastbenutzer betroffen sind.

## <a name="external-federated-user-access"></a>Zugriff auf externe Benutzer (Verbundbenutzer)

### <a name="install-update-and-delete-for-external-users"></a>Installieren, Aktualisieren und Löschen für externe Benutzer

Externe Benutzer können keine Apps in einem beliebigen Kontext installieren, aktualisieren oder löschen, z. B. in einem persönlichen, Chat, Kanal oder einer Besprechung. Sie haben keinen Zugriff auf den Teams-App-Store.

### <a name="usage-behavior-and-policy-for-external-users"></a>Verwendungsverhalten und Richtlinie für externe Benutzer

Externe Benutzer können keine Teams-Apps verwenden, und wenn ein externer Benutzer einem Kontext mit systemeigenen Benutzern hinzugefügt wird, können nicht mehr alle Benutzer – systemeigene und externe – Apps verwenden.

Externe Benutzer sind von den Richtlinien für Apps nicht betroffen, da sie keine Teams-Apps verwenden können.

## <a name="anonymous-user-in-meetings-access"></a>Anonymer Benutzer im Besprechungszugriff

### <a name="install-update-and-delete-for-anonymous-users"></a>Installieren, Aktualisieren und Löschen für anonyme Benutzer

Anonyme Benutzer können in Besprechungen keine Apps installieren, aktualisieren oder löschen.

### <a name="usage-behavior-and-policy-for-anonymous-users"></a>Verwendungsverhalten und Richtlinie für anonyme Benutzer

Anonyme Benutzer können Apps nicht direkt in Besprechungen verwenden. Native Benutzer können die Besprechungs-Apps weiterhin verwenden, wenn anonyme Benutzer anwesend sind. Wenn eine App eine adaptive Karte im Chat sendet, können anonyme Benutzer mit der Karte interagieren.

Anonyme Benutzer erben die globale Standardberechtigungsrichtlinie auf Benutzerebene. Dieses Steuerelement ermöglicht anonymen Benutzern die Interaktion mit Apps in Teams-Besprechungen, solange die App durch die Berechtigungsrichtlinie auf Benutzerebene aktiviert wurde. Anonyme Benutzer können nur mit Apps interagieren, die bereits in einer Besprechung verfügbar sind und diese Apps nicht erwerben und/oder verwalten können.
