---
title: Besprechungskonfiguration – Erstellen einer neuen oder Bearbeiten einer vorhandenen Besprechungskonfiguration
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
- ms.lync.lscp.ConfMeetingSettingEdit
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
ms.localizationpriority: medium
ms.assetid: e8fc19fa-6cd7-4f68-b90a-1c7e1b649abd
ROBOTS: NOINDEX, NOFOLLOW
description: Besprechungskonfigurationseinstellungen definieren die Benutzerbeitrittserfahrung für von Benutzern geplante Konferenzen. Diese Einstellungen gelten nur für geplante Besprechungen. Sie gelten nicht für Ad-hoc-Besprechungen, die durch Klicken auf die Option "Jetzt besprechen" im Client erstellt wurden.
ms.openlocfilehash: 6972bf701d2aa2f7bb01e92e7756eeee6cb1f3db
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/08/2021
ms.locfileid: "60829389"
---
# <a name="meeting-configuration-create-new-or-edit-existing"></a>Besprechungskonfiguration: Erstellen einer neuen oder Bearbeiten einer vorhandenen Besprechungskonfiguration

Besprechungskonfigurationseinstellungen definieren die Benutzerbeitrittserfahrung für von Benutzern geplante Konferenzen. Diese Einstellungen gelten nur für geplante Besprechungen. Sie gelten nicht für Ad-hoc-Besprechungen, die durch Klicken auf die Option **"Jetzt besprechen"** im Client erstellt wurden.

## <a name="ui-reference"></a>Referenz zur Benutzeroberfläche

In der folgenden Liste sind die Felder der Seite beschrieben.

- **Bereich** Gibt den Umfang der Besprechungskonfiguration an, die Sie erstellen oder ändern: global, Standort oder Pool.

- **Name** Besprechungskonfigurationen werden standardmäßig benannt, und der Name kann nicht geändert werden.

- **PSTN-Anrufer umgehen Wartebereich** Aktivieren Sie dieses Kontrollkästchen, um Benutzer, die sich über eine PsTN-Telefonleitung (Public Switched Telephone Network) in die Konferenz einwählen, automatisch zuzulassen. Deaktivieren Sie dieses Kontrollkästchen, um PSTN-Anrufer an den Konferenzlobby weiterzuleiten, wo sie sich in der Warteschleife befinden, bis ein Konferenzreferent ihnen Zugriff auf die Konferenz gewährt.

- **Als Referenten festlegen** Wählen Sie die Kategorie der Benutzer (neben dem Besprechungsorganisator) aus, die automatisch als Referenten festgelegt werden, wenn sie an einer Konferenz teilnehmen. Unabhängig von dieser Einstellung können Referenten explizit als Referenten festgelegt werden, wenn die Konferenz geplant ist, oder sie können während der Konferenz explizit zum Referenten höhergestuft werden. Mögliche Optionen:

  - **Keine** Wählen Sie diese Option aus, wenn kein Anderer als der Organisator automatisch als Referent festgelegt wird.

  - **Unternehmen** Wählen Sie diese Option aus, um nur Mitglieder Ihrer Organisation automatisch als Referenten festzulegen.

  - **Jeder** Wählen Sie diese Option aus, um jeden automatisch als Referenten festzulegen.

- **Konferenztyp standardmäßig zugewiesen** Mit dieser Einstellung wird gesteuert, ob das Outlook Konferenz-Add-In immer Konferenzen mithilfe der zugewiesenen Konferenz des Organisators plant, was bedeutet, dass geplante Konferenzen immer die gleiche Teilnahme-URL und Audioinformationen haben. Aktivieren Sie dieses Kontrollkästchen, damit geplante Konferenzen immer dieselbe Beitritts-URL verwenden. Deaktivieren Sie dieses Kontrollkästchen, um für jede Konferenz eine andere Beitritts-URL zu verwenden.

- **Standardmäßiges Zulassen anonymer Benutzer** Aktivieren Sie dieses Kontrollkästchen, wenn anonyme (d. h. nicht authentifizierte) Benutzer standardmäßig an Konferenzen teilnehmen dürfen. Deaktivieren Sie dieses Kontrollkästchen, wenn anonyme Benutzer standardmäßig nicht an Konferenzen teilnehmen dürfen.

- **Logo-URL** Geben Sie die URL ein, die das Bild enthält, das für benutzerdefinierte Konferenzseinladungen verwendet werden soll.

- **Hilfe-URL** Geben Sie die URL für eine Website ein, auf der Benutzer Unterstützung für die Teilnahme an der Konferenz erhalten können.

- **URL des rechtlichen Texts** Geben Sie die URL für eine Website ein, die die rechtlichen Informationen und Haftungsausschlüsse für die Konferenz enthält.

- **Benutzerdefinierter Fußzeilentext** Geben Sie den Text ein, der für benutzerdefinierte Konferenzseinladungen verwendet werden soll.

Ausführliche Informationen zur Verwendung von Besprechungskonfigurationen finden Sie unter [Create a or modify a Collection of Meeting Configuration Settings](/previous-versions/office/lync-server-2013/lync-server-2013-create-or-modify-a-collection-of-meeting-configuration-settings) in der Betriebsdokumentation. Ausführliche Informationen zum Festlegen von Besprechungskonfigurationen für große Besprechungen finden Sie unter "Einrichten der [Unterstützung für große Besprechungen"](/previous-versions/office/lync-server-2013/lync-server-2013-setting-up-support-for-large-meetings) in der Planungsdokumentation.