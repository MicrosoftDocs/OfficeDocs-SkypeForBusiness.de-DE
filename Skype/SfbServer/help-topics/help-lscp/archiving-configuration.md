---
title: Archivierungskonfiguration
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/27/2015
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.MonArchSettingMain
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 9c2fd164-a9b8-40e6-a1c4-423a7fe34aba
description: 'Verwenden Sie Archivierungskonfigurationen Steuerelement Archivierungsoptionen für Ihre Skype für Business Server-Bereitstellung, einschließlich aktivieren und deaktivieren die folgenden Optionen aus:'
ms.openlocfilehash: ac03dd94a83a755c06e88b2abce27bde9625453a
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "33887139"
---
# <a name="archiving-configuration"></a>Archivierungskonfiguration
 
Verwenden Sie Archivierungskonfigurationen Steuerelement Archivierungsoptionen für Ihre Skype für Business Server-Bereitstellung, einschließlich aktivieren und deaktivieren die folgenden Optionen aus:
  
- Blockieren von Chat- und Konferenzsitzungen bei Archivierungsfehlern
    
- Integration in Exchange 2013-Speicherung für Benutzer, die sich in Exchange 2013
    
- Bereinigen archivierter Daten
    
Zu den Archivierungskonfigurationen gehören die globale Konfiguration und optional eine oder mehrere Archivierungskonfigurationen:
  
- **Globale Konfiguration** Die globale Konfiguration wird standardmäßig in allen Skype für Business Server-Bereitstellungen erstellt. Sie können die globale Konfiguration bearbeiten, aber Sie können diese Archivierungskonfiguration nicht löschen. Wenn Sie versuchen, sie zu löschen, werden alle Optionen auf die Standardwerte zurückgesetzt.
    
- **Standortkonfiguration (optional)** Sie können eine oder mehrere Website Archivierungskonfigurationen angeben, von denen jedes Steuerelement Archivierungsoptionen für einen bestimmten Standort konfigurierbaren. Eine Standortkonfiguration setzt die globale Konfiguration außer Kraft, jedoch nur für die in den Archivierungsstandortkonfigurationen angegebenen Standorte. Sie können Standortkonfigurationen bearbeiten oder löschen.
    
- **Pool-Konfiguration (optional)** Sie können eine oder mehrere Pools Archivierungskonfiguration Steuerelement Archivierungsoptionen für einen bestimmten Pool angeben. Eine Poolkonfiguration setzt die globale Konfiguration und die Standortkonfiguration außer Kraft, jedoch nur für die in den Archivierungspoolkonfigurationen angegebenen Pools. Sie können Poolkonfigurationen bearbeiten oder löschen.
    
> [!NOTE]
> Archivierung Konfigurationen gelten für Benutzer, der in Skype für Business Server verwaltet und, wenn Sie Exchange, zum Speichern von archivierten Daten in Microsoft Exchange verwenden, für Benutzer, die sich in Exchange 2013 aber etwas unterschiedlich implementiert werden, für Benutzer in Exchange 2013 verwaltet. Im nächsten Abschnitt werden die Unterschiede beschrieben. 
  
Auf der Seite **Archivierungskonfiguration** werden die einzelnen Archivierungsrichtlinien aufgeführt, die für die Bereitstellung konfiguriert sind. Außerdem werden der Richtlinienname und -bereich (Global, Standort oder Pool) sowie die für eine Archivierungskonfiguration aktivierten Archivierungsoptionen angezeigt. Auf der Seite **Archivierungskonfiguration** haben Sie die folgenden Möglichkeiten:
- **Neue** Sie können eine oder mehrere der folgenden optionalen Archivierungskonfigurationen hinzufügen.
    
  - Standortkonfiguration
    
  - Poolkonfiguration
    
- **Bearbeiten** Sie können keines der Archivierungskonfiguration erst auf der Seite aufgeführten Optionen ändern. Mit dieser Option haben Sie folgende Möglichkeiten:
    
  - **Details anzeigen** Diese Option öffnet ein Dialogfeld, in dem Sie die Archivierungsoptionen für den ausgewählten Archivierungskonfiguration ändern können. Sie können nur für jeweils eine Archivierungskonfiguration Details anzeigen.
    
  - **Wählen Sie alle** Diese Option werden alle Archivierungskonfigurationen der Liste ausgewählt.
    
  - **Löschen** Diese Option werden alle ausgewählte Archivierungskonfigurationen gelöscht.
    
- **Aktion** Verwenden Sie diese Option, um schnell aktivieren oder Deaktivieren der Archivierung von Sofortnachrichtensitzungen oder webkonferenzsitzungen in einer Konfiguration auf der Seite, anstatt zur Bearbeitung der Konfigurations aufgeführt. Die unter **Aktion** verfügbaren Optionen richten sich danach, welche Option in der Archivierungskonfiguration momentan angegeben ist. Alle Optionen sind verfügbar, mit Ausnahme der Option, die für die Archivierungskonfiguration derzeit wirksam ist. Folgende Optionen sind vorhanden:
    
  - **Chatsitzungen archivieren**
    
  - **Chat- und Webkonferenzsitzungen archivieren**
    
  - **Archivierung deaktivieren**
    
- **Aktualisieren** Sie können den Status der Optionen aller Archivierungskonfigurationen zu überprüfen, um die Seite **Archivierungskonfiguration** aktualisieren.
    
Weitere Informationen über die Archivierungsfunktion und Funktionen, einschließlich Exchange-Integration finden Sie unter [Planen für die Archivierung in Skype für Business Server 2015](../../plan-your-deployment/archiving/archiving.md), [Archivierung für Skype für Business Server 2015 bereitstellen](../../deploy/deploy-archiving/deploy-archiving.md)und verwalten [Archivierung in Skype für Business Server 2015](../../manage/archiving/archiving.md).

