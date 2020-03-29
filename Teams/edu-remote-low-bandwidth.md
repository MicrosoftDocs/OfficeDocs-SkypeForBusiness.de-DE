---
title: Microsoft Teams für Bildungseinrichtungen – Anleitung zur geringen Bandbreite
author: MicrosoftHeidi
ms.author: heidip
manager: serdars
ms.topic: reference
ms.service: msteams
audience: admin
ms.reviewer: jesegher
description: Microsoft Teams für Bildungseinrichtungen – Artikel zur Unterstützung von Besprechungs- und Videoproblemen in Verbindung mit geringer Bandbreite. Ganz gleich, ob Sie Eltern, Pädagoge oder ITAdmin sind, Sie haben die Möglichkeit, die Erfahrung mit Teams zu verbessern.
localization_priority: Priority
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
- Teams_ITAdmin_RemoteWorkers
- remotework
appliesto:
- Microsoft Teams
ms.openlocfilehash: 24f34ea2e65906c648081a019d6acf8a3f8a5cd5
ms.sourcegitcommit: e710bb8dbbd084912cbf509896515a674ab5e19f
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/28/2020
ms.locfileid: "43034075"
---
# <a name="help-for-low-bandwidth-situations-for-teams-for-edu"></a><span data-ttu-id="aab77-104">Hilfe zu Situationen mit geringer Bandbreite für Teams für das Bildungswesen</span><span class="sxs-lookup"><span data-stu-id="aab77-104">Help for low bandwidth situations for Teams for EDU</span></span>

<span data-ttu-id="aab77-105">Bei der Arbeit mit Microsoft-Teams gibt es viele Netzwerkelemente, die sich auf die Leistung auswirken können, und eine niedrige Bandbreite ist eine der Situationen, die sich völlig unkontrollierbar anfühlen kann.</span><span class="sxs-lookup"><span data-stu-id="aab77-105">There are a lot of network elements when it comes to working with Microsoft Teams that can affect performance, and low bandwidth is one of the situations that can feel entirely out of your control.</span></span> <span data-ttu-id="aab77-106">Berücksichtigen Sie dabei Folgendes:</span><span class="sxs-lookup"><span data-stu-id="aab77-106">Consider the following:</span></span>

- <span data-ttu-id="aab77-107">Eine langsame Internetverbindung für die Schule.</span><span class="sxs-lookup"><span data-stu-id="aab77-107">A low-speed internet connection for the school.</span></span>
- <span data-ttu-id="aab77-108">Eine langsame Internetverbindung für die einen oder mehrere Schüler.</span><span class="sxs-lookup"><span data-stu-id="aab77-108">A low-speed internet connection for one or more students.</span></span>
- <span data-ttu-id="aab77-109">Zeiten des Tages, in denen die Bandbreite aufgrund einer Netzwerknutzung in einem bestimmten Gebiet gering ist.</span><span class="sxs-lookup"><span data-stu-id="aab77-109">Times of the day when there is low bandwidth due to network usage in an area.</span></span>
- <span data-ttu-id="aab77-110">Zeiten mit geringer Bandbreite aufgrund von Ausfällen, die weder in der Schule noch bei Schülern vor Ort sind, die aber dennoch die Leistung beeinträchtigen.</span><span class="sxs-lookup"><span data-stu-id="aab77-110">Low bandwidth periods due to outages local to neither the school nor to students, but which impact performance nonetheless.</span></span>
- <span data-ttu-id="aab77-111">Probleme, die nicht mit der Bandbreite zusammenhängen (z. B. Probleme mit der Hardware), die mit Problemen mit niedriger Bandbreite verwechselt werden können.</span><span class="sxs-lookup"><span data-stu-id="aab77-111">Non-bandwidth issues (for example, issues with hardware) that masquerade as low bandwidth issues.</span></span>

<span data-ttu-id="aab77-112">In diesem Artikel finden Sie bewährte Methoden für eine Vielzahl von Teams-Aktivitäten, wenn Sie mit einem Problem mit geringer Bandbreite konfrontiert sind.</span><span class="sxs-lookup"><span data-stu-id="aab77-112">This article will give you best practices to follow for a variety of Teams activities when you're faced with a low-bandwidth issue.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="aab77-113">Hier finden Sie Informationen über die [Verwendung des Arbeitsspeichers durch Microsoft Teams](teams-memory-usage-perf.md)verwendet, da es zusätzlich zu Problemen mit geringer Bandbreite möglicherweise zu Problemen mit den Ressourcen auf Ihrem Gerät kommt.</span><span class="sxs-lookup"><span data-stu-id="aab77-113">There's information here on [How Microsoft Teams uses memory](teams-memory-usage-perf.md), because in addition to low bandwidth problems, you may be having resource issues on your device.</span></span> <span data-ttu-id="aab77-114">Wenn Sie Hinweise zum Thema Netzwerk in Verbindung mit Microsoft Teams bräuchten, schauen Sie sich [Vorbereiten des Netzwerks Ihrer Organisation für Microsoft Teams](prepare-network.md) an.</span><span class="sxs-lookup"><span data-stu-id="aab77-114">If you're looking for network guidance for Microsoft Teams, review [Prepare your organization's network for Microsoft Teams](prepare-network.md).</span></span>

## <a name="resolving-low-bandwidth-issues-for-itadmins"></a><span data-ttu-id="aab77-115">Beheben von Problemen mit geringer Bandbreite für ITAdmins</span><span class="sxs-lookup"><span data-stu-id="aab77-115">Resolving low bandwidth issues for ITAdmins</span></span>

<span data-ttu-id="aab77-116">Wichtig ist, dass Sie sich als ITAdmin daran erinnern, dass Sie Lösungen für Probleme mit geringer Bandbreite, die weit verbreitet sind und sich schnell lösen lassen, auch sorgfältig prüfen sollten, da einige Probleme möglicherweise mit einem engeren Fokus auf den Lehrer oder sogar auf die Ebene von Schülern/Eltern behoben werden können.</span><span class="sxs-lookup"><span data-stu-id="aab77-116">The important thing to remember, as an ITAdmin, is that while you have solutions for low bandwidth issues that are wide-spread that will resolve problems quickly, this should be considered carefully, as some issues may be able to resolved with a more narrow focus taken at the educator or even the student/parent level.</span></span>

<span data-ttu-id="aab77-117">Kurz gesagt: Wenn das Problem mit geringer Bandbreite für eine große Gruppe von Schülern auftritt, ist das Handeln als ITAdmin sinnvoll und es ist auch sinnvoll, wenn die auf der Ebene "Schüler/Lehrer" getroffenen Aktionen nicht hilfreich waren.</span><span class="sxs-lookup"><span data-stu-id="aab77-117">In short, if the low bandwidth issue occurs for a wide group of students, taking action as an ITAdmin makes sense, and it also makes sense if the actions taken at the student/educator level haven't been helpful.</span></span>

> [!NOTE]
> <span data-ttu-id="aab77-118">Wenn Sie ausreichen Zeit haben, ist der [Leitfaden zur Überprüfung der Erlebnisqualität](quality-of-experience-review-guide.md) eine lohnende Lektüre (er ist nicht konkret auf die Version für Bildungseinrichtungen abgestimmt, aber er bietet trotzdem wertvolle Informationen).</span><span class="sxs-lookup"><span data-stu-id="aab77-118">If you've got the time to invest, the [Quality of Experience Review Guide](quality-of-experience-review-guide.md) is a worthwhile read (this is not EDU-specific, but it will still have valuable information).</span></span> <span data-ttu-id="aab77-119">So können erfahrene ITAdmins die Erfahrung für ihre Lehrer und Schüler gründlicher studieren.</span><span class="sxs-lookup"><span data-stu-id="aab77-119">This will allow experienced ITAdmins to go in-depth on the experience for their educators and students.</span></span>

### <a name="meetings-and-video"></a><span data-ttu-id="aab77-120">Besprechungen und Video</span><span class="sxs-lookup"><span data-stu-id="aab77-120">Meetings and video</span></span>

<span data-ttu-id="aab77-121">Ein primärer Schwerpunkt bei Problemen mit geringer Bandbreite sind Besprechungen und speziell Video in Besprechungen.</span><span class="sxs-lookup"><span data-stu-id="aab77-121">A primary focus for low bandwidth issues are meetings, and specifically video in meetings.</span></span> <span data-ttu-id="aab77-122">Im Folgenden sind einige der Maßnahmen aufgeführt, die ein ITAdmin in Betracht ziehen sollte, wenn er sich mit Problemen befasst, die von Studenten oder Pädagogen gemeldet werden, um die beste Erfahrung mit Treffen in einem Bildungsumfeld zu erzielen.</span><span class="sxs-lookup"><span data-stu-id="aab77-122">We have some of the actions below that an ITAdmin should consider when dealing with issues reported by students or educators in regard to having the best meeting experience in an educational setting.</span></span>

#### <a name="meeting-policies"></a><span data-ttu-id="aab77-123">Besprechungsrichtlinien</span><span class="sxs-lookup"><span data-stu-id="aab77-123">Meeting policies</span></span>

<span data-ttu-id="aab77-124">Im Hinblick auf Besprechungen ist einer der am meisten betroffenen Bereiche bei niedrigen Bandbreiten mit Videos verbunden.</span><span class="sxs-lookup"><span data-stu-id="aab77-124">In regards to meetings, one of the most concerning areas for low bandwidth situations has to do with videos.</span></span> <span data-ttu-id="aab77-125">Glücklicherweise kann Teams nicht nur automatisch auf die erkannte Bandbreite skalieren, sondern Sie als ITAdmin haben auch Richtlinienoptionen, die Sie auf der Ebene der einzelnen Organisatoren und/oder Benutzer einstellen können, um für alle Beteiligten die beste Erfahrung im Hinblick auf die Bandbreite, mit der sie zu einem bestimmten Zeitpunkt arbeiten müssen, zu gewährleisten.</span><span class="sxs-lookup"><span data-stu-id="aab77-125">Fortunately, in addition to Teams being able to scale to detected bandwidth automatically, you as an ITAdmin have policy options you can set at the per-organizer and/or per-user level to give everyone the best experience in light of the bandwidth they have to work with at a given time.</span></span>

<span data-ttu-id="aab77-126">Einige der Einstellungen, die Sie über die Richtlinie vornehmen können, sind:</span><span class="sxs-lookup"><span data-stu-id="aab77-126">Some of the things you can set via policy include:</span></span>

- <span data-ttu-id="aab77-127">Video wird vollständig deaktiviert, sodass es niemand aktivieren kann.</span><span class="sxs-lookup"><span data-stu-id="aab77-127">Disabling video altogether, so no one could enable it.</span></span>
- <span data-ttu-id="aab77-128">Media-Bitrate (diese wird pro Benutzer festgelegt).</span><span class="sxs-lookup"><span data-stu-id="aab77-128">Media bit rate (this is set per-user).</span></span>

<span data-ttu-id="aab77-129">Wenn Sie mehr über Ihre Optionen erfahren und die Einzelheiten der Richtlinien, die Sie für Besprechungen und Videos festlegen müssten, durchlaufen möchten, schauen Sie sich [Einstellungen zu Besprechungsrichtlinien in Teams: Audio und Video](https://docs.microsoft.com/microsoftteams/meeting-policies-in-teams#meeting-policy-settings---audio--video) an, um detaillierte Informationen zum Verfahren zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="aab77-129">To learn more about your options, and to walk through the specifics of what policies you'd need to set for meetings and video, check out [Meeting policy settings in Teams: Audio and video](https://docs.microsoft.com/microsoftteams/meeting-policies-in-teams#meeting-policy-settings---audio--video) for detailed walk-through information.</span></span>

#### <a name="screen-sharing-policies"></a><span data-ttu-id="aab77-130">Bildschirmfreigaberichtlinien</span><span class="sxs-lookup"><span data-stu-id="aab77-130">Screen sharing policies</span></span>

<span data-ttu-id="aab77-131">In anderen Fällen kann es vorkommen, dass Pädagogen ihren gesamten Bildschirm für die Schüler freigeben, wobei die Freigabe auf eine Anwendung beschränkt sein sollte, die für die zu unterrichtende Lektion relevant ist.</span><span class="sxs-lookup"><span data-stu-id="aab77-131">In other cases, educators may be sharing their entire screen to students, when sharing should be limited to an application relevant to the lesson being taught.</span></span> <span data-ttu-id="aab77-132">Dies kann auch über eine Richtlinie festgelegt werden, wenn dies wünschenswerter ist, als wenn die Pädagogen diese Entscheidung individuell treffen müssen.</span><span class="sxs-lookup"><span data-stu-id="aab77-132">This can also be set via policy, if that's a more desirable way to do it than to have educators making that choice individually.</span></span>

<span data-ttu-id="aab77-133">Einen guten Überblick darauf, was Sie tun können, um die Bildschirmfreigabe über Richtlinieneinstellungen zu begrenzen, gewinnen Sie unter [Einstellungen für Besprechungsrichtlinien in Teams: Bildschirmfreigabe](https://docs.microsoft.com/microsoftteams/meeting-policies-in-teams#meeting-policy-settings---audio--video).</span><span class="sxs-lookup"><span data-stu-id="aab77-133">For a good idea of what you can do about limiting screen sharing via policy settings, check out [Meeting policy settings in Teams: Screen sharing](https://docs.microsoft.com/microsoftteams/meeting-policies-in-teams#meeting-policy-settings---audio--video).</span></span>

#### <a name="dial-in-number-for-meetings"></a><span data-ttu-id="aab77-134">Einwahlnummer für Besprechungen</span><span class="sxs-lookup"><span data-stu-id="aab77-134">Dial-in number for meetings</span></span>

<span data-ttu-id="aab77-135">Es kann für einige Schüler einfacher sein, zu versuchen, sich in einige Unterrichtssitzungen einzuwählen.</span><span class="sxs-lookup"><span data-stu-id="aab77-135">It may be easier for some students to attempt to dial in to some classroom sessions.</span></span> <span data-ttu-id="aab77-136">Sie können eine Einwahlnummer für Teams-Besprechungen angeben, so dass Studenten mit Problemen als Alternative zur Teilnahme an einer Videobesprechung anrufen können.</span><span class="sxs-lookup"><span data-stu-id="aab77-136">You can provide a dial-in number for Teams meetings, so students with issues can phone in as an alternative to attending a video meeting.</span></span>

<span data-ttu-id="aab77-137">Weitere Informationen hierzu finden Sie unter [Festlegen der in Einladungen in Microsoft Teams enthaltenen Telefonnummern](set-the-phone-numbers-included-on-invites-in-teams.md).</span><span class="sxs-lookup"><span data-stu-id="aab77-137">For more information on this, you can read [Set the phone numbers included on invites in Microsoft Teams](set-the-phone-numbers-included-on-invites-in-teams.md).</span></span>

## <a name="low-bandwidth-scenarios-as-an-educator"></a><span data-ttu-id="aab77-138">Szenarien mit geringer Bandbreite als Pädagoge</span><span class="sxs-lookup"><span data-stu-id="aab77-138">Low bandwidth scenarios as an educator</span></span>

<span data-ttu-id="aab77-139">Pädagogen sollten sich befähigt fühlen, Maßnahmen zur Lösung von Problemen mit geringer Bandbreite zu ergreifen, und dies kann in den folgenden Situationen eine bessere Wahl als die Maßnahmen der ITAdmin sein:</span><span class="sxs-lookup"><span data-stu-id="aab77-139">Educators should feel empowered to take steps to resolve low bandwidth issues, and may be a superior choice to ITAdmin action in the following situations:</span></span>

- <span data-ttu-id="aab77-140">Wenn das Problem zeitweilig oder relativ vorübergehend ist.</span><span class="sxs-lookup"><span data-stu-id="aab77-140">If the problem is intermittent, or relatively transitory.</span></span>
- <span data-ttu-id="aab77-141">Wenn es eine bestimmte Tageszeit gibt, in der man mit einem Problem rechnen kann, oder wenn der Zeitraum mit geringer Bandbreite eine gewisse Vorhersehbarkeit hat.</span><span class="sxs-lookup"><span data-stu-id="aab77-141">If there is a specific time of the day you can anticipate there being an issue, or the low bandwidth period has some predictability to it.</span></span>

<span data-ttu-id="aab77-142">In diesen Fällen können Sie einige Aktionen ausführen.</span><span class="sxs-lookup"><span data-stu-id="aab77-142">In these situations, you can take some actions.</span></span>

<span data-ttu-id="aab77-143">Weitere Informationen finden Sie unter [Teams für Schularbeiten verwenden, wenn die Bandbreite gering ist](https://support.office.com/article/use-teams-for-schoolwork-when-bandwidth-is-low-5c5675f7-1b55-471a-9daa-ec1e6df38262).</span><span class="sxs-lookup"><span data-stu-id="aab77-143">For more information, check out [Use Teams for schoolwork when bandwidth is low](https://support.office.com/article/use-teams-for-schoolwork-when-bandwidth-is-low-5c5675f7-1b55-471a-9daa-ec1e6df38262).</span></span>

## <a name="low-bandwidth-scenarios-as-a-parent-or-student"></a><span data-ttu-id="aab77-144">Szenarien mit geringer Bandbreite für Eltern und Schüler</span><span class="sxs-lookup"><span data-stu-id="aab77-144">Low bandwidth scenarios as a parent or student</span></span>

<span data-ttu-id="aab77-145">Es gibt auch Situationen, und Sie sollten diese proaktiv mit Ihren Lehrkräften besprechen, in denen das Bandbreitenproblem auf der Seite der Schüler liegen kann (z. B. kann eine große Anzahl von Schülern die Video-Lektionen ohne Probleme ansehen, aber eine kleine Anzahl von Schülern hat Schwierigkeiten).</span><span class="sxs-lookup"><span data-stu-id="aab77-145">There are also situations, and you should proactively discuss them with your educators, where the bandwidth problem may be on the student's side (for example, a large number of students are able to watch the video lessons without issue, but a small number of students have difficulties).</span></span>

<span data-ttu-id="aab77-146">Es ist nicht zumutbar, von vielen Eltern zu erwarten, dass sie in der Lage sind, diese Probleme zu beheben, und Probleme mit niedriger Bandbreite können außerhalb der Kontrolle eines Schülers oder Elternteils liegen (ihr Zuhause hat vielleicht keinen Zugang zu hoher Bandbreite, sie haben möglicherweise viele Menschen in ihrer unmittelbaren Umgebung, die die Bandbreite verbrauchen und beeinflussen, was sie tun können, es kann eine Instabilität des Internets vorliegen usw.).</span><span class="sxs-lookup"><span data-stu-id="aab77-146">It's not reasonable to expect many parents to be able to troubleshoot these issues, and low bandwidth issues may be out of a student or parent's control (their home may not have access to high bandwidth, they may have a lot of people in their immediate area consuming bandwidth and affecting what they can do, there may be internet instability, and so on).</span></span>

<span data-ttu-id="aab77-147">Wir haben in unserem Artikel [Teams für die Schularbeiten bei geringer Bandbreite nutzen](https://support.office.com/article/use-teams-for-schoolwork-when-bandwidth-is-low-5c5675f7-1b55-471a-9daa-ec1e6df38262) für Eltern und Schüler einige Hinweise zur Verfügung gestellt. Sie können diese Empfehlungen durchgehen und ausprobieren, wenn Sie Probleme haben.</span><span class="sxs-lookup"><span data-stu-id="aab77-147">We've put together guidance in our [Use Teams for schoolwork when bandwidth is low](https://support.office.com/article/use-teams-for-schoolwork-when-bandwidth-is-low-5c5675f7-1b55-471a-9daa-ec1e6df38262) article for parents and students as well, you can review and try these recommendations if you're having any problems.</span></span>
