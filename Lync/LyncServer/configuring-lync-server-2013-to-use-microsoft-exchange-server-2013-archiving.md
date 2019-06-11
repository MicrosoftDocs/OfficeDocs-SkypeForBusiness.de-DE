---
title: Konfigurieren von lync Server 2013 für die Verwendung von Microsoft Exchange Server 2013-Archivierung
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring Lync Server 2013 to use Exchange Server 2013 archiving
ms:assetid: 260346d1-edc8-4a0c-8ad2-6c2401c3c377
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ679896(v=OCS.15)
ms:contentKeyID: 49557731
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b3f8ab22ed23adbce2d6cbd6ccbf1f378476ff00
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34839844"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-microsoft-lync-server-2013-to-use-microsoft-exchange-server-2013-archiving"></a><span data-ttu-id="422f0-102">Konfigurieren von Microsoft lync Server 2013 für die Verwendung von Microsoft Exchange Server 2013-Archivierung</span><span class="sxs-lookup"><span data-stu-id="422f0-102">Configuring Microsoft Lync Server 2013 to use Microsoft Exchange Server 2013 archiving</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="422f0-103">_**Letztes Änderungsdatum des Themas:** 2014-06-24_</span><span class="sxs-lookup"><span data-stu-id="422f0-103">_**Topic Last Modified:** 2014-06-24_</span></span>

<span data-ttu-id="422f0-104">Microsoft lync Server 2013 bietet Administratoren die Möglichkeit, im Postfach des Microsoft Exchange Server 2013 des Benutzers anstelle einer SQL Server-Datenbank Instant Messaging-und Webkonferenz Protokolle zu archivieren.</span><span class="sxs-lookup"><span data-stu-id="422f0-104">Microsoft Lync Server 2013 gives administrators the option of having instant messaging and Web conferencing transcripts archived to a user's Microsoft Exchange Server 2013 mailbox rather than a SQL Server database.</span></span> <span data-ttu-id="422f0-105">Wenn Sie diese Option aktivieren, werden Aufzeichnungen in den Löschordner des Benutzerpostfachs geschrieben.</span><span class="sxs-lookup"><span data-stu-id="422f0-105">If you enable this option, transcripts are written to the Purges folder in the user's mailbox.</span></span> <span data-ttu-id="422f0-106">Der Löschordner ist ein ausgeblendeter Ordner im Ordner „Wiederherstellbare Elemente“.</span><span class="sxs-lookup"><span data-stu-id="422f0-106">The Purges folder is a hidden folder found in the Recoverable Items folder.</span></span> <span data-ttu-id="422f0-107">Obwohl dieser Ordner für Endbenutzer nicht sichtbar ist, wird der Ordner von der Exchange-Suchmaschine indiziert und kann mithilfe der Exchange-Postfachsuche und/oder Microsoft SharePoint Server 2013 ermittelt werden.</span><span class="sxs-lookup"><span data-stu-id="422f0-107">Although this folder is not visible to end-users, the folder is indexed by the Exchange search engine and can be discovered by using Exchange mailbox search and/or Microsoft SharePoint Server 2013.</span></span> <span data-ttu-id="422f0-108">Da die Informationen im gleichen Ordner gespeichert sind, der von der Exchange-Funktion für in-situ-Speicher (für das Archivieren von e-Mails und anderer Exchange-Kommunikation) verwendet wird, können Administratoren ein einzelnes Tool verwenden, um nach der gesamten elektronischen Kommunikation zu suchen, die für eine archiviert wurde. Benutzer.</span><span class="sxs-lookup"><span data-stu-id="422f0-108">Because information is stored in the same folder used by the Exchange In-Place Hold feature (responsible for archiving email and other Exchange communications), administrators can use a single tool to search for all the electronic communications archived for a user.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="422f0-109">Um die Archivierung von lync-Unterhaltungen vollständig zu deaktivieren, müssen Sie auch das lync-Konversationsprotokoll deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="422f0-109">To completely disable archiving of Lync conversation, you must also disable Lync conversation history.</span></span> <span data-ttu-id="422f0-110">Weitere Informationen finden Sie unter den folgenden Themen: <A href="lync-server-2013-managing-the-archiving-of-internal-and-external-communications.md">Verwalten der Archivierung interner und externer Kommunikation in lync Server 2013</A>, <A href="https://docs.microsoft.com/powershell/module/skype/New-CsClientPolicy">New-CsClientPolicy</A>und <A href="https://docs.microsoft.com/powershell/module/skype/Set-CsClientPolicy">CsClientPolicy</A>.</span><span class="sxs-lookup"><span data-stu-id="422f0-110">For more information, see the following topics: <A href="lync-server-2013-managing-the-archiving-of-internal-and-external-communications.md">Managing the Archiving of internal and external communications in Lync Server 2013</A>, <A href="https://docs.microsoft.com/powershell/module/skype/New-CsClientPolicy">New-CsClientPolicy</A>, and <A href="https://docs.microsoft.com/powershell/module/skype/Set-CsClientPolicy">Set-CsClientPolicy</A>.</span></span>



</div>

<span data-ttu-id="422f0-111">Um Transkripte in Exchange 2013 zu archivieren, müssen Sie zunächst die Server-zu-Server-Authentifizierung zwischen den beiden Servern konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="422f0-111">In order to archive transcripts to Exchange 2013 you must begin by configuring server-to-server authentication between the two servers.</span></span> <span data-ttu-id="422f0-112">Nachdem die Server-zu-Server-Authentifizierung eingerichtet ist, können Sie die folgenden Aufgaben in Microsoft lync Server 2013 ausführen (Beachten Sie, dass Sie – je nach Konfiguration und Konfiguration – möglicherweise nicht alle diese Aufgaben ausführen müssen):</span><span class="sxs-lookup"><span data-stu-id="422f0-112">After server-to-server authentication is in place you can then carry out the following tasks in Microsoft Lync Server 2013 (note that, depending on your setup and configuration, you might not need to complete all of these tasks):</span></span>

1.  <span data-ttu-id="422f0-113">Aktivieren Sie die Exchange-Archivierung, indem Sie die Konfigurationseinstellungen ihrer lync Server-Archivierung ändern.</span><span class="sxs-lookup"><span data-stu-id="422f0-113">Enable Exchange archiving by modifying your Lync Server archiving configuration settings.</span></span> <span data-ttu-id="422f0-114">Dieser Schritt ist für alle Bereitstellungen erforderlich.</span><span class="sxs-lookup"><span data-stu-id="422f0-114">This step is required for all deployments.</span></span>

2.  <span data-ttu-id="422f0-115">Aktivieren Sie die Archivierung der internen und/oder externen Kommunikation für Ihre Benutzer.</span><span class="sxs-lookup"><span data-stu-id="422f0-115">Enable archiving for internal and/or external communications for your users.</span></span> <span data-ttu-id="422f0-116">Dieser Schritt ist für alle Bereitstellungen erforderlich.</span><span class="sxs-lookup"><span data-stu-id="422f0-116">This step is required for all deployments.</span></span>

3.  <span data-ttu-id="422f0-117">Konfigurieren Sie die Eigenschaft „ExchangeArchivingPolicy“ für jeden Benutzer.</span><span class="sxs-lookup"><span data-stu-id="422f0-117">Configure the ExchangeArchivingPolicy property for each user.</span></span> <span data-ttu-id="422f0-118">Dieser Schritt ist nur in lync Server erforderlich, und Exchange befindet sich in verschiedenen Gesamtstrukturen.</span><span class="sxs-lookup"><span data-stu-id="422f0-118">This step is only required in Lync Server and Exchange are located in different forests.</span></span>

<div>

## <a name="step-1-enabling-exchange-archiving"></a><span data-ttu-id="422f0-119">Schritt 1: Aktivieren der Exchange-Archivierung</span><span class="sxs-lookup"><span data-stu-id="422f0-119">Step 1: Enabling Exchange Archiving</span></span>

<span data-ttu-id="422f0-120">Die Archivierung in lync Server wird hauptsächlich mithilfe der Archivierungs Konfigurationseinstellungen verwaltet.</span><span class="sxs-lookup"><span data-stu-id="422f0-120">Archiving in Lync Server is primarily managed by using the archiving configuration settings.</span></span> <span data-ttu-id="422f0-121">Wenn Sie lync Server 2013 installieren, erhalten Sie automatisch eine einzige globale Sammlung dieser Einstellungen.</span><span class="sxs-lookup"><span data-stu-id="422f0-121">When you install Lync Server 2013 you are automatically given a single, global collection of these settings.</span></span> <span data-ttu-id="422f0-122">(Administratoren können optional neue Sammlungen von Archivierungseinstellungen im Website Bereich erstellen.) Standardmäßig ist die Archivierung in den globalen Einstellungen nicht aktiviert, und die Exchange-Archivierung ist in diesen Einstellungen nicht aktiviert.</span><span class="sxs-lookup"><span data-stu-id="422f0-122">(Administrators can optionally create new collections of archiving settings at the site scope.) By default, archiving is not enabled in the global settings, nor is Exchange archiving enabled in these settings.</span></span> <span data-ttu-id="422f0-123">Um Exchange-Archivierungs Administratoren verwenden zu können, müssen die EnableArchiving-und die EnableExchangeArchiving-Eigenschaft in diesen Konfigurationseinstellungen konfiguriert werden.</span><span class="sxs-lookup"><span data-stu-id="422f0-123">In order to use Exchange archiving administrators must configure both the EnableArchiving and the EnableExchangeArchiving properties in these configuration settings.</span></span> <span data-ttu-id="422f0-124">Die Eigenschaft „EnableArchiving“ kann auf einen von drei möglichen Werten festgelegt werden:</span><span class="sxs-lookup"><span data-stu-id="422f0-124">The EnableArchiving property can be set to one of three possible values:</span></span>

  - <span data-ttu-id="422f0-125">**Keine**.</span><span class="sxs-lookup"><span data-stu-id="422f0-125">**None**.</span></span> <span data-ttu-id="422f0-126">Die Archivierung ist deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="422f0-126">Archiving is disabled.</span></span> <span data-ttu-id="422f0-127">Dies ist der Standardwert.</span><span class="sxs-lookup"><span data-stu-id="422f0-127">This is the default value.</span></span> <span data-ttu-id="422f0-128">Wenn EnableArchiving auf None eingestellt ist, wird in ihrer lync Server-Archivierungsdatenbank oder in Exchange 2013 nichts archiviert.</span><span class="sxs-lookup"><span data-stu-id="422f0-128">If EnableArchiving is set to None then nothing will be archived in either your Lync Server archiving database or in Exchange 2013.</span></span>

  - <span data-ttu-id="422f0-129">\*\*\*\* Ist nicht verfügbar.</span><span class="sxs-lookup"><span data-stu-id="422f0-129">**ImOnly**.</span></span> <span data-ttu-id="422f0-130">Es werden nur Sofortnachrichten Abschriften archiviert.</span><span class="sxs-lookup"><span data-stu-id="422f0-130">Only instant message transcripts are archived.</span></span> <span data-ttu-id="422f0-131">Wenn die Exchange-Archivierung aktiviert ist, werden diese Protokolle in Exchange 2013 archiviert.</span><span class="sxs-lookup"><span data-stu-id="422f0-131">If Exchange archiving is enabled these transcripts will be archived in Exchange 2013.</span></span> <span data-ttu-id="422f0-132">Wenn die Exchange-Archivierung deaktiviert ist, werden diese Protokolle auf lync Server archiviert.</span><span class="sxs-lookup"><span data-stu-id="422f0-132">If Exchange archiving is disabled then these transcripts will be archived to Lync Server.</span></span>

  - <span data-ttu-id="422f0-133">**ImAndWebConf**.</span><span class="sxs-lookup"><span data-stu-id="422f0-133">**ImAndWebConf**.</span></span> <span data-ttu-id="422f0-134">Sowohl Sofortnachrichten Protokolle als auch Webkonferenz-Transkripte werden archiviert.</span><span class="sxs-lookup"><span data-stu-id="422f0-134">Both instant message transcripts and Web conferencing transcripts are archived.</span></span> <span data-ttu-id="422f0-135">Wenn die Exchange-Archivierung aktiviert ist, werden diese Protokolle in Exchange 2013 archiviert.</span><span class="sxs-lookup"><span data-stu-id="422f0-135">If Exchange archiving is enabled these transcripts will be archived in Exchange 2013.</span></span> <span data-ttu-id="422f0-136">Wenn die Exchange-Archivierung deaktiviert ist, werden diese Protokolle auf lync Server archiviert.</span><span class="sxs-lookup"><span data-stu-id="422f0-136">If Exchange archiving is disabled then these transcripts will be archived to Lync Server.</span></span>

<span data-ttu-id="422f0-137">Die EnableExchangeArchiving-Eigenschaft ist ein boolescher Wert: setzen Sie EnableExchangeArchiving auf true ($true), um die Exchange-Archivierung zu aktivieren oder EnableExchangeArchiving auf false festzulegen ($false), um die Exchange-Archivierung zu deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="422f0-137">The EnableExchangeArchiving property is a Boolean value: set EnableExchangeArchiving to True ($True) to enable Exchange archiving or set EnableExchangeArchiving to False ($False) to disable Exchange archiving.</span></span> <span data-ttu-id="422f0-138">Mit diesem Befehl können Sie beispielsweise die Archivierung von Sofortnachrichten Abschriften und die Exchange-Archivierung aktivieren:</span><span class="sxs-lookup"><span data-stu-id="422f0-138">For example, this command enables the archiving of instant messaging transcripts and also enables Exchange archiving:</span></span>

    Set-CsArchivingConfiguration -Identity "global" -EnableArchiving ImOnly -EnableExchangeArchiving $True

<span data-ttu-id="422f0-139">Wenn Sie die Exchange-Archivierung deaktivieren möchten, verwenden Sie einen Befehl ähnlich der folgenden, der die Sofortnachrichten Archivierung ermöglicht, aber die Archivierung in Exchange deaktiviert (d. h., Transkripte werden auf dem lync-Server archiviert):</span><span class="sxs-lookup"><span data-stu-id="422f0-139">To disable Exchange archiving, use a command similar to the following, which enables instant messaging archiving but disables archiving to Exchange (in other words, transcripts will be archived to Lync Server):</span></span>

    Set-CsArchivingConfiguration -Identity "global" -EnableArchiving ImOnly -EnableExchangeArchiving $False

<div>


> [!NOTE]  
> <span data-ttu-id="422f0-140">Wenn die EnableArchiving-Eigenschaft auf None eingestellt ist, werden von lync Server keine Sofortnachrichten und Webkonferenz-Transkripte archiviert.</span><span class="sxs-lookup"><span data-stu-id="422f0-140">If the EnableArchiving property is set to None then Lync Server will not archive instant messaging and Web conferencing transcripts at all.</span></span> <span data-ttu-id="422f0-141">In diesem Fall ignoriert der Server einfach den für EnableExchangeArchiving konfigurierten Wert.</span><span class="sxs-lookup"><span data-stu-id="422f0-141">In that case, the server will simply ignore the value configured for EnableExchangeArchiving.</span></span>



</div>

<span data-ttu-id="422f0-142">Die Exchange-Archivierung kann auch mithilfe der lync Server-Systemsteuerung aktiviert (oder deaktiviert) werden.</span><span class="sxs-lookup"><span data-stu-id="422f0-142">Exchange archiving can also be enabled (or disabled) by using the Lync Server Control Panel.</span></span> <span data-ttu-id="422f0-143">Führen Sie hierzu das folgende Verfahren aus:</span><span class="sxs-lookup"><span data-stu-id="422f0-143">To do that, complete the following procedure:</span></span>

1.  <span data-ttu-id="422f0-144">Klicken Sie in der Systemsteuerung auf **Überwachung und Archivierung** und dann auf **Archivierungskonfiguration**.</span><span class="sxs-lookup"><span data-stu-id="422f0-144">In Control Panel, click **Monitoring and Archiving**, and then click **Archiving Configuration**.</span></span>

2.  <span data-ttu-id="422f0-145">Doppelklicken Sie auf der Registerkarte **Archivierungskonfiguration** auf die zu ändernde Auflistung von Archivierungseinstellungen (z. B. auf die Auflistung **Global**).</span><span class="sxs-lookup"><span data-stu-id="422f0-145">On the **Archiving Configuration** tab, double-click the collection of archiving settings to be modified (for example, the **Global** collection).</span></span>

3.  <span data-ttu-id="422f0-146">Klicken Sie im Bereich **Archivierungseinstellung bearbeiten** auf die Dropdownliste **Archivierungseinstellung** und wählen Sie entweder **Chatsitzungen archivieren** (um nur Chatsitzungen zu archivieren) oder **Chat- und Webkonferenzsitzungen archivieren** (um sowohl Chat- als auch Webkonferenzsitzungen zu archivieren).</span><span class="sxs-lookup"><span data-stu-id="422f0-146">In the **Edit Archiving Setting** pane, click the **Archiving setting** dropdown list and select either **Archive IM sessions** (to archive just instant messaging sessions) or **Archive IM and web conferencing sessions** (to archive both instant messaging and Web conferencing sessions).</span></span>

4.  <span data-ttu-id="422f0-147">Nachdem Sie die zu archivierende Elemente ausgewählt haben, aktivieren Sie das Kontrollkästchen **Exchange-Server Integration** , um die Exchange-Archivierung zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="422f0-147">After choosing the items to be archived, select the **Exchange Server integration** checkbox to enable Exchange archiving.</span></span> <span data-ttu-id="422f0-148">Deaktivieren Sie dieses Kontrollkästchen, um die Exchange-Archivierung zu deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="422f0-148">To disable Exchange archiving, clear this checkbox.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="422f0-149">Das Kontrollkästchen <STRONG>Exchange Server-Integration</STRONG> ist nicht verfügbar, wenn <STRONG>Archivierungseinstellung</STRONG> auf <STRONG>Archivierung deaktivieren</STRONG> festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="422f0-149">The <STRONG>Exchange Server integration</STRONG> checkbox will not be available if the <STRONG>Archiving setting</STRONG> is set to <STRONG>Disable archiving</STRONG>.</span></span> <span data-ttu-id="422f0-150">Sie müssen zuerst die Archivierung aktivieren und dann die Exchange-Archivierung aktivieren.</span><span class="sxs-lookup"><span data-stu-id="422f0-150">You must enable archiving first and then enable Exchange archiving.</span></span>



</div>

<span data-ttu-id="422f0-151">Wenn sich lync Server 2013 und Exchange 2013 in derselben Gesamtstruktur befinden, wird die Archivierung für einzelne Benutzer (oder zumindest für Benutzer mit e-Mail-Konten in Exchange 2013) mithilfe von Exchange-in-situ-Speicherrichtlinien verwaltet.</span><span class="sxs-lookup"><span data-stu-id="422f0-151">If Lync Server 2013 and Exchange 2013 are located in the same forest then archiving for individual users (or at least for users who have email accounts on Exchange 2013) is managed by using Exchange In-Place Hold policies.</span></span> <span data-ttu-id="422f0-152">Wenn Sie über Benutzer verfügen, die in einer früheren Version von Exchange verwaltet werden, wird die Archivierung für diese Benutzer mithilfe von lync Server-Archivierungsrichtlinien verwaltet.</span><span class="sxs-lookup"><span data-stu-id="422f0-152">If you have users who are homed on a previous version of Exchange then archiving for those users will be managed by using Lync Server archiving policies.</span></span> <span data-ttu-id="422f0-153">Beachten Sie, dass nur Benutzer mit Konten in Exchange 2013 ihre lync-Transkripte in Exchange archivieren können.</span><span class="sxs-lookup"><span data-stu-id="422f0-153">Note that only users with accounts on Exchange 2013 can have their Lync transcripts archived to Exchange.</span></span>

<span data-ttu-id="422f0-154">Wenn sich lync Server 2013 und Exchange 2013 in verschiedenen Gesamtstrukturen befinden, wird die Archivierung für einzelne Benutzer durch Konfigurieren der ExchangeArchivingPolicy-Eigenschaft für jedes einzelne Benutzerkonto verwaltet.</span><span class="sxs-lookup"><span data-stu-id="422f0-154">If Lync Server 2013 and Exchange 2013 are located in different forests then archiving for individual users is managed by configuring the ExchangeArchivingPolicy property for each individual user account.</span></span> <span data-ttu-id="422f0-155">Weitere Informationen finden Sie in Schritt 3.</span><span class="sxs-lookup"><span data-stu-id="422f0-155">See Step 3 for more information.</span></span>

</div>

<div>

## <a name="step-2-enabling-the-archiving-of-internal-andor-external-communications"></a><span data-ttu-id="422f0-156">Schritt 2: Aktivieren der Archivierung der internen und/oder externen Kommunikation</span><span class="sxs-lookup"><span data-stu-id="422f0-156">Step 2: Enabling the Archiving of Internal and/or External Communications</span></span>

<span data-ttu-id="422f0-157">Nachdem Sie die Archivierung (und die Exchange-Archivierung) aktiviert haben, müssen Sie die entsprechenden Archivierungsrichtlinien ändern, um sicherzustellen, dass Benutzersitzungen tatsächlich archiviert werden.</span><span class="sxs-lookup"><span data-stu-id="422f0-157">After you have enabled archiving (and Exchange archiving) you must then modify the appropriate archiving policies to ensure that user sessions are actually archived.</span></span> <span data-ttu-id="422f0-158">Beachten Sie, dass die Archivierung von Instant Messaging-und Webkonferenz-Transkripten nicht durch lync Server gestartet werden kann (Schritt 1).</span><span class="sxs-lookup"><span data-stu-id="422f0-158">Note that simply enabling archiving (Step 1) does not cause Lync Server to begin archiving instant messaging and Web conferencing transcripts.</span></span> <span data-ttu-id="422f0-159">Stattdessen müssen Sie mit Archivierungsrichtlinien die interne und/oder externe Archivierung aktivieren.</span><span class="sxs-lookup"><span data-stu-id="422f0-159">Instead, you must use archiving policies to enable internal and/or external archiving.</span></span> <span data-ttu-id="422f0-160">Wenn Sie lync Server 2013 installieren, installieren Sie auch eine einzige globale Archivierungsrichtlinie, die zwei Eigenschaften enthält:</span><span class="sxs-lookup"><span data-stu-id="422f0-160">When you install Lync Server 2013 you also install a single, global archiving policy that contains two properties:</span></span>

  - <span data-ttu-id="422f0-p119">**ArchiveInternal**: Ist diese Eigenschaft auf „True“ ($True) gesetzt, werden interne Kommunikationssitzungen archiviert, an denen nur Benutzer in der Organisation beteiligt sind, die ein Active Directory-Konto besitzen.</span><span class="sxs-lookup"><span data-stu-id="422f0-p119">**ArchiveInternal**. When set to True ($True) indicates that internal communication sessions involving only users who have Active Directory accounts in your organization) will be archived.</span></span>

  - <span data-ttu-id="422f0-p120">**ArchiveExternal**: Ist diese Eigenschaft auf „True“ ($True) gesetzt, werden externe Kommunikationssitzungen archiviert (Sitzungen, an denen mindestens ein Benutzer beteiligt ist, der kein Active Directory-Konto in Ihrer Organisation besitzt).</span><span class="sxs-lookup"><span data-stu-id="422f0-p120">**ArchiveExternal**. When set to True ($True) indicates that internal communication sessions (sessions involving at least one user who does not have an Active Directory account in your organization) will be archived.</span></span>

<span data-ttu-id="422f0-165">Standardmäßig sind beide Eigenschaftenwerte auf "false" festgelegt, was bedeutet, dass weder interne noch externe Kommunikationssitzungen archiviert werden.</span><span class="sxs-lookup"><span data-stu-id="422f0-165">By default, both of these property values are set to False, meaning that neither internal nor external communication sessions are archived.</span></span> <span data-ttu-id="422f0-166">Zum Ändern der globalen Richtlinie können Sie die lync Server-Verwaltungsshell und das Cmdlet "Satz-CsArchivingPolicy" verwenden.</span><span class="sxs-lookup"><span data-stu-id="422f0-166">To modify the global policy, you can use the Lync Server Management Shell and the Set-CsArchivingPolicy cmdlet.</span></span> <span data-ttu-id="422f0-167">Dieser Befehl ermöglicht die Archivierung interner und externer Kommunikationssitzungen:</span><span class="sxs-lookup"><span data-stu-id="422f0-167">This command enables the archiving of both internal and external communication sessions:</span></span>

    Set-CsArchivingPolicy -Identity "global" -ArchiveInternal $True -ArchiveExternal $True

<span data-ttu-id="422f0-p122">Alternativ können Sie „New-CsArchivingPolicy“ verwenden, um entweder auf Standort- oder auf Einzelbenutzerebene eine neue Richtlinie zu erstellen. Mit diesem Befehl wird z. B. eine neue Archivierungsrichtlinie auf Benutzerebene namens „RedmondArchivingPolicy“ erstellt:</span><span class="sxs-lookup"><span data-stu-id="422f0-p122">Alternatively, you can use the New-CsArchivingPolicy to create a new policy at either the site scope or the per-user scope. For example, this command creates a new per-user archiving policy named RedmondArchivingPolicy:</span></span>

    New-CsArchivingPolicy -Identity "RedmondArchivingPolicy" -ArchiveInternal $True -ArchiveExternal $True

<span data-ttu-id="422f0-p123">Wenn Sie eine Richtlinie auf Einzelbenutzerebene erstellen, müssen Sie diese Richtlinie den entsprechenden Benutzern zuweisen. Beispiel:</span><span class="sxs-lookup"><span data-stu-id="422f0-p123">If you create a per-user policy you will then need to assign that policy to the appropriate users. For example:</span></span>

    Grant-CsArchivingPolicy -Identity "Ken Myer" -PolicyName  "RedmondArchivingPolicy"

<span data-ttu-id="422f0-172">Archivierungsrichtlinien können auch mithilfe der lync Server-Systemsteuerung verwaltet werden.</span><span class="sxs-lookup"><span data-stu-id="422f0-172">Archiving policies can also be managed by using the Lync Server Control Panel.</span></span> <span data-ttu-id="422f0-173">Klicken Sie in der Systemsteuerung auf **Überwachung und Archivierung** und anschließend auf **Archivierungsrichtlinie**.</span><span class="sxs-lookup"><span data-stu-id="422f0-173">Within the Control Panel, click **Monitoring and Archiving** and then click **Archiving Policy**.</span></span> <span data-ttu-id="422f0-174">Wenn Sie eine vorhandene Richtlinie ändern möchten, doppelklicken Sie auf die Richtlinie (z. b. Global), und aktivieren oder deaktivieren Sie dann im Bereich **Archivierungsrichtlinie bearbeiten** die Kontrollkästchen **interne Kommunikation** und **externe Kommunikation archivieren** nach Bedarf.</span><span class="sxs-lookup"><span data-stu-id="422f0-174">To modify an existing policy, double-click the policy (e.g., Global) and then, in the **Edit Archiving Policy** pane, select or clear the **Archive internal communications** and the **Archive external communications** checkboxes as needed.</span></span> <span data-ttu-id="422f0-175">Wenn Sie eine neue Archivierungsrichtlinie erstellen möchten, klicken Sie auf **neu** , und wählen Sie dann entweder **Website Richtlinie** oder **Benutzerrichtlinie**aus.</span><span class="sxs-lookup"><span data-stu-id="422f0-175">To create a new archiving policy, click **New** and then select either **Site policy** or **User policy**.</span></span> <span data-ttu-id="422f0-176">Wenn Sie eine neue Benutzerrichtlinie erstellen, müssen Sie (über die Registerkarte „Benutzer“) auf die entsprechenden Benutzerkonten zugreifen und diesen Benutzern die neue Richtlinie zuweisen.</span><span class="sxs-lookup"><span data-stu-id="422f0-176">If you create a new user policy then you must access the appropriate user accounts (from the **Users** tab) and assign those users the new policy.</span></span>

</div>

<div>

## <a name="step-3-configuring-the-exchangearchivingpolicy-property"></a><span data-ttu-id="422f0-177">Schritt 3: Konfigurieren der Eigenschaft "ExchangeArchivingPolicy"</span><span class="sxs-lookup"><span data-stu-id="422f0-177">Step 3: Configuring the ExchangeArchivingPolicy Property</span></span>

<span data-ttu-id="422f0-178">Wenn sich lync Server 2013 und Exchange 2013 in unterschiedlichen Gesamtstrukturen befinden, reicht es nicht aus, die Exchange-Archivierung einfach in den Archivierungs Konfigurationseinstellungen zu aktivieren. Dadurch werden keine Instant Messaging-und Webkonferenz Protokolle in Exchange archiviert.</span><span class="sxs-lookup"><span data-stu-id="422f0-178">If Lync Server 2013 and Exchange 2013 are located in different forests then it is not enough to simply enable Exchange archiving in the archiving configuration settings; that will not result in instant messaging and Web conferencing transcripts being archived in Exchange.</span></span> <span data-ttu-id="422f0-179">Stattdessen müssen Sie auch die ExchangeArchivingPolicy-Eigenschaft für jedes der relevanten lync Server-Benutzerkonten konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="422f0-179">Instead, you must also configure the ExchangeArchivingPolicy property on each of the relevant Lync Server user accounts.</span></span> <span data-ttu-id="422f0-180">Diese Eigenschaft kann auf einen von vier möglichen Werten eingestellt werden:</span><span class="sxs-lookup"><span data-stu-id="422f0-180">This property can be set to one of four possible values:</span></span>

1.  <span data-ttu-id="422f0-181">Uninitialized: Zeigt an, dass die Archivierung auf den Compliance-Archiv-Einstellungen basiert, die für das nm-exch-15-short-Postfach des Benutzers konfiguriert sind.</span><span class="sxs-lookup"><span data-stu-id="422f0-181">Uninitialized.</span></span> <span data-ttu-id="422f0-182">Gibt an, dass die Archivierung auf den in-situ-Speicherungs Einstellungen basiert, die für das Exchange-Postfach des Benutzers konfiguriert sind. Wenn in-situ-Speicher für das Postfach des Benutzers nicht aktiviert wurde, werden die Nachrichten-und Webkonferenz Protokolle des Benutzers in lync Server archiviert.</span><span class="sxs-lookup"><span data-stu-id="422f0-182">Indicates that archiving will be based on the In-Place Hold settings configured for the user's Exchange mailbox; if In-Place Hold has not been enabled on the user's mailbox then the user will have his or her messaging and Web conferencing transcripts archived in Lync Server.</span></span>

2.  <span data-ttu-id="422f0-183">**UseLyncArchivingPolicy**.</span><span class="sxs-lookup"><span data-stu-id="422f0-183">**UseLyncArchivingPolicy**.</span></span> <span data-ttu-id="422f0-184">Gibt an, dass die Protokolle für Sofortnachrichten und Webkonferenzen des Benutzers in lync Server und nicht in Exchange archiviert werden sollen.</span><span class="sxs-lookup"><span data-stu-id="422f0-184">Indicates that the user's instant messaging and Web conferencing transcripts should be archived in Lync Server rather than in Exchange.</span></span>

3.  <span data-ttu-id="422f0-185">\*\*\*\* Noarchiving.</span><span class="sxs-lookup"><span data-stu-id="422f0-185">**NoArchiving**.</span></span> <span data-ttu-id="422f0-186">Gibt an, dass die Protokolle für Chatnachrichten und Webkonferenzen des Benutzers überhaupt nicht archiviert werden sollen.</span><span class="sxs-lookup"><span data-stu-id="422f0-186">Indicates that the user's instant messaging and Web conferencing transcripts should not be archived at all.</span></span> <span data-ttu-id="422f0-187">Beachten Sie, dass diese Einstellung alle lync Server-Archivierungsrichtlinien außer Kraft setzt, die dem Benutzer zugewiesen sind.</span><span class="sxs-lookup"><span data-stu-id="422f0-187">Note that this setting overrides any Lync Server archiving policies assigned to the user.</span></span>

4.  <span data-ttu-id="422f0-188">**ArchivingToExchange**: zeigt an, dass die Chat- und Webkonferenzaufzeichnungen des Benutzers unabhängig von den Compliance-Archiv-Einstellungen, die ggf.</span><span class="sxs-lookup"><span data-stu-id="422f0-188">**ArchivingToExchange**.</span></span> <span data-ttu-id="422f0-189">Gibt an, dass die Protokolle des Benutzers für Sofortnachrichten und Webkonferenzen in Exchange unabhängig von den in-situ-Speicher-Einstellungen, die dem Postfach des Benutzers zugewiesen wurden (oder nicht), archiviert werden sollen.</span><span class="sxs-lookup"><span data-stu-id="422f0-189">Indicates that the user's instant messaging and Web conferencing transcripts should be archived to Exchange regardless of the In-Place Hold settings that have (or have not) been assigned to the user's mailbox.</span></span>

<span data-ttu-id="422f0-190">Wenn Sie beispielsweise ein Benutzerkonto so konfigurieren möchten, dass Sofortnachrichten und Webkonferenz Protokolle immer in Exchange archiviert werden, können Sie einen ähnlichen Befehl wie den folgenden in der lync Server-Verwaltungsshell verwenden:</span><span class="sxs-lookup"><span data-stu-id="422f0-190">For example, to configure a user account so that instant messaging and Web conferencing transcripts are always archived to Exchange you can use a command similar to this from the Lync Server Management Shell:</span></span>

    Set-CsUser -Identity "Ken Myer" -ExchangeArchivingPolicy ArchivingToExchange

<span data-ttu-id="422f0-191">Wenn Sie dieselbe Archivierungsrichtlinie für eine Gruppe von Benutzern (z. B. alle Benutzer, die im angegebenen Registrierungsstellenpool verwaltet werden) festlegen möchten, können Sie einen ähnlichen Befehl wie den folgenden verwenden:</span><span class="sxs-lookup"><span data-stu-id="422f0-191">If you want to set the same archiving policy for a group of users (for example, all the users homed on a specified Registrar pool) you can use a command similar to this:</span></span>

    Get-CsUser -Filter {RegistrarPool -eq "atl-cs-001.litwareinc.com"} | Set-CsUser -ExchangeArchivingPolicy ArchivingToExchange

<span data-ttu-id="422f0-192">Beachten Sie, dass Sie die lync Server-Verwaltungsshell (und Windows PowerShell) verwenden müssen, um den Wert der ExchangeArchivingPolicy-Eigenschaft zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="422f0-192">Note that you must use the Lync Server Management Shell (and Windows PowerShell) in order to configure value of the ExchangeArchivingPolicy property.</span></span> <span data-ttu-id="422f0-193">Diese Eigenschaft wird für Administratoren in der lync Server-Systemsteuerung nicht verfügbar gemacht.</span><span class="sxs-lookup"><span data-stu-id="422f0-193">This property is not exposed to administrators in the Lync Server Control Panel.</span></span>

<span data-ttu-id="422f0-194">Wenn Sie eine Liste aller Benutzer anzeigen möchten, denen eine bestimmte Archivierungsrichtlinie zugewiesen wurde, können Sie einen ähnlichen Befehl wie den folgenden verwenden. Der Befehl gibt den Active Directory-Anzeigenamen aller Benutzer zurück, für die die Eigenschaft „ExchangeArchivingPolicy“ auf „Uninitialized“ festgelegt ist:</span><span class="sxs-lookup"><span data-stu-id="422f0-194">If you would like to view a list of all the users who have been assigned a specific archiving policy then you can use a command similar to the following, which returns the Active Directory display name of all the users who have had the ExchangeArchivingPolicy property set to Uninitialized:</span></span>

    Get-CsUser | Where-Object {$_.ExchangeArchivingPolicy -eq "Uninitialized"} | Select-Object DisplayName

<span data-ttu-id="422f0-195">Entsprechend gibt dieser Befehl den Anzeigenamen aller Benutzer zurück, für die die Eigenschaft „ExchangeArchivingPolicy“ auf „UseLyncArchivingPolicy“ festgelegt ist:</span><span class="sxs-lookup"><span data-stu-id="422f0-195">Likewise, this command returns the display name of the users who have not have the ExchangeArchivingPolicy property set to UseLyncArchivingPolicy:</span></span>

    Get-CsUser | Where-Object {$_.ExchangeArchivingPolicy -ne "UseLyncArchivingPolicy"} | Select-Object DisplayName

</div>

</div>

<span> </span>

</div>

</div>

</div>

