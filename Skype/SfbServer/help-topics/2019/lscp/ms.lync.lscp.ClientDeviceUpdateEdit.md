---
title: Gerät Protokoll Konfiguration bearbeiten
ms.reviewer: ''
ms.author: SerdarS
author: SerdarSoysal
manager: serdars
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.ClientDeviceUpdateEdit
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e534e6a5-fb3e-40b1-a189-fce64c42f512
ROBOTS: NOINDEX, NOFOLLOW
description: Sie können auf der Seite Protokolleinstellungen bearbeiten eine geräteprotokollkonfiguration hinzufügen, die bestimmt, die maximale Cachegröße, die maximale Größe der Protokolldatei oder die Zeitdauer, die eine Protokolldatei gespeichert wird, bevor es gelöscht wird. Sie können diese Einstellungen entsprechend den Anforderungen der Organisation ändern.
ms.openlocfilehash: ac8e30dced9c5383ab88068d27a6a44444312da1
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/27/2019
ms.locfileid: "30890973"
---
# <a name="device-log-configuration-edit"></a>Geräteprotokollkonfiguration: Bearbeiten
 
Sie können auf der Seite **Protokolleinstellungen bearbeiten** eine geräteprotokollkonfiguration hinzufügen, die bestimmt, die maximale Cachegröße, die maximale Größe der Protokolldatei oder die Zeitdauer, die eine Protokolldatei gespeichert wird, bevor es gelöscht wird. Sie können diese Einstellungen entsprechend den Anforderungen der Organisation ändern.
  
> [!CAUTION]
> Durch das dauerhafte Löschen von Dateien werden diese aus dem Dateisystem entfernt. Nach dem Löschen einer Datei kann diese nicht mehr wiederhergestellt werden. 
  
## <a name="tasks-you-can-perform"></a>Mögliche Aufgaben

Klicken Sie auf der Seite **Protokolleinstellungen bearbeiten** können Sie die folgenden Aufgaben ausführen:
  
- Hinzufügen einer geräteprotokollkonfiguration global oder für einen bestimmten Standort.
    
- Ändern der Optionen für eine vorhandene Geräteprotokollkonfiguration
    
## <a name="ui-reference"></a>Referenz zur Benutzeroberfläche

In den folgenden Listen werden die Menüs, Befehle, Felder und Eigenschaften der Seite beschrieben.
  
- **Bereich** Gibt den Bereich (Global oder Standort) der geräteprotokollkonfiguration an.
    
- **Name** Sie können hinzufügen oder ändern den Namen der geräteprotokollkonfiguration an.
    
- **Maximale Dateigröße (Byte)** Sie können die maximale Größe angeben, die eine Protokolldatei werden kann, bevor es gelöscht wird. Der Standardwert ist 1,024,000 Bytes (1 MB).
    
- **Maximale Cachegröße (Bytes)** Sie können die maximale Datenmenge (in Bytes) angeben, die im Dateicache melden Sie sich vor dem aufbewahrt werden können, dass der Cache gelöscht werden muss und die Daten werden in einer Protokolldatei geschrieben. Der Standardwert ist 512,000 Byte (0,5 MB).
    
- **Minuten (1 bis 60) Cache zu leeren.** Sie können angeben, wie oft wird im Protokoll Dateicache gespeicherten Informationen in die aktuelle Protokolldatei geschrieben. Nachdem die Daten angemeldet ist, wird der Cache gelöscht. Der Standardwert beträgt fünf Minuten.
    
- **Tage (1-365)-Protokolldateien aufbewahrt werden sollen** Sie können die Anzahl der Tage angeben, die die Protokolldateien aufbewahrt werden, bevor sie gelöscht werden. Der Standardwert ist 10 Tage.
    
## <a name="see-also"></a>Siehe auch

[Geräteprotokollkonfiguration](ms.lync.lscp.ClientDeviceCfgMain.md)
