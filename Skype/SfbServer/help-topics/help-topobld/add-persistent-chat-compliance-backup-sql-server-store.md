---
title: Hinzufügen des SQL Server-Konformitätssicherungsspeichers für den beständigen Chat
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/27/2015
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddPersistentChatBackupComplianceStorePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 358b74bd-a97d-4f28-9bed-af633ea0099e
description: Sie konfigurieren die Backup-Compliance-SQL Server-Stores, die Backup-Datenbanken für den beständigen Chat Server oder den beständigen Chat Server-Compliance-SQL Server-Speicher bereitstellen
ms.openlocfilehash: 457874f87266453939c75cdef50d30231d8610bf
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2019
ms.locfileid: "34277706"
---
# <a name="add-persistent-chat-compliance-backup-sql-server-store"></a>Hinzufügen des SQL Server-Konformitätssicherungsspeichers für den beständigen Chat
 
Sie konfigurieren die Backup-Compliance-SQL Server-Stores, die Backup-Datenbanken für den beständigen Chat Server oder den beständigen Chat Server-Compliance-SQL Server-Speicher bereitstellen
  
 **SQL Server Store**: Wählen Sie einen vorhandenen SQL Server und optional eine Instanz für beständigen Chat aus.
  
Klicken Sie auf **neu** , um einen neuen SQL Server und optional eine neue Instanz für die Sicherungs Kompatibilitätsdaten für beständigen Chat zu definieren.
  
Aktivieren Sie das Kontrollkästchen **Spiegelung des SQL Server-Speichers aktivieren** , um eine SQL Server-Datenbank und eine optionale Instanz zu konfigurieren, die eine gespiegelte Datenbank für die Sicherungs Kompatibilitätsdaten für beständige Chats bereitstellt.
  
Wählen Sie aus der Liste Spiegelungs- **SQL Server Store** eine SQL Server-und eine optionale Instanz aus, die als SQL Server-Spiegelung für den beständigen Chat-Compliance-SQL-Server fungieren soll.
  
Klicken Sie auf **neu** , um einen neuen SQL Server und optional eine neue Instanz für die SQL Server-Spiegelung des beständigen Chats zu definieren.
  
Wählen Sie in der Liste **Automatisches Failover mithilfe des SQL Server-Spiegelungszeugen aktivieren** eine SQL Server-Instanz aus, die als Zeugenserver für Failoverszenarios dient. Der Zeugenserver spiegelt oder hostet keine Daten für die persistenten Chat Server, sondern stellt sicher, dass nur ein SQL Server in einer gespiegelten Konfiguration zu einem beliebigen Zeitpunkt der aktive SQL Server ist.
  
Klicken Sie auf **neu** , um einen neuen SQL Server-Zeugen optional eine Instanz für den beständigen Chat-Sicherungs Compliance-SQL Server-Spiegelungs Zeugen zu definieren.
  
Klicken Sie auf **Zurück**, um zum vorherigen Dialogfeld für die Pooldefinition zurückzukehren.
  
Klicken Sie auf **weiter** , nachdem Sie die Optionen für die Backup-SQL Server-Speicherkonfiguration dieses Pools eingegeben haben, und fahren Sie mit der Server Pool Definition des beständigen Chats fort.
  
Klicken Sie auf **Abbrechen**, um alle Änderungen zu verwerfen und den Assistenten **Neuen Pool für beständigen Chat definieren** zu beenden.
  
Klicken Sie auf **Hilfe**, um auf die kontextbezogene Hilfe (z. B. diese Seite) zuzugreifen.
  
## <a name="see-also"></a>Siehe auch

[Planen für den Server für beständigen Chat in Skype for Business Server 2015](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md)
  
[Server requirements for Skype for Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md)
  
[Hardware- und Softwareanforderungen an den Server für beständigen Chat in Skype for Business Server 2015](../../plan-your-deployment/persistent-chat-server/hardware-and-software-requirements.md)
  
[Konfigurieren des Kompatibilitätsdienstes auf dem Server für beständigen Chat in Skype for Business Server 2015](../../manage/persistent-chat/configure-compliance.md)
  
[Konfigurieren der hohen Verfügbarkeit und der Notfallwiederherstellung für Server für beständigen Chat in Skype for Business Server 2015](../../deploy/deploy-persistent-chat-server/configure-hadr-for-persistent-chat.md)
