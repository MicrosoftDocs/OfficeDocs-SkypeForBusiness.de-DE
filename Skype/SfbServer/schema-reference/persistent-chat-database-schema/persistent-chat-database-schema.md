---
title: Datenbankschema für beständigen Chat
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 10/20/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 58d7d94f-42f5-4c3e-8fe5-901fbe92152e
description: Dadurch wird das Schema der Datenbank für beständigen Chat in Skype for Business Server dokumentiert.
ms.openlocfilehash: b042f4490648760f4750e45fa1e35e032a8bf8b6
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2020
ms.locfileid: "41814743"
---
# <a name="persistent-chat-database-schema"></a><span data-ttu-id="646fa-103">Datenbankschema für beständigen Chat</span><span class="sxs-lookup"><span data-stu-id="646fa-103">Persistent Chat database schema</span></span>
 
<span data-ttu-id="646fa-104">Dadurch wird das Schema der Datenbank für beständigen Chat in Skype for Business Server dokumentiert.</span><span class="sxs-lookup"><span data-stu-id="646fa-104">This documents the schema of the Persistent Chat database in Skype for Business Server.</span></span>
  
<span data-ttu-id="646fa-105">Die persistent-Chat-Datenbank bezieht sich auf die Datenbank, die den Skype for Business Server-Back-End-Serverrollen **PersistentChatStore** (entsprechend der MGC-Datenbank) und **PersistentChatComplianceStore** (entsprechend der mgccomp-Datenbank) entspricht.</span><span class="sxs-lookup"><span data-stu-id="646fa-105">The Persistent Chat database refers to the database corresponding to the Skype for Business Server Back End Server roles **PersistentChatStore** (corresponding to the mgc database) and **PersistentChatComplianceStore** (corresponding to the mgccomp database).</span></span> <span data-ttu-id="646fa-106">Das Ziel der Veröffentlichung dieses Schemas ist es, Ihnen zu ermöglichen, Abfragen zu erstellen und einige Einblicke in das Erstellen nützlicher Berichte rund um die Chat-Nutzung, in Active rooms, in Top-Poster usw. zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="646fa-106">The goal of publishing this schema is to enable you to build queries and gain some insights into building useful reporting around chat usage, active rooms, top posters, and so on.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="646fa-107">Wir behalten uns das Recht vor, dieses Schema weiterzuentwickeln.</span><span class="sxs-lookup"><span data-stu-id="646fa-107">We reserve the right to evolve this schema.</span></span> <span data-ttu-id="646fa-108">Microsoft übernimmt keine Garantien, um die vollständige Abwärtskompatibilität mit diesem veröffentlichten Schema zu gewährleisten.</span><span class="sxs-lookup"><span data-stu-id="646fa-108">Microsoft does not make any guarantees to maintain full backward compatibility with this published schema.</span></span> 
  
<span data-ttu-id="646fa-109">Befolgen Sie diese bewährten Methoden:</span><span class="sxs-lookup"><span data-stu-id="646fa-109">Follow these best practices:</span></span>
  
- <span data-ttu-id="646fa-110">Es wird\* keine SELECT//-Auswahl unterstützt, da die Spaltenliste vergrößert werden kann.</span><span class="sxs-lookup"><span data-stu-id="646fa-110">No SELECT\* // is supported because the column list can grow.</span></span>
    
- <span data-ttu-id="646fa-111">Es werden keine vom benutzergenerierten Schemaänderungen unterstützt.</span><span class="sxs-lookup"><span data-stu-id="646fa-111">No user-generated schema modifications are supported.</span></span>
    
- <span data-ttu-id="646fa-112">Es werden keine Schreibvorgänge unterstützt.</span><span class="sxs-lookup"><span data-stu-id="646fa-112">No write operations are supported.</span></span>
    
- <span data-ttu-id="646fa-113">Testen Sie alle Abfragen, die Sie auf repräsentativ sortierten Datenbankenerstellen, um sicherzustellen, dass die Abfragen auf einer Ebene ausgeführt werden können, um Ihre Anforderungen zu erfüllen.</span><span class="sxs-lookup"><span data-stu-id="646fa-113">Test any queries that you build on representatively-sized databases to be sure that the queries can perform at a level to meet your needs.</span></span>
    
## <a name="in-this-section"></a><span data-ttu-id="646fa-114">Inhalt dieses Abschnitts</span><span class="sxs-lookup"><span data-stu-id="646fa-114">In this section</span></span>

- [<span data-ttu-id="646fa-115">Liste der Tabellen für den Server für beständigen Chat</span><span class="sxs-lookup"><span data-stu-id="646fa-115">List of Persistent Chat Server tables</span></span>](list-of-persistent-chat-server-tables.md)
    
- [<span data-ttu-id="646fa-116">Liste der beständigen Chat Server-Kompatibilitätstabellen in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="646fa-116">List of Persistent Chat Server compliance tables in Skype for Business Server</span></span>](list-of-persistent-chat-server-compliance-tables.md)
    
- [<span data-ttu-id="646fa-117">Ausführliche Informationen zur Tabelle für den Server für beständigen Chat</span><span class="sxs-lookup"><span data-stu-id="646fa-117">Persistent Chat Server table details</span></span>](persistent-chat-server-table-details.md)
    
- [<span data-ttu-id="646fa-118">Beispieldatenbankabfragen für beständigen Chat</span><span class="sxs-lookup"><span data-stu-id="646fa-118">Sample Persistent Chat database queries</span></span>](sample-persistent-chat-database-queries.md)
    

