---
title: Konfigurieren von Archivierungsoptionen für Skype for Business Server
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 2f534697-ac7f-45b7-8cdc-ba67f052223b
description: 'Zusammenfassung: Lesen Sie dieses Thema, um zu erfahren, wie Sie die anfänglichen Archivierungsoptionen für Skype for Business Server konfigurieren. Sie richten die Archivierungskonfigurationen zunächst ein, wenn Sie die Archivierung bereitstellen. Sie können konfigurationen jedoch nach der Bereitstellung ändern, hinzufügen und löschen.'
ms.openlocfilehash: b27a6bdd85b935b0751abf3da2bac94488234cdb
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/04/2021
ms.locfileid: "60749514"
---
# <a name="configure-archiving-options-for-skype-for-business-server"></a>Konfigurieren von Archivierungsoptionen für Skype for Business Server
 
**Zusammenfassung:** In diesem Thema erfahren Sie, wie Sie anfängliche Archivierungsoptionen für Skype for Business Server konfigurieren. Sie richten die Archivierungskonfigurationen zunächst ein, wenn Sie die Archivierung bereitstellen. Sie können konfigurationen jedoch nach der Bereitstellung ändern, hinzufügen und löschen.
  
Zum Konfigurieren der anfänglichen Archivierungskonfigurationen verwenden Sie Skype for Business Server Systemsteuerung, um Folgendes anzugeben:
  
- Konfiguration auf globaler Ebene, die standardmäßig erstellt wird, wenn Sie Skype for Business Server
    
- Optionale Konfigurationen auf Standortebene, die angeben, wie die Archivierung für einen bestimmten Standort implementiert wird
    
- Optionale Konfigurationen auf Poolebene, die angeben, wie die Archivierung für einen bestimmten Pool implementiert wird
    
Sie müssen Optionen für Folgendes konfigurieren:
  
- Aktivieren oder Deaktivieren der Archivierung
    
- Ob Chatsitzungen archiviert werden sollen
    
- Ob Webkonferenzsitzungen archiviert werden sollen
    
- Gibt an, ob Aktivitäten blockiert werden sollen, wenn die Archivierung nicht verfügbar ist.
    
- Ob Exchange Integration verwendet werden soll
    
- Einrichten des Löschens und Exportierens von Daten
    
> [!NOTE]
> Sie sollten alle geeigneten Optionen angeben, bevor Sie die Archivierung aktivieren. 
  
Ausführliche Informationen zur Implementierung von Archivierungskonfigurationen, einschließlich der Optionen, die Sie angeben können, und der Hierarchie der Archivierungskonfigurationen finden Sie unter [Plan for archiving in Skype for Business Server.](../../plan-your-deployment/archiving/archiving.md) Ausführliche Informationen zum Verwalten von Konfigurationen nach der Bereitstellung mithilfe der Systemsteuerung oder mithilfe von Windows PowerShell finden Sie unter [Verwalten von Archivierungsoptionen in Skype for Business Server.](../../manage/archiving/options.md)
  
## <a name="configure-global-level-archiving-options"></a>Konfigurieren von Archivierungsoptionen auf globaler Ebene

Wenn Sie Ihrer Topologie die Archivierung hinzufügen und die Topologie veröffentlichen, erstellt Skype for Business Server eine globale Konfiguration für die Archivierung. Standardmäßig sind in der globalen Konfiguration keine Archivierungsoptionen aktiviert. Die globale Konfiguration bestimmt, welche Optionen für Ihre gesamte Bereitstellung aktiviert werden, außer Sie richten Standort- oder Poolkonfigurationen ein, die die globale Konfiguration außer Kraft setzen.
  
So konfigurieren Sie Archivierungsoptionen auf globaler Ebene:
  
1. Melden Sie sich von einem Benutzerkonto, das der CsArchivingAdministrator- oder der CsAdministrator-Rolle zugeordnet ist, auf einem beliebigen Computer Ihrer internen Bereitstellung an.
    
2. Öffnen Sie ein Browserfenster, und geben Sie dann die Admin-URL ein, um die Skype for Business Server Systemsteuerung zu öffnen. 
    
3. Klicken Sie in der linken Navigationsleiste auf **Überwachung und Archivierung** und dann auf **Archivierungskonfiguration**.
    
4. Klicken Sie auf der Seite **Archivierungskonfiguration** auf **Global**, klicken Sie auf **Bearbeiten**, und klicken Sie dann auf **Details einblenden**.
    
5. Wählen Sie unter **Archivierungseinstellung bearbeiten – Global** in der Dropdownliste **Archivierungseinstellung** eine der folgenden Archivierungsoptionen aus:
    
   - **Archivierung deaktivieren**
    
   - **IM-Sitzungen archivieren**
    
   - **IM- und Webkonferenzsitzungen archivieren**
    
6. Führen Sie außerdem auf der Seite **"Archivierung bearbeiten** – Global" die folgenden Schritte aus:
    
   - Aktivieren Sie das Kontrollkästchen **Instant Messaging- oder Webkonferenzsitzungen bei Archivierungsfehlern blockieren**, um Aktivität zu blockieren, wenn die Archivierung nicht verfügbar ist.
    
   - Um Microsoft Exchange Server zum Speichern von Archivierungsdaten zu verwenden, klicken Sie auf das **Integrationskontrollkästchen von Microsoft Exchange.**
    
   - Zum Aktivieren des Löschvorgangs aktivieren Sie das Kontrollkästchen **Löschen von Archivierungsdaten aktivieren**, und führen Sie einen der folgenden Schritte aus:
    
   - Klicken Sie auf **Exportierte Archivierungsdaten und gespeicherte Archivierungsdaten löschen nach spätestens (Tage)**, und geben Sie eine Anzahl von Tagen an, um die archivierten Inhalte nach einer bestimmten Anzahl von Tagen zu löschen.
    
   - Klicken Sie auf **Nur exportierte Archivierungsdaten löschen**, um nur die exportierten Daten zu löschen.
    
7. Klicken Sie auf **Commit ausführen**.
    
## <a name="configure-site-level-archiving-options"></a>Konfigurieren von Archivierungsoptionen auf Standortebene

Sie können Archivierungsoptionen für einen bestimmten Standort angeben. Eine Standortkonfiguration setzt die globale Konfiguration außer Kraft, jedoch nur für den in der Standortkonfiguration angegebenen Standort. 
  
1. Melden Sie sich von einem Benutzerkonto, das der CsArchivingAdministrator- oder der CsAdministrator-Rolle zugeordnet ist, auf einem beliebigen Computer Ihrer internen Bereitstellung an.
    
2. Öffnen Sie ein Browserfenster, und geben Sie dann die Admin-URL ein, um die Skype for Business Server Systemsteuerung zu öffnen. 
    
3. Klicken Sie in der linken Navigationsleiste auf **Überwachung und Archivierung** und dann auf **Archivierungskonfiguration**.
    
4. Klicken Sie auf der Seite **Archivierungskonfiguration** auf **Neu** und dann auf **Standortkonfiguration**.
    
5. Wählen Sie unter **Standort auswählen** den Standort aus, der für die Archivierung konfiguriert werden soll.
    
6. Führen Sie unter **Neue Archivierungseinstellung** im Dropdown-Listenfeld **Archivierungseinstellung** eine der folgenden Aktionen aus:
    
   - Um nur Sofortnachrichtensitzungen zu archivieren, klicken Sie auf **Sofortnachrichtensitzungen archivieren**.
    
   - Klicken Sie auf **IM- und Webkonferenzsitzungen archivieren**, um sowohl IM-Sitzungen als auch Konferenzen zu archivieren.
    
   - Um die Archivierung für die Richtlinie zu deaktivieren, klicken Sie auf **Archivierung deaktivieren**.
    
7. Gehen Sie unter **Neue Archivierungseinstellung** wie folgt vor:
    
   - Aktivieren Sie das Kontrollkästchen **Instant Messaging- oder Webkonferenzsitzungen bei Archivierungsfehlern blockieren**, um die Aktivität zu blockieren, wenn die Archivierung nicht verfügbar ist.
    
   - Um Microsoft Exchange Server zum Speichern von Archivierungsdaten zu verwenden, klicken Sie auf das **Integrationskontrollkästchen von Microsoft Exchange.**
    
   - Zum Aktivieren des Löschvorgangs aktivieren Sie das Kontrollkästchen **Löschen von Archivierungsdaten aktivieren**, und führen Sie einen der folgenden Schritte aus:
    
   - Klicken Sie auf **Exportierte Archivierungsdaten und gespeicherte Archivierungsdaten löschen nach spätestens (Tage)**, und geben Sie eine Anzahl von Tagen an, um die archivierten Inhalte nach einer bestimmten Anzahl von Tagen zu löschen.
    
   - Klicken Sie auf **Nur exportierte Archivierungsdaten löschen**, um nur die exportierten Daten zu löschen.
    
8. Klicken Sie auf **Commit ausführen**.
    
## <a name="configure-pool-level-archiving-options"></a>Konfigurieren von Archivierungsoptionen auf Poolebene

Sie können Archivierungsoptionen für einen bestimmten Pool angeben. Eine Pool-Konfiguration überschreibt die globale Konfiguration und die Standortkonfiguration, jedoch nur für den in der Pool-Konfiguration angegebenen Pool.
  
1. Melden Sie sich von einem Benutzerkonto, das der CsArchivingAdministrator- oder der CsAdministrator-Rolle zugeordnet ist, auf einem beliebigen Computer Ihrer internen Bereitstellung an.
    
2. Öffnen Sie ein Browserfenster, und geben Sie dann die Admin-URL ein, um die Skype for Business Server Systemsteuerung zu öffnen. 
    
3. Klicken Sie in der linken Navigationsleiste auf **Überwachung und Archivierung** und dann auf **Archivierungskonfiguration**.
    
4. Klicken Sie auf der Seite **Archivierungskonfiguration** auf **Neu** und dann auf **Pool-Konfiguration**.
    
5. Wählen Sie in **Dienst auswählen** den Pool aus, der für die Archivierung konfiguriert werden soll.
    
6. Wählen Sie unter **Neue Archivierungseinstellung** in der Dropdownliste **Archivierungseinstellung** eine der folgenden Archivierungseinstellungen aus:
    
   - **Archivierung deaktivieren**
    
   - **IM-Sitzungen archivieren**
    
   - **IM- und Webkonferenzsitzungen archivieren**
    
7. Führen Sie außerdem auf der Seite **Neue Archivierungseinstellung** die folgenden Schritte aus:
    
   - Aktivieren Sie das Kontrollkästchen **Instant Messaging- oder Webkonferenzsitzungen bei Archivierungsfehlern blockieren**, um Aktivität zu blockieren, wenn die Archivierung nicht verfügbar ist.
    
   - Um Microsoft Exchange Server zum Speichern von Archivierungsdaten zu verwenden, klicken Sie auf das **Integrationskontrollkästchen von Microsoft Exchange.**
    
   - Zum Aktivieren des Löschvorgangs aktivieren Sie das Kontrollkästchen **Löschen von Archivierungsdaten aktivieren**, und führen Sie einen der folgenden Schritte aus:
    
   - Klicken Sie auf **Exportierte Archivierungsdaten und gespeicherte Archivierungsdaten löschen nach spätestens (Tage)**, und geben Sie eine Anzahl von Tagen an, um die archivierten Inhalte nach einer bestimmten Anzahl von Tagen zu löschen.
    
   - Klicken Sie auf **Nur exportierte Archivierungsdaten löschen**, um nur die exportierten Daten zu löschen.
    
8. Klicken Sie auf **Commit ausführen**.
    

