---
title: Archivierungskonfiguration – Erstellen einer neuen oder Bearbeiten einer vorhandenen Archivierungskonfiguration
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
- ms.lync.lscp.MonArchSettingEdit
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: 49096960-c442-4846-be8f-03c167acea41
description: 'Sie verwenden Archivierungskonfigurationen, um die Archivierungsoptionen für Ihre Bereitstellung zu steuern. Zu den Archivierungskonfigurationen gehören die globale Konfiguration und optional eine oder mehrere Poolkonfigurationen:'
ms.openlocfilehash: 411f9622706faa3388d611b3ae50a14fce739ff3
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/26/2021
ms.locfileid: "58596909"
---
# <a name="archiving-configuration-create-new-or-edit-existing"></a>Archivierungskonfiguration: Erstellen einer neuen oder Bearbeiten einer vorhandenen Archivierungskonfiguration
 
Sie verwenden Archivierungskonfigurationen, um die Archivierungsoptionen für Ihre Bereitstellung zu steuern. Zu den Archivierungskonfigurationen gehören die globale Konfiguration und optional eine oder mehrere Poolkonfigurationen:
  
- **Globale Konfiguration** Die globale Konfiguration wird standardmäßig erstellt. Sie können die globale Konfiguration bearbeiten, aber Sie können diese Archivierungskonfiguration nicht löschen. Wenn Sie versuchen, das Löschen durchzuführen, werden alle Optionen auf die Standardwerte zurückgesetzt.
    
- **Standortkonfiguration (optional)** Sie können eine oder mehrere Archivierungskonfigurationen für Standorte angeben, die Sie jeweils zum Steuern der Archivierungsoptionen für einen bestimmten Standort konfigurieren können. Eine Standortkonfiguration setzt die globale Konfiguration außer Kraft, jedoch nur für die in den Archivierungsstandortkonfigurationen angegebenen Standorte. Sie können Standortkonfigurationen bearbeiten oder löschen.
    
- **Poolkonfiguration (optional)** Sie können eine oder mehrere Archivierungskonfigurationen des Pools angeben, um die Archivierungsoptionen für einen bestimmten Pool zu steuern. Eine Poolkonfiguration setzt die globale Konfiguration und Standortkonfiguration außer Kraft, jedoch nur für die in den Archivierungspoolkonfigurationen angegebenen Pools. Sie können Poolkonfigurationen bearbeiten oder löschen.
    
> [!NOTE]
> Archivierungskonfigurationen gelten für Benutzer, die auf Skype for Business Server verwaltet werden, und, wenn Sie die Integrationsoption "Microsoft Exchange" aktivieren, um Exchange 2013 zum Speichern von Archivierungsdaten in Microsoft Exchange zu verwenden, für Benutzer, die am Exchange 2013 verwaltet werden. Einige Optionen werden jedoch für Benutzer, die auf Exchange 2013 verwaltet werden, geringfügig anders implementiert, wie im nächsten Abschnitt beschrieben. 
  
Geben Sie die folgenden Optionen an, um die Einstellungen für eine neue oder vorhandene Archivierungskonfiguration zu konfigurieren:
- **Name** Jede Archivierungskonfiguration erfordert einen Namen. Der Name wird anhand des Typs der Konfiguration bestimmt, die Sie hinzufügen oder bearbeiten:
    
  - **Globale Konfiguration** Der Standardname lautet "Global". Beispiel: Contoso North American Organization.
    
  - **Standortkonfiguration** Die Liste enthält die verfügbaren Websites in Ihrer Bereitstellung. Klicken Sie auf eine einzelne Website, um sie auszuwählen. Beispiel: Redmond Data Center.
    
  - **Poolkonfiguration** Geben Sie einen geeigneten Namen an, der dem Namen eines bestimmten Front-End-Pools oder Standard Edition Servers in Ihrer Bereitstellung entsprechen kann. Dies kann der Name eines bestimmten Front-End-Pools oder Standard Edition-Servers der Bereitstellung sein, beispielsweise "Marketingabteilung".
    
- **Beschreibung** Dies ist optional. Verwenden Sie diese Option zum Angeben weiterer Details wie Umfang oder Zweck der Konfiguration. Beispiel: "Koordination mit Rechtsabteilungen anderer Standorte".
    
- **Archivierungseinstellung** Folgende Optionen sind verfügbar:
    
  - **IM-Sitzungen archivieren**
    
  - **Chat- und Webkonferenzsitzungen archivieren**
    
  - **Archivierung deaktivieren**
    
- **Blockieren von Chat- oder Webkonferenzsitzungen bei Archivierungsfehlern** Fehler umfassen Folgendes:
    
  - **Ein** Fehler beim Chat kann eine vollständige Datenbank oder ein Problem mit dem Speicherdienst sein. In diesem Fall werden Sofortnachrichten für Benutzer blockiert, für die die Archivierung aktiviert wurde.
    
  - **Konferenzen** Ein Fehler kann eine nicht verfügbare Dateifreigabe oder ein Problem mit dem Speicherdienst sein. In diesem Fall werden aktiven Konferenzen, die beim Auftreten des Fehlers im Pool gehostet werden, in den eingeschränkten Modus umgeschaltet, und neue Konferenzen können nicht aktiviert werden.
    
    Sofortnachrichten und Konferenzen werden nach dem Beheben des Fehlers automatisch wiederhergestellt.
    
- **Integration von Microsoft Exchange** Wählen Sie diese Option aus, wenn Sie Benutzer haben, die am Exchange 2013 verwaltet werden. Mit dieser Option wird Exchange 2013 verwendet, um Daten für diese Benutzer zu speichern, wenn ihre Postfächer in In-Place Haltebereich gesetzt wurden. Wenn alle Ihre Benutzer am Exchange 2013 verwaltet werden, müssen Sie keine separaten SQL Server Datenbanken für die Speicherung von Archivierungsdaten einrichten.
    
- **Aktivieren des Löschens von Archivierungsdaten** Wählen Sie diese Option aus, um das Löschen zu aktivieren und Bereinigungsoptionen anzugeben, die Folgendes enthalten:
    
  - Bereinigung nach einer von Ihnen angegebenen Anzahl von Tagen
    
  - Löschen, nachdem die Archivierungsdaten exportiert wurden (einschließlich Daten, die in Exchange hochgeladen wurden, wenn Sie microsoft Exchange Integration aktivieren).
    
    > [!NOTE]
    > Wenn Sie die Integration von Microsoft Exchange aktivieren, wird die Bereinigung für Benutzer, die auf Exchange 2013 verwaltet werden, und deren Postfächer in In-Place Haltebereich gesetzt sind, durch Exchange gesteuert. Die einzige Ausnahme sind Konferenzdateien, die in der Lync Server-Dateifreigabe gespeichert sind. Diese Dateien werden erst aus der Dateifreigabe gelöscht, nachdem die Dateien exportiert (in Exchange hochgeladen) wurden, wenn Sie die Option zum Löschen von Daten auswählen, nachdem die Archivierungsdaten exportiert wurden, oder nach der angegebenen maximalen Anzahl von Tagen, wenn Sie eine maximale Anzahl von Tagen für die Aufbewahrung angeben. 
  
Ausführliche Informationen zu den Archivierungsfeatures und -funktionen, einschließlich Exchange Integration, finden Sie unter [Plan for archiving in Skype for Business Server 2015,](../../plan-your-deployment/archiving/archiving.md)Deploy archiving for Skype for Business Server [2015,](../../deploy/deploy-archiving/deploy-archiving.md)and [Manage archiving in Skype for Business Server 2015.](../../manage/archiving/archiving.md)

