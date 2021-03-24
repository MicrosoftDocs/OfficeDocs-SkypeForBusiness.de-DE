---
title: Verhalten von Teams-Apps für Nicht-Standardbenutzer
author: cichur
ms.author: v-cichur
ms.reviewer: joglocke
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: Erfahren Sie, wie sich Apps in Microsoft Teams für Nichtstandardbenutzer verhalten.
localization_priority: Normal
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
- m365initiative-meetings
appliesto:
- Microsoft Teams
ms.openlocfilehash: 6a8c3c842b47c4575779de4c0ae8301bededb632
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51098301"
---
# <a name="microsoft-teams-apps-behavior-for-non-standard-users"></a>Verhalten von Microsoft Teams-Apps für Nichtstandardbenutzer

In diesem Artikel wird beschrieben, wie sich Apps in Teams verhalten, wenn Gastbenutzer, externe (Verbundbenutzer) und anonyme Benutzer in einem Teams-Kontext vorhanden sind.

- Ein **Gastbenutzer** ist eine Person, die kein Mitarbeiter, Student oder Mitglied Ihrer Organisation ist. Er verfügt über kein Geschäfts-, Schul- oder Unikonto bei Ihrer Organisation.

- Ein **externer (Verbundbenutzer)** gehört zu einer anderen Domäne und hat keinen Zugriff auf die Teams oder Teamressourcen Ihrer Organisation.

>[!Note]
> Einen detaillierten Vergleich zwischen Gast und externen Benutzern finden Sie unter Kommunizieren mit [Benutzern aus anderen Organisationen.](./communicate-with-users-from-other-organizations.md)

- Ein **anonymer Benutzer** ist ein Konzept in Teams-Besprechungen, bei denen der Benutzer über einen Link der Besprechung beigetreten ist. Der Benutzer hat sich nicht mit seinem Microsoft- oder Organisationskonto angemeldet.

## <a name="guest-user-access"></a>Gastbenutzerzugriff

### <a name="install-update-and-delete-for-guest-users"></a>Installieren, Aktualisieren und Löschen für Gastbenutzer

Gäste können Apps nicht in einem freigegebenen Kontext installieren, aktualisieren oder löschen, z. B. in einem Chat, Kanal oder einer Besprechung. Sie können Apps in ihrem persönlichen Bereich mithilfe von Nachrichtenerweiterungen und direkten Links installieren, aktualisieren oder löschen. Gäste haben keinen Zugriff auf den Teams App Store.

### <a name="usage-behavior-and-policy-for-guest-users"></a>Verwendungsverhalten und -richtlinie für Gastbenutzer

Gäste können eine App verwenden, wenn die App von einem systemeigenen Benutzer installiert wurde.

Bots können Gastbenutzer proaktiv an die Nachricht senden, Gäste können jedoch nicht mit dem Bot interagieren. Gäste können den Bot nicht 1:1, @ den Bot erwähnen oder mit adaptiven Karten interagieren, die mit dem Bot kommunizieren.

Gäste halten sich an globale und organisationsweite Berechtigungsrichtlinien, die für den Host-Mandanten für jede App festgelegt wurden. Anders ausgedrückt: Wenn eine App für die gesamte Hostorganisation blockiert ist, können Gäste die App auch nicht verwenden.

Setuprichtlinien gelten nicht für Gastbenutzer. Dies bedeutet, dass die vom Administrator angeheftet App aus der Standardrichtlinie keine Auswirkungen auf Gastbenutzer hat.

## <a name="external-federated-user-access"></a>Externer Benutzerzugriff (Verbundbenutzer)

### <a name="install-update-and-delete-for-external-users"></a>Installieren, Aktualisieren und Löschen für externe Benutzer

Externe Benutzer können Apps nicht in einem beliebigen Kontext installieren, aktualisieren oder löschen, z. B. in einem persönlichen, chatten, kanalbezogenen oder besprechungsbezogenen Kontext. Sie haben keinen Zugriff auf den Teams App Store.

### <a name="usage-behavior-and-policy-for-external-users"></a>Verwendungsverhalten und Richtlinie für externe Benutzer

Externe Benutzer können keine Teams-Apps verwenden, und wenn ein externer Benutzer zu einem Kontext mit systemeigenen Benutzern hinzugefügt wird, können alle Benutzer – systemeigene und externe – Apps nicht mehr verwenden.

Externe Benutzer sind von App-Richtlinien nicht betroffen, da sie keine Teams-Apps verwenden können.

## <a name="anonymous-user-in-meetings-access"></a>Anonymer Benutzer in Besprechungen

### <a name="install-update-and-delete-for-anonymous-users"></a>Installieren, Aktualisieren und Löschen für anonyme Benutzer

Anonyme Benutzer können Apps in Besprechungen nicht installieren, aktualisieren oder löschen.

### <a name="usage-behavior-and-policy-for-anonymous-users"></a>Verwendungsverhalten und Richtlinie für anonyme Benutzer

Anonyme Benutzer können Apps in Besprechungen nicht direkt verwenden. Systemeigene Benutzer können weiterhin Besprechungs-Apps verwenden, wenn anonyme Benutzer vorhanden sind. Wenn eine App eine adaptive Karte im Chat sendet, können anonyme Benutzer mit der Karte interagieren.

Anonyme Benutzer erben die globale Standardberechtigungsrichtlinie auf Benutzerebene. Dieses Steuerelement ermöglicht anonymen Benutzern die Interaktion mit Apps in Teams-Besprechungen, wenn die Berechtigungsrichtlinie auf Benutzerebene die App aktiviert hat. Anonyme Benutzer können nur mit Apps interagieren, die bereits in einer Besprechung verfügbar sind und diese Apps nicht erwerben und/oder verwalten können.