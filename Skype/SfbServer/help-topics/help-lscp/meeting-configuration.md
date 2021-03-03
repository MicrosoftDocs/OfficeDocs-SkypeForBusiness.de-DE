---
title: Besprechungskonfiguration
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/24/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.lscp.ConfMeetingSettingMain
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 24e8f749-d54c-4315-a8fe-bb9303b356ef
description: Besprechungskonfigurationseinstellungen definieren den Typ von Konferenzen (auch alsMeetings bezeichnet), die Benutzer erstellen können, und steuern, wie (oder ob) anonyme Benutzer und Benutzer von Einwahlkonferenzen an diesen Konferenzen teilnehmen können. Diese Einstellungen gelten nur für geplante Besprechungen. Sie gelten nicht für Ad-hoc-Besprechungen, die durch Klicken auf die Option "Sofortbesprechungen" im Client erstellt wurden.
ms.openlocfilehash: 804aa22f750c86aacacb9bd4d938d364967b86f9
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2021
ms.locfileid: "49810895"
---
# <a name="meeting-configuration"></a>Besprechungskonfiguration

Besprechungskonfigurationseinstellungen definieren den Typ von Konferenzen (auch als "Besprechungen" bezeichnet), die Benutzer erstellen können, und steuern, wie (oder ob) anonyme Benutzer und Benutzer von Einwahlkonferenzen an diesen Konferenzen teilnehmen können. Diese Einstellungen gelten nur für geplante Besprechungen. Sie gelten nicht für Ad-hoc-Besprechungen, die durch Klicken auf die Option "Sofortbesprechungen" im Client erstellt wurden.

Konfigurationen für Besprechungen gelten auf globaler Ebene, Standortebene oder Poolebene:

- **Globale Besprechungskonfiguration:** Die globale Besprechungskonfiguration wird standardmäßig erstellt. Sie können die globale Besprechungskonfiguration bearbeiten, jedoch nicht löschen. Wenn Sie versuchen, die globale Besprechungskonfiguration zu entfernen, werden alle Einstellungen auf die Standardwerte zurückgesetzt.

- **Konfiguration von Besprechungen am Standort (optional):** Sie können eine oder mehrere Besprechungskonfigurationen für Den Standort erstellen, die jeweils für einen bestimmten Standort gelten. Standortkonfigurationen setzen die globale Konfiguration außer Kraft.

- **Pool-Besprechungskonfiguration (optional):** Sie können eine oder mehrere Besprechungskonfigurationen für Pools erstellen, die jeweils für einen bestimmten Pool gelten. Poolkonfigurationen setzen die globale Konfiguration und Standortkonfigurationen außer Kraft.

Auf der Seite **Besprechungskonfiguration** wird eine Liste mit allen Besprechungskonfigurationen angezeigt, die für Ihre Organisation definiert sind.

## <a name="tasks-you-can-perform"></a>Mögliche Aufgaben

Auf der Seite **Besprechungskonfiguration** können Sie die folgenden Aufgaben ausführen:

- Erstellen einer neuen Besprechungskonfiguration auf Standort- oder Poolebene

- Ändern der globalen Konfiguration oder einer vorhandenen Standort- oder Poolkonfiguration

- Löschen einer Standort- oder Poolkonfiguration

## <a name="ui-reference"></a>Referenz zur Benutzeroberfläche

In der folgenden Liste sind die Befehle der Seite beschrieben.

- **Neu** Startet eine neue Standort- oder Pool-Besprechungskonfiguration.

- **Bearbeiten** Öffnet die ausgewählte Besprechungskonfiguration, um sie zu bearbeiten, wählt alle Besprechungskonfigurationen in der Liste aus oder löscht die ausgewählte Standort- oder Poolkonfiguration.

    > [!NOTE]
    > Für die globale Besprechungskonfiguration werden die Einstellungen mit **Löschen** auf die Standardwerte zurückgesetzt.

- **Aktualisieren** Aktualisiert die Liste der Besprechungskonfigurationen.

In der folgenden Liste sind die Felder der Seite beschrieben.

- **Name** Identifiziert die Besprechungskonfiguration.

- **Bereich** Gibt den Bereich der Besprechungskonfiguration an: global, Standort oder Pool.

Ausführliche Informationen zur Verwendung von Besprechungskonfigurationen finden Sie unter [Create a or modify a Collection of Meeting Configuration Settings](https://technet.microsoft.com/library/ce6773c1-a0d5-4405-8e32-33a6f3a46a1a.aspx) in der Betriebsdokumentation.


