---
title: Archivierungsrichtlinie
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/27/2015
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.MonArchPolicyMain
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 9b69f1fa-8f3b-450e-aa89-91fd462f198d
description: 'Zum Aktivieren von Archivierungsrichtlinien verwendet und Archivierung für Benutzer deaktivieren auf Skype für Business Server verwaltet. In einer Archivierungsrichtlinie können Sie die Archivierung jeweils für eine oder beide der folgenden Kommunikationsarten aktivieren oder deaktivieren:'
ms.openlocfilehash: 03a2645019c083dc3ebdc0c9ca29f4a21d231085
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "33926136"
---
# <a name="archiving-policy"></a>Archivierungsrichtlinie
 
Zum Aktivieren von Archivierungsrichtlinien verwendet und Archivierung für Benutzer deaktivieren auf Skype für Business Server verwaltet. In einer Archivierungsrichtlinie können Sie die Archivierung jeweils für eine oder beide der folgenden Kommunikationsarten aktivieren oder deaktivieren:
  
- Interne Kommunikation
    
- Externe Kommunikation (mit mindestens einem Benutzer außerhalb des internen Netzwerks)
    
Zu den Archivierungsrichtlinien gehören die globale Richtlinie und optional eine oder mehrere Archivierungsrichtlinien für Standorte und Benutzer:
  
- **Globale Richtlinie** Die globale Richtlinie wird standardmäßig in allen Bereitstellungen erstellt. Sie können die globale Richtlinie bearbeiten, aber Sie können diese Richtlinie nicht löschen. Wenn Sie versuchen, sie zu löschen, werden alle Optionen auf die Standardwerte zurückgesetzt.
    
- **Richtlinien für den Standort (optional)** Sie können eine oder mehrere Website Archivierungsrichtlinien angeben, von denen jedes Sie zum Aktivieren und Deaktivieren der Archivierung von interner oder externer Kommunikation für eine einzelne Website konfigurieren können. Eine Standortrichtlinie setzt die globale Richtlinie außer Kraft, jedoch nur für die in den Archivierungsstandortrichtlinien angegebenen Standorte. Sie können Standortrichtlinien bearbeiten oder löschen.
    
- **Richtlinie für Benutzer (optional)** Sie können eine oder mehrere Benutzer Archivierungsrichtlinien angeben, von denen jedes Sie zum Aktivieren und Deaktivieren der Archivierung von interner oder externer Kommunikation für einen bestimmten Benutzer oder eine Benutzergruppe konfigurieren können. Eine Benutzerrichtlinie setzt die globale Richtlinie und die Standortrichtlinien außer Kraft, jedoch nur für die Benutzer und Benutzergruppen, denen Sie Archivierungsrichtlinien auf Benutzerebene zuweisen. Sie können Benutzerrichtlinien bearbeiten oder löschen.
    
> [!NOTE]
> Archivierungsrichtlinien gelten nur für Benutzer, die auf Skype für Business Server verwaltet. Wenn Sie zum Speichern von Exchange-Integration verwenden, Archivieren von Daten in Microsoft Exchange, klicken Sie dann auf Exchange 2013 Richtlinien Steuerelement Archivierung für Benutzer auf Exchange 2013 verwaltet. Zum Aktivieren der Archivierung für die Benutzer muss das Postfach des Benutzers auf Compliance-Archiv platziert werden. 
  
Auf der Seite **Archivierungsrichtlinie** sind die einzelnen Archivierungsrichtlinien aufgeführt, die für die Bereitstellung konfiguriert sind. Außerdem werden der Richtlinienname und -bereich (Global, Standort oder Benutzer) sowie die für eine Archivierungsrichtlinie aktivierten Archivierungsoptionen angezeigt. Auf der Seite **Archivierungsrichtlinie** haben Sie die folgenden Möglichkeiten:
- **Neue** Sie können eine oder mehrere der folgenden optionalen Archivierungsrichtlinien hinzufügen:
    
  - Standortrichtlinie
    
  - Benutzerrichtlinie
    
- **Bearbeiten** Sie können keines der Archivierungsrichtlinien auf der Seite aufgeführten Optionen ändern. Mit dieser Option haben Sie folgende Möglichkeiten:
    
  - **Details anzeigen**   Mit dieser Option öffnen Sie ein Dialogfeld, in dem Sie die Archivierungsoptionen für eine Archivierungsrichtlinie ändern können.
    
  - **Alles auswählen** Mit dieser Option werden alle Archivierungsrichtlinien der Liste ausgewählt.
    
  - **Löschen**   Mit dieser Option werden alle ausgewählten Archivierungsrichtlinien gelöscht.
    
- **Aktion** Verwenden Sie diese Option, um schnell aktivieren oder Deaktivieren der Archivierung von interner oder externer Kommunikation in einer Richtlinie auf der Seite, anstatt zur Bearbeitung der Richtlinie aufgeführt. Die unter **Aktion** verfügbaren Optionen richten sich danach, welche Option in der Archivierungsrichtlinie momentan angegeben ist. Alle Optionen sind verfügbar, mit Ausnahme der Option, die aktuell für die Archivierungsrichtlinie wirksam ist. Folgende Optionen sind vorhanden:
    
  - **Archivierung interner Kommunikation aktivieren**
    
  - **Archivierung interner Kommunikation deaktivieren**
    
  - **Archivierung externer Kommunikation aktivieren**
    
  - **Archivierung externer Kommunikation deaktivieren**
    
- **Aktualisieren** Sie können die Seite **Archivierungsrichtlinie** zum Überprüfen des Status der Optionen aller Archivierungsrichtlinien aktualisieren.
    
Weitere Informationen über die Archivierungsfunktion und Funktionen, einschließlich Exchange-Integration finden Sie unter [Planen für die Archivierung in Skype für Business Server 2015](../../plan-your-deployment/archiving/archiving.md), [Archivierung für Skype für Business Server 2015 bereitstellen](../../deploy/deploy-archiving/deploy-archiving.md)und verwalten [Archivierung in Skype für Business Server 2015](../../manage/archiving/archiving.md).

