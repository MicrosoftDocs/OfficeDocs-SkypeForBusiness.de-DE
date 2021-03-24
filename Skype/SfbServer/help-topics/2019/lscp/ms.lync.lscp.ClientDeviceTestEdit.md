---
title: Testgerät Erstellen neuer oder Bearbeiten vorhandener Geräte
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
- ms.lync.lscp.ClientDeviceTestEdit
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
localization_priority: Normal
ms.assetid: 8f9125dd-04b3-4a6d-9f41-4f19ddaf7a2d
ROBOTS: NOINDEX, NOFOLLOW
description: Die Funktion "Testgerät" wird zusammen mit der Funktion "Geräteaktualisierung" verwendet. Sie können der Seite Testgerät ein Gerät hinzufügen und mit diesem Gerät anschließend die Funktionalität neuer Updates überprüfen, bevor die Updates auf Produktionsgeräten bereitgestellt werden. Sie können ein Gerät global (in der gesamten Umgebung) oder an einem einzelnen Standort testen. Sie identifizieren ein Testgerät über seine MAC-Adresse (Media Access Control) oder Seriennummer. Wenn Sie ein Gerät hinzufügen, wird es in der Liste auf der Seite Testgerät der Skype for Business Server-Systemsteuerung angezeigt.
ms.openlocfilehash: 959abca17e208a397cbdd9ad6a69ba241aad4362
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51100631"
---
# <a name="test-device-create-new-or-edit-existing"></a>Testgerät: Erstellen eines neuen oder Bearbeiten eines vorhandenen Testgeräts

Die Funktion "Testgerät" wird zusammen mit der Funktion "Geräteaktualisierung" verwendet. Sie können der Seite **Testgerät** ein Gerät hinzufügen und mit diesem Gerät anschließend die Funktionalität neuer Updates überprüfen, bevor die Updates auf Produktionsgeräten bereitgestellt werden. Sie können ein Gerät global (in der gesamten Umgebung) oder an einem einzelnen Standort testen. Sie identifizieren ein Testgerät über seine MAC-Adresse (Media Access Control) oder Seriennummer. Wenn Sie ein Gerät hinzufügen, wird es in der Liste auf der Seite **Testgerät** der Skype for Business Server-Systemsteuerung angezeigt.

## <a name="tasks-you-can-perform"></a>Mögliche Aufgaben

Auf der Seite **Neues Testgerät** bzw. **Testgerät bearbeiten** können Sie die folgenden Aufgaben ausführen:

- Hinzufügen eines neuen Testgeräts

- Ändern der Eigenschaften eines vorhandenen Testgeräts

## <a name="ui-reference"></a>Referenz zur Benutzeroberfläche

In den folgenden Listen werden die Menüs, Befehle, Felder und Eigenschaften der Seite beschrieben.

- **Bereich** Identifiziert den Bereich (Global oder Site) des Testgeräts.

- **Name** Sie können den Namen des Testgeräts hinzufügen oder ändern.

- **Gerätename** Sie können den Namen des Testgeräts hinzufügen oder ändern.

- **Bezeichnertyp** Sie können die Methode auswählen, mit der das Gerät identifiziert werden soll, indem Sie eine der folgenden Optionen auswählen:

  - **MAC-Adresse**

  - **Seriennummer**

- **Eindeutiger Bezeichner** Sie können die MAC-Adresse oder Seriennummer des Geräts eingeben.

Ausführliche Informationen zu Testgeräten finden Sie unter [Add a Device to Test Update Functionality](/previous-versions/office/lync-server-2013/lync-server-2013-create-a-device-to-test-update-functionality) in der Betriebsdokumentation.
## <a name="see-also"></a>Siehe auch

[Testgerät](ms.lync.lscp.ClientDeviceTestMain.md)

[New-CsTestDevice](/powershell/module/skype/new-cstestdevice?view=skype-ps)

[Set-CsTestDevice](/powershell/module/skype/set-cstestdevice?view=skype-ps)

[Anzeigen von Softwareupdates für Geräte in Ihrer Organisation](/previous-versions/office/lync-server-2013/lync-server-2013-view-software-updates-for-devices-in-your-organization)