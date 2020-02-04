---
title: Geräteaktualisierung
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/23/2015
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.lscp.ClientDeviceUpdateMain
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 6f6b7f73-f8f5-41dc-9e2a-727baaaa828b
description: Microsoft veröffentlicht in regelmäßigen Abständen einen neuen Satz von Gerätefirmware-Updates für Skype for Business Phone Edition, die Sie auf Ihre Server importieren und an Benutzer verteilen können. Sie können die neuesten Regeln für Geräte Updates abrufen, indem Sie auf der Microsoft-Website auf der Seite Hilfe und Support auf der Microsoft-Website nach forPhone Edition suchen. Laden Sie das neueste Update-Paket herunter, und extrahieren Sie die Dateien in einen Ordner auf dem Computer, auf dem die Updates hochgeladen werden sollen. Nachdem Sie die Dateien extrahiert haben, können Sie das Cmdlet Import-CsDeviceUpdate verwenden, um die Geräteaktualisierungsregeln aus der extrahierten CAB-Datei (die „UCUpdates.cab“ oder ähnlich heißt) zu importieren. Ausführliche Informationen finden Sie unter Importieren-CsDeviceUpdate.
ms.openlocfilehash: 066564a315fdda57e33ad62f8abfe8e5dbe931e1
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/03/2020
ms.locfileid: "41700240"
---
# <a name="device-update"></a>Geräteupdate

Microsoft veröffentlicht in regelmäßigen Abständen einen neuen Satz von Gerätefirmware-Updates für Skype for Business Phone Edition, die Sie auf Ihre Server importieren und an Benutzer verteilen können. Sie erhalten den neuesten Satz von Geräteaktualisierungsregeln, indem Sie auf der Microsoft-Website die Seite „Hilfe und Support“ aufrufen und nach „Phone Edition“ suchen. Laden Sie das aktuelle Updatepaket herunter und extrahieren Sie die Dateien in einen Ordner auf dem Computer, auf den die Updates geladen werden sollen. Nachdem Sie die Dateien extrahiert haben, können Sie das Cmdlet **Import-CsDeviceUpdate** verwenden, um die Geräteaktualisierungsregeln aus der extrahierten CAB-Datei (die „UCUpdates.cab“ oder ähnlich heißt) zu importieren. Ausführliche Informationen finden Sie unter [importieren-CsDeviceUpdate](https://docs.microsoft.com/powershell/module/skype/import-csdeviceupdate?view=skype-ps).

Nachdem die geräteaktualisierungsregeln importiert wurden, können Sie auf der Seite **Device Update** diese Regeln für die Geräte Ihrer Organisation anzeigen und verwalten.

> [!TIP]
> Sie können die Firmwareupdates testen und dann, sofern die Tests erfolgreich waren, allen relevanten Geräten in der Organisation zur Verfügung stellen.

## <a name="tasks-you-can-perform"></a>Mögliche Aufgaben

Auf der Seite **Geräteupdate** können Sie die folgenden Aufgaben ausführen:

- Genehmigen von Geräteupdates der Liste

- Abbrechen oder Wiederherstellen ausstehender Geräteupdates

- Löschen von Geräteupdates aus der Liste

## <a name="ui-reference"></a>Referenz zur Benutzeroberfläche

In den folgenden Listen werden die Menüs, Befehle, Felder und Eigenschaften der Seite beschrieben.

- **Bearbeiten** von Sie können diese Option verwenden, um folgende Aktionen auszuführen:

  - **Alle auswählen** Mit dieser Option werden alle Geräte Updates in der Liste ausgewählt.

  - **Löschen** Mit dieser Option werden alle ausgewählten Geräte Updates gelöscht.

- **Aktion** Sie können ein oder mehrere Updates in der Liste auswählen und die folgenden Aktionen ausführen:

  - **Ausstehende Updates Abbrechen** Mit dieser Option wird verhindert, dass das ausgewählte Update auf den Geräten Ihrer Organisation bereitgestellt wird.

  - **Genehmigen** Mit dieser Option kann das ausgewählte Update auf den Geräten Ihrer Organisation bereitgestellt werden.

  - **Wiederherstellen** Mit dieser Option kann ein zuvor genehmigtes Update auf den Geräten Ihrer Organisation bereitgestellt werden.

- **Aktualisieren** Sie können die Liste aktualisieren, um den Status aller Geräte Updates zu überprüfen.

Ausführliche Informationen zum Geräteaktualisierungs-Webdienst finden Sie in der Planungsdokumentation unter [View Software Updates for Devices in Your Organization](https://technet.microsoft.com/library/d2cca12b-ed43-4e1f-90ab-d14bca8b482c.aspx) .
## <a name="see-also"></a>Siehe auch

[Importieren-CsDeviceUpdate](https://docs.microsoft.com/powershell/module/skype/import-csdeviceupdate?view=skype-ps)
