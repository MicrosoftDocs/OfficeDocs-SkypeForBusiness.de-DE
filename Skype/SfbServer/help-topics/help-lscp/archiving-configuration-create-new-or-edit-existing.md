---
title: Archivierungskonfiguration Erstellen einer neuen oder Bearbeiten einer vorhandenen
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/27/2015
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.MonArchSettingEdit
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 49096960-c442-4846-be8f-03c167acea41
description: 'Verwenden Sie Archivierungskonfigurationen zum Steuern der Archivierungsoptionen für Ihre Bereitstellung. Zu den Archivierungskonfigurationen gehören die globale Konfiguration und optional eine oder mehrere Poolkonfigurationen:'
ms.openlocfilehash: d9c1d63b01afd472850a0c311ab8a001c1c80b95
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "33887209"
---
# <a name="archiving-configuration-create-new-or-edit-existing"></a>Archivierungskonfiguration: Erstellen einer neuen oder Bearbeiten einer vorhandenen Archivierungskonfiguration
 
Verwenden Sie Archivierungskonfigurationen zum Steuern der Archivierungsoptionen für Ihre Bereitstellung. Zu den Archivierungskonfigurationen gehören die globale Konfiguration und optional eine oder mehrere Poolkonfigurationen:
  
- **Globale Konfiguration** Standardmäßig wird die globale Konfiguration erstellt. Sie können die globale Konfiguration bearbeiten, aber Sie können diese Archivierungskonfiguration nicht löschen. Wenn Sie versuchen, sie zu löschen, werden alle Optionen auf die Standardwerte zurückgesetzt.
    
- **Standortkonfiguration (optional)** Sie können eine oder mehrere Website Archivierungskonfigurationen angeben, von denen jedes Steuerelement Archivierungsoptionen für einen bestimmten Standort konfigurierbaren. Eine Standortkonfiguration setzt die globale Konfiguration außer Kraft, jedoch nur für die in den Archivierungsstandortkonfigurationen angegebenen Standorte. Sie können Standortkonfigurationen bearbeiten oder löschen.
    
- **Pool-Konfiguration (optional)** Sie können eine oder mehrere Pools Archivierungskonfigurationen, Kontrolle Archivierungsoptionen für einen bestimmten Pool angeben. Eine Poolkonfiguration setzt die globale Konfiguration und die Standortkonfiguration außer Kraft, jedoch nur für die in den Archivierungspoolkonfigurationen angegebenen Pools. Sie können Poolkonfigurationen bearbeiten oder löschen.
    
> [!NOTE]
> Archivierung Konfigurationen gelten für Benutzer, die auf Skype für Business Server verwaltet und, wenn Sie die Option Microsoft Exchange-Integration aktivieren mit Exchange 2013 zum Speichern von archivierten Datenteils in Microsoft Exchange, Benutzern, die sich in Exchange 2013. Allerdings werden einige Optionen etwas unterschiedlich implementiert für Benutzer in Exchange 2013, verwaltet wie im nächsten Abschnitt beschrieben. 
  
Geben Sie die folgenden Optionen an, um die Einstellungen für eine neue oder vorhandene Archivierungskonfiguration zu konfigurieren:
- **Name** Jede Archivierungskonfiguration erfordert einen Namen an. Der Name wird anhand des Typs der Konfiguration bestimmt, die Sie hinzufügen oder bearbeiten:
    
  - **Globale Konfiguration** Der Standardname ist Global. Ein Beispielname ist „Contoso North American Organization“.
    
  - **Standortkonfiguration** Die Liste enthält die verfügbaren Standorte in Ihrer Bereitstellung. Klicken Sie auf eine einzelne Website, um ihn auszuwählen. Beispielsweise Redmond-Rechenzentrum.
    
  - **Pool-Konfiguration** Geben Sie einen geeigneten Namen, der den Namen des einem bestimmten Front-End-Pool oder Standard Edition-Server in Ihrer Bereitstellung sein kann. Dies kann der Name eines bestimmten Front-End-Pools oder Standard Edition-Servers der Bereitstellung sein, beispielsweise „Marketingabteilung“.
    
- **Beschreibung** Dieser Schritt ist optional. Verwenden Sie diese Option zum Angeben weiterer Details wie Umfang oder Zweck der Konfiguration. Beispiel: „Koordination mit Rechtsabteilungen anderer Standorte“.
    
- **Archivierungseinstellung** Die folgenden: Optionen
    
  - **Chatsitzungen archivieren**
    
  - **Chat- und Webkonferenzsitzungen archivieren**
    
  - **Archivierung deaktivieren**
    
- **Block instant messaging (IM) oder webkonferenzsitzungen bei Archivierungsfehlern** Die folgenden: Fehler
    
  - **Sofortnachrichten** ein Fehler kann eine vollständige Datenbank oder ein Problem mit der Speicherdienst handeln. In diesem Fall ist der Chat für Benutzer blockiert, die für die Archivierung aktiviert sind.
    
  - **Live Meeting** Ein Fehler kann eine Dateifreigabe nicht verfügbar oder ein Problem mit der Speicherdienst handeln. In diesem Fall werden aktive Konferenzen, die beim Auftreten des Fehlers im Pool gehostet werden, in den eingeschränkten Modus umgeschaltet und neue Konferenzen können nicht aktiviert werden.
    
    Chatnachrichten und Konferenzen werden nach dem Beheben des Fehlers automatisch wiederhergestellt.
    
- **Microsoft Exchange-integration** Wählen Sie diese Option, wenn Benutzer vorhanden sind, der in Exchange 2013 verwaltet werden. Mit dieser Option wird Exchange 2013 zum Speichern von Daten für diese Benutzer verwendet, wenn ihre Postfächer Compliance-Archiv abgelegt wurden. Wenn alle Benutzer auf Exchange 2013 befinden, müssen Sie keine separaten SQL Server-Datenbanken für die Speicherung von Archivierungsdaten einrichten.
    
- **Aktivieren des Löschvorgangs archivierten Daten** Wählen Sie diese Option Aktivieren des Löschvorgangs und Entfernen von Optionen, die folgenden angeben:
    
  - Bereinigung nach einer von Ihnen angegebenen Anzahl von Tagen
    
  - Bereinigung nach archivierten Daten exportieren von Archivierungsdaten (einschließlich der Daten, die in Exchange hochgeladen wurde, wenn Sie Microsoft Exchange-Integration aktivieren).
    
    > [!NOTE]
    > Wenn Sie Microsoft Exchange-Integration aktivieren, Bereinigung für Benutzer, die in Exchange 2013 verwaltet und mit ihren Postfächern, bei denen In-Place Hold von Exchange gesteuert. Die einzige Ausnahme ist für Konferenzen-Dateien, die in der Lync Server-Dateifreigabe gespeichert sind. Diese Dateien werden von der Dateifreigabe, nachdem die Dateien (hochgeladenen zu Exchange) exportiert worden sind, wenn Sie die Option aus, um Daten zu löschen, nach dem Exportieren der archivierten Daten auswählen oder die angegebene maximale Anzahl von Tagen, gelöscht, wenn Sie eine maximale Anzahl von angeben Tage für die Aufbewahrung. 
  
Weitere Informationen über die Archivierungsfunktion und Funktionen, einschließlich Exchange-Integration finden Sie unter [Planen für die Archivierung in Skype für Business Server 2015](../../plan-your-deployment/archiving/archiving.md), [Archivierung für Skype für Business Server 2015 bereitstellen](../../deploy/deploy-archiving/deploy-archiving.md)und verwalten [Archivierung in Skype für Business Server 2015](../../manage/archiving/archiving.md).

