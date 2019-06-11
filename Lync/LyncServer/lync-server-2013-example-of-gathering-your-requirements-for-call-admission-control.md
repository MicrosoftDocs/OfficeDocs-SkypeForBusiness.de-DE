---
title: Beispiel für die Erfassung Ihrer Anforderungen für die Anrufsteuerung
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Example of gathering your requirements for call admission control
ms:assetid: 3363ac53-b7c4-4a59-aea1-b2f3ee016ae1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425827(v=OCS.15)
ms:contentKeyID: 48183820
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e17d9abb0387f0d77c696487558dec0c915b1651
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34832218"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="example-gathering-your-requirements-for-call-admission-control-in-lync-server-2013"></a>Beispiel: Erfassen Ihrer Anforderungen für die Anrufsteuerung in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2012-09-21_

Dieses Beispiel führt Sie Schritt für Schritt durch die Planung und Implementierung des Anrufsteuerungsdiensts (Call Admission Control, CAC). Bei diesem Verfahren werden die folgenden allgemeinen Aufgaben ausgeführt:

1.  Identifizieren aller Netzwerkhubs und Backbones (als *Netzwerkregionen* bezeichnet).

2.  Ermitteln Sie die lync Server Central-Website, die die CAC für jede netzwerkregion verwaltet.

3.  Identifizieren und Definieren der *Netzwerkstandorte*, die mit jeder Netzwerkregion verbunden sind.

4.  Beschreiben Sie für jede Netzwerk Website, deren Verbindung mit dem WAN von der Bandbreite abhängig ist, die Bandbreitenkapazität der WAN-Verbindung und die Bandbreitenbeschränkungen, die der Netzwerkadministrator für den lync Server-Mediendatenverkehr festgelegt hat (falls zutreffend). Standorte mit WAN-Verbindungen ohne Bandbreiteneinschränkung müssen nicht einbezogen werden.

5.  Zuordnen der einzelnen Subnetze in Ihrem Netzwerk zu einem Netzwerkstandort.

6.  Zuordnen der Verbindungen zwischen den Netzwerkregionen. Beschreiben Sie für jeden Link die Bandbreitenkapazität sowie alle Einschränkungen, die der Netzwerkadministrator für den Mediendatenverkehr in lync Server festgelegt hat.

7.  Definieren einer Route zwischen jedem Netzwerkregionenpaar.

<div>

## <a name="gather-the-required-information"></a>Sammeln der erforderlichen Informationen

Zur Vorbereitung der Anrufsteuerung müssen Sie die in den folgenden Schritten beschriebenen Informationen sammeln:

1.  Identifizieren Sie Ihre Netzwerkregionen. Eine Netzwerkregion repräsentiert einen Netzwerkbackbone oder einen Netzwerkhub.
    
    Ein Netzwerkbackbone oder ein Netzwerkhub ist Bestandteil der Computernetzwerkinfrastruktur, die verschiedene Komponenten im Netzwerk verbindet und einen Pfad für den Austausch von Informationen zwischen unterschiedlichen LANs oder Subnetzen bereitstellt. Ein Backbone kann unterschiedliche Netzwerke miteinander verknüpfen, von kleinen Standorten bis hin zu einem geografisch weit verteilten Bereich. Die Kapazität des Backbones ist in der Regel höher als die der Netzwerke, die mit ihm verbunden sind.
    
    Die hier vorgestellte Beispieltopologie umfasst drei Netzwerkregionen: Nordamerika, EMEA und APAC. Eine Netzwerkregion enthält verschiedene Netzwerkstandorte. Arbeiten Sie mit Ihrem Netzwerkadministrator zusammen, um die Netzwerkregionen für Ihr Unternehmen zu definieren.

2.  Identifizieren Sie den zentralen Standort, dem jede Netzwerkregion zugeordnet ist. Eine zentrale Website enthält mindestens einen Front-End-Server und ist die lync Server-Bereitstellung, die CAC für den gesamten Mediendatenverkehr verwaltet, der die WAN-Verbindung des Netzwerkbereichs durchläuft.
    
    **Beispielunternehmensnetzwerk mit drei Netzwerkregionen**
    
    ![Beispiel für eine Netzwerktopologie mit 3 netzwerkregionen] (images/Gg425827.08937347-250f-488f-ba5f-c256e6afcd8b(OCS.15).jpg "Beispiel für eine Netzwerktopologie mit 3 netzwerkregionen")  
    
    <div>
    

    > [!NOTE]
    > Ein MPLS-Netzwerk (Multiprotocol Label Switching) sollte als Netzwerkregion abgebildet werden, bei der jeder geografische Standort über einen entsprechenden Netzwerkstandort verfügt. Ausführliche Informationen finden Sie in der Planungsdokumentation unter dem Thema "<A href="lync-server-2013-call-admission-control-on-an-mpls-network.md">Anrufsteuerung in einem MPLS-Netzwerk mit lync Server 2013</A>".

    
    </div>
    
    In der vorhergehenden Beispiel-Netzwerktopologie gibt es drei netzwerkregionen, die jeweils einen zentralen lync Server-Standort aufweisen, der CAC verwaltet. Der geeignete zentrale Standort für eine Netzwerkregion wird nach geografischer Nähe ausgewählt. Da innerhalb der Netzwerkregionen das Aufkommen an Mediendatenverkehr am höchsten ist, führt die Festlegung nach geografischer Nähe zu einer eigenständigen Konfiguration, die auch dann noch funktionsfähig ist, wenn andere zentrale Standorte ausfallen.
    
    In diesem Beispiel ist eine lync Server-Bereitstellung mit dem Namen Chicago der zentrale Standort für die Region Nordamerika.
    
    Alle lync-Benutzer in Nordamerika sind in der Chicago-Bereitstellung auf Servern verwaltet. Die folgende Tabelle zeigt die zentralen Standorte für alle drei Netzwerkregionen.
    
    ### <a name="network-regions-and-their-associated-central-sites"></a>Netzwerkregionen und zugeordnete zentrale Standorte
    
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
    
    <div>
    

    > [!NOTE]
    > Je nach lync Server-Topologie kann derselbe zentrale Standort mehreren netzwerkregionen zugewiesen werden.

    
    </div>

3.  Identifizieren Sie für jede Netzwerkregion alle Netzwerkstandorte (Büros oder Zweigstellen), für deren WAN-Verbindungen keine Bandbreiteneinschränkungen gelten. Da diese Standorte keine Bandbreiteneinschränkungen aufweisen, müssen keine Richtlinien für die Anrufsteuerung auf sie angewendet werden.
    
    Im Beispiel in der folgenden Tabelle gibt es drei Netzwerkstandorte, deren WAN-Verbindungen keine Bandbreiteneinschränkungen aufweisen: „New York“, „Chicago“ und „Detroit“.
    
    ### <a name="network-sites-not-constrained-by-wan-bandwidth"></a>Netzwerkstandorte ohne Einschränkungen in Bezug auf die WAN-Bandbreite
    
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
    
    Im Beispiel in der folgenden Tabelle sind drei Netzwerkstandorte vorhanden, deren WAN-Bandbreite eingeschränkt ist: „Portland“, „Reno“ und „Albuquerque“.
    
    ### <a name="network-sites-constrained-by-wan-bandwidth"></a>Netzwerkstandorte mit Einschränkungen in Bezug auf die WAN-Bandbreite
    
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
    
    **Anrufsteuerung in der Netzwerkregion „Nordamerika“ mit drei Netzwerkstandorten, die keine Bandbreiteneinschränkung aufweisen (Chicago, New York und Detroit), und drei Netzwerkstandorten mit eingeschränkter WAN-Bandbreite (Portland, Reno und Albuquerque)**
    
    ![Beispiel für Netzwerk Websites, die durch WAN-Bandbreite beschränkt] sind (images/Gg425827.d9d1f231-db4d-4dd7-8fbc-eb0b6d1e705d(OCS.15).jpg "Beispiel für Netzwerk Websites, die durch WAN-Bandbreite beschränkt") sind  

5.  Ermitteln Sie für jede WAN-Verbindung mit eingeschränkter Bandbreite die folgenden Informationen:
    
      - Die gesamte Bandbreiteneinschränkung, die Sie für alle gleichzeitigen Audiositzungen festlegen möchten. Wenn diese Grenze durch eine neue Audiositzung überschritten wird, lässt Lync Server den Start der Sitzung nicht zu.
    
      - Die Bandbreiteneinschränkung, die Sie für jede einzelne Audiositzung festlegen möchten. Die standardmäßige Bandbreiteneinschränkung bei der Anrufsteuerung ist auf 175 KBit/s festgelegt, sie kann jedoch vom Administrator geändert werden.
    
      - Die gesamte Bandbreiteneinschränkung, die Sie für alle gleichzeitigen Videositzungen festlegen möchten. Wenn diese Grenze durch eine neue Videositzung überschritten wird, lässt Lync Server den Start der Sitzung nicht zu.
    
      - Die Bandbreiteneinschränkung, die Sie für jede einzelne Videositzung festlegen möchten. Die standardmäßige Bandbreiteneinschränkung bei der Anrufsteuerung ist auf 700 KBit/s festgelegt, sie kann jedoch vom Administrator geändert werden.
    
    ### <a name="network-sites-with-wan-bandwidth-constraint-information-bandwidth-in-kbps"></a>Netzwerkstandorte mit Informationen zur WAN-Bandbreiteneinschränkung (Bandbreite in KBit/s)
    
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
    
    <div>
    

    > [!IMPORTANT]
    > Jedes Subnetz in Ihrem Netzwerk muss einem Netzwerkstandort zugeordnet sein - selbst dann, wenn für den Netzwerkstandort keine Bandbreiteneinschränkungen gelten. Diese Anforderung gilt, da die Anrufsteuerung mithilfe von Subnetzinformationen ermittelt, an welchem Netzwerkstandort sich ein Endpunkt befindet. Wenn die Standorte beider Sitzungsteilnehmer ermittelt wurden, kann über die Anrufsteuerung festgestellt werden, ob genügend Bandbreite für einen Anruf vorhanden ist. Wird eine Sitzung über eine Verbindung ohne Bandbreiteneinschränkungen hergestellt, wird eine Warnung generiert.<BR>Wenn Sie A/V-Edgeserver (Audio/Video) bereitstellen, müssen die öffentlichen IP-Adressen der jeweiligen Edgeserver dem Netzwerkstandort zugeordnet werden, in dem der Edgeserver bereitgestellt wurde. Jede öffentliche IP-Adresse des A/V-Edgeservers muss in den Netzwerkkonfigurationseinstellungen als Subnetz mit der Subnetzmaske 32 hinzugefügt werden. Wenn Sie beispielsweise A/V-Edgeserver in Chicago bereitstellen, müssen Sie für jede externe IP-Adresse dieser Server ein Subnetz mit der Subnetzmaske 32 erstellen und den Netzwerkstandort „Chicago“ diesen Subnetzen zuordnen. Details zu öffentlichen IP-Adressen finden Sie unter <A href="lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md">Ermitteln der externen A/V-Firewall und Portanforderungen für lync Server 2013</A> in der Planungsdokumentation.

    
    </div>
    
    <div>
    

    > [!NOTE]
    > Es wird eine KHI-Warnung (Key Health Indicator) ausgegeben. Diese enthält eine Liste der IP-Adressen, die in Ihrem Netzwerk vorhanden, aber keinem Subnetz zugeordnet sind, oder gibt das Subnetz an, das die IP-Adressen enthält, jedoch keinem Netzwerkstandort zugeordnet ist. Diese Warnung wird innerhalb von 8 Stunden nur einmal angezeigt. Nachfolgend finden Sie die relevanten Warnungsinformationen und ein Beispiel:<BR><STRONG>Quelle:</STRONG> CS-bandbreitenrichtliniendienst (Core)<BR><STRONG>Ereignisnummer:</STRONG> 36034<BR><STRONG>Stufe:</STRONG> 2<BR><STRONG>Beschreibung:</STRONG> Die Subnetze für die folgenden IP- &lt;Adressen: die Liste&gt; der IP-Adressen ist entweder nicht konfiguriert, oder die Subnetze sind nicht mit einer Netzwerk Website verbunden.<BR><STRONG>Ursache:</STRONG> Die Subnetze für die entsprechenden IP-Adressen fehlen in den Netzwerkkonfigurationseinstellungen, oder die Subnetze sind nicht mit einer Netzwerk Website verbunden.<BR><STRONG>Auflösung:</STRONG> Fügen Sie den Netzwerkkonfigurationseinstellungen Subnetze hinzu, die der vorhergehenden Liste der IP-Adressen entsprechen, und ordnen Sie jedes Subnetz einer Netzwerk Website zu.<BR>Wenn die Liste der IP-Adressen beispielsweise die Einträge 10.121.248.226 und 10.121.249.20 enthält, sind diese IP-Adressen entweder keinem Subnetz zugeordnet oder das zugeordnete Subnetz gehört keinem Netzwerkstandort an. Wenn die zugehörigen Subnetze für diese Adressen 10.121.248.0/24 und 10.121.249.0/24 lauten, können Sie das Problem wie folgt lösen: 
    > <OL>
    > <LI>
    > <P>Stellen Sie sicher, dass die IP-Adresse 10.121.248.226 dem Subnetz 10.121.248.0/24 und die IP-Adresse 10.121.249.20 dem Subnetz 10.121.249.0/24 zugeordnet ist.</P>
    > <LI>
    > <P>Stellen Sie sicher, dass die Subnetze 10.121.248.0/24 und 10.121.249.0/24 jeweils einem Netzwerkstandort zugeordnet sind.</P></LI></OL>

    
    </div>
    
    ### <a name="network-sites-and-associated-subnets-bandwidth-in-kbps"></a>Netzwerkstandorte und zugeordnete Subnetze (Bandbreite in KBit/s)
    
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


7.  In der lync Server-Anruf Zulassungs Steuerung werden die Verbindungen zwischen netzwerkregionen als *Regions Verknüpfungen*bezeichnet. Ermitteln Sie für jede Regionenverbindung, ebenso wie für die Netzwerkstandorte, die folgenden Informationen:
    
      - Die gesamte Bandbreiteneinschränkung, die Sie für alle gleichzeitigen Audiositzungen festlegen möchten. Wenn diese Grenze durch eine neue Audiositzung überschritten wird, lässt Lync Server den Start der Sitzung nicht zu.
    
      - Die Bandbreiteneinschränkung, die Sie für jede einzelne Audiositzung festlegen möchten. Die standardmäßige Bandbreiteneinschränkung bei der Anrufsteuerung ist auf 175 KBit/s festgelegt, sie kann jedoch vom Administrator geändert werden.
    
      - Die gesamte Bandbreiteneinschränkung, die Sie für alle gleichzeitigen Videositzungen festlegen möchten. Wenn diese Grenze durch eine neue Videositzung überschritten wird, lässt Lync Server den Start der Sitzung nicht zu.
    
      - Die Bandbreiteneinschränkung, die Sie für jede einzelne Videositzung festlegen möchten. Die standardmäßige Bandbreiteneinschränkung bei der Anrufsteuerung ist auf 700 KBit/s festgelegt, sie kann jedoch vom Administrator geändert werden.
    
    **Netzwerkregionenverbindungen mit zugehörigen Bandbreiteneinschränkungen**
    
    ![Beispiel für Einschränkungen zwischen drei Regionen] (images/Gg425827.25259afa-ee7c-4d26-bc41-92ba9cb56dec(OCS.15).jpg "Beispiel für Einschränkungen zwischen drei Regionen")  
    
    ### <a name="region-link-bandwidth-information-bandwidth-in-kbps"></a>Bandbreiteninformationen zu Regionenverbindungen (Bandbreite in KBit/s)
    
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
    
    <div>
    

    > [!NOTE]
    > Für die Route zwischen den Regionen „Nordamerika“ und „APAC“ sind zwei Verbindungen erforderlich, da keine Region vorhanden ist, die die Regionen direkt miteinander verbindet.

    
    </div>
    
    ### <a name="region-routes"></a>Routen zwischen Regionen
    
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
    
      - Die gesamte Bandbreiteneinschränkung, die Sie für alle gleichzeitigen Audiositzungen festlegen möchten. Wenn diese Grenze durch eine neue Audiositzung überschritten wird, lässt Lync Server den Start der Sitzung nicht zu.
    
      - Die Bandbreiteneinschränkung, die Sie für jede einzelne Audiositzung festlegen möchten. Die standardmäßige Bandbreiteneinschränkung bei der Anrufsteuerung ist auf 175 KBit/s festgelegt, sie kann jedoch vom Administrator geändert werden.
    
      - Die gesamte Bandbreiteneinschränkung, die Sie für alle gleichzeitigen Videositzungen festlegen möchten. Wenn diese Grenze durch eine neue Videositzung überschritten wird, lässt Lync Server den Start der Sitzung nicht zu.
    
      - Die Bandbreiteneinschränkung, die Sie für jede einzelne Videositzung festlegen möchten. Die standardmäßige Bandbreiteneinschränkung bei der Anrufsteuerung ist auf 700 KBit/s festgelegt, sie kann jedoch vom Administrator geändert werden.
    
    **Anrufsteuerung in der Netzwerkregion „Nordamerika“ mit Anzeige der Bandbreitenkapazitäten und -einschränkungen für die standortübergreifende Verbindung zwischen Reno und Albuquerque**
    
    ![Netzwerk Websites, die durch das WAN-Bandbreite-Beispiel beschränkt] sind (images/Gg425827.063e5e1d-b6c8-4e8c-98db-c227c78f671d(OCS.15).jpg "Netzwerk Websites, die durch das WAN-Bandbreite-Beispiel beschränkt") sind  
    
    ### <a name="bandwidth-information-for-an-inter-site-link-between-two-network-sites-bandwidth-in-kbps"></a>Bandbreiteninformationen für eine standortübergreifende Verbindung zwischen zwei Netzwerkstandorten (Bandbreite in KBit/s)
    
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


<div>

## <a name="next-steps"></a>Nächste Schritte

Nachdem Sie die erforderlichen Informationen gesammelt haben, können Sie die CAC-Bereitstellung entweder mithilfe der lync Server-Verwaltungsshell oder der lync Server-Systemsteuerung durchführen.

<div>


> [!NOTE]
> Obwohl Sie die meisten Netzwerk Konfigurationsaufgaben mithilfe der lync Server-Systemsteuerung ausführen können, müssen Sie zum Erstellen von Subnetzen und standortübergreifenden Links die lync Server-Verwaltungsshell verwenden. Ausführliche Informationen finden Sie in der Dokumentation zur lync Server-Verwaltungsshell für das Cmdlet <STRONG>New-CsNetworkSubnet</STRONG> und das Cmdlet <STRONG>New-CsNetworkIntersitePolicy</STRONG> .



</div>

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

