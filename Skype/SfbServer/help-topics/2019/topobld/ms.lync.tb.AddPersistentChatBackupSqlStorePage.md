---
title: Hinzufügen des SQL Server-Sicherungsspeichers für den beständigen Chat
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/27/2015
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddPersistentChatBackupSqlStorePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 106698e4-ce73-4a34-8fc7-e9d3208a17dc
description: Sie konfigurieren die SQL Server-Speicher, die Sicherungsdatenbanken für den beständigen Chat-Server oder Persistent Chat Server Pool bereitgestellt werden.
ms.openlocfilehash: 67dc09cca54f0079fc4b7bac16355bbd8dc64633
ms.sourcegitcommit: e577b4bdf3827fdfaf4482928adde177a64e4406
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/24/2018
---
# <a name="add-persistent-chat-backup-sql-server-store"></a>Hinzufügen des SQL Server-Sicherungsspeichers für den beständigen Chat
 
Sie konfigurieren die SQL Server-Speicher, die Sicherungsdatenbanken für den beständigen Chat-Server oder Persistent Chat Server Pool bereitgestellt werden.
  
 **SQL Server-Speicher**: Wählen Sie eine vorhandene SQL Server-Instanz und optional eine Instanz für den beständigen Chat aus.
  
Klicken Sie auf **neu** , um eine neue SQL Server-Instanz und optional eine neue Instanz für die Sicherungsdaten beständigen Chat definieren.
  
Aktivieren Sie das Kontrollkästchen **Aktivieren SQL Server-Speicher für Spiegelung** Konfigurieren einer SQL Server-Datenbank und optional eine Instanz, die eine gespiegelte Datenbank für die Sicherungsdaten von beständigen Chat bereitstellen.
  
Wählen Sie in der Liste **SQL Server-Spiegelung Speicher** einen SQL Server und optional eine Instanz als SQL Server-Spiegel für beständigen Chat backup SQL Server verwenden.
  
Klicken Sie auf **neu** , um eine neue SQL Server-Instanz und optional eine neue Instanz für den beständigen Chat SQL Server-Spiegelung zu definieren.
  
Wählen Sie in der Liste **Automatisches Failover mithilfe des SQL Server-Spiegelungszeugen aktivieren** eine SQL Server-Instanz aus, die als Zeugenserver für Failoverszenarios dient. Der Zeugenserver werden nicht Spiegelung oder Host Daten für den Server für beständigen Chat, sondern wird sichergestellt, dass nur eine SQL Server in einer gespiegelten Konfiguration können Sie jederzeit die aktiven SQL Server ist.
  
Klicken Sie auf **neu** , um einen neuen SQL Server-Zeugen definieren optional eine Instanz für den beständigen Chat backup SQL Server-spiegelungszeugen aktivieren.
  
Klicken Sie auf **Zurück**, um zum vorherigen Dialogfeld für die Pooldefinition zurückzukehren.
  
Klicken Sie auf **Weiter** , nachdem Sie die Eingabe der Optionen für diesen Pool backup SQL Server-Speicher-Konfiguration und Fortfahren mit der Definition der Persistent Chat Server Pool abgeschlossen haben.
  
Klicken Sie auf **Abbrechen**, um alle Änderungen zu verwerfen und den Assistenten **Neuen Pool für beständigen Chat definieren** zu beenden.
  
Klicken Sie auf **Hilfe**, um auf die kontextbezogene Hilfe (z. B. diese Seite) zuzugreifen.
  
## <a name="see-also"></a>Siehe auch

#### 

[Planen Sie für Persistent Chatserver in Skype für Business Server 2015](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md)
  
[Serveranforderungen für Skype für Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md)
  
[Hardware und Software-Anforderungen für Persistent Chat Server in Skype für Business Server 2015](../../plan-your-deployment/persistent-chat-server/hardware-and-software-requirements.md)
  
[Konfigurieren von hoher Verfügbarkeit und notfallwiederherstellung für Persistent Chat Server in Skype Business Server 2015](../../deploy/deploy-persistent-chat-server/configure-hadr-for-persistent-chat.md)

