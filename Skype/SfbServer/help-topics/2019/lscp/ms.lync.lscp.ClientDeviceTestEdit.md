---
title: Erstellen eines neuen oder Bearbeiten eines vorhandenen Testgeräts
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
description: Die Funktion "Testgerät" wird zusammen mit der Funktion "Geräteaktualisierung" verwendet. Sie können der Seite Testgerät ein Gerät hinzufügen und mit diesem Gerät anschließend die Funktionalität neuer Updates überprüfen, bevor die Updates auf Produktionsgeräten bereitgestellt werden. Sie können ein Gerät global (in der gesamten Umgebung) oder innerhalb eines einzelnen Standorts testen. Sie identifizieren ein Testgerät über seine MAC-Adresse (Media Access Control) oder Seriennummer. Wenn Sie ein Gerät hinzufügen, wird es in der Liste auf der Seite "Testgerät" der Skype for Business Server-Systemsteuerung angezeigt.
ms.openlocfilehash: e1a8c570714b1096d14ac49260922c1a6dc3fecc
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2021
ms.locfileid: "49830325"
---
# <a name="test-device-create-new-or-edit-existing"></a>Testgerät: Erstellen eines neuen oder Bearbeiten eines vorhandenen Testgeräts

Die Funktion "Testgerät" wird zusammen mit der Funktion "Geräteaktualisierung" verwendet. Sie können der Seite **Testgerät** ein Gerät hinzufügen und mit diesem Gerät anschließend die Funktionalität neuer Updates überprüfen, bevor die Updates auf Produktionsgeräten bereitgestellt werden. Sie können ein Gerät global (in der gesamten Umgebung) oder innerhalb eines einzelnen Standorts testen. Sie identifizieren ein Testgerät über seine MAC-Adresse (Media Access Control) oder Seriennummer. Wenn Sie ein Gerät hinzufügen, wird es in der Liste auf der Seite **"Testgerät"** der Skype for Business Server-Systemsteuerung angezeigt.

## <a name="tasks-you-can-perform"></a>Mögliche Aufgaben

Auf der Seite **Neues Testgerät** bzw. **Testgerät bearbeiten** können Sie die folgenden Aufgaben ausführen:

- Hinzufügen eines neuen Testgeräts

- Ändern der Eigenschaften eines vorhandenen Testgeräts

## <a name="ui-reference"></a>Referenz zur Benutzeroberfläche

In den folgenden Listen werden die Menüs, Befehle, Felder und Eigenschaften der Seite beschrieben.

- **Bereich** Gibt den Bereich (Global oder Standort) des Testgeräts an.

- **Name** Sie können den Namen des Testgeräts hinzufügen oder ändern.

- **Gerätename** Sie können den Namen des Testgeräts hinzufügen oder ändern.

- **Bezeichnertyp** Sie können die Methode zum Identifizieren des Geräts auswählen, indem Sie eine der folgenden Optionen auswählen:

  - **MAC-Adresse**

  - **Seriennummer**

- **Eindeutiger Bezeichner** Sie können die MAC-Adresse oder Seriennummer des Geräts eingeben.

Ausführliche Informationen zu Testgeräten finden Sie unter [Add a Device to Test Update Functionality](https://technet.microsoft.com/library/ce509fd1-17b3-4b78-b269-fe5d06fe2e1d.aspx) in der Betriebsdokumentation.
## <a name="see-also"></a>Siehe auch

[Testgerät](ms.lync.lscp.ClientDeviceTestMain.md)

[New-CsTestDevice](https://docs.microsoft.com/powershell/module/skype/new-cstestdevice?view=skype-ps)

[Set-CsTestDevice](https://docs.microsoft.com/powershell/module/skype/set-cstestdevice?view=skype-ps)

[Anzeigen von Softwareupdates für Geräte in Ihrer Organisation](https://technet.microsoft.com/library/d2cca12b-ed43-4e1f-90ab-d14bca8b482c.aspx)
