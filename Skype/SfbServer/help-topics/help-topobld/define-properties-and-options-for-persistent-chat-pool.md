---
title: Definieren von Eigenschaften und Optionen für den Pool für beständigen Chat
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/27/2015
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.tb.AddPersistentChatOptionsPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: f4914a44-2113-48f1-8299-4645fc7011b6
description: 'Sie können Optionen für den Serverpool des beständigen Chats oder des beständigen Chats konfigurieren, indem Sie die folgenden Eigenschaften definieren:'
ms.openlocfilehash: 458e50ecc3ddd389a8e413e8f2dd368fc0f15369
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/03/2020
ms.locfileid: "41697550"
---
# <a name="define-properties-and-options-for-persistent-chat-pool"></a><span data-ttu-id="a257b-103">Definieren von Eigenschaften und Optionen für den Pool für beständigen Chat</span><span class="sxs-lookup"><span data-stu-id="a257b-103">Define Properties and Options for Persistent Chat Pool</span></span>
 
<span data-ttu-id="a257b-104">Sie können Optionen für den Serverpool des beständigen Chats oder des beständigen Chats konfigurieren, indem Sie die folgenden Eigenschaften definieren:</span><span class="sxs-lookup"><span data-stu-id="a257b-104">You configure options for your Persistent Chat Server or Persistent Chat Server pool by defining the following properties:</span></span>
  
 <span data-ttu-id="a257b-105">**Anzeigename des beständigen Chat Pools**: eine erforderliche Eigenschaft, die einen benutzerfreundlichen Namen definiert, der für diesen beständigen Chat Server oder den Serverpool für beständigen Chat angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="a257b-105">**Display name of the Persistent Chat pool**: A required property that defines a user friendly name that will be displayed for this Persistent Chat Server or Persistent Chat Server pool.</span></span>
  
 <span data-ttu-id="a257b-106">**Port für beständigen Chat**: eine erforderliche Eigenschaft, die die Portnummer definiert, die dieser beständige Chat Server oder beständiger Chat Serverpool überwacht.</span><span class="sxs-lookup"><span data-stu-id="a257b-106">**Persistent Chat port**: A required property that will define the port number that this Persistent Chat Server or Persistent Chat Server pool will listen on.</span></span>
  
 <span data-ttu-id="a257b-107">**Aktivieren der Kompatibilität**: Aktivieren Sie das Kontrollkästchen, wenn Sie beabsichtigen, das optionale Feature für beständigen Chat und die Datenbank bereitzustellen und zu implementieren.</span><span class="sxs-lookup"><span data-stu-id="a257b-107">**Enable compliance**: Select the check box if you plan to deploy and implement the optional Persistent Chat compliance feature and database.</span></span>
  
 <span data-ttu-id="a257b-108">**Verwenden von Backup-SQL Server-Stores zum Aktivieren der Disaster Recovery**: Aktivieren Sie dieses Kontrollkästchen, wenn Sie beabsichtigen, die Disaster Recovery des beständigen Chats von SQL Server-speichern aus einem konfigurierten Sicherungssatz von speichern auf einem anderen SQL Server bereitzustellen und zu implementieren.</span><span class="sxs-lookup"><span data-stu-id="a257b-108">**Use backup SQL Server stores to enable disaster recovery**: Select this check box if you plan to deploy and implement disaster recovery of the Persistent Chat SQL Server stores from a configured backup set of stores on another SQL Server.</span></span> <span data-ttu-id="a257b-109">Ausführliche Informationen finden Sie unter [Konfigurieren von Höchstverfügbarkeit und Disaster Recovery für beständigen Chat Server in Skype for Business Server 2015](../../deploy/deploy-persistent-chat-server/configure-hadr-for-persistent-chat.md).</span><span class="sxs-lookup"><span data-stu-id="a257b-109">For details, see [Configure high availability and disaster recovery for Persistent Chat Server in Skype for Business Server 2015](../../deploy/deploy-persistent-chat-server/configure-hadr-for-persistent-chat.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="a257b-110">Diese Option ist nur für Pools mit mehreren Servern verfügbar.</span><span class="sxs-lookup"><span data-stu-id="a257b-110">This option is available only for pools with multiple servers.</span></span> 
  
 <span data-ttu-id="a257b-111">**Verwenden Sie diesen Pool als Standard für die \<Website Website, in\>der dieser Server oder Pool konfiguriert ist**: Aktivieren Sie dieses Kontrollkästchen, wenn es sich um den standardmäßigen Chat Server oder den Serverpool für beständigen Chat für die Website handelt.</span><span class="sxs-lookup"><span data-stu-id="a257b-111">**Use this pool as default for the site \<site that this server or pool is being configured in\>**: Select this check box if this will be the default Persistent Chat Server or Persistent Chat Server pool for the site.</span></span> <span data-ttu-id="a257b-112">Sie müssen über einen standardmäßigen beständigen Chat Server oder Pol pro Website verfügen.</span><span class="sxs-lookup"><span data-stu-id="a257b-112">You must have one default Persistent Chat server or pol per site.</span></span>
  
> [!NOTE]
> <span data-ttu-id="a257b-113">Falls die Topologie mehrere Standorte umfasst, wird auch das Kontrollkästchen **Diesen Pool als Standard für alle Standorte verwenden** angezeigt.</span><span class="sxs-lookup"><span data-stu-id="a257b-113">If your topology includes multiple sites, a checkbox for **Use this pool as default for all sites** is also displayed.</span></span>
  
<span data-ttu-id="a257b-114">Klicken Sie auf **Zurück**, um zum vorherigen Dialogfeld für die Pooldefinition zurückzukehren.</span><span class="sxs-lookup"><span data-stu-id="a257b-114">Click **Back** to go back to the previous pool definition dialog.</span></span>
  
<span data-ttu-id="a257b-115">Klicken Sie auf **weiter** , nachdem Sie die Optionen für diesen Pool eingegeben haben, um die Definition des beständigen Chat Server Pools fortzusetzen.</span><span class="sxs-lookup"><span data-stu-id="a257b-115">Click **Next** after you have finished entering the options for this pool to proceed with the Persistent Chat Server pool definition.</span></span>
  
<span data-ttu-id="a257b-116">Klicken Sie auf **Abbrechen**, um alle Änderungen zu verwerfen und den Assistenten **Neuen Pool für beständigen Chat definieren** zu beenden.</span><span class="sxs-lookup"><span data-stu-id="a257b-116">Click **Cancel** to discard all changes and end the **Define New Persistent Chat Pool** wizard.</span></span>
  
<span data-ttu-id="a257b-117">Klicken Sie auf **Hilfe**, um auf die kontextbezogene Hilfe (z. B. diese Seite) zuzugreifen.</span><span class="sxs-lookup"><span data-stu-id="a257b-117">Click **Help** to access context sensitive help, such as this page.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="a257b-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a257b-118">See also</span></span>

[<span data-ttu-id="a257b-119">Planen für den Server für beständigen Chat in Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="a257b-119">Plan for Persistent Chat Server in Skype for Business Server 2015</span></span>](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md)
  
[<span data-ttu-id="a257b-120">Hinzufügen eines beständigen Chat Servers zu Ihrer Skype for Business Server 2015-Topologie</span><span class="sxs-lookup"><span data-stu-id="a257b-120">Add Persistent Chat Server to your Skype for Business Server 2015 topology</span></span>](../../deploy/deploy-persistent-chat-server/add-persistent-chat-server.md)
