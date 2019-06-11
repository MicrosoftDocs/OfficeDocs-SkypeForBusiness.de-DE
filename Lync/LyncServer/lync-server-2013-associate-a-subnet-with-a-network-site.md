---
title: 'Lync Server 2013: Zuordnen eines Subnetzes zu einem Netzwerkstandort'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Associate a subnet with a network site
ms:assetid: aa69e3ac-542a-4ba1-9582-2e6bee29f633
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412804(v=OCS.15)
ms:contentKeyID: 48185043
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ec5a896af6312fecf53259ac10e72f99598d4a7e
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34839915"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="associate-a-subnet-with-a-network-site-in-lync-server-2013"></a>Zuordnen eines Subnetzes zu einem Netzwerkstandort in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2012-10-19_

Jedes Subnetz in Ihrem Netzwerk muss einem bestimmten Netzwerkstandort zugeordnet sein, da mithilfe von Subnetzinformationen der Netzwerkstandort ermittelt wird, an dem sich ein Endpunkt befindet, während eine neuen Sitzung initiiert wird. Wenn die Position jeder Partei in einer Sitzung bekannt ist, können erweiterte Enterprise-VoIP-Features diese Informationen anwenden, um festzulegen, wie die Anrufeinrichtung oder das Routing gehandhabt werden soll.

<div>


> [!IMPORTANT]  
> Alle konfigurierten öffentlichen IP-Adressen der Audio-Video-Edgeserver in Ihrer Bereitstellung müssen den Netzwerkkonfigurationseinstellungen hinzugefügt werden. Diese IP-Adressen werden als Subnetze mit der Maske 32 hinzugefügt. Der zugeordnete Netzwerkstandort muss dem jeweiligen konfigurierten Netzwerkstandort entsprechen. Beispielsweise wäre die öffentliche IP-Adresse, die dem A/V-Edgeserver auf dem zentralen Standort Chicago entspricht, NetworkSiteID Chicago. Details zu öffentlichen IP-Adressen finden Sie unter <A href="lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md">Ermitteln der externen A/V-Firewall und Portanforderungen für lync Server 2013</A> in der Planungsdokumentation.



</div>

<div>


> [!NOTE]  
> Es wird eine KHI-Warnung (Key Health Indicator) ausgegeben. Diese enthält eine Liste der IP-Adressen, die in Ihrem Netzwerk vorhanden, aber keinem Subnetz zugeordnet sind oder sie gibt das Subnetz an, das die IP-Adressen enthält, jedoch keinem Netzwerkstandort zugeordnet ist. Diese Warnung wird innerhalb von acht Stunden nur einmal angezeigt. Nachfolgend finden Sie die relevanten Warnungsinformationen und ein Beispiel:<BR><STRONG>Quelle:</STRONG> CS-bandbreitenrichtliniendienst (Core)<BR><STRONG>Ereignisnummer:</STRONG> 36034<BR><STRONG>Stufe:</STRONG> 2<BR><STRONG>Beschreibung:</STRONG> Die Subnetze für die folgenden IP- &lt;Adressen: die Liste&gt; der IP-Adressen ist entweder nicht konfiguriert, oder die Subnetze sind nicht mit einer Netzwerk Website verbunden.<BR><STRONG>Ursache:</STRONG> Die Subnetze für die entsprechenden IP-Adressen fehlen in den Netzwerkkonfigurationseinstellungen, oder die Subnetze sind nicht mit einer Netzwerk Website verbunden.<BR><STRONG>Auflösung:</STRONG> Fügen Sie der Liste der IP-Adressen Subnetze hinzu, die den Netzwerkkonfigurationseinstellungen entsprechen, und ordnen Sie jedes Subnetz einer Netzwerk Website zu.<BR>Wenn die Liste der IP-Adressen beispielsweise die Einträge 10.121.248.226 und 10.121.249.20 enthält, sind diese IP-Adressen entweder keinem Subnetz zugeordnet oder das zugeordnete Subnetz gehört keinem Netzwerkstandort an. Wenn die zugehörigen Subnetze für diese Adressen 10.121.248.0/24 und 10.121.249.0/24 lauten, können Sie das Problem wie folgt lösen: 
> <OL>
> <LI>
> <P>Stellen Sie sicher, dass die IP-Adresse 10.121.248.226 dem Subnetz 10.121.248.0/24 und die IP-Adresse 10.121.249.20 dem Subnetz 10.121.249.0/24 zugeordnet ist.</P>
> <LI>
> <P>Stellen Sie sicher, dass die Subnetze 10.121.248.0/24 und 10.121.249.0/24 jeweils einem Netzwerkstandort zugeordnet sind.</P></LI></OL>



</div>

Details zum Arbeiten mit Netzwerksubnets finden Sie in der Dokumentation zur lync Server-Verwaltungsshell für die folgenden Cmdlets:

  - [New-CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkSubnet)

  - [Get-CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkSubnet)

  - [Set-CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkSubnet)

  - [Remove-CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkSubnet)

<div>


> [!TIP]  
> Wenn Sie mit einer Vielzahl von Subnetzen arbeiten, empfehlen wir die Verwendung einer CSV-Datei (Comma-Separated Values, CSV), um die Subnetze den Websites zuzuordnen. Die CSV-Datei muss die folgenden vier Spalten aufweisen: <STRONG>IPAddress</STRONG>, <STRONG>Mask</STRONG>, <STRONG>Description</STRONG>, <STRONG>NetworkSiteID</STRONG>.



</div>

<div>

## <a name="to-associate-a-subnet-with-a-network-site-by-using-management-shell"></a>So ordnen Sie ein Subnetz mithilfe der Verwaltungsshell einer Netzwerk Website zu

1.  Starten Sie die lync Server-Verwaltungsshell: Klicken Sie auf **Start**, klicken Sie auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server-Verwaltungsshell**.

2.  Führen Sie das Cmdlet **New-CsNetworkSubnet** aus, um ein Subnetz einem Netzwerkstandort zuzuordnen:
    
        New-CsNetworkSubnet -SubnetID <String> -MaskBits <Int32> -NetworkSiteID <String>
    
    Beispiel:
    
        New-CsNetworkSubnet -SubnetID 172.11.12.13 - MaskBits 20 -NetworkSiteID Chicago
    
    In diesem Beispiel haben Sie eine Zuordnung zwischen dem Subnetz 172.11.12.13 und dem Netzwerkstandort „Chicago“ erstellt.

3.  Wiederholen Sie Schritt 2 für alle Subnetze in der Topologie.

</div>

<div>

## <a name="to-associate-subnets-with-network-sites-by-importing-a-csv-file"></a>So ordnen Sie Subnetze durch Importieren einer CSV-Datei Netzwerkstandorten zu

1.  Erstellen Sie eine CSV-Datei, die alle Subnetze enthält, die Sie hinzufügen möchten. Erstellen Sie beispielsweise die Datei **Subnetz.csv** mit folgendem Inhalt:
    
    `IPAddress, mask, description, NetworkSiteID`
    
    `172.11.12.0, 24, "NA:Subnet in Portland", Portland`
    
    `172.11.13.0, 24, "NA:Subnet in Reno", Reno`
    
    `172.11.14.0, 25, "EMEA:Subnet in Warsaw", Warsaw`
    
    `172.11.15.0, 31, "EMEA:Subnet in Paris", Paris`

2.  Starten Sie die lync Server-Verwaltungsshell: Klicken Sie auf **Start**, klicken Sie auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server-Verwaltungsshell**.

3.  Führen Sie das folgende Cmdlet aus, um **Subnet. CSV**zu importieren, und speichern Sie dann den Inhalt im lync Server-Verwaltungsspeicher:
    
        import-csv subnet.csv | foreach {New-CSNCSSubnet  _.IPAddress -MaskBits $_.mask -Description $_.description -NetworkSiteID $_.NetworkSiteID}

</div>

<div>

## <a name="to-associate-a-subnet-with-a-network-site-by-using-lync-server-control-panel"></a>So verknüpfen Sie ein Subnetz mit einer Netzwerk Website mithilfe der lync Server-Systemsteuerung

1.  Öffnen Sie ein Browserfenster, und geben Sie dann die Administrator-URL ein, um die lync Server-Systemsteuerung zu öffnen. Details zu den verschiedenen Methoden, die Sie zum Starten der lync Server-Systemsteuerung verwenden können, finden Sie unter [Öffnen von lync Server 2013-Verwaltungstools](lync-server-2013-open-lync-server-administrative-tools.md).

2.  Klicken Sie in der linken Navigationsleiste auf **Netzwerkkonfiguration**.

3.  Klicken Sie auf die Navigationsschaltfläche **Subnetz**.

4.  Klicken Sie auf **Neu**.

5.  Klicken Sie auf der Seite **Neues Subnetz** auf **Subnetz-ID** und geben Sie dann die erste Adresse in den IP-Adressbereich ein, der von dem Subnetz definiert wird, das Sie einem Netzwerkstandort zuordnen möchten.

6.  Klicken Sie auf **Maske** und geben Sie die Bitmaske für das Subnetz ein.

7.  Klicken Sie auf **Netzwerkstandort-ID** und wählen Sie die Standort-ID des Standorts aus, dem Sie dieses Subnetz hinzufügen.
    
    <div>
    

    > [!NOTE]  
    > Wenn Sie noch keine Netzwerkstandorte erstellt haben, ist diese Liste leer. Details zum Verfahren finden Sie unter <A href="lync-server-2013-create-or-modify-a-network-site.md">erstellen oder Ändern einer Netzwerk Website in lync Server 2013</A>. Sie können auch Standort-IDs für Ihre Bereitstellung abrufen, indem Sie das Cmdlet <STRONG>Get-CsNetworkSite</STRONG> ausführen. Ausführliche Informationen finden Sie in der Dokumentation zur lync Server-Verwaltungsshell.

    
    </div>

8.  Klicken Sie optional auf **Beschreibung** und geben Sie zusätzliche Informationen zur Beschreibung dieses Subnetzes ein.

9.  Klicken Sie auf **Commit ausführen**.

Wiederholen Sie diese Schritte, um einem Netzwerkstandort weitere Subnetze hinzuzufügen.

</div>

</div>

<span> </span>

</div>

</div>

</div>

