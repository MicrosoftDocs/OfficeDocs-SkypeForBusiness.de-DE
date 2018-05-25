---
title: Hinzufügen des SQL Server-Konformitätssicherungsspeichers für den beständigen Chat
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/27/2015
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddPersistentChatBackupComplianceStorePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 358b74bd-a97d-4f28-9bed-af633ea0099e
description: Sie konfigurieren die Sicherung Compliance, den SQL Server-Speicher, die Sicherungsdatenbanken für Persistent Chat-Server bereitstellen oder Persistent Chat Server Compliance, den SQL Server-Speicher.
ms.openlocfilehash: 4e3a2bf034d5ab20c7352f2b6ef9c8a6a0c4befa
ms.sourcegitcommit: e577b4bdf3827fdfaf4482928adde177a64e4406
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/24/2018
---
# <a name="add-persistent-chat-compliance-backup-sql-server-store"></a>Hinzufügen des SQL Server-Konformitätssicherungsspeichers für den beständigen Chat
 
Sie konfigurieren die Sicherung Compliance, den SQL Server-Speicher, die Sicherungsdatenbanken für Persistent Chat-Server bereitstellen oder Persistent Chat Server Compliance, den SQL Server-Speicher.
  
 **SQL Server-Speicher**: Wählen Sie eine vorhandene SQL Server-Instanz und optional eine Instanz für den beständigen Chat aus.
  
Klicken Sie auf **neu** , um eine neue SQL Server-Instanz und optional eine neue Instanz für die sicherungskonformitätsdaten beständigen Chat definieren.
  
Aktivieren Sie das Kontrollkästchen **Aktivieren SQL Server-Speicher für Spiegelung** Konfigurieren einer SQL Server-Datenbank und optional eine Instanz, die eine gespiegelte Datenbank für die sicherungskonformitätsdaten beständigen Chat bereitstellen.
  
Wählen Sie in der Liste **SQL Server-Spiegelung Speicher** einen SQL Server und optional eine Instanz, die als SQL Server-Spiegel für die Konformität des beständigen Chats backup SQL Server fungiert.
  
Klicken Sie auf **neu** , um eine neue SQL Server-Instanz und optional eine neue Instanz für den beständigen Chat SQL Server-Spiegelung zu definieren.
  
Wählen Sie in der Liste **Automatisches Failover mithilfe des SQL Server-Spiegelungszeugen aktivieren** eine SQL Server-Instanz aus, die als Zeugenserver für Failoverszenarios dient. Der Zeugenserver werden nicht Spiegelung oder Host Daten für den Server für beständigen Chat, sondern wird sichergestellt, dass nur eine SQL Server in einer gespiegelten Konfiguration können Sie jederzeit die aktiven SQL Server ist.
  
Klicken Sie auf **neu** , um einen neuen SQL Server-Zeugen definieren optional eine Instanz für die Konformität des beständigen Chats backup SQL Server-spiegelungszeugen.
  
Klicken Sie auf **Zurück**, um zum vorherigen Dialogfeld für die Pooldefinition zurückzukehren.
  
Klicken Sie auf **Weiter** , nachdem Sie die Eingabe der Optionen für diesen Pool backup SQL Server-Speicher-Konfiguration und Fortfahren mit der Definition der Persistent Chat Server Pool abgeschlossen haben.
  
Klicken Sie auf **Abbrechen**, um alle Änderungen zu verwerfen und den Assistenten **Neuen Pool für beständigen Chat definieren** zu beenden.
  
Klicken Sie auf **Hilfe**, um auf die kontextbezogene Hilfe (z. B. diese Seite) zuzugreifen.
  
## <a name="see-also"></a>Siehe auch

#### 

[Planen Sie für Persistent Chatserver in Skype für Business Server 2015](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md)
  
[Serveranforderungen für Skype für Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md)
  
[Hardware und Software-Anforderungen für Persistent Chat Server in Skype für Business Server 2015](../../plan-your-deployment/persistent-chat-server/hardware-and-software-requirements.md)
  
[Konfigurieren des kompatibilitätsdiensts für Persistent Chat Server in Skype für Business Server 2015](../../manage/persistent-chat/configure-compliance.md)
  
[Konfigurieren von hoher Verfügbarkeit und notfallwiederherstellung für Persistent Chat Server in Skype Business Server 2015](../../deploy/deploy-persistent-chat-server/configure-hadr-for-persistent-chat.md)

