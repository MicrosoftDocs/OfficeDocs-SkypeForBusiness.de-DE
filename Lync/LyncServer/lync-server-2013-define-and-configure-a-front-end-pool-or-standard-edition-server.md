---
title: 'Lync Server 2013: Definieren und Konfigurieren eines Front-End-Pools oder Standard Edition-Servers'
TOCTitle: Definieren und Konfigurieren eines Front-End-Pools oder Standard Edition-Servers
ms:assetid: 713fc263-23dd-414a-b001-82932e4fe966
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg398538(v=OCS.15)
ms:contentKeyID: 49294367
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Definieren und Konfigurieren eines Front-End-Pools oder Standard Edition-Servers in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2015-03-09_

Für dieses Verfahren ist keine Mitgliedschaft in einer lokalen Administratorgruppe oder einer Domänengruppe mit besonderen Rechten erforderlich. Melden Sie sich als Standardbenutzer bei einem Computer an.

Wenn Sie einen Enterprise-Server bereitstellen, muss dauerhaft eine Mindestanzahl an Front-End-Servern in einem Pool ausgeführt werden. Eine Übersicht über diese Mindestanzahl finden Sie in der folgenden Tabelle.

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Gesamtzahl der Front-End-Server in dem Pool</th>
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



> [!NOTE]
> In Lync Server 2013 müssen die Dienste nach jedem Hinzufügen oder Entfernen eines Front-End-Servers zu bzw. aus dem Pool neu gestartet werden. Das Entfernen und Hinzufügen von Servern sollte als separater Vorgang ausgeführt werden. Verwenden Sie beispielsweise den folgenden Ablauf, um zwei Front-End-Server hinzuzufügen und zwei Front-End-Server zu entfernen: 
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



Nachdem Sie Ihre Topologie definiert haben, führen Sie die folgenden Schritte aus, um einen Front-End-Pool für Ihren Standort zu definieren. Ausführliche Informationen zum Definieren der Topologie finden Sie unter [Definieren und Konfigurieren einer Topologie für Lync Server 2013 im Topologie-Generator](lync-server-2013-define-and-configure-a-topology-in-topology-builder.md).

## So definieren Sie einen Front-End-Pool

1.  Klicken Sie im Assistenten zum Definieren eines neuen Front-End-Pools auf der Seite **Neuen Front-End-Pool** auf **Weiter** .

2.  Geben Sie auf der Seite **FQDN des Front-End-Pools definieren** einen vollqualifizierten Domänennamen (Fully Qualified Domain Name, FQDN) für den Pool ein, den Sie erstellen, klicken Sie auf **Front-End-Pool der Enterprise Edition** , und klicken Sie anschließend auf **Weiter** .

3.  Geben Sie auf der Seite **Computer in diesem Pool definieren** einen Computer-FQDN für den ersten Front-End-Server im Pool ein, und klicken Sie anschließend auf **Hinzufügen** . Wiederholen Sie diesen Schritt für (bis zu zwölf) zusätzliche Computer, die zum Pool hinzugefügt werden sollen, und klicken Sie anschließend auf **Weiter** .

4.  Aktivieren Sie auf der Seite **Funktionen auswählen** die Kontrollkästchen für die Funktionen, die für diesen Front-End-Pool bereitgestellt werden sollen. Wenn Sie z. B. lediglich Instant Messaging- und Anwesenheitsfunktionen bereitstellen, aktivieren Sie das Kontrollkästchen **Konferenzen** , um die Sofortnachrichtenfunktion für mehrere Teilnehmer zu aktivieren. Die Kontrollkästchen **Einwahlkonferenzen (PSTN)** , **Enterprise-VoIP** oder **Anrufsteuerung** würden Sie jedoch nicht aktivieren, da sich diese auf VoIP-, Video- und Zusammenarbeitskonferenzfunktionen beziehen.
    
      - **Konferenzen**   Bei Auswahl dieser Option wird ein umfassender Satz an Funktionen aktiviert, wie u. a.:
        
          - Sofortnachrichten mit mehr als zwei Teilnehmern in einer Sofortnachrichtenfunktionsitzung
        
          - Konferenzfunktionen, u. a. Dokumentzusammenarbeit, Anwendungsfreigabe und Desktopfreigabe
        
          - A/V-Konferenzfunktion, mit der Benutzer Audio/Video-Konferenzen (A/V) in Echtzeit durchführen können, ohne externe Dienste wie den Live Meeting-Dienst oder die Audiobrücke eines Drittanbieters verwenden zu müssen
    
      - **Einwahlkonferenzen (PSTN)**   Ermöglicht Benutzern die Teilnahme am Audioteil einer Lync Server 2013-Konferenz über ihr Festnetztelefon, sodass kein Audiokonferenzanbieter erforderlich ist.
    
      - **Enterprise-VoIP**   Enterprise-VoIP ist die VoIP-Lösung (Voice over IP) in Lync Server 2013, mit der Benutzer Anrufe tätigen und entgegennehmen können. Sie stellen diese Funktion bereit, wenn Sie die Verwendung von Lync Server 2013 für VoIP-Anrufe, Voicemail und andere Funktionen planen, für die ein Hardwaregerät oder ein Softwareclient verwendet wird.
    
      - **Anrufsteuerung**   Mithilfe der Anrufsteuerung wird basierend auf der verfügbaren Netzwerkbandbreite festgelegt, ob Echtzeitkommunikationssitzungen (z. B. Sprach- oder Videoanrufe) hergestellt werden können. Wenn Sie lediglich Sofortnachrichten- und Anwesenheitsfunktionen bereitgestellt haben, wird die Anrufsteuerung nicht benötigt, da diese Funktionen die Anrufsteuerung nicht nutzen.
    
      - **Archivierung**   Die Archivierung bietet Ihnen eine Möglichkeit zur Archivierung des Inhalts von Sofortnachrichten, des Inhalts von Konferenzen (Besprechungen) oder von beiden Inhalten, die über Lync Server 2013 gesendet werden.
    
      - **Monitoring**   Mit dem Monitoring Server können Sie numerische Daten zur Medienqualität im Netzwerk und an den Endpunkten, Nutzungsinformationen in Bezug auf VoIP-Anrufe (Voice over IP), Sofortnachrichten, A/V-Unterhaltungen (Audio/Video), Besprechungen, Anwendungsfreigaben und Dateiübertragungen sowie Fehlerinformationen und Informationen zur Problembehandlung bei Anruffehlern erfassen.
    

    > [!NOTE]
    > Zum Aktivieren der Anrufsteuerung in Ihrer Bereitstellung müssen Sie diese Funktion in genau einem Pool pro zentralem Standort aktivieren. Die Anrufsteuerung wird empfohlen, wenn Sie VoIP-Funktionen oder die A/V-Konferenzfunktion bereitstellen.

    
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
    <td><p>Chat und Anwesenheit</p></td>
    <td><p>X</p></td>
    <td><p></p></td>
    <td><p></p></td>
    <td><p></p></td>
    </tr>
    <tr class="even">
    <td><p>Konferenzen</p></td>
    <td><p>X</p></td>
    <td><p>X</p></td>
    <td><p></p></td>
    <td><p></p></td>
    </tr>
    <tr class="odd">
    <td><p>A/V-Konferenzen</p></td>
    <td><p>X</p></td>
    <td><p>X</p></td>
    <td><p></p></td>
    <td><p>X</p></td>
    </tr>
    <tr class="even">
    <td><p>Enterprise-VoIP</p></td>
    <td><p></p></td>
    <td><p></p></td>
    <td><p>X</p></td>
    <td><p>X</p></td>
    </tr>
    </tbody>
    </table>


5.  Auf der Seite **Verbundene Serverrollen auswählen** können Sie festlegen, ob der Vermittlungsserver mit dem Front-End-Server verbunden werden sollen oder ob Sie diesen als eigenständigen Server bereitstellen möchten.
    
    Sie können den Vermittlungsserver auf dem Front-End-Pool verbinden.
    
      - Wenn Sie den Vermittlungsserver mit dem Front-End-Pool der Enterprise Edition verbinden möchten, stellen Sie sicher, dass das Kontrollkästchen aktiviert ist. Die Serverrolle wird auf den Poolservern bereitgestellt.
    
      - Wenn Sie den Vermittlungsserver als eigenständigen Server bereitstellen möchten, deaktivieren Sie das entsprechende Kontrollkästchen. Sie stellen den Vermittlungsserver in einem separaten Bereitstellungsschritt bereit, nachdem die Bereitstellung des Front-End-Servers vollständig abgeschlossen wurde.
    

    > [!NOTE]
    > Es wird empfohlen, wenn möglich den Vermittlungsserver zu verbinden. Ausführliche Informationen zur Unterstützung von verbundenen oder eigenständigen Vermittlungsservern finden Sie unter <A href="lync-server-2013-components-and-topologies-for-mediation-server.md">Komponenten und Topologien für den Vermittlungsserver in Lync Server 2013</A> in der Planungsdokumentation.



6.  Über die Seite **Serverrollen zu diesem Front-End-Pool zuordnen** können Sie Serverrollen definieren und dem Front-End-Pool zuordnen. Die folgende Rolle ist verfügbar:
    
    **Edgepool aktivieren**   Zum Definieren und Zuordnen eines einzelnen Edgeservers oder eines Pools von Edgeservern. Ein Edgeserver vereinfacht die Kommunikation und Zusammenarbeit zwischen Benutzern innerhalb und außerhalb der Organisation, einschließlich Partnerbenutzern.
    
    Für die Bereitstellung und Zuordnung der Serverrollen sind zwei Szenarien möglich:
    
    In Szenario 1 definieren Sie eine neue Topologie für eine Neuinstallation. Die Installation kann über zwei Methoden ausgeführt werden:
    
      - Lassen Sie das Kontrollkästchen deaktiviert, und fahren Sie mit der Topologiedefinition fort. Nachdem Sie den Front-End-Server und den Back-End-Server veröffentlicht, konfiguriert und getestet haben, können Sie den Topologie-Generator erneut ausführen, um die Rollenserver zur Topologie hinzuzufügen. Bei dieser Vorgehensweise können Sie den Front-End-Pool und Server, auf dem SQL Server ausgeführt wird, ohne Komplikationen durch zusätzliche Rollen testen. Wenn Sie die anfänglichen Tests abgeschlossen haben, können Sie den Topologie-Generator zur Auswahl der erforderlichen Rollen erneut ausführen.
    
      - Wählen Sie die Rollen aus, die installiert werden müssen, und richten Sie anschließend die Hardware für die ausgewählten Rollen ein.
    
    In Szenario 2 verfügen Sie über eine vorhandene Bereitstellung, und in Ihrer Infrastruktur sollen neue Rollen installiert werden bzw. Sie müssen vorhandene Rollen einem neuen Front-End-Server zuordnen:
    
      - In diesem Fall wählen Sie die Rollen aus, die bereitgestellt oder dem neuen Front-End-Server zugeordnet werden sollen. In beiden Fällen fahren Sie mit der Definition der Rollen fort, richten gegebenenfalls erforderliche Hardware ein und führen die Installation aus.

7.  Führen Sie auf der Seite **SQL-Speicher definieren** einen der folgenden Schritte aus:
    
      - Zum Verwenden eines vorhandenen SQL Server-Speichers, der bereits in Ihrer Topologie definiert wurde, wählen Sie eine Instanz unter **SQL-Speicher** aus.
    
      - Zum Definieren einer neuen SQL Server-Instanz zum Speichern von Poolinformationen klicken Sie auf **Neu** , und geben Sie im Dialogfeld **Neuen SQL-Speicher definieren** den **SQL Server-FQDN** an:
    
      - Zum Angeben des Namens einer SQL Server-Instanz wählen Sie **Benannte Instanz** , und geben Sie anschließend den Namen der Instanz an.
    
      - Klicken Sie auf **Standardinstanz** , um die Standardinstanz zu verwenden.
    
      - Zum Verwenden der SQL-Spiegelung wählen Sie **SQL-Spiegelung aktivieren** aus, und wählen Sie dann eine vorhandene Instanz aus, oder erstellen Sie eine neue Instanz.

8.  Führen Sie auf der Seite **Dateifreigabe definieren** einen der folgenden Schritte aus:
    
      - Zum Verwenden einer Dateifreigabe, die bereits in Ihrer Topologie definiert wurde, wählen Sie **Zuvor definierte Dateifreigabe verwenden** .
    
      - Zum Definieren einer neuen Dateifreigabe wählen Sie **Neue Dateifreigabe definieren** , geben Sie im Feld **Dateiserver-FQDN** den vollqualifizierten Domänennamen des vorhandenen Dateiservers ein, auf dem sich die Dateifreigabe befinden soll, und geben Sie anschließend einen Namen für die Dateifreigabe in das Feld **Dateifreigabe** ein.
    

    > [!IMPORTANT]
    > Die Dateifreigabe für Lync Server 2013 kann sich auf dem Front-End-Server befinden. Beachten Sie, das die Dateifreigabe in diesem Beispiel auf dem SQL&nbsp;Server-basierten Back-End-Server platziert wurde. Möglicherweise ist dies nicht der optimale Speicherort für die Anforderungen Ihrer Organisation, und ein Dateiserver wäre die bessere Wahl. Sie können die Dateifreigabe definieren, ohne dass die Dateifreigabe erstellt wurde. Sie müssen die Dateifreigabe am definierten Speicherort erstellen, bevor Sie die Topologie veröffentlichen.



9.  Führen Sie auf der Seite **Webdienste-URL angeben** einen oder mehrere der folgenden Schritte aus:
    

    > [!IMPORTANT]
    > Die Basis-URL ist die Identität der Webdienste für die URL ohne https://. Wenn beispielsweise die vollständige URL der Webdienste des Pools "https://pool01.contoso.net" lautet, ist die Basis-URL "pool01.contoso.net".

    

    > [!WARNING]
    > Wenn Sie mehr als einen Front-End-Pool oder Front-End-Server verwenden, muss der externe FQDN für Webdienste eindeutig sein. Wenn Sie beispielsweise den externen FQDN für Webdienste für einen Front-End-Server, z.&nbsp;B. <STRONG>pool01.contoso.com</STRONG>, definieren, können Sie <STRONG>pool01.contoso.com</STRONG> nicht für einen weiteren Front-End-Pool oder Front-End-Server verwenden.

    
    1.  Wenn Sie den DNS-Lastenausgleich konfigurieren, aktivieren Sie das Kontrollkästchen **FQDN der internen Webdienste außer Kraft setzen** , und geben Sie in **Interne Basis-URL** die interne Basis-URL ein (diese muss sich vom Pool-FQDN unterscheiden und könnte z. B. "internal-\<Ihre Basis-URL\>" lauten).
        

        > [!WARNING]
        > Wenn Sie den internen Webdienst mit einem eigenen FQDN überschreiben, muss der FQDN gegenüber jedem anderen Front-End-Pool, jedem anderen Director und jedem anderen Directorpool eindeutig sein. <STRONG>Verwenden Sie nur Standardzeichen</STRONG> (A-Z, a-z, 0-9 und Bindestriche), wenn Sie URLs oder vollqualifizierte Domänennamen definieren. Verwenden Sie keine Unicode-Zeichen oder Unterstriche. Nicht-Standardzeichen in einem URL oder vollqualifizierten Domänennamen (FQDN) werden von externen DNS und öffentlichen Zertifizierungsstellen (wenn die URL oder der FQDN dem Antragstellernamen oder dem alternativen Antragstellernamen im Zertifikat zugewiesen werden muss) häufig nicht unterstützt.

    
    2.  Optional geben Sie die externe Basis-URL im Feld **Externe Basis-URL** ein. Die externe Basis-URL wird zur Unterscheidung dieser URL von Ihrer internen Domänenbenennung eingegeben. Beispiel: der Name Ihrer internen Domäne lautet "contoso.net", der Name Ihrer externen Domäne lautet "contoso.com". Zur Definition der URL würden Sie den Domänennamen "contoso.com" verwenden. Dies ist auch im Fall eines Reverseproxys wichtig. Der Domänenname der externen Basis-URL würde dem Domänennamen des vollqualifizierten Domänennamens des Reverseproxys entsprechen. Für Instant Messaging und Anwesenheit ist kein HTTP-Zugriff auf den Front-End-Pool erforderlich.
    

    > [!NOTE]
    > Zur Verwendung des DNS-Lastenausgleichs müssen Sie die entsprechenden DNS-Einträge erstellen. Ausführliche Informationen finden Sie unter <A href="lync-server-2013-configure-dns-for-load-balancing.md">Konfigurieren von DNS für den Lastenausgleich in Lync Server 2013</A>.



10. Wenn Sie auf der Seite **Auswählen von Funktionen** die Option **Konferenzen** ausgewählt haben, wählen Sie auf der Seite **Office Web Apps Server auswählen** die Option **Pool einem Office Web Apps Server zuordnen** aus, und klicken Sie dann auf **Neu** (oder wählen Sie einen vorhandenen Office Web Apps-Server aus der Dropdownliste aus).

11. Geben Sie im Dialogfeld **Neuen Office Web Apps Server definieren** im Feld **FQDN für Office Web Apps Server** den vollqualifizierten Domänennamen (FQDN) Ihres Office Web Apps-Server-Computers ein. Dabei sollte Ihre Office Web Apps-Server-Ermittlungs-URL automatisch im Feld **Office Web Apps Server-Ermittlung-URL** eingefügt werden.
    
    Wenn der Office Web Apps-Server lokal installiert ist und sich in derselben Netzwerkzone wie Lync Server 2013, sollte die Option **Office Web Apps Server wird in einem externen Netzwerk (z. B. Perimeternetzwerk/Internet) bereitgestellt** nicht ausgewählt werden.
    
    Wenn der Office Web Apps-Server außerhalb Ihrer internen Firewall bereitgestellt wird, wählen Sie die Option **Office Web Apps Server wird in einem externen Netzwerk (z. B. Perimeternetzwerk/Internet) bereitgestellt** aus.
    

    > [!NOTE]
    > Ausführliche Informationen finden Sie unter <A href="lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md">Konfigurieren der Integration mit Office Web Apps Server und Lync Server 2013</A>.



12. Wählen Sie auf der Seite **Archivierungs-SQL-Speicher definieren** eine vorhandene Instanz von SQL Server aus, oder definieren Sie eine neue Instanz, um die Daten zu speichern, die den Archivierungsdaten zugeordnet sind.

13. Wählen Sie auf der Seite **Monitoring-SQL-Speicher definieren** eine vorhandene Instanz von SQL Server aus, oder definieren Sie eine neue Instanz, um die Daten zu speichern, die den Überwachungsdaten zugeordnet sind.

14. Klicken Sie auf **Weiter** . Wenn Sie auf der Seite **Serverrollen zu diesem Front-End-Pool zuordnen** weitere Rollenserver definiert haben, werden im Assistenten separate Seiten zur Rollenkonfiguration geöffnet, auf denen Sie die Serverrollen konfigurieren können. Ausführliche Informationen finden Sie im Abschnitt:
    
    [Bereitstellen des Zugriffs durch externe Benutzer in Lync Server 2013](lync-server-2013-deploying-external-user-access.md)

15. Wenn Sie keine zusätzlichen Serverrollen ausgewählt haben, die konfiguriert und bereitgestellt werden sollen, oder wenn Sie die Konfiguration der zusätzlichen Rollenserver abgeschlossen haben, klicken Sie auf **Fertig stellen** .

