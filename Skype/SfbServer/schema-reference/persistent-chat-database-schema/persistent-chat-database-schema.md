---
title: Datenbankschema für beständigen Chat
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 10/20/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 58d7d94f-42f5-4c3e-8fe5-901fbe92152e
description: In diesem Artikel wird das Schema der Datenbank für beständigen Chat in Skype für Business Server.
ms.openlocfilehash: 37b22077157def7ea25a5cf70b23a0272a58956e
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "32212691"
---
# <a name="persistent-chat-database-schema"></a><span data-ttu-id="970e5-103">Datenbankschema für beständigen Chat</span><span class="sxs-lookup"><span data-stu-id="970e5-103">Persistent Chat database schema</span></span>
 
<span data-ttu-id="970e5-104">In diesem Artikel wird das Schema der Datenbank für beständigen Chat in Skype für Business Server.</span><span class="sxs-lookup"><span data-stu-id="970e5-104">This documents the schema of the Persistent Chat database in Skype for Business Server.</span></span>
  
<span data-ttu-id="970e5-105">Datenbank für beständigen Chat bezieht sich auf die Datenbank, die Skype für Business Server Back End-Server-Rollen **PersistentChatStore** (entsprechend der Mgc-Datenbank) und **PersistentChatComplianceStore** entspricht (entsprechend der Mgccomp-Datenbank).</span><span class="sxs-lookup"><span data-stu-id="970e5-105">The Persistent Chat database refers to the database corresponding to the Skype for Business Server Back End Server roles **PersistentChatStore** (corresponding to the mgc database) and **PersistentChatComplianceStore** (corresponding to the mgccomp database).</span></span> <span data-ttu-id="970e5-106">Das Ziel der Veröffentlichung von diesem Schemas ist, können Sie Abfragen erstellen und gewinnen Sie einige Einsichten in nützliche reporting um Chat Nutzung, aktiven Chatrooms, oberen Poster usw. erstellen.</span><span class="sxs-lookup"><span data-stu-id="970e5-106">The goal of publishing this schema is to enable you to build queries and gain some insights into building useful reporting around chat usage, active rooms, top posters, and so on.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="970e5-107">Wir behalten uns das Recht, die mit diesem Schema weiterentwickelt.</span><span class="sxs-lookup"><span data-stu-id="970e5-107">We reserve the right to evolve this schema.</span></span> <span data-ttu-id="970e5-108">Microsoft ist keine Garantien zum Aufrechterhalten der vollständigen Abwärtskompatibilität mit diesem Schema veröffentlichte stellen.</span><span class="sxs-lookup"><span data-stu-id="970e5-108">Microsoft does not make any guarantees to maintain full backward compatibility with this published schema.</span></span> 
  
<span data-ttu-id="970e5-109">Führen Sie die folgenden bewährten Methoden:</span><span class="sxs-lookup"><span data-stu-id="970e5-109">Follow these best practices:</span></span>
  
- <span data-ttu-id="970e5-110">Wählen Sie keine\* / / wird unterstützt, da die Spaltenliste Wachstum ausgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="970e5-110">No SELECT\* // is supported because the column list can grow.</span></span>
    
- <span data-ttu-id="970e5-111">Keine benutzergenerierten schemaänderungen Änderungen werden unterstützt.</span><span class="sxs-lookup"><span data-stu-id="970e5-111">No user-generated schema modifications are supported.</span></span>
    
- <span data-ttu-id="970e5-112">Es werden keine Schreibvorgänge unterstützt.</span><span class="sxs-lookup"><span data-stu-id="970e5-112">No write operations are supported.</span></span>
    
- <span data-ttu-id="970e5-113">Testen Sie alle Abfragen, die Sie erstellen Datenbanken ähnlicher Größe, um sicherzustellen, dass die Abfragen auf einer Ebene für Ihre Bedürfnisse ausführen können.</span><span class="sxs-lookup"><span data-stu-id="970e5-113">Test any queries that you build on representatively-sized databases to be sure that the queries can perform at a level to meet your needs.</span></span>
    
## <a name="in-this-section"></a><span data-ttu-id="970e5-114">Inhalt dieses Abschnitts</span><span class="sxs-lookup"><span data-stu-id="970e5-114">In this section</span></span>

- [<span data-ttu-id="970e5-115">Liste der Tabellen für den Server für beständigen Chat</span><span class="sxs-lookup"><span data-stu-id="970e5-115">List of Persistent Chat Server tables</span></span>](list-of-persistent-chat-server-tables.md)
    
- [<span data-ttu-id="970e5-116">Liste der kompatibilitätstabellen für Persistent Chat Server in Skype für Business Server</span><span class="sxs-lookup"><span data-stu-id="970e5-116">List of Persistent Chat Server compliance tables in Skype for Business Server</span></span>](list-of-persistent-chat-server-compliance-tables.md)
    
- [<span data-ttu-id="970e5-117">Ausführliche Informationen zur Tabelle für den Server für beständigen Chat</span><span class="sxs-lookup"><span data-stu-id="970e5-117">Persistent Chat Server table details</span></span>](persistent-chat-server-table-details.md)
    
- [<span data-ttu-id="970e5-118">Beispieldatenbankabfragen für beständigen Chat</span><span class="sxs-lookup"><span data-stu-id="970e5-118">Sample Persistent Chat database queries</span></span>](sample-persistent-chat-database-queries.md)
    

