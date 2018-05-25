---
title: Hinzufügen des SQL Server-Speichers für den beständigen Chat
ms.author: crowe
author: CarolynRowe
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
ms.openlocfilehash: 062092ff60fa30f7b8ac19725a12a3f62e1b9ec6
ms.sourcegitcommit: e577b4bdf3827fdfaf4482928adde177a64e4406
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/24/2018
---
# <a name="add-persistent-chat-sql-server-store"></a><span data-ttu-id="cc7d0-103">Hinzufügen des SQL Server-Speichers für den beständigen Chat</span><span class="sxs-lookup"><span data-stu-id="cc7d0-103">Add Persistent Chat SQL Server Store</span></span>
 
<span data-ttu-id="cc7d0-104">Konfigurieren Sie die SQL Server-Speicher, die Datenbanken für die Persistent Chat Server oder Pool Persistent Chat Server bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="cc7d0-104">You configure the SQL Server stores that will provide databases for the Persistent Chat Server or Persistent Chat Server pool.</span></span>
  
 <span data-ttu-id="cc7d0-105">**SQL Server-Speicher**: Wählen Sie eine vorhandene SQL Server-Instanz und optional eine Instanz für den beständigen Chat aus.</span><span class="sxs-lookup"><span data-stu-id="cc7d0-105">**SQL Server store**: Select an existing SQL Server and optionally an instance for Persistent Chat.</span></span>
  
<span data-ttu-id="cc7d0-106">Klicken Sie auf **neu** , um eine neue SQL Server-Instanz und optional eine neue Instanz für den beständigen Chat Daten definieren.</span><span class="sxs-lookup"><span data-stu-id="cc7d0-106">Click **New** to define a new SQL Server and optionally a new instance for the Persistent Chat data.</span></span>
  
<span data-ttu-id="cc7d0-107">Aktivieren Sie das Kontrollkästchen **Aktivieren SQL Server-Speicher für Spiegelung** Konfigurieren einer SQL Server-Datenbank und optional eine Instanz, die eine gespiegelte Datenbank für den beständigen Chat Daten bereitgestellt wird.</span><span class="sxs-lookup"><span data-stu-id="cc7d0-107">Select the **Enable SQL Server store mirroring** checkbox to configure a SQL Server database and optional instance that will provide a mirrored database for the Persistent Chat data.</span></span>
  
<span data-ttu-id="cc7d0-108">Wählen Sie in der Liste **SQL Server-Spiegelung Speicher** einen SQL Server und optional eine Instanz als SQL Server-Spiegel für die Persistent Chat SQL Server verwenden.</span><span class="sxs-lookup"><span data-stu-id="cc7d0-108">Select from the list **Mirroring SQL Server store** a SQL Server and optional instance to act as the SQL Server mirror for the Persistent Chat SQL Server.</span></span>
  
<span data-ttu-id="cc7d0-109">Klicken Sie auf **neu** , um eine neue SQL Server-Instanz und optional eine neue Instanz für den beständigen Chat SQL Server-Spiegelung zu definieren.</span><span class="sxs-lookup"><span data-stu-id="cc7d0-109">Click **New** to define a new SQL Server and optionally a new instance for the Persistent Chat SQL Server mirroring.</span></span>
  
<span data-ttu-id="cc7d0-110">Wählen Sie in der Liste **Automatisches Failover mithilfe des SQL Server-Spiegelungszeugen aktivieren** eine SQL Server-Instanz aus, die als Zeugenserver für Failoverszenarios dient.</span><span class="sxs-lookup"><span data-stu-id="cc7d0-110">Select the list **Use SQL Server mirroring witness to enable automatic failover** a SQL Server that will act as the witness server in failover scenarios.</span></span> <span data-ttu-id="cc7d0-111">Der Zeugenserver werden nicht Spiegelung oder Host Daten für den Server für beständigen Chat, sondern wird sichergestellt, dass nur eine SQL Server in einer gespiegelten Konfiguration können Sie jederzeit die aktiven SQL Server ist.</span><span class="sxs-lookup"><span data-stu-id="cc7d0-111">The witness server does not mirror or host data for the Persistent Chat servers, but ensures that only one SQL Server in a mirrored configuration is the active SQL Server at any time.</span></span>
  
<span data-ttu-id="cc7d0-112">Klicken Sie auf **neu** , um einen neuen SQL Server-Zeugen optional eine Instanz für den beständigen Chat SQL Server-spiegelungszeugen zu definieren.</span><span class="sxs-lookup"><span data-stu-id="cc7d0-112">Click **New** to define a new SQL Server witness optionally an instance for the Persistent Chat SQL Server mirroring witness.</span></span>
  
<span data-ttu-id="cc7d0-113">Klicken Sie auf **Zurück**, um zum vorherigen Dialogfeld für die Pooldefinition zurückzukehren.</span><span class="sxs-lookup"><span data-stu-id="cc7d0-113">Click **Back** to go back to the previous pool definition dialog.</span></span>
  
<span data-ttu-id="cc7d0-114">Klicken Sie auf **Weiter** , nachdem Sie die Eingabe der Optionen für die Konfiguration zum Speichern von SQL Server des Pools und Fortfahren mit der Definition der Persistent Chat Server Pool abgeschlossen haben.</span><span class="sxs-lookup"><span data-stu-id="cc7d0-114">Click **Next** after you have finished entering the options for this pool's SQL Server store configuration and to proceed with the Persistent Chat Server pool definition.</span></span>
  
<span data-ttu-id="cc7d0-115">Klicken Sie auf **Abbrechen**, um alle Änderungen zu verwerfen und den Assistenten **Neuen Pool für beständigen Chat definieren** zu beenden.</span><span class="sxs-lookup"><span data-stu-id="cc7d0-115">Click **Cancel** to discard all changes and end the **Define New Persistent Chat Pool** wizard.</span></span>
  
<span data-ttu-id="cc7d0-116">Klicken Sie auf **Hilfe**, um auf die kontextbezogene Hilfe (z. B. diese Seite) zuzugreifen.</span><span class="sxs-lookup"><span data-stu-id="cc7d0-116">Click **Help** to access context sensitive help, such as this page.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="cc7d0-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="cc7d0-117">See also</span></span>

#### 

[<span data-ttu-id="cc7d0-118">Planen Sie für Persistent Chatserver in Skype für Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="cc7d0-118">Plan for Persistent Chat Server in Skype for Business Server 2015</span></span>](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md)
  
[<span data-ttu-id="cc7d0-119">Hinzufügen von Persistent Chat Server zu Ihrer Skype für Business Server 2015 Topologie</span><span class="sxs-lookup"><span data-stu-id="cc7d0-119">Add Persistent Chat Server to your Skype for Business Server 2015 topology</span></span>](../../deploy/deploy-persistent-chat-server/add-persistent-chat-server.md)
  
[<span data-ttu-id="cc7d0-120">Hardware und Software-Anforderungen für Persistent Chat Server in Skype für Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="cc7d0-120">Hardware and software requirements for Persistent Chat Server in Skype for Business Server 2015</span></span>](../../plan-your-deployment/persistent-chat-server/hardware-and-software-requirements.md)
  
[<span data-ttu-id="cc7d0-121">Serveranforderungen für Skype für Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="cc7d0-121">Server requirements for Skype for Business Server 2015</span></span>](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md)
  
[<span data-ttu-id="cc7d0-122">Topologiegrundlagen Skype für Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="cc7d0-122">Topology Basics for Skype for Business Server 2015</span></span>](../../plan-your-deployment/topology-basics/topology-basics.md)
  
[<span data-ttu-id="cc7d0-123">Konfigurieren von hoher Verfügbarkeit und notfallwiederherstellung für Persistent Chat Server in Skype Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="cc7d0-123">Configure high availability and disaster recovery for Persistent Chat Server in Skype for Business Server 2015</span></span>](../../deploy/deploy-persistent-chat-server/configure-hadr-for-persistent-chat.md)

