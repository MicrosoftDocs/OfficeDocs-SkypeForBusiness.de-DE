---
title: So werden Benutzerfotos in Lync angezeigt
TOCTitle: So werden Benutzerfotos in Lync angezeigt
ms:assetid: b44a364d-a1d2-4d45-b27a-b5f77775e233
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Dn783119(v=OCS.15)
ms:contentKeyID: 62841172
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# So werden Benutzerfotos in Lync angezeigt

 

_**Letztes Änderungsdatum des Themas:** 2016-12-08_

**Zusammenfassung:** Im Lync-Client angezeigte Benutzerfotos können je nach verwendeter Lync-Funktion unterschiedlich sein, beispielsweise ob Sie sich in einer Konferenz oder einem Chat befinden.

In Lync 2010 wurde die Möglichkeit eingeführt, ein Foto zu Ihrem Lync-Profil hinzuzufügen, das für andere Lync-Benutzer angezeigt wird. Sie können außerdem auswählen, ob Fotos für Ihre Kontakte im Lync-Client angezeigt werden oder nicht. In Lync 2013 werden hochauflösende Fotos für Benutzer unterstützt. In diesem Thema wird beschrieben, wie der Lync-Client Benutzerfotos abruft und anzeigt, wo die Bilder gespeichert werden, welche Beschränkungen für die jeweilige Bildquelle bestehen und wie Benutzerfotos von verschiedenen Lync-Diensten verwendet werden.

## Überlegungen zur Planung

Sie sollten Folgendes bedenken, wenn Sie die Implementierung der Unterstützung für Benutzerfotos planen.

  - Die Unterstützung für hochauflösende Benutzerfotos erfordert, dass sich das Postfach des Benutzers auf Exchange 2013 und das Lync-Benutzerkonto in einem Lync 2013-Pool befindetn.

  - Hochauflösende Benutzerfotos werden nur in einer Umgebung unterstützt, in der sowohl Lync Server 2013 als auch Exchange 2013 verwendet werden.

  - Benutzer mit Postfächern auf Exchange 2010 verwenden immer das Attribut **thumbnailPhoto** von AD DS als Quelle für ihr Benutzerfoto.

  - Ein Benutzerfoto, das als **thumbnailPhoto**-Attribut von AD DS gespeichert ist, wird nicht für externe oder Partnerkontakte angezeigt.

  - Wenn die Fotos für Benutzerkontakte in AD DS gespeichert sind, ist die verwendete Bilddatei auf 96 × 96 Pixel und eine Dateigröße von höchstens 100 KB beschränkt.

  - Wenn die Konnektivität zwischen Lync Server und Exchange Server verloren geht, wird das **thumbnailPhoto** des Benutzers mit niedriger Auflösung von AD DS angezeigt und zwar nur für interne Benutzer.

  - Hochauflösende Benutzerfotos werden in Lync 2013-Besprechungen angezeigt, wenn ein aktiver Sprecher kein Video aktiviert hat. Das hochauflösende Foto wird außerdem angezeigt, wenn die Maus über ein Miniaturansichtsfoto im Katalog bewegt wird.

## Benutzerfotos in Lync 2010

Im Lync 2010-Client können Sie unter zwei Optionen für das Anzeigen eines Fotos für Ihr Profil auswählen: **Standardunternehmensbild** und **Bild von Webadresse anzeigen**.

## Standardunternehmensbild

Wenn Sie die Option **Standardunternehmensbild** auswählen, ruft Lync das für Sie angezeigte Foto von den Active Directory-Domänendiensten ab. Das verwendete Bild ist das Bild, das als Wert für das Attribut **thumbnailPhoto** in Active Directory-Domänendienste definiert ist. Diese Datei wird auch von Exchange zum Anzeigen von Bildern in Outlook verwendet.

Berücksichtigen Sie die folgenden Überlegungen zur Verwendung von Bildern von Active Directory-Domänendienste:

  - Nur Bilder mit Maßen von bis zu 96 mal 96 Pixeln werden unterstützt. Die Dateigröße für das Bild ist auf 100 KB beschränkt.

  - Standardmäßig können Benutzer das für das Attribut **thumbnailPhoto** verwendete Bild ändern, allerdings nicht direkt über den Lync-Client, sondern über die Active Directory-Domänendienste.

  - In den Active Directory-Domänendiensten gespeicherte Bilder werden nicht für externe Kontakte Ihrer Organisation angezeigt, selbst wenn es sich um Partnerkontakte handelt.

  - In großen Organisationen wirkt sich das Speichern und Abrufen der Bilder für eine große Anzahl von Benutzern möglicherweise auf die Größe und Leistung der Active Directory-Domänendienstedatenbank aus.

  - Die Beschränkungen für die Maße und Dateigröße von Bildern bedeuten, dass nur Bilder mit niedriger Auflösung verwendet werden können.

## So verwalten Benutzer ihre Benutzerfotos in den Active Directory-Domänendiensten

Der Benutzer kann das in seinem Active Directory-Domänendiensteprofil verwendete Bild nicht direkt über den Lync 2010-Client ändern. Das ist nur über die folgenden Optionen möglich, falls verfügbar:

  - **SharePoint Server**   Benutzer können ein Foto zu "Meine Website" auf SharePoint Server hochladen und dann die [Profilsynchronisierung in SharePoint konfigurieren](http://go.microsoft.com/fwlink/p/?linkid=507466), um das Foto mit dem Attribut **thumbnailPhoto** in den Active Directory-Domänendiensten zu synchronisieren.

  - **Unter einer öffentlich zugänglichen URL gespeichertes Foto**   Benutzer können bei der Konfiguration ihres Fotos eine öffentlich zugängliche URL für das gewünschte Bild angeben. Das Bild muss ohne ein Kennwort öffentlich zugänglich sein. Das unter der angegebenen Webadresse gespeicherte Bild wird über die Visitenkartenkategorie in den Anwesenheitsinformationen an andere Benutzer übertragen. Wenn der Lync-Client ein Benutzerfoto anzeigen muss, ruft er das Bild von der angegebenen Webadresse ab.

  - **Exchange 2010-Cmdlets für Windows PowerShell**   Administratoren können das Cmdlet [Import-RecipientDataProperty](http://go.microsoft.com/fwlink/p/?linkid=507468) in der Exchange 2010-Verwaltungsshell ausführen, um das Attribut **thumbnailPhoto** zu verwalten. Wenn Bilder mit Exchange 2010-Cmdlets importiert werden, ist die Dateigröße auf 10 KB begrenzt.

  - **Drittanbietertools**   Benutzer können ihr eigenes Foto für das Attribut **thumbnailPhoto** hochladen.

## Bild von Webadresse anzeigen

Wenn Sie die Option **Bild von Webadresse anzeigen** auswählen, ruft Lync das Bild unter der von Ihnen eingegebenen Adresse ab und zeigt es als Ihr Benutzerfoto in Lync an.

Berücksichtigen Sie die folgenden Überlegungen zur Verwendung von Bildern von einer Webadresse:

  - Dateigrößenbeschränkungen werden vom Attribut **MaxPhotoSizeKB** in der Clientrichtlinie bestimmt, das mit dem Cmdlet [New-CsClientPolicy](http://go.microsoft.com/fwlink/p/?linkid=507463) definiert wird. Die Standardgrößenbeschränkung beträgt 30 KB. Der maximale Wert ist 100 KB. Es gibt keine Einschränkung für die Auflösung des Bilds, aber wenn Sie versuchen, eine Bilddatei zu verwenden, die die Größenbeschränkung überschreitet, wird das Bild nicht an Lync-Clients hochgeladen. Sie können den Wert auf 0 setzen, um die Verwendung aller Benutzerfotos in Lync zu deaktivieren.

  - Benutzerfotos von einer Webadresse können von externen Partnerkontakten gesehen werden.

## Verwalten eines Benutzerfotos mit Clientrichtlinien-Cmdlets

In Lync Server 2010 werden Clientrichtlinieneinstellungen mit den CsClientPolicy-Cmdlets konfiguriert. Die konfigurierten Richtlinieneinstellungen werden über die In-Band-Bereitstellung an Clients gesendet. Die Benutzerfotoerfahrung wird durch die zwei Parameter **DisplayPhoto** und **MaxPhotoSizeKB** der CsClientPolicy-Cmdlets bestimmt. Der entsprechende In-Band-Bereitstellungsparameter für **DisplayPhoto** und **MaxPhotoSizeKB** heißt **PhotoUsage**. Die Werte für den Parameter **PhotoUsage** werden über **endpointConfigurationprovisionGroup** an Clients gesendet. Weitere Informationen finden Sie unter [Übersicht über Clientrichtlinien und -einstellungen](http://go.microsoft.com/fwlink/?linkid=507470).

Der Parameterwert für **DisplayPhoto** bestimmt die Quelle des Bilds für das Benutzerfoto. Die unterstützten Werte finden Sie in der folgenden Tabelle.


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>DisplayPhoto-Parameterwert</th>
<th>Bildquelle</th>
<th>Lync 2010-Clienteinstellung</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>NoPhoto</p></td>
<td><p>Keine</p></td>
<td><p><strong>Mein Bild nicht anzeigen</strong></p></td>
</tr>
<tr class="even">
<td><p>PhotoFromADOnly</p></td>
<td><p>Active Directory</p></td>
<td><p><strong>Standardunternehmensbild</strong></p></td>
</tr>
<tr class="odd">
<td><p>AllPhotos</p></td>
<td><p>Webadresse</p></td>
<td><p><strong>Bild von Webadresse anzeigen</strong></p></td>
</tr>
</tbody>
</table>


## So erhält der Lync 2010-Client Fotos

In Lync 2010 werden Benutzerfotos auf dem Server vom Adressbuchdienst verwaltet. Der Lync-Client erhält Benutzerfotos, indem er zunächst den Adressbuch-Webabfragedienst auf dem Server abfragt, der über den Verteilerlistenerweiterungs-Webdienst zur Verfügung gestellt wird. Der Client empfängt die Bilddatei und kopiert sie dann in den Cache des Benutzers, um nicht jedes Mal das Bild herunterladen zu müssen, wenn es angezeigt werden soll. Die von der Abfrage zurückgegebenen Attributwerte werden außerdem im zwischengespeicherten Adressbuchdienst-Eintrag für den Benutzer gespeichert. Der Adressbuchdienst löscht alle zwischengespeicherten Bilder alle 24 Stunden, was bedeutet, dass es bis zu 24 Stunden dauern kann, bis neue Benutzerbilder im Cache auf dem Server aktualisiert sind. Sie können eine Aktualisierung an den Cache erzwingen, indem Sie das Cmdlet [Update-CsAddressBook](https://docs.microsoft.com/en-us/powershell/module/skype/Update-CsAddressBook) verwenden.

Im Anwesenheitsstatus enthaltene Benutzerfotos verfügen außerdem über einen zugewiesenen Hashwert, den der Lync-Client verwendet, um zu bestimmen, ob ein neueres Bild vorhanden ist. Der Client wird automatisch über Änderungen an der im Anwesenheitsstatus verwendeten Bilddatei benachrichtigt.


> [!NOTE]
> Da Fotos nicht in der GalContacts.db-Datenbank gespeichert werden, ist das Herunterladen von Benutzerfotos nicht von der Einstellung <STRONG>AddressBookAvailability</STRONG> in der Clientrichtlinie abhängig (<A href="http://go.microsoft.com/fwlink/p/?linkid=507508">Set-CsClientPolicy</A>).



Die Abfrage an den Adressbuch-Webabfragedienst enthält die folgenden Attribute:

  - **PhotoHash**   Der Hashwert der binären Fotodaten, mit dem bestimmt wird, ob das aktuelle Foto geändert wurde

  - **PhotoRelPath**   Der relative Pfad zu der auf dem Server gespeicherten Bilddatei

  - **PhotoSize**   Die Größe der Bilddatei in Byte

  - **TimeStamp**   Datum und Zeit, zu denen die Bilddatei zuletzt vom Server heruntergeladen und an den Clientcache kopiert wurde

Nach dem Abrufen der Bilddatei vergleicht der Lync 2010-Client dann die von der Abfrage zurückgegebenen Attributwerte mit den vom Client durch die In-Band-Bereitstellung erhaltenen Attributwerten, um zu sehen, ob sich diese unterscheiden. Wenn sich die Werte unterscheiden, erhält der Client die Bilddatei des angemeldeten Benutzers mit einer HTTP GET-Anforderung.

Darüber hinaus wendet sich der Client ab dem Zeitpunkt, an dem die zwischengespeicherte Version der Bilddatei erstellt wurde, alle 24 Stunden an den Server, um den Wert des Attributs **PhotoHash** auf dem Server mit dem Wert auf dem Client zu vergleichen. Wenn die Werte unterschiedlich sind, weiß der Client, dass sich die Bilddatei geändert hat. Zum Abrufen der aktualisierten Bilddatei fragt der Client erneut den Adressbuch-Webabfragedienst ab, um die Bilddatei im Clientcache mit der Bilddatei auf dem Server zu aktualisieren, wodurch auch der **TimeStamp** für die Datei im Clientcache zurückgesetzt wird.

Im Folgenden ist eine Beispielantwort auf eine Abfrage an den Adressbuch-Webabfragedienst dargestellt:

    <Attribute>
              <Name>PhotoRelPath</Name>
              <Value>efa6096aed2746cb9ab2037f7dbdde9d.f2eeeb5946db54a7aa607ecd3ae09d
              95.photo</Value>
              <Values xmlns:d6p1="http://schemas.microsoft.com/2003/10/Serialization/Arrays" i:nil="true" />
    </Attribute>
    <Attribute>
              <Name>PhotoHash</Name>
              <Value>f2eeeb5946db54a7aa607ecd3ae09d95</Value>
              <Values xmlns:d6p1="http://schemas.microsoft.com/2003/10/Serialization/Arrays" i:nil="true" />
    </Attribute>
    <Attribute>
         <Name>PhotoSize</Name>
         <Value>4620</Value>
         <Valuesxmlns:d6p1="http://schemas.microsoft.com/2003/10/Serialization/Arrays"
    i:nil="true" />
    </Attribute>

## Benutzerfotos in Lync 2013

In Lync 2013 wurde die Unterstützung für hochauflösende Bilder für Benutzerfotos eingeführt. Lync 2013 bietet außerdem Unterstützung für das Speichern von Benutzerfotos im Postfach des Benutzers auf Exchange 2013, wodurch die in Lync 2010 vorhandenen Einschränkungen für die Bildauflösung und -größe aufgehoben werden. Benutzerfotos in Lync 2013 können bis zu 648 mal 648 Pixel mit einer Dateigröße von bis zu 20 MB groß sein. Hochauflösende Fotos in Lync 2013 müssen sich im Postfach des Benutzers auf Exchange 2013 befinden und werden nur mit dem Lync 2013-Client unterstützt. Diese Integration in Exchange nutzt das neue Autorisierungsframework namens Oauth, das in den 2013-Versionen von Lync, Exchange und SharePoint enthalten ist.

Wenn Exchange 2013 nicht in Ihrer Bereitstellung verwendet wird, ist die Unterstützung für Benutzerfotos dieselbe wie in Lync 2010. Die Benutzeroptionen zum Auswählen des verwendeten Fotos sind im Lync 2013-Client jedoch unterschiedlich. Im Lync 2013-Client können Benutzer entweder **Mein Bild ausblenden** oder **Mein Bild anzeigen** auswählen. Die Option **Bild von Webadresse anzeigen** ist standardmäßig nicht verfügbar, kann aber durch Zuweisen einer Clientrichtlinie aktiviert werden.

## Mein Bild ausblenden

Die Einstellungen für Benutzerfotos befinden sich in Lync 2013 im Dialogfeld **Optionen**. Wenn Sie **Mein Bild ausblenden** auswählen, wird im Lync-Client kein Benutzerfoto für Sie angezeigt. Ihr Foto wird aber immer noch auf Ihrer Visitenkarte und außerhalb von Lync angezeigt.

## Mein Bild anzeigen

Wenn Sie die Option **Mein Bild anzeigen** auswählen, wird Ihr Benutzerfoto in Ihrem Lync-Client und für andere Benutzer in Lync-Unterhaltungen angezeigt. Dabei wird das in AD DS gespeicherte Bild verwendet.

## Bild von Webadresse anzeigen

Die Option **Bild von Webadresse anzeigen** wird in Lync 2013 verfügbar, nachdem eine Clientrichtlinie zur Aktivierung der Option festgelegt wird. Die Clientversion muss neuer als 15.0.4535.1002 sein, die mit den [kumulativen Updates für Lync: November 2013](http://go.microsoft.com/fwlink/p/?linkid=509908) installiert wird. Benutzer müssen sich möglicherweise abmelden und erneut anmelden, um die Änderungen im Client zu sehen.

Sie können die Clientrichtlinie zur Aktivierung der Einstellung **Bild von Webadresse anzeigen** festlegen, indem Sie die Richtlinie [Set-CsClientPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsClientPolicy) in der Lync Server-Verwaltungsshell ausführen. Das folgende Beispiel-Cmdlet zeigt, wie Sie die Richtlinie global für alle Benutzer in Ihrer Bereitstellung festlegen:

    $pe=New-CsClientPolicyEntry -Name EnablePresencePhotoOptions -Value True

   &nbsp;

    $po=Get-CsClientPolicy -Identity Global

   &nbsp;

    $po.PolicyEntry.Add($pe)

   &nbsp;

    Set-CsClientPolicy -Instance $po

Wenn ein Bild an das Postfach des Benutzers hochgeladen wird, erstellt Exchange automatisch eine Version mit niedrigerer Auflösung des Bilds, die in Clientanwendungen verwendet werden kann. Das Benutzerfoto wird außerdem in AD DS aktualisiert.


> [!NOTE]
> Wenn eine Bilddatei in AD DS aktualisiert wird, wird ein 48 x 48 Pixel großes Bild erstellt und für "thumbnailPhoto" in AD DS verwendet. Jedes vorhandene Bild wird ersetzt. Wenn Sie also ein 96 x 96 Pixel großes Bild zu AD DS hinzugefügt haben, wird dieses mit dem neuen 48 x 48 Pixel großen Bild überschrieben. Das ist nur wichtig, wenn Sie Benutzer in Ihrer Umgebung haben, die Lync 2010-Clients verwenden, da diese Clients Benutzerfotos von AD DS erhalten. Sie können 96 x 96 Pixel große Bilder importieren, um die von AD DS erstellten Bilder zu ersetzen, wenn Lync 2010-Clients in Ihrer Organisation vorhanden sind.



## Unterstützung für Benutzerfotos in Lync 2013

In Lync 2013 werden drei Bildauflösungen für Benutzerfotos unterstützt, die in der folgenden Tabelle beschrieben sind. Das verwendete Bild wird von der Clientrichtlinieneinstellung bestimmt, die Lync-Benutzern zugewiesen ist. Weitere Informationen finden Sie unter "Verwalten eines Benutzerfotos mit Clientrichtlinien-Cmdlets" in diesem Thema.


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Bildauflösung (Pixel)</th>
<th>Application</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>48 x 48</p></td>
<td><p>Verwendet, wenn keine höhere Bildauflösung ausgewählt ist</p></td>
</tr>
<tr class="even">
<td><p>96 x 96</p></td>
<td><p>Verwendet in Outlook Web App und Outlook 2013</p></td>
</tr>
<tr class="odd">
<td><p>648 x 648</p></td>
<td><p>Verwendet im Lync 2013-Desktopclient und in Lync 2013 Web App</p></td>
</tr>
</tbody>
</table>


Alle Benutzer mit einem in Exchange 2013 aktivierten Postfach können ein anderes Bild, darunter hochauflösende Fotos, über Outlook Web Access oder Lync 2013-Clientoptionen hochladen. Für die verwendeten Bilder werden die folgenden Einstellungen empfohlen:

  - **Bildauflösung**   648 mal 648 Pixel

  - **Farbtiefe**   24-Bit

  - **Bilddateigröße**   bis zu 20 MB

  - **Dateiformat**   JPEG

Ein typisches 24-Bit-JPEG-Bild mit 648 mal 648 Pixeln hat eine Dateigröße von rund 240 KB, das heißt es wird jeweils 1 MB Speicherplatz pro vier Benutzerfotos benötigt.

