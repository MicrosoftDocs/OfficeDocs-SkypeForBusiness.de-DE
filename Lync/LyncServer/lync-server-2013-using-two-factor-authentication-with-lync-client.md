---
title: 'Lync Server 2013: Verwenden der zweistufigen Authentifizierung mit lync-Client'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Using two-factor authentication with Lync client
ms:assetid: d4136e61-c3ab-4b26-85c8-c1b2c24f5ee3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn338071(v=OCS.15)
ms:contentKeyID: 55115593
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5af9e9b5268fd218bfe5856473124514cfe34945
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34847302"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="using-two-factor-authentication-with-lync-client-and-lync-server-2013"></a>Verwenden der zweistufigen Authentifizierung mit lync-Client und lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2013-07-11_

In diesem Thema wurde beschrieben, wie Sie die zweistufige Authentifizierung mit lync 2013-Client nutzen können.

<div>

## <a name="sign-in-to-lync-2013-for-the-first-time"></a>Erstmaliges Anmelden bei lync 2013

Ihre lync-Anmeldeinformationen werden in der Regel automatisch konfiguriert, wenn lync 2013 installiert ist. Wenn Sie lync zum ersten Mal verwenden, müssen Sie den Client möglicherweise manuell starten.

**So können Sie sich zum ersten Mal bei lync anmelden**

1.  Melden Sie sich beim Netzwerk Ihrer Organisation an.

2.  Wählen Sie **Alle Programme** \> **starten** \> **Microsoft \> lync lync 2013**aus.
    
    Der Anmeldebildschirm von lync sollte angezeigt werden.
    
      - Wenn das Feld mit der Anmeldeadresse bereits ausgefüllt ist, überprüfen Sie, ob die angezeigte Adresse richtig ist.
    
      - Wenn dies nicht der Fall ist, oder wenn das Feld leer ist, geben Sie Ihre lync-Anmeldeadresse ein (Dies ist in der Regel identisch mit Ihrer e-Mail-Adresse).
    
      - Wenn ein leeres Kennwortfeld angezeigt wird, geben Sie Ihr Kennwort ein.

3.  Wählen Sie **Anmelden** aus.

</div>

<div>

## <a name="sign-out-of-lync"></a>Abmelden bei lync

Wenn Sie mit der Verwendung von lync fertig sind, können Sie die Anzeige schließen, sich von Ihrer Sitzung abmelden oder das Programm beenden, und zwar alle über das Menü "Datei". In der folgenden Tabelle werden die Unterschiede zwischen diesen Optionen erläutert.


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Option</th>
<th>Zweck</th>
<th>Vorgehensweise</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Schließen</p></td>
<td><p>Schließt die lync-Anzeige, lässt aber die lync-Sitzung, die mit Ihrer Benutzer-ID identifiziert wurde, weiterhin ausgeführt werden. Dies hat den Sinn, dass Sie weiterhin Benachrichtigungen erhalten und sich mit anderen austauschen können.</p>
<p>Sie können die Anzeige jederzeit wiederherstellen, indem Sie auf das lync-Symbol in der Taskleiste oder im Infobereich am unteren Rand des Bildschirms klicken.</p></td>
<td><p>Führen Sie im lync-Hauptfenster eine der folgenden Aktionen aus:</p>
<ol>
<li><p>Wählen Sie die Schaltfläche <strong>Optionen</strong> und dann <strong>Datei</strong> &gt; <strong>Schließen</strong>aus.</p></li>
<li><p>Klicken Sie auf die Schaltfläche <strong>Schließen</strong> (X) in der oberen rechten Ecke des Fensters.</p></li>
</ol></td>
</tr>
<tr class="even">
<td><p>Abmelden</p></td>
<td><p>Beendet die mit Ihrer Benutzer-ID verknüpfte lync-Sitzung, während lync weiterhin im Hintergrund ausgeführt wird. Wenn Sie sich abmelden, wird das Abmeldefenster angezeigt.</p>
<div>

> [!TIP]  
> Wählen Sie bei der Abmeldung <STRONG>Meine Anmeldeinformationen löschen</STRONG> aus, um den Datensatz mit Ihrer Anmelde-ID und dem Kennwort vom Computer zu entfernen. Dies vereinfacht möglicherweise den Support bei der Behandlung von Anmeldeproblemen. Außerdem trägt es dazu bei, Ihre Anmeldeinformationen zu sichern, da es nicht autorisierten Benutzern so erschwert wird, sich mit Ihren Anmeldeinformationen anzumelden.


</div></td>
<td><p>Klicken Sie im Hauptfenster von lync auf die Schaltfläche <strong>Optionen</strong> , und wählen Sie dann <strong>Datei</strong> &gt; <strong>Abmelden aus</strong>.</p></td>
</tr>
<tr class="odd">
<td><p>Beenden</p></td>
<td><p>Beendet die lync-Sitzung und beendet lync auf Ihrem Computer. Wenn Sie lync nach dem Beenden erneut starten möchten, wählen Sie <strong></strong> &gt; <strong>Alle Programme</strong> &gt; starten <strong>Microsoft lync</strong> &gt; <strong>lync 2013</strong>aus.</p></td>
<td><p>Klicken Sie im Hauptfenster von lync auf die Schaltfläche <strong>Optionen</strong> , und wählen Sie dann <strong>Datei</strong> &gt; <strong>Beenden</strong>aus.</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="sign-in-to-lync-with-a-smart-card"></a>Anmelden bei lync mit einer Smartcard

Einige Organisationen verwenden jetzt einen mehrstufigen Anmeldeprozess mit der Bezeichnung zweistufige Authentifizierung, um die Sicherheit für Ihre lync 2013-Benutzer zu erhöhen. Wenn Sie davon ausgehen, dass Sie diese Option verwenden, benötigen Sie eine "Smartcard", um sich bei lync anzumeldet. Smartcards sind in zwei Varianten erhältlich:

  - **Physische**   Informationen über die Größe einer Kreditkarte. Sie setzen sie für die Anmeldung in ein SmartCard-Lesegerät ein.

  - **Virtual**   kein physikalisches Objekt, sondern ein elektronischer Bezeichner, der auf einen speziellen Chip auf dem Computer geschrieben wird, der im Wesentlichen die Smartcard auf Ihren Computer aufbaut. Nur für die Verwendung mit Windows 8-Computern verfügbar, die den TPM-Chip (Trusted Platform Module) enthalten.

<div>

## <a name="enroll-your-smart-card"></a>Registrieren Ihrer SmartCard

Bevor Sie sich mit einer SmartCard anmelden können, muss die Karte „registriert“ werden – das bedeutet, dass Ihre Benutzeranmeldeinformationen für die Karte kenntlich gemacht werden müssen. Dies muss unabhängig davon erfolgen, ob es sich um eine physische oder um eine virtuelle Karte handelt. Dieser Vorgang wurde möglicherweise bereits vom lync Server-Administrator durchgeführt. Erkundigen Sie sich bei ihm, wenn Sie nicht sicher sind, ob dieser Vorgang bereits ausgeführt wurde.

<div>


> [!NOTE]  
> Da jede virtuelle Smartcard nur dem Gerät zugeordnet ist, auf dem Sie installiert ist, muss für jeden Windows 8-Computer, den Sie verwenden, eine separate Karte registriert werden.



</div>

**So registrieren Sie Ihre SmartCard**

1.  Melden Sie sich bei dem Computer an, auf dem Sie lync ausführen werden.

2.  Navigieren Sie im Internet Explorer zur Registrierungsseite der Zertifizierungsstelle Ihrer Organisation.
    
    Bitten Sie Ihren lync Server-Administrator um die Webadresse dieser Ressource, wenn Sie Sie nicht bereits haben. Die URL sieht ungefähr wie folgt aus: https://MyCA.\[YourCompanyName\]. com/certsrv.
    
    <div>
    

    > [!NOTE]  
    > Wenn Sie Internet Explorer 10 verwenden, müssen Sie diese Website möglicherweise im Kompatibilitätsmodus anzeigen.

    
    </div>

3.  Wenn Sie aufgefordert werden, sich auf der Zertifizierungsseite anzumelden, melden Sie sich mit Ihrem Domänenkonto (statt als Administrator Ihres Computers) an.

4.  Wählen Sie auf der Begrüßungsseite die Option **Zertifikat anfordern** aus.

5.  Wählen Sie **Erweiterte Anforderung** aus.

6.  Wählen Sie **Eine Anforderung an diese Zertifizierungsstelle erstellen und einreichen** und klicken Sie dann auf **Weiter**.

7.  Jetzt wird eine Seite mit dem Titel SmartCard-Registrierungsstelle angezeigt. Genehmigen Sie die Anfrage, das ActiveX-Steuerelement zu installieren, und füllen Sie dann das Formular für die erweiterte Zertifikatanforderung wie folgt aus:
    
    1.  Wählen Sie in der Dropdownliste **Zertifikatvorlage** den Eintrag **SmartCard-Benutzer** aus.
    
    2.  Wählen Sie **Neuen Schlüsselsatz erstellen** aus.
    
    3.  Suchen Sie die Herstellerinformationen auf dem Etikett Ihrer SmartCard und wählen Sie dann den betreffenden Hersteller in der **CSP**-Dropdownliste aus.
    
    4.  Wählen Sie **CSP** als Anforderungsformat aus, wenn dies noch nicht ausgewählt ist.
    
    5.  Wählen Sie in der Hashalgorithmus-Dropdownliste den Eintrag **sha1** aus, wenn er noch nicht ausgewählt ist.
    
    6.  Geben Sie Ihrem Zertifikat einen Namen, den Sie sich merken können und klicken Sie dann auf **Senden**.

8.  Legen Sie jetzt Ihre leere SmartCard in das an die Registrierungsstelle angeschlossene SmartCard-Lesegerät und klicken Sie auf **Registrieren**.

9.  Wenn Sie dazu aufgefordert werden, geben Sie Ihre PIN (Personal Identification Number) ein und klicken Sie dann auf **OK**.
    
    <div>
    

    > [!NOTE]  
    > Wenn der für Sie zuständige Mitarbeiter des technischen Supports Ihnen keine besondere PIN für die Registrierung Ihrer SmartCard gegeben hat, verwenden Sie die Standard-PIN für SmartCards, nämlich 12345678.

    
    </div>

10. Aktivieren Sie die Option, die den Benutzer (Sie) zwingt, die PIN bei der ersten Verwendung der SmartCard zu ändern.

11. Legen Sie jetzt Ihre leere SmartCard in das an die Registrierungsstelle angeschlossene SmartCard-Lesegerät und klicken Sie auf **Registrieren**.

12. Wenn Sie dazu aufgefordert werden, geben Sie Ihre PIN (Personal Identification Number) ein und klicken Sie dann auf **OK**.
    
    <div>
    

    > [!NOTE]  
    > Wenn der für Sie zuständige Mitarbeiter des technischen Supports Ihnen keine besondere PIN für die Registrierung Ihrer SmartCard gegeben hat, verwenden Sie die Standard-PIN für SmartCards, nämlich 12345678.

    
    </div>

13. Aktivieren Sie die Option, die den Benutzer (Sie) zwingt, die PIN bei der ersten Verwendung der SmartCard zu ändern.

14. Klicken Sie auf **OK**, um zu bestätigen, dass das angezeigte Zertifikat Ihre Informationen enthält.

15. Sobald der Hinweis angezeigt wird, dass das Zertifikat ausgestellt wurde, klicken Sie auf **Dieses Zertifikat installieren**, um den Registrierungsvorgang abzuschließen.

</div>

<div>

## <a name="sign-in-to-lync-with-your-smart-card-credentials"></a>Melden Sie sich mit ihren Smartcard-Anmeldeinformationen bei lync an.

Bevor Sie Ihre Smartcard zum ersten Mal verwenden, sollten Sie auf der lync-Anmeldeseite auf **Meine Anmeldeinformationen löschen** klicken. Dadurch werden alle eventuell auf dem Computer gespeicherten Anmeldeinformationen gelöscht und eine mögliche Fehlerquelle ausgeschaltet.

**So melden Sie sich mit ihren Smartcard-Anmeldeinformationen bei lync an**

1.  Starten Sie den lync-Client.

2.  Geben Sie auf dem Anmeldebildschirm Ihren Benutzerkontonamen für die Anmeldung im Feld **Anmeldeadresse** ein und klicken Sie dann auf **Anmelden**.

3.  Wenn Sie eine virtuelle SmartCard verwenden, überspringen Sie diesen Schritt.
    
    Wenn Sie eine physische SmartCard verwenden, legen Sie die SmartCard in Ihr SmartCard-Lesegerät ein, wenn Sie dazu aufgefordert werden, und klicken dann auf **OK**, wenn die Karte erkannt wird.

4.  Geben Sie die PIN-Nummer für Ihre SmartCard ein und klicken Sie dann auf **OK**.
    
    <div>
    

    > [!NOTE]  
    > Wenn Ihnen keine SmartCard-PIN von Ihrem Supportmitarbeiter zugewiesen wurde, verwenden Sie den Standardwert, nämlich 12345678.

    
    </div>

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

