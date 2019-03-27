---
title: Hinzufügen des SQL Server-Speichers für Konformität für den beständigen Chat
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/27/2015
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddPersistentChatComplianceStorePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b9771b53-e19a-4a12-bf01-24bae6f7e482
description: Konfigurieren Sie die Konformität, den, die SQL Server-Speicher, die Datenbanken für die Persistent Chat Server oder die Funktion zur Einhaltung von Persistent Chat Server bereitgestellt werden.
ms.openlocfilehash: 46b8052409bcb65a828bd07ebbec72d3b84c0962
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/27/2019
ms.locfileid: "30883074"
---
# <a name="add-persistent-chat-compliance-sql-server-store"></a><span data-ttu-id="8a92f-103">Hinzufügen des SQL Server-Speichers für Konformität für den beständigen Chat</span><span class="sxs-lookup"><span data-stu-id="8a92f-103">Add Persistent Chat Compliance SQL Server Store</span></span>
 
<span data-ttu-id="8a92f-104">Konfigurieren Sie die Konformität, den, die SQL Server-Speicher, die Datenbanken für die Persistent Chat Server oder die Funktion zur Einhaltung von Persistent Chat Server bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="8a92f-104">You configure the compliance SQL Server stores that will provide databases for the Persistent Chat Server or Persistent Chat Server compliance feature.</span></span>
  
 <span data-ttu-id="8a92f-105">**SQL Server-Speicher**: Wählen Sie eine vorhandene SQL Server-Instanz und optional eine Instanz für den beständigen Chat aus.</span><span class="sxs-lookup"><span data-stu-id="8a92f-105">**SQL Server store**: Select an existing SQL Server and optionally an instance for Persistent Chat.</span></span>
  
<span data-ttu-id="8a92f-106">Klicken Sie auf **neu** , um eine neue SQL Server-Instanz und optional eine neue Instanz für die Konformitätsdaten beständigen Chat definieren.</span><span class="sxs-lookup"><span data-stu-id="8a92f-106">Click **New** to define a new SQL Server and optionally a new instance for the Persistent Chat compliance data.</span></span>
  
<span data-ttu-id="8a92f-107">Aktivieren Sie das Kontrollkästchen **Aktivieren SQL Server-Speicher für Spiegelung** Konfigurieren einer SQL Server-Datenbank und optional eine Instanz, die eine gespiegelte Datenbank für die Konformitätsdaten beständigen Chat bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="8a92f-107">Select the **Enable SQL Server store mirroring** checkbox to configure a SQL Server database and optional instance that will provide a mirrored database for the Persistent Chat compliance data.</span></span>
  
<span data-ttu-id="8a92f-108">Wählen Sie in der Liste **SQL Server-Spiegelung Speicher** einen SQL Server und optional eine Instanz, die als SQL Server-Spiegel für die Konformität des beständigen Chats SQL Server fungiert.</span><span class="sxs-lookup"><span data-stu-id="8a92f-108">Select from the list **Mirroring SQL Server store** a SQL Server and optional instance to act as the SQL Server mirror for the Persistent Chat compliance SQL Server.</span></span>
  
<span data-ttu-id="8a92f-109">Klicken Sie auf **neu** , um eine neue SQL Server-Instanz und optional eine neue Instanz für den beständigen Chat SQL Server-Spiegelung zu definieren.</span><span class="sxs-lookup"><span data-stu-id="8a92f-109">Click **New** to define a new SQL Server and optionally a new instance for the Persistent Chat SQL Server mirroring.</span></span>
  
<span data-ttu-id="8a92f-110">Wählen Sie in der Liste **Automatisches Failover mithilfe des SQL Server-Spiegelungszeugen aktivieren** eine SQL Server-Instanz aus, die als Zeugenserver für Failoverszenarios dient.</span><span class="sxs-lookup"><span data-stu-id="8a92f-110">Select the list **Use SQL Server mirroring witness to enable automatic failover** a SQL Server that will act as the witness server in failover scenarios.</span></span> <span data-ttu-id="8a92f-111">Der Zeugenserver werden nicht Spiegelung oder Host Daten für den Server für beständigen Chat, sondern wird sichergestellt, dass nur eine SQL Server in einer gespiegelten Konfiguration können Sie jederzeit die aktiven SQL Server ist.</span><span class="sxs-lookup"><span data-stu-id="8a92f-111">The witness server does not mirror or host data for the Persistent Chat servers, but ensures that only one SQL Server in a mirrored configuration is the active SQL Server at any time.</span></span>
  
<span data-ttu-id="8a92f-112">Klicken Sie auf **neu** , um einen neuen SQL Server-Zeugen definieren optional eine Instanz für die Konformität des beständigen Chats SQL Server-spiegelungszeugen.</span><span class="sxs-lookup"><span data-stu-id="8a92f-112">Click **New** to define a new SQL Server witness optionally an instance for the Persistent Chat compliance SQL Server mirroring witness.</span></span>
  
<span data-ttu-id="8a92f-113">Klicken Sie auf **Zurück**, um zum vorherigen Dialogfeld für die Pooldefinition zurückzukehren.</span><span class="sxs-lookup"><span data-stu-id="8a92f-113">Click **Back** to go back to the previous pool definition dialog.</span></span>
  
<span data-ttu-id="8a92f-114">Klicken Sie auf **Weiter** , nachdem Sie die Eingabe der Optionen für diesen Pool backup SQL Server-Speicher-Konfiguration und Fortfahren mit der Definition der Persistent Chat Server Pool abgeschlossen haben.</span><span class="sxs-lookup"><span data-stu-id="8a92f-114">Click **Next** after you have finished entering the options for this pool's backup SQL Server store configuration and to proceed with the Persistent Chat Server pool definition.</span></span>
  
<span data-ttu-id="8a92f-115">Klicken Sie auf **Abbrechen**, um alle Änderungen zu verwerfen und den Assistenten **Neuen Pool für beständigen Chat definieren** zu beenden.</span><span class="sxs-lookup"><span data-stu-id="8a92f-115">Click **Cancel** to discard all changes and end the **Define New Persistent Chat Pool** wizard.</span></span>
  
<span data-ttu-id="8a92f-116">Klicken Sie auf **Hilfe**, um auf die kontextbezogene Hilfe (z. B. diese Seite) zuzugreifen.</span><span class="sxs-lookup"><span data-stu-id="8a92f-116">Click **Help** to access context sensitive help, such as this page.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="8a92f-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="8a92f-117">See also</span></span>

[<span data-ttu-id="8a92f-118">Planen für den Server für beständigen Chat in Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="8a92f-118">Plan for Persistent Chat Server in Skype for Business Server 2015</span></span>](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md)
  
[<span data-ttu-id="8a92f-119">Server requirements for Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="8a92f-119">Server requirements for Skype for Business Server 2015</span></span>](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md)
  
[<span data-ttu-id="8a92f-120">Hardware- und Softwareanforderungen an den Server für beständigen Chat in Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="8a92f-120">Hardware and software requirements for Persistent Chat Server in Skype for Business Server 2015</span></span>](../../plan-your-deployment/persistent-chat-server/hardware-and-software-requirements.md)
  
[<span data-ttu-id="8a92f-121">Konfigurieren des Kompatibilitätsdienstes auf dem Server für beständigen Chat in Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="8a92f-121">Configure the Compliance service for Persistent Chat Server in Skype for Business Server 2015</span></span>](../../manage/persistent-chat/configure-compliance.md)
