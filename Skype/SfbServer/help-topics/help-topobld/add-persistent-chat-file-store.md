---
title: Hinzufügen des Dateispeichers für beständigen Chat
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/8/2018
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddPersistentChatFileStorePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e1068706-ff61-4a98-8e51-4202111d936a
description: Sie müssen eine Dateifreigabe angeben, die als Dateispeicher für den Standard Edition-Server oder den Front-End-Pool der Enterprise Edition verwendet werden soll. Sie können als Dateispeicher eine vorhandene Dateifreigabe oder eine neue Dateifreigabe auswählen, indem Sie den vollqualifizierten Domänennamen (FQDN) des Dateiservers, auf dem sich die Dateifreigabe befindet, und einen Ordnernamen für die neue Dateifreigabe angeben.
ms.openlocfilehash: df8fd066961f872245ca0f5111726856180646cd
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "33897408"
---
# <a name="add-persistent-chat-file-store"></a><span data-ttu-id="f6b9a-104">Hinzufügen des Dateispeichers für beständigen Chat</span><span class="sxs-lookup"><span data-stu-id="f6b9a-104">Add Persistent Chat File Store</span></span>
 
<span data-ttu-id="f6b9a-p102">Sie müssen eine Dateifreigabe angeben, die als Dateispeicher für den Standard Edition-Server oder den Front-End-Pool der Enterprise Edition verwendet werden soll. Sie können als Dateispeicher eine vorhandene Dateifreigabe oder eine neue Dateifreigabe auswählen, indem Sie den vollqualifizierten Domänennamen (FQDN) des Dateiservers, auf dem sich die Dateifreigabe befindet, und einen Ordnernamen für die neue Dateifreigabe angeben.</span><span class="sxs-lookup"><span data-stu-id="f6b9a-p102">You must specify a file share to be used as the file store for the Standard Edition server or Enterprise Edition Front End pool. You can use an existing file share for the file store or you can specify a new file share by specifying the fully qualified domain name (FQDN) of the file server on which the file share is to be located and a folder name for the new file share.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="f6b9a-107">Die Dateifreigabe für Skype für Business Server darf sich nicht auf die Enterprise Edition-Front-End-Server, aber Sie können auf einem Standard Edition-Server befinden.</span><span class="sxs-lookup"><span data-stu-id="f6b9a-107">The file share for Skype for Business Server cannot be located on the Enterprise Edition Front End Server, but can be located on a Standard Edition server.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="f6b9a-108">Sie können die Dateifreigabe im Topologie-Generator definieren, bevor Sie die Dateifreigabe erstellen, aber Sie müssen die Dateifreigabe am angegebenen Speicherort erstellen, ehe Sie die Topologie veröffentlichen.</span><span class="sxs-lookup"><span data-stu-id="f6b9a-108">You can define the file share in Topology Builder before you create the file share, but you must create the file share in the defined location you define before you publish the topology.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="f6b9a-109">Wenn Sie eine Persistent Chat Server hinzufügen oder Persistent Chat Server Pool zu einer Topologie, Topologie-Generator die Datei einrichten kann muss speichern und Konfigurieren von discretionary Access Control enthält (DACL) für die Dateifreigabe für den Dateispeicher verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="f6b9a-109">When you add a Persistent Chat Server or Persistent Chat Server pool to your topology, Topology Builder must be able to set up the file store and configure discretionary access control lists (DACLs) on the file share to be used for the file store.</span></span> <span data-ttu-id="f6b9a-110">Deshalb müssen Sie bei Ausführung des Topologie-Generators zum Veröffentlichen der neuen Topologie mit einem Konto mit Vollzugriffsberechtigungen (Lesen/Schreiben/Ändern) für die Dateifreigabe angemeldet sein.</span><span class="sxs-lookup"><span data-stu-id="f6b9a-110">This requires that, when you run Topology Builder to publish the new topology, you are logged on with an account that has full control permissions (read/write/modify) for the file share.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="f6b9a-111">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f6b9a-111">See also</span></span>

[<span data-ttu-id="f6b9a-112">Planen für den Server für beständigen Chat in Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="f6b9a-112">Plan for Persistent Chat Server in Skype for Business Server 2015</span></span>](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md)
  
[<span data-ttu-id="f6b9a-113">Hinzufügen von Persistent Chat Server zu Ihrer Skype für Business Server 2015 Topologie</span><span class="sxs-lookup"><span data-stu-id="f6b9a-113">Add Persistent Chat Server to your Skype for Business Server 2015 topology</span></span>](../../deploy/deploy-persistent-chat-server/add-persistent-chat-server.md)
  
[<span data-ttu-id="f6b9a-114">Hardware- und Softwareanforderungen an den Server für beständigen Chat in Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="f6b9a-114">Hardware and software requirements for Persistent Chat Server in Skype for Business Server 2015</span></span>](../../plan-your-deployment/persistent-chat-server/hardware-and-software-requirements.md)
  
[<span data-ttu-id="f6b9a-115">Server requirements for Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="f6b9a-115">Server requirements for Skype for Business Server 2015</span></span>](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md)
  
[<span data-ttu-id="f6b9a-116">Topologiegrundlagen in Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="f6b9a-116">Topology Basics for Skype for Business Server 2015</span></span>](../../plan-your-deployment/topology-basics/topology-basics.md)
