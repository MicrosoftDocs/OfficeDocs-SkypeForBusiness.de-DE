---
title: Geräteprotokoll-Konfigurations Bearbeitung
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
- ms.lync.lscp.ClientDeviceUpdateEdit
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
localization_priority: Normal
ms.assetid: e534e6a5-fb3e-40b1-a189-fce64c42f512
ROBOTS: NOINDEX, NOFOLLOW
description: Sie können der Seite Protokolleinstellungen bearbeiten eine geräteprotokoll Konfiguration hinzufügen, die die maximale Größe des Protokollcaches, die maximale Protokolldateigröße oder die Zeitdauer festlegt, die eine Protokolldatei aufbewahrt wird, bevor Sie bereinigt wird. Sie können diese Einstellungen entsprechend den Anforderungen Ihrer Organisation ändern.
ms.openlocfilehash: f2c169038b69fbbb3e68838827a9a77d472c87e4
ms.sourcegitcommit: b1229ed5dc25a04e56aa02aab8ad3d4209559d8f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2020
ms.locfileid: "41794524"
---
# <a name="device-log-configuration-edit"></a>Geräteprotokollkonfiguration: Bearbeiten
 
Sie können der Seite **Protokolleinstellungen bearbeiten** eine geräteprotokoll Konfiguration hinzufügen, die die maximale Größe des Protokollcaches, die maximale Protokolldateigröße oder die Zeitdauer festlegt, die eine Protokolldatei aufbewahrt wird, bevor Sie bereinigt wird. Sie können diese Einstellungen entsprechend den Anforderungen Ihrer Organisation ändern.
  
> [!CAUTION]
> Durch das dauerhafte Löschen von Dateien werden diese aus dem Dateisystem entfernt. Nach dem Löschen einer Datei kann diese nicht mehr wiederhergestellt werden. 
  
## <a name="tasks-you-can-perform"></a>Mögliche Aufgaben

Auf der Seite **Protokolleinstellungen bearbeiten** können Sie die folgenden Aufgaben ausführen:
  
- Fügen Sie eine geräteprotokoll Konfiguration Global oder für eine bestimmte Website hinzu.
    
- Ändern der Optionen für eine vorhandene Geräteprotokollkonfiguration
    
## <a name="ui-reference"></a>Referenz zur Benutzeroberfläche

In den folgenden Listen werden die Menüs, Befehle, Felder und Eigenschaften der Seite beschrieben.
  
- **Bereich** Identifiziert den Bereich (Global oder Website) der geräteprotokoll Konfiguration.
    
- **Name** Sie können den Namen der geräteprotokoll Konfiguration hinzufügen oder ändern.
    
- **Maximale Dateigröße (Bytes)** Sie können die maximale Größe angeben, die eine Protokolldatei erhalten kann, bevor Sie bereinigt wird. Der Standardwert ist 1.024.000 Bytes (1 MB).
    
- **Maximale Cachegröße (Bytes)** Sie können die maximale Menge an Informationen (in Byte) angeben, die im Protokolldatei Cache gespeichert werden können, bevor dieser Cache gelöscht werden muss und die Daten in eine Protokolldatei geschrieben werden. Der Standardwert ist 512.000 Bytes (0,5 MB).
    
- **Minuten zum Leeren des Caches (1-60)** Sie können angeben, wie oft im Protokolldatei Cache gespeicherte Informationen in die eigentliche Protokolldatei geschrieben werden. Nachdem die Daten protokolliert wurden, wird der Cache gelöscht. Der Standardwert ist fünf Minuten.
    
- **Tage, um Protokolldateien zu speichern (1-365)** Sie können angeben, wie viele Tage die Protokolldateien aufbewahrt werden, bevor Sie gelöscht werden. Der Standardwert ist 10 Tage.
    
## <a name="see-also"></a>Siehe auch

[Geräteprotokollkonfiguration](ms.lync.lscp.ClientDeviceCfgMain.md)
