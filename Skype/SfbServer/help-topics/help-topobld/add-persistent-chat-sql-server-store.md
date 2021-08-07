---
title: Hinzufügen des SQL Server-Speichers für den beständigen Chat
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
- ms.lync.tb.AddPersistentChatSqlStorePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c8e6064a-8127-4c25-8685-06f49d8bbfce
description: Sie konfigurieren die SQL Server Speicher, die Datenbanken für den Server für beständigen Chat oder den Serverpool für beständigen Chat bereitstellen.
ms.openlocfilehash: 62e4eeab923f4af1671047b00141cd06bfe477ef6c140d66be28210eceab4246
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2021
ms.locfileid: "54277010"
---
# <a name="add-persistent-chat-sql-server-store"></a>Hinzufügen des SQL Server-Speichers für den beständigen Chat
 
Sie konfigurieren die SQL Server Speicher, die Datenbanken für den Server für beständigen Chat oder den Serverpool für beständigen Chat bereitstellen.
  
 **SQL Server Speicher:** Wählen Sie eine vorhandene SQL Server und optional eine Instanz für beständigen Chat aus.
  
Klicken Sie auf **Neu,** um eine neue SQL Server und optional eine neue Instanz für die Daten des beständigen Chats zu definieren.
  
Aktivieren Sie das Kontrollkästchen **"SQL Server Speicherspiegelung aktivieren",** um eine SQL Server Datenbank und eine optionale Instanz zu konfigurieren, die eine gespiegelte Datenbank für die Daten des beständigen Chats bereitstellt.
  
Wählen Sie aus der Liste **"Spiegelung", SQL Server** speichern Sie eine SQL Server und eine optionale Instanz, die als SQL Server Spiegel für den SQL Server für beständigen Chat fungieren soll.
  
Klicken Sie auf **Neu,** um eine neue SQL Server und optional eine neue Instanz für die Spiegelung des beständigen Chats SQL Server zu definieren.
  
Wählen Sie in der Liste **Automatisches Failover mithilfe des SQL Server-Spiegelungszeugen aktivieren** eine SQL Server-Instanz aus, die als Zeugenserver für Failoverszenarios dient. Der Zeugenserver stellt keine Spiegelung oder Hostdaten für die Server für beständigen Chat bereit, stellt jedoch sicher, dass immer nur ein SQL Server in einer gespiegelten Konfiguration der aktive SQL Server ist.
  
Klicken Sie auf **Neu,** um einen neuen SQL Server Zeugen zu definieren, optional eine Instanz für den Spiegelungszeugen für beständigen Chat SQL Server.
  
Klicken Sie auf **Zurück**, um zum vorherigen Dialogfeld für die Pooldefinition zurückzukehren.
  
Klicken Sie auf **"Weiter",** nachdem Sie die Optionen für die SQL Server Speicherkonfiguration dieses Pools eingegeben haben, und fahren Sie mit der Pooldefinition für den Server für beständigen Chat fort.
  
Klicken Sie auf **Abbrechen**, um alle Änderungen zu verwerfen und den Assistenten **Neuen Pool für beständigen Chat definieren** zu beenden.
  
Klicken Sie auf **Hilfe**, um auf die kontextbezogene Hilfe (z. B. diese Seite) zuzugreifen.
  
## <a name="see-also"></a>Siehe auch

[Plan for Persistent Chat Server in Skype for Business Server 2015](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md)
  
[Hinzufügen des Servers für beständigen Chat zu Ihrer Skype for Business Server 2015-Topologie](../../deploy/deploy-persistent-chat-server/add-persistent-chat-server.md)
  
[Hardware- und Softwareanforderungen für den Server für beständigen Chat in Skype for Business Server 2015](../../plan-your-deployment/persistent-chat-server/hardware-and-software-requirements.md)
  
[Serveranforderungen für Skype for Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md)
  
[Topologiegrundlagen für Skype for Business Server 2015](../../plan-your-deployment/topology-basics/topology-basics.md)
  
[Konfigurieren der hohen Verfügbarkeit und Notfallwiederherstellung für den Server für beständigen Chat in Skype for Business Server 2015](../../deploy/deploy-persistent-chat-server/configure-hadr-for-persistent-chat.md)
