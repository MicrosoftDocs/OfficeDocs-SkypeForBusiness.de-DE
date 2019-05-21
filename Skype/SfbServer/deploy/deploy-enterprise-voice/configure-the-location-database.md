---
title: Konfigurieren der Standortdatenbank in Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: fb84f5b6-c991-4893-bdbf-f195b4b7d28e
description: Konfigurieren, füllen und veröffentlichen Sie die E9-1-1-Standortdatenbank in Skype for Business Server Enterprise Voice.
ms.openlocfilehash: 82182a27c1459005d19c8a50d0a1babc83b178c9
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2019
ms.locfileid: "34301076"
---
# <a name="configure-the-location-database-in-skype-for-business-server"></a><span data-ttu-id="7bbbb-103">Konfigurieren der Standortdatenbank in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="7bbbb-103">Configure the location database in Skype for Business Server</span></span>
 
<span data-ttu-id="7bbbb-104">Konfigurieren, füllen und veröffentlichen Sie die E9-1-1-Standortdatenbank in Skype for Business Server Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="7bbbb-104">Configure, populate, and publish the E9-1-1 location database in Skype for Business Server Enterprise Voice.</span></span> 
  
<span data-ttu-id="7bbbb-105">Sie müssen zunächst die Standortdatenbank konfigurieren, um Clients für die automatische Ermittlung ihres Standorts innerhalb eines Netzwerks zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="7bbbb-105">To enable clients to automatically detect their location within a network, you first need to configure the location database.</span></span> 
  
<span data-ttu-id="7bbbb-106">Führen Sie zur Konfiguration der Standortdatenbank die folgenden Aufgaben aus:</span><span class="sxs-lookup"><span data-stu-id="7bbbb-106">To configure the location database, perform the following tasks:</span></span>
  
- <span data-ttu-id="7bbbb-107">Füllen Sie die Datenbank mit einer Zuordnung von Netzwerkelementen zu Standorten auf.</span><span class="sxs-lookup"><span data-stu-id="7bbbb-107">Populate the database with a mapping of network elements to locations.</span></span> <span data-ttu-id="7bbbb-108">Wenn Sie ein Elin-Gateway (Notfall Standort-Identifikationsnummer) verwenden, müssen Sie Elin in das \<Feld\> "CompanyName" einbeziehen.</span><span class="sxs-lookup"><span data-stu-id="7bbbb-108">If you use an Emergency Location Identification Number (ELIN) gateway, you need to include the ELIN in the \<CompanyName\> field.</span></span>
    
    <span data-ttu-id="7bbbb-109">Wenn Sie die Standortdatenbank nicht auffüllen und die Eigenschaft **Standort erforderlich** in der Standortrichtlinie auf **Ja** oder **Haftungsausschluss** festgelegt ist, wird der Benutzer vom Client aufgefordert, den Standort manuell einzugeben.</span><span class="sxs-lookup"><span data-stu-id="7bbbb-109">If you do not populate the location database, and the **Location Required** in the Location Policy is set to **Yes** or **Disclaimer**, the client will prompt the user to enter a location manually.</span></span>
    
- <span data-ttu-id="7bbbb-110">Überprüfen Sie die Adressen anhand der MSAG-Daten (Master Street Address Guide), die vom Dienstanbieter für E9-1-1 verwaltet werden.</span><span class="sxs-lookup"><span data-stu-id="7bbbb-110">Validate the addresses against the master street address guide (MSAG) that is maintained by the E9-1-1 service provider.</span></span>
    
- <span data-ttu-id="7bbbb-111">Veröffentlichen Sie die aktualisierte Datenbank.</span><span class="sxs-lookup"><span data-stu-id="7bbbb-111">Publish the updated database.</span></span>
    
## <a name="populate-the-location-database"></a><span data-ttu-id="7bbbb-112">Auffüllen der Standortdatenbank</span><span class="sxs-lookup"><span data-stu-id="7bbbb-112">Populate the location database</span></span>

<span data-ttu-id="7bbbb-113">Zum automatischen Suchen nach Clients in einem Netzwerk müssen Sie zunächst die Standortdatenbank mithilfe einer Netzwerk-Wiremap auffüllen, die Netzwerkelemente physischen Adressen (d. h. Postanschriften) zuordnet.</span><span class="sxs-lookup"><span data-stu-id="7bbbb-113">To automatically locate clients within a network, you first need to populate the location database with a network wiremap, which maps network elements to civic (that is, street) addresses.</span></span> <span data-ttu-id="7bbbb-114">Sie können Subnetze, drahtlose Zugriffspunkte, Switches und Ports verwenden, um die Wiremap zu definieren.</span><span class="sxs-lookup"><span data-stu-id="7bbbb-114">You can use subnets, wireless access points, switches, and ports to define the wiremap.</span></span>
  
<span data-ttu-id="7bbbb-115">Sie können der Standortdatenbank Adressen einzeln oder unter Verwendung einer CSV-Datei per Massenvorgang hinzufügen. Die CSV-Datei muss dabei die in der folgenden Tabelle beschriebenen Spaltenformate aufweisen.</span><span class="sxs-lookup"><span data-stu-id="7bbbb-115">You can add addresses to the location database individually, or in bulk by using a CSV file that contains the column formats described in the following table.</span></span>
  
<span data-ttu-id="7bbbb-p103">Wenn Sie ein ELIN-Gateway (Emergency Location Identification Number) verwenden, schließen Sie für jeden Standort die ELIN in das Feld **Unternehmensname** ein. Sie können für jeden Standort mehrere ELINs eingeben, jeweils durch ein Semikolon voneinander getrennt.</span><span class="sxs-lookup"><span data-stu-id="7bbbb-p103">If you use an Emergency Location Identification Number (ELIN) gateway, include the ELIN in the **CompanyName** field for each location. You can include multiple ELINs for each location, each separated by a semicolon.</span></span>
  
|<span data-ttu-id="7bbbb-118">**Netzwerkelement**</span><span class="sxs-lookup"><span data-stu-id="7bbbb-118">**Network Element**</span></span>|<span data-ttu-id="7bbbb-119">**Erforderliche Spalten**</span><span class="sxs-lookup"><span data-stu-id="7bbbb-119">**Required Columns**</span></span>|
|:-----|:-----|
|<span data-ttu-id="7bbbb-120">**Drahtloser Zugriffspunkt**</span><span class="sxs-lookup"><span data-stu-id="7bbbb-120">**Wireless access point**</span></span> <br/> |<span data-ttu-id="7bbbb-121">\<BSSID\>,\<Description\>,\<Location\>,\<CompanyName\>,\<Hausnummer\>,\<HouseNumberSuffix\>,\<\>,...</span><span class="sxs-lookup"><span data-stu-id="7bbbb-121">\<BSSID\>,\<Description\>,\<Location\>,\<CompanyName\>,\<HouseNumber\>,\<HouseNumberSuffix\>,\<PreDirectional\>,…</span></span>  <br/> <span data-ttu-id="7bbbb-122">... \<Straßennamen\>,\<"streetsuffix"\>,\<postdirectional\>,\<Ort\>,\<Bundes\>Land\<,\>PLZ\<, Land\></span><span class="sxs-lookup"><span data-stu-id="7bbbb-122">…\<StreetName\>,\<StreetSuffix\>,\<PostDirectional\>,\<City\>,\<State\>,\<PostalCode\>,\<Country\></span></span>  <br/> |
|<span data-ttu-id="7bbbb-123">**Subnetz**</span><span class="sxs-lookup"><span data-stu-id="7bbbb-123">**Subnet**</span></span> <br/> |<span data-ttu-id="7bbbb-124">\<Subnet\>,\<Description\>,\<Location\>,\<CompanyName\>,\<Hausnummer\>,\<HouseNumberSuffix\>,\<\>,...</span><span class="sxs-lookup"><span data-stu-id="7bbbb-124">\<Subnet\>,\<Description\>,\<Location\>,\<CompanyName\>,\<HouseNumber\>,\<HouseNumberSuffix\>,\<PreDirectional\>,…</span></span>  <br/> <span data-ttu-id="7bbbb-125">... \<Straßennamen\>,\<"streetsuffix"\>,\<postdirectional\>,\<Ort\>,\<Bundes\>Land\<,\>PLZ\<, Land\></span><span class="sxs-lookup"><span data-stu-id="7bbbb-125">…\<StreetName\>,\<StreetSuffix\>,\<PostDirectional\>,\<City\>,\<State\>,\<PostalCode\>,\<Country\></span></span>  <br/> |
|<span data-ttu-id="7bbbb-126">**Port**</span><span class="sxs-lookup"><span data-stu-id="7bbbb-126">**Port**</span></span> <br/> |<span data-ttu-id="7bbbb-127">\<\>Chassis-\<PortIDSubType\>,\<Port\>-Nr\<,\>Description\<,\>Location\<,\>CompanyName\<,\>Hausnummer\< , HouseNumberSuffix\>,...</span><span class="sxs-lookup"><span data-stu-id="7bbbb-127">\<ChassisID\>,\<PortIDSubType\>,\<PortID\>,\<Description\>,\<Location\>,\<CompanyName\>,\<HouseNumber\>,\<HouseNumberSuffix\>,…</span></span>  <br/> <span data-ttu-id="7bbbb-128">... \<Vorrichtungs\>-\<, Straßen\>Namen\<-\>,\<"streetsuffix"-,\>\<postdirectional-\>,\<Stadt\>\>\<-\< , Bundesland-, PLZ-, Land\></span><span class="sxs-lookup"><span data-stu-id="7bbbb-128">…\<PreDirectional\>,\<StreetName\>,\<StreetSuffix\>,\<PostDirectional\>,\<City\>,\<State\>,\<PostalCode\>,\<Country\></span></span>  <br/> |
|<span data-ttu-id="7bbbb-129">**Switch**</span><span class="sxs-lookup"><span data-stu-id="7bbbb-129">**Switch**</span></span> <br/> |<span data-ttu-id="7bbbb-130">\<\>Chassis-\<Nr\>,\<Description\>,\<Location\>,\<CompanyName\>,\<Hausnummer\>,\<HouseNumberSuffix,\>,...</span><span class="sxs-lookup"><span data-stu-id="7bbbb-130">\<ChassisID\>,\<Description\>,\<Location\>,\<CompanyName\>,\<HouseNumber\>,\<HouseNumberSuffix\>,\<PreDirectional\>,…</span></span>  <br/> <span data-ttu-id="7bbbb-131">... \<Straßennamen\>,\<"streetsuffix"\>,\<postdirectional\>,\<Ort\>,\<Bundes\>Land\<,\>PLZ\<, Land\></span><span class="sxs-lookup"><span data-stu-id="7bbbb-131">…\<StreetName\>,\<StreetSuffix\>,\<PostDirectional\>,\<City\>,\<State\>,\<PostalCode\>,\<Country\></span></span>  <br/> |
   
### <a name="to-add-network-elements-to-the-location-database"></a><span data-ttu-id="7bbbb-132">So fügen Sie der Standortdatenbank Netzwerkelemente hinzu</span><span class="sxs-lookup"><span data-stu-id="7bbbb-132">To add network elements to the location database</span></span>

1. <span data-ttu-id="7bbbb-133">Führen Sie das folgende Cmdlet aus, um der Standortdatenbank einen Subnetzstandort hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="7bbbb-133">Run the following cmdlet to add a subnet location to the location database.</span></span>
    
   ```
   Set-CsLisSubnet -Subnet 157.56.66.0 -Description "Subnet 1" -Location Location1 -CompanyName "Litware" -HouseNumber 1234 -HouseNumberSuffix "" -PreDirectional "" -StreetName 163rd -StreetSuffix Ave -PostDirectional NE -City Redmond -State WA -PostalCode 99123 -Country US
   ```

    <span data-ttu-id="7bbbb-p104">Für ELIN-Gateways geben Sie die ELIN in das Feld „Unternehmensname“ ein. Sie können mehrere ELINs eingeben. Beispiel:</span><span class="sxs-lookup"><span data-stu-id="7bbbb-p104">For ELIN gateways, put the ELIN in the CompanyName field. You can include more than one ELIN. For example:</span></span>
    
   ```
   Set-CsLisSubnet -Subnet 157.56.66.0 -Description "Subnet 1" -Location Location1 -CompanyName 425-555-0100; 425-555-0200; 425-555-0300 -HouseNumber 1234 -HouseNumberSuffix "" -PreDirectional "" -StreetName 163rd -StreetSuffix Ave -PostDirectional NE -City Redmond -State WA -PostalCode 99123 -Country US
   ```

    <span data-ttu-id="7bbbb-137">Alternativ dazu können Sie auch folgende Cmdlets ausführen und eine Datei namens „subnets.csv“ verwenden, um Subnetzstandorte per Massenvorgang zu aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="7bbbb-137">Alternately, you can run the following cmdlets and use a file named "subnets.csv" to bulk update subnet locations.</span></span>
    
   ```
   $g = Import-Csv subnets.csv
   $g | Set-CsLisSubnet
   ```

2. <span data-ttu-id="7bbbb-138">Führen Sie das folgende Cmdlet aus, um der Standortdatenbank drahtlose Standorte hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="7bbbb-138">Run the following cmdlet to add wireless locations to the location database.</span></span>
    
   ```
   Set-CsLisWirelessAccessPoint -BSSID 0A-23-CD-16-AA-2E -Description "Wireless1" -Location Location2 -CompanyName "Litware" -HouseNumber 2345 -HouseNumberSuffix "" -PreDirectional "" -StreetName 163rd -StreetSuffix Ave -PostDirectional NE -City Bellevue -State WA -PostalCode 99234 -Country US
   ```

   <span data-ttu-id="7bbbb-139">Alternativ dazu können Sie auch folgende Cmdlets ausführen und eine Datei namens „waps.csv“ verwenden, um drahtlose Standorte per Massenvorgang zu aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="7bbbb-139">Alternately, you can run the following cmdlets and use a file named "waps.csv" to bulk update wireless locations.</span></span>
    
   ```
   $g = Import-Csv waps.csv
   $g | Set-CsLisWirelessAccessPoint
   ```

3. <span data-ttu-id="7bbbb-140">Führen Sie das folgende Cmdlet aus, um der Standortdatenbank Switchstandorte hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="7bbbb-140">Run the following cmdlet to add switch locations to the location database.</span></span>
    
   ```
   Set-CsLisSwitch-ChassisID 0B-23-CD-16-AA-BB -Description "Switch1" -Location Location1 -CompanyName "Litware" -HouseNumber 1234 -HouseNumberSuffix "" -PreDirectional "" -StreetName 163rd -StreetSuffix Ave -PostDirectional NE -City Redmond -State WA -PostalCode 99123 -Country US
   ```

   <span data-ttu-id="7bbbb-141">Alternativ dazu können Sie auch folgende Cmdlets ausführen und eine Datei namens „switches.csv“ verwenden, um Switchstandorte per Massenvorgang zu aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="7bbbb-141">Alternately, you can run the following cmdlets and use a file named "switches.csv" to bulk update switch locations.</span></span>
    
   ```
   $g = Import-Csv switches.csv
   $g | Set-CsLisSwitch
   ```

4. <span data-ttu-id="7bbbb-142">Führen Sie das folgende Cmdlet aus, um der Standortdatenbank Portstandorte hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="7bbbb-142">Run the following cmdlet to add port locations to the location database</span></span>
    
   ```
   Set-CsLisPort -ChassisID 0C-23-CD-16-AA-CC -PortID 0A-abcd -Description "Port1" -Location Location2 -CompanyName "Litware" -HouseNumber 2345 -HouseNumberSuffix "" -PreDirectional "" -StreetName 163rd -StreetSuffix Ave -PostDirectional NE -City Bellevue -State WA -PostalCode 99234 -Country US
   ```

   <span data-ttu-id="7bbbb-p105">Der Standardwert für PortIDSubType lautet LocallyAssigned. Sie können den Wert auch auf InterfaceAlias oder InterfaceName festlegen.</span><span class="sxs-lookup"><span data-stu-id="7bbbb-p105">The default for PortIDSubType is LocallyAssigned. You can also set it to InterfaceAlias or InterfaceName</span></span>
    
   <span data-ttu-id="7bbbb-145">Alternativ dazu können Sie auch folgende Cmdlets ausführen und eine Datei namens „ports.csv“ verwenden, um Portstandorte per Massenvorgang zu aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="7bbbb-145">Alternately, you can run the following cmdlets and use a file named "ports.csv" to bulk update port locations.</span></span>
    
   ```
   $g = Import-Csv ports.csv
   $g | Set-CsLisPort
   ```

## <a name="validate-addresses"></a><span data-ttu-id="7bbbb-146">Überprüfen von Adressen</span><span class="sxs-lookup"><span data-stu-id="7bbbb-146">Validate addresses</span></span>

### <a name="to-validate-addresses-located-in-the-location-database"></a><span data-ttu-id="7bbbb-147">So überprüfen Sie Adressen in der Standortdatenbank auf Gültigkeit</span><span class="sxs-lookup"><span data-stu-id="7bbbb-147">To validate addresses located in the location database</span></span>

1.  <span data-ttu-id="7bbbb-148">Starten Sie die Skype for Business Server-Verwaltungsshell: Klicken Sie auf **Start**, zeigen Sie auf **Alle Programme** und dann auf **Skype for Business 2015** und klicken Sie anschließend auf **Skype for Business Server-Verwaltungsshell**.</span><span class="sxs-lookup"><span data-stu-id="7bbbb-148">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="7bbbb-149">Führen Sie die folgenden Cmdlets zum Konfigurieren der Verbindung mit dem Anbieter für die Notrufunterstützung aus.</span><span class="sxs-lookup"><span data-stu-id="7bbbb-149">Run the following cmdlets to configure the emergency service provider connection.</span></span>
    
   ```
   $pwd = Read-Host -AsSecureString <password>
   Set-CsLisServiceProvider -ServiceProviderName Provider1 -ValidationServiceUrl <URL provided by provider> -CertFileName <location of certificate provided by provider> -Password $pwd
   ```

3. <span data-ttu-id="7bbbb-150">Führen das folgende Cmdlet zum Überprüfen der Gültigkeit von Adressen in der Standortdatenbank aus.</span><span class="sxs-lookup"><span data-stu-id="7bbbb-150">Run the following cmdlet to validate the addresses in the location database.</span></span>
    
   ```
   Get-CsLisCivicAddress | Test-CsLisCivicAddress -UpdateValidationStatus
   ```

   <span data-ttu-id="7bbbb-151">Einzelne Adressen können Sie auch mit dem Cmdlet **Test-CsLisCivicAddress** validieren.</span><span class="sxs-lookup"><span data-stu-id="7bbbb-151">You can also use the **Test-CsLisCivicAddress** cmdlet to validate individual addresses.</span></span>
    
## <a name="publish-the-location-database"></a><span data-ttu-id="7bbbb-152">Veröffentlichen der Standortdatenbank</span><span class="sxs-lookup"><span data-stu-id="7bbbb-152">Publish the location database</span></span>

<span data-ttu-id="7bbbb-153">Die neuen Standorte, die Sie der Standortdatenbank hinzugefügt haben, stehen dem Client erst nach der Veröffentlichung zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="7bbbb-153">The new locations that you added to the location database will not be made available to the client until they have been published.</span></span>
  
<span data-ttu-id="7bbbb-154">Wenn Sie ELIN-Gateways (Emergency Location Identification Number) verwenden, müssen Sie die ELINs auch in die ALI (Automatic Location Identification)-Datenbank Ihres PSTN-Betreibers hochladen.</span><span class="sxs-lookup"><span data-stu-id="7bbbb-154">If you use Emergency Location Identification Number (ELIN) gateways, you also need to upload the ELINs to your public switched telephone network (PSTN) carrier's Automatic Location Identification (ALI) database.</span></span> <span data-ttu-id="7bbbb-155">Ihr PSTN-Betreiber verlangt möglicherweise, dass Sie ein bestimmtes Format für die ELIN-Einträge verwenden.</span><span class="sxs-lookup"><span data-stu-id="7bbbb-155">Your PSTN carrier may require you to use a specific format for the ELIN records.</span></span> <span data-ttu-id="7bbbb-156">Weitere Informationen erhalten Sie von Ihrem PSTN-Betreiber.</span><span class="sxs-lookup"><span data-stu-id="7bbbb-156">Contact your PSTN carrier for details.</span></span> <span data-ttu-id="7bbbb-157">Sie können die Datensätze aus der Datenbank des Standort Informationsdiensts exportieren und diese nach Bedarf formatieren.</span><span class="sxs-lookup"><span data-stu-id="7bbbb-157">You can export the records from the Location Information service database and format them as required.</span></span>
  
### <a name="to-publish-the-location-database"></a><span data-ttu-id="7bbbb-158">So veröffentlichen Sie die Standortdatenbank</span><span class="sxs-lookup"><span data-stu-id="7bbbb-158">To publish the location database</span></span>

-  <span data-ttu-id="7bbbb-159">Starten Sie die Skype for Business Server-Verwaltungsshell: Klicken Sie auf **Start**, zeigen Sie auf **Alle Programme** und dann auf **Skype for Business 2015** und klicken Sie anschließend auf **Skype for Business Server-Verwaltungsshell**.</span><span class="sxs-lookup"><span data-stu-id="7bbbb-159">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
- <span data-ttu-id="7bbbb-160">Führen Sie das folgende Cmdlet aus, um die Standortdatenbank zu veröffentlichen.</span><span class="sxs-lookup"><span data-stu-id="7bbbb-160">Run the following cmdlet to publish the location database.</span></span>
    
  ```
  Publish-CsLisConfiguration
  ```


