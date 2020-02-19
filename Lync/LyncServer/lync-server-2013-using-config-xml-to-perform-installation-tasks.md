---
title: 'Lync Server 2013: Verwenden von "config. xml" zum Ausführen von Installationsaufgaben'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Using Config.xml to perform installation tasks
ms:assetid: 0813184a-ab40-417c-b3a3-c2090766b831
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204651(v=OCS.15)
ms:contentKeyID: 48183332
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7b6b06b270157bc1aa2387662229dbff3eb8f4d5
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2020
ms.locfileid: "42138716"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="using-configxml-to-perform-installation-tasks-in-lync-server-2013"></a><span data-ttu-id="bc05f-102">Verwenden von "config. xml" zum Ausführen von Installationsaufgaben in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="bc05f-102">Using Config.xml to perform installation tasks in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="bc05f-103">_**Letztes Änderungsstand des Themas:** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="bc05f-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="bc05f-p101">Das Office-Anpassungstool (OAT) ist zwar das primäre Tool für die angepasste Installation, Administratoren können jedoch mit der Datei "Config.xml" zusätzliche, im OAT nicht verfügbare Installationsanweisungen angeben. Die folgenden Anpassungen können nur mithilfe der Datei Config.xml vorgenommen werden:</span><span class="sxs-lookup"><span data-stu-id="bc05f-p101">Although the Office Customization Tool (OCT) is the primary tool for customization installation, administrators can use the Config.xml file to specify additional installation instructions that are not available in the OCT. The following customizations can only be made by using the Config.xml file:</span></span>

  - <span data-ttu-id="bc05f-106">Angeben des Netzwerkinstallationspfads</span><span class="sxs-lookup"><span data-stu-id="bc05f-106">Specify the path of the network installation point.</span></span>

  - <span data-ttu-id="bc05f-107">Auswählen der zu installierenden Produkte</span><span class="sxs-lookup"><span data-stu-id="bc05f-107">Select the products to install.</span></span>

  - <span data-ttu-id="bc05f-108">Konfigurieren der Protokollierung und des Speicherorts der Setupanpassungsdatei und Softwareupdates</span><span class="sxs-lookup"><span data-stu-id="bc05f-108">Configure logging and the location of the Setup customization file and software updates.</span></span>

  - <span data-ttu-id="bc05f-109">Angeben von Installationsoptionen, z. B. Benutzername</span><span class="sxs-lookup"><span data-stu-id="bc05f-109">Specify installation options, such as user name.</span></span>

  - <span data-ttu-id="bc05f-110">Kopieren der lokalen Installationsquelle (Local Installation Source, LIS) auf den Benutzercomputer ohne Installation von Office</span><span class="sxs-lookup"><span data-stu-id="bc05f-110">Copy the local installation source (LIS) to the user's computer without installing Office.</span></span>

  - <span data-ttu-id="bc05f-111">Hinzufügen oder Entfernen von Sprachen in der Installation</span><span class="sxs-lookup"><span data-stu-id="bc05f-111">Add or remove languages from the installation.</span></span>

<span data-ttu-id="bc05f-112">Es wird empfohlen, dass Sie die Datei "config. xml" verwenden, um lync 2013 unbeaufsichtigte Installation zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="bc05f-112">We recommend that you use the Config.xml file to configure Lync 2013 silent installation.</span></span>

<span data-ttu-id="bc05f-113">Standardmäßig die Datei "config. xml", die im Hauptproduktordner gespeichert ist (beispielsweise \\"Product. WW) weist Setup an, dieses Produkt zu installieren.</span><span class="sxs-lookup"><span data-stu-id="bc05f-113">By default, the Config.xml file that is stored in the core product folder (for example, \\product.WW) directs Setup to install that product.</span></span> <span data-ttu-id="bc05f-114">Beispielsweise wird in der Datei "config. xml" im folgenden Ordner lync 2013 installiert:</span><span class="sxs-lookup"><span data-stu-id="bc05f-114">For example, the Config.xml file in the following folder installs Lync 2013:</span></span>

  - <span data-ttu-id="bc05f-115">\\\\Server\\Freigabe\\Lync15\\lync. WW \\config. XML</span><span class="sxs-lookup"><span data-stu-id="bc05f-115">\\\\server\\share\\Lync15\\Lync.WW \\Config.xml</span></span>

<span data-ttu-id="bc05f-116">Die für lync 2013 Installation am häufigsten verwendeten config. XML-Elemente sind in der folgenden Tabelle aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="bc05f-116">The Config.xml elements most commonly used for Lync 2013 installation are listed in the following table.</span></span>

### <a name="configxml-elements"></a><span data-ttu-id="bc05f-117">Config.xml-Elemente</span><span class="sxs-lookup"><span data-stu-id="bc05f-117">Config.xml elements</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="bc05f-118">Element</span><span class="sxs-lookup"><span data-stu-id="bc05f-118">Element</span></span></th>
<th><span data-ttu-id="bc05f-119">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="bc05f-119">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="bc05f-120">Konfiguration</span><span class="sxs-lookup"><span data-stu-id="bc05f-120">Configuration</span></span></p></td>
<td><p><span data-ttu-id="bc05f-p103">Element der obersten Ebene (erforderlich). Enthält das Produktattribut, z. B.: Product=Lync</span><span class="sxs-lookup"><span data-stu-id="bc05f-p103">Top-level element (required). Contains the Product attribute, for example: Product=Lync</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bc05f-123">OptionState</span><span class="sxs-lookup"><span data-stu-id="bc05f-123">OptionState</span></span></p></td>
<td><p><span data-ttu-id="bc05f-124">Gibt an, wie bestimmte Produktfeatures während der Installation behandelt werden.</span><span class="sxs-lookup"><span data-stu-id="bc05f-124">Specifies how specific product features are handled during installation.</span></span> <span data-ttu-id="bc05f-125">Verwenden Sie die folgenden Attribute, um die Installation von Business Connectivity Services zu verhindern, die freigegebene Komponenten enthält, die die Outlook 2010 behindern:</span><span class="sxs-lookup"><span data-stu-id="bc05f-125">Use the following attributes to prevent installation of Business Connectivity Services, which includes shared components that interfere with Outlook 2010:</span></span></p>
<ul>
<li><p><span data-ttu-id="bc05f-126">ID =&quot;LOBiMain&quot;</span><span class="sxs-lookup"><span data-stu-id="bc05f-126">Id=&quot;LOBiMain&quot;</span></span></p></li>
<li><p><span data-ttu-id="bc05f-127">State =&quot;abwesend&quot;</span><span class="sxs-lookup"><span data-stu-id="bc05f-127">State=&quot;Absent&quot;</span></span></p></li>
<li><p><span data-ttu-id="bc05f-128">Children =&quot;Force&quot;</span><span class="sxs-lookup"><span data-stu-id="bc05f-128">Children=&quot;Force&quot;</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bc05f-129">Anzeige</span><span class="sxs-lookup"><span data-stu-id="bc05f-129">Display</span></span></p></td>
<td><p><span data-ttu-id="bc05f-p105">Die Ebene der Benutzeroberfläche, die dem Benutzer angezeigt wird. Zu den typischen Attributen zählen Folgende:</span><span class="sxs-lookup"><span data-stu-id="bc05f-p105">The level of UI that Setup displays to the user. Typical attributes include the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="bc05f-132">CompletionNotice =&quot;ja&quot; | &quot;Nein&quot;(Standard)</span><span class="sxs-lookup"><span data-stu-id="bc05f-132">CompletionNotice=&quot;Yes&quot; | &quot;No&quot;(default)</span></span></p></li>
<li><p><span data-ttu-id="bc05f-133">AcceptEULA =&quot;ja&quot; | &quot;Nein&quot;(Standard)</span><span class="sxs-lookup"><span data-stu-id="bc05f-133">AcceptEula=&quot;Yes&quot; | &quot;No&quot;(default)</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bc05f-134">Protokollierung</span><span class="sxs-lookup"><span data-stu-id="bc05f-134">Logging</span></span></p></td>
<td><p><span data-ttu-id="bc05f-p106">Optionen für den vom Setup ausgeführten Protokollierungstyp. Zu den typischen Attributen zählen Folgende:</span><span class="sxs-lookup"><span data-stu-id="bc05f-p106">Options for the kind of logging that Setup performs. Typical attributes include the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="bc05f-137">Type =&quot;off&quot; | &quot;Standard&quot;(Standard) | &quot;Ausführlich&quot;</span><span class="sxs-lookup"><span data-stu-id="bc05f-137">Type =&quot;Off&quot; | &quot;Standard&quot;(default) | &quot;Verbose&quot;</span></span></p></li>
<li><p><span data-ttu-id="bc05f-138">Template=”Dateiname.txt” (Name der Protokolldatei)</span><span class="sxs-lookup"><span data-stu-id="bc05f-138">Template=”filename.txt” (the name of the log file)</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bc05f-139">Einstellung</span><span class="sxs-lookup"><span data-stu-id="bc05f-139">Setting</span></span></p></td>
<td><p><span data-ttu-id="bc05f-p107">Gibt Werte für Windows Installer-Eigenschaften an. Zu den typischen Attributen zählen Folgende:</span><span class="sxs-lookup"><span data-stu-id="bc05f-p107">Specifies values for Windows Installer properties. Typical attributes include the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="bc05f-142">Setting ID =&quot;Name&quot; (der Name der Windows Installer-Eigenschaft)</span><span class="sxs-lookup"><span data-stu-id="bc05f-142">Setting Id=&quot;name&quot; (the name of the Windows Installer property)</span></span></p></li>
<li><p><span data-ttu-id="bc05f-143">Wert =&quot;Wert&quot; (der Wert, der der Eigenschaft zugewiesen werden soll)</span><span class="sxs-lookup"><span data-stu-id="bc05f-143">Value=&quot;value&quot; (the value to assign to the property)</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bc05f-144">DistributionPoint</span><span class="sxs-lookup"><span data-stu-id="bc05f-144">DistributionPoint</span></span></p></td>
<td><p><span data-ttu-id="bc05f-p108">Der vollqualifizierte Pfad des Netzwerkinstallationspfads, von dem die Installation ausgeführt werden soll. Enthält das Standortattribut:</span><span class="sxs-lookup"><span data-stu-id="bc05f-p108">The fully qualified path of the network installation point from which the installation is to run. Includes the Location attribute:</span></span></p>
<ul>
<li><p><span data-ttu-id="bc05f-147">Location = "Pfad"</span><span class="sxs-lookup"><span data-stu-id="bc05f-147">Location=”path”</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


<span data-ttu-id="bc05f-148">Das folgende Beispiel zeigt eine Datei "config. xml" für eine typische automatische Installation von lync 2013.</span><span class="sxs-lookup"><span data-stu-id="bc05f-148">The following example shows a Config.xml file for a typical silent installation of Lync 2013.</span></span>

    <Configuration Product="Lync">
      <OptionState Id="LOBiMain" State="Absent" Children="Force" />
      <Display Level="None" CompletionNotice="No" AcceptEula="Yes" />
      <Logging Type="verbose" Path="%temp%" Template="LyncSetupVerbose(*).log" />
      <Setting Id="SETUP_REBOOT" Value="Never" />
      <DistributionPoint Location="\\server\share\Lync15" />
    </Configuration>

<span data-ttu-id="bc05f-149">Ausführliche Informationen zur Verwendung der Datei "config. xml" zur Durchführung von Office-Installations- <https://go.microsoft.com/fwlink/p/?linkid=267514>und Wartungsaufgaben finden Sie unter.</span><span class="sxs-lookup"><span data-stu-id="bc05f-149">Detailed information about using the Config.xml file to perform Office installation and maintenance tasks is available at <https://go.microsoft.com/fwlink/p/?linkid=267514>.</span></span>

<div>

## <a name="to-customize-the-configxml-file"></a><span data-ttu-id="bc05f-150">So passen Sie die Datei "Config.xml" an</span><span class="sxs-lookup"><span data-stu-id="bc05f-150">To customize the Config.xml file</span></span>

1.  <span data-ttu-id="bc05f-151">Öffnen Sie die Datei "Config.xml" in einem Text-Editor wie Editor.</span><span class="sxs-lookup"><span data-stu-id="bc05f-151">Open the Config.xml file by using a text editor tool, such as Notepad.</span></span>

2.  <span data-ttu-id="bc05f-152">Suchen Sie die Zeilen, die die zu ändernden Elemente enthalten.</span><span class="sxs-lookup"><span data-stu-id="bc05f-152">Locate the lines that contain the elements you want to change.</span></span>

3.  <span data-ttu-id="bc05f-153">Ändern Sie den Elementeintrag mit den gewünschten Optionen für eine automatische Installation.</span><span class="sxs-lookup"><span data-stu-id="bc05f-153">Modify the element entry with the silent options that you want to use.</span></span> <span data-ttu-id="bc05f-154">Stellen Sie sicher, dass Sie die Kommentartrennzeichen "\<\!--" und "--\>" entfernen.</span><span class="sxs-lookup"><span data-stu-id="bc05f-154">Make sure that you remove the comment delimiters, "\<\!--" and "--\>".</span></span> <span data-ttu-id="bc05f-155">Verwenden Sie z. B. die folgende Syntax:</span><span class="sxs-lookup"><span data-stu-id="bc05f-155">For example, use the following syntax:</span></span>
    
        < DistributionPoint Location="\\server\share\Lync15" />

4.  <span data-ttu-id="bc05f-156">Speichern Sie die Datei Config.xml.</span><span class="sxs-lookup"><span data-stu-id="bc05f-156">Save the Config.xml file.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

