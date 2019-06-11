---
title: Einführung
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Introduction
ms:assetid: 276395be-93df-4a16-97e2-cb468cd0f2e3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945588(v=OCS.15)
ms:contentKeyID: 51541414
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d496d0aeaabd8ef7502cae8db89f2668d0574499
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34840045"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="introduction"></a><span data-ttu-id="1bc6c-102">Einführung</span><span class="sxs-lookup"><span data-stu-id="1bc6c-102">Introduction</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1bc6c-103">_**Letztes Änderungsdatum des Themas:** 2013-02-24_</span><span class="sxs-lookup"><span data-stu-id="1bc6c-103">_**Topic Last Modified:** 2013-02-24_</span></span>

<span data-ttu-id="1bc6c-104">Das lync Server 2013-Tool Stress und Leistung (als LyncPerfTool bezeichnet) kann die Benutzerauslastung der folgenden Typen simulieren:</span><span class="sxs-lookup"><span data-stu-id="1bc6c-104">The Lync Server 2013 Stress and Performance Tool (referred to as LyncPerfTool) can simulate user load of the following types:</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="1bc6c-105">Instant Messaging (im) und Anwesenheitsinformationen</span><span class="sxs-lookup"><span data-stu-id="1bc6c-105">Instant messaging (IM) and presence</span></span></p></td>
<td><p><span data-ttu-id="1bc6c-106">Audiokonferenzen</span><span class="sxs-lookup"><span data-stu-id="1bc6c-106">Audio conferencing</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1bc6c-107">Anwendungsfreigabe</span><span class="sxs-lookup"><span data-stu-id="1bc6c-107">Application sharing</span></span></p></td>
<td><p><span data-ttu-id="1bc6c-108">VoIP (Voice over IP), einschließlich der PSTN-Simulation (Public Switched Telephone Network)</span><span class="sxs-lookup"><span data-stu-id="1bc6c-108">Voice over IP (VoIP), including public switched telephone network (PSTN) simulation</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1bc6c-109">Web Access-Client Konferenzen</span><span class="sxs-lookup"><span data-stu-id="1bc6c-109">Web Access Client conferencing</span></span></p></td>
<td><p><span data-ttu-id="1bc6c-110">Microsoft lync 2013 Attendant</span><span class="sxs-lookup"><span data-stu-id="1bc6c-110">Microsoft Lync 2013 Attendant</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1bc6c-111">Reaktionsgruppen</span><span class="sxs-lookup"><span data-stu-id="1bc6c-111">Response Groups</span></span></p></td>
<td><p><span data-ttu-id="1bc6c-112">Erweiterung der Verteilerliste</span><span class="sxs-lookup"><span data-stu-id="1bc6c-112">Distribution list expansion</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1bc6c-113">Adressbuch Download und Adressbuch Abfrage</span><span class="sxs-lookup"><span data-stu-id="1bc6c-113">Address book download and address book query</span></span></p></td>
<td><p><span data-ttu-id="1bc6c-114">Erweiterte 9-1-1 (E9-1-1)-Anrufe und Standortprofil (Wählplan)</span><span class="sxs-lookup"><span data-stu-id="1bc6c-114">Enhanced 9-1-1 (E9-1-1) calls and location profile (dial plan)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1bc6c-115">MultiView</span><span class="sxs-lookup"><span data-stu-id="1bc6c-115">MultiView</span></span></p></td>
<td><p><span data-ttu-id="1bc6c-116">Anzeigen mehrerer Datenströme aus einer Konferenz</span><span class="sxs-lookup"><span data-stu-id="1bc6c-116">Viewing multiple streams from a conference</span></span></p></td>
</tr>
<tr class="odd">
<td></td>
<td></td>
</tr>
</tbody>
</table>


<span data-ttu-id="1bc6c-117">Das Stress-und Leistungs Tool von lync Server 2013 unterstützt die Generierung und Föderations übergreifendes Laden von Datenpools über erweiterte Konfiguration.</span><span class="sxs-lookup"><span data-stu-id="1bc6c-117">The Lync Server 2013 Stress and Performance Tool supports cross-pool load generation and federation through advanced configuration only.</span></span>

<span data-ttu-id="1bc6c-118">Das Tool simuliert auch keine Benutzerauslastung für die folgenden Clients:</span><span class="sxs-lookup"><span data-stu-id="1bc6c-118">The tool also does not simulate user load for the following clients:</span></span>

  - <span data-ttu-id="1bc6c-119">Office Live Meeting 2007</span><span class="sxs-lookup"><span data-stu-id="1bc6c-119">Office Live Meeting 2007</span></span>

  - <span data-ttu-id="1bc6c-120">Lync 2013-beständiger Chat</span><span class="sxs-lookup"><span data-stu-id="1bc6c-120">Lync 2013 Persistent Chat</span></span>

<span data-ttu-id="1bc6c-121">Infolgedessen unterstützt das lync Server 2013-Tool Stress und Leistung das Testen der folgenden Komponenten nicht:</span><span class="sxs-lookup"><span data-stu-id="1bc6c-121">As a result, the Lync Server 2013 Stress and Performance Tool will not support testing the following components:</span></span>

  - <span data-ttu-id="1bc6c-122">Lync 2013-beständiger Chat</span><span class="sxs-lookup"><span data-stu-id="1bc6c-122">Lync 2013 Persistent Chat</span></span>

  - <span data-ttu-id="1bc6c-123">Exchange-Integrationsszenarien</span><span class="sxs-lookup"><span data-stu-id="1bc6c-123">Exchange integration scenarios</span></span>

<div>

## <a name="applications-and-files-included-with-the-lync-server-2013-stress-and-performance-tool"></a><span data-ttu-id="1bc6c-124">Im Lieferumfang des lync Server 2013-Tools für Stress und Leistung enthaltene Anwendungen und Dateien</span><span class="sxs-lookup"><span data-stu-id="1bc6c-124">Applications and Files Included with the Lync Server 2013 Stress and Performance Tool</span></span>

<span data-ttu-id="1bc6c-125">Die folgenden Anwendungen sind im Stress-und Leistungs Tool von lync Server 2013 enthalten:</span><span class="sxs-lookup"><span data-stu-id="1bc6c-125">The following applications are included in the Lync Server 2013 Stress and Performance Tool:</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="1bc6c-126">Tool</span><span class="sxs-lookup"><span data-stu-id="1bc6c-126">Tool</span></span></th>
<th><span data-ttu-id="1bc6c-127">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="1bc6c-127">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="1bc6c-128">UserProvisioningTool. exe</span><span class="sxs-lookup"><span data-stu-id="1bc6c-128">UserProvisioningTool.exe</span></span></p></td>
<td><p><span data-ttu-id="1bc6c-129">Das lync Server 2013-Bereitstellungstool für Benutzer.</span><span class="sxs-lookup"><span data-stu-id="1bc6c-129">The Lync Server 2013 User Provisioning tool.</span></span> <span data-ttu-id="1bc6c-130">Dieses Tool dient zum Erstellen von Benutzern und Kontakten.</span><span class="sxs-lookup"><span data-stu-id="1bc6c-130">This tool is used to create users and contacts.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1bc6c-131">UserProfileGenerator. exe</span><span class="sxs-lookup"><span data-stu-id="1bc6c-131">UserProfileGenerator.exe</span></span></p></td>
<td><p><span data-ttu-id="1bc6c-132">Das lync Server 2013 Load Configuration Tool.</span><span class="sxs-lookup"><span data-stu-id="1bc6c-132">The Lync Server 2013 Load Configuration Tool.</span></span> <span data-ttu-id="1bc6c-133">Dieses Tool dient zum Konfigurieren der Eigenschaften der Benutzerauslastung, die simuliert werden soll.</span><span class="sxs-lookup"><span data-stu-id="1bc6c-133">This tool is used to configure the characteristics of the user load to simulate.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1bc6c-134">LyncPerfTool. exe</span><span class="sxs-lookup"><span data-stu-id="1bc6c-134">LyncPerfTool.exe</span></span></p></td>
<td><p><span data-ttu-id="1bc6c-135">Das lync Server 2013-Tool für Stress und Leistung.</span><span class="sxs-lookup"><span data-stu-id="1bc6c-135">The Lync Server 2013 Stress and Performance Tool.</span></span> <span data-ttu-id="1bc6c-136">LyncPerfTool ist das Tool, das die Benutzerauslastung simuliert.</span><span class="sxs-lookup"><span data-stu-id="1bc6c-136">LyncPerfTool is the tool that simulates the user load.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1bc6c-137">Standard. TMX</span><span class="sxs-lookup"><span data-stu-id="1bc6c-137">Default.tmx</span></span></p></td>
<td><p><span data-ttu-id="1bc6c-138">Standard. TMX ist erforderlich, um das lync Server 2013-Protokollierungs Tool zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="1bc6c-138">Default.tmx is required to use the Lync Server 2013 Logging Tool.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1bc6c-139">Beispiele für Bereitstellungsskripts</span><span class="sxs-lookup"><span data-stu-id="1bc6c-139">Example provisioning scripts</span></span></p></td>
<td><p><span data-ttu-id="1bc6c-140">Diese Beispiele werden verwendet, um die Topologie für die Ausführung von Auslastungstests basierend auf bestimmten Szenarien zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="1bc6c-140">These examples are used to configure the topology for running load tests, based on specific scenarios</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

