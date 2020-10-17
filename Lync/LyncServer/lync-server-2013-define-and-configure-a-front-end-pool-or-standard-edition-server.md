---
title: Definieren und Konfigurieren eines Front-End-Pool oder Standard Edition-Server
description: Definieren und Konfigurieren eines Front-End-Pool oder Standard Edition-Servers.
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
ms.openlocfilehash: fd632564f0a5afd1f899ee8487f633c4685d12a7
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48569981"
---
# <a name="define-and-configure-a-front-end-pool-or-standard-edition-server-in-lync-server-2013"></a>Definieren und Konfigurieren eines Front-End-Pool oder Standard Edition-Server in lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2013-03-08_

Für dieses Verfahren ist keine Mitgliedschaft in einer lokalen Administratorgruppe oder einer Domänengruppe mit besonderen Rechten erforderlich. Melden Sie sich als Standardbenutzer bei einem Computer an.

Wenn Sie einen Enterprise-Server bereitstellen, muss immer eine Mindestanzahl von Front-End-Servern in einem Pool installiert sein. Eine Übersicht über diese Mindestanzahl finden Sie in der folgenden Tabelle.


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Gesamtanzahl der Front-End-Server im Pool</th>
<th>Anzahl der Server, die für die korrekte Funktionsweise des Pools ausgeführt werden müssen</th>
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
<td><p>4 </p></td>
</tr>
<tr class="odd">
<td><p>9-10</p></td>
<td><p>5 </p></td>
</tr>
<tr class="even">
<td><p>11-12</p></td>
<td><p>6 </p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]
> Für lync Server 2013 müssen Sie bei jedem Hinzufügen oder Entfernen eines Front-End-Server aus dem Pool Dienste neu starten. Das Entfernen und Hinzufügen von Servern sollte als separate Vorgänge erfolgen. Wenn Sie beispielsweise zwei Front-End-Server hinzufügen und zwei Front-End-Server entfernen möchten, verwenden Sie den folgenden Prozess: 
> <OL>
> <LI>
> <P>Entfernen Sie die beiden Front-End-Server.</P>
> <LI>
> <P>Veröffentlichen Sie die Topologie, und aktivieren Sie sie erneut.</P>
> <LI>
> <P>Starten Sie die Dienste neu.</P>
> <LI>
> <P>Fügen Sie die beiden Front-End-Server hinzu.</P>
> <LI>
> <P>Veröffentlichen Sie die Topologie, und aktivieren Sie sie erneut.</P>
> <LI>
> <P>Starten Sie die Dienste neu.</P></LI></OL>



</div>

Nachdem Sie Ihre Topologie definiert haben, verwenden Sie das folgende Verfahren, um eine Front-End-Pool für Ihre Website zu definieren. Ausführliche Informationen zum Definieren der Topologie finden Sie unter [definieren und Konfigurieren einer Topologie im Topologie-Generator für lync Server 2013](lync-server-2013-define-and-configure-a-topology-in-topology-builder.md).

<div>

## <a name="to-define-a-front-end-pool"></a>So definieren Sie eine Front-End-Pool

1.  Klicken Sie im Assistenten zum Definieren eines neuen Front-End-Pools auf der Seite **Neuen Front-End-Pool definieren** auf **Weiter**.

2.  Geben Sie auf der Seite **Front-End-Pool FQDN definieren** einen vollqualifizierten Domänennamen (Fully Qualified Domain Name, FQDN) für den Pool ein, den Sie erstellen möchten, klicken Sie auf **Enterprise Edition Front-End-Pool**, und klicken Sie dann auf **weiter**.

3.  Geben Sie auf der Seite **Computer in diesem Pool definieren** einen Computer-FQDN für den ersten Front-End-Server im Pool ein, und klicken Sie dann auf **Hinzufügen**. Wiederholen Sie diesen Schritt für alle weiteren Computer (bis zu zwölf), die Sie dem Pool hinzufügen möchten, und klicken Sie dann auf **weiter**.

4.  Aktivieren Sie auf der Seite **Features auswählen** die Kontrollkästchen für die Features, die in diesem Front-End-Pool werden sollen. Wenn Sie beispielsweise nur Instant Messaging-und Anwesenheitsfunktionen bereitstellen, aktivieren Sie das Kontrollkästchen **Konferenzen** , um mehrteiligen Chat zu ermöglichen, aber nicht die Kontrollkästchen **Einwahlkonferenzen**, **Enterprise-VoIP**oder **Anrufsteuerung** auswählen, da Sie die Features für VoIP, Video und gemeinschaftliche Konferenzen darstellen.
    
      - **Konferenzen**     Diese Auswahl ermöglicht eine umfangreiche Palette von Features, einschließlich:
        
          - Sofortnachrichten mit mehr als zwei Teilnehmern in einer Sofortnachrichtenfunktionsitzung
        
          - Konferenzfunktionen, u. a. Dokumentzusammenarbeit, Anwendungsfreigabe und Desktopfreigabe
        
          - A/v-Konferenzen, die es Benutzern ermöglichen, Echtzeit-Audio/Video-Konferenzen (a/v) zu haben, ohne externe Dienste wie den Live Meeting-Dienst oder eine Audio-Bridge eines Drittanbieters zu benötigen.
    
      - **Einwahlkonferenzen**     (PSTN) Ermöglicht Benutzern die Teilnahme am Audioteil einer lync Server 2013 Konferenz mithilfe eines PSTN-Telefons (Public Switched Telephone Network), ohne dass ein Anbieter für Audiokonferenzen erforderlich ist.
    
      - **Enterprise-VoIP**     Enterprise-VoIP ist die VoIP-Lösung (Voice over IP) in lync Server 2013, mit der Benutzer Telefonanrufe tätigen und empfangen können. Sie möchten dieses Feature bereitstellen, wenn Sie lync Server 2013 für Sprachanrufe, Voicemail und andere Funktionen verwenden möchten, die ein Hardwaregerät oder einen Software Client verwenden.
    
      - **Anrufsteuerung (Call Admission Control, CAC)**     Bei der Anrufsteuerung wird basierend auf der verfügbaren Netzwerkbandbreite festgelegt, ob Echt Zeit Kommunikationssitzungen wie Sprach-oder Videoanrufe eingerichtet werden dürfen. Wenn Sie lediglich Sofortnachrichten- und Anwesenheitsfunktionen bereitgestellt haben, wird die Anrufsteuerung nicht benötigt, da diese Funktionen die Anrufsteuerung nicht nutzen.
    
      - **Archivierung**     Die Archivierung bietet Ihnen die Möglichkeit, Chatinhalte, Konferenzinhalte (Besprechungen) oder beides zu archivieren, die über lync Server 2013 gesendet werden.
    
      - **Überwachung**     Mit Monitoring Server können Sie numerische Daten erfassen, die die Medienqualität in Ihrem Netzwerk und Endpunkten, Nutzungsinformationen im Zusammenhang mit VoIP-Anrufen, Chatnachrichten, A/V-Unterhaltungen, Besprechungen, Anwendungsfreigabe und Dateiübertragungen sowie Anruf Fehler-und Problembehandlungsinformationen für fehlgeschlagene Anrufe beschreiben.
    
    <div>
    

    > [!NOTE]
    > Zum Aktivieren der Anrufsteuerung in Ihrer Bereitstellung müssen Sie diese Funktion in genau einem Pool pro zentralem Standort aktivieren. Die Anrufsteuerung wird empfohlen, wenn Sie VoIP-Funktionen oder die A/V-Konferenzfunktion bereitstellen.

    
    </div>
    
    In der folgenden Tabelle sind die verfügbaren Funktionen (oben) sowie die für die Benutzer bereitgestellten Funktionen (links) aufgeführt. Um diese Funktionen für Ihre Organisation zu aktivieren, treffen Sie die in der Tabelle gezeigte Auswahl.
    
    
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
    <td><p>Sofortnachrichten und Anwesenheit</p></td>
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


5.  Auf der Seite verbundene **Serverrollen auswählen** können Sie die Vermittlungsserver im Front-End-Server collocate oder als eigenständigen Server bereitstellen.
    
    Sie können die Vermittlungsserver im Front-End-Pool collocate.
    
      - Wenn Sie beabsichtigen, die Vermittlungsserver im Enterprise Edition-Front-End-Pool collocate, stellen Sie sicher, dass das Kontrollkästchen aktiviert ist. Die Serverrolle wird auf den Poolservern bereitgestellt.
    
      - Wenn Sie die Vermittlungsserver als eigenständigen Server bereitstellen möchten, deaktivieren Sie das entsprechende Kontrollkästchen. Sie werden Vermittlungsserver in einem separaten Bereitstellungsschritt bereitstellen, nachdem Sie die Front-End-Server vollständig bereitgestellt haben.
    
    <div>
    

    > [!NOTE]
    > Es wird empfohlen, wenn möglich den Vermittlungsserver zu verbinden. Ausführliche Informationen zur Unterstützung für verbundene oder eigenständige Vermittlungsserver finden Sie unter <A href="lync-server-2013-components-and-topologies-for-mediation-server.md">Components and Topologies for Vermittlungsserver in lync Server 2013</A> in der Planungsdokumentation.

    
    </div>

6.  Auf der Seite **Serverrollen mit dieser Front-End-Pool zuordnen** können Sie Serverrollen mit dem Front-End-Pool definieren und zuordnen. Die folgende Rolle ist verfügbar:
    
    **Aktivieren eines Edgepool**     Definiert und ordnet einem einzelnen Edgeserver oder einem Pool von Edgeserver zu. Eine Edgeserver erleichtert die Kommunikation und Zusammenarbeit zwischen Benutzern innerhalb der Organisation und Personen außerhalb der Organisation, einschließlich Verbundbenutzern.
    
    Für die Bereitstellung und Zuordnung der Serverrollen sind zwei Szenarien möglich:
    
    In Szenario 1 definieren Sie eine neue Topologie für eine Neuinstallation. Die Installation kann über zwei Methoden ausgeführt werden:
    
      - Lassen Sie das Kontrollkästchen deaktiviert, und fahren Sie mit der Topologiedefinition fort. Nachdem Sie die Front-End-und Back-End-Server Rollen veröffentlicht, konfiguriert und getestet haben, können Sie den Topologie-Generator erneut ausführen, um die Rollen Server zur Topologie hinzuzufügen. Mit dieser Strategie können Sie die Front-End-Pool und den Server, auf dem SQL Server läuft, ohne zusätzliche Komplikationen durch zusätzliche Rollen testen. Nachdem Sie die ersten Tests abgeschlossen haben, können Sie den Topologie-Generator erneut ausführen, um die Rollen auszuwählen, die Sie bereitstellen müssen.
    
      - Wählen Sie die Rollen aus, die installiert werden müssen, und richten Sie anschließend die Hardware für die ausgewählten Rollen ein.
    
    Für Szenario 2 verfügen Sie über eine vorhandene Bereitstellung, und ihre Infrastruktur ist bereit für neue Rollen, oder Sie müssen vorhandene Rollen einer neuen Front-End-Server zuordnen:
    
      - In diesem Fall wählen Sie die Rollen aus, die Sie dem neuen Front-End-Server bereitstellen oder zuordnen möchten. In beiden Fällen fahren Sie mit der Definition der Rollen fort, richten gegebenenfalls erforderliche Hardware ein und führen die Installation aus.

7.  Führen Sie auf der Seite **SQL-Speicher definieren** einen der folgenden Schritte aus:
    
      - Zum Verwenden eines vorhandenen SQL Server-Speichers, der bereits in Ihrer Topologie definiert wurde, wählen Sie eine Instanz unter **SQL-Speicher** aus.
    
      - Zum Definieren einer neuen SQL Server Instanz zum Speichern von Poolinformationen klicken Sie auf **neu** , und geben Sie dann im Dialogfeld **neuen SQL-Speicher definieren** den **FQDN SQL Server**an.
    
      - Zum Angeben des Namens einer SQL Server-Instanz wählen Sie **Benannte Instanz**, und geben Sie anschließend den Namen der Instanz an.
    
      - Klicken Sie auf **Standardinstanz**, um die Standardinstanz zu verwenden.
    
      - Zum Verwenden der SQL-Spiegelung wählen Sie **SQL-Spiegelung aktivieren** aus, und wählen Sie dann eine vorhandene Instanz aus, oder erstellen Sie eine neue Instanz.

8.  Führen Sie auf der Seite **Dateifreigabe definieren** einen der folgenden Schritte aus:
    
      - Zum Verwenden einer Dateifreigabe, die bereits in Ihrer Topologie definiert wurde, wählen Sie **Zuvor definierte Dateifreigabe verwenden**.
    
      - Zum Definieren einer neuen Dateifreigabe wählen Sie **Neue Dateifreigabe definieren**, geben Sie im Feld **Dateiserver-FQDN** den vollqualifizierten Domänennamen des vorhandenen Dateiservers ein, auf dem sich die Dateifreigabe befinden soll, und geben Sie anschließend einen Namen für die Dateifreigabe in das Feld **Dateifreigabe** ein.
    
    <div>
    

    > [!IMPORTANT]
    > Die Dateifreigabe für lync Server 2013 kann sich nicht auf dem Front-End-Server befinden. Beachten Sie, das die Dateifreigabe in diesem Beispiel auf dem SQL Server-basierten Back-End-Server platziert wurde. Möglicherweise ist dies nicht der optimale Speicherort für die Anforderungen Ihrer Organisation, und ein Dateiserver wäre die bessere Wahl. Sie können die Dateifreigabe definieren, ohne dass die Dateifreigabe erstellt wurde. Sie müssen die Dateifreigabe am definierten Speicherort erstellen, bevor Sie die Topologie veröffentlichen.

    
    </div>

9.  Führen Sie auf der Seite **Webdienste-URL angeben** einen oder mehrere der folgenden Schritte aus:
    
    <div>
    

    > [!IMPORTANT]
    > Die Basis-URL ist die Webdienstidentität der URL ohne https://. Wenn beispielsweise die vollständige URL für die Webdienste des Pools ist https://pool01.contoso.net , lautet die Basis-URL pool01.contoso.net.

    
    </div>
    
    <div>
    

    > [!WARNING]
    > Wenn Sie mehr als eine Front-End-Pool oder Front-End-Server haben, muss der FQDN für externe Webdienste eindeutig sein. Wenn Sie beispielsweise den externen Webdienste-FQDN eines Front-End-Server als <STRONG>pool01.contoso.com</STRONG>definieren, können Sie <STRONG>pool01.contoso.com</STRONG> nicht für eine andere Front-End-Pool oder Front-End-Server verwenden.

    
    </div>
    
    1.  Wenn Sie den DNS-Lastenausgleich konfigurieren, aktivieren Sie das Kontrollkästchen **internen Webdienste Pool-FQDN außer Kraft setzen** , geben Sie die interne Basis-URL (die sich vom Pool-FQDN unterscheiden muss und beispielsweise Internal sein kann \<your base URL\> ) in die **interne Basis-URL**ein.
        
        <div>
        

        > [!WARNING]
        > Wenn Sie die internen Webdienste mit einem selbst definierten FQDN außer Kraft setzen möchten, muss jeder FQDN von jedem anderen Front-End-Pool, Director oder einem Directorpool eindeutig sein. <STRONG>Verwenden Sie nur Standardzeichen</STRONG> (einschließlich a – z, a – z, 0 – 9 und Bindestriche), wenn Sie URLs oder vollqualifizierte Domänennamen definieren. Verwenden Sie keine Unicode-Zeichen oder Unterstriche. Nicht Standardzeichen in einer URL oder einem FQDN werden von externen DNS-und öffentlichen CAS häufig nicht unterstützt (das heißt, wenn die URL oder der FQDN dem Antragstellernamen oder dem alternativen Antragstellernamen im Zertifikat zugewiesen werden muss).

        
        </div>
    
    2.  Optional geben Sie die externe Basis-URL im Feld **Externe Basis-URL** ein. Die externe Basis-URL wird zur Unterscheidung dieser URL von Ihrer internen Domänenbenennung eingegeben. Beispiel: der Name Ihrer internen Domäne lautet "contoso.net", der Name Ihrer externen Domäne lautet "contoso.com". Zur Definition der URL würden Sie den Domänennamen "contoso.com" verwenden. Dies ist auch im Fall eines Reverseproxys wichtig. Der Domänenname der externen Basis-URL würde dem Domänennamen des vollqualifizierten Domänennamens des Reverseproxys entsprechen. Für Chatnachrichten und Anwesenheitsinformationen ist der HTTP-Zugriff auf die Front-End-Pool erforderlich.
    
    <div>
    

    > [!NOTE]
    > Zur Verwendung des DNS-Lastenausgleichs müssen Sie die entsprechenden DNS-Einträge erstellen. Ausführliche Informationen finden Sie unter <A href="lync-server-2013-configure-dns-for-load-balancing.md">Konfigurieren von DNS für den Lastenausgleich in lync Server 2013</A>.

    
    </div>

10. Wenn Sie auf der Seite **Features auswählen** die Option **Konferenzen** ausgewählt haben, wählen Sie auf der Seite **Office-webappsserver auswählen** die Option **Pool mit einem Office-webappsserver zuordnen** aus, und klicken Sie dann auf **neu** (oder wählen Sie in der Dropdownliste einen vorhandenen Office-webapps-Server aus).

11. Geben Sie im Dialogfeld **Neuen Office Web Apps-Server definieren** den vollqualifizierten Domänennamen (FQDN) Ihres Office Web Apps-Servercomputers im Feld **FQDN von Office Web Apps-Server** ein. Anschließend sollte im Feld **Office Web Apps-Server-Such-URL** automatisch die Such-URL Ihres Office Web Apps-Servers stehen.
    
    Wenn der Office Web Apps-Server lokal und in der gleichen Netzwerkzone wie lync Server 2013 installiert ist, sollte die Option **Office Web Apps Server in einem externen Netzwerk bereitgestellt werden (d. "Perimeter/Internet")** sollte nicht ausgewählt werden.
    
    Wenn der Office Web Apps-Server außerhalb Ihrer internen Firewall bereitgestellt ist, aktivieren Sie die Option **Office Web Apps-Server ist in einem externen Netzwerk (d. h. Umkreis/Internet) bereitgestellt**.
    
    <div>
    

    > [!NOTE]
    > Ausführliche Informationen finden Sie unter <A href="lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md">Konfigurieren der Integration mit Office-webapps Server und lync Server 2013</A>.

    
    </div>

12. Wählen Sie auf der Seite **Archivierungs-SQL-Speicher definieren** eine vorhandene Instanz von SQL Server aus, oder definieren Sie eine neue Instanz, um die Daten zu speichern, die den Archivierungsdaten zugeordnet sind.

13. Wählen Sie auf der Seite **Monitoring-SQL-Speicher definieren** eine vorhandene Instanz von SQL Server aus, oder definieren Sie eine neue Instanz, um die Daten zu speichern, die den Überwachungsdaten zugeordnet sind.

14. Klicken Sie auf **Weiter**. Wenn Sie auf der Seite **Serverrollen mit dieser Front-End-Pool zuordnen** andere Rollen Server definiert haben, werden separate Seiten des Rollen Konfigurations-Assistenten geöffnet, über die Sie die Serverrollen konfigurieren können. Ausführliche Informationen finden Sie im Abschnitt:
    
    [Bereitstellen von externem Benutzer Zugriff in lync Server 2013](lync-server-2013-deploying-external-user-access.md)

15. Wenn Sie keine zusätzlichen Serverrollen ausgewählt haben, die konfiguriert und bereitgestellt werden sollen, oder wenn Sie die Konfiguration der zusätzlichen Rollenserver abgeschlossen haben, klicken Sie auf **Fertig stellen**.

</div>

</div>

<span> </span>

</div>

</div>

</div>

