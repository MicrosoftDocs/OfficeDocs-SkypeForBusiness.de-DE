---
title: Geräteprotokollkonfiguration
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/23/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.lscp.ClientDeviceCfgMain
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c9b81f20-ce8c-40f1-8bed-50775cc35e58
description: Der Geräteaktualisierungswebdienst erstellt automatisch Protokolldateien, die Geräteaktualisierungsaktivitäten aufzeichnen. Im Rahmen der Datenverwaltungsstrategie Ihrer Organisation können Sie Schwellenwerte für die Größe des Protokolldatencaches, die Protokolldateigröße oder die Dauer festlegen, die eine Protokolldatei vor dem Löschen aufbewahrt wird. Sie können diese Einstellungen entsprechend den Anforderungen Ihrer Organisation ändern. Wenn sie vom Geräteaktualisierungswebdienst nicht automatisch gelöscht werden sollen, können Sie sie bei Bedarf manuell löschen. Protokolleinstellungen können global oder auf Standortebene geändert werden.
ms.openlocfilehash: 27b4382c84d6aa12a642f191a6167e99ac10565c
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2021
ms.locfileid: "49829485"
---
# <a name="device-log-configuration"></a>Geräteprotokollkonfiguration

Der Geräteaktualisierungswebdienst erstellt automatisch Protokolldateien, die Geräteaktualisierungsaktivitäten aufzeichnen. Im Rahmen der Datenverwaltungsstrategie Ihrer Organisation können Sie Schwellenwerte für die Größe des Protokolldatencaches, die Protokolldateigröße oder die Dauer festlegen, die eine Protokolldatei vor dem Löschen aufbewahrt wird. Sie können diese Einstellungen entsprechend den Anforderungen Ihrer Organisation ändern. Wenn sie vom Geräteaktualisierungswebdienst nicht automatisch gelöscht werden sollen, können Sie sie bei Bedarf manuell löschen. Protokolleinstellungen können global oder auf Standortebene geändert werden.

> [!NOTE]
> Sie können auch eine Uhrzeit konfigurieren, zu der der Geräteaktualisierungswebdienst automatisch Protokolldateien löscht, die älter sind als die Anzahl der Tage, die Sie für den Dienst zum Speichern von Protokolldateien konfiguriert haben (standardmäßig protokolldateien, die älter als 10 Tage sind). Diese Einstellung kann nicht mithilfe der Skype for Business Server-Systemsteuerung geändert werden. Stattdessen müssen Sie die Skype for Business Server-Verwaltungsshell verwenden. Um die Uhrzeit anzugeben, zu der abgelaufene Protokolldateien gelöscht werden, verwenden Sie das **Cmdlet "New-CsDeviceUpdateConfiguration"** mit dem Parameter "-LogCleanUpTimeOfDay". Weitere Informationen finden Sie unter [New-CsDeviceUpdateConfiguration](https://docs.microsoft.com/powershell/module/skype/new-csdeviceupdateconfiguration?view=skype-ps).

> [!CAUTION]
> Durch das dauerhafte Löschen von Dateien werden diese aus dem Dateisystem entfernt. Nach dem Löschen einer Datei kann diese nicht mehr wiederhergestellt werden.

## <a name="tasks-you-can-perform"></a>Mögliche Aufgaben

Auf der Seite "Geräteprotokollkonfiguration" können Sie **die folgenden Aufgaben** ausführen:

- Fügen Sie eine Geräteprotokollkonfiguration global oder für einen bestimmten Standort oder Pool hinzu.

- Ändern Sie die Optionen für eine vorhandene Geräteprotokollkonfiguration.

## <a name="ui-reference"></a>Referenz zur Benutzeroberfläche

In den folgenden Listen werden die Menüs, Befehle, Felder und Eigenschaften der Seite beschrieben.

- **Neu** Sie können eine neue Geräteprotokollkonfiguration mit dem folgenden Bereich hinzufügen:

  - Global

  - Website

- **Bearbeiten** Sie können die Optionen einer Geräteprotokollkonfiguration in der Liste ändern. Mit dieser Option haben Sie folgende Möglichkeiten:

  - **Details anzeigen** Mit dieser Option wird ein Dialogfeld geöffnet, in dem Sie die Optionen für eine Geräteprotokollkonfiguration ändern können.

  - **Alles auswählen** Mit dieser Option werden alle Geräteprotokollkonfigurationen in der Liste ausgewählt.

  - **Löschen** Mit dieser Option werden alle ausgewählten Geräteprotokollkonfigurationen gelöscht.

- **Aktualisieren** Sie können die Geräteprotokollkonfigurationsliste aktualisieren, um den Status der Optionen aller Geräteprotokollkonfigurationen zu überprüfen.

## <a name="see-also"></a>Siehe auch

[Ändern von Protokolldateieinstellungen für die Geräteaktualisierung](https://technet.microsoft.com/library/9b57f126-1853-43b3-bbd4-06401e6498bd.aspx)
