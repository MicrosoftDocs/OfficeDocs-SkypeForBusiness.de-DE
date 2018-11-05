---
title: 'Lync Server 2013: Zuordnen eines Subnetzes zu einem Netzwerkstandort'
TOCTitle: Zuordnen eines Subnetzes zu einem Netzwerkstandort
ms:assetid: aa69e3ac-542a-4ba1-9582-2e6bee29f633
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg412804(v=OCS.15)
ms:contentKeyID: 49295043
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Zuordnen eines Subnetzes zu einem Netzwerkstandort in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2014-10-20_

Jedes Subnetz in Ihrem Netzwerk muss einem bestimmten Netzwerkstandort zugeordnet sein, da mithilfe von Subnetzinformationen der Netzwerkstandort ermittelt wird, an dem sich ein Endpunkt befindet, während eine neuen Sitzung initiiert wird. Wenn der Standort aller Teilnehmer an einer Sitzung bekannt ist, können erweiterte Enterprise-VoIP-Funktionen diese Informationen nutzen, um die Anrufeinrichtung und -weiterleitung durchzuführen.


> [!IMPORTANT]
> Alle konfigurierten öffentlichen IP-Adressen der Audio-Video-Edgeserver in Ihrer Bereitstellung müssen den Netzwerkkonfigurationseinstellungen hinzugefügt werden. Diese IP-Adressen werden als Subnetze mit der Maske&nbsp;32 hinzugefügt. Der zugeordnete Netzwerkstandort muss dem jeweiligen konfigurierten Netzwerkstandort entsprechen. Die öffentliche IP-Adresse, die dem A/V-Edgeserver am zentralen Standort Chicago entspricht, hat beispielsweise die Netzwerkstandort-ID "Chicago". Ausführliche Informationen zu öffentlichen IP-Adressen finden Sie unter <A href="lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md">Ermitteln der Anforderungen für externe A/V-Firewalls und Ports für Lync Server 2013</A> in der Planungsdokumentation.




> [!NOTE]
> Es wird eine KHI-Warnung (Key Health Indicator) ausgegeben. Diese enthält eine Liste der IP-Adressen, die in Ihrem Netzwerk vorhanden, aber keinem Subnetz zugeordnet sind, oder sie gibt das Subnetz an, das die IP-Adressen enthält, jedoch keinem Netzwerkstandort zugeordnet ist. Diese Warnung wird innerhalb von acht&nbsp;Stunden nur einmal angezeigt. Nachfolgend finden Sie die relevanten Warnungsinformationen und ein Beispiel:<BR><STRONG>Quelle :</STRONG> CS-Bandbreitenrichtliniendienst (Core)<BR><STRONG>Ereignisnummer :</STRONG> 36034<BR><STRONG>Ebene :</STRONG> 2<BR><STRONG>Beschreibung:</STRONG> Die Subnetze für die folgenden IP-Adressen: &lt;Liste der IP-Adressen&gt; sind entweder nicht konfiguriert oder die Subnetze sind keinem Netzwerkstandort zugeordnet.<BR><STRONG>Ursache:</STRONG> Die Subnetze für die zugehörigen IP-Adressen fehlen in den Netzwerkkonfigurationseinstellungen oder die Subnetze sind keinem Netzwerkstandort zugeordnet.<BR><STRONG>Lösung:</STRONG> Fügen Sie gemäß der IP-Adressenliste den Netzwerkkonfigurationseinstellungen Subnetze hinzu und ordnen Sie jedes Subnetz einem Netzwerkstandort zu.<BR>Wenn die Liste der IP-Adressen beispielsweise die Einträge 10.121.248.226 und 10.121.249.20 enthält, sind diese IP-Adressen entweder keinem Subnetz zugeordnet oder das zugeordnete Subnetz gehört keinem Netzwerkstandort an. Wenn die zugehörigen Subnetze für diese Adressen 10.121.248.0/24 und 10.121.249.0/24 lauten, können Sie das Problem wie folgt lösen: 
> <OL>
> <LI>
> <P>Stellen Sie sicher, dass die IP-Adresse 10.121.248.226 dem Subnetz 10.121.248.0/24 und die IP-Adresse 10.121.249.20 dem Subnetz 10.121.249.0/24 zugeordnet ist.</P>
> <LI>
> <P>Stellen Sie sicher, dass die Subnetze 10.121.248.0/24 und 10.121.249.0/24 jeweils einem Netzwerkstandort zugeordnet sind.</P></LI></OL>



Ausführliche Informationen zum Arbeiten mit Netzwerksubnetzen finden Sie in der Lync Server-Verwaltungsshell-Dokumentation der folgenden Cmdlets:

  - [New-CsNetworkSubnet](https://docs.microsoft.com/en-us/powershell/module/skype/New-CsNetworkSubnet)

  - [Get-CsNetworkSubnet](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsNetworkSubnet)

  - [Set-CsNetworkSubnet](https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsNetworkSubnet)

  - [Remove-CsNetworkSubnet](https://docs.microsoft.com/en-us/powershell/module/skype/Remove-CsNetworkSubnet)


> [!TIP]
> Wenn Sie mit vielen Subnetzen arbeiten, wird die Verwendung einer CSV-Datei (mit durch Trennzeichen getrennten Werten) empfohlen, um Subnetze Standorten zuzuordnen. Die CSV-Datei muss die folgenden vier Spalten enthalten: <STRONG>IP-Adresse</STRONG>, <STRONG>Maske</STRONG>, <STRONG>Beschreibung</STRONG>, <STRONG>Netzwerkstandort-ID</STRONG>.



## So ordnen Sie ein Subnetz mithilfe der Verwaltungsshell einem Netzwerkstandort zu

1.  Starten der Lync Server-Verwaltungsshell: Klicken Sie auf **Start**, zeigen Sie auf **Alle Programme** und dann auf **Microsoft Lync Server 2013**, und klicken Sie anschließend auf **Lync Server-Verwaltungsshell**.

2.  Führen Sie das Cmdlet **New-CsNetworkSubnet** aus, um ein Subnetz einem Netzwerkstandort zuzuordnen:
    
        New-CsNetworkSubnet -SubnetID <String> -MaskBits <Int32> -NetworkSiteID <String>
    
    Beispiel:
    
        New-CsNetworkSubnet -SubnetID 172.11.12.13 - MaskBits 20 -NetworkSiteID Chicago
    
    In diesem Beispiel haben Sie eine Zuordnung zwischen dem Subnetz 172.11.12.13 und dem Netzwerkstandort "Chicago" erstellt.

3.  Wiederholen Sie Schritt 2 für alle Subnetze in der Topologie.

## So ordnen Sie Subnetze durch Importieren einer CSV-Datei Netzwerkstandorten zu

1.  Erstellen Sie eine CSV-Datei, die alle Subnetze enthält, die Sie hinzufügen möchten. Erstellen Sie beispielsweise die Datei **Subnetz.csv** mit folgendem Inhalt:
    
    `IPAddress, mask, description, NetworkSiteID`
    
    `172.11.12.0, 24, "NA:Subnet in Portland", Portland`
    
    `172.11.13.0, 24, "NA:Subnet in Reno", Reno`
    
    `172.11.14.0, 25, "EMEA:Subnet in Warsaw", Warsaw`
    
    `172.11.15.0, 31, "EMEA:Subnet in Paris", Paris`

2.  Starten der Lync Server-Verwaltungsshell: Klicken Sie auf **Start**, zeigen Sie auf **Alle Programme** und dann auf **Microsoft Lync Server 2013**, und klicken Sie anschließend auf **Lync Server-Verwaltungsshell**.

3.  Führen Sie zum Importieren der Datei **subnet.csv** das folgende Cmdlet aus und speichern Sie ihren Inhalt im Verwaltungsspeicher von Lync Server:
    
        import-csv subnet.csv | foreach {New-CsNetworkSubnet $_IPAddress -MaskBits $_.mask -Description $_.description -NetworkSiteID $_.NetworkSiteID}

## So ordnen Sie ein Subnetz mithilfe der Lync Server-Systemsteuerung einem Netzwerkstandort zu

1.  Öffnen Sie ein Browserfenster, und geben Sie die Admin-URL ein, um die Lync Server-Systemsteuerung zu öffnen. Informationen zu den verschiedenen Methoden zum Starten der Lync Server-Systemsteuerung finden Sie unter [Öffnen von Lync Server-Verwaltungstools](lync-server-2013-open-lync-server-administrative-tools.md).

2.  Klicken Sie in der linken Navigationsleiste auf **Netzwerkkonfiguration**.

3.  Klicken Sie auf die Navigationsschaltfläche **Subnetz**.

4.  Klicken Sie auf **Neu**.

5.  Klicken Sie auf der Seite **Neues Subnetz** auf **Subnetz-ID** und geben Sie dann die erste Adresse in den IP-Adressbereich ein, der von dem Subnetz definiert wird, das Sie einem Netzwerkstandort zuordnen möchten.

6.  Klicken Sie auf **Maske** und geben Sie die Bitmaske für das Subnetz ein.

7.  Klicken Sie auf **Netzwerkstandort-ID** und wählen Sie die Standort-ID des Standorts aus, dem Sie dieses Subnetz hinzufügen.
    

    > [!NOTE]
    > Wenn Sie noch keine Netzwerkstandorte erstellt haben, ist diese Liste leer. Ausführliche Informationen zu dem Verfahren finden Sie unter <A href="lync-server-2013-create-or-modify-a-network-site.md">Erstellen oder Ändern eines Netzwerkstandorts in Lync Server 2013</A>. Sie können auch Standort-IDs für Ihre Bereitstellung abrufen, indem Sie das Cmdlet <STRONG>Get-CsNetworkSite</STRONG> ausführen. Ausführliche Informationen finden Sie in der Dokumentation zur Lync Server-Verwaltungsshell.



8.  Klicken Sie optional auf **Beschreibung** und geben Sie zusätzliche Informationen zur Beschreibung dieses Subnetzes ein.

9.  Klicken Sie auf **Commit**.

Wiederholen Sie diese Schritte, um einem Netzwerkstandort weitere Subnetze hinzuzufügen.

