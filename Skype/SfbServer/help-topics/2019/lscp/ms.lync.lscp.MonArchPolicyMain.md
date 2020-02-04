---
title: Archivierungsrichtlinie
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.lscp.MonArchPolicyMain
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 9b69f1fa-8f3b-450e-aa89-91fd462f198d
ROBOTS: NOINDEX, NOFOLLOW
description: 'Sie verwenden Archivierungsrichtlinien, um die Archivierung für Benutzer zu aktivieren und zu deaktivieren, die in Skype for Business Server verwaltet werden. In einer Archivierungsrichtlinie können Sie die Archivierung jeweils für eine oder beide der folgenden Kommunikationsarten aktivieren oder deaktivieren:'
ms.openlocfilehash: 63d1001a972b185fd8e36596798bc23e36a6ca3a
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/03/2020
ms.locfileid: "41704790"
---
# <a name="archiving-policy"></a>Archivierungsrichtlinie
 
Sie verwenden Archivierungsrichtlinien, um die Archivierung für Benutzer zu aktivieren und zu deaktivieren, die in Skype for Business Server verwaltet werden. In einer Archivierungsrichtlinie können Sie die Archivierung jeweils für eine oder beide der folgenden Kommunikationsarten aktivieren oder deaktivieren:
  
- Interne Kommunikation
    
- Externe Kommunikation (mit mindestens einem Benutzer außerhalb des internen Netzwerks)
    
Zu den Archivierungsrichtlinien gehören die globale Richtlinie und optional eine oder mehrere Archivierungsrichtlinien für Standorte und Benutzer:
  
- **Globale Richtlinie** Die globale Richtlinie wird in allen Bereitstellungen standardmäßig erstellt. Sie können die globale Richtlinie bearbeiten, aber Sie können diese Richtlinie nicht löschen. Wenn Sie versuchen, sie zu löschen, werden alle Optionen auf die Standardwerte zurückgesetzt.
    
- **Website Richtlinie (optional)** Sie können eine oder mehrere Website Archivierungsrichtlinien angeben, die jeweils für die Aktivierung und Deaktivierung der Archivierung interner oder externer Kommunikation für eine einzelne Website konfiguriert werden können. Eine Standortrichtlinie setzt die globale Richtlinie außer Kraft, jedoch nur für die in den Archivierungsstandortrichtlinien angegebenen Standorte. Sie können Standortrichtlinien bearbeiten oder löschen.
    
- **Benutzerrichtlinie (optional)** Sie können eine oder mehrere Benutzer Archivierungsrichtlinien angeben, die jeweils für die Aktivierung und Deaktivierung der Archivierung interner oder externer Kommunikation für einen bestimmten Benutzer oder eine Benutzergruppe konfiguriert werden können. Eine Benutzerrichtlinie setzt die globale Richtlinie und die Standortrichtlinien außer Kraft, jedoch nur für die Benutzer und Benutzergruppen, denen Sie Archivierungsrichtlinien auf Benutzerebene zuweisen. Sie können Benutzerrichtlinien bearbeiten oder löschen.
    
> [!NOTE]
> Archivierungsrichtlinien gelten nur für Benutzer, die in Skype for Business Server verwaltet werden. Wenn Sie die Exchange-Integration zum Speichern von Archivierungsdaten in Microsoft Exchange verwenden, Steuern Exchange-Richtlinien die Archivierung für in Exchange beheimatete Benutzer. Um die Archivierung für diese Benutzer zu aktivieren, muss das Postfach des Benutzers in-situ-Speicherplatz platziert werden. 
  
Auf der Seite **Archivierungsrichtlinie** sind die einzelnen Archivierungsrichtlinien aufgeführt, die für die Bereitstellung konfiguriert sind. Außerdem werden der Richtlinienname und -bereich (Global, Standort oder Benutzer) sowie die für eine Archivierungsrichtlinie aktivierten Archivierungsoptionen angezeigt. Auf der Seite **Archivierungsrichtlinie** haben Sie die folgenden Möglichkeiten:
- **Neu** Sie können eine oder mehrere der folgenden optionalen Archivierungsrichtlinien hinzufügen:
    
  - Standortrichtlinie
    
  - Benutzerrichtlinie
    
- **Bearbeiten** von Sie können die Optionen für alle auf der Seite aufgelisteten Archivierungsrichtlinien ändern. Mit dieser Option haben Sie folgende Möglichkeiten:
    
  - **Details anzeigen**   Mit dieser Option öffnen Sie ein Dialogfeld, in dem Sie die Archivierungsoptionen für eine Archivierungsrichtlinie ändern können.
    
  - **Alles auswählen** Mit dieser Option werden alle Archivierungsrichtlinien der Liste ausgewählt.
    
  - **Löschen**   Mit dieser Option werden alle ausgewählten Archivierungsrichtlinien gelöscht.
    
- **Aktion** Sie können diese Option verwenden, um die Archivierung interner oder externer Kommunikation in einer auf der Seite aufgelisteten Richtlinie schnell zu aktivieren oder zu deaktivieren, anstatt die Richtlinie zu bearbeiten. Die unter **Aktion** verfügbaren Optionen richten sich danach, welche Option in der Archivierungsrichtlinie momentan angegeben ist. Alle Optionen sind verfügbar, mit Ausnahme der Option, die aktuell für die Archivierungsrichtlinie wirksam ist. Folgende Optionen sind vorhanden:
    
  - **Archivierung interner Kommunikation aktivieren**
    
  - **Archivierung interner Kommunikation deaktivieren**
    
  - **Archivierung externer Kommunikation aktivieren**
    
  - **Archivierung externer Kommunikation deaktivieren**
    
- **Aktualisieren** Sie können die Seite **Archivierungsrichtlinie** aktualisieren, um den Status der Optionen aller Archivierungsrichtlinien zu überprüfen.
    
Details zum Archivierungsfeature und zu den Funktionen, einschließlich der Exchange-Integration, finden Sie unter [Planen der Archivierung in Skype for Business Server](../../../plan-your-deployment/archiving/archiving.md), [Bereitstellen der Archivierung für Skype for Business Server](../../../deploy/deploy-archiving/deploy-archiving.md)und [Verwalten der Archivierung in Skype for Business Server](../../../manage/archiving/archiving.md).

