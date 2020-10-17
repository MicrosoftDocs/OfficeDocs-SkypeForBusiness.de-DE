---
title: Konfigurieren der Dateiübertragung und der URL-Filterung für Chatnachrichten
description: Konfigurieren der Dateiübertragung und der URL-Filterung für Chatnachrichten.
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring file transfer and URL filtering for instant messaging (IM)
ms:assetid: 115a1a2c-599f-474c-a063-52f7144b5246
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520952(v=OCS.15)
ms:contentKeyID: 48183440
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 92f11c3f3bb924c1d92361c2635bfb37e1f03175
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48548351"
---
# <a name="configuring-file-transfer-and-url-filtering-for-instant-messaging-im-in-lync-server-2013"></a><span data-ttu-id="f2782-103">Konfigurieren der Dateiübertragung und der URL-Filterung für Chatnachrichten in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f2782-103">Configuring file transfer and URL filtering for instant messaging (IM) in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f2782-104">_**Letztes Änderungsstand des Themas:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="f2782-104">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="f2782-105">Mit dem intelligenten Sofortnachrichten-Filter Tool können Sie Ihre lync Server 2013-Bereitstellung vor der Verbreitung der häufigsten Virenarten mit minimaler Beeinträchtigung der Benutzerfreundlichkeit schützen.</span><span class="sxs-lookup"><span data-stu-id="f2782-105">The Intelligent IM Filter tool helps protect your Lync Server 2013 deployment against the spread of the most common forms of viruses with minimal degradation to the user experience.</span></span> <span data-ttu-id="f2782-106">Konfigurieren Sie mit dem intelligenten Sofortnachrichtenfilter Filter zum Blockieren unerwünschter oder potenziell schädlicher Sofortnachrichten von unbekannten Endpunkten außerhalb der Unternehmensfirewall.</span><span class="sxs-lookup"><span data-stu-id="f2782-106">Use Intelligent IM Filter to configure filters to block unsolicited or potentially harmful instant messages from unknown endpoints outside the corporate firewall.</span></span> <span data-ttu-id="f2782-107">Sie konfigurieren Filter, indem Sie die Kriterien angeben, die verwendet werden sollen, um zu bestimmen, was blockiert werden soll, beispielsweise Sofortnachrichten mit Hyperlinks mit bestimmten Präfixen und Dateien mit bestimmten Erweiterungen.</span><span class="sxs-lookup"><span data-stu-id="f2782-107">You configure filters by specifying the criteria to be used to determine what should be blocked, such as instant messages containing hyperlinks with specific prefixes and files with specific extensions.</span></span>

<span data-ttu-id="f2782-108">Der intelligente Chat Filter bietet Folgendes:</span><span class="sxs-lookup"><span data-stu-id="f2782-108">Intelligent IM Filter provides the following:</span></span>

  - <span data-ttu-id="f2782-109">Erweiterte URL-Filterung.</span><span class="sxs-lookup"><span data-stu-id="f2782-109">Enhanced URL filtering.</span></span>

  - <span data-ttu-id="f2782-110">Erweiterte Dateiübertragungsfilterung.</span><span class="sxs-lookup"><span data-stu-id="f2782-110">Enhanced file transfer filtering.</span></span>

<span data-ttu-id="f2782-111">Das Konfigurieren eines intelligenten Sofortnachrichtenfilters umfasst Folgendes:</span><span class="sxs-lookup"><span data-stu-id="f2782-111">Configuring Intelligent IM Filter includes the following:</span></span>

  - <span data-ttu-id="f2782-112">Konfigurieren der URL-Filterung</span><span class="sxs-lookup"><span data-stu-id="f2782-112">Configuring URL filtering.</span></span>

  - <span data-ttu-id="f2782-113">Konfigurieren der Dateiübertragungsfilterung.</span><span class="sxs-lookup"><span data-stu-id="f2782-113">Configuring file transfer filtering.</span></span>

<div>

## <a name="how-filtering-options-are-applied-to-instant-messages"></a><span data-ttu-id="f2782-114">Anwenden von Filteroptionen auf Chatnachrichten</span><span class="sxs-lookup"><span data-stu-id="f2782-114">How Filtering Options Are Applied to Instant Messages</span></span>

<span data-ttu-id="f2782-115">Vor dem Bereitstellen des intelligenten Chatnachrichten Filter-Tools müssen Sie verstehen, wie Filteroptionen angewendet werden, wenn Nachrichten von einem lync Server 2013 Server an einen anderen weitergeleitet werden.</span><span class="sxs-lookup"><span data-stu-id="f2782-115">Before you deploy the Intelligent IM Message Filter tool, you need to understand how filtering options are applied as messages are routed from one Lync Server 2013 server to another.</span></span> <span data-ttu-id="f2782-116">Die Art der Anwendung von Filteroptionen ist konsistent, unabhängig davon, ob die Server sich in einer einzigen Organisation oder in mehreren Organisationen befinden.</span><span class="sxs-lookup"><span data-stu-id="f2782-116">The way these filtering options are applied is consistent, regardless of whether the servers are located in a single organization or across organizational boundaries.</span></span> <span data-ttu-id="f2782-117">Diese Konsistenz gilt für die Art und Weise, in der die benutzerdefinierten Benachrichtigungs-und Warn Texte in Nachrichten eingefügt und über Server gesendet werden.</span><span class="sxs-lookup"><span data-stu-id="f2782-117">This consistency applies to the way that the customized notice and warning texts are inserted into messages and sent across servers.</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="f2782-118">Der Instant Messaging-Filter erhöht die Menge an CPU-Ressourcen, die zum Verarbeiten von URLs in einer Nachricht erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="f2782-118">The instant message filter increases the amount of CPU resources required to process URLs in a message.</span></span> <span data-ttu-id="f2782-119">Dieser Anstieg der CPU-Nachfrage wirkt sich auch auf die Leistung von lync Server aus.</span><span class="sxs-lookup"><span data-stu-id="f2782-119">This increase in CPU demand also affects the performance of Lync Server.</span></span>



</div>

<span data-ttu-id="f2782-120">Mithilfe der Seite **URL-Filter** in der **Chat-und Anwesenheits** Gruppe in lync Server-Systemsteuerung können Sie einige oder alle Hyperlinks blockieren oder eine Warnung konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="f2782-120">By using the **URL Filter** page in the **IM and Presence** group in Lync Server Control Panel, you can block some or all hyperlinks or configure a warning.</span></span> <span data-ttu-id="f2782-121">Die Warnung wird am Anfang einer Sofortnachricht eingefügt, die einen Hyperlink enthält, wenn Sie die Option **Hyperlink** -Präfix **senden Warnmeldung**auswählen.</span><span class="sxs-lookup"><span data-stu-id="f2782-121">The warning is inserted at the beginning of an instant message that contains a hyperlink when you choose the **Hyperlink prefix** option **Send warning message**.</span></span>

<span data-ttu-id="f2782-122">Wenn eine Sofortnachricht von einem Server auf einen anderen übertragen wird, gelten die folgenden allgemeinen Richtlinien:</span><span class="sxs-lookup"><span data-stu-id="f2782-122">When an instant message travels from one server to another, the following general guidelines apply:</span></span>

  - <span data-ttu-id="f2782-123">Wenn ein Server eine Sofortnachricht blockiert (da Sie das Kontrollkästchen **URLs mit Dateierweiterung blockieren** auf der Seite **URL-Filter** aktiviert haben oder wenn Sie die Option Hyperlinks für **Hyperlink-Präfix** **blockieren**ausgewählt haben), wird eine Fehlermeldung an den Client zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="f2782-123">If a server blocks an instant message (because you selected the **Block URLs with file extension** check box on the **URL Filter** page or because you chose the **Hyperlink prefix** option **Block hyperlinks**), an error message is returned to the client.</span></span> <span data-ttu-id="f2782-124">Nachfolgende Server erhalten diese Sofortnachricht nicht.</span><span class="sxs-lookup"><span data-stu-id="f2782-124">Subsequent servers do not receive this instant message.</span></span>

  - <span data-ttu-id="f2782-125">Wenn ein Server (Server1) eine Warnung zu einer Sofortnachricht hinzufügt, die einen aktiven Hyperlink enthält, kann ein folgender Server (Server2), der diese Sofortnachricht empfängt, nach wie vor eine andere Aktion basierend auf diesem in der Sofortnachricht vorhandenen aktiven Hyperlink ausführen und die Sofortnachricht blockieren oder eine Warnung hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="f2782-125">If a server (Server1) adds a warning to an instant message that contains an active hyperlink, a subsequent server (Server2) that receives this instant message can still take a different action based on this active hyperlink present in the instant message and block the instant message or add a warning.</span></span> <span data-ttu-id="f2782-126">Wenn Server2 nur zum Hinzufügen einer Warnung für diese URL konfiguriert ist, wird die zuvor von Server1 hinzugefügte Warnung entfernt, und die auf Server2 konfigurierte Warnung wird am Anfang der Sofortnachricht hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="f2782-126">If Server2 is configured only to add a warning for this URL, the earlier warning added by Server1 is removed, and the warning configured on Server2 is added to the beginning of the instant message.</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="f2782-127">Wenn Sie lync Server 2013 in einer gemischten Umgebung verwenden, ist Live Communications Server 2005 mit SP1 die minimale Version, die für die Verwendung der intelligenten Chat Filter Anwendung erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="f2782-127">If you are running Lync Server 2013 in a mixed environment, Live Communications Server 2005 with SP1 is the minimum version required to use the Intelligent IM Filter application.</span></span> <span data-ttu-id="f2782-128">Der intelligente Chat Filter wird auf Live Communications Server 2005 ohne SP1 nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="f2782-128">The Intelligent IM Filter is not supported on Live Communications Server 2005 without SP1.</span></span>



</div>

<div>

## <a name="url-filtering"></a><span data-ttu-id="f2782-129">URL-Filterung</span><span class="sxs-lookup"><span data-stu-id="f2782-129">URL Filtering</span></span>

<span data-ttu-id="f2782-130">URLs werden entsprechend Ihrem Hyperlink-Präfix gefiltert.</span><span class="sxs-lookup"><span data-stu-id="f2782-130">URLs are filtered according to their hyperlink prefix.</span></span> <span data-ttu-id="f2782-131">Die folgenden Beispiele sind gültige Präfixe:</span><span class="sxs-lookup"><span data-stu-id="f2782-131">The following examples are valid prefixes:</span></span>

  - <span data-ttu-id="f2782-132">www \* .</span><span class="sxs-lookup"><span data-stu-id="f2782-132">www\*.</span></span>

  - <span data-ttu-id="f2782-133">FTP.</span><span class="sxs-lookup"><span data-stu-id="f2782-133">ftp.</span></span>

  - <span data-ttu-id="f2782-134">http</span><span class="sxs-lookup"><span data-stu-id="f2782-134">http:</span></span>

<span data-ttu-id="f2782-135">Wenn Sie den Instant Messaging-Filter nicht so konfigurieren, dass eine URL-Filterung durchgeführt wird, werden alle in Chatnachrichten enthaltenen URLs ohne Änderung über den Server übergeben.</span><span class="sxs-lookup"><span data-stu-id="f2782-135">If you do not configure the instant message filter to perform any URL filtering, all URLs contained in instant messages are passed unmodified through the server.</span></span> <span data-ttu-id="f2782-136">Wenn Sie den Instant Messaging-Filter so konfigurieren, dass die URL-Filterung durchgeführt wird, werden URLs in Chatnachrichten entsprechend den Optionen gefiltert, die Sie im Dialogfeld **URL-Filter bearbeiten** oder **neuer URL** -Filter ausgewählt haben.</span><span class="sxs-lookup"><span data-stu-id="f2782-136">If you configure the instant message filter to perform URL filtering, URLs in instant messages are filtered according to the options that you select in the **Edit URL Filter** or **New URL Filter** dialog box.</span></span>

  - <span data-ttu-id="f2782-137">**URL-Filter aktivieren**     Mit dieser Option wird die URL-Filterung für die globale Bereitstellung oder für die von Ihnen ausgewählte Website aktiviert.</span><span class="sxs-lookup"><span data-stu-id="f2782-137">**Enable URL filter**   This option enables URL filtering for the global deployment or for the site that you select.</span></span>

  - <span data-ttu-id="f2782-138">**Blockieren von URLs mit Dateierweiterung**     Der Sofortnachrichtenfilter blockiert alle aktiven Intranet-oder Internet-URLs, die eine Datei mit einer im Dialogfeld **Dateifilter bearbeiten** unter **zu blockierenden Dateityperweiterungen** aufgeführten Dateinamenerweiterung enthalten.</span><span class="sxs-lookup"><span data-stu-id="f2782-138">**Block URLs with file extension**   The instant message filter blocks any active intranet or Internet URL that contains a file with an extension listed under **File type extensions to block** in the **Edit File Filter** dialog box.</span></span> <span data-ttu-id="f2782-139">Wenn eine URL blockiert wird, wird dem Absender eine Fehlermeldung angezeigt.</span><span class="sxs-lookup"><span data-stu-id="f2782-139">When a URL is blocked, an error message is displayed to the sender.</span></span> <span data-ttu-id="f2782-140">Wenn diese Option aktiviert ist, hat diese Option Vorrang vor allen anderen Filteroptionen für alle Dateierweiterungen, **die unter Dateityperweiterungen definiert sind, die blockiert werden sollen**.</span><span class="sxs-lookup"><span data-stu-id="f2782-140">When selected, this option takes precedence over all other filtering options for any file extensions defined under **File type extensions to block**.</span></span>
    
    <div>
    

    > [!IMPORTANT]
    > <span data-ttu-id="f2782-141">Das Filtern von Dateierweiterungen ist auf Standarddatei Namen limitiert.</span><span class="sxs-lookup"><span data-stu-id="f2782-141">Filtering of file extensions is limited to standard file names.</span></span> <span data-ttu-id="f2782-142">Das Filtern funktioniert möglicherweise nicht mit Dateierweiterungen, die in andere Namen eingebettet sind.</span><span class="sxs-lookup"><span data-stu-id="f2782-142">Filtering may not work with file extensions embedded in other names.</span></span>

    
    </div>

<span data-ttu-id="f2782-143">Wählen Sie eine der folgenden Optionen unter **Link Prefix**aus, um zu konfigurieren, wie Hyperlinks in Sofortnachrichtenunterhaltungen behandelt werden:</span><span class="sxs-lookup"><span data-stu-id="f2782-143">To configure how hyperlinks are handled in instant message conversations, select one of the following options under **Hyperlink prefix**:</span></span>

  - <span data-ttu-id="f2782-144">**Nicht filtern**     URLs in Nachrichten werden über den Server gesendet.</span><span class="sxs-lookup"><span data-stu-id="f2782-144">**Do not filter**   URLs in messages are sent through the server.</span></span> <span data-ttu-id="f2782-145">Wenn Sie diese Option auswählen, wird das Feld **Nachricht zulassen** angezeigt.</span><span class="sxs-lookup"><span data-stu-id="f2782-145">When you choose this option, the **Allow message** box appears.</span></span> <span data-ttu-id="f2782-146">Geben Sie im Feld **Nachricht zulassen** den Hinweis an, den Sie am Anfang jeder Sofortnachricht mit Hyperlinks einfügen möchten.</span><span class="sxs-lookup"><span data-stu-id="f2782-146">In the **Allow message** box, specify the notice that you want to insert at the beginning of each instant message containing hyperlinks.</span></span> <span data-ttu-id="f2782-147">Dieser Hinweis kann aus maximal 65535 Zeichen bestehen.</span><span class="sxs-lookup"><span data-stu-id="f2782-147">This notice can consist of no more than 65535 characters.</span></span>

  - <span data-ttu-id="f2782-148">**Hyperlinks blockieren**     Die Zustellung von Sofortnachrichten mit aktiven Hyperlinks wird durch lync Server blockiert, und dem Absender wird eine Fehlermeldung angezeigt.</span><span class="sxs-lookup"><span data-stu-id="f2782-148">**Block hyperlinks**   Delivery of instant messages containing active hyperlinks is blocked by Lync Server, and an error message is displayed to the sender.</span></span>

  - <span data-ttu-id="f2782-149">**Warnmeldung senden**     Lync Server erlaubt aktive Hyperlinks in Chatnachrichten, enthält jedoch eine Warnung.</span><span class="sxs-lookup"><span data-stu-id="f2782-149">**Send warning message**   Lync Server permits active hyperlinks in instant messages, but it includes a warning.</span></span> <span data-ttu-id="f2782-150">Wenn Sie diese Option auswählen, wird das **Warn Meldungs** Feld angezeigt.</span><span class="sxs-lookup"><span data-stu-id="f2782-150">When you choose this option, the **Warning message** box appears.</span></span> <span data-ttu-id="f2782-151">Im **Warn Meldungs** Feld müssen Sie die Warnung eingeben, die in Chatnachrichten enthalten sein soll, die gültige Hyperlinks enthalten.</span><span class="sxs-lookup"><span data-stu-id="f2782-151">In the **Warning message** box, you must type the warning that you want to include with instant messages containing valid hyperlinks.</span></span> <span data-ttu-id="f2782-152">Beispielsweise kann diese Warnung die potenziellen Gefahren für das Klicken auf einen unbekannten Link angeben oder sich auf die relevanten Richtlinien und Anforderungen Ihrer Organisation berufen.</span><span class="sxs-lookup"><span data-stu-id="f2782-152">For example, this warning might state the potential dangers of clicking an unknown link, or it might refer to your organization’s relevant policies and requirements.</span></span> <span data-ttu-id="f2782-153">Die Warnung darf nicht mehr als 65535 Zeichen enthalten.</span><span class="sxs-lookup"><span data-stu-id="f2782-153">The warning can be no more than 65535 characters.</span></span>

<span data-ttu-id="f2782-154">Wenn Sie **Hyperlinks blockieren** oder **Warnmeldung senden**auswählen, stehen die folgenden Optionen zur Verfügung:</span><span class="sxs-lookup"><span data-stu-id="f2782-154">If you select **Block hyperlinks** or **Send warning message**, the following options are available:</span></span>

  - <span data-ttu-id="f2782-155">**Ausschließen von Hyperlinks**     für lokales Intranet Der Sofortnachrichtenfilter blockiert nur Internet-URLs.</span><span class="sxs-lookup"><span data-stu-id="f2782-155">**Exclude local intranet hyperlinks**   The instant message filter blocks only Internet URLs.</span></span> <span data-ttu-id="f2782-156">URLs für Standorte in Ihrem Intranet werden unverändert über den Server übergeben.</span><span class="sxs-lookup"><span data-stu-id="f2782-156">URLs for locations within your intranet are passed unmodified through the server.</span></span> <span data-ttu-id="f2782-157">Die Intranet-URLs, die einzelne Server lync Server übergeben, hängen jedoch davon ab, welche Arten von lokalen Websites als Teil ihrer Intranetzone betrachtet werden.</span><span class="sxs-lookup"><span data-stu-id="f2782-157">However, the intranet URLs that individual servers running Lync Server pass depend on which types of local websites are considered part of their intranet zone.</span></span> <span data-ttu-id="f2782-158">Informationen zum Überprüfen der Intranet-Zoneneinstellungen eines Servers finden Sie unter "so konfigurieren Sie die Einstellungen für Intraneteinstellungen in Internet Explorer" unter [Ändern des Standard-URL-Filters in lync Server 2013](lync-server-2013-modify-the-default-url-filter.md).</span><span class="sxs-lookup"><span data-stu-id="f2782-158">To check a server’s intranet zone settings, see the “To configure your intranet settings in Internet Explorer” procedure in [Modify the default URL filter in Lync Server 2013](lync-server-2013-modify-the-default-url-filter.md).</span></span>

  - <span data-ttu-id="f2782-159">**Diese Verknüpfungs Präfixe Filtern**     Um auszuwählen, welche Präfixe Sie blockieren möchten, klicken Sie auf **auswählen**, und fügen Sie dann im Feld **Hyperlink-Präfix auswählen**die Präfixe zur Liste **Hyperlink-Präfixe** hinzu.</span><span class="sxs-lookup"><span data-stu-id="f2782-159">**Filter these hyperlink prefixes**   To choose which prefixes you want to block, click **Select**, and then, in **Select Hyperlink Prefix**, add the prefixes to the **Hyperlink prefixes** list.</span></span>
    
    <span data-ttu-id="f2782-160">Alle Präfixe mit Ausnahme von **href** müssen mit einem Punkt oder einem Doppelpunkt oder einem Sternchen, gefolgt von einem Punkt enden.</span><span class="sxs-lookup"><span data-stu-id="f2782-160">All prefixes except **href** must end with a period or a colon, or an asterisk followed by a period.</span></span> <span data-ttu-id="f2782-161">Gültige Präfixe können beliebige Zeichen im Satz gültiger URL-Zeichen enthalten, außer dem Sternchen ( \* ).</span><span class="sxs-lookup"><span data-stu-id="f2782-161">Valid prefixes can contain any characters in the set of valid URL characters except the asterisk (\*).</span></span> <span data-ttu-id="f2782-162">Die Gruppe gültiger URL-Zeichen lautet: \# \* +/0123456789 = @abcdefghijklmnopqrstuvwxyz ^ \_ \` abcdefghijklmnopqrstuvwxyz | ~</span><span class="sxs-lookup"><span data-stu-id="f2782-162">The set of valid URL characters is: \#\*+/0123456789=@ABCDEFGHIJKLMNOPQRSTUVWXYZ^\_\` abcdefghijklmnopqrstuvwxyz|~</span></span>

</div>

<div>

## <a name="file-transfer-filtering"></a><span data-ttu-id="f2782-163">Dateiübertragungsfilterung</span><span class="sxs-lookup"><span data-stu-id="f2782-163">File Transfer Filtering</span></span>

<span data-ttu-id="f2782-164">Filter Übertragungs Filterung wirkt sich sowohl auf Chatnachrichten als auch auf Konferenzen aus.</span><span class="sxs-lookup"><span data-stu-id="f2782-164">Filter transfer filtering affects both instant messages and conferences.</span></span> <span data-ttu-id="f2782-165">Bei Konferenzen wirken sich diese Einstellungen auf die handzettelfunktion in den Features Office Live Meeting 2007 Client-und Multimedia-Wiedergabe aus.</span><span class="sxs-lookup"><span data-stu-id="f2782-165">For conferences, these settings affect the handout feature in the Office Live Meeting 2007 client and multimedia playback features.</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="f2782-166">Lync Server bietet auch Optionen zum Festlegen von Dateiübertragungen.</span><span class="sxs-lookup"><span data-stu-id="f2782-166">Lync Server also offers file transfer setting options.</span></span> <span data-ttu-id="f2782-167">Diese serverseitige Option wird zusätzlich zu den clientseitigen Steuerelementen angeboten, die in lync Server verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="f2782-167">This server-side option is offered in addition to the client-side controls available in Lync Server.</span></span>



</div>

<span data-ttu-id="f2782-168">Sie können Dateiübertragungen während Sofortnachrichtenunterhaltungen filtern, wenn Sie das Handzettel Feature im Office Live Meeting 2007-Client verwenden, sowie für Multimedia-Wiedergabefunktionen für alle Dateitypen.</span><span class="sxs-lookup"><span data-stu-id="f2782-168">You can filter file transfers during instant message conversations, when you are using the handout feature in the Office Live Meeting 2007 client, and for multimedia playback features for all file types.</span></span> <span data-ttu-id="f2782-169">Sie können die folgenden Optionen festlegen, um Dateiübertragungen zu steuern:</span><span class="sxs-lookup"><span data-stu-id="f2782-169">You can set the following options to control file transfers:</span></span>

  - <span data-ttu-id="f2782-170">**Dateifilter aktivieren**     Mit dieser Option wird die Dateifilterung für die globale Bereitstellung oder für die von Ihnen ausgewählte Website aktiviert.</span><span class="sxs-lookup"><span data-stu-id="f2782-170">**Enable file filter**   This option enables file filtering for the global deployment or for the site that you select.</span></span>
    
    <span data-ttu-id="f2782-171">Wenn Sie den Dateifilter aktivieren, können Sie eine der folgenden Optionen bei der **Dateiübertragung**auswählen:</span><span class="sxs-lookup"><span data-stu-id="f2782-171">When you enable the file filter, you can choose one of the following options in **File transfer**:</span></span>
    
      - <span data-ttu-id="f2782-172">**Blockieren bestimmter Dateitypen**     Sie geben an, welche Dateiübertragungsanforderungen vom Server gefiltert werden, indem Sie eine Liste der zu blockierenden Dateierweiterungen angeben.</span><span class="sxs-lookup"><span data-stu-id="f2782-172">**Block specific file types**   You specify which file transfer requests are filtered by the server by specifying a list of file extensions to block.</span></span> <span data-ttu-id="f2782-173">Einträge in der Liste können alle Standardzeichen enthalten, jedoch nicht das Platzhalterzeichen ( \* ).</span><span class="sxs-lookup"><span data-stu-id="f2782-173">Entries in the list can contain all standard characters, but not the wildcard character (\*).</span></span> <span data-ttu-id="f2782-174">Im Office Live Meeting 2007-Client ist das Handzettel Feature aktiviert, aber jede Datei mit dieser Erweiterung kann nicht hochgeladen oder heruntergeladen werden.</span><span class="sxs-lookup"><span data-stu-id="f2782-174">In the Office Live Meeting 2007 client the handout feature is enabled, but any file with this extension cannot be uploaded or downloaded.</span></span> <span data-ttu-id="f2782-175">Wenn Sie das Kontrollkästchen **URLs mit Dateierweiterung blockieren** für die Einstellungen für einen URL-Filter aktivieren, der auf der Registerkarte **URL-Filter** aufgeführt ist, verwendet der URL-Filter diese Liste, um aktive Hyperlinks zu blockieren, die eine dieser Dateierweiterungen enthalten.</span><span class="sxs-lookup"><span data-stu-id="f2782-175">If you select the **Block URLs with file extension** check box on the settings for a URL filter listed on the **URL Filter** tab, the URL filter uses this same list to block active hyperlinks that contain any of these file extensions.</span></span> <span data-ttu-id="f2782-176">Um auszuwählen, welche Dateitypen Sie blockieren möchten, klicken Sie auf **auswählen**, und fügen Sie dann unter **Dateityp**die Dateierweiterungen der Liste **ausgewählte Dateitypen Erweiterungen** hinzu.</span><span class="sxs-lookup"><span data-stu-id="f2782-176">To choose which file types you want to block, click **Select**, and then, in **Select File Type**, add the file type extensions to the **Selected file type extensions** list.</span></span>
    
      - <span data-ttu-id="f2782-177">**Alle blockieren**     Der Server löscht alle Sofortnachrichten, die Dateiübertragungsanforderungen enthalten, und gibt eine Fehlermeldung an den Absender der Anforderung zurück.</span><span class="sxs-lookup"><span data-stu-id="f2782-177">**Block All**   The server drops all instant messages that contain file transfer requests and returns an error message to the sender of the request.</span></span> <span data-ttu-id="f2782-178">Das Handzettel Feature im Office Live Meeting 2007-Client ist deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="f2782-178">The handout feature in the Office Live Meeting 2007 client is disabled.</span></span>

<div>


> [!IMPORTANT]
> <span data-ttu-id="f2782-179">Das Filtern von Dateierweiterungen ist auf Standarddatei Namen limitiert.</span><span class="sxs-lookup"><span data-stu-id="f2782-179">Filtering of file extensions is limited to standard file names.</span></span> <span data-ttu-id="f2782-180">Das Filtern funktioniert möglicherweise nicht mit Dateierweiterungen, die in andere Namen eingebettet sind.</span><span class="sxs-lookup"><span data-stu-id="f2782-180">Filtering may not work with file extensions embedded in other names.</span></span>



</div>

</div>

</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="f2782-181">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="f2782-181">In This Section</span></span>

  - [<span data-ttu-id="f2782-182">Ändern des standardmäßigen dateiübertragungsfilters in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f2782-182">Modify the default file transfer filter in Lync Server 2013</span></span>](lync-server-2013-modify-the-default-file-transfer-filter.md)

  - [<span data-ttu-id="f2782-183">Erstellen eines neuen dateiübertragungsfilters in lync Server 2013 für einen bestimmten Standort</span><span class="sxs-lookup"><span data-stu-id="f2782-183">Create a new file transfer filter in Lync Server 2013 for a specific site</span></span>](lync-server-2013-create-a-new-file-transfer-filter-for-a-specific-site.md)

  - [<span data-ttu-id="f2782-184">Ändern des standardmäßigen URL-Filters in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f2782-184">Modify the default URL filter in Lync Server 2013</span></span>](lync-server-2013-modify-the-default-url-filter.md)

  - [<span data-ttu-id="f2782-185">Erstellen eines neuen URL-Filters in lync Server 2013 zur Behandlung von Hyperlinks in Chat Unterhaltungen</span><span class="sxs-lookup"><span data-stu-id="f2782-185">Create a new URL filter in Lync Server 2013 to handle hyperlinks in IM conversations</span></span>](lync-server-2013-create-a-new-url-filter-to-handle-hyperlinks-in-im-conversations.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="f2782-186">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f2782-186">See Also</span></span>


[<span data-ttu-id="f2782-187">Verwalten von Chat-und Anwesenheitseinstellungen in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f2782-187">Managing IM and presence settings in Lync Server 2013</span></span>](lync-server-2013-managing-im-and-presence-settings.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

