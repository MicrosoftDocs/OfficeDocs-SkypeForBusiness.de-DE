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
description: Hier finden Sie Informationen zu Richtlinien für die Aufzeichnung von Liveereignisen.
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 77bfb6f3d57b885a11574f08f21da5f8c1c488a9832aeae1ffe602c4a922d227
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2021
ms.locfileid: "54319658"
---
# <a name="live-event-recording-policies-in-microsoft-teams"></a>Richtlinien für die Aufzeichnung von Liveereignisen in Microsoft Teams

Es gibt mehrere Optionen zum Aufzeichnen eines Microsoft Teams Live-Ereignisses. Die Aufzeichnungsoptionen werden mithilfe von Aufzeichnungsrichtlinien festgelegt. In diesem Artikel werden die verschiedenen Einstellungen beschrieben.

Die Aufzeichnungsoptionen werden mit dem [PowerShell-Befehl Set-CsTeamsMeetingBroadcastPolicy festgelegt.](/powershell/module/skype/set-csteamsmeetingbroadcastpolicy)

## <a name="scheduling-and-option-behaviors"></a>Terminplanung und Optionsverhalten

Beim Planen einer Liveereignisaufzeichnung gibt es zwei Organisatoroptionen:

- Aufzeichnung für Produzenten und Moderatoren verfügbar

  - Aufzeichnungsdatei: Stellt eine Aufzeichnungsdatei bereit, die Produzenten und Moderatoren herunterladen können, nachdem das Ereignis vorbei ist.

- Aufzeichnung für Teilnehmer verfügbar

  - DVR: Ein digitaler Videorekorder (DVR) ermöglicht Teilnehmern das Zurückspulen und Anhalten während des Ereignisses.

  - VOD: Ein Video auf Abruf (VoD) ermöglicht Teilnehmern, das Ereignis nach dem Ende des Ereignisses zu verfolgen.

## <a name="broadcast-recording-policy-setting"></a>Richtlinieneinstellung für Aufzeichnung übertragen

Im Rahmen der Übertragungsrichtlinie können Sie die Aufzeichnung für ein Liveereignis aktivieren oder deaktivieren.

| &nbsp;| Aufzeichnung für Produzenten und Moderatoren verfügbar | Aufzeichnung für Teilnehmer verfügbar |
| ------------------------------- | ---------------------------------------------------- | ------------------------------------- |
| Immer aufzeichnen               | Deaktiviert und ausgewählt                                | Aktiviert und ausgewählt         |
| Organisator kann Aufzeichnen oder nicht | Standardmäßig aktiviert und ausgewählt                  | Standardmäßig aktiviert und ausgewählt   |
| Nie aufzeichnen               | Deaktiviert und nicht ausgewählt                            | Deaktiviert und nicht ausgewählt      |

## <a name="storage-and-persistence-behavior"></a>Storage und Persistenzverhalten

| Option                                       | Status   | DVR                                                   | VOD                                                     | Aufzeichnung läuft                |
| ------------------------------------------------ | ------------ | --------------------------------------------------------- | ----------------------------------------------------------- | ---------------------------- |
| Aufzeichnung für Teilnehmer verfügbar | Ausgewählt     | DVR ist verfügbar, und Azure Media Services (AMS)-Ressource wird 180 Tage lang gespeichert. | Teilnehmer können auf das Ereignis zugreifen und es anschauen                     |                              |
|                                                  | Nicht ausgewählt | DVR ist verfügbar, und die AMS-Ressource wird 180 Tage lang gespeichert. | Teilnehmer erhalten keinen Zugriff auf das Ereignis, nachdem es vorbei ist |                              |
||Deaktiviert (Nicht ausgewählt)|DVR ist verfügbar, und die AMS-Ressource wird nach dem -Ereignis gelöscht.|Teilnehmer erhalten keinen Zugriff auf das Ereignis, nachdem es vorbei ist||
| Aufzeichnung für Produzenten und Moderatoren verfügbar | Ausgewählt     |                                                           |                                                             | Eine MP4-Datei wird erstellt und gespeichert. |
|                                                  | Nicht ausgewählt |                                                           |                                                             | Es wird keine Datei erstellt           |

### <a name="related-topics"></a>Verwandte Themen

- [Was sind Teams-Liveereignisse?](what-are-teams-live-events.md)
- [Planen von Teams-Liveereignissen](plan-for-teams-live-events.md)
- [Konfigurieren der Einstellungen für Liveereignisse in Teams](configure-teams-live-events.md)
- [Teams Besprechungsaufzeichnung mit Wolken](../cloud-recording.md)
