---
title: Verwenden von "config. xml" zum Ausführen von Installationsaufgaben in Skype for Business-Clients
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.reviewer: PhillipGarding
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 0813184a-ab40-417c-b3a3-c2090766b831
description: 'Zusammenfassung: Wie die Datei „Config.xml“ verwendet wird, um weitere Installationshinweise anzugeben.'
ms.openlocfilehash: a935e3623e99324eb24caef4e7e232d2311c5cfb
ms.sourcegitcommit: dd3a3ab4ddbdcfe772f30fb01ba3b97c45c43dd4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41768648"
---
# <a name="use-configxml-to-perform-installation-tasks-in-skype-for-business-clients"></a><span data-ttu-id="3c6fc-103">Verwenden von "config. xml" zum Ausführen von Installationsaufgaben in Skype for Business-Clients</span><span class="sxs-lookup"><span data-stu-id="3c6fc-103">Use Config.xml to perform installation tasks in Skype for Business clients</span></span>

<span data-ttu-id="3c6fc-104">**Zusammenfassung:** Wie die Datei „Config.xml“ verwendet wird, um weitere Installationshinweise anzugeben.</span><span class="sxs-lookup"><span data-stu-id="3c6fc-104">**Summary:** How to use the Config.xml file to specify additional installation instructions.</span></span>

<span data-ttu-id="3c6fc-p101">Das Office-Anpassungstool (OAT) ist zwar das primäre Tool für die angepasste Installation, Administratoren können jedoch mit der Datei "Config.xml" zusätzliche, im OAT nicht verfügbare Installationsanweisungen angeben. Die folgenden Anpassungen können nur mithilfe der Datei Config.xml vorgenommen werden:</span><span class="sxs-lookup"><span data-stu-id="3c6fc-p101">Although the Office Customization Tool (OCT) is the primary tool for customization installation, administrators can use the Config.xml file to specify additional installation instructions that are not available in the OCT. The following customizations can only be made by using the Config.xml file:</span></span>

- <span data-ttu-id="3c6fc-107">Angeben des Netzwerkinstallationspfads</span><span class="sxs-lookup"><span data-stu-id="3c6fc-107">Specify the path of the network installation point.</span></span>

- <span data-ttu-id="3c6fc-108">Auswählen der zu installierenden Produkte</span><span class="sxs-lookup"><span data-stu-id="3c6fc-108">Select the products to install.</span></span>

- <span data-ttu-id="3c6fc-109">Konfigurieren der Protokollierung und des Speicherorts der Setupanpassungsdatei und Softwareupdates</span><span class="sxs-lookup"><span data-stu-id="3c6fc-109">Configure logging and the location of the Setup customization file and software updates.</span></span>

- <span data-ttu-id="3c6fc-110">Angeben von Installationsoptionen, z. B. Benutzername</span><span class="sxs-lookup"><span data-stu-id="3c6fc-110">Specify installation options, such as user name.</span></span>

- <span data-ttu-id="3c6fc-111">Kopieren der lokalen Installationsquelle (Local Installation Source, LIS) auf den Benutzercomputer ohne Installation von Office</span><span class="sxs-lookup"><span data-stu-id="3c6fc-111">Copy the local installation source (LIS) to the user's computer without installing Office.</span></span>

- <span data-ttu-id="3c6fc-112">Hinzufügen oder Entfernen von Sprachen in der Installation</span><span class="sxs-lookup"><span data-stu-id="3c6fc-112">Add or remove languages from the installation.</span></span>

<span data-ttu-id="3c6fc-113">Wir empfehlen, die Datei config. XML zum Konfigurieren der unbeaufsichtigten Installation von Skype for Business zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="3c6fc-113">We recommend that you use the Config.xml file to configure Skype for Business silent installation.</span></span> 

<span data-ttu-id="3c6fc-114">Standardmäßig ist die Datei config. XML, die im Kernproduktordner gespeichert ist (beispielsweise \ _Product_. WW) weist Setup an, dieses Produkt zu installieren.</span><span class="sxs-lookup"><span data-stu-id="3c6fc-114">By default, the Config.xml file that is stored in the core product folder (for example, \ _product_.WW) directs Setup to install that product.</span></span> <span data-ttu-id="3c6fc-115">Beispielsweise installiert die Datei config. XML im folgenden Ordner Skype for Business:</span><span class="sxs-lookup"><span data-stu-id="3c6fc-115">For example, the Config.xml file in the following folder installs Skype for Business:</span></span>

- <span data-ttu-id="3c6fc-116">\\server\share\Skype15\Skype.WW \Config.xml</span><span class="sxs-lookup"><span data-stu-id="3c6fc-116">\\server\share\Skype15\Skype.WW \Config.xml</span></span>

<span data-ttu-id="3c6fc-117">Die am häufigsten für die Skype for Business-Installation verwendeten config. XML-Elemente sind in der folgenden Tabelle aufgelistet.</span><span class="sxs-lookup"><span data-stu-id="3c6fc-117">The Config.xml elements most commonly used for Skype for Business installation are listed in the following table.</span></span>

<span data-ttu-id="3c6fc-118">**Config.xml-Elemente**</span><span class="sxs-lookup"><span data-stu-id="3c6fc-118">**Config.xml elements**</span></span>


| <span data-ttu-id="3c6fc-119">**Element**</span><span class="sxs-lookup"><span data-stu-id="3c6fc-119">**Element**</span></span>              | <span data-ttu-id="3c6fc-120">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="3c6fc-120">**Description**</span></span>                                                                                                                                                                                                                                                                                         |
|:-------------------------|:--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| <span data-ttu-id="3c6fc-121">Konfiguration</span><span class="sxs-lookup"><span data-stu-id="3c6fc-121">Configuration</span></span>  <br/>     | <span data-ttu-id="3c6fc-p103">Element der obersten Ebene (erforderlich). Enthält das Produktattribut, z. B.: Product=Lync (auch für Skype for Business-Clients geeignet)</span><span class="sxs-lookup"><span data-stu-id="3c6fc-p103">Top-level element (required). Contains the Product attribute, for example: Product=Lync (This will work for Skype for Business clients)</span></span>  <br/>                                                                                                                                                          |
| <span data-ttu-id="3c6fc-124">OptionState</span><span class="sxs-lookup"><span data-stu-id="3c6fc-124">OptionState</span></span>  <br/>       | <span data-ttu-id="3c6fc-125">Gibt an, wie bestimmte Produktfeatures während der Installation behandelt werden.</span><span class="sxs-lookup"><span data-stu-id="3c6fc-125">Specifies how specific product features are handled during installation.</span></span> <span data-ttu-id="3c6fc-126">Verwenden Sie die folgenden Attribute, um die Installation von Business Connectivity Services zu verhindern, die freigegebene Komponenten umfasst, die Outlook stören:</span><span class="sxs-lookup"><span data-stu-id="3c6fc-126">Use the following attributes to prevent installation of Business Connectivity Services, which includes shared components that interfere with Outlook:</span></span> <br/>  <span data-ttu-id="3c6fc-127">Id="LOBiMain"</span><span class="sxs-lookup"><span data-stu-id="3c6fc-127">Id="LOBiMain"</span></span> <br/>  <span data-ttu-id="3c6fc-128">State="Absent"</span><span class="sxs-lookup"><span data-stu-id="3c6fc-128">State="Absent"</span></span> <br/>  <span data-ttu-id="3c6fc-129">Children="Force"</span><span class="sxs-lookup"><span data-stu-id="3c6fc-129">Children="Force"</span></span> <br/> |
| <span data-ttu-id="3c6fc-130">Anzeige</span><span class="sxs-lookup"><span data-stu-id="3c6fc-130">Display</span></span>  <br/>           | <span data-ttu-id="3c6fc-p105">Die Ebene der Benutzeroberfläche, die dem Benutzer angezeigt wird. Zu den typischen Attributen zählen Folgende:</span><span class="sxs-lookup"><span data-stu-id="3c6fc-p105">The level of UI that Setup displays to the user. Typical attributes include the following:</span></span> <br/>  <span data-ttu-id="3c6fc-133">CompletionNotice = "Ja"</span><span class="sxs-lookup"><span data-stu-id="3c6fc-133">CompletionNotice="Yes"</span></span>                                                                                                                                                                                |
| <span data-ttu-id="3c6fc-134">Protokollierung</span><span class="sxs-lookup"><span data-stu-id="3c6fc-134">Logging</span></span>  <br/>           | <span data-ttu-id="3c6fc-p106">Optionen für den vom Setup ausgeführten Protokollierungstyp. Zu den typischen Attributen zählen Folgende:</span><span class="sxs-lookup"><span data-stu-id="3c6fc-p106">Options for the kind of logging that Setup performs. Typical attributes include the following:</span></span> <br/>  <span data-ttu-id="3c6fc-137">Geben Sie = "aus" ein.</span><span class="sxs-lookup"><span data-stu-id="3c6fc-137">Type ="Off"</span></span>                                                                                                                                                                                       |
| <span data-ttu-id="3c6fc-138">Einstellung</span><span class="sxs-lookup"><span data-stu-id="3c6fc-138">Setting</span></span>  <br/>           | <span data-ttu-id="3c6fc-p107">Gibt Werte für Windows Installer-Eigenschaften an. Zu den typischen Attributen zählen Folgende:</span><span class="sxs-lookup"><span data-stu-id="3c6fc-p107">Specifies values for Windows Installer properties. Typical attributes include the following: </span></span><br/>  <span data-ttu-id="3c6fc-141">Setting ID = " *Name*" (der Name der Windows Installer-Eigenschaft)</span><span class="sxs-lookup"><span data-stu-id="3c6fc-141">Setting Id=" *name*" (the name of the Windows Installer property)</span></span>  <br/>  <span data-ttu-id="3c6fc-142">Value = " *Wert*" (der Wert, der der Eigenschaft zugewiesen werden soll)</span><span class="sxs-lookup"><span data-stu-id="3c6fc-142">Value=" *value*" (the value to assign to the property)</span></span>  <br/>                                                             |
| <span data-ttu-id="3c6fc-143">DistributionPoint</span><span class="sxs-lookup"><span data-stu-id="3c6fc-143">DistributionPoint</span></span>  <br/> | <span data-ttu-id="3c6fc-p108">Der vollqualifizierte Pfad des Netzwerkinstallationspfads, von dem die Installation ausgeführt werden soll. Enthält das Standortattribut:</span><span class="sxs-lookup"><span data-stu-id="3c6fc-p108">The fully qualified path of the network installation point from which the installation is to run. Includes the Location attribute: </span></span><br/>  <span data-ttu-id="3c6fc-146">Location = " *path*"</span><span class="sxs-lookup"><span data-stu-id="3c6fc-146">Location=" *path*"</span></span>  <br/>                                                                                                                                     |

<span data-ttu-id="3c6fc-147">Das folgende Beispiel zeigt eine config. XML-Datei für eine typische unbeaufsichtigte Installation des Skype for Business-Clients.</span><span class="sxs-lookup"><span data-stu-id="3c6fc-147">The following example shows a Config.xml file for a typical silent installation of the Skype for Business client.</span></span> 

```xml
<Configuration Product="Lync"> 
  <OptionState Id="LOBiMain" State="Absent" Children="Force" /> 
  <Display Level="None" CompletionNotice="No" AcceptEula="Yes" /> 
  <Logging Type="verbose" Path="%temp%" Template="LyncSetupVerbose(*).log" />
  <Setting Id="SETUP_REBOOT" Value="Never" /> 
  <DistributionPoint Location="\\server\share\Skype15" /> 
</Configuration>
```

<span data-ttu-id="3c6fc-148">Detaillierte Informationen zur Verwendung der Datei config. XML zum Ausführen von Office-Installations-und-Wartungs [https://go.microsoft.com/fwlink/p/?linkid=267514](https://go.microsoft.com/fwlink/p/?linkid=267514)Aufgaben finden Sie unter.</span><span class="sxs-lookup"><span data-stu-id="3c6fc-148">Detailed information about using the Config.xml file to perform Office installation and maintenance tasks is available at [https://go.microsoft.com/fwlink/p/?linkid=267514](https://go.microsoft.com/fwlink/p/?linkid=267514).</span></span>

## <a name="to-customize-the-configxml-file"></a><span data-ttu-id="3c6fc-149">So passen Sie die Datei "Config.xml" an</span><span class="sxs-lookup"><span data-stu-id="3c6fc-149">To customize the Config.xml file</span></span>

1. <span data-ttu-id="3c6fc-150">Öffnen Sie die Datei "Config.xml" in einem Text-Editor wie Editor.</span><span class="sxs-lookup"><span data-stu-id="3c6fc-150">Open the Config.xml file by using a text editor tool, such as Notepad.</span></span>

2. <span data-ttu-id="3c6fc-151">Suchen Sie die Zeilen, die die zu ändernden Elemente enthalten.</span><span class="sxs-lookup"><span data-stu-id="3c6fc-151">Locate the lines that contain the elements you want to change.</span></span>

3. <span data-ttu-id="3c6fc-152">Ändern Sie den Elementeintrag mit den gewünschten Optionen für eine automatische Installation.</span><span class="sxs-lookup"><span data-stu-id="3c6fc-152">Modify the element entry with the silent options that you want to use.</span></span> <span data-ttu-id="3c6fc-153">Stellen Sie sicher, dass Sie die Kommentartrennzeichen "\<!--" und "--\>" entfernen.</span><span class="sxs-lookup"><span data-stu-id="3c6fc-153">Make sure that you remove the comment delimiters, "\<!--" and "--\>".</span></span> <span data-ttu-id="3c6fc-154">Verwenden Sie z. B. die folgende Syntax:</span><span class="sxs-lookup"><span data-stu-id="3c6fc-154">For example, use the following syntax:</span></span>

   <pre>
   < DistributionPoint Location="\\server\share\Skype15" />
   </pre>

4. <span data-ttu-id="3c6fc-155">Speichern Sie die Datei Config.xml.</span><span class="sxs-lookup"><span data-stu-id="3c6fc-155">Save the Config.xml file.</span></span>


