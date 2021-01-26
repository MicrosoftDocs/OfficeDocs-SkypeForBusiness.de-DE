---
title: 'Archivierungsrichtlinie: Erstellen einer neuen oder Bearbeiten einer vorhandenen Archivierungsrichtlinie'
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/27/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.lscp.MonArchPolicyEdit
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: a4f948e7-e8f6-449a-8907-f61c5b143c05
description: 'Sie verwenden Archivierungsrichtlinien, um die Archivierung der internen und externen Kommunikation in Ihrer Bereitstellung für Benutzer zu steuern, die in Skype for Business Server gespeichert sind. Zu den Archivierungsrichtlinien gehören die globale Richtlinie und optional eine oder mehrere Richtlinien für Standorte und Benutzer:'
ms.openlocfilehash: 9c852c592776f9e529c11dd46272715af52e8111
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2021
ms.locfileid: "49826965"
---
# <a name="archiving-policy-create-new-or-edit-existing"></a>Archivierungsrichtlinie: Erstellen einer neuen oder Bearbeiten einer vorhandenen Archivierungsrichtlinie
 
Sie verwenden Archivierungsrichtlinien, um die Archivierung der internen und externen Kommunikation in Ihrer Bereitstellung für Benutzer zu steuern, die in Skype for Business Server gespeichert sind. Zu den Archivierungsrichtlinien gehören die globale Richtlinie und optional eine oder mehrere Richtlinien für Standorte und Benutzer:
  
- **Globale Richtlinie** Die globale Richtlinie wird standardmäßig in allen Skype for Business Server-Bereitstellungen erstellt. Sie können die globale Richtlinie bearbeiten, aber Sie können diese Richtlinie nicht löschen. Wenn Sie versuchen, das Löschen durchzuführen, werden alle Optionen auf die Standardwerte zurückgesetzt.
    
- **Standortrichtlinien (optional)** Sie können eine oder mehrere Archivierungsrichtlinien für Den Standort angeben, die Sie jeweils so konfigurieren können, dass die Archivierung der internen oder externen Kommunikation für einen bestimmten Standort aktiviert oder deaktiviert wird. Eine Standortrichtlinie setzt die globale Richtlinie außer Kraft, jedoch nur für die in den Archivierungsrichtlinien angegebenen Standorte. Sie können Standortrichtlinien bearbeiten oder löschen.
    
- **Benutzerrichtlinien (optional)** Sie können eine oder mehrere Archivierungsrichtlinien für Benutzer angeben, die Sie jeweils so konfigurieren können, dass die Archivierung für die interne oder externe Kommunikation für einen bestimmten Benutzer aktiviert oder deaktiviert wird. Eine Benutzerrichtlinie setzt die globale Richtlinie und die Standortrichtlinien außer Kraft, jedoch nur für die Benutzer, denen Sie eine Benutzerrichtlinie zuweisen. Sie können Benutzerrichtlinien bearbeiten oder löschen.
    
> [!NOTE]
> Wenn Sie die Exchange-Integration zum Speichern von Archivierungsdaten in Microsoft Exchange verwenden, steuern Exchange 2013-Richtlinien die Archivierung für Benutzer, die in Exchange 2013 gespeichert sind. Um die Archivierung für diese Benutzer zu aktivieren, muss das Postfach des Benutzers in den In-Place platziert werden. 
  
Geben Sie die folgenden Optionen an, um die Einstellungen für eine neue oder vorhandene Archivierungsrichtlinie zu konfigurieren:
- **Name** Jede Archivierungsrichtlinie erfordert einen Namen. Der Name wird anhand des Typs der Richtlinie bestimmt, die Sie hinzufügen oder bearbeiten:
    
  - **Globale Richtlinie** Der Standardname ist "Global". Sie können ihn in einen aussagekräftigen Namen ändern. Beispiel: Contoso North American Organization.
    
  - **Standortrichtlinie** Die in diesem Dialogfeld aufgeführten Websites enthalten alle verfügbaren Websites in Ihrer Bereitstellung. Klicken Sie auf eine einzelne Website, um sie auszuwählen. Beispiel: Redmond Data Center.
    
  - **Benutzerrichtlinie** Geben Sie einen geeigneten Namen an, z. B. den Namen eines bestimmten Benutzers oder den Namen einer Benutzergruppe oder eines Teams in Ihrer Organisation. Beispiel: Rechtsabteilung.
    
- **Beschreibung** Dies ist optional. Verwenden Sie diese Option zum Angeben weiterer Details, z. B. Umfang oder Zweck der Richtlinie. Beispiel: "Koordination mit Rechtsabteilungen anderer Standorte".
    
- **Archivieren der internen Kommunikation** Aktivieren Sie dieses Kontrollkästchen, um die Archivierung der Kommunikation in Ihrem internen Netzwerk zu aktivieren. Diese Option ist in keiner Richtlinie standardmäßig aktiviert.
    
- **Archivieren der externen Kommunikation** Aktivieren Sie dieses Kontrollkästchen, um die Archivierung von Kommunikationen zu aktivieren, die externe Benutzer wie Remotebenutzer (einschließlich anonymer Benutzer und Benutzer mit PIC-Einstellung) und Verbundpartner umfassen. Diese Option ist in keiner Richtlinie standardmäßig aktiviert.
    
Weitere Informationen zu den Archivierungsfunktionen, einschließlich der Exchange-Integration, finden Sie unter "Planen der Archivierung [in Skype for Business Server 2015",](../../plan-your-deployment/archiving/archiving.md)"Bereitstellen der Archivierung für Skype for Business Server [2015"](../../deploy/deploy-archiving/deploy-archiving.md)und "Verwalten der Archivierung [in Skype for Business Server 2015".](../../manage/archiving/archiving.md)

