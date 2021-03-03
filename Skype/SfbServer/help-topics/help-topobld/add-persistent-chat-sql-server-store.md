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
description: Sie konfigurieren die SQL Server, die Datenbanken für den Server für beständigen Chat oder den Pool für den Server für beständigen Chat bereitstellen.
ms.openlocfilehash: e93705e0646f1115994a61c936a5c0cb16149dfa
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2021
ms.locfileid: "49818655"
---
# <a name="add-persistent-chat-sql-server-store"></a>Hinzufügen des SQL Server-Speichers für den beständigen Chat
 
Sie konfigurieren die SQL Server, die Datenbanken für den Server für beständigen Chat oder den Pool für den Server für beständigen Chat bereitstellen.
  
 **SQL Server:** Wählen Sie eine vorhandene SQL Server und optional eine Instanz für den beständigen Chat aus.
  
Klicken **Sie auf** "Neu", um SQL Server und optional eine neue Instanz für die Daten des beständigen Chats zu definieren.
  
Aktivieren **Sie das Kontrollkästchen SQL Server** speicherspiegelung aktivieren, um eine SQL Server-Datenbank und optionale Instanz zu konfigurieren, die eine gespiegelte Datenbank für die Daten des beständigen Chats bereitstellen.
  
Wählen Sie in der Liste **"Spiegelung" SQL Server eine** SQL Server und optionale Instanz, die als Spiegelung für den beständigen Chat SQL Server dient, SQL Server.
  
Klicken **Sie auf** "Neu", SQL Server und optional eine neue Instanz für die Spiegelung des beständigen Chats SQL Server definieren.
  
Wählen Sie in der Liste **Automatisches Failover mithilfe des SQL Server-Spiegelungszeugen aktivieren** eine SQL Server-Instanz aus, die als Zeugenserver für Failoverszenarios dient. Der Zeugenserver spiegelt oder hostet keine Daten für die Server für beständigen Chat, sondern stellt sicher, dass immer nur ein SQL Server in einer gespiegelten Konfiguration die aktive SQL Server ist.
  
Klicken **Sie auf** "Neu", um SQL Server instanz für den Spiegelungszeugen für den beständigen SQL Server zu definieren.
  
Klicken Sie auf **Zurück**, um zum vorherigen Dialogfeld für die Pooldefinition zurückzukehren.
  
Klicken **Sie** auf "Weiter", nachdem Sie die Optionen für die Konfiguration des SQL Server pools eingeben und mit der Pooldefinition für den Server für beständigen Chat fortfahren möchten.
  
Klicken Sie auf **Abbrechen**, um alle Änderungen zu verwerfen und den Assistenten **Neuen Pool für beständigen Chat definieren** zu beenden.
  
Klicken Sie auf **Hilfe**, um auf die kontextbezogene Hilfe (z. B. diese Seite) zuzugreifen.
  
## <a name="see-also"></a>Siehe auch

[Planen des Servers für beständigen Chat in Skype for Business Server 2015](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md)
  
[Hinzufügen eines Servers für beständigen Chat zu Ihrer Skype for Business Server 2015-Topologie](../../deploy/deploy-persistent-chat-server/add-persistent-chat-server.md)
  
[Hardware- und Softwareanforderungen für den Server für beständigen Chat in Skype for Business Server 2015](../../plan-your-deployment/persistent-chat-server/hardware-and-software-requirements.md)
  
[Serveranforderungen für Skype for Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md)
  
[Topologiegrunddaten für Skype for Business Server 2015](../../plan-your-deployment/topology-basics/topology-basics.md)
  
[Konfigurieren von hoher Verfügbarkeit und Notfallwiederherstellung für den Server für beständigen Chat in Skype for Business Server 2015](../../deploy/deploy-persistent-chat-server/configure-hadr-for-persistent-chat.md)
