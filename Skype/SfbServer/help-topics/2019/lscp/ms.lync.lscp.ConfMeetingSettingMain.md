---
title: Besprechungskonfiguration
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.lscp.ConfMeetingSettingMain
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 24e8f749-d54c-4315-a8fe-bb9303b356ef
ROBOTS: NOINDEX, NOFOLLOW
description: Die Konfigurationseinstellungen für Besprechungen definieren den Typ von Konferenzen (auch calledmeetings), die Benutzer erstellen können, und Steuern, wie (oder ob) anonyme Benutzer und Benutzer von Einwahlkonferenzen an diesen Konferenzen teilnehmen können. Diese Einstellungen gelten nur für geplante Besprechungen. Sie gelten nicht für Ad-hoc-Besprechungen, die durch Klicken auf die Option Sofortbesprechung erstellt werden.
ms.openlocfilehash: 15dfed475928fe56b42e7a47522c911256b0f033
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/03/2020
ms.locfileid: "41705010"
---
# <a name="meeting-configuration"></a>Besprechungskonfiguration

Konfigurationseinstellungen für Besprechungen legen fest, welche Arten von Konferenzen (auch „Besprechungen“ genannt) Benutzer erstellen können. Zusätzlich steuern sie, wie (bzw. ob) anonyme Benutzer und Benutzer von Einwahlkonferenzen an diesen Besprechungen teilnehmen können. Diese Einstellungen gelten nur für geplante Besprechungen und nicht für Ad-hoc-Besprechungen, die durch Klicken auf die Option „Sofortbesprechung“ erstellt werden.

Konfigurationen für Besprechungen gelten auf globaler Ebene, Standortebene oder Poolebene:

- **Globale besprechungskonfiguration:** Die globale besprechungskonfiguration wird standardmäßig erstellt. Sie können die globale Besprechungskonfiguration bearbeiten, jedoch nicht löschen. Wenn Sie versuchen, die globale Besprechungskonfiguration zu entfernen, werden alle Einstellungen auf die Standardwerte zurückgesetzt.

- **Konfiguration der Website Besprechung (optional):** Sie können eine oder mehrere Website Besprechungs Konfigurationen erstellen, die jeweils für eine bestimmte Website gelten. Standortkonfigurationen setzen die globale Konfiguration außer Kraft.

- **Pool-besprechungskonfiguration (optional):** Sie können eine oder mehrere Pool-Besprechungs Konfigurationen erstellen, die jeweils für einen bestimmten Pool gelten. Poolkonfigurationen setzen die globale Konfiguration und die Standortkonfigurationen außer Kraft.

Auf der Seite **Besprechungskonfiguration** wird eine Liste mit allen Besprechungskonfigurationen angezeigt, die für Ihre Organisation definiert sind.

## <a name="tasks-you-can-perform"></a>Mögliche Aufgaben

Auf der Seite **Besprechungskonfiguration** können Sie die folgenden Aufgaben ausführen:

- Erstellen einer neuen Besprechungskonfiguration auf Standort- oder Poolebene

- Ändern der globalen Konfiguration oder einer vorhandenen Standort- oder Poolkonfiguration

- Löschen einer Standort- oder Poolkonfiguration

## <a name="ui-reference"></a>Referenz zur Benutzeroberfläche

In der folgenden Liste werden die Befehle der Seite beschrieben.

- **Neu** Startet eine neue Konfiguration für eine Website Besprechung oder eine Pool-besprechungskonfiguration.

- **Bearbeiten** von Öffnet die ausgewählte besprechungskonfiguration, um Sie zu bearbeiten, wählt alle Besprechungs Konfigurationen in der Liste aus oder löscht die ausgewählte Websitekonfiguration oder Poolkonfiguration.

    > [!NOTE]
    > Für die globale Besprechungskonfiguration werden die Einstellungen mit **Löschen** auf die Standardwerte zurückgesetzt.

- **Aktualisieren** Aktualisiert die Liste der Besprechungs Konfigurationen.

In der folgenden Liste werden die Felder der Seite beschrieben.

- **Name** Identifiziert die besprechungskonfiguration.

- **Bereich** Identifiziert den Bereich der besprechungskonfiguration: Global, Site oder Pool.

Ausführliche Informationen zur Verwendung von Besprechungskonfigurationen finden Sie in der Betriebsdokumentation unter [Create a or modify a Collection of Meeting Configuration Settings](https://technet.microsoft.com/library/ce6773c1-a0d5-4405-8e32-33a6f3a46a1a.aspx).


