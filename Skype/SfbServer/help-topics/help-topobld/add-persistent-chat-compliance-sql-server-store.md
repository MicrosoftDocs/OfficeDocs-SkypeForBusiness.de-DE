---
title: Hinzufügen des SQL Server-Speichers für Konformität für den beständigen Chat
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
- ms.lync.tb.AddPersistentChatComplianceStorePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b9771b53-e19a-4a12-bf01-24bae6f7e482
description: Sie konfigurieren die Kompatibilität SQL Server Speichern, die Datenbanken für die Kompatibilitätsfunktion für den Server für beständigen Chat oder den Server für beständigen Chat bereitstellen.
ms.openlocfilehash: c3a045e8a8489bce7c333ade7a133afbc80016a7db81239c5df5292854a76870
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2021
ms.locfileid: "54309414"
---
# <a name="add-persistent-chat-compliance-sql-server-store"></a>Hinzufügen des SQL Server-Speichers für Compliance für beständigen Chat
 
Sie konfigurieren die Kompatibilität SQL Server Speichern, die Datenbanken für die Kompatibilitätsfunktion für den Server für beständigen Chat oder den Server für beständigen Chat bereitstellen.
  
 **SQL Server Speicher:** Wählen Sie eine vorhandene SQL Server und optional eine Instanz für beständigen Chat aus.
  
Klicken Sie auf **Neu,** um eine neue SQL Server und optional eine neue Instanz für die Kompatibilitätsdaten für beständigen Chat zu definieren.
  
Aktivieren Sie das Kontrollkästchen **"SQL Server Spiegelung speichern aktivieren",** um eine SQL Server Datenbank und eine optionale Instanz zu konfigurieren, die eine gespiegelte Datenbank für die Kompatibilitätsdaten für beständigen Chat bereitstellt.
  
Wählen Sie aus der Liste **"Spiegelung" aus, SQL Server** eine SQL Server und eine optionale Instanz speichern, die als SQL Server Spiegel für die Kompatibilität des beständigen Chats SQL Server fungieren soll.
  
Klicken Sie auf **Neu,** um eine neue SQL Server und optional eine neue Instanz für die Spiegelung des beständigen Chats SQL Server zu definieren.
  
Wählen Sie in der Liste **Automatisches Failover mithilfe des SQL Server-Spiegelungszeugen aktivieren** eine SQL Server-Instanz aus, die als Zeugenserver für Failoverszenarios dient. Der Zeugenserver stellt keine Spiegelung oder Hostdaten für die Server für beständigen Chat bereit, stellt jedoch sicher, dass immer nur ein SQL Server in einer gespiegelten Konfiguration der aktive SQL Server ist.
  
Klicken Sie auf **Neu,** um einen neuen SQL Server Zeugen zu definieren, optional eine Instanz für die Kompatibilität des beständigen Chats SQL Server Spiegelungszeugen.
  
Klicken Sie auf **Zurück**, um zum vorherigen Dialogfeld für die Pooldefinition zurückzukehren.
  
Klicken Sie auf **"Weiter",** nachdem Sie die Optionen für die Sicherung SQL Server Speicherkonfiguration dieses Pools eingegeben haben, und fahren Sie mit der Pooldefinition für den Server für beständigen Chat fort.
  
Klicken Sie auf **Abbrechen**, um alle Änderungen zu verwerfen und den Assistenten **Neuen Pool für beständigen Chat definieren** zu beenden.
  
Klicken Sie auf **Hilfe**, um auf die kontextbezogene Hilfe (z. B. diese Seite) zuzugreifen.
  
## <a name="see-also"></a>Siehe auch

[Plan for Persistent Chat Server in Skype for Business Server 2015](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md)
  
[Serveranforderungen für Skype for Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md)
  
[Hardware- und Softwareanforderungen für den Server für beständigen Chat in Skype for Business Server 2015](../../plan-your-deployment/persistent-chat-server/hardware-and-software-requirements.md)
  
[Konfigurieren des Kompatibilitätsdiensts für den Server für beständigen Chat in Skype for Business Server 2015](../../manage/persistent-chat/configure-compliance.md)
