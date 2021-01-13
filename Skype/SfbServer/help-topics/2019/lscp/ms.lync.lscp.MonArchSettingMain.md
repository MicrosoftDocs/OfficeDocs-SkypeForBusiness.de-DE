---
title: Archivierungskonfiguration
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
- ms.lync.lscp.MonArchSettingMain
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
localization_priority: Normal
ms.assetid: 9c2fd164-a9b8-40e6-a1c4-423a7fe34aba
ROBOTS: NOINDEX, NOFOLLOW
description: 'Sie verwenden Archivierungskonfigurationen zum Steuern der Archivierungsoptionen für Ihre Skype for Business Server-Bereitstellung, einschließlich der Aktivierung und Deaktivierung der folgenden Optionen:'
ms.openlocfilehash: 56ab256d79a22ce8b08efc9ad135d4c8309ff5d4
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2021
ms.locfileid: "49833595"
---
# <a name="archiving-configuration"></a>Archivierungskonfiguration
 
Sie verwenden Archivierungskonfigurationen zum Steuern der Archivierungsoptionen für Ihre Skype for Business Server-Bereitstellung, einschließlich der Aktivierung und Deaktivierung der folgenden Optionen:
  
- Blockieren von Chat- und Konferenzsitzungen bei Archivierungsfehlern
    
- Integration in den Exchange-Speicher für Benutzer, die in Exchange gespeichert sind
    
- Bereinigen archivierter Daten
    
Zu den Archivierungskonfigurationen gehören die globale Konfiguration und optional eine oder mehrere Archivierungskonfigurationen:
  
- **Globale Konfiguration** Die globale Konfiguration wird standardmäßig in allen Skype for Business Server-Bereitstellungen erstellt. Sie können die globale Konfiguration bearbeiten, aber Sie können diese Archivierungskonfiguration nicht löschen. Wenn Sie versuchen, das Löschen durchzuführen, werden alle Optionen auf die Standardwerte zurückgesetzt.
    
- **Standortkonfiguration (optional)** Sie können eine oder mehrere Archivierungskonfigurationen für Den Standort angeben, die Sie jeweils zum Steuern der Archivierungsoptionen für einen bestimmten Standort konfigurieren können. Eine Standortkonfiguration setzt die globale Konfiguration außer Kraft, jedoch nur für die in den Archivierungsstandortkonfigurationen angegebenen Standorte. Sie können Standortkonfigurationen bearbeiten oder löschen.
    
- **Poolkonfiguration (optional)** Sie können eine oder mehrere Archivierungskonfigurationen für Pools angeben, um die Archivierungsoptionen für einen bestimmten Pool zu steuern. Eine Poolkonfiguration setzt die globale Konfiguration und Standortkonfiguration außer Kraft, jedoch nur für die in den Archivierungspoolkonfigurationen angegebenen Pools. Sie können Poolkonfigurationen bearbeiten oder löschen.
    
> [!NOTE]
> Archivierungskonfigurationen gelten für Benutzer, die in Skype for Business Server gespeichert sind, und, wenn Sie Exchange zum Speichern von Archivierungsdaten in Microsoft Exchange verwenden, für Benutzer, die in Exchange gespeichert sind, für Benutzer, die in Exchange gespeichert sind, jedoch geringfügig anders implementiert werden. Die Unterschiede werden im nächsten Abschnitt beschrieben. 
  
Auf der Seite **Archivierungskonfiguration** sind die einzelnen Archivierungsrichtlinien aufgeführt, die für die Bereitstellung konfiguriert sind. Außerdem werden der Richtlinienname und -bereich (global, Standort oder Pool) sowie die für eine Archivierungskonfiguration aktivierten Archivierungsoptionen angezeigt. Auf der Seite **Archivierungskonfiguration** haben Sie die folgenden Möglichkeiten:
- **Neu** Sie können eine oder mehrere der folgenden optionalen Archivierungskonfigurationen hinzufügen.
    
  - Standortkonfiguration
    
  - Poolkonfiguration
    
- **Bearbeiten** Sie können die Optionen aller auf der Seite aufgeführten Archivierungskonfigurationen ändern. Mit dieser Option haben Sie folgende Möglichkeiten:
    
  - **Details anzeigen** Mit dieser Option wird ein Dialogfeld geöffnet, in dem Sie die Archivierungsoptionen für die ausgewählte Archivierungskonfiguration ändern können. Sie können nur für jeweils eine Archivierungskonfiguration Details anzeigen.
    
  - **Alle auswählen** Mit dieser Option werden alle Archivierungskonfigurationen in der Liste ausgewählt.
    
  - **Löschen** Mit dieser Option werden alle ausgewählten Archivierungskonfigurationen gelöscht.
    
- **Aktion** Mit dieser Option können Sie die Archivierung von Sitzungs- oder Webkonferenzsitzungen in allen auf der Seite aufgeführten Konfigurationen schnell aktivieren oder deaktivieren, anstatt die Konfiguration zu bearbeiten. Die unter **Aktion** verfügbaren Optionen richten sich danach, welche Option in der Archivierungskonfiguration momentan angegeben ist. Alle Optionen sind verfügbar, mit Ausnahme der Option, die für die Archivierungskonfiguration derzeit wirksam ist. Folgende Optionen sind vorhanden:
    
  - **Chatsitzungen archivieren**
    
  - **Chat- und Webkonferenzsitzungen archivieren**
    
  - **Archivierung deaktivieren**
    
- **Aktualisieren** Sie können die Seite **"Archivierungskonfiguration"** aktualisieren, um den Status der Optionen aller Archivierungskonfigurationen zu überprüfen.
    
Weitere Informationen zu den Archivierungsfunktionen, einschließlich der Exchange-Integration, finden Sie unter "Planen der Archivierung [in Skype for Business Server",](../../../plan-your-deployment/archiving/archiving.md)"Bereitstellen der Archivierung für Skype for Business [Server"](../../../deploy/deploy-archiving/deploy-archiving.md)und "Verwalten der Archivierung [in Skype for Business Server".](../../../manage/archiving/archiving.md)

