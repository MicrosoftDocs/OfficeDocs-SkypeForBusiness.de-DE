---
title: Archivierungsrichtlinie zum Erstellen neuer oder Bearbeiten vorhandener Daten
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.lscp.MonArchPolicyEdit
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: a4f948e7-e8f6-449a-8907-f61c5b143c05
ROBOTS: NOINDEX, NOFOLLOW
description: 'Sie verwenden Archivierungsrichtlinien, um die Archivierung interner und externer Kommunikation in Ihrer Bereitstellung für Benutzer zu steuern, die in Skype for Business Server verwaltet werden. Zu den Archivierungsrichtlinien gehören die globale Richtlinie und optional eine oder mehrere Richtlinien für Standorte und Benutzer:'
ms.openlocfilehash: 1eb1f0060e80fbb7d325f5fbe1b7a247d6d006b6
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/03/2020
ms.locfileid: "41691220"
---
# <a name="archiving-policy-create-new-or-edit-existing"></a>Archivierungsrichtlinie: Erstellen einer neuen oder Bearbeiten einer vorhandenen Archivierungsrichtlinie
 
Sie verwenden Archivierungsrichtlinien, um die Archivierung interner und externer Kommunikation in Ihrer Bereitstellung für Benutzer zu steuern, die in Skype for Business Server verwaltet werden. Zu den Archivierungsrichtlinien gehören die globale Richtlinie und optional eine oder mehrere Richtlinien für Standorte und Benutzer:
  
- **Globale Richtlinie** Die globale Richtlinie wird in allen Skype for Business Server-Bereitstellungen standardmäßig erstellt. Sie können die globale Richtlinie bearbeiten, aber Sie können diese Richtlinie nicht löschen. Wenn Sie versuchen, sie zu löschen, werden alle Optionen auf die Standardwerte zurückgesetzt.
    
- **Website Richtlinien (optional)** Sie können eine oder mehrere Website Archivierungsrichtlinien angeben, die jeweils für die Aktivierung und Deaktivierung der Archivierung interner oder externer Kommunikation für eine bestimmte Website konfiguriert werden können. Eine Standortrichtlinie setzt die globale Richtlinie außer Kraft, jedoch nur für die in den Archivierungsrichtlinien angegebenen Standorte. Sie können Standortrichtlinien bearbeiten oder löschen.
    
- **Benutzerrichtlinien (optional)** Sie können eine oder mehrere Benutzer Archivierungsrichtlinien angeben, die jeweils für die Aktivierung und Deaktivierung der Archivierung für die interne oder externe Kommunikation für einen bestimmten Benutzer konfiguriert werden können. Eine Benutzerrichtlinie setzt die globale Richtlinie und die Standortrichtlinien außer Kraft, jedoch nur für die Benutzer, denen Sie eine Benutzerrichtlinie zuweisen. Sie können Benutzerrichtlinien bearbeiten oder löschen.
    
> [!NOTE]
> Wenn Sie die Exchange-Integration zum Speichern von Archivierungsdaten in Microsoft Exchange verwenden, Steuern Exchange-Richtlinien die Archivierung für in Exchange beheimatete Benutzer. Um die Archivierung für diese Benutzer zu aktivieren, muss das Postfach des Benutzers in-situ-Speicherplatz platziert werden. 
  
Geben Sie die folgenden Optionen an, um die Einstellungen für eine neue oder vorhandene Archivierungsrichtlinie zu konfigurieren:
- **Name** Für jede Archivierungsrichtlinie ist ein Name erforderlich. Der Name wird anhand des Typs der Richtlinie bestimmt, die Sie hinzufügen oder bearbeiten:
    
  - **Globale Richtlinie** Der Standardname lautet Global. Sie können es in einen aussagekräftigeren Namen ändern. Ein Beispielname ist „Contoso North American Organization“.
    
  - **Website Richtlinie** Die in diesem Dialogfeld aufgeführten Websites enthalten alle verfügbaren Websites in Ihrer Bereitstellung. Klicken Sie auf eine einzelne Website, um Sie auszuwählen. Beispiel: Redmond-Rechenzentrum.
    
  - **Benutzerrichtlinien** Geben Sie einen geeigneten Namen an, beispielsweise den Namen eines bestimmten Benutzers oder den Namen einer Benutzergruppe oder eines Teams in Ihrer Organisation. Beispiel: „Rechtsabteilung“.
    
- **Beschreibung** Dies ist optional. Verwenden Sie diese Option zum Angeben weiterer Details, z. B. Umfang oder Zweck der Richtlinie. Beispiel: „Koordination mit Rechtsabteilungen anderer Standorte“.
    
- **Archivieren interner Kommunikation** Aktivieren Sie dieses Kontrollkästchen, um die Archivierung von Kommunikationen in Ihrem internen Netzwerk zu aktivieren. Diese Option ist in keiner Richtlinie standardmäßig aktiviert.
    
- **Archivieren externer Kommunikation** Aktivieren Sie dieses Kontrollkästchen, um die Archivierung von Kommunikationen zu aktivieren, die externe Benutzer einschließen, beispielsweise Remotebenutzer (einschließlich anonyme und PIC-Benutzer), und Verbundpartner. Diese Option ist in keiner Richtlinie standardmäßig aktiviert.
    
Details zum Archivierungsfeature und zu den Funktionen, einschließlich der Exchange-Integration, finden Sie unter [Planen der Archivierung in Skype for Business Server](../../../plan-your-deployment/archiving/archiving.md), [Bereitstellen der Archivierung für Skype for Business Server](../../../deploy/deploy-archiving/deploy-archiving.md)und [Verwalten der Archivierung in Skype for Business Server](../../../manage/archiving/archiving.md).

