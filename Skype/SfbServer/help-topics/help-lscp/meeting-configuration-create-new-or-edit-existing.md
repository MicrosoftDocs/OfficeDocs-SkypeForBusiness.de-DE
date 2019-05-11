---
title: Besprechungskonfiguration Erstellen einer neuen oder Bearbeiten einer vorhandenen
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/24/2015
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.ConfMeetingSettingEdit
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e8fc19fa-6cd7-4f68-b90a-1c7e1b649abd
description: Mithilfe von Konfigurationseinstellungen für Besprechungen wird der Benutzerbeitritt für von Benutzern geplante Konferenzen definiert. Diese Einstellungen gelten nur für geplante Besprechungen. Sie gelten nicht für Ad-hoc-Besprechungen, die durch Klicken auf die Option Sofortbesprechung erstellt werden.
ms.openlocfilehash: 6af03588f5265c7fba208e88f2965639a1933153
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "33910890"
---
# <a name="meeting-configuration-create-new-or-edit-existing"></a>Besprechungskonfiguration: Erstellen einer neuen oder Bearbeiten einer vorhandenen Besprechungskonfiguration

Mithilfe von Konfigurationseinstellungen für Besprechungen wird der Benutzerbeitritt für von Benutzern geplante Konferenzen definiert. Diese Einstellungen gelten nur für geplante Besprechungen. Sie gelten nicht für Ad-hoc-Besprechungen, die durch Klicken auf die Option **Sofortbesprechung** erstellt werden.

## <a name="ui-reference"></a>Referenz zur Benutzeroberfläche

In der folgenden Liste werden die Felder der Seite beschrieben.

- **Bereich** Gibt den Bereich der besprechungskonfiguration, die Sie erstellen oder ändern: global, Standort oder Pool.

- **Name** Besprechungskonfigurationen erhalten standardmäßig, und der Name kann nicht geändert werden.

- **PSTN-Anrufer umgehen die lobby** Aktivieren Sie dieses Kontrollkästchen, um automatisch Benutzer, die in einwählen, um der Konferenz über eine public switched Telephone Network, (PSTN) Telefonleitung zuzulassen. Deaktivieren Sie dieses Kontrollkästchen, um PSTN-Anrufer in den Konferenzwartebereich weiterzuleiten und dort zu halten, bis ihnen der Konferenzreferent Zugang zur Besprechung gewährt.

- **Legen Sie als Referent** Wählen Sie die Kategorie von Benutzern (außer dem Organisator der Besprechung), die automatisch als Referenten festgelegt werden, wenn sie an eine Konferenz teilnehmen. Unabhängig von dieser Einstellung können Benutzer explizit als Referenten festgelegt werden, wenn die Konferenz geplant wird, oder sie können während der Konferenz explizit zu Referenten ernannt werden. Mögliche Optionen:

  - **None** Wählen Sie diese Option aus, wenn keine andere Person als der Organisator automatisch als Referent festgelegt ist.

  - **Unternehmen** Wählen Sie diese Option, um nur Mitglieder Ihrer Organisation automatisch als Referenten festzulegen.

  - **Jeder** Wählen Sie diese Option, um automatisch alle Personen als Referenten festzulegen.

- **Konferenztyp standardmäßig zugewiesen** Dieser Einstellung wird gesteuert, ob das Outlook-Add-Konferenzen immer Konferenzen plant mithilfe der Organisator Konferenz zugewiesen, haben, d. h., die immer Konferenzen geplant, die dieselbe Join-URL und Zugriffsinformationen enthalten. Aktivieren Sie dieses Kontrollkästchen, geplante Konferenzen verwenden Sie dieselbe URL Join immer haben. Deaktivieren Sie dieses Kontrollkästchen, um einen anderen Join-URL für jede Konferenz verwenden.

- **Anonyme Benutzer zulassen, standardmäßig** Aktivieren Sie dieses Kontrollkästchen, wenn anonyme (d. h., nicht authentifizierte) Benutzer an Konferenzen teilnehmen in der Standardeinstellung zulässig sind. Deaktivieren Sie dieses Kontrollkästchen, wenn anonyme Benutzer nicht standardmäßig zu Konferenzen zugelassen werden sollen.

- **Logo-URL** Geben Sie die URL mit dem Bild für benutzerdefinierte konferenzeinladungen verwendet werden soll.

- **Hilfe-URL** Geben Sie die URL für eine Website, in dem Benutzer Hilfe zur Teilnahme an der Konferenz erhalten können.

- **URL zu rechtlichen** Geben Sie die URL für eine Website, die die rechtliche Hinweise und Haftungsausschlüsse für die Konferenz.

- **Benutzerdefinierter Fußzeilentext text** Geben Sie den Text für benutzerdefinierte konferenzeinladungen verwendet wird.

Ausführliche Informationen zur Verwendung von Besprechungskonfigurationen finden Sie in der Betriebsdokumentation unter [Create a or modify a Collection of Meeting Configuration Settings](https://technet.microsoft.com/library/ce6773c1-a0d5-4405-8e32-33a6f3a46a1a.aspx). Ausführliche Informationen zur Festlegung von Besprechungskonfigurationen für große Besprechungen finden Sie in der Planungsdokumentation unter [Setting Up Support for Large Meetings](https://technet.microsoft.com/library/8e22d34b-b395-408d-9d48-8f2a3abe9513.aspx).


