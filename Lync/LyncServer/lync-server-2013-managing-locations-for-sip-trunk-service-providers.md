---
title: 'Lync Server 2013: Verwalten von Speicherorten für SIP-Trunk Dienstanbieter'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Managing locations for SIP trunk service providers
ms:assetid: d9b33b56-66c2-4dee-b056-faaf98925bf2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398959(v=OCS.15)
ms:contentKeyID: 48185548
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f27eeac11006eab2209bb5491d991a677e3a2887
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/21/2020
ms.locfileid: "42218081"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="managing-locations-for-sip-trunk-service-providers-in-lync-server-2013"></a><span data-ttu-id="76244-102">Verwalten von Speicherorten für SIP-Trunk Dienstanbieter in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="76244-102">Managing locations for SIP trunk service providers in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="76244-103">_**Letztes Änderungsstand des Themas:** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="76244-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="76244-104">Um lync Server so zu konfigurieren, dass Clients in einem Netzwerk automatisch gefunden werden, müssen Sie entweder die Standortinformationsdienst Datenbank mit einem Netzwerk Wiremap auffüllen und die Speicherorte veröffentlichen oder eine Verbindung mit einer externen Datenbank herstellen, die bereits die richtige enthält. Zuordnungen.</span><span class="sxs-lookup"><span data-stu-id="76244-104">To configure Lync Server to automatically locate clients within a network, you need to either populate the Location Information service database with a network wiremap and publish the locations, or link to an external database that already contains the correct mappings.</span></span> <span data-ttu-id="76244-105">Im Rahmen dieses Vorgangs müssen Sie die Adressen der Standorte mit Ihrem E9-1-1-Dienstanbieter abgleichen.</span><span class="sxs-lookup"><span data-stu-id="76244-105">As part of this process, you need to validate the civic addresses of the locations with your E9-1-1 service provider.</span></span> <span data-ttu-id="76244-106">Ausführliche Informationen finden Sie unter [Konfigurieren der Standortdatenbank in lync Server 2013](lync-server-2013-configure-the-location-database.md) in der Bereitstellungsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="76244-106">For details, see [Configure the location database in Lync Server 2013](lync-server-2013-configure-the-location-database.md) in the Deployment documentation.</span></span>

<span data-ttu-id="76244-107">Die Datenbank des Standortinformationsdiensts füllen Sie mit einem Emergency Response Location (ERL) auf, der aus der allgemeinen Adresse und der spezifischen Adresse innerhalb eines Gebäudes besteht.</span><span class="sxs-lookup"><span data-stu-id="76244-107">You populate the Location Information service database with an Emergency Response Location (ERL), which consists of a civic address and the specific address within a building.</span></span> <span data-ttu-id="76244-108">Das Feld Standortinformationsdienst **Speicherort** , bei dem es sich um eine bestimmte Position innerhalb eines Gebäudes handelt, weist eine maximale Länge von 20 Zeichen (einschließlich Leerzeichen) auf.</span><span class="sxs-lookup"><span data-stu-id="76244-108">The Location Information service **Location** field, which is the specific location within a building, has a maximum length of 20 characters (including spaces).</span></span> <span data-ttu-id="76244-109">In diesem Feld mit begrenzter Länge sollten Sie Folgendes angeben:</span><span class="sxs-lookup"><span data-stu-id="76244-109">Within that limited length, try to include the following:</span></span>

  - <span data-ttu-id="76244-p103">Einen leicht verständlichen Namen für den Standort des Notfallanrufers, um sicherzustellen, dass Notrufempfänger den Standort unverzüglich auffinden, wenn sie an der durchgegebenen Adresse eintreffen. Dieser Standortname kann die Hausnummer, das Stockwerk, den Gebäudetrakt, die Zimmernummer usw. beinhalten. Vermeiden Sie Spitznamen, die nur Mitarbeiter kennen und dazu führen könnten, dass sich Notrufempfänger zur falschen Adresse begeben.</span><span class="sxs-lookup"><span data-stu-id="76244-p103">An easy-to-understand name that identifies the location of the 911 caller to help ensure that emergency responders find the specific location promptly when they arrive at the civic address. This location name may include a building number, floor number, wing designator, room number, and so on. Avoid nicknames known only to employees, which might cause emergency responders to go to the wrong location.</span></span>

  - <span data-ttu-id="76244-113">Eine Standort-ID, mit der Benutzer leicht erkennen können, dass Ihr lync-Client den richtigen Speicherort ausgewählt hat.</span><span class="sxs-lookup"><span data-stu-id="76244-113">A location identifier that helps users to easily see that their Lync client picked up the correct location.</span></span> <span data-ttu-id="76244-114">Der lync-Client verkettet automatisch die Felder ermittelter **Speicherort** und **Ort** in der Kopfzeile und zeigt diese an.</span><span class="sxs-lookup"><span data-stu-id="76244-114">The Lync client automatically concatenates and displays the discovered **Location** and **City** fields in its header.</span></span> <span data-ttu-id="76244-115">Es empfiehlt sich, die Straßenadresse des Gebäudes zu jeder Standort-ID hinzuzufügen (beispielsweise "Straßennummer \<\>1. Etage").</span><span class="sxs-lookup"><span data-stu-id="76244-115">A good practice is to add the street address of the building to each location identifier (for example, "1st Floor \<street number\>").</span></span> <span data-ttu-id="76244-116">Ohne die Straßenadresse kann ein allgemeiner Standort Bezeichner wie "1. OG" auf alle Gebäude in der Stadt angewendet werden.</span><span class="sxs-lookup"><span data-stu-id="76244-116">Without the street address, a generic location identifier such as "1st Floor" could apply to any building in the city.</span></span>

  - <span data-ttu-id="76244-117">Wenn es sich um eine ungefähre Standortangabe handelt, da der Standort von einem Funkzugriffspunkt ermittelt wird, können Sie das Wort Near (Ca.) hinzufügen (z. B. "Ca. 1. Stock 1234").</span><span class="sxs-lookup"><span data-stu-id="76244-117">If the location is approximate because it’s determined by a wireless access point, you can add the word Near (for example, "Near 1st Floor 1234").</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="76244-118">Speicherorte, die der zentralen Standortdatenbank hinzugefügt wurden, stehen dem Client erst zur Verfügung, wenn Sie mithilfe eines lync Server-Verwaltungsshell-Befehls veröffentlicht werden und in die lokalen Speicher des Pools repliziert werden.</span><span class="sxs-lookup"><span data-stu-id="76244-118">Locations added to the central location database are not available to the client until they are published by using a Lync Server Management Shell command and are replicated to the pool's local stores.</span></span> <span data-ttu-id="76244-119">Ausführliche Informationen finden Sie unter <A href="lync-server-2013-publish-the-location-database.md">Veröffentlichen der Standortdatenbank aus lync Server 2013</A> in der Bereitstellungsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="76244-119">For details, see <A href="lync-server-2013-publish-the-location-database.md">Publish the location database from Lync Server 2013</A> in the Deployment documentation.</span></span>



</div>

<span data-ttu-id="76244-120">In den folgenden Abschnitten erfahren Sie, was Sie beim Auffüllen und Verwalten der Standortdatenbank bedenken müssen.</span><span class="sxs-lookup"><span data-stu-id="76244-120">The following sections discuss considerations that you need to take into account when populating and maintaining the location database.</span></span>

<div>

## <a name="populating-the-location-database"></a><span data-ttu-id="76244-121">Auffüllen der Standortdatenbank</span><span class="sxs-lookup"><span data-stu-id="76244-121">Populating the Location Database</span></span>

<span data-ttu-id="76244-122">Die folgenden Fragen helfen Ihnen zu bestimmen, wie die Standortdatenbank aufgefüllt werden soll.</span><span class="sxs-lookup"><span data-stu-id="76244-122">The following questions can help you determine how to populate the location database.</span></span>

  - <span data-ttu-id="76244-123">**Welches Verfahren verwenden Sie zum Auffüllen der Standortdatenbank?**</span><span class="sxs-lookup"><span data-stu-id="76244-123">**What process will you use to populate the location database?**</span></span>  
    <span data-ttu-id="76244-p106">Wo befinden sich die Daten, und welche Schritte müssen Sie ausführen, um die Daten in das für die Standortdatenbank erforderliche Format zu konvertieren? Werden die Standorte einzeln oder mithilfe einer CSV-Datei per Massenvorgang hinzugefügt?</span><span class="sxs-lookup"><span data-stu-id="76244-p106">Where does the data exist, and what steps do you need to take to convert the data into the format required by the location database? Will you add locations individually, or in bulk, by using a CSV file?</span></span>

<!-- end list -->

  - <span data-ttu-id="76244-126">**Verfügen Sie über eine Drittanbieterdatenbank, die bereits Standortzuordnungen enthält?**</span><span class="sxs-lookup"><span data-stu-id="76244-126">**Do you have a third party database that already contains a mapping of locations?**</span></span>  
    <span data-ttu-id="76244-127">Mithilfe der sekundären Standortinformationsdienst-Option von lync Server zum Herstellen einer Verbindung mit einer Drittanbieterdatenbank können Sie Standorte mithilfe einer Offline Plattform gruppieren und verwalten.</span><span class="sxs-lookup"><span data-stu-id="76244-127">By using Lync Server's Secondary Location Information service option to connect to a third-party database, you can group and manage locations by using an offline platform.</span></span> <span data-ttu-id="76244-128">Der Vorteil dieses Ansatzes ist, dass Sie Standorte nicht nur Netzwerk-IDs, sondern auch einem Benutzer zuordnen können.</span><span class="sxs-lookup"><span data-stu-id="76244-128">A benefit to this approach is that in addition to associating locations to network identifiers, you can associate locations to a user.</span></span> <span data-ttu-id="76244-129">Dies bedeutet, dass der Standortinformationsdienst mehrere Adressen zurückgeben kann, die aus dem sekundären Standortinformationsdienst stammen, an einen lync Server-Client.</span><span class="sxs-lookup"><span data-stu-id="76244-129">This means that the Location Information service can return multiple addresses, originating from the Secondary Location Information service, to a Lync Server client.</span></span> <span data-ttu-id="76244-130">Der Benutzer kann dann den am besten geeigneten Standort wählen.</span><span class="sxs-lookup"><span data-stu-id="76244-130">The user can then choose the most appropriate location.</span></span>
    
    <span data-ttu-id="76244-131">Für die Integration in die Standortinformationsdienst muss die Drittanbieterdatenbank dem lync Server standortanforderung/Antwortschema entsprechen.</span><span class="sxs-lookup"><span data-stu-id="76244-131">To integrate with the Location Information service, the third-party database must follow the Lync Server Location Request/Response schema.</span></span> <span data-ttu-id="76244-132">Ausführliche Informationen finden Sie unter\["MS-\]E911WS: Webdienst für E911-Support Protokoll Spezifikation" <https://go.microsoft.com/fwlink/p/?linkid=213819>unter.</span><span class="sxs-lookup"><span data-stu-id="76244-132">For details, see "\[MS-E911WS\]: Web Service for E911 Support Protocol Specification" at <https://go.microsoft.com/fwlink/p/?linkid=213819>.</span></span> <span data-ttu-id="76244-133">Ausführliche Informationen zum Bereitstelleneiner sekundären Standortinformationsdienst finden Sie unter [Configure a Secondary Standortinformationsdienst in lync Server 2013](lync-server-2013-configure-a-secondary-location-information-service.md) in der Bereitstellungsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="76244-133">For details about deploying a Secondary Location Information service, see [Configure a secondary Location Information service in Lync Server 2013](lync-server-2013-configure-a-secondary-location-information-service.md) in the Deployment documentation.</span></span>

<span data-ttu-id="76244-134">Ausführliche Informationen zum Auffüllen der Standortdatenbank finden Sie unter [configure the Location Database in lync Server 2013](lync-server-2013-configure-the-location-database.md) in der Bereitstellungsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="76244-134">For details about populating the location database, see [Configure the location database in Lync Server 2013](lync-server-2013-configure-the-location-database.md) in the Deployment documentation.</span></span>

</div>

<div>

## <a name="maintaining-the-location-database"></a><span data-ttu-id="76244-135">Verwalten der Standortdatenbank</span><span class="sxs-lookup"><span data-stu-id="76244-135">Maintaining the Location Database</span></span>

<span data-ttu-id="76244-p109">Nach dem Auffüllen der Standortdatenbank müssen Sie eine Strategie zum Aktualisieren der Datenbank entwickeln, um Änderungen an der Netzwerkkonfiguration umzusetzen. Die folgenden Fragen helfen Ihnen zu bestimmen, wie die Standortdatenbank verwaltet werden soll.</span><span class="sxs-lookup"><span data-stu-id="76244-p109">After you populate the location database, you need to develop a strategy for updating the database as the network configuration changes. The following questions will help you determine how to maintain the location database.</span></span>

  - <span data-ttu-id="76244-138">**Wie aktualisieren Sie die Standortdatenbank?**</span><span class="sxs-lookup"><span data-stu-id="76244-138">**How will you update the location database?**</span></span>  
    <span data-ttu-id="76244-p110">Eine Aktualisierung der Standortdatenbank kann in verschiedenen Situationen notwendig sein, etwa beim Hinzufügen von Funkzugriffspunkten, bei einer Neuverkabelung des Büros (mit neuen Switchzuordnungen) und bei einer Subnetzerweiterung. Aktualisieren Sie jeden Standort sofort, oder führen Sie mithilfe einer CSV-Datei eine Aktualisierung aller Standorte per Massenvorgang durch?</span><span class="sxs-lookup"><span data-stu-id="76244-p110">There are several scenarios that require an update to the location database, including adding WAPs, office recabling (resulting in different switch assignments), and subnet expansion. Will you directly update each individual location, or will you perform a bulk update of all the locations by using a CSV file?</span></span>

<!-- end list -->

  - <span data-ttu-id="76244-141">**Verwenden Sie eine SNMP-Anwendung zum Abgleich von Lync-Client-MAC-Adressen mit den Port- und Switchbezeichnern?**</span><span class="sxs-lookup"><span data-stu-id="76244-141">**Will you use an SNMP application to match Lync client MAC addresses to port and switch identifiers?**</span></span>  
    <span data-ttu-id="76244-142">Wenn Sie eine SNMP-Anwendung verwenden, müssen Sie ein manuelles Verfahren ausarbeiten, um die Konsistenz der Switch- und Portinformationen zwischen der SNMP-Anwendung und der Standortdatenbank sicherzustellen.</span><span class="sxs-lookup"><span data-stu-id="76244-142">If you use an SNMP application, you need to develop a manual process for keeping the switch chassis and port information consistent between the SNMP application and the location database.</span></span> <span data-ttu-id="76244-143">Wenn die SNMP-Anwendung eine Gehäuse-IP-Adresse oder Port-ID zurückgibt, die nicht in der Datenbank enthalten ist, kann der Standortinformationsdienst keinen Standort an den Client zurückgeben.</span><span class="sxs-lookup"><span data-stu-id="76244-143">If the SNMP application returns a chassis IP address or port ID that is not included in the database, the Location Information service will not be able to return a location to the client.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

