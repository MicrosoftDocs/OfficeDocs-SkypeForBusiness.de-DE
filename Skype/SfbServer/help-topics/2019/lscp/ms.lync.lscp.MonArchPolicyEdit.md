---
title: Erstellen einer neuen oder Bearbeiten einer vorhandenen Archivierungsrichtlinie
ms.reviewer: null
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
  - ms.lync.lscp.MonArchPolicyEdit
ms.prod: skype-for-business-itpro
f1.keywords:
  - CSH
ms.localizationpriority: medium
ms.assetid: a4f948e7-e8f6-449a-8907-f61c5b143c05
ROBOTS: 'NOINDEX, NOFOLLOW'
description: 'Sie verwenden Archivierungsrichtlinien, um die Archivierung der internen und externen Kommunikation in Ihrer Bereitstellung für Benutzer zu steuern, die auf Skype for Business Server verwaltet werden. Zu den Archivierungsrichtlinien gehören die globale Richtlinie und optional eine oder mehrere Richtlinien für Standorte und Benutzer:'
---

# <a name="archiving-policy-create-new-or-edit-existing"></a>Archivierungsrichtlinie: Erstellen einer neuen oder Bearbeiten einer vorhandenen Archivierungsrichtlinie
 
Sie verwenden Archivierungsrichtlinien, um die Archivierung der internen und externen Kommunikation in Ihrer Bereitstellung für Benutzer zu steuern, die auf Skype for Business Server verwaltet werden. Zu den Archivierungsrichtlinien gehören die globale Richtlinie und optional eine oder mehrere Richtlinien für Standorte und Benutzer:
  
- **Globale Richtlinie** Die globale Richtlinie wird standardmäßig in allen Skype for Business Server Bereitstellungen erstellt. Sie können die globale Richtlinie bearbeiten, aber Sie können diese Richtlinie nicht löschen. Wenn Sie versuchen, das Löschen durchzuführen, werden alle Optionen auf die Standardwerte zurückgesetzt.
    
- **Websiterichtlinien (optional)** Sie können eine oder mehrere Archivierungsrichtlinien für Standorte angeben, die Sie jeweils so konfigurieren können, dass die Archivierung der internen oder externen Kommunikation für einen bestimmten Standort aktiviert und deaktiviert wird. Eine Standortrichtlinie setzt die globale Richtlinie außer Kraft, jedoch nur für die in den Archivierungsrichtlinien angegebenen Standorte. Sie können Standortrichtlinien bearbeiten oder löschen.
    
- **Benutzerrichtlinien (optional)** Sie können eine oder mehrere Archivierungsrichtlinien für Benutzer angeben, die Sie jeweils so konfigurieren können, dass die Archivierung für die interne oder externe Kommunikation für einen bestimmten Benutzer aktiviert und deaktiviert wird. Eine Benutzerrichtlinie setzt die globale Richtlinie und die Standortrichtlinien außer Kraft, jedoch nur für die Benutzer, denen Sie eine Benutzerrichtlinie zuweisen. Sie können Benutzerrichtlinien bearbeiten oder löschen.
    
> [!NOTE]
> Wenn Sie Exchange Integration zum Speichern von Archivierungsdaten in Microsoft Exchange verwenden, steuern Exchange Richtlinien die Archivierung für Benutzer, die auf Exchange verwaltet werden. Um die Archivierung für diese Benutzer zu aktivieren, muss das Postfach des Benutzers in In-Place Haltebereich gesetzt werden. 
  
Geben Sie die folgenden Optionen an, um die Einstellungen für eine neue oder vorhandene Archivierungsrichtlinie zu konfigurieren:
- **Namen** Jede Archivierungsrichtlinie erfordert einen Namen. Der Name wird anhand des Typs der Richtlinie bestimmt, die Sie hinzufügen oder bearbeiten:
    
  - **Globale Richtlinie** Der Standardname lautet "Global". Sie können ihn in einen aussagekräftigeren Namen ändern. Beispiel: Contoso North American Organization.
    
  - **Standortrichtlinie** Die in diesem Dialogfeld aufgeführten Websites enthalten alle verfügbaren Websites in Ihrer Bereitstellung. Klicken Sie auf eine einzelne Website, um sie auszuwählen. Beispiel: Redmond Data Center.
    
  - **Benutzerrichtlinie** Geben Sie einen geeigneten Namen an, z. B. den Namen eines bestimmten Benutzers oder den Namen einer Benutzergruppe oder eines Teams in Ihrer Organisation. Beispiel: Rechtsabteilung.
    
- **Beschreibung** Dies ist optional. Verwenden Sie diese Option zum Angeben weiterer Details, z. B. Umfang oder Zweck der Richtlinie. Beispiel: "Koordination mit Rechtsabteilungen anderer Standorte".
    
- **Interne Kommunikation archivieren** Aktivieren Sie dieses Kontrollkästchen, um die Archivierung der Kommunikation in Ihrem internen Netzwerk zu aktivieren. Diese Option ist in keiner Richtlinie standardmäßig aktiviert.
    
- **Archivieren der externen Kommunikation** Aktivieren Sie dieses Kontrollkästchen, um die Archivierung von Kommunikationen zu aktivieren, die externe Benutzer, z. B. Remotebenutzer (einschließlich anonyme Benutzer und Pic-Einstellungsbenutzer), sowie Verbundpartner umfassen. Diese Option ist in keiner Richtlinie standardmäßig aktiviert.
    
Ausführliche Informationen zu den Archivierungsfeatures und -funktionen, einschließlich Exchange Integration, finden Sie unter [Plan for archiving in Skype for Business Server](../../../plan-your-deployment/archiving/archiving.md), [Deploy archiving for Skype for Business Server](../../../deploy/deploy-archiving/deploy-archiving.md) und [Manage archiving in Skype for Business Server ](../../../manage/archiving/archiving.md).

