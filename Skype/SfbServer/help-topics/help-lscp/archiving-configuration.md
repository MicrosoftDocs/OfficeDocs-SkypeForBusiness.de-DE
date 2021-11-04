---
title: Archivierungskonfiguration
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
ms.date: 3/27/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.lscp.MonArchSettingMain
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: 9c2fd164-a9b8-40e6-a1c4-423a7fe34aba
description: 'Sie verwenden Archivierungskonfigurationen, um die Archivierungsoptionen für Ihre Skype for Business Server Bereitstellung zu steuern, einschließlich der Aktivierung und Deaktivierung der folgenden Optionen:'
ms.openlocfilehash: d8dadcb81254254b96802870e8d4e9a22da038a1
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/04/2021
ms.locfileid: "60744731"
---
# <a name="archiving-configuration"></a>Archivierungskonfiguration
 
Sie verwenden Archivierungskonfigurationen, um die Archivierungsoptionen für Ihre Skype for Business Server Bereitstellung zu steuern, einschließlich der Aktivierung und Deaktivierung der folgenden Optionen:
  
- Blockieren von Chat- und Konferenzsitzungen bei Archivierungsfehlern
    
- Integration in Exchange 2013-Speicher für Benutzer, die am Exchange 2013 verwaltet werden
    
- Bereinigen archivierter Daten
    
Zu den Archivierungskonfigurationen gehören die globale Konfiguration und optional eine oder mehrere Archivierungskonfigurationen:
  
- **Globale Konfiguration** Die globale Konfiguration wird standardmäßig in allen Skype for Business Server Bereitstellungen erstellt. Sie können die globale Konfiguration bearbeiten, aber Sie können diese Archivierungskonfiguration nicht löschen. Wenn Sie versuchen, das Löschen durchzuführen, werden alle Optionen auf die Standardwerte zurückgesetzt.
    
- **Standortkonfiguration (optional)** Sie können eine oder mehrere Archivierungskonfigurationen für Standorte angeben, die Sie jeweils zum Steuern der Archivierungsoptionen für einen bestimmten Standort konfigurieren können. Eine Standortkonfiguration setzt die globale Konfiguration außer Kraft, jedoch nur für die in den Archivierungsstandortkonfigurationen angegebenen Standorte. Sie können Standortkonfigurationen bearbeiten oder löschen.
    
- **Poolkonfiguration (optional)** Sie können eine oder mehrere Archivierungskonfigurationen des Pools angeben, um die Archivierungsoptionen für einen bestimmten Pool zu steuern. Eine Poolkonfiguration setzt die globale Konfiguration und Standortkonfiguration außer Kraft, jedoch nur für die in den Archivierungspoolkonfigurationen angegebenen Pools. Sie können Poolkonfigurationen bearbeiten oder löschen.
    
> [!NOTE]
> Archivierungskonfigurationen gelten für Benutzer, die auf Skype for Business Server verwaltet werden, und, wenn Sie Exchange zum Speichern von Archivierungsdaten in Microsoft Exchange verwenden, für Benutzer, die auf Exchange 2013 verwaltet werden, aber für Benutzer, die am Exchange 2013 verwaltet werden, geringfügig unterschiedlich implementiert werden. Die Unterschiede werden im nächsten Abschnitt beschrieben. 
  
Auf der Seite **Archivierungskonfiguration** sind die einzelnen Archivierungsrichtlinien aufgeführt, die für die Bereitstellung konfiguriert sind. Außerdem werden der Richtlinienname und -bereich (global, Standort oder Pool) sowie die für eine Archivierungskonfiguration aktivierten Archivierungsoptionen angezeigt. Auf der Seite **Archivierungskonfiguration** haben Sie die folgenden Möglichkeiten:
- **Neu** Sie können eine oder mehrere der folgenden optionalen Archivierungskonfigurationen hinzufügen.
    
  - Standortkonfiguration
    
  - Poolkonfiguration
    
- **Bearbeiten** Sie können die Optionen aller auf der Seite aufgeführten Archivierungskonfigurationen ändern. Mit dieser Option haben Sie folgende Möglichkeiten:
    
  - **Details anzeigen** Mit dieser Option wird ein Dialogfeld geöffnet, in dem Sie die Archivierungsoptionen für die ausgewählte Archivierungskonfiguration ändern können. Sie können nur für jeweils eine Archivierungskonfiguration Details anzeigen.
    
  - **Alle auswählen** Mit dieser Option werden alle Archivierungskonfigurationen in der Liste ausgewählt.
    
  - **Löschen** Mit dieser Option werden alle ausgewählten Archivierungskonfigurationen gelöscht.
    
- **Aktion** Sie können diese Option verwenden, um die Archivierung von Chat- oder Webkonferenzsitzungen in allen auf der Seite aufgeführten Konfigurationen schnell zu aktivieren oder zu deaktivieren, anstatt die Konfiguration zu bearbeiten. Die unter **Aktion** verfügbaren Optionen richten sich danach, welche Option in der Archivierungskonfiguration momentan angegeben ist. Alle Optionen sind verfügbar, mit Ausnahme der Option, die für die Archivierungskonfiguration derzeit wirksam ist. Folgende Optionen sind vorhanden:
    
  - **Chatsitzungen archivieren**
    
  - **Chat- und Webkonferenzsitzungen archivieren**
    
  - **Archivierung deaktivieren**
    
- **Aktualisieren** Sie können die Seite **"Archivierungskonfiguration"** aktualisieren, um den Status der Optionen aller Archivierungskonfigurationen zu überprüfen.
    
Ausführliche Informationen zu den Archivierungsfeatures und -funktionen, einschließlich Exchange Integration, finden Sie unter [Plan for archiving in Skype for Business Server 2015,](../../plan-your-deployment/archiving/archiving.md)Deploy archiving for Skype for Business Server [2015](../../deploy/deploy-archiving/deploy-archiving.md)und [Manage archiving in Skype for Business Server 2015.](../../manage/archiving/archiving.md)

