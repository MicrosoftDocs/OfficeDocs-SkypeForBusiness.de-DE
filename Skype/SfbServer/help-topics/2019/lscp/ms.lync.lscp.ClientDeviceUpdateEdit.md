---
title: Bearbeiten der Geräteprotokollkonfiguration
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
- ms.lync.lscp.ClientDeviceUpdateEdit
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
ms.localizationpriority: medium
ms.assetid: e534e6a5-fb3e-40b1-a189-fce64c42f512
ROBOTS: NOINDEX, NOFOLLOW
description: Sie können der Seite "Protokolleinstellung bearbeiten" eine Geräteprotokollkonfiguration hinzufügen, die die maximale Größe des Protokollcaches, die maximale Größe der Protokolldatei oder die Dauer der Aufbewahrung einer Protokolldatei bestimmt, bevor sie gelöscht wird. Sie können diese Einstellungen entsprechend den Anforderungen Ihrer Organisation ändern.
ms.openlocfilehash: 93a5d8202d473623741b9c2f0082718bc5f7be82
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/04/2021
ms.locfileid: "60758017"
---
# <a name="device-log-configuration-edit"></a>Geräteprotokollkonfiguration: Bearbeiten
 
Sie können der Seite **"Protokolleinstellung bearbeiten"** eine Geräteprotokollkonfiguration hinzufügen, die die maximale Größe des Protokollcaches, die maximale Größe der Protokolldatei oder die Dauer der Aufbewahrung einer Protokolldatei bestimmt, bevor sie gelöscht wird. Sie können diese Einstellungen entsprechend den Anforderungen Ihrer Organisation ändern.
  
> [!CAUTION]
> Durch das dauerhafte Löschen von Dateien werden diese aus dem Dateisystem entfernt. Nach dem Löschen einer Datei kann diese nicht mehr wiederhergestellt werden. 
  
## <a name="tasks-you-can-perform"></a>Mögliche Aufgaben

Auf der Seite **"Protokolleinstellung bearbeiten"** können Sie die folgenden Aufgaben ausführen:
  
- Fügen Sie eine Geräteprotokollkonfiguration global oder für einen bestimmten Standort hinzu.
    
- Ändern sie die Optionen für eine vorhandene Geräteprotokollkonfiguration.
    
## <a name="ui-reference"></a>Referenz zur Benutzeroberfläche

In den folgenden Listen werden die Menüs, Befehle, Felder und Eigenschaften der Seite beschrieben.
  
- **Bereich** Gibt den Bereich (global oder Standort) der Geräteprotokollkonfiguration an.
    
- **Name** Sie können den Namen der Geräteprotokollkonfiguration hinzufügen oder ändern.
    
- **Maximale Dateigröße (Bytes)** Sie können die maximale Größe einer Protokolldatei angeben, bevor sie gelöscht wird. Der Standardwert beträgt 1.024.000 (1 MB).
    
- **Maximale Cachegröße (Bytes)** Sie können die maximale Menge an Informationen (in Bytes) angeben, die im Protokolldateicache gespeichert werden können, bevor dieser Cache gelöscht werden muss und die Daten in eine Protokolldatei geschrieben werden. Der Standardwert beträgt 512.000 (0,5 MB).
    
- **Minuten zum Leeren des Caches (1-60)** Sie können angeben, wie oft im Protokolldateicache gespeicherte Informationen in die eigentliche Protokolldatei geschrieben werden. Nachdem die Daten protokolliert wurden, wird der Cache geleert. Der Standardwert beträgt fünf Minuten.
    
- **Tage zum Aufbewahren von Protokolldateien (1-365)** Sie können angeben, wie viele Tage die Protokolldateien aufbewahrt werden, bevor sie gelöscht werden. Der Standardwert beträgt 10 Tage.
    
## <a name="see-also"></a>Weitere Informationen

[Geräteprotokollkonfiguration](ms.lync.lscp.ClientDeviceCfgMain.md)
