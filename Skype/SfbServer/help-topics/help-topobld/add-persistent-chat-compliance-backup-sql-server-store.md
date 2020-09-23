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
# <a name="add-persistent-chat-compliance-backup-sql-server-store"></a><span data-ttu-id="1c2f4-103">Hinzufügen des SQL Server-Konformitätssicherungsspeichers für den beständigen Chat</span><span class="sxs-lookup"><span data-stu-id="1c2f4-103">Add Persistent Chat Compliance Backup SQL Server Store</span></span>
 
<span data-ttu-id="1c2f4-104">Sie konfigurieren die Sicherungsrichtlinien SQL Server Speicher, die Sicherungsdatenbanken für den Server für beständigen Chat oder für die Einhaltung SQL Server Speichers für beständigen Chat bereitstellen sollen.</span><span class="sxs-lookup"><span data-stu-id="1c2f4-104">You configure the Backup compliance SQL Server stores that will provide backup databases for the Persistent Chat Server or Persistent Chat Server compliance SQL Server stores.</span></span>
  
 <span data-ttu-id="1c2f4-105">**SQL Server Speicher**: Wählen Sie eine vorhandene SQL Server und optional eine Instanz für den beständigen Chat aus.</span><span class="sxs-lookup"><span data-stu-id="1c2f4-105">**SQL Server store**: Select an existing SQL Server and optionally an instance for Persistent Chat.</span></span>
  
<span data-ttu-id="1c2f4-106">Klicken Sie auf **neu** , um eine neue SQL Server und optional eine neue Instanz für die Sicherungs Konformitätsdaten der persistent Chat-Sicherung zu definieren.</span><span class="sxs-lookup"><span data-stu-id="1c2f4-106">Click **New** to define a new SQL Server and optionally a new instance for the Persistent Chat backup compliance data.</span></span>
  
<span data-ttu-id="1c2f4-107">Aktivieren Sie das Kontrollkästchen **SQL Server Speicherspiegelung aktivieren** , um eine SQL Server Datenbank und optionale Instanz zu konfigurieren, die eine gespiegelte Datenbank für die Sicherungs Konformitätsdaten für den persistent Chat bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="1c2f4-107">Select the **Enable SQL Server store mirroring** checkbox to configure a SQL Server database and optional instance that will provide a mirrored database for the Persistent Chat backup compliance data.</span></span>
  
<span data-ttu-id="1c2f4-108">Wählen Sie im Listen **Spiegelungs SQL Server** eine SQL Server und optionale Instanz aus, die als SQL Server Spiegel für die Compliance-SQL Server für die Sicherung der persistenten Chats fungiert.</span><span class="sxs-lookup"><span data-stu-id="1c2f4-108">Select from the list **Mirroring SQL Server store** a SQL Server and optional instance to act as the SQL Server mirror for the Persistent Chat backup compliance SQL Server.</span></span>
  
<span data-ttu-id="1c2f4-109">Klicken Sie auf **neu** , um eine neue SQL Server und optional eine neue Instanz für den beständigen Chat SQL Server Spiegelung zu definieren.</span><span class="sxs-lookup"><span data-stu-id="1c2f4-109">Click **New** to define a new SQL Server and optionally a new instance for the Persistent Chat SQL Server mirroring.</span></span>
  
<span data-ttu-id="1c2f4-110">Wählen Sie in der Liste **Automatisches Failover mithilfe des SQL Server-Spiegelungszeugen aktivieren** eine SQL Server-Instanz aus, die als Zeugenserver für Failoverszenarios dient.</span><span class="sxs-lookup"><span data-stu-id="1c2f4-110">Select the list **Use SQL Server mirroring witness to enable automatic failover** a SQL Server that will act as the witness server in failover scenarios.</span></span> <span data-ttu-id="1c2f4-111">Der Zeugenserver spiegelt oder hostet keine Daten für die Server für beständigen Chat, sondern stellt sicher, dass jeweils nur ein SQL Server in einer gespiegelten Konfiguration der aktive SQL Server ist.</span><span class="sxs-lookup"><span data-stu-id="1c2f4-111">The witness server does not mirror or host data for the Persistent Chat servers, but ensures that only one SQL Server in a mirrored configuration is the active SQL Server at any time.</span></span>
  
<span data-ttu-id="1c2f4-112">Klicken Sie auf **neu** , um einen neuen SQL Server Zeugen optional eine Instanz für die Sicherungs Konformität für beständigen Chat SQL Server Spiegelungs Zeugen zu definieren.</span><span class="sxs-lookup"><span data-stu-id="1c2f4-112">Click **New** to define a new SQL Server witness optionally an instance for the Persistent Chat backup compliance SQL Server mirroring witness.</span></span>
  
<span data-ttu-id="1c2f4-113">Klicken Sie auf **Zurück**, um zum vorherigen Dialogfeld für die Pooldefinition zurückzukehren.</span><span class="sxs-lookup"><span data-stu-id="1c2f4-113">Click **Back** to go back to the previous pool definition dialog.</span></span>
  
<span data-ttu-id="1c2f4-114">Klicken Sie auf **weiter** , nachdem Sie die Eingabe der Optionen für die Sicherung SQL Server Speicherkonfiguration dieses Pools abgeschlossen haben, und fahren Sie mit der Definition des Server Pools für beständigen Chat fort.</span><span class="sxs-lookup"><span data-stu-id="1c2f4-114">Click **Next** after you have finished entering the options for this pool's backup SQL Server store configuration and to proceed with the Persistent Chat Server pool definition.</span></span>
  
<span data-ttu-id="1c2f4-115">Klicken Sie auf **Abbrechen**, um alle Änderungen zu verwerfen und den Assistenten **Neuen Pool für beständigen Chat definieren** zu beenden.</span><span class="sxs-lookup"><span data-stu-id="1c2f4-115">Click **Cancel** to discard all changes and end the **Define New Persistent Chat Pool** wizard.</span></span>
  
<span data-ttu-id="1c2f4-116">Klicken Sie auf **Hilfe**, um auf die kontextbezogene Hilfe (z. B. diese Seite) zuzugreifen.</span><span class="sxs-lookup"><span data-stu-id="1c2f4-116">Click **Help** to access context sensitive help, such as this page.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="1c2f4-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="1c2f4-117">See also</span></span>

[<span data-ttu-id="1c2f4-118">Planen des Servers für beständigen Chat in Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="1c2f4-118">Plan for Persistent Chat Server in Skype for Business Server 2015</span></span>](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md)
  
[<span data-ttu-id="1c2f4-119">Server Anforderungen für Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="1c2f4-119">Server requirements for Skype for Business Server 2015</span></span>](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md)
  
[<span data-ttu-id="1c2f4-120">Hardware-und Softwareanforderungen für den Server für beständigen Chat in Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="1c2f4-120">Hardware and software requirements for Persistent Chat Server in Skype for Business Server 2015</span></span>](../../plan-your-deployment/persistent-chat-server/hardware-and-software-requirements.md)
  
[<span data-ttu-id="1c2f4-121">Konfigurieren des Kompatibilitätsdiensts für den Server für beständigen Chat in Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="1c2f4-121">Configure the Compliance service for Persistent Chat Server in Skype for Business Server 2015</span></span>](../../manage/persistent-chat/configure-compliance.md)
  
[<span data-ttu-id="1c2f4-122">Konfigurieren der hohen Verfügbarkeit und der Notfallwiederherstellung für den Server für beständigen Chat in Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="1c2f4-122">Configure high availability and disaster recovery for Persistent Chat Server in Skype for Business Server 2015</span></span>](../../deploy/deploy-persistent-chat-server/configure-hadr-for-persistent-chat.md)
