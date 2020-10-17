---
title: 'Lync Server 2013: Überlegungen zur Migration für Besprechungen'
description: 'Lync Server 2013: Migrationsüberlegungen für Besprechungen.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Migration considerations for meetings
ms:assetid: a9807d58-99a3-4cff-b4c6-74950d106a2b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412800(v=OCS.15)
ms:contentKeyID: 61097556
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e238405acf7bc2a96fd2efd4cca761c1f1f258fd
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48560941"
---
# <a name="migration-considerations-for-meetings-in-lync-server-2013"></a><span data-ttu-id="07ec9-103">Migrationsüberlegungen für Besprechungen in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="07ec9-103">Migration considerations for meetings in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="07ec9-104">_**Letztes Änderungsstand des Themas:** 2014-02-10_</span><span class="sxs-lookup"><span data-stu-id="07ec9-104">_**Topic Last Modified:** 2014-02-10_</span></span>

<span data-ttu-id="07ec9-105">In diesem Abschnitt werden die folgenden Themen erläutert:</span><span class="sxs-lookup"><span data-stu-id="07ec9-105">The following topics are discussed in this section:</span></span>

  - <span data-ttu-id="07ec9-106">Änderungen an Besprechungen in Microsoft lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="07ec9-106">Changes to meetings in Microsoft Lync Server 2013</span></span>

  - <span data-ttu-id="07ec9-107">Migrieren von Benutzern basierend auf ihren Konferenzanforderungen</span><span class="sxs-lookup"><span data-stu-id="07ec9-107">Migrating users based on their conferencing needs</span></span>

  - <span data-ttu-id="07ec9-108">Migrieren von vorhandenen Besprechungen und Besprechungsinhalten</span><span class="sxs-lookup"><span data-stu-id="07ec9-108">Migrating existing meetings and meeting content</span></span>

  - <span data-ttu-id="07ec9-109">Benutzererfahrung während lync Server 2010 Migration</span><span class="sxs-lookup"><span data-stu-id="07ec9-109">User experience during Lync Server 2010 migration</span></span>

  - <span data-ttu-id="07ec9-110">Benutzererfahrung während Office Communications Server 2007 R2 Migration</span><span class="sxs-lookup"><span data-stu-id="07ec9-110">User Experience during Office Communications Server 2007 R2 migration</span></span>

  - <span data-ttu-id="07ec9-111">Microsoft lync 2013 Kompatibilität mit Besprechungen in früheren Server Versionen</span><span class="sxs-lookup"><span data-stu-id="07ec9-111">Microsoft Lync 2013 compatibility with meetings on earlier server versions</span></span>

<div>

## <a name="changes-to-meetings-in-lync-server-2013"></a><span data-ttu-id="07ec9-112">Änderungen an Besprechungen in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="07ec9-112">Changes to Meetings in Lync Server 2013</span></span>

<span data-ttu-id="07ec9-113">**Lync Server 2013 Funktionen.**     Lync Server 2013 stellt neue Konferenzfeatures bereit, die Benutzern zur Verfügung stehen, nachdem Ihre Konten in lync Server 2013 verschoben wurden und sich mit dem lync 2013-Client anmelden.</span><span class="sxs-lookup"><span data-stu-id="07ec9-113">**Lync Server 2013 features.**   Lync Server 2013 provides new conferencing features that become available to users after their accounts are moved to Lync Server 2013 and they sign in with the Lync 2013 client.</span></span> <span data-ttu-id="07ec9-114">Neue Features werden in [neuen Konferenzfeatures in lync Server 2013](lync-server-2013-new-conferencing-features.md) und Neuerungen [für Clients in lync Server 2013](lync-server-2013-what-s-new-for-clients.md)erläutert.</span><span class="sxs-lookup"><span data-stu-id="07ec9-114">New features are outlined in [New conferencing features in Lync Server 2013](lync-server-2013-new-conferencing-features.md) and [What's new for clients in Lync Server 2013](lync-server-2013-what-s-new-for-clients.md).</span></span>

<span data-ttu-id="07ec9-115">**Besprechungs-URL.**     Wie in lync Server 2010 verfügen alle neu geplanten Besprechungen in lync Server 2013 über ein URL-Präfix für https://, und vorhandene Besprechungen werden zusammen mit Benutzerkonten migriert.</span><span class="sxs-lookup"><span data-stu-id="07ec9-115">**Meeting URL.**   As in Lync Server 2010, all newly scheduled meetings in Lync Server 2013 have a URL prefix of https:// and existing meetings migrate along with user accounts.</span></span> <span data-ttu-id="07ec9-116">Lync Server 2013 unterstützt jedoch nicht die Office Communications Server 2007 R2-Telefonkonferenz (conf://-URL-Präfix) oder Webkonferenz (Meet://-URL-Präfix).</span><span class="sxs-lookup"><span data-stu-id="07ec9-116">However, Lync Server 2013 does not support the Office Communications Server 2007 R2 conference call (conf:// URL prefix) or web conference (meet:// URL prefix).</span></span> <span data-ttu-id="07ec9-117">Weitere Informationen finden Sie unter "Migrieren von Besprechungen aus Office Communications Server 2007 R2" weiter unten in diesem Thema.</span><span class="sxs-lookup"><span data-stu-id="07ec9-117">See “Migrating Meetings from Office Communications Server 2007 R2” later in this topic for more information.</span></span>

<span data-ttu-id="07ec9-118">**Client Unterstützung.**     Im Gegensatz zu lync Server 2010 unterstützt lync Server 2013 keine Office Communicator-Clients für Konferenzen.</span><span class="sxs-lookup"><span data-stu-id="07ec9-118">**Client support.**   Unlike Lync Server 2010, Lync Server 2013 does not support Office Communicator clients for conferencing.</span></span> <span data-ttu-id="07ec9-119">Sie können die folgenden Clients nicht verwenden, um an Besprechungen teilzunehmen, die über das Online-Besprechungs-Add-in für lync 2013 geplant wurden:</span><span class="sxs-lookup"><span data-stu-id="07ec9-119">You cannot use the following clients to join meetings scheduled through the Online Meeting Add-in for Lync 2013:</span></span>

  - <span data-ttu-id="07ec9-120">Office Communicator 2007 R2</span><span class="sxs-lookup"><span data-stu-id="07ec9-120">Office Communicator 2007 R2</span></span>

  - <span data-ttu-id="07ec9-121">Microsoft Office Communications Server 2007 R2 Attendant</span><span class="sxs-lookup"><span data-stu-id="07ec9-121">Microsoft Office Communications Server 2007 R2 Attendant</span></span>

  - <span data-ttu-id="07ec9-122">Office Communicator 2007</span><span class="sxs-lookup"><span data-stu-id="07ec9-122">Office Communicator 2007</span></span>

  - <span data-ttu-id="07ec9-123">Office Live Meeting 2007</span><span class="sxs-lookup"><span data-stu-id="07ec9-123">Office Live Meeting 2007</span></span>

<span data-ttu-id="07ec9-124">Während der Migration sollten Office Communicator 2007 R2 Benutzer lync Web App 2013 verwenden, um lync Server 2013 Besprechungen teilzunehmen, bis Ihre Clients aktualisiert wurden.</span><span class="sxs-lookup"><span data-stu-id="07ec9-124">During migration, Office Communicator 2007 R2 users should use Lync Web App 2013 to join Lync Server 2013 meetings until their clients are upgraded.</span></span> <span data-ttu-id="07ec9-125">Beachten Sie, dass Office Communicator 2007 R2 Benutzer weiterhin ihren vorhandenen Client für die lync Server 2013 für Anwesenheits-und Chatfunktionen verwenden können, aber Konferenzfeatures werden nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="07ec9-125">Note that Office Communicator 2007 R2 users can continue to use their existing client against Lync Server 2013 for presence and IM features, but conferencing features are not supported.</span></span>

<div>


</div>

</div>

<div>

## <a name="migrating-users-based-on-their-conferencing-needs"></a><span data-ttu-id="07ec9-126">Migrieren von Benutzern basierend auf ihren Konferenzanforderungen</span><span class="sxs-lookup"><span data-stu-id="07ec9-126">Migrating Users Based on Their Conferencing Needs</span></span>

<span data-ttu-id="07ec9-127">**Häufige Besprechungsorganisatoren.**     Ziehen Sie es vor, häufige Besprechungsorganisatoren frühzeitig zu migrieren, damit Sie die neuen lync Server 2013 und lync 2013 Features nutzen können, die in [neuen Konferenzfeatures in lync Server 2013](lync-server-2013-new-conferencing-features.md) und Neuerungen [für Clients in lync Server 2013](lync-server-2013-what-s-new-for-clients.md)erläutert werden.</span><span class="sxs-lookup"><span data-stu-id="07ec9-127">**Frequent meeting organizers.**   Consider migrating frequent meeting organizers early in the process so that they can take advantage of the new Lync Server 2013 and Lync 2013 features outlined in [New conferencing features in Lync Server 2013](lync-server-2013-new-conferencing-features.md) and [What's new for clients in Lync Server 2013](lync-server-2013-what-s-new-for-clients.md).</span></span>

<span data-ttu-id="07ec9-128">**Live Meeting Benutzer.**     Wenn Sie von Office Communications Server 2007 R2 migrieren und über Benutzer verfügen, die spezielle Webkonferenz Features für Live Meeting benötigen – insbesondere Unterstützung für große Besprechungen und Break-out-Räume – haben Sie die folgenden Optionen:</span><span class="sxs-lookup"><span data-stu-id="07ec9-128">**Live Meeting users.**   If you are migrating from Office Communications Server 2007 R2 and you have users who need web conferencing features specific to Live Meeting—particularly support for large meetings and break-out rooms—you have the following options:</span></span>

  - <span data-ttu-id="07ec9-129">Empfehlen Sie Organisatoren die Verwendung des Live Meeting-Diensts (falls in Ihrer Organisation vorhanden).</span><span class="sxs-lookup"><span data-stu-id="07ec9-129">Advise organizers to use the Live Meeting service, if available in your organization.</span></span>

  - <span data-ttu-id="07ec9-130">Lassen Sie die Organisatoren in der früheren Version von Office Communications Server verwaltet, damit Sie weiterhin Server basierte Live Meeting-Webkonferenzen planen können.</span><span class="sxs-lookup"><span data-stu-id="07ec9-130">Leave the organizers homed on the earlier version of Office Communications Server, so they can continue to schedule server-based Live Meeting web conferences.</span></span>

</div>

<div>

## <a name="migrating-existing-meetings-and-meeting-content"></a><span data-ttu-id="07ec9-131">Migrieren von vorhandenen Besprechungen und Besprechungsinhalten</span><span class="sxs-lookup"><span data-stu-id="07ec9-131">Migrating Existing Meetings and Meeting Content</span></span>

<div>

## <a name="migrating-meetings-from-lync-server-2010"></a><span data-ttu-id="07ec9-132">Migrieren von Besprechungen aus lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="07ec9-132">Migrating Meetings from Lync Server 2010</span></span>

<span data-ttu-id="07ec9-133">Wenn Sie einen Benutzer aus lync Server 2010 in lync Server 2013 verschieben, werden die folgenden Informationen mit dem Konto des Benutzers verschoben:</span><span class="sxs-lookup"><span data-stu-id="07ec9-133">When you move a user from Lync Server 2010 to Lync Server 2013, the following information moves with the user’s account:</span></span>

  - <span data-ttu-id="07ec9-134">Vom Benutzer bereits geplante Besprechungen.</span><span class="sxs-lookup"><span data-stu-id="07ec9-134">Meetings already scheduled by the user.</span></span> <span data-ttu-id="07ec9-135">Dies umfasst Konferenzverzeichnisse und Konferenzdaten.</span><span class="sxs-lookup"><span data-stu-id="07ec9-135">This includes conferencing directories and conferencing data.</span></span>

  - <span data-ttu-id="07ec9-136">Die persönliche Identifikationsnummer (PIN) des Benutzers.</span><span class="sxs-lookup"><span data-stu-id="07ec9-136">The user’s personal identification number (PIN).</span></span> <span data-ttu-id="07ec9-137">Die aktuelle PIN des Benutzers ist weiterhin solange gültig, bis sie abläuft oder der Benutzer eine neue PIN anfordert.</span><span class="sxs-lookup"><span data-stu-id="07ec9-137">The user’s current PIN continues to work until it expires or the user requests a new PIN.</span></span>

<span data-ttu-id="07ec9-138">Die folgenden Benutzerkontoinformationen werden jedoch nicht auf den neuen Server umsteigen:</span><span class="sxs-lookup"><span data-stu-id="07ec9-138">However, the following user account information does not move to the new server:</span></span>

  - <span data-ttu-id="07ec9-139">Besprechungsinhalte, beispielsweise PowerPoint-Präsentationen, Whiteboard-Inhalte und Umfragedaten</span><span class="sxs-lookup"><span data-stu-id="07ec9-139">Meeting content, for example PowerPoint presentations, whiteboard content, and poll data</span></span>

<span data-ttu-id="07ec9-140">Verwenden Sie den MoveMeetingContent-Parameter des Move-CsUser-Cmdlets, um den Inhalt zu verlagern, der in Besprechungen freigegeben wurde.</span><span class="sxs-lookup"><span data-stu-id="07ec9-140">To move the content that has been shared in meetings, use the MoveMeetingContent parameter of the Move-CsUser cmdlet.</span></span> <span data-ttu-id="07ec9-141">Ausführliche Informationen zur Verwendung dieses Cmdlets finden Sie unter CsUser in der Dokumentation zu lync Server 2013 [-](https://docs.microsoft.com/powershell/module/skype/Move-CsUser) Cmdlets.</span><span class="sxs-lookup"><span data-stu-id="07ec9-141">For details about using this cmdlet, see [Move-CsUser](https://docs.microsoft.com/powershell/module/skype/Move-CsUser) in the Lync Server 2013 cmdlets documentation.</span></span>

</div>

<div>

## <a name="migrating-meetings-from-office-communications-server-2007-r2"></a><span data-ttu-id="07ec9-142">Migrieren von Besprechungen aus Office Communications Server 2007 R2</span><span class="sxs-lookup"><span data-stu-id="07ec9-142">Migrating Meetings from Office Communications Server 2007 R2</span></span>

<span data-ttu-id="07ec9-143">Office Communications Server 2007 R2 Besprechungen sind entweder Konferenzanrufe (conf://-URL-Präfix) oder Webkonferenzen (Meet://-URL-Präfix).</span><span class="sxs-lookup"><span data-stu-id="07ec9-143">Office Communications Server 2007 R2 meetings are either conference calls (conf:// URL prefix) or web conferences (meet:// URL prefix).</span></span> <span data-ttu-id="07ec9-144">Diese früheren conf://-und Meet://-Konferenzen werden von lync Server 2013 nicht unterstützt, und Sie werden nicht zusammen mit dem Benutzerkonto migriert.</span><span class="sxs-lookup"><span data-stu-id="07ec9-144">Lync Server 2013 does not support these earlier conf:// and meet:// conferences, and they are not migrated along with the user account.</span></span> <span data-ttu-id="07ec9-145">Nach der Migration sollten Sie die Benutzer anweisen, die Links für alle geplanten Onlinebesprechungen zu aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="07ec9-145">After migration, you should instruct users to update the links for any online meetings they have scheduled.</span></span> <span data-ttu-id="07ec9-146">Dies können Sie nach der Installation des lync 2013 Clients durchführen, indem Sie eine geplante Besprechungseinladung öffnen, die die Besprechungs-URL aktualisiert und die Einladung erneut an die Teilnehmer sendet.</span><span class="sxs-lookup"><span data-stu-id="07ec9-146">They can do this after installing the Lync 2013 client by opening a scheduled meeting invitation—which updates the meeting URL—and resending the invitation to participants.</span></span>

</div>

</div>

<div>

## <a name="user-experience-during-lync-server-2010-migration"></a><span data-ttu-id="07ec9-147">Benutzererfahrung während lync Server 2010 Migration</span><span class="sxs-lookup"><span data-stu-id="07ec9-147">User Experience during Lync Server 2010 Migration</span></span>

<span data-ttu-id="07ec9-148">Dieser Abschnitt enthält eine Zusammenfassung der Benutzer Konferenz Erfahrung bei der Migration von lync 2010.</span><span class="sxs-lookup"><span data-stu-id="07ec9-148">This section provides a summary of users’ conferencing experience when migrating from Lync 2010.</span></span> <span data-ttu-id="07ec9-149">Weitere Informationen zur Koexistenz von lync Server 2013-Clients und zur Interaktion mit vorherigen Client-und Server Versionen finden Sie unter [Client Interoperabilität in lync 2013](lync-server-2013-client-interoperability-in-lync-2013.md).</span><span class="sxs-lookup"><span data-stu-id="07ec9-149">For more details about how Lync Server 2013 clients can coexist and interact with previous client and server versions, see [Client interoperability in Lync 2013](lync-server-2013-client-interoperability-in-lync-2013.md).</span></span>

<div>

## <a name="joining-lync-server-2010-meetings-with-a-lync-2013-client"></a><span data-ttu-id="07ec9-150">Beitreten lync Server 2010 Besprechungen mit einem lync 2013-Client</span><span class="sxs-lookup"><span data-stu-id="07ec9-150">Joining Lync Server 2010 Meetings with a Lync 2013 Client</span></span>

<span data-ttu-id="07ec9-151">Während der Migration von lync Server 2010 kann es eine gewisse Koexistenz geben, wenn Benutzer lync Server 2010 Besprechungen mit einem lync 2013-Client beitreten.</span><span class="sxs-lookup"><span data-stu-id="07ec9-151">During migration from Lync Server 2010, there may be a period of coexistence when users join Lync Server 2010 meetings with a Lync 2013 client.</span></span> <span data-ttu-id="07ec9-152">Diese Benutzer haben Zugriff auf lync 2013 Clientfeatures mit den folgenden Ausnahmen:</span><span class="sxs-lookup"><span data-stu-id="07ec9-152">These users have access to Lync 2013 client features with the following exceptions:</span></span>

  - <span data-ttu-id="07ec9-153">In den Verwaltungsoptionen für **Teilnehmer** , auf die durch den Hinweis auf das Symbol Personen im Besprechungsfenster zugegriffen werden kann, funktioniert die Option **keine Besprechungs-Chat** Funktion nicht.</span><span class="sxs-lookup"><span data-stu-id="07ec9-153">In the **Participants** management options, which are accessible by pointing to the people icon in the meeting window, the **No Meeting IM** option does not function.</span></span>

  - <span data-ttu-id="07ec9-154">Die Katalogansicht funktioniert nicht in Videokonferenzen.</span><span class="sxs-lookup"><span data-stu-id="07ec9-154">Gallery View does not function in video conferences.</span></span> <span data-ttu-id="07ec9-155">Der Benutzer sieht anstelle aller Lautsprecher nur den aktiven Lautsprecher.</span><span class="sxs-lookup"><span data-stu-id="07ec9-155">The user sees only the active speaker instead of all speakers.</span></span> <span data-ttu-id="07ec9-156">In der Liste der Optionen zum **Auswählen eines Layouts** ist die **Katalogansicht** nicht verfügbar.</span><span class="sxs-lookup"><span data-stu-id="07ec9-156">In the list of **Pick a Layout** options, **Gallery View** is unavailable</span></span>

  - <span data-ttu-id="07ec9-157">Die Teilnehmerliste wird standardmäßig in Videokonferenzen angezeigt.</span><span class="sxs-lookup"><span data-stu-id="07ec9-157">The participant list displays by default in video conferences.</span></span>

  - <span data-ttu-id="07ec9-158">Wenn Sie mit der rechten Maustaste auf einen Benutzer in der Teilnehmerliste klicken, sind die Verwaltungsoptionen **Video Spotlight** und **PIN-an-Katalog** -Teilnehmerverwaltung Sperren nicht verfügbar.</span><span class="sxs-lookup"><span data-stu-id="07ec9-158">When right-clicking a user in the participants list, the **Lock the Video Spotlight** and **Pin to Gallery** participant management options are unavailable.</span></span>

</div>

</div>

<div>

## <a name="user-experience-during-office-communications-server-2007-r2-migration"></a><span data-ttu-id="07ec9-159">Benutzererfahrung während Office Communications Server 2007 R2 Migration</span><span class="sxs-lookup"><span data-stu-id="07ec9-159">User Experience during Office Communications Server 2007 R2 Migration</span></span>

<span data-ttu-id="07ec9-160">Dieser Abschnitt enthält eine Zusammenfassung der Benutzer Konferenz Erfahrung bei der Migration von Office Communications Server 2007 R2, sowohl vor als auch nach der Installation von lync 2013.</span><span class="sxs-lookup"><span data-stu-id="07ec9-160">This section provides a summary of users’ conferencing experience when migrating from Office Communications Server 2007 R2, both before and after Lync 2013 is installed.</span></span> <span data-ttu-id="07ec9-161">Weitere Informationen zur Koexistenz von lync Server 2013-Clients und zur Interaktion mit vorherigen Client-und Server Versionen finden Sie unter [Client Interoperabilität in lync 2013](lync-server-2013-client-interoperability-in-lync-2013.md).</span><span class="sxs-lookup"><span data-stu-id="07ec9-161">For more details about how Lync Server 2013 clients can coexist and interact with previous client and server versions, see [Client interoperability in Lync 2013](lync-server-2013-client-interoperability-in-lync-2013.md).</span></span>

<div>

## <a name="after-user-account-is-migrated-before-lync-2013-is-installed"></a><span data-ttu-id="07ec9-162">Nachdem das Benutzerkonto migriert wurde, bevor lync 2013 installiert ist</span><span class="sxs-lookup"><span data-stu-id="07ec9-162">After User Account is Migrated, Before Lync 2013 Is Installed</span></span>

<span data-ttu-id="07ec9-163">Nachdem ein Benutzer zum lync Server 2013 Server migriert wurde, aber bevor neue Clients installiert werden, können Office Communicator 2007 R2 Benutzer den vorhandenen Client weiterhin für die lync Server 2013 von Anwesenheits-und Chat Features verwenden, aber Konferenzfeatures werden nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="07ec9-163">After a user is migrated to the Lync Server 2013 server, but before new clients are installed, Office Communicator 2007 R2 users can continue to use their existing client against Lync Server 2013 for presence and IM features, but conferencing features are not supported.</span></span>

</div>

<div>

## <a name="after-user-account-is-migrated-after-lync-2013-is-installed"></a><span data-ttu-id="07ec9-164">Nachdem das Benutzerkonto migriert wurde, nachdem lync 2013 installiert wurde</span><span class="sxs-lookup"><span data-stu-id="07ec9-164">After User Account is Migrated, After Lync 2013 Is Installed</span></span>

<span data-ttu-id="07ec9-165">Wenn ein migrierter Benutzer lync 2013 installiert, wird auch das Online Besprechungs-Add-in für lync 2013 installiert.</span><span class="sxs-lookup"><span data-stu-id="07ec9-165">When a migrated user installs Lync 2013, the Online Meeting Add-in for Lync 2013 is installed too.</span></span> <span data-ttu-id="07ec9-166">Dies hat folgende Auswirkungen:</span><span class="sxs-lookup"><span data-stu-id="07ec9-166">This has the following effects:</span></span>

  - <span data-ttu-id="07ec9-167">Alle nachfolgend geplanten Besprechungen verwenden das neue Besprechungsformat mit einer Adresse vom Typ "https://" anstatt der früheren Live Meeting-Adresse vom Typ "meet://".</span><span class="sxs-lookup"><span data-stu-id="07ec9-167">All subsequently scheduled meetings use the new meeting format, which uses an https:// address instead of the legacy meet:// Live Meeting address.</span></span>

  - <span data-ttu-id="07ec9-168">In einer IT-verwalteten Bereitstellung von lync 2013 hat der Administrator die Möglichkeit, die Add-in für Konferenzen für Microsoft Office Outlook zu deinstallieren, die zum Planen von Live Meeting Server-und dienstbasierten Besprechungen verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="07ec9-168">In an IT-managed deployment of Lync 2013, the administrator has the option of uninstalling the Conferencing Add-in for Microsoft Office Outlook, which is used to schedule Live Meeting server and service-based meetings.</span></span> <span data-ttu-id="07ec9-169">Möglicherweise müssen einige Benutzer jedoch weiterhin auf Live Meeting-Diensten basierte Besprechungen planen.</span><span class="sxs-lookup"><span data-stu-id="07ec9-169">However, you may have users who need to continue to schedule Live Meeting service meetings.</span></span> <span data-ttu-id="07ec9-170">In einem solchen Fall ist es möglich, die gemeinsame Ausführung beider Add-Ins zuzulassen.</span><span class="sxs-lookup"><span data-stu-id="07ec9-170">In this case, you can allow both add-ins to coexist.</span></span>

</div>

<div>

## <a name="meetings-with-federated-organizations-that-use-previous-clients"></a><span data-ttu-id="07ec9-171">Besprechungen mit Verbundorganisationen, die frühere Clients verwenden</span><span class="sxs-lookup"><span data-stu-id="07ec9-171">Meetings with Federated Organizations that Use Previous Clients</span></span>

<span data-ttu-id="07ec9-172">Benutzer in Verbundorganisationen, die Microsoft Office Communicator 2007 verwenden, können in Ihrer Organisation nicht an lync Server 2013 Besprechungen teilnehmen, wenn diese Besprechungen vom Organisator gesperrt sind.</span><span class="sxs-lookup"><span data-stu-id="07ec9-172">Users in federated organizations who are using Microsoft Office Communicator 2007 cannot join Lync Server 2013 meetings in your organization if those meetings are locked by the organizer.</span></span> <span data-ttu-id="07ec9-173">Sie müssen diese Besprechungen in lync Server 2013 neu planen, sodass Sie lync Web App verwenden können, wenn Partner Teilnehmer der Besprechung mithilfe der neuen https://-Besprechungs-URL beitreten.</span><span class="sxs-lookup"><span data-stu-id="07ec9-173">You have to reschedule these meetings in Lync Server 2013 so when federated participants join the meeting by using the new https:// meeting URL, they can use Lync Web App.</span></span>

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

