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

# <a name="administering-the-address-book-service-in-lync-server-2013"></a>Verwalten des Adressbuchdiensts in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2014-02-05_

Als Teil der Bereitstellung von lync Server, Enterprise Edition oder Standard Edition-Server wird der Adressbuchdienst standardmäßig installiert. Die vom Adressbuchdienst – RTCab – verwendete Datenbank wird auf dem SQL Server erstellt (für Enterprise Edition, dies ist der Back-End-SQL-Server; für den Standard Edition-Server, den zusammengefassten SQL Server).

<div>


> [!NOTE]  
> Informationen zur Verwendung der <STRONG>ADSI-Bearbeitung</STRONG> zum Bearbeiten von Active Directory-Objektattributen finden Sie unter <A href="http://go.microsoft.com/fwlink/?linkid=330427">ADSI-Bearbeitung</A>. Informationen zu einem Tool im Resource Kit speziell für den Adressbuchdienst finden Sie unter <A href="http://go.microsoft.com/fwlink/?linkid=330429">Microsoft lync Server 2013 Resource Kit-Tools</A>.



</div>

<div>

## <a name="address-book-server-phone-number-normalization"></a>Telefonnummernnormalisierung des Adressbuchservers

Lync Server erfordert standardisierte RFC 3966/E. 164-Telefonnummern. Um Telefonnummern zu verwenden, die nicht strukturiert oder inkonsistent formatiert sind, verwendet lync Server den Adressbuchserver, um Telefonnummern vorverarbeiten, bevor Sie an die Normalisierungsregeln übergeben werden. Wenn eine Telefonnummer aus dem Adressbuch verwendet wird und die Normalisierungsregel angewendet wird, können Clients wie lync Phone Edition und lync Mobile diese normalisierten Nummern verwenden.

Die Normalisierungsregeln, die in früheren Versionen verwendet wurden, funktionieren möglicherweise ohne Anpassungen nicht ordnungsgemäß. Da die Leerzeichen und nicht obligatorischen Zeichen vor den Normalisierungsregeln entfernt werden, wenn Ihr Regex-Ausdruck speziell nach einem Strich oder einem anderen Zeichen sucht, das entfernt wurde, schlägt die Normalisierungsregel möglicherweise fehl. Überprüfen Sie Ihre Normalisierungsregeln, um sicherzustellen, dass Sie nicht nach diesen nicht obligatorischen Zeichen suchen, oder dass die Regel ordnungsgemäß fehlschlägt und fortgesetzt werden kann, wenn das Zeichen nicht vorhanden ist, wenn es von der Regel erwartet wird.

</div>

<div>

## <a name="user-replicator-and-address-book-server"></a>Benutzer-Replikator und Adressbuch Server

Der Adressbuch Server verwendet die vom Benutzerreplikationsdienst zur Verfügung gestellten Daten, um die Informationen zu aktualisieren, die er ursprünglich aus der globalen Adressliste (Global Address List, GAL) erhält. Der Benutzerreplikationsdienst schreibt die Attribute der Active Directory-Domänendienste für jeden Benutzer, Kontakt und jede Gruppe in die Tabelle AbUserEntry-Tabelle in der Datenbank, und der Adressbuchserver synchronisiert die Benutzerdaten aus der Datenbank in Dateien im Dateispeicher des Adressbuchservers und in die Adressbuchdatenbank RTCab. Das Schema für die Tabelle AbUserEntry-Tabelle verwendet zwei Spalten, **UserGuid** und **UserData**. **UserGuid** ist die Indexspalte und enthält die 16-Byte-GUID des Active Directory-Objekts. **UserData** ist eine Bildspalte, die alle zuvor erwähnten Attribute für Active Directory-Domänendienste für diesen Kontakt enthält.

Der Benutzerreplikationsdienst bestimmt, welche Active Directory-Attribute geschrieben werden sollen, indem Sie eine Konfigurationstabelle lesen, die sich in derselben SQL Server-basierten Instanz wie die Tabelle AbUserEntry-Tabelle befindet. Die AbAttribute-Tabelle enthält drei Spalten, **ID**, **Name**, **Flags**und **enable**. Die Tabelle wird beim Einrichten der Datenbank erstellt. Wenn die AbAttribute-Tabelle leer ist, überspringt der Benutzerreplikationsdienst die Tabelle AbUserEntry-Tabellen Verarbeitungslogik. Adressbuchserver Attribute sind dynamisch und werden aus der AbAttribute-Tabelle abgerufen, die zunächst vom Adressbuchserver geschrieben wird, wenn der Adressbuchserver aktiviert wird.

Bei der Aktivierung des Adressbuchservers wird die AbAttribute-Tabelle mit den in der folgenden Tabelle dargestellten Werten gefüllt.


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
<th>Kennzeichnungen</th>
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
<td><p>DisplayName</p></td>
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
<td><p>6</p></td>
<td><p>Unternehmen</p></td>
<td><p>0x06000000</p></td>
</tr>
<tr class="odd">
<td><p>7</p></td>
<td><p>physicalDeliveryOfficeName</p></td>
<td><p>0x07000000</p></td>
</tr>
<tr class="even">
<td><p>8</p></td>
<td><p>msRTCSIP-PrimaryUserAddress</p></td>
<td><p>0x08520C00</p></td>
</tr>
<tr class="odd">
<td><p>9</p></td>
<td><p>telephoneNumber</p></td>
<td><p>0x09022800</p></td>
</tr>
<tr class="even">
<td><p>10</p></td>
<td><p>homePhone</p></td>
<td><p>0x0A302800</p></td>
</tr>
<tr class="odd">
<td><p>11</p></td>
<td><p>Mobil</p></td>
<td><p>0x0B622800</p></td>
</tr>
<tr class="even">
<td><p>12</p></td>
<td><p>otherTelephone</p></td>
<td><p>0x0C302000</p></td>
</tr>
<tr class="odd">
<td><p>13</p></td>
<td><p>ipPhone</p></td>
<td><p>0x0D302000</p></td>
</tr>
<tr class="even">
<td><p>14</p></td>
<td><p>Mail</p></td>
<td><p>0x0E500000</p></td>
</tr>
<tr class="odd">
<td><p>15</p></td>
<td><p>GroupType</p></td>
<td><p>0x0F010800</p></td>
</tr>
<tr class="even">
<td><p>16</p></td>
<td><p>Abteilung</p></td>
<td><p>0x10000000</p></td>
</tr>
<tr class="odd">
<td><p>17</p></td>
<td><p>Beschreibung</p></td>
<td><p>0x11000100</p></td>
</tr>
<tr class="even">
<td><p>18</p></td>
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


Die Zahlen in der Spalte " **ID** " müssen eindeutig sein und nie wieder verwendet werden. Außerdem wird durch das aufrecht erhalten der ID-Werte unter 256 Platz in den vom Adressbuch Server geschriebenen Ausgabedateien gespart. Der maximale ID-Wert ist jedoch 65535. Die Spalte **Name** entspricht dem Active Directory-Attributnamen, den der Benutzerreplikationsdienst in die Tabelle AbUserEntry-Tabelle für jeden Kontakt aufnehmen soll. Der Wert in der Spalte **Flags** wird verwendet, um den Typ des Attributs zu definieren. Die folgenden Typen von Adressbuch Server Attributen werden vom Benutzerreplikationsdienst erkannt, der durch das niedrige Byte des Werts in der Spalte **Flags** angegeben wird.


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
<td><p>Ein Zeichenfolgenattribut. Der Benutzerreplikationsdienst wandelt diesen Typ in UTF-8 um, bevor er ihn in der Tabelle AbUserEntry-Tabelle speichert.</p></td>
</tr>
<tr class="even">
<td><p>0x1</p></td>
<td><p>Ein binäres Attribut. Der Benutzerreplikationsdienst speichert diese ohne Konvertierung im BLOB.</p></td>
</tr>
<tr class="odd">
<td><p>0x2</p></td>
<td><p>Ein Zeichenfolgenattribut, wird aber nur berücksichtigt, wenn der Attributwert &quot;mit Tel&quot;: beginnt. Dies gilt in erster Linie für mehrwertige Zeichenfolgenattribute, insbesondere für <strong>proxyAddresses</strong>. In diesem Fall ist der Adressbuch Server nur an <strong>proxyAddresses</strong> -Einträgen interessiert, &quot;die mit&quot;Tel: beginnen. Aus diesem Grund speichert der Benutzerreplikationsdienst im Interesse des Speicherplatzes nur die Einträge, &quot;die mit&quot;Tel: beginnen.</p></td>
</tr>
<tr class="even">
<td><p>0x3</p></td>
<td><p>Ein boolesches Zeichenfolgenattribut, das bei true bewirkt, dass der Benutzer Replicator diesen Kontakt nicht in die Tabelle AbUserEntry-Tabelle einfügt. Ist der Wert false, wird der Benutzerreplikationsdienst dazu veranlasst, die Attribute für diesen Kontakt in die Tabelle AbUserEntry-Tabelle einzubeziehen, jedoch nicht das jeweilige Attribut mit diesem Flag. Dies ist ein weiterer spezieller Case-Typ, der in erster Linie für das <strong>msExchHideFromAddressLists</strong> -Attribut steht.</p></td>
</tr>
<tr class="odd">
<td><p>0x4</p></td>
<td><p>Ein Zeichenfolgenattribut, wird aber nur berücksichtigt, wenn der Attributwert &quot;mit SMTP&quot; beginnt: und &quot; @ &quot; das Symbol enthält.</p></td>
</tr>
<tr class="even">
<td><p>0x5</p></td>
<td><p>Ein Zeichenfolgenattribut, wird aber nur berücksichtigt, wenn der Attributwert entweder &quot;mit "&quot; Tel &quot;:"&quot; oder "SMTP &quot; @ &quot; :" beginnt und das Symbol enthält.</p></td>
</tr>
<tr class="odd">
<td><p>0x100</p></td>
<td><p>Wenn festzulegen, handelt es sich um ein mehrwertiges Attribut, das für jeden Kontakt mehrmals angezeigt werden kann.</p></td>
</tr>
<tr class="even">
<td><p>0x400</p></td>
<td><p>Wenn diese Einstellung festgesetzt ist, wird das Attribut "e-Mail-Benutzerkontoname" für einen Kontakt angegeben. Der Adressbuch Server verwendet dieses Flag, um zu ermitteln, welcher Attributwert im Ereignisprotokolleintrag für die Telefon Normalisierung angezeigt werden soll.</p></td>
</tr>
<tr class="odd">
<td><p>0x800</p></td>
<td><p>Wenn festzulegen, wird ein erforderliches Attribut für einen Kontakt angegeben. Der Adressbuch Server enthält nur dann einen Benutzer in der Tabelle AbUserEntry-Tabelle, wenn ein Wert für dieses Attribut in Active Directory vorhanden ist. Wenn mehr als ein erforderliches Attribut vorhanden ist, muss nur einer von Ihnen über einen Wert verfügen, um den Benutzer in die Tabelle AbUserEntry-Tabelle einzubeziehen.</p></td>
</tr>
<tr class="even">
<td><p>0x1000</p></td>
<td><p>Wenn der Wert für Address Book Server gesetzt ist, wird der Wert dieses Attributs immer normalisiert.</p></td>
</tr>
<tr class="odd">
<td><p>0x2000</p></td>
<td><p>Ist der Wert festgelegt, verwendet der Adressbuch Server die normalisierte Zahl von <strong>proxyAddresses</strong>, wenn die <strong>UseNormalizationRules</strong> -CMS-Einstellung falsch ist. Andernfalls verhält es sich wie beim Flag-Bit 0x1000.</p></td>
</tr>
<tr class="even">
<td><p>0x4000</p></td>
<td><p>Wenn festgelegt, enthält der Adressbuch Server keine Objekte in der Tabelle AbUserEntry-Tabelle, die diesen Wert für das angegebene Attribut aufweisen. Wenn beispielsweise für das <strong>Attribut msRTCSIP-PrimaryUserAddress-</strong> Attribut dieses Flag-Bit festgesetzt ist, werden Kontakte mit diesem Attribut nicht in die Datenbank geschrieben.</p></td>
</tr>
<tr class="odd">
<td><p>0X8000</p></td>
<td><p>Wenn festgelegt, enthält der Adressbuch Server keine Objekte in der Tabelle AbUserEntry-Tabelle, die diesen Wert für das angegebene Attribut nicht aufweisen. Wenn sowohl die 0x4000-als auch die 0X8000-Flag-Bits für ein Objekt gesetzt sind, hat das Attribut mit dem Flag-Bit-Wert, der auf 0x4000 gesetzt ist, Vorrang, und das Objekt wird aus der Tabelle AbUserEntry-Tabelle ausgeschlossen.</p></td>
</tr>
<tr class="even">
<td><p>0x10000</p></td>
<td><p>Wenn diese Einstellung eingestellt ist, stellt dies ein Group-Objekt dar. Der Benutzerreplikationsdienst verwendet dieses Flag-Bit, um <strong></strong> Kontakte mit dem GroupType-Attribut einzubeziehen, deren Anwesenheitsstatus auf eine Gruppe (beispielsweise eine Verteilerliste oder eine Sicherheitsgruppe) hinweist.</p></td>
</tr>
<tr class="odd">
<td><p>0x20000</p></td>
<td><p>Ist dieser Wert festzulegen, verwendet der Benutzerreplikationsdienst dieses Flag-Bit, um dieses Attribut in gerätespezifische Adressbuch Server Dateien (also Dateien mit der Erweiterung ". kleckse") einzubeziehen.</p></td>
</tr>
</tbody>
</table>


In früheren Versionen von lync Server musste der Administrator beim Anwenden einer Änderung an Active Directory CSUserDatabase und **Update – CSAddressBook** Windows PowerShell-Cmdlets ausführen, um die Änderung auf dem lync **-** Server beizubehalten. Benutzerdatenbank und RTCab-Datenbank sofort. In lync Server 2013 wird der lync Server-Benutzerreplikationsdienst die Änderungen aus Active Directory aufnehmen und die lync Server-Benutzerdatenbank basierend auf einem konfigurierten Intervall aktualisieren. Der lync Server-Benutzerreplikationsdienst gibt die Änderungen auch schnell an die RTCab-Datenbank weiter, ohne dass der Administrator Update-CSAddressBook ausführen muss. Wenn die Adressbuch-Webabfrage aktiviert ist, werden die Änderungen in den Suchergebnissen von lync-Clients wiedergegeben. Administratoren müssen nur Update-CSAddressBook ausführen, wenn der Download der Adressbuchdatei aktiviert ist.

<div>


> [!NOTE]  
> Standardmäßig wird der lync Server-Benutzerreplikationsdienst automatisch alle 5 Minuten ausgeführt. Sie können dieses Intervall mithilfe von "Satz-CSUserReplicatorConfiguration-ReplicationCycleInterval &lt; &gt;" konfigurieren.



</div>

</div>

<div>

## <a name="filtering-the-address-book"></a>Filtern des Adressbuchs

Die in den Adressbuch Server Dateien aufgefüllten Benutzer können basierend auf bestimmten Active Directory-Domänendienst Attributen, die in der AbAttribute-Tabelle aufgelistet sind, gesteuert werden. Ein solches Attribut, das für die Filterung verwendet wird, ist das **msExchangeHideFromAddressBook** -Attribut. Hierbei handelt es sich um ein vom Exchange-Schema hinzugefügtes Benutzerattribut. Wenn der Wert dieses Attributs wahr ist, verwendet Exchange Server dieses Attribut zum Ausblenden des Kontakts aus der globalen Outlook-Adressliste (GAL). Wenn der Wert dieses Attributs auf "true" festgelegt ist, enthält der Benutzerreplikationsdienst diesen Benutzer in der Tabelle AbUserEntry-Tabelle nicht, und dieser Benutzer befindet sich nicht in den Adressbuch Server Dateien.

Sie können einige Flag-Bits verwenden, um einen Filter für die Verwendung in Adressbuch Server Attributen zu definieren. So kann beispielsweise das vorhanden sein bestimmter kennzeichenbits ein Attribut als Include-Attribut oder Exclude-Attribut identifizieren. Der Benutzerreplikationsdienst filtert Kontakte aus, die ein Exclude-Attribut enthalten, und filtert Contains, die kein Include-Attribut enthalten.

<div>


> [!WARNING]  
> Weitere Informationen zum Filtern des Adressbuchs finden Sie unter <A href="https://technet.microsoft.com/en-us/library/gg415643(v=ocs.15)">Adressbuch Server-Cmdlets in lync Server 2013</A>und <A href="http://go.microsoft.com/fwlink/?linkid=330430">Filtern des lync 2013-Adressbuchs</A> .



</div>

Derzeit gibt es drei verschiedene Filter. In der folgenden Tabelle sind diese Filter aufgelistet.


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
<td><p>Wenn festzulegen, wird ein erforderliches Attribut für einen Kontakt angegeben. Der Benutzerreplikationsdienst verwendet dieses Flag-Bit, um Kontakte zu filtern, die nicht mindestens ein erforderliches Attribut enthalten. OuPathId ist ein erforderliches Attribut, das immer gesetzt ist. Daher sollte mindestens eines der anderen erforderlichen Attribute festzulegen sein. Andernfalls wird der Kontakt (mit dem Wert des required-Attributs OuPathId) immer noch nicht in die Datenbank geschrieben. Wenn beispielsweise <strong>telephoneNumber</strong> und <strong>homePhone</strong> als erforderliche Attribute definiert sind, werden nur die Kontakte, die mindestens eines dieser Attribute aufweisen, in die Datenbank geschrieben.</p></td>
</tr>
<tr class="even">
<td><p>0x4000</p></td>
<td><p>Wenn festzulegen, wird ein Exclude-Attribut identifiziert. Der Benutzerreplikationsdienst verwendet dieses Flag-Bit, um Kontakte zu filtern, die dieses Attribut enthalten. Wenn beispielsweise <strong>Attribut msRTCSIP-PrimaryUserAddress</strong> als Exclude-Attribut definiert ist, werden Kontakte mit diesem Attribut nicht in die Datenbank geschrieben.</p></td>
</tr>
<tr class="odd">
<td><p>0X8000</p></td>
<td><p>Wenn festzulegen, wird ein Include-Attribut angegeben. Der Benutzerreplikationsdienst verwendet dieses Flag-Bit, um Kontakte zu filtern, die dieses Attribut nicht enthalten. Wenn beispielsweise <strong>Attribut msRTCSIP-PrimaryUserAddress</strong> als Include-Attribut definiert ist, werden nur die Kontakte, die dieses Attribut aufweisen, in die Datenbank geschrieben.</p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> Wenn sowohl das 0x4000 (Exclude-Attribut) als auch das 0X8000 (Include-Attribut)-Flag-Bits gesetzt sind, überschreibt das 0x4000-Bit das 0X8000-Bit, und der Kontakt wird ausgeschlossen.



</div>

Zwar können Sie das Adressbuch so filtern, dass nur bestimmte Benutzer eingeschlossen werden, aber das Einschränken von Einträgen schränkt nicht die Möglichkeit anderer Benutzer ein, die gefilterten Benutzer zu kontaktieren oder Ihren Anwesenheitsstatus anzuzeigen. Benutzer können jederzeit Sofortnachrichten suchen, manuell senden oder Anrufe an Benutzer, die sich nicht im Adressbuch befinden, manuell initiieren, indem Sie den vollständigen Anmeldenamen eines Benutzers eingeben. Auch Kontaktinformationen für einen Benutzer finden Sie in Outlook.

Wenn Sie über vollständige Kontaktdatensätze in den Adressbuchdateien verfügen, können Sie mithilfe von lync Server e-Mail-, Telefon-oder Enterprise-Sprachanrufe initiieren (das heißt, wenn Enterprise-VoIP auf dem Server aktiviert ist), mit Benutzern, die nicht für die Sitzungs Initiierung konfiguriert sind. Protocol (SIP) verwenden, ziehen einige Organisationen es vor, nur SIP-fähige Benutzer in Ihre Adressbuch Server Einträge einzubeziehen. Sie können das Adressbuch so filtern, dass nur SIP-fähige Benutzer eingeschlossen werden, indem Sie das 0x800-Bit in der Spalte **Flags** der folgenden erforderlichen Attribute löschen: mailNickname, **telephoneNumber**, **homePhone**und **Handy**. **** Sie können das Adressbuch auch filtern, um nur SIP-fähige Benutzer einzubeziehen, indem Sie das 0X8000 (Include-Attribut) in der Spalte **Flags** des **Attribut msRTCSIP-PrimaryUserAddress-** Attributs festlegen. Dadurch können auch Dienstkonten aus den Adressbuchdateien ausgeschlossen werden.

Nachdem Sie die AbAttribute-Tabelle geändert haben, können Sie die Daten in der Tabelle AbUserEntry-Tabelle aktualisieren, indem Sie den Befehl Cmdlet **Update-CsUserDatabase** ausführen. Nach Abschluss der ur-Replikation können Sie die Datei im Dateispeicher des Adressbuchservers aktualisieren, indem Sie den Befehl Cmdlet **UpdateCsAddressBook** manuell ausführen.

<div>


> [!NOTE]  
> Der Front-End-Server, auf dem der Adressbuchserver gespeichert ist, kann nicht administrativ konfiguriert werden. Eine wird während der Bereitstellung ausgewählt – in der Regel der erste bereitgestellte Front-End-Server. Bei einem Fehler wechselt der Adressbuchdienst zu einem anderen Front-End-Server und erfordert keine administrative Beachtung.



</div>

<div>


> [!IMPORTANT]  
> Wenn Sie Ihre Infrastruktur von einer Bereitstellung mit mehreren Gesamtstrukturen oder von einer übergeordneten/untergeordneten Bereitstellung konsolidiert oder anderweitig geändert haben (wie etwa das Konsolidieren Ihrer Infrastruktur, bevor Sie zu lync Server wechseln), stellen Sie möglicherweise fest, dass der Adressbuchdienst heruntergeladen wird, und die Die Adressbuch-Webabfrage schlägt für einige Benutzer fehl. Bei einer Bereitstellung mit mehreren Domänen oder Gesamtstrukturen wird das Attribut <STRONG>Attribut msRTCSIP-OriginatorSid</STRONG> für die Benutzerobjekte aufgefüllt, die das Problem aufweisen. Das <STRONG>Attribut msRTCSIP-OriginatorSid-</STRONG> Attribut muss für diese Objekte auf Null festgesetzt werden, um das Problem zu beheben.



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

