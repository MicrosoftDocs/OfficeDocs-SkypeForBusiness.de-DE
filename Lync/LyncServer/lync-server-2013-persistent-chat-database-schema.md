---
title: 'Lync Server 2013: Datenbankschema für beständigen Chat'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Persistent Chat database schema
ms:assetid: 58d7d94f-42f5-4c3e-8fe5-901fbe92152e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558653(v=OCS.15)
ms:contentKeyID: 48184228
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3f35b1551b1ef7f228c70cbb76e748eae5e7cf59
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34825191"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="persistent-chat-database-schema-in-lync-server-2013"></a><span data-ttu-id="a092e-102">Datenbankschema für beständigen Chat in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a092e-102">Persistent Chat database schema in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a092e-103">_**Letztes Änderungsdatum des Themas:** 2012-09-18_</span><span class="sxs-lookup"><span data-stu-id="a092e-103">_**Topic Last Modified:** 2012-09-18_</span></span>

<span data-ttu-id="a092e-104">Dadurch wird das Schema der Datenbank für beständigen Chat in der lync Server 2013-Kommunikationssoftware dokumentiert.</span><span class="sxs-lookup"><span data-stu-id="a092e-104">This documents the schema of the Persistent Chat database in Lync Server 2013 communications software.</span></span>

<span data-ttu-id="a092e-105">Die Datenbank für beständigen Chat bezieht sich auf die Datenbank, die den lync Server 2013-Back-End-Serverrollen **PersistentChatStore** (entsprechend der MGC-Datenbank) und **PersistentChatComplianceStore** (entsprechend der mgccomp Datenbank).</span><span class="sxs-lookup"><span data-stu-id="a092e-105">The Persistent Chat database refers to the database corresponding to the Lync Server 2013 Back End Server roles **PersistentChatStore** (corresponding to the mgc database) and **PersistentChatComplianceStore** (corresponding to the mgccomp database).</span></span> <span data-ttu-id="a092e-106">Das Ziel der Veröffentlichung dieses Schemas ist es, Ihnen zu ermöglichen, Abfragen zu erstellen und einige Einblicke in das Erstellen nützlicher Berichte rund um die Chat-Nutzung, in Active rooms, in Top-Poster usw. zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="a092e-106">The goal of publishing this schema is to enable you to build queries and gain some insights into building useful reporting around chat usage, active rooms, top posters, and so on.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="a092e-107">Wir behalten uns das Recht vor, dieses Schema weiterzuentwickeln.</span><span class="sxs-lookup"><span data-stu-id="a092e-107">We reserve the right to evolve this schema.</span></span> <span data-ttu-id="a092e-108">Microsoft übernimmt keine Garantien, um die vollständige Abwärtskompatibilität mit diesem veröffentlichten Schema zu gewährleisten.</span><span class="sxs-lookup"><span data-stu-id="a092e-108">Microsoft does not make any guarantees to maintain full backward compatibility with this published schema.</span></span>



</div>

<span data-ttu-id="a092e-109">Befolgen Sie diese bewährten Methoden:</span><span class="sxs-lookup"><span data-stu-id="a092e-109">Follow these best practices:</span></span>

  - <span data-ttu-id="a092e-110">Es wird\* keine SELECT//-Auswahl unterstützt, da die Spaltenliste vergrößert werden kann.</span><span class="sxs-lookup"><span data-stu-id="a092e-110">No SELECT\* // is supported because the column list can grow.</span></span>

  - <span data-ttu-id="a092e-111">Es werden keine vom benutzergenerierten Schemaänderungen unterstützt.</span><span class="sxs-lookup"><span data-stu-id="a092e-111">No user-generated schema modifications are supported.</span></span>

  - <span data-ttu-id="a092e-112">Es werden keine Schreibvorgänge unterstützt.</span><span class="sxs-lookup"><span data-stu-id="a092e-112">No write operations are supported.</span></span>

  - <span data-ttu-id="a092e-113">Testen Sie alle Abfragen, die Sie auf repräsentativ sortierten Datenbankenerstellen, um sicherzustellen, dass die Abfragen auf einer Ebene ausgeführt werden können, um Ihre Anforderungen zu erfüllen.</span><span class="sxs-lookup"><span data-stu-id="a092e-113">Test any queries that you build on representatively-sized databases to be sure that the queries can perform at a level to meet your needs.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="a092e-114">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="a092e-114">In This Section</span></span>

  - [<span data-ttu-id="a092e-115">Liste der Tabellen für den Server für beständigen Chat in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a092e-115">List of Persistent Chat Server tables in Lync Server 2013</span></span>](lync-server-2013-list-of-persistent-chat-server-tables.md)

  - [<span data-ttu-id="a092e-116">Liste der Kompatibilitätstabellen für den Server für beständigen Chat in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a092e-116">List of Persistent Chat Server compliance tables in Lync Server 2013</span></span>](lync-server-2013-list-of-persistent-chat-server-compliance-tables.md)

  - [<span data-ttu-id="a092e-117">Ausführliche Informationen zur Tabelle für den Server für beständigen Chat in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a092e-117">Persistent Chat Server table details in Lync Server 2013</span></span>](lync-server-2013-persistent-chat-server-table-details.md)

  - [<span data-ttu-id="a092e-118">Beispieldatenbankabfragen für beständigen Chat für Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a092e-118">Sample Persistent Chat database queries for Lync Server 2013</span></span>](lync-server-2013-sample-persistent-chat-database-queries.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

