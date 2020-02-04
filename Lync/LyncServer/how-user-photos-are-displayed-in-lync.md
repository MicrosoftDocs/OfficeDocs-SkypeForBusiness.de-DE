---
title: So werden Benutzerfotos in Lync angezeigt
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: How user photos are displayed in Lync
ms:assetid: b44a364d-a1d2-4d45-b27a-b5f77775e233
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn783119(v=OCS.15)
ms:contentKeyID: 62835297
ms.date: 08/27/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8cd3214c3ada87db6f44f6b99373346d4f0a27d4
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41730695"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="how-user-photos-are-displayed-in-lync"></a>So werden Benutzerfotos in Lync angezeigt

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2014-08-25_

**Zusammenfassung:** Benutzer Fotos, die in lync-Client angezeigt werden, können je nach verwendetem lync-Feature unterschiedlich sein, beispielsweise in einer Konferenz oder im Chat.

Lync 2010 hat die Möglichkeit eingeführt, ein Foto in Ihr lync-Profil einzubeziehen, das für andere lync-Benutzer angezeigt wird. Sie können auch auswählen, ob Fotos für Ihre Kontakte in lync-Client angezeigt werden sollen. In lync 2013: Unterstützung für Fotos mit hoher Auflösung für Benutzer. In diesem Thema wird beschrieben, wie Benutzer Fotos vom lync-Client abgerufen und angezeigt werden, wo die Bilder gespeichert werden, welche Einschränkungen für die einzelnen Bildquellen gelten und wie Benutzer Fotos von verschiedenen lync-Diensten verwendet werden.

<div>

## <a name="planning-considerations"></a>Planungsüberlegungen

Bei der Planung der Implementierung der Unterstützung für Benutzer Fotos sollten Sie Folgendes berücksichtigen:

  - Für die Unterstützung von Benutzer Fotos mit hoher Auflösung muss das Postfach des Benutzers auf Exchange 2013 und das lync-Benutzerkonto im lync 2013-Pool gespeichert sein.

  - Benutzer Fotos mit hoher Auflösung werden nur in einer Umgebung unterstützt, in der sowohl lync Server 2013 als auch Exchange 2013 verwendet werden.

  - Benutzer mit Postfächern in Exchange 2010 verwenden immer das **thumbnailPhoto** -Attribut aus AD DS als Quelle für das Benutzer Foto.

  - Ein Benutzer Foto, das als **thumbnailPhoto** -Attribut in AD DS gespeichert ist, wird für externe/verbundene Kontakte nicht angezeigt.

  - Wenn die Fotos für Benutzer Kontakte in AD DS gespeichert sind, ist die verwendete Bilddatei auf 96 × 96 Pixel und auf eine Dateigröße von 100 KB limitiert.

  - Wenn die Konnektivität zwischen lync Server und Exchange Server verloren geht, werden die **thumbnailPhoto** der Benutzer mit niedriger Auflösung von AD DS und nur internen Benutzern angezeigt.

  - Benutzer Fotos mit hoher Auflösung werden in lync 2013-Besprechungen angezeigt, wenn für einen aktiven Lautsprecher kein Video aktiviert ist. Wenn Sie den Mauszeiger über ein Miniaturbild im Katalog bewegen, wird auch das Foto mit hoher Auflösung angezeigt.

</div>

<div>

## <a name="user-photos-in-lync-2010"></a>Benutzer Fotos in lync 2010

Im lync 2010-Client können Sie aus zwei Optionen auswählen, um ein Foto für Ihr Profil, das **standardmäßige Unternehmensbild** und das **Bild von einer Webadresse**anzuzeigen.

<div>

## <a name="default-corporate-picture"></a>Standardbild für Unternehmen

Wenn Sie die Standardoption für das **Unternehmensbild** auswählen, ruft lync das für Sie angezeigte Foto in den Active Directory-Domänendiensten ab. Das verwendete Bild ist das Bild, das als Wert für das **thumbnailPhoto** -Attribut in den Active Directory-Domänendiensten definiert ist. Hierbei handelt es sich um die gleiche Datei, die von Exchange zum Anzeigen von Bildern in Outlook verwendet wird.

Überlegungen zur Verwendung von Bildern aus Active Directory-Domänendiensten umfassen Folgendes:

  - Es werden nur Bilder mit einer Größe von bis zu 96 Pixeln von 96 Pixeln unterstützt. Die Dateigröße für das Bild ist auf 100 KB limitiert.

  - Standardmäßig können Benutzer das für das **thumbnailPhoto** -Attribut verwendete Bild ändern, allerdings nicht direkt über den lync-Client. Sie können dies über die Active Directory-Domänendienste deaktivieren.

  - Bilder, die in den Active Directory-Domänendiensten gespeichert sind, werden nicht für Kontakte außerhalb Ihrer Organisation angezeigt, auch wenn es sich um Verbund Kontakte handelt.

  - In großen Organisationen kann das Speichern und Abrufen der Bilder für eine große Anzahl von Benutzern Auswirkungen auf die Größe und Leistung der Datenbank für die Active Directory-Domänendienste haben.

  - Die geringen Bildabmessungen und die Dateigröße bedeuten, dass nur Bilder mit niedriger Auflösung verwendet werden können.

<div>

## <a name="how-users-manage-their-user-photos-in-active-directory-domain-services"></a>Verwalten von Benutzer Fotos in Active Directory-Domänendiensten durch Benutzer

Der Benutzer kann das Bild, das in seinem Active Directory-Domänendienst Profil verwendet wird, nicht direkt über den lync 2010-Client ändern. Sie können eine der folgenden Optionen verwenden, falls verfügbar:

  - **SharePoint Server**   -Benutzer können ein Foto auf "Meine Website" auf einem SharePoint-Server hochladen und dann die [Profilsynchronisierung in SharePoint konfigurieren](http://go.microsoft.com/fwlink/p/?linkid=507466) , um das Foto mit dem **thumbnailPhoto** -Attribut in den Active Directory-Domänendiensten zu synchronisieren.

  - **Foto, das auf öffentlich zugänglichen URL**   -Benutzern gespeichert ist, kann das Benutzer Foto konfigurieren, das eine öffentlich zugängliche URL für das Bild angibt, das Sie verwenden möchten. Das Bild muss ohne Kennwort öffentlich zugänglich sein. Das Bild, das bei der angegebenen Webadresse gespeichert ist, wird über die Kategorie Visitenkarte in den Anwesenheitsinformationen an andere Benutzer übertragen. Wenn der lync-Client ein Benutzer Foto anzeigen muss, wird das Bild von der angegebenen Webadresse abgerufen.

  - **Exchange 2010-Cmdlets für Windows PowerShell**   -Administratoren können das Cmdlet " [Import-RecipientDataProperty](http://go.microsoft.com/fwlink/p/?linkid=507468) " in der Exchange 2010-Verwaltungsshell ausführen, um das **thumbnailPhoto** -Attribut zu verwalten. Wenn Bilder mit Exchange 2010-Cmdlets importiert werden, ist die Dateigröße auf 10 KB limitiert.

  - **Tools von Drittanbietern**   Benutzer können nur Ihr eigenes Foto für das **thumbnailPhoto** -Attribut hochladen.

</div>

</div>

<div>

## <a name="show-a-picture-from-a-web-address"></a>Anzeigen eines Bilds aus einer Internetadresse

Wenn Sie die Option **Bild aus einer Webadresse anzeigen** auswählen, ruft lync das Bild an der von Ihnen eingegebenen Adresse ab und zeigt es für Ihr Benutzer Foto in lync an.

Überlegungen zur Verwendung von Bildern aus einer Webadresse sind die folgenden:

  - Die Dateigrößenbeschränkungen werden durch das **MaxPhotoSizeKB** -Attribut in der Clientrichtlinie bestimmt, das mit dem Cmdlet [New-CsClientPolicy](http://go.microsoft.com/fwlink/p/?linkid=507463) definiert ist. Die Standardgrößenbeschränkung beträgt 30 KB. Der Höchstwert ist 100 KB. Es gibt keine Einschränkung für die Auflösung des Bilds, aber wenn Sie versuchen, eine Bilddatei zu verwenden, die die Größenbeschränkung überschreitet, wird Sie nicht auf lync-Clients heruntergeladen. Sie können den Wert auf 0 setzen, um zu verhindern, dass alle Benutzer Fotos in lync verwendet werden.

  - Benutzer Fotos von einer Webadresse können von externen Föderationskontakten angezeigt werden.

</div>

<div>

## <a name="managing-users-photo-with-client-policy-cmdlets"></a>Verwalten des Fotos eines Benutzers mit Client Richtlinien-Cmdlets

In lync Server 2010 werden Clientrichtlinien Einstellungen mit den CsClientPolicy-Cmdlets konfiguriert. Die konfigurierten Richtlinieneinstellungen werden über die in-Band-Bereitstellung an Clients gesendet. Die beiden Parameter der CsClientPolicy-Cmdlets, die die Benutzer Fotoerfahrung bestimmen, sind **DisplayPhoto** und **MaxPhotoSizeKB**. Der entsprechende in-Band-Bereitstellungsparameter für **DisplayPhoto** und **MaxPhotoSizeKB** hat den Namen " **fotousage**". Werte für den Parameter " **fotousage** " werden über die **endpointConfiguration** **provisiongroup**an Clients gesendet. Weitere Informationen finden Sie unter [Übersicht über Client Richtlinien und-Einstellungen](http://go.microsoft.com/fwlink/?linkid=507470) .

Der **DisplayPhoto** -Parameterwert bestimmt die Quelle des Foto Bilds des Benutzers. Die unterstützten Werte sind in der folgenden Tabelle enthalten.


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
<th>Lync 2010-Clienteinstellungen</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Nophoto</p></td>
<td><p>Keine</p></td>
<td><p><strong>Mein Bild nicht anzeigen</strong></p></td>
</tr>
<tr class="even">
<td><p>PhotoFromADOnly</p></td>
<td><p>Active Directory</p></td>
<td><p><strong>Standardbild für Unternehmen</strong></p></td>
</tr>
<tr class="odd">
<td><p>Allphotos</p></td>
<td><p>Internetadresse</p></td>
<td><p><strong>Anzeigen eines Bilds aus einer Internetadresse</strong></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="how-lync-2010-client-gets-photos"></a>So erhält lync 2010-Client Fotos

In lync 2010 werden Benutzer Fotos vom Adressbuchdienst auf dem Server verwaltet. Der lync-Client ruft Benutzer Fotos ab, indem er zuerst den Adressbuch-Webabfrage Dienst (ABWQ) auf dem Server abfragt, der über den Webdienst für die Verteilerlistenerweiterung verfügbar gemacht wird. Der Client empfängt die Bilddatei und kopiert Sie dann in den Cache des Benutzers, um zu vermeiden, dass das Bild jedes mal heruntergeladen wird, wenn es angezeigt werden muss. Die von der Abfrage zurückgegebenen Attributwerte werden auch im zwischengespeicherten Adressbuchdienst Eintrag für den Benutzer gespeichert. Der Adressbuchdienst löscht alle zwischengespeicherten Bilder alle 24 Stunden, was bedeutet, dass es bis zu 24 Stunden dauern kann, bis neue Benutzer Bilder im Cache auf dem Server aktualisiert werden. Sie können eine Aktualisierung des Caches erzwingen, indem Sie das Cmdlet [Update-CsAddressBook](https://docs.microsoft.com/powershell/module/skype/Update-CsAddressBook) verwenden.

Benutzer Fotos, die im Anwesenheitsstatus enthalten sind, weisen auch einen zugehörigen Hashwert auf, mit dem lync-Client ermittelt, ob ein neueres Bild verfügbar ist. Der Client wird automatisch über Änderungen an der im Anwesenheitsstatus verwendeten Bilddatei benachrichtigt.

<div class=" ">


> [!NOTE]  
> Da Fotos nicht in der GalContacts. DB-Datenbank gespeichert sind, hängt das Herunterladen von Benutzer Fotos nicht von der <STRONG>AddressBookAvailability</STRONG> -Einstellung in der Clientrichtlinie ab (<A href="http://go.microsoft.com/fwlink/p/?linkid=507508">Satz-CsClientPolicy</A>).



</div>

Die Abfrage des ABWQ-Diensts umfasst die folgenden Attribute:

  - **Photo Hash**   den Hashwert der binären Fotodaten und wird verwendet, um zu bestimmen, ob sich das aktuelle Foto geändert hat.

  - **PhotoRelPath**   der relative Pfad zu der auf dem Server gespeicherten Bilddatei.

  - **Fotografieren**   Sie die Größe der Bilddatei in Bytes.

  - **Timestamp**   das Datum und die Uhrzeit, zu dem die Bilddatei zuletzt vom Server heruntergeladen und in den Clientcache kopiert wurde.

Als nächstes vergleicht der lync 2010-Client nach dem Abrufen der Bilddatei die von der Abfrage zurückgegebenen Attributwerte mit den vom Client empfangenen Attributwerten aus der in-Band-Bereitstellung, um festzustellen, ob Sie sich unterscheiden. Wenn sich die Werte unterscheiden, ruft der Client die Bilddatei des angemeldeten Benutzers mit einer HTTP GET-Anforderung ab.

Darüber hinaus überprüft der Client den Server alle 24 Stunden ab dem Zeitpunkt, zu dem die zwischengespeicherte Version der Bilddatei erstellt wurde, um den Wert des Foto **Hash** Attributs auf dem Server mit dem Wert auf dem Client zu vergleichen. Wenn sich die Werte unterscheiden, weiß der Client, dass sich die Bilddatei geändert hat. Um die aktualisierte Image-Datei abzurufen, fragt der Client erneut den ABWQ-Dienst ab, um die Bilddatei im Clientcache mit der Bilddatei auf dem Server zu aktualisieren, wodurch auch der **Zeitstempel** für die Datei im Clientcache zurückgesetzt wird.

Im folgenden wird eine Beispielantwort auf eine Abfrage des ABWQ-Diensts veranschaulicht:
```xml
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
```

</div>

</div>

<div>

## <a name="user-photos-in-lync-2013"></a>Benutzer Fotos in lync 2013

Lync 2013 hat Unterstützung für Bilder mit hoher Auflösung für Benutzer Fotos eingeführt. Lync 2013 umfasst auch die Unterstützung für das Speichern von Benutzer Fotos im Postfach des Benutzers in Exchange 2013, wodurch die in lync 2010 vorhandenen Bildauflösungen und Größenbeschränkungen entfernt werden. Benutzer Fotos in lync 2013 können bis zu 648 Pixel von 648 Pixeln mit einer Dateigröße von bis zu 20 MB sein. Fotos mit hoher Auflösung in lync 2013 müssen sich im Postfach des Benutzers in Exchange 2013 befinden und nur mit dem lync 2013-Client unterstützt werden. Diese Integration in Exchange nutzt das neue Autorisierungsframework, das in den 2013-Versionen von lync, Exchange und SharePoint namens OAuth enthalten ist.

Wenn Exchange 2013 in Ihrer Bereitstellung nicht verwendet wird, ist die Unterstützung für Benutzer Fotos identisch mit lync 2010. Die Benutzeroptionen zur Auswahl des zu verwendenden Fotos unterscheiden sich jedoch in lync 2013-Client. In lync 2013-Client können Benutzer entweder " **mein Bild verbergen** " oder " **mein Bild anzeigen**" auswählen. Die Option " **Bild von einer Website anzeigen** " ist standardmäßig nicht verfügbar, kann aber durch Zuweisen einer Clientrichtlinie aktiviert werden.

<div>

## <a name="hide-my-picture"></a>Mein Bild ausblenden

Einstellungen für Benutzer Fotos finden Sie im Dialogfeld " **Optionen** " in lync 2013. Wenn Sie **mein Bild ausblenden**auswählen, wird im lync-Client kein Benutzer Foto angezeigt, aber Ihr Foto wird weiterhin auf Ihrer Visitenkarte und außerhalb von lync angezeigt.

</div>

<div>

## <a name="show-my-picture"></a>Mein Bild anzeigen

Wenn Sie die Option " **mein Bild anzeigen** " auswählen, wird das Benutzer Foto in einem lync-Client und anderen Benutzern in lync-Unterhaltungen angezeigt. Das verwendete Bild wird in AD DS gespeichert.

</div>

<div>

## <a name="show-a-picture-from-a-website"></a>Anzeigen eines Bilds von einer Website

Die Option **Bild von einer Website anzeigen** steht in lync 2013 nach dem Festlegen einer Clientrichtlinie zum Aktivieren zur Verfügung. Die Client Version muss neuer als 15.0.4535.1002 sein, die mit den [kumulierten Updates für lync installiert wird: November 2013](http://go.microsoft.com/fwlink/p/?linkid=509908). Benutzer müssen sich möglicherweise abmelden und dann wieder zurück, um die Änderungen im Client anzuzeigen.

Sie können festlegen, dass die Clientrichtlinie für die **Anzeige von Bildern aus einer Website** Einstellung aktiviert ist, indem Sie die Richtlinie für die CsClientPolicy in der lync Server [-](https://docs.microsoft.com/powershell/module/skype/Set-CsClientPolicy) Verwaltungsshell ausführen. Die folgenden Beispiel-Cmdlets veranschaulichen, wie Sie die Richtlinie für alle Benutzer in Ihrer Bereitstellung global festlegen:

   ```powershell
    $pe=New-CsClientPolicyEntry -Name EnablePresencePhotoOptions -Value True
   ```

   ```powershell
    $po=Get-CsClientPolicy -Identity Global
   ```

   ```powershell
    $po.PolicyEntry.Add($pe)
   ```

   ```powershell
    Set-CsClientPolicy -Instance $po
   ```


Wenn ein Bild in das Postfach des Benutzers hochgeladen wird, erstellt Exchange automatisch eine Version der niedrigeren Auflösung des Bilds, die in Clientanwendungen verwendet werden kann. Das Benutzer Foto wird in AD DS ebenfalls aktualisiert.

<div class=" ">


> [!NOTE]  
> Wenn eine Bilddatei in AD DS aktualisiert wird, wird ein Bild von 48 x 48 Pixel erstellt und für die thumbnailPhoto in AD DS verwendet. Jedes vorhandene Bild wird ersetzt. Wenn Sie AD DS also ein 96 x 96-Bild hinzugefügt haben, wird es mit dem neuen 48 x 48-Bild überschrieben. Dies ist nur wichtig, wenn Sie Benutzer in Ihrer Umgebung mit lync 2010-Clients verwenden, da diese Clients Benutzer Fotos von AD DS erhalten. Sie können 96 x 96 Pixelbilder importieren, um diejenigen zu ersetzen, die von AD DS erstellt wurden, wenn Sie über lync 2010-Clients in Ihrer Organisation verfügen.



</div>

</div>

<div>

## <a name="user-photo-support-in-lync-2013"></a>Unterstützung für Benutzer Fotos in lync 2013

In lync 2013 werden für Benutzer Fotos drei Bildauflösungen unterstützt, wie in der folgenden Tabelle beschrieben. Das verwendete Bild wird von der Clientrichtlinien Einstellung bestimmt, die lync-Benutzern zugewiesen ist. Weitere Informationen finden Sie unter "Verwalten des Fotos des Benutzers mit Client Richtlinien-Cmdlets" in diesem Thema.


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Bildauflösung (Pixel)</th>
<th>Anwendung</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>48 x 48</p></td>
<td><p>Wird verwendet, wenn kein Bild höherer Auflösung ausgewählt ist</p></td>
</tr>
<tr class="even">
<td><p>96 x 96</p></td>
<td><p>Verwendung in Outlook Web App und Outlook 2013</p></td>
</tr>
<tr class="odd">
<td><p>648 x 648</p></td>
<td><p>Wird in lync 2013-Desktop Client und lync 2013 Web App verwendet</p></td>
</tr>
</tbody>
</table>


Jeder Benutzer mit einem in Exchange 2013 aktivierten Postfach kann ein anderes Bild, einschließlich Fotos mit hoher Auflösung, über die Outlook Web Access-oder lync 2013-Clientoptionen hochladen. Die empfohlenen Einstellungen für verwendete Bilder sind:

  - **Bildauflösung**   648 x 648 Pixel

  - **Farbtiefe**   24-Bit

  - **Bilddateigröße**   bis zu 20 MB

  - **Dateiformat**   JPEG

Ein typisches 24-Bit-JPEG-Bild mit einer Größe von 648 Pixeln von 648 Pixeln hat eine Dateigröße von etwa 240 KB, sodass für alle 4 Benutzer Fotos 1 MB Speicherplatz benötigt wird.

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

