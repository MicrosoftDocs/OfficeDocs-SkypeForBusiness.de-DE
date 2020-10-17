---
title: 'Lync Server 2013: Planen und Konfigurieren von IPv6'
description: 'Lync Server 2013: Planen und Konfigurieren von IPv6.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Planning for and configuring IPv6
ms:assetid: 01f77196-38f4-4292-9480-2e2fbd57eabe
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204624(v=OCS.15)
ms:contentKeyID: 48183236
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2c63268bd92fc9d3b683cfa05ab49f01ea56d6ba
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48554361"
---
# <a name="planning-for-and-configuring-ipv6-in-lync-server-2013"></a><span data-ttu-id="ad59e-103">Planen und Konfigurieren von IPv6 in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ad59e-103">Planning for and configuring IPv6 in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ad59e-104">_**Letztes Änderungsstand des Themas:** 2012-06-14_</span><span class="sxs-lookup"><span data-stu-id="ad59e-104">_**Topic Last Modified:** 2012-06-14_</span></span>

<span data-ttu-id="ad59e-105">Lync Server 2013 enthält Unterstützung für IPv6-Adressen (IP Version 6) sowie die weitere Unterstützung von IPv4-Adressen (IP Version 4).</span><span class="sxs-lookup"><span data-stu-id="ad59e-105">Lync Server 2013 includes support for IP version 6 (IPv6) addresses, along with continued support of IP version 4 (IPv4) addresses.</span></span> <span data-ttu-id="ad59e-106">IPv4-Adressen sind 32-Bit-Adressen, mit denen ein Computer über das Internet kommunizieren kann.</span><span class="sxs-lookup"><span data-stu-id="ad59e-106">IPv4 addresses are 32-bit addresses that allow a computer to communicate over the Internet.</span></span> <span data-ttu-id="ad59e-107">Aufgrund der weltweit steigenden Anzahl von Geräten sind die verfügbaren IPv4-Adressen nicht mehr verfügbar. Aus diesem Grund werden viele neue Geräte in die Verwendung von IPv6-Adressen verschoben.</span><span class="sxs-lookup"><span data-stu-id="ad59e-107">Due to the increasing number of devices worldwide, the available IPv4 addresses have run out. Because of this, many new devices are moving to using IPv6 addresses.</span></span> <span data-ttu-id="ad59e-108">IPv6-Adressen führen dieselbe Funktion wie IPv4-Adressen aus (mit einigen zusätzlichen Funktionen), aber anstatt nur 32-Bits zu verwenden, verwenden IPv6-Adressen 128-Bits.</span><span class="sxs-lookup"><span data-stu-id="ad59e-108">IPv6 addresses perform the same function as IPv4 addresses (with some additional features), but instead of using only 32-bits, IPv6 addresses use 128-bits.</span></span> <span data-ttu-id="ad59e-109">Dies bietet nicht nur eine neue Gruppe von Adressen, sondern auch eine weitaus größere Anzahl von Adressen.</span><span class="sxs-lookup"><span data-stu-id="ad59e-109">This provides not only a new set of addresses, but also a much larger number of them.</span></span> <span data-ttu-id="ad59e-110">Eine typische IPv4-Adresse sieht etwa so aus: 192.0.2.235, wohingegen eine IPv6-Adresse wie folgt aussieht: 2001:0db8:85a3:0000:0000:8a2e: 0370:7334.</span><span class="sxs-lookup"><span data-stu-id="ad59e-110">A typical IPv4 address looks something like this: 192.0.2.235, whereas an IPv6 address looks like this: 2001:0db8:85a3:0000:0000:8a2e:0370:7334.</span></span> <span data-ttu-id="ad59e-111">Die Änderung der Formatierung und Funktionalität für Geräte, die IPv6-Adressen verwenden, erfordert in ihrer lync Server 2013 Installation verschiedene Überlegungen zur Bereitstellung und Konfiguration.</span><span class="sxs-lookup"><span data-stu-id="ad59e-111">The change in formatting and functionality for devices that use IPv6 addresses requires several deployment and configuration considerations in your Lync Server 2013 installation.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="ad59e-112">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="ad59e-112">In This Section</span></span>

  - [<span data-ttu-id="ad59e-113">Übersicht über IP-Adresstypen für lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ad59e-113">Overview of IP address types for Lync Server 2013</span></span>](lync-server-2013-overview-of-ip-address-types.md)

  - [<span data-ttu-id="ad59e-114">Technische Anforderungen für IPv6 in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ad59e-114">Technical requirements for IPv6 in Lync Server 2013</span></span>](lync-server-2013-technical-requirements-for-ipv6.md)

  - [<span data-ttu-id="ad59e-115">Überlegungen zu Migration und Koexistenz für IPv6 in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ad59e-115">Migration and coexistence considerations for IPv6 in Lync Server 2013</span></span>](lync-server-2013-migration-and-coexistence-considerations-for-ipv6.md)

  - [<span data-ttu-id="ad59e-116">Konfigurieren von IP-Adresstypen in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ad59e-116">Configure IP address types in Lync Server 2013</span></span>](lync-server-2013-configure-ip-address-types.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

