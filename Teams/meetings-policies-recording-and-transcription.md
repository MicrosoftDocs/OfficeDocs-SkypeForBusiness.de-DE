---
title: Verwalten von Besprechungsrichtlinien für Aufzeichnung und Transkription
author: mkbond007
ms.author: mabond
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
description: Erfahren Sie, wie Sie Besprechungsrichtlinieneinstellungen in Teams für die Aufzeichnung und Transkription verwalten.
ms.openlocfilehash: 12f8be910c713a9ce023ac17c956ef50f5889792
ms.sourcegitcommit: 173bdbaea41893d39a951d79d050526b897044d5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/07/2022
ms.locfileid: "67268980"
---
# <a name="meeting-policy-settings-for-recording--transcription"></a>Besprechungsrichtlinieneinstellungen für die Aufzeichnung & Transkription

In diesem Artikel werden die Besprechungsrichtlinieneinstellungen für aufzeichnungs- und transkriptionsspezifische Einstellungen beschrieben, einschließlich der folgenden:

- [Transkription zulassen](#allow-transcription)
- [Cloud-Aufnahme zulassen](#allow-cloud-recording)
- [Speichern von Aufzeichnungen außerhalb Ihres Landes oder Ihrer Region](#store-recordings-outside-of-your-country-or-region)

## <a name="allow-transcription"></a>Transkription zulassen

Hierbei handelt es sich um eine Kombination aus einer benutzerspezifischen und einer organisatorspezifischen Richtlinie. Mit dieser Einstellung wird gesteuert, ob Untertitel- und Transkriptionsfeatures während der Wiedergabe von Besprechungsaufzeichnungen verfügbar sind. Die Person, die die Aufzeichnung gestartet hat, muss diese Einstellung aktiviert haben, damit diese Features mit der Aufzeichnung funktionieren können.

Wenn Sie diese Einstellung aktivieren, wird eine Kopie des Transkripts erstellt, das mit der Besprechungsaufzeichnung gespeichert wird. Dadurch werden für die Besprechungsaufzeichnung **"Suchen"**, **"Cc"** und **"Transkripte"** aktiviert.

Die Transkription für aufgezeichnete Besprechungen wird derzeit nur für Benutzer unterstützt, die ihre Sprache in Teams-Besprechungen festlegen oder Englisch sprechen.

## <a name="allow-cloud-recording"></a>Cloud-Aufzeichnung zulassen

Diese Einstellung ist eine Kombination aus einer Organisator- und Benutzerrichtlinie und steuert, ob die Besprechungen aufgezeichnet werden können. Die Aufzeichnung kann vom Besprechungsorganisator oder von einem anderen Besprechungsteilnehmer gestartet werden, wenn die Richtlinieneinstellung für den Teilnehmer aktiviert ist, und wenn es sich um einen authentifizierten Benutzer aus derselben Organisation handelt.

Personen außerhalb Ihrer Organisation, z. b. Partner- oder anonyme Benutzer, können die Aufzeichnung nicht starten. Gastbenutzer können die Aufzeichnung nicht starten oder beenden.

![Screenshot mit Aufzeichnungsoptionen](media/meeting-policies-recording.png)

Sehen Sie sich das folgende Beispiel an.

|Benutzer |Besprechungsrichtlinie  |Cloud-Aufnahme zulassen |
|---------|---------|---------|
|Daniela | Global   | Aus |
|Amalia | Location1MeetingPolicy | Ein|
|Johann (externer Benutzer) | Nicht zutreffend | Nicht zutreffend|

- Von Daniela organisierte Besprechungen können nicht aufgezeichnet werden.
- Amanda kann keine von Daniela organisierten Besprechungen aufzeichnen.
- Von Amanda organisierte Besprechungen können aufgezeichnet werden.
- Daniela kann keine von Amanda organisierten Besprechungen aufzeichnen.
- John kann keine von Amanda organisierten Besprechungen aufzeichnen.

Näheres zur Aufzeichnung von Cloud-Besprechungen erfahren Sie unter [Aufzeichnen von Microsoft Teams-Cloudbesprechungen](cloud-recording.md).

## <a name="store-recordings-outside-of-your-country-or-region"></a>Speichern von Aufzeichnungen außerhalb Ihres Landes oder Ihrer Region

Diese Richtlinie steuert, ob Besprechungsdatensätze dauerhaft in einem anderen Land oder einer anderen Region gespeichert werden können. Wenn sie aktiviert ist, können die Aufzeichnungen nicht migriert werden. Weitere Informationen zu Cloudbesprechungen und wo Aufzeichnungen gespeichert werden, finden Sie unter [Teams Cloud Meeting Recording](cloud-recording.md).

## <a name="related-topics"></a>Verwandte Themen

- [Zuweisen von Richtlinien zu Benutzern in Teams](policy-assignment-overview.md)
- [Aufzeichnung von Cloudbesprechungen](cloud-recording.md)
- [Besprechungsrichtlinien und Ablauf von Besprechungen in Microsoft Teams](meeting-expiration.md)
