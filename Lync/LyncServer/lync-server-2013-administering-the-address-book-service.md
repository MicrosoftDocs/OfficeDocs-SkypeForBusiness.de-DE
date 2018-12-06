---
title: Verwalten des Adressbuchdiensts in Lync Server 2013
TOCTitle: Verwalten des Adressbuchdiensts in Lync Server 2013
ms:assetid: 801e4243-9670-4477-aa2f-88b61ecf5351
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg429711(v=OCS.15)
ms:contentKeyID: 49294559
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Verwalten des Adressbuchdiensts in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2016-12-08_

Im Rahmen der Bereitstellung von Lync Server, Enterprise Edition oder des Standard Edition-Servers wird der Adressbuchdienst standardmäßig installiert. Die vom Adressbuchdienst genutzte Datenbank "RTCab" wird auf dem SQL Server erstellt. (Für die Enterprise Edition ist dies der Back-End-SQL Server, für den Standard Edition-Server der verbundene SQL Server.)


> [!NOTE]
> Informationen zur Verwendung von <STRONG>ADSI-Editor</STRONG> zum Bearbeiten von Active Directory-Domänendienste-Objektattributen finden Sie unter <A href="http://go.microsoft.com/fwlink/?linkid=330427">ADSI-Editor</A>. Informationen zu einem Tool für den Adressbuchdienst im Resource Kit finden Sie unter <A href="http://go.microsoft.com/fwlink/?linkid=330429">Resource-Kit-Tools in Microsoft Lync Server&nbsp;2013</A>.



## Normalisierung von Telefonnummern auf dem Adressbuchserver

Für Lync Server sind Telefonnummern nach dem RFC 3966/E.164-Standard erforderlich. Bei unstrukturierten oder inkonsistent formatierten Telefonnummern lässt Lync Server die Telefonnummern auf dem Adressbuchserver vorbereiten, bevor sie an die Normalisierungsregeln weitergeleitet werden. Wird eine Telefonnummer aus dem Adressbuch verwendet und die Normalisierungsregel angewendet, können Clients wie Lync Phone Edition und Lync Mobile diese normalisierten Nummern verwenden.

Die in früheren Versionen verwendeten Normalisierungsregeln funktionieren möglicherweise nicht ordnungsgemäß, wenn sie nicht angepasst werden. Da die Leerzeichen und die nicht erforderlichen Zeichen vor Einsatz der Normalisierungsregeln entfernt werden, tritt bei Ihrer Normalisierungsregel eventuell ein Fehler auf, falls der reguläre Ausdruck speziell nach einem Bindestrich oder einem anderen Zeichen sucht, das entfernt wurde. Überprüfen Sie Ihre Normalisierungsregeln, und stellen Sie sicher, dass sie nicht nach diesen nicht erforderlichen Zeichen suchen bzw. dass die Regel trotz Fehler fortgesetzt werden kann, wenn das Zeichen sich nicht an der von der Regel erwarteten Stelle befindet.

## Benutzerreplikationsdienst und Adressbuchserver

Der Adressbuchserver nutzt die vom Benutzerreplikationsdienst bereitgestellten Informationen zum Aktualisieren der Daten, die er anfangs von der globalen Adressliste (GAL) erhält. Der Benutzerreplikationsdienst schreibt die Attribute der Active Directory-Domänendienste für jeden Benutzer, jeden Kontakt und jede Gruppe in die Tabelle "AbUserEntry" in der Datenbank, und der Adressbuchserver synchronisiert die Benutzerdaten aus der Datenbank in die Dateien im Dateispeicher des Adressbuchservers und in die Adressbuchdatenbank "RTCab". Das Schema für die Tabelle "AbUserEntry" verwendet zwei Spalten, **UserGuid** und **UserData**. **UserGuid** ist die Indexspalte und enthält die 16-Byte-GUID des Active Directory-Objekts. **UserData** ist eine Spalte mit allen zuvor genannten Attributen der Active Directory-Domänendienste für diesen Kontakt.

Der Benutzerreplikationsdienst bestimmt, welche Active Directory-Attribute geschrieben werden, indem er eine Konfigurationstabelle liest, die sich in derselben SQL Server-basierten Instanz befindet, wie die Tabelle "AbUserEntry". Die Tabelle "AbAttribute" enthält vier Spalten, **ID**, **Name**, **Flags** und **Enable**. Die Tabelle wird bei der Datenbankeinrichtung erstellt. Ist die Tabelle "AbAttribute" leer, überspringt der Benutzerreplikationsdienst die Logik zur Verarbeitung der Tabelle "AbUserEntry". Die Adressbuchserver-Attribute sind dynamisch und werden aus der Tabelle "AbAttribute" geladen, die anfänglich vom Adressbuchserver bei seiner Aktivierung geschrieben wird.

Durch die Aktivierung des Adressbuchservers wird die Tabelle "AbAttribute" mit Werten gefüllt, die in der folgenden Tabelle aufgeführt sind.


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
<td><p>Sn</p></td>
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
<td><p>groupType</p></td>
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
<td><p>proxyAddress</p></td>
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


Die Zahlen in der Spalte **ID** müssen eindeutig sein und sollten auf keinen Fall wiederverwendet werden. Wenn die ID-Werte unter 256 bleiben, wird hierdurch außerdem Speicherplatz in den vom Adressbuchserver geschriebenen Ausgabedateien eingespart. Der Höchstwert für ID-Werte ist jedoch 65535. Die Spalte **Name** entspricht dem Active Directory-Attributnamen, den der Benutzerreplikationsdienst für jeden Kontakt in der Tabelle "AbUserEntry" ablegen soll. Der Wert in der Spalte **Flags** dient zum Definieren des Attributtyps. Der Benutzerreplikationsdienst erkennt die folgenden Typen von Adressbuchserverattributen, angegeben durch das niedrige Byte des Werts in der Spalte **Flags**.


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
<td><p>Ein Zeichenfolgenattribut. Der Benutzerreplikationsdienst konvertiert diesen Typ in UTF-8, bevor er in der Tabelle &quot;AbUserEntry&quot; gespeichert wird.</p></td>
</tr>
<tr class="even">
<td><p>0x1</p></td>
<td><p>Ein Binärattribut. Der Benutzerreplikationsdienst speichert dieses Attribut ohne Konvertierung im Blob.</p></td>
</tr>
<tr class="odd">
<td><p>0x2</p></td>
<td><p>Ein Zeichenfolgenattribut, das jedoch nur dann einbezogen wird, wenn der Attributwert mit &quot;tel:&quot; beginnt. Dies wird hauptsächlich für Zeichenfolgenattribute mit mehreren Werten verwendet, vor allem <strong>proxyAddresses</strong>. In diesem Fall beschränkt sich der Adressbuchserver auf <strong>proxyAddresses</strong>-Einträge, die mit &quot;tel:&quot; beginnen. Um daher Speicherplatz zu sparen, speichert der Benutzerreplikationsdienst nur die Einträge, die mit &quot;tel:&quot; beginnen.</p></td>
</tr>
<tr class="even">
<td><p>0x3</p></td>
<td><p>Ein Attribut mit boolescher Zeichenfolge. Lautet dieses TRUE, nimmt der Benutzerreplikationsdienst diesen Kontakt nicht in die Tabelle &quot;AbUserEntry&quot; auf. Lautet es FALSE, nimmt der Benutzerreplikationsdienst zwar die Attribute für diesen Kontakt in die Tabelle &quot;AbUserEntry&quot; auf, jedoch nicht das bestimmte Attribut mit diesem Kennzeichen. Dies ist ein weiterer Spezialtyp, der hauptsächlich für das Attribut <strong>msExchHideFromAddressLists</strong> gilt.</p></td>
</tr>
<tr class="odd">
<td><p>0x4</p></td>
<td><p>Ein Zeichenfolgenattribut, das jedoch nur dann einbezogen wird, wenn der Attributwert mit &quot;smtp:&quot; beginnt und das Symbol &quot;@&quot; enthält.</p></td>
</tr>
<tr class="even">
<td><p>0x5</p></td>
<td><p>Ein Zeichenfolgenattribut, das jedoch nur dann einbezogen wird, wenn der Attributwert mit &quot;tel:&quot; oder &quot;smtp:&quot; beginnt und das Symbol &quot;@&quot; enthält.</p></td>
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
<td><p>Wird dieses Attribut festgelegt, wird hierdurch ein erforderliches Attribut für einen Kontakt angegeben. Der Adressbuchserver nimmt einen Benutzer nur dann in die Tabelle &quot;AbUserEntry&quot; auf, wenn ein Wert für dieses Attribut in Active Directory vorhanden ist. Gibt es mehrere erforderliche Attribute, muss nur eines davon über einen Wert verfügen, damit der Benutzer in die Tabelle &quot;AbUserEntry&quot; aufgenommen wird.</p></td>
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
<td><p>Wird dieses Attribut festgelegt, nimmt der Adressbuchserver keine Objekte in die Tabelle &quot;AbUserEntry&quot; auf, die diesen Wert für das angegebene Attribut aufweisen. Wenn dieses Kennzeichenbit beispielsweise für das Attribut <strong>msRTCSIP-PrimaryUserAddress</strong> festgelegt wurde, werden Kontakte mit diesem Attribut nicht in die Datenbank geschrieben.</p></td>
</tr>
<tr class="odd">
<td><p>0x8000</p></td>
<td><p>Wird dieses Attribut festgelegt, nimmt der Adressbuchserver keine Objekte in die Tabelle &quot;AbUserEntry&quot; auf, die nicht diesen Wert für das angegebene Attribut aufweisen. Wurden beide Kennzeichenbits &quot;0x4000&quot; und &quot;0x8000&quot; für ein Objekt festgelegt, erhält das Attribut mit dem Kennzeichenbit &quot;0x4000&quot; Vorrang, und das Objekt wird aus der Tabelle &quot;AbUserEntry&quot; ausgeschlossen.</p></td>
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


Wenn in früheren Versionen von Lync Server eine Änderung an Active Directory vorgenommen wurde, musste der Adminstrator umgehend die Windows PowerShell-Cmdlets **Update -CSUserDatabase** und **Update –CSAddressBook** ausführen, um die Änderungen dauerhaft in der Lync Server-Benutzerdatenbank und RTCab-Datenbank zu speichern. In Lync Server 2013 erkennt der Lync Server-Benutzerreplikationsdienst die Änderungen in Active Directory und aktualisiert die Lync Server-Benutzerdatenbank basierend auf einem konfiguriertem Intervall. Außerdem übernimmt der Lync Server-Benutzerreplikationsdienst die Änderungen rasch in die RTC-Datenbank, ohne dass der Administrator "Update-CSAddressBook" ausführen muss. Wenn der Adressbuch-Webabfragedienst aktiviert ist, werden die Änderungen in den Suchergebnissen der Lync-Clients reflektiert. Administratoren müssen "Update-CSAddressBook" nur dann ausführen, wenn das Herunterladen von Adressbuchdateien aktiviert ist.


> [!NOTE]
> Standardmäßig wird der Lync Server-Benutzerreplikationsdienst automatisch alle 5 Minuten ausgeführt. Sie können dieses Intervall mit "Set -CSUserReplicatorConfiguration -ReplicationCycleInterval &lt;&gt;" konfigurieren.



## Filtern des Adressbuchs

Die in den Adressbuchserver-Dateien enthaltenen Benutzer können basierend auf bestimmten Attributen der Active Directory-Domänendienste gesteuert werden, die in der Tabelle "AbAttribute" aufgeführt sind. Das Attribut **msExchangeHideFromAddressBook** ist ein solches Filterattribut. Hierbei handelt es sich um ein Benutzerattribut, das durch das Exchange-Schema hinzugefügt wird. Wenn der Wert dieses Attributs TRUE lautet, blendet Exchange Server den Kontakt aus der globalen Outlook-Adressliste (GAL) aus. Lautet der Wert dieses Attributs TRUE, nimmt der Benutzerreplikationsdienst außerdem den betreffenden Benutzer nicht in die Tabelle "AbUserEntry" auf, und der Benutzer ist nicht in den Adressbuchserver-Dateien enthalten.

Mithilfe einiger Kennzeichenbits können Sie einen Filter definieren, der für Adressbuchserver-Attribute verwendet wird. Beispielsweise kann das Attribut anhand bestimmter vorhandener Kennzeichenbits als Include- oder als Exclude-Attribut gekennzeichnet werden. Der Benutzerreplikationsdienst filtert Kontakte heraus, die ein Exclude-Attribut enthalten, sowie Kontakte, die kein Include-Attribut aufweisen.


> [!WARNING]
> Weitere Informationen zum Filtern des Adressbuchs finden Sie unter <A href="https://technet.microsoft.com/en-us/library/gg415643(v=ocs.15)">Cmdlets für Adressbuchserver</A> und <A href="http://go.microsoft.com/fwlink/?linkid=330430">Filtern des Lync&nbsp;2013.-Adressbuchs</A>



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
<td><p>Wird dieses Attribut festgelegt, wird hierdurch ein erforderliches Attribut für einen Kontakt angegeben. Der Benutzerreplikationsdienst filtert anhand dieses Kennzeichenbits Kontakte heraus, die nicht mindestens eines der erforderlichen Attribute enthalten. &quot;OuPathId&quot; ist ein erforderliches Attribut, das immer festgelegt ist. Daher sollte mindestens ein weiteres erforderliches Attribut festgelegt sein. Andernfalls wird der Kontakt (also mit dem Wert des erforderlichen Attributs &quot;OuPathId&quot;) dennoch nicht in die Datenbank geschrieben. Wenn beispielsweise <strong>telephoneNumber</strong> und <strong>homePhone</strong> als erforderliche Attribute definiert sind, werden nur die Kontakte in die Datenbank geschrieben, die mindestens eines dieser Attribute aufweisen.</p></td>
</tr>
<tr class="even">
<td><p>0x4000</p></td>
<td><p>Wird dieses Attribut festgelegt, weist dies auf ein Exclude-Attribut hin. Der Benutzerreplikationsdienst filtert anhand dieses Kennzeichenbits Kontakte heraus, die dieses Attribut enthalten. Wenn beispielsweise <strong>msRTCSIP-PrimaryUserAddress</strong> als Exclude-Attribut festgelegt wurde, werden Kontakte mit diesem Attribut nicht in die Datenbank geschrieben.</p></td>
</tr>
<tr class="odd">
<td><p>0x8000</p></td>
<td><p>Wird dieses Attribut festgelegt, weist dies auf ein Include-Attribut hin. Der Benutzerreplikationsdienst filtert anhand dieses Kennzeichenbits Kontakte heraus, die dieses Attribut nicht enthalten. Wenn beispielsweise <strong>msRTCSIP-PrimaryUserAddress</strong> als Include-Attribut festgelegt wurde, werden nur Kontakte mit diesem Attribut in die Datenbank geschrieben.</p></td>
</tr>
</tbody>
</table>



> [!NOTE]
> Wurden sowohl das Kennzeichenbit "0x4000" (Exclude-Attribut) als auch das Kennzeichenbit "0x8000" (Include-Attribut) festgelegt, setzt das Bit "0x4000" das Bit "0x8000" außer Kraft, und der Kontakt wird ausgeschlossen.



Auch wenn Sie das Adressbuch so filtern können, dass es nur bestimmte Benutzer enthält, wird durch diese Einschränkung der Einträge nicht die Möglichkeit der Benutzer beschränkt, die gefilterten Benutzer zu kontaktieren oder deren Anwesenheitsstatus anzuzeigen. Benutzer können nicht im Adressbuch enthaltene Benutzer immer finden, manuell Sofortnachrichten senden oder manuell Anrufe an diese Benutzer tätigen, indem sie den vollständigen Anmeldenamen eines Benutzers eingeben. Außerdem können auch Kontaktinformationen für einen Benutzer in Outlook gefunden werden.

Auch wenn Sie bei vollständigen Kontaktdatensätzen in den Adressbuchdateien Lync Server verwenden können, um E-Mail-, Telefon- oder Enterprise-VoIP-Anrufe (falls Enterprise-VoIP auf dem Server aktiviert ist) mit Benutzern zu initiieren, die nicht für SIP (Session Initiation Protocol) konfiguriert sind, ziehen einige Organisationen es vor, nur SIP-aktivierte Benutzer in ihren Adressbuchserver-Einträgen aufzunehmen. Sie können das Adressbuch so filtern, dass darin nur SIP-aktivierte Benutzer enthalten sind, indem Sie das Bit "0x800" in der Spalte **Flags** der folgenden erforderlichen Attribute löschen: **mailNickname**, **telephoneNumber**, **homePhone** und **mobile**. Eine weitere Möglichkeit, das Adressbuch so zu filtern, dass darin nur SIP-aktivierte Benutzer enthalten sind, besteht darin, das Bit "0x8000" (Include-Attribut) in der Spalte **Flags** des Attributs **msRTCSIP-PrimaryUserAddress** festzulegen: Auf diese Weise können auch Dienstkonten aus den Adressbuchdateien ausgeschlossen werden.

Nachdem Sie die Tabelle "AbAttribute" geändert haben, können Sie die Daten in der Tabelle "AbUserEntry" aktualisieren, indem Sie das Cmdlet**Update-CsUserDatabase** ausführen. Nach Abschluss der Benutzerreplikation können Sie die Datei im Adressbuchserver-Dateispeicher aktualisieren, indem Sie manuell das Cmdlet **UpdateCsAddressBook** ausführen.


> [!NOTE]
> Der Front-End-Server, auf dem sich der Adressbuchserver befindet, kann vom Administrator nicht konfiguriert werden. Er wird während der Bereitstellung ausgewählt – in der Regel handelt es sich um den ersten bereitgestellten Front-End-Server. Falls er ausfällt, wird der Adressbuchdienst ohne Administratoreingriff auf einen anderen Front-End-Server verschoben.




> [!IMPORTANT]
> Wenn Sie Ihre Infrastruktur konsolidiert oder auf andere Weise von einer Bereitstellung mit mehreren Gesamtstrukturen oder einer Bereitstellung aus übergeordneten/untergeordneten Domänen geändert haben (beispielsweise durch Konsolidierung Ihrer Infrastruktur vor dem Wechsel auf Lync Server), stellen Sie möglicherweise fest, dass der Download des Adressbuchdiensts und die Webabfrage des Adressbuchs für einige Benutzer nicht mehr möglich ist. In einer Bereitstellung, die zuvor mehrere Domänen oder Gesamtstrukturen umfasste, ist das Attribut <STRONG>MsRTCSIP-OriginatorSid</STRONG> für die Benutzerobjekte belegt, bei denen das Problem auftritt. Das Attribut <STRONG>MsRTCSIP-OriginatorSid</STRONG> muss für diese Objekte auf NULL gesetzt werden, um das Problem zu beheben.


