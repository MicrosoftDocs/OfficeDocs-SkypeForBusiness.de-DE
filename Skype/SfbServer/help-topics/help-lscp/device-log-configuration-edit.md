---
title: Bearbeiten der Geräteprotokollkonfiguration
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.lscp.ClientDeviceUpdateEdit
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e534e6a5-fb3e-40b1-a189-fce64c42f512
description: Sie können der Seite "Protokolleinstellung bearbeiten" eine Geräteprotokollkonfiguration hinzufügen, die die maximale Größe des Protokollcaches, die maximale Protokolldateigröße oder den Zeitraum bestimmt, für den eine Protokolldatei aufbewahrt wird, bevor sie gelöscht wird. Sie können diese Einstellungen entsprechend den Anforderungen Ihrer Organisation ändern.
ms.openlocfilehash: 694729b74209715bd87bed0c3bd59d80f31fff59
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2021
ms.locfileid: "49807315"
---
# <a name="device-log-configuration-edit"></a>Geräteprotokollkonfiguration: Bearbeiten
 
Sie können der Seite "Protokolleinstellung bearbeiten" eine Geräteprotokollkonfiguration hinzufügen, die die maximale Größe des Protokollcaches, die maximale Protokolldateigröße oder den Zeitraum bestimmt, für den eine Protokolldatei aufbewahrt wird, bevor sie gelöscht wird.  Sie können diese Einstellungen entsprechend den Anforderungen Ihrer Organisation ändern.
  
> [!CAUTION]
> Durch das dauerhafte Löschen von Dateien werden diese aus dem Dateisystem entfernt. Nach dem Löschen einer Datei kann diese nicht mehr wiederhergestellt werden. 
  
## <a name="tasks-you-can-perform"></a>Mögliche Aufgaben

Auf der Seite "Protokolleinstellung bearbeiten" können Sie **die folgenden Aufgaben** ausführen:
  
- Fügen Sie eine Geräteprotokollkonfiguration global oder für einen bestimmten Standort hinzu.
    
- Ändern Sie die Optionen für eine vorhandene Geräteprotokollkonfiguration.
    
## <a name="ui-reference"></a>Referenz zur Benutzeroberfläche

In den folgenden Listen werden die Menüs, Befehle, Felder und Eigenschaften der Seite beschrieben.
  
- **Bereich** Gibt den Bereich (Global oder Standort) der Geräteprotokollkonfiguration an.
    
- **Name** Sie können den Namen der Geräteprotokollkonfiguration hinzufügen oder ändern.
    
- **Maximale Dateigröße (Bytes)** Sie können die maximale Größe einer Protokolldatei angeben, bevor sie gelöscht wird. Der Standardwert beträgt 1.024.000 (1 MB).
    
- **Maximale Cachegröße (Bytes)** Sie können die maximale Informationsmenge (in Byte) angeben, die im Protokolldateicache gespeichert werden kann, bevor der Cache gelöscht und die Daten in eine Protokolldatei geschrieben werden müssen. Der Standardwert beträgt 512.000 (0,5 MB).
    
- **Minuten bis zum Leeren des Caches (1-60)** Sie können angeben, wie oft im Protokolldateicache gespeicherte Informationen in die eigentliche Protokolldatei geschrieben werden. Nachdem die Daten protokolliert wurden, wird der Cache geleert. Der Standardwert beträgt fünf Minuten.
    
- **Tage zum Speichern von Protokolldateien (1-365)** Sie können angeben, wie viele Tage die Protokolldateien aufbewahrt werden, bevor sie gelöscht werden. Der Standardwert beträgt 10 Tage.
    
## <a name="see-also"></a>Weitere Informationen

[Geräteprotokollkonfiguration](device-log-configuration.md)
