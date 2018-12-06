---
title: Auffüllen der Standortdatenbank
TOCTitle: Auffüllen der Standortdatenbank
ms:assetid: fb84f5b6-c991-4893-bdbf-f195b4b7d28e
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg413069(v=OCS.15)
ms:contentKeyID: 49295991
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Auffüllen der Standortdatenbank

 

_**Letztes Änderungsdatum des Themas:** 2015-03-09_

Zum automatischen Suchen nach Clients in einem Netzwerk müssen Sie zunächst die Standortdatenbank mithilfe einer Netzwerk-*Wiremap* auffüllen, die Netzwerkelemente physischen Adressen (d.\&nbsp;h. Postanschriften) zuordnet. Sie können Subnetze, drahtlose Zugriffspunkte, Switches und Ports verwenden, um die Wiremap zu definieren.

Sie können der Standortdatenbank Adressen einzeln oder unter Verwendung einer CSV-Datei per Massenvorgang hinzufügen. Die CSV-Datei muss dabei die in der folgenden Tabelle beschriebenen Spaltenformate aufweisen.

Wenn Sie ein ELIN-Gateway (Emergency Location Identification Number) verwenden, schließen Sie für jeden Standort die ELIN in das Feld **Unternehmensname** ein. Sie können für jeden Standort mehrere ELINs eingeben, jeweils durch ein Semikolon voneinander getrennt.


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Netzwerkelement</th>
<th>Erforderliche Spalten</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>Drahtloser Zugriffspunkt</strong></p></td>
<td><p>&lt;BSSID&gt;,&lt;Beschreibung&gt;,&lt;Ort&gt;,&lt;Unternehmensname&gt;,&lt;Hausnummer&gt;,&lt;Suffix_Hausnummer&gt;,&lt;Himmelsrichtung_vor_Straße&gt;,…</p>
<p>…&lt;Straßenname&gt;,&lt;Suffix_Straßenname&gt;,&lt;Himmelsrichtung_nach_Straße&gt;,&lt;Stadt&gt;,&lt;Bundesland_Kanton&gt;,&lt;Postleitzahl&gt;,&lt;Land&gt;</p></td>
</tr>
<tr class="even">
<td><p><strong>Subnetz</strong></p></td>
<td><p>&lt;Subnetz&gt;,&lt;Beschreibung&gt;,&lt;Ort&gt;,&lt;Unternehmensname&gt;,&lt;Hausnummer&gt;,&lt;Suffix_Hausnummer&gt;,&lt;Himmelsrichtung_vor_Straße&gt;,…</p>
<p>…&lt;Straßenname&gt;,&lt;Suffix_Straßenname&gt;,&lt;Himmelsrichtung_nach_Straße&gt;,&lt;Stadt&gt;,&lt;Bundesland_Kanton&gt;,&lt;Postleitzahl&gt;,&lt;Land&gt;</p></td>
</tr>
<tr class="odd">
<td><p><strong>Port</strong></p></td>
<td><p>&lt;MAC-Adresse&gt;,&lt;Untertyp_Port&gt;,&lt;Port-ID&gt;,&lt;Beschreibung&gt;,&lt;Ort&gt;,&lt;Unternehmensname&gt;,&lt;Hausnummer&gt;,&lt;Suffix_Hausnummer&gt;,…</p>
<p>…&lt;Himmelsrichtung_vor_Straße&gt;,&lt;Straßenname&gt;,&lt;Suffix_Straßenname&gt;,&lt;Himmelsrichtung_nach_Straße&gt;,&lt;Stadt&gt;,&lt;Bundlesland_Kanton&gt;,&lt;Postleitzahl&gt;,&lt;Land&gt;</p></td>
</tr>
<tr class="even">
<td><p><strong>Switch</strong></p></td>
<td><p>&lt;MAC-Adresse&gt;,&lt;Beschreibung&gt;,&lt;Ort&gt;,&lt;Unternehmensname&gt;,&lt;Hausnummer&gt;,&lt;Suffix_Hausnummer&gt;,&lt;Himmelsrichtung_vor_Straße&gt;,…</p>
<p>…&lt;Straßenname&gt;,&lt;Suffix_Straßenname&gt;,&lt;Himmelsrichtung_nach_Straße&gt;,&lt;Stadt&gt;,&lt;Bundesland_Kanton&gt;,&lt;Postleitzahl&gt;,&lt;Land&gt;</p></td>
</tr>
</tbody>
</table>


Wenn Sie die Standortdatenbank nicht auffüllen und die Eigenschaft **Standort erforderlich** in der Ortungsrichtlinie auf **Ja** oder **Haftungsausschluss** festgelegt ist, wird der Benutzer vom Client aufgefordert, den Standort manuell einzugeben.

Ausführliche Informationen zum Auffüllen der Standortdatenbank finden Sie in der Lync Server-Verwaltungsshell-Dokumentation für die folgenden Cmdlets:

  - **Get-CsLisSubnet**

  - **Set-CsLisSubnet**

  - Remove-CsLisSubnet

  - **Get-CsLisWirelessAccessPoint**

  - **Set-CsLisWirelessAccessPoint**

  - **Remove-CsLisWirelessAccessPoint**

  - **Get-CsLisSwitch**

  - **Set-CsLisSwitch**

  - **Remove-CsLisSwitch**

  - **Get-CsLisPort**

  - **Set-CsLisPort**

  - **Remove-CsLisPort**

## So fügen Sie der Standortdatenbank Netzwerkelemente hinzu

1.  Führen Sie das folgende Cmdlet aus, um der Standortdatenbank einen Subnetzstandort hinzuzufügen.
    
        Set-CsLisSubnet -Subnet 157.56.66.0 -Description "Subnet 1" -Location Location1 -CompanyName "Litware" -HouseNumber 1234 -HouseNumberSuffix "" -PreDirectional "" -StreetName 163rd -StreetSuffix Ave -PostDirectional NE -City Redmond -State WA -PostalCode 99123 -Country US
    
    Für ELIN-Gateways geben Sie die ELIN in das Feld **Unternehmensname** ein. Sie können mehrere ELINs eingeben. Beispiel:
    
        Set-CsLisSubnet -Subnet 157.56.66.0 -Description "Subnet 1" -Location Location1 -CompanyName 425-555-0100; 425-555-0200; 425-555-0300 -HouseNumber 1234 -HouseNumberSuffix "" -PreDirectional "" -StreetName 163rd -StreetSuffix Ave -PostDirectional NE -City Redmond -State WA -PostalCode 99123 -Country US
    
    Alternativ dazu können Sie auch folgende Cmdlets ausführen und eine Datei namens **subnets.csv** verwenden, um Subnetzstandorte per Massenvorgang zu aktualisieren.
    
        $g = Import-Csv subnets.csv
        $g | Set-CsLisSubnet

2.  Führen Sie das folgende Cmdlet aus, um der Standortdatenbank drahtlose Standorte hinzuzufügen.
    
        Set-CsLisWirelessAccessPoint -BSSID 0A-23-CD-16-AA-2E -Description "Wireless1" -Location Location2 -CompanyName "Litware" -HouseNumber 2345 -HouseNumberSuffix "" -PreDirectional "" -StreetName 163rd -StreetSuffix Ave -PostDirectional NE -City Bellevue -State WA -PostalCode 99234 -Country US
    
    Alternativ dazu können Sie auch folgende Cmdlets ausführen und eine Datei namens **waps.csv** verwenden, um drahtlose Standorte per Massenvorgang zu aktualisieren.
    
        $g = Import-Csv waps.csv
        $g | Set-CsLisWirelessAccessPoint

3.  Führen Sie das folgende Cmdlet aus, um der Standortdatenbank Switchstandorte hinzuzufügen.
    
        Set-CsLisSwitch-ChassisID 0B-23-CD-16-AA-BB -Description "Switch1" -Location Location1 -CompanyName "Litware" -HouseNumber 1234 -HouseNumberSuffix "" -PreDirectional "" -StreetName 163rd -StreetSuffix Ave -PostDirectional NE -City Redmond -State WA -PostalCode 99123 -Country US
    
    Alternativ dazu können Sie auch folgende Cmdlets ausführen und eine Datei namens **switches.csv** verwenden, um Switchstandorte per Massenvorgang zu aktualisieren.
    
        $g = Import-Csv switches.csv
        $g | Set-CsLisSwitch

4.  Führen Sie das folgende Cmdlet aus, um der Standortdatenbank Portstandorte hinzuzufügen.
    
        Set-CsLisPort -ChassisID 0C-23-CD-16-AA-CC -PortID 0A-abcd -Description "Port1" -Location Location2 -CompanyName "Litware" -HouseNumber 2345 -HouseNumberSuffix "" -PreDirectional "" -StreetName 163rd -StreetSuffix Ave -PostDirectional NE -City Bellevue -State WA -PostalCode 99234 -Country US
    
    Der Standardwert für **PortIDSubType** lautet **LocallyAssigned**. Sie können den Wert auch auf **InterfaceAlias** oder **InterfaceName** festlegen.
    
    Alternativ dazu können Sie auch folgende Cmdlets ausführen und eine Datei namens **ports.csv** verwenden, um Portstandorte per Massenvorgang zu aktualisieren.
    
        $g = Import-Csv ports.csv
        $g | Set-CsLisPort

