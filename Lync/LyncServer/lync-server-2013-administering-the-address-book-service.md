---
title: 'Lync Server 2013: Verwalten des Adressbuchdiensts'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Administering the Address Book Service
ms:assetid: 801e4243-9670-4477-aa2f-88b61ecf5351
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg429711(v=OCS.15)
ms:contentKeyID: 48184649
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 45dbc2c71cf34515f8f6176e4f579e6683ad319e
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2020
ms.locfileid: "42146258"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="administering-the-address-book-service-in-lync-server-2013"></a><span data-ttu-id="b0079-102">Verwalten des Adressbuchdiensts in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b0079-102">Administering the Address Book Service in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b0079-103">_**Letztes Änderungsstand des Themas:** 2014-02-05_</span><span class="sxs-lookup"><span data-stu-id="b0079-103">_**Topic Last Modified:** 2014-02-05_</span></span>

<span data-ttu-id="b0079-104">Im Rahmen der Bereitstellung von lync Server, Enterprise Edition oder Standard Edition-Server wird der Adressbuchdienst standardmäßig installiert.</span><span class="sxs-lookup"><span data-stu-id="b0079-104">As a part of the deployment of Lync Server, Enterprise Edition or Standard Edition server, the Address Book Service is installed by default.</span></span> <span data-ttu-id="b0079-105">Die vom Adressbuchdienst – RTCab – verwendete Datenbank wird auf dem SQL Server erstellt (für Enterprise Edition ist dies die Back-End-SQL Server; für Standard Edition-Server die verbundene SQL Server).</span><span class="sxs-lookup"><span data-stu-id="b0079-105">The database used by the Address Book Service – RTCab – is created on the SQL Server (for Enterprise Edition, this is the back-end SQL Server; for Standard Edition server, the collocated SQL Server).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="b0079-106">Informationen zum Bearbeiten von Active Directory-Domänendienste Objektattributen mithilfe von <STRONG>ADSI-Bearbeitung</STRONG> finden Sie unter <A href="https://go.microsoft.com/fwlink/?linkid=330427">ADSI Edit</A>.</span><span class="sxs-lookup"><span data-stu-id="b0079-106">For information about using <STRONG>ADSI Edit</STRONG> to edit Active Directory Domain Services object attributes, see <A href="https://go.microsoft.com/fwlink/?linkid=330427">ADSI Edit</A>.</span></span> <span data-ttu-id="b0079-107">Informationen zu einem Tool im Resource Kit speziell für den Adressbuchdienst finden Sie unter <A href="https://go.microsoft.com/fwlink/?linkid=330429">Microsoft lync Server 2013 Resource Kit Tools</A>.</span><span class="sxs-lookup"><span data-stu-id="b0079-107">For information about a tool in the Resource Kit specifically for the Address Book service, see <A href="https://go.microsoft.com/fwlink/?linkid=330429">Microsoft Lync Server 2013 Resource Kit Tools</A>.</span></span>



</div>

<div>

## <a name="address-book-server-phone-number-normalization"></a><span data-ttu-id="b0079-108">Normalisierung von Telefonnummern auf dem Adressbuchserver</span><span class="sxs-lookup"><span data-stu-id="b0079-108">Address Book Server Phone Number Normalization</span></span>

<span data-ttu-id="b0079-109">Lync Server erfordert standardisierte RFC 3966/E. 164-Telefonnummern.</span><span class="sxs-lookup"><span data-stu-id="b0079-109">Lync Server requires standardized RFC 3966/E.164 phone numbers.</span></span> <span data-ttu-id="b0079-110">Um Telefonnummern zu verwenden, die unstrukturiert oder inkonsistent formatiert sind, verwendet lync Server den Adressbuch Server, um Telefonnummern vorverarbeiten, bevor Sie an die Normalisierungsregeln übergeben werden.</span><span class="sxs-lookup"><span data-stu-id="b0079-110">To use phone numbers that are unstructured or inconsistently formatted, Lync Server relies on the Address Book Server to preprocess phone numbers before they are handed off to the normalization rules.</span></span> <span data-ttu-id="b0079-111">Wenn eine Telefonnummer aus dem Adressbuch verwendet wird und die Normalisierungsregel angewendet wird, können Clients wie lync Phone Edition und lync Mobile diese normalisierten Nummern verwenden.</span><span class="sxs-lookup"><span data-stu-id="b0079-111">When a phone number is used from the address book and the normalization rule is applied, clients, such as Lync Phone Edition and Lync Mobile, can use these normalized numbers.</span></span>

<span data-ttu-id="b0079-p104">Die in früheren Versionen verwendeten Normalisierungsregeln funktionieren möglicherweise nicht ordnungsgemäß, wenn sie nicht angepasst werden. Da die Leerzeichen und die nicht erforderlichen Zeichen vor Einsatz der Normalisierungsregeln entfernt werden, tritt bei Ihrer Normalisierungsregel eventuell ein Fehler auf, falls der reguläre Ausdruck speziell nach einem Bindestrich oder einem anderen Zeichen sucht, das entfernt wurde. Überprüfen Sie Ihre Normalisierungsregeln, und stellen Sie sicher, dass sie nicht nach diesen nicht erforderlichen Zeichen suchen bzw. dass die Regel trotz Fehler fortgesetzt werden kann, wenn das Zeichen sich nicht an der von der Regel erwarteten Stelle befindet.</span><span class="sxs-lookup"><span data-stu-id="b0079-p104">The normalization rules that were used in previous versions may not work properly without some adjustments. Because the white space and non-mandatory characters are removed prior to the normalization rules, if your regex expression is specifically looking for a dash or other character that was removed, your normalization rule might fail. You should review your normalization rules to ensure that either they are not looking for these non-mandatory characters, or that the rule can fail gracefully and continue in the event that the character is not present where the rule anticipates it will be.</span></span>

</div>

<div>

## <a name="user-replicator-and-address-book-server"></a><span data-ttu-id="b0079-115">Benutzerreplikationsdienst und Adressbuchserver</span><span class="sxs-lookup"><span data-stu-id="b0079-115">User Replicator and Address Book Server</span></span>

<span data-ttu-id="b0079-116">Der Adressbuchserver nutzt die vom Benutzerreplikationsdienst bereitgestellten Informationen zum Aktualisieren der Daten, die er anfangs von der globalen Adressliste (GAL) erhält.</span><span class="sxs-lookup"><span data-stu-id="b0079-116">The Address Book Server uses data provided by User Replicator to update the information that it initially obtains from the global address list (GAL).</span></span> <span data-ttu-id="b0079-117">Der Benutzerreplikationsdienst schreibt die Active Directory-Domänendienste Attribute für alle Benutzer, Kontakte und Gruppen in die Tabelle AbUserEntry-Tabelle in der Datenbank, und der Adressbuchserver synchronisiert die Benutzerdaten aus der Datenbank in Dateien im Dateispeicher des Adressbuchservers und in die Adressbuchdatenbank RTCab.</span><span class="sxs-lookup"><span data-stu-id="b0079-117">User Replicator writes the Active Directory Domain Services attributes for each user, contact, and group into the AbUserEntry table in the database and the Address Book Server syncs the user data from the database into files in the Address Book Server file store and into the Address Book database RTCab.</span></span> <span data-ttu-id="b0079-118">Das Schema für die Tabelle "AbUserEntry" verwendet zwei Spalten, **UserGuid** und **UserData**.</span><span class="sxs-lookup"><span data-stu-id="b0079-118">The schema for the AbUserEntry table uses two columns, **UserGuid** and **UserData**.</span></span> <span data-ttu-id="b0079-119">**UserGuid** ist die Indexspalte und enthält die 16-Byte-GUID des Active Directory-Objekts.</span><span class="sxs-lookup"><span data-stu-id="b0079-119">**UserGuid** is the index column and contains the 16-byte GUID of the Active Directory object.</span></span> <span data-ttu-id="b0079-120">**UserData** ist eine Bildspalte, die alle zuvor erwähnten Active Directory-Domänendienste Attribute für diesen Kontakt enthält.</span><span class="sxs-lookup"><span data-stu-id="b0079-120">**UserData** is an image column which contains all of the previously mentioned Active Directory Domain Services attributes for that contact.</span></span>

<span data-ttu-id="b0079-121">Der Benutzerreplikationsdienst legt fest, welche Active Directory Attribute durchlesen einer Konfigurationstabelle, die sich in derselben SQL Server basierten Instanz wie die Tabelle AbUserEntry-Tabelle befindet, geschrieben werden sollen.</span><span class="sxs-lookup"><span data-stu-id="b0079-121">User Replicator determines which Active Directory attributes to write by reading a configuration table located in the same SQL Server-based instance as the AbUserEntry table.</span></span> <span data-ttu-id="b0079-122">Die Tabelle "AbAttribute" enthält vier Spalten, **ID**, **Name**, **Flags** und **Enable**.</span><span class="sxs-lookup"><span data-stu-id="b0079-122">The AbAttribute table contains three columns, **ID**, **Name**, **Flags**, and **Enable**.</span></span> <span data-ttu-id="b0079-123">Die Tabelle wird bei der Datenbankeinrichtung erstellt.</span><span class="sxs-lookup"><span data-stu-id="b0079-123">The table is created during database setup.</span></span> <span data-ttu-id="b0079-124">Ist die Tabelle "AbAttribute" leer, überspringt der Benutzerreplikationsdienst die Logik zur Verarbeitung der Tabelle "AbUserEntry".</span><span class="sxs-lookup"><span data-stu-id="b0079-124">If the AbAttribute table is empty, User Replicator skips its AbUserEntry table processing logic.</span></span> <span data-ttu-id="b0079-125">Die Adressbuchserver-Attribute sind dynamisch und werden aus der Tabelle "AbAttribute" geladen, die anfänglich vom Adressbuchserver bei seiner Aktivierung geschrieben wird.</span><span class="sxs-lookup"><span data-stu-id="b0079-125">Address Book Server attributes are dynamic and are retrieved from the AbAttribute table, which is initially written by the Address Book Server when the Address Book Server is activated.</span></span>

<span data-ttu-id="b0079-126">Die Aktivierung der Adressbuch Server füllt die AbAttribute-Tabelle mit den in der folgenden Tabelle aufgeführten Werten.</span><span class="sxs-lookup"><span data-stu-id="b0079-126">Address Book Server activation populates the AbAttribute table with the values shown in the following table.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="b0079-127">ID</span><span class="sxs-lookup"><span data-stu-id="b0079-127">ID</span></span></th>
<th><span data-ttu-id="b0079-128">Name</span><span class="sxs-lookup"><span data-stu-id="b0079-128">Name</span></span></th>
<th><span data-ttu-id="b0079-129">Flags</span><span class="sxs-lookup"><span data-stu-id="b0079-129">Flags</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b0079-130">1</span><span class="sxs-lookup"><span data-stu-id="b0079-130">1</span></span></p></td>
<td><p><span data-ttu-id="b0079-131">givenName</span><span class="sxs-lookup"><span data-stu-id="b0079-131">givenName</span></span></p></td>
<td><p><span data-ttu-id="b0079-132">0x01400000</span><span class="sxs-lookup"><span data-stu-id="b0079-132">0x01400000</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b0079-133">2</span><span class="sxs-lookup"><span data-stu-id="b0079-133">2</span></span></p></td>
<td><p><span data-ttu-id="b0079-134">SN</span><span class="sxs-lookup"><span data-stu-id="b0079-134">Sn</span></span></p></td>
<td><p><span data-ttu-id="b0079-135">0x02400000</span><span class="sxs-lookup"><span data-stu-id="b0079-135">0x02400000</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b0079-136">3</span><span class="sxs-lookup"><span data-stu-id="b0079-136">3</span></span></p></td>
<td><p><span data-ttu-id="b0079-137">displayName</span><span class="sxs-lookup"><span data-stu-id="b0079-137">displayName</span></span></p></td>
<td><p><span data-ttu-id="b0079-138">0x03420000</span><span class="sxs-lookup"><span data-stu-id="b0079-138">0x03420000</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b0079-139">4</span><span class="sxs-lookup"><span data-stu-id="b0079-139">4</span></span></p></td>
<td><p><span data-ttu-id="b0079-140">Titel</span><span class="sxs-lookup"><span data-stu-id="b0079-140">Title</span></span></p></td>
<td><p><span data-ttu-id="b0079-141">0x04000000</span><span class="sxs-lookup"><span data-stu-id="b0079-141">0x04000000</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b0079-142">5</span><span class="sxs-lookup"><span data-stu-id="b0079-142">5</span></span></p></td>
<td><p><span data-ttu-id="b0079-143">mailNickname</span><span class="sxs-lookup"><span data-stu-id="b0079-143">mailNickname</span></span></p></td>
<td><p><span data-ttu-id="b0079-144">0x05400000</span><span class="sxs-lookup"><span data-stu-id="b0079-144">0x05400000</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b0079-145">6 </span><span class="sxs-lookup"><span data-stu-id="b0079-145">6</span></span></p></td>
<td><p><span data-ttu-id="b0079-146">Company</span><span class="sxs-lookup"><span data-stu-id="b0079-146">Company</span></span></p></td>
<td><p><span data-ttu-id="b0079-147">0x06000000</span><span class="sxs-lookup"><span data-stu-id="b0079-147">0x06000000</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b0079-148">7 </span><span class="sxs-lookup"><span data-stu-id="b0079-148">7</span></span></p></td>
<td><p><span data-ttu-id="b0079-149">physicalDeliveryOfficeName</span><span class="sxs-lookup"><span data-stu-id="b0079-149">physicalDeliveryOfficeName</span></span></p></td>
<td><p><span data-ttu-id="b0079-150">0x07000000</span><span class="sxs-lookup"><span data-stu-id="b0079-150">0x07000000</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b0079-151">8 </span><span class="sxs-lookup"><span data-stu-id="b0079-151">8</span></span></p></td>
<td><p><span data-ttu-id="b0079-152">msRTCSIP-PrimaryUserAddress</span><span class="sxs-lookup"><span data-stu-id="b0079-152">msRTCSIP-PrimaryUserAddress</span></span></p></td>
<td><p><span data-ttu-id="b0079-153">0x08520C00</span><span class="sxs-lookup"><span data-stu-id="b0079-153">0x08520C00</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b0079-154">9 </span><span class="sxs-lookup"><span data-stu-id="b0079-154">9</span></span></p></td>
<td><p><span data-ttu-id="b0079-155">telephoneNumber</span><span class="sxs-lookup"><span data-stu-id="b0079-155">telephoneNumber</span></span></p></td>
<td><p><span data-ttu-id="b0079-156">0x09022800</span><span class="sxs-lookup"><span data-stu-id="b0079-156">0x09022800</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b0079-157">10 </span><span class="sxs-lookup"><span data-stu-id="b0079-157">10</span></span></p></td>
<td><p><span data-ttu-id="b0079-158">homePhone</span><span class="sxs-lookup"><span data-stu-id="b0079-158">homePhone</span></span></p></td>
<td><p><span data-ttu-id="b0079-159">0x0A302800</span><span class="sxs-lookup"><span data-stu-id="b0079-159">0x0A302800</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b0079-160">11 </span><span class="sxs-lookup"><span data-stu-id="b0079-160">11</span></span></p></td>
<td><p><span data-ttu-id="b0079-161">Mobil</span><span class="sxs-lookup"><span data-stu-id="b0079-161">Mobile</span></span></p></td>
<td><p><span data-ttu-id="b0079-162">0x0B622800</span><span class="sxs-lookup"><span data-stu-id="b0079-162">0x0B622800</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b0079-163">12</span><span class="sxs-lookup"><span data-stu-id="b0079-163">12</span></span></p></td>
<td><p><span data-ttu-id="b0079-164">otherTelephone</span><span class="sxs-lookup"><span data-stu-id="b0079-164">otherTelephone</span></span></p></td>
<td><p><span data-ttu-id="b0079-165">0x0C302000</span><span class="sxs-lookup"><span data-stu-id="b0079-165">0x0C302000</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b0079-166">13 </span><span class="sxs-lookup"><span data-stu-id="b0079-166">13</span></span></p></td>
<td><p><span data-ttu-id="b0079-167">ipPhone</span><span class="sxs-lookup"><span data-stu-id="b0079-167">ipPhone</span></span></p></td>
<td><p><span data-ttu-id="b0079-168">0x0D302000</span><span class="sxs-lookup"><span data-stu-id="b0079-168">0x0D302000</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b0079-169">14 </span><span class="sxs-lookup"><span data-stu-id="b0079-169">14</span></span></p></td>
<td><p><span data-ttu-id="b0079-170">E-Mail</span><span class="sxs-lookup"><span data-stu-id="b0079-170">Mail</span></span></p></td>
<td><p><span data-ttu-id="b0079-171">0x0E500000</span><span class="sxs-lookup"><span data-stu-id="b0079-171">0x0E500000</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b0079-172">15 </span><span class="sxs-lookup"><span data-stu-id="b0079-172">15</span></span></p></td>
<td><p><span data-ttu-id="b0079-173">groupType</span><span class="sxs-lookup"><span data-stu-id="b0079-173">groupType</span></span></p></td>
<td><p><span data-ttu-id="b0079-174">0x0F010800</span><span class="sxs-lookup"><span data-stu-id="b0079-174">0x0F010800</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b0079-175">16 </span><span class="sxs-lookup"><span data-stu-id="b0079-175">16</span></span></p></td>
<td><p><span data-ttu-id="b0079-176">Abteilung</span><span class="sxs-lookup"><span data-stu-id="b0079-176">Department</span></span></p></td>
<td><p><span data-ttu-id="b0079-177">0x10000000</span><span class="sxs-lookup"><span data-stu-id="b0079-177">0x10000000</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b0079-178">17 </span><span class="sxs-lookup"><span data-stu-id="b0079-178">17</span></span></p></td>
<td><p><span data-ttu-id="b0079-179">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="b0079-179">Description</span></span></p></td>
<td><p><span data-ttu-id="b0079-180">0x11000100</span><span class="sxs-lookup"><span data-stu-id="b0079-180">0x11000100</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b0079-181">18 </span><span class="sxs-lookup"><span data-stu-id="b0079-181">18</span></span></p></td>
<td><p><span data-ttu-id="b0079-182">Manager</span><span class="sxs-lookup"><span data-stu-id="b0079-182">Manager</span></span></p></td>
<td><p><span data-ttu-id="b0079-183">0x12040001</span><span class="sxs-lookup"><span data-stu-id="b0079-183">0x12040001</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b0079-184">19</span><span class="sxs-lookup"><span data-stu-id="b0079-184">19</span></span></p></td>
<td><p><span data-ttu-id="b0079-185">ProxyAddress</span><span class="sxs-lookup"><span data-stu-id="b0079-185">proxyAddress</span></span></p></td>
<td><p><span data-ttu-id="b0079-186">0x00500105</span><span class="sxs-lookup"><span data-stu-id="b0079-186">0x00500105</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b0079-187">20</span><span class="sxs-lookup"><span data-stu-id="b0079-187">20</span></span></p></td>
<td><p><span data-ttu-id="b0079-188">msExchHideFromAddressLists</span><span class="sxs-lookup"><span data-stu-id="b0079-188">msExchHideFromAddressLists</span></span></p></td>
<td><p><span data-ttu-id="b0079-189">0xFF000003</span><span class="sxs-lookup"><span data-stu-id="b0079-189">0xFF000003</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b0079-190">99</span><span class="sxs-lookup"><span data-stu-id="b0079-190">99</span></span></p></td>
<td><p><span data-ttu-id="b0079-191">entryID</span><span class="sxs-lookup"><span data-stu-id="b0079-191">entryID</span></span></p></td>
<td><p><span data-ttu-id="b0079-192">0x99000000</span><span class="sxs-lookup"><span data-stu-id="b0079-192">0x99000000</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="b0079-193">Die Zahlen in der Spalte **ID** müssen eindeutig sein und sollten auf keinen Fall wiederverwendet werden.</span><span class="sxs-lookup"><span data-stu-id="b0079-193">The numbers in the **ID** column must be unique and should never be reused.</span></span> <span data-ttu-id="b0079-194">Wenn die ID-Werte unter 256 bleiben, wird hierdurch außerdem Speicherplatz in den vom Adressbuchserver geschriebenen Ausgabedateien eingespart.</span><span class="sxs-lookup"><span data-stu-id="b0079-194">Also, keeping the ID values under 256 saves space in the output files written by the Address Book Server.</span></span> <span data-ttu-id="b0079-195">Der Höchstwert für ID-Werte ist jedoch 65535.</span><span class="sxs-lookup"><span data-stu-id="b0079-195">However, the maximum ID value is 65535.</span></span> <span data-ttu-id="b0079-196">Die Spalte **Name** entspricht dem Active Directory Attributnamen, den der Benutzerreplikationsdienst in der Tabelle AbUserEntry-Tabelle für jeden Kontakt platzieren soll.</span><span class="sxs-lookup"><span data-stu-id="b0079-196">The **Name** column corresponds to the Active Directory attribute name that User Replicator should put in the AbUserEntry table for each contact.</span></span> <span data-ttu-id="b0079-197">Der Wert in der Spalte **Flags** dient zum Definieren des Attributtyps.</span><span class="sxs-lookup"><span data-stu-id="b0079-197">The value in the **Flags** column is used to define the type of attribute.</span></span> <span data-ttu-id="b0079-198">Der Benutzerreplikationsdienst erkennt die folgenden Typen von Adressbuchserverattributen, angegeben durch das niedrige Byte des Werts in der Spalte **Flags**.</span><span class="sxs-lookup"><span data-stu-id="b0079-198">The following types of Address Book Server attributes are recognized by User Replicator, indicated by the low byte of the value in the **Flags** column.</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="b0079-199">Attribut</span><span class="sxs-lookup"><span data-stu-id="b0079-199">Attribute</span></span></th>
<th><span data-ttu-id="b0079-200">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="b0079-200">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b0079-201">0x0</span><span class="sxs-lookup"><span data-stu-id="b0079-201">0x0</span></span></p></td>
<td><p><span data-ttu-id="b0079-p108">Ein Zeichenfolgenattribut. Der Benutzerreplikationsdienst konvertiert diesen Typ in UTF-8, bevor er in der Tabelle "AbUserEntry" gespeichert wird.</span><span class="sxs-lookup"><span data-stu-id="b0079-p108">A string attribute. User Replicator converts this type to UTF-8 before storing it in the AbUserEntry table.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b0079-204">0x1</span><span class="sxs-lookup"><span data-stu-id="b0079-204">0x1</span></span></p></td>
<td><p><span data-ttu-id="b0079-p109">Ein Binärattribut. Der Benutzerreplikationsdienst speichert dieses Attribut ohne Konvertierung im Blob.</span><span class="sxs-lookup"><span data-stu-id="b0079-p109">A binary attribute. User Replicator stores this in the blob without any conversion.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b0079-207">0x2</span><span class="sxs-lookup"><span data-stu-id="b0079-207">0x2</span></span></p></td>
<td><p><span data-ttu-id="b0079-208">Ein Zeichenfolgenattribut, ist jedoch nur enthalten, wenn der Attributwert &quot;mit Tel&quot;: beginnt.</span><span class="sxs-lookup"><span data-stu-id="b0079-208">A string attribute, but is included only if the attribute value begins with &quot;tel:&quot;.</span></span> <span data-ttu-id="b0079-209">Dies wird hauptsächlich für Zeichenfolgenattribute mit mehreren Werten verwendet, vor allem <strong>proxyAddresses</strong>.</span><span class="sxs-lookup"><span data-stu-id="b0079-209">This is primarily for multi-valued string attributes, specifically <strong>proxyAddresses</strong>.</span></span> <span data-ttu-id="b0079-210">In diesem Fall interessiert sich der Adressbuch Server nur für <strong>proxyAddresses</strong> -Einträge, die &quot;mit "&quot;Tel:" beginnen.</span><span class="sxs-lookup"><span data-stu-id="b0079-210">In this case, Address Book Server is interested only in <strong>proxyAddresses</strong> entries that begin with &quot;tel:&quot;.</span></span> <span data-ttu-id="b0079-211">Aus diesem Grund speichert der Benutzerreplikationsdienst im Interesse des Speicherplatzes nur die Einträge, &quot;die mit&quot;Tel: beginnen.</span><span class="sxs-lookup"><span data-stu-id="b0079-211">Therefore, in the interest of saving space, User Replicator stores only the entries that begin with &quot;tel:&quot;.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b0079-212">0x3</span><span class="sxs-lookup"><span data-stu-id="b0079-212">0x3</span></span></p></td>
<td><p><span data-ttu-id="b0079-p111">Ein Attribut mit boolescher Zeichenfolge. Lautet dieses TRUE, nimmt der Benutzerreplikationsdienst diesen Kontakt nicht in die Tabelle "AbUserEntry" auf. Lautet es FALSE, nimmt der Benutzerreplikationsdienst zwar die Attribute für diesen Kontakt in die Tabelle "AbUserEntry" auf, jedoch nicht das bestimmte Attribut mit diesem Kennzeichen. Dies ist ein weiterer Spezialtyp, der hauptsächlich für das Attribut <strong>msExchHideFromAddressLists</strong> gilt.</span><span class="sxs-lookup"><span data-stu-id="b0079-p111">A Boolean string attribute, which if TRUE causes User Replicator to not include this contact in the AbUserEntry table. If FALSE, it causes User Replicator to include the attributes for this contact in the AbUserEntry table, but not the particular attribute with this flag. This is another special case type that is primarily for the <strong>msExchHideFromAddressLists</strong> attribute.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b0079-216">0x4</span><span class="sxs-lookup"><span data-stu-id="b0079-216">0x4</span></span></p></td>
<td><p><span data-ttu-id="b0079-217">Ein Zeichenfolgenattribut, ist jedoch nur enthalten, wenn der Attributwert &quot;mit SMTP&quot; beginnt: und &quot; @ &quot; das Symbol enthält.</span><span class="sxs-lookup"><span data-stu-id="b0079-217">A string attribute, but is included only if the attribute value begins with &quot;smtp:&quot; and includes the &quot;@&quot; symbol.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b0079-218">0x5</span><span class="sxs-lookup"><span data-stu-id="b0079-218">0x5</span></span></p></td>
<td><p><span data-ttu-id="b0079-219">Ein Zeichenfolgenattribut, ist jedoch nur enthalten, wenn der Attributwert mit &quot;Tel:&quot; oder &quot;SMTP:&quot; beginnt und das &quot; @ &quot; Symbol enthält.</span><span class="sxs-lookup"><span data-stu-id="b0079-219">A string attribute, but is included only if the attribute value begins with either &quot;tel:&quot; or &quot;smtp:&quot; and includes the &quot;@&quot; symbol.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b0079-220">0x100</span><span class="sxs-lookup"><span data-stu-id="b0079-220">0x100</span></span></p></td>
<td><p><span data-ttu-id="b0079-221">Wird dieses festgelegt, handelt es sich um ein Attribut mit mehreren Werten, das für jeden Kontakt mehrmals vorhanden sein kann.</span><span class="sxs-lookup"><span data-stu-id="b0079-221">If set, this is a multi-valued attribute that can appear more than once for each contact.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b0079-222">0x400</span><span class="sxs-lookup"><span data-stu-id="b0079-222">0x400</span></span></p></td>
<td><p><span data-ttu-id="b0079-p112">Wird dieses Attribut festgelegt, wird hierdurch für einen Kontakt das Attribut für den Kontonamen des E-Mail-Benutzers angegeben. Der Adressbuchserver stellt anhand dieses Kennzeichens fest, welcher Attributwert im Ereignisprotokolleintrag für die Telefonnormalisierung aufgeführt werden soll.</span><span class="sxs-lookup"><span data-stu-id="b0079-p112">If set, this identifies the email user account name attribute for a contact. Address Book Server uses this flag to identify which attribute value to show in the phone normalization event log entry.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b0079-225">0x800</span><span class="sxs-lookup"><span data-stu-id="b0079-225">0x800</span></span></p></td>
<td><p><span data-ttu-id="b0079-p113">Wird dieses Attribut festgelegt, wird hierdurch ein erforderliches Attribut für einen Kontakt angegeben. Der Adressbuchserver nimmt einen Benutzer nur dann in die Tabelle "AbUserEntry" auf, wenn ein Wert für dieses Attribut in Active Directory vorhanden ist. Gibt es mehrere erforderliche Attribute, muss nur eines davon über einen Wert verfügen, damit der Benutzer in die Tabelle "AbUserEntry" aufgenommen wird.</span><span class="sxs-lookup"><span data-stu-id="b0079-p113">If set, this identifies a required attribute for a contact. Address Book Server includes a user in the AbUserEntry table only if there is a value for this attribute in Active Directory. If there is more than one required attribute, only one of them is required to have a value to include the user in the AbUserEntry table.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b0079-229">0x1000</span><span class="sxs-lookup"><span data-stu-id="b0079-229">0x1000</span></span></p></td>
<td><p><span data-ttu-id="b0079-230">Wird dieses Attribut festgelegt, normalisiert der Adressbuchserver immer den Wert dieses Attributs.</span><span class="sxs-lookup"><span data-stu-id="b0079-230">If set, Address Book Server always normalizes the value of this attribute.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b0079-231">0x2000</span><span class="sxs-lookup"><span data-stu-id="b0079-231">0x2000</span></span></p></td>
<td><p><span data-ttu-id="b0079-232">Wird dieses Attribut festgelegt, verwendet der Adressbuchserver die normalisierte Nummer aus <strong>proxyAddresses</strong>, wenn die CMS-Einstellung <strong>UseNormalizationRules</strong> FALSE lautet; andernfalls verhält er sich so wie bei Einstellung des Kennzeichenbits auf 0x1000.</span><span class="sxs-lookup"><span data-stu-id="b0079-232">If set, Address Book Server uses the normalized number from <strong>proxyAddresses</strong>, if the <strong>UseNormalizationRules</strong> CMS setting is FALSE; otherwise it behaves the same as when the flag bit is 0x1000.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b0079-233">0x4000</span><span class="sxs-lookup"><span data-stu-id="b0079-233">0x4000</span></span></p></td>
<td><p><span data-ttu-id="b0079-p114">Wird dieses Attribut festgelegt, nimmt der Adressbuchserver keine Objekte in die Tabelle "AbUserEntry" auf, die diesen Wert für das angegebene Attribut aufweisen. Wenn dieses Kennzeichenbit beispielsweise für das Attribut <strong>msRTCSIP-PrimaryUserAddress</strong> festgelegt wurde, werden Kontakte mit diesem Attribut nicht in die Datenbank geschrieben.</span><span class="sxs-lookup"><span data-stu-id="b0079-p114">If set, Address Book Server does not include objects in the AbUserEntry table that have this value for the specified attribute. For example, if the <strong>msRTCSIP-PrimaryUserAddress</strong> attribute has this flag bit set, then contacts that have this attribute are not written to the database.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b0079-236">0X8000</span><span class="sxs-lookup"><span data-stu-id="b0079-236">0x8000</span></span></p></td>
<td><p><span data-ttu-id="b0079-p115">Wird dieses Attribut festgelegt, nimmt der Adressbuchserver keine Objekte in die Tabelle "AbUserEntry" auf, die nicht diesen Wert für das angegebene Attribut aufweisen. Wurden beide Kennzeichenbits "0x4000" und "0x8000" für ein Objekt festgelegt, erhält das Attribut mit dem Kennzeichenbit "0x4000" Vorrang, und das Objekt wird aus der Tabelle "AbUserEntry" ausgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="b0079-p115">If set, Address Book Server does not include objects in the AbUserEntry table that do not have this value for the specified attribute. If both the 0x4000 and 0x8000 flag bits are set on an object, the attribute with the flag bit value set to 0x4000 takes precedence, and the object is excluded from the AbUserEntry table.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b0079-239">0x10000</span><span class="sxs-lookup"><span data-stu-id="b0079-239">0x10000</span></span></p></td>
<td><p><span data-ttu-id="b0079-p116">Wird dieses Attribut festgelegt, steht dies für ein Gruppenobjekt. Der Benutzerreplikationsdienst verwendet dieses Kennzeichen zum Aufnehmen von Objekten mit dem Attribut <strong>groupType</strong>, dessen Vorhandensein auf eine Gruppe hinweist (z. B. eine Verteilerliste oder Sicherheitsgruppe).</span><span class="sxs-lookup"><span data-stu-id="b0079-p116">If set, this represents a group object. User Replicator uses this flag bit to include contacts with the <strong>groupType</strong> attribute whose presence indicates a group (for example, a distribution list or security group).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b0079-242">0x20000</span><span class="sxs-lookup"><span data-stu-id="b0079-242">0x20000</span></span></p></td>
<td><p><span data-ttu-id="b0079-243">Wird dieses Attribut festgelegt, verwendet der Benutzerreplikationsdienst dieses Kennzeichenbit zum Aufnehmen dieses Attributs in gerätespezifischen Adressbuchserver-Dateien (also Dateien mit der Erweiterung DABS).</span><span class="sxs-lookup"><span data-stu-id="b0079-243">If set, User Replicator uses this flag bit to include this attribute in device-specific Address Book Server files (that is, files with a .dabs extension).</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="b0079-244">In früheren Versionen von lync Server muss der Administrator beim Anwenden einer Änderung an Active Directory die Cmdlets " **Update-CSUserDatabase** " und " **Update – Windows PowerShell CSAddressBook** " ausführen, um die Änderung an der lync Server Benutzerdatenbank und der RTCab-Datenbank sofort beizubehalten.</span><span class="sxs-lookup"><span data-stu-id="b0079-244">In previous versions of Lync Server, when applying a change to Active Directory, the administrator would be required to run **Update -CSUserDatabase** and **Update –CSAddressBook** Windows PowerShell cmdlets to persist the change to the Lync Server user database and RTCab database immediately.</span></span> <span data-ttu-id="b0079-245">In lync Server 2013 übernimmt lync Server Benutzerreplikationsdienst die Änderungen aus Active Directory und aktualisiert die lync Server Benutzerdatenbank basierend auf einem konfigurierten Intervall.</span><span class="sxs-lookup"><span data-stu-id="b0079-245">In Lync Server 2013, Lync Server User Replicator will pick up the changes from Active Directory and update the Lync Server user database based on a configured interval.</span></span> <span data-ttu-id="b0079-246">Lync Server Benutzerreplikationsdienst wird die Änderungen auch schnell an die RTCab-Datenbank weitergeben, ohne dass der Administrator Update-CSAddressBook ausführen muss.</span><span class="sxs-lookup"><span data-stu-id="b0079-246">Lync Server User Replicator will also propagate the changes to the RTCab database quickly without the administrator having to run Update-CSAddressBook.</span></span> <span data-ttu-id="b0079-247">Wenn die Adressbuch-Webabfrage aktiviert ist, werden die Änderungen in den Suchergebnissen von lync-Clients wiedergegeben.</span><span class="sxs-lookup"><span data-stu-id="b0079-247">If Address Book Web query is enabled, then the changes will be reflected in search results by Lync clients.</span></span> <span data-ttu-id="b0079-248">Administratoren müssen Update-CSAddressBook nur ausführen, wenn der Download der Adressbuchdatei aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="b0079-248">Administrators will only need to run Update -CSAddressBook if the Address Book file download is enabled.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="b0079-249">Standardmäßig wird lync Server Benutzerreplikationsdienst alle 5 Minuten automatisch ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="b0079-249">By default Lync Server User Replicator runs automatically every 5 minutes.</span></span> <span data-ttu-id="b0079-250">Sie können dieses Intervall mithilfe von "Menge-CSUserReplicatorConfiguration-ReplicationCycleInterval &lt; &gt;" konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="b0079-250">You can configure this interval by using Set -CSUserReplicatorConfiguration -ReplicationCycleInterval &lt;&gt;.</span></span>



</div>

</div>

<div>

## <a name="filtering-the-address-book"></a><span data-ttu-id="b0079-251">Filtern des Adressbuchs</span><span class="sxs-lookup"><span data-stu-id="b0079-251">Filtering the Address Book</span></span>

<span data-ttu-id="b0079-252">Die in den Adressbuch Server-Dateien aufgefüllten Benutzer können basierend auf bestimmten Active Directory-Domänendienste Attributen, die in der AbAttribute-Tabelle aufgeführt sind, gesteuert werden.</span><span class="sxs-lookup"><span data-stu-id="b0079-252">The users populated in the Address Book Server files can be controlled based on certain Active Directory Domain Services attributes listed in the AbAttribute table.</span></span> <span data-ttu-id="b0079-253">Das Attribut **msExchangeHideFromAddressBook** ist ein solches Filterattribut.</span><span class="sxs-lookup"><span data-stu-id="b0079-253">One such attribute used for filtering is the **msExchangeHideFromAddressBook** attribute.</span></span> <span data-ttu-id="b0079-254">Hierbei handelt es sich um ein Benutzerattribut, das durch das Exchange-Schema hinzugefügt wird.</span><span class="sxs-lookup"><span data-stu-id="b0079-254">This is a user attribute added by the Exchange schema.</span></span> <span data-ttu-id="b0079-255">Wenn der Wert dieses Attributs TRUE lautet, blendet Exchange Server den Kontakt aus der globalen Outlook-Adressliste (GAL) aus.</span><span class="sxs-lookup"><span data-stu-id="b0079-255">If the value of this attribute is TRUE, Exchange Server uses this attribute to hide the contact from the Outlook Global Address List (GAL).</span></span> <span data-ttu-id="b0079-256">Lautet der Wert dieses Attributs TRUE, nimmt der Benutzerreplikationsdienst außerdem den betreffenden Benutzer nicht in die Tabelle "AbUserEntry" auf, und der Benutzer ist nicht in den Adressbuchserver-Dateien enthalten.</span><span class="sxs-lookup"><span data-stu-id="b0079-256">Similarly, if the value of this attribute is TRUE, User Replicator does not include that user in the AbUserEntry table and this user will not be in the Address Book Server files.</span></span>

<span data-ttu-id="b0079-p120">Mithilfe einiger Kennzeichenbits können Sie einen Filter definieren, der für Adressbuchserver-Attribute verwendet wird. Beispielsweise kann das Attribut anhand bestimmter vorhandener Kennzeichenbits als Include- oder als Exclude-Attribut gekennzeichnet werden. Der Benutzerreplikationsdienst filtert Kontakte heraus, die ein Exclude-Attribut enthalten, sowie Kontakte, die kein Include-Attribut aufweisen.</span><span class="sxs-lookup"><span data-stu-id="b0079-p120">You can use some flag bits to define a filter to use on Address Book Server attributes. For example, the presence of certain flag bits can identify an attribute as an include attribute or an exclude attribute. User Replicator filters out contacts that contain an exclude attribute and filters out contains that do not contain an include attribute.</span></span>

<div>


> [!WARNING]  
> <span data-ttu-id="b0079-260">Weitere Informationen zum Filtern des Adressbuchs finden Sie unter <A href="https://technet.microsoft.com/library/gg415643(v=ocs.15)">Address Book Server-Cmdlets in lync Server 2013</A>und <A href="https://go.microsoft.com/fwlink/?linkid=330430">Filtern lync 2013 Adressbuchs</A> .</span><span class="sxs-lookup"><span data-stu-id="b0079-260">For more information about filtering the Address Book, see <A href="https://technet.microsoft.com/library/gg415643(v=ocs.15)">Address Book Server cmdlets in Lync Server 2013</A>, and <A href="https://go.microsoft.com/fwlink/?linkid=330430">Filter Lync 2013 address book</A></span></span>



</div>

<span data-ttu-id="b0079-p121">Zurzeit gibt es drei verschiedene Filter. Diese Filter werden in der folgenden Tabelle gezeigt.</span><span class="sxs-lookup"><span data-stu-id="b0079-p121">Currently, there are three different filters. The following table lists these filters.</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="b0079-263">Attribut</span><span class="sxs-lookup"><span data-stu-id="b0079-263">Attribute</span></span></th>
<th><span data-ttu-id="b0079-264">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="b0079-264">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b0079-265">0x800</span><span class="sxs-lookup"><span data-stu-id="b0079-265">0x800</span></span></p></td>
<td><p><span data-ttu-id="b0079-p122">Wird dieses Attribut festgelegt, wird hierdurch ein erforderliches Attribut für einen Kontakt angegeben. Der Benutzerreplikationsdienst filtert anhand dieses Kennzeichenbits Kontakte heraus, die nicht mindestens eines der erforderlichen Attribute enthalten. "OuPathId" ist ein erforderliches Attribut, das immer festgelegt ist. Daher sollte mindestens ein weiteres erforderliches Attribut festgelegt sein. Andernfalls wird der Kontakt (also mit dem Wert des erforderlichen Attributs "OuPathId") dennoch nicht in die Datenbank geschrieben. Wenn beispielsweise <strong>telephoneNumber</strong> und <strong>homePhone</strong> als erforderliche Attribute definiert sind, werden nur die Kontakte in die Datenbank geschrieben, die mindestens eines dieser Attribute aufweisen.</span><span class="sxs-lookup"><span data-stu-id="b0079-p122">If set, this identifies a required attribute for a contact. User Replicator uses this flag bit to filter out contacts that do not contain at least one required attribute. The OuPathId is a required attribute, which is always set. So at least one of other required attributes should be set. Otherwise, contact (that is, with value of required attribute OuPathId) will still not be written to database. For example, if <strong>telephoneNumber</strong> and <strong>homePhone</strong> are defined as required attributes, only the contacts that have at least one of these attributes are written to the database.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b0079-272">0x4000</span><span class="sxs-lookup"><span data-stu-id="b0079-272">0x4000</span></span></p></td>
<td><p><span data-ttu-id="b0079-p123">Wird dieses Attribut festgelegt, weist dies auf ein Exclude-Attribut hin. Der Benutzerreplikationsdienst filtert anhand dieses Kennzeichenbits Kontakte heraus, die dieses Attribut enthalten. Wenn beispielsweise <strong>msRTCSIP-PrimaryUserAddress</strong> als Exclude-Attribut festgelegt wurde, werden Kontakte mit diesem Attribut nicht in die Datenbank geschrieben.</span><span class="sxs-lookup"><span data-stu-id="b0079-p123">If set, this identifies an exclude attribute. User Replicator uses this flag bit to filter out contacts that contain this attribute. For example, if <strong>msRTCSIP-PrimaryUserAddress</strong> is defined as an exclude attribute, contacts that have this attribute are not written to the database.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b0079-276">0X8000</span><span class="sxs-lookup"><span data-stu-id="b0079-276">0x8000</span></span></p></td>
<td><p><span data-ttu-id="b0079-p124">Wird dieses Attribut festgelegt, weist dies auf ein Include-Attribut hin. Der Benutzerreplikationsdienst filtert anhand dieses Kennzeichenbits Kontakte heraus, die dieses Attribut nicht enthalten. Wenn beispielsweise <strong>msRTCSIP-PrimaryUserAddress</strong> als Include-Attribut festgelegt wurde, werden nur Kontakte mit diesem Attribut in die Datenbank geschrieben.</span><span class="sxs-lookup"><span data-stu-id="b0079-p124">If set, this identifies an include attribute. User Replicator uses this flag bit to filter out contacts that do not contain this attribute. For example, if <strong>msRTCSIP-PrimaryUserAddress</strong> is defined as an include attribute, only the contacts that have this attribute are written to the database.</span></span></p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> <span data-ttu-id="b0079-280">Wurden sowohl das Kennzeichenbit "0x4000" (Exclude-Attribut) als auch das Kennzeichenbit "0x8000" (Include-Attribut) festgelegt, setzt das Bit "0x4000" das Bit "0x8000" außer Kraft, und der Kontakt wird ausgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="b0079-280">If both the 0x4000 (exclude attribute) and 0x8000 (include attribute) flag bits are set, the 0x4000 bit overrides the 0x8000 bit and the contact is excluded.</span></span>



</div>

<span data-ttu-id="b0079-p125">Auch wenn Sie das Adressbuch so filtern können, dass es nur bestimmte Benutzer enthält, wird durch diese Einschränkung der Einträge nicht die Möglichkeit der Benutzer beschränkt, die gefilterten Benutzer zu kontaktieren oder deren Anwesenheitsstatus anzuzeigen. Benutzer können nicht im Adressbuch enthaltene Benutzer immer finden, manuell Sofortnachrichten senden oder manuell Anrufe an diese Benutzer tätigen, indem sie den vollständigen Anmeldenamen eines Benutzers eingeben. Außerdem können auch Kontaktinformationen für einen Benutzer in Outlook gefunden werden.</span><span class="sxs-lookup"><span data-stu-id="b0079-p125">Although you can filter the Address Book to include only certain users, limiting entries does not limit other users' ability to contact the filtered users or to see their presence status. Users can always find, manually send instant messages, or manually initiate calls to users not in the Address Book by entering a user's complete sign-in name. Also, contact information for a user could also be found in Outlook.</span></span>

<span data-ttu-id="b0079-284">Bei vollständigen Kontaktdatensätzen in den Adressbuchdateien können Sie lync Server verwenden, um e-Mail-, Telefon-oder Enterprise-VoIP-Anrufe zu initiieren (Wenn Enterprise-VoIP auf dem Server aktiviert ist) mit Benutzern, die nicht für die Sitzungs Initiierung konfiguriert sind. Protocol (SIP) möchten einige Organisationen nur SIP-aktivierte Benutzer in Ihre Adressbuch Server Einträge einschließen.</span><span class="sxs-lookup"><span data-stu-id="b0079-284">While having full contact records in the Address Book files enables you to use Lync Server to initiate email, telephone, or Enterprise Voice calls (that is, if Enterprise Voice is enabled on the server) with users that are not configured for Session Initiation Protocol (SIP), some organizations prefer to include only SIP-enabled users in their Address Book Server entries.</span></span> <span data-ttu-id="b0079-285">Sie können das Adressbuch filtern, um nur SIP-aktivierte Benutzer einzuschließen, indem Sie das 0x800-Bit in der Spalte **Flags** der folgenden erforderlichen Attribute deaktivieren: **mailnick Name**, **telephoneNumber**, **homePhone**und **Mobile**.</span><span class="sxs-lookup"><span data-stu-id="b0079-285">You can filter the Address Book to include only SIP-enabled users by clearing the 0x800 bit in the **Flags** column of the following required attributes: **mailNickname**, **telephoneNumber**, **homePhone**, and **mobile**.</span></span> <span data-ttu-id="b0079-286">Sie können das Adressbuch auch filtern, um nur SIP-aktivierte Benutzer einzuschließen, indem Sie das 0X8000 (Include-Attribut) in der Spalte **Flags** des **msRTCSIP-PrimaryUserAddress-** Attributs festlegen.</span><span class="sxs-lookup"><span data-stu-id="b0079-286">You can also filter the Address Book to include only SIP-enabled users by setting the 0x8000 (include attribute) in the **Flags** column of the **msRTCSIP-PrimaryUserAddress** attribute.</span></span> <span data-ttu-id="b0079-287">Dies hilft auch, Dienstkonten aus den Adressbuchdateien auszuschließen.</span><span class="sxs-lookup"><span data-stu-id="b0079-287">This also helps to exclude service accounts from the Address Book files.</span></span>

<span data-ttu-id="b0079-288">Nachdem Sie die Tabelle "AbAttribute" geändert haben, können Sie die Daten in der Tabelle "AbUserEntry" aktualisieren, indem Sie das Cmdlet**Update-CsUserDatabase** ausführen.</span><span class="sxs-lookup"><span data-stu-id="b0079-288">After you modify the AbAttribute table, you can refresh the data in the AbUserEntry table by running the cmdlet **Update-CsUserDatabase** command.</span></span> <span data-ttu-id="b0079-289">Nach Abschluss der Benutzerreplikation können Sie die Datei im Adressbuchserver-Dateispeicher aktualisieren, indem Sie manuell das Cmdlet **UpdateCsAddressBook** ausführen.</span><span class="sxs-lookup"><span data-stu-id="b0079-289">After UR replication completes, you can update the file in the Address Book Server file store by manually running the cmdlet **UpdateCsAddressBook** command.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="b0079-290">Der Front-End-Server, dass der Adressbuch Server gespeichert wird, ist nicht administrativ konfigurierbar.</span><span class="sxs-lookup"><span data-stu-id="b0079-290">The Front End Server that the Address Book Server is placed is not administratively configurable.</span></span> <span data-ttu-id="b0079-291">Eine wird während der Bereitstellung ausgewählt – in der Regel der erste bereitgestellte Front-End-Server.</span><span class="sxs-lookup"><span data-stu-id="b0079-291">One is chosen during deployment—typically, the first Front End Server deployed.</span></span> <span data-ttu-id="b0079-292">Im Falle eines Fehlers wechselt der Adressbuchdienst zu einem anderen Front-End-Server und erfordert keine administrative Aufmerksamkeit.</span><span class="sxs-lookup"><span data-stu-id="b0079-292">In the event of failure, the Address Book Service will move to another Front End Server, and requires no administrative attention.</span></span>



</div>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="b0079-293">Wenn Sie Ihre Infrastruktur von einer Bereitstellung mit mehreren Gesamtstrukturen oder einer übergeordneten/untergeordneten Bereitstellung konsolidiert oder anderweitig geändert haben (beispielsweise die Konsolidierung Ihrer Infrastruktur vor dem Wechsel zu lync Server), können Sie feststellen, dass der Adressbuchdienst herunterladen und die Adressbuch-Webabfrage für einige Benutzer fehlschlägt.</span><span class="sxs-lookup"><span data-stu-id="b0079-293">If you have consolidated or otherwise modified your infrastructure from a multi-forest deployment or a parent/child deployment (such as consolidating your infrastructure before moving to Lync Server), you may find that the Address Book service download and the Address Book Web Query fails for some users.</span></span> <span data-ttu-id="b0079-294">In einer Bereitstellung, die zuvor mehrere Domänen oder Gesamtstrukturen umfasste, ist das Attribut <STRONG>MsRTCSIP-OriginatorSid</STRONG> für die Benutzerobjekte belegt, bei denen das Problem auftritt.</span><span class="sxs-lookup"><span data-stu-id="b0079-294">When in a deployment that had multiple domains or forests, the attribute <STRONG>MsRTCSIP-OriginatorSid</STRONG> is populated on the user objects that are exhibiting the issue.</span></span> <span data-ttu-id="b0079-295">Das Attribut <STRONG>MsRTCSIP-OriginatorSid</STRONG> muss für diese Objekte auf NULL gesetzt werden, um das Problem zu beheben.</span><span class="sxs-lookup"><span data-stu-id="b0079-295">The <STRONG>MsRTCSIP-OriginatorSid</STRONG> attribute must be set to NULL on these objects to resolve the issue.</span></span>



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

