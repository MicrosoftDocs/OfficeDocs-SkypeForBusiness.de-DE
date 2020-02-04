---
title: 'Lync Server 2013: Konfigurieren von benutzerdefinierten Anwesenheitsstatus'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring custom presence states
ms:assetid: e17364a8-8b93-45fc-a614-c80e45435d42
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398997(v=OCS.15)
ms:contentKeyID: 48185534
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c69f7a5b32b4ad0dd31f8be118aa2f2173ff3e22
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41758195"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-custom-presence-states-in-lync-server-2013"></a><span data-ttu-id="b1b50-102">Konfigurieren von benutzerdefinierten Anwesenheitsstatus in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b1b50-102">Configuring custom presence states in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b1b50-103">_**Letztes Änderungsdatum des Themas:** 2013-01-10_</span><span class="sxs-lookup"><span data-stu-id="b1b50-103">_**Topic Last Modified:** 2013-01-10_</span></span>

<span data-ttu-id="b1b50-104">Wenn Sie benutzerdefinierte Anwesenheitsstatus in lync 2013 definieren möchten, erstellen Sie eine XML-Konfigurationsdatei für benutzerdefinierte Anwesenheitsinformationen, und geben Sie dann den Speicherort mithilfe der lync Server-Verwaltungsshell-Cmdlets **New-CSClientPolicy** oder **CSClientPolicy** mit dem Parameter CustomStateURL an.</span><span class="sxs-lookup"><span data-stu-id="b1b50-104">To define custom presence states in Lync 2013, create an XML custom presence configuration file, and then specify its location by using the Lync Server Management Shell cmdlets **New-CSClientPolicy** or **Set-CSClientPolicy** with the parameter CustomStateURL.</span></span>

<span data-ttu-id="b1b50-105">Konfigurationsdateien weisen die folgenden Eigenschaften auf:</span><span class="sxs-lookup"><span data-stu-id="b1b50-105">Configuration files have the following properties:</span></span>

  - <span data-ttu-id="b1b50-106">Benutzerdefinierte Anwesenheitsstatus können mit den Anwesenheits Indikatoren "verfügbar", "beschäftigt" und "nicht stören" konfiguriert werden.</span><span class="sxs-lookup"><span data-stu-id="b1b50-106">Custom presence states can be configured with the Available, Busy, and Do Not Disturb presence indicators.</span></span>

  - <span data-ttu-id="b1b50-107">Das Availability-Attribut bestimmt, welcher Anwesenheitsindikator dem Statustext des benutzerdefinierten Zustands zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="b1b50-107">The availability attribute determines which presence indicator is associated with the status text of the custom state.</span></span> <span data-ttu-id="b1b50-108">Im Beispiel weiter unten in diesem Thema wird der StatusText, der von zu Hause aus funktioniert, rechts neben dem grünen (verfügbaren) Anwesenheitsindikator angezeigt.</span><span class="sxs-lookup"><span data-stu-id="b1b50-108">In the example later in this topic, the status text Working from Home is displayed to the right of the green (Available) presence indicator.</span></span>

  - <span data-ttu-id="b1b50-109">Die maximale Länge des Status Texts beträgt 64 Zeichen.</span><span class="sxs-lookup"><span data-stu-id="b1b50-109">The maximum length of the status text is 64 characters.</span></span>

  - <span data-ttu-id="b1b50-110">Es können maximal vier benutzerdefinierte Anwesenheitsstatus hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="b1b50-110">A maximum of four custom presence states can be added.</span></span>

  - <span data-ttu-id="b1b50-111">Der CustomStateURL-Parameter gibt den Speicherort der Konfigurationsdatei an.</span><span class="sxs-lookup"><span data-stu-id="b1b50-111">The CustomStateURL parameter specifies the location of the configuration file.</span></span> <span data-ttu-id="b1b50-112">In lync 2013 ist der SIP-Modus für höhere Sicherheit standardmäßig aktiviert, daher müssen Sie die benutzerdefinierte Anwesenheits Konfigurationsdatei auf einem Webserver speichern, auf dem HTTPS aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="b1b50-112">In Lync 2013, SIP high security mode is enabled by default, so you will need to store the custom presence configuration file on a web server that has HTTPS enabled.</span></span> <span data-ttu-id="b1b50-113">Andernfalls können lync 2013-Clients keine Verbindung herstellen.</span><span class="sxs-lookup"><span data-stu-id="b1b50-113">Otherwise, Lync 2013 clients will be unable to connect to it.</span></span> <span data-ttu-id="b1b50-114">Eine gültige Adresse lautet beispielsweise `https://lspool.corp.contoso.com/ClientConfigFolder/CustomPresence.xml`.</span><span class="sxs-lookup"><span data-stu-id="b1b50-114">For example, a valid address would be `https://lspool.corp.contoso.com/ClientConfigFolder/CustomPresence.xml`.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="b1b50-115">Obwohl es in einer Produktionsumgebung nicht empfohlen wird, können Sie eine Konfigurationsdatei testen, die sich auf einer nicht-HTTPS-Dateifreigabe befindet, indem Sie die Registrierungseinstellung EnableSIPHighSecurityMode verwenden, um den SIP-Modus für höchste Sicherheit auf dem Client zu deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="b1b50-115">Although it is not recommended in a production environment, you can test a configuration file that is located on a non-HTTPS file share by using the EnableSIPHighSecurityMode registry setting to disable SIP high security mode on the client.</span></span> <span data-ttu-id="b1b50-116">Anschließend können Sie die Registrierungseinstellung CustomStateURL verwenden, um einen nicht-HTTPS-Speicherort für die Konfigurationsdatei anzugeben.</span><span class="sxs-lookup"><span data-stu-id="b1b50-116">Then you can use the CustomStateURL registry setting to specify a non-HTTPS location for the configuration file.</span></span> <span data-ttu-id="b1b50-117">Beachten Sie, dass lync 2013 die Registrierungseinstellungen von lync 2010 ehrt, die Registrierungsstruktur jedoch aktualisiert wurde.</span><span class="sxs-lookup"><span data-stu-id="b1b50-117">Note that Lync 2013 honors Lync 2010 registry settings, but the registry hive has been updated.</span></span> <span data-ttu-id="b1b50-118">Sie würden die Registrierungseinstellungen wie folgt erstellen:</span><span class="sxs-lookup"><span data-stu-id="b1b50-118">You would create the registry settings as follows:</span></span> 
> <UL>
> <LI>
> <P><span data-ttu-id="b1b50-119">HKEY_LOCAL_MACHINE \software\policies\microsoft\office\15.0\lync\enablesiphighsecuritymode</span><span class="sxs-lookup"><span data-stu-id="b1b50-119">HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Office\15.0\Lync\EnableSIPHighSecurityMode</span></span></P>
> <P><span data-ttu-id="b1b50-120">Geben Sie Folgendes ein: DWORD</span><span class="sxs-lookup"><span data-stu-id="b1b50-120">Type: DWORD</span></span></P>
> <P><span data-ttu-id="b1b50-121">Wertdaten: 0</span><span class="sxs-lookup"><span data-stu-id="b1b50-121">Value data: 0</span></span></P>
> <LI>
> <P><span data-ttu-id="b1b50-122">HKEY_LOCAL_MACHINE \software\policies\microsoft\office\15.0\lync\customstateurl</span><span class="sxs-lookup"><span data-stu-id="b1b50-122">HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Office\15.0\Lync\CustomStateURL</span></span></P>
> <P><span data-ttu-id="b1b50-123">Typ: Zeichenfolge (REG_SZ)</span><span class="sxs-lookup"><span data-stu-id="b1b50-123">Type: String (REG_SZ)</span></span></P>
> <P><span data-ttu-id="b1b50-124">Werte Daten (Beispiele): file://\\lspool. Corp. contoso. com\LSFileShare\ClientConfigFolder\Presence.XML oder file:///c:/LSFileShare/ClientConfigFolder/Group_1_Pres.XML</span><span class="sxs-lookup"><span data-stu-id="b1b50-124">Value data (examples): file://\\lspool.corp.contoso.com\LSFileShare\ClientConfigFolder\Presence.xml or file:///c:/LSFileShare/ClientConfigFolder/Group_1_Pres.xml</span></span></P></LI></UL>



</div>

<span data-ttu-id="b1b50-125">Lokalisieren Sie Ihren benutzerdefinierten Anwesenheitsstatus, indem Sie ein oder mehrere Gebietsschema-ID-Schemas (LCID) in der XML-Konfigurationsdatei angeben.</span><span class="sxs-lookup"><span data-stu-id="b1b50-125">Localize your custom presence state by specifying one or more locale ID (LCID) schema in the XML configuration file.</span></span> <span data-ttu-id="b1b50-126">Das Beispiel weiter unten in diesem Thema zeigt die Lokalisierung in Englisch (USA) (1033), Norwegisch-Nynorsk (1044), Französisch-Frankreich (1036) und Türkisch (1055).</span><span class="sxs-lookup"><span data-stu-id="b1b50-126">The example later in this topic shows localization into English - United States (1033), Norwegian - Bokmål (1044), French - France (1036), and Turkish (1055).</span></span> <span data-ttu-id="b1b50-127">Eine Liste der LCIDs finden Sie Untergebiets Schema-IDs, die <http://go.microsoft.com/fwlink/p/?linkid=157331>von Microsoft at zugewiesen wurden.</span><span class="sxs-lookup"><span data-stu-id="b1b50-127">For a list of LCIDs, see Locale IDs Assigned by Microsoft at <http://go.microsoft.com/fwlink/p/?linkid=157331>.</span></span>

<div>

## <a name="to-add-custom-presence-states-to-lync-2013"></a><span data-ttu-id="b1b50-128">So fügen Sie benutzerdefinierte Anwesenheitsstatus zu lync 2013 hinzu</span><span class="sxs-lookup"><span data-stu-id="b1b50-128">To add custom presence states to Lync 2013</span></span>

1.  <span data-ttu-id="b1b50-129">Erstellen Sie eine XML-Konfigurationsdatei, die das Format des folgenden Beispiels verwendet:</span><span class="sxs-lookup"><span data-stu-id="b1b50-129">Create an XML configuration file that uses the format of the following example:</span></span>
    
        <?xml version="1.0"?>
        <customStates xmlns="http://schemas.microsoft.com/09/2009/communicator/customStates">
          <customState ID="1" availability="online">
            <activity LCID="1033">Working from Home</activity>
            <activity LCID="1044">activity 2 for 1044</activity>
            <activity LCID="1055">activity 3 for 1055</activity>
          </customState>
          <customState ID="2" availability="busy">
            <activity LCID="1033">In a Live Meeting</activity>
            <activity LCID="1036">Equivalent French String for - In a Live Meeting </activity>
          </customState>
          <customState ID="3" availability="busy">
            <activity LCID="1033">Meeting with Customer</activity>
            <activity LCID="1055">meeting with client</activity>
            <activity LCID="1036">Equivalent French String for - Meeting with Customer</activity>
          </customState>
          <customState ID="4" availability="do-not-disturb">
            <activity LCID="1033">Interviewing</activity>
          </customState>
        </customStates>

2.  <span data-ttu-id="b1b50-130">Speichern Sie die XML-Konfigurationsdatei auf einem Webserver mit aktiviertem HTTPS.</span><span class="sxs-lookup"><span data-stu-id="b1b50-130">Save the XML configuration file to a web server with HTTPS enabled.</span></span> <span data-ttu-id="b1b50-131">In diesem Beispiel wird die Datei "Presence. xml" genannt und an dem Speicherort https://lspool.corp.contoso.com/ClientConfigFolder/CustomPresence.xmlgespeichert.</span><span class="sxs-lookup"><span data-stu-id="b1b50-131">In this example, the file is named Presence.xml and saved to the location https://lspool.corp.contoso.com/ClientConfigFolder/CustomPresence.xml.</span></span>

3.  <span data-ttu-id="b1b50-132">Starten Sie die lync Server-Verwaltungsshell: Klicken Sie auf **Start**, klicken Sie auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server-Verwaltungsshell**.</span><span class="sxs-lookup"><span data-stu-id="b1b50-132">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

4.  <span data-ttu-id="b1b50-133">Definieren Sie in der lync Server-Verwaltungsshell den Speicherort der XML-Konfigurationsdatei mithilfe eines Befehls, der der folgenden ähnelt:</span><span class="sxs-lookup"><span data-stu-id="b1b50-133">In the Lync Server Management Shell, define the location of your XML configuration file by using a command similar to the following:</span></span>
    
        New-CsClientPolicy -Identity ContosoCustomStates 
        -CustomStateURL "https://lspool.corp.contoso.com/ClientConfigFolder/CustomPresence.xml"

5.  <span data-ttu-id="b1b50-134">Verwenden Sie das Cmdlet **Grant-CSClientPolicy** , um diese neue Richtlinie Benutzern zuzuweisen.</span><span class="sxs-lookup"><span data-stu-id="b1b50-134">Use the **Grant-CSClientPolicy** cmdlet to assign this new policy to users.</span></span>

<span data-ttu-id="b1b50-135">Ausführliche Informationen finden Sie unter [New-CsClientPolicy](https://docs.microsoft.com/powershell/module/skype/New-CsClientPolicy) und [Grant-CsClientPolicy](https://docs.microsoft.com/powershell/module/skype/Grant-CsClientPolicy) in der Dokumentation zur lync Server-Verwaltungsshell.</span><span class="sxs-lookup"><span data-stu-id="b1b50-135">For details, see [New-CsClientPolicy](https://docs.microsoft.com/powershell/module/skype/New-CsClientPolicy) and [Grant-CsClientPolicy](https://docs.microsoft.com/powershell/module/skype/Grant-CsClientPolicy) in the Lync Server Management Shell documentation.</span></span>

<div>


> [!NOTE]  
> <UL>
> <LI>
> <P><span data-ttu-id="b1b50-136">Standardmäßig aktualisiert lync Server 2013&nbsp;die Clientrichtlinien und-Einstellungen alle drei Stunden.</span><span class="sxs-lookup"><span data-stu-id="b1b50-136">By default, Lync Server 2013&nbsp;updates client policies and settings every three hours.</span></span></P>
> <LI>
> <P><span data-ttu-id="b1b50-137">Wenn Sie weiterhin Gruppenrichtlinieneinstellungen aus früheren Versionen wie CustomStateURL verwenden möchten, erkennt lync 2013 die Einstellungen, wenn Sie sich in der neuen Richtlinien Registrierungsstruktur (HKEY_LOCAL_MACHINE \software\policies\microsoft\office\15.0\lync) befinden.</span><span class="sxs-lookup"><span data-stu-id="b1b50-137">If you want to continue using Group Policy settings from previous releases, such as CustomStateURL, Lync 2013 will recognize the settings if they are located in the new policy registry hive (HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Office\15.0\Lync).</span></span> <span data-ttu-id="b1b50-138">Serverbasierte Clientrichtlinien haben jedoch Vorrang.</span><span class="sxs-lookup"><span data-stu-id="b1b50-138">However, server-based client policies take precedence.</span></span></P></LI></UL>



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

