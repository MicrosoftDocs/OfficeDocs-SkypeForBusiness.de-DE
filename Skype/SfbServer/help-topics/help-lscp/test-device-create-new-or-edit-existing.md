---
title: Test Gerät neues erstellen oder vorhandenes bearbeiten
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
- ms.lync.lscp.ClientDeviceTestEdit
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 8f9125dd-04b3-4a6d-9f41-4f19ddaf7a2d
description: Die Funktion „Testgerät“ wird zusammen mit der Funktion „Geräteaktualisierung“ verwendet. Sie können der Seite Testgerät ein Gerät hinzufügen und mit diesem Gerät anschließend die Funktionalität neuer Updates überprüfen, bevor die Updates auf Produktionsgeräten bereitgestellt werden. Sie können ein Gerät global (innerhalb Ihrer gesamten Umgebung) oder innerhalb eines einzelnen Standorts testen. Sie identifizieren ein Testgerät über seine MAC-Adresse (Media Access Control) oder Seriennummer. Wenn Sie ein Gerät hinzufügen, wird es in der Liste auf der Seite Testgerät des Skype for Business Server-Control Panels angezeigt.
ms.openlocfilehash: e34a70091e4558db4c2e201f86c9aa81d50f3dda
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2020
ms.locfileid: "41822057"
---
# <a name="test-device-create-new-or-edit-existing"></a>Testgerät: Erstellen eines neuen oder Bearbeiten eines vorhandenen Testgeräts

Die Funktion „Testgerät“ wird zusammen mit der Funktion „Geräteaktualisierung“ verwendet. Sie können der Seite **Testgerät** ein Gerät hinzufügen und mit diesem Gerät anschließend die Funktionalität neuer Updates überprüfen, bevor die Updates auf Produktionsgeräten bereitgestellt werden. Sie können ein Gerät global (innerhalb Ihrer gesamten Umgebung) oder innerhalb eines einzelnen Standorts testen. Sie identifizieren ein Testgerät über seine MAC-Adresse (Media Access Control) oder Seriennummer. Wenn Sie ein Gerät hinzufügen, wird es in der Liste auf der Seite **Testgerät** des Skype for Business Server-Control Panels angezeigt.

## <a name="tasks-you-can-perform"></a>Mögliche Aufgaben

Auf der Seite **Neues Testgerät** bzw. **Testgerät bearbeiten** können Sie die folgenden Aufgaben ausführen:

- Hinzufügen eines neuen Testgeräts

- Ändern der Eigenschaften eines vorhandenen Testgeräts

## <a name="ui-reference"></a>Referenz zur Benutzeroberfläche

In den folgenden Listen werden die Menüs, Befehle, Felder und Eigenschaften der Seite beschrieben.

- **Bereich** Identifiziert den Bereich (Global oder Website) des Testgeräts.

- **Name** Sie können den Namen des Testgeräts hinzufügen oder ändern.

- **Gerätename** Sie können den Namen des Testgeräts hinzufügen oder ändern.

- **Identifier-Typ** Sie können die zum Identifizieren des Geräts zu verwendende Methode auswählen, indem Sie eine der folgenden Optionen auswählen:

  - **MAC-Adresse**

  - **Seriennummer**

- **Eindeutiger Bezeichner** Sie können die Mac-Adresse oder die Seriennummer des Geräts eingeben.

Ausführliche Informationen zu Testgeräten finden Sie unter [Add a Device to Test Update Functionality](https://technet.microsoft.com/library/ce509fd1-17b3-4b78-b269-fe5d06fe2e1d.aspx) in der Betriebsdokumentation.
## <a name="see-also"></a>Siehe auch

[Testgerät](test-device.md)

[Neu – CsTestDevice](https://docs.microsoft.com/powershell/module/skype/new-cstestdevice?view=skype-ps)

[Satz-CsTestDevice](https://docs.microsoft.com/powershell/module/skype/set-cstestdevice?view=skype-ps)

[Anzeigen von Software Updates für Geräte in Ihrer Organisation](https://technet.microsoft.com/library/d2cca12b-ed43-4e1f-90ab-d14bca8b482c.aspx)
