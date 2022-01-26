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
description: Erfahren Sie, wie Sie Besprechungsrichtlinieneinstellungen in Teams für Aufzeichnungen und Transkriptionen verwalten.
ms.openlocfilehash: ee558ae87d7bea781cae3d2bc267f82bc1fdb18a
ms.sourcegitcommit: faeb8976299375e7658499ff31d25e8ef6003144
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/26/2022
ms.locfileid: "62224072"
---
# <a name="meeting-policy-settings-for-recording--transcription"></a>Besprechungsrichtlinieneinstellungen zum Aufzeichnen & Transkription

In diesem Artikel werden die Besprechungsrichtlinieneinstellungen speziell für Aufzeichnungen und Transkriptionen beschrieben, einschließlich der folgenden:

- [Transkription zulassen](#allow-transcription)
- [Cloud-Aufnahme zulassen](#allow-cloud-recording)
- [Store Aufzeichnungen außerhalb Ihres Landes oder Ihrer Region](#store-recordings-outside-of-your-country-or-region)

## <a name="allow-transcription"></a>Transkription zulassen

Hierbei handelt es sich um eine Kombination aus einer benutzerspezifischen und einer organisatorspezifischen Richtlinie. Mit dieser Einstellung wird gesteuert, ob Untertitel- und Transkriptionsfeatures während der Wiedergabe von Besprechungsaufzeichnungen verfügbar sind. Die Person, die die Aufzeichnung gestartet hat, muss diese Einstellung aktiviert haben, damit diese Funktionen mit der Aufzeichnung arbeiten können.

Wenn Sie diese Einstellung aktivieren, wird eine Kopie des Transkripts erstellt, das mit der **Besprechungsaufzeichnung** gespeichert wird. Dadurch werden die Aufzeichnungen "Suchen",  **"Cc"** und "Aufzeichnungen" aktiviert.

Transkription für aufgezeichnete Besprechungen wird derzeit nur für Benutzer unterstützt, die in einer Besprechung die Sprache auf Englisch festlegen Teams sprechen.

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
