---
title: Mit "config.xml" zum Ausführen von Installationsaufgaben in Skype für Business-clients
ms.author: chucked
author: chuckedmonson
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 0813184a-ab40-417c-b3a3-c2090766b831
description: 'Zusammenfassung: Wie die Datei „Config.xml“ verwendet wird, um weitere Installationshinweise anzugeben.'
ms.openlocfilehash: ea869fe2b49d5c1a5b4e04c3bc75cfd52b66555e
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/24/2018
ms.locfileid: "21003508"
---
# <a name="use-configxml-to-perform-installation-tasks-in-skype-for-business-clients"></a><span data-ttu-id="28e64-103">Mit "config.xml" zum Ausführen von Installationsaufgaben in Skype für Business-clients</span><span class="sxs-lookup"><span data-stu-id="28e64-103">Use Config.xml to perform installation tasks in Skype for Business clients</span></span>
 
<span data-ttu-id="28e64-104">**Zusammenfassung:** Wie die Datei „Config.xml“ verwendet wird, um weitere Installationshinweise anzugeben.</span><span class="sxs-lookup"><span data-stu-id="28e64-104">**Summary:** How to use the Config.xml file to specify additional installation instructions.</span></span>
  
<span data-ttu-id="28e64-p101">Das Office-Anpassungstool (OAT) ist zwar das primäre Tool für die angepasste Installation, Administratoren können jedoch mit der Datei "Config.xml" zusätzliche, im OAT nicht verfügbare Installationsanweisungen angeben. Die folgenden Anpassungen können nur mithilfe der Datei Config.xml vorgenommen werden:</span><span class="sxs-lookup"><span data-stu-id="28e64-p101">Although the Office Customization Tool (OCT) is the primary tool for customization installation, administrators can use the Config.xml file to specify additional installation instructions that are not available in the OCT. The following customizations can only be made by using the Config.xml file:</span></span>
  
- <span data-ttu-id="28e64-107">Angeben des Netzwerkinstallationspfads</span><span class="sxs-lookup"><span data-stu-id="28e64-107">Specify the path of the network installation point.</span></span>
    
- <span data-ttu-id="28e64-108">Auswählen der zu installierenden Produkte</span><span class="sxs-lookup"><span data-stu-id="28e64-108">Select the products to install.</span></span>
    
- <span data-ttu-id="28e64-109">Konfigurieren der Protokollierung und des Speicherorts der Setupanpassungsdatei und Softwareupdates</span><span class="sxs-lookup"><span data-stu-id="28e64-109">Configure logging and the location of the Setup customization file and software updates.</span></span>
    
- <span data-ttu-id="28e64-110">Angeben von Installationsoptionen, z. B. Benutzername</span><span class="sxs-lookup"><span data-stu-id="28e64-110">Specify installation options, such as user name.</span></span>
    
- <span data-ttu-id="28e64-111">Kopieren der lokalen Installationsquelle (Local Installation Source, LIS) auf den Benutzercomputer ohne Installation von Office</span><span class="sxs-lookup"><span data-stu-id="28e64-111">Copy the local installation source (LIS) to the user's computer without installing Office.</span></span>
    
- <span data-ttu-id="28e64-112">Hinzufügen oder Entfernen von Sprachen in der Installation</span><span class="sxs-lookup"><span data-stu-id="28e64-112">Add or remove languages from the installation.</span></span>
    
<span data-ttu-id="28e64-113">Es wird empfohlen, dass Sie die Datei "config.xml" zum Konfigurieren von Skype für die automatische Installation von Business verwenden.</span><span class="sxs-lookup"><span data-stu-id="28e64-113">We recommend that you use the Config.xml file to configure Skype for Business silent installation.</span></span> 
  
<span data-ttu-id="28e64-114">Standardmäßig werden in der Datei Config.xml, die in der kernproduktordner gespeichert wird (beispielsweise \ _Produkt_. WW) weist das Installationsprogramm, um dieses Produkt zu installieren.</span><span class="sxs-lookup"><span data-stu-id="28e64-114">By default, the Config.xml file that is stored in the core product folder (for example, \ _product_.WW) directs Setup to install that product.</span></span> <span data-ttu-id="28e64-115">Beispielsweise wird die Datei "config.xml" in den folgenden Ordner Skype für Unternehmen installiert:</span><span class="sxs-lookup"><span data-stu-id="28e64-115">For example, the Config.xml file in the following folder installs Skype for Business:</span></span>
  
- <span data-ttu-id="28e64-116">\\server\share\Skype15\Skype.ww \Config.xml</span><span class="sxs-lookup"><span data-stu-id="28e64-116">\\server\share\Skype15\Skype.WW \Config.xml</span></span>
    
<span data-ttu-id="28e64-117">Die am häufigsten verwendeten für Skype für die Installation von Business Config.xml-Elemente sind in der folgenden Tabelle aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="28e64-117">The Config.xml elements most commonly used for Skype for Business installation are listed in the following table.</span></span>
  
<span data-ttu-id="28e64-118">**Config.xml-Elemente**</span><span class="sxs-lookup"><span data-stu-id="28e64-118">**Config.xml elements**</span></span>

|<span data-ttu-id="28e64-119">**Element**</span><span class="sxs-lookup"><span data-stu-id="28e64-119">**Element**</span></span>|<span data-ttu-id="28e64-120">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="28e64-120">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="28e64-121">Konfiguration</span><span class="sxs-lookup"><span data-stu-id="28e64-121">Configuration</span></span>  <br/> |<span data-ttu-id="28e64-p103">Element der obersten Ebene (erforderlich). Enthält das Produktattribut, z. B.: Product=Lync (auch für Skype for Business-Clients geeignet)</span><span class="sxs-lookup"><span data-stu-id="28e64-p103">Top-level element (required). Contains the Product attribute, for example: Product=Lync (This will work for Skype for Business clients)</span></span>  <br/> |
|<span data-ttu-id="28e64-124">"OptionState"</span><span class="sxs-lookup"><span data-stu-id="28e64-124">OptionState</span></span>  <br/> | <span data-ttu-id="28e64-125">Gibt an, wie bestimmte Produktfeatures während der Installation behandelt werden.</span><span class="sxs-lookup"><span data-stu-id="28e64-125">Specifies how specific product features are handled during installation.</span></span> <span data-ttu-id="28e64-126">Verwenden Sie die folgenden Attribute, um die Installation von Business Connectivity Services zu verhindern, dass die freigegebene Komponenten umfasst, die Outlook beeinflussen:</span><span class="sxs-lookup"><span data-stu-id="28e64-126">Use the following attributes to prevent installation of Business Connectivity Services, which includes shared components that interfere with Outlook:</span></span> <br/>  <span data-ttu-id="28e64-127">ID = "LOBiMain"</span><span class="sxs-lookup"><span data-stu-id="28e64-127">Id="LOBiMain"</span></span> <br/>  <span data-ttu-id="28e64-128">State="Absent"</span><span class="sxs-lookup"><span data-stu-id="28e64-128">State="Absent"</span></span> <br/>  <span data-ttu-id="28e64-129">Children="Force"</span><span class="sxs-lookup"><span data-stu-id="28e64-129">Children="Force"</span></span> <br/> |
|<span data-ttu-id="28e64-130">Anzeige</span><span class="sxs-lookup"><span data-stu-id="28e64-130">Display</span></span>  <br/> | <span data-ttu-id="28e64-p105">Die Ebene der Benutzeroberfläche, die dem Benutzer angezeigt wird. Zu den typischen Attributen zählen Folgende:</span><span class="sxs-lookup"><span data-stu-id="28e64-p105">The level of UI that Setup displays to the user. Typical attributes include the following:</span></span> <br/>  <span data-ttu-id="28e64-133">CompletionNotice = "Yes"</span><span class="sxs-lookup"><span data-stu-id="28e64-133">CompletionNotice="Yes"</span></span> | <span data-ttu-id="28e64-134">"No"(Standard) "</span><span class="sxs-lookup"><span data-stu-id="28e64-134">"No"(default)</span></span> <br/>  <span data-ttu-id="28e64-135">AcceptEula = "Yes"</span><span class="sxs-lookup"><span data-stu-id="28e64-135">AcceptEula="Yes"</span></span> | <span data-ttu-id="28e64-136">"No"(Standard) "</span><span class="sxs-lookup"><span data-stu-id="28e64-136">"No"(default)</span></span> <br/> |
|<span data-ttu-id="28e64-137">Protokollierung</span><span class="sxs-lookup"><span data-stu-id="28e64-137">Logging</span></span>  <br/> | <span data-ttu-id="28e64-p106">Optionen für den vom Setup ausgeführten Protokollierungstyp. Zu den typischen Attributen zählen Folgende:</span><span class="sxs-lookup"><span data-stu-id="28e64-p106">Options for the kind of logging that Setup performs. Typical attributes include the following:</span></span> <br/>  <span data-ttu-id="28e64-140">Type = "Off"</span><span class="sxs-lookup"><span data-stu-id="28e64-140">Type ="Off"</span></span> | <span data-ttu-id="28e64-141">"Standard"(Standard)</span><span class="sxs-lookup"><span data-stu-id="28e64-141">"Standard"(default)</span></span> | <span data-ttu-id="28e64-142">"Verbose"</span><span class="sxs-lookup"><span data-stu-id="28e64-142">"Verbose"</span></span> <br/>  <span data-ttu-id="28e64-143">Template = " _Dateiname_.txt" (der Name der Protokolldatei)</span><span class="sxs-lookup"><span data-stu-id="28e64-143">Template=" _filename_.txt" (the name of the log file)</span></span>  <br/> |
|<span data-ttu-id="28e64-144">Einstellung</span><span class="sxs-lookup"><span data-stu-id="28e64-144">Setting</span></span>  <br/> | <span data-ttu-id="28e64-p107">Gibt Werte für Windows Installer-Eigenschaften an. Zu den typischen Attributen zählen Folgende:</span><span class="sxs-lookup"><span data-stu-id="28e64-p107">Specifies values for Windows Installer properties. Typical attributes include the following: </span></span><br/>  <span data-ttu-id="28e64-147">Setting Id = " _Name_" (der Name der Windows Installer-Eigenschaft)</span><span class="sxs-lookup"><span data-stu-id="28e64-147">Setting Id=" _name_" (the name of the Windows Installer property)</span></span>  <br/>  <span data-ttu-id="28e64-148">Wert = " _Wert_" (der Wert der Eigenschaft zugewiesen)</span><span class="sxs-lookup"><span data-stu-id="28e64-148">Value=" _value_" (the value to assign to the property)</span></span>  <br/> |
|<span data-ttu-id="28e64-149">DistributionPoint</span><span class="sxs-lookup"><span data-stu-id="28e64-149">DistributionPoint</span></span>  <br/> | <span data-ttu-id="28e64-p108">Der vollqualifizierte Pfad des Netzwerkinstallationspfads, von dem die Installation ausgeführt werden soll. Enthält das Standortattribut:</span><span class="sxs-lookup"><span data-stu-id="28e64-p108">The fully qualified path of the network installation point from which the installation is to run. Includes the Location attribute: </span></span><br/>  <span data-ttu-id="28e64-152">Speicherort = " _Pfad_"</span><span class="sxs-lookup"><span data-stu-id="28e64-152">Location=" _path_"</span></span>  <br/> |
   
<span data-ttu-id="28e64-153">Das folgende Beispiel zeigt eine Datei Config.xml für eine typische automatische Installation von der Skype für Business-Client.</span><span class="sxs-lookup"><span data-stu-id="28e64-153">The following example shows a Config.xml file for a typical silent installation of the Skype for Business client.</span></span> 
  
```
<Configuration Product="Lync"> 
  <OptionState Id="LOBiMain" State="Absent" Children="Force" /> 
  <Display Level="None" CompletionNotice="No" AcceptEula="Yes" /> 
  <Logging Type="verbose" Path="%temp%" Template="LyncSetupVerbose(*).log" />
  <Setting Id="SETUP_REBOOT" Value="Never" /> 
  <DistributionPoint Location="\\server\share\Skype15" /> 
</Configuration>
```

<span data-ttu-id="28e64-154">Ausführliche Informationen zur Verwendung der Datei "config.xml" zum Ausführen von Office-Installation und Wartung Aufgaben finden Sie unter [https://go.microsoft.com/fwlink/p/?linkid=267514](https://go.microsoft.com/fwlink/p/?linkid=267514).</span><span class="sxs-lookup"><span data-stu-id="28e64-154">Detailed information about using the Config.xml file to perform Office installation and maintenance tasks is available at [https://go.microsoft.com/fwlink/p/?linkid=267514](https://go.microsoft.com/fwlink/p/?linkid=267514).</span></span>
  
## <a name="to-customize-the-configxml-file"></a><span data-ttu-id="28e64-155">So passen Sie die Datei "Config.xml" an</span><span class="sxs-lookup"><span data-stu-id="28e64-155">To customize the Config.xml file</span></span>

1. <span data-ttu-id="28e64-156">Öffnen Sie die Datei "Config.xml" in einem Text-Editor wie Editor.</span><span class="sxs-lookup"><span data-stu-id="28e64-156">Open the Config.xml file by using a text editor tool, such as Notepad.</span></span>
    
2. <span data-ttu-id="28e64-157">Suchen Sie die Zeilen, die die zu ändernden Elemente enthalten.</span><span class="sxs-lookup"><span data-stu-id="28e64-157">Locate the lines that contain the elements you want to change.</span></span>
    
3. <span data-ttu-id="28e64-158">Ändern Sie den Elementeintrag mit den gewünschten Optionen für eine automatische Installation.</span><span class="sxs-lookup"><span data-stu-id="28e64-158">Modify the element entry with the silent options that you want to use.</span></span> <span data-ttu-id="28e64-159">Stellen Sie sicher, dass Sie die Kommentartrennzeichen entfernen "\<!--" und "–\>".</span><span class="sxs-lookup"><span data-stu-id="28e64-159">Make sure that you remove the comment delimiters, "\<!--" and "--\>".</span></span> <span data-ttu-id="28e64-160">Verwenden Sie z. B. die folgende Syntax:</span><span class="sxs-lookup"><span data-stu-id="28e64-160">For example, use the following syntax:</span></span>
    
  <pre>
  < DistributionPoint Location="\\server\share\Skype15" />
  </pre>

4. <span data-ttu-id="28e64-161">Speichern Sie die Datei Config.xml.</span><span class="sxs-lookup"><span data-stu-id="28e64-161">Save the Config.xml file.</span></span>
    

