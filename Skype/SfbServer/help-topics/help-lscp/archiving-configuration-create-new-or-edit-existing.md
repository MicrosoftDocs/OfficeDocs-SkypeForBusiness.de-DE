---
title: Archivierungskonfiguration neues erstellen oder vorhandenes bearbeiten
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/27/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.lscp.MonArchSettingEdit
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 49096960-c442-4846-be8f-03c167acea41
description: 'Verwenden Sie Archivierungskonfigurationen zum Steuern der Archivierungsoptionen für Ihre Bereitstellung. Zu den Archivierungskonfigurationen gehören die globale Konfiguration und optional eine oder mehrere Poolkonfigurationen:'
ms.openlocfilehash: af8819d44fb510a0addb460dc98b4d18bdbfd88c
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2020
ms.locfileid: "41823218"
---
# <a name="archiving-configuration-create-new-or-edit-existing"></a>Archivierungskonfiguration: Erstellen einer neuen oder Bearbeiten einer vorhandenen Archivierungskonfiguration
 
Verwenden Sie Archivierungskonfigurationen zum Steuern der Archivierungsoptionen für Ihre Bereitstellung. Zu den Archivierungskonfigurationen gehören die globale Konfiguration und optional eine oder mehrere Poolkonfigurationen:
  
- **Globale Konfiguration** Die globale Konfiguration wird standardmäßig erstellt. Sie können die globale Konfiguration bearbeiten, aber Sie können diese Archivierungskonfiguration nicht löschen. Wenn Sie versuchen, sie zu löschen, werden alle Optionen auf die Standardwerte zurückgesetzt.
    
- **Websitekonfiguration (optional)** Sie können eine oder mehrere Website Archivierungs Konfigurationen angeben, die jeweils für die Steuerung der Archivierungsoptionen für eine bestimmte Website konfiguriert werden können. Eine Standortkonfiguration setzt die globale Konfiguration außer Kraft, jedoch nur für die in den Archivierungsstandortkonfigurationen angegebenen Standorte. Sie können Standortkonfigurationen bearbeiten oder löschen.
    
- **Pool Konfiguration (optional)** Sie können eine oder mehrere Pool Archivierungs Konfigurationen angeben, um Archivierungsoptionen für einen bestimmten Pool zu steuern. Eine Poolkonfiguration setzt die globale Konfiguration und die Standortkonfiguration außer Kraft, jedoch nur für die in den Archivierungspoolkonfigurationen angegebenen Pools. Sie können Poolkonfigurationen bearbeiten oder löschen.
    
> [!NOTE]
> Archivierungs Konfigurationen gelten für Benutzer, die sich in Skype for Business Server befinden, und, wenn Sie die Microsoft Exchange-Integrations Option aktivieren, um Exchange 2013 zum Speichern von Archivierungsdaten in Microsoft Exchange zu verwenden, für Benutzer, die in Exchange 2013 verwaltet werden. Einige Optionen werden allerdings für Benutzer, die in Exchange 2013 verwaltet werden, etwas anders implementiert, wie im nächsten Abschnitt beschrieben. 
  
Geben Sie die folgenden Optionen an, um die Einstellungen für eine neue oder vorhandene Archivierungskonfiguration zu konfigurieren:
- **Name** Für jede Archivierungskonfiguration ist ein Name erforderlich. Der Name wird anhand des Typs der Konfiguration bestimmt, die Sie hinzufügen oder bearbeiten:
    
  - **Globale Konfiguration** Der Standardname lautet Global. Ein Beispielname ist „Contoso North American Organization“.
    
  - **Websitekonfiguration** Die Liste enthält die verfügbaren Websites in Ihrer Bereitstellung. Klicken Sie auf eine einzelne Website, um Sie auszuwählen. Beispiel: Redmond-Rechenzentrum.
    
  - **Pool Konfiguration** Geben Sie einen geeigneten Namen an, bei dem es sich um den Namen eines bestimmten Front-End-Pools oder eines Standard Edition-Servers in Ihrer Bereitstellung handeln kann. Dies kann der Name eines bestimmten Front-End-Pools oder Standard Edition-Servers der Bereitstellung sein, beispielsweise „Marketingabteilung“.
    
- **Beschreibung** Dies ist optional. Verwenden Sie diese Option zum Angeben weiterer Details wie Umfang oder Zweck der Konfiguration. Beispiel: „Koordination mit Rechtsabteilungen anderer Standorte“.
    
- **Archivierungseinstellung** Die folgenden Optionen sind verfügbar:
    
  - **Chatsitzungen archivieren**
    
  - **Chat- und Webkonferenzsitzungen archivieren**
    
  - **Archivierung deaktivieren**
    
- **Blockieren von Sofortnachrichten (im) oder Webkonferenz Sitzungen, wenn die Archivierung fehlschlägt** Zu den Fehlern gehören die folgenden:
    
  - Bei einem Fehler kann es sich um eine vollständige Datenbank oder **um ein Problem** mit dem Speicherdienst handeln. In diesem Fall ist der Chat für Benutzer blockiert, die für die Archivierung aktiviert sind.
    
  - **Konferenzen** Bei einem Fehler kann es sich um eine nicht verfügbare Dateifreigabe oder um ein Problem mit dem Speicherdienst handeln. In diesem Fall werden aktive Konferenzen, die beim Auftreten des Fehlers im Pool gehostet werden, in den eingeschränkten Modus umgeschaltet und neue Konferenzen können nicht aktiviert werden.
    
    Chatnachrichten und Konferenzen werden nach dem Beheben des Fehlers automatisch wiederhergestellt.
    
- **Microsoft Exchange-Integration** Wählen Sie diese Option aus, wenn Sie über Benutzer verfügen, die in Exchange 2013 verwaltet werden. Mit dieser Option wird Exchange 2013 verwendet, um Daten für diese Benutzer zu speichern, wenn ihre Postfächer im in-situ-Speicher platziert wurden. Wenn alle Ihre Benutzer in Exchange 2013 verwaltet werden, müssen Sie keine separaten SQL Server-Datenbanken für die Speicherung von Archivierungsdaten einrichten.
    
- **Aktivieren des Bereinigens von Archivierungsdaten** Wählen Sie diese Option aus, um das Bereinigen zu aktivieren und Bereinigungsoptionen anzugeben, die Folgendes umfassen:
    
  - Bereinigung nach einer von Ihnen angegebenen Anzahl von Tagen
    
  - Bereinigen nach dem Exportieren der Archivierungsdaten (einschließlich der Daten, die in Exchange hochgeladen wurden, wenn Sie die Microsoft Exchange-Integration aktivieren)
    
    > [!NOTE]
    > Wenn Sie die Microsoft Exchange-Integration aktivieren, wird das Bereinigen für Benutzer, die sich in Exchange 2013 befinden, und deren Postfächer, die in-situ-Speicher platziert werden, von Exchange gesteuert. Die einzige Ausnahme ist für Konferenz Dateien, die auf der lync Server-Dateifreigabe gespeichert sind. Diese Dateien werden von der Dateifreigabe nur bereinigt, nachdem die Dateien exportiert (in Exchange hochgeladen) wurden, wenn Sie die Option zum Löschen von Daten nach dem Exportieren der Archivierungsdaten oder nach der angegebenen maximalen Anzahl von Tagen auswählen, wenn Sie eine maximale Anzahl von Tagen angeben. Tage für die Aufbewahrung. 
  
Details zum Archivierungsfeature und zu den Funktionen, einschließlich der Exchange-Integration, finden Sie unter [Planen der Archivierung in Skype for Business Server 2015](../../plan-your-deployment/archiving/archiving.md), [Bereitstellen der Archivierung für Skype for Business Server 2015](../../deploy/deploy-archiving/deploy-archiving.md)und [Verwalten der Archivierung in Skype for Business Server 2015](../../manage/archiving/archiving.md).

