---
title: Anzeigen von Benutzer Fotos in lync
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
ms.openlocfilehash: 097262cc3a4ba4b56cd023bc5174d881426deff2
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2020
ms.locfileid: "42137916"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="how-user-photos-are-displayed-in-lync"></a>Anzeigen von Benutzer Fotos in lync

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2014-08-25_

**Zusammenfassung:** Benutzer Fotos, die in lync-Client angezeigt werden, können je nach verwendetem lync-Feature unterschiedlich sein, beispielsweise in einer Konferenz oder im Chat.

Lync 2010 wurde die Möglichkeit eingeführt, ein Foto mit Ihrem lync-Profil einzuschließen, das anderen lync-Benutzern angezeigt wird. Sie können auch auswählen, ob Fotos für Ihre Kontakte in lync-Client angezeigt werden sollen. In lync 2013 Unterstützung für hochauflösende Fotos für Benutzer. In diesem Thema wird beschrieben, wie Benutzer Fotos von lync-Client abgerufen und angezeigt werden, wo die Bilder gespeichert werden, welche Einschränkungen für welche Bildquellen gelten und wie Benutzer Fotos von verschiedenen lync-Diensten verwendet werden.

<div>

## <a name="planning-considerations"></a>Überlegungen zur Planung

Bei der Planung der Implementierung von Unterstützung für Benutzer Fotos sollten Sie Folgendes berücksichtigen.

  - Für die Unterstützung von hochauflösenden Benutzern ist es erforderlich, dass sich das Postfach des Benutzers auf Exchange 2013 und das lync-Benutzerkonto in lync 2013 Pool befinden.

  - Hochauflösende Benutzer Fotos werden nur in einer Umgebung unterstützt, in der sowohl lync Server 2013 als auch Exchange 2013 verwendet werden.

  - Benutzer mit Postfächern in Exchange 2010 verwenden immer das **thumbnailPhoto** -Attribut aus AD DS als Quelle für das Benutzer Foto.

  - Ein Benutzer Foto, das als **thumbnailPhoto** -Attribut aus AD DS gespeichert wird, wird nicht für externe/Verbund Kontakte angezeigt.

  - Wenn die Fotos für Benutzer Kontakte in AD DS gespeichert werden, ist die verwendete Bilddatei auf 96 × 96 Pixel und eine Dateigröße von mehr als 100 KB begrenzt.

  - Wenn die Konnektivität zwischen lync Server und Exchange Server verloren geht, wird die **thumbnailPhoto** der Benutzer mit niedriger Auflösung von AD DS und nur für interne Benutzer angezeigt.

  - Hochauflösende Benutzer Fotos werden in lync 2013 Besprechungen angezeigt, wenn für einen aktiven Lautsprecher kein Video aktiviert ist. Wenn Sie die Maus über ein Vorschaubild in der Galerie bewegen, wird auch das Foto mit hoher Auflösung angezeigt.

</div>

<div>

## <a name="user-photos-in-lync-2010"></a>Benutzer Fotos in lync 2010

Im lync 2010-Client können Sie zwischen zwei Optionen auswählen, um ein Foto für Ihr Profil, ein **standardmäßiges Unternehmensbild** und **ein Bild von einer Webadresse**anzuzeigen.

<div>

## <a name="default-corporate-picture"></a>Standardbild für Unternehmen

Wenn Sie die Standardoption " **Unternehmensbild** " auswählen, erhält lync das für Sie angezeigte Foto aus Active Directory-Domänendienste. Das verwendete Bild ist das Bild, das als Wert für das **thumbnailPhoto** -Attribut in Active Directory-Domänendienste definiert ist. Dies ist die gleiche Datei, die von Exchange zum Anzeigen von Bildern in Outlook verwendet wird.

Überlegungen zur Verwendung von Bildern aus Active Directory-Domänendienste umfassen Folgendes:

  - Es werden nur Bilder mit einer Größe von bis zu 96 Pixeln von 96 Pixel unterstützt. Die Dateigröße für das Bild ist auf 100 KB limitiert.

  - Standardmäßig können Benutzer das für das **thumbnailPhoto** -Attribut verwendete Bild ändern, jedoch nicht direkt über den lync-Client. Sie können dies über Active Directory-Domänendienste deaktivieren.

  - In Active Directory-Domänendienste gespeicherte Bilder werden nicht für Kontakte außerhalb Ihrer Organisation angezeigt, auch wenn es sich um Verbund Kontakte handelt.

  - In großen Organisationen kann das Speichern und Abrufen der Bilder für eine große Anzahl von Benutzern Auswirkungen auf die Größe und Leistung der Active Directory-Domänendienste Datenbank haben.

  - Die begrenzten Bildabmessungen und die Dateigröße bedeuten, dass nur Bilder mit niedriger Auflösung verwendet werden können.

<div>

## <a name="how-users-manage-their-user-photos-in-active-directory-domain-services"></a>So verwalten Benutzer Ihre Benutzer Fotos in Active Directory-Domänendienste

Der Benutzer kann das im Active Directory-Domänendienste Profil verwendete Bild nicht direkt über lync 2010-Client ändern. Sie können eine der folgenden Optionen verwenden, falls verfügbar:

  - **SharePoint Server**   Benutzer können ein Foto auf einem SharePoint Server in "Meine Website" hochladen und dann die [Profilsynchronisierung in SharePoint konfigurieren](https://go.microsoft.com/fwlink/p/?linkid=507466) , um das Foto mit dem **thumbnailPhoto** -Attribut in Active Directory-Domänendienste zu synchronisieren.

  - **Auf öffentlich zugänglichen URLs**   gespeicherte Fotos können Benutzer Fotos konfigurieren, die eine öffentlich zugängliche URL für das Bild angeben, das Sie verwenden möchten. Das Bild muss ohne Kennwort öffentlich zugänglich sein. Das Bild, das in der angegebenen Webadresse gespeichert ist, wird über die Visitenkarten Kategorie in den Anwesenheitsinformationen an andere Benutzer übertragen. Wenn der lync-Client ein Benutzer Foto anzeigen muss, ruft es das Bild aus der angegebenen Webadresse ab.

  - **Exchange 2010-Cmdlets für Windows PowerShell**   Administratoren können das Cmdlet [Import-RecipientDataProperty](https://go.microsoft.com/fwlink/p/?linkid=507468) in der Exchange 2010 Verwaltungsshell in ausführen, um das **thumbnailPhoto** -Attribut zu verwalten. Wenn Bilder mit Exchange 2010-Cmdlets importiert werden, ist die Dateigröße auf 10 KB limitiert.

  - **Drittanbietertools**   Benutzer können nur Ihr eigenes Foto für das **thumbnailPhoto** -Attribut hochladen.

</div>

</div>

<div>

## <a name="show-a-picture-from-a-web-address"></a>Anzeigen eines Bilds aus einer Webadresse

Wenn Sie die Option **Bild aus einer Webadresse anzeigen** auswählen, ruft lync das Bild an der von Ihnen eingegebenen Adresse ab und zeigt es für Ihr Benutzer Foto in lync an.

Überlegungen zur Verwendung von Bildern aus einer Webadresse umfassen Folgendes:

  - Die Dateigrößenbeschränkungen werden durch das **MaxPhotoSizeKB** -Attribut in der Clientrichtlinie bestimmt, das mit dem Cmdlet [New-CsClientPolicy](https://go.microsoft.com/fwlink/p/?linkid=507463) definiert ist. Die Standardgrößenbeschränkung beträgt 30 KB. Der Höchstwert ist 100 KB. Es gibt keine Einschränkung für die Auflösung des Bilds, aber wenn Sie versuchen, eine Image-Datei zu verwenden, die die Größenbeschränkung überschreitet, wird Sie nicht auf lync-Clients heruntergeladen. Sie können den Wert auf 0 festlegen, um zu verhindern, dass alle Benutzer Fotos in lync verwendet werden.

  - Benutzer Fotos aus einer Webadresse können von externen verbundkontakten angezeigt werden.

</div>

<div>

## <a name="managing-users-photo-with-client-policy-cmdlets"></a>Verwalten des Fotos eines Benutzers mit Client Richtlinien-Cmdlets

In lync Server 2010 werden die Clientrichtlinien Einstellungen mit den CsClientPolicy-Cmdlets konfiguriert. Die konfigurierten Richtlinieneinstellungen werden über die in-Band-Konfiguration an Clients gesendet. Die beiden Parameter der CsClientPolicy-Cmdlets, die die Benutzer Fotodarstellung bestimmen, sind **DisplayPhoto** und **MaxPhotoSizeKB**. Der entsprechende Parameter für die in-Band-Provision für **DisplayPhoto** und **MaxPhotoSizeKB** hat den Namen " **fotousage**". Werte für den Parameter " **fotousage** " werden über die **endpointConfiguration** **provisionarygroup**an Clients gesendet. Weitere Informationen finden Sie unter [Übersicht über Client Richtlinien und-Einstellungen](https://go.microsoft.com/fwlink/?linkid=507470) .

Der Wert des **DisplayPhoto** -Parameters bestimmt die Quelle des Foto Bilds des Benutzers. Die unterstützten Werte sind in der folgenden Tabelle enthalten.


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
<th>Lync 2010 Clienteinstellungen</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>NoPhoto</p></td>
<td><p>none</p></td>
<td><p><strong>Mein Bild nicht anzeigen</strong></p></td>
</tr>
<tr class="even">
<td><p>PhotoFromADOnly</p></td>
<td><p>Active Directory Domain Services</p></td>
<td><p><strong>Standardbild für Unternehmen</strong></p></td>
</tr>
<tr class="odd">
<td><p>AllPhotos</p></td>
<td><p>Webadresse</p></td>
<td><p><strong>Anzeigen eines Bilds aus einer Webadresse</strong></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="how-lync-2010-client-gets-photos"></a>So erhält lync 2010 Client Fotos

In lync 2010 werden Benutzer Fotos vom Adressbuchdienst auf dem Server verwaltet. Der lync-Client ruft Benutzer Fotos ab, indem er zuerst den Adressbuch-Webabfrage Dienst (ABWQ) auf dem Server abfragt, der über den Webdienst für die Verteilerlistenerweiterung verfügbar gemacht wird. Der Client empfängt die Bilddatei und kopiert Sie dann in den Cache des Benutzers, um zu vermeiden, dass das Bild jedes mal heruntergeladen wird, wenn es angezeigt werden muss. Die von der Abfrage zurückgegebenen Attributwerte werden auch im zwischengespeicherten Adressbuchdienst Eintrag für den Benutzer gespeichert. Der Adressbuchdienst löscht alle zwischengespeicherten Bilder alle 24 Stunden, was bedeutet, dass es bis zu 24 Stunden dauern kann, bis neue Benutzer Bilder im Cache auf dem Server aktualisiert werden. Sie können eine Aktualisierung des Caches mit dem Cmdlet [Update-CsAddressBook](https://docs.microsoft.com/powershell/module/skype/Update-CsAddressBook) erzwingen.

Im Anwesenheitsstatus enthaltene Benutzer Fotos weisen ebenfalls einen Hashwert auf, mit dem der lync-Client ermittelt, ob ein neueres Bild verfügbar ist. Der Client wird automatisch über Änderungen an der Bild Datei benachrichtigt, die im Anwesenheitsstatus verwendet wird.

<div class=" ">


> [!NOTE]  
> Da Fotos nicht in der GalContacts. DB-Datenbank gespeichert sind, hängt das Herunterladen von Benutzer Fotos nicht von der <STRONG>AddressBookAvailability</STRONG> -Einstellung in der Clientrichtlinie ("<A href="https://go.microsoft.com/fwlink/p/?linkid=507508">CsClientPolicy</A>") ab.



</div>

Die Abfrage an den ABWQ-Dienst umfasst die folgenden Attribute:

  - **Photo Hash**   der Hashwert der binären Fotodaten und wird verwendet, um zu bestimmen, ob das aktuelle Foto geändert wurde.

  - **PhotoRelPath**   der relative Pfad zu der auf dem Server gespeicherten Abbilddatei.

  - **Die Größe der**Bilddatei wird in Bytes abbildet.   

  - **Timestamp**   das Datum und die Uhrzeit, zu der die Bilddatei zuletzt vom Server heruntergeladen und in den Clientcache kopiert wurde.

Als nächstes vergleicht lync 2010-Client die von der Abfrage zurückgegebenen Attributwerte mit den vom Client von der in-Band-Bereitstellung empfangenen Attributwerten, um zu sehen, ob Sie unterschiedlich sind, nachdem die Abbilddatei abgerufen wurde. Wenn die Werte unterschiedlich sind, ruft der Client die Bilddatei des angemeldeten Benutzers mit einer HTTP GET-Anforderung ab.

Darüber hinaus prüft der Client alle 24 Stunden ab dem Zeitpunkt, zu dem die zwischengespeicherte Version der Bilddatei erstellt wurde, den Server, um den Wert des Foto **Hash** Attributs auf dem Server mit dem Wert auf dem Client zu vergleichen. Wenn die Werte unterschiedlich sind, weiß der Client, dass die Bilddatei geändert wurde. Um die aktualisierte Bilddatei zu erhalten, fragt der Client den ABWQ-Dienst erneut ab, um die Bilddatei im Clientcache mit der Abbilddatei auf dem Server zu aktualisieren, wodurch auch der **Zeitstempel** für die Datei im Clientcache zurückgesetzt wird.

Im folgenden finden Sie eine Beispielantwort auf eine Abfrage an den ABWQ-Dienst:
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

Lync 2013 wurde die Unterstützung für hochauflösende Bilder für Benutzer Fotos eingeführt. Lync 2013 enthält auch Unterstützung für das Speichern von Benutzer Fotos im Postfach des Benutzers auf Exchange 2013, wodurch die in lync 2010 vorhandenen Bildauflösungen und Größenbeschränkungen entfernt werden. Benutzer Fotos in lync 2013 können bis zu 648 Pixel von 648 Pixel mit einer Dateigröße von bis zu 20 MB sein. Hochauflösende Fotos in lync 2013 müssen sich im Postfach des Benutzers auf Exchange 2013 befinden und nur mit lync 2013-Client unterstützt werden. Diese Integration in Exchange nutzt das neue Autorisierungsframework, das in den 2013-Versionen von lync, Exchange und SharePoint mit dem Namen OAuth enthalten ist.

Wenn Exchange 2013 nicht in Ihrer Bereitstellung verwendet wird, ist die Unterstützung für Benutzer Fotos identisch mit lync 2010. Die Benutzeroptionen zum Auswählen des zu verwendenden Fotos unterscheiden sich jedoch in lync 2013-Client. In lync 2013-Client können Benutzer entweder " **mein Bild verbergen** " oder " **eigenes Bild anzeigen**" auswählen. Die Option **Bild von einer Website anzeigen** ist standardmäßig nicht verfügbar, kann jedoch durch Zuweisen einer Clientrichtlinie aktiviert werden.

<div>

## <a name="hide-my-picture"></a>Mein Bild ausblenden

Einstellungen für Benutzer Fotos befinden sich im Dialogfeld **Optionen** in lync 2013. Wenn Sie " **mein Bild ausblenden**" auswählen, wird im lync-Client kein Benutzer Foto angezeigt, das Foto wird jedoch weiterhin auf Ihrer Visitenkarte und außerhalb von lync angezeigt.

</div>

<div>

## <a name="show-my-picture"></a>Mein Bild anzeigen

Wenn Sie die Option " **eigenes Bild anzeigen** " auswählen, wird das Benutzer Foto in Ihrem lync-Client und anderen Benutzern in lync-Unterhaltungen angezeigt. Das verwendete Bild ist diejenige, die in AD DS gespeichert ist.

</div>

<div>

## <a name="show-a-picture-from-a-website"></a>Anzeigen eines Bilds von einer Website

Die Option **Bild aus einer Website anzeigen** wird in lync 2013 verfügbar, nachdem eine Clientrichtlinie festgelegt wurde, um Sie zu aktivieren. Die Client Version muss neuer sein als 15.0.4535.1002, die mit den lync- [kumulativen Updates installiert wird: November 2013](https://go.microsoft.com/fwlink/p/?linkid=509908). Benutzer müssen sich möglicherweise abmelden und wieder einloggen, um die Änderungen im Client anzuzeigen.

Sie können festlegen, dass für die Clientrichtlinie das **Anzeigen von Bildern aus einer Website** Einstellung aktiviert wird, indem Sie die Richtlinie " [CsClientPolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsClientPolicy) " im lync Server-Verwaltungsshell festlegen. Die folgenden Beispiel-Cmdlets veranschaulichen, wie die Richtlinie für alle Benutzer in Ihrer Bereitstellung global festgelegt wird:

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


Wenn ein Bild in das Postfach des Benutzers hochgeladen wird, erstellt Exchange automatisch eine Version mit niedrigerer Auflösung des Bilds, die in Clientanwendungen verwendet werden kann. Das Benutzer Foto wird auch in AD DS aktualisiert.

<div class=" ">


> [!NOTE]  
> Wenn eine Bilddatei in AD DS aktualisiert wird, wird ein 48 x 48 Pixel Bild erstellt und für die thumbnailPhoto in AD DS verwendet. Jedes vorhandene Bild wird ersetzt. Wenn Sie also AD DS ein 96 x 96-Bild hinzugefügt haben, wird es mit dem neuen 48 x 48-Bild überschrieben. Dies ist nur wichtig, wenn Sie über Benutzer in Ihrer Umgebung verfügen, die lync 2010-Clients verwenden, da diese Clients Benutzer Fotos von AD DS erhalten. Sie können 96 x 96 Pixelbilder importieren, um diejenigen zu ersetzen, die von AD DS erstellt wurden, wenn Sie lync 2010-Clients in Ihrer Organisation haben.



</div>

</div>

<div>

## <a name="user-photo-support-in-lync-2013"></a>Unterstützung für Benutzer Fotos in lync 2013

In lync 2013 werden drei Bildauflösungen für Benutzer Fotos unterstützt, wie in der folgenden Tabelle beschrieben. Das verwendete Bild wird durch die Clientrichtlinien Einstellung bestimmt, die lync-Benutzern zugewiesen ist. Weitere Informationen finden Sie unter "Verwalten von Benutzer Fotos mit Client Richtlinien-Cmdlets" in diesem Thema.


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
<td><p>Wird verwendet, wenn kein Bild mit höherer Auflösung ausgewählt ist</p></td>
</tr>
<tr class="even">
<td><p>96 x 96</p></td>
<td><p>Wird in Outlook Web App und Outlook 2013 verwendet</p></td>
</tr>
<tr class="odd">
<td><p>648 x 648</p></td>
<td><p>Wird in lync 2013-Desktop Client und lync 2013-Webanwendung verwendet</p></td>
</tr>
</tbody>
</table>


Jeder Benutzer mit einem in Exchange 2013 aktivierten Postfach kann ein anderes Bild, einschließlich hochauflösender Fotos, über Outlook Web Access oder lync 2013 Clientoptionen hochladen. Die empfohlenen Einstellungen für verwendete Bilder umfassen Folgendes:

  - **Bildauflösung**   648 von 648 Pixel

  - **Farbtiefe**   24-Bit

  - **Bilddateigröße**   bis zu 20 MB

  - **Dateiformat**   JPEG

Ein typisches 24-Bit-JPEG-Bild mit 648 Pixeln von 648 Pixel weist eine Dateigröße von etwa 240 KB auf, daher sind 1 MB Speicherplatz für alle 4 Benutzer Fotos erforderlich.

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

