---
title: Aufzeichnungsrichtlinien für Liveereignisse
author: cichur
ms.author: v-cichur
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: christi.balaki
audience: admin
search.appverid: MET150
f1.keywords:
- CSH
localization_priority: Normal
ms.collection:
- M365-collaboration
description: Erfahren Sie mehr über Richtlinien für die Liveereignisaufzeichnung.
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 9fd67ce67d31effdba0d152a3d5920bb17f23b25
ms.sourcegitcommit: 31a585cc0fe6350efacf3a7771d1e590d5e4233c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/10/2021
ms.locfileid: "50615169"
---
# <a name="live-event-recording-policies-in-microsoft-teams"></a>Richtlinien für die Liveereignisaufzeichnung in Microsoft Teams

Sie haben mehrere Optionen zum Aufzeichnen eines Microsoft Teams-Liveereigniss. Die Aufzeichnungsoptionen werden mithilfe von Aufzeichnungsrichtlinien festgelegt. In diesem Artikel werden die verschiedenen Einstellungen beschrieben.

Die Aufzeichnungsoptionen werden mit dem [PowerShell-Befehl Set-CsTeamsMeetingBroadcastPolicy festgelegt.](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingbroadcastpolicy?view=skype-ps)

## <a name="scheduling-and-option-behaviors"></a>Planungs- und Optionsverhalten

Beim Planen einer Liveereignisaufzeichnung gibt es zwei Organisatoroptionen:

- Aufzeichnung für Produzenten und Presenter verfügbar

  - Aufzeichnungsdatei: Stellt eine Aufzeichnungsdatei bereit, die Produzenten und Presenter herunterladen können, nachdem das Ereignis beendet ist.

- Aufzeichnung für Teilnehmer verfügbar

  - DVR: Ein digitaler Videorekorder (DVR) ermöglicht Teilnehmern das Zurückspulen und Anhalten während des Ereignisses.

  - VOD: Ein Video on Demand (VOD) ermöglicht teilnehmern, nach dem Ende des Ereignisses zu schauen

## <a name="broadcast-recording-policy-setting"></a>Richtlinieneinstellung für übertragungsaufzeichnungsrichtlinien

Im Rahmen der Übertragungsrichtlinie gibt es eine Einstellung, mit der Sie die Aufzeichnung für ein Liveereignis aktivieren oder deaktivieren können.

|                                 | Aufzeichnung für Produzenten und Presenter verfügbar | Aufzeichnung für Teilnehmer verfügbar |
| ------------------------------- | ---------------------------------------------------- | ------------------------------------- |
| Immer aufzeichnen               | Deaktiviert und ausgewählt                                | Deaktiviert und ausgewählt         |
| Organizer kann aufzeichnen oder nicht | Aktiviert und nicht standardmäßig ausgewählt                  | Aktiviert und nicht standardmäßig ausgewählt   |
| Nie aufzeichnen               | Deaktiviert und nicht ausgewählt                            | Deaktiviert und nicht ausgewählt      |

Wenn die Richtlinie auf **"Immer aufzeichnen"** festgelegt ist, enthält die Richtlinienseite die folgenden ausgewählten Optionen:

![Richtlinieneinstellungen für Liveereignisse](../media/live-event-recording-policy.png "Screenshot der Richtlinieneinstellungen für Liveereignisse im Microsoft Teams Admin Center")

## <a name="storage-and-persistence-behavior"></a>Speicher- und Persistenzverhalten

| Option                                       | Status   | DVR                                                   | VOD                                                     | Aufzeichnung läuft                |
| ------------------------------------------------ | ------------ | --------------------------------------------------------- | ----------------------------------------------------------- | ---------------------------- |
| Aufzeichnung für Produzenten und Presenter verfügbar | Ausgewählt     | DVR ist verfügbar, und die Azure Media Services (AMS)-Ressource wird 180 Tage lang gespeichert. | Teilnehmer können auf das Ereignis zugreifen und es anschauen                     |                              |
|                                                  | Nicht ausgewählt | DVR ist verfügbar, und die AMS-Ressource wird 180 Tage lang gespeichert. | Teilnehmer erhalten nach dem Ende keinen Zugriff auf das Ereignis |                              |
||Deaktiviert (Nicht ausgewählt)|DVR ist verfügbar, und die AMS-Ressource wird nach dem Ereignis gelöscht.|Teilnehmer erhalten nach dem Ende keinen Zugriff auf das Ereignis||
| Aufzeichnung für Produzenten und Presenter verfügbar | Ausgewählt     |                                                           |                                                             | Ein MP4 wird erstellt und gespeichert |
|                                                  | Nicht ausgewählt |                                                           |                                                             | Es wird keine Datei erstellt           |

### <a name="related-topics"></a>Verwandte Themen

- [Was sind Liveereignisse von Teams?](what-are-teams-live-events.md)
- [Planen von Teams-Liveereignissen](plan-for-teams-live-events.md)
- [Konfigurieren der Einstellungen für Liveereignisse in Teams](configure-teams-live-events.md)
- [Aufzeichnung der Besprechungsaufzeichnung in Teams clouds](../cloud-recording.md)
