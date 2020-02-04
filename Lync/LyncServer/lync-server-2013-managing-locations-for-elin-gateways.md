---
title: 'Lync Server 2013: Verwalten von Speicherorten für Elin-Gateways'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Managing locations for ELIN gateways
ms:assetid: ced79c13-4e7e-4034-95cd-6fc913f4f222
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205288(v=OCS.15)
ms:contentKeyID: 48185496
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ba5a7e9067e4cd59ca42e60c620dbb4e8ee5b901
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41762103"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="managing-locations-for-elin-gateways-in-lync-server-2013"></a><span data-ttu-id="249df-102">Verwalten von Speicherorten für Elin-Gateways in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="249df-102">Managing locations for ELIN gateways in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="249df-103">_**Letztes Änderungsdatum des Themas:** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="249df-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="249df-104">Damit lync Server automatisch Speicherorte für Clients in einem Netzwerk bereitstellt, müssen Sie die folgenden Aufgaben ausführen:</span><span class="sxs-lookup"><span data-stu-id="249df-104">To have Lync Server automatically provide locations for clients within a network, you need to perform the following tasks:</span></span>

  - <span data-ttu-id="249df-105">Füllen Sie die Datenbank des Standort Informationsdiensts mit einem Netzwerk-Wiremap, und fügen Sie die Notfall Standort-Identifikationsnummern (Elins) in das Feld Firma ein.</span><span class="sxs-lookup"><span data-stu-id="249df-105">Populate the Location Information service database with a network wiremap, and include the Emergency Location Identification Numbers (ELINs) in the CompanyName field.</span></span>

  - <span data-ttu-id="249df-106">Veröffentlichen Sie die Standorte, damit sie für Clients in Ihrem Netzwerk verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="249df-106">Publish the locations so that they are available for clients in your network.</span></span>

  - <span data-ttu-id="249df-107">Laden Sie die ELINs in die ALI (Automatic Location Identification)-Datenbank Ihres PSTN-Betreibers hoch.</span><span class="sxs-lookup"><span data-stu-id="249df-107">Upload the ELINs to your public switched telephone network (PSTN) carrier's Automatic Location Identification (ALI) database.</span></span>

<span data-ttu-id="249df-108">Details zum Ausführen dieser Aufgaben finden Sie unter [Konfigurieren der Standortdatenbank in lync Server 2013](lync-server-2013-configure-the-location-database.md) in der Bereitstellungsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="249df-108">For details about how to perform these tasks, see [Configure the location database in Lync Server 2013](lync-server-2013-configure-the-location-database.md) in the Deployment documentation.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="249df-109">Speicherorte, die der zentralen Standortdatenbank hinzugefügt wurden, stehen dem Client erst zur Verfügung, nachdem Sie mithilfe eines lync Server-Verwaltungsshell-Befehls veröffentlicht und in den lokalen Speicher des Pools repliziert wurden.</span><span class="sxs-lookup"><span data-stu-id="249df-109">Locations added to the central location database are not available to the client until they have been published by using a Lync Server Management Shell command and are replicated to the pool's local stores.</span></span> <span data-ttu-id="249df-110">Ausführliche Informationen finden Sie unter <A href="lync-server-2013-publish-the-location-database.md">Veröffentlichen der Standortdatenbank aus lync Server 2013</A> in der Bereitstellungsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="249df-110">For details, see <A href="lync-server-2013-publish-the-location-database.md">Publish the location database from Lync Server 2013</A> in the Deployment documentation.</span></span>



</div>

<span data-ttu-id="249df-111">In diesem Abschnitt wird beschrieben, was Sie beim Planen der Aktualisierung und Verwaltung der Standortdatenbank berücksichtigen sollten.</span><span class="sxs-lookup"><span data-stu-id="249df-111">This section describes things to consider as you plan to update and maintain the location database.</span></span>

<div>

## <a name="planning-emergency-locations"></a><span data-ttu-id="249df-112">Planen der Notfallstandorte</span><span class="sxs-lookup"><span data-stu-id="249df-112">Planning Emergency Locations</span></span>

<span data-ttu-id="249df-113">Wenn Sie Elin-Gateways verwenden, füllen Sie die standortinformationsdienst-Datenbank mit der bürgerlichen Adresse, einer bestimmten Stelle in einem Gebäude und mindestens einem Elin für jeden Standort auf.</span><span class="sxs-lookup"><span data-stu-id="249df-113">When you use ELIN gateways, you populate the Location Information service database with the civic address, a specific location within a building, and at least one ELIN for each location .</span></span> <span data-ttu-id="249df-114">In der Planungsphase sollten Sie festlegen, wie Sie die Standorte benennen und wie Sie ELINs zuweisen möchten.</span><span class="sxs-lookup"><span data-stu-id="249df-114">During the planning phase, it is a good idea to decide how you want to name the locations and how you want to assign ELINs.</span></span>

<div>

## <a name="planning-location-names"></a><span data-ttu-id="249df-115">Planen der Standortnamen</span><span class="sxs-lookup"><span data-stu-id="249df-115">Planning Location Names</span></span>

<span data-ttu-id="249df-116">Das Feld standortinformationsdienst **Standort** , in dem sich die bestimmte Position in einem Gebäude befindet, hat eine maximale Länge von 20 Zeichen (einschließlich Leerzeichen).</span><span class="sxs-lookup"><span data-stu-id="249df-116">The Location Information service **Location** field, which holds the specific location within a building, has a maximum length of 20 characters (including spaces).</span></span> <span data-ttu-id="249df-117">In diesem Feld mit begrenzter Länge sollten Sie Folgendes angeben:</span><span class="sxs-lookup"><span data-stu-id="249df-117">Within that limited length, try to include the following:</span></span>

  - <span data-ttu-id="249df-p104">Einen leicht verständlichen Namen für den Standort des Notfallanrufers, um sicherzustellen, dass Notrufempfänger den Standort unverzüglich auffinden, wenn sie an der durchgegebenen Adresse eintreffen. Dieser Standortname kann die Hausnummer, das Stockwerk, den Gebäudetrakt, die Zimmernummer usw. beinhalten. Vermeiden Sie Spitznamen, die nur Mitarbeiter kennen und die dazu führen könnten, dass sich Notrufempfänger zur falschen Adresse begeben.</span><span class="sxs-lookup"><span data-stu-id="249df-p104">An easy-to-understand name that identifies the location of the 911 caller to help ensure that emergency responders find the specific location promptly when they arrive at the civic address. This location name may include a building number, floor number, wing designator, room number, and so on. Avoid nicknames that are known only to employees, which might cause emergency responders to go to the wrong location.</span></span>

  - <span data-ttu-id="249df-121">Eine Standort-ID, die Benutzern hilft, einfach zu erkennen, dass Ihr lync-Client den richtigen Speicherort übernommen hat.</span><span class="sxs-lookup"><span data-stu-id="249df-121">A location identifier that helps users to easily see that their Lync client picked up the correct location.</span></span> <span data-ttu-id="249df-122">Der lync-Client verkettet und zeigt die Felder "gefundener **Ort** " und **"Ort"** in der Kopfzeile automatisch an.</span><span class="sxs-lookup"><span data-stu-id="249df-122">The Lync client automatically concatenates and displays the discovered **Location** and **City** fields in its header.</span></span> <span data-ttu-id="249df-123">Eine gute Vorgehensweise besteht darin, jeder Standortkennung die Straßenadresse des Gebäudes hinzuzufügen (zum Beispiel " \<Straßennummer\>1. Etage").</span><span class="sxs-lookup"><span data-stu-id="249df-123">A good practice is to add the street address of the building to each location identifier (for example, "1st Floor \<street number\>").</span></span> <span data-ttu-id="249df-124">Ohne die Straßenadresse kann eine generische Standortkennung wie "1. Etage" für alle Gebäude in der Stadt gelten.</span><span class="sxs-lookup"><span data-stu-id="249df-124">Without the street address, a generic location identifier such as "1st Floor" could apply to any building in the city.</span></span>

  - <span data-ttu-id="249df-125">Wenn es sich um eine ungefähre Standortangabe handelt, da der Standort von einem Funkzugriffspunkt ermittelt wird, sollten Sie das Wort Near (Ca.) hinzufügen (z. B. „Ca. 1. Stock 1234“).</span><span class="sxs-lookup"><span data-stu-id="249df-125">If the location is approximate because it’s determined by a wireless access point, you may want to add the word Near (for example, "Near 1st Floor 1234").</span></span>

</div>

<div>

## <a name="planning-elins"></a><span data-ttu-id="249df-126">Planen der ELINs</span><span class="sxs-lookup"><span data-stu-id="249df-126">Planning ELINs</span></span>

<span data-ttu-id="249df-p106">Nachdem Sie festgelegt haben, wie der Gebäudebereich in Standorte aufgeteilt werden soll, müssen Sie bestimmen, wie viele ELINs jedem Standort zugewiesen werden sollen. Beispielsweise können in einem Gebäude mit mehreren Stockwerken oder mehreren Parteien unterschiedliche Gebäudebereiche verschiedenen Notfallzonen zugewiesen werden. In der Regel wird jedes Stockwerk in einem Gebäude als Standort ausgewiesen. Jedem Standort werden dann ELINs zugewiesen, die bei einem Notruf als wählende Nummern verwendet werden. Von Ihrem PSTN-Betreiber erfahren Sie, welche Telefonnummern als ELINs verwendet werden können. Die folgende Tabelle enthält ein Beispiel für Standorte für eine bestimmte Anschrift.</span><span class="sxs-lookup"><span data-stu-id="249df-p106">After you decide how you want to divide your building space into locations, you need to decide how many ELINs to assign to each location. For example, in a multifloor or multitenant building, different areas in the building can be assigned different emergency zones. Typically, each floor in a building is designated as a location. Each location is then assigned one or more ELINs, which are used as the calling number(s) during an emergency call. Contact your PSTN carrier for phone numbers that you can use for ELINs. The following table provides an example of locations for a specific street address.</span></span>

### <a name="sample-location-and-elin-assignments"></a><span data-ttu-id="249df-133">Beispielstandort und ELIN-Zuweisungen</span><span class="sxs-lookup"><span data-stu-id="249df-133">Sample Location and ELIN Assignments</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="249df-134">Gebäudebereich</span><span class="sxs-lookup"><span data-stu-id="249df-134">Building Area</span></span></th>
<th><span data-ttu-id="249df-135">Ort</span><span class="sxs-lookup"><span data-stu-id="249df-135">Location</span></span></th>
<th><span data-ttu-id="249df-136">ELIN</span><span class="sxs-lookup"><span data-stu-id="249df-136">ELIN</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="249df-137">Erster Stock</span><span class="sxs-lookup"><span data-stu-id="249df-137">First floor</span></span></p></td>
<td><p><span data-ttu-id="249df-138">1</span><span class="sxs-lookup"><span data-stu-id="249df-138">1</span></span></p></td>
<td><p><span data-ttu-id="249df-139">425-555-0100</span><span class="sxs-lookup"><span data-stu-id="249df-139">425-555-0100</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="249df-140">Zweiter Stock</span><span class="sxs-lookup"><span data-stu-id="249df-140">Second floor</span></span></p></td>
<td><p><span data-ttu-id="249df-141">2</span><span class="sxs-lookup"><span data-stu-id="249df-141">2</span></span></p></td>
<td><p><span data-ttu-id="249df-142">425-555-0111</span><span class="sxs-lookup"><span data-stu-id="249df-142">425-555-0111</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="249df-143">Dritter Stock</span><span class="sxs-lookup"><span data-stu-id="249df-143">Third floor</span></span></p></td>
<td><p><span data-ttu-id="249df-144">3</span><span class="sxs-lookup"><span data-stu-id="249df-144">3</span></span></p></td>
<td><p><span data-ttu-id="249df-145">425-555-0123</span><span class="sxs-lookup"><span data-stu-id="249df-145">425-555-0123</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="249df-146">Die von Ihnen definierten Standorte sollten die folgenden Anforderungen erfüllen:</span><span class="sxs-lookup"><span data-stu-id="249df-146">The locations you define should meet the following requirements:</span></span>

  - <span data-ttu-id="249df-147">Lokale und nationale/regionale Bestimmungen im Hinblick auf den maximalen Bereich pro Standort und die Anzahl von Standorten pro Anschrift werden eingehalten.</span><span class="sxs-lookup"><span data-stu-id="249df-147">Comply with local and national/regional regulations in terms of maximum area per location and number of locations per street address.</span></span>

  - <span data-ttu-id="249df-148">Sie sind aussagekräftig genug, damit die Person, die den Notruf getätigt hat, problemlos auffindbar ist.</span><span class="sxs-lookup"><span data-stu-id="249df-148">Are specific enough to make it easy to locate the emergency caller.</span></span>

</div>

</div>

<div>

## <a name="populating-the-location-database"></a><span data-ttu-id="249df-149">Auffüllen der Standortdatenbank</span><span class="sxs-lookup"><span data-stu-id="249df-149">Populating the Location Database</span></span>

<span data-ttu-id="249df-150">Die folgenden Fragen helfen Ihnen zu bestimmen, wie die Standortdatenbank aufgefüllt werden soll.</span><span class="sxs-lookup"><span data-stu-id="249df-150">The following questions will help you determine how to will populate the location database.</span></span>

  - <span data-ttu-id="249df-151">**Welches Verfahren verwenden Sie zum Auffüllen der Standortdatenbank?**</span><span class="sxs-lookup"><span data-stu-id="249df-151">**What process will you use to populate the location database?**</span></span>  
    <span data-ttu-id="249df-p107">Wo befinden sich die Daten und welche Schritte müssen Sie ausführen, um die Daten in das für die Standortdatenbank erforderliche Format zu konvertieren? Werden die Standorte einzeln oder mithilfe einer CSV-Datei als Batch hinzugefügt?</span><span class="sxs-lookup"><span data-stu-id="249df-p107">Where does the data exist, and what steps do you need to take to convert the data into the format required by the location database? Will you add locations individually, or in bulk, by using a CSV file?</span></span>

<!-- end list -->

  - <span data-ttu-id="249df-154">**Verfügen Sie über eine Drittanbieterdatenbank, die bereits Standortzuordnungen enthält?**</span><span class="sxs-lookup"><span data-stu-id="249df-154">**Do you have a third party database that already contains a mapping of locations?**</span></span>  
    <span data-ttu-id="249df-155">Wenn Sie die Option sekundärer standortinformationsdienst von lync Server zum Herstellen einer Verbindung mit einer Drittanbieter-Datenbank verwenden, können Sie Speicherorte mithilfe einer Offline Plattform gruppieren und verwalten.</span><span class="sxs-lookup"><span data-stu-id="249df-155">By using Lync Server's Secondary Location Information service option to connect to a third-party database, you can group and manage locations by using an offline platform.</span></span> <span data-ttu-id="249df-156">Der Vorteil dieses Ansatzes ist, dass Sie Standorte nicht nur Netzwerk-IDs, sondern auch einem Benutzer zuordnen können.</span><span class="sxs-lookup"><span data-stu-id="249df-156">A benefit to this approach is that in addition to associating locations to network identifiers, you can associate locations to a user.</span></span> <span data-ttu-id="249df-157">Dies bedeutet, dass der standortinformationsdienst mehrere Adressen, die vom sekundären standortinformationsdienst stammen, an einen lync Server-Client zurückgeben kann.</span><span class="sxs-lookup"><span data-stu-id="249df-157">This means that the Location Information service can return multiple addresses, originating from the Secondary Location Information service, to a Lync Server client.</span></span> <span data-ttu-id="249df-158">Der Benutzer kann dann den am besten geeigneten Standort wählen.</span><span class="sxs-lookup"><span data-stu-id="249df-158">The user can then choose the most appropriate location.</span></span>
    
    <span data-ttu-id="249df-159">Zur Integration in den standortinformationsdienst muss die Drittanbieterdatenbank dem Anforderungs-/Antwortschema des lync Server-Standorts folgen.</span><span class="sxs-lookup"><span data-stu-id="249df-159">To integrate with the Location Information service, the third-party database must follow the Lync Server Location Request/Response schema.</span></span> <span data-ttu-id="249df-160">Ausführliche Informationen finden Sie <http://go.microsoft.com/fwlink/p/?linkid=213819>unter.</span><span class="sxs-lookup"><span data-stu-id="249df-160">For details, see <http://go.microsoft.com/fwlink/p/?linkid=213819>.</span></span> <span data-ttu-id="249df-161">Details zum Bereitstellen eines sekundären Standort Informationsdiensts finden Sie unter [Konfigurieren eines sekundären Standort Informationsdiensts in lync Server 2013](lync-server-2013-configure-a-secondary-location-information-service.md) in der Bereitstellungsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="249df-161">For details about deploying a Secondary Location Information service, see [Configure a secondary Location Information service in Lync Server 2013](lync-server-2013-configure-a-secondary-location-information-service.md) in the Deployment documentation.</span></span>

<span data-ttu-id="249df-162">Details zum Auffüllen der Standortdatenbank finden Sie unter [Konfigurieren der Standortdatenbank in lync Server 2013](lync-server-2013-configure-the-location-database.md) in der Bereitstellungsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="249df-162">For details about populating the location database, see [Configure the location database in Lync Server 2013](lync-server-2013-configure-the-location-database.md) in the Deployment documentation.</span></span>

</div>

<div>

## <a name="maintaining-the-location-database"></a><span data-ttu-id="249df-163">Verwalten der Standortdatenbank</span><span class="sxs-lookup"><span data-stu-id="249df-163">Maintaining the Location Database</span></span>

<span data-ttu-id="249df-p110">Nach dem Auffüllen der Standortdatenbank müssen Sie eine Strategie zum Aktualisieren der Datenbank entwickeln, um Änderungen an der Netzwerkkonfiguration umzusetzen. Die folgenden Fragen helfen Ihnen zu bestimmen, wie die Standortdatenbank verwaltet werden soll.</span><span class="sxs-lookup"><span data-stu-id="249df-p110">After you populate the location database, you need to develop a strategy for updating the database as the network configuration changes. The following questions will help you determine how to maintain the location database.</span></span>

  - <span data-ttu-id="249df-166">**Wie aktualisieren Sie die Standortdatenbank?**</span><span class="sxs-lookup"><span data-stu-id="249df-166">**How will you update the location database?**</span></span>  
    <span data-ttu-id="249df-p111">Eine Aktualisierung der Standortdatenbank kann in verschiedenen Situationen notwendig sein, etwa beim Hinzufügen von Funkzugriffspunkten, bei einer Neuverkabelung des Büros (mit neuen Switchzuordnungen) und bei einer Subnetzerweiterung. Aktualisieren Sie jeden Standort sofort oder führen Sie mithilfe einer CSV-Datei eine Aktualisierung aller Standorte als Batch durch?</span><span class="sxs-lookup"><span data-stu-id="249df-p111">There are several scenarios that require an update to the location database, including adding wireless access points (WAPs), office recabling (resulting in different switch assignments), and subnet expansion. Will you directly update each individual location, or will you perform a bulk update of all the locations by using a CSV file?</span></span>

<!-- end list -->

  - <span data-ttu-id="249df-169">**Verwenden Sie eine SNMP-Anwendung zum Abgleich von Lync-Client-MAC-Adressen mit den Port- und Switchbezeichnern?**</span><span class="sxs-lookup"><span data-stu-id="249df-169">**Will you use an SNMP application to match Lync client MAC addresses to port and switch identifiers?**</span></span>  
    <span data-ttu-id="249df-170">Wenn Sie eine SNMP-Anwendung verwenden, müssen Sie ein manuelles Verfahren ausarbeiten, um die Konsistenz der Switch- und Portinformationen zwischen der SNMP-Anwendung und der Standortdatenbank sicherzustellen.</span><span class="sxs-lookup"><span data-stu-id="249df-170">If you use an SNMP application, you need to develop a manual process for keeping the switch chassis and port information consistent between the SNMP application and the location database.</span></span> <span data-ttu-id="249df-171">Wenn die SNMP-Anwendung eine Chassis-IP-Adresse oder Port-ID zurückgibt, die nicht in der Datenbank enthalten ist, kann der standortinformationsdienst keinen Standort an den Client zurückgeben.</span><span class="sxs-lookup"><span data-stu-id="249df-171">If the SNMP application returns a chassis IP address or port ID that is not included in the database, the Location Information service will not be able to return a location to the client.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

