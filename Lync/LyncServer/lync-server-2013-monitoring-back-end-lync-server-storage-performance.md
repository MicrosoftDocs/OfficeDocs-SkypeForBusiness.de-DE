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
ms.openlocfilehash: aad04524df22c9d299b4a871b580330052d2aa5b
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/16/2020
ms.locfileid: "48531952"
---
# <a name="monitoring-back-end-lync-server-2013-storage-performance"></a><span data-ttu-id="0a100-102">Überwachen der Back-End-lync Server 2013 Speicherleistung</span><span class="sxs-lookup"><span data-stu-id="0a100-102">Monitoring back end Lync Server 2013 storage performance</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0a100-103">_**Letztes Änderungsstand des Themas:** 2014-05-02_</span><span class="sxs-lookup"><span data-stu-id="0a100-103">_**Topic Last Modified:** 2014-05-02_</span></span>

<span data-ttu-id="0a100-104">Die lync Server 2013 Back-End-Datenbanken sind ein sehr wichtiger Bestandteil der lync Server 2013-Bereitstellung.</span><span class="sxs-lookup"><span data-stu-id="0a100-104">The Lync Server 2013 back-end databases are a very important part of the Lync Server 2013 deployment.</span></span> <span data-ttu-id="0a100-105">Es wird empfohlen, die Datenbanken und die entsprechenden Transaktionsprotokolle ständig zu überwachen, um sicherzustellen, dass das lync Server 2013 Back-End optimal ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="0a100-105">We recommend constantly monitoring the databases and respective transaction logs to help to make sure that the Lync Server 2013 back end is performing optimally.</span></span>

<span data-ttu-id="0a100-106">In der folgenden Tabelle werden Leistungsindikatoren aufgeführt, die überwacht werden sollten, um Informationen zur Speicherleistung zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="0a100-106">The following table identifies performance counters that should be monitored to learn information about Storage Performance.</span></span> <span data-ttu-id="0a100-107">Die Basiswerte für diese Leistungsindikatoren müssen zuerst bestimmt werden (wenn das System normal ist, die erwartete Last), um die Leistungsänderungen zu verstehen, wenn das System beansprucht wird.</span><span class="sxs-lookup"><span data-stu-id="0a100-107">The baseline values for these counters must be determined first (when system is at its normal, expected load) to understand the performance changes when system is stressed.</span></span>

### <a name="performance-counters-to-be-monitored"></a><span data-ttu-id="0a100-108">Zu überwachende Leistungsindikatoren</span><span class="sxs-lookup"><span data-stu-id="0a100-108">Performance counters to be monitored</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="0a100-109">Leistungsindikator</span><span class="sxs-lookup"><span data-stu-id="0a100-109">Performance Counter</span></span></th>
<th><span data-ttu-id="0a100-110">Baseline-Schwellenwerte</span><span class="sxs-lookup"><span data-stu-id="0a100-110">Baseline thresholds</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="0a100-111">Transaktionen/s (RTC)</span><span class="sxs-lookup"><span data-stu-id="0a100-111">Transactions/sec (RTC)</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0a100-112">Transaktionen/Sek. (RTCDyn)</span><span class="sxs-lookup"><span data-stu-id="0a100-112">Transactions/sec (rtcdyn)</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0a100-113">Transaktionen/SEK (tempdb)</span><span class="sxs-lookup"><span data-stu-id="0a100-113">Transactions/sec (tempdb)</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0a100-114">Protokollleerungen/s (RTC)</span><span class="sxs-lookup"><span data-stu-id="0a100-114">Log Flushes/sec (RTC)</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0a100-115">Protokollleerungen/Sek. (RTCDyn)</span><span class="sxs-lookup"><span data-stu-id="0a100-115">Log Flushes/sec (rtcdyn)</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0a100-116">Protokollleerungen/s (tempdb)</span><span class="sxs-lookup"><span data-stu-id="0a100-116">Log Flushes/sec (tempdb)</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0a100-117">Datenträgerübertragungen/SEK (Lesen + Schreiben) – RTC-DB</span><span class="sxs-lookup"><span data-stu-id="0a100-117">Disk Transfers/sec (read+write) - RTC db</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0a100-118">Datenträgerübertragungen/SEK-RTC-Protokoll</span><span class="sxs-lookup"><span data-stu-id="0a100-118">Disk Transfers/sec - RTC log</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0a100-119">Datenträgerübertragungen/SEK-RTCDyn DB</span><span class="sxs-lookup"><span data-stu-id="0a100-119">Disk Transfers/sec - rtcdyn db</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0a100-120">Datenträgerübertragungen/SEK-RTCdyn-Protokoll</span><span class="sxs-lookup"><span data-stu-id="0a100-120">Disk Transfers/sec - rtcdyn log</span></span></p></td>
<td></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

