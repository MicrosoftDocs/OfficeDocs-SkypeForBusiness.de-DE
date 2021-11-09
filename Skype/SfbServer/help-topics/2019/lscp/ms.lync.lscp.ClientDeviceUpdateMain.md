---
title: Geräteaktualisierung
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
- ms.lync.lscp.ClientDeviceUpdateMain
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
ms.localizationpriority: medium
ms.assetid: 6f6b7f73-f8f5-41dc-9e2a-727baaaa828b
ROBOTS: NOINDEX, NOFOLLOW
description: Microsoft veröffentlicht in regelmäßigen Abständen einen neuen Satz von Gerätefirmwareupdates für Skype for Business Telefon Edition, die Sie auf Ihre Server importieren und an Benutzer verteilen können. Sie können die neuesten Geräteupdateregeln abrufen, indem Sie auf der Microsoft-Website zur Hilfe- und Supportseite wechseln und nach DerPhone Edition suchen.Laden Sie das neueste Updatepaket herunter, und extrahieren Sie die Dateien in einen Ordner auf dem Computer, auf den die Updates hochgeladen werden sollen. Nachdem die Dateien extrahiert wurden, können Sie das Cmdlet Import-CsDeviceUpdate verwenden, um die Geräteaktualisierungsregeln zu importieren, die in der extrahierten .CAB Datei enthalten sind (die den Namen UCUpdates.cab hat). Ausführliche Informationen finden Sie unter "Import-CsDeviceUpdate".
ms.openlocfilehash: 19815f81a3a6fe9a3c35b1528b5eefb066003481
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/08/2021
ms.locfileid: "60858602"
---
# <a name="device-update"></a>Geräteaktualisierung

Microsoft veröffentlicht in regelmäßigen Abständen einen neuen Satz von Gerätefirmwareupdates für Skype for Business Telefon Edition, die Sie auf Ihre Server importieren und an Benutzer verteilen können. Sie können die neuesten Geräteupdateregeln abrufen, indem Sie auf der Microsoft-Website auf die Hilfe- und Supportseite wechseln und nach "Telefon Edition" suchen. Laden Sie das neueste Updatepaket herunter, und extrahieren Sie die Dateien in einen Ordner auf dem Computer, auf den die Updates hochgeladen werden sollen. Nachdem die Dateien extrahiert wurden, können Sie das Cmdlet **"Import-CsDeviceUpdate"** verwenden, um die Geräteaktualisierungsregeln in der extrahierten .CAB datei zu importieren (die den Namen UCUpdates.cab hat). Ausführliche Informationen finden Sie unter [Import-CsDeviceUpdate](/powershell/module/skype/import-csdeviceupdate?view=skype-ps).

Nachdem die Geräteaktualisierungsregeln importiert wurden, können Sie diese Regeln auf der Seite **"Geräteupdate"** für die Geräte Ihrer Organisation anzeigen und verwalten.

> [!TIP]
> Sie können die Firmwareupdates testen und sie dann, sofern die Tests erfolgreich waren, allen relevanten Geräten in der Organisation zur Verfügung stellen.

## <a name="tasks-you-can-perform"></a>Mögliche Aufgaben

Auf der Seite **Geräteupdate** können Sie die folgenden Aufgaben ausführen:

- Genehmigen von Geräteupdates der Liste

- Abbrechen oder Wiederherstellen ausstehender Geräteupdates

- Löschen von Geräteupdates aus der Liste

## <a name="ui-reference"></a>Referenz zur Benutzeroberfläche

In den folgenden Listen werden die Menüs, Befehle, Felder und Eigenschaften der Seite beschrieben.

- **Bearbeiten** Sie können diese Option verwenden, um Folgendes zu tun:

  - **Alle auswählen** Mit dieser Option werden alle Geräteupdates in der Liste ausgewählt.

  - **Löschen** Mit dieser Option werden alle ausgewählten Geräteupdates gelöscht.

- **Aktion** Sie können eine oder mehrere Updates in der Liste auswählen und die folgenden Aktionen ausführen:

  - **Abbrechen ausstehender Updates** Diese Option verhindert, dass das ausgewählte Update auf den Geräten Ihrer Organisation bereitgestellt wird.

  - **Genehmigen** Mit dieser Option kann das ausgewählte Update auf den Geräten Ihrer Organisation bereitgestellt werden.

  - **Wiederherstellen** Mit dieser Option kann ein zuvor genehmigtes Update auf den Geräten Ihrer Organisation bereitgestellt werden.

- **Aktualisieren** Sie können die Liste aktualisieren, um den Status aller Geräteupdates zu überprüfen.

Ausführliche Informationen zum Geräteaktualisierungs-Webdienst finden Sie unter [View Software Updates for Devices in Your Organization](/previous-versions/office/lync-server-2013/lync-server-2013-view-software-updates-for-devices-in-your-organization) in der Planungsdokumentation.
## <a name="see-also"></a>Siehe auch

[Import-CsDeviceUpdate](/powershell/module/skype/import-csdeviceupdate?view=skype-ps)