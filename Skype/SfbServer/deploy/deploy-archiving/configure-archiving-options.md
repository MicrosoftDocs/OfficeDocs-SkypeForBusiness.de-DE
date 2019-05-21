---
title: Konfigurieren von Archivierungsoptionen für Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 2f534697-ac7f-45b7-8cdc-ba67f052223b
description: 'Zusammenfassung: Lesen Sie dieses Thema, um zu erfahren, wie Sie die anfänglichen Archivierungsoptionen für Skype for Business Server konfigurieren. Sie haben zunächst Archivierungs Konfigurationen eingerichtet, wenn Sie die Archivierung bereitstellen, aber Sie können Konfigurationen nach der Bereitstellung ändern, hinzufügen und löschen.'
ms.openlocfilehash: 33438bb56c1ce55b0b449b9ee4124e27ae8638cc
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2019
ms.locfileid: "34286601"
---
# <a name="configure-archiving-options-for-skype-for-business-server"></a>Konfigurieren von Archivierungsoptionen für Skype for Business Server
 
**Zusammenfassung:** In diesem Thema erfahren Sie, wie Sie die anfänglichen Archivierungsoptionen für Skype for Business Server konfigurieren. Sie haben zunächst Archivierungs Konfigurationen eingerichtet, wenn Sie die Archivierung bereitstellen, aber Sie können Konfigurationen nach der Bereitstellung ändern, hinzufügen und löschen.
  
Zum Konfigurieren der anfänglichen Archivierungs Konfigurationen verwenden Sie die Skype for Business Server-Systemsteuerung, um Folgendes anzugeben:
  
- Konfiguration auf globaler Ebene, die standardmäßig bei der Bereitstellung von Skype for Business Server erstellt wird
    
- Optionale Konfigurationen auf Standortebene, um anzugeben, wie die Archivierung für einen bestimmten Standort implementiert wird
    
- Optionale Konfigurationen auf Poolebene, die angeben, wie die Archivierung für einen bestimmten Pool implementiert wird
    
Sie müssen Optionen für Folgendes konfigurieren:
  
- Ob die Archivierung aktiviert oder deaktiviert werden soll
    
- Ob Chatsitzungen archiviert werden sollen
    
- Ob Webkonferenzsitzungen archiviert werden sollen
    
- Ob Aktivitäten blockiert werden sollen, wenn die Archivierung nicht verfügbar ist
    
- Ob die Exchange-Integration verwendet werden soll
    
- Wie das Bereinigen und Exportieren von Daten eingerichtet werden soll
    
> [!NOTE]
> Sie sollten alle entsprechenden Optionen angeben, bevor Sie die Archivierung aktivieren. 
  
Einzelheiten zur Implementierung von Archivierungs Konfigurationen, einschließlich der Optionen, die Sie angeben können, und der Hierarchie der Archivierungs Konfigurationen finden Sie unter [Planen der Archivierung in Skype for Business Server](../../plan-your-deployment/archiving/archiving.md). Details zum Verwalten von Konfigurationen nach der Bereitstellung mithilfe der Systemsteuerung oder mithilfe von Windows PowerShell finden Sie unter [Verwalten von Archivierungsoptionen in Skype for Business Server](../../manage/archiving/options.md).
  
## <a name="configure-global-level-archiving-options"></a>Konfigurieren von Archivierungsoptionen auf globaler Ebene

Wenn Sie Ihrer Topologie Archivierungsvorgänge hinzufügen und die Topologie veröffentlichen, erstellt Skype for Business Server eine globale Konfiguration für die Archivierung. Standardmäßig sind für die globale Konfiguration keine Archivierungsoptionen aktiviert. Die globale Konfiguration bestimmt, welche Optionen für Ihre gesamte Bereitstellung aktiviert werden, außer Sie richten Standort- oder Poolkonfigurationen ein, die die globale Konfiguration außer Kraft setzen.
  
So konfigurieren Sie Archivierungsoptionen auf globaler Ebene:
  
1. Melden Sie sich mit einem Benutzerkonto, dem die Rolle "CsArchivingAdministrator" oder "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.
    
2. Öffnen Sie ein Browserfenster, und geben Sie dann die Administrator-URL ein, um das Skype for Business Server Control Panel zu öffnen. 
    
3. Klicken Sie auf der linken Navigationsleiste auf **Überwachung und Archivierung** und anschließend auf **Archivierungskonfiguration**.
    
4. Klicken Sie auf der Seite **Archivierungskonfiguration** auf **Global**, klicken Sie auf **Bearbeiten** und klicken Sie dann auf **Details einblenden**.
    
5. Wählen Sie unter **Archivierungseinstellung bearbeiten – Global** in der Dropdownliste **Archivierungseinstellung** eine der folgenden Archivierungsoptionen aus:
    
   - **Archivierung deaktivieren**
    
   - **Chatsitzungen archivieren**
    
   - **Chat- und Webkonferenzsitzungen archivieren**
    
6. Gehen Sie auch auf der Seite **Archivierungseinstellungen bearbeiten – Global** wie folgt vor:
    
   - Aktivieren Sie das Kontrollkästchen **Bei Archivierungsfehler Chat- oder Webkonferenzsitzungen blockieren**, um Aktivitäten zu blockieren, wenn die Archivierung nicht verfügbar ist.
    
   - Wenn Sie Microsoft Exchange Server zum Speichern von Archivierungsdaten verwenden möchten, klicken Sie auf das Kontrollkästchen **Microsoft Exchange-Integration** .
    
   - Zum Aktivieren des Löschvorgangs für Daten aktivieren Sie das Kontrollkästchen **Bereinigungsfunktion für alle Archivierungsdaten aktivieren** und führen Sie einen der folgenden Schritte aus:
    
   - Klicken Sie auf **Löschen von exportierten und gespeicherten Archivierungsdaten nach einer Höchstdauer von (Tage)** und geben Sie eine Anzahl von Tagen an, um die archivierten Inhalte nach einer bestimmten Anzahl von Tagen zu löschen.
    
   - Klicken Sie auf **Nur exportierte Archivierungsdaten löschen**, um nur die exportierten Daten zu löschen.
    
7. Klicken Sie auf **Commit ausführen**.
    
## <a name="configure-site-level-archiving-options"></a>Konfigurieren von Archivierungsoptionen auf Standortebene

Sie können Archivierungsoptionen für einen bestimmten Standort festlegen. Eine Standortkonfiguration überschreibt die globale Konfiguration, aber nur für den in der Standortkonfiguration angegebenen Standort. 
  
1. Melden Sie sich mit einem Benutzerkonto, dem die Rolle "CsArchivingAdministrator" oder "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.
    
2. Öffnen Sie ein Browserfenster, und geben Sie dann die Administrator-URL ein, um das Skype for Business Server Control Panel zu öffnen. 
    
3. Klicken Sie auf der linken Navigationsleiste auf **Überwachung und Archivierung** und anschließend auf **Archivierungskonfiguration**.
    
4. Klicken Sie auf der Seite **Archivierungskonfiguration** auf **Neu** und dann auf **Standortkonfiguration**.
    
5. Wählen Sie unter **Standort auswählen** den Standort aus, der für die Archivierung konfiguriert werden soll.
    
6. Führen Sie unter **Neue Archivierungseinstellung** im Dropdown-Listenfeld **Archivierungseinstellung** eine der folgenden Aktionen aus:
    
   - Klicken Sie auf **Chatsitzungen archivieren**, um die Archivierung ausschließlich für Chatsitzungen zu aktivieren.
    
   - Um sowohl Chatsitzungen als auch Konferenzen zu archivieren, klicken Sie auf **Chat- und Webkonferenzsitzungen archivieren**.
    
   - Klicken Sie auf **Archivierung deaktivieren**, um die Archivierung für die Richtlinie zu deaktivieren.
    
7. Führen Sie außerdem in **Neue Archivierungseinstellung** die folgenden Aktionen aus:
    
   - Aktivieren Sie das Kontrollkästchen **Bei Archivierungsfehler Chat- oder Webkonferenzsitzungen blockieren**, um Aktivitäten zu blockieren, wenn die Archivierung nicht verfügbar ist.
    
   - Wenn Sie Microsoft Exchange Server zum Speichern von Archivierungsdaten verwenden möchten, klicken Sie auf das Kontrollkästchen **Microsoft Exchange-Integration** .
    
   - Zum Aktivieren des Löschvorgangs für Daten aktivieren Sie das Kontrollkästchen **Bereinigungsfunktion für alle Archivierungsdaten aktivieren** und führen Sie einen der folgenden Schritte aus:
    
   - Klicken Sie auf **Löschen von exportierten und gespeicherten Archivierungsdaten nach einer Höchstdauer von (Tage)** und geben Sie eine Anzahl von Tagen an, um die archivierten Inhalte nach einer bestimmten Anzahl von Tagen zu löschen.
    
   - Klicken Sie auf **Nur exportierte Archivierungsdaten löschen**, um nur die exportierten Daten zu löschen.
    
8. Klicken Sie auf **Commit ausführen**.
    
## <a name="configure-pool-level-archiving-options"></a>Konfigurieren von Archivierungsoptionen auf Poolebene

Sie können Archivierungsoptionen für einen bestimmten Pool festlegen. Eine Poolkonfiguration überschreibt die globale Konfiguration und die Standortkonfiguration, aber nur für den in der Poolkonfiguration angegebenen Pool.
  
1. Melden Sie sich mit einem Benutzerkonto, dem die Rolle „CsArchivingAdministrator“ oder „CsAdministrator“ zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.
    
2. Öffnen Sie ein Browserfenster, und geben Sie dann die Administrator-URL ein, um das Skype for Business Server Control Panel zu öffnen. 
    
3. Klicken Sie auf der linken Navigationsleiste auf **Überwachung und Archivierung** und anschließend auf **Archivierungskonfiguration**.
    
4. Klicken Sie auf der Seite **Archivierungskonfiguration** auf **Neu** und dann auf **Poolkonfiguration**.
    
5. Wählen Sie in **Dienst auswählen** den Pool aus, der für die Archivierung konfiguriert werden soll.
    
6. Wählen Sie unter **Neue Archivierungseinstellung** in der Dropdownliste **Archivierungseinstellung** eine der folgenden Archivierungseinstellungen aus:
    
   - **Archivierung deaktivieren**
    
   - **Chatsitzungen archivieren**
    
   - **Chat- und Webkonferenzsitzungen archivieren**
    
7. Führen Sie außerdem auf der Seite **Neue Archivierungseinstellung** die folgenden Schritte aus:
    
   - Aktivieren Sie das Kontrollkästchen **Bei Archivierungsfehler Chat- oder Webkonferenzsitzungen blockieren**, um Aktivitäten zu blockieren, wenn die Archivierung nicht verfügbar ist.
    
   - Wenn Sie Microsoft Exchange Server zum Speichern von Archivierungsdaten verwenden möchten, klicken Sie auf das Kontrollkästchen **Microsoft Exchange-Integration** .
    
   - Zum Aktivieren des Löschvorgangs für Daten aktivieren Sie das Kontrollkästchen **Bereinigungsfunktion für alle Archivierungsdaten aktivieren** und führen Sie einen der folgenden Schritte aus:
    
   - Klicken Sie auf **Löschen von exportierten und gespeicherten Archivierungsdaten nach einer Höchstdauer von (Tage)** und geben Sie eine Anzahl von Tagen an, um die archivierten Inhalte nach einer bestimmten Anzahl von Tagen zu löschen.
    
   - Klicken Sie auf **Nur exportierte Archivierungsdaten löschen**, um nur die exportierten Daten zu löschen.
    
8. Klicken Sie auf **Commit ausführen**.
    

