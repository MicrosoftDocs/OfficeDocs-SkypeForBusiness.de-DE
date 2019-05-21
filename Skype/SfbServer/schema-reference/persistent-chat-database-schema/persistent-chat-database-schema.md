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
localization_priority: Normal
ms.assetid: 58d7d94f-42f5-4c3e-8fe5-901fbe92152e
description: Dadurch wird das Schema der Datenbank für beständigen Chat in Skype for Business Server dokumentiert.
ms.openlocfilehash: 9a3e09a03f764f8866865e08259cbaac12a1c554
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2019
ms.locfileid: "34295615"
---
# <a name="persistent-chat-database-schema"></a><span data-ttu-id="da45f-103">Datenbankschema für beständigen Chat</span><span class="sxs-lookup"><span data-stu-id="da45f-103">Persistent Chat database schema</span></span>
 
<span data-ttu-id="da45f-104">Dadurch wird das Schema der Datenbank für beständigen Chat in Skype for Business Server dokumentiert.</span><span class="sxs-lookup"><span data-stu-id="da45f-104">This documents the schema of the Persistent Chat database in Skype for Business Server.</span></span>
  
<span data-ttu-id="da45f-105">Die persistent-Chat-Datenbank bezieht sich auf die Datenbank, die den Skype for Business Server-Back-End-Serverrollen **PersistentChatStore** (entsprechend der MGC-Datenbank) und **PersistentChatComplianceStore** (entsprechend der mgccomp-Datenbank).</span><span class="sxs-lookup"><span data-stu-id="da45f-105">The Persistent Chat database refers to the database corresponding to the Skype for Business Server Back End Server roles **PersistentChatStore** (corresponding to the mgc database) and **PersistentChatComplianceStore** (corresponding to the mgccomp database).</span></span> <span data-ttu-id="da45f-106">Das Ziel der Veröffentlichung dieses Schemas ist es, Ihnen zu ermöglichen, Abfragen zu erstellen und einige Einblicke in das Erstellen nützlicher Berichte rund um die Chat-Nutzung, in Active rooms, in Top-Poster usw. zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="da45f-106">The goal of publishing this schema is to enable you to build queries and gain some insights into building useful reporting around chat usage, active rooms, top posters, and so on.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="da45f-107">Wir behalten uns das Recht vor, dieses Schema weiterzuentwickeln.</span><span class="sxs-lookup"><span data-stu-id="da45f-107">We reserve the right to evolve this schema.</span></span> <span data-ttu-id="da45f-108">Microsoft übernimmt keine Garantien, um die vollständige Abwärtskompatibilität mit diesem veröffentlichten Schema zu gewährleisten.</span><span class="sxs-lookup"><span data-stu-id="da45f-108">Microsoft does not make any guarantees to maintain full backward compatibility with this published schema.</span></span> 
  
<span data-ttu-id="da45f-109">Befolgen Sie diese bewährten Methoden:</span><span class="sxs-lookup"><span data-stu-id="da45f-109">Follow these best practices:</span></span>
  
- <span data-ttu-id="da45f-110">Es wird\* keine SELECT//-Auswahl unterstützt, da die Spaltenliste vergrößert werden kann.</span><span class="sxs-lookup"><span data-stu-id="da45f-110">No SELECT\* // is supported because the column list can grow.</span></span>
    
- <span data-ttu-id="da45f-111">Es werden keine vom benutzergenerierten Schemaänderungen unterstützt.</span><span class="sxs-lookup"><span data-stu-id="da45f-111">No user-generated schema modifications are supported.</span></span>
    
- <span data-ttu-id="da45f-112">Es werden keine Schreibvorgänge unterstützt.</span><span class="sxs-lookup"><span data-stu-id="da45f-112">No write operations are supported.</span></span>
    
- <span data-ttu-id="da45f-113">Testen Sie alle Abfragen, die Sie auf repräsentativ sortierten Datenbankenerstellen, um sicherzustellen, dass die Abfragen auf einer Ebene ausgeführt werden können, um Ihre Anforderungen zu erfüllen.</span><span class="sxs-lookup"><span data-stu-id="da45f-113">Test any queries that you build on representatively-sized databases to be sure that the queries can perform at a level to meet your needs.</span></span>
    
## <a name="in-this-section"></a><span data-ttu-id="da45f-114">Inhalt dieses Abschnitts</span><span class="sxs-lookup"><span data-stu-id="da45f-114">In this section</span></span>

- [<span data-ttu-id="da45f-115">Liste der Tabellen für den Server für beständigen Chat</span><span class="sxs-lookup"><span data-stu-id="da45f-115">List of Persistent Chat Server tables</span></span>](list-of-persistent-chat-server-tables.md)
    
- [<span data-ttu-id="da45f-116">Liste der beständigen Chat Server-Kompatibilitätstabellen in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="da45f-116">List of Persistent Chat Server compliance tables in Skype for Business Server</span></span>](list-of-persistent-chat-server-compliance-tables.md)
    
- [<span data-ttu-id="da45f-117">Ausführliche Informationen zur Tabelle für den Server für beständigen Chat</span><span class="sxs-lookup"><span data-stu-id="da45f-117">Persistent Chat Server table details</span></span>](persistent-chat-server-table-details.md)
    
- [<span data-ttu-id="da45f-118">Beispieldatenbankabfragen für beständigen Chat</span><span class="sxs-lookup"><span data-stu-id="da45f-118">Sample Persistent Chat database queries</span></span>](sample-persistent-chat-database-queries.md)
    

