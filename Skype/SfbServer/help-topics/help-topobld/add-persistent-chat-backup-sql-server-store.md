---
title: Hinzufügen des SQL Server-Sicherungsspeichers für den beständigen Chat
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/27/2015
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddPersistentChatBackupSqlStorePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 106698e4-ce73-4a34-8fc7-e9d3208a17dc
description: Sie konfigurieren die Backup-SQL Server-Speicher, die Backup-Datenbanken für den beständigen Chat Server oder den Serverpool für beständigen Chat bereitstellen.
ms.openlocfilehash: 39e5e1ead6ed3cb089545406852de16170d782dc
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2019
ms.locfileid: "34304653"
---
# <a name="add-persistent-chat-backup-sql-server-store"></a><span data-ttu-id="1e266-103">Hinzufügen des SQL Server-Sicherungsspeichers für den beständigen Chat</span><span class="sxs-lookup"><span data-stu-id="1e266-103">Add Persistent Chat Backup SQL Server Store</span></span>
 
<span data-ttu-id="1e266-104">Sie konfigurieren die Backup-SQL Server-Speicher, die Backup-Datenbanken für den beständigen Chat Server oder den Serverpool für beständigen Chat bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="1e266-104">You configure the Backup SQL Server stores that will provide backup databases for the Persistent Chat Server or Persistent Chat Server pool.</span></span>
  
 <span data-ttu-id="1e266-105">**SQL Server Store**: Wählen Sie einen vorhandenen SQL Server und optional eine Instanz für beständigen Chat aus.</span><span class="sxs-lookup"><span data-stu-id="1e266-105">**SQL Server store**: Select an existing SQL Server and optionally an instance for Persistent Chat.</span></span>
  
<span data-ttu-id="1e266-106">Klicken Sie auf **neu** , um einen neuen SQL Server und optional eine neue Instanz für die Backup-Daten des beständigen Chats zu definieren.</span><span class="sxs-lookup"><span data-stu-id="1e266-106">Click **New** to define a new SQL Server and optionally a new instance for the Persistent Chat backup data.</span></span>
  
<span data-ttu-id="1e266-107">Aktivieren Sie das Kontrollkästchen **Spiegelung des SQL Server-Speichers aktivieren** , um eine SQL Server-Datenbank und eine optionale Instanz zu konfigurieren, die eine gespiegelte Datenbank für die Backup-Daten des beständigen Chats bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="1e266-107">Select the **Enable SQL Server store mirroring** checkbox to configure a SQL Server database and optional instance that will provide a mirrored database for the Persistent Chat backup data.</span></span>
  
<span data-ttu-id="1e266-108">Wählen Sie aus der Liste der Spiegelungs- **SQL Server** eine SQL Server-und eine optionale Instanz aus, die als SQL Server-Spiegelung für den persistenten Chat-Backup-SQL-Server fungieren soll.</span><span class="sxs-lookup"><span data-stu-id="1e266-108">Select from the list **Mirroring SQL Server store** a SQL Server and optional instance to act as the SQL Server mirror for the Persistent Chat backup SQL Server.</span></span>
  
<span data-ttu-id="1e266-109">Klicken Sie auf **neu** , um einen neuen SQL Server und optional eine neue Instanz für die SQL Server-Spiegelung des beständigen Chats zu definieren.</span><span class="sxs-lookup"><span data-stu-id="1e266-109">Click **New** to define a new SQL Server and optionally a new instance for the Persistent Chat SQL Server mirroring.</span></span>
  
<span data-ttu-id="1e266-110">Wählen Sie in der Liste **Automatisches Failover mithilfe des SQL Server-Spiegelungszeugen aktivieren** eine SQL Server-Instanz aus, die als Zeugenserver für Failoverszenarios dient.</span><span class="sxs-lookup"><span data-stu-id="1e266-110">Select the list **Use SQL Server mirroring witness to enable automatic failover** a SQL Server that will act as the witness server in failover scenarios.</span></span> <span data-ttu-id="1e266-111">Der Zeugenserver spiegelt oder hostet keine Daten für die persistenten Chat Server, sondern stellt sicher, dass nur ein SQL Server in einer gespiegelten Konfiguration zu einem beliebigen Zeitpunkt der aktive SQL Server ist.</span><span class="sxs-lookup"><span data-stu-id="1e266-111">The witness server does not mirror or host data for the Persistent Chat servers, but ensures that only one SQL Server in a mirrored configuration is the active SQL Server at any time.</span></span>
  
<span data-ttu-id="1e266-112">Klicken Sie auf **neu** , um einen neuen SQL Server-Zeugen optional eine Instanz für den beständigen Chat-Sicherungs-SQL Server-Spiegelungs Zeugen zu definieren.</span><span class="sxs-lookup"><span data-stu-id="1e266-112">Click **New** to define a new SQL Server witness optionally an instance for the Persistent Chat backup SQL Server mirroring witness.</span></span>
  
<span data-ttu-id="1e266-113">Klicken Sie auf **Zurück**, um zum vorherigen Dialogfeld für die Pooldefinition zurückzukehren.</span><span class="sxs-lookup"><span data-stu-id="1e266-113">Click **Back** to go back to the previous pool definition dialog.</span></span>
  
<span data-ttu-id="1e266-114">Klicken Sie auf **weiter** , nachdem Sie die Optionen für die Backup-SQL Server-Speicherkonfiguration dieses Pools eingegeben haben, und fahren Sie mit der Server Pool Definition des beständigen Chats fort.</span><span class="sxs-lookup"><span data-stu-id="1e266-114">Click **Next** after you have finished entering the options for this pool's backup SQL Server store configuration and to proceed with the Persistent Chat Server pool definition.</span></span>
  
<span data-ttu-id="1e266-115">Klicken Sie auf **Abbrechen**, um alle Änderungen zu verwerfen und den Assistenten **Neuen Pool für beständigen Chat definieren** zu beenden.</span><span class="sxs-lookup"><span data-stu-id="1e266-115">Click **Cancel** to discard all changes and end the **Define New Persistent Chat Pool** wizard.</span></span>
  
<span data-ttu-id="1e266-116">Klicken Sie auf **Hilfe**, um auf die kontextbezogene Hilfe (z. B. diese Seite) zuzugreifen.</span><span class="sxs-lookup"><span data-stu-id="1e266-116">Click **Help** to access context sensitive help, such as this page.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="1e266-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="1e266-117">See also</span></span>

[<span data-ttu-id="1e266-118">Planen für den Server für beständigen Chat in Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="1e266-118">Plan for Persistent Chat Server in Skype for Business Server 2015</span></span>](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md)
  
[<span data-ttu-id="1e266-119">Server requirements for Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="1e266-119">Server requirements for Skype for Business Server 2015</span></span>](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md)
  
[<span data-ttu-id="1e266-120">Hardware- und Softwareanforderungen an den Server für beständigen Chat in Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="1e266-120">Hardware and software requirements for Persistent Chat Server in Skype for Business Server 2015</span></span>](../../plan-your-deployment/persistent-chat-server/hardware-and-software-requirements.md)
  
[<span data-ttu-id="1e266-121">Konfigurieren der hohen Verfügbarkeit und der Notfallwiederherstellung für Server für beständigen Chat in Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="1e266-121">Configure high availability and disaster recovery for Persistent Chat Server in Skype for Business Server 2015</span></span>](../../deploy/deploy-persistent-chat-server/configure-hadr-for-persistent-chat.md)
