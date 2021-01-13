---
title: 'Archivierungskonfiguration: Erstellen einer neuen oder Bearbeiten einer vorhandenen Archivierungskonfiguration'
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
- ms.lync.lscp.MonArchSettingEdit
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
localization_priority: Normal
ms.assetid: 49096960-c442-4846-be8f-03c167acea41
ROBOTS: NOINDEX, NOFOLLOW
description: 'Sie verwenden Archivierungskonfigurationen, um archivierungsoptionen für Ihre Bereitstellung zu steuern. Zu den Archivierungskonfigurationen gehören die globale Konfiguration und optional eine oder mehrere Poolkonfigurationen:'
ms.openlocfilehash: 77d1be61be3a1bad063bb7f32957937f182094e4
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2021
ms.locfileid: "49812255"
---
# <a name="archiving-configuration-create-new-or-edit-existing"></a>Archivierungskonfiguration: Erstellen einer neuen oder Bearbeiten einer vorhandenen Archivierungskonfiguration
 
Sie verwenden Archivierungskonfigurationen, um archivierungsoptionen für Ihre Bereitstellung zu steuern. Zu den Archivierungskonfigurationen gehören die globale Konfiguration und optional eine oder mehrere Poolkonfigurationen:
  
- **Globale Konfiguration** Die globale Konfiguration wird standardmäßig erstellt. Sie können die globale Konfiguration bearbeiten, aber Sie können diese Archivierungskonfiguration nicht löschen. Wenn Sie versuchen, das Löschen durchzuführen, werden alle Optionen auf die Standardwerte zurückgesetzt.
    
- **Standortkonfiguration (optional)** Sie können eine oder mehrere Archivierungskonfigurationen für Den Standort angeben, die Sie jeweils zum Steuern der Archivierungsoptionen für einen bestimmten Standort konfigurieren können. Eine Standortkonfiguration setzt die globale Konfiguration außer Kraft, jedoch nur für die in den Archivierungsstandortkonfigurationen angegebenen Standorte. Sie können Standortkonfigurationen bearbeiten oder löschen.
    
- **Poolkonfiguration (optional)** Sie können eine oder mehrere Archivierungskonfigurationen für Pools angeben, um die Archivierungsoptionen für einen bestimmten Pool zu steuern. Eine Poolkonfiguration setzt die globale Konfiguration und Standortkonfiguration außer Kraft, jedoch nur für die in den Archivierungspoolkonfigurationen angegebenen Pools. Sie können Poolkonfigurationen bearbeiten oder löschen.
    
> [!NOTE]
> Archivierungskonfigurationen gelten für Benutzer, die in Skype for Business Server gespeichert sind, und, wenn Sie die Microsoft Exchange-Integrationsoption aktivieren, um Exchange zum Speichern von Archivierungsdaten in Microsoft Exchange zu verwenden, für Benutzer, die in Exchange gespeichert sind. Einige Optionen werden jedoch für Benutzer, die in Exchange zu Hause sind, geringfügig anders implementiert, wie im nächsten Abschnitt beschrieben. 
  
Geben Sie die folgenden Optionen an, um die Einstellungen für eine neue oder vorhandene Archivierungskonfiguration zu konfigurieren:
- **Name** Jede Archivierungskonfiguration erfordert einen Namen. Der Name wird anhand des Typs der Konfiguration bestimmt, die Sie hinzufügen oder bearbeiten:
    
  - **Globale Konfiguration** Der Standardname ist "Global". Beispiel: Contoso North American Organization.
    
  - **Standortkonfiguration** Die Liste enthält die verfügbaren Websites in Ihrer Bereitstellung. Klicken Sie auf eine einzelne Website, um sie auszuwählen. Beispiel: Redmond Data Center.
    
  - **Poolkonfiguration** Geben Sie einen geeigneten Namen an, der dem Namen eines bestimmten Front-End-Pools oder Standard Edition-Servers in Ihrer Bereitstellung entsprechen kann. Dies kann der Name eines bestimmten Front-End-Pools oder Standard Edition-Servers der Bereitstellung sein, beispielsweise "Marketingabteilung".
    
- **Beschreibung** Dies ist optional. Verwenden Sie diese Option zum Angeben weiterer Details wie Umfang oder Zweck der Konfiguration. Beispiel: "Koordination mit Rechtsabteilungen anderer Standorte".
    
- **Archivierungseinstellung** Folgende Optionen stehen zur Verfügung:
    
  - **IM-Sitzungen archivieren**
    
  - **Chat- und Webkonferenzsitzungen archivieren**
    
  - **Archivierung deaktivieren**
    
- **Blockieren von Chat- oder Webkonferenzsitzungen,** wenn die Archivierung fehlschlägt Zu den Fehlern gehören folgende:
    
  - **Bei einem** Ausfall von Im-A-Daten kann es sich um eine vollständige Datenbank oder ein Problem mit dem Speicherdienst befinden. In diesem Fall werden Sofortnachrichten für Benutzer blockiert, für die die Archivierung aktiviert wurde.
    
  - **Konferenzen** Ein Fehler kann eine nicht verfügbare Dateifreigabe oder ein Problem mit dem Speicherdienst sein. In diesem Fall werden aktiven Konferenzen, die beim Auftreten des Fehlers im Pool gehostet werden, in den eingeschränkten Modus umgeschaltet, und neue Konferenzen können nicht aktiviert werden.
    
    Sofortnachrichten und Konferenzen werden nach dem Beheben des Fehlers automatisch wiederhergestellt.
    
- **Microsoft Exchange-Integration** Wählen Sie diese Option aus, wenn Benutzer in Exchange zu Hause sind. Mit dieser Option wird Exchange zum Speichern von Daten für diese Benutzer verwendet, wenn ihre Postfächer in den In-Place wurden. Wenn alle Ihre Benutzer in Exchange gespeichert sind, müssen Sie keine separaten SQL Server zum Speichern von Archivierungsdaten einrichten.
    
- **Aktivieren des Löschens von Archivierungsdaten** Wählen Sie diese Option aus, um das Löschen zu aktivieren und Bereinigungsoptionen anzugeben, die Folgendes umfassen:
    
  - Bereinigung nach einer von Ihnen angegebenen Anzahl von Tagen
    
  - Löschen, nachdem die Archivierungsdaten exportiert wurden (einschließlich daten, die in Exchange hochgeladen wurden, wenn Sie die Microsoft Exchange-Integration aktivieren).
    
    > [!NOTE]
    > Wenn Sie die Microsoft Exchange-Integration aktivieren, wird das Löschen für Benutzer, die in Exchange und mit ihren Postfächern im In-Place platziert sind, von Exchange gesteuert. Die einzige Ausnahme sind Konferenzdateien, die in der Lync Server-Dateifreigabe gespeichert sind. Diese Dateien werden erst aus der Dateifreigabe gelöscht, nachdem die Dateien exportiert (nach Exchange hochgeladen) wurden, wenn Sie die Option zum Löschen von Daten nach dem Exportieren der Archivierungsdaten oder nach der angegebenen maximalen Anzahl von Tagen auswählen, wenn Sie eine maximale Anzahl von Tagen für die Aufbewahrung angeben. 
  
Weitere Informationen zu den Archivierungsfunktionen, einschließlich der Exchange-Integration, finden Sie unter "Planen der Archivierung [in Skype for Business Server",](../../../plan-your-deployment/archiving/archiving.md)"Bereitstellen der Archivierung für Skype for Business [Server"](../../../deploy/deploy-archiving/deploy-archiving.md)und "Verwalten der Archivierung [in Skype for Business Server".](../../../manage/archiving/archiving.md)

