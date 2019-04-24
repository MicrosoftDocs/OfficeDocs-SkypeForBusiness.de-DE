---
title: Geräteaktualisierung
ms.reviewer: ''
ms.author: SerdarS
author: SerdarSoysal
manager: serdars
ms.date: 3/23/2015
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.ClientDeviceUpdateMain
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 6f6b7f73-f8f5-41dc-9e2a-727baaaa828b
description: Microsoft stellt in regelmäßigen Abständen einen neuen Satz von Geräteupdates Firmware für Skype für Business Phone Edition, die Sie importieren auf den Servern und an Benutzer verteilen können. Sie können erhalten der aktuellen Gruppe von geräteaktualisierungsregeln durch Aufrufen der Hilfe und Support-Seite auf der Microsoft-Website und Suche ForPhone Edition.Download das neueste Updatepaket und extrahieren Sie die Dateien in einen Ordner auf dem Computer, auf dem die Updates sind hochgeladen werden. Nachdem Sie die Dateien extrahiert haben, können Sie das Cmdlet Import-CsDeviceUpdate verwenden, um die Geräteaktualisierungsregeln aus der extrahierten CAB-Datei (die „UCUpdates.cab“ oder ähnlich heißt) zu importieren. Weitere Informationen hierzu finden Sie unter Import-CsDeviceUpdate.
ms.openlocfilehash: 271803e5a04f09ceda1fb98aced4501d3a08183e
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "32234650"
---
# <a name="device-update"></a>Geräteupdate

Microsoft stellt in regelmäßigen Abständen einen neuen Satz von Geräteupdates Firmware für Skype für Business Phone Edition, die Sie importieren auf den Servern und an Benutzer verteilen können. Sie erhalten den neuesten Satz von Geräteaktualisierungsregeln, indem Sie auf der Microsoft-Website die Seite „Hilfe und Support“ aufrufen und nach „Phone Edition“ suchen. Laden Sie das aktuelle Updatepaket herunter und extrahieren Sie die Dateien in einen Ordner auf dem Computer, auf den die Updates geladen werden sollen. Nachdem Sie die Dateien extrahiert haben, können Sie das Cmdlet **Import-CsDeviceUpdate** verwenden, um die Geräteaktualisierungsregeln aus der extrahierten CAB-Datei (die „UCUpdates.cab“ oder ähnlich heißt) zu importieren. Weitere Informationen hierzu finden Sie unter [Import-CsDeviceUpdate](https://docs.microsoft.com/powershell/module/skype/import-csdeviceupdate?view=skype-ps).

Nach dem Import der geräteaktualisierungsregeln können Sie die Seite **Geräteupdate** verwenden, anzeigen und verwalten diese Regeln für die Geräte Ihrer Organisation.

> [!TIP]
> Sie können die Firmwareupdates testen und dann, sofern die Tests erfolgreich waren, allen relevanten Geräten in der Organisation zur Verfügung stellen.

## <a name="tasks-you-can-perform"></a>Mögliche Aufgaben

Auf der Seite **Geräteupdate** können Sie die folgenden Aufgaben ausführen:

- Genehmigen von Geräteupdates der Liste

- Abbrechen oder Wiederherstellen ausstehender Geräteupdates

- Löschen von Geräteupdates aus der Liste

## <a name="ui-reference"></a>Referenz zur Benutzeroberfläche

In den folgenden Listen werden die Menüs, Befehle, Felder und Eigenschaften der Seite beschrieben.

- **Bearbeiten** Diese Option können Sie folgende Aktionen ausführen:

  - **Wählen Sie alle** Diese Option werden alle Geräteupdates der Liste ausgewählt.

  - **Löschen** Diese Option werden alle ausgewählten Geräteupdates gelöscht.

- **Aktion** Sie können ein oder mehrere Updates in der Liste wählen und führen die folgenden Aktionen aus:

  - **Ausstehende Updates Abbrechen** Diese Option wird verhindert, dass das ausgewählte Update Geräte der Organisation bereitgestellt wird.

  - **Genehmigen** Mit dieser Option können das ausgewählte Update für die Geräte Ihrer Organisation bereitgestellt werden.

  - **Stellen Sie wieder her** Mit dieser Option können ein bereits genehmigtes Update auf Geräten in Ihrer Organisation bereitgestellt werden

- **Aktualisieren** Aktualisieren Sie die Liste, um den Status aller Geräteupdates zu überprüfen.

Ausführliche Informationen zum Geräteaktualisierungs-Webdienst finden Sie in der Planungsdokumentation unter [View Software Updates for Devices in Your Organization](https://technet.microsoft.com/library/d2cca12b-ed43-4e1f-90ab-d14bca8b482c.aspx) .
## <a name="see-also"></a>Siehe auch

[Import-CsDeviceUpdate](https://docs.microsoft.com/powershell/module/skype/import-csdeviceupdate?view=skype-ps)
