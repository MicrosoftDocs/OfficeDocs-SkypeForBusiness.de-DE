---
title: Geräteprotokollkonfiguration
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
- ms.lync.lscp.ClientDeviceCfgMain
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
localization_priority: Normal
ms.assetid: c9b81f20-ce8c-40f1-8bed-50775cc35e58
ROBOTS: NOINDEX, NOFOLLOW
description: Der Geräteaktualisierungswebdienst erstellt automatisch Protokolldateien, die Geräteaktualisierungsaktivitäten aufzeichnen. Im Rahmen der Datenverwaltungsstrategie Ihrer Organisation sollten Sie Schwellenwerte für die Größe des Protokolldatencaches, die Größe der Protokolldatei oder die Dauer festlegen, die eine Protokolldatei vor dem Löschen aufbewahrt wird. Sie können diese Einstellungen entsprechend den Anforderungen Ihrer Organisation ändern. Wenn Sie nicht möchten, dass der Geräteaktualisierungswebdienst Protokolldateien automatisch löscht, können Sie sie bei Bedarf manuell löschen. Protokolleinstellungen können global oder auf Standortebene geändert werden.
ms.openlocfilehash: 8ef84325709a6648bec8eb9ff14c8433510f1bf6cabafb8b39dfb86a6f54d238
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2021
ms.locfileid: "54330439"
---
# <a name="device-log-configuration"></a>Geräteprotokollkonfiguration

Der Geräteaktualisierungswebdienst erstellt automatisch Protokolldateien, die Geräteaktualisierungsaktivitäten aufzeichnen. Im Rahmen der Datenverwaltungsstrategie Ihrer Organisation sollten Sie Schwellenwerte für die Größe des Protokolldatencaches, die Größe der Protokolldatei oder die Dauer festlegen, die eine Protokolldatei vor dem Löschen aufbewahrt wird. Sie können diese Einstellungen entsprechend den Anforderungen Ihrer Organisation ändern. Wenn Sie nicht möchten, dass der Geräteaktualisierungswebdienst Protokolldateien automatisch löscht, können Sie sie bei Bedarf manuell löschen. Protokolleinstellungen können global oder auf Standortebene geändert werden.

> [!NOTE]
> Sie können auch eine Uhrzeit konfigurieren, zu der der Geräteaktualisierungswebdienst Protokolldateien automatisch löschen soll, die älter als die Anzahl der Tage sind, die Sie für den Dienst konfiguriert haben, um Protokolldateien beizubehalten (standardmäßig also Protokolldateien, die älter als 10 Tage sind). Diese Einstellung kann nicht mit Skype for Business Server Systemsteuerung geändert werden. Stattdessen müssen Sie Skype for Business Server Verwaltungsshell verwenden. Verwenden Sie das Cmdlet **"New-CsDeviceUpdateConfiguration"** mit dem Parameter "-LogCleanUpTimeOfDay", um die Uhrzeit anzugeben, zu der abgelaufene Protokolldateien gelöscht werden sollen. Ausführliche Informationen finden Sie unter ["New-CsDeviceUpdateConfiguration".](/powershell/module/skype/new-csdeviceupdateconfiguration?view=skype-ps)

> [!CAUTION]
> Durch das dauerhafte Löschen von Dateien werden diese aus dem Dateisystem entfernt. Nach dem Löschen einer Datei kann diese nicht mehr wiederhergestellt werden.

## <a name="tasks-you-can-perform"></a>Mögliche Aufgaben

Auf der Seite **"Geräteprotokollkonfiguration"** können Sie die folgenden Aufgaben ausführen:

- Fügen Sie eine Geräteprotokollkonfiguration global oder für einen bestimmten Standort oder Pool hinzu.

- Ändern sie die Optionen für eine vorhandene Geräteprotokollkonfiguration.

## <a name="ui-reference"></a>Referenz zur Benutzeroberfläche

In den folgenden Listen werden die Menüs, Befehle, Felder und Eigenschaften der Seite beschrieben.

- **Neu** Sie können eine neue Geräteprotokollkonfiguration mit folgendem Bereich hinzufügen:

  - Global

  - Website

- **Bearbeiten** Sie können die Optionen einer Geräteprotokollkonfiguration in der Liste ändern. Mit dieser Option haben Sie folgende Möglichkeiten:

  - **Details anzeigen** Mit dieser Option wird ein Dialogfeld geöffnet, in dem Sie die Optionen für eine Geräteprotokollkonfiguration ändern können.

  - **Alle auswählen** Diese Option wählt alle Geräteprotokollkonfigurationen in der Liste aus.

  - **Löschen** Mit dieser Option werden alle ausgewählten Geräteprotokollkonfigurationen gelöscht.

- **Aktualisieren** Sie können die Geräteprotokollkonfigurationsliste aktualisieren, um den Status der Optionen für alle Geräteprotokollkonfigurationen zu überprüfen.

## <a name="see-also"></a>Siehe auch

[Ändern von Protokolldateieinstellungen für die Geräteaktualisierung](/previous-versions/office/lync-server-2013/lync-server-2013-modify-settings-for-device-update-log-files)