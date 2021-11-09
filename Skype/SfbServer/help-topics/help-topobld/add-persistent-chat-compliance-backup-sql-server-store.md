---
title: Hinzufügen des SQL Server-Konformitätssicherungsspeichers für den beständigen Chat
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
ms.date: 3/27/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddPersistentChatBackupComplianceStorePage
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: 358b74bd-a97d-4f28-9bed-af633ea0099e
description: Sie konfigurieren die Sicherungscompliance SQL Server Speicher, die Sicherungsdatenbanken für den Server für beständigen Chat oder den Server für beständigen Chat SQL Server Speicher bereitstellen.
ms.openlocfilehash: 818fda030415f8b1274b3dadf2ceed000f40a16d
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/08/2021
ms.locfileid: "60857672"
---
# <a name="add-persistent-chat-compliance-backup-sql-server-store"></a>Hinzufügen des SQL Server-Compliancesicherungsspeichers für beständigen Chat
 
Sie konfigurieren die Sicherungscompliance SQL Server Speicher, die Sicherungsdatenbanken für den Server für beständigen Chat oder den Server für beständigen Chat SQL Server Speicher bereitstellen.
  
 **SQL Server Speicher:** Wählen Sie eine vorhandene SQL Server und optional eine Instanz für beständigen Chat aus.
  
Klicken Sie auf **Neu,** um eine neue SQL Server und optional eine neue Instanz für die Konformitätsdaten für den beständigen Chat zu definieren.
  
Aktivieren Sie das Kontrollkästchen **"SQL Server Spiegelung speichern aktivieren",** um eine SQL Server-Datenbank und eine optionale Instanz zu konfigurieren, die eine gespiegelte Datenbank für die Sicherungscompliancedaten für beständigen Chat bereitstellt.
  
Wählen Sie aus der Liste **"Spiegelung", SQL Server** speichern Sie eine SQL Server und eine optionale Instanz, die als SQL Server Spiegel für die Sicherungscompliance SQL Server für beständigen Chat fungieren soll.
  
Klicken Sie auf **Neu,** um eine neue SQL Server und optional eine neue Instanz für die Spiegelung des beständigen Chats SQL Server zu definieren.
  
Wählen Sie in der Liste **Automatisches Failover mithilfe des SQL Server-Spiegelungszeugen aktivieren** eine SQL Server-Instanz aus, die als Zeugenserver für Failoverszenarios dient. Der Zeugenserver stellt keine Spiegelung oder Hostdaten für die Server für beständigen Chat bereit, stellt jedoch sicher, dass immer nur ein SQL Server in einer gespiegelten Konfiguration die aktive SQL Server ist.
  
Klicken Sie auf **Neu,** um einen neuen SQL Server Zeugen zu definieren, optional eine Instanz für die Sicherungskonformität des beständigen Chats SQL Server Spiegelungszeugen.
  
Klicken Sie auf **Zurück**, um zum vorherigen Dialogfeld für die Pooldefinition zurückzukehren.
  
Klicken Sie auf **"Weiter",** nachdem Sie die Optionen für die Sicherung SQL Server Speicherkonfiguration dieses Pools eingegeben haben, und fahren Sie mit der Pooldefinition für den Server für beständigen Chat fort.
  
Klicken Sie auf **Abbrechen**, um alle Änderungen zu verwerfen und den Assistenten **Neuen Pool für beständigen Chat definieren** zu beenden.
  
Klicken Sie auf **Hilfe**, um auf die kontextbezogene Hilfe (z. B. diese Seite) zuzugreifen.
  
## <a name="see-also"></a>Siehe auch

[Plan for Persistent Chat Server in Skype for Business Server 2015](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md)
  
[Serveranforderungen für Skype for Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md)
  
[Hardware- und Softwareanforderungen für den Server für beständigen Chat in Skype for Business Server 2015](../../plan-your-deployment/persistent-chat-server/hardware-and-software-requirements.md)
  
[Konfigurieren des Kompatibilitätsdiensts für den Server für beständigen Chat in Skype for Business Server 2015](../../manage/persistent-chat/configure-compliance.md)
  
[Konfigurieren der hohen Verfügbarkeit und Notfallwiederherstellung für den Server für beständigen Chat in Skype for Business Server 2015](../../deploy/deploy-persistent-chat-server/configure-hadr-for-persistent-chat.md)
