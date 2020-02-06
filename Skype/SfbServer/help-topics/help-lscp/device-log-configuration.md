---
title: Geräteprotokollkonfiguration
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
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
description: Der Geräteaktualisierungs-Webdienst erstellt automatisch Protokolldateien, mit denen die Aktivität bei der Geräteaktualisierung aufgezeichnet wird. Im Rahmen der Datenverwaltungsstrategie Ihrer Organisation empfiehlt es sich, Schwellenwerte für die Größe des Protokolldaten Caches, die Größe der Protokolldatei oder den Zeitraum festzulegen, in dem eine Protokolldatei aufbewahrt wird, bevor Sie bereinigt wird. Sie können diese Einstellungen entsprechend den Anforderungen Ihrer Organisation ändern. Falls Sie nicht möchten, dass der Geräteaktualisierungs-Webdienst die Protokolldateien automatisch löscht, können Sie diese je nach Bedarf manuell löschen. Protokolleinstellungen können global oder auf Standortebene geändert werden.
ms.openlocfilehash: 7621a70ebfb8a2129e468ce38655dcc61bdbf420
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2020
ms.locfileid: "41822898"
---
# <a name="device-log-configuration"></a>Geräteprotokollkonfiguration

Der Geräteaktualisierungs-Webdienst erstellt automatisch Protokolldateien, mit denen die Aktivität bei der Geräteaktualisierung aufgezeichnet wird. Im Rahmen der Datenverwaltungsstrategie Ihrer Organisation empfiehlt es sich, Schwellenwerte für die Größe des Protokolldaten Caches, die Größe der Protokolldatei oder den Zeitraum festzulegen, in dem eine Protokolldatei aufbewahrt wird, bevor Sie bereinigt wird. Sie können diese Einstellungen entsprechend den Anforderungen Ihrer Organisation ändern. Falls Sie nicht möchten, dass der Geräteaktualisierungs-Webdienst die Protokolldateien automatisch löscht, können Sie diese je nach Bedarf manuell löschen. Protokolleinstellungen können global oder auf Standortebene geändert werden.

> [!NOTE]
> Sie können auch eine Uhrzeit konfigurieren, zu der der Geräteaktualisierungs-Webdienst automatisch Protokolldateien löscht, die älter sind als die angegebene Anzahl von Tagen für die Speicherung der Protokolldateien durch den Dienst (in der Standardeinstellung sind dies Protokolldateien, die älter als 10 Tage sind). Diese Einstellung kann mit der Skype for Business Server-Systemsteuerung nicht geändert werden. Stattdessen müssen Sie die Skype for Business Server-Verwaltungsshell verwenden. Wenn Sie die Uhrzeit zum Löschen abgelaufener Protokolldateien angeben möchten, verwenden Sie das Cmdlet **New-CsDeviceUpdateConfiguration** mit dem Parameter-LogCleanUpTimeOfDay. Ausführliche Informationen finden Sie unter [New-CsDeviceUpdateConfiguration](https://docs.microsoft.com/powershell/module/skype/new-csdeviceupdateconfiguration?view=skype-ps).

> [!CAUTION]
> Durch das dauerhafte Löschen von Dateien werden diese aus dem Dateisystem entfernt. Nach dem Löschen einer Datei kann diese nicht mehr wiederhergestellt werden.

## <a name="tasks-you-can-perform"></a>Mögliche Aufgaben

Auf der Seite **Geräteprotokollkonfiguration** können Sie die folgenden Aufgaben ausführen:

- Hinzufügen einer Geräteprotokollkonfiguration auf globaler Ebene oder für einen bestimmten Standort oder Pool

- Ändern der Optionen für eine vorhandene Geräteprotokollkonfiguration

## <a name="ui-reference"></a>Referenz zur Benutzeroberfläche

In den folgenden Listen werden die Menüs, Befehle, Felder und Eigenschaften der Seite beschrieben.

- **Neu** Sie können eine neue geräteprotokoll Konfiguration mit dem folgenden Bereich hinzufügen:

  - Global

  - Standort

- **Bearbeiten** von Sie können die Optionen für eine geräteprotokoll Konfiguration in der Liste ändern. Mit dieser Option haben Sie folgende Möglichkeiten:

  - **Details anzeigen** Mit dieser Option wird ein Dialogfeld geöffnet, in dem Sie die Optionen für eine geräteprotokoll Konfiguration ändern können.

  - **Alle auswählen** Mit dieser Option wird die gesamte geräteprotokoll Konfiguration in der Liste ausgewählt.

  - **Löschen** Mit dieser Option wird alle ausgewählte geräteprotokoll Konfiguration gelöscht.

- **Aktualisieren** Sie können die geräteprotokoll-Konfigurationsliste aktualisieren, um den Status der Optionen für die gesamte geräteprotokoll Konfiguration zu überprüfen.

## <a name="see-also"></a>Siehe auch

[Modify Settings for Log Files of Device Update Activity](https://technet.microsoft.com/library/9b57f126-1853-43b3-bbd4-06401e6498bd.aspx)
