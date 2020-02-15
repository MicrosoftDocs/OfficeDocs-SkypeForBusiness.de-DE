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
ms.openlocfilehash: ed95696dc0acad9030615f8a031672f8abf3a136
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42046758"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-the-initial-topology-design-for-lync-server-2013"></a><span data-ttu-id="b950b-102">Erstellen des anfänglichen Topologie Designs für lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b950b-102">Create the initial topology design for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b950b-103">_**Letztes Änderungsstand des Themas:** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="b950b-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="b950b-104">Nachdem Sie die Installation des lync Server 2013 Planungstools abgeschlossen haben, können Sie das Planungstool starten und mit dem Entwerfen der vorgeschlagenen lync Server 2013 Infrastruktur beginnen.</span><span class="sxs-lookup"><span data-stu-id="b950b-104">After you have finished installing the Lync Server 2013, Planning Tool, you are ready to start the Planning Tool and begin designing the proposed Lync Server 2013 infrastructure.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="b950b-105">Das Planungstool ist ein Assistenten gesteuertes Tool mit detaillierten Anleitungen, um den Entscheidungsfindungsprozess beim Entwerfen Ihrer Websites und der Topologie zu informieren.</span><span class="sxs-lookup"><span data-stu-id="b950b-105">The Planning Tool is a wizard-driven tool with detailed guides to inform your decision-making process in designing your sites and topology.</span></span> <span data-ttu-id="b950b-106">Dieses Thema ist nicht als vollständiger Leitfaden gedacht, sondern dient lediglich dazu, Ihnen den Einstieg in die Verwendung des Planungstools in ihren Entwurfs Sitzungen zu erleichtern.</span><span class="sxs-lookup"><span data-stu-id="b950b-106">This topic is intended not as an exhaustive guide, but simply to help get you started using the Planning Tool in your design sessions.</span></span>



</div>

<div>

## <a name="to-get-started-using-the-planning-tool-and-create-the-initial-design"></a><span data-ttu-id="b950b-107">So beginnen Sie mit dem Planungs Tool und erstellen den anfänglichen Entwurf</span><span class="sxs-lookup"><span data-stu-id="b950b-107">To get started using the Planning Tool and create the initial design</span></span>

1.  <span data-ttu-id="b950b-108">Starten des lync Server 2013, Planungstools: Klicken Sie im **Startmenü**auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **Planungstool**.</span><span class="sxs-lookup"><span data-stu-id="b950b-108">Start the Lync Server 2013, Planning Tool: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Planning Tool**.</span></span>

2.  <span data-ttu-id="b950b-109">Nachdem das Planungstool gestartet wurde, wird die Seite **Willkommen beim Planungstool für Microsoft lync Server 2013** angezeigt.</span><span class="sxs-lookup"><span data-stu-id="b950b-109">After the Planning Tool has started, the **Welcome to the Planning Tool for Microsoft Lync Server 2013** page appears.</span></span> <span data-ttu-id="b950b-110">Wählen Sie eine der folgenden Optionen aus, um mit Ihrem Entwurf zu beginnen:</span><span class="sxs-lookup"><span data-stu-id="b950b-110">Choose one of the following options to begin your design:</span></span>
    
      - <span data-ttu-id="b950b-111">**Option 1: Erste Schritte**   klicken **Sie auf erste Schritte** , um eine bestimmte Reihe von Interview Fragen mit relevanten Auswahlmöglichkeiten zum Definieren der Kriterien anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="b950b-111">**Option 1: Get Started**   Clicking **Get Started** provides a specific series of interview questions with relevant selections to define the criteria.</span></span> <span data-ttu-id="b950b-112">Nachdem Sie den Abschnitt erste **Schritte** mit dem ersten Gespräch abgeschlossen haben, gehen Sie zu **Design Websites** , um die Websitearchitektur zu definieren.</span><span class="sxs-lookup"><span data-stu-id="b950b-112">After you have finished the initial **Get Started** interview section, you proceed into **Design Sites** to define your site architecture.</span></span> <span data-ttu-id="b950b-113">Um diese Option abzuschließen, fahren Sie mit Schritt 3 fort.</span><span class="sxs-lookup"><span data-stu-id="b950b-113">To complete this option, proceed to step 3.</span></span>
    
      - <span data-ttu-id="b950b-114">**Option 2: Design Websites**   Wenn Sie auf der Willkommensseite auf " **Design Sites** " klicken, werden die im Abschnitt " **Erste Schritte** " dargestellten Interview Fragen umgangen.</span><span class="sxs-lookup"><span data-stu-id="b950b-114">**Option 2: Design Sites**   Clicking **Design Sites** at the Welcome page bypasses the interview questions presented in the **Get Started** section.</span></span> <span data-ttu-id="b950b-115">Die Informationen, die durch Antworten auf das Interview Fragen im Abschnitt **Erste Schritte** gesammelt worden wären, werden mit dieser Option auf Standardwerte festgelegt.</span><span class="sxs-lookup"><span data-stu-id="b950b-115">The information that would have been gathered by responding to the interview questions in **Get Started** section is set to default values with this option.</span></span> <span data-ttu-id="b950b-116">Durch Klicken auf **Websites entwerfen**kann der erfahrene Designer das ursprüngliche Interview umgehen und die Standardwerte bei Bedarf auf der Startseite der **zentralen Websites** ändern.</span><span class="sxs-lookup"><span data-stu-id="b950b-116">By clicking **Design Sites**, the experienced designer can bypass the initial interview and change the default values, as needed, on the **Central Sites** start page.</span></span> <span data-ttu-id="b950b-117">Um diese Option abzuschließen, überspringen Sie die Schritte 3-5, und beginnen Sie mit Schritt 6.</span><span class="sxs-lookup"><span data-stu-id="b950b-117">To complete this option, skip over steps 3-5 and start at step 6.</span></span>
    
      - <span data-ttu-id="b950b-118">**Option 3: Anzeigen der gespeicherten Topologie**   Wenn Sie eine Topologie durch vorherige Verwendung des Planungstools bereits abgeschlossen und gespeichert haben, können Sie die meisten dieser Schritte überspringen und mit dem Öffnen und Anzeigen der Topologie beginnen.</span><span class="sxs-lookup"><span data-stu-id="b950b-118">**Option 3: Display Your Saved Topology**   If you have already completed and saved a topology through previous use of the Planning Tool, you can skip over most of these steps and start by opening and displaying the topology.</span></span> <span data-ttu-id="b950b-119">Sie können auch Änderungen und Aktualisierungen an der Topologie vornehmen, Sie erneut speichern und dann in Microsoft Excel oder Microsoft Visio exportieren.</span><span class="sxs-lookup"><span data-stu-id="b950b-119">You can also make changes and updates to the topology, resave it, and then export it to Microsoft Excel or Microsoft Visio.</span></span> <span data-ttu-id="b950b-120">Um diese Option abzuschließen, überspringen Sie die Schritte 3-12, und beginnen Sie mit Schritt 13.</span><span class="sxs-lookup"><span data-stu-id="b950b-120">To complete this option, skip over steps 3-12 and start at step 13.</span></span>

3.  <span data-ttu-id="b950b-121">Klicken Sie auf **Erste Schritte** , um mit dem Entwerfen Ihrer lync Server 2013 Topologie zu beginnen.</span><span class="sxs-lookup"><span data-stu-id="b950b-121">Click **Get Started** to begin designing your Lync Server 2013 topology.</span></span>

4.  <span data-ttu-id="b950b-122">Beantworten Sie die einzelnen Abschnitte, indem Sie die entsprechenden Kriterien für Ihren Entwurf auswählen, und klicken Sie dann auf **weiter** , um zur nächsten Assistentenseite zu gelangen.</span><span class="sxs-lookup"><span data-stu-id="b950b-122">Answer each section by selecting the appropriate criteria for your design, and then click **Next** to proceed to the next Wizard page.</span></span> <span data-ttu-id="b950b-123">Klicken Sie auf **zurück** , um Änderungen auf vorherigen Seiten vorzunehmen.</span><span class="sxs-lookup"><span data-stu-id="b950b-123">Click **Back** to make changes on previous pages.</span></span>
    
    <div>
    

    > [!TIP]  
    > <span data-ttu-id="b950b-124">Jede Seite enthält eine Beschreibung der Auswahlkriterien und Empfehlungen basierend auf bevorzugten Methoden und Kapazitätsplanung.</span><span class="sxs-lookup"><span data-stu-id="b950b-124">Each page has a description of the selection criteria, and recommendations based on preferred practices and capacity planning.</span></span> <span data-ttu-id="b950b-125">Wenn Sie weitere Informationen benötigen <STRONG>, klicken Sie auf Weitere Informationen</STRONG> , um detaillierte Informationen aus der lync Server 2013 Planungsdokumentation auf der Microsoft TechNet-Website zu lesen.</span><span class="sxs-lookup"><span data-stu-id="b950b-125">If you require additional details, click <STRONG>Learn more</STRONG> to read detailed information from the Lync Server 2013 Planning documentation on the Microsoft TechNet website.</span></span> <span data-ttu-id="b950b-126">Für den Zugriff auf die Microsoft TechNet-Website benötigen Sie eine Internet Verbindung.</span><span class="sxs-lookup"><span data-stu-id="b950b-126">You must have Internet connectivity to access the Microsoft TechNet website.</span></span>

    
    </div>

5.  <span data-ttu-id="b950b-127">Wählen Sie die entsprechenden Optionen für Ihren Entwurf aus.</span><span class="sxs-lookup"><span data-stu-id="b950b-127">Select the appropriate options for your design.</span></span> <span data-ttu-id="b950b-128">Nachdem die anfänglichen Kriterien definiert wurden, wird eine Seite bestätigen, dass ihre Features-Übersicht abgeschlossen ist.</span><span class="sxs-lookup"><span data-stu-id="b950b-128">After the initial criteria are defined, a page will confirm that your Features Overview is complete.</span></span>

6.  <span data-ttu-id="b950b-129">Klicken Sie auf **Websites entwerfen** , um Ihren zentralen Standort zu definieren.</span><span class="sxs-lookup"><span data-stu-id="b950b-129">Click **Design Sites** to define your central site.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="b950b-130">Für jede lync Server 2013 Topologie ist mindestens ein zentraler Standort erforderlich.</span><span class="sxs-lookup"><span data-stu-id="b950b-130">Each Lync Server 2013 topology will have at least one central site.</span></span> <span data-ttu-id="b950b-131">Ihr Entwurf kann einen einzelnen zentralen Standort, einen zentralen Standort mit einer Reihe von Zweigstellenstandorten, eine Reihe von zentralen Standorten oder eine Reihe von zentralen Standorten mit Zweigstellenstandorten aufweisen, die jedem zentralen Standort zugeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="b950b-131">Your design may have a single central site, a central site with a number of branch sites, a number of central sites, or a number of central sites with branch sites associated with each central site.</span></span>

    
    </div>

7.  <span data-ttu-id="b950b-132">Geben Sie unter **Websitename**den Namen ein, mit dem dieser zentrale Standort identifiziert wird.</span><span class="sxs-lookup"><span data-stu-id="b950b-132">In **Site Name**, type the name that will identify this central site.</span></span>

8.  <span data-ttu-id="b950b-133">Geben Sie unter **Standort verwaltete Benutzer**die erwartete Anzahl von lokalen gleichzeitigen Benutzern ein, die an diesem zentralen Standort verwaltet werden sollen.</span><span class="sxs-lookup"><span data-stu-id="b950b-133">In **Site Homed Users**, type the expected number of on-premises concurrent users who will be homed in this central site.</span></span>

9.  <span data-ttu-id="b950b-134">Geben Sie in in der Cloud vernetzte **Benutzer**die erwartete Anzahl gleichzeitiger Online Benutzer ein, die an diesem zentralen Standort verwaltet werden sollen.</span><span class="sxs-lookup"><span data-stu-id="b950b-134">In **Cloud Homed Users**, type the expected number of online concurrent users who will be homed in this central site.</span></span>

10. <span data-ttu-id="b950b-135">Ändern Sie bei Bedarf die Auswahlmöglichkeiten für Online Zusammenarbeit, Benutzer, VoIP, zusätzliche Bereitstellungsoptionen oder Server Anwendungen.</span><span class="sxs-lookup"><span data-stu-id="b950b-135">Modify the selections for Online Collaboration, Users, Voice, Additional Deployment Options, or Server Applications, as needed.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="b950b-136">Zu diesem Zeitpunkt im Entwurf können Sie nur Optionen für Ihre Bereitstellung auswählen oder deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="b950b-136">At this point in the design, you can only select or clear options for your deployment.</span></span> <span data-ttu-id="b950b-137">Sie können jedoch in einer späteren Phase des Planungstools weitere Optionen konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="b950b-137">However, you can configure more options in a later phase of the Planning Tool.</span></span> <span data-ttu-id="b950b-138">Es gibt auch Optionen, die nicht verfügbar sind und nicht gelöscht werden können.</span><span class="sxs-lookup"><span data-stu-id="b950b-138">There are also options that are unavailable and cannot be cleared.</span></span> <span data-ttu-id="b950b-139">Darüber hinaus müssen Sie möglicherweise eine Option deaktivieren, um eine andere zu löschen.</span><span class="sxs-lookup"><span data-stu-id="b950b-139">In addition, you may have to clear one option in order to clear another.</span></span> <span data-ttu-id="b950b-140">Wenn Sie beispielsweise die <STRONG>Enterprise-VoIP</STRONG> -Option unter VoIP deaktivieren, werden die Optionen <STRONG>Reaktionsgruppe</STRONG>, <STRONG>Ankündigung</STRONG>und <STRONG>Anruf parken</STRONG> unter Server Anwendungen (alle Features von Enterprise-VoIP) ebenfalls gelöscht.</span><span class="sxs-lookup"><span data-stu-id="b950b-140">For example, if you clear the <STRONG>Enterprise Voice</STRONG> option under Voice, then the <STRONG>Response Group</STRONG>, <STRONG>Announcement</STRONG>, and <STRONG>Call Park</STRONG> options under Server Applications (all of which are features of Enterprise Voice) are also cleared.</span></span>

    
    </div>

11. <span data-ttu-id="b950b-141">Nachdem Sie einen Websitenamen und die Anzahl der Benutzerdefiniert haben, klicken Sie auf **weiter**.</span><span class="sxs-lookup"><span data-stu-id="b950b-141">After defining a site name and number of users, click **Next**.</span></span>

12. <span data-ttu-id="b950b-142">Auf den folgenden Seiten werden Informationen zu SIP-Domänen, Konferenzeinstellungen, VoIP-Einstellungen und-Infrastruktur, Exchange um, externer Benutzer Zugriff, Einstellungen für beständigen Chat, Clienteinstellungen, Zusammenstellungsoptionen und Zweigstellen Sites abgefragt.</span><span class="sxs-lookup"><span data-stu-id="b950b-142">The following pages ask for information about SIP domains, conference settings, voice settings and infrastructure, Exchange UM, external user access, Persistent Chat settings, client settings, collocation options, and branch sites.</span></span> <span data-ttu-id="b950b-143">Beantworten Sie diese Fragen entsprechend.</span><span class="sxs-lookup"><span data-stu-id="b950b-143">Answer these questions as appropriate.</span></span>

13. <span data-ttu-id="b950b-144">In der letzten Frage werden Sie gefragt, ob Sie einen anderen zentralen Standort erstellen möchten.</span><span class="sxs-lookup"><span data-stu-id="b950b-144">The final question asks if you want to create another central site.</span></span> <span data-ttu-id="b950b-145">Wenn Sie **Ja**auswählen, kehrt das Planungs Tool zur Seite Zentrale Standorte zurück.</span><span class="sxs-lookup"><span data-stu-id="b950b-145">If you select **Yes**, then the Planning Tool returns to the Central Sites page.</span></span> <span data-ttu-id="b950b-146">Wenn Sie **Nein**auswählen, klicken Sie auf **weiter**, und klicken Sie dann auf **Zeichnen** , um die Ansicht globaler Topologie auf hoher Ebene anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="b950b-146">If you select **No**, click **Next**, and then click **Draw** to display the high-level Global Topology view.</span></span>

14. <span data-ttu-id="b950b-147">Klicken Sie auf **anzeigen**, um eine vorhandene Topologie anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="b950b-147">To view an existing topology, click **Display**.</span></span>

15. <span data-ttu-id="b950b-148">Klicken Sie auf die XML-Datei, die die zuvor gespeicherte Topologie darstellt, und klicken Sie dann auf **Öffnen**.</span><span class="sxs-lookup"><span data-stu-id="b950b-148">Click the .xml file that represents the previously saved topology, and then click **Open**.</span></span>

16. <span data-ttu-id="b950b-149">Das Planungs Tool zeigt die Seite globale Topologie an.</span><span class="sxs-lookup"><span data-stu-id="b950b-149">The Planning Tool displays the Global Topology page.</span></span> <span data-ttu-id="b950b-150">Sie können jetzt mit der Bearbeitung, Aktualisierung oder Änderung der Topologie beginnen, indem Sie die Tools verwenden, die im Planungs Tool zur Verfügung stehen.</span><span class="sxs-lookup"><span data-stu-id="b950b-150">You can now begin editing, updating, or changing the topology by using the tools available in the Planning Tool.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="b950b-151">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b950b-151">See Also</span></span>


[<span data-ttu-id="b950b-152">Bearbeiten des Entwurfs in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b950b-152">Editing the design in Lync Server 2013</span></span>](lync-server-2013-editing-the-design.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

