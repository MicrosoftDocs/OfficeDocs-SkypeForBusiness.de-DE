---
title: 'Lync Server 2013: Datenbankschema für beständigen Chat'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Persistent Chat database schema
ms:assetid: 58d7d94f-42f5-4c3e-8fe5-901fbe92152e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558653(v=OCS.15)
ms:contentKeyID: 48184228
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0b393f9281c1bb1fc1072a541b33bbab2656dafb
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/16/2020
ms.locfileid: "48524252"
---
# <a name="persistent-chat-database-schema-in-lync-server-2013"></a><span data-ttu-id="0c0a1-102">Datenbankschema für beständigen Chat in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0c0a1-102">Persistent Chat database schema in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0c0a1-103">_**Letztes Änderungsstand des Themas:** 2012-09-18_</span><span class="sxs-lookup"><span data-stu-id="0c0a1-103">_**Topic Last Modified:** 2012-09-18_</span></span>

<span data-ttu-id="0c0a1-104">In diesem Dokument wird das Schema der Datenbank für beständigen Chat in lync Server 2013 Kommunikationssoftware dokumentiert.</span><span class="sxs-lookup"><span data-stu-id="0c0a1-104">This documents the schema of the Persistent Chat database in Lync Server 2013 communications software.</span></span>

<span data-ttu-id="0c0a1-105">Die Datenbank für beständigen Chat bezieht sich auf die Datenbank, die den lync Server 2013 Back-End-Server Rollen **PersistentChatStore** (entsprechend der MGC-Datenbank) und **PersistentChatComplianceStore** (entsprechend der mgccomp-Datenbank) entspricht.</span><span class="sxs-lookup"><span data-stu-id="0c0a1-105">The Persistent Chat database refers to the database corresponding to the Lync Server 2013 Back End Server roles **PersistentChatStore** (corresponding to the mgc database) and **PersistentChatComplianceStore** (corresponding to the mgccomp database).</span></span> <span data-ttu-id="0c0a1-106">Durch die Veröffentlichung dieses Schemas können Sie Abfragen erstellen und erhalten Einblick in das Erstellen hilfreicher Berichte zur Verwendung der Chatfunktion, zu aktiven Räumen, Benutzern mit den meisten Beiträgen usw.</span><span class="sxs-lookup"><span data-stu-id="0c0a1-106">The goal of publishing this schema is to enable you to build queries and gain some insights into building useful reporting around chat usage, active rooms, top posters, and so on.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="0c0a1-p102">Wir behalten uns das Recht zur Weiterentwicklung dieses Schemas vor. Microsoft übernimmt keinerlei Garantie für eine dauerhafte vollständige Abwärtskompatibilität mit diesem veröffentlichten Schema.</span><span class="sxs-lookup"><span data-stu-id="0c0a1-p102">We reserve the right to evolve this schema. Microsoft does not make any guarantees to maintain full backward compatibility with this published schema.</span></span>



</div>

<span data-ttu-id="0c0a1-109">Halten Sie sich an folgende bewährte Methoden:</span><span class="sxs-lookup"><span data-stu-id="0c0a1-109">Follow these best practices:</span></span>

  - <span data-ttu-id="0c0a1-110">Keine SELECT \* //wird unterstützt, da die Spaltenliste wachsen kann.</span><span class="sxs-lookup"><span data-stu-id="0c0a1-110">No SELECT\* // is supported because the column list can grow.</span></span>

  - <span data-ttu-id="0c0a1-111">Es werden keine benutzergenerierten Schemaänderungen unterstützt.</span><span class="sxs-lookup"><span data-stu-id="0c0a1-111">No user-generated schema modifications are supported.</span></span>

  - <span data-ttu-id="0c0a1-112">Auch Schreibvorgänge werden nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="0c0a1-112">No write operations are supported.</span></span>

  - <span data-ttu-id="0c0a1-113">Testen Sie alle Abfragen, die Sie erstellen, mit Datenbanken ähnlicher Größe, um sicherzustellen, dass die Leistung der Abfragen Ihren Anforderungen entspricht.</span><span class="sxs-lookup"><span data-stu-id="0c0a1-113">Test any queries that you build on representatively-sized databases to be sure that the queries can perform at a level to meet your needs.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="0c0a1-114">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="0c0a1-114">In This Section</span></span>

  - [<span data-ttu-id="0c0a1-115">Liste der Server Tabellen für beständigen Chat in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0c0a1-115">List of Persistent Chat Server tables in Lync Server 2013</span></span>](lync-server-2013-list-of-persistent-chat-server-tables.md)

  - [<span data-ttu-id="0c0a1-116">Liste der Kompatibilitätstabellen für den Server für beständigen Chat in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0c0a1-116">List of Persistent Chat Server compliance tables in Lync Server 2013</span></span>](lync-server-2013-list-of-persistent-chat-server-compliance-tables.md)

  - [<span data-ttu-id="0c0a1-117">Tabellendetails für persistent Chat Server in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0c0a1-117">Persistent Chat Server table details in Lync Server 2013</span></span>](lync-server-2013-persistent-chat-server-table-details.md)

  - [<span data-ttu-id="0c0a1-118">Beispiel für Datenbankabfragen für beständigen Chat für lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0c0a1-118">Sample Persistent Chat database queries for Lync Server 2013</span></span>](lync-server-2013-sample-persistent-chat-database-queries.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

