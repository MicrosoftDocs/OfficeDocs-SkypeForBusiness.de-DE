---
title: Archivierungsrichtlinie Erstellen einer neuen oder Bearbeiten einer vorhandenen
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 3/27/2015
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.MonArchPolicyEdit
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: a4f948e7-e8f6-449a-8907-f61c5b143c05
description: 'Verwenden Sie Archivierungsrichtlinien, um die Archivierung der internen und externen Kommunikation in Ihrer Bereitstellung für Benutzer, die auf Skype für Business Server verwaltet werden. Zu den Archivierungsrichtlinien gehören die globale Richtlinie und optional eine oder mehrere Richtlinien für Standorte und Benutzer:'
ms.openlocfilehash: f01fb0c53d88000d76a00e74353cd1c6005163f0
ms.sourcegitcommit: 9d816453083c26fd24f8a1cdc0f53f3d218c43b3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/25/2018
---
# <a name="archiving-policy-create-new-or-edit-existing"></a>Archivierungsrichtlinie: Erstellen einer neuen oder Bearbeiten einer vorhandenen Archivierungsrichtlinie
 
Verwenden Sie Archivierungsrichtlinien, um die Archivierung der internen und externen Kommunikation in Ihrer Bereitstellung für Benutzer, die auf Skype für Business Server verwaltet werden. Zu den Archivierungsrichtlinien gehören die globale Richtlinie und optional eine oder mehrere Richtlinien für Standorte und Benutzer:
  
- **Globale Richtlinie** Die globale Richtlinie wird standardmäßig in allen Skype für Business Server-Bereitstellungen erstellt. Sie können die globale Richtlinie bearbeiten, aber nicht löschen. Wenn Sie versuchen, sie zu löschen, werden alle Optionen auf die Standardwerte zurückgesetzt.
    
- **Website-Richtlinien (optional)** Sie können mindestens einen Website-Archivierungsrichtlinien angeben, von denen jedes Sie zum Aktivieren und Deaktivieren der Archivierung von interner oder externer Kommunikation für eine bestimmte Website konfigurieren können. Eine Standortrichtlinie setzt die globale Richtlinie außer Kraft, jedoch nur für die in den Archivierungsrichtlinien angegebenen Standorte. Sie können Standortrichtlinien bearbeiten oder löschen.
    
- **Richtlinien für Benutzer (optional)** Sie können einen oder mehrere Benutzer Archivierungsrichtlinien angeben, die Sie zum Aktivieren und Deaktivieren der Archivierung für interner oder externer Kommunikation für einen bestimmten Benutzer konfigurieren können. Eine Benutzerrichtlinie setzt die globale Richtlinie und die Standortrichtlinien außer Kraft, jedoch nur für die Benutzer, denen Sie eine Benutzerrichtlinie zuweisen. Sie können Benutzerrichtlinien bearbeiten oder löschen.
    
> [!NOTE]
> Wenn Sie zum Speichern von Exchange-Integration verwenden, Archivieren von Daten in Microsoft Exchange, klicken Sie dann auf Exchange 2013 Richtlinien Steuerelement Archivierung für Benutzer auf Exchange 2013 verwaltet. Zum Aktivieren der Archivierung für die Benutzer muss das Postfach des Benutzers auf Compliance-Archiv platziert werden. 
  
Geben Sie die folgenden Optionen an, um die Einstellungen für eine neue oder vorhandene Archivierungsrichtlinie zu konfigurieren:
- **Name** Jede Archivierungsrichtlinie erfordert einen Namen an. Der Name wird anhand des Typs der Richtlinie bestimmt, die Sie hinzufügen oder bearbeiten:
    
  - **Globale Richtlinie** Der Standardname ist Global. Sie können ihn in einen aussagekräftigeren Namen ändern. Ein Beispielname ist „Contoso North American Organization“.
    
  - **Standortrichtlinie** In diesem Dialogfeld aufgeführten Sites enthalten alle verfügbaren Standorte in Ihrer Bereitstellung. Klicken Sie auf eine einzelne Website, um ihn auszuwählen. Beispielsweise Redmond-Rechenzentrum.
    
  - **Benutzerrichtlinie** Geben Sie einen geeigneten Namen, beispielsweise den Namen eines bestimmten Benutzers oder der Name des eine Benutzergruppe oder ein Team in Ihrer Organisation. Beispiel: „Rechtsabteilung“.
    
- **Beschreibung** Dieser Schritt ist optional. Verwenden Sie diese Option zum Angeben weiterer Details, z. B. Umfang oder Zweck der Richtlinie. Beispiel: „Koordination mit Rechtsabteilungen anderer Standorte“.
    
- **Interne Kommunikation archivieren** Aktivieren Sie dieses Kontrollkästchen, um die Archivierung der Kommunikation in Ihrem internen Netzwerk aktivieren. Diese Option ist in keiner Richtlinie standardmäßig aktiviert.
    
- **Externe Kommunikation archivieren** Aktivieren Sie dieses Kontrollkästchen zum Aktivieren der Archivierung der Kommunikation, die enthalten externe Benutzer, wie remote-Benutzern (einschließlich anonyme und PIC-Einstellung Benutzer), und Verbundpartner. Diese Option ist in keiner Richtlinie standardmäßig aktiviert.
    
Weitere Informationen über die Archivierungsfunktion und Funktionen, einschließlich Exchange-Integration finden Sie unter [Planen für die Archivierung in Skype für Business Server 2015](../../../plan-your-deployment/archiving/archiving.md), [Archivierung für Skype für Business Server 2015 bereitstellen](../../../deploy/deploy-archiving/deploy-archiving.md)und verwalten [Archivierung in Skype für Business Server 2015](../../../manage/archiving/archiving.md).

