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
ms.openlocfilehash: b72d08d786f41dc606b419f9452970d683b8da37
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/21/2020
ms.locfileid: "42188658"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="administering-the-address-book-service-in-lync-server-2013"></a>Verwalten des Adressbuchdiensts in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2014-02-05_

Im Rahmen der Bereitstellung von lync Server, Enterprise Edition oder Standard Edition-Server wird der Adressbuchdienst standardmäßig installiert. Die vom Adressbuchdienst – RTCab – verwendete Datenbank wird auf dem SQL Server erstellt (für Enterprise Edition ist dies die Back-End-SQL Server; für Standard Edition-Server die verbundene SQL Server).

<div>


> [!NOTE]  
> Informationen zum Bearbeiten von Active Directory-Domänendienste Objektattributen mithilfe von <STRONG>ADSI-Bearbeitung</STRONG> finden Sie unter <A href="https://go.microsoft.com/fwlink/?linkid=330427">ADSI Edit</A>. Informationen zu einem Tool im Resource Kit speziell für den Adressbuchdienst finden Sie unter <A href="https://go.microsoft.com/fwlink/?linkid=330429">Microsoft lync Server 2013 Resource Kit Tools</A>.



</div>

<div>

## <a name="address-book-server-phone-number-normalization"></a>Normalisierung von Telefonnummern auf dem Adressbuchserver

Lync Server erfordert standardisierte RFC 3966/E. 164-Telefonnummern. Um Telefonnummern zu verwenden, die unstrukturiert oder inkonsistent formatiert sind, verwendet lync Server den Adressbuch Server, um Telefonnummern vorverarbeiten, bevor Sie an die Normalisierungsregeln übergeben werden. Wenn eine Telefonnummer aus dem Adressbuch verwendet wird und die Normalisierungsregel angewendet wird, können Clients wie lync Phone Edition und lync Mobile diese normalisierten Nummern verwenden.

Die in früheren Versionen verwendeten Normalisierungsregeln funktionieren möglicherweise nicht ordnungsgemäß, wenn sie nicht angepasst werden. Da die Leerzeichen und die nicht erforderlichen Zeichen vor Einsatz der Normalisierungsregeln entfernt werden, tritt bei Ihrer Normalisierungsregel eventuell ein Fehler auf, falls der reguläre Ausdruck speziell nach einem Bindestrich oder einem anderen Zeichen sucht, das entfernt wurde. Überprüfen Sie Ihre Normalisierungsregeln, und stellen Sie sicher, dass sie nicht nach diesen nicht erforderlichen Zeichen suchen bzw. dass die Regel trotz Fehler fortgesetzt werden kann, wenn das Zeichen sich nicht an der von der Regel erwarteten Stelle befindet.

</div>

<div>

## <a name="user-replicator-and-address-book-server"></a>Benutzerreplikationsdienst und Adressbuchserver

Der Adressbuchserver nutzt die vom Benutzerreplikationsdienst bereitgestellten Informationen zum Aktualisieren der Daten, die er anfangs von der globalen Adressliste (GAL) erhält. Der Benutzerreplikationsdienst schreibt die Active Directory-Domänendienste Attribute für alle Benutzer, Kontakte und Gruppen in die Tabelle AbUserEntry-Tabelle in der Datenbank, und der Adressbuchserver synchronisiert die Benutzerdaten aus der Datenbank in Dateien im Dateispeicher des Adressbuchservers und in die Adressbuchdatenbank RTCab. Das Schema für die Tabelle "AbUserEntry" verwendet zwei Spalten, **UserGuid** und **UserData**. **UserGuid** ist die Indexspalte und enthält die 16-Byte-GUID des Active Directory-Objekts. **UserData** ist eine Bildspalte, die alle zuvor erwähnten Active Directory-Domänendienste Attribute für diesen Kontakt enthält.

Der Benutzerreplikationsdienst legt fest, welche Active Directory Attribute durchlesen einer Konfigurationstabelle, die sich in derselben SQL Server basierten Instanz wie die Tabelle AbUserEntry-Tabelle befindet, geschrieben werden sollen. Die Tabelle "AbAttribute" enthält vier Spalten, **ID**, **Name**, **Flags** und **Enable**. Die Tabelle wird bei der Datenbankeinrichtung erstellt. Ist die Tabelle "AbAttribute" leer, überspringt der Benutzerreplikationsdienst die Logik zur Verarbeitung der Tabelle "AbUserEntry". Die Adressbuchserver-Attribute sind dynamisch und werden aus der Tabelle "AbAttribute" geladen, die anfänglich vom Adressbuchserver bei seiner Aktivierung geschrieben wird.

Die Aktivierung der Adressbuch Server füllt die AbAttribute-Tabelle mit den in der folgenden Tabelle aufgeführten Werten.


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>ID</th>
<th>Name</th>
<th>Flags</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>1</p></td>
<td><p>givenName</p></td>
<td><p>0x01400000</p></td>
</tr>
<tr class="even">
<td><p>2</p></td>
<td><p>SN</p></td>
<td><p>0x02400000</p></td>
</tr>
<tr class="odd">
<td><p>3</p></td>
<td><p>displayName</p></td>
<td><p>0x03420000</p></td>
</tr>
<tr class="even">
<td><p>4</p></td>
<td><p>Titel</p></td>
<td><p>0x04000000</p></td>
</tr>
<tr class="odd">
<td><p>5</p></td>
<td><p>mailNickname</p></td>
<td><p>0x05400000</p></td>
</tr>
<tr class="even">
<td><p>6 </p></td>
<td><p>Company</p></td>
<td><p>0x06000000</p></td>
</tr>
<tr class="odd">
<td><p>7 </p></td>
<td><p>physicalDeliveryOfficeName</p></td>
<td><p>0x07000000</p></td>
</tr>
<tr class="even">
<td><p>8 </p></td>
<td><p>msRTCSIP-PrimaryUserAddress</p></td>
<td><p>0x08520C00</p></td>
</tr>
<tr class="odd">
<td><p>9 </p></td>
<td><p>telephoneNumber</p></td>
<td><p>0x09022800</p></td>
</tr>
<tr class="even">
<td><p>10 </p></td>
<td><p>homePhone</p></td>
<td><p>0x0A302800</p></td>
</tr>
<tr class="odd">
<td><p>11 </p></td>
<td><p>Mobil</p></td>
<td><p>0x0B622800</p></td>
</tr>
<tr class="even">
<td><p>12</p></td>
<td><p>otherTelephone</p></td>
<td><p>0x0C302000</p></td>
</tr>
<tr class="odd">
<td><p>13 </p></td>
<td><p>ipPhone</p></td>
<td><p>0x0D302000</p></td>
</tr>
<tr class="even">
<td><p>14 </p></td>
<td><p>E-Mail</p></td>
<td><p>0x0E500000</p></td>
</tr>
<tr class="odd">
<td><p>15 </p></td>
<td><p>groupType</p></td>
<td><p>0x0F010800</p></td>
</tr>
<tr class="even">
<td><p>16 </p></td>
<td><p>Abteilung</p></td>
<td><p>0x10000000</p></td>
</tr>
<tr class="odd">
<td><p>17 </p></td>
<td><p>Beschreibung</p></td>
<td><p>0x11000100</p></td>
</tr>
<tr class="even">
<td><p>18 </p></td>
<td><p>Manager</p></td>
<td><p>0x12040001</p></td>
</tr>
<tr class="odd">
<td><p>19</p></td>
<td><p>ProxyAddress</p></td>
<td><p>0x00500105</p></td>
</tr>
<tr class="even">
<td><p>20</p></td>
<td><p>msExchHideFromAddressLists</p></td>
<td><p>0xFF000003</p></td>
</tr>
<tr class="odd">
<td><p>99</p></td>
<td><p>entryID</p></td>
<td><p>0x99000000</p></td>
</tr>
</tbody>
</table>


Die Zahlen in der Spalte **ID** müssen eindeutig sein und sollten auf keinen Fall wiederverwendet werden. Wenn die ID-Werte unter 256 bleiben, wird hierdurch außerdem Speicherplatz in den vom Adressbuchserver geschriebenen Ausgabedateien eingespart. Der Höchstwert für ID-Werte ist jedoch 65535. Die Spalte **Name** entspricht dem Active Directory Attributnamen, den der Benutzerreplikationsdienst in der Tabelle AbUserEntry-Tabelle für jeden Kontakt platzieren soll. Der Wert in der Spalte **Flags** dient zum Definieren des Attributtyps. Der Benutzerreplikationsdienst erkennt die folgenden Typen von Adressbuchserverattributen, angegeben durch das niedrige Byte des Werts in der Spalte **Flags**.


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Attribut</th>
<th>Beschreibung</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>0x0</p></td>
<td><p>Ein Zeichenfolgenattribut. Der Benutzerreplikationsdienst konvertiert diesen Typ in UTF-8, bevor er in der Tabelle "AbUserEntry" gespeichert wird.</p></td>
</tr>
<tr class="even">
<td><p>0x1</p></td>
<td><p>Ein Binärattribut. Der Benutzerreplikationsdienst speichert dieses Attribut ohne Konvertierung im Blob.</p></td>
</tr>
<tr class="odd">
<td><p>0x2</p></td>
<td><p>Ein Zeichenfolgenattribut, ist jedoch nur enthalten, wenn der Attributwert &quot;mit Tel&quot;: beginnt. Dies wird hauptsächlich für Zeichenfolgenattribute mit mehreren Werten verwendet, vor allem <strong>proxyAddresses</strong>. In diesem Fall interessiert sich der Adressbuch Server nur für <strong>proxyAddresses</strong> -Einträge, die &quot;mit "&quot;Tel:" beginnen. Aus diesem Grund speichert der Benutzerreplikationsdienst im Interesse des Speicherplatzes nur die Einträge, &quot;die mit&quot;Tel: beginnen.</p></td>
</tr>
<tr class="even">
<td><p>0x3</p></td>
<td><p>Ein Attribut mit boolescher Zeichenfolge. Lautet dieses TRUE, nimmt der Benutzerreplikationsdienst diesen Kontakt nicht in die Tabelle "AbUserEntry" auf. Lautet es FALSE, nimmt der Benutzerreplikationsdienst zwar die Attribute für diesen Kontakt in die Tabelle "AbUserEntry" auf, jedoch nicht das bestimmte Attribut mit diesem Kennzeichen. Dies ist ein weiterer Spezialtyp, der hauptsächlich für das Attribut <strong>msExchHideFromAddressLists</strong> gilt.</p></td>
</tr>
<tr class="odd">
<td><p>0x4</p></td>
<td><p>Ein Zeichenfolgenattribut, ist jedoch nur enthalten, wenn der Attributwert &quot;mit SMTP&quot; beginnt: und &quot; @ &quot; das Symbol enthält.</p></td>
</tr>
<tr class="even">
<td><p>0x5</p></td>
<td><p>Ein Zeichenfolgenattribut, ist jedoch nur enthalten, wenn der Attributwert mit &quot;Tel:&quot; oder &quot;SMTP:&quot; beginnt und das &quot; @ &quot; Symbol enthält.</p></td>
</tr>
<tr class="odd">
<td><p>0x100</p></td>
<td><p>Wird dieses festgelegt, handelt es sich um ein Attribut mit mehreren Werten, das für jeden Kontakt mehrmals vorhanden sein kann.</p></td>
</tr>
<tr class="even">
<td><p>0x400</p></td>
<td><p>Wird dieses Attribut festgelegt, wird hierdurch für einen Kontakt das Attribut für den Kontonamen des E-Mail-Benutzers angegeben. Der Adressbuchserver stellt anhand dieses Kennzeichens fest, welcher Attributwert im Ereignisprotokolleintrag für die Telefonnormalisierung aufgeführt werden soll.</p></td>
</tr>
<tr class="odd">
<td><p>0x800</p></td>
<td><p>Wird dieses Attribut festgelegt, wird hierdurch ein erforderliches Attribut für einen Kontakt angegeben. Der Adressbuchserver nimmt einen Benutzer nur dann in die Tabelle "AbUserEntry" auf, wenn ein Wert für dieses Attribut in Active Directory vorhanden ist. Gibt es mehrere erforderliche Attribute, muss nur eines davon über einen Wert verfügen, damit der Benutzer in die Tabelle "AbUserEntry" aufgenommen wird.</p></td>
</tr>
<tr class="even">
<td><p>0x1000</p></td>
<td><p>Wird dieses Attribut festgelegt, normalisiert der Adressbuchserver immer den Wert dieses Attributs.</p></td>
</tr>
<tr class="odd">
<td><p>0x2000</p></td>
<td><p>Wird dieses Attribut festgelegt, verwendet der Adressbuchserver die normalisierte Nummer aus <strong>proxyAddresses</strong>, wenn die CMS-Einstellung <strong>UseNormalizationRules</strong> FALSE lautet; andernfalls verhält er sich so wie bei Einstellung des Kennzeichenbits auf 0x1000.</p></td>
</tr>
<tr class="even">
<td><p>0x4000</p></td>
<td><p>Wird dieses Attribut festgelegt, nimmt der Adressbuchserver keine Objekte in die Tabelle "AbUserEntry" auf, die diesen Wert für das angegebene Attribut aufweisen. Wenn dieses Kennzeichenbit beispielsweise für das Attribut <strong>msRTCSIP-PrimaryUserAddress</strong> festgelegt wurde, werden Kontakte mit diesem Attribut nicht in die Datenbank geschrieben.</p></td>
</tr>
<tr class="odd">
<td><p>0X8000</p></td>
<td><p>Wird dieses Attribut festgelegt, nimmt der Adressbuchserver keine Objekte in die Tabelle "AbUserEntry" auf, die nicht diesen Wert für das angegebene Attribut aufweisen. Wurden beide Kennzeichenbits "0x4000" und "0x8000" für ein Objekt festgelegt, erhält das Attribut mit dem Kennzeichenbit "0x4000" Vorrang, und das Objekt wird aus der Tabelle "AbUserEntry" ausgeschlossen.</p></td>
</tr>
<tr class="even">
<td><p>0x10000</p></td>
<td><p>Wird dieses Attribut festgelegt, steht dies für ein Gruppenobjekt. Der Benutzerreplikationsdienst verwendet dieses Kennzeichen zum Aufnehmen von Objekten mit dem Attribut <strong>groupType</strong>, dessen Vorhandensein auf eine Gruppe hinweist (z. B. eine Verteilerliste oder Sicherheitsgruppe).</p></td>
</tr>
<tr class="odd">
<td><p>0x20000</p></td>
<td><p>Wird dieses Attribut festgelegt, verwendet der Benutzerreplikationsdienst dieses Kennzeichenbit zum Aufnehmen dieses Attributs in gerätespezifischen Adressbuchserver-Dateien (also Dateien mit der Erweiterung DABS).</p></td>
</tr>
</tbody>
</table>


In früheren Versionen von lync Server muss der Administrator beim Anwenden einer Änderung an Active Directory die Cmdlets " **Update-CSUserDatabase** " und " **Update – Windows PowerShell CSAddressBook** " ausführen, um die Änderung an der lync Server Benutzerdatenbank und der RTCab-Datenbank sofort beizubehalten. In lync Server 2013 übernimmt lync Server Benutzerreplikationsdienst die Änderungen aus Active Directory und aktualisiert die lync Server Benutzerdatenbank basierend auf einem konfigurierten Intervall. Lync Server Benutzerreplikationsdienst wird die Änderungen auch schnell an die RTCab-Datenbank weitergeben, ohne dass der Administrator Update-CSAddressBook ausführen muss. Wenn die Adressbuch-Webabfrage aktiviert ist, werden die Änderungen in den Suchergebnissen von lync-Clients wiedergegeben. Administratoren müssen Update-CSAddressBook nur ausführen, wenn der Download der Adressbuchdatei aktiviert ist.

<div>


> [!NOTE]  
> Standardmäßig wird lync Server Benutzerreplikationsdienst alle 5 Minuten automatisch ausgeführt. Sie können dieses Intervall mithilfe von "Menge-CSUserReplicatorConfiguration-ReplicationCycleInterval &lt; &gt;" konfigurieren.



</div>

</div>

<div>

## <a name="filtering-the-address-book"></a>Filtern des Adressbuchs

Die in den Adressbuch Server-Dateien aufgefüllten Benutzer können basierend auf bestimmten Active Directory-Domänendienste Attributen, die in der AbAttribute-Tabelle aufgeführt sind, gesteuert werden. Das Attribut **msExchangeHideFromAddressBook** ist ein solches Filterattribut. Hierbei handelt es sich um ein Benutzerattribut, das durch das Exchange-Schema hinzugefügt wird. Wenn der Wert dieses Attributs TRUE lautet, blendet Exchange Server den Kontakt aus der globalen Outlook-Adressliste (GAL) aus. Lautet der Wert dieses Attributs TRUE, nimmt der Benutzerreplikationsdienst außerdem den betreffenden Benutzer nicht in die Tabelle "AbUserEntry" auf, und der Benutzer ist nicht in den Adressbuchserver-Dateien enthalten.

Mithilfe einiger Kennzeichenbits können Sie einen Filter definieren, der für Adressbuchserver-Attribute verwendet wird. Beispielsweise kann das Attribut anhand bestimmter vorhandener Kennzeichenbits als Include- oder als Exclude-Attribut gekennzeichnet werden. Der Benutzerreplikationsdienst filtert Kontakte heraus, die ein Exclude-Attribut enthalten, sowie Kontakte, die kein Include-Attribut aufweisen.

<div>


> [!WARNING]  
> Weitere Informationen zum Filtern des Adressbuchs finden Sie unter <A href="https://technet.microsoft.com/library/gg415643(v=ocs.15)">Address Book Server-Cmdlets in lync Server 2013</A>und <A href="https://go.microsoft.com/fwlink/?linkid=330430">Filtern lync 2013 Adressbuchs</A> .



</div>

Zurzeit gibt es drei verschiedene Filter. Diese Filter werden in der folgenden Tabelle gezeigt.


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Attribut</th>
<th>Beschreibung</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>0x800</p></td>
<td><p>Wird dieses Attribut festgelegt, wird hierdurch ein erforderliches Attribut für einen Kontakt angegeben. Der Benutzerreplikationsdienst filtert anhand dieses Kennzeichenbits Kontakte heraus, die nicht mindestens eines der erforderlichen Attribute enthalten. "OuPathId" ist ein erforderliches Attribut, das immer festgelegt ist. Daher sollte mindestens ein weiteres erforderliches Attribut festgelegt sein. Andernfalls wird der Kontakt (also mit dem Wert des erforderlichen Attributs "OuPathId") dennoch nicht in die Datenbank geschrieben. Wenn beispielsweise <strong>telephoneNumber</strong> und <strong>homePhone</strong> als erforderliche Attribute definiert sind, werden nur die Kontakte in die Datenbank geschrieben, die mindestens eines dieser Attribute aufweisen.</p></td>
</tr>
<tr class="even">
<td><p>0x4000</p></td>
<td><p>Wird dieses Attribut festgelegt, weist dies auf ein Exclude-Attribut hin. Der Benutzerreplikationsdienst filtert anhand dieses Kennzeichenbits Kontakte heraus, die dieses Attribut enthalten. Wenn beispielsweise <strong>msRTCSIP-PrimaryUserAddress</strong> als Exclude-Attribut festgelegt wurde, werden Kontakte mit diesem Attribut nicht in die Datenbank geschrieben.</p></td>
</tr>
<tr class="odd">
<td><p>0X8000</p></td>
<td><p>Wird dieses Attribut festgelegt, weist dies auf ein Include-Attribut hin. Der Benutzerreplikationsdienst filtert anhand dieses Kennzeichenbits Kontakte heraus, die dieses Attribut nicht enthalten. Wenn beispielsweise <strong>msRTCSIP-PrimaryUserAddress</strong> als Include-Attribut festgelegt wurde, werden nur Kontakte mit diesem Attribut in die Datenbank geschrieben.</p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> Wurden sowohl das Kennzeichenbit "0x4000" (Exclude-Attribut) als auch das Kennzeichenbit "0x8000" (Include-Attribut) festgelegt, setzt das Bit "0x4000" das Bit "0x8000" außer Kraft, und der Kontakt wird ausgeschlossen.



</div>

Auch wenn Sie das Adressbuch so filtern können, dass es nur bestimmte Benutzer enthält, wird durch diese Einschränkung der Einträge nicht die Möglichkeit der Benutzer beschränkt, die gefilterten Benutzer zu kontaktieren oder deren Anwesenheitsstatus anzuzeigen. Benutzer können nicht im Adressbuch enthaltene Benutzer immer finden, manuell Sofortnachrichten senden oder manuell Anrufe an diese Benutzer tätigen, indem sie den vollständigen Anmeldenamen eines Benutzers eingeben. Außerdem können auch Kontaktinformationen für einen Benutzer in Outlook gefunden werden.

Bei vollständigen Kontaktdatensätzen in den Adressbuchdateien können Sie lync Server verwenden, um e-Mail-, Telefon-oder Enterprise-VoIP-Anrufe zu initiieren (Wenn Enterprise-VoIP auf dem Server aktiviert ist) mit Benutzern, die nicht für die Sitzungs Initiierung konfiguriert sind. Protocol (SIP) möchten einige Organisationen nur SIP-aktivierte Benutzer in Ihre Adressbuch Server Einträge einschließen. Sie können das Adressbuch filtern, um nur SIP-aktivierte Benutzer einzuschließen, indem Sie das 0x800-Bit in der Spalte **Flags** der folgenden erforderlichen Attribute deaktivieren: **mailnick Name**, **telephoneNumber**, **homePhone**und **Mobile**. Sie können das Adressbuch auch filtern, um nur SIP-aktivierte Benutzer einzuschließen, indem Sie das 0X8000 (Include-Attribut) in der Spalte **Flags** des **msRTCSIP-PrimaryUserAddress-** Attributs festlegen. Dies hilft auch, Dienstkonten aus den Adressbuchdateien auszuschließen.

Nachdem Sie die Tabelle "AbAttribute" geändert haben, können Sie die Daten in der Tabelle "AbUserEntry" aktualisieren, indem Sie das Cmdlet**Update-CsUserDatabase** ausführen. Nach Abschluss der Benutzerreplikation können Sie die Datei im Adressbuchserver-Dateispeicher aktualisieren, indem Sie manuell das Cmdlet **UpdateCsAddressBook** ausführen.

<div>


> [!NOTE]  
> Der Front-End-Server, dass der Adressbuch Server gespeichert wird, ist nicht administrativ konfigurierbar. Eine wird während der Bereitstellung ausgewählt – in der Regel der erste bereitgestellte Front-End-Server. Im Falle eines Fehlers wechselt der Adressbuchdienst zu einem anderen Front-End-Server und erfordert keine administrative Aufmerksamkeit.



</div>

<div>


> [!IMPORTANT]  
> Wenn Sie Ihre Infrastruktur von einer Bereitstellung mit mehreren Gesamtstrukturen oder einer übergeordneten/untergeordneten Bereitstellung konsolidiert oder anderweitig geändert haben (beispielsweise die Konsolidierung Ihrer Infrastruktur vor dem Wechsel zu lync Server), können Sie feststellen, dass der Adressbuchdienst herunterladen und die Adressbuch-Webabfrage für einige Benutzer fehlschlägt. In einer Bereitstellung, die zuvor mehrere Domänen oder Gesamtstrukturen umfasste, ist das Attribut <STRONG>MsRTCSIP-OriginatorSid</STRONG> für die Benutzerobjekte belegt, bei denen das Problem auftritt. Das Attribut <STRONG>MsRTCSIP-OriginatorSid</STRONG> muss für diese Objekte auf NULL gesetzt werden, um das Problem zu beheben.



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

