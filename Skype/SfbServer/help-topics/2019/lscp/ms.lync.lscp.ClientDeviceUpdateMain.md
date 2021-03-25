---
title: Geräteaktualisierung
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
- ms.lync.lscp.ClientDeviceUpdateMain
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
localization_priority: Normal
ms.assetid: 6f6b7f73-f8f5-41dc-9e2a-727baaaa828b
ROBOTS: NOINDEX, NOFOLLOW
description: Microsoft veröffentlicht regelmäßig neue Gerätefirmwareupdates für Skype for Business Phone Edition, die Sie auf Ihre Server importieren und an Benutzer verteilen können. Sie können die neuesten Geräteupdateregeln abrufen, indem Sie zur Seite Hilfe und Support auf der Microsoft-Website gehen und nachPhone Edition suchen.Laden Sie das neueste Updatepaket herunter, und extrahieren Sie die Dateien in einen Ordner auf dem Computer, in den die Updates hochgeladen werden sollen. Nachdem die Dateien extrahiert wurden, können Sie das cmdlet Import-CsDeviceUpdate verwenden, um die Geräteaktualisierungsregeln zu importieren, die sich in der extrahierten befinden. CAB-Datei (die den Namen UCUpdates.cab). Weitere Informationen finden Sie unter Import-CsDeviceUpdate.
ms.openlocfilehash: f62ece38e33bfdc02a6110bb7cc4e53210c9b500
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51120254"
---
# <a name="device-update"></a>Geräteaktualisierung

Microsoft veröffentlicht regelmäßig neue Gerätefirmwareupdates für Skype for Business Phone Edition, die Sie auf Ihre Server importieren und an Benutzer verteilen können. Sie können die neuesten Geräteupdateregeln abrufen, indem Sie auf der Microsoft-Website zur Hilfe- und Supportseite gehen und nach "Phone Edition" suchen. Laden Sie das neueste Updatepaket herunter, und extrahieren Sie die Dateien in einen Ordner auf dem Computer, in den die Updates hochgeladen werden sollen. Nachdem die Dateien extrahiert wurden, können Sie das **Cmdlet Import-CsDeviceUpdate** verwenden, um die Geräteaktualisierungsregeln zu importieren, die in der extrahierten gefunden wurden. CAB-Datei (die den Namen UCUpdates.cab). Weitere Informationen finden Sie unter [Import-CsDeviceUpdate](/powershell/module/skype/import-csdeviceupdate?view=skype-ps).

Nachdem die Geräteaktualisierungsregeln importiert wurden,  können Sie die Seite Geräteupdate verwenden, um diese Regeln für die Geräte Ihrer Organisation ein- und zu verwalten.

> [!TIP]
> Sie können die Firmwareupdates testen und sie dann, sofern die Tests erfolgreich waren, allen relevanten Geräten in der Organisation zur Verfügung stellen.

## <a name="tasks-you-can-perform"></a>Mögliche Aufgaben

Auf der Seite **Geräteupdate** können Sie die folgenden Aufgaben ausführen:

- Genehmigen von Geräteupdates der Liste

- Abbrechen oder Wiederherstellen ausstehender Geräteupdates

- Löschen von Geräteupdates aus der Liste

## <a name="ui-reference"></a>Referenz zur Benutzeroberfläche

In den folgenden Listen werden die Menüs, Befehle, Felder und Eigenschaften der Seite beschrieben.

- **Bearbeiten** Sie können diese Option verwenden, um die folgenden Schritte zu tun:

  - **Wählen Sie Alle aus.** Mit dieser Option werden alle Geräteupdates in der Liste ausgewählt.

  - **Löschen** Mit dieser Option werden alle ausgewählten Geräteupdates gelöscht.

- **Aktion** Sie können ein oder mehrere Updates in der Liste auswählen und die folgenden Aktionen ausführen:

  - **Abbrechen ausstehender Updates** Mit dieser Option wird verhindert, dass das ausgewählte Update auf den Geräten Ihrer Organisation bereitgestellt wird.

  - **Genehmigen** Mit dieser Option kann das ausgewählte Update auf den Geräten Ihrer Organisation bereitgestellt werden.

  - **Wiederherstellen** Mit dieser Option kann ein zuvor genehmigtes Update auf den Geräten Ihrer Organisation bereitgestellt werden.

- **Aktualisieren** Sie können die Liste aktualisieren, um den Status aller Geräteupdates zu überprüfen.

Ausführliche Informationen zum Geräteaktualisierungs-Webdienst finden Sie unter [View Software Updates for Devices in Your Organization](/previous-versions/office/lync-server-2013/lync-server-2013-view-software-updates-for-devices-in-your-organization) in der Planungsdokumentation.
## <a name="see-also"></a>Siehe auch

[Import-CsDeviceUpdate](/powershell/module/skype/import-csdeviceupdate?view=skype-ps)