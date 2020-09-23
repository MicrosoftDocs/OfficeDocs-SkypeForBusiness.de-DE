---
title: Hinzufügen des SQL Server-Konformitätssicherungsspeichers für den beständigen Chat
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
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
description: Sie konfigurieren die Sicherungsrichtlinien SQL Server Speicher, die Sicherungsdatenbanken für den Server für beständigen Chat oder für die Einhaltung SQL Server Speichers für beständigen Chat bereitstellen sollen.
ms.openlocfilehash: 9251c322560d06652c4eefe80b6c05a51aa9f922
ms.sourcegitcommit: c69ab11b701a4833179b8479bc3204dfd4412096
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/23/2020
ms.locfileid: "48218696"
---
# <a name="add-persistent-chat-compliance-backup-sql-server-store"></a>Hinzufügen des SQL Server-Konformitätssicherungsspeichers für den beständigen Chat
 
Sie konfigurieren die Sicherungsrichtlinien SQL Server Speicher, die Sicherungsdatenbanken für den Server für beständigen Chat oder für die Einhaltung SQL Server Speichers für beständigen Chat bereitstellen sollen.
  
 **SQL Server Speicher**: Wählen Sie eine vorhandene SQL Server und optional eine Instanz für den beständigen Chat aus.
  
Klicken Sie auf **neu** , um eine neue SQL Server und optional eine neue Instanz für die Sicherungs Konformitätsdaten der persistent Chat-Sicherung zu definieren.
  
Aktivieren Sie das Kontrollkästchen **SQL Server Speicherspiegelung aktivieren** , um eine SQL Server Datenbank und optionale Instanz zu konfigurieren, die eine gespiegelte Datenbank für die Sicherungs Konformitätsdaten für den persistent Chat bereitstellt.
  
Wählen Sie im Listen **Spiegelungs SQL Server** eine SQL Server und optionale Instanz aus, die als SQL Server Spiegel für die Compliance-SQL Server für die Sicherung der persistenten Chats fungiert.
  
Klicken Sie auf **neu** , um eine neue SQL Server und optional eine neue Instanz für den beständigen Chat SQL Server Spiegelung zu definieren.
  
Wählen Sie in der Liste **Automatisches Failover mithilfe des SQL Server-Spiegelungszeugen aktivieren** eine SQL Server-Instanz aus, die als Zeugenserver für Failoverszenarios dient. Der Zeugenserver spiegelt oder hostet keine Daten für die Server für beständigen Chat, sondern stellt sicher, dass jeweils nur ein SQL Server in einer gespiegelten Konfiguration der aktive SQL Server ist.
  
Klicken Sie auf **neu** , um einen neuen SQL Server Zeugen optional eine Instanz für die Sicherungs Konformität für beständigen Chat SQL Server Spiegelungs Zeugen zu definieren.
  
Klicken Sie auf **Zurück**, um zum vorherigen Dialogfeld für die Pooldefinition zurückzukehren.
  
Klicken Sie auf **weiter** , nachdem Sie die Eingabe der Optionen für die Sicherung SQL Server Speicherkonfiguration dieses Pools abgeschlossen haben, und fahren Sie mit der Definition des Server Pools für beständigen Chat fort.
  
Klicken Sie auf **Abbrechen**, um alle Änderungen zu verwerfen und den Assistenten **Neuen Pool für beständigen Chat definieren** zu beenden.
  
Klicken Sie auf **Hilfe**, um auf die kontextbezogene Hilfe (z. B. diese Seite) zuzugreifen.
  
## <a name="see-also"></a>Siehe auch

[Planen des Servers für beständigen Chat in Skype for Business Server 2015](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md)
  
[Server Anforderungen für Skype for Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md)
  
[Hardware-und Softwareanforderungen für den Server für beständigen Chat in Skype for Business Server 2015](../../plan-your-deployment/persistent-chat-server/hardware-and-software-requirements.md)
  
[Konfigurieren des Kompatibilitätsdiensts für den Server für beständigen Chat in Skype for Business Server 2015](../../manage/persistent-chat/configure-compliance.md)
  
[Konfigurieren der hohen Verfügbarkeit und der Notfallwiederherstellung für den Server für beständigen Chat in Skype for Business Server 2015](../../deploy/deploy-persistent-chat-server/configure-hadr-for-persistent-chat.md)
