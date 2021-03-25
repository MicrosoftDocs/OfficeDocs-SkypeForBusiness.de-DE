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
description: Der Device Update-Webdienst erstellt automatisch Protokolldateien, die Geräteaktualisierungsaktivitäten aufzeichnen. Im Rahmen der Datenverwaltungsstrategie Ihrer Organisation sollten Sie Schwellenwerte für die Größe des Protokolldatencaches, die Größe der Protokolldatei oder die Dauer festlegen, die eine Protokolldatei vor dem Löschen aufbewahrt wird. Sie können diese Einstellungen entsprechend den Anforderungen Ihrer Organisation ändern. Wenn der Device Update-Webdienst Protokolldateien nicht automatisch löschen soll, können Sie sie bei Bedarf manuell löschen. Protokolleinstellungen können global oder auf Standortebene geändert werden.
ms.openlocfilehash: c9bd2c3077325540e6151fabd7bc4127b909a12a
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51120274"
---
# <a name="device-log-configuration"></a>Geräteprotokollkonfiguration

Der Device Update-Webdienst erstellt automatisch Protokolldateien, die Geräteaktualisierungsaktivitäten aufzeichnen. Im Rahmen der Datenverwaltungsstrategie Ihrer Organisation sollten Sie Schwellenwerte für die Größe des Protokolldatencaches, die Größe der Protokolldatei oder die Dauer festlegen, die eine Protokolldatei vor dem Löschen aufbewahrt wird. Sie können diese Einstellungen entsprechend den Anforderungen Ihrer Organisation ändern. Wenn der Device Update-Webdienst Protokolldateien nicht automatisch löschen soll, können Sie sie bei Bedarf manuell löschen. Protokolleinstellungen können global oder auf Standortebene geändert werden.

> [!NOTE]
> Sie können auch eine Uhrzeit konfigurieren, zu der der Geräteupdatewebdienst protokolldateien automatisch löscht, die älter als die Anzahl der Tage sind, die Sie für das Speichern von Protokolldateien konfiguriert haben (standardmäßig protokolldateien, die älter als 10 Tage sind). Diese Einstellung kann nicht mithilfe der Skype for Business Server-Systemsteuerung geändert werden. Stattdessen müssen Sie die Skype for Business Server-Verwaltungsshell verwenden. Verwenden Sie das **Cmdlet New-CsDeviceUpdateConfiguration** mit dem Parameter -LogCleanUpTimeOfDay, um die Uhrzeit anzugeben, zu der abgelaufene Protokolldateien gelöscht werden. Weitere Informationen finden Sie unter [New-CsDeviceUpdateConfiguration](/powershell/module/skype/new-csdeviceupdateconfiguration?view=skype-ps).

> [!CAUTION]
> Durch das dauerhafte Löschen von Dateien werden diese aus dem Dateisystem entfernt. Nach dem Löschen einer Datei kann diese nicht mehr wiederhergestellt werden.

## <a name="tasks-you-can-perform"></a>Mögliche Aufgaben

Sie können die folgenden Aufgaben auf der Seite **Geräteprotokollkonfiguration** ausführen:

- Fügen Sie eine Geräteprotokollkonfiguration global oder für einen bestimmten Standort oder Pool hinzu.

- Ändern Sie die Optionen für eine vorhandene Geräteprotokollkonfiguration.

## <a name="ui-reference"></a>Referenz zur Benutzeroberfläche

In den folgenden Listen werden die Menüs, Befehle, Felder und Eigenschaften der Seite beschrieben.

- **Neu** Sie können eine neue Geräteprotokollkonfiguration mit dem folgenden Bereich hinzufügen:

  - Global

  - Website

- **Bearbeiten** Sie können die Optionen einer Geräteprotokollkonfiguration in der Liste ändern. Mit dieser Option haben Sie folgende Möglichkeiten:

  - **Details anzeigen** Mit dieser Option wird ein Dialogfeld geöffnet, in dem Sie die Optionen für eine Geräteprotokollkonfiguration ändern können.

  - **Wählen Sie Alle aus.** Diese Option wählt alle Geräteprotokollkonfigurationen in der Liste aus.

  - **Löschen** Mit dieser Option wird alle ausgewählte Geräteprotokollkonfiguration gelöscht.

- **Aktualisieren** Sie können die Konfigurationsliste des Geräteprotokolls aktualisieren, um den Status der Optionen aller Geräteprotokollkonfigurationen zu überprüfen.

## <a name="see-also"></a>Siehe auch

[Ändern von Protokolldateieinstellungen für die Geräteaktualisierung](/previous-versions/office/lync-server-2013/lync-server-2013-modify-settings-for-device-update-log-files)