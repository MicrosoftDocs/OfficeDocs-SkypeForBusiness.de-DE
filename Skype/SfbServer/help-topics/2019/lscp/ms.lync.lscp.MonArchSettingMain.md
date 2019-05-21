---
title: Archivierungskonfiguration
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.MonArchSettingMain
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 9c2fd164-a9b8-40e6-a1c4-423a7fe34aba
ROBOTS: NOINDEX, NOFOLLOW
description: 'Sie verwenden Archivierungs Konfigurationen, um Archivierungsoptionen für Ihre Skype for Business Server-Bereitstellung zu steuern, einschließlich der Aktivierung und Deaktivierung der folgenden Optionen:'
ms.openlocfilehash: 8c585d2a5816f2d29b3f468fd48fa82c36254d5f
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2019
ms.locfileid: "34291936"
---
# <a name="archiving-configuration"></a>Archivierungskonfiguration
 
Sie verwenden Archivierungs Konfigurationen, um Archivierungsoptionen für Ihre Skype for Business Server-Bereitstellung zu steuern, einschließlich der Aktivierung und Deaktivierung der folgenden Optionen:
  
- Blockieren von Chat- und Konferenzsitzungen bei Archivierungsfehlern
    
- Integration in Exchange-Speicher für Benutzer, die sich in Exchange befinden
    
- Bereinigen archivierter Daten
    
Zu den Archivierungskonfigurationen gehören die globale Konfiguration und optional eine oder mehrere Archivierungskonfigurationen:
  
- **Globale Konfiguration** Die globale Konfiguration wird standardmäßig in allen Skype for Business Server-Bereitstellungen erstellt. Sie können die globale Konfiguration bearbeiten, aber Sie können diese Archivierungskonfiguration nicht löschen. Wenn Sie versuchen, sie zu löschen, werden alle Optionen auf die Standardwerte zurückgesetzt.
    
- **Websitekonfiguration (optional)** Sie können eine oder mehrere Website Archivierungs Konfigurationen angeben, die jeweils für die Steuerung der Archivierungsoptionen für eine bestimmte Website konfiguriert werden können. Eine Standortkonfiguration setzt die globale Konfiguration außer Kraft, jedoch nur für die in den Archivierungsstandortkonfigurationen angegebenen Standorte. Sie können Standortkonfigurationen bearbeiten oder löschen.
    
- **Pool Konfiguration (optional)** Sie können eine oder mehrere Pool Archivierungskonfiguration angeben, um Archivierungsoptionen für einen bestimmten Pool zu steuern. Eine Poolkonfiguration setzt die globale Konfiguration und die Standortkonfiguration außer Kraft, jedoch nur für die in den Archivierungspoolkonfigurationen angegebenen Pools. Sie können Poolkonfigurationen bearbeiten oder löschen.
    
> [!NOTE]
> Archivierungs Konfigurationen gelten für Benutzer, die sich in Skype for Business Server befinden, und, wenn Sie Exchange zum Speichern von Archivierungsdaten in Microsoft Exchange verwenden, für Benutzer, die sich in Exchange befinden, aber für Benutzer, die in Exchange verwaltet werden, etwas anders implementiert sind. Die Unterschiede werden im nächsten Abschnitt beschrieben. 
  
Auf der Seite **Archivierungskonfiguration** werden die einzelnen Archivierungsrichtlinien aufgeführt, die für die Bereitstellung konfiguriert sind. Außerdem werden der Richtlinienname und -bereich (Global, Standort oder Pool) sowie die für eine Archivierungskonfiguration aktivierten Archivierungsoptionen angezeigt. Auf der Seite **Archivierungskonfiguration** haben Sie die folgenden Möglichkeiten:
- **Neu** Sie können eine oder mehrere der folgenden optionalen Archivierungs Konfigurationen hinzufügen.
    
  - Standortkonfiguration
    
  - Poolkonfiguration
    
- **Bearbeiten** von Sie können die Optionen für alle auf der Seite aufgelisteten Archivierungs Konfigurationen ändern. Mit dieser Option haben Sie folgende Möglichkeiten:
    
  - **Details anzeigen** Mit dieser Option wird ein Dialogfeld geöffnet, in dem Sie die Archivierungsoptionen für die ausgewählte Archivierungskonfiguration ändern können. Sie können nur für jeweils eine Archivierungskonfiguration Details anzeigen.
    
  - **Alle auswählen** Mit dieser Option werden alle Archivierungs Konfigurationen in der Liste ausgewählt.
    
  - **Löschen** Mit dieser Option werden alle ausgewählten Archivierungs Konfigurationen gelöscht.
    
- **Aktion** Sie können diese Option verwenden, um die Archivierung von Chatsitzungen oder Webkonferenz Sitzungen in einer beliebigen auf der Seite aufgeführten Konfiguration schnell zu aktivieren oder zu deaktivieren, anstatt die Konfiguration zu bearbeiten. Die unter **Aktion** verfügbaren Optionen richten sich danach, welche Option in der Archivierungskonfiguration momentan angegeben ist. Alle Optionen sind verfügbar, mit Ausnahme der Option, die für die Archivierungskonfiguration derzeit wirksam ist. Folgende Optionen sind vorhanden:
    
  - **Chatsitzungen archivieren**
    
  - **Chat- und Webkonferenzsitzungen archivieren**
    
  - **Archivierung deaktivieren**
    
- **Aktualisieren** Sie können die Seite **Archivierungskonfiguration** aktualisieren, um den Status der Optionen aller Archivierungs Konfigurationen zu überprüfen.
    
Details zum Archivierungsfeature und zu den Funktionen, einschließlich der Exchange-Integration, finden Sie unter [Planen der Archivierung in Skype](../../../plan-your-deployment/archiving/archiving.md)for Business Server, [Bereitstellen der Archivierung für Skype for Business Server](../../../deploy/deploy-archiving/deploy-archiving.md)und [Verwalten der Archivierung in Skype for Business. Server](../../../manage/archiving/archiving.md)aus.

