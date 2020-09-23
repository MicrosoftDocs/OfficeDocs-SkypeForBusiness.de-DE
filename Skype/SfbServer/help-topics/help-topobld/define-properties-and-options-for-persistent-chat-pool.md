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
- CSH
ms.custom:
- ms.lync.tb.AddPersistentChatOptionsPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: f4914a44-2113-48f1-8299-4645fc7011b6
description: 'Sie können Optionen für den Serverpool für beständigen Chat oder für beständigen Chat konfigurieren, indem Sie die folgenden Eigenschaften definieren:'
ms.openlocfilehash: 8d3cef04d7089ffff640740bb048ca52cf7fd91e
ms.sourcegitcommit: c69ab11b701a4833179b8479bc3204dfd4412096
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/23/2020
ms.locfileid: "48218546"
---
# <a name="define-properties-and-options-for-persistent-chat-pool"></a><span data-ttu-id="ce33a-103">Definieren von Eigenschaften und Optionen für den Pool für beständigen Chat</span><span class="sxs-lookup"><span data-stu-id="ce33a-103">Define Properties and Options for Persistent Chat Pool</span></span>
 
<span data-ttu-id="ce33a-104">Sie können Optionen für den Serverpool für beständigen Chat oder für beständigen Chat konfigurieren, indem Sie die folgenden Eigenschaften definieren:</span><span class="sxs-lookup"><span data-stu-id="ce33a-104">You configure options for your Persistent Chat Server or Persistent Chat Server pool by defining the following properties:</span></span>
  
 <span data-ttu-id="ce33a-105">**Anzeigename des Pools für beständigen Chat**: eine erforderliche Eigenschaft, die einen benutzerfreundlichen Namen definiert, der für diesen persistent Chat Server oder den Serverpool für beständigen Chat angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="ce33a-105">**Display name of the Persistent Chat pool**: A required property that defines a user friendly name that will be displayed for this Persistent Chat Server or Persistent Chat Server pool.</span></span>
  
 <span data-ttu-id="ce33a-106">**Port für beständigen Chat**: eine erforderliche Eigenschaft, mit der die Portnummer definiert wird, die von diesem Serverpool für beständigen Chat oder beständiger Chat überwacht wird.</span><span class="sxs-lookup"><span data-stu-id="ce33a-106">**Persistent Chat port**: A required property that will define the port number that this Persistent Chat Server or Persistent Chat Server pool will listen on.</span></span>
  
 <span data-ttu-id="ce33a-107">**Kompatibilität aktivieren**: Aktivieren Sie das Kontrollkästchen, wenn Sie das optionale Feature für beständigen Chat und die Datenbank bereitstellen und implementieren möchten.</span><span class="sxs-lookup"><span data-stu-id="ce33a-107">**Enable compliance**: Select the check box if you plan to deploy and implement the optional Persistent Chat compliance feature and database.</span></span>
  
 <span data-ttu-id="ce33a-108">**Verwenden von Sicherungs SQL Server speichern zum Aktivieren der Notfallwiederherstellung**: Aktivieren Sie dieses Kontrollkästchen, wenn Sie die Notfallwiederherstellung des beständigen Chats SQL Server speichern aus einem konfigurierten Sicherungssatzes von Speichern in einem anderen SQL Server bereitstellen und implementieren möchten.</span><span class="sxs-lookup"><span data-stu-id="ce33a-108">**Use backup SQL Server stores to enable disaster recovery**: Select this check box if you plan to deploy and implement disaster recovery of the Persistent Chat SQL Server stores from a configured backup set of stores on another SQL Server.</span></span> <span data-ttu-id="ce33a-109">Ausführliche Informationen finden Sie unter [Konfigurieren der hohen Verfügbarkeit und Notfallwiederherstellung für den Server für beständigen Chat in Skype for Business Server 2015](../../deploy/deploy-persistent-chat-server/configure-hadr-for-persistent-chat.md).</span><span class="sxs-lookup"><span data-stu-id="ce33a-109">For details, see [Configure high availability and disaster recovery for Persistent Chat Server in Skype for Business Server 2015](../../deploy/deploy-persistent-chat-server/configure-hadr-for-persistent-chat.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="ce33a-110">Diese Option ist nur für Pools mit mehreren Servern verfügbar.</span><span class="sxs-lookup"><span data-stu-id="ce33a-110">This option is available only for pools with multiple servers.</span></span> 
  
 <span data-ttu-id="ce33a-111">\*\*Diesen Pool als Standard für die \<site that this server or pool is being configured in\> Website verwenden \*\*: Aktivieren Sie dieses Kontrollkästchen, wenn es sich um den Standardserver für beständigen Chat oder den Serverpool für beständigen Chat für die Website handelt.</span><span class="sxs-lookup"><span data-stu-id="ce33a-111">**Use this pool as default for the site \<site that this server or pool is being configured in\>**: Select this check box if this will be the default Persistent Chat Server or Persistent Chat Server pool for the site.</span></span> <span data-ttu-id="ce33a-112">Sie müssen über einen standardmäßigen Server für beständigen Chat oder Pol pro Website verfügen.</span><span class="sxs-lookup"><span data-stu-id="ce33a-112">You must have one default Persistent Chat server or pol per site.</span></span>
  
> [!NOTE]
> <span data-ttu-id="ce33a-113">Wenn Ihre Topologie mehrere Standorte umfasst, wird auch ein Kontrollkästchen für **diesen Pool als Standard für alle Websites verwenden** angezeigt.</span><span class="sxs-lookup"><span data-stu-id="ce33a-113">If your topology includes multiple sites, a checkbox for **Use this pool as default for all sites** is also displayed.</span></span>
  
<span data-ttu-id="ce33a-114">Klicken Sie auf **Zurück**, um zum vorherigen Dialogfeld für die Pooldefinition zurückzukehren.</span><span class="sxs-lookup"><span data-stu-id="ce33a-114">Click **Back** to go back to the previous pool definition dialog.</span></span>
  
<span data-ttu-id="ce33a-115">Klicken Sie auf **weiter** , nachdem Sie die Eingabe der Optionen für diesen Pool abgeschlossen haben, um mit der Definition des Server Pools für beständigen Chat fortzufahren.</span><span class="sxs-lookup"><span data-stu-id="ce33a-115">Click **Next** after you have finished entering the options for this pool to proceed with the Persistent Chat Server pool definition.</span></span>
  
<span data-ttu-id="ce33a-116">Klicken Sie auf **Abbrechen**, um alle Änderungen zu verwerfen und den Assistenten **Neuen Pool für beständigen Chat definieren** zu beenden.</span><span class="sxs-lookup"><span data-stu-id="ce33a-116">Click **Cancel** to discard all changes and end the **Define New Persistent Chat Pool** wizard.</span></span>
  
<span data-ttu-id="ce33a-117">Klicken Sie auf **Hilfe**, um auf die kontextbezogene Hilfe (z. B. diese Seite) zuzugreifen.</span><span class="sxs-lookup"><span data-stu-id="ce33a-117">Click **Help** to access context sensitive help, such as this page.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="ce33a-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ce33a-118">See also</span></span>

[<span data-ttu-id="ce33a-119">Planen des Servers für beständigen Chat in Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="ce33a-119">Plan for Persistent Chat Server in Skype for Business Server 2015</span></span>](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md)
  
[<span data-ttu-id="ce33a-120">Hinzufügen eines Servers für beständigen Chat zu Ihrer Skype for Business Server 2015 Topologie</span><span class="sxs-lookup"><span data-stu-id="ce33a-120">Add Persistent Chat Server to your Skype for Business Server 2015 topology</span></span>](../../deploy/deploy-persistent-chat-server/add-persistent-chat-server.md)
