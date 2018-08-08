---
title: Planen des Parkens von Anrufen in Skype for Business
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 985dc326-0aef-4308-b98b-c1d0069311e7
description: Planung für das Parken von Anrufen in Skype für Business Server Enterprise-VoIP, können die für Anrufe, die auf halten und Weiterleiten von Anrufen zu Abteilungen eingefügt. Hierzu gehören die Kapazitätsplanung, unterstützte Anrufe und unterstützte Clients.
ms.openlocfilehash: a675100f8b40e1ab293c0240ea0acbe3beb7fa27
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/24/2018
ms.locfileid: "20988550"
---
# <a name="plan-for-call-park-in-skype-for-business"></a><span data-ttu-id="b0cfa-104">Planen des Parkens von Anrufen in Skype for Business</span><span class="sxs-lookup"><span data-stu-id="b0cfa-104">Plan for Call Park in Skype for Business</span></span>
 
<span data-ttu-id="b0cfa-105">Planung für das Parken von Anrufen in Skype für Business Server Enterprise-VoIP, können die für Anrufe, die auf halten und Weiterleiten von Anrufen zu Abteilungen eingefügt.</span><span class="sxs-lookup"><span data-stu-id="b0cfa-105">Planning for call park in Skype for Business Server Enterprise Voice, which enables putting calls on hold and transferring calls to departments.</span></span> <span data-ttu-id="b0cfa-106">Hierzu gehören die Kapazitätsplanung, unterstützte Anrufe und unterstützte Clients.</span><span class="sxs-lookup"><span data-stu-id="b0cfa-106">Includes capacity planning, supported calls, and supported clients.</span></span>
  
<span data-ttu-id="b0cfa-107">Die Anwendung zum Parken kann Enterprise-VoIP-Benutzer folgende Aktionen ausführen:</span><span class="sxs-lookup"><span data-stu-id="b0cfa-107">The Call Park application enables Enterprise Voice users to do the following:</span></span>
  
- <span data-ttu-id="b0cfa-108">Halten eines Anrufs und anschließendes Entgegennehmen des Anrufs am selben oder an einem anderen Telefon.</span><span class="sxs-lookup"><span data-stu-id="b0cfa-108">Put a call on hold and then retrieve the call from the same phone or another phone.</span></span>
    
- <span data-ttu-id="b0cfa-109">Halten eines Anrufs, um ihn an eine Abteilung oder einen allgemeinen Bereich zu übergeben (z. B. die Vertriebsabteilung oder ein Lagerort mit einem Telefon im öffentlichen Bereich).</span><span class="sxs-lookup"><span data-stu-id="b0cfa-109">Put a call on hold to transfer it to a department or general area (for example, to a sales department or a warehouse where there is a common area phone).</span></span>
    
- <span data-ttu-id="b0cfa-110">Halten eines Anrufs, um weitere Anrufe an einem Telefon entgegennehmen zu können.</span><span class="sxs-lookup"><span data-stu-id="b0cfa-110">Put a call on hold and keep the original answering phone free for other calls.</span></span>
    
<span data-ttu-id="b0cfa-111">Wenn ein Benutzer Parks überträgt Gespräch Skype für Business Server den Anruf an eine temporäre Zahl, eine Orbit aufgerufen wird, in dem der Anruf gespeichert, bis es abgerufen wird, oder das Zeitlimit überschritten. Skype für Business Server sendet den Orbit, dem Benutzer, der den Anruf geparkt.</span><span class="sxs-lookup"><span data-stu-id="b0cfa-111">When a user parks a call, Skype for Business Server transfers the call to a temporary number, called an orbit, where the call is held until it is retrieved or it times out. Skype for Business Server sends the orbit to the user who parked the call.</span></span> <span data-ttu-id="b0cfa-112">Zum Wiederaufnehmen des geparkten Anrufs kann der Benutzer die Orbitnummer wählen oder auf den Orbitlink oder die Schaltfläche im Fenster „Unterhaltung“ klicken.</span><span class="sxs-lookup"><span data-stu-id="b0cfa-112">To retrieve the parked call, the user can dial the orbit number or click the orbit link or button in the Conversation window.</span></span> 
  
<span data-ttu-id="b0cfa-p104">Der Benutzer, der einen Anruf geparkt hat, kann einen anderen Benutzer mithilfe eines externen Mechanismus (beispielsweise über eine Sofortnachricht oder ein Paging-System) über die Orbitnummer informieren, damit dieser Benutzer den Anruf entgegennehmen kann. Der Benutzer, der den Anruf geparkt hat, kann das Fenster „Unterhaltung“ geöffnet lassen, um eine Benachrichtigung zu erhalten, sobald der Anruf entgegengenommen wurde.</span><span class="sxs-lookup"><span data-stu-id="b0cfa-p104">The user who parked a call can notify someone to retrieve the call by using an external mechanism, such as instant messaging (IM) or a paging system, to communicate the orbit number to someone else. The user who parked the call can leave the Conversation window open to receive notification when the call is retrieved.</span></span>
  
<span data-ttu-id="b0cfa-115">Da orbitbereiche global eindeutig sind, ist es möglich, Anrufe von jeder Skype für Business Server-Website oder PBX-Telefon abrufen, wenn routing entsprechend konfiguriert ist.</span><span class="sxs-lookup"><span data-stu-id="b0cfa-115">Because orbit ranges are globally unique, it is possible to retrieve calls from any Skype for Business Server site or PBX phone if routing is configured appropriately.</span></span> <span data-ttu-id="b0cfa-116">Wenn der Anruf innerhalb einer konfigurierbaren Zeitdauer nicht wiederaufgenommen wird, wird er erneut an den Benutzer zurückgegeben, der den Anruf geparkt hat.</span><span class="sxs-lookup"><span data-stu-id="b0cfa-116">If no one retrieves the call within a configurable amount of time, the call rings back to the person who parked it.</span></span> <span data-ttu-id="b0cfa-117">Wenn dieser Benutzer den Anruf nicht beantwortet, wird er an ein Fallbackziel übergeben (z. B. einen Agent), sofern dies konfiguriert wurde.</span><span class="sxs-lookup"><span data-stu-id="b0cfa-117">If that person does not answer the ringback, the call is transferred to a fallback destination, such as to an operator, if so configured.</span></span> <span data-ttu-id="b0cfa-118">Sie können konfigurieren, wie oft das Telefon erneut läutet (ein- bis zehnmal), bevor der Anruf weitergeleitet wird.</span><span class="sxs-lookup"><span data-stu-id="b0cfa-118">You can configure the number of times the call rings back before being transferred from one to ten times.</span></span> <span data-ttu-id="b0cfa-119">Wenn ein weitergeleiteter Anruf nicht entgegengenommen wird, wird die Verbindung unterbrochen.</span><span class="sxs-lookup"><span data-stu-id="b0cfa-119">If no one answers a transferred call, the call is disconnected.</span></span> <span data-ttu-id="b0cfa-120">Wenn der Anruf entgegengenommen oder die Verbindung unterbrochen wird, wird der Orbit erneut freigegeben.</span><span class="sxs-lookup"><span data-stu-id="b0cfa-120">The orbit is freed when the call is retrieved or disconnected.</span></span>
  
<span data-ttu-id="b0cfa-121">Wenn Sie die Funktion zum Parken von Anrufen bereitstellen, müssen Sie Durchwahlnummernbereiche zum Parken von Anrufen reservieren.</span><span class="sxs-lookup"><span data-stu-id="b0cfa-121">When you deploy Call Park, you need to reserve ranges of extension numbers for parking calls.</span></span> <span data-ttu-id="b0cfa-122">Bei diesen Durchwahlnummern muss es sich um virtuelle Durchwahlnummern handeln, also solche, denen kein Benutzer oder Telefon zugewiesen ist.</span><span class="sxs-lookup"><span data-stu-id="b0cfa-122">These extensions need to be virtual extensions: extensions that have no user or phone assigned to them.</span></span> <span data-ttu-id="b0cfa-123">Anschließend konfigurieren Sie die Orbittabelle für das Parken von Anrufen mit den Durchwahlnummernbereichen und geben an, welcher Anwendungsdienst die Anwendung zum Parken von Anrufen hostet, die die einzelnen Bereiche verarbeitet.</span><span class="sxs-lookup"><span data-stu-id="b0cfa-123">You then configure the call park orbit table with the ranges of extension numbers and specify which Application service hosts the Call Park application that handles each range.</span></span> <span data-ttu-id="b0cfa-124">Jeder Front-End-Pool verfügt über die Tabelle zum Parken von Anrufen auf den entsprechenden Back End-Server, der verwendet wird, um Anrufe zu verwalten, die im Pool geparkt werden.</span><span class="sxs-lookup"><span data-stu-id="b0cfa-124">Each Front End pool has a Call Park table on the corresponding Back End Server that is used to manage calls that are parked on the pool.</span></span> <span data-ttu-id="b0cfa-125">Die Liste der orbitbereiche in der zentralen gespeichert ist speichern und wird verwendet, um Orbits auf den Zielpool weitergeleitet.</span><span class="sxs-lookup"><span data-stu-id="b0cfa-125">The list of orbit ranges is stored in Central Management store and is used to route orbits to the destination pool.</span></span> <span data-ttu-id="b0cfa-126">Jede Skype für Business Server Pool, in dem die Anwendung zum Parken bereitgestellt und konfiguriert ist, kann eine oder mehrere orbitbereiche haben.</span><span class="sxs-lookup"><span data-stu-id="b0cfa-126">Each Skype for Business Server pool where the Call Park application is deployed and configured can have one or more orbit ranges.</span></span> <span data-ttu-id="b0cfa-127">Orbitbereiche müssen für die Skype für Business Server-Bereitstellung global eindeutig sein.</span><span class="sxs-lookup"><span data-stu-id="b0cfa-127">Orbit ranges must be globally unique across the Skype for Business Server deployment.</span></span> 
  
<span data-ttu-id="b0cfa-p107">Sie können darüber hinaus weitere Einstellungen für das Parken von Anrufen konfigurieren, wie z. B., an welches Ziel Anrufe bei einem Timeout umgeleitet werden und ob für den Anrufer Musik wiedergegeben wird, während der Anruf geparkt ist. Außerdem können Sie die Musikdatei angeben, die beim Parken des Anrufs wiedergegeben wird.</span><span class="sxs-lookup"><span data-stu-id="b0cfa-p107">You also configure other Call Park settings, such as where calls are redirected if they time out and whether the person on the phone hears music while parked. You can also specify the music file to play while the call is on hold.</span></span>
  
> [!NOTE]
> <span data-ttu-id="b0cfa-130">Benutzerdefinierte Musik halten-Dateien für das Parken werden nicht als Teil der Skype für notfallwiederherstellungsprozess Business Server gesichert und deshalb verloren gehen, wenn die Dateien auf den Pool hochgeladen beschädigt, beschädigt oder gelöscht werden.</span><span class="sxs-lookup"><span data-stu-id="b0cfa-130">Customized music-on-hold files for Call Park are not backed up as part of the Skype for Business Server disaster recovery process and will be lost if the files uploaded to the pool are damaged, corrupted, or erased.</span></span> <span data-ttu-id="b0cfa-131">Bewahren Sie stets eine separate Sicherungskopie der für geparkte Anrufe hochgeladenen angepassten Musikdateien auf.</span><span class="sxs-lookup"><span data-stu-id="b0cfa-131">Always keep a separate backup copy of the customized music-on-hold files that you have uploaded for Call Park.</span></span> 
  
<span data-ttu-id="b0cfa-132">Die Anwendung zum Parken von Anrufen ist eine Enterprise-VoIP-Komponente.</span><span class="sxs-lookup"><span data-stu-id="b0cfa-132">The Call Park application is a component of Enterprise Voice.</span></span> <span data-ttu-id="b0cfa-133">Wenn Sie Enterprise-VoIP bereitstellen, wird die Anwendung zum Parken installiert und automatisch aktiviert.</span><span class="sxs-lookup"><span data-stu-id="b0cfa-133">When you deploy Enterprise Voice, the Call Park application is installed and activated automatically.</span></span> <span data-ttu-id="b0cfa-134">Vor der Verwendung des Parkens von Anrufen jedoch muss der Enterprise-VoIP-Administrator konfiguriert wird und für Benutzer über VoIP-Richtlinie zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="b0cfa-134">Before you can use Call Park, however, the Enterprise Voice administrator must configure it and enable it for users through voice policy.</span></span>
  
## <a name="deployment-and-requirements"></a><span data-ttu-id="b0cfa-135">Bereitstellung und Anforderungen</span><span class="sxs-lookup"><span data-stu-id="b0cfa-135">Deployment and requirements</span></span>

<span data-ttu-id="b0cfa-136">Die Anwendung zum Parken wird bei der Bereitstellung von Enterprise-VoIP automatisch installiert.</span><span class="sxs-lookup"><span data-stu-id="b0cfa-136">The Call Park application is automatically installed when you deploy Enterprise Voice.</span></span> <span data-ttu-id="b0cfa-137">Konfigurieren von VoIP-Richtlinie aktivieren Sie das Parken von Anrufen.</span><span class="sxs-lookup"><span data-stu-id="b0cfa-137">You enable Call Park by configuring voice policy.</span></span>
  
### <a name="software-requirements"></a><span data-ttu-id="b0cfa-138">Softwareanforderungen</span><span class="sxs-lookup"><span data-stu-id="b0cfa-138">Software requirements</span></span>

<span data-ttu-id="b0cfa-139">Alle Front-End-Servern und Standard Edition-Servern in der Parken bereitgestellt wird, müssen die Windows Media Format-Laufzeitkomponente für Server mit Windows Server 2008 R2 oder Microsoft Media Foundation für Server mit Windows Server 2012 oder Windows Server installiert haben 2012 R2.</span><span class="sxs-lookup"><span data-stu-id="b0cfa-139">All Front End Servers and Standard Edition servers where Call Park is deployed must have the Windows Media Format Runtime installed for servers running Windows Server 2008 R2, or Microsoft Media Foundation for servers running Windows Server 2012 or Windows Server 2012 R2.</span></span> <span data-ttu-id="b0cfa-140">Windows Media Format-Laufzeitkomponente ist für Windows Server 2008 R2 als Teil des Windows Desktop Experience installiert.</span><span class="sxs-lookup"><span data-stu-id="b0cfa-140">For Windows Server 2008 R2, Windows Media Format Runtime is installed as part of Windows Desktop Experience.</span></span> <span data-ttu-id="b0cfa-141">Windows Media Format-Laufzeitkomponente oder Microsoft Media Foundation ist erforderlich für Windows Media Audio (WMA)-Dateien, die zum Parken von Anrufen wiedergegeben wird für die Musik in der Warteschleife.</span><span class="sxs-lookup"><span data-stu-id="b0cfa-141">Windows Media Format Runtime or Microsoft Media Foundation is required for Windows Media Audio (.wma) files that Call Park plays for music on hold.</span></span>
  
### <a name="port-requirements"></a><span data-ttu-id="b0cfa-142">Portanforderungen</span><span class="sxs-lookup"><span data-stu-id="b0cfa-142">Port requirements</span></span>

<span data-ttu-id="b0cfa-143">Die Anwendung zum Parken von Anrufen verwendet **Port 5075** für SIP-überwachungsanforderungen verwendet.</span><span class="sxs-lookup"><span data-stu-id="b0cfa-143">The Call Park application uses **Port 5075**  for SIP listening requests.</span></span>
    
> [!NOTE]
> <span data-ttu-id="b0cfa-144">Dieser Port ist eine Standardeinstellung, die Sie mit dem Cmdlet **Set-CsApplicationServer** ändern können.</span><span class="sxs-lookup"><span data-stu-id="b0cfa-144">This port is a default setting that you can change by using the **Set-CsApplicationServer** cmdlet.</span></span> <span data-ttu-id="b0cfa-145">Ausführliche Informationen zu diesem Cmdlet finden Sie unter der Lync Server-Verwaltungsshell-Dokumentation.</span><span class="sxs-lookup"><span data-stu-id="b0cfa-145">For details about this cmdlet, see the Lync Server Management Shell documentation.</span></span>
  
### <a name="audio-file-requirements"></a><span data-ttu-id="b0cfa-146">Anforderungen für Audiodateien</span><span class="sxs-lookup"><span data-stu-id="b0cfa-146">Audio File requirements</span></span>

<span data-ttu-id="b0cfa-147">Halten Sie das Parken von Anrufen, die Anwendung auf nur Windows Media Audio (WMA) Dateien für die Musik unterstützt.</span><span class="sxs-lookup"><span data-stu-id="b0cfa-147">The Call Park application supports only Windows Media Audio (.wma) files for music on hold.</span></span> <span data-ttu-id="b0cfa-148">Der Microsoft Ausdruck Encoder 4 können Sie Dateien für die Musik in der Warteschleife anpassen.</span><span class="sxs-lookup"><span data-stu-id="b0cfa-148">You can use the Microsoft Expression Encoder 4 to customize files for music on hold.</span></span> <span data-ttu-id="b0cfa-149">Informationen zum Herunterladen von Expression Encoder 4 finden Sie unter ["Expression Encoder 4"](https://go.microsoft.com/fwlink/p/?linkId=202843).</span><span class="sxs-lookup"><span data-stu-id="b0cfa-149">To download Expression Encoder 4, see   ["Expression Encoder 4"](https://go.microsoft.com/fwlink/p/?linkId=202843).</span></span> <span data-ttu-id="b0cfa-150">Verwenden Sie das Tool, um die Datei in ein WMA-Format zu konvertieren.</span><span class="sxs-lookup"><span data-stu-id="b0cfa-150">Use the tool to convert the file to a .wma format.</span></span> <span data-ttu-id="b0cfa-151">Das empfohlene Format für das Parken von Anrufen Musik halten Dateien ist Media Audio 9, 44 kHz, 16 Bit, Mono, CBR 32 Kbit/s.</span><span class="sxs-lookup"><span data-stu-id="b0cfa-151">The recommended format for Call Park music-on-hold files is Media Audio 9, 44 kHz, 16 bits, Mono, CBR, 32 kbps.</span></span>
  
> [!NOTE]
> <span data-ttu-id="b0cfa-152">Die konvertierte Datei wird über das Telefon nur mit 16 kHz abgespielt, auch wenn sie mit 44 kHz aufgezeichnet wurde.</span><span class="sxs-lookup"><span data-stu-id="b0cfa-152">The converted file plays over the phone only at 16 kHz, even if it was recorded at 44 kHz.</span></span> 
  
## <a name="supported-clients-and-calls"></a><span data-ttu-id="b0cfa-153">Unterstützte Clients und Anrufe</span><span class="sxs-lookup"><span data-stu-id="b0cfa-153">Supported clients and calls</span></span>

<span data-ttu-id="b0cfa-154">Die folgenden Clients und Anruftypen werden für das Parken unterstützt.</span><span class="sxs-lookup"><span data-stu-id="b0cfa-154">The following clients and types of calls are supported for Call Park</span></span>
  
### <a name="clients-supported-for-parking-calls"></a><span data-ttu-id="b0cfa-155">Für das Parken von Anrufen unterstützte Clients</span><span class="sxs-lookup"><span data-stu-id="b0cfa-155">Clients Supported for Parking Calls</span></span>

<span data-ttu-id="b0cfa-156">Anrufe von IP-, Nebenstellen-, Festnetz- oder Mobiltelefonen können geparkt werden.</span><span class="sxs-lookup"><span data-stu-id="b0cfa-156">Calls from any IP, private branch exchange (PBX), public switched telephone network (PSTN), or mobile phone can be parked.</span></span>
  
> [!NOTE]
> <span data-ttu-id="b0cfa-p114">Nur Audioanrufe können geparkt werden. Das Parken von Chatnachrichten und Konferenzen ist nicht möglich.</span><span class="sxs-lookup"><span data-stu-id="b0cfa-p114">Only audio calls can be parked. Instant messages and conferences cannot be parked.</span></span> 
  
<span data-ttu-id="b0cfa-159">Die folgenden Clients können zum Parken von Anrufen für das Parken von Anrufen:</span><span class="sxs-lookup"><span data-stu-id="b0cfa-159">The following clients can use Call Park to park calls:</span></span>
  
- <span data-ttu-id="b0cfa-160">Skype for Business</span><span class="sxs-lookup"><span data-stu-id="b0cfa-160">Skype for Business</span></span>
    
- <span data-ttu-id="b0cfa-161">Lync 2013</span><span class="sxs-lookup"><span data-stu-id="b0cfa-161">Lync 2013</span></span>
    
- <span data-ttu-id="b0cfa-162">Lync 2010</span><span class="sxs-lookup"><span data-stu-id="b0cfa-162">Lync 2010</span></span>
    
- <span data-ttu-id="b0cfa-163">Lync 2010 Attendant</span><span class="sxs-lookup"><span data-stu-id="b0cfa-163">Lync 2010 Attendant</span></span>
    
- <span data-ttu-id="b0cfa-164">Lync Phone Edition</span><span class="sxs-lookup"><span data-stu-id="b0cfa-164">Lync Phone Edition</span></span>
    
> [!NOTE]
> <span data-ttu-id="b0cfa-165">Mobiltelefone können nicht zum Parken von Anrufen für das Parken von Anrufen verwenden.</span><span class="sxs-lookup"><span data-stu-id="b0cfa-165">Mobile phones cannot use Call Park to park calls.</span></span> 
  
### <a name="clients-supported-for-retrieving-calls"></a><span data-ttu-id="b0cfa-166">Für das Wiederaufnehmen geparkter Anrufe unterstützte Clients</span><span class="sxs-lookup"><span data-stu-id="b0cfa-166">Clients Supported for Retrieving Calls</span></span>

<span data-ttu-id="b0cfa-p115">Orbitbereiche werden als Blöcke virtueller Durchwahlnummern (Durchwahlnummern, denen kein Benutzer oder Telefon zugewiesen ist) konfiguriert. Wenn Sie Orbits als virtuelle Durchwahlnummern konfigurieren, können Mobil- und Festnetztelefone keine geparkten Anrufe wiederaufnehmen.</span><span class="sxs-lookup"><span data-stu-id="b0cfa-p115">Orbit ranges are configured as blocks of virtual extensions (extensions without an assigned user or phone). When you configure orbits as virtual extensions, mobile phones and PSTN phones cannot retrieve parked calls.</span></span>
  
<span data-ttu-id="b0cfa-169">Das Wiederaufnehmen geparkter Anrufe durch Partnerbenutzer ist nicht möglich.</span><span class="sxs-lookup"><span data-stu-id="b0cfa-169">Federated users cannot retrieve parked calls.</span></span>
  
<span data-ttu-id="b0cfa-170">Die folgenden Clients können Anrufe wiederaufnehmen, die auf das Parken von Anrufen geparkt wurden:</span><span class="sxs-lookup"><span data-stu-id="b0cfa-170">The following clients can retrieve calls that are parked on Call Park:</span></span>
  
- <span data-ttu-id="b0cfa-171">Skype for Business</span><span class="sxs-lookup"><span data-stu-id="b0cfa-171">Skype for Business</span></span>
    
- <span data-ttu-id="b0cfa-172">Lync 2013</span><span class="sxs-lookup"><span data-stu-id="b0cfa-172">Lync 2013</span></span>
    
- <span data-ttu-id="b0cfa-173">Lync 2010</span><span class="sxs-lookup"><span data-stu-id="b0cfa-173">Lync 2010</span></span>
    
- <span data-ttu-id="b0cfa-174">Lync 2010 Attendant</span><span class="sxs-lookup"><span data-stu-id="b0cfa-174">Lync 2010 Attendant</span></span>
    
- <span data-ttu-id="b0cfa-175">Lync Phone Edition</span><span class="sxs-lookup"><span data-stu-id="b0cfa-175">Lync Phone Edition</span></span>
    
- <span data-ttu-id="b0cfa-176">IP-Telefone in öffentlichen Bereichen</span><span class="sxs-lookup"><span data-stu-id="b0cfa-176">IP common area phones</span></span>
    
- <span data-ttu-id="b0cfa-177">Nicht-IP-Telefone, die mit der Skype für Business Server-Infrastruktur, einschließlich Telefone in öffentlichen Bereichen und private Branch Exchange, (Nebenstellenanlage PBX) verbunden sind</span><span class="sxs-lookup"><span data-stu-id="b0cfa-177">Non-IP phones that are connected to the Skype for Business Server infrastructure, including common area phones and private branch exchange (PBX) phones</span></span>
    
## <a name="call-park-capacity-planning"></a><span data-ttu-id="b0cfa-178">Kapazitätsplanung für das Parken von Anrufen</span><span class="sxs-lookup"><span data-stu-id="b0cfa-178">Call Park capacity planning</span></span>

<span data-ttu-id="b0cfa-179">Die folgende Tabelle beschreibt das Benutzermodell für das Parken von Anrufen, das Sie als Grundlage für Anforderungen an die kapazitätsplanung verwenden können.</span><span class="sxs-lookup"><span data-stu-id="b0cfa-179">The following table describes the Call Park user model that you can use as the basis for capacity planning requirements.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="b0cfa-180">Beachten Sie, dass die kapazitätsplanung, für die Disaster Recovery jeder Pool eines gekoppelten Pools die Arbeitslast für das Parken von Anrufen Dienste in beiden Pools kann soll beibehalten.</span><span class="sxs-lookup"><span data-stu-id="b0cfa-180">Keep in mind that, for disaster recovery capacity planning, each pool of a paired pool should be able to handle the workloads for Call Park services in both pools.</span></span> 
  
<span data-ttu-id="b0cfa-181">**Benutzermodell der Funktion zum Parken von Anrufen**</span><span class="sxs-lookup"><span data-stu-id="b0cfa-181">**Call Park User Model**</span></span>

|<span data-ttu-id="b0cfa-182">**Metrik**</span><span class="sxs-lookup"><span data-stu-id="b0cfa-182">**Metric**</span></span>|<span data-ttu-id="b0cfa-183">**Pro Front-End-Pool <br/> (mit 8 Front-End-Servern)**</span><span class="sxs-lookup"><span data-stu-id="b0cfa-183">**Per Front End pool  <br/>  (with 8 Front End Servers)**</span></span>|<span data-ttu-id="b0cfa-184">**Pro Standard Edition-Server**</span><span class="sxs-lookup"><span data-stu-id="b0cfa-184">**Per Standard Edition server**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="b0cfa-185">Rate für das Parken von Anrufen</span><span class="sxs-lookup"><span data-stu-id="b0cfa-185">Park rate</span></span>  <br/> |<span data-ttu-id="b0cfa-186">8 pro Minute</span><span class="sxs-lookup"><span data-stu-id="b0cfa-186">8 per minute</span></span>  <br/> |<span data-ttu-id="b0cfa-187">1 pro Minute</span><span class="sxs-lookup"><span data-stu-id="b0cfa-187">1 per minute</span></span>  <br/> |
|<span data-ttu-id="b0cfa-188">Rate für das Abrufen geparkter Anrufe</span><span class="sxs-lookup"><span data-stu-id="b0cfa-188">Retrieve parked call rate</span></span>  <br/> |<span data-ttu-id="b0cfa-189">8 pro Minute</span><span class="sxs-lookup"><span data-stu-id="b0cfa-189">8 per minute</span></span>  <br/> |<span data-ttu-id="b0cfa-190">1 pro Minute</span><span class="sxs-lookup"><span data-stu-id="b0cfa-190">1 per minute</span></span>  <br/> |
|<span data-ttu-id="b0cfa-191">Durchschnittliche Parkdauer</span><span class="sxs-lookup"><span data-stu-id="b0cfa-191">Average park duration</span></span>  <br/> |<span data-ttu-id="b0cfa-192">60 Sekunden</span><span class="sxs-lookup"><span data-stu-id="b0cfa-192">60 seconds</span></span>  <br/> |<span data-ttu-id="b0cfa-193">60 Sekunden</span><span class="sxs-lookup"><span data-stu-id="b0cfa-193">60 seconds</span></span>  <br/> |
   

