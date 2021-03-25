---
title: Besprechungskonfiguration Erstellen neuer oder Bearbeiten vorhandener Besprechungskonfigurationen
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
- ms.lync.lscp.ConfMeetingSettingEdit
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
localization_priority: Normal
ms.assetid: e8fc19fa-6cd7-4f68-b90a-1c7e1b649abd
ROBOTS: NOINDEX, NOFOLLOW
description: Besprechungskonfigurationseinstellungen definieren die Benutzererfahrung für von Benutzern geplante Konferenzen. Diese Einstellungen gelten nur für geplante Besprechungen. Sie gelten nicht für Ad-hoc-Besprechungen, die durch Klicken auf die Option Jetzt treffen im Client erstellt wurden.
ms.openlocfilehash: 3d37b1894531a62f605f083cbe1e2f36953f2ff2
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51121129"
---
# <a name="meeting-configuration-create-new-or-edit-existing"></a>Besprechungskonfiguration: Erstellen einer neuen oder Bearbeiten einer vorhandenen Besprechungskonfiguration

Besprechungskonfigurationseinstellungen definieren die Benutzererfahrung für von Benutzern geplante Konferenzen. Diese Einstellungen gelten nur für geplante Besprechungen. Sie gelten nicht für Ad-hoc-Besprechungen, die durch Klicken auf die Option **Jetzt** treffen im Client erstellt wurden.

## <a name="ui-reference"></a>Referenz zur Benutzeroberfläche

In der folgenden Liste sind die Felder der Seite beschrieben.

- **Bereich** Gibt den Umfang der Besprechungskonfiguration an, die Sie erstellen oder ändern: global, standort- oder pool.

- **Name** Besprechungskonfigurationen werden standardmäßig benannt, und der Name kann nicht geändert werden.

- **PstN-Anrufer umgehen Lobby** Aktivieren Sie dieses Kontrollkästchen, um Benutzer, die sich über eine Festnetzleitung (Public Switched Telephone Network, PSTN) in die Konferenz einwählen, automatisch zu lassen. Aktivieren Sie dieses Kontrollkästchen, um PSTN-Anrufer an die Konferenzlobby weiterzurouten, in der sie sich befinden, bis ihnen ein Konferenz presenter Zugriff auf die Konferenz gewährt.

- **Als Moderator festlegen** Wählen Sie die Kategorie der Benutzer (neben dem Besprechungsorganisator), die automatisch als Organisator festgelegt werden, wenn sie an einer Konferenz teilnehmen. Unabhängig von dieser Einstellung können Moderatoren explizit als Moderatoren festgelegt werden, wenn die Konferenz geplant ist, oder sie können während der Konferenz explizit zum Moderator heraufgestuft werden. Mögliche Optionen:

  - **Keine** Wählen Sie diese Option aus, wenn kein anderer als der Organisator automatisch als Organisator festgelegt wird.

  - **Unternehmen** Wählen Sie diese Option aus, um automatisch nur Mitglieder Ihrer Organisation als Lektoren zu bestimmen.

  - **Jeder** Wählen Sie diese Option aus, um jeden automatisch als Lektor zu bestimmen.

- **Zugewiesener Konferenztyp standardmäßig** Diese Einstellung steuert, ob das Outlook Conferencing Addin konferenzen immer mithilfe der vom Organisator zugewiesenen Konferenz plant, was bedeutet, dass geplante Konferenzen immer die gleiche Teilnahme-URL und Audioinformationen haben. Aktivieren Sie dieses Kontrollkästchen, damit geplante Konferenzen immer dieselbe Teilnahme-URL verwenden. Aktivieren Sie dieses Kontrollkästchen, um eine andere Teilnahme-URL für jede Konferenz zu verwenden.

- **Anonyme Benutzer standardmäßig zugeben** Aktivieren Sie dieses Kontrollkästchen, wenn anonyme (d. h. nicht authentifizierte) Benutzer standardmäßig an Konferenzen teilnehmen dürfen. Aktivieren Sie dieses Kontrollkästchen, wenn anonyme Benutzer standardmäßig nicht an Konferenzen teilnehmen dürfen.

- **Logo-URL** Geben Sie die URL ein, mit der das Bild für benutzerdefinierte Konferenzeinladungen verwendet werden soll.

- **Hilfe-URL** Geben Sie die URL für eine Website ein, auf der Benutzer Unterstützung für den Beitritt zur Konferenz erhalten können.

- **URL für juristischen Text** Geben Sie die URL für eine Website mit den rechtlichen Informationen und Haftungsausschlüssen für die Konferenz ein.

- **Benutzerdefinierter Fußzeilentext** Geben Sie den Text ein, der für benutzerdefinierte Konferenzeinladungen verwendet werden soll.

Ausführliche Informationen zur Verwendung von Besprechungskonfigurationen finden Sie unter [Create a or modify a Collection of Meeting Configuration Settings](/previous-versions/office/lync-server-2013/lync-server-2013-create-or-modify-a-collection-of-meeting-configuration-settings) in der Betriebsdokumentation. Ausführliche Informationen zum Festlegen von Besprechungskonfigurationen für große Besprechungen finden Sie unter [Einrichten des Support für große](/previous-versions/office/lync-server-2013/lync-server-2013-setting-up-support-for-large-meetings) Besprechungen in der Planungsdokumentation.