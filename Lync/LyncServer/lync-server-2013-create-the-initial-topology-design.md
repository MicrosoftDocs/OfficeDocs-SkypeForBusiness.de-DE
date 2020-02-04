---
title: 'Lync Server 2013: Erstellen des anfänglichen Topologie-Designs'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create the initial design
ms:assetid: f3131153-de14-41be-b1e6-7d4bb0191af1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615047(v=OCS.15)
ms:contentKeyID: 51541530
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7fc8d3e731c2772b275dd861c41b8c10f2127a2a
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41756959"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-the-initial-topology-design-for-lync-server-2013"></a><span data-ttu-id="1f4d5-102">Erstellen des anfänglichen Topologie-Designs für lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1f4d5-102">Create the initial topology design for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1f4d5-103">_**Letztes Änderungsdatum des Themas:** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="1f4d5-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="1f4d5-104">Nachdem Sie die Installation von lync Server 2013, Planungstool, abgeschlossen haben, können Sie das Planungstool starten und mit dem Entwerfen der vorgeschlagenen lync Server 2013-Infrastruktur beginnen.</span><span class="sxs-lookup"><span data-stu-id="1f4d5-104">After you have finished installing the Lync Server 2013, Planning Tool, you are ready to start the Planning Tool and begin designing the proposed Lync Server 2013 infrastructure.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="1f4d5-105">Das Planungstool ist ein Assistenten gesteuertes Tool mit detaillierten Leitfäden, mit deren Hilfe Sie Ihre Entscheidungsfindung beim Entwerfen Ihrer Websites und Topologie unterrichten können.</span><span class="sxs-lookup"><span data-stu-id="1f4d5-105">The Planning Tool is a wizard-driven tool with detailed guides to inform your decision-making process in designing your sites and topology.</span></span> <span data-ttu-id="1f4d5-106">Dieses Thema ist nicht als umfassender Leitfaden zu verstehen, sondern dient lediglich dazu, Ihnen bei der Verwendung des Planungstools in ihren Entwurfs Sitzungen zu helfen.</span><span class="sxs-lookup"><span data-stu-id="1f4d5-106">This topic is intended not as an exhaustive guide, but simply to help get you started using the Planning Tool in your design sessions.</span></span>



</div>

<div>

## <a name="to-get-started-using-the-planning-tool-and-create-the-initial-design"></a><span data-ttu-id="1f4d5-107">So beginnen Sie mit der Verwendung des Planungstools und Erstellen des anfänglichen Entwurfs</span><span class="sxs-lookup"><span data-stu-id="1f4d5-107">To get started using the Planning Tool and create the initial design</span></span>

1.  <span data-ttu-id="1f4d5-108">Starten Sie lync Server 2013, Planungstool: Klicken Sie auf **Start**, klicken Sie auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **Planungstool**.</span><span class="sxs-lookup"><span data-stu-id="1f4d5-108">Start the Lync Server 2013, Planning Tool: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Planning Tool**.</span></span>

2.  <span data-ttu-id="1f4d5-109">Nachdem das Planungstool gestartet wurde, wird die Seite **Willkommen bei Planning Tool für Microsoft lync Server 2013** angezeigt.</span><span class="sxs-lookup"><span data-stu-id="1f4d5-109">After the Planning Tool has started, the **Welcome to the Planning Tool for Microsoft Lync Server 2013** page appears.</span></span> <span data-ttu-id="1f4d5-110">Wählen Sie eine der folgenden Optionen, um zu beginnen:</span><span class="sxs-lookup"><span data-stu-id="1f4d5-110">Choose one of the following options to begin your design:</span></span>
    
      - <span data-ttu-id="1f4d5-111">**Option 1: Erste Schritte**   beim Klicken auf " **Erste Schritte** " finden Sie eine bestimmte Reihe von Interview Fragen mit relevanten Auswahlmöglichkeiten, um die Kriterien zu definieren.</span><span class="sxs-lookup"><span data-stu-id="1f4d5-111">**Option 1: Get Started**   Clicking **Get Started** provides a specific series of interview questions with relevant selections to define the criteria.</span></span> <span data-ttu-id="1f4d5-112">Fahren Sie nach Beantwortung der anfänglichen Fragen in **Erste Schritte** mit dem Abschnitt **Standorte entwerfen** fort, um die Architektur Ihres Standorts zu definieren.</span><span class="sxs-lookup"><span data-stu-id="1f4d5-112">After you have finished the initial **Get Started** interview section, you proceed into **Design Sites** to define your site architecture.</span></span> <span data-ttu-id="1f4d5-113">Fahren Sie mit Schritt 3 fort, um diese Option abzuschließen.</span><span class="sxs-lookup"><span data-stu-id="1f4d5-113">To complete this option, proceed to step 3.</span></span>
    
      - <span data-ttu-id="1f4d5-114">**Option 2: Design Websites**   Wenn Sie auf der Willkommensseite auf **Design Websites** klicken, werden die im Abschnitt **Erste Schritte** vorgestellten Fragen im Interview umgangen.</span><span class="sxs-lookup"><span data-stu-id="1f4d5-114">**Option 2: Design Sites**   Clicking **Design Sites** at the Welcome page bypasses the interview questions presented in the **Get Started** section.</span></span> <span data-ttu-id="1f4d5-115">Die Informationen, die anhand der Fragen im Abschnitt **Erste Schritte** erfasst worden wären, werden bei Auswahl dieser Option auf Standardwerte gesetzt.</span><span class="sxs-lookup"><span data-stu-id="1f4d5-115">The information that would have been gathered by responding to the interview questions in **Get Started** section is set to default values with this option.</span></span> <span data-ttu-id="1f4d5-116">Durch Klicken auf **Standorte entwerfen** können erfahrene Nutzer, die für den Entwurf verantwortlich sind, die anfänglichen Fragen umgehen und die Standardwerte nach Bedarf auf der Startseite für den Abschnitt **Zentrale Standorte** ändern.</span><span class="sxs-lookup"><span data-stu-id="1f4d5-116">By clicking **Design Sites**, the experienced designer can bypass the initial interview and change the default values, as needed, on the **Central Sites** start page.</span></span> <span data-ttu-id="1f4d5-117">Überspringen Sie die Schritte 3–5, und beginnen Sie mit Schritt 6, um diese Option abzuschließen.</span><span class="sxs-lookup"><span data-stu-id="1f4d5-117">To complete this option, skip over steps 3-5 and start at step 6.</span></span>
    
      - <span data-ttu-id="1f4d5-118">**Option 3: Anzeigen der gespeicherten Topologie**   Wenn Sie bereits eine Topologie durch vorherige Verwendung des Planungstools abgeschlossen und gespeichert haben, können Sie die meisten dieser Schritte überspringen und zunächst die Topologie öffnen und anzeigen.</span><span class="sxs-lookup"><span data-stu-id="1f4d5-118">**Option 3: Display Your Saved Topology**   If you have already completed and saved a topology through previous use of the Planning Tool, you can skip over most of these steps and start by opening and displaying the topology.</span></span> <span data-ttu-id="1f4d5-119">Sie können die Topologie ändern, aktualisieren, erneut speichern und anschließend nach Microsoft Excel oder Microsoft Visio exportieren.</span><span class="sxs-lookup"><span data-stu-id="1f4d5-119">You can also make changes and updates to the topology, resave it, and then export it to Microsoft Excel or Microsoft Visio.</span></span> <span data-ttu-id="1f4d5-120">Überspringen Sie die Schritte 3–12 und beginnen Sie mit Schritt 13, um diese Option abzuschließen.</span><span class="sxs-lookup"><span data-stu-id="1f4d5-120">To complete this option, skip over steps 3-12 and start at step 13.</span></span>

3.  <span data-ttu-id="1f4d5-121">Klicken Sie auf **Erste Schritte** , um mit dem Entwerfen Ihrer lync Server 2013-Topologie zu beginnen.</span><span class="sxs-lookup"><span data-stu-id="1f4d5-121">Click **Get Started** to begin designing your Lync Server 2013 topology.</span></span>

4.  <span data-ttu-id="1f4d5-p106">Beantworten Sie die Fragen in jedem Abschnitt, indem Sie die geeigneten Kriterien für Ihren Entwurf auswählen, und klicken Sie anschließend auf **Weiter**, um mit der nächsten Seite des Assistenten fortzufahren. Klicken Sie auf **Zurück**, um Änderungen auf vorherigen Seiten vorzunehmen.</span><span class="sxs-lookup"><span data-stu-id="1f4d5-p106">Answer each section by selecting the appropriate criteria for your design, and then click **Next** to proceed to the next Wizard page. Click **Back** to make changes on previous pages.</span></span>
    
    <div>
    

    > [!TIP]  
    > <span data-ttu-id="1f4d5-124">Jede Seite bietet eine Beschreibung der Auswahlkriterien sowie Empfehlungen basierend auf bevorzugten Vorgehensweisen und der Kapazitätsplanung.</span><span class="sxs-lookup"><span data-stu-id="1f4d5-124">Each page has a description of the selection criteria, and recommendations based on preferred practices and capacity planning.</span></span> <span data-ttu-id="1f4d5-125">Wenn Sie weitere Informationen benötigen <STRONG>, klicken Sie auf Weitere Informationen</STRONG> , um detaillierte Informationen aus der lync Server 2013-Planungsdokumentation auf der Microsoft TechNet-Website zu lesen.</span><span class="sxs-lookup"><span data-stu-id="1f4d5-125">If you require additional details, click <STRONG>Learn more</STRONG> to read detailed information from the Lync Server 2013 Planning documentation on the Microsoft TechNet website.</span></span> <span data-ttu-id="1f4d5-126">Für den Zugriff auf die Microsoft TechNet-Website ist eine Internetverbindung erforderlich.</span><span class="sxs-lookup"><span data-stu-id="1f4d5-126">You must have Internet connectivity to access the Microsoft TechNet website.</span></span>

    
    </div>

5.  <span data-ttu-id="1f4d5-127">Wählen Sie die geeigneten Optionen für Ihren Entwurf.</span><span class="sxs-lookup"><span data-stu-id="1f4d5-127">Select the appropriate options for your design.</span></span> <span data-ttu-id="1f4d5-128">Nach der Definition der anfänglichen Kriterien werden Sie darüber informiert, dass die Funktionsübersicht vollständig ist.</span><span class="sxs-lookup"><span data-stu-id="1f4d5-128">After the initial criteria are defined, a page will confirm that your Features Overview is complete.</span></span>

6.  <span data-ttu-id="1f4d5-129">Klicken Sie auf **Websites entwerfen** , um Ihre zentrale Website zu definieren.</span><span class="sxs-lookup"><span data-stu-id="1f4d5-129">Click **Design Sites** to define your central site.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="1f4d5-130">Jede lync Server 2013-Topologie verfügt über mindestens einen zentralen Standort.</span><span class="sxs-lookup"><span data-stu-id="1f4d5-130">Each Lync Server 2013 topology will have at least one central site.</span></span> <span data-ttu-id="1f4d5-131">Ihr Entwurf kann eine einzige zentrale Website, einen zentralen Standort mit einer Reihe von Zweigstellen, eine Reihe von zentralen Standorten oder eine Reihe zentraler Standorte mit Verzweigungs Websites aufweisen, die jedem zentralen Standort zugeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="1f4d5-131">Your design may have a single central site, a central site with a number of branch sites, a number of central sites, or a number of central sites with branch sites associated with each central site.</span></span>

    
    </div>

7.  <span data-ttu-id="1f4d5-132">Geben Sie unter **Websitename**den Namen ein, der diese zentrale Website kennzeichnet.</span><span class="sxs-lookup"><span data-stu-id="1f4d5-132">In **Site Name**, type the name that will identify this central site.</span></span>

8.  <span data-ttu-id="1f4d5-133">Geben Sie in "Website-vernetzte **Benutzer**" die erwartete Anzahl von lokalen gleichzeitigen Benutzern ein, die an diesem zentralen Standort verwaltet werden sollen.</span><span class="sxs-lookup"><span data-stu-id="1f4d5-133">In **Site Homed Users**, type the expected number of on-premises concurrent users who will be homed in this central site.</span></span>

9.  <span data-ttu-id="1f4d5-134">Geben Sie in Cloud-vernetzten **Benutzern**die erwartete Anzahl von gleichzeitigen Online Benutzern ein, die in diesem zentralen Standort verwaltet werden sollen.</span><span class="sxs-lookup"><span data-stu-id="1f4d5-134">In **Cloud Homed Users**, type the expected number of online concurrent users who will be homed in this central site.</span></span>

10. <span data-ttu-id="1f4d5-135">Ändern Sie nach Bedarf die Auswahl für Onlinezusammenarbeit, Benutzer, VoIP, zusätzliche Bereitstellungsoptionen oder Serveranwendungen.</span><span class="sxs-lookup"><span data-stu-id="1f4d5-135">Modify the selections for Online Collaboration, Users, Voice, Additional Deployment Options, or Server Applications, as needed.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="1f4d5-136">Zu diesem Entwurfszeitpunkt können Sie Optionen für Ihre Bereitstellung nur auswählen oder deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="1f4d5-136">At this point in the design, you can only select or clear options for your deployment.</span></span> <span data-ttu-id="1f4d5-137">Sie können jedoch in einer späteren Phase des Planungstools weitere Optionen konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="1f4d5-137">However, you can configure more options in a later phase of the Planning Tool.</span></span> <span data-ttu-id="1f4d5-138">Einige Optionen sind nicht verfügbar und können nicht deaktiviert werden.</span><span class="sxs-lookup"><span data-stu-id="1f4d5-138">There are also options that are unavailable and cannot be cleared.</span></span> <span data-ttu-id="1f4d5-139">Darüber hinaus müssen Sie möglicherweise eine Option deaktivieren, um eine andere deaktivieren zu können.</span><span class="sxs-lookup"><span data-stu-id="1f4d5-139">In addition, you may have to clear one option in order to clear another.</span></span> <span data-ttu-id="1f4d5-140">Wenn Sie zum Beispiel unter „VoIP“ die Option <STRONG>Enterprise-VoIP</STRONG> deaktivieren, sind unter „Serveranwendungen“ die Optionen <STRONG>Reaktionsgruppe</STRONG>, <STRONG>Ankündigung</STRONG> und <STRONG>Anruf parken</STRONG> deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="1f4d5-140">For example, if you clear the <STRONG>Enterprise Voice</STRONG> option under Voice, then the <STRONG>Response Group</STRONG>, <STRONG>Announcement</STRONG>, and <STRONG>Call Park</STRONG> options under Server Applications (all of which are features of Enterprise Voice) are also cleared.</span></span>

    
    </div>

11. <span data-ttu-id="1f4d5-141">Klicken Sie nach dem Definieren von Standortname und Nutzeranzahl auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="1f4d5-141">After defining a site name and number of users, click **Next**.</span></span>

12. <span data-ttu-id="1f4d5-142">Auf den folgenden Seiten werden Informationen zu SIP-Domänen, Konferenzeinstellungen, Spracheinstellungen und-Infrastruktur, Exchange um-, externer Benutzer Zugriff, Einstellungen für beständigen Chat, Clienteinstellungen, Zusammenstellungsoptionen und Verzweigungs Websites verlangt.</span><span class="sxs-lookup"><span data-stu-id="1f4d5-142">The following pages ask for information about SIP domains, conference settings, voice settings and infrastructure, Exchange UM, external user access, Persistent Chat settings, client settings, collocation options, and branch sites.</span></span> <span data-ttu-id="1f4d5-143">Geben Sie die entsprechenden Informationen an.</span><span class="sxs-lookup"><span data-stu-id="1f4d5-143">Answer these questions as appropriate.</span></span>

13. <span data-ttu-id="1f4d5-144">In der letzten Frage wird gefragt, ob Sie eine weitere zentrale Website erstellen möchten.</span><span class="sxs-lookup"><span data-stu-id="1f4d5-144">The final question asks if you want to create another central site.</span></span> <span data-ttu-id="1f4d5-145">Wenn Sie **Ja**auswählen, kehrt das Planungs Tool zur Seite "zentrale Websites" zurück.</span><span class="sxs-lookup"><span data-stu-id="1f4d5-145">If you select **Yes**, then the Planning Tool returns to the Central Sites page.</span></span> <span data-ttu-id="1f4d5-146">Wenn Sie **Nein** auswählen, klicken Sie auf **Weiter** und anschließend auf **Zeichnen**, um die allgemeine Übersicht über die globale Technologie anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="1f4d5-146">If you select **No**, click **Next**, and then click **Draw** to display the high-level Global Topology view.</span></span>

14. <span data-ttu-id="1f4d5-147">Klicken Sie zum Anzeigen einer vorhandenen Topologie auf **Anzeigen**.</span><span class="sxs-lookup"><span data-stu-id="1f4d5-147">To view an existing topology, click **Display**.</span></span>

15. <span data-ttu-id="1f4d5-148">Klicken Sie auf die XML-Datei, welche die zuvor gespeicherte Topologie enthält, und klicken Sie auf **Öffnen**.</span><span class="sxs-lookup"><span data-stu-id="1f4d5-148">Click the .xml file that represents the previously saved topology, and then click **Open**.</span></span>

16. <span data-ttu-id="1f4d5-149">Das Planungs Tool zeigt die Seite globale Topologie an.</span><span class="sxs-lookup"><span data-stu-id="1f4d5-149">The Planning Tool displays the Global Topology page.</span></span> <span data-ttu-id="1f4d5-150">Mit den im Planungs Tool verfügbaren Tools können Sie nun mit dem Bearbeiten, aktualisieren oder Ändern der Topologie beginnen.</span><span class="sxs-lookup"><span data-stu-id="1f4d5-150">You can now begin editing, updating, or changing the topology by using the tools available in the Planning Tool.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="1f4d5-151">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="1f4d5-151">See Also</span></span>


[<span data-ttu-id="1f4d5-152">Bearbeiten des Entwurfs in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1f4d5-152">Editing the design in Lync Server 2013</span></span>](lync-server-2013-editing-the-design.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

