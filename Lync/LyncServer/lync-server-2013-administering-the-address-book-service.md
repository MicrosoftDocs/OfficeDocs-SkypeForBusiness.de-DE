---
title: 'Lync Server 2013: Verwalten des Adressbuchdiensts'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Administering the Address Book Service
ms:assetid: 801e4243-9670-4477-aa2f-88b61ecf5351
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg429711(v=OCS.15)
ms:contentKeyID: 48184649
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8acf59a898f8da14b9c5c4151728206cc501ceaf
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34839996"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="administering-the-address-book-service-in-lync-server-2013"></a><span data-ttu-id="1a339-102">Verwalten des Adressbuchdiensts in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1a339-102">Administering the Address Book Service in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1a339-103">_**Letztes Änderungsdatum des Themas:** 2014-02-05_</span><span class="sxs-lookup"><span data-stu-id="1a339-103">_**Topic Last Modified:** 2014-02-05_</span></span>

<span data-ttu-id="1a339-104">Als Teil der Bereitstellung von lync Server, Enterprise Edition oder Standard Edition-Server wird der Adressbuchdienst standardmäßig installiert.</span><span class="sxs-lookup"><span data-stu-id="1a339-104">As a part of the deployment of Lync Server, Enterprise Edition or Standard Edition server, the Address Book Service is installed by default.</span></span> <span data-ttu-id="1a339-105">Die vom Adressbuchdienst – RTCab – verwendete Datenbank wird auf dem SQL Server erstellt (für Enterprise Edition, dies ist der Back-End-SQL-Server; für den Standard Edition-Server, den zusammengefassten SQL Server).</span><span class="sxs-lookup"><span data-stu-id="1a339-105">The database used by the Address Book Service – RTCab – is created on the SQL Server (for Enterprise Edition, this is the back-end SQL Server; for Standard Edition server, the collocated SQL Server).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="1a339-106">Informationen zur Verwendung der <STRONG>ADSI-Bearbeitung</STRONG> zum Bearbeiten von Active Directory-Objektattributen finden Sie unter <A href="http://go.microsoft.com/fwlink/?linkid=330427">ADSI-Bearbeitung</A>.</span><span class="sxs-lookup"><span data-stu-id="1a339-106">For information about using <STRONG>ADSI Edit</STRONG> to edit Active Directory Domain Services object attributes, see <A href="http://go.microsoft.com/fwlink/?linkid=330427">ADSI Edit</A>.</span></span> <span data-ttu-id="1a339-107">Informationen zu einem Tool im Resource Kit speziell für den Adressbuchdienst finden Sie unter <A href="http://go.microsoft.com/fwlink/?linkid=330429">Microsoft lync Server 2013 Resource Kit-Tools</A>.</span><span class="sxs-lookup"><span data-stu-id="1a339-107">For information about a tool in the Resource Kit specifically for the Address Book service, see <A href="http://go.microsoft.com/fwlink/?linkid=330429">Microsoft Lync Server 2013 Resource Kit Tools</A>.</span></span>



</div>

<div>

## <a name="address-book-server-phone-number-normalization"></a><span data-ttu-id="1a339-108">Telefonnummernnormalisierung des Adressbuchservers</span><span class="sxs-lookup"><span data-stu-id="1a339-108">Address Book Server Phone Number Normalization</span></span>

<span data-ttu-id="1a339-109">Lync Server erfordert standardisierte RFC 3966/E. 164-Telefonnummern.</span><span class="sxs-lookup"><span data-stu-id="1a339-109">Lync Server requires standardized RFC 3966/E.164 phone numbers.</span></span> <span data-ttu-id="1a339-110">Um Telefonnummern zu verwenden, die nicht strukturiert oder inkonsistent formatiert sind, verwendet lync Server den Adressbuchserver, um Telefonnummern vorverarbeiten, bevor Sie an die Normalisierungsregeln übergeben werden.</span><span class="sxs-lookup"><span data-stu-id="1a339-110">To use phone numbers that are unstructured or inconsistently formatted, Lync Server relies on the Address Book Server to preprocess phone numbers before they are handed off to the normalization rules.</span></span> <span data-ttu-id="1a339-111">Wenn eine Telefonnummer aus dem Adressbuch verwendet wird und die Normalisierungsregel angewendet wird, können Clients wie lync Phone Edition und lync Mobile diese normalisierten Nummern verwenden.</span><span class="sxs-lookup"><span data-stu-id="1a339-111">When a phone number is used from the address book and the normalization rule is applied, clients, such as Lync Phone Edition and Lync Mobile, can use these normalized numbers.</span></span>

<span data-ttu-id="1a339-112">Die Normalisierungsregeln, die in früheren Versionen verwendet wurden, funktionieren möglicherweise ohne Anpassungen nicht ordnungsgemäß.</span><span class="sxs-lookup"><span data-stu-id="1a339-112">The normalization rules that were used in previous versions may not work properly without some adjustments.</span></span> <span data-ttu-id="1a339-113">Da die Leerzeichen und nicht obligatorischen Zeichen vor den Normalisierungsregeln entfernt werden, wenn Ihr Regex-Ausdruck speziell nach einem Strich oder einem anderen Zeichen sucht, das entfernt wurde, schlägt die Normalisierungsregel möglicherweise fehl.</span><span class="sxs-lookup"><span data-stu-id="1a339-113">Because the white space and non-mandatory characters are removed prior to the normalization rules, if your regex expression is specifically looking for a dash or other character that was removed, your normalization rule might fail.</span></span> <span data-ttu-id="1a339-114">Überprüfen Sie Ihre Normalisierungsregeln, um sicherzustellen, dass Sie nicht nach diesen nicht obligatorischen Zeichen suchen, oder dass die Regel ordnungsgemäß fehlschlägt und fortgesetzt werden kann, wenn das Zeichen nicht vorhanden ist, wenn es von der Regel erwartet wird.</span><span class="sxs-lookup"><span data-stu-id="1a339-114">You should review your normalization rules to ensure that either they are not looking for these non-mandatory characters, or that the rule can fail gracefully and continue in the event that the character is not present where the rule anticipates it will be.</span></span>

</div>

<div>

## <a name="user-replicator-and-address-book-server"></a><span data-ttu-id="1a339-115">Benutzer-Replikator und Adressbuch Server</span><span class="sxs-lookup"><span data-stu-id="1a339-115">User Replicator and Address Book Server</span></span>

<span data-ttu-id="1a339-116">Der Adressbuch Server verwendet die vom Benutzerreplikationsdienst zur Verfügung gestellten Daten, um die Informationen zu aktualisieren, die er ursprünglich aus der globalen Adressliste (Global Address List, GAL) erhält.</span><span class="sxs-lookup"><span data-stu-id="1a339-116">The Address Book Server uses data provided by User Replicator to update the information that it initially obtains from the global address list (GAL).</span></span> <span data-ttu-id="1a339-117">Der Benutzerreplikationsdienst schreibt die Attribute der Active Directory-Domänendienste für jeden Benutzer, Kontakt und jede Gruppe in die Tabelle AbUserEntry-Tabelle in der Datenbank, und der Adressbuchserver synchronisiert die Benutzerdaten aus der Datenbank in Dateien im Dateispeicher des Adressbuchservers und in die Adressbuchdatenbank RTCab.</span><span class="sxs-lookup"><span data-stu-id="1a339-117">User Replicator writes the Active Directory Domain Services attributes for each user, contact, and group into the AbUserEntry table in the database and the Address Book Server syncs the user data from the database into files in the Address Book Server file store and into the Address Book database RTCab.</span></span> <span data-ttu-id="1a339-118">Das Schema für die Tabelle AbUserEntry-Tabelle verwendet zwei Spalten, **UserGuid** und **UserData**.</span><span class="sxs-lookup"><span data-stu-id="1a339-118">The schema for the AbUserEntry table uses two columns, **UserGuid** and **UserData**.</span></span> <span data-ttu-id="1a339-119">**UserGuid** ist die Indexspalte und enthält die 16-Byte-GUID des Active Directory-Objekts.</span><span class="sxs-lookup"><span data-stu-id="1a339-119">**UserGuid** is the index column and contains the 16-byte GUID of the Active Directory object.</span></span> <span data-ttu-id="1a339-120">**UserData** ist eine Bildspalte, die alle zuvor erwähnten Attribute für Active Directory-Domänendienste für diesen Kontakt enthält.</span><span class="sxs-lookup"><span data-stu-id="1a339-120">**UserData** is an image column which contains all of the previously mentioned Active Directory Domain Services attributes for that contact.</span></span>

<span data-ttu-id="1a339-121">Der Benutzerreplikationsdienst bestimmt, welche Active Directory-Attribute geschrieben werden sollen, indem Sie eine Konfigurationstabelle lesen, die sich in derselben SQL Server-basierten Instanz wie die Tabelle AbUserEntry-Tabelle befindet.</span><span class="sxs-lookup"><span data-stu-id="1a339-121">User Replicator determines which Active Directory attributes to write by reading a configuration table located in the same SQL Server-based instance as the AbUserEntry table.</span></span> <span data-ttu-id="1a339-122">Die AbAttribute-Tabelle enthält drei Spalten, **ID**, **Name**, **Flags**und **enable**.</span><span class="sxs-lookup"><span data-stu-id="1a339-122">The AbAttribute table contains three columns, **ID**, **Name**, **Flags**, and **Enable**.</span></span> <span data-ttu-id="1a339-123">Die Tabelle wird beim Einrichten der Datenbank erstellt.</span><span class="sxs-lookup"><span data-stu-id="1a339-123">The table is created during database setup.</span></span> <span data-ttu-id="1a339-124">Wenn die AbAttribute-Tabelle leer ist, überspringt der Benutzerreplikationsdienst die Tabelle AbUserEntry-Tabellen Verarbeitungslogik.</span><span class="sxs-lookup"><span data-stu-id="1a339-124">If the AbAttribute table is empty, User Replicator skips its AbUserEntry table processing logic.</span></span> <span data-ttu-id="1a339-125">Adressbuchserver Attribute sind dynamisch und werden aus der AbAttribute-Tabelle abgerufen, die zunächst vom Adressbuchserver geschrieben wird, wenn der Adressbuchserver aktiviert wird.</span><span class="sxs-lookup"><span data-stu-id="1a339-125">Address Book Server attributes are dynamic and are retrieved from the AbAttribute table, which is initially written by the Address Book Server when the Address Book Server is activated.</span></span>

<span data-ttu-id="1a339-126">Bei der Aktivierung des Adressbuchservers wird die AbAttribute-Tabelle mit den in der folgenden Tabelle dargestellten Werten gefüllt.</span><span class="sxs-lookup"><span data-stu-id="1a339-126">Address Book Server activation populates the AbAttribute table with the values shown in the following table.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="1a339-127">ID</span><span class="sxs-lookup"><span data-stu-id="1a339-127">ID</span></span></th>
<th><span data-ttu-id="1a339-128">Name</span><span class="sxs-lookup"><span data-stu-id="1a339-128">Name</span></span></th>
<th><span data-ttu-id="1a339-129">Kennzeichnungen</span><span class="sxs-lookup"><span data-stu-id="1a339-129">Flags</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="1a339-130">1</span><span class="sxs-lookup"><span data-stu-id="1a339-130">1</span></span></p></td>
<td><p><span data-ttu-id="1a339-131">givenName</span><span class="sxs-lookup"><span data-stu-id="1a339-131">givenName</span></span></p></td>
<td><p><span data-ttu-id="1a339-132">0x01400000</span><span class="sxs-lookup"><span data-stu-id="1a339-132">0x01400000</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1a339-133">2</span><span class="sxs-lookup"><span data-stu-id="1a339-133">2</span></span></p></td>
<td><p><span data-ttu-id="1a339-134">SN</span><span class="sxs-lookup"><span data-stu-id="1a339-134">Sn</span></span></p></td>
<td><p><span data-ttu-id="1a339-135">0x02400000</span><span class="sxs-lookup"><span data-stu-id="1a339-135">0x02400000</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1a339-136">3</span><span class="sxs-lookup"><span data-stu-id="1a339-136">3</span></span></p></td>
<td><p><span data-ttu-id="1a339-137">DisplayName</span><span class="sxs-lookup"><span data-stu-id="1a339-137">displayName</span></span></p></td>
<td><p><span data-ttu-id="1a339-138">0x03420000</span><span class="sxs-lookup"><span data-stu-id="1a339-138">0x03420000</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1a339-139">4</span><span class="sxs-lookup"><span data-stu-id="1a339-139">4</span></span></p></td>
<td><p><span data-ttu-id="1a339-140">Titel</span><span class="sxs-lookup"><span data-stu-id="1a339-140">Title</span></span></p></td>
<td><p><span data-ttu-id="1a339-141">0x04000000</span><span class="sxs-lookup"><span data-stu-id="1a339-141">0x04000000</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1a339-142">5</span><span class="sxs-lookup"><span data-stu-id="1a339-142">5</span></span></p></td>
<td><p><span data-ttu-id="1a339-143">mailNickname</span><span class="sxs-lookup"><span data-stu-id="1a339-143">mailNickname</span></span></p></td>
<td><p><span data-ttu-id="1a339-144">0x05400000</span><span class="sxs-lookup"><span data-stu-id="1a339-144">0x05400000</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1a339-145">6</span><span class="sxs-lookup"><span data-stu-id="1a339-145">6</span></span></p></td>
<td><p><span data-ttu-id="1a339-146">Unternehmen</span><span class="sxs-lookup"><span data-stu-id="1a339-146">Company</span></span></p></td>
<td><p><span data-ttu-id="1a339-147">0x06000000</span><span class="sxs-lookup"><span data-stu-id="1a339-147">0x06000000</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1a339-148">7</span><span class="sxs-lookup"><span data-stu-id="1a339-148">7</span></span></p></td>
<td><p><span data-ttu-id="1a339-149">physicalDeliveryOfficeName</span><span class="sxs-lookup"><span data-stu-id="1a339-149">physicalDeliveryOfficeName</span></span></p></td>
<td><p><span data-ttu-id="1a339-150">0x07000000</span><span class="sxs-lookup"><span data-stu-id="1a339-150">0x07000000</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1a339-151">8</span><span class="sxs-lookup"><span data-stu-id="1a339-151">8</span></span></p></td>
<td><p><span data-ttu-id="1a339-152">msRTCSIP-PrimaryUserAddress</span><span class="sxs-lookup"><span data-stu-id="1a339-152">msRTCSIP-PrimaryUserAddress</span></span></p></td>
<td><p><span data-ttu-id="1a339-153">0x08520C00</span><span class="sxs-lookup"><span data-stu-id="1a339-153">0x08520C00</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1a339-154">9</span><span class="sxs-lookup"><span data-stu-id="1a339-154">9</span></span></p></td>
<td><p><span data-ttu-id="1a339-155">telephoneNumber</span><span class="sxs-lookup"><span data-stu-id="1a339-155">telephoneNumber</span></span></p></td>
<td><p><span data-ttu-id="1a339-156">0x09022800</span><span class="sxs-lookup"><span data-stu-id="1a339-156">0x09022800</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1a339-157">10</span><span class="sxs-lookup"><span data-stu-id="1a339-157">10</span></span></p></td>
<td><p><span data-ttu-id="1a339-158">homePhone</span><span class="sxs-lookup"><span data-stu-id="1a339-158">homePhone</span></span></p></td>
<td><p><span data-ttu-id="1a339-159">0x0A302800</span><span class="sxs-lookup"><span data-stu-id="1a339-159">0x0A302800</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1a339-160">11</span><span class="sxs-lookup"><span data-stu-id="1a339-160">11</span></span></p></td>
<td><p><span data-ttu-id="1a339-161">Mobil</span><span class="sxs-lookup"><span data-stu-id="1a339-161">Mobile</span></span></p></td>
<td><p><span data-ttu-id="1a339-162">0x0B622800</span><span class="sxs-lookup"><span data-stu-id="1a339-162">0x0B622800</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1a339-163">12</span><span class="sxs-lookup"><span data-stu-id="1a339-163">12</span></span></p></td>
<td><p><span data-ttu-id="1a339-164">otherTelephone</span><span class="sxs-lookup"><span data-stu-id="1a339-164">otherTelephone</span></span></p></td>
<td><p><span data-ttu-id="1a339-165">0x0C302000</span><span class="sxs-lookup"><span data-stu-id="1a339-165">0x0C302000</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1a339-166">13</span><span class="sxs-lookup"><span data-stu-id="1a339-166">13</span></span></p></td>
<td><p><span data-ttu-id="1a339-167">ipPhone</span><span class="sxs-lookup"><span data-stu-id="1a339-167">ipPhone</span></span></p></td>
<td><p><span data-ttu-id="1a339-168">0x0D302000</span><span class="sxs-lookup"><span data-stu-id="1a339-168">0x0D302000</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1a339-169">14</span><span class="sxs-lookup"><span data-stu-id="1a339-169">14</span></span></p></td>
<td><p><span data-ttu-id="1a339-170">Mail</span><span class="sxs-lookup"><span data-stu-id="1a339-170">Mail</span></span></p></td>
<td><p><span data-ttu-id="1a339-171">0x0E500000</span><span class="sxs-lookup"><span data-stu-id="1a339-171">0x0E500000</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1a339-172">15</span><span class="sxs-lookup"><span data-stu-id="1a339-172">15</span></span></p></td>
<td><p><span data-ttu-id="1a339-173">GroupType</span><span class="sxs-lookup"><span data-stu-id="1a339-173">groupType</span></span></p></td>
<td><p><span data-ttu-id="1a339-174">0x0F010800</span><span class="sxs-lookup"><span data-stu-id="1a339-174">0x0F010800</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1a339-175">16</span><span class="sxs-lookup"><span data-stu-id="1a339-175">16</span></span></p></td>
<td><p><span data-ttu-id="1a339-176">Abteilung</span><span class="sxs-lookup"><span data-stu-id="1a339-176">Department</span></span></p></td>
<td><p><span data-ttu-id="1a339-177">0x10000000</span><span class="sxs-lookup"><span data-stu-id="1a339-177">0x10000000</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1a339-178">17</span><span class="sxs-lookup"><span data-stu-id="1a339-178">17</span></span></p></td>
<td><p><span data-ttu-id="1a339-179">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="1a339-179">Description</span></span></p></td>
<td><p><span data-ttu-id="1a339-180">0x11000100</span><span class="sxs-lookup"><span data-stu-id="1a339-180">0x11000100</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1a339-181">18</span><span class="sxs-lookup"><span data-stu-id="1a339-181">18</span></span></p></td>
<td><p><span data-ttu-id="1a339-182">Manager</span><span class="sxs-lookup"><span data-stu-id="1a339-182">Manager</span></span></p></td>
<td><p><span data-ttu-id="1a339-183">0x12040001</span><span class="sxs-lookup"><span data-stu-id="1a339-183">0x12040001</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1a339-184">19</span><span class="sxs-lookup"><span data-stu-id="1a339-184">19</span></span></p></td>
<td><p><span data-ttu-id="1a339-185">ProxyAddress</span><span class="sxs-lookup"><span data-stu-id="1a339-185">proxyAddress</span></span></p></td>
<td><p><span data-ttu-id="1a339-186">0x00500105</span><span class="sxs-lookup"><span data-stu-id="1a339-186">0x00500105</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1a339-187">20</span><span class="sxs-lookup"><span data-stu-id="1a339-187">20</span></span></p></td>
<td><p><span data-ttu-id="1a339-188">msExchHideFromAddressLists</span><span class="sxs-lookup"><span data-stu-id="1a339-188">msExchHideFromAddressLists</span></span></p></td>
<td><p><span data-ttu-id="1a339-189">0xFF000003</span><span class="sxs-lookup"><span data-stu-id="1a339-189">0xFF000003</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1a339-190">99</span><span class="sxs-lookup"><span data-stu-id="1a339-190">99</span></span></p></td>
<td><p><span data-ttu-id="1a339-191">entryID</span><span class="sxs-lookup"><span data-stu-id="1a339-191">entryID</span></span></p></td>
<td><p><span data-ttu-id="1a339-192">0x99000000</span><span class="sxs-lookup"><span data-stu-id="1a339-192">0x99000000</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="1a339-193">Die Zahlen in der Spalte " **ID** " müssen eindeutig sein und nie wieder verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="1a339-193">The numbers in the **ID** column must be unique and should never be reused.</span></span> <span data-ttu-id="1a339-194">Außerdem wird durch das aufrecht erhalten der ID-Werte unter 256 Platz in den vom Adressbuch Server geschriebenen Ausgabedateien gespart.</span><span class="sxs-lookup"><span data-stu-id="1a339-194">Also, keeping the ID values under 256 saves space in the output files written by the Address Book Server.</span></span> <span data-ttu-id="1a339-195">Der maximale ID-Wert ist jedoch 65535.</span><span class="sxs-lookup"><span data-stu-id="1a339-195">However, the maximum ID value is 65535.</span></span> <span data-ttu-id="1a339-196">Die Spalte **Name** entspricht dem Active Directory-Attributnamen, den der Benutzerreplikationsdienst in die Tabelle AbUserEntry-Tabelle für jeden Kontakt aufnehmen soll.</span><span class="sxs-lookup"><span data-stu-id="1a339-196">The **Name** column corresponds to the Active Directory attribute name that User Replicator should put in the AbUserEntry table for each contact.</span></span> <span data-ttu-id="1a339-197">Der Wert in der Spalte **Flags** wird verwendet, um den Typ des Attributs zu definieren.</span><span class="sxs-lookup"><span data-stu-id="1a339-197">The value in the **Flags** column is used to define the type of attribute.</span></span> <span data-ttu-id="1a339-198">Die folgenden Typen von Adressbuch Server Attributen werden vom Benutzerreplikationsdienst erkannt, der durch das niedrige Byte des Werts in der Spalte **Flags** angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="1a339-198">The following types of Address Book Server attributes are recognized by User Replicator, indicated by the low byte of the value in the **Flags** column.</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="1a339-199">Attribut</span><span class="sxs-lookup"><span data-stu-id="1a339-199">Attribute</span></span></th>
<th><span data-ttu-id="1a339-200">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="1a339-200">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="1a339-201">0x0</span><span class="sxs-lookup"><span data-stu-id="1a339-201">0x0</span></span></p></td>
<td><p><span data-ttu-id="1a339-202">Ein Zeichenfolgenattribut.</span><span class="sxs-lookup"><span data-stu-id="1a339-202">A string attribute.</span></span> <span data-ttu-id="1a339-203">Der Benutzerreplikationsdienst wandelt diesen Typ in UTF-8 um, bevor er ihn in der Tabelle AbUserEntry-Tabelle speichert.</span><span class="sxs-lookup"><span data-stu-id="1a339-203">User Replicator converts this type to UTF-8 before storing it in the AbUserEntry table.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1a339-204">0x1</span><span class="sxs-lookup"><span data-stu-id="1a339-204">0x1</span></span></p></td>
<td><p><span data-ttu-id="1a339-205">Ein binäres Attribut.</span><span class="sxs-lookup"><span data-stu-id="1a339-205">A binary attribute.</span></span> <span data-ttu-id="1a339-206">Der Benutzerreplikationsdienst speichert diese ohne Konvertierung im BLOB.</span><span class="sxs-lookup"><span data-stu-id="1a339-206">User Replicator stores this in the blob without any conversion.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1a339-207">0x2</span><span class="sxs-lookup"><span data-stu-id="1a339-207">0x2</span></span></p></td>
<td><p><span data-ttu-id="1a339-208">Ein Zeichenfolgenattribut, wird aber nur berücksichtigt, wenn der Attributwert &quot;mit Tel&quot;: beginnt.</span><span class="sxs-lookup"><span data-stu-id="1a339-208">A string attribute, but is included only if the attribute value begins with &quot;tel:&quot;.</span></span> <span data-ttu-id="1a339-209">Dies gilt in erster Linie für mehrwertige Zeichenfolgenattribute, insbesondere für <strong>proxyAddresses</strong>.</span><span class="sxs-lookup"><span data-stu-id="1a339-209">This is primarily for multi-valued string attributes, specifically <strong>proxyAddresses</strong>.</span></span> <span data-ttu-id="1a339-210">In diesem Fall ist der Adressbuch Server nur an <strong>proxyAddresses</strong> -Einträgen interessiert, &quot;die mit&quot;Tel: beginnen.</span><span class="sxs-lookup"><span data-stu-id="1a339-210">In this case, Address Book Server is interested only in <strong>proxyAddresses</strong> entries that begin with &quot;tel:&quot;.</span></span> <span data-ttu-id="1a339-211">Aus diesem Grund speichert der Benutzerreplikationsdienst im Interesse des Speicherplatzes nur die Einträge, &quot;die mit&quot;Tel: beginnen.</span><span class="sxs-lookup"><span data-stu-id="1a339-211">Therefore, in the interest of saving space, User Replicator stores only the entries that begin with &quot;tel:&quot;.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1a339-212">0x3</span><span class="sxs-lookup"><span data-stu-id="1a339-212">0x3</span></span></p></td>
<td><p><span data-ttu-id="1a339-213">Ein boolesches Zeichenfolgenattribut, das bei true bewirkt, dass der Benutzer Replicator diesen Kontakt nicht in die Tabelle AbUserEntry-Tabelle einfügt.</span><span class="sxs-lookup"><span data-stu-id="1a339-213">A Boolean string attribute, which if TRUE causes User Replicator to not include this contact in the AbUserEntry table.</span></span> <span data-ttu-id="1a339-214">Ist der Wert false, wird der Benutzerreplikationsdienst dazu veranlasst, die Attribute für diesen Kontakt in die Tabelle AbUserEntry-Tabelle einzubeziehen, jedoch nicht das jeweilige Attribut mit diesem Flag.</span><span class="sxs-lookup"><span data-stu-id="1a339-214">If FALSE, it causes User Replicator to include the attributes for this contact in the AbUserEntry table, but not the particular attribute with this flag.</span></span> <span data-ttu-id="1a339-215">Dies ist ein weiterer spezieller Case-Typ, der in erster Linie für das <strong>msExchHideFromAddressLists</strong> -Attribut steht.</span><span class="sxs-lookup"><span data-stu-id="1a339-215">This is another special case type that is primarily for the <strong>msExchHideFromAddressLists</strong> attribute.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1a339-216">0x4</span><span class="sxs-lookup"><span data-stu-id="1a339-216">0x4</span></span></p></td>
<td><p><span data-ttu-id="1a339-217">Ein Zeichenfolgenattribut, wird aber nur berücksichtigt, wenn der Attributwert &quot;mit SMTP&quot; beginnt: und &quot; @ &quot; das Symbol enthält.</span><span class="sxs-lookup"><span data-stu-id="1a339-217">A string attribute, but is included only if the attribute value begins with &quot;smtp:&quot; and includes the &quot;@&quot; symbol.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1a339-218">0x5</span><span class="sxs-lookup"><span data-stu-id="1a339-218">0x5</span></span></p></td>
<td><p><span data-ttu-id="1a339-219">Ein Zeichenfolgenattribut, wird aber nur berücksichtigt, wenn der Attributwert entweder &quot;mit "&quot; Tel &quot;:"&quot; oder "SMTP &quot; @ &quot; :" beginnt und das Symbol enthält.</span><span class="sxs-lookup"><span data-stu-id="1a339-219">A string attribute, but is included only if the attribute value begins with either &quot;tel:&quot; or &quot;smtp:&quot; and includes the &quot;@&quot; symbol.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1a339-220">0x100</span><span class="sxs-lookup"><span data-stu-id="1a339-220">0x100</span></span></p></td>
<td><p><span data-ttu-id="1a339-221">Wenn festzulegen, handelt es sich um ein mehrwertiges Attribut, das für jeden Kontakt mehrmals angezeigt werden kann.</span><span class="sxs-lookup"><span data-stu-id="1a339-221">If set, this is a multi-valued attribute that can appear more than once for each contact.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1a339-222">0x400</span><span class="sxs-lookup"><span data-stu-id="1a339-222">0x400</span></span></p></td>
<td><p><span data-ttu-id="1a339-223">Wenn diese Einstellung festgesetzt ist, wird das Attribut "e-Mail-Benutzerkontoname" für einen Kontakt angegeben.</span><span class="sxs-lookup"><span data-stu-id="1a339-223">If set, this identifies the email user account name attribute for a contact.</span></span> <span data-ttu-id="1a339-224">Der Adressbuch Server verwendet dieses Flag, um zu ermitteln, welcher Attributwert im Ereignisprotokolleintrag für die Telefon Normalisierung angezeigt werden soll.</span><span class="sxs-lookup"><span data-stu-id="1a339-224">Address Book Server uses this flag to identify which attribute value to show in the phone normalization event log entry.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1a339-225">0x800</span><span class="sxs-lookup"><span data-stu-id="1a339-225">0x800</span></span></p></td>
<td><p><span data-ttu-id="1a339-226">Wenn festzulegen, wird ein erforderliches Attribut für einen Kontakt angegeben.</span><span class="sxs-lookup"><span data-stu-id="1a339-226">If set, this identifies a required attribute for a contact.</span></span> <span data-ttu-id="1a339-227">Der Adressbuch Server enthält nur dann einen Benutzer in der Tabelle AbUserEntry-Tabelle, wenn ein Wert für dieses Attribut in Active Directory vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="1a339-227">Address Book Server includes a user in the AbUserEntry table only if there is a value for this attribute in Active Directory.</span></span> <span data-ttu-id="1a339-228">Wenn mehr als ein erforderliches Attribut vorhanden ist, muss nur einer von Ihnen über einen Wert verfügen, um den Benutzer in die Tabelle AbUserEntry-Tabelle einzubeziehen.</span><span class="sxs-lookup"><span data-stu-id="1a339-228">If there is more than one required attribute, only one of them is required to have a value to include the user in the AbUserEntry table.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1a339-229">0x1000</span><span class="sxs-lookup"><span data-stu-id="1a339-229">0x1000</span></span></p></td>
<td><p><span data-ttu-id="1a339-230">Wenn der Wert für Address Book Server gesetzt ist, wird der Wert dieses Attributs immer normalisiert.</span><span class="sxs-lookup"><span data-stu-id="1a339-230">If set, Address Book Server always normalizes the value of this attribute.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1a339-231">0x2000</span><span class="sxs-lookup"><span data-stu-id="1a339-231">0x2000</span></span></p></td>
<td><p><span data-ttu-id="1a339-232">Ist der Wert festgelegt, verwendet der Adressbuch Server die normalisierte Zahl von <strong>proxyAddresses</strong>, wenn die <strong>UseNormalizationRules</strong> -CMS-Einstellung falsch ist. Andernfalls verhält es sich wie beim Flag-Bit 0x1000.</span><span class="sxs-lookup"><span data-stu-id="1a339-232">If set, Address Book Server uses the normalized number from <strong>proxyAddresses</strong>, if the <strong>UseNormalizationRules</strong> CMS setting is FALSE; otherwise it behaves the same as when the flag bit is 0x1000.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1a339-233">0x4000</span><span class="sxs-lookup"><span data-stu-id="1a339-233">0x4000</span></span></p></td>
<td><p><span data-ttu-id="1a339-234">Wenn festgelegt, enthält der Adressbuch Server keine Objekte in der Tabelle AbUserEntry-Tabelle, die diesen Wert für das angegebene Attribut aufweisen.</span><span class="sxs-lookup"><span data-stu-id="1a339-234">If set, Address Book Server does not include objects in the AbUserEntry table that have this value for the specified attribute.</span></span> <span data-ttu-id="1a339-235">Wenn beispielsweise für das <strong>Attribut msRTCSIP-PrimaryUserAddress-</strong> Attribut dieses Flag-Bit festgesetzt ist, werden Kontakte mit diesem Attribut nicht in die Datenbank geschrieben.</span><span class="sxs-lookup"><span data-stu-id="1a339-235">For example, if the <strong>msRTCSIP-PrimaryUserAddress</strong> attribute has this flag bit set, then contacts that have this attribute are not written to the database.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1a339-236">0X8000</span><span class="sxs-lookup"><span data-stu-id="1a339-236">0x8000</span></span></p></td>
<td><p><span data-ttu-id="1a339-237">Wenn festgelegt, enthält der Adressbuch Server keine Objekte in der Tabelle AbUserEntry-Tabelle, die diesen Wert für das angegebene Attribut nicht aufweisen.</span><span class="sxs-lookup"><span data-stu-id="1a339-237">If set, Address Book Server does not include objects in the AbUserEntry table that do not have this value for the specified attribute.</span></span> <span data-ttu-id="1a339-238">Wenn sowohl die 0x4000-als auch die 0X8000-Flag-Bits für ein Objekt gesetzt sind, hat das Attribut mit dem Flag-Bit-Wert, der auf 0x4000 gesetzt ist, Vorrang, und das Objekt wird aus der Tabelle AbUserEntry-Tabelle ausgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="1a339-238">If both the 0x4000 and 0x8000 flag bits are set on an object, the attribute with the flag bit value set to 0x4000 takes precedence, and the object is excluded from the AbUserEntry table.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1a339-239">0x10000</span><span class="sxs-lookup"><span data-stu-id="1a339-239">0x10000</span></span></p></td>
<td><p><span data-ttu-id="1a339-240">Wenn diese Einstellung eingestellt ist, stellt dies ein Group-Objekt dar.</span><span class="sxs-lookup"><span data-stu-id="1a339-240">If set, this represents a group object.</span></span> <span data-ttu-id="1a339-241">Der Benutzerreplikationsdienst verwendet dieses Flag-Bit, um <strong></strong> Kontakte mit dem GroupType-Attribut einzubeziehen, deren Anwesenheitsstatus auf eine Gruppe (beispielsweise eine Verteilerliste oder eine Sicherheitsgruppe) hinweist.</span><span class="sxs-lookup"><span data-stu-id="1a339-241">User Replicator uses this flag bit to include contacts with the <strong>groupType</strong> attribute whose presence indicates a group (for example, a distribution list or security group).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1a339-242">0x20000</span><span class="sxs-lookup"><span data-stu-id="1a339-242">0x20000</span></span></p></td>
<td><p><span data-ttu-id="1a339-243">Ist dieser Wert festzulegen, verwendet der Benutzerreplikationsdienst dieses Flag-Bit, um dieses Attribut in gerätespezifische Adressbuch Server Dateien (also Dateien mit der Erweiterung ". kleckse") einzubeziehen.</span><span class="sxs-lookup"><span data-stu-id="1a339-243">If set, User Replicator uses this flag bit to include this attribute in device-specific Address Book Server files (that is, files with a .dabs extension).</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="1a339-244">In früheren Versionen von lync Server musste der Administrator beim Anwenden einer Änderung an Active Directory CSUserDatabase und **Update – CSAddressBook** Windows PowerShell-Cmdlets ausführen, um die Änderung auf dem lync **-** Server beizubehalten. Benutzerdatenbank und RTCab-Datenbank sofort.</span><span class="sxs-lookup"><span data-stu-id="1a339-244">In previous versions of Lync Server, when applying a change to Active Directory, the administrator would be required to run **Update -CSUserDatabase** and **Update –CSAddressBook** Windows PowerShell cmdlets to persist the change to the Lync Server user database and RTCab database immediately.</span></span> <span data-ttu-id="1a339-245">In lync Server 2013 wird der lync Server-Benutzerreplikationsdienst die Änderungen aus Active Directory aufnehmen und die lync Server-Benutzerdatenbank basierend auf einem konfigurierten Intervall aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="1a339-245">In Lync Server 2013, Lync Server User Replicator will pick up the changes from Active Directory and update the Lync Server user database based on a configured interval.</span></span> <span data-ttu-id="1a339-246">Der lync Server-Benutzerreplikationsdienst gibt die Änderungen auch schnell an die RTCab-Datenbank weiter, ohne dass der Administrator Update-CSAddressBook ausführen muss.</span><span class="sxs-lookup"><span data-stu-id="1a339-246">Lync Server User Replicator will also propagate the changes to the RTCab database quickly without the administrator having to run Update-CSAddressBook.</span></span> <span data-ttu-id="1a339-247">Wenn die Adressbuch-Webabfrage aktiviert ist, werden die Änderungen in den Suchergebnissen von lync-Clients wiedergegeben.</span><span class="sxs-lookup"><span data-stu-id="1a339-247">If Address Book Web query is enabled, then the changes will be reflected in search results by Lync clients.</span></span> <span data-ttu-id="1a339-248">Administratoren müssen nur Update-CSAddressBook ausführen, wenn der Download der Adressbuchdatei aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="1a339-248">Administrators will only need to run Update -CSAddressBook if the Address Book file download is enabled.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="1a339-249">Standardmäßig wird der lync Server-Benutzerreplikationsdienst automatisch alle 5 Minuten ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="1a339-249">By default Lync Server User Replicator runs automatically every 5 minutes.</span></span> <span data-ttu-id="1a339-250">Sie können dieses Intervall mithilfe von "Satz-CSUserReplicatorConfiguration-ReplicationCycleInterval &lt; &gt;" konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="1a339-250">You can configure this interval by using Set -CSUserReplicatorConfiguration -ReplicationCycleInterval &lt;&gt;.</span></span>



</div>

</div>

<div>

## <a name="filtering-the-address-book"></a><span data-ttu-id="1a339-251">Filtern des Adressbuchs</span><span class="sxs-lookup"><span data-stu-id="1a339-251">Filtering the Address Book</span></span>

<span data-ttu-id="1a339-252">Die in den Adressbuch Server Dateien aufgefüllten Benutzer können basierend auf bestimmten Active Directory-Domänendienst Attributen, die in der AbAttribute-Tabelle aufgelistet sind, gesteuert werden.</span><span class="sxs-lookup"><span data-stu-id="1a339-252">The users populated in the Address Book Server files can be controlled based on certain Active Directory Domain Services attributes listed in the AbAttribute table.</span></span> <span data-ttu-id="1a339-253">Ein solches Attribut, das für die Filterung verwendet wird, ist das **msExchangeHideFromAddressBook** -Attribut.</span><span class="sxs-lookup"><span data-stu-id="1a339-253">One such attribute used for filtering is the **msExchangeHideFromAddressBook** attribute.</span></span> <span data-ttu-id="1a339-254">Hierbei handelt es sich um ein vom Exchange-Schema hinzugefügtes Benutzerattribut.</span><span class="sxs-lookup"><span data-stu-id="1a339-254">This is a user attribute added by the Exchange schema.</span></span> <span data-ttu-id="1a339-255">Wenn der Wert dieses Attributs wahr ist, verwendet Exchange Server dieses Attribut zum Ausblenden des Kontakts aus der globalen Outlook-Adressliste (GAL).</span><span class="sxs-lookup"><span data-stu-id="1a339-255">If the value of this attribute is TRUE, Exchange Server uses this attribute to hide the contact from the Outlook Global Address List (GAL).</span></span> <span data-ttu-id="1a339-256">Wenn der Wert dieses Attributs auf "true" festgelegt ist, enthält der Benutzerreplikationsdienst diesen Benutzer in der Tabelle AbUserEntry-Tabelle nicht, und dieser Benutzer befindet sich nicht in den Adressbuch Server Dateien.</span><span class="sxs-lookup"><span data-stu-id="1a339-256">Similarly, if the value of this attribute is TRUE, User Replicator does not include that user in the AbUserEntry table and this user will not be in the Address Book Server files.</span></span>

<span data-ttu-id="1a339-257">Sie können einige Flag-Bits verwenden, um einen Filter für die Verwendung in Adressbuch Server Attributen zu definieren.</span><span class="sxs-lookup"><span data-stu-id="1a339-257">You can use some flag bits to define a filter to use on Address Book Server attributes.</span></span> <span data-ttu-id="1a339-258">So kann beispielsweise das vorhanden sein bestimmter kennzeichenbits ein Attribut als Include-Attribut oder Exclude-Attribut identifizieren.</span><span class="sxs-lookup"><span data-stu-id="1a339-258">For example, the presence of certain flag bits can identify an attribute as an include attribute or an exclude attribute.</span></span> <span data-ttu-id="1a339-259">Der Benutzerreplikationsdienst filtert Kontakte aus, die ein Exclude-Attribut enthalten, und filtert Contains, die kein Include-Attribut enthalten.</span><span class="sxs-lookup"><span data-stu-id="1a339-259">User Replicator filters out contacts that contain an exclude attribute and filters out contains that do not contain an include attribute.</span></span>

<div>


> [!WARNING]  
> <span data-ttu-id="1a339-260">Weitere Informationen zum Filtern des Adressbuchs finden Sie unter <A href="https://technet.microsoft.com/en-us/library/gg415643(v=ocs.15)">Adressbuch Server-Cmdlets in lync Server 2013</A>und <A href="http://go.microsoft.com/fwlink/?linkid=330430">Filtern des lync 2013-Adressbuchs</A> .</span><span class="sxs-lookup"><span data-stu-id="1a339-260">For more information about filtering the Address Book, see <A href="https://technet.microsoft.com/en-us/library/gg415643(v=ocs.15)">Address Book Server cmdlets in Lync Server 2013</A>, and <A href="http://go.microsoft.com/fwlink/?linkid=330430">Filter Lync 2013 address book</A></span></span>



</div>

<span data-ttu-id="1a339-261">Derzeit gibt es drei verschiedene Filter.</span><span class="sxs-lookup"><span data-stu-id="1a339-261">Currently, there are three different filters.</span></span> <span data-ttu-id="1a339-262">In der folgenden Tabelle sind diese Filter aufgelistet.</span><span class="sxs-lookup"><span data-stu-id="1a339-262">The following table lists these filters.</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="1a339-263">Attribut</span><span class="sxs-lookup"><span data-stu-id="1a339-263">Attribute</span></span></th>
<th><span data-ttu-id="1a339-264">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="1a339-264">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="1a339-265">0x800</span><span class="sxs-lookup"><span data-stu-id="1a339-265">0x800</span></span></p></td>
<td><p><span data-ttu-id="1a339-266">Wenn festzulegen, wird ein erforderliches Attribut für einen Kontakt angegeben.</span><span class="sxs-lookup"><span data-stu-id="1a339-266">If set, this identifies a required attribute for a contact.</span></span> <span data-ttu-id="1a339-267">Der Benutzerreplikationsdienst verwendet dieses Flag-Bit, um Kontakte zu filtern, die nicht mindestens ein erforderliches Attribut enthalten.</span><span class="sxs-lookup"><span data-stu-id="1a339-267">User Replicator uses this flag bit to filter out contacts that do not contain at least one required attribute.</span></span> <span data-ttu-id="1a339-268">OuPathId ist ein erforderliches Attribut, das immer gesetzt ist.</span><span class="sxs-lookup"><span data-stu-id="1a339-268">The OuPathId is a required attribute, which is always set.</span></span> <span data-ttu-id="1a339-269">Daher sollte mindestens eines der anderen erforderlichen Attribute festzulegen sein.</span><span class="sxs-lookup"><span data-stu-id="1a339-269">So at least one of other required attributes should be set.</span></span> <span data-ttu-id="1a339-270">Andernfalls wird der Kontakt (mit dem Wert des required-Attributs OuPathId) immer noch nicht in die Datenbank geschrieben.</span><span class="sxs-lookup"><span data-stu-id="1a339-270">Otherwise, contact (that is, with value of required attribute OuPathId) will still not be written to database.</span></span> <span data-ttu-id="1a339-271">Wenn beispielsweise <strong>telephoneNumber</strong> und <strong>homePhone</strong> als erforderliche Attribute definiert sind, werden nur die Kontakte, die mindestens eines dieser Attribute aufweisen, in die Datenbank geschrieben.</span><span class="sxs-lookup"><span data-stu-id="1a339-271">For example, if <strong>telephoneNumber</strong> and <strong>homePhone</strong> are defined as required attributes, only the contacts that have at least one of these attributes are written to the database.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1a339-272">0x4000</span><span class="sxs-lookup"><span data-stu-id="1a339-272">0x4000</span></span></p></td>
<td><p><span data-ttu-id="1a339-273">Wenn festzulegen, wird ein Exclude-Attribut identifiziert.</span><span class="sxs-lookup"><span data-stu-id="1a339-273">If set, this identifies an exclude attribute.</span></span> <span data-ttu-id="1a339-274">Der Benutzerreplikationsdienst verwendet dieses Flag-Bit, um Kontakte zu filtern, die dieses Attribut enthalten.</span><span class="sxs-lookup"><span data-stu-id="1a339-274">User Replicator uses this flag bit to filter out contacts that contain this attribute.</span></span> <span data-ttu-id="1a339-275">Wenn beispielsweise <strong>Attribut msRTCSIP-PrimaryUserAddress</strong> als Exclude-Attribut definiert ist, werden Kontakte mit diesem Attribut nicht in die Datenbank geschrieben.</span><span class="sxs-lookup"><span data-stu-id="1a339-275">For example, if <strong>msRTCSIP-PrimaryUserAddress</strong> is defined as an exclude attribute, contacts that have this attribute are not written to the database.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1a339-276">0X8000</span><span class="sxs-lookup"><span data-stu-id="1a339-276">0x8000</span></span></p></td>
<td><p><span data-ttu-id="1a339-277">Wenn festzulegen, wird ein Include-Attribut angegeben.</span><span class="sxs-lookup"><span data-stu-id="1a339-277">If set, this identifies an include attribute.</span></span> <span data-ttu-id="1a339-278">Der Benutzerreplikationsdienst verwendet dieses Flag-Bit, um Kontakte zu filtern, die dieses Attribut nicht enthalten.</span><span class="sxs-lookup"><span data-stu-id="1a339-278">User Replicator uses this flag bit to filter out contacts that do not contain this attribute.</span></span> <span data-ttu-id="1a339-279">Wenn beispielsweise <strong>Attribut msRTCSIP-PrimaryUserAddress</strong> als Include-Attribut definiert ist, werden nur die Kontakte, die dieses Attribut aufweisen, in die Datenbank geschrieben.</span><span class="sxs-lookup"><span data-stu-id="1a339-279">For example, if <strong>msRTCSIP-PrimaryUserAddress</strong> is defined as an include attribute, only the contacts that have this attribute are written to the database.</span></span></p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> <span data-ttu-id="1a339-280">Wenn sowohl das 0x4000 (Exclude-Attribut) als auch das 0X8000 (Include-Attribut)-Flag-Bits gesetzt sind, überschreibt das 0x4000-Bit das 0X8000-Bit, und der Kontakt wird ausgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="1a339-280">If both the 0x4000 (exclude attribute) and 0x8000 (include attribute) flag bits are set, the 0x4000 bit overrides the 0x8000 bit and the contact is excluded.</span></span>



</div>

<span data-ttu-id="1a339-281">Zwar können Sie das Adressbuch so filtern, dass nur bestimmte Benutzer eingeschlossen werden, aber das Einschränken von Einträgen schränkt nicht die Möglichkeit anderer Benutzer ein, die gefilterten Benutzer zu kontaktieren oder Ihren Anwesenheitsstatus anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="1a339-281">Although you can filter the Address Book to include only certain users, limiting entries does not limit other users' ability to contact the filtered users or to see their presence status.</span></span> <span data-ttu-id="1a339-282">Benutzer können jederzeit Sofortnachrichten suchen, manuell senden oder Anrufe an Benutzer, die sich nicht im Adressbuch befinden, manuell initiieren, indem Sie den vollständigen Anmeldenamen eines Benutzers eingeben.</span><span class="sxs-lookup"><span data-stu-id="1a339-282">Users can always find, manually send instant messages, or manually initiate calls to users not in the Address Book by entering a user's complete sign-in name.</span></span> <span data-ttu-id="1a339-283">Auch Kontaktinformationen für einen Benutzer finden Sie in Outlook.</span><span class="sxs-lookup"><span data-stu-id="1a339-283">Also, contact information for a user could also be found in Outlook.</span></span>

<span data-ttu-id="1a339-284">Wenn Sie über vollständige Kontaktdatensätze in den Adressbuchdateien verfügen, können Sie mithilfe von lync Server e-Mail-, Telefon-oder Enterprise-Sprachanrufe initiieren (das heißt, wenn Enterprise-VoIP auf dem Server aktiviert ist), mit Benutzern, die nicht für die Sitzungs Initiierung konfiguriert sind. Protocol (SIP) verwenden, ziehen einige Organisationen es vor, nur SIP-fähige Benutzer in Ihre Adressbuch Server Einträge einzubeziehen.</span><span class="sxs-lookup"><span data-stu-id="1a339-284">While having full contact records in the Address Book files enables you to use Lync Server to initiate email, telephone, or Enterprise Voice calls (that is, if Enterprise Voice is enabled on the server) with users that are not configured for Session Initiation Protocol (SIP), some organizations prefer to include only SIP-enabled users in their Address Book Server entries.</span></span> <span data-ttu-id="1a339-285">Sie können das Adressbuch so filtern, dass nur SIP-fähige Benutzer eingeschlossen werden, indem Sie das 0x800-Bit in der Spalte **Flags** der folgenden erforderlichen Attribute löschen: mailNickname, **telephoneNumber**, **homePhone**und **Handy**. \*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="1a339-285">You can filter the Address Book to include only SIP-enabled users by clearing the 0x800 bit in the **Flags** column of the following required attributes: **mailNickname**, **telephoneNumber**, **homePhone**, and **mobile**.</span></span> <span data-ttu-id="1a339-286">Sie können das Adressbuch auch filtern, um nur SIP-fähige Benutzer einzubeziehen, indem Sie das 0X8000 (Include-Attribut) in der Spalte **Flags** des **Attribut msRTCSIP-PrimaryUserAddress-** Attributs festlegen.</span><span class="sxs-lookup"><span data-stu-id="1a339-286">You can also filter the Address Book to include only SIP-enabled users by setting the 0x8000 (include attribute) in the **Flags** column of the **msRTCSIP-PrimaryUserAddress** attribute.</span></span> <span data-ttu-id="1a339-287">Dadurch können auch Dienstkonten aus den Adressbuchdateien ausgeschlossen werden.</span><span class="sxs-lookup"><span data-stu-id="1a339-287">This also helps to exclude service accounts from the Address Book files.</span></span>

<span data-ttu-id="1a339-288">Nachdem Sie die AbAttribute-Tabelle geändert haben, können Sie die Daten in der Tabelle AbUserEntry-Tabelle aktualisieren, indem Sie den Befehl Cmdlet **Update-CsUserDatabase** ausführen.</span><span class="sxs-lookup"><span data-stu-id="1a339-288">After you modify the AbAttribute table, you can refresh the data in the AbUserEntry table by running the cmdlet **Update-CsUserDatabase** command.</span></span> <span data-ttu-id="1a339-289">Nach Abschluss der ur-Replikation können Sie die Datei im Dateispeicher des Adressbuchservers aktualisieren, indem Sie den Befehl Cmdlet **UpdateCsAddressBook** manuell ausführen.</span><span class="sxs-lookup"><span data-stu-id="1a339-289">After UR replication completes, you can update the file in the Address Book Server file store by manually running the cmdlet **UpdateCsAddressBook** command.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="1a339-290">Der Front-End-Server, auf dem der Adressbuchserver gespeichert ist, kann nicht administrativ konfiguriert werden.</span><span class="sxs-lookup"><span data-stu-id="1a339-290">The Front End Server that the Address Book Server is placed is not administratively configurable.</span></span> <span data-ttu-id="1a339-291">Eine wird während der Bereitstellung ausgewählt – in der Regel der erste bereitgestellte Front-End-Server.</span><span class="sxs-lookup"><span data-stu-id="1a339-291">One is chosen during deployment—typically, the first Front End Server deployed.</span></span> <span data-ttu-id="1a339-292">Bei einem Fehler wechselt der Adressbuchdienst zu einem anderen Front-End-Server und erfordert keine administrative Beachtung.</span><span class="sxs-lookup"><span data-stu-id="1a339-292">In the event of failure, the Address Book Service will move to another Front End Server, and requires no administrative attention.</span></span>



</div>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="1a339-293">Wenn Sie Ihre Infrastruktur von einer Bereitstellung mit mehreren Gesamtstrukturen oder von einer übergeordneten/untergeordneten Bereitstellung konsolidiert oder anderweitig geändert haben (wie etwa das Konsolidieren Ihrer Infrastruktur, bevor Sie zu lync Server wechseln), stellen Sie möglicherweise fest, dass der Adressbuchdienst heruntergeladen wird, und die Die Adressbuch-Webabfrage schlägt für einige Benutzer fehl.</span><span class="sxs-lookup"><span data-stu-id="1a339-293">If you have consolidated or otherwise modified your infrastructure from a multi-forest deployment or a parent/child deployment (such as consolidating your infrastructure before moving to Lync Server), you may find that the Address Book service download and the Address Book Web Query fails for some users.</span></span> <span data-ttu-id="1a339-294">Bei einer Bereitstellung mit mehreren Domänen oder Gesamtstrukturen wird das Attribut <STRONG>Attribut msRTCSIP-OriginatorSid</STRONG> für die Benutzerobjekte aufgefüllt, die das Problem aufweisen.</span><span class="sxs-lookup"><span data-stu-id="1a339-294">When in a deployment that had multiple domains or forests, the attribute <STRONG>MsRTCSIP-OriginatorSid</STRONG> is populated on the user objects that are exhibiting the issue.</span></span> <span data-ttu-id="1a339-295">Das <STRONG>Attribut msRTCSIP-OriginatorSid-</STRONG> Attribut muss für diese Objekte auf Null festgesetzt werden, um das Problem zu beheben.</span><span class="sxs-lookup"><span data-stu-id="1a339-295">The <STRONG>MsRTCSIP-OriginatorSid</STRONG> attribute must be set to NULL on these objects to resolve the issue.</span></span>



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

