---
title: Planen des Anruf Parks in Skype for Business
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 985dc326-0aef-4308-b98b-c1d0069311e7
description: Planung für den Parken von Anrufen in Skype for Business Server Enterprise-VoIP, wodurch Anrufe in Wartestellung gehalten und Anrufe an Abteilungen übertragen werden können. Hierzu gehören die Kapazitätsplanung, unterstützte Anrufe und unterstützte Clients.
ms.openlocfilehash: 3effeab4afef60fb7a5021206d9fc3cd0227ceb1
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2020
ms.locfileid: "41803195"
---
# <a name="plan-for-call-park-in-skype-for-business"></a><span data-ttu-id="58c59-104">Planen des Anruf Parks in Skype for Business</span><span class="sxs-lookup"><span data-stu-id="58c59-104">Plan for Call Park in Skype for Business</span></span>
 
<span data-ttu-id="58c59-105">Planung für den Parken von Anrufen in Skype for Business Server Enterprise-VoIP, wodurch Anrufe in Wartestellung gehalten und Anrufe an Abteilungen übertragen werden können.</span><span class="sxs-lookup"><span data-stu-id="58c59-105">Planning for call park in Skype for Business Server Enterprise Voice, which enables putting calls on hold and transferring calls to departments.</span></span> <span data-ttu-id="58c59-106">Hierzu gehören die Kapazitätsplanung, unterstützte Anrufe und unterstützte Clients.</span><span class="sxs-lookup"><span data-stu-id="58c59-106">Includes capacity planning, supported calls, and supported clients.</span></span>
  
<span data-ttu-id="58c59-107">Mit der Anwendung "Anruf parken" können Enterprise-VoIP-Benutzer die folgenden Aktionen ausführen:</span><span class="sxs-lookup"><span data-stu-id="58c59-107">The Call Park application enables Enterprise Voice users to do the following:</span></span>
  
- <span data-ttu-id="58c59-108">Halten eines Anrufs und anschließendes Entgegennehmen des Anrufs am selben oder an einem anderen Telefon.</span><span class="sxs-lookup"><span data-stu-id="58c59-108">Put a call on hold and then retrieve the call from the same phone or another phone.</span></span>
    
- <span data-ttu-id="58c59-109">Halten eines Anrufs, um ihn an eine Abteilung oder einen allgemeinen Bereich zu übergeben (z. B. die Vertriebsabteilung oder ein Lagerort mit einem Telefon im öffentlichen Bereich).</span><span class="sxs-lookup"><span data-stu-id="58c59-109">Put a call on hold to transfer it to a department or general area (for example, to a sales department or a warehouse where there is a common area phone).</span></span>
    
- <span data-ttu-id="58c59-110">Halten eines Anrufs, um weitere Anrufe an einem Telefon entgegennehmen zu können.</span><span class="sxs-lookup"><span data-stu-id="58c59-110">Put a call on hold and keep the original answering phone free for other calls.</span></span>
    
<span data-ttu-id="58c59-111">Wenn ein Benutzer einen Anruf parkt, übernimmt Skype for Business Server den Anruf an eine temporäre Nummer, die so genannte Orbit, in der der Anruf gehalten wird, bis er abgerufen wird, oder es ist ein Timeout. Skype for Business Server sendet die Umlaufbahn an den Benutzer, der den Anruf abgestellt hat.</span><span class="sxs-lookup"><span data-stu-id="58c59-111">When a user parks a call, Skype for Business Server transfers the call to a temporary number, called an orbit, where the call is held until it is retrieved or it times out. Skype for Business Server sends the orbit to the user who parked the call.</span></span> <span data-ttu-id="58c59-112">Zum Wiederaufnehmen des geparkten Anrufs kann der Benutzer die Orbitnummer wählen oder auf den Orbitlink oder die Schaltfläche im Fenster „Unterhaltung“ klicken.</span><span class="sxs-lookup"><span data-stu-id="58c59-112">To retrieve the parked call, the user can dial the orbit number or click the orbit link or button in the Conversation window.</span></span> 
  
<span data-ttu-id="58c59-p104">Der Benutzer, der einen Anruf geparkt hat, kann einen anderen Benutzer mithilfe eines externen Mechanismus (beispielsweise über eine Sofortnachricht oder ein Paging-System) über die Orbitnummer informieren, damit dieser Benutzer den Anruf entgegennehmen kann. Der Benutzer, der den Anruf geparkt hat, kann das Fenster „Unterhaltung“ geöffnet lassen, um eine Benachrichtigung zu erhalten, sobald der Anruf entgegengenommen wurde.</span><span class="sxs-lookup"><span data-stu-id="58c59-p104">The user who parked a call can notify someone to retrieve the call by using an external mechanism, such as instant messaging (IM) or a paging system, to communicate the orbit number to someone else. The user who parked the call can leave the Conversation window open to receive notification when the call is retrieved.</span></span>
  
<span data-ttu-id="58c59-115">Da die Umlaufbahn Bereiche global eindeutig sind, ist es möglich, Anrufe von jeder Skype for Business Server-Website oder einem PBX-Telefon abzurufen, wenn Routing entsprechend konfiguriert ist.</span><span class="sxs-lookup"><span data-stu-id="58c59-115">Because orbit ranges are globally unique, it is possible to retrieve calls from any Skype for Business Server site or PBX phone if routing is configured appropriately.</span></span> <span data-ttu-id="58c59-116">Wenn der Anruf innerhalb einer konfigurierbaren Zeitdauer nicht wiederaufgenommen wird, wird er erneut an den Benutzer zurückgegeben, der den Anruf geparkt hat.</span><span class="sxs-lookup"><span data-stu-id="58c59-116">If no one retrieves the call within a configurable amount of time, the call rings back to the person who parked it.</span></span> <span data-ttu-id="58c59-117">Wenn dieser Benutzer den Anruf nicht beantwortet, wird er an ein Fallbackziel übergeben (z. B. einen Agent), sofern dies konfiguriert wurde.</span><span class="sxs-lookup"><span data-stu-id="58c59-117">If that person does not answer the ringback, the call is transferred to a fallback destination, such as to an operator, if so configured.</span></span> <span data-ttu-id="58c59-118">Sie können konfigurieren, wie oft das Telefon erneut läutet (ein- bis zehnmal), bevor der Anruf weitergeleitet wird.</span><span class="sxs-lookup"><span data-stu-id="58c59-118">You can configure the number of times the call rings back before being transferred from one to ten times.</span></span> <span data-ttu-id="58c59-119">Wenn ein weitergeleiteter Anruf nicht entgegengenommen wird, wird die Verbindung unterbrochen.</span><span class="sxs-lookup"><span data-stu-id="58c59-119">If no one answers a transferred call, the call is disconnected.</span></span> <span data-ttu-id="58c59-120">Wenn der Anruf entgegengenommen oder die Verbindung unterbrochen wird, wird der Orbit erneut freigegeben.</span><span class="sxs-lookup"><span data-stu-id="58c59-120">The orbit is freed when the call is retrieved or disconnected.</span></span>
  
<span data-ttu-id="58c59-121">Wenn Sie die Funktion zum Parken von Anrufen bereitstellen, müssen Sie Durchwahlnummernbereiche zum Parken von Anrufen reservieren.</span><span class="sxs-lookup"><span data-stu-id="58c59-121">When you deploy Call Park, you need to reserve ranges of extension numbers for parking calls.</span></span> <span data-ttu-id="58c59-122">Bei diesen Durchwahlnummern muss es sich um virtuelle Durchwahlnummern handeln, also solche, denen kein Benutzer oder Telefon zugewiesen ist.</span><span class="sxs-lookup"><span data-stu-id="58c59-122">These extensions need to be virtual extensions: extensions that have no user or phone assigned to them.</span></span> <span data-ttu-id="58c59-123">Anschließend konfigurieren Sie die Orbittabelle für das Parken von Anrufen mit den Durchwahlnummernbereichen und geben an, welcher Anwendungsdienst die Anwendung zum Parken von Anrufen hostet, die die einzelnen Bereiche verarbeitet.</span><span class="sxs-lookup"><span data-stu-id="58c59-123">You then configure the call park orbit table with the ranges of extension numbers and specify which Application service hosts the Call Park application that handles each range.</span></span> <span data-ttu-id="58c59-124">Jeder Front-End-Pool verfügt über eine Anruf Park Tabelle auf dem entsprechenden Back-End-Server, der zum Verwalten von Anrufen dient, die auf dem Pool abgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="58c59-124">Each Front End pool has a Call Park table on the corresponding Back End Server that is used to manage calls that are parked on the pool.</span></span> <span data-ttu-id="58c59-125">Die Liste der Umlaufbahn Bereiche wird im zentralen Verwaltungsspeicher gespeichert und zum Weiterleiten von Umlaufbahnen an den Ziel Pool verwendet.</span><span class="sxs-lookup"><span data-stu-id="58c59-125">The list of orbit ranges is stored in Central Management store and is used to route orbits to the destination pool.</span></span> <span data-ttu-id="58c59-126">Jeder Skype for Business-Server Pool, in dem die Anwendung für das Parken von Anrufen bereitgestellt und konfiguriert ist, kann einen oder mehrere Umlaufbahn Bereiche aufweisen.</span><span class="sxs-lookup"><span data-stu-id="58c59-126">Each Skype for Business Server pool where the Call Park application is deployed and configured can have one or more orbit ranges.</span></span> <span data-ttu-id="58c59-127">Umlaufbahn Bereiche müssen in der Skype for Business Server-Bereitstellung global eindeutig sein.</span><span class="sxs-lookup"><span data-stu-id="58c59-127">Orbit ranges must be globally unique across the Skype for Business Server deployment.</span></span> 
  
<span data-ttu-id="58c59-p107">Sie können darüber hinaus weitere Einstellungen für das Parken von Anrufen konfigurieren, wie z. B., an welches Ziel Anrufe bei einem Timeout umgeleitet werden und ob für den Anrufer Musik wiedergegeben wird, während der Anruf geparkt ist. Außerdem können Sie die Musikdatei angeben, die beim Parken des Anrufs wiedergegeben wird.</span><span class="sxs-lookup"><span data-stu-id="58c59-p107">You also configure other Call Park settings, such as where calls are redirected if they time out and whether the person on the phone hears music while parked. You can also specify the music file to play while the call is on hold.</span></span>
  
> [!NOTE]
> <span data-ttu-id="58c59-130">Angepasste Musik-in-situ-Dateien für den Parken von Anrufen werden nicht im Rahmen des Disaster Recovery-Prozesses von Skype for Business Server gesichert und gehen verloren, wenn die Dateien, die in den Pool hochgeladen wurden, beschädigt, beschädigt oder gelöscht wurden.</span><span class="sxs-lookup"><span data-stu-id="58c59-130">Customized music-on-hold files for Call Park are not backed up as part of the Skype for Business Server disaster recovery process and will be lost if the files uploaded to the pool are damaged, corrupted, or erased.</span></span> <span data-ttu-id="58c59-131">Bewahren Sie stets eine separate Sicherungskopie der für geparkte Anrufe hochgeladenen angepassten Musikdateien auf.</span><span class="sxs-lookup"><span data-stu-id="58c59-131">Always keep a separate backup copy of the customized music-on-hold files that you have uploaded for Call Park.</span></span> 
  
<span data-ttu-id="58c59-132">Die Anwendung zum Parken von Anrufen ist eine Enterprise-VoIP-Komponente.</span><span class="sxs-lookup"><span data-stu-id="58c59-132">The Call Park application is a component of Enterprise Voice.</span></span> <span data-ttu-id="58c59-133">Wenn Sie Enterprise-VoIP bereitstellen, wird die Anwendung für den Anruf Park automatisch installiert und aktiviert.</span><span class="sxs-lookup"><span data-stu-id="58c59-133">When you deploy Enterprise Voice, the Call Park application is installed and activated automatically.</span></span> <span data-ttu-id="58c59-134">Bevor Sie den Anruf Park verwenden können, muss der Enterprise Voice-Administrator ihn aber über die VoIP-Richtlinie konfigurieren und für die Benutzer aktivieren.</span><span class="sxs-lookup"><span data-stu-id="58c59-134">Before you can use Call Park, however, the Enterprise Voice administrator must configure it and enable it for users through voice policy.</span></span>
  
## <a name="deployment-and-requirements"></a><span data-ttu-id="58c59-135">Bereitstellung und Anforderungen</span><span class="sxs-lookup"><span data-stu-id="58c59-135">Deployment and requirements</span></span>

<span data-ttu-id="58c59-136">Die Anwendung Parken wird automatisch installiert, wenn Sie Enterprise-VoIP bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="58c59-136">The Call Park application is automatically installed when you deploy Enterprise Voice.</span></span> <span data-ttu-id="58c59-137">Sie aktivieren den Anruf Park durch Konfigurieren der VoIP-Richtlinie.</span><span class="sxs-lookup"><span data-stu-id="58c59-137">You enable Call Park by configuring voice policy.</span></span>
  
### <a name="software-requirements"></a><span data-ttu-id="58c59-138">Softwareanforderungen</span><span class="sxs-lookup"><span data-stu-id="58c59-138">Software requirements</span></span>

<span data-ttu-id="58c59-139">Auf allen Front-End-Servern und Standard Edition-Servern, auf denen der Anruf Park bereitgestellt wird, muss die Windows Media-Format Laufzeit für Server mit Windows Server 2008 R2 oder Microsoft Media Foundation für Server mit Windows Server 2012 oder Windows Server installiert sein. 2012 R2.</span><span class="sxs-lookup"><span data-stu-id="58c59-139">All Front End Servers and Standard Edition servers where Call Park is deployed must have the Windows Media Format Runtime installed for servers running Windows Server 2008 R2, or Microsoft Media Foundation for servers running Windows Server 2012 or Windows Server 2012 R2.</span></span> <span data-ttu-id="58c59-140">Für Windows Server 2008 R2 wird die Windows Media-Format Laufzeit als Teil der Windows-Desktop Oberfläche installiert.</span><span class="sxs-lookup"><span data-stu-id="58c59-140">For Windows Server 2008 R2, Windows Media Format Runtime is installed as part of Windows Desktop Experience.</span></span> <span data-ttu-id="58c59-141">Windows Media Format Runtime oder Microsoft Media Foundation ist für Windows Media Audio-Dateien (WMA) erforderlich, in denen Park Wiedergaben für Musik im Wartebereich aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="58c59-141">Windows Media Format Runtime or Microsoft Media Foundation is required for Windows Media Audio (.wma) files that Call Park plays for music on hold.</span></span>
  
### <a name="port-requirements"></a><span data-ttu-id="58c59-142">Portanforderungen</span><span class="sxs-lookup"><span data-stu-id="58c59-142">Port requirements</span></span>

<span data-ttu-id="58c59-143">Die Anwendung für den Anruf Park verwendet **Port 5075** für SIP-Abhör Anforderungen.</span><span class="sxs-lookup"><span data-stu-id="58c59-143">The Call Park application uses **Port 5075**  for SIP listening requests.</span></span>
    
> [!NOTE]
> <span data-ttu-id="58c59-144">Dieser Port ist die Standardeinstellung, die Sie mit dem Cmdlet **Set-CsApplicationServer** ändern können.</span><span class="sxs-lookup"><span data-stu-id="58c59-144">This port is a default setting that you can change by using the **Set-CsApplicationServer** cmdlet.</span></span> <span data-ttu-id="58c59-145">Details zu diesem Cmdlet finden Sie in der Dokumentation zur lync Server-Verwaltungsshell.</span><span class="sxs-lookup"><span data-stu-id="58c59-145">For details about this cmdlet, see the Lync Server Management Shell documentation.</span></span>
  
### <a name="audio-file-requirements"></a><span data-ttu-id="58c59-146">Anforderungen für Audiodateien</span><span class="sxs-lookup"><span data-stu-id="58c59-146">Audio File requirements</span></span>

<span data-ttu-id="58c59-147">Die Anwendung "Parken" unterstützt nur WMA-Dateien (Windows Media Audio) für Musik in Wartestellung.</span><span class="sxs-lookup"><span data-stu-id="58c59-147">The Call Park application supports only Windows Media Audio (.wma) files for music on hold.</span></span> <span data-ttu-id="58c59-148">Sie können den Microsoft Expression Encoder 4 verwenden, um Dateien für Musik in Wartestellung anzupassen.</span><span class="sxs-lookup"><span data-stu-id="58c59-148">You can use the Microsoft Expression Encoder 4 to customize files for music on hold.</span></span> <span data-ttu-id="58c59-149">Informationen zum Herunterladen von Expression Encoder 4 finden Sie unter ["Expression Encoder 4"](https://go.microsoft.com/fwlink/p/?linkId=202843).</span><span class="sxs-lookup"><span data-stu-id="58c59-149">To download Expression Encoder 4, see   ["Expression Encoder 4"](https://go.microsoft.com/fwlink/p/?linkId=202843).</span></span> <span data-ttu-id="58c59-150">Verwenden Sie das Tool, um die Datei in ein WMA-Format umzuwandeln.</span><span class="sxs-lookup"><span data-stu-id="58c59-150">Use the tool to convert the file to a .wma format.</span></span> <span data-ttu-id="58c59-151">Das empfohlene Format für Music-on-halten-Dateien im Parken von anrufen ist Media Audio 9, 44 kHz, 16 Bits, Mono, CBR, 32 Kbit/s.</span><span class="sxs-lookup"><span data-stu-id="58c59-151">The recommended format for Call Park music-on-hold files is Media Audio 9, 44 kHz, 16 bits, Mono, CBR, 32 kbps.</span></span>
  
> [!NOTE]
> <span data-ttu-id="58c59-152">Die konvertierte Datei wird über das Telefon nur mit 16 kHz abgespielt, auch wenn sie mit 44 kHz aufgezeichnet wurde.</span><span class="sxs-lookup"><span data-stu-id="58c59-152">The converted file plays over the phone only at 16 kHz, even if it was recorded at 44 kHz.</span></span> 
  
## <a name="supported-clients-and-calls"></a><span data-ttu-id="58c59-153">Unterstützte Clients und Anrufe</span><span class="sxs-lookup"><span data-stu-id="58c59-153">Supported clients and calls</span></span>

<span data-ttu-id="58c59-154">Die folgenden Clients und Anrufarten werden für den Parken von Anrufen unterstützt.</span><span class="sxs-lookup"><span data-stu-id="58c59-154">The following clients and types of calls are supported for Call Park</span></span>
  
### <a name="clients-supported-for-parking-calls"></a><span data-ttu-id="58c59-155">Für das Parken von Anrufen unterstützte Clients</span><span class="sxs-lookup"><span data-stu-id="58c59-155">Clients Supported for Parking Calls</span></span>

<span data-ttu-id="58c59-156">Anrufe von IP-, Nebenstellen-, Festnetz- oder Mobiltelefonen können geparkt werden.</span><span class="sxs-lookup"><span data-stu-id="58c59-156">Calls from any IP, private branch exchange (PBX), public switched telephone network (PSTN), or mobile phone can be parked.</span></span>
  
> [!NOTE]
> <span data-ttu-id="58c59-p114">Nur Audioanrufe können geparkt werden. Das Parken von Chatnachrichten und Konferenzen ist nicht möglich.</span><span class="sxs-lookup"><span data-stu-id="58c59-p114">Only audio calls can be parked. Instant messages and conferences cannot be parked.</span></span> 
  
<span data-ttu-id="58c59-159">Die folgenden Clients können den Anruf Park zum Parken von Anrufen verwenden:</span><span class="sxs-lookup"><span data-stu-id="58c59-159">The following clients can use Call Park to park calls:</span></span>
  
- <span data-ttu-id="58c59-160">Skype for Business</span><span class="sxs-lookup"><span data-stu-id="58c59-160">Skype for Business</span></span>
    
- <span data-ttu-id="58c59-161">Lync 2013</span><span class="sxs-lookup"><span data-stu-id="58c59-161">Lync 2013</span></span>
    
- <span data-ttu-id="58c59-162">Lync 2010</span><span class="sxs-lookup"><span data-stu-id="58c59-162">Lync 2010</span></span>
    
- <span data-ttu-id="58c59-163">Lync 2010 Attendant</span><span class="sxs-lookup"><span data-stu-id="58c59-163">Lync 2010 Attendant</span></span>
    
- <span data-ttu-id="58c59-164">Lync Phone Edition</span><span class="sxs-lookup"><span data-stu-id="58c59-164">Lync Phone Edition</span></span>
    
> [!NOTE]
> <span data-ttu-id="58c59-165">Mobiltelefone können den Anruf Park nicht zum Parken von Anrufen verwenden.</span><span class="sxs-lookup"><span data-stu-id="58c59-165">Mobile phones cannot use Call Park to park calls.</span></span> 
  
### <a name="clients-supported-for-retrieving-calls"></a><span data-ttu-id="58c59-166">Für das Wiederaufnehmen geparkter Anrufe unterstützte Clients</span><span class="sxs-lookup"><span data-stu-id="58c59-166">Clients Supported for Retrieving Calls</span></span>

<span data-ttu-id="58c59-p115">Orbitbereiche werden als Blöcke virtueller Durchwahlnummern (Durchwahlnummern, denen kein Benutzer oder Telefon zugewiesen ist) konfiguriert. Wenn Sie Orbits als virtuelle Durchwahlnummern konfigurieren, können Mobil- und Festnetztelefone keine geparkten Anrufe wiederaufnehmen.</span><span class="sxs-lookup"><span data-stu-id="58c59-p115">Orbit ranges are configured as blocks of virtual extensions (extensions without an assigned user or phone). When you configure orbits as virtual extensions, mobile phones and PSTN phones cannot retrieve parked calls.</span></span>
  
<span data-ttu-id="58c59-169">Das Wiederaufnehmen geparkter Anrufe durch Partnerbenutzer ist nicht möglich.</span><span class="sxs-lookup"><span data-stu-id="58c59-169">Federated users cannot retrieve parked calls.</span></span>
  
<span data-ttu-id="58c59-170">Die folgenden Clients können Anrufe abrufen, die im Park des Anrufs abgestellt sind:</span><span class="sxs-lookup"><span data-stu-id="58c59-170">The following clients can retrieve calls that are parked on Call Park:</span></span>
  
- <span data-ttu-id="58c59-171">Skype for Business</span><span class="sxs-lookup"><span data-stu-id="58c59-171">Skype for Business</span></span>
    
- <span data-ttu-id="58c59-172">Lync 2013</span><span class="sxs-lookup"><span data-stu-id="58c59-172">Lync 2013</span></span>
    
- <span data-ttu-id="58c59-173">Lync 2010</span><span class="sxs-lookup"><span data-stu-id="58c59-173">Lync 2010</span></span>
    
- <span data-ttu-id="58c59-174">Lync 2010 Attendant</span><span class="sxs-lookup"><span data-stu-id="58c59-174">Lync 2010 Attendant</span></span>
    
- <span data-ttu-id="58c59-175">Lync Phone Edition</span><span class="sxs-lookup"><span data-stu-id="58c59-175">Lync Phone Edition</span></span>
    
- <span data-ttu-id="58c59-176">IP-Telefone in öffentlichen Bereichen</span><span class="sxs-lookup"><span data-stu-id="58c59-176">IP common area phones</span></span>
    
- <span data-ttu-id="58c59-177">Nicht-IP-Telefone, die mit der Skype for Business Server-Infrastruktur verbunden sind, einschließlich Telefone im öffentlichen Bereich und Private Branch Exchange (PBX)-Telefone</span><span class="sxs-lookup"><span data-stu-id="58c59-177">Non-IP phones that are connected to the Skype for Business Server infrastructure, including common area phones and private branch exchange (PBX) phones</span></span>
    
## <a name="call-park-capacity-planning"></a><span data-ttu-id="58c59-178">Kapazitätsplanung für das Parken von Anrufen</span><span class="sxs-lookup"><span data-stu-id="58c59-178">Call Park capacity planning</span></span>

<span data-ttu-id="58c59-179">In der folgenden Tabelle wird das Benutzermodell des Anruf Parks beschrieben, das Sie als Grundlage für die Kapazitäts Planungsanforderungen verwenden können.</span><span class="sxs-lookup"><span data-stu-id="58c59-179">The following table describes the Call Park user model that you can use as the basis for capacity planning requirements.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="58c59-180">Beachten Sie, dass für die Planung von Disaster Recovery-Kapazität jeder Pool eines gekoppelten Pools in der Lage sein sollte, die Arbeitslasten für die Dienste des Anruf Parks in beiden Pools zu behandeln.</span><span class="sxs-lookup"><span data-stu-id="58c59-180">Keep in mind that, for disaster recovery capacity planning, each pool of a paired pool should be able to handle the workloads for Call Park services in both pools.</span></span> 
  
<span data-ttu-id="58c59-181">**Benutzermodell der Funktion zum Parken von Anrufen**</span><span class="sxs-lookup"><span data-stu-id="58c59-181">**Call Park User Model**</span></span>

|<span data-ttu-id="58c59-182">**Metrik**</span><span class="sxs-lookup"><span data-stu-id="58c59-182">**Metric**</span></span>|<span data-ttu-id="58c59-183">**Pro Front-End <br/> -Pool (mit 8 Front-End-Servern)**</span><span class="sxs-lookup"><span data-stu-id="58c59-183">**Per Front End pool  <br/>  (with 8 Front End Servers)**</span></span>|<span data-ttu-id="58c59-184">**Pro Standard Edition-Server**</span><span class="sxs-lookup"><span data-stu-id="58c59-184">**Per Standard Edition server**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="58c59-185">Rate für das Parken von Anrufen</span><span class="sxs-lookup"><span data-stu-id="58c59-185">Park rate</span></span>  <br/> |<span data-ttu-id="58c59-186">8 pro Minute</span><span class="sxs-lookup"><span data-stu-id="58c59-186">8 per minute</span></span>  <br/> |<span data-ttu-id="58c59-187">1 pro Minute</span><span class="sxs-lookup"><span data-stu-id="58c59-187">1 per minute</span></span>  <br/> |
|<span data-ttu-id="58c59-188">Rate für das Abrufen geparkter Anrufe</span><span class="sxs-lookup"><span data-stu-id="58c59-188">Retrieve parked call rate</span></span>  <br/> |<span data-ttu-id="58c59-189">8 pro Minute</span><span class="sxs-lookup"><span data-stu-id="58c59-189">8 per minute</span></span>  <br/> |<span data-ttu-id="58c59-190">1 pro Minute</span><span class="sxs-lookup"><span data-stu-id="58c59-190">1 per minute</span></span>  <br/> |
|<span data-ttu-id="58c59-191">Durchschnittliche Parkdauer</span><span class="sxs-lookup"><span data-stu-id="58c59-191">Average park duration</span></span>  <br/> |<span data-ttu-id="58c59-192">60 Sekunden</span><span class="sxs-lookup"><span data-stu-id="58c59-192">60 seconds</span></span>  <br/> |<span data-ttu-id="58c59-193">60 Sekunden</span><span class="sxs-lookup"><span data-stu-id="58c59-193">60 seconds</span></span>  <br/> |
   

