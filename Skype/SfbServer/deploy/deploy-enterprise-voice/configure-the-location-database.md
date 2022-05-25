---
title: Konfigurieren der Standortdatenbank in Skype for Business Server
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: fb84f5b6-c991-4893-bdbf-f195b4b7d28e
description: Konfigurieren, auffüllen und veröffentlichen Sie die E9-1-1-Standortdatenbank in Skype for Business Server Enterprise-VoIP.
ms.openlocfilehash: fc7f53e1b62ec23e8075a9eac0d1158ee0143a5b
ms.sourcegitcommit: c53c22069b1babce7a2364de631057ff501ca1c0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/25/2022
ms.locfileid: "65671561"
---
# <a name="configure-the-location-database-in-skype-for-business-server"></a>Konfigurieren der Standortdatenbank in Skype for Business Server
 
Konfigurieren, auffüllen und veröffentlichen Sie die E9-1-1-Standortdatenbank in Skype for Business Server Enterprise-VoIP. 
  
Sie müssen zunächst die Standortdatenbank konfigurieren, um Clients für die automatische Ermittlung ihres Standorts innerhalb eines Netzwerks zu aktivieren. 
  
Führen Sie zum Konfigurieren der Standortdatenbank die folgenden Aufgaben aus:
  
- Füllen Sie die Datenbank mit einer Zuordnung von Netzwerkelementen zu Standorten auf. Wenn Sie ein ELIN-Gateway (Emergency Location Identification Number) verwenden, müssen Sie das ELIN in das \<CompanyName\> Feld einschließen.
    
    Wenn Sie die Standortdatenbank nicht auffüllen und der in der Standortrichtlinie **erforderliche Speicherort** auf **"Ja** " oder " **Haftungsausschluss**" festgelegt ist, fordert der Client den Benutzer auf, einen Speicherort manuell einzugeben.
    
- Überprüfen Sie die Adressen anhand der MSAG-Daten (Master Street Address Guide), die vom Dienstanbieter für E9-1-1 verwaltet werden.
    
- Veröffentlichen Sie die aktualisierte Datenbank.
    
## <a name="populate-the-location-database"></a>Auffüllen der Standortdatenbank

Um Clients in einem Netzwerk automatisch zu finden, müssen Sie zuerst die Standortdatenbank mit einer Netzwerk-Wiremap auffüllen, die Netzwerkelemente zivilen Adressen (d. h. Straßenadressen) zu ordnet. Sie können Subnetze, drahtlose Zugriffspunkte, Switches und Ports verwenden, um die Wiremap zu definieren.
  
Mithilfe einer CSV-Datei, die die in der folgenden Tabelle beschriebenen Spaltenformate enthält, können Sie der Speicherortdatenbank einzeln oder massenweise Adressen hinzufügen.
  
Wenn Sie ein ELIN-Gateway (Emergency Location Identification Number) verwenden, schließen Sie das ELIN in das Feld **"CompanyName** " für jeden Standort ein. Sie können für jede Position mehrere ELINs einfügen, die jeweils durch ein Semikolon getrennt sind.
  
|**Network-Element**|**Erforderliche Spalten**|
|:-----|:-----|
|**Drahtloser Zugriffspunkt** <br/> |\<BSSID\>,\<Description\>,\<Location\>,\<CompanyName\>,\<HouseNumber\>,\<HouseNumberSuffix\>,\<PreDirectional\>,...  <br/> ...\<StreetName\>,\<StreetSuffix\>,\<PostDirectional\>,\<City\>,\<State\>,\<PostalCode\>,\<Country\>  <br/> |
|**Subnetz** <br/> |\<Subnet\>,\<Description\>,\<Location\>,\<CompanyName\>,\<HouseNumber\>,\<HouseNumberSuffix\>,\<PreDirectional\>,...  <br/> ...\<StreetName\>,\<StreetSuffix\>,\<PostDirectional\>,\<City\>,\<State\>,\<PostalCode\>,\<Country\>  <br/> |
|**Port** <br/> |\<ChassisID\>,\<PortIDSubType\>,\<PortID\>,\<Description\>,\<Location\>,\<CompanyName\>,\<HouseNumber\>,\<HouseNumberSuffix\>,...  <br/> ...\<PreDirectional\>,\<StreetName\>,\<StreetSuffix\>,\<PostDirectional\>,\<City\>,\<State\>,\<PostalCode\>,\<Country\>  <br/> |
|**Switch** <br/> |\<ChassisID\>,\<Description\>,\<Location\>,\<CompanyName\>,\<HouseNumber\>,\<HouseNumberSuffix\>,\<PreDirectional\>,...  <br/> ...\<StreetName\>,\<StreetSuffix\>,\<PostDirectional\>,\<City\>,\<State\>,\<PostalCode\>,\<Country\>  <br/> |
   
### <a name="to-add-network-elements-to-the-location-database"></a>So fügen Sie der Standortdatenbank Netzwerkelemente hinzu

1. Führen Sie das folgende Cmdlet aus, um der Standortdatenbank einen Subnetzspeicherort hinzuzufügen.
    
   ```powershell
   Set-CsLisSubnet -Subnet 157.56.66.0 -Description "Subnet 1" -Location Location1 -CompanyName "Litware" -HouseNumber 1234 -HouseNumberSuffix "" -PreDirectional "" -StreetName 163rd -StreetSuffix Ave -PostDirectional NE -City Redmond -State WA -PostalCode 99123 -Country US
   ```

    Fügen Sie für ELIN-Gateways den ELIN in das Feld "CompanyName" ein. Sie können mehrere ELINs einschließen. Beispiel:
    
   ```powershell
   Set-CsLisSubnet -Subnet 157.56.66.0 -Description "Subnet 1" -Location Location1 -CompanyName 425-555-0100; 425-555-0200; 425-555-0300 -HouseNumber 1234 -HouseNumberSuffix "" -PreDirectional "" -StreetName 163rd -StreetSuffix Ave -PostDirectional NE -City Redmond -State WA -PostalCode 99123 -Country US
   ```

    Alternativ können Sie die folgenden Cmdlets ausführen und eine Datei mit dem Namen "subnets.csv" verwenden, um Subnetzstandorte massenweise zu aktualisieren.
    
   ```powershell
   $g = Import-Csv subnets.csv
   $g | Set-CsLisSubnet
   ```

2. Führen Sie das folgende Cmdlet aus, um der Standortdatenbank drahtlose Standorte hinzuzufügen.
    
   ```powershell
   Set-CsLisWirelessAccessPoint -BSSID 0A-23-CD-16-AA-2E -Description "Wireless1" -Location Location2 -CompanyName "Litware" -HouseNumber 2345 -HouseNumberSuffix "" -PreDirectional "" -StreetName 163rd -StreetSuffix Ave -PostDirectional NE -City Bellevue -State WA -PostalCode 99234 -Country US
   ```

   Alternativ können Sie die folgenden Cmdlets ausführen und eine Datei mit dem Namen "waps.csv" verwenden, um Drahtlose Speicherorte massenweise zu aktualisieren.
    
   ```powershell
   $g = Import-Csv waps.csv
   $g | Set-CsLisWirelessAccessPoint
   ```

3. Führen Sie das folgende Cmdlet aus, um der Standortdatenbank Switchspeicherorte hinzuzufügen.
    
   ```powershell
   Set-CsLisSwitch -ChassisID 0B-23-CD-16-AA-BB -Description "Switch1" -Location Location1 -CompanyName "Litware" -HouseNumber 1234 -HouseNumberSuffix "" -PreDirectional "" -StreetName 163rd -StreetSuffix Ave -PostDirectional NE -City Redmond -State WA -PostalCode 99123 -Country US
   ```

   Alternativ können Sie die folgenden Cmdlets ausführen und eine Datei mit dem Namen "switches.csv" verwenden, um switch-Speicherorte massenweise zu aktualisieren.
    
   ```powershell
   $g = Import-Csv switches.csv
   $g | Set-CsLisSwitch
   ```

4. Führen Sie das folgende Cmdlet aus, um der Standortdatenbank Portspeicherorte hinzuzufügen.
    
   ```powershell
   Set-CsLisPort -ChassisID 0C-23-CD-16-AA-CC -PortID 0A-abcd -Description "Port1" -Location Location2 -CompanyName "Litware" -HouseNumber 2345 -HouseNumberSuffix "" -PreDirectional "" -StreetName 163rd -StreetSuffix Ave -PostDirectional NE -City Bellevue -State WA -PostalCode 99234 -Country US
   ```

   Der Standardwert für PortIDSubType ist LocallyAssigned. Sie können sie auch auf "InterfaceAlias" oder "InterfaceName" festlegen.
    
   Alternativ können Sie die folgenden Cmdlets ausführen und eine Datei mit dem Namen "ports.csv" verwenden, um Portspeicherorte massenweise zu aktualisieren.
    
   ```powershell
   $g = Import-Csv ports.csv
   $g | Set-CsLisPort
   ```

## <a name="validate-addresses"></a>Überprüfen von Adressen

### <a name="to-validate-addresses-located-in-the-location-database"></a>So überprüfen Sie Adressen in der Standortdatenbank auf Gültigkeit

1.  Starten Sie die Skype for Business Server Verwaltungsshell: Klicken Sie auf **"Start**", dann auf **"Alle Programme**", klicken Sie auf **Skype for Business 2015**, und klicken Sie dann auf **Skype for Business Server Verwaltungsshell**.
    
2. Führen Sie die folgenden Cmdlets zum Konfigurieren der Verbindung mit dem Anbieter für die Notrufunterstützung aus.
    
   ```powershell
   $pwd = Read-Host -AsSecureString <password>
   Set-CsLisServiceProvider -ServiceProviderName Provider1 -ValidationServiceUrl <URL provided by provider> -CertFileName <location of certificate provided by provider> -Password $pwd
   ```

3. Führen das folgende Cmdlet zum Überprüfen der Gültigkeit von Adressen in der Standortdatenbank aus.
    
   ```powershell
   Get-CsLisCivicAddress | Test-CsLisCivicAddress -UpdateValidationStatus
   ```

   Mit dem Cmdlet **Test-CsLisCivicAddress** können Sie auch einzelne Adressen validieren.
    
## <a name="publish-the-location-database"></a>Veröffentlichen der Speicherortdatenbank

Die neuen Standorte, die Sie der Standortdatenbank hinzugefügt haben, stehen dem Client erst nach der Veröffentlichung zur Verfügung.
  
Wenn Sie ELIN-Gateways (Emergency Location Identification Number) verwenden, müssen Sie auch die die ELINs in die ALI (Automatic Location Identification)-Datenbank Ihres PSTN-Betreibers hochladen. Ihr PSTN-Betreiber verlangt möglicherweise, dass Sie ein bestimmtes Format für die ELIN-Einträge verwenden. Weitere Informationen erhalten Sie von Ihrem PSTN-Betreiber. Sie können die Datensätze aus der Standortinformationsdienstdatenbank exportieren und nach Bedarf formatieren.
  
### <a name="to-publish-the-location-database"></a>So veröffentlichen Sie die Standortdatenbank

-  Starten Sie die Skype for Business Server Verwaltungsshell: Klicken Sie auf **"Start**", dann auf **"Alle Programme**", klicken Sie auf **Skype for Business 2015**, und klicken Sie dann auf **Skype for Business Server Verwaltungsshell**.
    
- Führen Sie das folgende Cmdlet aus, um die Standortdatenbank zu veröffentlichen.
    
  ```powershell
  Publish-CsLisConfiguration
  ```


