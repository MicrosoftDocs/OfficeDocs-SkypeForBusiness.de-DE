---
title: Besprechungskonfiguration Erstellen einer neuen oder Bearbeiten einer vorhandenen Besprechungskonfiguration
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/24/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.lscp.ConfMeetingSettingEdit
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e8fc19fa-6cd7-4f68-b90a-1c7e1b649abd
description: Besprechungskonfigurationseinstellungen definieren die Benutzererfahrung für von Benutzern geplante Konferenzen. Diese Einstellungen gelten nur für geplante Besprechungen. Sie gelten nicht für Ad-hoc-Besprechungen, die durch Klicken auf die Option "Sofortbesprechungen" im Client erstellt wurden.
ms.openlocfilehash: dc37e3d76a81a09fe2cbd2407f4d3a2dff3d703e
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2021
ms.locfileid: "49803935"
---
# <a name="meeting-configuration-create-new-or-edit-existing"></a>Besprechungskonfiguration: Erstellen einer neuen oder Bearbeiten einer vorhandenen Besprechungskonfiguration

Besprechungskonfigurationseinstellungen definieren die Benutzererfahrung für von Benutzern geplante Konferenzen. Diese Einstellungen gelten nur für geplante Besprechungen. Sie gelten nicht für Ad-hoc-Besprechungen, die durch Klicken auf die Option  "Sofortbesprechungen" im Client erstellt wurden.

## <a name="ui-reference"></a>Referenz zur Benutzeroberfläche

In der folgenden Liste sind die Felder der Seite beschrieben.

- **Bereich** Gibt den Bereich der Besprechungskonfiguration an, die Sie erstellen oder ändern: global, Standort oder Pool.

- **Name** Besprechungskonfigurationen werden standardmäßig benannt, und der Name kann nicht geändert werden.

- **PstN-Anrufer umgehen Wartebereich** Aktivieren Sie dieses Kontrollkästchen, um Benutzer, die sich über eine Festnetzleitung (Public Switched Telephone Network, PSTN) in die Konferenz einwählen, automatisch zu lassen. Aktivieren Sie dieses Kontrollkästchen, um Festnetzanrufe an die Warteschleife weiterzurouten, in der sie sich befinden, bis ihnen ein Konferenz presenter Zugriff auf die Konferenz gewährt.

- **Als Moderator festlegen** Wählen Sie die Kategorie der Benutzer (neben dem Besprechungsorganisator) aus, die automatisch als Organisator festgelegt werden, wenn sie an einer Konferenz teilnehmen. Unabhängig von dieser Einstellung können Moderatoren explizit als Moderatoren festgelegt werden, wenn die Konferenz geplant ist, oder sie können während der Konferenz explizit zu Moderatoren ernannt werden. Mögliche Optionen:

  - **Keine** Wählen Sie diese Option aus, wenn nur der Organisator automatisch als Organisator festgelegt wird.

  - **Unternehmen** Wählen Sie diese Option aus, um nur Mitglieder Ihrer Organisation automatisch als Lektoren zu bestimmen.

  - **Jeder** Wählen Sie diese Option aus, um jeden automatisch als Lektor zu kennzeichnen.

- **Zugewiesener Konferenztyp standardmäßig** Diese Einstellung steuert, ob das Outlook-Konferenz-Add-In konferenzen immer mithilfe der vom Organisator zugewiesenen Konferenz plant, was bedeutet, dass geplante Konferenzen immer die gleiche Teilnahme-URL und dieselben Audioinformationen haben. Aktivieren Sie dieses Kontrollkästchen, damit für geplante Konferenzen immer dieselbe Teilnahme-URL verwendet wird. Aktivieren Sie dieses Kontrollkästchen, um für jede Konferenz eine andere Teilnahme-URL zu verwenden.

- **Anonyme Benutzer standardmäßig zugeben** Aktivieren Sie dieses Kontrollkästchen, wenn anonyme (d. h. nicht authentifizierte) Benutzer standardmäßig an Konferenzen teilnehmen dürfen. Aktivieren Sie dieses Kontrollkästchen, wenn anonyme Benutzer standardmäßig nicht an Konferenzen teilnehmen dürfen.

- **Logo-URL** Geben Sie die URL mit dem Bild ein, das für benutzerdefinierte Konferenzeinladungen verwendet werden soll.

- **Hilfe-URL** Geben Sie die URL für eine Website ein, auf der Benutzer Unterstützung für den Beitritt zur Konferenz erhalten können.

- **URL für rechtlichen Text** Geben Sie die URL für eine Website mit den rechtlichen Informationen und Haftungsausschlüssen für die Konferenz ein.

- **Benutzerdefinierter Fußzeilentext** Geben Sie den Text ein, der für benutzerdefinierte Konferenzeinladungen verwendet werden soll.

Ausführliche Informationen zur Verwendung von Besprechungskonfigurationen finden Sie unter [Create a or modify a Collection of Meeting Configuration Settings](https://technet.microsoft.com/library/ce6773c1-a0d5-4405-8e32-33a6f3a46a1a.aspx) in der Betriebsdokumentation. Ausführliche Informationen zum Festlegen von Besprechungskonfigurationen für große Besprechungen finden Sie unter [Setting Up Support for Large Meetings](https://technet.microsoft.com/library/8e22d34b-b395-408d-9d48-8f2a3abe9513.aspx) in der Planungsdokumentation.


