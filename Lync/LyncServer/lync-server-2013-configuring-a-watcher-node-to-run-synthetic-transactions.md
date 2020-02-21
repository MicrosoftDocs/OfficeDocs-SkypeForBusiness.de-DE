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
ms.openlocfilehash: 605a859717736785df2d726720c2984162ff830d
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/21/2020
ms.locfileid: "42207991"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configuring-a-watcher-node-to-run-synthetic-transactions-in-lync-server-2013"></a><span data-ttu-id="b3a30-102">Konfigurieren eines Watcher-Knotens zum Ausführen synthetischer Transaktionen in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b3a30-102">Configuring a watcher node to run synthetic transactions in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b3a30-103">_**Letztes Änderungsstand des Themas:** 2014-02-07_</span><span class="sxs-lookup"><span data-stu-id="b3a30-103">_**Topic Last Modified:** 2014-02-07_</span></span>

<span data-ttu-id="b3a30-p101">Nachdem die System Center-Agentdateien installiert wurden, müssen Sie im nächsten Schritt den Watcher-Knoten selbst konfigurieren. Die Schritte zum Konfigurieren eines Watcher-Knotens hängen davon ab, ob sich der Computer mit dem Watcher-Knoten innerhalb oder außerhalb Ihrs Umkreisnetzwerks befindet.</span><span class="sxs-lookup"><span data-stu-id="b3a30-p101">After the System Center agent files have been installed, you must next configure the watcher node itself. The steps you take to configure a watcher node will vary depending on whether your watcher node computer lies inside your perimeter network or outside your perimeter network.</span></span>

<span data-ttu-id="b3a30-106">Beim Konfigurieren eines Watcher-Knotens müssen Sie außerdem die Authentifizierungsmethode auswählen, die von diesem Knoten verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="b3a30-106">When you configure a watcher node, you must also choose the type of authentication method to be employed by that node.</span></span> <span data-ttu-id="b3a30-107">Lync Server 2013 können Sie eine von zwei Authentifizierungsmethoden auswählen: vertrauenswürdige Server-oder Anmelde Informations Authentifizierung.</span><span class="sxs-lookup"><span data-stu-id="b3a30-107">Lync Server 2013 enables you to choose one of two authentication methods: Trusted Server or Credential Authentication.</span></span> <span data-ttu-id="b3a30-108">Die Unterschiede zwischen diesen beiden Methoden werden in der folgenden Tabelle erläutert:</span><span class="sxs-lookup"><span data-stu-id="b3a30-108">The differences between these two methods are outlined in the following table:</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="b3a30-109">Konfiguration</span><span class="sxs-lookup"><span data-stu-id="b3a30-109">Configuration</span></span></th>
<th><span data-ttu-id="b3a30-110">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="b3a30-110">Description</span></span></th>
<th><span data-ttu-id="b3a30-111">Unterstützte Standorte</span><span class="sxs-lookup"><span data-stu-id="b3a30-111">Locations Supported</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b3a30-112">Vertrauenswürdiger Server</span><span class="sxs-lookup"><span data-stu-id="b3a30-112">Trusted Server</span></span></p></td>
<td><p><span data-ttu-id="b3a30-113">Ein Zertifikat wird verwendet, um die Identität eines internen Servers anzunehmen und die Authentifizierungsaufforderungen zu umgehen.</span><span class="sxs-lookup"><span data-stu-id="b3a30-113">Uses a certificate to impersonate an internal server and bypass authentication challenges.</span></span></p>
<p><span data-ttu-id="b3a30-114">Diese Methode eignet sich für Administratoren, die es vorziehen, ein einzelnes Zertifikat anstelle vieler Benutzerkennwörter auf jedem Watcher-Knoten zu verwalten.</span><span class="sxs-lookup"><span data-stu-id="b3a30-114">This is useful for administrators who would prefer to manage a single certificate instead of many user passwords on each watcher node.</span></span></p></td>
<td><p><span data-ttu-id="b3a30-115">Innerhalb des Unternehmens.</span><span class="sxs-lookup"><span data-stu-id="b3a30-115">Inside the enterprise.</span></span></p>
<p><span data-ttu-id="b3a30-p103">Beachten Sie, dass sich bei dieser Methode der Watcher-Knoten in derselben Domäne wie die überwachten Pools befinden muss. Falls sich der Watcher-Knoten und die überwachten Pools in unterschiedlichen Domänen befinden, verwenden Sie stattdessen die Authentifizierung mit Anmeldeinformationen.</span><span class="sxs-lookup"><span data-stu-id="b3a30-p103">Note that, with this method, the watcher node must be in the same domain as the pools being monitored. If the watcher node and the monitored pools are in different domains, use Credential Authentication instead.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b3a30-118">Authentifizierung mit Anmeldeinformationen</span><span class="sxs-lookup"><span data-stu-id="b3a30-118">Credential Authentication</span></span></p></td>
<td><p><span data-ttu-id="b3a30-119">Benutzernamen und Kennwörter werden auf sichere Weise in der Windows-Anmeldeinformationsverwaltung auf jedem Watcher-Knoten gespeichert.</span><span class="sxs-lookup"><span data-stu-id="b3a30-119">Stores user names and passwords securely in Windows Credential Manager on each watcher node.</span></span></p>
<p><span data-ttu-id="b3a30-p104">Dieser Modus erfordert einen höheren Kennwortverwaltungsaufwand, ist aber die einzige Option für Watcher-Knoten außerhalb des Unternehmens. Diese Watcher-Knoten können nicht als Endpunkt, der bezüglich der Authentifizierung vertrauenswürdig ist, betrachtet werden.</span><span class="sxs-lookup"><span data-stu-id="b3a30-p104">This mode requires more password management, but is the only option for watcher nodes located outside of the enterprise. These watcher nodes cannot be treated as an endpoint trusted for authentication.</span></span></p></td>
<td><p><span data-ttu-id="b3a30-122">Außerhalb des Unternehmens.</span><span class="sxs-lookup"><span data-stu-id="b3a30-122">Outside the enterprise.</span></span></p>
<p><span data-ttu-id="b3a30-123">Innerhalb des Unternehmens.</span><span class="sxs-lookup"><span data-stu-id="b3a30-123">Inside the enterprise.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="b3a30-124">Sie sollten auch überprüfen, ob Ihre Firewall eingehende Regeln für sowohl MonitoringHost. exe als auch PowerShell. exe aufweist.</span><span class="sxs-lookup"><span data-stu-id="b3a30-124">You should also verify that your firewall has inbound rules for both MonitoringHost.exe and PowerShell.exe.</span></span> <span data-ttu-id="b3a30-125">Wenn diese Prozesse durch die Firewall blockiert werden, tritt bei ihren synthetischen Transaktionen ein Fehler 504 (Servertimeout) auf.</span><span class="sxs-lookup"><span data-stu-id="b3a30-125">If these processes are blocked by the firewall then your synthetic transactions will fail with a 504 (server timeout) error.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

