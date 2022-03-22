---
title: Einchecken und Raumfreigabe in Microsoft Teams Panels
ms.author: czawideh
author: cazawideh
manager: serdars
ms.reviewer: gary.lai
ms.service: msteams
audience: Admin
appliesto:
- Microsoft Teams
f1.keywords:
- NOCSH
ms.collection:
- M365-voice
ms.topic: reference
search.appverid: MET150
description: Dieser Artikel enthält Anleitungen zum Aktivieren des Eincheckens und der Raumfreigabe Teams Panels.
ms.openlocfilehash: 9e90916c5db4d5ec32a40f0e021f9bf7b294d09f
ms.sourcegitcommit: f8b935e009895138eddfc1ae360b7b2ace747d3c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/02/2022
ms.locfileid: "63689100"
---
# <a name="check-in-and-room-release-on-microsoft-teams-panels"></a>Einchecken und Raumfreigabe in Microsoft Teams Panels

Wenn Das Einchecken und die Raumfreigabe aktiviert sind, checken die Benutzer Teams Bereiche in dem Raum ein, den sie zu Beginn der Besprechung reserviert haben. Wenn sich ein Benutzer nicht innerhalb einer festgelegten Frist nach dem Beginn der Besprechung eincheckt, lehnt der Besprechungsraum die Besprechungs-Einladung ab, sendet eine Absagenachricht an den Besprechungsorganisator, und der Raum kann von anderen reserviert werden.  

## <a name="requirements"></a>Anforderungen 

Dieses Feature kann in einer eigenständigen Bereitstellung im Teams verwendet werden. Sie können für zusätzliche Funktionen wie Eincheckbenachrichtigungen auch Teams-Panels mit Teams-Räume unter Android mit App-Version 1449/1.0.96.2022011305 oder höher koppeln.  

## <a name="enable-check-in-and-room-release"></a>Aktivieren von Einchecken und Raumfreigabe 

Der Einchecken und die Raumfreigabe ist standardmäßig deaktiviert. Um sie zu aktivieren,  

1. Melden Sie Teams Anmeldeinformationen im Anmeldebereich an.  

2. Wechseln Sie **zu Einstellungen > Einstellungen > für Einstellungen > für Geräte und Einstellungen > Besprechungen**.

3. Aktivieren Sie Freigaberaum, wenn niemand eincheckt.

4. Um die Zeit anzupassen, die Benutzer einchecken müssen, bevor der Raum freigegeben wird, wechseln Sie zu Freigabe nach **:** und wählen Sie eine Option aus der Dropdownliste aus.  

Wenn Teams-Bereiche mit einem Raum Teams Android gekoppelt sind, kann sich ein Benutzer in den Besprechungsraum Teams einchecken.  

## <a name="turn-on-check-in-notifications"></a>Aktivieren von Eincheckbenachrichtigungen

> [!NOTE]
> Dieses Feature ist derzeit nur für Teams verfügbar, die mit einem Raum Teams Android gekoppelt sind. Der Teams und der Teams müssen bei demselben Ressourcenkonto angemeldet sein. Weitere [Informationen finden Sie Teams Koppeln eines Microsoft Teams mit einem Raum unter Android](use-teams-panels.md#pair-a-teams-panel-with-a-microsoft-teams-room-on-android).  

Eingecheckte Benachrichtigungen werden gesendet, wenn eine Besprechung über das reservierte Zeitfenster fortgeht. Sobald sich ein Benutzer aus der nächsten Besprechung eincheckt, wird die Benachrichtigung vor dem Raumanzeiger zu der geplanten Startzeit der Besprechung angezeigt, damit die vorherigen Besprechungsteilnehmer wissen, dass ihre Reservierung beendet ist und dass Personen auf den Raum warten.  

Zum Aktivieren von Eincheckbenachrichtigungen  

1. Melden Sie Teams Anmeldeinformationen im Anmeldebereich an. 

2. Wechseln Sie **zu Einstellungen > Einstellungen > für Einstellungen > für Geräte und Einstellungen > Besprechungen**.

3. Wechseln Sie **zu Einchecken,** und aktivieren Sie **Eincheckbenachrichtigung senden**.

## <a name="related-topics"></a>Verwandte Themen

- [So wird's Microsoft Teams verwendet](use-teams-panels.md)

- [Microsoft Teams-Panels](teams-panels.md)