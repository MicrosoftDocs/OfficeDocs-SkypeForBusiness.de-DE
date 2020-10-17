---
title: Einführung
description: Einführung in.
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Introduction
ms:assetid: 276395be-93df-4a16-97e2-cb468cd0f2e3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945588(v=OCS.15)
ms:contentKeyID: 51541414
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8eb847c499bde077ccaf2aa050de801ceeedcc6f
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48565281"
---
# <a name="introduction"></a><span data-ttu-id="d5d9e-103">Einführung</span><span class="sxs-lookup"><span data-stu-id="d5d9e-103">Introduction</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d5d9e-104">_**Letztes Änderungsstand des Themas:** 2013-02-24_</span><span class="sxs-lookup"><span data-stu-id="d5d9e-104">_**Topic Last Modified:** 2013-02-24_</span></span>

<span data-ttu-id="d5d9e-105">Das lync Server 2013 Stress and Performance-Tool (als LyncPerfTool bezeichnet) kann die Benutzerlast der folgenden Typen simulieren:</span><span class="sxs-lookup"><span data-stu-id="d5d9e-105">The Lync Server 2013 Stress and Performance Tool (referred to as LyncPerfTool) can simulate user load of the following types:</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d5d9e-106">Instant Messaging und Anwesenheit</span><span class="sxs-lookup"><span data-stu-id="d5d9e-106">Instant messaging (IM) and presence</span></span></p></td>
<td><p><span data-ttu-id="d5d9e-107">Audiokonferenz</span><span class="sxs-lookup"><span data-stu-id="d5d9e-107">Audio conferencing</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d5d9e-108">Anwendungsfreigabe</span><span class="sxs-lookup"><span data-stu-id="d5d9e-108">Application sharing</span></span></p></td>
<td><p><span data-ttu-id="d5d9e-109">VoIP (Voice over IP), einschließlich PSTN-Simulation (Public Switched Telephone Network)</span><span class="sxs-lookup"><span data-stu-id="d5d9e-109">Voice over IP (VoIP), including public switched telephone network (PSTN) simulation</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d5d9e-110">Webzugriffs-Client Konferenzen</span><span class="sxs-lookup"><span data-stu-id="d5d9e-110">Web Access Client conferencing</span></span></p></td>
<td><p><span data-ttu-id="d5d9e-111">Microsoft lync 2013 Attendant</span><span class="sxs-lookup"><span data-stu-id="d5d9e-111">Microsoft Lync 2013 Attendant</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d5d9e-112">Reaktionsgruppen</span><span class="sxs-lookup"><span data-stu-id="d5d9e-112">Response Groups</span></span></p></td>
<td><p><span data-ttu-id="d5d9e-113">Verteilerlistenerweiterung</span><span class="sxs-lookup"><span data-stu-id="d5d9e-113">Distribution list expansion</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d5d9e-114">Adressbuch Download und Adressbuch Abfrage</span><span class="sxs-lookup"><span data-stu-id="d5d9e-114">Address book download and address book query</span></span></p></td>
<td><p><span data-ttu-id="d5d9e-115">Enhanced 9-1-1 (E9-1-1) Anrufe und Standortprofil (Wählplan)</span><span class="sxs-lookup"><span data-stu-id="d5d9e-115">Enhanced 9-1-1 (E9-1-1) calls and location profile (dial plan)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d5d9e-116">MultiView</span><span class="sxs-lookup"><span data-stu-id="d5d9e-116">MultiView</span></span></p></td>
<td><p><span data-ttu-id="d5d9e-117">Anzeigen mehrerer Datenströme aus einer Konferenz</span><span class="sxs-lookup"><span data-stu-id="d5d9e-117">Viewing multiple streams from a conference</span></span></p></td>
</tr>
<tr class="odd">
<td></td>
<td></td>
</tr>
</tbody>
</table>


<span data-ttu-id="d5d9e-118">Das Tool für die lync Server 2013 Spannung und Leistung unterstützt die Generierung und den Verbund von Pool Lasten über erweiterte Konfigurationen.</span><span class="sxs-lookup"><span data-stu-id="d5d9e-118">The Lync Server 2013 Stress and Performance Tool supports cross-pool load generation and federation through advanced configuration only.</span></span>

<span data-ttu-id="d5d9e-119">Das Tool simuliert außerdem keine Benutzerlast für die folgenden Clients:</span><span class="sxs-lookup"><span data-stu-id="d5d9e-119">The tool also does not simulate user load for the following clients:</span></span>

  - <span data-ttu-id="d5d9e-120">Office Live Meeting 2007</span><span class="sxs-lookup"><span data-stu-id="d5d9e-120">Office Live Meeting 2007</span></span>

  - <span data-ttu-id="d5d9e-121">Lync 2013 beständiger Chat</span><span class="sxs-lookup"><span data-stu-id="d5d9e-121">Lync 2013 Persistent Chat</span></span>

<span data-ttu-id="d5d9e-122">Daher unterstützt das lync Server 2013 Stress and Performance-Tool nicht das Testen der folgenden Komponenten:</span><span class="sxs-lookup"><span data-stu-id="d5d9e-122">As a result, the Lync Server 2013 Stress and Performance Tool will not support testing the following components:</span></span>

  - <span data-ttu-id="d5d9e-123">Lync 2013 beständiger Chat</span><span class="sxs-lookup"><span data-stu-id="d5d9e-123">Lync 2013 Persistent Chat</span></span>

  - <span data-ttu-id="d5d9e-124">Exchange-Integrationsszenarien</span><span class="sxs-lookup"><span data-stu-id="d5d9e-124">Exchange integration scenarios</span></span>

<div>

## <a name="applications-and-files-included-with-the-lync-server-2013-stress-and-performance-tool"></a><span data-ttu-id="d5d9e-125">Im lync Server 2013 Stress and Performance Tool enthaltene Anwendungen und Dateien</span><span class="sxs-lookup"><span data-stu-id="d5d9e-125">Applications and Files Included with the Lync Server 2013 Stress and Performance Tool</span></span>

<span data-ttu-id="d5d9e-126">Die folgenden Anwendungen sind im lync Server 2013 Stress and Performance Tool enthalten:</span><span class="sxs-lookup"><span data-stu-id="d5d9e-126">The following applications are included in the Lync Server 2013 Stress and Performance Tool:</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="d5d9e-127">Tool</span><span class="sxs-lookup"><span data-stu-id="d5d9e-127">Tool</span></span></th>
<th><span data-ttu-id="d5d9e-128">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="d5d9e-128">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d5d9e-129">UserProvisioningTool.exe</span><span class="sxs-lookup"><span data-stu-id="d5d9e-129">UserProvisioningTool.exe</span></span></p></td>
<td><p><span data-ttu-id="d5d9e-130">Das lync Server 2013 Benutzer ProTools.</span><span class="sxs-lookup"><span data-stu-id="d5d9e-130">The Lync Server 2013 User Provisioning tool.</span></span> <span data-ttu-id="d5d9e-131">Dieses Tool wird zum Erstellen von Benutzern und Kontakten verwendet.</span><span class="sxs-lookup"><span data-stu-id="d5d9e-131">This tool is used to create users and contacts.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d5d9e-132">UserProfileGenerator.exe</span><span class="sxs-lookup"><span data-stu-id="d5d9e-132">UserProfileGenerator.exe</span></span></p></td>
<td><p><span data-ttu-id="d5d9e-133">Das lync Server 2013 Lade Konfigurations Tool.</span><span class="sxs-lookup"><span data-stu-id="d5d9e-133">The Lync Server 2013 Load Configuration Tool.</span></span> <span data-ttu-id="d5d9e-134">Dieses Tool dient zum Konfigurieren der Merkmale der Benutzerlast, die simuliert werden soll.</span><span class="sxs-lookup"><span data-stu-id="d5d9e-134">This tool is used to configure the characteristics of the user load to simulate.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d5d9e-135">LyncPerfTool.exe</span><span class="sxs-lookup"><span data-stu-id="d5d9e-135">LyncPerfTool.exe</span></span></p></td>
<td><p><span data-ttu-id="d5d9e-136">Das Tool für die lync Server 2013 Spannung und Leistung.</span><span class="sxs-lookup"><span data-stu-id="d5d9e-136">The Lync Server 2013 Stress and Performance Tool.</span></span> <span data-ttu-id="d5d9e-137">LyncPerfTool ist das Tool, mit dem die Benutzerlast simuliert wird.</span><span class="sxs-lookup"><span data-stu-id="d5d9e-137">LyncPerfTool is the tool that simulates the user load.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d5d9e-138">Standard. TMX</span><span class="sxs-lookup"><span data-stu-id="d5d9e-138">Default.tmx</span></span></p></td>
<td><p><span data-ttu-id="d5d9e-139">Standard. TMX ist für die Verwendung des lync Server 2013-Protokollierungstools erforderlich.</span><span class="sxs-lookup"><span data-stu-id="d5d9e-139">Default.tmx is required to use the Lync Server 2013 Logging Tool.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d5d9e-140">Beispielskripts für die Skriptverarbeitung</span><span class="sxs-lookup"><span data-stu-id="d5d9e-140">Example provisioning scripts</span></span></p></td>
<td><p><span data-ttu-id="d5d9e-141">Diese Beispiele werden verwendet, um die Topologie für das Durchführen von Auslastungstests basierend auf bestimmten Szenarien zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="d5d9e-141">These examples are used to configure the topology for running load tests, based on specific scenarios</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

