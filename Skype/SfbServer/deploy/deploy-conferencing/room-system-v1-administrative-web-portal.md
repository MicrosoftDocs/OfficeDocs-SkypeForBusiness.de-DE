---
title: Bereitstellen des administrativen SRS v1-Webportals in Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 81822efa-2100-4017-a470-8a5b98c49522
ms.collection: M365-voice
description: Das Skype for Business Server Skype Room Systems v1 (SRS v1, früher als lync Room System bezeichnet) administratives Webportal ist ein Webportal, mit dem Organisationen ihre Skype Room Systems-Konferenzräume aufrecht erhalten können. Administratoren können das administrative Webportal von SRS v1 verwenden, um die Geräte Integrität zu überwachen, beispielsweisedurch Überwachung von Audio/Videogeräten. Mit diesem Portal können Administratoren Remote Diagnoseinformationen sammeln, um die Integrität des Konferenzraums zu überwachen.
ms.openlocfilehash: d718adb60437fdd7e08724a5ba5fc48fa120425e
ms.sourcegitcommit: 693205da865111380b55c514955ac264031eb2fd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/02/2020
ms.locfileid: "42045898"
---
# <a name="deploy-srs-v1-administrative-web-portal-in-skype-for-business-server"></a><span data-ttu-id="8ae4e-105">Bereitstellen des administrativen SRS v1-Webportals in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="8ae4e-105">Deploy SRS v1 Administrative Web Portal in Skype for Business Server</span></span>

<span data-ttu-id="8ae4e-106">Das Skype for Business Server Skype Room Systems v1 (SRS v1, früher als lync Room System bezeichnet) administratives Webportal ist ein Webportal, mit dem Organisationen ihre Skype Room Systems-Konferenzräume aufrecht erhalten können.</span><span class="sxs-lookup"><span data-stu-id="8ae4e-106">The Skype for Business Server Skype Room Systems v1 (SRS v1, formerly known as Lync Room System) Administrative Web Portal is a web portal that organizations can use to maintain their Skype Room Systems conference rooms.</span></span> <span data-ttu-id="8ae4e-107">Administratoren können das administrative Webportal von SRS v1 verwenden, um die Geräte Integrität zu überwachen, beispielsweisedurch Überwachung von Audio/Videogeräten.</span><span class="sxs-lookup"><span data-stu-id="8ae4e-107">Administrators can use the SRS v1 Administrative Web Portal to monitor device health, for example by monitoring audio/video devices.</span></span> <span data-ttu-id="8ae4e-108">Mit diesem Portal können Administratoren Remote Diagnoseinformationen sammeln, um die Integrität des Konferenzraums zu überwachen.</span><span class="sxs-lookup"><span data-stu-id="8ae4e-108">With this portal, administrators can remotely collect diagnostic information to monitor conference room health.</span></span>

<span data-ttu-id="8ae4e-109">Um dieses Feature verwenden zu können, muss das administrative Webportal SRS v1 auf jeder Skype for Business Server Front-End-Server bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="8ae4e-109">To use this feature, the SRS v1 Administrative Web Portal needs to be deployed on every Skype for Business Server Front End Server.</span></span> <span data-ttu-id="8ae4e-110">Dieses Handbuch enthält Anweisungen für Administratoren zum Installieren und Konfigurieren des Webportals für die SRS-Verwaltung.</span><span class="sxs-lookup"><span data-stu-id="8ae4e-110">This guide provides instructions for administrators on how to install and configure the SRS Administrative Web Portal.</span></span> <span data-ttu-id="8ae4e-111">Sie richtet sich an Administratoren, die über Kenntnisse in Skype for Business Server Verwaltung verfügen und über Administratorrechte verfügen, um die Skype for Business Server Topologie zu ändern.</span><span class="sxs-lookup"><span data-stu-id="8ae4e-111">It is intended for administrators who have knowledge of Skype for Business Server administration, and who have administrator user rights to modify the Skype for Business Server topology.</span></span>

<span data-ttu-id="8ae4e-112">Nachdem das Verwaltungsportal SRS v1 auf dem Server bereitgestellt wurde, können Administratoren den Status SRS v1-Geräte überprüfen, indem Sie sich über ihre eigenen Computer oder Laptops an der Website anmelden.</span><span class="sxs-lookup"><span data-stu-id="8ae4e-112">After the SRS v1 Administrative Web Portal is deployed on the server, administrators can check the status SRS v1 devices by logging on to the site from their own computers or laptops.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="8ae4e-113">Laden Sie das [Microsoft Skype Room Systems v1-Verwaltungs Webportal für Skype for Business Server 2015](https://www.microsoft.com/download/details.aspx?id=46906)herunter.</span><span class="sxs-lookup"><span data-stu-id="8ae4e-113">Download the [Microsoft Skype Room Systems v1 Administrative Web Portal for Skype for Business Server 2015](https://www.microsoft.com/download/details.aspx?id=46906).</span></span>

<span data-ttu-id="8ae4e-114">Inhalt dieses Themas:</span><span class="sxs-lookup"><span data-stu-id="8ae4e-114">In this topic:</span></span>

- [<span data-ttu-id="8ae4e-115">Konfigurieren der Umgebung für das administrative Webportal von SRS v1</span><span class="sxs-lookup"><span data-stu-id="8ae4e-115">Configure your environment for the SRS v1 Administrative Web Portal</span></span>](room-system-v1-administrative-web-portal.md#Config_Env)

- [<span data-ttu-id="8ae4e-116">Installieren des Administrator-Webportals für SRS v1</span><span class="sxs-lookup"><span data-stu-id="8ae4e-116">Install the SRS v1 Administrative Web Portal</span></span>](room-system-v1-administrative-web-portal.md#Install_SRS)

- [<span data-ttu-id="8ae4e-117">Verwenden des Webportals für die SRS-Verwaltung</span><span class="sxs-lookup"><span data-stu-id="8ae4e-117">Use the SRS Administrative Web Portal</span></span>](room-system-v1-administrative-web-portal.md#Use_Portal)

## <a name="configure-your-environment-for-the-srs-v1-administrative-web-portal"></a><span data-ttu-id="8ae4e-118">Konfigurieren der Umgebung für das administrative Webportal von SRS v1</span><span class="sxs-lookup"><span data-stu-id="8ae4e-118">Configure your environment for the SRS v1 Administrative Web Portal</span></span>
<span data-ttu-id="8ae4e-119"><a name="Config_Env"> </a></span><span class="sxs-lookup"><span data-stu-id="8ae4e-119"><a name="Config_Env"> </a></span></span>

<span data-ttu-id="8ae4e-120">Um das administrative Webportal SRS v1 verwenden zu können, müssen Sie die folgenden Voraussetzungen installieren oder konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="8ae4e-120">To use the SRS v1 Administrative Web Portal, you will need to install or configure the following prerequisites.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="8ae4e-121">Wenn der Server mit der Kerberos-und der NTLM-Authentifizierung konfiguriert ist und SRS auf einem Computer ausgeführt wird, der nicht der Domäne angehört, schlägt die Kerberos-Authentifizierung fehl, und der Benutzer kann den Status SRS nicht im Verwaltungsportal sehen.</span><span class="sxs-lookup"><span data-stu-id="8ae4e-121">If the server is configured with both Kerberos and NTLM authentication, and SRS is running on a computer that is not joined to the domain, Kerberos authentication will fail and the user will not see the status of SRS in the administrative portal.</span></span> <span data-ttu-id="8ae4e-122">Um dieses Problem zu beheben, konfigurieren Sie den Server mit NTLM-Authentifizierung oder mit NTLM-und TLS-DSK-Authentifizierung (ohne Kerberos), oder verbinden Sie den SRS-Computer mit der Domäne.</span><span class="sxs-lookup"><span data-stu-id="8ae4e-122">To resolve this issue, configure the server with NTLM authentication or both NTLM and TLS-DSK authentication (without Kerberos), or join the SRS computer to the domain.</span></span>

1. <span data-ttu-id="8ae4e-123">Installieren Sie Skype for Business Server kumulierten Updates in der Skype for Business Server-Topologie.</span><span class="sxs-lookup"><span data-stu-id="8ae4e-123">Install Skype for Business Server Cumulative Updates in the Skype for Business Server topology.</span></span>

    <span data-ttu-id="8ae4e-124">Informationen zum Abrufen des Updates oder zum Anzeigen der darin enthaltenen Informationen finden Sie unter [Updates für Skype for Business Server 2015](https://support.microsoft.com/help/3061064/updates-for-skype-for-business-server-2015).</span><span class="sxs-lookup"><span data-stu-id="8ae4e-124">To get the update or see what's included with it, see [Updates for Skype for Business Server 2015](https://support.microsoft.com/help/3061064/updates-for-skype-for-business-server-2015).</span></span>

2. <span data-ttu-id="8ae4e-125">Erstellen Sie einen SIP-aktivierten Active Directory-Benutzer.</span><span class="sxs-lookup"><span data-stu-id="8ae4e-125">Create a SIP-enabled Active Directory user.</span></span>

    <span data-ttu-id="8ae4e-126">Das administrative Webportal SRS v1 verwendet diese Anmeldeinformationen zum Abfragen von Informationen aus Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="8ae4e-126">The SRS v1 Administrative Web Portal uses these credentials to query information from Skype for Business Server.</span></span> <span data-ttu-id="8ae4e-127">Der Benutzername in den angegebenen Beispielen lautet LRSApp.</span><span class="sxs-lookup"><span data-stu-id="8ae4e-127">The username in the examples given is LRSApp.</span></span>

3. <span data-ttu-id="8ae4e-128">Erstellen Sie eine Active Directory Sicherheitsgruppe mit dem Namen LRSSupportAdminGroup.</span><span class="sxs-lookup"><span data-stu-id="8ae4e-128">Create an Active Directory security group with name LRSSupportAdminGroup.</span></span>

    <span data-ttu-id="8ae4e-129">Erstellen Sie die Gruppe mit dem Gruppenbereich als globaler und Gruppentyp als Sicherheit.</span><span class="sxs-lookup"><span data-stu-id="8ae4e-129">Create the group with Group Scope as Global and Group Type as Security.</span></span> <span data-ttu-id="8ae4e-130">SIP-aktivierte Benutzer, die dieser Gruppe hinzugefügt werden, sind berechtigt, die Liste der Räume anzuzeigen und bestimmte Befehle auszuführen, beispielsweise das Sammeln von Protokollen.</span><span class="sxs-lookup"><span data-stu-id="8ae4e-130">SIP enabled users who are added to this group will be authorized to see the list of rooms and execute certain commands, such as collecting logs.</span></span>

4. <span data-ttu-id="8ae4e-131">Erstellen Sie eine Active Directory Sicherheitsgruppe mit dem Namen LRSFullAccessAdminGroup.</span><span class="sxs-lookup"><span data-stu-id="8ae4e-131">Create an Active Directory security group with name LRSFullAccessAdminGroup.</span></span>

    <span data-ttu-id="8ae4e-132">Erstellen Sie die Gruppe mit Gruppenbereich als globaler und Gruppentyp als Sicherheit. SIP-aktivierte Benutzer, die dieser Gruppe hinzugefügt werden, sind berechtigt, alle Verwaltungsportal Funktionen in einem einzelnen Skype-Raum zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="8ae4e-132">Create the group with Group Scope as Global and Group Type as Security.SIP enabled users who are added to this group are authorized to use all admin portal functionality on a single Skype room.</span></span> <span data-ttu-id="8ae4e-133">Wenn Sie Unterstützung für die Massenverwaltung von Skype-Räumen einschließen möchten, lesen Sie Schritt 5.</span><span class="sxs-lookup"><span data-stu-id="8ae4e-133">To include support for bulk management of Skype rooms, refer to step 5.</span></span>

     ![Liste der Administratorgruppen mit der Rolle "Sicherheitsgruppe"](../../media/LRS_LRSFullAccessAdminGroup.png)

5. <span data-ttu-id="8ae4e-135">Erstellen Sie eine Active Directory Sicherheitsgruppe mit dem Namen LRSPowerUserAdminsGroup.</span><span class="sxs-lookup"><span data-stu-id="8ae4e-135">Create an Active Directory security group with name LRSPowerUserAdminsGroup.</span></span>

    <span data-ttu-id="8ae4e-136">Erstellen Sie die Gruppe mit dem Gruppenbereich als globaler und Gruppentyp als Sicherheit.</span><span class="sxs-lookup"><span data-stu-id="8ae4e-136">Create the group with Group Scope as Global and Group Type as Security.</span></span> <span data-ttu-id="8ae4e-137">SIP-aktivierte Benutzer, die dieser Gruppe hinzugefügt werden, sind berechtigt, alle Verwaltungsportal Funktionen einschließlich der Massenverwaltung von Skype for Business Chatrooms zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="8ae4e-137">SIP enabled users who are added to this group are authorized to use all admin portal functionality including bulk management of Skype for Business rooms.</span></span>

6. <span data-ttu-id="8ae4e-138">Fügen Sie LRSFullAccessAdminGroup als Mitglied von LRSSupportAdminGroup hinzu.</span><span class="sxs-lookup"><span data-stu-id="8ae4e-138">Add LRSFullAccessAdminGroup as a member of LRSSupportAdminGroup.</span></span>

     ![LRSSupportAdminGroup-Eigenschaften-Mitgliederseite](../../media/LRS_Add_LRSSupportAdminGroup.png)

7. <span data-ttu-id="8ae4e-140">Erstellen Sie einen SIP-aktivierten Active Directory Benutzer mit dem Namen LRSSupport.</span><span class="sxs-lookup"><span data-stu-id="8ae4e-140">Create a SIP enabled Active Directory user with name LRSSupport.</span></span> <span data-ttu-id="8ae4e-141">Fügen Sie diesen Benutzer zu LRSSupportAdminGroup hinzu.</span><span class="sxs-lookup"><span data-stu-id="8ae4e-141">Add this user to LRSSupportAdminGroup.</span></span>

     ![LRSSupportAdminGroup-Eigenschaften-Mitgliederseite](../../media/LRS_Add_LRS_SIP_SupportUser.png)

8. <span data-ttu-id="8ae4e-143">Installieren Sie [ASP.NET MVC 4 für Visual Studio 2010 SP1 und Visual-webdeveloper 2010 SP1](https://go.microsoft.com/fwlink/p/?LinkId=323967).</span><span class="sxs-lookup"><span data-stu-id="8ae4e-143">Install [ASP.NET MVC 4 for Visual Studio 2010 SP1 and Visual Web Developer 2010 SP1](https://go.microsoft.com/fwlink/p/?LinkId=323967).</span></span>

## <a name="install-the-srs-v1-administrative-web-portal"></a><span data-ttu-id="8ae4e-144">Installieren des Administrator-Webportals für SRS v1</span><span class="sxs-lookup"><span data-stu-id="8ae4e-144">Install the SRS v1 Administrative Web Portal</span></span>
<span data-ttu-id="8ae4e-145"><a name="Install_SRS"> </a></span><span class="sxs-lookup"><span data-stu-id="8ae4e-145"><a name="Install_SRS"> </a></span></span>

<span data-ttu-id="8ae4e-146">Laden Sie das [Microsoft Skype Room Systems v1-Verwaltungs Webportal für Skype for Business Server 2015](https://www.microsoft.com/download/details.aspx?id=46906)herunter.</span><span class="sxs-lookup"><span data-stu-id="8ae4e-146">Download the [Microsoft Skype Room Systems v1 Administrative Web Portal for Skype for Business Server 2015](https://www.microsoft.com/download/details.aspx?id=46906).</span></span>

<span data-ttu-id="8ae4e-147">Führen Sie die folgenden Schritte aus, um das administrative Webportal von SRS V1 zu installieren.</span><span class="sxs-lookup"><span data-stu-id="8ae4e-147">To install the SRS v1 Administrative Web Portal, use the following steps.</span></span>

1. <span data-ttu-id="8ae4e-148">Konfigurieren Sie den Port für vertrauenswürdige Anwendungen, indem Sie das folgende Cmdlet in Skype for Business Server Management Shell ausführen:</span><span class="sxs-lookup"><span data-stu-id="8ae4e-148">Configure the Trusted Application Port by running the following cmdlet in Skype for Business Server Management Shell:</span></span>

   ```powershell
   Set-CsWebServer -Identity POOLFQDN -MeetingRoomAdminPortalInternalListeningPort 4456 -MeetingRoomAdminPortalExternalListeningPort 4457
   ```

2. <span data-ttu-id="8ae4e-149">Um das Besprechungsraum Portal zu installieren, laden Sie **MeetingRoomPortalInstaller. msi** herunter, und führen Sie es dann als Administrator aus.</span><span class="sxs-lookup"><span data-stu-id="8ae4e-149">To install the Meeting Room Portal, download **MeetingRoomPortalInstaller.msi** and then run it as an administrator.</span></span>

3. <span data-ttu-id="8ae4e-150">Öffnen Sie die Datei "file. config" unter folgendem Speicherort:</span><span class="sxs-lookup"><span data-stu-id="8ae4e-150">Open the Web.config file from the following location:</span></span>

    <span data-ttu-id="8ae4e-151">% Programm-files%\Skype for Business Server 2015 \ Components\Meeting Raum Portal\Int\Handler</span><span class="sxs-lookup"><span data-stu-id="8ae4e-151">%Program Files%\Skype for Business Server 2015\Web Components\Meeting Room Portal\Int\Handler</span></span>\

4. <span data-ttu-id="8ae4e-152">Ändern Sie in der Datei "file. config" den PortalUserName in den in Schritt 2 erstellten Benutzernamen im Abschnitt "[Konfigurieren der Umgebung für das administrative Webportal der SRS v1](room-system-v1-administrative-web-portal.md#Config_Env)" (der empfohlene Name im Schritt lautet LRSApp):</span><span class="sxs-lookup"><span data-stu-id="8ae4e-152">In the Web.Config file, change the PortalUserName to the username created in Step 2 under the section "[Configure your environment for the SRS v1 Administrative Web Portal](room-system-v1-administrative-web-portal.md#Config_Env)" (the recommended name in the step is LRSApp):</span></span>

    ```xml
    <add key="PortalUserName" value="sip:LRSApp@domain.com" />
    ```

5. <span data-ttu-id="8ae4e-153">Da das SRS v1-Verwaltungsportal eine vertrauenswürdige Anwendung ist, müssen Sie das Kennwort nicht in der Portal Konfiguration angeben.</span><span class="sxs-lookup"><span data-stu-id="8ae4e-153">Because the SRS v1 Admin Portal is a trusted application, you do not need to provide the password in the portal configuration.</span></span> <span data-ttu-id="8ae4e-154">Wenn dieser Benutzer eine andere Registrierungsstelle als die lokale Registrierungsstelle verwendet, müssen Sie die Registrierungsstelle dafür angeben, indem Sie die folgende in der Datei "Internet. config" hinzufügen:</span><span class="sxs-lookup"><span data-stu-id="8ae4e-154">If this user is using a different registrar than local registrar, you need to specify the registrar for it by adding the following line in the Web.Config file:</span></span>

   ```xml
   <add key="PortalUserRegistrarFQDN" value="pool-xxxx.domain.com" />
   ```

6. <span data-ttu-id="8ae4e-155">Wenn es sich bei dem verwendeten Port nicht um 5061 handelt, fügen Sie die folgende in der Datei "Internet. config" hinzu:</span><span class="sxs-lookup"><span data-stu-id="8ae4e-155">If the port used is other than 5061, add the following line in the Web.Config file:</span></span>

   ```xml
   <add key="PortalUserRegistrarPort" value="5061" />
   ```

### <a name="verify-installation-of-the-srs-administrative-web-portal"></a><span data-ttu-id="8ae4e-156">Überprüfen der Installation des Webportals für die SRS-Verwaltung</span><span class="sxs-lookup"><span data-stu-id="8ae4e-156">Verify Installation of the SRS Administrative Web Portal</span></span>

<span data-ttu-id="8ae4e-157">Führen Sie die folgenden Schritte aus, um die Installation des administrativen Webportal SRS V1 zu überprüfen:</span><span class="sxs-lookup"><span data-stu-id="8ae4e-157">To verify installation of the SRS v1 Administrative Web Portal, do the following:</span></span>

1. <span data-ttu-id="8ae4e-158">Navigieren Sie auf einem Front-End-Server zur folgenden URL:</span><span class="sxs-lookup"><span data-stu-id="8ae4e-158">On a Front End server, browse to the following URL:</span></span>

    <span data-ttu-id="8ae4e-159">https:// \<fe-server\> /LRS</span><span class="sxs-lookup"><span data-stu-id="8ae4e-159">https://\<fe-server\>/lrs</span></span>

    <span data-ttu-id="8ae4e-160">Es sollten keine Fehler angezeigt werden, wie in der folgenden Abbildung dargestellt:</span><span class="sxs-lookup"><span data-stu-id="8ae4e-160">You should not see any errors, as shown in the following image:</span></span>

     ![Anmeldebildschirm des lync Room-System Administrator Portals](../../media/LRS_AdminPortalSignIn.png)

2. <span data-ttu-id="8ae4e-162">Wenn keine Fehler angezeigt werden, versuchen Sie von einem anderen Computer in der Topologie aus auf die folgende URL zuzugreifen:</span><span class="sxs-lookup"><span data-stu-id="8ae4e-162">If you do not see any errors, try accessing the following URL from any other computer in the topology:</span></span>

    <span data-ttu-id="8ae4e-163">https:// \<fe-server\> /LRS</span><span class="sxs-lookup"><span data-stu-id="8ae4e-163">https://\<fe-server\>/lrs</span></span>

    <span data-ttu-id="8ae4e-164">Um auf die Seite zugreifen zu können, müssen Sie die DNS-Einträge wie unter "[erforderliche DNS-Einträge für die automatische Client Anmeldung](https://go.microsoft.com/fwlink/p/?LinkId=318056)" beschrieben hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="8ae4e-164">To access the page, you will need to add the DNS records as described in "[Required DNS Records for Automatic Client Sign-In](https://go.microsoft.com/fwlink/p/?LinkId=318056)."</span></span>

## <a name="use-the-srs-administrative-web-portal"></a><span data-ttu-id="8ae4e-165">Verwenden des Webportals für die SRS-Verwaltung</span><span class="sxs-lookup"><span data-stu-id="8ae4e-165">Use the SRS Administrative Web Portal</span></span>
<span data-ttu-id="8ae4e-166"><a name="Use_Portal"> </a></span><span class="sxs-lookup"><span data-stu-id="8ae4e-166"><a name="Use_Portal"> </a></span></span>

<span data-ttu-id="8ae4e-167">Nachdem Sie SRS auf dem Server bereitgestellt haben, können Sie den Status aller SRS-Räume überprüfen, indem Sie sich über einen Browser beim administrativen Webportal SRS v1 anmelden.</span><span class="sxs-lookup"><span data-stu-id="8ae4e-167">After you deploy SRS on the server, you can check the status of all SRS rooms by signing into the SRS v1 Administrative Web Portal from a browser.</span></span>

### <a name="sign-in"></a><span data-ttu-id="8ae4e-168">Anmelden</span><span class="sxs-lookup"><span data-stu-id="8ae4e-168">Sign in</span></span>

1. <span data-ttu-id="8ae4e-169">Wechseln Sie zur folgenden URL:</span><span class="sxs-lookup"><span data-stu-id="8ae4e-169">Browse to the following URL:</span></span>

    <span data-ttu-id="8ae4e-170">https:// \<fe-server\> /LRS</span><span class="sxs-lookup"><span data-stu-id="8ae4e-170">https://\<fe-server\>/lrs</span></span>

2. <span data-ttu-id="8ae4e-171">Geben Sie die Anmeldeinformationen für das LRSSupport-Konto oder ein Konto ein, das der Sicherheitsgruppe LRSSupportAdminGroup hinzugefügt wurde.</span><span class="sxs-lookup"><span data-stu-id="8ae4e-171">Enter the credentials for the LRSSupport account or an account that was added to the LRSSupportAdminGroup security group.</span></span>

![Anmeldebildschirm des lync Room-System Administrator Portals](../../media/LRS_AdminPortalSignIn.png)

### <a name="srs-administrative-web-portal-summary-page"></a><span data-ttu-id="8ae4e-173">Seite "Zusammenfassung der SRS-administrativen Webportale"</span><span class="sxs-lookup"><span data-stu-id="8ae4e-173">SRS Administrative Web Portal Summary Page</span></span>

<span data-ttu-id="8ae4e-174">Die Zusammenfassungsseite enthält die folgenden Informationen für alle auf dem Server bereitgestellten SRS-Räume:</span><span class="sxs-lookup"><span data-stu-id="8ae4e-174">The summary page provides the following information for all of the SRS rooms deployed on the server:</span></span>

- <span data-ttu-id="8ae4e-175">- **Tag** Der benutzerdefinierte Name, den der Administrator dem Chatroom übergibt.</span><span class="sxs-lookup"><span data-stu-id="8ae4e-175">**Tag** The custom name that the administrator gives to the room.</span></span> <span data-ttu-id="8ae4e-176">Das-Tag kann im Portal festgelegt werden, indem auf den Raumnamen geklickt wird.</span><span class="sxs-lookup"><span data-stu-id="8ae4e-176">The Tag can be set in the portal by clicking on the room name.</span></span>

- <span data-ttu-id="8ae4e-177">**Integrität** Der Integritätsstatus des Raums, der vom aggregierten Integritätsstatus des Raums abgeleitet wird, der auf der Seite "Raumeinstellungen" im Abschnitt "Integrität" angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="8ae4e-177">**Health** The health status of the room, which is derived from the Aggregate Health status of the room, which is shown under the Health section of the Room Settings page.</span></span>

- <span data-ttu-id="8ae4e-178">**Nächste Besprechung** Das Datum und die Uhrzeit, zu denen die nächste Besprechung geplant ist.</span><span class="sxs-lookup"><span data-stu-id="8ae4e-178">**Next Meeting** The date and time the next meeting is scheduled.</span></span>

- <span data-ttu-id="8ae4e-179">**SRS-Version, Hersteller, Modell** Diese Werte sind in SRS voreingestellt.</span><span class="sxs-lookup"><span data-stu-id="8ae4e-179">**SRS Version, Manufacturer, Model** These values are preset in SRS.</span></span> <span data-ttu-id="8ae4e-180">Je nach Hersteller können diese Felder leer bleiben.</span><span class="sxs-lookup"><span data-stu-id="8ae4e-180">Depending on the manufacturer, these fields might be left blank.</span></span>

- <span data-ttu-id="8ae4e-181">**Letzte Aktualisierung** Zeigt an, wann die Webseite zuletzt aktualisiert wurde.</span><span class="sxs-lookup"><span data-stu-id="8ae4e-181">**Last Refresh** Displays the last time the web page was refreshed.</span></span>

![Zusammenfassung der lync Room System-Administrator Portal-Ansicht](../../media/LRS_AdminPortal_Summary_view.png)

> [!NOTE]
> <span data-ttu-id="8ae4e-183">Das Menü Massenverwaltung wird nur angezeigt, wenn Sie Mitglied der Sicherheitsgruppe LRSPowerUserAdminsGroup sind.</span><span class="sxs-lookup"><span data-stu-id="8ae4e-183">You will only see the Bulk Management menu if you are part of the LRSPowerUserAdminsGroup security group.</span></span>

### <a name="srs-room-information"></a><span data-ttu-id="8ae4e-184">SRS-Rauminformationen</span><span class="sxs-lookup"><span data-stu-id="8ae4e-184">SRS Room Information</span></span>

<span data-ttu-id="8ae4e-185">Im Abschnitt Rauminformationen des Portals können Sie einzelne SRS-Räume anzeigen und konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="8ae4e-185">The Room Info section of the portal allows you to view and configure individual SRS rooms.</span></span> <span data-ttu-id="8ae4e-186">Es enthält vier Abschnitte: Einstellungen, Details, Protokollierung und Integrität.</span><span class="sxs-lookup"><span data-stu-id="8ae4e-186">It contains four sections: Settings, Details, Logging, and Health.</span></span>

#### <a name="settings"></a><span data-ttu-id="8ae4e-187">Einstellungen</span><span class="sxs-lookup"><span data-stu-id="8ae4e-187">Settings</span></span>

<span data-ttu-id="8ae4e-188">Im Abschnitt "Einstellungen" können Sie das Kennwort, das Raum-Tag und die Standardlautstärke für den Raum festlegen.</span><span class="sxs-lookup"><span data-stu-id="8ae4e-188">In the Settings section, you can set the password, room tag, and default volume levels for the room.</span></span> <span data-ttu-id="8ae4e-189">Wenn Sie diese Einstellungen konfigurieren, werden die Änderungen erst nach dem Neustart der SRS-Konsole repliziert.</span><span class="sxs-lookup"><span data-stu-id="8ae4e-189">If you configure these settings, the changes are replicated only after you restart the SRS console.</span></span> <span data-ttu-id="8ae4e-190">Es werden nur System Updateeinstellungen für SRS-Geräte mithilfe von Version 15,12 und höher angezeigt.</span><span class="sxs-lookup"><span data-stu-id="8ae4e-190">You will only see System Updates settings for SRS devices using release 15.12 and later.</span></span>

![Raum System-Administrator Portal-Einstellungen für lync Room-Systeme](../../media/LRS_AdminPortal_RoomInfoSettings.png)

#### <a name="details"></a><span data-ttu-id="8ae4e-192">Details</span><span class="sxs-lookup"><span data-stu-id="8ae4e-192">Details</span></span>

<span data-ttu-id="8ae4e-193">Der Abschnitt Details enthält eine schreibgeschützte Zusammenfassung der Einstellungen des SRS-Raums, einschließlich: der Zeitpunkt der letzten Aktualisierung; nächste Besprechung; Letzte Aktualisierungen, Wartung und Kalibrierung; Standardeinstellungen für Lautsprecher, Mic und Rufton; Version SIP-URI; Anzahl der Bildschirme und Details zu jedem Bildschirm; Status und Aktivität.</span><span class="sxs-lookup"><span data-stu-id="8ae4e-193">The Details section provides a read-only summary of the SRS room's settings, including: the time of last refresh; next meeting; last updates, maintenance and calibration; default speaker, mic, and ringer settings; version; SIP URI; number of screens and details about each screen; status, and activity.</span></span>

![Detail Ansicht des lync Room-System Administrator Portals](../../media/LRS_AdminPortal_Detail_view.png)

#### <a name="troubleshooting"></a><span data-ttu-id="8ae4e-195">Problembehandlung</span><span class="sxs-lookup"><span data-stu-id="8ae4e-195">Troubleshooting</span></span>

<span data-ttu-id="8ae4e-196">Der Abschnitt Problembehandlung kann verwendet werden, um Protokolle Remote zu sammeln und Sie an einem angegebenen Speicherort zu speichern.</span><span class="sxs-lookup"><span data-stu-id="8ae4e-196">The Troubleshooting section can be used to remotely collect logs and save them to a specified location.</span></span> <span data-ttu-id="8ae4e-197">Sie können auch die SRS-Konsole (SRS-Benutzeroberfläche) neu starten oder das gesamte System neu starten.</span><span class="sxs-lookup"><span data-stu-id="8ae4e-197">You can also restart the SRS console (SRS user interface) or restart the entire system.</span></span> <span data-ttu-id="8ae4e-198">Geben Sie zum Sammeln von Protokollen einen Ordnerpfad im angegebenen Format an, und stellen Sie sicher, dass der Ordner über Schreibberechtigungen verfügt, die für das Konto des SRS-Computers erteilt wurden.</span><span class="sxs-lookup"><span data-stu-id="8ae4e-198">To collect logs, provide a folder path in the specified format and make sure that the folder has write permissions given to the SRS machine account.</span></span> <span data-ttu-id="8ae4e-199">Wenn die Protokollgröße zu groß ist, kann es bis zu 5 Minuten dauern, bis das Sammeln von Protokollen abgeschlossen ist.</span><span class="sxs-lookup"><span data-stu-id="8ae4e-199">If the log size is too big, it can take up to 5 minutes to finish collecting logs.</span></span> <span data-ttu-id="8ae4e-200">Wenn Sie die Seite aktualisieren, erhalten Sie den neuesten Status.</span><span class="sxs-lookup"><span data-stu-id="8ae4e-200">Refreshing the page will give you the latest status.</span></span>

#### <a name="health"></a><span data-ttu-id="8ae4e-201">Gesundheitswesen</span><span class="sxs-lookup"><span data-stu-id="8ae4e-201">Health</span></span>

<span data-ttu-id="8ae4e-202">Der Abschnitt "Integrität" gibt einen visuellen Hinweis auf die Integrität der Skype for Business Server-Verbindung, des Audiogeräts, des Videogeräts, des Zustands der Ausfallsicherheit und des Bildschirmgeräts.</span><span class="sxs-lookup"><span data-stu-id="8ae4e-202">The Health section gives a visual indication of the health of the Skype for Business Server connection, audio device, video device, resiliency state, and screen device.</span></span>

![Raum System-Administrator Portal für lync Room-Integrität](../../media/LRS_AdminPortal_RoomInfoHealth.png)

### <a name="additional-notes-about-the-administrative-web-portal"></a><span data-ttu-id="8ae4e-204">Zusätzliche Hinweise zum administrativen Webportal</span><span class="sxs-lookup"><span data-stu-id="8ae4e-204">Additional Notes about the Administrative Web Portal</span></span>

> [!NOTE]
>  <span data-ttu-id="8ae4e-205">Einstellungsänderungen werden erst dann angewendet, wenn das SRS-System neu gestartet wird. > Wenn das LRSApp-Kontokennwort abgelaufen ist, können Sie den Status der Räume nicht anzeigen.</span><span class="sxs-lookup"><span data-stu-id="8ae4e-205">Setting changes are applied only after the SRS system is restarted.>  If the LRSApp account password expires, you will not be able to see the status of the rooms.</span></span> <span data-ttu-id="8ae4e-206">Konfigurieren Sie das Kennwort für das LRSAppuser-Konto so, dass es nie abläuft, oder aktualisieren Sie das Kennwort, wenn es sich in der Nähe des Ablaufs befindet. > das SRS-Verwaltungsportal wird nur für lokale Bereitstellungen unterstützt.</span><span class="sxs-lookup"><span data-stu-id="8ae4e-206">Configure the LRSAppuser account password so that it never expires, or be sure to update the password when it is near expiration.>  The SRS administrative web portal is supported for on-premises deployments only.</span></span>

### <a name="bulk-management"></a><span data-ttu-id="8ae4e-207">Massenverwaltung</span><span class="sxs-lookup"><span data-stu-id="8ae4e-207">Bulk management</span></span>

<span data-ttu-id="8ae4e-208">Die Massenverwaltung von SRS Rooms ist ein Feature, das für fortgeschrittene IT-Administratoren entwickelt wurde, um den Workflow zu vereinfachen und Sie mit einem zeitsparenden, bequemen Tool zur Remoteverwaltung mehrerer Räume in massenweise zu ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="8ae4e-208">Bulk management of SRS rooms is a feature designed for advanced IT administrators, to simplify their workflow, and enable them with a time-saving convenient tool to remotely manage multiple rooms in a bulk fashion.</span></span>

<span data-ttu-id="8ae4e-209">Um diese Funktionalität sehen zu können, muss der Benutzer als Mitglied der speziellen Sicherheitsgruppe " **LRSPowerUserAdminsGroup**" bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="8ae4e-209">In order to see this functionality, the user need to be provisioned as a member of the special security group, **LRSPowerUserAdminsGroup**.</span></span>

<span data-ttu-id="8ae4e-210">Es gibt keine Beschränkung für die Anzahl der SRS-Räume, die Sie für die Massenverwaltung auswählen können.</span><span class="sxs-lookup"><span data-stu-id="8ae4e-210">There is no limit to the number of SRS rooms you can select for bulk management.</span></span> <span data-ttu-id="8ae4e-211">Sie können jedoch jeweils nur einen Massen Verwaltungsvorgang ausführen.</span><span class="sxs-lookup"><span data-stu-id="8ae4e-211">However, you can perform only one bulk management operation at a time.</span></span>

<span data-ttu-id="8ae4e-212">Wählen Sie zum Durchführen eines Massen Verwaltungsvorgangs die Räume aus, die Sie überwachen möchten, und klicken Sie dann auf das Massen Verwaltungsmenü.</span><span class="sxs-lookup"><span data-stu-id="8ae4e-212">To perform a bulk management operation, select the rooms you want to monitor, and click on the Bulk management menu.</span></span>

### <a name="frequently-asked-questions"></a><span data-ttu-id="8ae4e-213">Häufig gestellte Fragen</span><span class="sxs-lookup"><span data-stu-id="8ae4e-213">Frequently asked questions</span></span>

#### <a name="why-cant-i-sign-in-to-the-administrative-web-portal"></a><span data-ttu-id="8ae4e-214">Warum kann ich mich nicht beim administrativen Webportal anmelden?</span><span class="sxs-lookup"><span data-stu-id="8ae4e-214">Why can't I sign in to the administrative web portal?</span></span>

<span data-ttu-id="8ae4e-215">Wenn Sie öffnen https://localhost/lrs , werden Sie die Anmeldeseite sehen können, aber wenn Sie Ihre Anmeldeinformationen eingeben, können Sie sich nicht anmelden.</span><span class="sxs-lookup"><span data-stu-id="8ae4e-215">When you open https://localhost/lrs, you will be able to see the sign in page, but when you type in your credentials, you cannot sign in.</span></span> <span data-ttu-id="8ae4e-216">In diesem Fall müssen Sie sich öffnen, um https://FQDNofFEserver/SRS sich beim administrativen Webportal anzumelden.</span><span class="sxs-lookup"><span data-stu-id="8ae4e-216">In this case, you must open https://FQDNofFEserver/SRS to sign in to the administrative web portal.</span></span>

#### <a name="why-cant-i-see-srs-v1-in-the-administrative-web-portal"></a><span data-ttu-id="8ae4e-217">Warum wird SRS v1 nicht im administrativen Webportal angezeigt?</span><span class="sxs-lookup"><span data-stu-id="8ae4e-217">Why can't I see SRS v1 in the administrative web portal?</span></span>

- <span data-ttu-id="8ae4e-218">Stellen Sie sicher, dass Sie über SRS-Konten in Ihrer Bereitstellung verfügen und dass Sie gemäß den Bereitstellungsempfehlungen für das SRS-Verwaltungsportal erstellt wurden.</span><span class="sxs-lookup"><span data-stu-id="8ae4e-218">Make sure you have SRS accounts in your deployment and that they are created according to the SRS Administrative Web Portal deployment recommendations.</span></span> <span data-ttu-id="8ae4e-219">Stellen Sie sicher, dass die SRS-Konten mithilfe von enable-csmeetingroom ", not enable-CsUser, im Skype for Business Server bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="8ae4e-219">Make sure the SRS accounts are provisioned using Enable-CsMeetingRoom, not Enable-CsUser, on the Skype for Business Server.</span></span>

- <span data-ttu-id="8ae4e-220">Wenn Sie SRS-Konten erstellt haben und die Konten im administrativen Webportal nicht sehen können, sammeln Sie die Serverprotokolle mithilfe des Skype for Business Server Protokollierungstools, wobei die **MeetingPortal** -Komponente ausgewählt ist, und senden Sie Sie dann an Ihren SRS-Support Kontakt.</span><span class="sxs-lookup"><span data-stu-id="8ae4e-220">If you have created SRS accounts and cannot see the accounts in administrative web portal, collect the server logs by using the Skype for Business Server Logging tool with the **MeetingPortal** component selected, and then send them to your SRS support contact.</span></span>

- <span data-ttu-id="8ae4e-221">Wenn Sie SRS-Konten erstellt haben und die Konten im administrativen Webportal nicht sehen können, sammeln Sie die Clientprotokolle mit Fiddler und kopieren Sie das Konsolenprotokoll auch aus den Browser Entwicklungstools, und senden Sie Sie dann an Ihren SRS-Support Kontakt.</span><span class="sxs-lookup"><span data-stu-id="8ae4e-221">If you have created SRS accounts and cannot see the accounts in administrative web portal, collect the client logs using Fiddler, and also copy the console log from the browser development tools, and then send them to your SRS support contact.</span></span> <span data-ttu-id="8ae4e-222">Sie können den Wert der Ablaufverfolgungsstufe auch in der Datei "Internet. config" ändern, um ein detaillierteres Protokoll zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="8ae4e-222">You can also modify the trace level value in the Web.config to get a more detailed log.</span></span>

  ```xml
  <system.diagnostics>
    <switches>
      <!--
      This switch controls logging message levels. 0 implies
      logging is turned off. 1 implies only errors are logged,
      2 implies errors &amp; warnings. 4 is the most detailed.
      -->
      <add name="TraceLevelSwitch" value="3" />
    </switches>
  </system.diagnostics>
  ```

#### <a name="why-cant-i-see-the-status-of-srs-in-the-administrative-web-portal"></a><span data-ttu-id="8ae4e-223">Warum kann ich den Status von SRS nicht im administrativen Webportal anzeigen?</span><span class="sxs-lookup"><span data-stu-id="8ae4e-223">Why can't I see the status of SRS in the administrative web portal?</span></span>

- <span data-ttu-id="8ae4e-224">Stellen Sie sicher, dass das LRSApp-Benutzerkonto SIP-aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="8ae4e-224">Make sure that the LRSApp user account is SIP-enabled.</span></span>

- <span data-ttu-id="8ae4e-225">Wenn Sie weiterhin Probleme haben, sammeln Sie die Datei **Trace. log** im SRS-System von D:\Tracing\LRSAdminLogs, \, und senden Sie Sie dann an Ihren SRS-Support Kontakt.</span><span class="sxs-lookup"><span data-stu-id="8ae4e-225">If you are still having issues, collect the **Trace.log** file in the SRS system from D:\Tracing\LRSAdminLogs\, and then send it to your SRS support contact.</span></span>

#### <a name="why-cant-i-see-the-bulk-management-menus-for-srs-in-the-administrative-web-portal"></a><span data-ttu-id="8ae4e-226">Warum kann ich die Menüs für die Massenverwaltung für SRS nicht im administrativen Webportal anzeigen?</span><span class="sxs-lookup"><span data-stu-id="8ae4e-226">Why can't I see the bulk management menus for SRS in the administrative web portal?</span></span>

<span data-ttu-id="8ae4e-227">Stellen Sie sicher, dass das LRSApp-Benutzerkonto SIP-aktiviert ist und Teil der Sicherheitsgruppe LRSPowerUserAdminsGroup ist.</span><span class="sxs-lookup"><span data-stu-id="8ae4e-227">Make sure that the LRSApp user account is SIP-enabled, and is part of the LRSPowerUserAdminsGroup security group.</span></span>

#### <a name="does-the-srs-v1-administrative-web-portal-work-with-microsoft-teams-rooms"></a><span data-ttu-id="8ae4e-228">Funktioniert das administrative Webportal SRS V1 mit Microsoft Teams-Räumen?</span><span class="sxs-lookup"><span data-stu-id="8ae4e-228">Does the SRS v1 administrative web portal work with Microsoft Teams Rooms?</span></span>

<span data-ttu-id="8ae4e-229">Nein.</span><span class="sxs-lookup"><span data-stu-id="8ae4e-229">No.</span></span>


