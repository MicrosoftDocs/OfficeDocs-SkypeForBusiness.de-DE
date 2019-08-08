---
title: Bereitstellen des Administrator-Web-Portals für SRS V1 in Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 81822efa-2100-4017-a470-8a5b98c49522
ms.collection: M365-voice
description: Der Skype for Business-Server Skype Room Systems v1 (SRS v1, ehemals lync Room System) administratives Webportal ist ein Webportal, das Organisationen verwenden können, um Ihre Skype Room Systems-Konferenzräume zu verwalten. Administratoren können das administrative Web Portal für SRS v1 verwenden, um die Geräte Integrität zu überwachen, beispielsweisedurch überwachen von Audio/Video-Geräten. Mit diesem Portal können Administratoren über Remoteverbindungen Diagnoseinformationen sammeln, um die Konferenzraumintegrität zu überwachen.
ms.openlocfilehash: bf18cefbdaa5beeaef63d16b5447cce2969fc147
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/07/2019
ms.locfileid: "36234174"
---
# <a name="deploy-srs-v1-administrative-web-portal-in-skype-for-business-server"></a><span data-ttu-id="8a97a-105">Bereitstellen des Administrator-Web-Portals für SRS V1 in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="8a97a-105">Deploy SRS v1 Administrative Web Portal in Skype for Business Server</span></span>

<span data-ttu-id="8a97a-106">Der Skype for Business-Server Skype Room Systems v1 (SRS v1, ehemals lync Room System) administratives Webportal ist ein Webportal, das Organisationen verwenden können, um Ihre Skype Room Systems-Konferenzräume zu verwalten.</span><span class="sxs-lookup"><span data-stu-id="8a97a-106">The Skype for Business Server Skype Room Systems v1 (SRS v1, formerly known as Lync Room System) Administrative Web Portal is a web portal that organizations can use to maintain their Skype Room Systems conference rooms.</span></span> <span data-ttu-id="8a97a-107">Administratoren können das administrative Web Portal für SRS v1 verwenden, um die Geräte Integrität zu überwachen, beispielsweisedurch überwachen von Audio/Video-Geräten.</span><span class="sxs-lookup"><span data-stu-id="8a97a-107">Administrators can use the SRS v1 Administrative Web Portal to monitor device health, for example by monitoring audio/video devices.</span></span> <span data-ttu-id="8a97a-108">Mit diesem Portal können Administratoren über Remoteverbindungen Diagnoseinformationen sammeln, um die Konferenzraumintegrität zu überwachen.</span><span class="sxs-lookup"><span data-stu-id="8a97a-108">With this portal, administrators can remotely collect diagnostic information to monitor conference room health.</span></span>

<span data-ttu-id="8a97a-109">Um dieses Feature verwenden zu können, muss das administrative SRS v1-Webportal auf jedem Front-End-Server von Skype for Business Server bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="8a97a-109">To use this feature, the SRS v1 Administrative Web Portal needs to be deployed on every Skype for Business Server Front End Server.</span></span> <span data-ttu-id="8a97a-110">Dieses Handbuch enthält Anweisungen für Administratoren, wie das Webportal zur Verwaltung von SRS installiert und konfiguriert wird.</span><span class="sxs-lookup"><span data-stu-id="8a97a-110">This guide provides instructions for administrators on how to install and configure the SRS Administrative Web Portal.</span></span> <span data-ttu-id="8a97a-111">Sie ist für Administratoren vorgesehen, die über Kenntnisse der Skype for Business Server-Verwaltung verfügen und über Administratorrechte verfügen, um die Skype for Business Server-Topologie zu ändern.</span><span class="sxs-lookup"><span data-stu-id="8a97a-111">It is intended for administrators who have knowledge of Skype for Business Server administration, and who have administrator user rights to modify the Skype for Business Server topology.</span></span>

<span data-ttu-id="8a97a-112">Nachdem das administrative SRS v1-Webportal auf dem Server bereitgestellt wurde, können Administratoren den Status SRS v1-Geräte überprüfen, indem Sie sich auf Ihren eigenen Computern oder Laptops bei der Website anmelden.</span><span class="sxs-lookup"><span data-stu-id="8a97a-112">After the SRS v1 Administrative Web Portal is deployed on the server, administrators can check the status SRS v1 devices by logging on to the site from their own computers or laptops.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="8a97a-113">Laden Sie das [Microsoft Skype Room Systems v1 Administrative Web-Portal für Skype for Business Server 2015](https://www.microsoft.com/en-us/download/details.aspx?id=46906)herunter.</span><span class="sxs-lookup"><span data-stu-id="8a97a-113">Download the [Microsoft Skype Room Systems v1 Administrative Web Portal for Skype for Business Server 2015](https://www.microsoft.com/en-us/download/details.aspx?id=46906).</span></span>

<span data-ttu-id="8a97a-114">In diesem Thema:</span><span class="sxs-lookup"><span data-stu-id="8a97a-114">In this topic:</span></span>

- [<span data-ttu-id="8a97a-115">Konfigurieren Sie Ihre Umgebung für das Webportal zur Verwaltung von SRS v1</span><span class="sxs-lookup"><span data-stu-id="8a97a-115">Configure your environment for the SRS v1 Administrative Web Portal</span></span>](room-system-v1-administrative-web-portal.md#Config_Env)

- [<span data-ttu-id="8a97a-116">Installieren Sie das Webportal zur Verwaltung von SRS v1</span><span class="sxs-lookup"><span data-stu-id="8a97a-116">Install the SRS v1 Administrative Web Portal</span></span>](room-system-v1-administrative-web-portal.md#Install_SRS)

- [<span data-ttu-id="8a97a-117">Verwenden Sie das Webportal zur Verwaltung von SRS</span><span class="sxs-lookup"><span data-stu-id="8a97a-117">Use the SRS Administrative Web Portal</span></span>](room-system-v1-administrative-web-portal.md#Use_Portal)

## <a name="configure-your-environment-for-the-srs-v1-administrative-web-portal"></a><span data-ttu-id="8a97a-118">Konfigurieren Sie Ihre Umgebung für das Webportal zur Verwaltung von SRS v1</span><span class="sxs-lookup"><span data-stu-id="8a97a-118">Configure your environment for the SRS v1 Administrative Web Portal</span></span>
<span data-ttu-id="8a97a-119"><a name="Config_Env"> </a></span><span class="sxs-lookup"><span data-stu-id="8a97a-119"></span></span>

<span data-ttu-id="8a97a-120">Zur Nutzung des Webportals für die Verwaltung des SRS v1 müssen Sie die folgenden Voraussetzungen installieren oder konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="8a97a-120">To use the SRS v1 Administrative Web Portal, you will need to install or configure the following prerequisites.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="8a97a-p104">Wenn für den Server sowohl Kerberos- als auch die NTLM-Authentifizerung konfiguriert wurde und SRS auf einem Computer ausgeführt wird, der nicht Teil der Domäne ist, schlägt die Kerberos-Authentifizierung fehl und dem Benutzer wird der SRS-Status im Verwaltungsportal nicht angezeigt. Sie können dieses Problem lösen, indem Sie entweder die NTLM-Authentifizierung bzw. die NTLM- und TLS-DSK-Authentifizierung (ohne Kerberos) konfigurieren oder mit dem SRS-Computer der Domäne beitreten.</span><span class="sxs-lookup"><span data-stu-id="8a97a-p104">If the server is configured with both Kerberos and NTLM authentication, and SRS is running on a computer that is not joined to the domain, Kerberos authentication will fail and the user will not see the status of SRS in the administrative portal. To resolve this issue, configure the server with NTLM authentication or both NTLM and TLS-DSK authentication (without Kerberos), or join the SRS computer to the domain.</span></span>

1. <span data-ttu-id="8a97a-123">Installieren Sie die kumulierten Updates für Skype for Business Server in der Skype for Business Server-Topologie.</span><span class="sxs-lookup"><span data-stu-id="8a97a-123">Install Skype for Business Server Cumulative Updates in the Skype for Business Server topology.</span></span>

    <span data-ttu-id="8a97a-124">Wenn Sie das Update erhalten oder sehen möchten, was darin enthalten ist, lesen Sie [Updates für Skype for Business Server 2015](https://support.microsoft.com/en-us/help/3061064/updates-for-skype-for-business-server-2015).</span><span class="sxs-lookup"><span data-stu-id="8a97a-124">To get the update or see what's included with it, see [Updates for Skype for Business Server 2015](https://support.microsoft.com/en-us/help/3061064/updates-for-skype-for-business-server-2015).</span></span>

2. <span data-ttu-id="8a97a-125">Erstellen Sie einen SIP-aktivierten Active Directory-Benutzer.</span><span class="sxs-lookup"><span data-stu-id="8a97a-125">Create a SIP-enabled Active Directory user.</span></span>

    <span data-ttu-id="8a97a-126">Das administrative Web Portal für SRS v1 verwendet diese Anmeldeinformationen, um Informationen von Skype for Business Server abzufragen.</span><span class="sxs-lookup"><span data-stu-id="8a97a-126">The SRS v1 Administrative Web Portal uses these credentials to query information from Skype for Business Server.</span></span> <span data-ttu-id="8a97a-127">Der in den Beispielen verwendete Benutzername lautet LRSApp.</span><span class="sxs-lookup"><span data-stu-id="8a97a-127">The username in the examples given is LRSApp.</span></span>

3. <span data-ttu-id="8a97a-128">Erstellen Sie eine Active Directory-Sicherheitsgruppe mit dem Namen LRSSupportAdminGroup.</span><span class="sxs-lookup"><span data-stu-id="8a97a-128">Create an Active Directory security group with name LRSSupportAdminGroup.</span></span>

    <span data-ttu-id="8a97a-p106">Erstellen Sie die Gruppe mit dem Gruppenbereich  Global  und dem Gruppentyp  Sicherheit . SIP-aktivierte Benutzer, die dieser Gruppe hinzugefügt werden, sind berechtigt, die Liste der Räume anzuzeigen und bestimmte Befehle auszuführen, wie das Speichern von Protokollen.</span><span class="sxs-lookup"><span data-stu-id="8a97a-p106">Create the group with Group Scope as Global and Group Type as Security. SIP enabled users who are added to this group will be authorized to see the list of rooms and execute certain commands, such as collecting logs.</span></span>

4. <span data-ttu-id="8a97a-131">Erstellen Sie eine Active Directory-Sicherheitsgruppe mit dem Namen LRSFullAccessAdminGroup. </span><span class="sxs-lookup"><span data-stu-id="8a97a-131">Create an Active Directory security group with name LRSFullAccessAdminGroup.</span></span>

    <span data-ttu-id="8a97a-p107">Erstellen Sie die Gruppe mit dem Gruppenbereich „Global“ und dem Gruppentyp „Sicherheit“. SIP-aktivierte Benutzer, die dieser Gruppe hinzugefügt werden, sind berechtigt, alle Funktionen des Verwaltungsportals für einen einzelnen Skype-Raum zu nutzen. Um Unterstützung für die Massenverwaltung von Skype-Räumen zu erhalten, finden Sie unter Schritt 5. </span><span class="sxs-lookup"><span data-stu-id="8a97a-p107">Create the group with Group Scope as Global and Group Type as Security.SIP enabled users who are added to this group are authorized to use all admin portal functionality on a single Skype room. To include support for bulk management of Skype rooms, refer to step 5.</span></span>

     ![Liste der Verwaltungsgruppen mit Sicherheitsgruppenrolle](../../media/LRS_LRSFullAccessAdminGroup.png)

5. <span data-ttu-id="8a97a-135">Erstellen Sie eine Active Directory-Sicherheitsgruppe mit dem Namen LRSPowerUserAdminsGroup.</span><span class="sxs-lookup"><span data-stu-id="8a97a-135">Create an Active Directory security group with name LRSPowerUserAdminsGroup.</span></span>

    <span data-ttu-id="8a97a-136">Erstellen Sie die Gruppe mit dem Gruppenbereich  Global  und dem Gruppentyp  Sicherheit .</span><span class="sxs-lookup"><span data-stu-id="8a97a-136">Create the group with Group Scope as Global and Group Type as Security.</span></span> <span data-ttu-id="8a97a-137">SIP-aktivierte Benutzer, die dieser Gruppe hinzugefügt werden, sind berechtigt, alle Funktionen des Administrator Portals einschließlich der Massenverwaltung von Skype for Business-Räumen zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="8a97a-137">SIP enabled users who are added to this group are authorized to use all admin portal functionality including bulk management of Skype for Business rooms.</span></span>

6. <span data-ttu-id="8a97a-138">Fügen Sie LRSFullAccessAdminGroup als Mitglied von LRSSupportAdminGroup hinzu.</span><span class="sxs-lookup"><span data-stu-id="8a97a-138">Add LRSFullAccessAdminGroup as a member of LRSSupportAdminGroup.</span></span>

     ![LRSSupportAdminGroup-Eigenschaftenmember (Seite)](../../media/LRS_Add_LRSSupportAdminGroup.png)

7. <span data-ttu-id="8a97a-140">Erstellen Sie einen SIP-aktivierten Active Directory-Benutzer mit dem Namen LRSSupport.</span><span class="sxs-lookup"><span data-stu-id="8a97a-140">Create a SIP enabled Active Directory user with name LRSSupport.</span></span> <span data-ttu-id="8a97a-141">Fügen Sie diesen Benutzer zu LRSSupportAdminGroup hinzu.</span><span class="sxs-lookup"><span data-stu-id="8a97a-141">Add this user to LRSSupportAdminGroup.</span></span>

     ![LRSSupportAdminGroup-Eigenschaftenmember (Seite)](../../media/LRS_Add_LRS_SIP_SupportUser.png)

8. <span data-ttu-id="8a97a-143">Installieren Sie [ASP.NET MVC 4 für Visual Studio 2010 SP1 und Visual Web Developer 2010 SP1](https://go.microsoft.com/fwlink/p/?LinkId=323967).</span><span class="sxs-lookup"><span data-stu-id="8a97a-143">Install [ASP.NET MVC 4 for Visual Studio 2010 SP1 and Visual Web Developer 2010 SP1](https://go.microsoft.com/fwlink/p/?LinkId=323967).</span></span>

## <a name="install-the-srs-v1-administrative-web-portal"></a><span data-ttu-id="8a97a-144">Installieren Sie das Webportal zur Verwaltung von SRS v1</span><span class="sxs-lookup"><span data-stu-id="8a97a-144">Install the SRS v1 Administrative Web Portal</span></span>
<span data-ttu-id="8a97a-145"><a name="Install_SRS"> </a></span><span class="sxs-lookup"><span data-stu-id="8a97a-145"></span></span>

<span data-ttu-id="8a97a-146">Laden Sie das [Microsoft Skype Room Systems v1 Administrative Web-Portal für Skype for Business Server 2015](https://www.microsoft.com/en-us/download/details.aspx?id=46906)herunter.</span><span class="sxs-lookup"><span data-stu-id="8a97a-146">Download the [Microsoft Skype Room Systems v1 Administrative Web Portal for Skype for Business Server 2015](https://www.microsoft.com/en-us/download/details.aspx?id=46906).</span></span>

<span data-ttu-id="8a97a-147">Wenn Sie das Webportal zur Verwaltung von SRS v1 installieren möchten, gehen Sie wie folgt vor.</span><span class="sxs-lookup"><span data-stu-id="8a97a-147">To install the SRS v1 Administrative Web Portal, use the following steps.</span></span>

1. <span data-ttu-id="8a97a-148">Konfigurieren Sie den Port für vertrauenswürdige Anwendungen, indem Sie das folgende Cmdlet in der Skype for Business Server-Verwaltungsshell ausführen:</span><span class="sxs-lookup"><span data-stu-id="8a97a-148">Configure the Trusted Application Port by running the following cmdlet in Skype for Business Server Management Shell:</span></span>

   ```
   Set-CsWebServer -Identity POOLFQDN -MeetingRoomAdminPortalInternalListeningPort 4456 -MeetingRoomAdminPortalExternalListeningPort 4457
   ```

2. <span data-ttu-id="8a97a-149">Installieren Sie das Besprechungsraum-Administratorportal. Laden Sie dazu **MeetingRoomPortalInstaller.msi** herunter, und führen Sie das Programm anschließend als Administrator aus.</span><span class="sxs-lookup"><span data-stu-id="8a97a-149">To install the Meeting Room Portal, download **MeetingRoomPortalInstaller.msi** and then run it as an administrator.</span></span>

3. <span data-ttu-id="8a97a-150">Öffnen Sie die Datei Web.config aus folgendem Speicherort:</span><span class="sxs-lookup"><span data-stu-id="8a97a-150">Open the Web.config file from the following location:</span></span>

    <span data-ttu-id="8a97a-151">%Program Files%\Skype for Business Server 2015\Web Components\Meeting Room Portal\Int\Handler</span><span class="sxs-lookup"><span data-stu-id="8a97a-151">%Program Files%\Skype for Business Server 2015\Web Components\Meeting Room Portal\Int\Handler</span></span>\

4. <span data-ttu-id="8a97a-152">Ändern Sie in der Datei Web. config die PortalUserName in den in Schritt 2 erstellten Benutzernamen unter dem Abschnitt "[Konfigurieren der Umgebung für das administrative Web-Portal für SRS v1](room-system-v1-administrative-web-portal.md#Config_Env)" (der empfohlene Name im Schritt lautet LRSApp):</span><span class="sxs-lookup"><span data-stu-id="8a97a-152">In the Web.Config file, change the PortalUserName to the username created in Step 2 under the section "[Configure your environment for the SRS v1 Administrative Web Portal](room-system-v1-administrative-web-portal.md#Config_Env)" (the recommended name in the step is LRSApp):</span></span>

    ```
    <add key="PortalUserName" value="sip:LRSApp@domain.com" />
    ```

5. <span data-ttu-id="8a97a-p110">Da das Webportal zur Verwaltung von SRS v1 eine vertrauenswürdige Anwendung ist, müssen Sie das Kennwort bei der Portalkonfiguration nicht angeben. Wenn für diesen Benutzer nicht die lokale Registrierungsstelle, sondern eine andere Registrierungsstelle verwendet wird, müssen Sie diese für den Benutzer angeben, indem Sie folgende Zeile in die Datei Web.Config einfügen: </span><span class="sxs-lookup"><span data-stu-id="8a97a-p110">Because the SRS v1 Admin Portal is a trusted application, you do not need to provide the password in the portal configuration. If this user is using a different registrar than local registrar, you need to specify the registrar for it by adding the following line in the Web.Config file:</span></span>

   ```
   <add key="PortalUserRegistrarFQDN" value="pool-xxxx.domain.com" />
   ```

6. <span data-ttu-id="8a97a-155">Wenn der verwendete Port nicht der Port 5061 ist, fügen Sie folgende Zeile in die Datei Web.Config ein: </span><span class="sxs-lookup"><span data-stu-id="8a97a-155">If the port used is other than 5061, add the following line in the Web.Config file:</span></span>

   ```
   <add key="PortalUserRegistrarPort" value="5061" />
   ```

### <a name="verify-installation-of-the-srs-administrative-web-portal"></a><span data-ttu-id="8a97a-156">Überprüfen Sie die Installation des Webportals zur Verwaltung von SRS</span><span class="sxs-lookup"><span data-stu-id="8a97a-156">Verify Installation of the SRS Administrative Web Portal</span></span>

<span data-ttu-id="8a97a-157">Wenn Sie die Installation des Webportals zur Verwaltung von SRS v1 überprüfen möchten, gehen Sie wie folgt vor.</span><span class="sxs-lookup"><span data-stu-id="8a97a-157">To verify installation of the SRS v1 Administrative Web Portal, do the following:</span></span>

1. <span data-ttu-id="8a97a-158">Navigieren Sie auf einem Front-End-Server zur folgenden URL:</span><span class="sxs-lookup"><span data-stu-id="8a97a-158">On a Front End server, browse to the following URL:</span></span>

    <span data-ttu-id="8a97a-159">https://\<FE-Server\>/LRS</span><span class="sxs-lookup"><span data-stu-id="8a97a-159">https://\<fe-server\>/lrs</span></span>

    <span data-ttu-id="8a97a-160">Sie sollten keine Fehler sehen (siehe folgende Abbildung):</span><span class="sxs-lookup"><span data-stu-id="8a97a-160">You should not see any errors, as shown in the following image:</span></span>

     ![Anmeldebildschirm für das Webportal zur Verwaltung des Lync-Raumsystems](../../media/LRS_AdminPortalSignIn.png)

2. <span data-ttu-id="8a97a-162">Wenn Sie keine Fehler sehen, versuchen Sie, über einen anderen Computer in der Topologie auf die folgende URL zuzugreifen:</span><span class="sxs-lookup"><span data-stu-id="8a97a-162">If you do not see any errors, try accessing the following URL from any other computer in the topology:</span></span>

    <span data-ttu-id="8a97a-163">https://\<FE-Server\>/LRS</span><span class="sxs-lookup"><span data-stu-id="8a97a-163">https://\<fe-server\>/lrs</span></span>

    <span data-ttu-id="8a97a-164">Wenn Sie auf die Seite zugreifen möchten, müssen Sie die DNS-Einträge hinzufügen, wie unter "[erforderliche DNS-Einträge für die automatische Client Anmeldung](https://go.microsoft.com/fwlink/p/?LinkId=318056)" beschrieben ist.</span><span class="sxs-lookup"><span data-stu-id="8a97a-164">To access the page, you will need to add the DNS records as described in "[Required DNS Records for Automatic Client Sign-In](https://go.microsoft.com/fwlink/p/?LinkId=318056)."</span></span>

## <a name="use-the-srs-administrative-web-portal"></a><span data-ttu-id="8a97a-165">Verwenden Sie das Webportal zur Verwaltung von SRS</span><span class="sxs-lookup"><span data-stu-id="8a97a-165">Use the SRS Administrative Web Portal</span></span>
<span data-ttu-id="8a97a-166"><a name="Use_Portal"> </a></span><span class="sxs-lookup"><span data-stu-id="8a97a-166"></span></span>

<span data-ttu-id="8a97a-167">Nach der Bereitstellung von SRS auf dem Server können Sie den Status aller SRS-Räume überprüfen, indem Sie sich von einem Browser beim Webportal für die Verwaltung von SRS v1 anmelden.</span><span class="sxs-lookup"><span data-stu-id="8a97a-167">After you deploy SRS on the server, you can check the status of all SRS rooms by signing into the SRS v1 Administrative Web Portal from a browser.</span></span>

### <a name="sign-in"></a><span data-ttu-id="8a97a-168">Anmelden</span><span class="sxs-lookup"><span data-stu-id="8a97a-168">Sign in</span></span>

1. <span data-ttu-id="8a97a-169">Navigieren Sie zu der folgenden URL:</span><span class="sxs-lookup"><span data-stu-id="8a97a-169">Browse to the following URL:</span></span>

    <span data-ttu-id="8a97a-170">https://\<FE-Server\>/LRS</span><span class="sxs-lookup"><span data-stu-id="8a97a-170">https://\<fe-server\>/lrs</span></span>

2. <span data-ttu-id="8a97a-171">Geben Sie die Anmeldeinformationen für das LRSSupport-Konto oder ein Konto ein, das der Sicherheitsgruppe LRSSupportAdminGroup hinzugefügt wurde.</span><span class="sxs-lookup"><span data-stu-id="8a97a-171">Enter the credentials for the LRSSupport account or an account that was added to the LRSSupportAdminGroup security group.</span></span>

![Anmeldebildschirm für das Webportal zur Verwaltung des Lync-Raumsystems](../../media/LRS_AdminPortalSignIn.png)

### <a name="srs-administrative-web-portal-summary-page"></a><span data-ttu-id="8a97a-173">Übersichtsseite für das Webportal für die Verwaltung von SRS</span><span class="sxs-lookup"><span data-stu-id="8a97a-173">SRS Administrative Web Portal Summary Page</span></span>

<span data-ttu-id="8a97a-174">Die Übersichtsseite stellt die folgenden Informationen für alle SRS-Räume bereit, die auf dem Server bereitgestellt werden:</span><span class="sxs-lookup"><span data-stu-id="8a97a-174">The summary page provides the following information for all of the SRS rooms deployed on the server:</span></span>

- <span data-ttu-id="8a97a-175">- **Tag** Der benutzerdefinierte Name, den der Administrator dem Chatroom übergibt.</span><span class="sxs-lookup"><span data-stu-id="8a97a-175">**Tag** The custom name that the administrator gives to the room.</span></span> <span data-ttu-id="8a97a-176">Das Tag kann im Portal festgelegt werden, indem Sie auf den Raumnamen klicken.</span><span class="sxs-lookup"><span data-stu-id="8a97a-176">The Tag can be set in the portal by clicking on the room name.</span></span>

- <span data-ttu-id="8a97a-177">**Gesundheit** Der Integritätsstatus des Raums, der aus dem Aggregat Integritätsstatus des Raums abgeleitet wird, der im Abschnitt "Gesundheit" auf der Seite "Raumeinstellungen" angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="8a97a-177">**Health** The health status of the room, which is derived from the Aggregate Health status of the room, which is shown under the Health section of the Room Settings page.</span></span>

- <span data-ttu-id="8a97a-178">**Nächste Besprechung** Das Datum und die Uhrzeit, zu der die nächste Besprechung geplant ist.</span><span class="sxs-lookup"><span data-stu-id="8a97a-178">**Next Meeting** The date and time the next meeting is scheduled.</span></span>

- <span data-ttu-id="8a97a-179">**SRS-Version, Hersteller, Modell** Diese Werte werden in SRS voreingestellt.</span><span class="sxs-lookup"><span data-stu-id="8a97a-179">**SRS Version, Manufacturer, Model** These values are preset in SRS.</span></span> <span data-ttu-id="8a97a-180">Je nach Hersteller können diese Felder auch leer sein.</span><span class="sxs-lookup"><span data-stu-id="8a97a-180">Depending on the manufacturer, these fields might be left blank.</span></span>

- <span data-ttu-id="8a97a-181">**Letzte Aktualisierung** Zeigt den Zeitpunkt an, zu dem die Webseite zuletzt aktualisiert wurde.</span><span class="sxs-lookup"><span data-stu-id="8a97a-181">**Last Refresh** Displays the last time the web page was refreshed.</span></span>

![Zusammenfassungsansicht für das Webportal zur Verwaltung des Lync-Raumsystems](../../media/LRS_AdminPortal_Summary_view.png)

> [!NOTE]
> <span data-ttu-id="8a97a-183">Wenn Sie zur LRSPowerUserAdminsGroup-Sicherheitsgruppe gehören, wird das Menü Massenverwaltung nur angezeigt.</span><span class="sxs-lookup"><span data-stu-id="8a97a-183">You will only see the Bulk Management menu if you are part of the LRSPowerUserAdminsGroup security group.</span></span>

### <a name="srs-room-information"></a><span data-ttu-id="8a97a-184">SRS-Rauminformationen</span><span class="sxs-lookup"><span data-stu-id="8a97a-184">SRS Room Information</span></span>

<span data-ttu-id="8a97a-p113">Im Abschnitt zu den Rauminformationen des Portals können Sie individuelle SRS-Räume anzeigen und konfigurieren. Hier finden Sie vier Abschnitte zu Einstellungen, Details, Protokollierung und Integrität.</span><span class="sxs-lookup"><span data-stu-id="8a97a-p113">The Room Info section of the portal allows you to view and configure individual SRS rooms. It contains four sections: Settings, Details, Logging, and Health.</span></span>

#### <a name="settings"></a><span data-ttu-id="8a97a-187">Einstellungen</span><span class="sxs-lookup"><span data-stu-id="8a97a-187">Settings</span></span>

<span data-ttu-id="8a97a-p114">Im Abschnitt zu den Einstellungen können Sie das Kennwort, das Tag für den Raum und die Standardlautstärke für den Raum festlegen. Wenn Sie diese Einstellungen konfigurieren, werden die Änderungen erst repliziert, nachdem Sie die SRS-Konsole neu gestartet haben. Ihnen werden nur die System-Updates-Einstellungen für SRS-Geräte angezeigt, die Version 15.12 oder höher verwenden.</span><span class="sxs-lookup"><span data-stu-id="8a97a-p114">In the Settings section, you can set the password, room tag, and default volume levels for the room. If you configure these settings, the changes are replicated only after you restart the SRS console. You will only see System Updates settings for SRS devices using release 15.12 and later.</span></span>

![Einstellungen für das Webportal zur Verwaltung des Lync-Raumsystems](../../media/LRS_AdminPortal_RoomInfoSettings.png)

#### <a name="details"></a><span data-ttu-id="8a97a-192">Details</span><span class="sxs-lookup"><span data-stu-id="8a97a-192">Details</span></span>

<span data-ttu-id="8a97a-193">Der Abschnitt Details enthält eine schreibgeschützte Zusammenfassung der Einstellungen des SRS-Raums, einschließlich: die Uhrzeit der letzten Aktualisierung. nächste Besprechung; Letzte Updates, Wartung und Kalibrierung; Standardeinstellungen für Lautsprecher, Mikrofon und Klingelton Version SIP-URI; Anzahl der Bildschirme und Details zu jedem Bildschirm; Status und Aktivität.</span><span class="sxs-lookup"><span data-stu-id="8a97a-193">The Details section provides a read-only summary of the SRS room's settings, including: the time of last refresh; next meeting; last updates, maintenance and calibration; default speaker, mic, and ringer settings; version; SIP URI; number of screens and details about each screen; status, and activity.</span></span>

![Detailansicht für das Webportal zur Verwaltung des Lync-Raumsystems](../../media/LRS_AdminPortal_Detail_view.png)

#### <a name="troubleshooting"></a><span data-ttu-id="8a97a-195">Problembehandlung</span><span class="sxs-lookup"><span data-stu-id="8a97a-195">Troubleshooting</span></span>

<span data-ttu-id="8a97a-p115">Im Abschnitt zur Problembehandlung können Sie remote Protokolle erfassen und sie an einem angegebenen Standort speichern. Sie können außerdem die SRS-Konsole (SRS-Benutzeroberfläche) oder das gesamte System neu starten. Stellen Sie zur Erfassung von Protokollen einen Ordnerpfad im angegebenen Format bereit und vergewissern Sie sich, dass der Ordner über Schreibberechtigungen für das SRS-Computerkonto verfügt. Bei einer sehr umfangreichen Protokollgröße kann es bis zu 5 Minuten dauern, bis der Vorgang zur Erfassung der Protokolle abgeschlossen ist. Sie erhalten den aktuellen Status, wenn Sie die Seite aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="8a97a-p115">The Troubleshooting section can be used to remotely collect logs and save them to a specified location. You can also restart the SRS console (SRS user interface) or restart the entire system. To collect logs, provide a folder path in the specified format and make sure that the folder has write permissions given to the SRS machine account. If the log size is too big, it can take up to 5 minutes to finish collecting logs. Refreshing the page will give you the latest status.</span></span>

#### <a name="health"></a><span data-ttu-id="8a97a-201">Integrität</span><span class="sxs-lookup"><span data-stu-id="8a97a-201">Health</span></span>

<span data-ttu-id="8a97a-202">Der Abschnitt "Gesundheit" bietet eine visuelle Anzeige des Zustands der Skype for Business-Server Verbindung, des Audiogeräts, des Videogeräts, des Stabilitäts Status und des Bildschirmgeräts.</span><span class="sxs-lookup"><span data-stu-id="8a97a-202">The Health section gives a visual indication of the health of the Skype for Business Server connection, audio device, video device, resiliency state, and screen device.</span></span>

![Integrität für das Webportal zur Verwaltung des Lync-Raumsystems](../../media/LRS_AdminPortal_RoomInfoHealth.png)

### <a name="additional-notes-about-the-administrative-web-portal"></a><span data-ttu-id="8a97a-204">Weitere Hinweise zum Webportal für die Verwaltung</span><span class="sxs-lookup"><span data-stu-id="8a97a-204">Additional Notes about the Administrative Web Portal</span></span>

> [!NOTE]
>  <span data-ttu-id="8a97a-205">Das Festlegen von Änderungen wird erst nach einem Neustart des SRS-Systems übernommen. #a0 Wenn das LRSApp-Kontokennwort abläuft, können Sie den Status der Räume nicht sehen.</span><span class="sxs-lookup"><span data-stu-id="8a97a-205">Setting changes are applied only after the SRS system is restarted.>  If the LRSApp account password expires, you will not be able to see the status of the rooms.</span></span> <span data-ttu-id="8a97a-206">Konfigurieren Sie das Kennwort für das LRSAppuser-Konto so, dass es nie abläuft, oder aktualisieren Sie das Kennwort, wenn es nahezu abgelaufen ist. #a0 das SRS-Verwaltungs Webportal wird nur für lokale Bereitstellungen unterstützt.</span><span class="sxs-lookup"><span data-stu-id="8a97a-206">Configure the LRSAppuser account password so that it never expires, or be sure to update the password when it is near expiration.>  The SRS administrative web portal is supported for on-premises deployments only.</span></span>

### <a name="bulk-management"></a><span data-ttu-id="8a97a-207">Massenverwaltung </span><span class="sxs-lookup"><span data-stu-id="8a97a-207">Bulk management</span></span>

<span data-ttu-id="8a97a-208">Die Massenverwaltung von SRS-Räumen ist eine Funktion, die für fortgeschrittene IT-Administratoren entwickelt wurde, um den Workflow zu vereinfachen und durch ein zeitsparendes praktisches Tool die Remote-Verwaltung mehrerer Räume in Form eines Massenvorgangs zu ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="8a97a-208">Bulk management of SRS rooms is a feature designed for advanced IT administrators, to simplify their workflow, and enable them with a time-saving convenient tool to remotely manage multiple rooms in a bulk fashion.</span></span>

<span data-ttu-id="8a97a-209">Um diese Funktion anzuzeigen, muss der Benutzer als ein Mitglied der besonderen Sicherheitsgruppe **LRSPowerUserAdminsGroup** eingerichtet sein.  </span><span class="sxs-lookup"><span data-stu-id="8a97a-209">In order to see this functionality, the user need to be provisioned as a member of the special security group, **LRSPowerUserAdminsGroup**.</span></span>

<span data-ttu-id="8a97a-p117">Die Anzahl der für die Massenverwaltung auswählbaren SRS-Räume ist nicht begrenzt. Sie können jedoch immer nur einen Massenverwaltungsvorgang durchführen.</span><span class="sxs-lookup"><span data-stu-id="8a97a-p117">There is no limit to the number of SRS rooms you can select for bulk management. However, you can perform only one bulk management operation at a time.</span></span>

<span data-ttu-id="8a97a-212">Wählen Sie zum Durchführen eines Massenverwaltungsvorgangs die Räume, die Sie überwachen möchten, und klicken sie auf das Massenverwaltungsmenü. </span><span class="sxs-lookup"><span data-stu-id="8a97a-212">To perform a bulk management operation, select the rooms you want to monitor, and click on the Bulk management menu.</span></span>

### <a name="frequently-asked-questions"></a><span data-ttu-id="8a97a-213">Häufig gestellte Fragen</span><span class="sxs-lookup"><span data-stu-id="8a97a-213">Frequently asked questions</span></span>

#### <a name="why-cant-i-sign-in-to-the-administrative-web-portal"></a><span data-ttu-id="8a97a-214">Warum kann ich mich nicht beim administrativen Webportal anmelden?</span><span class="sxs-lookup"><span data-stu-id="8a97a-214">Why can't I sign in to the administrative web portal?</span></span>

<span data-ttu-id="8a97a-215">Wenn Sie öffnen https://localhost/lrs, können Sie die Anmeldeseite sehen, aber wenn Sie Ihre Anmeldeinformationen eingeben, können Sie sich nicht anmelden.</span><span class="sxs-lookup"><span data-stu-id="8a97a-215">When you open https://localhost/lrs, you will be able to see the sign in page, but when you type in your credentials, you cannot sign in.</span></span> <span data-ttu-id="8a97a-216">In diesem Fall müssen Sie die Anmeldung https://FQDNofFEserver/SRS beim Administrator-Webportal öffnen.</span><span class="sxs-lookup"><span data-stu-id="8a97a-216">In this case, you must open https://FQDNofFEserver/SRS to sign in to the administrative web portal.</span></span>

#### <a name="why-cant-i-see-srs-v1-in-the-administrative-web-portal"></a><span data-ttu-id="8a97a-217">Warum kann ich SRS v1 nicht im Administrator-Webportal sehen?</span><span class="sxs-lookup"><span data-stu-id="8a97a-217">Why can't I see SRS v1 in the administrative web portal?</span></span>

- <span data-ttu-id="8a97a-218">Stellen Sie sicher, dass Sie SRS-Konten in Ihrer Bereitstellung haben und diese nach den Empfehlungen für die Bereitstellung des Webportals für die SRS-Verwaltung erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="8a97a-218">Make sure you have SRS accounts in your deployment and that they are created according to the SRS Administrative Web Portal deployment recommendations.</span></span> <span data-ttu-id="8a97a-219">Stellen Sie sicher, dass die SRS-Konten mithilfe von enable-CsMeetingRoom, nicht enable-CsUser, auf dem Skype for Business-Server bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="8a97a-219">Make sure the SRS accounts are provisioned using Enable-CsMeetingRoom, not Enable-CsUser, on the Skype for Business Server.</span></span>

- <span data-ttu-id="8a97a-220">Wenn Sie SRS-Konten erstellt haben und die Konten im administrativen Webportal nicht sehen können, sammeln Sie die Serverprotokolle mithilfe des Skype for Business Server-Protokollierungstools, wobei die **MeetingPortal** -Komponente ausgewählt ist, und senden Sie Sie dann an Ihren SRS-Support Kontakt.</span><span class="sxs-lookup"><span data-stu-id="8a97a-220">If you have created SRS accounts and cannot see the accounts in administrative web portal, collect the server logs by using the Skype for Business Server Logging tool with the **MeetingPortal** component selected, and then send them to your SRS support contact.</span></span>

- <span data-ttu-id="8a97a-p120">Wenn Sie SRS-Konten erstellt haben und die Konten im Webportal für die Verwaltung nicht sehen können, erfassen Sie die Clientprotokolle unter Verwendung von Fiddler, kopieren Sie das Konsolenprotokoll aus den Browserentwicklungstools und senden Sie diese dann an Ihren SRS-Supportkontakt. Sie können außerdem den Wert für die Verfolgungsstufe in der Datei Web.Confi ändern, um ein ausführliches Protokoll zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="8a97a-p120">If you have created SRS accounts and cannot see the accounts in administrative web portal, collect the client logs using Fiddler, and also copy the console log from the browser development tools, and then send them to your SRS support contact. You can also modify the trace level value in the Web.config to get a more detailed log.</span></span>

  ```
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

#### <a name="why-cant-i-see-the-status-of-srs-in-the-administrative-web-portal"></a><span data-ttu-id="8a97a-223">Warum wird der Status von SRS im Administrator-Webportal nicht angezeigt?</span><span class="sxs-lookup"><span data-stu-id="8a97a-223">Why can't I see the status of SRS in the administrative web portal?</span></span>

- <span data-ttu-id="8a97a-224">Stellen Sie sicher, dass für das LRSApp-Benutzerkonto SIP aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="8a97a-224">Make sure that the LRSApp user account is SIP-enabled.</span></span>

- <span data-ttu-id="8a97a-225">Wenn weiterhin Probleme auftreten, sammeln Sie die Datei **Trace. log** im SRS-System von D:\Tracing\LRSAdminLogs\, , und senden Sie Sie dann an Ihren SRS-Support Kontakt.</span><span class="sxs-lookup"><span data-stu-id="8a97a-225">If you are still having issues, collect the **Trace.log** file in the SRS system from D:\Tracing\LRSAdminLogs\, and then send it to your SRS support contact.</span></span>

#### <a name="why-cant-i-see-the-bulk-management-menus-for-srs-in-the-administrative-web-portal"></a><span data-ttu-id="8a97a-226">Warum werden die Menüs für die Massenverwaltung für SRS im administrativen Webportal nicht angezeigt?</span><span class="sxs-lookup"><span data-stu-id="8a97a-226">Why can't I see the bulk management menus for SRS in the administrative web portal?</span></span>

<span data-ttu-id="8a97a-227">Stellen Sie sicher, dass das LRSApp-Benutzerkonto SIP-fähig ist und Teil der LRSPowerUserAdminsGroup-Sicherheitsgruppe ist.</span><span class="sxs-lookup"><span data-stu-id="8a97a-227">Make sure that the LRSApp user account is SIP-enabled, and is part of the LRSPowerUserAdminsGroup security group.</span></span>

#### <a name="does-the-srs-v1-administrative-web-portal-work-with-microsoft-teams-rooms"></a><span data-ttu-id="8a97a-228">Funktioniert das administrative SRS v1-Webportal mit Microsoft Teams-Räumen?</span><span class="sxs-lookup"><span data-stu-id="8a97a-228">Does the SRS v1 administrative web portal work with Microsoft Teams Rooms?</span></span>

<span data-ttu-id="8a97a-229">Nein.</span><span class="sxs-lookup"><span data-stu-id="8a97a-229">No.</span></span>


