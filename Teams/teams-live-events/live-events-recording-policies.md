---
title: Aufzeichnungsrichtlinien für Liveereignisse
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: christi.balaki
audience: admin
search.appverid: MET150
f1.keywords:
- CSH
ms.localizationpriority: medium
ms.collection:
- M365-collaboration
description: Erfahren Sie mehr über die Aufzeichnungsrichtlinien für Liveereignisse.
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 5ae98255edf26843e59839192a9f20096182bfa2
ms.sourcegitcommit: 4d88637f510a78d5709d1213c3e285d83a022014
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/14/2022
ms.locfileid: "66794113"
---
# <a name="live-event-recording-policies-in-microsoft-teams"></a>Richtlinien für die Aufzeichnung von Liveereignissen in Microsoft Teams

Sie haben mehrere Optionen zum Aufzeichnen eines Microsoft Teams-Liveereignisses. Die Aufzeichnungsoptionen werden mithilfe von Aufzeichnungsrichtlinien festgelegt. In diesem Artikel werden die verschiedenen Einstellungen beschrieben.

Die Aufzeichnungsoptionen werden mit dem [PowerShell-Befehl Set-CsTeamsMeetingBroadcastPolicy](/powershell/module/skype/set-csteamsmeetingbroadcastpolicy) festgelegt.

## <a name="scheduling-and-option-behaviors"></a>Planungs- und Optionsverhalten

Es gibt zwei Organisatoroptionen beim Planen einer Liveereignisaufzeichnung:

- Aufzeichnung für Produzenten und Referenten verfügbar

  - Aufzeichnungsdatei: Stellt eine Aufzeichnungsdatei bereit, die Produzenten und Referenten herunterladen können, nachdem das Ereignis vorbei ist.

- Aufzeichnung für Teilnehmer verfügbar

  - DVR: Ein digitaler Videorekorder (DIGITAL Video Recorder, DVR) ermöglicht teilnehmern das Zurückspulen und Anhalten während der Veranstaltung.

  - VOD: Ein Video on Demand (VOD) ermöglicht Es Teilnehmern, nach Abschluss des Ereignisses zu sehen

## <a name="broadcast-recording-policy-setting"></a>Richtlinieneinstellung für Die Übertragungsaufzeichnung

Im Rahmen der Übertragungsrichtlinie gibt es eine Einstellung, mit der Sie die Aufzeichnung für ein Liveereignis aktivieren oder deaktivieren können.

| &nbsp;| Aufzeichnung für Produzenten und Referenten verfügbar | Aufzeichnung für Teilnehmer verfügbar |
| ------------------------------- | ---------------------------------------------------- | ------------------------------------- |
| Immer aufzeichnen               | Deaktiviert und ausgewählt                                | Aktiviert und ausgewählt         |
| Organisator kann aufzeichnen oder nicht | Standardmäßig aktiviert und ausgewählt                  | Standardmäßig aktiviert und ausgewählt   |
| Nie aufzeichnen               | Deaktiviert und nicht ausgewählt                            | Deaktiviert und nicht ausgewählt      |

## <a name="storage-and-persistence-behavior"></a>Speicher- und Persistenzverhalten

| Option                                       | Status   | DVR                                                   | VOD                                                     | Aufzeichnung läuft                |
| ------------------------------------------------ | ------------ | --------------------------------------------------------- | ----------------------------------------------------------- | ---------------------------- |
| Aufzeichnung für Teilnehmer verfügbar | Ausgewählt     | DVR ist verfügbar, und die Azure Media Services (AMS)-Ressource wird 180 Tage lang gespeichert. | Teilnehmer können auf das Ereignis zugreifen und es ansehen                     |                              |
|                                                  | Nicht ausgewählt | DVR ist verfügbar, und das AMS-Objekt wird 180 Tage lang gespeichert. | Teilnehmer erhalten keinen Zugriff auf das Ereignis, nachdem es vorbei ist |                              |
||Deaktiviert (Nicht ausgewählt)|DVR ist verfügbar, und die AMS-Ressource wird nach dem Ereignis gelöscht.|Teilnehmer erhalten keinen Zugriff auf das Ereignis, nachdem es vorbei ist||
| Aufzeichnung für Produzenten und Referenten verfügbar | Ausgewählt     |                                                           |                                                             | Ein MP4 wird erstellt und 180 Tage lang gespeichert. |
|                                                  | Nicht ausgewählt |                                                           |                                                             | Es wird keine Datei erstellt.           |

### <a name="related-topics"></a>Verwandte Themen

- [Was sind Teams-Liveereignisse?](what-are-teams-live-events.md)
- [Planen von Teams-Liveereignissen](plan-for-teams-live-events.md)
- [Konfigurieren der Einstellungen für Liveereignisse in Teams](configure-teams-live-events.md)
- [Teams Clouds-Besprechungsaufzeichnung](../cloud-recording.md)
