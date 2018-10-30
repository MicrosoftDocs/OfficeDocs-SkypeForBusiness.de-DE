---
title: 'Lync Server 2013: Beispiel: Zusammenstellen der Anforderungen Ihrer Organisation für die Anrufsteuerung'
TOCTitle: 'Beispiel: Zusammenstellen der Anforderungen Ihrer Organisation für die Anrufsteuerung'
ms:assetid: 3363ac53-b7c4-4a59-aea1-b2f3ee016ae1
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg425827(v=OCS.15)
ms:contentKeyID: 49293618
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Beispiel: Zusammenstellen der Anforderungen Ihrer Organisation für die Anrufsteuerung in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2015-03-09_

Dieses Beispiel führt Sie Schritt für Schritt durch die Planung und Implementierung der Anrufsteuerungsdiensts (Call Admission Control, CAC). Bei diesem Verfahren werden die folgenden allgemeinen Aufgaben ausgeführt:

1.  Identifizieren aller Netzwerkhubs und Backbones (als *Netzwerkregionen* bezeichnet).

2.  Identifizieren des zentralen Lync Server-Standorts, der die Anrufsteuerung für jede Netzwerkregion verwaltet.

3.  Identifizieren und Definieren der *Netzwerkstandorte* , die mit jeder Netzwerkregion verbunden sind.

4.  Für jeden Netzwerkstandort mit eingeschränkter WAN-Bandbreite: Beschreiben der Bandbreitenkapazität der WAN-Verbindung und der Bandbreiteneinschränkungen, die der Netzwerkadministrator für den Lync Server-Mediendatenverkehr festgelegt hat (sofern anwendbar). Standorte mit WAN-Verbindungen ohne Bandbreiteneinschränkung müssen nicht einbezogen werden.

5.  Zuordnen der einzelnen Subnetze in Ihrem Netzwerk zu einem Netzwerkstandort.

6.  Zuordnen der Verbindungen zwischen den Netzwerkregionen. Beschreiben Sie für jede Verbindung die Bandbreitenkapazität und Einschränkungen, die der Netzwerkadministrator für den Lync Server-Mediendatenverkehr definiert hat.

7.  Definieren einer Route zwischen jedem Netzwerkregionenpaar.

## Sammeln der erforderlichen Informationen

Zur Vorbereitung der Anrufsteuerung müssen Sie die in den folgenden Schritten beschriebenen Informationen sammeln:

1.  Identifizieren Sie Ihre Netzwerkregionen. Eine Netzwerkregion repräsentiert einen Netzwerkbackbone oder einen Netzwerkhub.
    
    Ein Netzwerkbackbone oder ein Netzwerkhub ist Bestandteil der Computernetzwerkinfrastruktur, die verschiedene Komponenten im Netzwerk verbindet und einen Pfad für den Austausch von Informationen zwischen unterschiedlichen LANs oder Subnetzen bereitstellt. Ein Backbone kann unterschiedliche Netzwerke miteinander verknüpfen, von kleinen Standorten bis hin zu einem geografisch weit verteilten Bereich. Die Kapazität des Backbones ist in der Regel höher als die der Netzwerke, die mit ihm verbunden sind.
    
    Die hier vorgestellte Beispieltopologie umfasst drei Netzwerkregionen: Nordamerika, EMEA und APAC. Eine Netzwerkregion enthält verschiedene Netzwerkstandorte. Arbeiten Sie mit Ihrem Netzwerkadministrator zusammen, um die Netzwerkregionen für Ihr Unternehmen zu definieren.

2.  Identifizieren Sie den zentralen Standort, dem jede Netzwerkregion zugeordnet ist. Ein zentraler Standort umfasst mindestens einen Front-End-Server und die Lync Server-Bereitstellung, mit der die Anrufsteuerung für den gesamten Mediendatenverkehr verwaltet wird, der über die WAN-Verbindung der Netzwerkregion geleitet wird.
    
    **Beispielunternehmensnetzwerk mit drei Netzwerkregionen**
    
    ![Netzwerktopologiebeispiel mit drei Netzwerkregionen](images/Gg425827.08937347-250f-488f-ba5f-c256e6afcd8b(OCS.15).jpg "Netzwerktopologiebeispiel mit drei Netzwerkregionen")  
    

    > [!NOTE]
    > Ein MPLS-Netzwerk (Multiprotocol Label Switching) sollte als Netzwerkregion abgebildet werden, bei der jeder geografische Standort über einen entsprechenden Netzwerkstandort verfügt. Ausführliche Informationen finden Sie unter <A href="lync-server-2013-call-admission-control-on-an-mpls-network.md">Anrufsteuerung in einem MPLS-Netzwerk mit Lync Server 2013</A> in der Planungsdokumentation.

    
    In der oben gezeigten beispielhaften Netzwerktopologie sind drei Netzwerkregionen aufgeführt, jede mit einem zentralen Lync Server-Standort zur Verwaltung der Anrufsteuerung. Der geeignete zentrale Standort für eine Netzwerkregion wird nach geografischer Nähe ausgewählt. Da innerhalb der Netzwerkregionen das Aufkommen an Mediendatenverkehr am höchsten ist, führt die Festlegung nach geografischer Nähe zu einer eigenständigen Konfiguration, die auch dann noch funktionsfähig ist, wenn andere zentrale Standorte ausfallen.
    
    Im hier verwendeten Beispiel fungiert die Lync Server-Bereitstellung "Chicago" als zentraler Standort für die Region "Nordamerika".
    
    Alle Lync-Benutzer in der Region "Nordamerika" werden auf Servern in der Bereitstellung "Chicago" verwaltet. Die folgende Tabelle zeigt die zentralen Standorte für alle drei Netzwerkregionen.
    
    ### Netzwerkregionen und zugeordnete zentrale Standorte
    
    <table>
    <colgroup>
    <col style="width: 50%" />
    <col style="width: 50%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th>Netzwerkregion</th>
    <th>Zentraler Standort</th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p>Nordamerika</p></td>
    <td><p>Chicago</p></td>
    </tr>
    <tr class="even">
    <td><p>EMEA</p></td>
    <td><p>London</p></td>
    </tr>
    <tr class="odd">
    <td><p>APAC</p></td>
    <td><p>Peking</p></td>
    </tr>
    </tbody>
    </table>
    

    > [!NOTE]
    > In Abhängigkeit von Ihrer Lync Server-Topologie kann derselbe zentrale Standort mehreren Netzwerkregionen zugeordnet werden.



3.  Identifizieren Sie für jede Netzwerkregion alle Netzwerkstandorte (Büros oder Zweigstellen), für deren WAN-Verbindungen keine Bandbreiteneinschränkungen gelten. Da diese Standorte keine Bandbreiteneinschränkungen aufweisen, müssen keine Richtlinien für die Anrufsteuerung auf sie angewendet werden.
    
    Im Beispiel in der folgenden Tabelle gibt es drei Netzwerkstandorte, deren WAN-Verbindungen keine Bandbreiteneinschränkungen aufweisen: "New York", "Chicago" und "Detroit".
    
    ### Netzwerkstandorte ohne Einschränkungen in Bezug auf die WAN-Bandbreite
    
    <table>
    <colgroup>
    <col style="width: 50%" />
    <col style="width: 50%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th>Netzwerkstandort</th>
    <th>Netzwerkregion</th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p>New York</p></td>
    <td><p>Nordamerika</p></td>
    </tr>
    <tr class="even">
    <td><p>Chicago</p></td>
    <td><p>Nordamerika</p></td>
    </tr>
    <tr class="odd">
    <td><p>Detroit</p></td>
    <td><p>Nordamerika</p></td>
    </tr>
    </tbody>
    </table>


4.  Identifizieren Sie für jede Netzwerkregion alle Netzwerkstandorte, die über WAN-Verbindungen mit Bandbreiteneinschränkungen eine Verbindung mit der Netzwerkregion herstellen.
    
    Um die Audio- und Videoqualität besser sicherstellen zu können, wird für diese Netzwerkstandorte mit Bandbreiteneinschränkungen empfohlen, die WAN-Verbindungen zu überwachen und Richtlinien für die Anrufsteuerung anzuwenden, um den Mediendatenverkehr (Sprache oder Video) von und zu der Netzwerkregion zu beschränken.
    
    Im Beispiel in der folgenden Tabelle sind drei Netzwerkstandorte vorhanden, deren WAN-Bandbreite eingeschränkt ist: "Portland", "Reno" und "Albuquerque".
    
    ### Netzwerkstandorte mit Einschränkungen in Bezug auf die WAN-Bandbreite
    
    <table>
    <colgroup>
    <col style="width: 50%" />
    <col style="width: 50%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th>Netzwerkstandort</th>
    <th>Netzwerkregion</th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p>Albuquerque</p></td>
    <td><p>Nordamerika</p></td>
    </tr>
    <tr class="even">
    <td><p>Reno</p></td>
    <td><p>Nordamerika</p></td>
    </tr>
    <tr class="odd">
    <td><p>Portland</p></td>
    <td><p>Nordamerika</p></td>
    </tr>
    </tbody>
    </table>
    
    **Anrufsteuerung in der Netzwerkregion "Nordamerika" mit drei Netzwerkstandorten, die keine Bandbreiteneinschränkung aufweisen (Chicago, New York und Detroit), und drei Netzwerkstandorten mit eingeschränkter WAN-Bandbreite (Portland, Reno und Albuquerque)**
    
    ![Beispiel: Netzwerkstandorte mit Einschränkungen in Bezug auf die WAN-Bandbreite](images/Gg425827.d9d1f231-db4d-4dd7-8fbc-eb0b6d1e705d(OCS.15).jpg "Beispiel: Netzwerkstandorte mit Einschränkungen in Bezug auf die WAN-Bandbreite")  

5.  Ermitteln Sie für jede WAN-Verbindung mit eingeschränkter Bandbreite die folgenden Informationen:
    
      - Bandbreiteneinschränkung gesamt, die Sie für alle gleichzeitigen Audiositzungen festlegen möchten. Wenn eine neue Audiositzung zu einer Überschreitung dieses Grenzwerts führen würde, lässt Lync Server den Start dieser Sitzung nicht zu.
    
      - Bandbreiteneinschränkung, die Sie für jede einzelne Audiositzung festlegen möchten. Die standardmäßige Bandbreiteneinschränkung bei der Anrufsteuerung ist auf 175 KBit/s festgelegt, sie kann jedoch vom Administrator geändert werden.
    
      - Bandbreiteneinschränkung gesamt, die Sie für alle gleichzeitigen Videositzungen festlegen möchten. Wenn eine neue Videositzung zu einer Überschreitung dieses Grenzwerts führen würde, lässt Lync Server den Start dieser Sitzung nicht zu.
    
      - Bandbreiteneinschränkung, die Sie für jede einzelne Videositzung festlegen möchten. Die standardmäßige Bandbreiteneinschränkung bei der Anrufsteuerung ist auf 700 KBit/s festgelegt, sie kann jedoch vom Administrator geändert werden.
    
    ### Netzwerkstandorte mit Informationen zur WAN-Bandbreiteneinschränkung (Bandbreite in KBit/s)
    
    <table style="width:100%;">
    <colgroup>
    <col style="width: 14%" />
    <col style="width: 14%" />
    <col style="width: 14%" />
    <col style="width: 14%" />
    <col style="width: 14%" />
    <col style="width: 14%" />
    <col style="width: 14%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th>Netzwerkstandort</th>
    <th>Netzwerkregion</th>
    <th>Grenzwert für Bandbreite</th>
    <th>Grenzwert für Audio</th>
    <th>Grenzwert für Audiositzung</th>
    <th>Grenzwert für Video</th>
    <th>Grenzwert für Videositzung</th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p>Albuquerque</p></td>
    <td><p>Nordamerika</p></td>
    <td><p>5.000</p></td>
    <td><p>2.000</p></td>
    <td><p>175</p></td>
    <td><p>1.400</p></td>
    <td><p>700</p></td>
    </tr>
    <tr class="even">
    <td><p>Reno</p></td>
    <td><p>Nordamerika</p></td>
    <td><p>10.000</p></td>
    <td><p>4.000</p></td>
    <td><p>175</p></td>
    <td><p>2.800</p></td>
    <td><p>700</p></td>
    </tr>
    <tr class="odd">
    <td><p>Portland</p></td>
    <td><p>Nordamerika</p></td>
    <td><p>5.000</p></td>
    <td><p>4.000</p></td>
    <td><p>175</p></td>
    <td><p>2.800</p></td>
    <td><p>700</p></td>
    </tr>
    <tr class="even">
    <td><p>New York</p></td>
    <td><p>Nordamerika</p></td>
    <td><p>(keine Begrenzung)</p></td>
    <td><p>(keine Begrenzung)</p></td>
    <td><p>(keine Begrenzung)</p></td>
    <td><p>(keine Begrenzung)</p></td>
    <td><p>(keine Begrenzung)</p></td>
    </tr>
    <tr class="odd">
    <td><p>Chicago</p></td>
    <td><p>Nordamerika</p></td>
    <td><p>(keine Begrenzung)</p></td>
    <td><p>(keine Begrenzung)</p></td>
    <td><p>(keine Begrenzung)</p></td>
    <td><p>(keine Begrenzung)</p></td>
    <td><p>(keine Begrenzung)</p></td>
    </tr>
    <tr class="even">
    <td><p>Detroit</p></td>
    <td><p>Nordamerika</p></td>
    <td><p>(keine Begrenzung)</p></td>
    <td><p>(keine Begrenzung)</p></td>
    <td><p>(keine Begrenzung)</p></td>
    <td><p>(keine Begrenzung)</p></td>
    <td><p>(keine Begrenzung)</p></td>
    </tr>
    </tbody>
    </table>


6.  Geben Sie für jedes Subnetz in Ihrem Netzwerk den zugeordneten Netzwerkstandort an.
    

    > [!IMPORTANT]
    > Jedes Subnetz in Ihrem Netzwerk muss einem Netzwerkstandort zugeordnet sein - selbst dann, wenn für den Netzwerkstandort keine Bandbreiteneinschränkungen gelten. Diese Anforderung gilt, da die Anrufsteuerung mithilfe von Subnetzinformationen ermittelt, an welchem Netzwerkstandort sich ein Endpunkt befindet. Wenn die Standorte beider Sitzungsteilnehmer ermittelt wurden, kann über die Anrufsteuerung festgestellt werden, ob genügend Bandbreite für einen Anruf vorhanden ist. Wird eine Sitzung über eine Verbindung ohne Bandbreiteneinschränkungen hergestellt, wird eine Warnung generiert.<BR>Wenn Sie A/V-Edgeserver (Audio/Video) bereitstellen, müssen die öffentlichen IP-Adressen der jeweiligen Edgeserver dem Netzwerkstandort zugeordnet werden, in dem der Edgeserver bereitgestellt wurde. Jede öffentliche IP-Adresse des A/V-Edgeservers muss in den Netzwerkkonfigurationseinstellungen als Subnetz mit der Subnetzmaske&nbsp;32 hinzugefügt werden. Wenn Sie beispielsweise A/V-Edgeserver in Chicago bereitstellen, müssen Sie für jede externe IP-Adresse dieser Server ein Subnetz mit der Subnetzmaske&nbsp;32 erstellen und Netzwerkstandort "Chicago" diesen Subnetzen zuordnen. Ausführliche Informationen zu öffentlichen IP-Adressen finden Sie unter <A href="lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md">Ermitteln der Anforderungen für externe A/V-Firewalls und Ports für Lync Server 2013</A> in der Planungsdokumentation.

    

    > [!NOTE]
    > Es wird eine KHI-Warnung (Key Health Indicator) ausgegeben. Diese enthält eine Liste der IP-Adressen, die in Ihrem Netzwerk vorhanden, aber keinem Subnetz zugeordnet sind, oder gibt das Subnetz an, das die IP-Adressen enthält, jedoch keinem Netzwerkstandort zugeordnet ist. Diese Warnung wird innerhalb von 8&nbsp;Stunden nur einmal angezeigt. Nachfolgend finden Sie die relevanten Warnungsinformationen und ein Beispiel:<BR><STRONG>Quelle :</STRONG> CS-Bandbreitenrichtliniendienst (Core)<BR><STRONG>Ereignisnummer :</STRONG> 36034<BR><STRONG>Ebene :</STRONG> 2<BR><STRONG>Beschreibung :</STRONG> Die Subnetze für die folgenden IP-Adressen: &lt;Liste der IP-Adressen&gt; ist entweder nicht konfiguriert, oder die Subnetze sind keinem Netzwerkstandort zugeordnet.<BR><STRONG>Ursache :</STRONG> Die Subnetze für die zugehörigen IP-Adressen fehlen in den Netzwerkkonfigurationseinstellungen, oder die Subnetze sind keinem Netzwerkstandort zugeordnet.<BR><STRONG>Lösung :</STRONG> Fügen Sie gemäß der IP-Adressenliste den Netzwerkkonfigurationseinstellungen Subnetze hinzu, und ordnen Sie jedes Subnetz einem Netzwerkstandort zu.<BR>Wenn die Liste der IP-Adressen beispielsweise die Einträge 10.121.248.226 und 10.121.249.20 enthält, sind diese IP-Adressen entweder keinem Subnetz zugeordnet, oder das zugeordnete Subnetz gehört keinem Netzwerkstandort an. Wenn die zugehörigen Subnetze für diese Adressen 10.121.248.0/24 und 10.121.249.0/24 lauten, können Sie das Problem wie folgt lösen: 
    > <OL>
    > <LI>
    > <P>Stellen Sie sicher, dass die IP-Adresse 10.121.248.226 dem Subnetz 10.121.248.0/24 und die IP-Adresse 10.121.249.20 dem Subnetz 10.121.249.0/24 zugeordnet ist.</P>
    > <LI>
    > <P>Stellen Sie sicher, dass die Subnetze 10.121.248.0/24 und 10.121.249.0/24 jeweils einem Netzwerkstandort zugeordnet sind.</P></LI></OL>

    
    ### Netzwerkstandorte und zugeordnete Subnetze (Bandbreite in KBit/s)
    
    <table>
    <colgroup>
    <col style="width: 12%" />
    <col style="width: 12%" />
    <col style="width: 12%" />
    <col style="width: 12%" />
    <col style="width: 12%" />
    <col style="width: 12%" />
    <col style="width: 12%" />
    <col style="width: 12%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th>Netzwerkstandort</th>
    <th>Netzwerkregion</th>
    <th>Grenzwert für Bandbreite</th>
    <th>Grenzwert für Audio</th>
    <th>Grenzwert für Audiositzung</th>
    <th>Grenzwert für Video</th>
    <th>Grenzwert für Videositzung</th>
    <th>Subnetze</th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p>Albuquerque</p></td>
    <td><p>Nordamerika</p></td>
    <td><p>5.000</p></td>
    <td><p>2.000</p></td>
    <td><p>175</p></td>
    <td><p>1.400</p></td>
    <td><p>700</p></td>
    <td><p>172.29.79.0/23, 157.57.215.0/25, 172.29.90.0/23, 172.29.80.0/24</p></td>
    </tr>
    <tr class="even">
    <td><p>Reno</p></td>
    <td><p>Nordamerika</p></td>
    <td><p>10.000</p></td>
    <td><p>4.000</p></td>
    <td><p>175</p></td>
    <td><p>2.800</p></td>
    <td><p>700</p></td>
    <td><p>157.57.210.0/23, 172.28.151.128/25</p></td>
    </tr>
    <tr class="odd">
    <td><p>Portland</p></td>
    <td><p>Nordamerika</p></td>
    <td><p>5.000</p></td>
    <td><p>4.000</p></td>
    <td><p>175</p></td>
    <td><p>2.800</p></td>
    <td><p>700</p></td>
    <td><p>172.29.77.0/24 10.71.108.0/24, 157.57.208.0/23</p></td>
    </tr>
    <tr class="even">
    <td><p>New York</p></td>
    <td><p>Nordamerika</p></td>
    <td><p>(keine Begrenzung)</p></td>
    <td><p>(keine Begrenzung)</p></td>
    <td><p>(keine Begrenzung)</p></td>
    <td><p>(keine Begrenzung)</p></td>
    <td><p>(keine Begrenzung)</p></td>
    <td><p>172.29.80.0/23, 157.57.216.0/25, 172.29.91.0/23, 172.29.81.0/24</p></td>
    </tr>
    <tr class="odd">
    <td><p>Chicago</p></td>
    <td><p>Nordamerika</p></td>
    <td><p>(keine Begrenzung)</p></td>
    <td><p>(keine Begrenzung)</p></td>
    <td><p>(keine Begrenzung)</p></td>
    <td><p>(keine Begrenzung)</p></td>
    <td><p>(keine Begrenzung)</p></td>
    <td><p>157.57.211.0/23, 172.28.152.128/25</p></td>
    </tr>
    <tr class="even">
    <td><p>Detroit</p></td>
    <td><p>Nordamerika</p></td>
    <td><p>(keine Begrenzung)</p></td>
    <td><p>(keine Begrenzung)</p></td>
    <td><p>(keine Begrenzung)</p></td>
    <td><p>(keine Begrenzung)</p></td>
    <td><p>(keine Begrenzung)</p></td>
    <td><p>172.29.78.0/24 10.71.109.0/24, 157.57.209.0/23</p></td>
    </tr>
    </tbody>
    </table>


7.  Bei der Lync Server-Anrufsteuerung werden die Verbindungen zwischen Netzwerkregionen als *Regionenverbindungen* bezeichnet. Ermitteln Sie für jede Regionenverbindung, ebenso wie für die Netzwerkstandorte, die folgenden Informationen:
    
      - Bandbreiteneinschränkung gesamt, die Sie für alle gleichzeitigen Audiositzungen festlegen möchten. Wenn eine neue Audiositzung zu einer Überschreitung dieses Grenzwerts führen würde, lässt Lync Server den Start dieser Sitzung nicht zu.
    
      - Bandbreiteneinschränkung, die Sie für jede einzelne Audiositzung festlegen möchten. Die standardmäßige Bandbreiteneinschränkung bei der Anrufsteuerung ist auf 175 KBit/s festgelegt, sie kann jedoch vom Administrator geändert werden.
    
      - Bandbreiteneinschränkung gesamt, die Sie für alle gleichzeitigen Videositzungen festlegen möchten. Wenn eine neue Videositzung zu einer Überschreitung dieses Grenzwerts führen würde, lässt Lync Server den Start dieser Sitzung nicht zu.
    
      - Bandbreiteneinschränkung, die Sie für jede einzelne Videositzung festlegen möchten. Die standardmäßige Bandbreiteneinschränkung bei der Anrufsteuerung ist auf 700 KBit/s festgelegt, sie kann jedoch vom Administrator geändert werden.
    
    **Netzwerkregionenverbindungen mit zugehörigen Bandbreiteneinschränkungen**
    
    ![Beispiel für Einschränkungen zwischen drei Regionen](images/Gg425827.25259afa-ee7c-4d26-bc41-92ba9cb56dec(OCS.15).jpg "Beispiel für Einschränkungen zwischen drei Regionen")  
    
    ### Bandbreiteninformationen zu Regionenverbindungen (Bandbreite in KBit/s)
    
    <table>
    <colgroup>
    <col style="width: 12%" />
    <col style="width: 12%" />
    <col style="width: 12%" />
    <col style="width: 12%" />
    <col style="width: 12%" />
    <col style="width: 12%" />
    <col style="width: 12%" />
    <col style="width: 12%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th>Name der Regionenverbindung</th>
    <th>Erste Region</th>
    <th>Zweite Region</th>
    <th>Grenzwert für Bandbreite</th>
    <th>Grenzwert für Audio</th>
    <th>Grenzwert für Audiositzung</th>
    <th>Grenzwert für Video</th>
    <th>Grenzwert für Videositzung</th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p>NA-EMEA-LINK</p></td>
    <td><p>Nordamerika</p></td>
    <td><p>EMEA</p></td>
    <td><p>50.000</p></td>
    <td><p>20.000</p></td>
    <td><p>175</p></td>
    <td><p>14.000</p></td>
    <td><p>700</p></td>
    </tr>
    <tr class="even">
    <td><p>EMEA-APAC-LINK</p></td>
    <td><p>EMEA</p></td>
    <td><p>APAC</p></td>
    <td><p>25.000</p></td>
    <td><p>10.000</p></td>
    <td><p>175</p></td>
    <td><p>7.000</p></td>
    <td><p>700</p></td>
    </tr>
    </tbody>
    </table>


8.  Definieren einer Route zwischen jedem Netzwerkregionenpaar.
    

    > [!NOTE]
    > Für die Route zwischen den Regionen "Nordamerika" und "APAC" sind zwei Verbindungen erforderlich, da keine Region vorhanden ist, die die Regionen direkt miteinander verbindet.

    
    ### Routen zwischen Regionen
    
    <table>
    <colgroup>
    <col style="width: 25%" />
    <col style="width: 25%" />
    <col style="width: 25%" />
    <col style="width: 25%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th>Name der Regionenroute</th>
    <th>Erste Region</th>
    <th>Zweite Region</th>
    <th>Regionenverbindungen</th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p>NA-EMEA-ROUTE</p></td>
    <td><p>Nordamerika</p></td>
    <td><p>EMEA</p></td>
    <td><p>NA-EMEA-LINK</p></td>
    </tr>
    <tr class="even">
    <td><p>EMEA-APAC-ROUTE</p></td>
    <td><p>EMEA</p></td>
    <td><p>APAC</p></td>
    <td><p>EMEA-APAC-LINK</p></td>
    </tr>
    <tr class="odd">
    <td><p>NA-APAC-ROUTE</p></td>
    <td><p>Nordamerika</p></td>
    <td><p>APAC</p></td>
    <td><p>NA-EMEA-LINK, EMEA-APAC-LINK</p></td>
    </tr>
    </tbody>
    </table>


9.  Ermitteln Sie für jedes Netzwerkstandortpaar, das durch eine einzelne Verbindung direkt miteinander verbunden wird (als *standortübergreifende* Verbindung bezeichnet), die folgenden Informationen:
    
      - Bandbreiteneinschränkung gesamt, die Sie für alle gleichzeitigen Audiositzungen festlegen möchten. Wenn eine neue Audiositzung zu einer Überschreitung dieses Grenzwerts führen würde, lässt Lync Server den Start dieser Sitzung nicht zu.
    
      - Bandbreiteneinschränkung, die Sie für jede einzelne Audiositzung festlegen möchten. Die standardmäßige Bandbreiteneinschränkung bei der Anrufsteuerung ist auf 175 KBit/s festgelegt, sie kann jedoch vom Administrator geändert werden.
    
      - Bandbreiteneinschränkung gesamt, die Sie für alle gleichzeitigen Videositzungen festlegen möchten. Wenn eine neue Videositzung zu einer Überschreitung dieses Grenzwerts führen würde, lässt Lync Server den Start dieser Sitzung nicht zu.
    
      - Bandbreiteneinschränkung, die Sie für jede einzelne Videositzung festlegen möchten. Die standardmäßige Bandbreiteneinschränkung bei der Anrufsteuerung ist auf 700 KBit/s festgelegt, sie kann jedoch vom Administrator geändert werden.
    
    **Anrufsteuerung in der Netzwerkregion "Nordamerika" mit Anzeige der Bandbreitenkapazitäten und -einschränkungen für die standortübergreifende Verbindung zwischen Reno und Albuquerque**
    
    ![Netzwerkstandorte mit Einschränkungen in Bezug auf die WAN-Bandbreite (Beispiel)](images/Gg425827.063e5e1d-b6c8-4e8c-98db-c227c78f671d(OCS.15).jpg "Netzwerkstandorte mit Einschränkungen in Bezug auf die WAN-Bandbreite (Beispiel)")  
    
    ### Bandbreiteninformationen für eine standortübergreifende Verbindung zwischen zwei Netzwerkstandorten (Bandbreite in KBit/s)
    
    <table>
    <colgroup>
    <col style="width: 12%" />
    <col style="width: 12%" />
    <col style="width: 12%" />
    <col style="width: 12%" />
    <col style="width: 12%" />
    <col style="width: 12%" />
    <col style="width: 12%" />
    <col style="width: 12%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th>Name der standortübergreifenden Verbindung</th>
    <th>Erster Standort</th>
    <th>Zweiter Standort</th>
    <th>Grenzwert für Bandbreite</th>
    <th>Grenzwert für Audio</th>
    <th>Grenzwert für Audiositzung</th>
    <th>Grenzwert für Video</th>
    <th>Grenzwert für Videositzung</th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p>Reno-Albu-Intersite-Link</p></td>
    <td><p>Reno</p></td>
    <td><p>Albuquerque</p></td>
    <td><p>20.000</p></td>
    <td><p>12.000</p></td>
    <td><p>175</p></td>
    <td><p>5.000</p></td>
    <td><p>700</p></td>
    </tr>
    </tbody>
    </table>


## Nächste Schritte

Nachdem Sie die erforderlichen Informationen zusammengetragen haben, können Sie die Anrufsteuerung entweder mit der Lync Server-Verwaltungsshell oder der Lync Server-Systemsteuerung bereitstellen.


> [!NOTE]
> Wenngleich Sie mit der Lync Server-Systemsteuerung die meisten Aufgaben in Bezug auf die Netzwerkkonfiguration ausführen können, müssen Sie zum Erstellen von Subnetzen und standortübergreifenden Verbindungen die Lync Server-Verwaltungsshell verwenden. Ausführliche Informationen finden Sie in der Lync Server-Verwaltungsshell-Dokumentation für das Cmdlet <STRONG>New-CsNetworkSubnet</STRONG> und das Cmdlet <STRONG>New-CsNetworkIntersitePolicy</STRONG>.


