---
title: Archivierungsrichtlinie
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
- ms.lync.lscp.MonArchPolicyMain
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
localization_priority: Normal
ms.assetid: 9b69f1fa-8f3b-450e-aa89-91fd462f198d
ROBOTS: NOINDEX, NOFOLLOW
description: 'Sie verwenden Archivierungsrichtlinien, um die Archivierung für Benutzer zu aktivieren und zu deaktivieren, die in Skype for Business Server gespeichert sind. In einer Archivierungsrichtlinie können Sie die Archivierung jeweils für eine oder beide der folgenden Kommunikationsarten aktivieren oder deaktivieren:'
ms.openlocfilehash: 041fc71da18ff38b14e82ce9d2ab14f366326b29
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2021
ms.locfileid: "49833615"
---
# <a name="archiving-policy"></a>Archivierungsrichtlinie
 
Sie verwenden Archivierungsrichtlinien, um die Archivierung für Benutzer zu aktivieren und zu deaktivieren, die in Skype for Business Server gespeichert sind. In einer Archivierungsrichtlinie können Sie die Archivierung jeweils für eine oder beide der folgenden Kommunikationsarten aktivieren oder deaktivieren:
  
- Interne Kommunikation
    
- Externe Kommunikation (mit mindestens einem Benutzer außerhalb des internen Netzwerks)
    
Zu den Archivierungsrichtlinien gehören die globale Richtlinie und optional eine oder mehrere Archivierungsrichtlinien für Standorte und Benutzer:
  
- **Globale Richtlinie** Die globale Richtlinie wird standardmäßig in allen Bereitstellungen erstellt. Sie können die globale Richtlinie bearbeiten, aber Sie können diese Richtlinie nicht löschen. Wenn Sie versuchen, das Löschen durchzuführen, werden alle Optionen auf die Standardwerte zurückgesetzt.
    
- **Standortrichtlinie (optional)** Sie können eine oder mehrere Archivierungsrichtlinien für Den Standort angeben, die Sie jeweils so konfigurieren können, dass die Archivierung der internen oder externen Kommunikation für einen einzelnen Standort aktiviert oder deaktiviert wird. Eine Standortrichtlinie setzt die globale Richtlinie außer Kraft, jedoch nur für die in den Archivierungsstandortrichtlinien angegebenen Standorte. Sie können Standortrichtlinien bearbeiten oder löschen.
    
- **Benutzerrichtlinie (optional)** Sie können eine oder mehrere Archivierungsrichtlinien für Benutzer angeben, die Sie jeweils so konfigurieren können, dass die Archivierung der internen oder externen Kommunikation für einen bestimmten Benutzer oder eine bestimmte Benutzergruppe aktiviert oder deaktiviert wird. Eine Benutzerrichtlinie setzt die globale Richtlinie und die Standortrichtlinien außer Kraft, jedoch nur für die Benutzer und Benutzergruppen, denen Sie Archivierungsrichtlinien auf Benutzerebene zuweisen. Sie können Benutzerrichtlinien bearbeiten oder löschen.
    
> [!NOTE]
> Archivierungsrichtlinien gelten nur für Benutzer, die in Skype for Business Server gespeichert sind. Wenn Sie die Integration von Exchange zum Speichern von Archivierungsdaten in Microsoft Exchange verwenden, steuern die Exchange-Richtlinien die Archivierung für Benutzer, die in Exchange gespeichert sind. Um die Archivierung für diese Benutzer zu aktivieren, muss das Postfach des Benutzers in den In-Place platziert werden. 
  
Auf der Seite **Archivierungsrichtlinie** sind die einzelnen Archivierungsrichtlinien aufgeführt, die für die Bereitstellung konfiguriert sind. Außerdem werden der Richtlinienname und -bereich (global, Standort oder Benutzer) sowie die für eine Archivierungsrichtlinie aktivierten Archivierungsoptionen angezeigt. Auf der Seite **Archivierungsrichtlinie** haben Sie die folgenden Möglichkeiten:
- **Neu** Sie können eine oder mehrere der folgenden optionalen Archivierungsrichtlinien hinzufügen:
    
  - Standortrichtlinie
    
  - Benutzerrichtlinie
    
- **Bearbeiten** Sie können die Optionen der auf der Seite aufgeführten Archivierungsrichtlinien ändern. Mit dieser Option haben Sie folgende Möglichkeiten:
    
  - **Details anzeigen**   Mit dieser Option öffnen Sie ein Dialogfeld, in dem Sie die Archivierungsoptionen für eine Archivierungsrichtlinie ändern können.
    
  - **Alles auswählen** Mit dieser Option werden alle Archivierungsrichtlinien der Liste ausgewählt.
    
  - **Löschen**   Mit dieser Option werden alle ausgewählten Archivierungsrichtlinien gelöscht.
    
- **Aktion** Sie können diese Option verwenden, um die Archivierung der internen oder externen Kommunikation in jeder auf der Seite aufgeführten Richtlinie schnell zu aktivieren oder zu deaktivieren, anstatt die Richtlinie zu bearbeiten. Die unter **Aktion** verfügbaren Optionen richten sich danach, welche Option in der Archivierungsrichtlinie momentan angegeben ist. Alle Optionen sind verfügbar, mit Ausnahme der Option, die für die Archivierungsrichtlinie derzeit wirksam ist. Folgende Optionen sind vorhanden:
    
  - **Archivierung interner Kommunikation aktivieren**
    
  - **Archivierung interner Kommunikation deaktivieren**
    
  - **Archivierung externer Kommunikation aktivieren**
    
  - **Archivierung externer Kommunikation deaktivieren**
    
- **Aktualisieren** Sie können die Seite **"Archivierungsrichtlinie"** aktualisieren, um den Status der Optionen aller Archivierungsrichtlinien zu überprüfen.
    
Weitere Informationen zu den Archivierungsfunktionen, einschließlich der Exchange-Integration, finden Sie unter "Planen der Archivierung [in Skype for Business Server",](../../../plan-your-deployment/archiving/archiving.md)"Bereitstellen der Archivierung für Skype for Business [Server"](../../../deploy/deploy-archiving/deploy-archiving.md)und "Verwalten der Archivierung [in Skype for Business Server".](../../../manage/archiving/archiving.md)

