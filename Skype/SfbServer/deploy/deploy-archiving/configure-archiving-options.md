---
title: Konfigurieren von Archivierungsoptionen für Skype für Business Server
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 2f534697-ac7f-45b7-8cdc-ba67f052223b
description: 'Zusammenfassung: Lesen Sie in diesem Thema erfahren, wie die ursprüngliche Archivierungsoptionen für Skype für Business Server konfigurieren. Zunächst eingerichtet werden Archivierungskonfigurationen, wenn Sie die Archivierung bereitstellen, jedoch können Sie ändern, hinzufügen und Löschen von Konfigurationen nach der Bereitstellung.'
ms.openlocfilehash: 186ebae95c3d4d27ef634c0ca9ae1bc99bbfa253
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/24/2018
ms.locfileid: "21020414"
---
# <a name="configure-archiving-options-for-skype-for-business-server"></a>Konfigurieren von Archivierungsoptionen für Skype für Business Server
 
**Zusammenfassung:** Lesen Sie in diesem Thema erfahren, wie die ursprüngliche Archivierungsoptionen für Skype für Business Server konfigurieren. Zunächst eingerichtet werden Archivierungskonfigurationen, wenn Sie die Archivierung bereitstellen, jedoch können Sie ändern, hinzufügen und Löschen von Konfigurationen nach der Bereitstellung.
  
Konfiguration verwenden anfänglichen Archivierungskonfigurationen, Sie Skype Business Server-Systemsteuerung Folgendes an:
  
- Konfiguration auf globaler Ebene, die standardmäßig erstellt wird, bei der Bereitstellung von Skype für Business Server
    
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
  
Weitere Informationen dazu, wie Sie Archivierung Konfigurationen implementiert werden, einschließlich der Optionen, die Sie angeben können, und die Hierarchie der Archivierungskonfigurationen, finden Sie unter [Plan für die Archivierung in Skype für Business Server](../../plan-your-deployment/archiving/archiving.md). Ausführliche Informationen zum Verwalten von Konfigurationen nach der Bereitstellung mithilfe der Systemsteuerung oder mithilfe von Windows PowerShell, finden Sie unter [Archivierungsoptionen in Skype für Business Server verwalten](../../manage/archiving/options.md).
  
## <a name="configure-global-level-archiving-options"></a>Konfigurieren von Archivierungsoptionen auf globaler Ebene

Wenn Sie die Archivierung Ihrer Topologie hinzufügen und der Topologie veröffentlichen, erstellt Skype für Business Server eine globale Konfiguration für die Archivierung. Standardmäßig sind für die globale Konfiguration keine Archivierungsoptionen aktiviert. Die globale Konfiguration bestimmt, welche Optionen für Ihre gesamte Bereitstellung aktiviert werden, außer Sie richten Standort- oder Poolkonfigurationen ein, die die globale Konfiguration außer Kraft setzen.
  
So konfigurieren Sie Archivierungsoptionen auf globaler Ebene:
  
1. Melden Sie sich mit einem Benutzerkonto, dem die Rolle „CsArchivingAdministrator“ oder „CsAdministrator“ zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.
    
2. Öffnen Sie ein Browserfenster, und geben Sie die Admin-URL, um die Skype Business Server-Systemsteuerung zu öffnen. 
    
3. Klicken Sie auf der linken Navigationsleiste auf **Überwachung und Archivierung** und anschließend auf **Archivierungskonfiguration**.
    
4. Klicken Sie auf der Seite **Archivierungskonfiguration** auf **Global**, klicken Sie auf **Bearbeiten** und klicken Sie dann auf **Details einblenden**.
    
5. Wählen Sie unter **Archivierungseinstellung bearbeiten – Global** in der Dropdownliste **Archivierungseinstellung** eine der folgenden Archivierungsoptionen aus:
    
   - **Archivierung deaktivieren**
    
   - **Chatsitzungen archivieren**
    
   - **Chat- und Webkonferenzsitzungen archivieren**
    
6. Führen Sie auf der Seite **Archivierungseinstellung bearbeiten – Global** auch Folgendes:
    
   - Aktivieren Sie das Kontrollkästchen **Bei Archivierungsfehler Chat- oder Webkonferenzsitzungen blockieren**, um Aktivitäten zu blockieren, wenn die Archivierung nicht verfügbar ist.
    
   - Klicken Sie auf das Kontrollkästchen **Microsoft Exchange-Integration** , um die Verwendung von Microsoft Exchange Server zum Speichern von archivierten Daten.
    
   - Zum Aktivieren des Löschvorgangs für Daten aktivieren Sie das Kontrollkästchen **Bereinigungsfunktion für alle Archivierungsdaten aktivieren** und führen Sie einen der folgenden Schritte aus:
    
   - Klicken Sie auf **Löschen von exportierten und gespeicherten Archivierungsdaten nach einer Höchstdauer von (Tage)** und geben Sie eine Anzahl von Tagen an, um die archivierten Inhalte nach einer bestimmten Anzahl von Tagen zu löschen.
    
   - Klicken Sie auf **Nur exportierte Archivierungsdaten löschen**, um nur die exportierten Daten zu löschen.
    
7. Klicken Sie auf **Commit ausführen**.
    
## <a name="configure-site-level-archiving-options"></a>Konfigurieren von Archivierungsoptionen auf Standortebene

Sie können Archivierungsoptionen für einen bestimmten Standort festlegen. Eine Standortkonfiguration überschreibt die globale Konfiguration, aber nur für den in der Standortkonfiguration angegebenen Standort. 
  
1. Melden Sie sich mit einem Benutzerkonto, dem die Rolle „CsArchivingAdministrator“ oder „CsAdministrator“ zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.
    
2. Öffnen Sie ein Browserfenster, und geben Sie die Admin-URL, um die Skype Business Server-Systemsteuerung zu öffnen. 
    
3. Klicken Sie auf der linken Navigationsleiste auf **Überwachung und Archivierung** und anschließend auf **Archivierungskonfiguration**.
    
4. Klicken Sie auf der Seite **Archivierungskonfiguration** auf **Neu** und dann auf **Standortkonfiguration**.
    
5. Wählen Sie unter **Standort auswählen** den Standort aus, der für die Archivierung konfiguriert werden soll.
    
6. Führen Sie unter **Neue Archivierungseinstellung** im Dropdown-Listenfeld **Archivierungseinstellung** eine der folgenden Aktionen aus:
    
   - Klicken Sie auf **Chatsitzungen archivieren**, um die Archivierung ausschließlich für Chatsitzungen zu aktivieren.
    
   - Um sowohl Chatsitzungen als auch Konferenzen zu archivieren, klicken Sie auf **Chat- und Webkonferenzsitzungen archivieren**.
    
   - Klicken Sie auf **Archivierung deaktivieren**, um die Archivierung für die Richtlinie zu deaktivieren.
    
7. Führen Sie außerdem in **Neue Archivierungseinstellung** die folgenden Aktionen aus:
    
   - Aktivieren Sie das Kontrollkästchen **Bei Archivierungsfehler Chat- oder Webkonferenzsitzungen blockieren**, um Aktivitäten zu blockieren, wenn die Archivierung nicht verfügbar ist.
    
   - Klicken Sie auf das Kontrollkästchen **Microsoft Exchange-Integration** , um die Verwendung von Microsoft Exchange Server zum Speichern von archivierten Daten.
    
   - Zum Aktivieren des Löschvorgangs für Daten aktivieren Sie das Kontrollkästchen **Bereinigungsfunktion für alle Archivierungsdaten aktivieren** und führen Sie einen der folgenden Schritte aus:
    
   - Klicken Sie auf **Löschen von exportierten und gespeicherten Archivierungsdaten nach einer Höchstdauer von (Tage)** und geben Sie eine Anzahl von Tagen an, um die archivierten Inhalte nach einer bestimmten Anzahl von Tagen zu löschen.
    
   - Klicken Sie auf **Nur exportierte Archivierungsdaten löschen**, um nur die exportierten Daten zu löschen.
    
8. Klicken Sie auf **Commit ausführen**.
    
## <a name="configure-pool-level-archiving-options"></a>Konfigurieren von Archivierungsoptionen auf Poolebene

Sie können Archivierungsoptionen für einen bestimmten Pool festlegen. Eine Poolkonfiguration überschreibt die globale Konfiguration und die Standortkonfiguration, aber nur für den in der Poolkonfiguration angegebenen Pool.
  
1. Melden Sie sich mit einem Benutzerkonto, dem die Rolle „CsArchivingAdministrator“ oder „CsAdministrator“ zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.
    
2. Öffnen Sie ein Browserfenster, und geben Sie die Admin-URL, um die Skype Business Server-Systemsteuerung zu öffnen. 
    
3. Klicken Sie auf der linken Navigationsleiste auf **Überwachung und Archivierung** und anschließend auf **Archivierungskonfiguration**.
    
4. Klicken Sie auf der Seite **Archivierungskonfiguration** auf **Neu** und dann auf **Poolkonfiguration**.
    
5. Wählen Sie in **Dienst auswählen** den Pool aus, der für die Archivierung konfiguriert werden soll.
    
6. Wählen Sie unter **Neue Archivierungseinstellung** in der Dropdownliste **Archivierungseinstellung** eine der folgenden Archivierungseinstellungen aus:
    
   - **Archivierung deaktivieren**
    
   - **Chatsitzungen archivieren**
    
   - **Chat- und Webkonferenzsitzungen archivieren**
    
7. Führen Sie außerdem auf der Seite **Neue Archivierungseinstellung** die folgenden Schritte aus:
    
   - Aktivieren Sie das Kontrollkästchen **Bei Archivierungsfehler Chat- oder Webkonferenzsitzungen blockieren**, um Aktivitäten zu blockieren, wenn die Archivierung nicht verfügbar ist.
    
   - Klicken Sie auf das Kontrollkästchen **Microsoft Exchange-Integration** , um die Verwendung von Microsoft Exchange Server zum Speichern von archivierten Daten.
    
   - Zum Aktivieren des Löschvorgangs für Daten aktivieren Sie das Kontrollkästchen **Bereinigungsfunktion für alle Archivierungsdaten aktivieren** und führen Sie einen der folgenden Schritte aus:
    
   - Klicken Sie auf **Löschen von exportierten und gespeicherten Archivierungsdaten nach einer Höchstdauer von (Tage)** und geben Sie eine Anzahl von Tagen an, um die archivierten Inhalte nach einer bestimmten Anzahl von Tagen zu löschen.
    
   - Klicken Sie auf **Nur exportierte Archivierungsdaten löschen**, um nur die exportierten Daten zu löschen.
    
8. Klicken Sie auf **Commit ausführen**.
    

