---
title: 'Lync Server 2013: Abrufen eines Standorts'
description: 'Lync Server 2013: Abrufen eines Standorts.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Acquiring a location
ms:assetid: 9bf069aa-d240-4d95-be3a-e795537f8e70
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205110(v=OCS.15)
ms:contentKeyID: 48184903
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 25aa907b5373cadd9eb8ffe9e32a7531afa01deb
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48571111"
---
# <a name="acquiring-a-location-in-lync-server-2013"></a><span data-ttu-id="83d1c-103">Erwerben eines Standorts in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="83d1c-103">Acquiring a location in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="83d1c-104">_**Letztes Änderungsstand des Themas:** 2012-06-06_</span><span class="sxs-lookup"><span data-stu-id="83d1c-104">_**Topic Last Modified:** 2012-06-06_</span></span>

<span data-ttu-id="83d1c-105">In einer lync Server 2013 E9-1 -1-Bereitstellung erwirbt jeder intern verbundene lync-oder lync Phone Edition-Client aktiv einen eigenen Standort.</span><span class="sxs-lookup"><span data-stu-id="83d1c-105">In a Lync Server 2013 E9-1-1 deployment, each internally-connected Lync or Lync Phone Edition client actively acquires its own location.</span></span> <span data-ttu-id="83d1c-106">Nach der SIP-Registrierung stellt der Client alle Netzwerk Verbindungsinformationen bereit, die er über sich selbst in einer standortanforderung an den Standortinformationsdienst kennt, bei dem es sich um einen Webdienst handelt, der von einer replizierten SQL Server Datenbank unterstützt wird.</span><span class="sxs-lookup"><span data-stu-id="83d1c-106">After SIP registration, the client furnishes all the network connectivity information that it knows about itself it in a location request to the Location Information service, which is a web service backed by a replicated SQL Server database.</span></span> <span data-ttu-id="83d1c-107">Jeder zentrale Website Pool verfügt über eine Standortinformationsdienst, die die Netzwerkinformationen verwendet, um die Datensätze für einen passenden Speicherort abzufragen.</span><span class="sxs-lookup"><span data-stu-id="83d1c-107">Each central site pool has a Location Information service, which uses the network information to query its records for a matching location.</span></span> <span data-ttu-id="83d1c-108">Wenn eine Übereinstimmung vorliegt, gibt der Standortinformationsdienst einen Speicherort an den Client zurück.</span><span class="sxs-lookup"><span data-stu-id="83d1c-108">If there is a match, the Location Information service returns a location to the client.</span></span> <span data-ttu-id="83d1c-109">Wird keine Übereinstimmung ermittelt, wird der Benutzer möglicherweise zur manuellen Eingabe eines Standorts aufgefordert (abhängig von den Einstellungen in der Ortungsrichtlinie).</span><span class="sxs-lookup"><span data-stu-id="83d1c-109">If there is not a match, the user may be prompted to enter a location manually (depending on location policy settings).</span></span> <span data-ttu-id="83d1c-110">Die Standortdaten werden in einem standardisierten IETF-XML-Format (Internet Engineering Task Force), das als PIDF-LO (Presence Information Data Format Location Object) bezeichnet wird, zurück an den Client übertragen.</span><span class="sxs-lookup"><span data-stu-id="83d1c-110">The location data are transmitted back to the client in an Internet Engineering Task Force (IETF) standardized XML format called Presence Information Data Format Location Object (PIDF-LO).</span></span>

<span data-ttu-id="83d1c-111">Der lync Server-Client enthält die PIDF-Lo-Daten im Rahmen eines Notrufs, und diese Daten werden vom E9-1 -1-Dienstanbieter verwendet, um den entsprechenden Rettungsleitstelle zu ermitteln und den Anruf an diesen Rettungsleitstelle zusammen mit dem korrekten ESQK weiterzuleiten, sodass der Rettungsleitstelle Dispatcher den Standort des Anrufers abrufen kann.</span><span class="sxs-lookup"><span data-stu-id="83d1c-111">The Lync Server client includes the PIDF-LO data as part of an emergency call, and this data is used by the E9-1-1 service provider to determine the appropriate PSAP and route the call to that PSAP along with the correct ESQK, which allows the PSAP dispatcher to obtain the caller’s location.</span></span>

<span data-ttu-id="83d1c-112">Das folgende Diagramm zeigt, wie ein lync Server-Client einen Standort erwirbt (mit Ausnahme der Adress basierten Ortungsmethode eines Drittanbieters für Client Mac):</span><span class="sxs-lookup"><span data-stu-id="83d1c-112">The following diagram shows how a Lync Server client acquires a location (except for the third-party client MAC address–based location method):</span></span>

<span data-ttu-id="83d1c-113">![So erwirbt Client ein Standort Diagramm](images/JJ205110.4438f5fc-f1b2-444b-8565-09035363ed43(OCS.15).jpg "So erwirbt Client ein Standort Diagramm")</span><span class="sxs-lookup"><span data-stu-id="83d1c-113">![How Client Acquires a Location diagram](images/JJ205110.4438f5fc-f1b2-444b-8565-09035363ed43(OCS.15).jpg "How Client Acquires a Location diagram")</span></span>

<span data-ttu-id="83d1c-114">Damit ein Client einen Standort abrufen kann, müssen die folgenden Schritte ausgeführt werden:</span><span class="sxs-lookup"><span data-stu-id="83d1c-114">For a client to acquire a location, the following steps must take place:</span></span>

1.  <span data-ttu-id="83d1c-115">Der Administrator füllt die Standortinformationsdienst Datenbank mit dem Netzwerk Wiremap (Tabellen, die verschiedene Arten von Netzwerkadressen den entsprechenden Notfall Antwort Standorten zuordnen (ERLs)).</span><span class="sxs-lookup"><span data-stu-id="83d1c-115">The administrator populates the Location Information service database with the network wiremap (tables that map various types of network addresses to corresponding Emergency Response Locations (ERLs)).</span></span>

2.  <span data-ttu-id="83d1c-p102">Wenn Sie einen SIP-Trunk-E9-1-1-Dienstanbieter verwenden, überprüft der Administrator die Teile der ERLs mit den allgemeinen Adressen anhand einer MSAG (Master Street Address Guide)-Datenbank, die vom E9-1-1-Dienstanbieter verwaltet wird. Wenn Sie ein ELIN-Gateway verwenden, stellt der Administrator sicher, dass der PSTN-Netzbetreiber die ELINs in die ALI (Automatic Location Identification)-Datenbank hochlädt.</span><span class="sxs-lookup"><span data-stu-id="83d1c-p102">If you use a SIP trunk E9-1-1 service provider, the administrator validates the civic address portions of the ERLs against a Master Street Address Guide (MSAG) database maintained by the E9-1-1 service provider. If you use an ELIN gateway, the administrator ensures that the PSTN carrier uploads the ELINs to the Automatic Location Identification (ALI) database.</span></span>

3.  <span data-ttu-id="83d1c-118">Während der Registrierung oder wenn eine Netzwerkänderung erfolgt, sendet ein intern verbundener Client eine standortanforderung, die die ermittelten Netzwerkadressen des Clients enthält, an den Standortinformationsdienst.</span><span class="sxs-lookup"><span data-stu-id="83d1c-118">During registration or whenever a network change occurs, an internally-connected client sends a location request that contains the client's discovered network addresses to the Location Information service.</span></span>

4.  <span data-ttu-id="83d1c-119">Das Standortinformationsdienst fragt seine veröffentlichten Datensätze nach einem Speicherort ab und gibt, wenn eine Übereinstimmung gefunden wird, das Erl an den Client im PIDF-Lo-Format zurück.</span><span class="sxs-lookup"><span data-stu-id="83d1c-119">The Location Information service queries its published records for a location, and, if a match is found, returns the ERL to the client in PIDF-LO format.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

