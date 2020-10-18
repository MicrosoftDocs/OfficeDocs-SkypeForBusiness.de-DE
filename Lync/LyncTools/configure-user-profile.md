---
title: Konfigurieren des Benutzerprofils
description: Konfigurieren Sie das Benutzerprofil.
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Configure User Profile
ms:assetid: 52713245-e502-4539-a238-66ff1aca26b1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945594(v=OCS.15)
ms:contentKeyID: 51541419
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 682297da43797dd2d774094e85e8688ef3c64d98
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48573091"
---
# <a name="configure-user-profile"></a><span data-ttu-id="85bbf-103">Konfigurieren des Benutzerprofils</span><span class="sxs-lookup"><span data-stu-id="85bbf-103">Configure User Profile</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="85bbf-104">_**Letztes Änderungsstand des Themas:** 2018-10-11_</span><span class="sxs-lookup"><span data-stu-id="85bbf-104">_**Topic Last Modified:** 2018-10-11_</span></span>

<span data-ttu-id="85bbf-105">Mit den im lync Server 2013 Stress and Performance Tool-Paket enthaltenen Tools können Sie Testbenutzerkonten erstellen und konfigurieren, mit denen Sie Auslastungssimulationen ausführen können.</span><span class="sxs-lookup"><span data-stu-id="85bbf-105">The tools included in the Lync Server 2013 Stress and Performance Tool package enable you to create and configure test user accounts that you can use to run load simulations.</span></span> <span data-ttu-id="85bbf-106">Verwenden Sie das lync Server 2013 Benutzer Erstellungs Tool, um die Benutzer zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="85bbf-106">Use the Lync Server 2013 User Creation Tool to create the users.</span></span> <span data-ttu-id="85bbf-107">(Weitere Informationen finden Sie unter [Create users and Contacts](create-users-and-contacts.md).) Nachdem Benutzer erstellt wurden, konfigurieren Sie die Benutzerprofile mithilfe des lync Server 2013 Tools zum Laden der Konfiguration.</span><span class="sxs-lookup"><span data-stu-id="85bbf-107">(For details, see [Create Users and Contacts](create-users-and-contacts.md).) After users are created, configure the user profiles by using the Lync Server 2013 Load Configuration Tool.</span></span>

<div>

## <a name="running-the-lync-server-2013-load-configuration-tool"></a><span data-ttu-id="85bbf-108">Ausführung des lync Server 2013 Lade Konfigurationstools</span><span class="sxs-lookup"><span data-stu-id="85bbf-108">Running the Lync Server 2013 Load Configuration Tool</span></span>

<span data-ttu-id="85bbf-109">Zum Konfigurieren von Benutzerprofilen führen Sie das lync Server 2013 Konfigurations Tool für die Auslastung (UserProfileGenerator.exe) aus, und füllen Sie die einzelnen Registerkarten aus.</span><span class="sxs-lookup"><span data-stu-id="85bbf-109">To configure user profiles, run the Lync Server 2013 Load Configuration Tool (UserProfileGenerator.exe) and fill out each of the tabs.</span></span> <span data-ttu-id="85bbf-110">UserProfileGenerator.exe generiert ein Verzeichnis für jeden Clientcomputer, den Sie zum Ausführen der Simulation benötigen.</span><span class="sxs-lookup"><span data-stu-id="85bbf-110">UserProfileGenerator.exe generates a directory for each of the client computers that you need to run the simulation.</span></span> <span data-ttu-id="85bbf-111">Jedes Clientverzeichnis enthält auch ein Skript zum Starten aller Instanzen des lync Server 2013 Stress and Performance Tool (LyncPerfTool.exe).</span><span class="sxs-lookup"><span data-stu-id="85bbf-111">Each client directory also comes with a script to start all the instances of the Lync Server 2013 Stress and Performance Tool (LyncPerfTool.exe).</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="85bbf-112">Die in UserProfileGenerator angegebenen benutzerspezifischen Werte müssen mit den Werten übereinstimmen, die im lync Server 2013-Benutzer Erstellungs Tool (UserProvisioningTool) für den Pool angegeben sind.</span><span class="sxs-lookup"><span data-stu-id="85bbf-112">The user-specific values specified in UserProfileGenerator must match the values specified in the Lync Server 2013 User Creation Tool (UserProvisioningTool) for the pool.</span></span>



</div>

<span data-ttu-id="85bbf-113">Füllen Sie die Felder auf jeder Registerkarte des lync Server 2013 Auslastungs Konfigurationstools aus, wie in den folgenden Abschnitten beschrieben.</span><span class="sxs-lookup"><span data-stu-id="85bbf-113">Fill in the fields on each tab of the Lync Server 2013 Load Configuration Tool, as described in the following sections.</span></span>

<div>

## <a name="common-configuration"></a><span data-ttu-id="85bbf-114">Allgemeine Konfiguration</span><span class="sxs-lookup"><span data-stu-id="85bbf-114">Common Configuration</span></span>

<span data-ttu-id="85bbf-115">Die folgende Abbildung zeigt die Registerkarte " **Allgemeine Konfiguration** " des lync Server 2013 Tools zum Laden der Konfiguration.</span><span class="sxs-lookup"><span data-stu-id="85bbf-115">The **Common Configuration** tab of the Lync Server 2013 Load Configuration Tool is shown in the following figure.</span></span> <span data-ttu-id="85bbf-116">Füllen Sie die Felder auf der Registerkarte **Allgemeine Konfiguration** aus, wie in den folgenden Schritten beschrieben.</span><span class="sxs-lookup"><span data-stu-id="85bbf-116">Fill in the fields of the **Common Configuration** tab, as described in the following steps.</span></span>

<span data-ttu-id="85bbf-117">![Allgemeine Konfigurationsregisterkarte.](images/JJ945594.c68dcc8f-10f2-499e-95a2-fccbcc206c2f(OCS.15).jpg "Allgemeine Konfigurationsregisterkarte.")</span><span class="sxs-lookup"><span data-stu-id="85bbf-117">![Common Configuration tab.](images/JJ945594.c68dcc8f-10f2-499e-95a2-fccbcc206c2f(OCS.15).jpg "Common Configuration tab.")</span></span>

1.  <span data-ttu-id="85bbf-118">Geben Sie unter **Anzahl der verfügbaren**Computer die Anzahl von Computern ein, die Sie zum Ausführen LyncPerfTool.exe verwenden möchten, oder klicken Sie auf.</span><span class="sxs-lookup"><span data-stu-id="85bbf-118">In **Number of Available Machines**, type or click the number of computers that you want to use to run LyncPerfTool.exe.</span></span> <span data-ttu-id="85bbf-119">Es wird empfohlen, dass Sie einen Computer für jeden 4.500-Benutzer haben, den Sie simulieren werden.</span><span class="sxs-lookup"><span data-stu-id="85bbf-119">We recommend that you have one computer for every 4,500 users that you will be simulating.</span></span> <span data-ttu-id="85bbf-120">Diese Nummer kann variieren, wenn Sie die Auslastungsstufe verringern oder wenn Sie nur eine Teilmenge der verfügbaren Features verwenden.</span><span class="sxs-lookup"><span data-stu-id="85bbf-120">That number may vary if you reduce the load level or if you use only a subset of the available features.</span></span> <span data-ttu-id="85bbf-121">(Auf der Registerkarte **Allgemeine Szenarien** werden Ladestufen festgelegt.)</span><span class="sxs-lookup"><span data-stu-id="85bbf-121">(Load levels are set on the **General Scenarios** tab.)</span></span>

2.  <span data-ttu-id="85bbf-122">Geben Sie unter **Präfix für Benutzernamen**das Präfix für den Benutzernamen der Benutzer ein.</span><span class="sxs-lookup"><span data-stu-id="85bbf-122">In **Prefix for User Names**, type the prefix for the user name of the users.</span></span> <span data-ttu-id="85bbf-123">Um sich anzumelden, wird der URI (Uniform Resource Identifier): UserPrefix \[ User Start Index... (Anzahl der Benutzer-1) \] @User Domäne.</span><span class="sxs-lookup"><span data-stu-id="85bbf-123">To log in, the Uniform Resource Identifier (URI) will be: UserPrefix\[User Start Index…(Number Of Users-1)\]@User Domain.</span></span>

3.  <span data-ttu-id="85bbf-124">Geben Sie unter **Kennwort für alle Benutzer**das Kennwort ein, das zum Erstellen der Benutzer verwendet wurde.</span><span class="sxs-lookup"><span data-stu-id="85bbf-124">In **Password for All Users**, enter the password that was used for creating the users.</span></span> <span data-ttu-id="85bbf-125">Wenn Sie dieses Feld leer lassen, wird der Benutzername als Kennwort verwendet.</span><span class="sxs-lookup"><span data-stu-id="85bbf-125">If you leave this field empty, the username will be used as the password.</span></span>

4.  <span data-ttu-id="85bbf-126">Klicken Sie im **Start Index des Benutzers**auf oder geben Sie den Index des ersten Benutzers ein, der konfiguriert werden soll.</span><span class="sxs-lookup"><span data-stu-id="85bbf-126">In **User Start Index**, click or type the index of the first user to be configured.</span></span> <span data-ttu-id="85bbf-127">Sie können verschiedene Bereiche für verschiedene Typen oder Last Ebenen konfigurieren, aber Sie müssen UserProfileGenerator.exe einmal pro Bereich ausführen, den Sie konfigurieren möchten.</span><span class="sxs-lookup"><span data-stu-id="85bbf-127">You can configure different ranges for different types or levels of load, but you must run UserProfileGenerator.exe once per the range that you want to configure.</span></span>

5.  <span data-ttu-id="85bbf-128">Klicken Sie unter **Anzahl der Benutzer**auf oder geben Sie die Gesamtzahl der Benutzer ein, die Sie konfigurieren möchten.</span><span class="sxs-lookup"><span data-stu-id="85bbf-128">In **Number of Users**, click or type the total number of users you are going to configure.</span></span>

6.  <span data-ttu-id="85bbf-129">Geben Sie in **Benutzerdomäne**die für den SIP-URI verwendete Domäne ein.</span><span class="sxs-lookup"><span data-stu-id="85bbf-129">In **User Domain**, type the domain used for the SIP URI.</span></span> <span data-ttu-id="85bbf-130">Dies wird verwendet, um den SIP-URI jedes Benutzers zu erstellen, der sich am lync Server 2013 Front-End-Server oder Standard Edition-Server anmeldet.</span><span class="sxs-lookup"><span data-stu-id="85bbf-130">This is used to construct the SIP URI of each user to log on to the Lync Server 2013 Front End Server or Standard Edition server.</span></span> <span data-ttu-id="85bbf-131">Es kann sich von der Kontodomäne unterscheiden.</span><span class="sxs-lookup"><span data-stu-id="85bbf-131">It can be different from the account domain.</span></span>

7.  <span data-ttu-id="85bbf-132">Geben Sie unter **Kontodomäne**die Active Directory-Domänendienste Domänenanmeldung ein.</span><span class="sxs-lookup"><span data-stu-id="85bbf-132">In **Account Domain**, type the Active Directory Domain Services domain logon.</span></span>

8.  <span data-ttu-id="85bbf-133">Geben Sie die maximale Anzahl gleichzeitiger Endpunkte in der **Anmeldung pro Sekunde (pro Instanz)** ein, für die das Tool sich in allen Endpunkten/Benutzern anmelden soll.</span><span class="sxs-lookup"><span data-stu-id="85bbf-133">Enter the maximum number of concurrent endpoints in **Sign In Per Second (per instance)** for which you want the tool to log in all the endpoints/users.</span></span> <span data-ttu-id="85bbf-134">Die empfohlene Rate beträgt \< = 2 pro Sekunde/Standard-SKU Fe.</span><span class="sxs-lookup"><span data-stu-id="85bbf-134">The recommended rate is \<=2 per second/standard SKU FE.</span></span>

9.  <span data-ttu-id="85bbf-135">Geben Sie in **Zugriffs Proxy oder Pool-FQDN**den vollqualifizierten Domänennamen (FQDN) des Servers ein, mit dem die Clients eine Verbindung herstellen möchten.</span><span class="sxs-lookup"><span data-stu-id="85bbf-135">In **Access Proxy or Pool FQDN**, type the fully qualified domain name (FQDN) of the server that you want the clients to connect to.</span></span> <span data-ttu-id="85bbf-136">Wenn sich die Benutzer extern anmelden, geben Sie den Zugriffsproxy an.</span><span class="sxs-lookup"><span data-stu-id="85bbf-136">If the users are logging on externally, specify the access proxy.</span></span> <span data-ttu-id="85bbf-137">Wenn die Benutzer intern sind, geben Sie den FQDN des Pools oder Standard Edition-Server an.</span><span class="sxs-lookup"><span data-stu-id="85bbf-137">If the users are internal, specify the FQDN of their pool or Standard Edition server.</span></span>

10. <span data-ttu-id="85bbf-138">Klicken oder geben Sie in **Port**den Port ein, den Benutzer für SIP verwenden sollen (der Standardwert lautet 5061).</span><span class="sxs-lookup"><span data-stu-id="85bbf-138">In **Port**, click or type the port that you want users to use for SIP (the default is 5061).</span></span>

<span data-ttu-id="85bbf-139">Geben Sie für externe Netzwerk Server Einstellungen den **Zugriffs Proxy oder Pool-FQDN** und den **Port**an.</span><span class="sxs-lookup"><span data-stu-id="85bbf-139">For External Network Server Settings, specify the **Access Proxy or Pool FQDN** and the **Port**.</span></span> <span data-ttu-id="85bbf-140">Diese Einstellungen werden nur für die Auslastungssimulation externer Endpunkte verwendet.</span><span class="sxs-lookup"><span data-stu-id="85bbf-140">These settings are used only for External endpoints load simulation.</span></span>

</div>

<div>

## <a name="general-scenarios"></a><span data-ttu-id="85bbf-141">Allgemeine Szenarien</span><span class="sxs-lookup"><span data-stu-id="85bbf-141">General Scenarios</span></span>

<span data-ttu-id="85bbf-142">Die folgende Abbildung zeigt die Registerkarte **Allgemeine Szenarien** des lync Server 2013 Tools zum Laden der Konfiguration.</span><span class="sxs-lookup"><span data-stu-id="85bbf-142">The **General Scenarios** tab of the Lync Server 2013 Load Configuration Tool is shown in the following figure.</span></span>

<span data-ttu-id="85bbf-143">Konfigurieren Sie die Ladestufen und Parameter für jedes der allgemeinen Szenarien, die Sie ausführen möchten, oder lassen Sie die Option deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="85bbf-143">Configure the load levels and parameters for each of the general scenarios that you want to run, or leave disabled.</span></span>

<span data-ttu-id="85bbf-144">![Registerkarte Allgemeine Szenarien.](images/JJ945594.4f046d39-b532-4baf-99a6-c89d1d6d1fcc(OCS.15).jpg "Registerkarte Allgemeine Szenarien.")</span><span class="sxs-lookup"><span data-stu-id="85bbf-144">![General Scenarios tab.](images/JJ945594.4f046d39-b532-4baf-99a6-c89d1d6d1fcc(OCS.15).jpg "General Scenarios tab.")</span></span>

1.  <span data-ttu-id="85bbf-145">Geben Sie in **Instant Messaging**, das Peer-to-Peer und Konferenzen umfasst, den entsprechenden Wert für die Auslastungsstufe an.</span><span class="sxs-lookup"><span data-stu-id="85bbf-145">In **Instant Messaging**, which includes peer-to-peer and conferencing, specify the appropriate value for the Load Level.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="85bbf-146">Werte für die lastebene für alle Felder (außer Standort Informationsdienste) sind <STRONG>deaktiviert</STRONG>, <STRONG>niedrig</STRONG>, <STRONG>Mittel</STRONG>, <STRONG>hoch</STRONG>und <STRONG>Benutzerdefiniert</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="85bbf-146">Load level values for all fields (except Location Information Services) are <STRONG>Disabled</STRONG>, <STRONG>Low</STRONG>, <STRONG>Medium</STRONG>, <STRONG>High</STRONG>, and <STRONG>Custom</STRONG>.</span></span> <span data-ttu-id="85bbf-147">Wenn niedrig, Mittel, hoch oder Benutzerdefiniert ausgewählt ist, werden Konfigurationen für jede Modalität und jeden Client generiert.</span><span class="sxs-lookup"><span data-stu-id="85bbf-147">When Low, Medium, High, or Custom is selected, configurations will be generated for each modality and client.</span></span> <span data-ttu-id="85bbf-148">High bewirkt, dass die maximale unterstützte Last für den Server generiert wird, das Medium entspricht 60% der Last, und Low entspricht 30% der Last.</span><span class="sxs-lookup"><span data-stu-id="85bbf-148">High will result in the maximum supported load to be generated for the server, Medium corresponds to 60 percent of the load, and Low corresponds to 30 percent of the load.</span></span>

    
    </div>

2.  <span data-ttu-id="85bbf-149">Geben Sie in **Audiokonferenzen**, bei denen es sich nur um Audiokonferenzen handelt, den entsprechenden Wert für die Auslastungsstufe an.</span><span class="sxs-lookup"><span data-stu-id="85bbf-149">In **Audio Conferencing**, which is audio conferencing only, specify the appropriate value for Load Level.</span></span> <span data-ttu-id="85bbf-150">Peer-zu-Peer-Anrufe werden weiter unten in diesem Thema im Abschnitt VoIP-Szenarien behandelt.</span><span class="sxs-lookup"><span data-stu-id="85bbf-150">Peer-to-peer calls are covered in the Voice Scenarios section later in this topic.</span></span> <span data-ttu-id="85bbf-151">Um MultiView zu aktivieren, öffnen Sie die Registerkarte **erweitert** für diese Modalität.</span><span class="sxs-lookup"><span data-stu-id="85bbf-151">To enable MultiView, open the **Advanced** tab for that modality.</span></span>

3.  <span data-ttu-id="85bbf-152">Geben Sie in **Anwendungsfreigabe**den entsprechenden Wert für die Auslastungsstufe an.</span><span class="sxs-lookup"><span data-stu-id="85bbf-152">In **Application Sharing**, specify the appropriate value for Load Level.</span></span>

4.  <span data-ttu-id="85bbf-153">Geben Sie in **Datenzusammenarbeit**, einschließlich Datenkonferenzen, den entsprechenden Wert für die Auslastungsstufe an.</span><span class="sxs-lookup"><span data-stu-id="85bbf-153">In **Data Collaboration**, which includes data conferencing, specify the appropriate value for Load Level.</span></span>

5.  <span data-ttu-id="85bbf-154">Geben Sie in **Verteilerlistenerweiterung**den entsprechenden Wert für die Auslastungsstufe an.</span><span class="sxs-lookup"><span data-stu-id="85bbf-154">In **Distribution List Expansion**, specify the appropriate value for Load Level.</span></span> <span data-ttu-id="85bbf-155">Sie müssen auch auf die Schaltfläche **erweitert** klicken und dann die Felder mit den gleichen Werten ausfüllen, die Sie auf der Registerkarte **Verteilerliste** des lync Server Benutzer Erstellungstools (UserProvisioningTool.exe) konfiguriert haben.</span><span class="sxs-lookup"><span data-stu-id="85bbf-155">You must also click the **Advanced** button, and then fill in the fields with the same values that you configured on the **Distribution List** tab of the Lync Server User Creation Tool (UserProvisioningTool.exe).</span></span> <span data-ttu-id="85bbf-156">Ausführliche Informationen zu diesen Feldern finden Sie unter [Create users and Contacts](create-users-and-contacts.md) .</span><span class="sxs-lookup"><span data-stu-id="85bbf-156">For details about these fields, see [Create Users and Contacts](create-users-and-contacts.md)</span></span>

6.  <span data-ttu-id="85bbf-157">Geben Sie in der **Adressbuch-Webabfrage**, bei der es sich um den Adressbuch Suchdienst (nicht den Adressbuchdatei Download) handelt, den entsprechenden Wert für die Auslastungsstufe an.</span><span class="sxs-lookup"><span data-stu-id="85bbf-157">In **Address Book Web Query**, which is the address book lookup service (not the address book file download), specify the appropriate value for Load Level.</span></span> <span data-ttu-id="85bbf-158">Klicken Sie zum Aktivieren der Adressbuch Downloads auf die entsprechende Schaltfläche **erweitert** , und legen Sie **EnableABSDownload** auf true fest.</span><span class="sxs-lookup"><span data-stu-id="85bbf-158">To enable address book downloads, click the corresponding **Advanced** button, and then set **EnableABSDownload** to true.</span></span>

7.  <span data-ttu-id="85bbf-159">Geben Sie im **Reaktionsgruppendienst**den entsprechenden Wert für die Auslastungsstufe an.</span><span class="sxs-lookup"><span data-stu-id="85bbf-159">In **Response Group Service**, specify the appropriate value for Load Level.</span></span> <span data-ttu-id="85bbf-160">Sie müssen auch auf die entsprechende Schaltfläche **erweitert** klicken und dann die URIs der Reaktionsgruppen angeben, die Sie bereits erstellt haben, wenn Sie Reaktionsgruppen-Dienst-Agents zur Verfügung stellen.</span><span class="sxs-lookup"><span data-stu-id="85bbf-160">You must also click the corresponding **Advanced** button, and then specify the URIs of the response groups you have already created when provisioning Response Group Service agents.</span></span> <span data-ttu-id="85bbf-161">Sie müssen mindestens eine Reaktionsgruppe angeben.</span><span class="sxs-lookup"><span data-stu-id="85bbf-161">You must specify at least one response group.</span></span> <span data-ttu-id="85bbf-162">Verwenden Sie Semikolons, um mehrere Reaktionsgruppen voneinander zu trennen.</span><span class="sxs-lookup"><span data-stu-id="85bbf-162">Use semicolons to separate multiple response groups.</span></span> <span data-ttu-id="85bbf-163">Aktualisieren Sie RGSUriSuffixStartIndex und RGSUriSuffixEndIndex auf die tatsächlichen Werte.</span><span class="sxs-lookup"><span data-stu-id="85bbf-163">Update RGSUriSuffixStartIndex and RGSUriSuffixEndIndex to the actual values.</span></span>

8.  <span data-ttu-id="85bbf-164">Wählen Sie unter **Standort Informationsdienste**den entsprechenden Wert für lastebene aus.</span><span class="sxs-lookup"><span data-stu-id="85bbf-164">In **Location Information Services**, select the appropriate value for Load Level.</span></span> <span data-ttu-id="85bbf-165">Die Auslastungsstufe für Standort Informationsdienste muss **aktiviert** oder **deaktiviert**werden.</span><span class="sxs-lookup"><span data-stu-id="85bbf-165">The load level for Location Information Services must be **Enabled** or **Disabled**.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="85bbf-166">In jedem der Szenarien befinden sich neben der Schaltfläche <STRONG>Erweiterte</STRONG> Schaltflächen und eine Reihe von Kontrollkästchen, die Variationen der Szenarien ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="85bbf-166">Each of the scenarios has an <STRONG>Advanced</STRONG> button located next to it, and a set of check boxes that enable variations of the scenarios.</span></span> <span data-ttu-id="85bbf-167"><STRONG>Ad-hoc</STRONG> bedeutet, dass die Simulation von Konferenzen generiert wird, die die ganze Stunde hindurch erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="85bbf-167"><STRONG>Ad-hoc</STRONG> means to generate simulation of conferences that will be created throughout the hour.</span></span> <span data-ttu-id="85bbf-168"><STRONG>Large conf</STRONG> bedeutet, dass großes Konferenz Szenario simuliert wird.</span><span class="sxs-lookup"><span data-stu-id="85bbf-168"><STRONG>Large Conf</STRONG> means that Large Conference Scenario will be simulated.</span></span> <span data-ttu-id="85bbf-169"><STRONG>Externe</STRONG> Mittel, um auch externe Benutzer zu simulieren.</span><span class="sxs-lookup"><span data-stu-id="85bbf-169"><STRONG>External</STRONG> means to also simulate external users.</span></span><BR><span data-ttu-id="85bbf-170">Diese Schaltflächen und Kontrollkästchen ermöglichen den Zugriff auf die spezifischen Werte für jedes Szenario, das das Verhalten des lync Server 2013 Stress-und Leistungstools (LyncPerfTool) ändert und die Anpassung ermöglichen kann.</span><span class="sxs-lookup"><span data-stu-id="85bbf-170">These buttons and check boxes allow access to values specific to each scenario that will change the behavior of the Lync Server 2013 Stress and Performance Tool (LyncPerfTool) and make customization possible.</span></span> <span data-ttu-id="85bbf-171">Wenn der Wert der Auslastungsstufe <STRONG>Custom</STRONG>ist, wird für jedes Szenario auf der Registerkarte <STRONG>Allgemeine Szenarien</STRONG> (mit Ausnahme von Standort Informationsdiensten) die Konversations Rate mithilfe des entsprechenden Felds im Dialogfeld <STRONG>erweitert</STRONG> berechnet.</span><span class="sxs-lookup"><span data-stu-id="85bbf-171">For each scenario on the <STRONG>General Scenarios</STRONG> tab (except for Location Information Services), if the value of Load Level is <STRONG>Custom</STRONG>, then the conversation rate will be calculated using the corresponding field in the <STRONG>Advanced</STRONG> dialog box.</span></span> <span data-ttu-id="85bbf-172">Der Feldname unterscheidet sich je nach Szenario, aber die Feld Beschreibung gibt an, "Hinweis: Diese Nummer wird nur verwendet, wenn Benutzerdefiniert aus dem Dropdownmenü ausgewählt wird."</span><span class="sxs-lookup"><span data-stu-id="85bbf-172">The field name differs, depending on the scenario, but the field description will state, "NOTE: This number will only be used if Custom is selected from the drop-down menu."</span></span> <span data-ttu-id="85bbf-173">Im allgemeinen ändern die Werte <STRONG>hoch</STRONG>, <STRONG>Mittel</STRONG>und <STRONG>niedrig</STRONG> die Gesprächs Raten pro Modalität entsprechend dem Benutzermodell, das eine Balance aller Szenarien darstellt.</span><span class="sxs-lookup"><span data-stu-id="85bbf-173">In general, the values <STRONG>High</STRONG>, <STRONG>Medium</STRONG>, and <STRONG>Low</STRONG> will alter the conversation rates per modality in line with the User Model that is a balance of all the scenarios.</span></span> <span data-ttu-id="85bbf-174">Wenn aufgrund eines Unterschieds in der erwarteten Nutzung die Auslastungsstufe pro Modalität geändert werden muss, wird die Verwendung einer <STRONG>benutzerdefinierten</STRONG> Unterhaltungs Rate empfohlen.</span><span class="sxs-lookup"><span data-stu-id="85bbf-174">If there is a need to change the load level per modality due to a difference in expected usage, we recommend using a <STRONG>Custom</STRONG> conversation rate.</span></span><BR>



</div>

</div>

<div>

## <a name="voice-scenarios"></a><span data-ttu-id="85bbf-175">VoIP-Szenarien</span><span class="sxs-lookup"><span data-stu-id="85bbf-175">Voice Scenarios</span></span>

<span data-ttu-id="85bbf-176">In der folgenden Abbildung ist die Registerkarte **VoIP-Szenarien** des lync Server 2013 Tools zur Lasten Konfiguration dargestellt.</span><span class="sxs-lookup"><span data-stu-id="85bbf-176">The **Voice Scenarios** tab of the Lync Server 2013 Load Configuration Tool is shown in the following figure.</span></span>

<span data-ttu-id="85bbf-177">Verwenden Sie die Registerkarte **VoIP-Szenarien** , um alle VoIP-bezogenen Szenarien zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="85bbf-177">Use the **Voice Scenarios** tab to configure all of the voice-related scenarios.</span></span>

<span data-ttu-id="85bbf-178">![Registerkarte VoIP-Szenarien.](images/JJ945594.28edf664-da59-40b0-9a0e-196f01e9ca86(OCS.15).jpg "Registerkarte VoIP-Szenarien.")</span><span class="sxs-lookup"><span data-stu-id="85bbf-178">![Voice Scenarios tab.](images/JJ945594.28edf664-da59-40b0-9a0e-196f01e9ca86(OCS.15).jpg "Voice Scenarios tab.")</span></span>

1.  <span data-ttu-id="85bbf-179">Klicken Sie in **VoIP**auf die Schaltfläche **erweitert** , und geben Sie dann Werte für die Felder **PhoneAreaCode** und **LocationProfile** (Wählplan) an.</span><span class="sxs-lookup"><span data-stu-id="85bbf-179">In **VoIP**, click the **Advanced** button, and then provide values for the **PhoneAreaCode** and **LocationProfile** (dial plan) fields.</span></span> <span data-ttu-id="85bbf-180">Sie müssen auch einen Wert für die **Auslastungsstufe**angeben.</span><span class="sxs-lookup"><span data-stu-id="85bbf-180">You must also specify a value for **Load Level**.</span></span> <span data-ttu-id="85bbf-181">Wenn die Auslastungsstufe für **VoIP** und **UC/PSTN-Gateway** aktiviert ist, wird immer ein öffentliches Telefonnetz (PSTN) zu Unified Communications (UC)-Konfigurationsdatei generiert, das externe Anrufe simuliert wird.</span><span class="sxs-lookup"><span data-stu-id="85bbf-181">If Load Level for **VoIP** and **UC/PSTN Gateway** is Enabled, then a public switched telephone network (PSTN) to unified communications (UC) configuration file will always be generated that will simulate external calls.</span></span>

2.  <span data-ttu-id="85bbf-182">Geben Sie in **UC/PSTN-Gateway**einen Wert für die Auslastungsstufe an.</span><span class="sxs-lookup"><span data-stu-id="85bbf-182">In **UC/PSTN Gateway**, specify a value for Load Level.</span></span> <span data-ttu-id="85bbf-183">Wenn Sie eine andere lastebene als **deaktiviert**auswählen, müssen Sie einen Wert für die **PSTN-Vorwahl** angeben, indem Sie unter Vermittlungsserver und PSTN auf die Schaltfläche **Hinzufügen** klicken.</span><span class="sxs-lookup"><span data-stu-id="85bbf-183">If you select a load level other than **Disabled**, you must supply a value for **PSTN Area Code** by clicking the **Add** button under Mediation Server and PSTN.</span></span> <span data-ttu-id="85bbf-184">Stellen Sie sicher, dass für diese Ortskennzahl eine Route konfiguriert ist.</span><span class="sxs-lookup"><span data-stu-id="85bbf-184">Verify that you have a route configured for that area code.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="85bbf-185">Sie können entweder die lync Server-Systemsteuerung oder die lync Server-Verwaltungsshell verwenden, um die Konfiguration der VoIP-Route zu überprüfen.</span><span class="sxs-lookup"><span data-stu-id="85bbf-185">You can use either the Lync Server Control Panel or the Lync Server Management Shell to verify voice route configuration.</span></span>

    
    </div>

3.  <span data-ttu-id="85bbf-186">Geben Sie in der **Konferenzzentrale**einen Wert für die Auslastungsstufe an.</span><span class="sxs-lookup"><span data-stu-id="85bbf-186">In **Conferencing Attendant**, specify a value for Load Level.</span></span> <span data-ttu-id="85bbf-187">Wenn Sie eine lastebene (nicht **deaktiviert**) auswählen, wird das Feld **Telefonnummer** aktiviert.</span><span class="sxs-lookup"><span data-stu-id="85bbf-187">Selecting a load level (other than **Disabled**) will enable the **Telephone Number** field.</span></span> <span data-ttu-id="85bbf-188">Geben Sie die Telefonnummer der automatischen Telefonzentrale ein, die Sie verwenden möchten.</span><span class="sxs-lookup"><span data-stu-id="85bbf-188">Enter the telephone number of the Auto Attendant that you want to use.</span></span> <span data-ttu-id="85bbf-189">Klicken Sie außerdem auf die Schaltfläche **erweitert** , und geben Sie einen Wert für das Feld **LocationProfile** ein.</span><span class="sxs-lookup"><span data-stu-id="85bbf-189">Also, click the **Advanced** button, and then specify a value for the **LocationProfile** field.</span></span>

4.  <span data-ttu-id="85bbf-190">Geben Sie im Bereich " **Parken von Anrufen**" den entsprechenden Wert für die **Auslastungsstufe**an.</span><span class="sxs-lookup"><span data-stu-id="85bbf-190">In **Call Park Service**, specify the appropriate value for **Load Level**.</span></span>

5.  <span data-ttu-id="85bbf-191">In **Vermittlungsserver und PSTN**müssen Sie für jede Vermittlungsserver, die Sie verwenden möchten, über einen separaten PSTN-Simulator verfügen.</span><span class="sxs-lookup"><span data-stu-id="85bbf-191">In **Mediation Server and PSTN**, for each Mediation Server that you want to use, you must have a separate PSTN simulator.</span></span> <span data-ttu-id="85bbf-192">Nachdem Sie festgestellt haben, welcher Client als Simulator verwendet werden soll, müssen Sie Ihre Vermittlungsserver so konfigurieren, dass Anrufe an diesen Computer auf dem von Ihnen konfigurierten PSTN-Simulator-Port weitergeleitet werden.</span><span class="sxs-lookup"><span data-stu-id="85bbf-192">After you have determined which client you are going to use as the simulator, you need to configure your Mediation Server to route calls to that computer on the PSTN Simulator port that you configured.</span></span> <span data-ttu-id="85bbf-193">Klicken Sie auf **Hinzufügen** , um den Wert für die Vermittlungsserver zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="85bbf-193">Click **Add** to configure the value for the Mediation Server.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="85bbf-194">In jedem der Szenarien befindet sich daneben eine Schaltfläche " <STRONG>erweitert</STRONG> ".</span><span class="sxs-lookup"><span data-stu-id="85bbf-194">Each of the scenarios has an <STRONG>Advanced</STRONG> button located next to it.</span></span> <span data-ttu-id="85bbf-195">Diese Schaltflächen ermöglichen den Zugriff auf spezifische Werte für jedes Szenario, das das Verhalten des lync Server 2013 Stress and Performance Tool (LyncPerfTool) ändert und die Anpassung aktiviert.</span><span class="sxs-lookup"><span data-stu-id="85bbf-195">These buttons allow access to values specific to each scenario that will change the behavior of the Lync Server 2013 Stress and Performance Tool (LyncPerfTool) and enable customization.</span></span> <span data-ttu-id="85bbf-196">Wenn der Wert der <STRONG>Auslastungsstufe</STRONG> <STRONG>Custom</STRONG>ist, wird für jedes Szenario auf der Registerkarte <STRONG>VoIP-Szenarien</STRONG> die Konversations Rate mithilfe des entsprechenden Felds im Dialogfeld <STRONG>erweitert</STRONG> berechnet.</span><span class="sxs-lookup"><span data-stu-id="85bbf-196">For each scenario on the <STRONG>Voice Scenarios</STRONG> tab, if the value of <STRONG>Load Level</STRONG> is <STRONG>Custom</STRONG>, then the conversation rate will be calculated by using the corresponding field in the <STRONG>Advanced</STRONG> dialog box.</span></span> <span data-ttu-id="85bbf-197">Der Feldname unterscheidet sich je nach Szenario, aber die Feld Beschreibung gibt an, "Hinweis: Diese Nummer wird nur verwendet, wenn Benutzerdefiniert aus dem Dropdownmenü ausgewählt wird."</span><span class="sxs-lookup"><span data-stu-id="85bbf-197">The field name differs, depending on the scenario, but the field description will state, "NOTE: This number will only be used if Custom is selected from the drop-down menu."</span></span>



</div>

</div>

<div>

## <a name="reach"></a><span data-ttu-id="85bbf-198">Erreichen</span><span class="sxs-lookup"><span data-stu-id="85bbf-198">Reach</span></span>

<span data-ttu-id="85bbf-199">REACH ist eine neue Erfahrung in lync Server 2013, die Konferenzszenarien über den Unified Communications Web API (UCWA) Server unterstützt, der auf dem Front-End Server installiert ist.</span><span class="sxs-lookup"><span data-stu-id="85bbf-199">Reach is a new experience in Lync Server 2013 that supports conferencing scenarios through the Unified Communications Web API (UCWA) server that is installed on the Front-End server.</span></span> <span data-ttu-id="85bbf-200">In der folgenden Abbildung ist die Registerkarte " **REACH** " des lync Server 2013 Tools zum Laden der Konfiguration dargestellt.</span><span class="sxs-lookup"><span data-stu-id="85bbf-200">The **Reach** tab of the Lync Server 2013 Load Configuration Tool is shown in the following figure.</span></span>

<span data-ttu-id="85bbf-201">Verwenden Sie die Registerkarte **REACH** , um alle REACH-bezogenen Szenarien zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="85bbf-201">Use the **Reach** tab to configure all the reach-related scenarios.</span></span>

<span data-ttu-id="85bbf-202">![Registerkarte "REACH".](images/JJ945594.65ccf6de-0e8d-47ba-93f3-9dcb39d3fd62(OCS.15).jpg "Registerkarte "REACH".")</span><span class="sxs-lookup"><span data-stu-id="85bbf-202">![Reach tab.](images/JJ945594.65ccf6de-0e8d-47ba-93f3-9dcb39d3fd62(OCS.15).jpg "Reach tab.")</span></span>

1.  <span data-ttu-id="85bbf-203">Klicken Sie auf die Schaltfläche **erweitert** neben **Allgemeine Einstellungen für REACH**.</span><span class="sxs-lookup"><span data-stu-id="85bbf-203">Click the **Advanced** button next to **General Reach Settings**.</span></span> <span data-ttu-id="85bbf-204">Legen Sie das Feld **UcwaTargetServerUrl** auf die Directorpool virtuelle IP (VIP) oder die Front-End-Pool VIP fest.</span><span class="sxs-lookup"><span data-stu-id="85bbf-204">Set the field **UcwaTargetServerUrl** to the Director pool virtual IP (VIP) or the Front End pool VIP.</span></span>

2.  <span data-ttu-id="85bbf-205">Wählen Sie unter **Anwendungsfreigabe**, **Datenzusammenarbeit**und **Sofortnachrichten**den entsprechenden Wert für die **Auslastungsstufe**aus.</span><span class="sxs-lookup"><span data-stu-id="85bbf-205">In **Application Sharing**, **Data Collaboration**, and **IM**, select the appropriate value for **Load Level**.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="85bbf-206">In jedem der Szenarien befindet sich daneben eine Schaltfläche " <STRONG>erweitert</STRONG> ".</span><span class="sxs-lookup"><span data-stu-id="85bbf-206">Each of the scenarios has an <STRONG>Advanced</STRONG> button located next to it.</span></span> <span data-ttu-id="85bbf-207">Diese Schaltflächen ermöglichen den Zugriff auf spezifische Werte für jedes Szenario, das das Verhalten des lync Server 2013 Stress and Performance Tool (LyncPerfTool) ändert und die Anpassung aktiviert.</span><span class="sxs-lookup"><span data-stu-id="85bbf-207">These buttons allow access to values specific to each scenario that will change the behavior of the Lync Server 2013 Stress and Performance Tool (LyncPerfTool) and enable customization.</span></span> <span data-ttu-id="85bbf-208">Wenn die <STRONG>Auslastungsstufe</STRONG> <STRONG>Custom</STRONG>ist, wird für jedes der REACH-Szenarien anstelle der Standardeinstellung der im Feld <STRONG>ConversationsPerHour</STRONG> angegebene Wert verwendet.</span><span class="sxs-lookup"><span data-stu-id="85bbf-208">For each of the Reach scenarios, if the <STRONG>Load Level</STRONG> is <STRONG>Custom</STRONG>, then the value specified in the <STRONG>ConversationsPerHour</STRONG> field is used instead of the default</span></span>



</div>

<span data-ttu-id="85bbf-209">Verwenden Sie die Registerkarte **Mobilität** , um alle mobilitätsbezogenen Szenarien zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="85bbf-209">Use the **Mobility** tab to configure all of the mobility-related scenarios.</span></span>

<span data-ttu-id="85bbf-210">![Registerkarte Mobilität.](images/JJ945594.4dd8f3e0-921c-48a5-8b23-2a0330d3c334(OCS.15).jpg "Registerkarte Mobilität.")</span><span class="sxs-lookup"><span data-stu-id="85bbf-210">![Mobility tab.](images/JJ945594.4dd8f3e0-921c-48a5-8b23-2a0330d3c334(OCS.15).jpg "Mobility tab.")</span></span>

1.  <span data-ttu-id="85bbf-211">Klicken Sie auf die Schaltfläche **erweitert** neben **Mobility (UCWA)**.</span><span class="sxs-lookup"><span data-stu-id="85bbf-211">Click the **Advanced** button next to **Mobility (UCWA)**.</span></span> <span data-ttu-id="85bbf-212">Legen Sie das Feld **UcwaTargetServerUrl** auf die Directorpool virtuelle IP (VIP) oder die Front-End-Pool VIP fest.</span><span class="sxs-lookup"><span data-stu-id="85bbf-212">Set the field **UcwaTargetServerUrl** to the Director pool virtual IP (VIP) or the Front End pool VIP.</span></span>

2.  <span data-ttu-id="85bbf-213">Wählen Sie in **Anwesenheits-und P2P \\ -Chat-Audio**den entsprechenden Wert für die **Auslastungsstufe** aus, um die Mobilitäts Szenario-Simulation zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="85bbf-213">In **Presence and P2P Instant Messaging\\Audio**, select the appropriate value for **Load Level** to enable Mobility Scenario simulation.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="85bbf-214">In jedem der Szenarien befindet sich daneben eine Schaltfläche " <STRONG>erweitert</STRONG> ".</span><span class="sxs-lookup"><span data-stu-id="85bbf-214">Each of the scenarios has an <STRONG>Advanced</STRONG> button located next to it.</span></span> <span data-ttu-id="85bbf-215">Diese Schaltflächen ermöglichen den Zugriff auf spezifische Werte für jedes Szenario, das das Verhalten des lync Server 2013 Stress and Performance Tool (LyncPerfTool) ändert und die Anpassung aktiviert.</span><span class="sxs-lookup"><span data-stu-id="85bbf-215">These buttons allow access to values specific to each scenario that will change the behavior of the Lync Server 2013 Stress and Performance Tool (LyncPerfTool) and enable customization.</span></span> <span data-ttu-id="85bbf-216">Wenn die <STRONG>Auslastungsstufe</STRONG> <STRONG>Custom</STRONG>ist, wird für jedes der REACH-Szenarien anstelle der Standardeinstellung der im Feld <STRONG>ConversationsPerHour</STRONG> angegebene Wert verwendet.</span><span class="sxs-lookup"><span data-stu-id="85bbf-216">For each of the Reach scenarios, if the <STRONG>Load Level</STRONG> is <STRONG>Custom</STRONG>, then the value specified in the <STRONG>ConversationsPerHour</STRONG> field is used instead of the default.</span></span>



</div>

</div>

<div>

## <a name="summary"></a><span data-ttu-id="85bbf-217">Zusammenfassung</span><span class="sxs-lookup"><span data-stu-id="85bbf-217">Summary</span></span>

<span data-ttu-id="85bbf-218">Die Registerkarte " **Zusammenfassung** " des lync Server 2013 Tools zum Laden der Konfiguration ist in der folgenden Abbildung dargestellt.</span><span class="sxs-lookup"><span data-stu-id="85bbf-218">The **Summary** tab of the Lync Server 2013 Load Configuration Tool is shown in the following figure.</span></span>

<span data-ttu-id="85bbf-219">![Registerkarte Zusammenfassung.](images/JJ945594.c675e869-8ded-4195-8c2a-68d844fc96ad(OCS.15).jpg "Registerkarte Zusammenfassung.")</span><span class="sxs-lookup"><span data-stu-id="85bbf-219">![Summary tab.](images/JJ945594.c675e869-8ded-4195-8c2a-68d844fc96ad(OCS.15).jpg "Summary tab.")</span></span>

<span data-ttu-id="85bbf-220">Auf der Registerkarte **Zusammenfassung** wird angegeben, welche Benutzer für welche Szenarien verwendet werden sollen.</span><span class="sxs-lookup"><span data-stu-id="85bbf-220">The **Summary** tab indicates which users to use for each of the scenarios.</span></span> <span data-ttu-id="85bbf-221">Benutzernummern Bereiche können manuell konfiguriert werden, indem das Kontrollkästchen Benutzer **definierte Benutzerbereichs Generierung aktivieren aktiviert** ist, und dann doppelklicken Sie auf das Szenario in der Tabelle mit dem **Benutzerbereich** , den Sie anpassen möchten.</span><span class="sxs-lookup"><span data-stu-id="85bbf-221">It is possible to manually configure user number ranges by selecting the **Enable Custom User Range Generation** check box, and then double-clicking the scenario in the table that has the **User Range** that you want to customize.</span></span> <span data-ttu-id="85bbf-222">Überprüfen Sie (RunClient.bat) beim Start eine Anmelde Verzögerung hinzufügen, um Verzögerungen in den generierten Batchdateien einzuschließen, die dem Anmelderate entsprechen.</span><span class="sxs-lookup"><span data-stu-id="85bbf-222">Check (RunClient.bat) Add sign-in delay when starting, in order to include delays in the generated batch files to correspond with the sign-in rate.</span></span> <span data-ttu-id="85bbf-223">Dies ist hilfreich, um eine Serverüberlastung zu verhindern, wenn eine große Anzahl von Benutzern signiert wird.</span><span class="sxs-lookup"><span data-stu-id="85bbf-223">This is useful to prevent server overload when signing in a large number of users.</span></span> <span data-ttu-id="85bbf-224">Klicken Sie auf **Dateien generieren**, und wählen Sie den Ordner aus, in dem die Konfiguration generiert werden soll.</span><span class="sxs-lookup"><span data-stu-id="85bbf-224">Click **Generate Files**, and select the folder where you want to generate the configuration.</span></span> <span data-ttu-id="85bbf-225">Ein Dialogfeld wie die folgende Abbildung wird angezeigt, wenn Ihre Dateien erfolgreich erstellt wurden.</span><span class="sxs-lookup"><span data-stu-id="85bbf-225">A dialog box similar to the following figure will appear when your files have been successfully created.</span></span>

<span data-ttu-id="85bbf-226">![Bestätigung, dass Dateien erstellt wurden.](images/JJ945594.00dc1e92-bfba-48e7-9568-b97ad864491e(OCS.15).jpg "Bestätigung, dass Dateien erstellt wurden.")</span><span class="sxs-lookup"><span data-stu-id="85bbf-226">![Acknowledgement that files have been created.](images/JJ945594.00dc1e92-bfba-48e7-9568-b97ad864491e(OCS.15).jpg "Acknowledgement that files have been created.")</span></span>

</div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="85bbf-227">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="85bbf-227">See Also</span></span>


[<span data-ttu-id="85bbf-228">Erstellen von Benutzern und Kontakten</span><span class="sxs-lookup"><span data-stu-id="85bbf-228">Create Users and Contacts</span></span>](create-users-and-contacts.md)  
</div>
</div>
<span></span>
</div>
</div>
</div>
