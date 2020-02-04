---
title: Hinzufügen des SQL Server-Speichers für den beständigen Chat
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/27/2015
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.tb.AddPersistentChatSqlStorePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c8e6064a-8127-4c25-8685-06f49d8bbfce
description: Sie konfigurieren die SQL Server-Speicher, die Datenbanken für den beständigen Chat Server oder den Serverpool für beständigen Chat bereitstellen.
ms.openlocfilehash: 794ad4a1b5427fab7a8409fbbbd76448c33e918e
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/03/2020
ms.locfileid: "41685058"
---
# <a name="add-persistent-chat-sql-server-store"></a><span data-ttu-id="a946e-103">Hinzufügen des SQL Server-Speichers für den beständigen Chat</span><span class="sxs-lookup"><span data-stu-id="a946e-103">Add Persistent Chat SQL Server Store</span></span>
 
<span data-ttu-id="a946e-104">Sie konfigurieren die SQL Server-Speicher, die Datenbanken für den beständigen Chat Server oder den Serverpool für beständigen Chat bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="a946e-104">You configure the SQL Server stores that will provide databases for the Persistent Chat Server or Persistent Chat Server pool.</span></span>
  
 <span data-ttu-id="a946e-105">**SQL Server Store**: Wählen Sie einen vorhandenen SQL Server und optional eine Instanz für beständigen Chat aus.</span><span class="sxs-lookup"><span data-stu-id="a946e-105">**SQL Server store**: Select an existing SQL Server and optionally an instance for Persistent Chat.</span></span>
  
<span data-ttu-id="a946e-106">Klicken Sie auf **neu** , um einen neuen SQL Server und optional eine neue Instanz für die persistenten Chat Daten zu definieren.</span><span class="sxs-lookup"><span data-stu-id="a946e-106">Click **New** to define a new SQL Server and optionally a new instance for the Persistent Chat data.</span></span>
  
<span data-ttu-id="a946e-107">Aktivieren Sie das Kontrollkästchen **Spiegelung des SQL Server-Speichers aktivieren** , um eine SQL Server-Datenbank und eine optionale Instanz zu konfigurieren, die eine gespiegelte Datenbank für die persistenten Chat-Daten bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="a946e-107">Select the **Enable SQL Server store mirroring** checkbox to configure a SQL Server database and optional instance that will provide a mirrored database for the Persistent Chat data.</span></span>
  
<span data-ttu-id="a946e-108">Wählen Sie aus der Liste **Spiegelungs-SQL Server Store** eine SQL Server-und eine optionale Instanz aus, die als SQL Server-Spiegelung für den beständigen Chat SQL Server fungieren soll.</span><span class="sxs-lookup"><span data-stu-id="a946e-108">Select from the list **Mirroring SQL Server store** a SQL Server and optional instance to act as the SQL Server mirror for the Persistent Chat SQL Server.</span></span>
  
<span data-ttu-id="a946e-109">Klicken Sie auf **neu** , um einen neuen SQL Server und optional eine neue Instanz für die SQL Server-Spiegelung des beständigen Chats zu definieren.</span><span class="sxs-lookup"><span data-stu-id="a946e-109">Click **New** to define a new SQL Server and optionally a new instance for the Persistent Chat SQL Server mirroring.</span></span>
  
<span data-ttu-id="a946e-110">Wählen Sie in der Liste **Automatisches Failover mithilfe des SQL Server-Spiegelungszeugen aktivieren** eine SQL Server-Instanz aus, die als Zeugenserver für Failoverszenarios dient.</span><span class="sxs-lookup"><span data-stu-id="a946e-110">Select the list **Use SQL Server mirroring witness to enable automatic failover** a SQL Server that will act as the witness server in failover scenarios.</span></span> <span data-ttu-id="a946e-111">Der Zeugenserver spiegelt oder hostet keine Daten für die persistenten Chat Server, sondern stellt sicher, dass nur ein SQL Server in einer gespiegelten Konfiguration zu einem beliebigen Zeitpunkt der aktive SQL Server ist.</span><span class="sxs-lookup"><span data-stu-id="a946e-111">The witness server does not mirror or host data for the Persistent Chat servers, but ensures that only one SQL Server in a mirrored configuration is the active SQL Server at any time.</span></span>
  
<span data-ttu-id="a946e-112">Klicken Sie auf **neu** , um einen neuen SQL Server-Zeugen optional eine Instanz für den SQL Server-Spiegelungs Zeugen für beständigen Chat zu definieren.</span><span class="sxs-lookup"><span data-stu-id="a946e-112">Click **New** to define a new SQL Server witness optionally an instance for the Persistent Chat SQL Server mirroring witness.</span></span>
  
<span data-ttu-id="a946e-113">Klicken Sie auf **Zurück**, um zum vorherigen Dialogfeld für die Pooldefinition zurückzukehren.</span><span class="sxs-lookup"><span data-stu-id="a946e-113">Click **Back** to go back to the previous pool definition dialog.</span></span>
  
<span data-ttu-id="a946e-114">Klicken Sie auf **weiter** , nachdem Sie die Optionen für die SQL Server Store-Konfiguration dieses Pools eingegeben haben, und fahren Sie mit der Definition des beständigen Chat-Server Pools fort.</span><span class="sxs-lookup"><span data-stu-id="a946e-114">Click **Next** after you have finished entering the options for this pool's SQL Server store configuration and to proceed with the Persistent Chat Server pool definition.</span></span>
  
<span data-ttu-id="a946e-115">Klicken Sie auf **Abbrechen**, um alle Änderungen zu verwerfen und den Assistenten **Neuen Pool für beständigen Chat definieren** zu beenden.</span><span class="sxs-lookup"><span data-stu-id="a946e-115">Click **Cancel** to discard all changes and end the **Define New Persistent Chat Pool** wizard.</span></span>
  
<span data-ttu-id="a946e-116">Klicken Sie auf **Hilfe**, um auf die kontextbezogene Hilfe (z. B. diese Seite) zuzugreifen.</span><span class="sxs-lookup"><span data-stu-id="a946e-116">Click **Help** to access context sensitive help, such as this page.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="a946e-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a946e-117">See also</span></span>

[<span data-ttu-id="a946e-118">Planen für den Server für beständigen Chat in Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="a946e-118">Plan for Persistent Chat Server in Skype for Business Server 2015</span></span>](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md)
  
[<span data-ttu-id="a946e-119">Hinzufügen eines beständigen Chat Servers zu Ihrer Skype for Business Server 2015-Topologie</span><span class="sxs-lookup"><span data-stu-id="a946e-119">Add Persistent Chat Server to your Skype for Business Server 2015 topology</span></span>](../../deploy/deploy-persistent-chat-server/add-persistent-chat-server.md)
  
[<span data-ttu-id="a946e-120">Hardware- und Softwareanforderungen an den Server für beständigen Chat in Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="a946e-120">Hardware and software requirements for Persistent Chat Server in Skype for Business Server 2015</span></span>](../../plan-your-deployment/persistent-chat-server/hardware-and-software-requirements.md)
  
[<span data-ttu-id="a946e-121">Server requirements for Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="a946e-121">Server requirements for Skype for Business Server 2015</span></span>](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md)
  
[<span data-ttu-id="a946e-122">Topologiegrundlagen in Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="a946e-122">Topology Basics for Skype for Business Server 2015</span></span>](../../plan-your-deployment/topology-basics/topology-basics.md)
  
[<span data-ttu-id="a946e-123">Konfigurieren der hohen Verfügbarkeit und der Notfallwiederherstellung für Server für beständigen Chat in Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="a946e-123">Configure high availability and disaster recovery for Persistent Chat Server in Skype for Business Server 2015</span></span>](../../deploy/deploy-persistent-chat-server/configure-hadr-for-persistent-chat.md)
