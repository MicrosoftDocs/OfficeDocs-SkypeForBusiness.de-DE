---
title: Verwalten von Besprechungsrichtlinien für Aufzeichnung und Transkription
author: KarliStites
ms.author: kastites
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: jastark
audience: admin
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.meetingpolicies.recordingandtranscription
description: Erfahren Sie, wie Sie Besprechungsrichtlinieneinstellungen in Teams Aufzeichnung und Transkription verwalten.
ms.openlocfilehash: c89fc88c46ae8b614021417ab2aa02832f64fce1
ms.sourcegitcommit: 69a5d4994ef75b9c16efa99554fb7f2ee1ccf52a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/10/2021
ms.locfileid: "58973222"
---
# <a name="meeting-policy-settings-for-recording--transcription"></a>Besprechungsrichtlinieneinstellungen zum Aufzeichnen & Transkription

In diesem Artikel werden die Besprechungsrichtlinieneinstellungen speziell für Aufzeichnungen und Transkriptionen beschrieben, einschließlich der folgenden:

- [Transkription zulassen](#allow-transcription)
- [Cloud-Aufnahme zulassen](#allow-cloud-recording)
- [Store Aufzeichnungen außerhalb Ihres Landes oder Ihrer Region](#store-recordings-outside-of-your-country-or-region)

## <a name="allow-transcription"></a>Transkription zulassen

Hierbei handelt es sich um eine Kombination aus einer benutzerspezifischen und einer organisatorspezifischen Richtlinie. Mit dieser Einstellung wird gesteuert, ob Untertitel- und Transkriptionsfeatures während der Wiedergabe von Besprechungsaufzeichnungen verfügbar sind. Wenn Sie diese Einstellung deaktivieren, **stehen** die Optionen Suchen und **CC** während der Wiedergabe einer Besprechungsaufzeichnung nicht zur Verfügung. Die Person, die die Aufzeichnung gestartet hat, muss diese Einstellung aktivieren, damit die Aufzeichnung auch eine Transkription enthält.

Transkription für aufgezeichnete Besprechungen wird derzeit nur für Benutzer unterstützt, die ihre Sprache in Besprechungen auf Englisch festlegen Teams sprechen.

## <a name="allow-cloud-recording"></a>Cloud-Aufzeichnung zulassen

Diese Einstellung ist eine Kombination aus einer Richtlinie pro Organisator und einer Benutzerrichtlinie und steuert, ob die Besprechungen aufgezeichnet werden können. Die Aufzeichnung kann vom Besprechungsorganisator oder von einem anderen Besprechungsteilnehmer gestartet werden, wenn die Richtlinieneinstellung für den Teilnehmer aktiviert ist, und wenn es sich um einen authentifizierten Benutzer aus derselben Organisation handelt.

Personen außerhalb Ihrer Organisation, z. b. Partner- oder anonyme Benutzer, können die Aufzeichnung nicht starten. Gastbenutzer können die Aufzeichnung nicht starten oder beenden.

![Screenshot mit Aufzeichnungsoptionen](media/meeting-policies-recording.png)

Sehen Sie sich das folgende Beispiel an.

|Benutzer |Besprechungsrichtlinie  |Cloud-Aufnahme zulassen |
|---------|---------|---------|
|Daniela | Global   | Aus |
|Amalia | Location1MeetingPolicy | Ein|
|Johann (externer Benutzer) | Nicht zutreffend | Nicht zutreffend|

- Von Daniela organisierte Besprechungen können nicht aufgezeichnet werden.
- Amanda kann keine besprechungen aufzeichnen, die von Daniela organisiert wurden.
- Besprechungen, die von Amanda organisiert werden, können aufgezeichnet werden.
- Daniela kann keine von Amanda organisierten Besprechungen aufzeichnen.
- John kann keine Besprechungen aufzeichnen, die von Amanda organisiert wurden.

Näheres zur Aufzeichnung von Cloud-Besprechungen erfahren Sie unter [Aufzeichnen von Microsoft Teams-Cloudbesprechungen](cloud-recording.md).

## <a name="store-recordings-outside-of-your-country-or-region"></a>Store Aufzeichnungen außerhalb Ihres Landes oder Ihrer Region

Mit dieser Richtlinie wird kontrolliert, ob Besprechungsdatensätze dauerhaft in einem anderen Land oder einer anderen Region gespeichert werden können. Wenn sie aktiviert ist, können die Aufzeichnungen nicht migriert werden. Weitere Informationen zu Cloudbesprechungen und wo Aufzeichnungen gespeichert werden, finden Sie unter Teams [von Cloudbesprechungen.](cloud-recording.md)

## <a name="related-topics"></a>Verwandte Themen

- [Zuweisen von Richtlinien zu Benutzern in Teams](policy-assignment-overview.md)
- [Cloud-Besprechungsaufzeichnung](cloud-recording.md)