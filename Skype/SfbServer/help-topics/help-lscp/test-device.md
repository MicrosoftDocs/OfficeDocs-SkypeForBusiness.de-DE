---
title: Testgerät
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
- ms.lync.lscp.ClientDeviceTestMain
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: a1ea564c-f403-4f61-a36b-5a429708e7ca
description: Sie können ein Gerät zur Seite Testgerät hinzufügen und mit diesem Gerät anschließend die Funktionalität neuer Updates überprüfen, bevor die Updates auf Produktionsgeräten bereitgestellt werden. Sie können ein Gerät global (in der gesamten Umgebung) oder an einem einzelnen Standort testen. Sie identifizieren ein Testgerät über seine MAC-Adresse (Media Access Control) oder Seriennummer. Wenn Sie ein Gerät hinzufügen, wird es in der Liste auf der Seite Testgerät der Skype for Business Server-Systemsteuerung angezeigt.
ms.openlocfilehash: e48c76237f8d9cafb1642e8ec1e598dcc24453c3
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51099351"
---
# <a name="test-device"></a>Testgerät

Sie können ein Gerät zur Seite **Testgerät** hinzufügen und mit diesem Gerät anschließend die Funktionalität neuer Updates überprüfen, bevor die Updates auf Produktionsgeräten bereitgestellt werden. Sie können ein Gerät global (in der gesamten Umgebung) oder an einem einzelnen Standort testen. Sie identifizieren ein Testgerät über seine MAC-Adresse (Media Access Control) oder Seriennummer. Wenn Sie ein Gerät hinzufügen, wird es in der Liste auf der Seite **Testgerät** der Skype for Business Server-Systemsteuerung angezeigt.

## <a name="tasks-you-can-perform"></a>Mögliche Aufgaben

Auf der Seite **Testgerät** können Sie die folgenden Aufgaben ausführen:

- Hinzufügen eines Testgeräts auf globaler Ebene oder für einen bestimmten Standort

- Ändern der Optionen für ein vorhandenes Testgerät

## <a name="ui-reference"></a>Referenz zur Benutzeroberfläche

In den folgenden Listen werden die Menüs, Befehle, Felder und Eigenschaften der Seite beschrieben.

- **Neu** Sie können ein neues Testgerät mit folgendem Umfang hinzufügen:

  - Global

  - Website

- **Bearbeiten** Sie können die Optionen eines Testgeräts in der Liste ändern. Mit dieser Option haben Sie folgende Möglichkeiten:

  - **Details anzeigen** Mit dieser Option wird ein Dialogfeld geöffnet, in dem Sie die Optionen für ein Testgerät ändern können.

  - **Wählen Sie Alle aus.** Mit dieser Option werden alle Testgeräte in der Liste ausgewählt.

  - **Löschen** Mit dieser Option werden alle ausgewählten Testgeräte gelöscht.

- **Aktualisieren** Sie können die Liste der Testgeräte aktualisieren, um den Status der Optionen aller Testgeräte zu überprüfen.

Ausführliche Informationen zu Testgeräten finden Sie unter [Add a Device to Test Update Functionality](/previous-versions/office/lync-server-2013/lync-server-2013-create-a-device-to-test-update-functionality) in der Betriebsdokumentation.
## <a name="see-also"></a>Siehe auch

[Testgerät: Erstellen eines neuen oder Bearbeiten eines vorhandenen Testgeräts](test-device-create-new-or-edit-existing.md)

[New-CsTestDevice](/powershell/module/skype/new-cstestdevice?view=skype-ps)

[Set-CsTestDevice](/powershell/module/skype/set-cstestdevice?view=skype-ps)

[Anzeigen von Softwareupdates für Geräte in Ihrer Organisation](/previous-versions/office/lync-server-2013/lync-server-2013-view-software-updates-for-devices-in-your-organization)