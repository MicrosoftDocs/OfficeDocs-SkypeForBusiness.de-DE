---
title: Definieren und Konfigurieren eines Front-End-Pools oder Standard Edition-Servers
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Define and configure a Front End pool or Standard Edition server
ms:assetid: 713fc263-23dd-414a-b001-82932e4fe966
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398538(v=OCS.15)
ms:contentKeyID: 48184457
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ddc430370c59e279e0e36aa662da0f33973e0d80
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41762763"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="define-and-configure-a-front-end-pool-or-standard-edition-server-in-lync-server-2013"></a>Definieren und Konfigurieren eines Front-End-Pools oder Standard Edition-Servers in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2013-03-08_

Für dieses Verfahren ist keine Mitgliedschaft in einem lokalen Administrator oder einer privilegierten Domänengruppe erforderlich. Melden Sie sich als Standardbenutzer an einem Computer an.

Wenn Sie einen Enterprise-Server bereitstellen, muss immer eine Mindestanzahl an Front-End-Servern in einem Pool ausgeführt werden. In der folgenden Tabelle werden diese Anforderungen zusammengefasst.


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Gesamtzahl der Front-End-Server im Pool</th>
<th>Anzahl der Server, die aktiv sein müssen, damit der Pool funktioniert</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>1-2</p></td>
<td><p>1</p></td>
</tr>
<tr class="even">
<td><p>3-4</p></td>
<td><p>2</p></td>
</tr>
<tr class="odd">
<td><p>5-6</p></td>
<td><p>3</p></td>
</tr>
<tr class="even">
<td><p>7-8</p></td>
<td><p>4</p></td>
</tr>
<tr class="odd">
<td><p>9-10</p></td>
<td><p>5</p></td>
</tr>
<tr class="even">
<td><p>11-12</p></td>
<td><p>6</p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]
> Bei lync Server 2013 müssen Sie jedes Mal, wenn Sie einen Front-End-Server aus dem Pool hinzufügen oder entfernen, Dienste neu starten. Das Entfernen und Hinzufügen von Servern sollte als separate Vorgänge erfolgen. Wenn Sie beispielsweise zwei Front-End-Server hinzufügen und zwei Front-End-Server entfernen möchten, verwenden Sie den folgenden Prozess: 
> <OL>
> <LI>
> <P>Entfernen Sie die beiden Front-End-Server.</P>
> <LI>
> <P>Veröffentlichen Sie die Topologie, und aktivieren Sie Sie erneut.</P>
> <LI>
> <P>Starten Sie die Dienste neu</P>
> <LI>
> <P>Fügen Sie die beiden Front-End-Server hinzu.</P>
> <LI>
> <P>Veröffentlichen Sie die Topologie, und aktivieren Sie Sie erneut.</P>
> <LI>
> <P>Starten Sie die Dienste neu.</P></LI></OL>



</div>

Nachdem Sie Ihre Topologie definiert haben, gehen Sie wie folgt vor, um einen Front-End-Pool für Ihre Website zu definieren. Details zum Definieren der Topologie finden Sie unter [definieren und Konfigurieren einer Topologie im Topologie-Generator für lync Server 2013](lync-server-2013-define-and-configure-a-topology-in-topology-builder.md).

<div>

## <a name="to-define-a-front-end-pool"></a>So definieren Sie einen Front-End-Pool

1.  Klicken Sie im Assistenten zum Definieren eines neuen Front-End-Pools auf der Seite **Neues Front-End-Pool definieren** auf **weiter**.

2.  Geben Sie auf der Seite **FQDN des Front-End-Pools definieren** einen vollqualifizierten Domänennamen (Fully Qualified Domain Name, FQDN) für den zu erstellenden Pool ein, klicken Sie auf **Enterprise Edition-Front-End-Pool**, und klicken Sie dann auf **weiter**

3.  Geben Sie auf der Seite **Computer auf diesem Pool definieren** einen Computer-FQDN für den ersten Front-End-Server im Pool ein, und klicken Sie dann auf **Hinzufügen**. Wiederholen Sie diesen Schritt für alle weiteren Computer (bis zu zwölf), die Sie dem Pool hinzufügen möchten, und klicken Sie dann auf **weiter**.

4.  Aktivieren Sie auf der Seite **Features auswählen** die Kontrollkästchen für die Features, die in diesem Front-End-Pool angezeigt werden sollen. Wenn Sie beispielsweise nur Chat-und Anwesenheitsfeatures bereitstellen, aktivieren Sie das Kontrollkästchen **Konferenz Konferenzen** , um die mehrteilige Chatfunktion zuzulassen, aber nicht die Kontrollkästchen **Einwahl (PSTN) Conferencing**, **Enterprise Voice**oder **Anrufsteuerung** zu aktivieren, da Sie die Features für sprach-, Video-und kollaborative Konferenzen darstellen.
    
      - **Konferenzen**   diese Auswahl bietet eine Reihe von Funktionen, einschließlich:
        
          - Chatten mit mehr als zwei Teilnehmer in einer Chatsitzung.
        
          - Konferenz, die Zusammenarbeit in Dokumenten, Anwendungsfreigabe und Desktopfreigabe umfasst.
        
          - A/v-Konferenzen, mit denen Benutzer in Echtzeit Audio/Video-Konferenzen (a/v) führen können, ohne externe Dienste wie den Live Meeting-Dienst oder eine Audio-Bridge eines Drittanbieters zu benötigen.
    
      - **Durch Einwahlkonferenzen**   (PSTN) können Benutzer an einem Audioteil einer lync Server 2013-Konferenz teilnehmen, indem Sie ein PSTN-Telefon (Public Switched Telephone Network) verwenden, ohne einen Audiokonferenz-Anbieter zu benötigen.
    
      - **Enterprise Voice**   Enterprise-VoIP ist die VoIP-Lösung (Voice over IP) in lync Server 2013, mit der Benutzer Telefonanrufe tätigen und empfangen können. Sie würden dieses Feature bereitstellen, wenn Sie beabsichtigen, lync Server 2013 für Sprachanrufe, Voicemail und andere Funktionen zu verwenden, die ein Hardwaregerät oder einen Software Client verwenden.
    
      - **Anrufannahme Steuerung (CAC)**   CAC ermittelt basierend auf der verfügbaren Netzwerkbandbreite, ob Echt Zeit Kommunikationssitzungen wie Sprach-oder Videoanrufe eingerichtet werden können. Wenn Sie nur Chat und Anwesenheit bereitgestellt haben, ist CAC nicht erforderlich, da keine dieser beiden Features CAC verwendet.
    
      - **Die Archivierungs**   Archivierung bietet eine Möglichkeit zum Archivieren von Chat Inhalten, Konferenz (Besprechungs-) Inhalten oder beidem, die über lync Server 2013 gesendet werden.
    
      - **Mit Monitoring**   Server können Sie numerische Daten erfassen, die die Medienqualität in Ihrem Netzwerk und Endpunkten beschreiben, Nutzungsinformationen zu VoIP-Anrufen, Chatnachrichten, A/V-Unterhaltungen, Besprechungen, Anwendungsfreigabe und Dateiübertragungen sowie Anruf Fehler und Informationen zur Problembehandlung bei fehlgeschlagenen anrufen.
    
    <div>
    

    > [!NOTE]
    > Wenn Sie CAC in Ihrer Bereitstellung aktivieren möchten, müssen Sie CAC in genau einem Pool pro zentralen Standort aktivieren. CAC wird empfohlen, wenn Sie Sprachfeatures oder A/V-Konferenzen bereitstellen.

    
    </div>
    
    In der folgenden Tabelle sind die verfügbaren Funktionen (oben) und die den Benutzern angebotenen Funktionen (links) aufgeführt. Die Auswahl in der Tabelle ist das, was Sie auswählen sollten, um diese Features für Ihre Organisation zu aktivieren.
    
    
    <table>
    <colgroup>
    <col style="width: 20%" />
    <col style="width: 20%" />
    <col style="width: 20%" />
    <col style="width: 20%" />
    <col style="width: 20%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th></th>
    <th>Konferenzen</th>
    <th>Einwahlkonferenzen</th>
    <th>Enterprise-VoIP</th>
    <th>Anrufsteuerung</th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p>Chat und Anwesenheit</p></td>
    <td><p>X</p></td>
    <td></td>
    <td></td>
    <td></td>
    </tr>
    <tr class="even">
    <td><p>Konferenzen</p></td>
    <td><p>X</p></td>
    <td><p>X</p></td>
    <td></td>
    <td></td>
    </tr>
    <tr class="odd">
    <td><p>A/V-Konferenzen</p></td>
    <td><p>X</p></td>
    <td><p>X</p></td>
    <td></td>
    <td><p>X</p></td>
    </tr>
    <tr class="even">
    <td><p>Enterprise-VoIP</p></td>
    <td></td>
    <td></td>
    <td><p>X</p></td>
    <td><p>X</p></td>
    </tr>
    </tbody>
    </table>


5.  Auf der Seite **"Serverrollen auswählen** " können Sie den Vermittlungsserver auf dem Front-End-Server collocate oder als eigenständigen Server bereitstellen.
    
    Sie können den Vermittlungs Server im Front-End-Pool collocate.
    
      - Wenn Sie beabsichtigen, den Vermittlungs Server im Front-End-Pool der Enterprise Edition collocate, stellen Sie sicher, dass das Kontrollkästchen aktiviert ist. Die Serverrolle wird auf den Servern im Pool bereitgestellt.
    
      - Wenn Sie den Vermittlungsserver als eigenständigen Server bereitstellen möchten, deaktivieren Sie das entsprechende Kontrollkästchen. Nachdem Sie den Front-End-Server vollständig bereitgestellt haben, werden Sie den Vermittlungsserver in einem separaten Bereitstellungsschritt bereitstellen.
    
    <div>
    

    > [!NOTE]
    > Wir empfehlen, dass Sie den Vermittlungs Server nach Möglichkeit collocate. Ausführliche Informationen zur Unterstützung für sich selbst oder eigenständige Vermittlungsserver finden Sie unter <A href="lync-server-2013-components-and-topologies-for-mediation-server.md">Komponenten und Topologien für Mediation Server in lync Server 2013</A> in der Planungsdokumentation.

    
    </div>

6.  Mit der Seite **Serverrollen mit diesem Front-End-Pool verknüpfen** können Sie Serverrollen mit dem Front-End-Pool definieren und zuordnen. Die folgende Rolle ist verfügbar:
    
    **Aktivieren eines Edge-Pools**   definiert und ordnet einen einzelnen Edgeserver oder einen Pool von Edgeserver zu. Ein Edgeserver vereinfacht die Kommunikation und Zusammenarbeit zwischen Benutzern innerhalb der Organisation und Personen außerhalb der Organisation, einschließlich Verbundbenutzern.
    
    Es gibt zwei mögliche Szenarien, mit denen Sie die Serverrollen bereitstellen und zuordnen können:
    
    In Szenario 1 definieren Sie eine neue Topologie für eine Neuinstallation. Sie können sich der Installation auf eine von zwei Arten nähern:
    
      - Deaktivieren Sie das Kontrollkästchen, und fahren Sie mit dem Definieren der Topologie fort. Nachdem Sie den Front-End-Server und den Back-End-Server veröffentlicht, konfiguriert und getestet haben, können Sie den Topologie-Generator erneut ausführen, um die Rollenserver zur Topologie hinzuzufügen. Mit dieser Strategie können Sie den Front-End-Pool und den Server, auf dem SQL Server ausgeführt wird, ohne zusätzliche Komplikationen durch zusätzliche Rollen testen. Wenn Sie die anfänglichen Tests abgeschlossen haben, können Sie den Topologie-Generator zur Auswahl der erforderlichen Rollen erneut ausführen.
    
      - Wählen Sie die Rollen aus, die installiert werden müssen, und richten Sie anschließend die Hardware für die ausgewählten Rollen ein.
    
    Für Szenario zwei verfügen Sie über eine vorhandene Bereitstellung, und ihre Infrastruktur ist für neue Rollen bereit, oder Sie müssen vorhandene Rollen einem neuen Front-End-Server zuordnen:
    
      - In diesem Fall wählen Sie die Rollen aus, die Sie dem neuen Front-End-Server bereitstellen oder zuordnen möchten. In beiden Fällen fahren Sie mit der Definition der Rollen fort, richten gegebenenfalls erforderliche Hardware ein und führen die Installation aus.

7.  Führen Sie auf der Seite **SQL Store definieren** eine der folgenden Aktionen aus:
    
      - Zum Verwenden eines SQL Server-Speichers, der bereits in Ihrer Topologie definiert wurde, wählen Sie eine Instanz unter **SQL-Speicher** aus.
    
      - Wenn Sie eine neue SQL Server-Instanz zum Speichern von Poolinformationen definieren möchten, klicken Sie auf **neu** , und geben Sie dann den **SQL Server-FQDN**im Dialogfeld **neuen SQL-Speicher definieren** ein.
    
      - Zum Angeben des Namens einer SQL Server-Instanz wählen Sie **Benannte Instanz** und geben Sie anschließend den Namen der Instanz an.
    
      - Klicken Sie auf **Standardinstanz**, um die Standardinstanz zu verwenden.
    
      - Wenn Sie die SQL-Spiegelung verwenden möchten, wählen Sie **SQL-Spiegelung aktivieren** aus, und wählen Sie eine vorhandene Instanz aus, oder erstellen Sie eine neue Instanz.

8.  Führen Sie auf der Seite " **Dateifreigabe definieren** " eine der folgenden Aktionen aus:
    
      - Zum Verwenden einer Dateifreigabe, die bereits in Ihrer Topologie definiert wurde, wählen Sie **Zuvor definierte Dateifreigabe verwenden**.
    
      - Zum Definieren einer neuen Dateifreigabe wählen Sie **Neue Dateifreigabe definieren**, geben Sie im Feld **Dateiserver-FQDN** den vollqualifizierten Domänennamen des vorhandenen Dateiservers ein, auf dem sich die Dateifreigabe befinden soll, und geben Sie anschließend einen Namen für die Dateifreigabe in das Feld **Dateifreigabe** ein.
    
    <div>
    

    > [!IMPORTANT]
    > Die Dateifreigabe für lync Server 2013 kann nicht auf dem Front-End-Server gefunden werden. Beachten Sie, dass sich die Dateifreigabe in diesem Beispiel auf dem auf SQL Server basierenden Back-End-Server befand. Dies ist möglicherweise kein optimaler Ort für die Anforderungen Ihrer Organisation, und ein Dateiserver ist möglicherweise eine bessere Wahl. Sie können die Dateifreigabe definieren, ohne sie erstellt zu haben. Sie müssen die Dateifreigabe am definierten Speicherort erstellen, bevor Sie die Topologie veröffentlichen.

    
    </div>

9.  Führen Sie auf der Seite **Geben Sie die Webdienste-URL** an eine oder beide der folgenden Aktionen aus:
    
    <div>
    

    > [!IMPORTANT]
    > Die Basis-URL ist die Webdienstidentität der URL ohne https://. Wenn beispielsweise die vollständige URL für die Webdienste des Pools lautet https://pool01.contoso.net, lautet die Basis-URL pool01.contoso.net.

    
    </div>
    
    <div>
    

    > [!WARNING]
    > Wenn Sie über mehr als einen Front-End-Pool oder Front-End-Server verfügen, muss der FQDN für externe Webdienste eindeutig sein. Wenn Sie beispielsweise den FQDN eines externen Webdiensts eines Front-End-Servers als <STRONG>pool01.contoso.com</STRONG>definieren, können Sie <STRONG>pool01.contoso.com</STRONG> nicht für einen anderen Front-End-Pool oder Front-End-Server verwenden.

    
    </div>
    
    1.  Wenn Sie den DNS-Lastenausgleich konfigurieren, aktivieren Sie das Kontrollkästchen **Interner FQDN des Webdienste-Pools außer Kraft setzen** , geben Sie die interne Basis-URL ein (die sich vom FQDN des Pools unter\<scheiden muss und\>beispielsweise Internal-ihre Basis-URL) in der **internen Basis-URL**sein kann.
        
        <div>
        

        > [!WARNING]
        > Wenn Sie sich entscheiden, die internen Webdienste mit einem selbst definierten FQDN zu überschreiben, muss jeder FQDN für jeden anderen Front-End-Pool, Director oder Director-Pool eindeutig sein. <STRONG>Verwenden Sie nur Standardzeichen</STRONG> (A – Z, a – z, 0 – 9 und Bindestriche), wenn Sie URLs oder vollqualifizierte Domänennamen definieren. Verwenden Sie keine Unicode-Zeichen oder Unterstriche. Nicht-Standardzeichen in einem URL oder vollqualifizierten Domänennamen (FQDN) werden von externen DNS und öffentlichen Zertifizierungsstellen (wenn die URL oder der FQDN dem Antragstellernamen oder dem alternativen Antragstellernamen im Zertifikat zugewiesen werden muss) häufig nicht unterstützt.

        
        </div>
    
    2.  Optional können Sie die externe Basis-URL in der **externen Basis-URL**eingeben. Sie würden die externe Basis-URL eingeben, um Sie von ihrer internen Domänen Namensgebung zu unterscheiden. Beispielsweise ist Ihre interne Domäne contoso.net, aber ihr externer Domänenname lautet contoso.com. Sie würden die URL mit dem contoso.com-Domänennamen definieren. Dies ist auch im Fall eines Reverseproxys wichtig. Der Domänenname der externen Basis-URL würde dem Domänennamen des vollqualifizierten Domänennamens des Reverseproxys entsprechen. Für Sofortnachrichten und Anwesenheitsinformationen ist der HTTP-Zugriff auf den Front-End-Pool erforderlich.
    
    <div>
    

    > [!NOTE]
    > Wenn Sie den DNS-Lastenausgleich verwenden möchten, müssen Sie die entsprechenden DNS-Einträge erstellen. Ausführliche Informationen finden Sie unter <A href="lync-server-2013-configure-dns-for-load-balancing.md">Konfigurieren von DNS für den Lastenausgleich in lync Server 2013</A>.

    
    </div>

10. Wenn Sie auf der Seite **"Features auswählen** " **Konferenzen** ausgewählt haben, wählen Sie auf der Seite **Office Web Apps Server auswählen** die Option **Pool mit einem Office Web Apps-Server verknüpfen** aus, und klicken Sie dann auf **neu** (oder wählen Sie in der Dropdownliste einen vorhandenen Office Web Apps-Server aus) aus.

11. Geben Sie im Dialogfeld **Neuen Office Web Apps-Server definieren** den vollqualifizierten Domänennamen (FQDN) Ihres Office Web Apps-Servercomputers im Feld **FQDN von Office Web Apps-Server** ein. Anschließend sollte im Feld **Office Web Apps-Server-Such-URL** automatisch die Such-URL Ihres Office Web Apps-Servers stehen.
    
    Wenn der Office Web Apps-Server lokal und in derselben Netzwerkzone wie lync Server 2013 installiert ist, sollte die Option **Office Web Apps Server in einem externen Netzwerk bereitgestellt werden (also Umkreis/Internet)** , nicht ausgewählt werden.
    
    Wenn der Office Web Apps-Server außerhalb Ihrer internen Firewall bereitgestellt ist, aktivieren Sie die Option **Office Web Apps-Server ist in einem externen Netzwerk (d. h. Umkreis/Internet) bereitgestellt**.
    
    <div>
    

    > [!NOTE]
    > Ausführliche Informationen finden Sie unter <A href="lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md">Konfigurieren der Integration in Office Web Apps Server und lync Server 2013</A>.

    
    </div>

12. Wählen Sie auf der Seite **Archivierungs-SQL-Speicher definieren** eine vorhandene Instanz oder SQL Server aus, oder definieren Sie eine neue Instanz zum Speichern der Daten, die mit den Archivierungsdaten verknüpft sind.

13. Wählen Sie auf der Seite **Definieren der Überwachung des SQL Stores** eine vorhandene Instanz oder SQL Server aus, oder definieren Sie eine neue Instanz zum Speichern der Daten, die mit Überwachungsdaten verknüpft sind.

14. Klicken Sie auf **Weiter**. Wenn Sie auf der Seite **Serverrollen mit diesem Front-End-Pool zuordnen** andere Rollen Server definiert haben, werden die Seiten des Assistenten für die Rollenkonfiguration separat geöffnet, damit Sie die Serverrollen konfigurieren können. Ausführliche Informationen finden Sie unter den folgenden Themen:
    
    [Bereitstellen des Zugriffs durch externe Benutzer in Lync Server 2013](lync-server-2013-deploying-external-user-access.md)

15. Wenn Sie keine zusätzlichen Serverrollen zum Konfigurieren und Bereitstellen ausgewählt haben oder wenn Sie die Konfiguration der zusätzlichen Rollen Server abgeschlossen haben, klicken Sie auf **Fertig stellen**.

</div>

</div>

<span> </span>

</div>

</div>

</div>

