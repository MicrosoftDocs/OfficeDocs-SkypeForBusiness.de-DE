---
title: Die Cmdlets für die Skype for Business Online Berichterstellung und Rest-Webdienst
description: Die Skype for Business Online Cmdlets für die Berichterstellung und Rest-Webdienst.
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: The Skype for Business Online reporting cmdlets and REST web service
ms:assetid: cadd73a7-c08a-4102-b73a-ccb3ad4987bf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn362845(v=OCS.15)
ms:contentKeyID: 56563409
ms.date: 05/04/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f2160e0910d42f811ec8b03fa50450d5f73c59b1
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48567941"
---
# <a name="the-skype-for-business-online-reporting-cmdlets-and-rest-web-service"></a><span data-ttu-id="780c2-103">Die Cmdlets für die Skype for Business Online Berichterstellung und Rest-Webdienst</span><span class="sxs-lookup"><span data-stu-id="780c2-103">The Skype for Business Online reporting cmdlets and REST web service</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="780c2-104">_**Letztes Änderungsstand des Themas:** 2014-09-05_</span><span class="sxs-lookup"><span data-stu-id="780c2-104">_**Topic Last Modified:** 2014-09-05_</span></span>

<span data-ttu-id="780c2-105">In Verbindung mit den Berichtsfeatures bietet Skype for Business Online Zugriff auf fünf Windows PowerShell-Cmdlets, mit denen diese Berichte generiert werden können und von Administratoren auch zum Zurückgeben benutzerdefinierter Berichtsdaten verwendet werden können.</span><span class="sxs-lookup"><span data-stu-id="780c2-105">In conjunction with the reporting features, Skype for Business Online provides access to five Windows PowerShell cmdlets that help generate those reports and are also can be used by administrators to return customized reporting data.</span></span> <span data-ttu-id="780c2-106">Skype for Business Online enthält auch den Rest (Representational State Transfer), der von Entwicklern zum Abrufen benutzerdefinierter Berichtsinformationen verwendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="780c2-106">Skype for Business Online also includes the REST (Representational State Transfer), which can be used by developers to retrieve customized reporting information.</span></span>

<span data-ttu-id="780c2-107">Die für Administratoren verfügbaren Berichts-Cmdlets umfassen Folgendes:</span><span class="sxs-lookup"><span data-stu-id="780c2-107">The reporting cmdlets available to administrators include:</span></span>

  - <span data-ttu-id="780c2-108">Get-CsActiveUserReport, das Informationen zur Anzahl der aktiven Benutzer bereitstellt (Benutzer, die sich bei Skype for Business Online angemeldet haben und an mindestens einer Konferenz oder einer Peer-to-Peer-Kommunikationssitzung teilgenommen haben).</span><span class="sxs-lookup"><span data-stu-id="780c2-108">Get-CsActiveUserReport, which provides information about the number of active users (that is, users who have logged on to Skype for Business Online and participated in at least one conference or peer-to-peer communication session).</span></span>

  - <span data-ttu-id="780c2-109">Get-CsAVConferenceTimeReport, das Informationen über den Zeitraum (in Minuten), den Benutzer in Audio/Video-Konferenzen verbracht haben, bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="780c2-109">Get-CsAVConferenceTimeReport, which provides information about the amount of time (in minutes) users spent in audio/video conferences.</span></span>

  - <span data-ttu-id="780c2-110">Get-CsConferenceReport, das Informationen über die Anzahl und den Typ von Konferenzen bereitstellt, an denen Benutzer teilgenommen haben.</span><span class="sxs-lookup"><span data-stu-id="780c2-110">Get-CsConferenceReport, which provides information about the number and type of conferences that users participated in.</span></span>

  - <span data-ttu-id="780c2-111">Get-CsP2PAVTimeReport, das Informationen über den Zeitraum (in Minuten), den Benutzer in Peer-to-Peer-Sitzungen mit Audio-und/oder Videodaten verbracht haben.</span><span class="sxs-lookup"><span data-stu-id="780c2-111">Get-CsP2PAVTimeReport, which provides information about the amount of time (in minutes) users spent in peer-to-peer sessions that included audio and/or video.</span></span>

  - <span data-ttu-id="780c2-112">Get-CsP2PSessionReport, das Informationen über die Anzahl und den Typ von Peer-zu-Peer-Sitzungen bereitstellt, an denen Benutzer teilgenommen haben.</span><span class="sxs-lookup"><span data-stu-id="780c2-112">Get-CsP2PSessionReport, which provides information about the number and type of peer-to-peer sessions that users participated in.</span></span>

<span data-ttu-id="780c2-113">Die meisten Administratoren verwenden die Berichte, die im Microsoft 365 Admin Center zur Verfügung stehen: Diese Berichte werden nicht nur automatisch generiert, sondern bieten auch eine grafische Darstellung der Daten, die häufig einfacher zu interpretieren sind als die von den Berichts-Cmdlets zurückgegebenen unformatierten Zahlenwerte.</span><span class="sxs-lookup"><span data-stu-id="780c2-113">Most administrators will use the reports available in the Microsoft 365 admin center: not only are those reports auto-generated, but they also provide a graphical representation of the data that is often easier to interpret than the raw number values returned by the reporting cmdlets.</span></span> <span data-ttu-id="780c2-114">Administratoren, die mit Windows PowerShell vertraut sind, können jedoch mithilfe der Cmdlets für die Berichterstellung Daten zurückgeben, die in den lync Online Berichten nicht leicht verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="780c2-114">However, administrators familiar with Windows PowerShell can use the reporting cmdlets to return data that is not readily available from the Lync Online reports.</span></span> <span data-ttu-id="780c2-115">Beispielsweise werden mit den Cmdlets für die Berichterstellung Informationen zur Sitzungsdauer zurückgegeben (der Zeitraum in Minuten, in dem jede Sitzung dauerte).</span><span class="sxs-lookup"><span data-stu-id="780c2-115">For example, the reporting cmdlets return information about session duration (the amount of time, in minutes, that each session lasted).</span></span> <span data-ttu-id="780c2-116">Einzelne Sitzungsdauer sind nicht verfügbar, wenn Sie die lync Online Berichte verwenden.</span><span class="sxs-lookup"><span data-stu-id="780c2-116">Individual session durations are not available using the Lync Online reports.</span></span> <span data-ttu-id="780c2-117">Dementsprechend werden in den lync Online Berichten in der täglichen Ansicht nur Informationen für die vorhergehenden 14 Tage angezeigt.</span><span class="sxs-lookup"><span data-stu-id="780c2-117">Likewise, in daily view the Lync Online reports display information only for the preceding 14 days.</span></span> <span data-ttu-id="780c2-118">Wenn Sie die Tagessummen für einen anderen Tag (beispielsweise ein Datum aus vier Monaten) überprüfen möchten, können Sie dies mithilfe der Cmdlets für die Berichterstellung tun.</span><span class="sxs-lookup"><span data-stu-id="780c2-118">If you would like to review the daily totals for a different day (for example, a date from four months ago) you can do so by using the reporting cmdlets.</span></span>

<span data-ttu-id="780c2-119">Administratoren sind möglicherweise auch an dem Artikel interessiert, der [Excel zum Abrufen von Office 365 Berichtsdaten](https://msdn.microsoft.com/library/dn781442.aspx)verwendet, in dem die Verwendung der OData-Datenabfrage Funktion in Microsoft Excel zum Erstellen eines benutzerdefinierten Office 365-Berichts erläutert wird.</span><span class="sxs-lookup"><span data-stu-id="780c2-119">Administrators might also be interested in the article [Using Excel to Retrieve Office 365 Reporting Data](https://msdn.microsoft.com/library/dn781442.aspx), which explains how to use the OData data querying feature in Microsoft Excel to create custom office 365 report.</span></span> <span data-ttu-id="780c2-120">Benutzerdefinierte Berichte bieten Ihnen die Möglichkeit zu diktieren, welche Daten (und wie viele Daten) vom Office 365 Berichtsdienst zurückgegeben werden.</span><span class="sxs-lookup"><span data-stu-id="780c2-120">Custom reports give you the ability to dictate which data (and how much data) is returned from the Office 365 reporting service.</span></span> <span data-ttu-id="780c2-121">Mit benutzerdefinierten Berichten können Sie auch solche Dinge tun, die angeben, wie die Daten sortiert und gruppiert werden sollen, und den Zugriff auf Informationen ermöglichen, die nicht im Admin Center angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="780c2-121">Custom reports also enable you to do such things as specify how the data should be sorted and grouped, and provide access to information that is not displayed in the admin center.</span></span>

<span data-ttu-id="780c2-122">Administratoren mit Entwicklungshintergrund können mithilfe des Rest-Webdiensts Informationen abrufen, die nicht im Skype for Business Online Admin Center angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="780c2-122">Administrators with a development background can use the REST web service to obtain information not displayed in the Skype for Business Online admin center.</span></span> <span data-ttu-id="780c2-123">Der Rest-Dienst ähnelt dem SOAP-Dienst, da jede Technologie eine Möglichkeit bietet, XML-Daten zwischen einem Client und einem Server zu übertragen.</span><span class="sxs-lookup"><span data-stu-id="780c2-123">The REST service is similar to the SOAP service, in that each technology provides a way to transfer XML data between a client and a server.</span></span> <span data-ttu-id="780c2-124">Der Rest-Dienst verfügt jedoch über mindestens zwei Vorteile gegenüber dem SOAP-Dienst.</span><span class="sxs-lookup"><span data-stu-id="780c2-124">However, the REST service has at least two advantages over the SOAP service.</span></span> <span data-ttu-id="780c2-125">Für einen übernimmt Rest XML-Datenübertragungen unter Verwendung eines standardisierten Formats, das als Atom-Veröffentlichungsformat bezeichnet wird.</span><span class="sxs-lookup"><span data-stu-id="780c2-125">For one, REST performs XML data transfers using a standardized format known as the ATOM syndication format.</span></span> <span data-ttu-id="780c2-126">Im Gegensatz dazu verwendet SOAP ein nicht standardmäßiges Format beim Übertragen von Daten.</span><span class="sxs-lookup"><span data-stu-id="780c2-126">By contrast, SOAP using a non-standard format when transferring data.</span></span> <span data-ttu-id="780c2-127">Darüber hinaus kann Rest Daten über Netzwerke übertragen, die HTTP-Verben außer Get und Post blockieren.</span><span class="sxs-lookup"><span data-stu-id="780c2-127">In addition, REST is able to transfer data across networks that block HTTP verbs other than GET and POST.</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="780c2-128">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="780c2-128">See Also</span></span>


<span data-ttu-id="780c2-129">[Lync Online Berichterstellung](https://technet.microsoft.com/library/dn362827\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="780c2-129">[Lync Online reporting](https://technet.microsoft.com/library/dn362827\(v=ocs.15\))</span></span>  


[<span data-ttu-id="780c2-130">Der Webdienst für die Office 365-Berichterstellung</span><span class="sxs-lookup"><span data-stu-id="780c2-130">The Office 365 Reporting Web Service</span></span>](https://msdn.microsoft.com/library/office/jj984325.aspx)  
[<span data-ttu-id="780c2-131">Informationen zum Webdienst "Office 365-Berichterstellung"</span><span class="sxs-lookup"><span data-stu-id="780c2-131">Learning About the Office 365 Reporting Web Service</span></span>](https://msdn.microsoft.com/library/office/jj984321.aspx)  
<span data-ttu-id="780c2-132">[Die Cmdlets für die Exchange Online-Berichterstellung](https://technet.microsoft.com/library/jj200780\(v=exchg.150\).aspx)</span><span class="sxs-lookup"><span data-stu-id="780c2-132">[The Exchange Online Reporting Cmdlets](https://technet.microsoft.com/library/jj200780\(v=exchg.150\).aspx)</span></span>  
[<span data-ttu-id="780c2-133">Verwenden von Excel zum Abrufen von Office 365-Berichterstellungsdaten</span><span class="sxs-lookup"><span data-stu-id="780c2-133">Using Excel to Retrieve Office 365 Reporting Data</span></span>](https://msdn.microsoft.com/library/dn781442.aspx)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

