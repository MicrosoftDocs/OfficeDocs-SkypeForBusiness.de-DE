---
title: Erstellen von Benutzern und Kontakten
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Create Users and Contacts
ms:assetid: 04b24d07-2864-463d-b508-544c2674c4ab
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945587(v=OCS.15)
ms:contentKeyID: 51541412
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 660ac18e00ef25a3cda4dd37d6a7850fee2fa459
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42049147"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-users-and-contacts"></a><span data-ttu-id="08a04-102">Erstellen von Benutzern und Kontakten</span><span class="sxs-lookup"><span data-stu-id="08a04-102">Create Users and Contacts</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="08a04-103">_**Letztes Änderungsstand des Themas:** 2013-02-22_</span><span class="sxs-lookup"><span data-stu-id="08a04-103">_**Topic Last Modified:** 2013-02-22_</span></span>

<span data-ttu-id="08a04-104">Sie müssen das lync Server 2013-Benutzer Bereitstellungs Tool (UserProvisioningTool. exe) verwenden, um Benutzer und Kontakte in Vorbereitung auf Stress-und Leistungs Auslastungstests zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="08a04-104">You must use the Lync Server 2013 User Provisioning Tool (UserProvisioningTool.exe) to create users and contacts in preparation for stress and performance load testing.</span></span>

<span data-ttu-id="08a04-105">Im folgenden finden Sie eine Liste von Begriffen und Definitionen, die Sie beim Durchlesen dieses Themas hilfreich finden.</span><span class="sxs-lookup"><span data-stu-id="08a04-105">Here is a list of terms and definitions that you might find useful as you read through this topic.</span></span>

  - <span data-ttu-id="08a04-106">Organisationseinheit – die Active Directory-Domänendienste Organisationseinheit (Organizational Unit, OU).</span><span class="sxs-lookup"><span data-stu-id="08a04-106">Organizational Unit – The Active Directory Domain Services organizational unit (OU).</span></span>

  - <span data-ttu-id="08a04-107">Verbund/Cross-Pool – Benutzer, die für die Kommunikation mit Benutzern von anderen Chat Diensten (Instant Messaging) wie MSN-Netzwerk mit Internet Diensten, AOL® und Yahoo\!-® aktiviert werden.</span><span class="sxs-lookup"><span data-stu-id="08a04-107">Federated / Cross Pool – Users who will be enabled to communicate with users from other Instant Messaging (IM) services, such as MSN network of Internet services, AOL®, and Yahoo\!®.</span></span>

  - <span data-ttu-id="08a04-108">Verteilerlisten – die Objekte in Active Directory-Domänendienste, die eine Liste der Active Directory-Domänendienste-Benutzer enthalten, die zum Starten der Kommunikation mit Personengruppen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="08a04-108">Distribution Lists – The objects in Active Directory Domain Services that contain a list of Active Directory Domain Services users, used for launching communications with groups of people.</span></span>

  - <span data-ttu-id="08a04-109">Location Info Service – der lync Server 2013 Dienst, der bei Aktivierung und Konfiguration pro Telefon den Abruf des physischen Speicherorts für erweiterte 9-1-1-Dienste (E9-1-1) ermöglicht.</span><span class="sxs-lookup"><span data-stu-id="08a04-109">Location Info Service – The Lync Server 2013 service that, when enabled and configured per phone, enables retrieval of physical location for Enhanced 9-1-1 (E9-1-1) services.</span></span>

  - <span data-ttu-id="08a04-110">US-Telefonnummern – die Telefonnummern, die Benutzern zugewiesen sind, zusätzlich zu dem SIP-URI, der zum Weiterleiten von eingehenden und ausgehenden Anrufen und Reverse Number Lookup (können) verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="08a04-110">U.S. Phone Numbers – The phone numbers that are assigned to users, in addition to the SIP URI that is used for routing inbound and outbound calls and reverse number lookup (RNL).</span></span>

<div>

## <a name="create-users-and-contacts-by-using-userprovisioningtoolexe"></a><span data-ttu-id="08a04-111">Erstellen von Benutzern und Kontakten mithilfe von UserProvisioningTool. exe</span><span class="sxs-lookup"><span data-stu-id="08a04-111">Create Users and Contacts by Using UserProvisioningTool.exe</span></span>

<span data-ttu-id="08a04-112">Zum Erstellen von Benutzern und Kontakten für die Auslastungssimulation müssen Sie das lync Server Benutzer prodienste-Tool verwenden.</span><span class="sxs-lookup"><span data-stu-id="08a04-112">You must use the Lync Server User Provisioning Tool to create users and contacts for load simulation.</span></span> <span data-ttu-id="08a04-113">Das lync Server-Benutzer Prothesen-Tool wird mit dem lync Server Stress and Performance Tool Package installiert.</span><span class="sxs-lookup"><span data-stu-id="08a04-113">The Lync Server User Provisioning Tool is installed with the Lync Server Stress and Performance Tool package.</span></span> <span data-ttu-id="08a04-114">Stellen Sie sicher, dass das Paketinstallationsprogramm (CapacityPlanningTool. msi) auf dem Front-End-Server oder dem Standard Edition-Server ausgeführt wurde.</span><span class="sxs-lookup"><span data-stu-id="08a04-114">Be sure that the package installer (CapacityPlanningTool.msi) has been run on the Front End Server or the Standard Edition server.</span></span> <span data-ttu-id="08a04-115">Starten Sie das lync Server Benutzer bereitstellen-Tool, indem Sie die Datei UserProvisioningTool. exe (befindet sich unter%\\InstalledDirectory% LyncStressAndPerfTool LyncStress) auf der Front-End-Server oder auf der Standard Edition-Server.</span><span class="sxs-lookup"><span data-stu-id="08a04-115">Start the Lync Server User Provisioning Tool by running the file UserProvisioningTool.exe (located at %InstalledDirectory%LyncStressAndPerfTool\\LyncStress) on the Front End Server or on the Standard Edition server.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="08a04-116">Sie müssen als Mitglied der Sicherheitsgruppe "Domänen-Admins" angemeldet sein, um UserProvisioningTool. exe ausführen zu können.</span><span class="sxs-lookup"><span data-stu-id="08a04-116">You must be logged on as a member of the Domain Admins security group in order to run UserProvisioningTool.exe.</span></span> <span data-ttu-id="08a04-117">Sie müssen in diesem Kontext ausgeführt werden, da UserProvisioningTool. exe neue Active Directory-Domänendienste Benutzer erstellt und konfiguriert.</span><span class="sxs-lookup"><span data-stu-id="08a04-117">It is necessary to run from this context because UserProvisioningTool.exe will be creating and configuring new Active Directory Domain Services users.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="08a04-118">Wenn Sie eine große Anzahl von Benutzern (10.000 oder mehr) erstellen, führen Sie UserProvisioningTool. exe auf einem High-End-Computer aus.</span><span class="sxs-lookup"><span data-stu-id="08a04-118">When you create a significant number of users (10,000 or more), run UserProvisioningTool.exe from a high-end computer.</span></span> <span data-ttu-id="08a04-119">Beachten Sie, dass der Domänencontroller auch bei der Erstellung der Benutzer eine hohe Auslastung erfahren wird.</span><span class="sxs-lookup"><span data-stu-id="08a04-119">Note that the domain controller will also experience high load while the users are being created.</span></span>



</div>

<span data-ttu-id="08a04-120">Wenn das lync Server Benutzer ProTools geöffnet wird, klicken Sie auf **Konfiguration** und dann auf Konfiguration **Laden**.</span><span class="sxs-lookup"><span data-stu-id="08a04-120">When the Lync Server User Provisioning Tool opens, click **Configuration** and select **Load Configuration**.</span></span> <span data-ttu-id="08a04-121">Laden Sie die Standarddatei, die im Paket enthalten ist, SampleData. XML, um mit der Konfiguration von Benutzern und Kontakten zu beginnen.</span><span class="sxs-lookup"><span data-stu-id="08a04-121">To begin configuring users and contacts, load the default file that is included in the package, SampleData.xml.</span></span> <span data-ttu-id="08a04-122">Dadurch werden die Felder mit Beispieldaten vorab gefüllt, die Sie für Ihr System überarbeiten müssen.</span><span class="sxs-lookup"><span data-stu-id="08a04-122">This will prepopulate the fields with example data that you'll need to revise for your system.</span></span> <span data-ttu-id="08a04-123">Wenn Sie über eine vorkonfigurierte XML-Datei verfügen, die bereits angepasste Einstellungen enthält, laden Sie diese Datei stattdessen.</span><span class="sxs-lookup"><span data-stu-id="08a04-123">If you have a preconfigured XML file that already contains customized settings, load that file instead.</span></span> <span data-ttu-id="08a04-124">Füllen Sie die Felder im lync Server Benutzer protoolieren aus, wie in den folgenden Abschnitten beschrieben.</span><span class="sxs-lookup"><span data-stu-id="08a04-124">Fill in the fields in the Lync Server User Provisioning Tool, as described in the following sections.</span></span>

<span data-ttu-id="08a04-125">![Registerkarte "Benutzererstellung".](images/JJ945587.80d3c17b-7482-4818-8381-1eff8717d2fe(OCS.15).jpg "Registerkarte "Benutzererstellung".")</span><span class="sxs-lookup"><span data-stu-id="08a04-125">![User Creation tab.](images/JJ945587.80d3c17b-7482-4818-8381-1eff8717d2fe(OCS.15).jpg "User Creation tab.")</span></span>

<span data-ttu-id="08a04-126">Führen Sie die folgenden Schritte aus, um Serveroptionen zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="08a04-126">To configure server options, follow these steps.</span></span>

1.  <span data-ttu-id="08a04-127">Geben Sie im **Front-End-Pool-FQDN**den vollqualifizierten Domänennamen (Fully Qualified Domain Name, FQDN) des Standard Edition-Server oder Front-End-Pool, in dem die Benutzer gehostet werden sollen.</span><span class="sxs-lookup"><span data-stu-id="08a04-127">In **Front End Pool FQDN**, type the fully qualified domain name (FQDN) of the Standard Edition server or Front End pool where you want to host the users.</span></span>

2.  <span data-ttu-id="08a04-128">Geben Sie unter **Benutzer Name Präfix**ein Präfix ein, das Sie zum Erstellen von Benutzernamen zu Testzwecken verwenden möchten.</span><span class="sxs-lookup"><span data-stu-id="08a04-128">In **User Name Prefix**, type a prefix that you want to use to build user names for testing purposes.</span></span>

3.  <span data-ttu-id="08a04-129">Geben Sie unter **Kennwort**ein Kennwort an, das auf alle Testbenutzerkonten angewendet wird.</span><span class="sxs-lookup"><span data-stu-id="08a04-129">In **Password**, specify a password that will be applied for all of the test user accounts.</span></span>

4.  <span data-ttu-id="08a04-130">Geben Sie in **SIP-Domäne**den Domänennamen ein, der für SIP-URIs der Testbenutzer (Uniform Resource Identifiers) verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="08a04-130">In **SIP Domain**, type the domain name to be used for test users’ SIP URIs (Uniform Resource Identifiers).</span></span>

5.  <span data-ttu-id="08a04-131">Geben Sie in **Kontodomäne**den Domänennamen Ihrer aktuellen Active Directory-Domänendienste Domäne ein, unter der Sie die Testbenutzer erstellen möchten.</span><span class="sxs-lookup"><span data-stu-id="08a04-131">In **Account Domain**, type the domain name of your current Active Directory Domain Services domain, under which you want to create the test users.</span></span>

6.  <span data-ttu-id="08a04-132">Geben Sie in **Organisationseinheit**den Namen der Active Directory-Domänendienste ou ein, in der Sie die Benutzerobjekte erstellen möchten.</span><span class="sxs-lookup"><span data-stu-id="08a04-132">In **Organizational Unit**, type the name of the Active Directory Domain Services OU where you want to create the User objects.</span></span> <span data-ttu-id="08a04-133">Wenn die Organisationseinheit nicht vorhanden ist, wird Sie erstellt.</span><span class="sxs-lookup"><span data-stu-id="08a04-133">If the OU does not exist, it will be created.</span></span>

7.  <span data-ttu-id="08a04-134">Geben Sie unter **Telefonvorwahl**den dreistelligen Vorwahlcode ein, der für Testbenutzerkonten verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="08a04-134">In **Phone Area Code**, type the three-digit area code that will be used for test user accounts.</span></span> <span data-ttu-id="08a04-135">Stellen Sie sicher, dass die Telefonvorwahl nicht mit den Gebietscodes anderer Benutzer in Active Directory-Domänendienste in Konflikt steht.</span><span class="sxs-lookup"><span data-stu-id="08a04-135">Be sure that phone area code does not conflict with any other users’ area codes in Active Directory Domain Services.</span></span>

8.  <span data-ttu-id="08a04-136">Aktivieren Sie das Kontrollkästchen **sprachaktiviert** , wenn Sie die Testbenutzer für Enterprise-VoIP aktivieren möchten.</span><span class="sxs-lookup"><span data-stu-id="08a04-136">Select the **Voice Enabled** check box if you want to enable the test users for Enterprise Voice.</span></span>

9.  <span data-ttu-id="08a04-137">Geben Sie unter **Anzahl der Benutzer**die Gesamtzahl der Testbenutzer an, die Sie erstellen möchten.</span><span class="sxs-lookup"><span data-stu-id="08a04-137">In **Number of Users**, specify the total number of test users that you want to create.</span></span>

10. <span data-ttu-id="08a04-138">Geben Sie unter **Start Index**die Startnummer an, die als Suffix für das Benutzernamenpräfix verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="08a04-138">In **Start Index**, specify the starting number that will be used as suffix to the user name prefix.</span></span>

<div>

## <a name="create-users-button"></a><span data-ttu-id="08a04-139">Schaltfläche "Benutzer erstellen"</span><span class="sxs-lookup"><span data-stu-id="08a04-139">Create Users Button</span></span>

<span data-ttu-id="08a04-140">Wenn Sie auf die Schaltfläche Benutzer erstellen klicken, werden alle Eingabeparameter überprüft.</span><span class="sxs-lookup"><span data-stu-id="08a04-140">When you click on the Create Users button, it will validate all the input parameters.</span></span>

  - <span data-ttu-id="08a04-141">Wenn Validierungsfehler vorliegen, werden Sie aufgefordert, diese Eingabewerte zu korrigieren.</span><span class="sxs-lookup"><span data-stu-id="08a04-141">If there are any validation errors, it will prompt you to correct those input values.</span></span>

  - <span data-ttu-id="08a04-142">Wenn alle Eingabewerte korrekt sind, wird mit dem Erstellen von Benutzern in Active Directory-Domänendienste begonnen.</span><span class="sxs-lookup"><span data-stu-id="08a04-142">If all the input values are correct, it will start creating users in Active Directory Domain Services.</span></span> <span data-ttu-id="08a04-143">Unten in diesem Formular wird eine Statusleiste angezeigt.</span><span class="sxs-lookup"><span data-stu-id="08a04-143">A progress bar will appear at the bottom of this form.</span></span> <span data-ttu-id="08a04-144">Es wird empfohlen, die Anwendung nicht zu schließen, während die Statusanzeige aktiv ist.</span><span class="sxs-lookup"><span data-stu-id="08a04-144">We recommend that you do not close the application while the progress bar is active.</span></span>

<span data-ttu-id="08a04-145">Die Erstellung des Benutzers ist ein langsamer Prozess.</span><span class="sxs-lookup"><span data-stu-id="08a04-145">User Creation is a slow process.</span></span> <span data-ttu-id="08a04-146">Es kann mehrere Minuten dauern.</span><span class="sxs-lookup"><span data-stu-id="08a04-146">It can take several minutes.</span></span> <span data-ttu-id="08a04-147">Wenn die Anzahl der Benutzer sehr groß ist, kann der Vorgang sogar einige Stunden dauern.</span><span class="sxs-lookup"><span data-stu-id="08a04-147">If the number of users is very large, the process could even take a few hours.</span></span> <span data-ttu-id="08a04-148">Wenn die Benutzer bereits vorhanden sind, werden Sie mit allen Änderungen aktualisiert.</span><span class="sxs-lookup"><span data-stu-id="08a04-148">If the users already exist, they are updated with any changes.</span></span> <span data-ttu-id="08a04-149">Sie können überprüfen, ob die Benutzer erstellt wurden, indem Sie sich als einer der Benutzer im Bereich anmelden.</span><span class="sxs-lookup"><span data-stu-id="08a04-149">You can validate that the users were created by logging on as one of the users in the range.</span></span> <span data-ttu-id="08a04-150">Verwenden Sie das Benutzerpräfix, die Benutzernummer und @sipDomain als Benutzername (beispielsweise LyncUser10@contoso.net) zusammen mit dem angegebenen Kennwort.</span><span class="sxs-lookup"><span data-stu-id="08a04-150">Use the user prefix, user number, and @sipDomain as the user name (for example, LyncUser10@contoso.net), along with the specified password.</span></span>

</div>

<div>

## <a name="delete-users-button"></a><span data-ttu-id="08a04-151">Schaltfläche "Benutzer löschen"</span><span class="sxs-lookup"><span data-stu-id="08a04-151">Delete Users Button</span></span>

<span data-ttu-id="08a04-152">Wenn Sie auf die Schaltfläche Benutzer löschen klicken, werden alle Eingabeparameter überprüft.</span><span class="sxs-lookup"><span data-stu-id="08a04-152">When you click on Delete Users button, it will validate all the input parameters.</span></span>

  - <span data-ttu-id="08a04-153">Wenn Validierungsfehler vorliegen, werden Sie aufgefordert, diese Eingabewerte zu korrigieren.</span><span class="sxs-lookup"><span data-stu-id="08a04-153">If there are any validation errors, it will prompt you to correct those input values.</span></span>

  - <span data-ttu-id="08a04-154">Wenn alle Eingabewerte korrekt sind, wird das Deaktivieren und Löschen von Benutzern in Active Directory-Domänendienste gestartet.</span><span class="sxs-lookup"><span data-stu-id="08a04-154">If all the input values are correct, it will start disabling and deleting users in Active Directory Domain Services.</span></span> <span data-ttu-id="08a04-155">Unten in diesem Formular wird eine Statusleiste angezeigt.</span><span class="sxs-lookup"><span data-stu-id="08a04-155">A progress bar will appear at the bottom of this form.</span></span> <span data-ttu-id="08a04-156">Es wird empfohlen, die Anwendung nicht zu schließen, während die Statusanzeige aktiv ist.</span><span class="sxs-lookup"><span data-stu-id="08a04-156">We recommend that you do not close the application while the progress bar is active.</span></span>

<div>


> [!NOTE]  
> <OL>
> <LI>
> <P><span data-ttu-id="08a04-157">Nur US-formatierte Telefonnummern werden unterstützt.</span><span class="sxs-lookup"><span data-stu-id="08a04-157">Only U.S.-formatted phone numbers are supported.</span></span> <span data-ttu-id="08a04-158">Telefonnummern werden immer Benutzern zugewiesen, und alle von UserProvisioningTool. exe erstellten Benutzer sind für Enterprise-VoIP aktiviert.</span><span class="sxs-lookup"><span data-stu-id="08a04-158">Phone numbers are always assigned to users, and all users created by UserProvisioningTool.exe are enabled for Enterprise Voice.</span></span> <span data-ttu-id="08a04-159">Alle Szenarien, die die Telefonnummer wie automatische Telefonzentrale für Konferenzen oder UC-PSTN-Anrufe verwenden, verwenden diese Telefonnummer, um Anrufe ordnungsgemäß weiterzuleiten.</span><span class="sxs-lookup"><span data-stu-id="08a04-159">Any scenarios that use the phone number, such as Conferencing Auto Attendant or UC-PSTN calls, use this phone number to properly route calls.</span></span> <span data-ttu-id="08a04-160">Aus diesem Grund muss jeder Benutzer eine eindeutige Telefonnummer haben.</span><span class="sxs-lookup"><span data-stu-id="08a04-160">For this reason, every user must have a unique phone number.</span></span> <span data-ttu-id="08a04-161">Wenn Sie Benutzer zweimal erstellen müssen, tritt beim Ausführen des Befehls ein Fehler auf, es sei denn, Sie verwenden eine andere Vorwahl oder wenn die vorherigen Benutzer mithilfe des Cmdlets <STRONG>Disable-CsUser</STRONG> deaktiviert wurden.</span><span class="sxs-lookup"><span data-stu-id="08a04-161">If you have to create users twice, the command will fail unless you use a different area code, or if the previous users have been disabled by using the <STRONG>Disable-CsUser</STRONG> cmdlet.</span></span></P>
> <LI>
> <P><span data-ttu-id="08a04-162">Bevor Sie Kontakte erstellen, müssen Sie zuerst die Benutzerreplikation ausführen, die auf der Registerkarte Benutzer ausgeführt wird. Wenn Sie Ihre Benutzer soeben erstellt haben, müssen Sie warten, bis lync Server Replikation abgeschlossen ist und die Benutzerkonten in der Datenbank auffüllen.</span><span class="sxs-lookup"><span data-stu-id="08a04-162">Before you create contacts, you must first complete user replication, performed from the Users tab. If you have just created your users, you must wait until Lync Server replication completes and populates the user accounts in the database.</span></span> <span data-ttu-id="08a04-163">Wenn die Replikation der Benutzer noch nicht abgeschlossen ist, wird ein Fehler angezeigt.</span><span class="sxs-lookup"><span data-stu-id="08a04-163">If the users have not finished replicating, you will see an error.</span></span> <span data-ttu-id="08a04-164">Sie wissen, wann Benutzer die Replikation abgeschlossen haben, wenn lync Server 2013 Front-End-Dienst gestartet wurde, oder indem Sie das Cmdlet <STRONG>Get-CsUser</STRONG> für den letzten Benutzer erfolgreich ausführen.</span><span class="sxs-lookup"><span data-stu-id="08a04-164">You will know when users have finished replicating if Lync Server 2013 Front End service has started, or by successfully running the <STRONG>Get-CsUser</STRONG> cmdlet on the last user.</span></span></P></LI></OL>



</div>

</div>

</div>

<div>

## <a name="contacts-creation-tab"></a><span data-ttu-id="08a04-165">Registerkarte "Kontakte erstellen"</span><span class="sxs-lookup"><span data-stu-id="08a04-165">Contacts Creation Tab</span></span>

<span data-ttu-id="08a04-166">Auf der Registerkarte Kontakte Erstellung können Sie Details für die Kontakte von Benutzern angeben.</span><span class="sxs-lookup"><span data-stu-id="08a04-166">The Contacts Creation tab enables you to specify details for users’ contacts.</span></span>

<span data-ttu-id="08a04-167">![Registerkarte Kontakte erstellen.](images/JJ945587.7508726e-83e6-4878-8edd-114543d9af24(OCS.15).jpg "Registerkarte Kontakte erstellen.")</span><span class="sxs-lookup"><span data-stu-id="08a04-167">![Contacts Creation tab.](images/JJ945587.7508726e-83e6-4878-8edd-114543d9af24(OCS.15).jpg "Contacts Creation tab.")</span></span>

<span data-ttu-id="08a04-168">Führen Sie die folgenden Schritte aus, um die Kontakte der Benutzer zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="08a04-168">To configure users’ contacts, follow these steps.</span></span>

1.  <span data-ttu-id="08a04-169">Geben Sie in durchschnittliche Kontakte pro Benutzer die durchschnittliche Anzahl von Kontakten an, die in Kontaktlisten für jeden Benutzer aufgefüllt werden sollen.</span><span class="sxs-lookup"><span data-stu-id="08a04-169">In Average Contacts per User, specify the average number of contacts to populate in contact lists for each of the users.</span></span>

2.  <span data-ttu-id="08a04-170">Aktivieren Sie das Kontrollkästchen fixiert, wenn Sie für jeden Benutzer eine gleiche Anzahl von Kontakten erstellen möchten.</span><span class="sxs-lookup"><span data-stu-id="08a04-170">Select the Fixed check box if you want to create an equal number of contacts for every user.</span></span> <span data-ttu-id="08a04-171">Wenn Sie die Anzahl der für Benutzer erstellten Kontakte variieren möchten, deaktivieren Sie das Kontrollkästchen.</span><span class="sxs-lookup"><span data-stu-id="08a04-171">If you want to vary the number of contacts created for users, clear the check box.</span></span>

3.  <span data-ttu-id="08a04-172">Geben Sie in durchschnittliche Kontaktgruppen pro Benutzer die Anzahl der Kontaktgruppen pro Benutzer an.</span><span class="sxs-lookup"><span data-stu-id="08a04-172">In Average Contact Groups per User, specify the number of contact groups per user.</span></span> <span data-ttu-id="08a04-173">Diese Nummer muss kleiner sein als durchschnittliche Kontakte pro Benutzer.</span><span class="sxs-lookup"><span data-stu-id="08a04-173">This number must be smaller than Average Contacts per User.</span></span>

4.  <span data-ttu-id="08a04-174">Geben Sie in Prozent für Verbund-/Pool Kontakte eine Zahl zwischen 0 und 100 an.</span><span class="sxs-lookup"><span data-stu-id="08a04-174">In Federated / Cross Pool Contacts Percentage, specify a number between 0 and 100.</span></span> <span data-ttu-id="08a04-175">Dieser Prozentsatz der Kontakte wird mit den Verbundbenutzern erstellt.</span><span class="sxs-lookup"><span data-stu-id="08a04-175">This percentage of contacts will be created with the federated users.</span></span>

5.  <span data-ttu-id="08a04-176">Geben Sie unter Benutzerpräfix für Verbund/Cross-Pool den Benutzernamen für Verbundbenutzer an, der den Kontaktlisten lokaler Benutzer hinzugefügt wird.</span><span class="sxs-lookup"><span data-stu-id="08a04-176">In Federated / Cross Pool User Prefix, specify the username for federated users that will be added to the contact lists of local users.</span></span>

6.  <span data-ttu-id="08a04-177">Geben Sie in Pool-SIP-Domäne des Verbund Pools den SIP-Domänennamen der Verbundbenutzer an.</span><span class="sxs-lookup"><span data-stu-id="08a04-177">In Federated / Cross Pool User SIP Domain, specify the SIP Domain Name of the federated users.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="08a04-178">Keiner der Benutzer sollte beim Erstellen von Kontakten angemeldet sein.</span><span class="sxs-lookup"><span data-stu-id="08a04-178">None of the users should be signed in when creating contacts.</span></span>

    
    </div>

7.  <span data-ttu-id="08a04-179">Überprüfen Sie auf der Registerkarte Benutzererstellung, ob die Parameter richtig sind.</span><span class="sxs-lookup"><span data-stu-id="08a04-179">In User Creation tab, verify that the parameters are correct.</span></span> <span data-ttu-id="08a04-180">Der Bereich der Benutzer, für die Kontakte erstellt werden, wird auf der Registerkarte Benutzererstellung abgerufen.</span><span class="sxs-lookup"><span data-stu-id="08a04-180">The range of users for which contacts will be created is obtained from the User Creation tab.</span></span>

8.  <span data-ttu-id="08a04-181">Klicken Sie auf Kontakte erstellen, um mit der Erstellung des Kontakts zu beginnen.</span><span class="sxs-lookup"><span data-stu-id="08a04-181">Click Create Contacts to begin the contact creation.</span></span> <span data-ttu-id="08a04-182">Dieser Vorgang kann mehrere Minuten dauern.</span><span class="sxs-lookup"><span data-stu-id="08a04-182">This process can take several minutes.</span></span> <span data-ttu-id="08a04-183">Nachdem er abgeschlossen wurde, wird ein Dialogfeld mit der Meldung angezeigt, dass der Vorgang erfolgreich abgeschlossen wurde.</span><span class="sxs-lookup"><span data-stu-id="08a04-183">After it completes, a dialog box will appear with the message, "Operation Completed Successfully."</span></span> <span data-ttu-id="08a04-184">Sie können die Kontakte, die erstellt wurden, überprüfen, indem Sie sich als ein Benutzer anmelden, der auf der Registerkarte Benutzererstellung erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="08a04-184">You can validate the contacts that were created by logging on as a user that was created from the User Creation tab.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="08a04-185">Nachdem die Kontakte erstellt wurden, startet dieses Tool alle Front-End-Server im Ziel Pool neu.</span><span class="sxs-lookup"><span data-stu-id="08a04-185">After the contacts are created, this tool will restart all the Front End Servers in the target pool.</span></span> <span data-ttu-id="08a04-186">Je nachdem, wie viele Kontakte durch diesen Vorgang erstellt wurden, kann es länger dauern (bis zu 2 Stunden), bis die Front-End-Server gestartet wurden.</span><span class="sxs-lookup"><span data-stu-id="08a04-186">It may take longer (up to 2 hours) for the Front End Servers to start, depending on how many contacts were created by this operation.</span></span>

    
    </div>

</div>

<div>

## <a name="distribution-list"></a><span data-ttu-id="08a04-187">Verteilerliste</span><span class="sxs-lookup"><span data-stu-id="08a04-187">Distribution List</span></span>

<span data-ttu-id="08a04-188">Eines der Features des lync Server 2013 Stress-und Leistungstools besteht darin, das Erweiterungsfeature Verteilerliste (DL) in lync 2013 zu simulieren.</span><span class="sxs-lookup"><span data-stu-id="08a04-188">One of the features of the Lync Server 2013 Stress and Performance Tool is to simulate the distribution list (DL) expansion feature in Lync 2013.</span></span> <span data-ttu-id="08a04-189">Wenn Sie die DL-Erweiterung in UserProvisioningTool nicht aktivieren, können Sie diesen Schritt überspringen.</span><span class="sxs-lookup"><span data-stu-id="08a04-189">If you are not going to enable DL expansion in UserProvisioningTool, you can skip this step.</span></span>

<span data-ttu-id="08a04-190">![Registerkarte "Erstellung von Verteilerlisten".](images/JJ945587.0a1d681b-2aea-4724-90d8-efa8a526f600(OCS.15).jpg "Registerkarte "Erstellung von Verteilerlisten".")</span><span class="sxs-lookup"><span data-stu-id="08a04-190">![Distribution List Creation tab.](images/JJ945587.0a1d681b-2aea-4724-90d8-efa8a526f600(OCS.15).jpg "Distribution List Creation tab.")</span></span>

<span data-ttu-id="08a04-191">Auf der Registerkarte Verteilerliste können Sie DLS erstellen, die das Belastungs-und Leistungs Tool für das Erweiterungsfeature "Verteilerlisten" verwenden wird.</span><span class="sxs-lookup"><span data-stu-id="08a04-191">The Distribution List tab enables you to create DLs that the Stress and Performance Tool will use for Distribution List Expansion feature.</span></span> <span data-ttu-id="08a04-192">Vor dem Erstellen von Verteilerlisten müssen lync Server 2013 bereits installiert sein.</span><span class="sxs-lookup"><span data-stu-id="08a04-192">Prior to creating DLs, Lync Server 2013 must already be installed.</span></span> <span data-ttu-id="08a04-193">Sie müssen lync Server 2013 ForestPrep ausgeführt haben.</span><span class="sxs-lookup"><span data-stu-id="08a04-193">You must have run Lync Server 2013 ForestPrep.</span></span> <span data-ttu-id="08a04-194">Andernfalls sind die DL-Attribute im Active Directory-Domänendienste-Schema nicht vorhanden, und das Tool kann keine Verteilerlisten erstellen.</span><span class="sxs-lookup"><span data-stu-id="08a04-194">Otherwise, the DL attributes do not exist in the Active Directory Domain Services schema and the tool will not be able to create DLs.</span></span>

<span data-ttu-id="08a04-195">Führen Sie die folgenden Schritte aus, um Verteilerlisten zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="08a04-195">To configure distribution lists, follow these steps.</span></span>

1.  <span data-ttu-id="08a04-196">Geben Sie unter Anzahl der Verteilerlisten die Gesamtzahl der DLS an, die Sie erstellen möchten.</span><span class="sxs-lookup"><span data-stu-id="08a04-196">In Number of Distribution Lists, specify the total number of DLs that you want to create.</span></span> <span data-ttu-id="08a04-197">(Es wird empfohlen, mit der doppelten Anzahl von Benutzern zu beginnen).</span><span class="sxs-lookup"><span data-stu-id="08a04-197">(We recommend that you start with twice the number of users).</span></span> <span data-ttu-id="08a04-198">Sie werden von 0 bis n-1 nummeriert.</span><span class="sxs-lookup"><span data-stu-id="08a04-198">They are numbered from 0 to n-1.</span></span>

2.  <span data-ttu-id="08a04-199">Geben Sie Unterverteiler Listen Präfix das Präfix an, das die DLS aufweisen soll.</span><span class="sxs-lookup"><span data-stu-id="08a04-199">In Distribution List Prefix, specify the prefix that the DLs will have.</span></span> <span data-ttu-id="08a04-200">Wenn Sie beispielsweise 100 DLS und ein Präfix für testDL angeben, werden die DLS mit testDL0, testDL1 usw. über testDL99.</span><span class="sxs-lookup"><span data-stu-id="08a04-200">For example if you specify 100 DLs and a prefix of testDL, the DLs will be named testDL0, testDL1, and so on, through testDL99.</span></span>

3.  <span data-ttu-id="08a04-201">Geben Sie in mindestmember in einer Dist. List die minimale Anzahl von Benutzern an, die in jeder Verteilerliste hinzugefügt werden sollen.</span><span class="sxs-lookup"><span data-stu-id="08a04-201">In Minimum Members in a Dist. List, specify the minimum number of users to add in each Distribution List.</span></span>

4.  <span data-ttu-id="08a04-202">Geben Sie in maximale Mitgliederzahl in einer Dist. List die maximale Anzahl von Benutzern an, die in jeder Verteilerliste hinzugefügt werden soll.</span><span class="sxs-lookup"><span data-stu-id="08a04-202">In Maximum Members in a Dist. List, specify the maximum number of users to add in each Distribution List.</span></span>

<div>

## <a name="create-distribution-lists-button"></a><span data-ttu-id="08a04-203">Schaltfläche "Verteilerlisten erstellen"</span><span class="sxs-lookup"><span data-stu-id="08a04-203">Create Distribution Lists Button</span></span>

<span data-ttu-id="08a04-204">Wenn Sie auf die Schaltfläche Verteilerlisten erstellen klicken, fragt das Tool Active Directory-Domänendienste ab, um zu sehen, ob Verteilerlisten, die mit den Präfixen und Nummern übereinstimmen, bereits vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="08a04-204">When you click the Create Distribution Lists button, the tool queries Active Directory Domain Services to see if distribution lists matching the prefix and numbers already exist.</span></span> <span data-ttu-id="08a04-205">Mit dem Tool werden nur diejenigen erstellt, die noch nicht vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="08a04-205">The tool will create only the ones that do not already exist.</span></span> <span data-ttu-id="08a04-206">Beim Hinzufügen von Mitgliedern zu diesen neu erstellten Verteilerlisten werden die Benutzer aus dem Bereich ausgewählt, der auf der Registerkarte Benutzererstellung angegeben ist.</span><span class="sxs-lookup"><span data-stu-id="08a04-206">When adding members to these newly created Distribution Lists, it will pick the users from the range specified on the User Creation tab.</span></span>

</div>

</div>

<div>

## <a name="location-info-service-config-tab"></a><span data-ttu-id="08a04-207">Registerkarte "Location Info Service config"</span><span class="sxs-lookup"><span data-stu-id="08a04-207">Location Info Service Config Tab</span></span>

<span data-ttu-id="08a04-208">Eines der Features des Tools lync Server 2013 Stress und Leistung ist das Generieren von Dummy-Konfigurationsdateien für den standortinformationsdienst.</span><span class="sxs-lookup"><span data-stu-id="08a04-208">One of the features of the Lync Server 2013 Stress and Performance Tool is to generate dummy configuration files for the Location Information Service.</span></span> <span data-ttu-id="08a04-209">Der standortinformationsdienst hat in der Regel keine nennenswerten Auswirkungen auf die Leistung der Server.</span><span class="sxs-lookup"><span data-stu-id="08a04-209">The Location Information Service typically does not have any significant performance impact on the servers.</span></span>

<span data-ttu-id="08a04-210">![Registerkarte "Location Info Service config".](images/JJ945587.52ea4e9e-d50a-4dc9-982b-31ee5ace4578(OCS.15).jpg "Registerkarte "Location Info Service config".")</span><span class="sxs-lookup"><span data-stu-id="08a04-210">![Location Info Service Config tab.](images/JJ945587.52ea4e9e-d50a-4dc9-982b-31ee5ace4578(OCS.15).jpg "Location Info Service Config tab.")</span></span>

<span data-ttu-id="08a04-211">Wenn Sie dieses Feature testen möchten, können Sie die im Formular genannten Werte eingeben und dann auf die Schaltfläche "LIS-Konfigurationsdateien generieren" klicken.</span><span class="sxs-lookup"><span data-stu-id="08a04-211">If you choose to test this feature, you can fill in the values mentioned in the form and then click the Generate LIS Config Files button.</span></span> <span data-ttu-id="08a04-212">Es generiert CSV-Dateien namens "\_LIS Subnet. csv"\_, "LIS Switches\_. csv", "LIS\_Ports. csv" und "LIS WAP. csv".</span><span class="sxs-lookup"><span data-stu-id="08a04-212">It will generate CSV files called LIS\_Subnet.csv, LIS\_Switches.csv, LIS\_Ports.csv, and LIS\_WAP.csv.</span></span> <span data-ttu-id="08a04-213">Anschließend können Sie diese CSV-Dateien mithilfe des Cmdlets " **CsLisSubnet** ", des Cmdlets " **setCsLisSwitch** ", des Cmdlets " **setCsLisPort** " und des Cmdlets "Sets- **CsWirelessAccessPoint** " in die LIS-Datenbank importieren.</span><span class="sxs-lookup"><span data-stu-id="08a04-213">You can then import these CSV files into LIS database by using the **Set-CsLisSubnet** cmdlet, the **Set-CsLisSwitch** cmdlet, the **Set-CsLisPort** cmdlet, and the **Set-CsWirelessAccessPoint** cmdlet, respectively.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

