---
title: Verwenden der Datei „config.xml“ zur Durchführung von Installationsaufgaben in Skype for Business Server 2015
ms.author: chucked
author: chuckedmonson
manager: serdars
ms.date: 12/20/2016
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 0813184a-ab40-417c-b3a3-c2090766b831
description: 'Zusammenfassung: Informationen zu die Datei Config.xml verwenden, um zusätzlich Hinweise zur Installation anzugeben.'
ms.openlocfilehash: f55683d672df890be8baf0ac7ca50b3170faf3d2
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/28/2018
---
# <a name="use-configxml-to-perform-installation-tasks-in-skype-for-business-server-2015"></a><span data-ttu-id="2bf58-103">Verwenden der Datei „config.xml“ zur Durchführung von Installationsaufgaben in Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="2bf58-103">Use Config.xml to perform installation tasks in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="2bf58-104">**Zusammenfassung:** Wie die Datei „Config.xml“ verwendet wird, um weitere Installationshinweise anzugeben.</span><span class="sxs-lookup"><span data-stu-id="2bf58-104">**Summary:** How to use the Config.xml file to specify additional installation instructions.</span></span>
  
<span data-ttu-id="2bf58-p101">Das Office-Anpassungstool (OAT) ist zwar das primäre Tool für die angepasste Installation, Administratoren können jedoch mit der Datei "Config.xml" zusätzliche, im OAT nicht verfügbare Installationsanweisungen angeben. Die folgenden Anpassungen können nur mithilfe der Datei Config.xml vorgenommen werden:</span><span class="sxs-lookup"><span data-stu-id="2bf58-p101">Although the Office Customization Tool (OCT) is the primary tool for customization installation, administrators can use the Config.xml file to specify additional installation instructions that are not available in the OCT. The following customizations can only be made by using the Config.xml file:</span></span>
  
- <span data-ttu-id="2bf58-107">Angeben des Netzwerkinstallationspfads</span><span class="sxs-lookup"><span data-stu-id="2bf58-107">Specify the path of the network installation point.</span></span>
    
- <span data-ttu-id="2bf58-108">Auswählen der zu installierenden Produkte</span><span class="sxs-lookup"><span data-stu-id="2bf58-108">Select the products to install.</span></span>
    
- <span data-ttu-id="2bf58-109">Konfigurieren der Protokollierung und des Speicherorts der Setupanpassungsdatei und Softwareupdates</span><span class="sxs-lookup"><span data-stu-id="2bf58-109">Configure logging and the location of the Setup customization file and software updates.</span></span>
    
- <span data-ttu-id="2bf58-110">Angeben von Installationsoptionen, z. B. Benutzername</span><span class="sxs-lookup"><span data-stu-id="2bf58-110">Specify installation options, such as user name.</span></span>
    
- <span data-ttu-id="2bf58-111">Kopieren der lokalen Installationsquelle (Local Installation Source, LIS) auf den Benutzercomputer ohne Installation von Office</span><span class="sxs-lookup"><span data-stu-id="2bf58-111">Copy the local installation source (LIS) to the user's computer without installing Office.</span></span>
    
- <span data-ttu-id="2bf58-112">Hinzufügen oder Entfernen von Sprachen in der Installation</span><span class="sxs-lookup"><span data-stu-id="2bf58-112">Add or remove languages from the installation.</span></span>
    
<span data-ttu-id="2bf58-113">Es wird empfohlen, dass Sie die Datei "config.xml" zum Konfigurieren von Skype für die automatische Installation von Business verwenden.</span><span class="sxs-lookup"><span data-stu-id="2bf58-113">We recommend that you use the Config.xml file to configure Skype for Business silent installation.</span></span> 
  
<span data-ttu-id="2bf58-114">Standardmäßig werden in der Datei Config.xml, die in der kernproduktordner gespeichert wird (beispielsweise \ _Produkt_. WW) weist das Installationsprogramm, um dieses Produkt zu installieren.</span><span class="sxs-lookup"><span data-stu-id="2bf58-114">By default, the Config.xml file that is stored in the core product folder (for example, \ _product_.WW) directs Setup to install that product.</span></span> <span data-ttu-id="2bf58-115">Beispielsweise wird die Datei "config.xml" in den folgenden Ordner Skype für Unternehmen installiert:</span><span class="sxs-lookup"><span data-stu-id="2bf58-115">For example, the Config.xml file in the following folder installs Skype for Business:</span></span>
  
- <span data-ttu-id="2bf58-116">\\server\share\Skype15\Skype.ww \Config.xml</span><span class="sxs-lookup"><span data-stu-id="2bf58-116">\\server\share\Skype15\Skype.WW \Config.xml</span></span>
    
<span data-ttu-id="2bf58-117">Die am häufigsten verwendeten für Skype für die Installation von Business Config.xml-Elemente sind in der folgenden Tabelle aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="2bf58-117">The Config.xml elements most commonly used for Skype for Business installation are listed in the following table.</span></span>
  
<span data-ttu-id="2bf58-118">**Config.XML-Elemente**</span><span class="sxs-lookup"><span data-stu-id="2bf58-118">**Config.xml elements**</span></span>

|<span data-ttu-id="2bf58-119">**Element**</span><span class="sxs-lookup"><span data-stu-id="2bf58-119">**Element**</span></span>|<span data-ttu-id="2bf58-120">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="2bf58-120">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="2bf58-121">Konfiguration</span><span class="sxs-lookup"><span data-stu-id="2bf58-121">Configuration</span></span>  <br/> |<span data-ttu-id="2bf58-p103">Element der obersten Ebene (erforderlich). Enthält das Produktattribut, z. B.: Product=Lync (auch für Skype for Business-Clients geeignet)</span><span class="sxs-lookup"><span data-stu-id="2bf58-p103">Top-level element (required). Contains the Product attribute, for example: Product=Lync (This will work for Skype for Business clients)</span></span>  <br/> |
|<span data-ttu-id="2bf58-124">"OptionState"</span><span class="sxs-lookup"><span data-stu-id="2bf58-124">OptionState</span></span>  <br/> | <span data-ttu-id="2bf58-125">Gibt an, wie bestimmte Produktfeatures während der Installation behandelt werden.</span><span class="sxs-lookup"><span data-stu-id="2bf58-125">Specifies how specific product features are handled during installation.</span></span> <span data-ttu-id="2bf58-126">Verwenden Sie die folgenden Attribute, um die Installation von Business Connectivity Services zu verhindern, dass die gemeinsam genutzte Komponenten enthält, die mit Outlook 2016 stören:</span><span class="sxs-lookup"><span data-stu-id="2bf58-126">Use the following attributes to prevent installation of Business Connectivity Services, which includes shared components that interfere with Outlook 2016:</span></span> <br/>  <span data-ttu-id="2bf58-127">ID = "LOBiMain"</span><span class="sxs-lookup"><span data-stu-id="2bf58-127">Id="LOBiMain"</span></span> <br/>  <span data-ttu-id="2bf58-128">State="Absent"</span><span class="sxs-lookup"><span data-stu-id="2bf58-128">State="Absent"</span></span> <br/>  <span data-ttu-id="2bf58-129">Children="Force"</span><span class="sxs-lookup"><span data-stu-id="2bf58-129">Children="Force"</span></span> <br/> |
|<span data-ttu-id="2bf58-130">Anzeige</span><span class="sxs-lookup"><span data-stu-id="2bf58-130">Display</span></span>  <br/> | <span data-ttu-id="2bf58-p105">Die Ebene der Benutzeroberfläche, die dem Benutzer angezeigt wird. Zu den typischen Attributen zählen Folgende:</span><span class="sxs-lookup"><span data-stu-id="2bf58-p105">The level of UI that Setup displays to the user. Typical attributes include the following:</span></span> <br/>  <span data-ttu-id="2bf58-133">CompletionNotice = "Yes"</span><span class="sxs-lookup"><span data-stu-id="2bf58-133">CompletionNotice="Yes"</span></span> | <span data-ttu-id="2bf58-134">"No"(Standard) "</span><span class="sxs-lookup"><span data-stu-id="2bf58-134">"No"(default)</span></span> <br/>  <span data-ttu-id="2bf58-135">AcceptEula = "Yes"</span><span class="sxs-lookup"><span data-stu-id="2bf58-135">AcceptEula="Yes"</span></span> | <span data-ttu-id="2bf58-136">"No"(Standard) "</span><span class="sxs-lookup"><span data-stu-id="2bf58-136">"No"(default)</span></span> <br/> |
|<span data-ttu-id="2bf58-137">Protokollierung</span><span class="sxs-lookup"><span data-stu-id="2bf58-137">Logging</span></span>  <br/> | <span data-ttu-id="2bf58-p106">Optionen für den vom Setup ausgeführten Protokollierungstyp. Zu den typischen Attributen zählen Folgende:</span><span class="sxs-lookup"><span data-stu-id="2bf58-p106">Options for the kind of logging that Setup performs. Typical attributes include the following:</span></span> <br/>  <span data-ttu-id="2bf58-140">Type = "Off"</span><span class="sxs-lookup"><span data-stu-id="2bf58-140">Type ="Off"</span></span> | <span data-ttu-id="2bf58-141">"Standard"(Standard)</span><span class="sxs-lookup"><span data-stu-id="2bf58-141">"Standard"(default)</span></span> | <span data-ttu-id="2bf58-142">"Verbose"</span><span class="sxs-lookup"><span data-stu-id="2bf58-142">"Verbose"</span></span> <br/>  <span data-ttu-id="2bf58-143">Template = " _Dateiname_.txt" (der Name der Protokolldatei)</span><span class="sxs-lookup"><span data-stu-id="2bf58-143">Template=" _filename_.txt" (the name of the log file)</span></span>  <br/> |
|<span data-ttu-id="2bf58-144">Einstellung</span><span class="sxs-lookup"><span data-stu-id="2bf58-144">Setting</span></span>  <br/> | <span data-ttu-id="2bf58-p107">Gibt Werte für Windows Installer-Eigenschaften an. Zu den typischen Attributen zählen Folgende:</span><span class="sxs-lookup"><span data-stu-id="2bf58-p107">Specifies values for Windows Installer properties. Typical attributes include the following: </span></span><br/>  <span data-ttu-id="2bf58-147">Setting Id = " _Name_" (der Name der Windows Installer-Eigenschaft)</span><span class="sxs-lookup"><span data-stu-id="2bf58-147">Setting Id=" _name_" (the name of the Windows Installer property)</span></span>  <br/>  <span data-ttu-id="2bf58-148">Wert = " _Wert_" (der Wert der Eigenschaft zugewiesen)</span><span class="sxs-lookup"><span data-stu-id="2bf58-148">Value=" _value_" (the value to assign to the property)</span></span>  <br/> |
|<span data-ttu-id="2bf58-149">DistributionPoint</span><span class="sxs-lookup"><span data-stu-id="2bf58-149">DistributionPoint</span></span>  <br/> | <span data-ttu-id="2bf58-p108">Der vollqualifizierte Pfad des Netzwerkinstallationspfads, von dem die Installation ausgeführt werden soll. Enthält das Standortattribut:</span><span class="sxs-lookup"><span data-stu-id="2bf58-p108">The fully qualified path of the network installation point from which the installation is to run. Includes the Location attribute: </span></span><br/>  <span data-ttu-id="2bf58-152">Speicherort = " _Pfad_"</span><span class="sxs-lookup"><span data-stu-id="2bf58-152">Location=" _path_"</span></span>  <br/> |
   
<span data-ttu-id="2bf58-153">Das folgende Beispiel zeigt eine Datei Config.xml für eine typische automatische Installation von Skype für Unternehmen.</span><span class="sxs-lookup"><span data-stu-id="2bf58-153">The following example shows a Config.xml file for a typical silent installation of Skype for Business.</span></span> 
  
```
<Configuration Product="Lync"> 
  <OptionState Id="LOBiMain" State="Absent" Children="Force" /> 
  <Display Level="None" CompletionNotice="No" AcceptEula="Yes" /> 
  <Logging Type="verbose" Path="%temp%" Template="LyncSetupVerbose(*).log" />
  <Setting Id="SETUP_REBOOT" Value="Never" /> 
  <DistributionPoint Location="\\server\share\Skype15" /> 
</Configuration>
```

<span data-ttu-id="2bf58-154">Ausführliche Informationen zur Verwendung der Datei "config.xml" zum Ausführen von Office-Installation und Wartung Aufgaben finden Sie unter [https://go.microsoft.com/fwlink/p/?linkid=267514](https://go.microsoft.com/fwlink/p/?linkid=267514).</span><span class="sxs-lookup"><span data-stu-id="2bf58-154">Detailed information about using the Config.xml file to perform Office installation and maintenance tasks is available at [https://go.microsoft.com/fwlink/p/?linkid=267514](https://go.microsoft.com/fwlink/p/?linkid=267514).</span></span>
  
## <a name="to-customize-the-configxml-file"></a><span data-ttu-id="2bf58-155">So passen Sie die Datei "Config.xml" an</span><span class="sxs-lookup"><span data-stu-id="2bf58-155">To customize the Config.xml file</span></span>

1. <span data-ttu-id="2bf58-156">Öffnen Sie die Datei "Config.xml" in einem Text-Editor wie Editor.</span><span class="sxs-lookup"><span data-stu-id="2bf58-156">Open the Config.xml file by using a text editor tool, such as Notepad.</span></span>
    
2. <span data-ttu-id="2bf58-157">Suchen Sie die Zeilen, die die zu ändernden Elemente enthalten.</span><span class="sxs-lookup"><span data-stu-id="2bf58-157">Locate the lines that contain the elements you want to change.</span></span>
    
3. <span data-ttu-id="2bf58-158">Ändern Sie den Elementeintrag mit den gewünschten Optionen für eine automatische Installation.</span><span class="sxs-lookup"><span data-stu-id="2bf58-158">Modify the element entry with the silent options that you want to use.</span></span> <span data-ttu-id="2bf58-159">Stellen Sie sicher, dass Sie die Kommentartrennzeichen entfernen "\<!--" und "–\>".</span><span class="sxs-lookup"><span data-stu-id="2bf58-159">Make sure that you remove the comment delimiters, "\<!--" and "--\>".</span></span> <span data-ttu-id="2bf58-160">Verwenden Sie z. B. die folgende Syntax:</span><span class="sxs-lookup"><span data-stu-id="2bf58-160">For example, use the following syntax:</span></span>
    
  ```
  < DistributionPoint Location="\\server\share\Skype15" />
  ```

4. <span data-ttu-id="2bf58-161">Speichern Sie die Datei Config.xml.</span><span class="sxs-lookup"><span data-stu-id="2bf58-161">Save the Config.xml file.</span></span>
    

