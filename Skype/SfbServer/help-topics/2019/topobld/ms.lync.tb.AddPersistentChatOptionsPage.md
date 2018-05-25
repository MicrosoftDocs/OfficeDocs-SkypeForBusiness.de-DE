---
title: Definieren von Eigenschaften und Optionen für den Pool für beständigen Chat
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/27/2015
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddPersistentChatOptionsPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: f4914a44-2113-48f1-8299-4645fc7011b6
description: 'Konfigurieren Sie Optionen für den beständigen Chat-Server oder Persistent Chat Server Pool, durch die folgenden Eigenschaften definieren:'
ms.openlocfilehash: 445e84b4be0567b63b9a56a7bc130e584a826430
ms.sourcegitcommit: e577b4bdf3827fdfaf4482928adde177a64e4406
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/24/2018
---
# <a name="define-properties-and-options-for-persistent-chat-pool"></a><span data-ttu-id="a7f7a-103">Definieren von Eigenschaften und Optionen für den Pool für beständigen Chat</span><span class="sxs-lookup"><span data-stu-id="a7f7a-103">Define Properties and Options for Persistent Chat Pool</span></span>
 
<span data-ttu-id="a7f7a-104">Konfigurieren Sie Optionen für den beständigen Chat-Server oder Persistent Chat Server Pool, durch die folgenden Eigenschaften definieren:</span><span class="sxs-lookup"><span data-stu-id="a7f7a-104">You configure options for your Persistent Chat Server or Persistent Chat Server pool by defining the following properties:</span></span>
  
 <span data-ttu-id="a7f7a-105">**Anzeigename des Pools für den beständigen Chat**: eine erforderliche Eigenschaft, die einen benutzerfreundlichen Namen definiert, die für diesen Persistent Chat Server oder Pool Persistent Chat Server angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="a7f7a-105">**Display name of the Persistent Chat pool**: A required property that defines a user friendly name that will be displayed for this Persistent Chat Server or Persistent Chat Server pool.</span></span>
  
 <span data-ttu-id="a7f7a-106">**Port für beständigen Chat**: eine erforderliche Eigenschaft, die definieren, den Port number, die diese Persistent Chat-Server oder Pool Persistent Chat Server überwacht wird.</span><span class="sxs-lookup"><span data-stu-id="a7f7a-106">**Persistent Chat port**: A required property that will define the port number that this Persistent Chat Server or Persistent Chat Server pool will listen on.</span></span>
  
 <span data-ttu-id="a7f7a-107">**Konformität aktivieren**: Aktivieren Sie das Kontrollkästchen, wenn Sie planen, bereitstellen und implementieren Sie die optionale Funktion für beständigen Chat Compliance und die Datenbank.</span><span class="sxs-lookup"><span data-stu-id="a7f7a-107">**Enable compliance**: Select the check box if you plan to deploy and implement the optional Persistent Chat compliance feature and database.</span></span>
  
 <span data-ttu-id="a7f7a-108">**Sicherung mithilfe von SQL Server gespeichert werden, um Disaster Recovery zu aktivieren**: Aktivieren Sie dieses Kontrollkästchen, wenn Sie planen, bereitstellen und Implementieren von Wiederherstellung des beständigen Chat SQL-Servers aus einem konfigurierten Sicherungssatz auf einem anderen SQL Server-Speicher gespeichert werden.</span><span class="sxs-lookup"><span data-stu-id="a7f7a-108">**Use backup SQL Server stores to enable disaster recovery**: Select this check box if you plan to deploy and implement disaster recovery of the Persistent Chat SQL Server stores from a configured backup set of stores on another SQL Server.</span></span> <span data-ttu-id="a7f7a-109">Weitere Informationen hierzu finden Sie unter [Configure hohe Verfügbarkeit und notfallwiederherstellung für Persistent Chat Server in Skype für Business Server 2015](../../deploy/deploy-persistent-chat-server/configure-hadr-for-persistent-chat.md).</span><span class="sxs-lookup"><span data-stu-id="a7f7a-109">For details, see [Configure high availability and disaster recovery for Persistent Chat Server in Skype for Business Server 2015](../../deploy/deploy-persistent-chat-server/configure-hadr-for-persistent-chat.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="a7f7a-110">Diese Option ist nur für Pools mit mehreren Servern verfügbar.</span><span class="sxs-lookup"><span data-stu-id="a7f7a-110">This option is available only for pools with multiple servers.</span></span> 
  
 <span data-ttu-id="a7f7a-111">**Verwenden Sie diesen Pool als Standard für diese Website \<Website, die in diesen Server oder Pool konfiguriert wird\>**: Aktivieren Sie dieses Kontrollkästchen, wenn dies die standardmäßigen Persistent Chat Server oder Pool von Persistent Chat Server für die Website sein wird.</span><span class="sxs-lookup"><span data-stu-id="a7f7a-111">**Use this pool as default for the site \<site that this server or pool is being configured in\>**: Select this check box if this will be the default Persistent Chat Server or Persistent Chat Server pool for the site.</span></span> <span data-ttu-id="a7f7a-112">Sie müssen einen Standardwert beständigen Chat-Server oder Pol pro Website verfügen.</span><span class="sxs-lookup"><span data-stu-id="a7f7a-112">You must have one default Persistent Chat server or pol per site.</span></span>
  
> [!NOTE]
> <span data-ttu-id="a7f7a-113">Falls die Topologie mehrere Standorte umfasst, wird auch das Kontrollkästchen **Diesen Pool als Standard für alle Standorte verwenden** angezeigt.</span><span class="sxs-lookup"><span data-stu-id="a7f7a-113">If your topology includes multiple sites, a checkbox for **Use this pool as default for all sites** is also displayed.</span></span>
  
<span data-ttu-id="a7f7a-114">Klicken Sie auf **Zurück**, um zum vorherigen Dialogfeld für die Pooldefinition zurückzukehren.</span><span class="sxs-lookup"><span data-stu-id="a7f7a-114">Click **Back** to go back to the previous pool definition dialog.</span></span>
  
<span data-ttu-id="a7f7a-115">Klicken Sie auf **Weiter** , klicken Sie nach Eingabe der Optionen für diesen Pool aus, um mit der Definition von Persistent Chat Server Pool fortzufahren.</span><span class="sxs-lookup"><span data-stu-id="a7f7a-115">Click **Next** after you have finished entering the options for this pool to proceed with the Persistent Chat Server pool definition.</span></span>
  
<span data-ttu-id="a7f7a-116">Klicken Sie auf **Abbrechen**, um alle Änderungen zu verwerfen und den Assistenten **Neuen Pool für beständigen Chat definieren** zu beenden.</span><span class="sxs-lookup"><span data-stu-id="a7f7a-116">Click **Cancel** to discard all changes and end the **Define New Persistent Chat Pool** wizard.</span></span>
  
<span data-ttu-id="a7f7a-117">Klicken Sie auf **Hilfe**, um auf die kontextbezogene Hilfe (z. B. diese Seite) zuzugreifen.</span><span class="sxs-lookup"><span data-stu-id="a7f7a-117">Click **Help** to access context sensitive help, such as this page.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="a7f7a-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a7f7a-118">See also</span></span>

#### 

[<span data-ttu-id="a7f7a-119">Planen Sie für Persistent Chatserver in Skype für Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="a7f7a-119">Plan for Persistent Chat Server in Skype for Business Server 2015</span></span>](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md)
  
[<span data-ttu-id="a7f7a-120">Hinzufügen von Persistent Chat Server zu Ihrer Skype für Business Server 2015 Topologie</span><span class="sxs-lookup"><span data-stu-id="a7f7a-120">Add Persistent Chat Server to your Skype for Business Server 2015 topology</span></span>](../../deploy/deploy-persistent-chat-server/add-persistent-chat-server.md)

