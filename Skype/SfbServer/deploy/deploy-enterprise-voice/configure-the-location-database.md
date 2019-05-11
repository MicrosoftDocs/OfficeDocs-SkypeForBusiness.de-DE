---
title: Konfigurieren der Standortdatenbank in Skype für Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: fb84f5b6-c991-4893-bdbf-f195b4b7d28e
description: Konfigurieren und Veröffentlichen der Standortdatenbank E9-1-1 in Skype für Business Server Enterprise-VoIP auffüllen.
ms.openlocfilehash: e5f25cfcda35d4a78a369a2a5103f7bcd5b06a40
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "33893049"
---
# <a name="configure-the-location-database-in-skype-for-business-server"></a>Konfigurieren der Standortdatenbank in Skype für Business Server
 
Konfigurieren und Veröffentlichen der Standortdatenbank E9-1-1 in Skype für Business Server Enterprise-VoIP auffüllen. 
  
Sie müssen zunächst die Standortdatenbank konfigurieren, um Clients für die automatische Ermittlung ihres Standorts innerhalb eines Netzwerks zu aktivieren. 
  
Führen Sie zur Konfiguration der Standortdatenbank die folgenden Aufgaben aus:
  
- Füllen Sie die Datenbank mit einer Zuordnung von Netzwerkelementen zu Standorten auf. Wenn Sie eine Emergency Location Identification Anzahl ()-Gateway verwenden, müssen Sie die ELIN in der \<CompanyName\> dar.
    
    Wenn Sie die Standortdatenbank nicht auffüllen und die Eigenschaft **Standort erforderlich** in der Standortrichtlinie auf **Ja** oder **Haftungsausschluss** festgelegt ist, wird der Benutzer vom Client aufgefordert, den Standort manuell einzugeben.
    
- Überprüfen Sie die Adressen anhand der MSAG-Daten (Master Street Address Guide), die vom Dienstanbieter für E9-1-1 verwaltet werden.
    
- Veröffentlichen Sie die aktualisierte Datenbank.
    
## <a name="populate-the-location-database"></a>Auffüllen der Standortdatenbank

Zum automatischen Suchen nach Clients in einem Netzwerk müssen Sie zunächst die Standortdatenbank mithilfe einer Netzwerk-Wiremap auffüllen, die Netzwerkelemente physischen Adressen (d. h. Postanschriften) zuordnet. Sie können Subnetze, drahtlose Zugriffspunkte, Switches und Ports verwenden, um die Wiremap zu definieren.
  
Sie können der Standortdatenbank Adressen einzeln oder unter Verwendung einer CSV-Datei per Massenvorgang hinzufügen. Die CSV-Datei muss dabei die in der folgenden Tabelle beschriebenen Spaltenformate aufweisen.
  
Wenn Sie ein ELIN-Gateway (Emergency Location Identification Number) verwenden, schließen Sie für jeden Standort die ELIN in das Feld **Unternehmensname** ein. Sie können für jeden Standort mehrere ELINs eingeben, jeweils durch ein Semikolon voneinander getrennt.
  
|**Netzwerkelement**|**Erforderliche Spalten**|
|:-----|:-----|
|**Drahtloser Zugriffspunkt** <br/> |\<BSSID\>,\<Beschreibung\>,\<Speicherort\>,\<CompanyName\>,\<Hausnummer\>,\<HouseNumberSuffix\>,\<PreDirectional\>,...  <br/> ... \<StreetName\>,\<StreetSuffix\>,\<PostDirectional\>,\<City\>,\<Zustand\>,\<PostalCode\>,\<Land\>  <br/> |
|**Subnetz** <br/> |\<Subnetz\>,\<Beschreibung\>,\<Speicherort\>,\<CompanyName\>,\<Hausnummer\>,\<HouseNumberSuffix\>,\<PreDirectional\>,...  <br/> ... \<StreetName\>,\<StreetSuffix\>,\<PostDirectional\>,\<City\>,\<Zustand\>,\<PostalCode\>,\<Land\>  <br/> |
|**Port** <br/> |\<ChassisID\>,\<PortIDSubType\>,\<PortID\>,\<Beschreibung\>,\<Speicherort\>,\<CompanyName\>,\<Hausnummer\>,\< HouseNumberSuffix\>,...  <br/> ... \<PreDirectional\>,\<StreetName\>,\<StreetSuffix\>,\<PostDirectional\>,\<City\>,\<Zustand\>,\<PostalCode\>,\< Land\>  <br/> |
|**Switch** <br/> |\<ChassisID\>,\<Beschreibung\>,\<Speicherort\>,\<CompanyName\>,\<Hausnummer\>,\<HouseNumberSuffix\>,\<PreDirectional\>,...  <br/> ... \<StreetName\>,\<StreetSuffix\>,\<PostDirectional\>,\<City\>,\<Zustand\>,\<PostalCode\>,\<Land\>  <br/> |
   
### <a name="to-add-network-elements-to-the-location-database"></a>So fügen Sie der Standortdatenbank Netzwerkelemente hinzu

1. Führen Sie das folgende Cmdlet aus, um der Standortdatenbank einen Subnetzstandort hinzuzufügen.
    
   ```
   Set-CsLisSubnet -Subnet 157.56.66.0 -Description "Subnet 1" -Location Location1 -CompanyName "Litware" -HouseNumber 1234 -HouseNumberSuffix "" -PreDirectional "" -StreetName 163rd -StreetSuffix Ave -PostDirectional NE -City Redmond -State WA -PostalCode 99123 -Country US
   ```

    Für ELIN-Gateways geben Sie die ELIN in das Feld „Unternehmensname“ ein. Sie können mehrere ELINs eingeben. Beispiel:
    
   ```
   Set-CsLisSubnet -Subnet 157.56.66.0 -Description "Subnet 1" -Location Location1 -CompanyName 425-555-0100; 425-555-0200; 425-555-0300 -HouseNumber 1234 -HouseNumberSuffix "" -PreDirectional "" -StreetName 163rd -StreetSuffix Ave -PostDirectional NE -City Redmond -State WA -PostalCode 99123 -Country US
   ```

    Alternativ dazu können Sie auch folgende Cmdlets ausführen und eine Datei namens „subnets.csv“ verwenden, um Subnetzstandorte per Massenvorgang zu aktualisieren.
    
   ```
   $g = Import-Csv subnets.csv
   $g | Set-CsLisSubnet
   ```

2. Führen Sie das folgende Cmdlet aus, um der Standortdatenbank drahtlose Standorte hinzuzufügen.
    
   ```
   Set-CsLisWirelessAccessPoint -BSSID 0A-23-CD-16-AA-2E -Description "Wireless1" -Location Location2 -CompanyName "Litware" -HouseNumber 2345 -HouseNumberSuffix "" -PreDirectional "" -StreetName 163rd -StreetSuffix Ave -PostDirectional NE -City Bellevue -State WA -PostalCode 99234 -Country US
   ```

   Alternativ dazu können Sie auch folgende Cmdlets ausführen und eine Datei namens „waps.csv“ verwenden, um drahtlose Standorte per Massenvorgang zu aktualisieren.
    
   ```
   $g = Import-Csv waps.csv
   $g | Set-CsLisWirelessAccessPoint
   ```

3. Führen Sie das folgende Cmdlet aus, um der Standortdatenbank Switchstandorte hinzuzufügen.
    
   ```
   Set-CsLisSwitch-ChassisID 0B-23-CD-16-AA-BB -Description "Switch1" -Location Location1 -CompanyName "Litware" -HouseNumber 1234 -HouseNumberSuffix "" -PreDirectional "" -StreetName 163rd -StreetSuffix Ave -PostDirectional NE -City Redmond -State WA -PostalCode 99123 -Country US
   ```

   Alternativ dazu können Sie auch folgende Cmdlets ausführen und eine Datei namens „switches.csv“ verwenden, um Switchstandorte per Massenvorgang zu aktualisieren.
    
   ```
   $g = Import-Csv switches.csv
   $g | Set-CsLisSwitch
   ```

4. Führen Sie das folgende Cmdlet aus, um der Standortdatenbank Portstandorte hinzuzufügen.
    
   ```
   Set-CsLisPort -ChassisID 0C-23-CD-16-AA-CC -PortID 0A-abcd -Description "Port1" -Location Location2 -CompanyName "Litware" -HouseNumber 2345 -HouseNumberSuffix "" -PreDirectional "" -StreetName 163rd -StreetSuffix Ave -PostDirectional NE -City Bellevue -State WA -PostalCode 99234 -Country US
   ```

   Der Standardwert für PortIDSubType lautet LocallyAssigned. Sie können den Wert auch auf InterfaceAlias oder InterfaceName festlegen.
    
   Alternativ dazu können Sie auch folgende Cmdlets ausführen und eine Datei namens „ports.csv“ verwenden, um Portstandorte per Massenvorgang zu aktualisieren.
    
   ```
   $g = Import-Csv ports.csv
   $g | Set-CsLisPort
   ```

## <a name="validate-addresses"></a>Überprüfen von Adressen

### <a name="to-validate-addresses-located-in-the-location-database"></a>So überprüfen Sie Adressen in der Standortdatenbank auf Gültigkeit

1.  Starten Sie die Skype for Business Server-Verwaltungsshell: Klicken Sie auf **Start**, zeigen Sie auf **Alle Programme** und dann auf **Skype for Business 2015** und klicken Sie anschließend auf **Skype for Business Server-Verwaltungsshell**.
    
2. Führen Sie die folgenden Cmdlets zum Konfigurieren der Verbindung mit dem Anbieter für die Notrufunterstützung aus.
    
   ```
   $pwd = Read-Host -AsSecureString <password>
   Set-CsLisServiceProvider -ServiceProviderName Provider1 -ValidationServiceUrl <URL provided by provider> -CertFileName <location of certificate provided by provider> -Password $pwd
   ```

3. Führen das folgende Cmdlet zum Überprüfen der Gültigkeit von Adressen in der Standortdatenbank aus.
    
   ```
   Get-CsLisCivicAddress | Test-CsLisCivicAddress -UpdateValidationStatus
   ```

   Einzelne Adressen können Sie auch mit dem Cmdlet **Test-CsLisCivicAddress** validieren.
    
## <a name="publish-the-location-database"></a>Veröffentlichen der Standortdatenbank

Die neuen Standorte, die Sie der Standortdatenbank hinzugefügt haben, stehen dem Client erst nach der Veröffentlichung zur Verfügung.
  
Wenn Sie ELIN-Gateways (Emergency Location Identification Number) verwenden, müssen Sie die ELINs auch in die ALI (Automatic Location Identification)-Datenbank Ihres PSTN-Betreibers hochladen. Ihr PSTN-Betreiber verlangt möglicherweise, dass Sie ein bestimmtes Format für die ELIN-Einträge verwenden. Weitere Informationen erhalten Sie von Ihrem PSTN-Betreiber. Können Sie die Datensätze aus der Datenbank exportieren und nach Bedarf zu formatieren.
  
### <a name="to-publish-the-location-database"></a>So veröffentlichen Sie die Standortdatenbank

-  Starten Sie die Skype for Business Server-Verwaltungsshell: Klicken Sie auf **Start**, zeigen Sie auf **Alle Programme** und dann auf **Skype for Business 2015** und klicken Sie anschließend auf **Skype for Business Server-Verwaltungsshell**.
    
- Führen Sie das folgende Cmdlet aus, um die Standortdatenbank zu veröffentlichen.
    
  ```
  Publish-CsLisConfiguration
  ```


