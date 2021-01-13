---
title: Geräteaktualisierung
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
- ms.lync.lscp.ClientDeviceUpdateMain
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 6f6b7f73-f8f5-41dc-9e2a-727baaaa828b
description: Microsoft veröffentlicht regelmäßig eine neue Reihe von Gerätefirmwareupdates für Skype for Business Phone Edition, die Sie auf Ihre Server importieren und an Benutzer verteilen können. Sie erhalten den neuesten Satz von Geräteaktualisierungsregeln, indem Sie auf der Seite "Hilfe und Support" auf der Website von Microsoft nach "Phone Edition" suchen. Laden Sie das neueste Updatepaket herunter, und extrahieren Sie die Dateien in einen Ordner auf dem Computer, in den die Updates hochgeladen werden sollen. Nachdem die Dateien extrahiert wurden, können Sie das cmdlet Import-CsDeviceUpdate verwenden, um die Geräteaktualisierungsregeln in der extrahierten zu importieren. CAB-Datei (die den Namen UCUpdates.cab). Weitere Informationen finden Sie unter Import-CsDeviceUpdate.
ms.openlocfilehash: 375069d5812d5aa13ebd63dd02eaa3cdd6151cc3
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2021
ms.locfileid: "49811055"
---
# <a name="device-update"></a>Geräteaktualisierung

Microsoft veröffentlicht regelmäßig eine neue Reihe von Gerätefirmwareupdates für Skype for Business Phone Edition, die Sie auf Ihre Server importieren und an Benutzer verteilen können. Sie erhalten den neuesten Satz von Geräteaktualisierungsregeln, indem Sie auf der Seite "Hilfe und Support" auf der Website von Microsoft nach "Phone Edition" suchen. Laden Sie das neueste Updatepaket herunter, und extrahieren Sie die Dateien in einen Ordner auf dem Computer, in den die Updates hochgeladen werden sollen. Nachdem die Dateien extrahiert wurden, können Sie das **Cmdlet "Import-CsDeviceUpdate"** verwenden, um die in der extrahierten Datei gefundenen Geräteaktualisierungsregeln zu importieren. CAB-Datei (die den Namen UCUpdates.cab). Weitere Informationen finden Sie unter [Import-CsDeviceUpdate](https://docs.microsoft.com/powershell/module/skype/import-csdeviceupdate?view=skype-ps).

Nachdem die Geräteaktualisierungsregeln importiert wurden,  können Sie diese Regeln auf der Seite "Geräteaktualisierung" für die Geräte Ihrer Organisation anzeigen und verwalten.

> [!TIP]
> Sie können die Firmwareupdates testen und sie dann, sofern die Tests erfolgreich waren, allen relevanten Geräten in der Organisation zur Verfügung stellen.

## <a name="tasks-you-can-perform"></a>Mögliche Aufgaben

Auf der Seite **Geräteupdate** können Sie die folgenden Aufgaben ausführen:

- Genehmigen von Geräteupdates der Liste

- Abbrechen oder Wiederherstellen ausstehender Geräteupdates

- Löschen von Geräteupdates aus der Liste

## <a name="ui-reference"></a>Referenz zur Benutzeroberfläche

In den folgenden Listen werden die Menüs, Befehle, Felder und Eigenschaften der Seite beschrieben.

- **Bearbeiten** Sie können diese Option verwenden, um folgendes zu tun:

  - **Alles auswählen** Mit dieser Option werden alle Geräteupdates in der Liste ausgewählt.

  - **Löschen** Mit dieser Option werden alle ausgewählten Geräteupdates gelöscht.

- **Aktion** Sie können ein oder mehrere Updates in der Liste auswählen und die folgenden Aktionen ausführen:

  - **Abbrechen ausstehender Updates** Mit dieser Option wird verhindert, dass das ausgewählte Update auf den Geräten Ihrer Organisation bereitgestellt wird.

  - **Genehmigen** Mit dieser Option kann das ausgewählte Update auf den Geräten Ihrer Organisation bereitgestellt werden.

  - **Wiederherstellen** Mit dieser Option kann ein zuvor genehmigtes Update auf den Geräten Ihrer Organisation bereitgestellt werden.

- **Aktualisieren** Sie können die Liste aktualisieren, um den Status aller Geräteupdates zu überprüfen.

Ausführliche Informationen zum Geräteaktualisierungs-Webdienst finden Sie unter [View Software Updates for Devices in Your Organization](https://technet.microsoft.com/library/d2cca12b-ed43-4e1f-90ab-d14bca8b482c.aspx) in der Planungsdokumentation.
## <a name="see-also"></a>Siehe auch

[Import-CsDeviceUpdate](https://docs.microsoft.com/powershell/module/skype/import-csdeviceupdate?view=skype-ps)
