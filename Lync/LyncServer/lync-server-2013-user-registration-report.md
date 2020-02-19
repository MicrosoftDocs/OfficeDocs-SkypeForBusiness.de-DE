---
title: 'Lync Server 2013: Bericht über Benutzerregistrierung'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: User Registration Report
ms:assetid: 151d5cc9-cc1b-4cfa-be9c-55ebe321f7a4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558614(v=OCS.15)
ms:contentKeyID: 48183486
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 77edf04decc6aee7bb0cd292c1b5b0b38139a164
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2020
ms.locfileid: "42140808"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="user-registration-report-in-lync-server-2013"></a><span data-ttu-id="05935-102">Bericht über Benutzerregistrierung in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="05935-102">User Registration Report in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="05935-103">_**Letztes Änderungsstand des Themas:** 2012-10-21_</span><span class="sxs-lookup"><span data-stu-id="05935-103">_**Topic Last Modified:** 2012-10-21_</span></span>

<span data-ttu-id="05935-104">Der Bericht über Benutzerregistrierung bietet eine Übersicht über die Benutzeranmelde Aktivität, vor allem Informationen zur Anzahl der Benutzer, die sich in einem bestimmten Zeitraum bei Microsoft lync Server 2013 angemeldet haben (stündlich, täglich, wöchentlich, monatlich).</span><span class="sxs-lookup"><span data-stu-id="05935-104">The User Registration Report provides an overview of user logon activity, most notably information about the number of users who logged on to Microsoft Lync Server 2013 during a specified time period (hourly, daily, weekly, monthly).</span></span> <span data-ttu-id="05935-105">Beachten Sie, dass der Bericht nur die Anzahl der angemeldeten Personen enthält.</span><span class="sxs-lookup"><span data-stu-id="05935-105">Keep in mind that the report only tells you how many people logged on.</span></span> <span data-ttu-id="05935-106">Er enthält keine Informationen dazu, *welche* Personen sich angemeldet haben.</span><span class="sxs-lookup"><span data-stu-id="05935-106">It does not tell you *which* people logged on.</span></span> <span data-ttu-id="05935-107">Überwachungsberichte bieten keine Informationen darüber, welche bestimmten Benutzer lync Server 2013 verwenden (und welche nicht).</span><span class="sxs-lookup"><span data-stu-id="05935-107">Monitoring Reports do not provide information about which specific users are using Lync Server 2013 (and which ones are not).</span></span> <span data-ttu-id="05935-108">Der Bericht über Benutzeraktivität bietet jedoch eine grobe Schätzung in Bezug auf Benutzerinformationen.</span><span class="sxs-lookup"><span data-stu-id="05935-108">However, you can get a rough estimate of user information by using the User Activity Report.</span></span>

<span data-ttu-id="05935-109">Bei der Bereitstellung von Informationen zu Benutzeranmeldungen werden vom Bericht über Benutzerregistrierung zwei erhebliche Unterschiede hervorgehoben.</span><span class="sxs-lookup"><span data-stu-id="05935-109">When providing information about user logons, the User Registration Report draws two important distinctions.</span></span> <span data-ttu-id="05935-110">Zunächst werden die Anmeldungen in zwei Hauptkategorien unterteilt: interne Anmeldungen und externe Anmeldungen.</span><span class="sxs-lookup"><span data-stu-id="05935-110">First, it breaks logons down into two primary categories: internal logons and external logons.</span></span> <span data-ttu-id="05935-111">Bei internen Anmeldungen handelt es sich um Benutzer, die sich innerhalb der Fierwall Ihrer Organisation anmelden (d. h. während Sie mit dem Unternehmensnetzwerk verbunden sind).</span><span class="sxs-lookup"><span data-stu-id="05935-111">Internal logons represent users who logged on from inside your organization's firewall (that is, while connected to the corporate network).</span></span> <span data-ttu-id="05935-112">Externe Anmeldungen stellen Benutzer dar, die sich über eine Edgeserver von außerhalb der Firewall angemeldet haben (beispielsweise zählt ein Benutzer, der sich bei einem Internet Café angemeldet hat, als externe Anmeldung).</span><span class="sxs-lookup"><span data-stu-id="05935-112">External logons represent users who logged on from outside the firewall through an Edge Server (for example, a user who logged on from an Internet café counts as an external logon).</span></span> <span data-ttu-id="05935-113">Wenn Sie wissen möchten, wie viele Ihrer Benutzer sich außerhalb der Firewall anmelden, finden Sie diese Information im Bericht über Benutzerregistrierung.</span><span class="sxs-lookup"><span data-stu-id="05935-113">If you need to know how many of your users are logging on from outside the firewall, the User Registration Report can provide you with this information.</span></span>

<span data-ttu-id="05935-114">Der Bericht über Benutzerregistrierung enthält zudem Informationen darüber, wie viele *aktive* Benutzer in einem bestimmten Zeitraum anwesend waren.</span><span class="sxs-lookup"><span data-stu-id="05935-114">In addition, the User Registration Report notes how many *active* users were present during a given time period.</span></span> <span data-ttu-id="05935-115">Ein aktiver Benutzer ist ein Benutzer, der an einer Chatsitzung teilgenommen, an einer lync-Besprechung teilgenommen, einen Telefonanruf getätigt oder empfangen oder anderweitig lync Server in diesem Zeitraum verwendet hat.</span><span class="sxs-lookup"><span data-stu-id="05935-115">An active user is a user who took part in an instant messaging (IM) session, participated in a Lync Meeting, made or received a phone call, or otherwise used Lync Server during that period of time.</span></span> <span data-ttu-id="05935-116">Dadurch unterscheiden sich aktive Benutzer von Benutzern, die sich zwar angemeldet, das System aber nicht tatsächlich genutzt haben.</span><span class="sxs-lookup"><span data-stu-id="05935-116">This is different from a user who logged on, but never actually used the system.</span></span>

<div>

## <a name="accessing-the-user-registration-report"></a><span data-ttu-id="05935-117">Zugreifen auf den Bericht über Benutzerregistrierung</span><span class="sxs-lookup"><span data-stu-id="05935-117">Accessing the User Registration Report</span></span>

<span data-ttu-id="05935-p104">Sie können nur über die Homepage für Überwachungsberichte auf den Bericht über Benutzerregistrierung zugreifen. Der Bericht über Benutzerregistrierung ist nicht mit anderen Berichten verknüpft.</span><span class="sxs-lookup"><span data-stu-id="05935-p104">You access the User Registration Report only from the Monitoring Reports home page. The User Registration Report does not link to any other reports.</span></span>

</div>

<div>

## <a name="making-the-best-use-of-the-user-registration-report"></a><span data-ttu-id="05935-120">Optimale Nutzung des Berichts über Benutzerregistrierung</span><span class="sxs-lookup"><span data-stu-id="05935-120">Making the Best Use of the User Registration Report</span></span>

<span data-ttu-id="05935-121">Nachdem Sie lync Server einer häufig gestellten Frage bereitgestellt haben, lautet diese Vorgehensweise: Woher weiß ich, ob meine Benutzer diese neue Technologie tatsächlich verwenden?</span><span class="sxs-lookup"><span data-stu-id="05935-121">After you've deployed Lync Server one commonly-asked question is this: How do I know if my users are actually using this new technology?</span></span> <span data-ttu-id="05935-122">Der Bericht über Benutzerregistrierung weist in dieser Hinsicht zwar einige Einschränkungen auf, kann Ihnen aber dennoch bei der Beantwortung dieser Frage helfen.</span><span class="sxs-lookup"><span data-stu-id="05935-122">Although it has a few limitations in this regard, the User Registration Report can help you answer this question.</span></span> <span data-ttu-id="05935-123">Um festzustellen, ob Benutzer lync Server verwenden, müssen Sie zwei Dinge tun.</span><span class="sxs-lookup"><span data-stu-id="05935-123">To determine whether or not users are using Lync Server, you need to do two things.</span></span> <span data-ttu-id="05935-124">Rufen Sie zunächst den Wert der Metrik "Eindeutige angemeldete Benutzer" im Bericht über Benutzerregistrierung ab.</span><span class="sxs-lookup"><span data-stu-id="05935-124">First, get the value of the Unique logon users metric from the User Registration Report.</span></span> <span data-ttu-id="05935-125">Dieser Wert gibt an, wie viele unterschiedliche Personen bei lync Server angemeldet sind.</span><span class="sxs-lookup"><span data-stu-id="05935-125">This value tells you how many distinct individuals logged on to Lync Server.</span></span>

<span data-ttu-id="05935-126">Im Vergleich dazu zeigt die Metrik "Gesamt Anmeldungen" an, wie viele Personen insgesamt bei lync Server angemeldet sind.</span><span class="sxs-lookup"><span data-stu-id="05935-126">By comparison, the Total logons metric shows how many total times anyone logged on to Lync Server.</span></span> <span data-ttu-id="05935-127">Nehmen wir beispielsweise an, dass Ken Myers an einem einzigen Tag an lync Server fünf verschiedenen Zeiten angemeldet ist.</span><span class="sxs-lookup"><span data-stu-id="05935-127">For example, suppose Ken Myer logged on to Lync Server five different times in a single day.</span></span> <span data-ttu-id="05935-128">In diesem Fall zählt Ken Myer als fünf separate Anmeldesitzungen für die Metrik "Anmeldungen insgesamt", aber nur als ein angemeldeter Benutzer für die Metrik "Eindeutige angemeldete Benutzer".</span><span class="sxs-lookup"><span data-stu-id="05935-128">In that case, Ken Myer would count as five separate logon sessions for the Total logons metric, but just one logon user for the Unique logon users metric.</span></span> <span data-ttu-id="05935-129">Häufig melden sich Benutzer auch auf verschiedenen Geräten oder an verschiedenen Standorten an.</span><span class="sxs-lookup"><span data-stu-id="05935-129">Likewise, it's not uncommon for a user to log on from multiple devices or multiple locations.</span></span> <span data-ttu-id="05935-130">Beispielsweise kann sich ein Benutzer mit seinem Desktopcomputer, seinem Laptop Computer, anmelden, und er kann ein IP-Telefon haben, das sich automatisch bei lync Server anmeldet.</span><span class="sxs-lookup"><span data-stu-id="05935-130">For example, a user can log on using her desktop computer, her laptop computer, and she can have an IP phone that automatically logs on to Lync Server.</span></span> <span data-ttu-id="05935-131">In diesem Beispiel ist ein eindeutiger Benutzer mit drei Anmeldungen vorhanden.</span><span class="sxs-lookup"><span data-stu-id="05935-131">In this example, there is one unique user with three logons.</span></span>

<span data-ttu-id="05935-132">Sehen Sie sich in der folgenden Tabelle mit Anmeldungen in einem bestimmten Zeitraum an, in der der Unterschied zwischen Anmeldungen insgesamt und eindeutigen Anmeldungen näher erklärt ist.</span><span class="sxs-lookup"><span data-stu-id="05935-132">To further explain the difference between total logons and unique logons, consider the logons for a given time period in the following table.</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="05935-133">Benutzer</span><span class="sxs-lookup"><span data-stu-id="05935-133">User</span></span></th>
<th><span data-ttu-id="05935-134">Anmeldezeitpunkt</span><span class="sxs-lookup"><span data-stu-id="05935-134">Logon time</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="05935-135">Ken Myer</span><span class="sxs-lookup"><span data-stu-id="05935-135">Ken Myer</span></span></p></td>
<td><p><span data-ttu-id="05935-136">07.07.2012 08:45:00</span><span class="sxs-lookup"><span data-stu-id="05935-136">7/7/2012 8:45 AM</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="05935-137">Ken Myer</span><span class="sxs-lookup"><span data-stu-id="05935-137">Ken Myer</span></span></p></td>
<td><p><span data-ttu-id="05935-138">07.07.2012 08:46:00</span><span class="sxs-lookup"><span data-stu-id="05935-138">7/7/2012 8:46 AM</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="05935-139">Pilar Ackerman</span><span class="sxs-lookup"><span data-stu-id="05935-139">Pilar Ackerman</span></span></p></td>
<td><p><span data-ttu-id="05935-140">07.07.2012 09:17:00</span><span class="sxs-lookup"><span data-stu-id="05935-140">7/7/2012 9:17 AM</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="05935-141">Ken Myer</span><span class="sxs-lookup"><span data-stu-id="05935-141">Ken Myer</span></span></p></td>
<td><p><span data-ttu-id="05935-142">07.07.2012 09:22:00</span><span class="sxs-lookup"><span data-stu-id="05935-142">7/7/2012 9:22 AM</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="05935-143">Pilar Ackerman</span><span class="sxs-lookup"><span data-stu-id="05935-143">Pilar Ackerman</span></span></p></td>
<td><p><span data-ttu-id="05935-144">07.07.2012 09:31:00</span><span class="sxs-lookup"><span data-stu-id="05935-144">7/7/2012 9:31 AM</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="05935-p107">Insgesamt fanden fünf Anmeldungen statt, es sind jedoch nur zwei eindeutige angemeldete Benutzer vorhanden: Ken Myer (der sich dreimal angemeldet hat) und Pilar Ackerman (die sich zweimal angemeldet hat). Darin besteht der Unterschied zwischen Anmeldungen und eindeutigen angemeldeten Benutzern.</span><span class="sxs-lookup"><span data-stu-id="05935-p107">Notice that there is a total of five logons; however, there are only two unique logon users: Ken Myer (who logged on three times) and Pilar Ackerman (who logged on twice). That's the difference between logons and unique logon users.</span></span>

<span data-ttu-id="05935-147">Sie müssen nicht nur die Anzahl der eindeutigen Anmeldungen kennen, sondern auch die Gesamtzahl der Benutzer, die für lync Server aktiviert wurden.</span><span class="sxs-lookup"><span data-stu-id="05935-147">In addition to knowing the number of unique logons, you need to know the total number of users who have been enabled for Lync Server.</span></span> <span data-ttu-id="05935-148">Dieser Wert kann abgerufen werden, indem Sie die lync Server 2013-Verwaltungsshell öffnen und den folgenden Windows PowerShell-Befehl ausführen:</span><span class="sxs-lookup"><span data-stu-id="05935-148">That value can be retrieved by opening the Lync Server 2013 Management Shell and running the following Windows PowerShell command:</span></span>

    (Get-CsUser).Count

<span data-ttu-id="05935-149">Wenn der obige Befehl den Wert 1.236 zurückgibt und die Metrik für eindeutige Anmeldebenutzer einen durchschnittlichen Wert von 667 zurückgibt, deutet dies darauf hin, dass sich etwas mehr als die Hälfte der Benutzer für lync tatsächlich am System anmelden (d. 667 dividiert durch 1.236). , was ungefähr 54% beträgt.</span><span class="sxs-lookup"><span data-stu-id="05935-149">If the preceding command returns a value of 1,236 and Unique logon users metric returns an average value of 667, that suggests that a little over half of your users enable for Lync are actually logging on to the system each day (that is, 667 divided by 1,236, which is approximately 54%).</span></span>

<div>


> [!WARNING]  
> <span data-ttu-id="05935-150">Beachten Sie, dass die Metriken die Benutzer aufzeichnen, die sich tatsächlich im angegebenen Zeitraum angemeldet haben.</span><span class="sxs-lookup"><span data-stu-id="05935-150">Keep in mind that the logon metrics record users who actually logged on during the specified time period.</span></span> <span data-ttu-id="05935-151">Bereits am System angemeldete Benutzer werden nicht erfasst.</span><span class="sxs-lookup"><span data-stu-id="05935-151">They don't keep track of users who were already logged on to the system.</span></span> <span data-ttu-id="05935-152">Wenn die Metrik "Eindeutige angemeldete Benutzer" 667 Anmeldungen anzeigt und insgesamt 1.236 Benutzer vorhanden sind, deutet dies darauf hin, dass sich ca. die Hälfte Ihrer Benutzer am System anmeldet.</span><span class="sxs-lookup"><span data-stu-id="05935-152">For example, if your Unique logon users metric shows 667 logons and you have 1,236 users, that suggests that about half your users are logging on to the system.</span></span> <span data-ttu-id="05935-153">Angenommen jedoch, 300 Benutzer waren bereits am System angemeldet, als Sie begonnen haben, die Anmeldedaten zu überprüfen.</span><span class="sxs-lookup"><span data-stu-id="05935-153">However, suppose 300 users were already logged on to the system at the time you began checking the logon data.</span></span> <span data-ttu-id="05935-154">Das bedeutet, dass Sie tatsächlich fast 1.000 Benutzer bei lync Server angemeldet hatten, was dazu führen würde, dass näher an 80% ihrer Benutzer angemeldet waren.</span><span class="sxs-lookup"><span data-stu-id="05935-154">That would mean that you actually had nearly 1,000 users logged on to Lync Server, which would mean that closer to 80% of your users were logged on.</span></span>



</div>

<span data-ttu-id="05935-155">Vergleichen Sie auch den Wert "Eindeutige angemeldete Benutzer" mit dem Wert der Metrik "Eindeutige aktive Benutzer".</span><span class="sxs-lookup"><span data-stu-id="05935-155">You should also compare the Unique logon users value with the value of the Unique active users metric.</span></span> <span data-ttu-id="05935-156">Die Metrik "Unique Active Users" gibt an, wie viele eindeutige Benutzer lync Server tatsächlich verwendet haben: Sie haben einen Anruf getätigt, sich einer lync-Besprechung angeschlossen oder an einer Chatsitzung teilgenommen.</span><span class="sxs-lookup"><span data-stu-id="05935-156">The Unique active users metric tells you how many unique users actually used Lync Server: they made a phone call, they joined a Lync Meeting, or they participated in an IM session.</span></span> <span data-ttu-id="05935-157">Dies sind nützliche Informationen, da Microsoft lync 2013 so konfiguriert werden können, dass Sie bei jedem Start von Windows automatisch gestartet werden.</span><span class="sxs-lookup"><span data-stu-id="05935-157">This is useful information, because Microsoft Lync 2013 can be configured to automatically start each time a user starts Windows.</span></span> <span data-ttu-id="05935-158">Aus diesem Grund haben Sie möglicherweise eine große Anzahl von Benutzern, die sich automatisch bei lync anmelden, wenn Sie sich jeden Tag bei Windows anmelden, aber in diesem Zeitraum niemals tatsächlich lync Server verwenden.</span><span class="sxs-lookup"><span data-stu-id="05935-158">Because of that, you might have a large number of users who automatically log on to Lync when they log on to Windows each day, but then never actually use Lync Server during that time period.</span></span>

<span data-ttu-id="05935-159">Die Metrik "Unique Active Users" bietet auch aussagekräftigere Daten in einer Organisation, in der Benutzer normalerweise nicht am Ende des Tages Windows abmelden.</span><span class="sxs-lookup"><span data-stu-id="05935-159">The Unique active users metric also provides more meaningful data in an organization where users typically do not log off Windows at the end of the day.</span></span> <span data-ttu-id="05935-160">Stattdessen Sperren Sie einfach Ihre Computer und lassen Windows und lync auf dem laufenden.</span><span class="sxs-lookup"><span data-stu-id="05935-160">Instead, they simply lock their computers and leave Windows and Lync running.</span></span> <span data-ttu-id="05935-161">In einer solchen Situation erfolgen sehr wenige Anmeldungen pro Tag, da sich Benutzer vor einigen Tagen angemeldet und seitdem nicht mehr abgemeldet haben.</span><span class="sxs-lookup"><span data-stu-id="05935-161">In a situation like that, you might end up with very few logons per day because your users logged on several days ago and never logged off.</span></span> <span data-ttu-id="05935-162">Eindeutige aktive Benutzer erfahren jedoch, ob Benutzer lync oder einen anderen lync Server-Client aktiv verwenden.</span><span class="sxs-lookup"><span data-stu-id="05935-162">However, Unique active users tells you whether users are actively using Lync or another Lync Server client.</span></span>

</div>

<div>

## <a name="filters"></a><span data-ttu-id="05935-163">Filter</span><span class="sxs-lookup"><span data-stu-id="05935-163">Filters</span></span>

<span data-ttu-id="05935-164">Mithilfe von Filtern können Sie eine gezieltere Datenauswahl erreichen oder die zurückgegebenen Daten auf unterschiedliche Weise anzeigen.</span><span class="sxs-lookup"><span data-stu-id="05935-164">Filters provide a way for you to return a more finely targeted set of data or to view the returned data in different ways.</span></span> <span data-ttu-id="05935-165">Beispielsweise können Sie mit dem Bericht über Benutzerregistrierung Daten für alle Registrierungsstellen Pools und Edgeserver anzeigen oder Daten für einen einzelnen Pool anzeigen.</span><span class="sxs-lookup"><span data-stu-id="05935-165">For example, the User Registration Report enables you to view data for all your Registrar pool and Edge Servers or to view data for an individual pool.</span></span> <span data-ttu-id="05935-166">Sie können außerdem festlegen, wie Daten gruppiert werden sollen.</span><span class="sxs-lookup"><span data-stu-id="05935-166">You can also choose how data should be grouped.</span></span> <span data-ttu-id="05935-167">In diesem Fall werden die Registrierungen nach Stunde, Tag, Woche oder Monat zusammengefasst.</span><span class="sxs-lookup"><span data-stu-id="05935-167">In this case, registrations grouped by hour, day, week, or month.</span></span>

<span data-ttu-id="05935-168">In der folgenden Tabelle werden die Filter aufgelistet, die Sie im Bericht über Benutzerregistrierung verwenden können.</span><span class="sxs-lookup"><span data-stu-id="05935-168">The following table lists the filters that you can use with the User Registration Report.</span></span>

### <a name="user-registration-report-filters"></a><span data-ttu-id="05935-169">Filter im Bericht über Benutzerregistrierung</span><span class="sxs-lookup"><span data-stu-id="05935-169">User Registration Report Filters</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="05935-170">Name</span><span class="sxs-lookup"><span data-stu-id="05935-170">Name</span></span></th>
<th><span data-ttu-id="05935-171">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="05935-171">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="05935-172"><strong>From</strong></span><span class="sxs-lookup"><span data-stu-id="05935-172"><strong>From</strong></span></span></p></td>
<td><p><span data-ttu-id="05935-p113">Anfangsdatum und -uhrzeit für den Zeitraum. Wenn die Daten nach Stunden angezeigt werden sollen, geben Sie Anfangsdatum und -uhrzeit wie folgt ein:</span><span class="sxs-lookup"><span data-stu-id="05935-p113">Start date and time for the time range. To view data by hours, enter both the start date and time as follows:</span></span></p>
<p><span data-ttu-id="05935-175">07.07.2012 13:00</span><span class="sxs-lookup"><span data-stu-id="05935-175">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="05935-p114">Wenn Sie keinen Anfangszeitpunkt eingeben, beginnt der Bericht automatisch am angegebenen Tag um 12:00 Uhr. Zum Anzeigen der Daten nach Tag geben Sie nur das Datum ein:</span><span class="sxs-lookup"><span data-stu-id="05935-p114">If you do not enter a start time, the report automatically begins at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="05935-178">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="05935-178">7/7/2012</span></span></p>
<p><span data-ttu-id="05935-179">Sollen die Daten nach Woche oder Monat angezeigt werden, geben Sie irgendein Datum ein, das in die anzuzeigende Woche oder den anzuzeigenden Monat fällt (Sie müssen nicht den ersten Tag der Woche oder des Monats eingeben):</span><span class="sxs-lookup"><span data-stu-id="05935-179">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="05935-180">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="05935-180">7/3/2012</span></span></p>
<p><span data-ttu-id="05935-181">Eine Woche läuft immer von Sonntag bis einschließlich Samstag.</span><span class="sxs-lookup"><span data-stu-id="05935-181">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="05935-182"><strong>Ziel</strong></span><span class="sxs-lookup"><span data-stu-id="05935-182"><strong>To</strong></span></span></p></td>
<td><p><span data-ttu-id="05935-p115">Enddatum und -uhrzeit für den Zeitraum. Wenn die Daten nach Stunden angezeigt werden sollen, geben Sie Enddatum und -uhrzeit wie folgt ein:</span><span class="sxs-lookup"><span data-stu-id="05935-p115">End date and time for the time range. To view data by hours, enter both the end date and time as follows:</span></span></p>
<p><span data-ttu-id="05935-185">07.07.2012 13:00</span><span class="sxs-lookup"><span data-stu-id="05935-185">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="05935-p116">Wenn Sie keinen Endzeitpunkt eingeben, endet der Bericht automatisch am angegebenen Tag um 12:00 Uhr. Zum Anzeigen der Daten nach Tag geben Sie nur das Datum ein:</span><span class="sxs-lookup"><span data-stu-id="05935-p116">If you do not enter an end time, the report automatically ends at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="05935-188">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="05935-188">7/7/2012</span></span></p>
<p><span data-ttu-id="05935-189">Sollen die Daten nach Woche oder Monat angezeigt werden, geben Sie irgendein Datum ein, das in die anzuzeigende Woche oder den anzuzeigenden Monat fällt (Sie müssen nicht den ersten Tag der Woche oder des Monats eingeben):</span><span class="sxs-lookup"><span data-stu-id="05935-189">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="05935-190">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="05935-190">7/3/2012</span></span></p>
<p><span data-ttu-id="05935-191">Eine Woche läuft immer von Sonntag bis einschließlich Samstag.</span><span class="sxs-lookup"><span data-stu-id="05935-191">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="05935-192"><strong>Intervall</strong></span><span class="sxs-lookup"><span data-stu-id="05935-192"><strong>Interval</strong></span></span></p></td>
<td><p><span data-ttu-id="05935-p117">Zeitintervall. Wählen Sie eine der folgenden Optionen aus:</span><span class="sxs-lookup"><span data-stu-id="05935-p117">Time interval. Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="05935-195">Stündlich (maximal 25 Stunden können angezeigt werden)</span><span class="sxs-lookup"><span data-stu-id="05935-195">Hourly (a maximum of 25 hours can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="05935-196">Täglich (maximal 31 Tage können angezeigt werden)</span><span class="sxs-lookup"><span data-stu-id="05935-196">Daily (a maximum of 31 days can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="05935-197">Wöchentlich (maximal 12 Wochen können angezeigt werden)</span><span class="sxs-lookup"><span data-stu-id="05935-197">Weekly (a maximum of 12 weeks can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="05935-198">Monatlich (maximal 12 Monate können angezeigt werden)</span><span class="sxs-lookup"><span data-stu-id="05935-198">Monthly (a maximum of 12 months can be displayed)</span></span></p></li>
</ul>
<p><span data-ttu-id="05935-p118">Wenn mit dem angegebenen Start- und Endzeitpunkt die maximale Anzahl der zulässigen Werte für das ausgewählte Intervall überschritten wird, wird nur die maximale Anzahl an Werten (beginnend mit dem Startzeitpunkt) angezeigt. Beispiel: Wenn Sie das Intervall "Täglich" mit dem Startdatum 07.07.2012 und dem Enddatum 28.02.2012 ausgewählt haben, werden Daten für die Tage 07.08.2012 12:00 Uhr bis 07.09.2012 12:00 Uhr angezeigt (d. h. Daten für insgesamt 31 Tage).</span><span class="sxs-lookup"><span data-stu-id="05935-p118">If the start and end dates exceed the maximum number of values allowed for the selected interval, only the maximum number of values (starting from the start date) are displayed. For example, if you select the Daily interval with a start date of 7/7/2012 and an end date of 2/28/2012, data is displayed for the days 8/7/2012 12:00 AM to 9/7/2012 12:00 AM (that is, a total of 31 days' worth of data).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="05935-201"><strong>Pool</strong></span><span class="sxs-lookup"><span data-stu-id="05935-201"><strong>Pool</strong></span></span></p></td>
<td><p><span data-ttu-id="05935-202">Vollqualifizierter Domänenname (FQDN) des Registrierungsstellenpools oder Edgeservers.</span><span class="sxs-lookup"><span data-stu-id="05935-202">Fully qualified domain name (FQDN) of the Registrar pool or Edge Server.</span></span> <span data-ttu-id="05935-203">Sie können einen einzelnen Pool oder <strong>[Alle]</strong> auswählen, um die Daten für alle Pools anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="05935-203">You can either select an individual pool or choose <strong>[All]</strong> to view data for all the pools.</span></span> <span data-ttu-id="05935-204">Diese Dropdownliste wird basierend auf den Datensätzen in der Datenbank automatisch ausgefüllt.</span><span class="sxs-lookup"><span data-stu-id="05935-204">This drop-down list is automatically populated for you based on the records in the database.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics"></a><span data-ttu-id="05935-205">Metriken</span><span class="sxs-lookup"><span data-stu-id="05935-205">Metrics</span></span>

<span data-ttu-id="05935-206">In der folgenden Tabelle werden die Metriken aufgelistet, die im Bericht über Benutzerregistrierung enthalten sind.</span><span class="sxs-lookup"><span data-stu-id="05935-206">The following table lists the information provided in the User Registration Report.</span></span>

### <a name="user-registration-report-metrics"></a><span data-ttu-id="05935-207">Metriken im Bericht über Benutzerregistrierung</span><span class="sxs-lookup"><span data-stu-id="05935-207">User Registration Report Metrics</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="05935-208">Name</span><span class="sxs-lookup"><span data-stu-id="05935-208">Name</span></span></th>
<th><span data-ttu-id="05935-209">Kann nach dieser Metrik sortiert werden?</span><span class="sxs-lookup"><span data-stu-id="05935-209">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="05935-210">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="05935-210">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="05935-211"><strong>Stündlich</strong></span><span class="sxs-lookup"><span data-stu-id="05935-211"><strong>Hourly</strong></span></span></p>
<p><span data-ttu-id="05935-212"><strong>Täglich</strong></span><span class="sxs-lookup"><span data-stu-id="05935-212"><strong>Daily</strong></span></span></p>
<p><span data-ttu-id="05935-213"><strong>Wöchentlich</strong></span><span class="sxs-lookup"><span data-stu-id="05935-213"><strong>Weekly</strong></span></span></p>
<p><span data-ttu-id="05935-214"><strong>Monatlich</strong></span><span class="sxs-lookup"><span data-stu-id="05935-214"><strong>Monthly</strong></span></span></p></td>
<td><p><span data-ttu-id="05935-215">Nein</span><span class="sxs-lookup"><span data-stu-id="05935-215">No</span></span></p></td>
<td><p><span data-ttu-id="05935-p120">Gibt das auf der Filtersymbolleiste gewählte Zeitintervall an. Sie können gegebenenfalls auf ein bestimmtes Zeitintervall klicken, um ausführliche Informationen zu diesem Intervall anzuzeigen. Wenn Sie beispielsweise das tägliche Intervall verwenden und auf 07.07.2012 klicken, wird eine stündliche Übersicht der Benutzerregistrierungsaktivität für dieses Datum angezeigt.</span><span class="sxs-lookup"><span data-stu-id="05935-p120">Indicates the time interval that you selected on the filter toolbar. Where applicable, you can click a given time interval to view detailed information for that interval. For example, if you are using the Daily interval and you click 7/7/2012, you see an hourly breakdown of user registration activity for that date.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="05935-219"><strong>Anmeldungen insgesamt</strong></span><span class="sxs-lookup"><span data-stu-id="05935-219"><strong>Total logons</strong></span></span></p></td>
<td><p><span data-ttu-id="05935-220">Nein</span><span class="sxs-lookup"><span data-stu-id="05935-220">No</span></span></p></td>
<td><p><span data-ttu-id="05935-221">Die Gesamtzahl der erfolgreichen Anmeldesitzungen.</span><span class="sxs-lookup"><span data-stu-id="05935-221">Total number of successful logon sessions.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="05935-222"><strong>Interne Anmeldungen</strong></span><span class="sxs-lookup"><span data-stu-id="05935-222"><strong>Internal logons</strong></span></span></p></td>
<td><p><span data-ttu-id="05935-223">Nein</span><span class="sxs-lookup"><span data-stu-id="05935-223">No</span></span></p></td>
<td><p><span data-ttu-id="05935-224">Die Gesamtzahl der Anmeldungen im internen Netzwerk.</span><span class="sxs-lookup"><span data-stu-id="05935-224">Total number of logons within the internal network.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="05935-225"><strong>Externe Anmeldungen</strong></span><span class="sxs-lookup"><span data-stu-id="05935-225"><strong>External logons</strong></span></span></p></td>
<td><p><span data-ttu-id="05935-226">Nein</span><span class="sxs-lookup"><span data-stu-id="05935-226">No</span></span></p></td>
<td><p><span data-ttu-id="05935-227">Die Gesamtzahl der Anmeldungen von außerhalb des internen Netzwerks über den Edgeserver.</span><span class="sxs-lookup"><span data-stu-id="05935-227">Total number of logons from outside the internal network, using the Edge Server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="05935-228"><strong>Eindeutige angemeldete Benutzer</strong></span><span class="sxs-lookup"><span data-stu-id="05935-228"><strong>Unique logon users</strong></span></span></p></td>
<td><p><span data-ttu-id="05935-229">Nein</span><span class="sxs-lookup"><span data-stu-id="05935-229">No</span></span></p></td>
<td><p><span data-ttu-id="05935-p121">Die Gesamtzahl der Benutzer, die mindestens eine Anmeldesitzung hatten. Ein Benutzer, der mehrere Anmeldesitzungen ausgeführt hat, zählt als ein einziger Benutzer, genauso wie eine Person, die nur eine einzige Anmeldesitzung ausgeführt hat.</span><span class="sxs-lookup"><span data-stu-id="05935-p121">Total number of users who had at least one logon session. A user who had multiple logon sessions counts as one user, the same as a person who had just a single logon session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="05935-232"><strong>Eindeutige aktive Benutzer</strong></span><span class="sxs-lookup"><span data-stu-id="05935-232"><strong>Unique active users</strong></span></span></p></td>
<td><p><span data-ttu-id="05935-233">Nein</span><span class="sxs-lookup"><span data-stu-id="05935-233">No</span></span></p></td>
<td><p><span data-ttu-id="05935-p122">Die Gesamtzahl der Benutzer, die an einer Peer-zu-Peer- oder Konferenzsitzung teilgenommen haben. Ein Benutzer, der mehrere Sitzungen ausgeführt hat, zählt als ein einziger Benutzer, genauso wie eine Person, die nur eine einzige Sitzung ausgeführt hat.</span><span class="sxs-lookup"><span data-stu-id="05935-p122">Total number of users who were involved in a peer-to-peer or conferencing session. A user who had multiple sessions counts as one user, the same as a person who had just a single session.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

