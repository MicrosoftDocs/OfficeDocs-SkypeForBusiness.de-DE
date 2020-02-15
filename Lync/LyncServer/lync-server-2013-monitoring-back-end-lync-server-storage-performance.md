---
title: 'Lync Server 2013: Überwachen der Back-End-lync Server Speicherleistung'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Monitoring back end Lync Server 2013 storage performance
ms:assetid: 71627c70-1953-4ac2-afbe-f3ad85be0f44
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720917(v=OCS.15)
ms:contentKeyID: 63969619
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 760e66403fd1da2b5a45cf0db065dc201e1fd02a
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42051157"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="monitoring-back-end-lync-server-2013-storage-performance"></a><span data-ttu-id="7d6ed-102">Überwachen der Back-End-lync Server 2013 Speicherleistung</span><span class="sxs-lookup"><span data-stu-id="7d6ed-102">Monitoring back end Lync Server 2013 storage performance</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7d6ed-103">_**Letztes Änderungsstand des Themas:** 2014-05-02_</span><span class="sxs-lookup"><span data-stu-id="7d6ed-103">_**Topic Last Modified:** 2014-05-02_</span></span>

<span data-ttu-id="7d6ed-104">Die lync Server 2013 Back-End-Datenbanken sind ein sehr wichtiger Bestandteil der lync Server 2013-Bereitstellung.</span><span class="sxs-lookup"><span data-stu-id="7d6ed-104">The Lync Server 2013 back-end databases are a very important part of the Lync Server 2013 deployment.</span></span> <span data-ttu-id="7d6ed-105">Es wird empfohlen, die Datenbanken und die entsprechenden Transaktionsprotokolle ständig zu überwachen, um sicherzustellen, dass das lync Server 2013 Back-End optimal ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="7d6ed-105">We recommend constantly monitoring the databases and respective transaction logs to help to make sure that the Lync Server 2013 back end is performing optimally.</span></span>

<span data-ttu-id="7d6ed-106">In der folgenden Tabelle werden Leistungsindikatoren aufgeführt, die überwacht werden sollten, um Informationen zur Speicherleistung zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="7d6ed-106">The following table identifies performance counters that should be monitored to learn information about Storage Performance.</span></span> <span data-ttu-id="7d6ed-107">Die Basiswerte für diese Leistungsindikatoren müssen zuerst bestimmt werden (wenn das System normal ist, die erwartete Last), um die Leistungsänderungen zu verstehen, wenn das System beansprucht wird.</span><span class="sxs-lookup"><span data-stu-id="7d6ed-107">The baseline values for these counters must be determined first (when system is at its normal, expected load) to understand the performance changes when system is stressed.</span></span>

### <a name="performance-counters-to-be-monitored"></a><span data-ttu-id="7d6ed-108">Zu überwachende Leistungsindikatoren</span><span class="sxs-lookup"><span data-stu-id="7d6ed-108">Performance counters to be monitored</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="7d6ed-109">Leistungsindikator</span><span class="sxs-lookup"><span data-stu-id="7d6ed-109">Performance Counter</span></span></th>
<th><span data-ttu-id="7d6ed-110">Baseline-Schwellenwerte</span><span class="sxs-lookup"><span data-stu-id="7d6ed-110">Baseline thresholds</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="7d6ed-111">Transaktionen/s (RTC)</span><span class="sxs-lookup"><span data-stu-id="7d6ed-111">Transactions/sec (RTC)</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7d6ed-112">Transaktionen/Sek. (RTCDyn)</span><span class="sxs-lookup"><span data-stu-id="7d6ed-112">Transactions/sec (rtcdyn)</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7d6ed-113">Transaktionen/SEK (tempdb)</span><span class="sxs-lookup"><span data-stu-id="7d6ed-113">Transactions/sec (tempdb)</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7d6ed-114">Protokollleerungen/s (RTC)</span><span class="sxs-lookup"><span data-stu-id="7d6ed-114">Log Flushes/sec (RTC)</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7d6ed-115">Protokollleerungen/Sek. (RTCDyn)</span><span class="sxs-lookup"><span data-stu-id="7d6ed-115">Log Flushes/sec (rtcdyn)</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7d6ed-116">Protokollleerungen/s (tempdb)</span><span class="sxs-lookup"><span data-stu-id="7d6ed-116">Log Flushes/sec (tempdb)</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7d6ed-117">Datenträgerübertragungen/SEK (Lesen + Schreiben) – RTC-DB</span><span class="sxs-lookup"><span data-stu-id="7d6ed-117">Disk Transfers/sec (read+write) - RTC db</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7d6ed-118">Datenträgerübertragungen/SEK-RTC-Protokoll</span><span class="sxs-lookup"><span data-stu-id="7d6ed-118">Disk Transfers/sec - RTC log</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7d6ed-119">Datenträgerübertragungen/SEK-RTCDyn DB</span><span class="sxs-lookup"><span data-stu-id="7d6ed-119">Disk Transfers/sec - rtcdyn db</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7d6ed-120">Datenträgerübertragungen/SEK-RTCdyn-Protokoll</span><span class="sxs-lookup"><span data-stu-id="7d6ed-120">Disk Transfers/sec - rtcdyn log</span></span></p></td>
<td></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

