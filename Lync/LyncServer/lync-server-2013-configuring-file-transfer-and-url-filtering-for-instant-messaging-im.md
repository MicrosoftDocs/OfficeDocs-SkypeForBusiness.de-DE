---
title: Konfigurieren der Dateiübertragung und der URL-Filterung für Sofortnachrichten (im)
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
ms.openlocfilehash: e6c5a6053118b14b68c49a7fdaa6f444aca7ad23
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41729025"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-file-transfer-and-url-filtering-for-instant-messaging-im-in-lync-server-2013"></a><span data-ttu-id="514b3-102">Konfigurieren der Dateiübertragung und der URL-Filterung für Chatnachrichten in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="514b3-102">Configuring file transfer and URL filtering for instant messaging (IM) in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="514b3-103">_**Letztes Änderungsdatum des Themas:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="514b3-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="514b3-104">Das intelligente Chat-Filter Tool schützt Ihre lync Server 2013-Bereitstellung vor der Verbreitung der häufigsten Virenarten mit minimalem Abbau der Benutzerfreundlichkeit.</span><span class="sxs-lookup"><span data-stu-id="514b3-104">The Intelligent IM Filter tool helps protect your Lync Server 2013 deployment against the spread of the most common forms of viruses with minimal degradation to the user experience.</span></span> <span data-ttu-id="514b3-105">Verwenden Sie den intelligenten Chatfilter, um Filter so zu konfigurieren, dass unerwünschte oder potenziell schädliche Sofortnachrichten von unbekannten Endpunkten außerhalb der Unternehmensfirewall blockiert werden.</span><span class="sxs-lookup"><span data-stu-id="514b3-105">Use Intelligent IM Filter to configure filters to block unsolicited or potentially harmful instant messages from unknown endpoints outside the corporate firewall.</span></span> <span data-ttu-id="514b3-106">Sie konfigurieren Filter, indem Sie die Kriterien angeben, die verwendet werden sollen, um zu bestimmen, was blockiert werden soll, beispielsweise Sofortnachrichten, die Links mit bestimmten Präfixen und Dateien mit bestimmten Erweiterungen enthalten.</span><span class="sxs-lookup"><span data-stu-id="514b3-106">You configure filters by specifying the criteria to be used to determine what should be blocked, such as instant messages containing hyperlinks with specific prefixes and files with specific extensions.</span></span>

<span data-ttu-id="514b3-107">Der intelligente Chat Filter bietet die folgenden Optionen:</span><span class="sxs-lookup"><span data-stu-id="514b3-107">Intelligent IM Filter provides the following:</span></span>

  - <span data-ttu-id="514b3-108">Erweiterte URL-Filterung.</span><span class="sxs-lookup"><span data-stu-id="514b3-108">Enhanced URL filtering.</span></span>

  - <span data-ttu-id="514b3-109">Erweiterte Dateiübertragungsfilterung.</span><span class="sxs-lookup"><span data-stu-id="514b3-109">Enhanced file transfer filtering.</span></span>

<span data-ttu-id="514b3-110">Das Konfigurieren intelligenter Chat Filter umfasst Folgendes:</span><span class="sxs-lookup"><span data-stu-id="514b3-110">Configuring Intelligent IM Filter includes the following:</span></span>

  - <span data-ttu-id="514b3-111">Konfigurieren der URL-Filterung</span><span class="sxs-lookup"><span data-stu-id="514b3-111">Configuring URL filtering.</span></span>

  - <span data-ttu-id="514b3-112">Konfigurieren der Dateiübertragungsfilterung</span><span class="sxs-lookup"><span data-stu-id="514b3-112">Configuring file transfer filtering.</span></span>

<div>

## <a name="how-filtering-options-are-applied-to-instant-messages"></a><span data-ttu-id="514b3-113">Anwenden von Filteroptionen auf Sofortnachrichten</span><span class="sxs-lookup"><span data-stu-id="514b3-113">How Filtering Options Are Applied to Instant Messages</span></span>

<span data-ttu-id="514b3-114">Bevor Sie das intelligente Chatnachrichten Filter Tool bereitstellen, müssen Sie wissen, wie Filteroptionen angewendet werden, wenn Nachrichten von einem lync Server 2013-Server an einen anderen weitergeleitet werden.</span><span class="sxs-lookup"><span data-stu-id="514b3-114">Before you deploy the Intelligent IM Message Filter tool, you need to understand how filtering options are applied as messages are routed from one Lync Server 2013 server to another.</span></span> <span data-ttu-id="514b3-115">Die Art und Weise, wie diese Filteroptionen angewendet werden, ist konsistent, unabhängig davon, ob sich die Server in einer einzelnen Organisation oder unternehmensübergreifend befinden.</span><span class="sxs-lookup"><span data-stu-id="514b3-115">The way these filtering options are applied is consistent, regardless of whether the servers are located in a single organization or across organizational boundaries.</span></span> <span data-ttu-id="514b3-116">Diese Konsistenz bezieht sich auf die Art und Weise, wie angepasste Benachrichtigungs-und Warnungstexte in Nachrichten eingefügt und serverübergreifend gesendet werden.</span><span class="sxs-lookup"><span data-stu-id="514b3-116">This consistency applies to the way that the customized notice and warning texts are inserted into messages and sent across servers.</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="514b3-117">Der Sofortnachrichtenfilter erhöht die Anzahl der CPU-Ressourcen, die für die Verarbeitung von URLs in einer Nachricht erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="514b3-117">The instant message filter increases the amount of CPU resources required to process URLs in a message.</span></span> <span data-ttu-id="514b3-118">Dieser Anstieg der CPU-Nachfrage wirkt sich auch auf die Leistung von lync Server aus.</span><span class="sxs-lookup"><span data-stu-id="514b3-118">This increase in CPU demand also affects the performance of Lync Server.</span></span>



</div>

<span data-ttu-id="514b3-119">Mithilfe der Seite " **URL-Filter** " in der **Chat-und Anwesenheits** Gruppe in der lync Server-Systemsteuerung können Sie einige oder alle Links blockieren oder eine Warnung konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="514b3-119">By using the **URL Filter** page in the **IM and Presence** group in Lync Server Control Panel, you can block some or all hyperlinks or configure a warning.</span></span> <span data-ttu-id="514b3-120">Die Warnung wird am Anfang einer Sofortnachricht eingefügt, die einen Link enthält, wenn Sie die Option " **Hyperlink-Präfix** " auf " **Warnmeldung senden**" auswählen.</span><span class="sxs-lookup"><span data-stu-id="514b3-120">The warning is inserted at the beginning of an instant message that contains a hyperlink when you choose the **Hyperlink prefix** option **Send warning message**.</span></span>

<span data-ttu-id="514b3-121">Wenn eine Sofortnachricht von einem Server zu einem anderen reist, gelten die folgenden allgemeinen Richtlinien:</span><span class="sxs-lookup"><span data-stu-id="514b3-121">When an instant message travels from one server to another, the following general guidelines apply:</span></span>

  - <span data-ttu-id="514b3-122">Wenn ein Server eine Chatnachricht blockiert (weil Sie auf der Seite **URL-Filter** das Kontrollkästchen **URLs mit Dateierweiterung blockieren** aktiviert haben oder wenn Sie die Option **Hyperlink-Präfix** - **Links blockieren**ausgewählt haben), wird eine Fehlermeldung an den Client zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="514b3-122">If a server blocks an instant message (because you selected the **Block URLs with file extension** check box on the **URL Filter** page or because you chose the **Hyperlink prefix** option **Block hyperlinks**), an error message is returned to the client.</span></span> <span data-ttu-id="514b3-123">Nachfolgende Server empfangen diese Sofortnachricht nicht.</span><span class="sxs-lookup"><span data-stu-id="514b3-123">Subsequent servers do not receive this instant message.</span></span>

  - <span data-ttu-id="514b3-124">Wenn ein Server (Server1) eine Warnung zu einer Sofortnachricht hinzufügt, die einen aktiven Link enthält, kann ein nach folgender Server (Server2), der diese Sofortnachricht empfängt, weiterhin eine andere Aktion auf der Grundlage dieses aktiven Links in der Chatnachricht durchführen und die Sofortnachricht oder eine Warnung hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="514b3-124">If a server (Server1) adds a warning to an instant message that contains an active hyperlink, a subsequent server (Server2) that receives this instant message can still take a different action based on this active hyperlink present in the instant message and block the instant message or add a warning.</span></span> <span data-ttu-id="514b3-125">Wenn Server2 nur zum Hinzufügen einer Warnung für diese URL konfiguriert ist, wird die zuvor von Server1 hinzugefügte Warnung entfernt, und die auf Server2 konfigurierte Warnung wird am Anfang der Sofortnachricht hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="514b3-125">If Server2 is configured only to add a warning for this URL, the earlier warning added by Server1 is removed, and the warning configured on Server2 is added to the beginning of the instant message.</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="514b3-126">Wenn Sie lync Server 2013 in einer gemischten Umgebung ausführen, ist Live Communications Server 2005 mit SP1 die Mindestversion, die für die Verwendung der intelligenten Chat Filter-Anwendung erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="514b3-126">If you are running Lync Server 2013 in a mixed environment, Live Communications Server 2005 with SP1 is the minimum version required to use the Intelligent IM Filter application.</span></span> <span data-ttu-id="514b3-127">Der intelligente Chat-Filter wird auf Live Communications Server 2005 ohne SP1 nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="514b3-127">The Intelligent IM Filter is not supported on Live Communications Server 2005 without SP1.</span></span>



</div>

<div>

## <a name="url-filtering"></a><span data-ttu-id="514b3-128">URL-Filterung</span><span class="sxs-lookup"><span data-stu-id="514b3-128">URL Filtering</span></span>

<span data-ttu-id="514b3-129">URLs werden gemäß Ihrem Link Präfix gefiltert.</span><span class="sxs-lookup"><span data-stu-id="514b3-129">URLs are filtered according to their hyperlink prefix.</span></span> <span data-ttu-id="514b3-130">Die folgenden Beispiele sind gültige Präfixe:</span><span class="sxs-lookup"><span data-stu-id="514b3-130">The following examples are valid prefixes:</span></span>

  - <span data-ttu-id="514b3-131">www\*.</span><span class="sxs-lookup"><span data-stu-id="514b3-131">www\*.</span></span>

  - <span data-ttu-id="514b3-132">FTP.</span><span class="sxs-lookup"><span data-stu-id="514b3-132">ftp.</span></span>

  - <span data-ttu-id="514b3-133">http</span><span class="sxs-lookup"><span data-stu-id="514b3-133">http:</span></span>

<span data-ttu-id="514b3-134">Wenn Sie den Sofortnachrichtenfilter nicht so konfigurieren, dass eine URL-Filterung durchgeführt wird, werden alle URLs, die in Sofortnachrichten enthalten sind, über den Server unverändert übergeben.</span><span class="sxs-lookup"><span data-stu-id="514b3-134">If you do not configure the instant message filter to perform any URL filtering, all URLs contained in instant messages are passed unmodified through the server.</span></span> <span data-ttu-id="514b3-135">Wenn Sie den Sofortnachrichtenfilter so konfigurieren, dass URL-Filterung durchgeführt wird, werden URLs in Sofortnachrichten entsprechend den Optionen gefiltert, die Sie im Dialogfeld **URL-Filter bearbeiten** oder **neuer URL-Filter** ausgewählt haben.</span><span class="sxs-lookup"><span data-stu-id="514b3-135">If you configure the instant message filter to perform URL filtering, URLs in instant messages are filtered according to the options that you select in the **Edit URL Filter** or **New URL Filter** dialog box.</span></span>

  - <span data-ttu-id="514b3-136">**URL-Filter**   aktivieren diese Option aktiviert die URL-Filterung für die globale Bereitstellung oder für die von Ihnen ausgewählte Website.</span><span class="sxs-lookup"><span data-stu-id="514b3-136">**Enable URL filter**   This option enables URL filtering for the global deployment or for the site that you select.</span></span>

  - <span data-ttu-id="514b3-137">**Blockieren von URLs mit Dateierweiterung**   der Sofortnachrichtenfilter blockiert alle aktiven Intranet-oder Internet-URLs, die eine Datei mit einer Erweiterung enthalten, die im Dialogfeld **Dateifilter bearbeiten** unter **zu blockierende Dateityperweiterungen** aufgeführt ist.</span><span class="sxs-lookup"><span data-stu-id="514b3-137">**Block URLs with file extension**   The instant message filter blocks any active intranet or Internet URL that contains a file with an extension listed under **File type extensions to block** in the **Edit File Filter** dialog box.</span></span> <span data-ttu-id="514b3-138">Wenn eine URL blockiert ist, wird dem Absender eine Fehlermeldung angezeigt.</span><span class="sxs-lookup"><span data-stu-id="514b3-138">When a URL is blocked, an error message is displayed to the sender.</span></span> <span data-ttu-id="514b3-139">Wenn diese Option ausgewählt ist, hat diese Option Vorrang vor allen anderen Filteroptionen für alle Dateierweiterungen, **die unter zu blockierende Dateityperweiterungen**definiert sind.</span><span class="sxs-lookup"><span data-stu-id="514b3-139">When selected, this option takes precedence over all other filtering options for any file extensions defined under **File type extensions to block**.</span></span>
    
    <div>
    

    > [!IMPORTANT]
    > <span data-ttu-id="514b3-140">Das Filtern von Dateierweiterungen ist auf standardmäßige Dateinamen limitiert.</span><span class="sxs-lookup"><span data-stu-id="514b3-140">Filtering of file extensions is limited to standard file names.</span></span> <span data-ttu-id="514b3-141">Das Filtern funktioniert möglicherweise nicht mit Dateierweiterungen, die in anderen Namen eingebettet sind.</span><span class="sxs-lookup"><span data-stu-id="514b3-141">Filtering may not work with file extensions embedded in other names.</span></span>

    
    </div>

<span data-ttu-id="514b3-142">Wenn Sie konfigurieren möchten, wie Hyperlinks in Sofortnachrichtenunterhaltungen gehandhabt werden, wählen Sie eine der folgenden Optionen unter **Link-Präfix**aus:</span><span class="sxs-lookup"><span data-stu-id="514b3-142">To configure how hyperlinks are handled in instant message conversations, select one of the following options under **Hyperlink prefix**:</span></span>

  - <span data-ttu-id="514b3-143">**Sie können keine**   URLs in Nachrichten filtern, die über den Server gesendet werden.</span><span class="sxs-lookup"><span data-stu-id="514b3-143">**Do not filter**   URLs in messages are sent through the server.</span></span> <span data-ttu-id="514b3-144">Wenn Sie diese Option auswählen, wird das Feld **Nachricht zulassen** angezeigt.</span><span class="sxs-lookup"><span data-stu-id="514b3-144">When you choose this option, the **Allow message** box appears.</span></span> <span data-ttu-id="514b3-145">Geben Sie im Feld **Nachricht zulassen** den Hinweis an, den Sie am Anfang jeder Sofortnachricht mit Links einfügen möchten.</span><span class="sxs-lookup"><span data-stu-id="514b3-145">In the **Allow message** box, specify the notice that you want to insert at the beginning of each instant message containing hyperlinks.</span></span> <span data-ttu-id="514b3-146">Dieser Hinweis kann aus maximal 65535 Zeichen bestehen.</span><span class="sxs-lookup"><span data-stu-id="514b3-146">This notice can consist of no more than 65535 characters.</span></span>

  - <span data-ttu-id="514b3-147">**Blockieren von Links**   die Zustellung von Sofortnachrichten mit aktiven Links wird von lync Server blockiert, und dem Absender wird eine Fehlermeldung angezeigt.</span><span class="sxs-lookup"><span data-stu-id="514b3-147">**Block hyperlinks**   Delivery of instant messages containing active hyperlinks is blocked by Lync Server, and an error message is displayed to the sender.</span></span>

  - <span data-ttu-id="514b3-148">**Warnungsnachricht**   senden lync Server erlaubt aktive Links in Sofortnachrichten, enthält aber eine Warnung.</span><span class="sxs-lookup"><span data-stu-id="514b3-148">**Send warning message**   Lync Server permits active hyperlinks in instant messages, but it includes a warning.</span></span> <span data-ttu-id="514b3-149">Wenn Sie diese Option auswählen, wird das Dialogfeld **Warnmeldung** angezeigt.</span><span class="sxs-lookup"><span data-stu-id="514b3-149">When you choose this option, the **Warning message** box appears.</span></span> <span data-ttu-id="514b3-150">Im Feld **Warnung** müssen Sie die Warnung eingeben, die Sie in Sofortnachrichten mit gültigen Hyperlinks einbeziehen möchten.</span><span class="sxs-lookup"><span data-stu-id="514b3-150">In the **Warning message** box, you must type the warning that you want to include with instant messages containing valid hyperlinks.</span></span> <span data-ttu-id="514b3-151">Mit dieser Warnung können Sie beispielsweise die möglichen Gefahren für das Klicken auf einen unbekannten Link angeben, oder es kann auf die relevanten Richtlinien und Anforderungen Ihrer Organisation verweisen.</span><span class="sxs-lookup"><span data-stu-id="514b3-151">For example, this warning might state the potential dangers of clicking an unknown link, or it might refer to your organization’s relevant policies and requirements.</span></span> <span data-ttu-id="514b3-152">Die Warnung darf maximal 65535 Zeichen lang sein.</span><span class="sxs-lookup"><span data-stu-id="514b3-152">The warning can be no more than 65535 characters.</span></span>

<span data-ttu-id="514b3-153">Wenn Sie **Links blockieren** oder **Warnmeldung senden**auswählen, stehen die folgenden Optionen zur Verfügung:</span><span class="sxs-lookup"><span data-stu-id="514b3-153">If you select **Block hyperlinks** or **Send warning message**, the following options are available:</span></span>

  - <span data-ttu-id="514b3-154">**Lokale Intranet-Links**   ausschließen der Sofortnachrichtenfilter blockiert nur Internet-URLs.</span><span class="sxs-lookup"><span data-stu-id="514b3-154">**Exclude local intranet hyperlinks**   The instant message filter blocks only Internet URLs.</span></span> <span data-ttu-id="514b3-155">URLs für Standorte innerhalb Ihres Intranets werden ungeändert über den Server weitergeleitet.</span><span class="sxs-lookup"><span data-stu-id="514b3-155">URLs for locations within your intranet are passed unmodified through the server.</span></span> <span data-ttu-id="514b3-156">Die Intranet-URLs, die von einzelnen Servern mit lync Server übertragen werden, hängen jedoch davon ab, welche Typen von lokalen Websites als Teil ihrer Intranetzone angesehen werden.</span><span class="sxs-lookup"><span data-stu-id="514b3-156">However, the intranet URLs that individual servers running Lync Server pass depend on which types of local websites are considered part of their intranet zone.</span></span> <span data-ttu-id="514b3-157">Informationen zum Überprüfen der Intranet-Zoneneinstellungen eines Servers finden Sie unter [Ändern des Standard-URL-Filters in lync Server 2013](lync-server-2013-modify-the-default-url-filter.md)unter "so konfigurieren Sie Ihre Intraneteinstellungen in Internet Explorer".</span><span class="sxs-lookup"><span data-stu-id="514b3-157">To check a server’s intranet zone settings, see the “To configure your intranet settings in Internet Explorer” procedure in [Modify the default URL filter in Lync Server 2013](lync-server-2013-modify-the-default-url-filter.md).</span></span>

  - <span data-ttu-id="514b3-158">**Filtern Sie diese Link Präfixe**   , um auszuwählen, welche Präfixe blockiert werden sollen, klicken Sie auf **auswählen**, und fügen Sie dann im Feld **Link Präfix auswählen**die Präfixe der Liste **Hyperlink-Präfixe** hinzu.</span><span class="sxs-lookup"><span data-stu-id="514b3-158">**Filter these hyperlink prefixes**   To choose which prefixes you want to block, click **Select**, and then, in **Select Hyperlink Prefix**, add the prefixes to the **Hyperlink prefixes** list.</span></span>
    
    <span data-ttu-id="514b3-159">Alle Präfixe mit Ausnahme von **href** müssen mit einem Punkt oder einem Doppelpunkt oder einem Sternchen, gefolgt von einem Punkt, enden.</span><span class="sxs-lookup"><span data-stu-id="514b3-159">All prefixes except **href** must end with a period or a colon, or an asterisk followed by a period.</span></span> <span data-ttu-id="514b3-160">Gültige Präfixe können alle Zeichen in der Gruppe gültiger URL-Zeichen mit Ausnahme des Sternchens\*() enthalten.</span><span class="sxs-lookup"><span data-stu-id="514b3-160">Valid prefixes can contain any characters in the set of valid URL characters except the asterisk (\*).</span></span> <span data-ttu-id="514b3-161">Der Satz gültiger URL-Zeichen lautet: \# \*+/0123456789 = @abcdefghijklmnopqrstuvwxyz ^\_ \` abcdefghijklmnopqrstuvwxyz | ~</span><span class="sxs-lookup"><span data-stu-id="514b3-161">The set of valid URL characters is: \#\*+/0123456789=@ABCDEFGHIJKLMNOPQRSTUVWXYZ^\_\` abcdefghijklmnopqrstuvwxyz|~</span></span>

</div>

<div>

## <a name="file-transfer-filtering"></a><span data-ttu-id="514b3-162">Dateiübertragungsfilterung</span><span class="sxs-lookup"><span data-stu-id="514b3-162">File Transfer Filtering</span></span>

<span data-ttu-id="514b3-163">Filter Übertragungsfilter wirken sich sowohl auf Sofortnachrichten als auch auf Konferenzen aus.</span><span class="sxs-lookup"><span data-stu-id="514b3-163">Filter transfer filtering affects both instant messages and conferences.</span></span> <span data-ttu-id="514b3-164">Bei Konferenzen wirken sich diese Einstellungen auf das Handzettel Feature in den Office Live Meeting 2007-Client-und Multimedia-Wiedergabe Features aus.</span><span class="sxs-lookup"><span data-stu-id="514b3-164">For conferences, these settings affect the handout feature in the Office Live Meeting 2007 client and multimedia playback features.</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="514b3-165">Lync Server bietet außerdem Einstellungen für die Dateiübertragung.</span><span class="sxs-lookup"><span data-stu-id="514b3-165">Lync Server also offers file transfer setting options.</span></span> <span data-ttu-id="514b3-166">Diese serverseitige Option wird zusätzlich zu den in lync Server verfügbaren clientseitigen Steuerelementen angeboten.</span><span class="sxs-lookup"><span data-stu-id="514b3-166">This server-side option is offered in addition to the client-side controls available in Lync Server.</span></span>



</div>

<span data-ttu-id="514b3-167">Sie können Dateiübertragungen während Sofortnachrichtenunterhaltungen filtern, wenn Sie die handzettelfunktion im Office Live Meeting 2007-Client verwenden, und für Multimedia-Wiedergabe Features für alle Dateitypen.</span><span class="sxs-lookup"><span data-stu-id="514b3-167">You can filter file transfers during instant message conversations, when you are using the handout feature in the Office Live Meeting 2007 client, and for multimedia playback features for all file types.</span></span> <span data-ttu-id="514b3-168">Sie können die folgenden Optionen festlegen, um Dateiübertragungen zu steuern:</span><span class="sxs-lookup"><span data-stu-id="514b3-168">You can set the following options to control file transfers:</span></span>

  - <span data-ttu-id="514b3-169">**Dateifilter**   aktivieren mit dieser Option wird die Dateifilterung für die globale Bereitstellung oder für die von Ihnen ausgewählte Website aktiviert.</span><span class="sxs-lookup"><span data-stu-id="514b3-169">**Enable file filter**   This option enables file filtering for the global deployment or for the site that you select.</span></span>
    
    <span data-ttu-id="514b3-170">Wenn Sie den Dateifilter aktivieren, können Sie eine der folgenden Optionen in **Dateiübertragung**auswählen:</span><span class="sxs-lookup"><span data-stu-id="514b3-170">When you enable the file filter, you can choose one of the following options in **File transfer**:</span></span>
    
      - <span data-ttu-id="514b3-171">**Blockieren bestimmter Dateitypen**   Sie geben an, welche Dateiübertragungsanforderungen vom Server gefiltert werden sollen, indem Sie eine Liste der zu blockierenden Dateierweiterungen angeben.</span><span class="sxs-lookup"><span data-stu-id="514b3-171">**Block specific file types**   You specify which file transfer requests are filtered by the server by specifying a list of file extensions to block.</span></span> <span data-ttu-id="514b3-172">Einträge in der Liste können alle Standardzeichen, aber nicht das Platzhalterzeichen (\*) enthalten.</span><span class="sxs-lookup"><span data-stu-id="514b3-172">Entries in the list can contain all standard characters, but not the wildcard character (\*).</span></span> <span data-ttu-id="514b3-173">Im Office Live Meeting 2007-Client ist die handzettelfunktion aktiviert, aber jede Datei mit dieser Erweiterung kann nicht hochgeladen oder heruntergeladen werden.</span><span class="sxs-lookup"><span data-stu-id="514b3-173">In the Office Live Meeting 2007 client the handout feature is enabled, but any file with this extension cannot be uploaded or downloaded.</span></span> <span data-ttu-id="514b3-174">Wenn Sie das Kontrollkästchen **URLs mit Dateierweiterung blockieren** in den Einstellungen für einen URL-Filter auswählen, der auf der Registerkarte **URL-Filter** aufgelistet ist, verwendet der URL-Filter dieselbe Liste, um aktive Hyperlinks zu blockieren, die eine dieser Dateierweiterungen enthalten.</span><span class="sxs-lookup"><span data-stu-id="514b3-174">If you select the **Block URLs with file extension** check box on the settings for a URL filter listed on the **URL Filter** tab, the URL filter uses this same list to block active hyperlinks that contain any of these file extensions.</span></span> <span data-ttu-id="514b3-175">Wenn Sie auswählen möchten, welche Dateitypen blockiert werden sollen, klicken Sie auf **auswählen**, und fügen Sie dann im Feld **Dateityp**die Dateierweiterungen zur Liste **ausgewählte Dateityperweiterungen** hinzu.</span><span class="sxs-lookup"><span data-stu-id="514b3-175">To choose which file types you want to block, click **Select**, and then, in **Select File Type**, add the file type extensions to the **Selected file type extensions** list.</span></span>
    
      - <span data-ttu-id="514b3-176">**Blockieren der gesamte**   Server löscht alle Sofortnachrichten, die Dateiübertragungsanforderungen enthalten, und gibt eine Fehlermeldung an den Absender der Anforderung zurück.</span><span class="sxs-lookup"><span data-stu-id="514b3-176">**Block All**   The server drops all instant messages that contain file transfer requests and returns an error message to the sender of the request.</span></span> <span data-ttu-id="514b3-177">Das Handzettel Feature im Office Live Meeting 2007-Client ist deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="514b3-177">The handout feature in the Office Live Meeting 2007 client is disabled.</span></span>

<div>


> [!IMPORTANT]
> <span data-ttu-id="514b3-178">Das Filtern von Dateierweiterungen ist auf standardmäßige Dateinamen limitiert.</span><span class="sxs-lookup"><span data-stu-id="514b3-178">Filtering of file extensions is limited to standard file names.</span></span> <span data-ttu-id="514b3-179">Das Filtern funktioniert möglicherweise nicht mit Dateierweiterungen, die in anderen Namen eingebettet sind.</span><span class="sxs-lookup"><span data-stu-id="514b3-179">Filtering may not work with file extensions embedded in other names.</span></span>



</div>

</div>

</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="514b3-180">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="514b3-180">In This Section</span></span>

  - [<span data-ttu-id="514b3-181">Ändern des standardmäßigen dateiübertragungsfilters in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="514b3-181">Modify the default file transfer filter in Lync Server 2013</span></span>](lync-server-2013-modify-the-default-file-transfer-filter.md)

  - [<span data-ttu-id="514b3-182">Erstellen eines neuen dateiübertragungsfilters in lync Server 2013 für eine bestimmte Website</span><span class="sxs-lookup"><span data-stu-id="514b3-182">Create a new file transfer filter in Lync Server 2013 for a specific site</span></span>](lync-server-2013-create-a-new-file-transfer-filter-for-a-specific-site.md)

  - [<span data-ttu-id="514b3-183">Ändern des Standard-URL-Filters in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="514b3-183">Modify the default URL filter in Lync Server 2013</span></span>](lync-server-2013-modify-the-default-url-filter.md)

  - [<span data-ttu-id="514b3-184">Erstellen eines neuen URL-Filters in lync Server 2013 zur Behandlung von Hyperlinks in Chat Unterhaltungen</span><span class="sxs-lookup"><span data-stu-id="514b3-184">Create a new URL filter in Lync Server 2013 to handle hyperlinks in IM conversations</span></span>](lync-server-2013-create-a-new-url-filter-to-handle-hyperlinks-in-im-conversations.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="514b3-185">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="514b3-185">See Also</span></span>


[<span data-ttu-id="514b3-186">Verwalten von Einstellungen für Chat und Anwesenheit in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="514b3-186">Managing IM and presence settings in Lync Server 2013</span></span>](lync-server-2013-managing-im-and-presence-settings.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

