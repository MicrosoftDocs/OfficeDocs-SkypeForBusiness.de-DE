---
title: Hinzufügen des SQL Server-Konformitätssicherungsspeichers für den beständigen Chat
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/27/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddPersistentChatBackupComplianceStorePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 358b74bd-a97d-4f28-9bed-af633ea0099e
description: Sie konfigurieren die Sicherungscompliance SQL Server Speicher, die Sicherungsdatenbanken für den Server für beständigen Chat oder den Server für beständigen Chat SQL Server Speicher bereitstellen.
ms.openlocfilehash: edcb80d798e6039560db4149b17ce7c2d2d61b9d92a4450199dcad29b12093dc
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2021
ms.locfileid: "54344924"
---
# <a name="add-persistent-chat-compliance-backup-sql-server-store"></a>Hinzufügen des SQL Server-Compliancesicherungsspeichers für beständigen Chat
 
Sie konfigurieren die Sicherungscompliance SQL Server Speicher, die Sicherungsdatenbanken für den Server für beständigen Chat oder den Server für beständigen Chat SQL Server Speicher bereitstellen.
  
 **SQL Server Speicher:** Wählen Sie eine vorhandene SQL Server und optional eine Instanz für beständigen Chat aus.
  
Klicken Sie auf **Neu,** um eine neue SQL Server und optional eine neue Instanz für die Konformitätsdaten für den beständigen Chat zu definieren.
  
Aktivieren Sie das Kontrollkästchen **"SQL Server Spiegelung speichern aktivieren",** um eine SQL Server Datenbank und eine optionale Instanz zu konfigurieren, die eine gespiegelte Datenbank für die Compliancedaten für die Sicherung des beständigen Chats bereitstellt.
  
Wählen Sie aus der Liste **"Spiegelung", SQL Server** eine SQL Server und eine optionale Instanz speichern, die als SQL Server Spiegel für die Sicherungscompliance SQL Server für beständigen Chat fungieren soll.
  
Klicken Sie auf **Neu,** um eine neue SQL Server und optional eine neue Instanz für die Spiegelung des beständigen Chats SQL Server zu definieren.
  
Wählen Sie in der Liste **Automatisches Failover mithilfe des SQL Server-Spiegelungszeugen aktivieren** eine SQL Server-Instanz aus, die als Zeugenserver für Failoverszenarios dient. Der Zeugenserver spiegelt keine Spiegelung oder Hostdaten für die Server für beständigen Chat ab, stellt jedoch sicher, dass immer nur ein SQL Server in einer gespiegelten Konfiguration der aktive SQL Server ist.
  
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
