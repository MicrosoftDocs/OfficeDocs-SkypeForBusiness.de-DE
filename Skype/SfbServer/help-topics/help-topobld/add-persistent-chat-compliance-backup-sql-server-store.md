---
title: Hinzufügen des SQL Server-Konformitätssicherungsspeichers für den beständigen Chat
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/27/2015
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddPersistentChatBackupComplianceStorePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 358b74bd-a97d-4f28-9bed-af633ea0099e
description: Sie konfigurieren die Sicherung Compliance, den SQL Server-Speicher, die Sicherungsdatenbanken für Persistent Chat-Server bereitstellen oder Persistent Chat Server Compliance, den SQL Server-Speicher.
ms.openlocfilehash: 4e3a2bf034d5ab20c7352f2b6ef9c8a6a0c4befa
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/28/2018
---
# <a name="add-persistent-chat-compliance-backup-sql-server-store"></a><span data-ttu-id="5a10f-103">Hinzufügen des SQL Server-Konformitätssicherungsspeichers für den beständigen Chat</span><span class="sxs-lookup"><span data-stu-id="5a10f-103">Add Persistent Chat Compliance Backup SQL Server Store</span></span>
 
<span data-ttu-id="5a10f-104">Sie konfigurieren die Sicherung Compliance, den SQL Server-Speicher, die Sicherungsdatenbanken für Persistent Chat-Server bereitstellen oder Persistent Chat Server Compliance, den SQL Server-Speicher.</span><span class="sxs-lookup"><span data-stu-id="5a10f-104">You configure the Backup compliance SQL Server stores that will provide backup databases for the Persistent Chat Server or Persistent Chat Server compliance SQL Server stores.</span></span>
  
 <span data-ttu-id="5a10f-105">**SQL Server-Speicher**: Wählen Sie eine vorhandene SQL Server-Instanz und optional eine Instanz für den beständigen Chat aus.</span><span class="sxs-lookup"><span data-stu-id="5a10f-105">**SQL Server store**: Select an existing SQL Server and optionally an instance for Persistent Chat.</span></span>
  
<span data-ttu-id="5a10f-106">Klicken Sie auf **neu** , um eine neue SQL Server-Instanz und optional eine neue Instanz für die sicherungskonformitätsdaten beständigen Chat definieren.</span><span class="sxs-lookup"><span data-stu-id="5a10f-106">Click **New** to define a new SQL Server and optionally a new instance for the Persistent Chat backup compliance data.</span></span>
  
<span data-ttu-id="5a10f-107">Aktivieren Sie das Kontrollkästchen **Aktivieren SQL Server-Speicher für Spiegelung** Konfigurieren einer SQL Server-Datenbank und optional eine Instanz, die eine gespiegelte Datenbank für die sicherungskonformitätsdaten beständigen Chat bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="5a10f-107">Select the **Enable SQL Server store mirroring** checkbox to configure a SQL Server database and optional instance that will provide a mirrored database for the Persistent Chat backup compliance data.</span></span>
  
<span data-ttu-id="5a10f-108">Wählen Sie in der Liste **SQL Server-Spiegelung Speicher** einen SQL Server und optional eine Instanz, die als SQL Server-Spiegel für die Konformität des beständigen Chats backup SQL Server fungiert.</span><span class="sxs-lookup"><span data-stu-id="5a10f-108">Select from the list **Mirroring SQL Server store** a SQL Server and optional instance to act as the SQL Server mirror for the Persistent Chat backup compliance SQL Server.</span></span>
  
<span data-ttu-id="5a10f-109">Klicken Sie auf **neu** , um eine neue SQL Server-Instanz und optional eine neue Instanz für den beständigen Chat SQL Server-Spiegelung zu definieren.</span><span class="sxs-lookup"><span data-stu-id="5a10f-109">Click **New** to define a new SQL Server and optionally a new instance for the Persistent Chat SQL Server mirroring.</span></span>
  
<span data-ttu-id="5a10f-110">Wählen Sie in der Liste **Automatisches Failover mithilfe des SQL Server-Spiegelungszeugen aktivieren** eine SQL Server-Instanz aus, die als Zeugenserver für Failoverszenarios dient.</span><span class="sxs-lookup"><span data-stu-id="5a10f-110">Select the list **Use SQL Server mirroring witness to enable automatic failover** a SQL Server that will act as the witness server in failover scenarios.</span></span> <span data-ttu-id="5a10f-111">Der Zeugenserver werden nicht Spiegelung oder Host Daten für den Server für beständigen Chat, sondern wird sichergestellt, dass nur eine SQL Server in einer gespiegelten Konfiguration können Sie jederzeit die aktiven SQL Server ist.</span><span class="sxs-lookup"><span data-stu-id="5a10f-111">The witness server does not mirror or host data for the Persistent Chat servers, but ensures that only one SQL Server in a mirrored configuration is the active SQL Server at any time.</span></span>
  
<span data-ttu-id="5a10f-112">Klicken Sie auf **neu** , um einen neuen SQL Server-Zeugen definieren optional eine Instanz für die Konformität des beständigen Chats backup SQL Server-spiegelungszeugen.</span><span class="sxs-lookup"><span data-stu-id="5a10f-112">Click **New** to define a new SQL Server witness optionally an instance for the Persistent Chat backup compliance SQL Server mirroring witness.</span></span>
  
<span data-ttu-id="5a10f-113">Klicken Sie auf **Zurück**, um zum vorherigen Dialogfeld für die Pooldefinition zurückzukehren.</span><span class="sxs-lookup"><span data-stu-id="5a10f-113">Click **Back** to go back to the previous pool definition dialog.</span></span>
  
<span data-ttu-id="5a10f-114">Klicken Sie auf **Weiter** , nachdem Sie die Eingabe der Optionen für diesen Pool backup SQL Server-Speicher-Konfiguration und Fortfahren mit der Definition der Persistent Chat Server Pool abgeschlossen haben.</span><span class="sxs-lookup"><span data-stu-id="5a10f-114">Click **Next** after you have finished entering the options for this pool's backup SQL Server store configuration and to proceed with the Persistent Chat Server pool definition.</span></span>
  
<span data-ttu-id="5a10f-115">Klicken Sie auf **Abbrechen**, um alle Änderungen zu verwerfen und den Assistenten **Neuen Pool für beständigen Chat definieren** zu beenden.</span><span class="sxs-lookup"><span data-stu-id="5a10f-115">Click **Cancel** to discard all changes and end the **Define New Persistent Chat Pool** wizard.</span></span>
  
<span data-ttu-id="5a10f-116">Klicken Sie auf **Hilfe**, um auf die kontextbezogene Hilfe (z. B. diese Seite) zuzugreifen.</span><span class="sxs-lookup"><span data-stu-id="5a10f-116">Click **Help** to access context sensitive help, such as this page.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="5a10f-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="5a10f-117">See also</span></span>

#### 

[<span data-ttu-id="5a10f-118">Planen Sie für Persistent Chatserver in Skype für Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="5a10f-118">Plan for Persistent Chat Server in Skype for Business Server 2015</span></span>](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md)
  
[<span data-ttu-id="5a10f-119">Serveranforderungen für Skype für Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="5a10f-119">Server requirements for Skype for Business Server 2015</span></span>](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md)
  
[<span data-ttu-id="5a10f-120">Hardware und Software-Anforderungen für Persistent Chat Server in Skype für Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="5a10f-120">Hardware and software requirements for Persistent Chat Server in Skype for Business Server 2015</span></span>](../../plan-your-deployment/persistent-chat-server/hardware-and-software-requirements.md)
  
[<span data-ttu-id="5a10f-121">Konfigurieren des kompatibilitätsdiensts für Persistent Chat Server in Skype für Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="5a10f-121">Configure the Compliance service for Persistent Chat Server in Skype for Business Server 2015</span></span>](../../manage/persistent-chat/configure-compliance.md)
  
[<span data-ttu-id="5a10f-122">Konfigurieren von hoher Verfügbarkeit und notfallwiederherstellung für Persistent Chat Server in Skype Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="5a10f-122">Configure high availability and disaster recovery for Persistent Chat Server in Skype for Business Server 2015</span></span>](../../deploy/deploy-persistent-chat-server/configure-hadr-for-persistent-chat.md)

