---
title: Besprechungskonfiguration neues erstellen oder vorhandenes bearbeiten
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
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
description: Mithilfe von Konfigurationseinstellungen für Besprechungen wird der Benutzerbeitritt für von Benutzern geplante Konferenzen definiert. Diese Einstellungen gelten nur für geplante Besprechungen. Sie gelten nicht für Ad-hoc-Besprechungen, die durch Klicken auf die Option Sofortbesprechung erstellt werden.
ms.openlocfilehash: e7b3ac1858ed012d99af32c8910b6f9e6d69f6a2
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2020
ms.locfileid: "41822688"
---
# <a name="meeting-configuration-create-new-or-edit-existing"></a>Besprechungskonfiguration: Erstellen einer neuen oder Bearbeiten einer vorhandenen Besprechungskonfiguration

Mithilfe von Konfigurationseinstellungen für Besprechungen wird der Benutzerbeitritt für von Benutzern geplante Konferenzen definiert. Diese Einstellungen gelten nur für geplante Besprechungen. Sie gelten nicht für Ad-hoc-Besprechungen, die durch Klicken auf die Option **Sofortbesprechung** erstellt werden.

## <a name="ui-reference"></a>Referenz zur Benutzeroberfläche

In der folgenden Liste werden die Felder der Seite beschrieben.

- **Bereich** Identifiziert den Bereich der zu erstellende oder zu ändernden besprechungskonfiguration: Global, Site oder Pool.

- **Name** Besprechungs Konfigurationen werden standardmäßig benannt, und der Name kann nicht geändert werden.

- **PSTN-Anrufer Bypass-Lobby** Aktivieren Sie dieses Kontrollkästchen, um die Benutzer, die sich bei der Konferenz einwählen, über eine Telefonleitung des öffentlichen Telefonnetzes (PSTN) automatisch zuzulassen. Deaktivieren Sie dieses Kontrollkästchen, um PSTN-Anrufer in den Konferenzwartebereich weiterzuleiten und dort zu halten, bis ihnen der Konferenzreferent Zugang zur Besprechung gewährt.

- **Als Referent festlegen** Wählen Sie die Kategorie der Benutzer (außer dem Besprechungsorganisator) aus, die beim teilnehmen an einer Konferenz automatisch als Referenten festgelegt werden. Unabhängig von dieser Einstellung können Benutzer explizit als Referenten festgelegt werden, wenn die Konferenz geplant wird, oder sie können während der Konferenz explizit zu Referenten ernannt werden. Mögliche Optionen:

  - **Keine** Wählen Sie diese Option aus, wenn kein anderer als der Organisator automatisch als Referent festgelegt ist.

  - **Unternehmen** Wählen Sie diese Option aus, um nur Mitglieder Ihrer Organisation automatisch als Referenten festzulegen.

  - **Alle Personen** Wählen Sie diese Option aus, um automatisch alle Personen als Referenten festzulegen.

- **Standardmäßig zugewiesene Konferenztypen** Mit dieser Einstellung wird gesteuert, ob das Outlook-Konferenz-Add-in Konferenzen immer mithilfe der zugewiesenen Konferenz des Organisators plant, was bedeutet, dass geplante Konferenzen immer über die gleiche URL-und Audioinformationen für die Teilnahme verfügen. Aktivieren Sie dieses Kontrollkästchen, damit geplante Konferenzen immer dieselbe Join-URL verwenden. Deaktivieren Sie dieses Kontrollkästchen, um für jede Konferenz eine andere Join-URL zu verwenden.

- **Standardmäßig anonyme Benutzer zulassen** Aktivieren Sie dieses Kontrollkästchen, wenn anonyme (nicht authentifizierte) Benutzer standardmäßig an Konferenzen teilnehmen dürfen. Deaktivieren Sie dieses Kontrollkästchen, wenn anonyme Benutzer nicht standardmäßig zu Konferenzen zugelassen werden sollen.

- **Logo-URL** Geben Sie die URL ein, die das Bild enthält, das für benutzerdefinierte Konferenzeinladungen verwendet werden soll.

- **Hilfe-URL** Geben Sie die URL für eine Website ein, auf der Benutzer Unterstützung für die Teilnahme an der Konferenz erhalten können.

- **URL für juristischen Text** Geben Sie die URL für eine Website mit den rechtlichen Informationen und Haftungsausschlüssen für die Konferenz ein.

- **Benutzerdefinierter Fußzeilentext** Geben Sie den Text ein, der für benutzerdefinierte Konferenzeinladungen verwendet werden soll.

Ausführliche Informationen zur Verwendung von Besprechungskonfigurationen finden Sie in der Betriebsdokumentation unter [Create a or modify a Collection of Meeting Configuration Settings](https://technet.microsoft.com/library/ce6773c1-a0d5-4405-8e32-33a6f3a46a1a.aspx). Ausführliche Informationen zur Festlegung von Besprechungskonfigurationen für große Besprechungen finden Sie in der Planungsdokumentation unter [Setting Up Support for Large Meetings](https://technet.microsoft.com/library/8e22d34b-b395-408d-9d48-8f2a3abe9513.aspx).


