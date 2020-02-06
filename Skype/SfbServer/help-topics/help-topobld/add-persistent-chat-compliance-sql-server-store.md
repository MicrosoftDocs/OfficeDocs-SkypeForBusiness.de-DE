---
title: Hinzufügen des SQL Server-Speichers für Konformität für den beständigen Chat
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/27/2015
audience: ITPro
ms.topic: article
f1.keywords:
- NOCSH
ms.custom:
- ms.lync.tb.AddPersistentChatComplianceStorePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b9771b53-e19a-4a12-bf01-24bae6f7e482
description: Sie konfigurieren die Compliance-SQL Server-Stores, die Datenbanken für den Server für beständigen Chat Server oder das Compliance-Feature für beständigen Chat bereitstellen.
ms.openlocfilehash: fd51b3d582c915d02799f2f633869e84f3659c4f
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2020
ms.locfileid: "41820687"
---
# <a name="add-persistent-chat-compliance-sql-server-store"></a>Hinzufügen des SQL Server-Speichers für Konformität für den beständigen Chat
 
Sie konfigurieren die Compliance-SQL Server-Stores, die Datenbanken für den Server für beständigen Chat Server oder das Compliance-Feature für beständigen Chat bereitstellen.
  
 **SQL Server Store**: Wählen Sie einen vorhandenen SQL Server und optional eine Instanz für beständigen Chat aus.
  
Klicken Sie auf **neu** , um einen neuen SQL Server und optional eine neue Instanz für die Kompatibilitätsdaten des beständigen Chats zu definieren.
  
Aktivieren Sie das Kontrollkästchen **Spiegelung des SQL Server-Speichers aktivieren** , um eine SQL Server-Datenbank und eine optionale Instanz zu konfigurieren, die eine gespiegelte Datenbank für die beständigen Chat-Kompatibilitätsdaten bereitstellt.
  
Wählen Sie aus der Liste **Spiegelungs-SQL Server Store** eine SQL Server-und eine optionale Instanz aus, die als SQL Server-Spiegelung für den Compliance-SQL Server für beständigen Chat fungieren soll.
  
Klicken Sie auf **neu** , um einen neuen SQL Server und optional eine neue Instanz für die SQL Server-Spiegelung des beständigen Chats zu definieren.
  
Wählen Sie in der Liste **Automatisches Failover mithilfe des SQL Server-Spiegelungszeugen aktivieren** eine SQL Server-Instanz aus, die als Zeugenserver für Failoverszenarios dient. Der Zeugenserver spiegelt oder hostet keine Daten für die persistenten Chat Server, sondern stellt sicher, dass nur ein SQL Server in einer gespiegelten Konfiguration zu einem beliebigen Zeitpunkt der aktive SQL Server ist.
  
Klicken Sie auf **neu** , um einen neuen SQL Server-Zeugen zu definieren optional eine Instanz für den beständigen Chat-Konformitäts Zeugen für SQL Server-Spiegelung.
  
Klicken Sie auf **Zurück**, um zum vorherigen Dialogfeld für die Pooldefinition zurückzukehren.
  
Klicken Sie auf **weiter** , nachdem Sie die Optionen für die Backup-SQL Server-Speicherkonfiguration dieses Pools eingegeben haben, und fahren Sie mit der Server Pool Definition des beständigen Chats fort.
  
Klicken Sie auf **Abbrechen**, um alle Änderungen zu verwerfen und den Assistenten **Neuen Pool für beständigen Chat definieren** zu beenden.
  
Klicken Sie auf **Hilfe**, um auf die kontextbezogene Hilfe (z. B. diese Seite) zuzugreifen.
  
## <a name="see-also"></a>Siehe auch

[Planen für den Server für beständigen Chat in Skype for Business Server 2015](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md)
  
[Server requirements for Skype for Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md)
  
[Hardware- und Softwareanforderungen an den Server für beständigen Chat in Skype for Business Server 2015](../../plan-your-deployment/persistent-chat-server/hardware-and-software-requirements.md)
  
[Konfigurieren des Kompatibilitätsdienstes auf dem Server für beständigen Chat in Skype for Business Server 2015](../../manage/persistent-chat/configure-compliance.md)
