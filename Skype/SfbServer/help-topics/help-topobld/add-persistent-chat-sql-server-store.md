---
title: Hinzufügen des SQL Server-Speichers für den beständigen Chat
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/27/2015
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddPersistentChatSqlStorePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c8e6064a-8127-4c25-8685-06f49d8bbfce
description: Konfigurieren Sie die SQL Server-Speicher, die Datenbanken für die Persistent Chat Server oder Pool Persistent Chat Server bereitgestellt werden.
ms.openlocfilehash: ec95ed721009163133c123e1fb9fb231e106022c
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "33897364"
---
# <a name="add-persistent-chat-sql-server-store"></a>Hinzufügen des SQL Server-Speichers für den beständigen Chat
 
Konfigurieren Sie die SQL Server-Speicher, die Datenbanken für die Persistent Chat Server oder Pool Persistent Chat Server bereitgestellt werden.
  
 **SQL Server-Speicher**: Wählen Sie eine vorhandene SQL Server-Instanz und optional eine Instanz für den beständigen Chat aus.
  
Klicken Sie auf **neu** , um eine neue SQL Server-Instanz und optional eine neue Instanz für den beständigen Chat Daten definieren.
  
Aktivieren Sie das Kontrollkästchen **Aktivieren SQL Server-Speicher für Spiegelung** Konfigurieren einer SQL Server-Datenbank und optional eine Instanz, die eine gespiegelte Datenbank für den beständigen Chat Daten bereitgestellt wird.
  
Wählen Sie in der Liste **SQL Server-Spiegelung Speicher** einen SQL Server und optional eine Instanz als SQL Server-Spiegel für die Persistent Chat SQL Server verwenden.
  
Klicken Sie auf **neu** , um eine neue SQL Server-Instanz und optional eine neue Instanz für den beständigen Chat SQL Server-Spiegelung zu definieren.
  
Wählen Sie in der Liste **Automatisches Failover mithilfe des SQL Server-Spiegelungszeugen aktivieren** eine SQL Server-Instanz aus, die als Zeugenserver für Failoverszenarios dient. Der Zeugenserver werden nicht Spiegelung oder Host Daten für den Server für beständigen Chat, sondern wird sichergestellt, dass nur eine SQL Server in einer gespiegelten Konfiguration können Sie jederzeit die aktiven SQL Server ist.
  
Klicken Sie auf **neu** , um einen neuen SQL Server-Zeugen optional eine Instanz für den beständigen Chat SQL Server-spiegelungszeugen zu definieren.
  
Klicken Sie auf **Zurück**, um zum vorherigen Dialogfeld für die Pooldefinition zurückzukehren.
  
Klicken Sie auf **Weiter** , nachdem Sie die Eingabe der Optionen für die Konfiguration zum Speichern von SQL Server des Pools und Fortfahren mit der Definition der Persistent Chat Server Pool abgeschlossen haben.
  
Klicken Sie auf **Abbrechen**, um alle Änderungen zu verwerfen und den Assistenten **Neuen Pool für beständigen Chat definieren** zu beenden.
  
Klicken Sie auf **Hilfe**, um auf die kontextbezogene Hilfe (z. B. diese Seite) zuzugreifen.
  
## <a name="see-also"></a>Siehe auch

[Planen für den Server für beständigen Chat in Skype for Business Server 2015](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md)
  
[Hinzufügen von Persistent Chat Server zu Ihrer Skype für Business Server 2015 Topologie](../../deploy/deploy-persistent-chat-server/add-persistent-chat-server.md)
  
[Hardware- und Softwareanforderungen an den Server für beständigen Chat in Skype for Business Server 2015](../../plan-your-deployment/persistent-chat-server/hardware-and-software-requirements.md)
  
[Server requirements for Skype for Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md)
  
[Topologiegrundlagen in Skype for Business Server 2015](../../plan-your-deployment/topology-basics/topology-basics.md)
  
[Konfigurieren der hohen Verfügbarkeit und der Notfallwiederherstellung für Server für beständigen Chat in Skype for Business Server 2015](../../deploy/deploy-persistent-chat-server/configure-hadr-for-persistent-chat.md)
