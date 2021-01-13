---
title: Testgerät
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
- ms.lync.lscp.ClientDeviceTestMain
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
localization_priority: Normal
ms.assetid: a1ea564c-f403-4f61-a36b-5a429708e7ca
ROBOTS: NOINDEX, NOFOLLOW
description: Sie können ein Gerät zur Seite Testgerät hinzufügen und mit diesem Gerät anschließend die Funktionalität neuer Updates überprüfen, bevor die Updates auf Produktionsgeräten bereitgestellt werden. Sie können ein Gerät global (in der gesamten Umgebung) oder innerhalb eines einzelnen Standorts testen. Sie identifizieren ein Testgerät über seine MAC-Adresse (Media Access Control) oder Seriennummer. Wenn Sie ein Gerät hinzufügen, wird es in der Liste auf der Seite "Testgerät" der Skype for Business Server-Systemsteuerung angezeigt.
ms.openlocfilehash: 78365c32f54307eb9b557a8ac2a7287a59acd81f
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2021
ms.locfileid: "49830315"
---
# <a name="test-device"></a>Testgerät

Sie können ein Gerät zur Seite **Testgerät** hinzufügen und mit diesem Gerät anschließend die Funktionalität neuer Updates überprüfen, bevor die Updates auf Produktionsgeräten bereitgestellt werden. Sie können ein Gerät global (in der gesamten Umgebung) oder innerhalb eines einzelnen Standorts testen. Sie identifizieren ein Testgerät über seine MAC-Adresse (Media Access Control) oder Seriennummer. Wenn Sie ein Gerät hinzufügen, wird es in der Liste auf der Seite **"Testgerät"** der Skype for Business Server-Systemsteuerung angezeigt.

## <a name="tasks-you-can-perform"></a>Mögliche Aufgaben

Auf der Seite **Testgerät** können Sie die folgenden Aufgaben ausführen:

- Hinzufügen eines Testgeräts auf globaler Ebene oder für einen bestimmten Standort

- Ändern der Optionen für ein vorhandenes Testgerät

## <a name="ui-reference"></a>Referenz zur Benutzeroberfläche

In den folgenden Listen werden die Menüs, Befehle, Felder und Eigenschaften der Seite beschrieben.

- **Neu** Sie können ein neues Testgerät mit dem folgenden Bereich hinzufügen:

  - Global

  - Website

- **Bearbeiten** Sie können die Optionen eines Testgeräts in der Liste ändern. Mit dieser Option haben Sie folgende Möglichkeiten:

  - **Details anzeigen** Mit dieser Option wird ein Dialogfeld geöffnet, in dem Sie die Optionen für ein Testgerät ändern können.

  - **Alles auswählen** Mit dieser Option werden alle Testgeräte in der Liste ausgewählt.

  - **Löschen** Mit dieser Option werden alle ausgewählten Testgeräte gelöscht.

- **Aktualisieren** Sie können die Liste der Testgeräte aktualisieren, um den Status der Optionen aller Testgeräte zu überprüfen.

Ausführliche Informationen zu Testgeräten finden Sie unter [Add a Device to Test Update Functionality](https://technet.microsoft.com/library/ce509fd1-17b3-4b78-b269-fe5d06fe2e1d.aspx) in der Betriebsdokumentation.
## <a name="see-also"></a>Siehe auch

[Testgerät: Erstellen eines neuen oder Bearbeiten eines vorhandenen Testgeräts](ms.lync.lscp.ClientDeviceTestEdit.md)

[New-CsTestDevice](https://docs.microsoft.com/powershell/module/skype/new-cstestdevice?view=skype-ps)

[Set-CsTestDevice](https://docs.microsoft.com/powershell/module/skype/set-cstestdevice?view=skype-ps)

[Anzeigen von Softwareupdates für Geräte in Ihrer Organisation](https://technet.microsoft.com/library/d2cca12b-ed43-4e1f-90ab-d14bca8b482c.aspx)
