---
title: 'Lync Server 2013: Konfigurieren eines Watcher-Knotens zum Ausführen synthetischer Transaktionen'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring a watcher node to run synthetic transactions
ms:assetid: cedda508-8881-4079-88d5-49798f342ddf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205314(v=OCS.15)
ms:contentKeyID: 48185578
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 19211c786c288326d5769824524f5571e5df2f00
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41763419"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-a-watcher-node-to-run-synthetic-transactions-in-lync-server-2013"></a><span data-ttu-id="f1208-102">Konfigurieren eines Watcher-Knotens zum Ausführen synthetischer Transaktionen in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f1208-102">Configuring a watcher node to run synthetic transactions in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f1208-103">_**Letztes Änderungsdatum des Themas:** 2014-02-07_</span><span class="sxs-lookup"><span data-stu-id="f1208-103">_**Topic Last Modified:** 2014-02-07_</span></span>

<span data-ttu-id="f1208-104">Nachdem Sie die System Center-Agent-Dateien installiert haben, müssen Sie den Watcher-Knoten als Nächstes konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="f1208-104">After the System Center agent files have been installed, you must next configure the watcher node itself.</span></span> <span data-ttu-id="f1208-105">Die Schritte zum Konfigurieren eines Watcher-Knotens variieren je nachdem, ob sich der Watcher-Knoten Computer in Ihrem Umkreisnetzwerk oder außerhalb Ihres Umkreisnetzwerks befindet.</span><span class="sxs-lookup"><span data-stu-id="f1208-105">The steps you take to configure a watcher node will vary depending on whether your watcher node computer lies inside your perimeter network or outside your perimeter network.</span></span>

<span data-ttu-id="f1208-106">Beim Konfigurieren eines Monitorknotens müssen Sie außerdem die Authentifizierungsmethode auswählen, die von diesem Knoten verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="f1208-106">When you configure a watcher node, you must also choose the type of authentication method to be employed by that node.</span></span> <span data-ttu-id="f1208-107">Mit lync Server 2013 können Sie eine von zwei Authentifizierungsmethoden auswählen: vertrauenswürdige Server-oder Anmelde Informations Authentifizierung.</span><span class="sxs-lookup"><span data-stu-id="f1208-107">Lync Server 2013 enables you to choose one of two authentication methods: Trusted Server or Credential Authentication.</span></span> <span data-ttu-id="f1208-108">Die Unterschiede zwischen diesen beiden Methoden sind in der folgenden Tabelle beschrieben:</span><span class="sxs-lookup"><span data-stu-id="f1208-108">The differences between these two methods are outlined in the following table:</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="f1208-109">Konfiguration</span><span class="sxs-lookup"><span data-stu-id="f1208-109">Configuration</span></span></th>
<th><span data-ttu-id="f1208-110">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="f1208-110">Description</span></span></th>
<th><span data-ttu-id="f1208-111">Unterstützte Speicherorte</span><span class="sxs-lookup"><span data-stu-id="f1208-111">Locations Supported</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f1208-112">Vertrauenswürdiger Server</span><span class="sxs-lookup"><span data-stu-id="f1208-112">Trusted Server</span></span></p></td>
<td><p><span data-ttu-id="f1208-113">Ein Zertifikat wird verwendet, um die Identität eines internen Servers anzunehmen und die Authentifizierungsaufforderungen zu umgehen.</span><span class="sxs-lookup"><span data-stu-id="f1208-113">Uses a certificate to impersonate an internal server and bypass authentication challenges.</span></span></p>
<p><span data-ttu-id="f1208-114">Dies ist hilfreich für Administratoren, die ein einzelnes Zertifikat anstelle von vielen Benutzerkennwörtern für jeden Watcher-Knoten verwalten möchten.</span><span class="sxs-lookup"><span data-stu-id="f1208-114">This is useful for administrators who would prefer to manage a single certificate instead of many user passwords on each watcher node.</span></span></p></td>
<td><p><span data-ttu-id="f1208-115">Innerhalb des Unternehmens.</span><span class="sxs-lookup"><span data-stu-id="f1208-115">Inside the enterprise.</span></span></p>
<p><span data-ttu-id="f1208-116">Beachten Sie, dass sich der Watcher-Knoten bei dieser Methode in der gleichen Domäne wie die zu überwachenden Pools befinden muss.</span><span class="sxs-lookup"><span data-stu-id="f1208-116">Note that, with this method, the watcher node must be in the same domain as the pools being monitored.</span></span> <span data-ttu-id="f1208-117">Wenn sich der Watcher-Knoten und die überwachten Pools in verschiedenen Domänen befinden, verwenden Sie stattdessen die Anmelde Informations Authentifizierung.</span><span class="sxs-lookup"><span data-stu-id="f1208-117">If the watcher node and the monitored pools are in different domains, use Credential Authentication instead.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f1208-118">Authentifizierung von Anmeldeinformationen</span><span class="sxs-lookup"><span data-stu-id="f1208-118">Credential Authentication</span></span></p></td>
<td><p><span data-ttu-id="f1208-119">Benutzernamen und Kennwörter werden auf sichere Weise in der Windows-Anmeldeinformationsverwaltung auf jedem Monitorknoten gespeichert.</span><span class="sxs-lookup"><span data-stu-id="f1208-119">Stores user names and passwords securely in Windows Credential Manager on each watcher node.</span></span></p>
<p><span data-ttu-id="f1208-120">Dieser Modus erfordert mehr Kennwortverwaltung, ist aber die einzige Option für Watcher-Knoten, die sich außerhalb des Unternehmens befinden.</span><span class="sxs-lookup"><span data-stu-id="f1208-120">This mode requires more password management, but is the only option for watcher nodes located outside of the enterprise.</span></span> <span data-ttu-id="f1208-121">Diese Monitorknoten können nicht als vertrauenswürdiger Endpunkt für die Authentifizierung betrachtet werden.</span><span class="sxs-lookup"><span data-stu-id="f1208-121">These watcher nodes cannot be treated as an endpoint trusted for authentication.</span></span></p></td>
<td><p><span data-ttu-id="f1208-122">Außerhalb des Unternehmens.</span><span class="sxs-lookup"><span data-stu-id="f1208-122">Outside the enterprise.</span></span></p>
<p><span data-ttu-id="f1208-123">Innerhalb des Unternehmens.</span><span class="sxs-lookup"><span data-stu-id="f1208-123">Inside the enterprise.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="f1208-124">Sie sollten auch überprüfen, ob Ihre Firewall eingehende Regeln für MonitoringHost. exe und PowerShell. exe aufweist.</span><span class="sxs-lookup"><span data-stu-id="f1208-124">You should also verify that your firewall has inbound rules for both MonitoringHost.exe and PowerShell.exe.</span></span> <span data-ttu-id="f1208-125">Wenn diese Prozesse von der Firewall blockiert werden, schlagen Ihre synthetischen Transaktionen mit einem 504-Fehler (Servertimeout) fehl.</span><span class="sxs-lookup"><span data-stu-id="f1208-125">If these processes are blocked by the firewall then your synthetic transactions will fail with a 504 (server timeout) error.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

