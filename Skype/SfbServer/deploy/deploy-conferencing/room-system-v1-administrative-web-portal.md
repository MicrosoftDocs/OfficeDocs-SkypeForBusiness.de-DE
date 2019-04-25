---
title: Bereitstellen von SRS v1 Administrative Webportal in Skype für Business Server
ms.reviewer: ''
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 81822efa-2100-4017-a470-8a5b98c49522
ms.collection: M365-voice
description: Die Skype für Server Skype Raum Geschäftssystemen v1 (SRS v1, früher bekannt als Lync Raum System) Administrative Webportal ist ein Webportal, mit denen Organisationen können der Konferenzräume Skype Raum Systeme verwalten. Administratoren können dem SRS v1 Administrative Webportal Gerät Zustand, beispielsweise zu überwachen, durch die Überwachung der a/v-Geräte verwenden. Mit diesem Portal können Administratoren über Remoteverbindungen Diagnoseinformationen sammeln, um die Konferenzraumintegrität zu überwachen.
ms.openlocfilehash: b616084016a3b660f4af5bcd3bda6926dfc7e286
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "32226211"
---
# <a name="deploy-srs-v1-administrative-web-portal-in-skype-for-business-server"></a><span data-ttu-id="27816-105">Bereitstellen von SRS v1 Administrative Webportal in Skype für Business Server</span><span class="sxs-lookup"><span data-stu-id="27816-105">Deploy SRS v1 Administrative Web Portal in Skype for Business Server</span></span>

<span data-ttu-id="27816-106">Die Skype für Server Skype Raum Geschäftssystemen v1 (SRS v1, früher bekannt als Lync Raum System) Administrative Webportal ist ein Webportal, mit denen Organisationen können der Konferenzräume Skype Raum Systeme verwalten.</span><span class="sxs-lookup"><span data-stu-id="27816-106">The Skype for Business Server Skype Room Systems v1 (SRS v1, formerly known as Lync Room System) Administrative Web Portal is a web portal that organizations can use to maintain their Skype Room Systems conference rooms.</span></span> <span data-ttu-id="27816-107">Administratoren können dem SRS v1 Administrative Webportal Gerät Zustand, beispielsweise zu überwachen, durch die Überwachung der a/v-Geräte verwenden.</span><span class="sxs-lookup"><span data-stu-id="27816-107">Administrators can use the SRS v1 Administrative Web Portal to monitor device health, for example by monitoring audio/video devices.</span></span> <span data-ttu-id="27816-108">Mit diesem Portal können Administratoren über Remoteverbindungen Diagnoseinformationen sammeln, um die Konferenzraumintegrität zu überwachen.</span><span class="sxs-lookup"><span data-stu-id="27816-108">With this portal, administrators can remotely collect diagnostic information to monitor conference room health.</span></span>

<span data-ttu-id="27816-109">Um dieses Feature verwenden können, muss dem SRS v1 Administrative Webportal auf jedem Skype für Business Server-Front-End-Server bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="27816-109">To use this feature, the SRS v1 Administrative Web Portal needs to be deployed on every Skype for Business Server Front End Server.</span></span> <span data-ttu-id="27816-110">Dieses Handbuch enthält Anweisungen für Administratoren, wie das Webportal zur Verwaltung von SRS installiert und konfiguriert wird.</span><span class="sxs-lookup"><span data-stu-id="27816-110">This guide provides instructions for administrators on how to install and configure the SRS Administrative Web Portal.</span></span> <span data-ttu-id="27816-111">Es ist für Administratoren vorgesehen, die Skype-Kenntnisse für die Verwaltung der Business Server besitzen und über Administratorrechte verfügen, um die Skype für Business Server-Topologie ändern verfügen.</span><span class="sxs-lookup"><span data-stu-id="27816-111">It is intended for administrators who have knowledge of Skype for Business Server administration, and who have administrator user rights to modify the Skype for Business Server topology.</span></span>

<span data-ttu-id="27816-112">Nach der SRS v1, den administrativen Webportal auf dem Server bereitgestellt wird, können Administratoren von ihren eigenen Computern oder Laptops an der Website anmelden, um den Status SRS v1-Geräten überprüfen.</span><span class="sxs-lookup"><span data-stu-id="27816-112">After the SRS v1 Administrative Web Portal is deployed on the server, administrators can check the status SRS v1 devices by logging on to the site from their own computers or laptops.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="27816-113">Laden Sie das [Microsoft Skype Raum Systeme v1 Administrative Webportal für Skype für Business Server 2015](https://www.microsoft.com/en-us/download/details.aspx?id=46906).</span><span class="sxs-lookup"><span data-stu-id="27816-113">Download the [Microsoft Skype Room Systems v1 Administrative Web Portal for Skype for Business Server 2015](https://www.microsoft.com/en-us/download/details.aspx?id=46906).</span></span>

<span data-ttu-id="27816-114">In diesem Thema:</span><span class="sxs-lookup"><span data-stu-id="27816-114">In this topic:</span></span>

- [<span data-ttu-id="27816-115">Konfigurieren Sie Ihre Umgebung für das Webportal zur Verwaltung von SRS v1</span><span class="sxs-lookup"><span data-stu-id="27816-115">Configure your environment for the SRS v1 Administrative Web Portal</span></span>](room-system-v1-administrative-web-portal.md#Config_Env)

- [<span data-ttu-id="27816-116">Installieren Sie das Webportal zur Verwaltung von SRS v1</span><span class="sxs-lookup"><span data-stu-id="27816-116">Install the SRS v1 Administrative Web Portal</span></span>](room-system-v1-administrative-web-portal.md#Install_SRS)

- [<span data-ttu-id="27816-117">Verwenden Sie das Webportal zur Verwaltung von SRS</span><span class="sxs-lookup"><span data-stu-id="27816-117">Use the SRS Administrative Web Portal</span></span>](room-system-v1-administrative-web-portal.md#Use_Portal)

## <a name="configure-your-environment-for-the-srs-v1-administrative-web-portal"></a><span data-ttu-id="27816-118">Konfigurieren Sie Ihre Umgebung für das Webportal zur Verwaltung von SRS v1</span><span class="sxs-lookup"><span data-stu-id="27816-118">Configure your environment for the SRS v1 Administrative Web Portal</span></span>
<span data-ttu-id="27816-119"><a name="Config_Env"> </a></span><span class="sxs-lookup"><span data-stu-id="27816-119"></span></span>

<span data-ttu-id="27816-120">Zur Nutzung des Webportals für die Verwaltung des SRS v1 müssen Sie die folgenden Voraussetzungen installieren oder konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="27816-120">To use the SRS v1 Administrative Web Portal, you will need to install or configure the following prerequisites.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="27816-p104">Wenn für den Server sowohl Kerberos- als auch die NTLM-Authentifizerung konfiguriert wurde und SRS auf einem Computer ausgeführt wird, der nicht Teil der Domäne ist, schlägt die Kerberos-Authentifizierung fehl und dem Benutzer wird der SRS-Status im Verwaltungsportal nicht angezeigt. Sie können dieses Problem lösen, indem Sie entweder die NTLM-Authentifizierung bzw. die NTLM- und TLS-DSK-Authentifizierung (ohne Kerberos) konfigurieren oder mit dem SRS-Computer der Domäne beitreten.</span><span class="sxs-lookup"><span data-stu-id="27816-p104">If the server is configured with both Kerberos and NTLM authentication, and SRS is running on a computer that is not joined to the domain, Kerberos authentication will fail and the user will not see the status of SRS in the administrative portal. To resolve this issue, configure the server with NTLM authentication or both NTLM and TLS-DSK authentication (without Kerberos), or join the SRS computer to the domain.</span></span>

1. <span data-ttu-id="27816-123">Installieren Sie Skype für Business Server kumulativen Updates in der Skype für Business Server-Topologie.</span><span class="sxs-lookup"><span data-stu-id="27816-123">Install Skype for Business Server Cumulative Updates in the Skype for Business Server topology.</span></span>

    <span data-ttu-id="27816-124">Um das Update oder Umfang mit angezeigt wird, finden Sie unter [Updates für Skype für Business Server 2015](https://support.microsoft.com/en-us/help/3061064/updates-for-skype-for-business-server-2015).</span><span class="sxs-lookup"><span data-stu-id="27816-124">To get the update or see what's included with it, see [Updates for Skype for Business Server 2015](https://support.microsoft.com/en-us/help/3061064/updates-for-skype-for-business-server-2015).</span></span>

2. <span data-ttu-id="27816-125">Erstellen Sie einen SIP-aktivierten Active Directory-Benutzer.</span><span class="sxs-lookup"><span data-stu-id="27816-125">Create a SIP-enabled Active Directory user.</span></span>

    <span data-ttu-id="27816-126">Der SRS v1 Administrative Webportal verwendet diese Anmeldeinformationen zur Abfrage von Informationen von Skype für Business Server.</span><span class="sxs-lookup"><span data-stu-id="27816-126">The SRS v1 Administrative Web Portal uses these credentials to query information from Skype for Business Server.</span></span> <span data-ttu-id="27816-127">Der in den Beispielen verwendete Benutzername lautet LRSApp.</span><span class="sxs-lookup"><span data-stu-id="27816-127">The username in the examples given is LRSApp.</span></span>

3. <span data-ttu-id="27816-128">Erstellen Sie eine Active Directory-Sicherheitsgruppe mit dem Namen LRSSupportAdminGroup.</span><span class="sxs-lookup"><span data-stu-id="27816-128">Create an Active Directory security group with name LRSSupportAdminGroup.</span></span>

    <span data-ttu-id="27816-p106">Erstellen Sie die Gruppe mit dem Gruppenbereich  Global  und dem Gruppentyp  Sicherheit . SIP-aktivierte Benutzer, die dieser Gruppe hinzugefügt werden, sind berechtigt, die Liste der Räume anzuzeigen und bestimmte Befehle auszuführen, wie das Speichern von Protokollen.</span><span class="sxs-lookup"><span data-stu-id="27816-p106">Create the group with Group Scope as Global and Group Type as Security. SIP enabled users who are added to this group will be authorized to see the list of rooms and execute certain commands, such as collecting logs.</span></span>

4. <span data-ttu-id="27816-131">Erstellen Sie eine Active Directory-Sicherheitsgruppe mit dem Namen LRSFullAccessAdminGroup. </span><span class="sxs-lookup"><span data-stu-id="27816-131">Create an Active Directory security group with name LRSFullAccessAdminGroup.</span></span>

    <span data-ttu-id="27816-p107">Erstellen Sie die Gruppe mit dem Gruppenbereich „Global“ und dem Gruppentyp „Sicherheit“. SIP-aktivierte Benutzer, die dieser Gruppe hinzugefügt werden, sind berechtigt, alle Funktionen des Verwaltungsportals für einen einzelnen Skype-Raum zu nutzen. Um Unterstützung für die Massenverwaltung von Skype-Räumen zu erhalten, finden Sie unter Schritt 5. </span><span class="sxs-lookup"><span data-stu-id="27816-p107">Create the group with Group Scope as Global and Group Type as Security.SIP enabled users who are added to this group are authorized to use all admin portal functionality on a single Skype room. To include support for bulk management of Skype rooms, refer to step 5.</span></span>

     ![Liste der Verwaltungsgruppen mit Sicherheitsgruppenrolle](../../media/LRS_LRSFullAccessAdminGroup.png)

5. <span data-ttu-id="27816-135">Erstellen Sie eine Active Directory-Sicherheitsgruppe mit dem Namen LRSPowerUserAdminsGroup.</span><span class="sxs-lookup"><span data-stu-id="27816-135">Create an Active Directory security group with name LRSPowerUserAdminsGroup.</span></span>

    <span data-ttu-id="27816-136">Erstellen Sie die Gruppe mit dem Gruppenbereich  Global  und dem Gruppentyp  Sicherheit .</span><span class="sxs-lookup"><span data-stu-id="27816-136">Create the group with Group Scope as Global and Group Type as Security.</span></span> <span data-ttu-id="27816-137">SIP-aktivierten Benutzer, die dieser Gruppe hinzugefügt werden alle einschließlich Massen Verwaltung von Skype für Räume Business Portal Admin-Funktionen verwenden dürfen.</span><span class="sxs-lookup"><span data-stu-id="27816-137">SIP enabled users who are added to this group are authorized to use all admin portal functionality including bulk management of Skype for Business rooms.</span></span>

6. <span data-ttu-id="27816-138">Fügen Sie als Mitglied der LRSSupportAdminGroup LRSFullAccessAdminGroup hinzu.</span><span class="sxs-lookup"><span data-stu-id="27816-138">Add LRSFullAccessAdminGroup as a member of LRSSupportAdminGroup.</span></span>

     ![LRSSupportAdminGroup-Eigenschaftenmember (Seite)](../../media/LRS_Add_LRSSupportAdminGroup.png)

7. <span data-ttu-id="27816-140">Erstellen Sie einen SIP-aktivierten Active Directory-Benutzer mit dem Namen LRSSupport.</span><span class="sxs-lookup"><span data-stu-id="27816-140">Create a SIP enabled Active Directory user with name LRSSupport.</span></span> <span data-ttu-id="27816-141">Fügen Sie diesen Benutzer zu LRSSupportAdminGroup hinzu.</span><span class="sxs-lookup"><span data-stu-id="27816-141">Add this user to LRSSupportAdminGroup.</span></span>

     ![LRSSupportAdminGroup-Eigenschaftenmember (Seite)](../../media/LRS_Add_LRS_SIP_SupportUser.png)

8. <span data-ttu-id="27816-143">Installieren Sie [ASP.NET MVC 4 für Visual Studio 2010 SP1 und Visual Web Developer 2010 SP1](https://go.microsoft.com/fwlink/p/?LinkId=323967).</span><span class="sxs-lookup"><span data-stu-id="27816-143">Install [ASP.NET MVC 4 for Visual Studio 2010 SP1 and Visual Web Developer 2010 SP1](https://go.microsoft.com/fwlink/p/?LinkId=323967).</span></span>

## <a name="install-the-srs-v1-administrative-web-portal"></a><span data-ttu-id="27816-144">Installieren Sie das Webportal zur Verwaltung von SRS v1</span><span class="sxs-lookup"><span data-stu-id="27816-144">Install the SRS v1 Administrative Web Portal</span></span>
<span data-ttu-id="27816-145"><a name="Install_SRS"> </a></span><span class="sxs-lookup"><span data-stu-id="27816-145"></span></span>

<span data-ttu-id="27816-146">Laden Sie das [Microsoft Skype Raum Systeme v1 Administrative Webportal für Skype für Business Server 2015](https://www.microsoft.com/en-us/download/details.aspx?id=46906).</span><span class="sxs-lookup"><span data-stu-id="27816-146">Download the [Microsoft Skype Room Systems v1 Administrative Web Portal for Skype for Business Server 2015](https://www.microsoft.com/en-us/download/details.aspx?id=46906).</span></span>

<span data-ttu-id="27816-147">Wenn Sie das Webportal zur Verwaltung von SRS v1 installieren möchten, gehen Sie wie folgt vor.</span><span class="sxs-lookup"><span data-stu-id="27816-147">To install the SRS v1 Administrative Web Portal, use the following steps.</span></span>

1. <span data-ttu-id="27816-148">Konfigurieren Sie die vertrauenswürdige Anwendung Port durch das folgende Cmdlet in Skype für Business Server-Verwaltungsshell ausführen:</span><span class="sxs-lookup"><span data-stu-id="27816-148">Configure the Trusted Application Port by running the following cmdlet in Skype for Business Server Management Shell:</span></span>

   ```
   Set-CsWebServer -Identity POOLFQDN -MeetingRoomAdminPortalInternalListeningPort 4456 -MeetingRoomAdminPortalExternalListeningPort 4457
   ```

2. <span data-ttu-id="27816-149">Installieren Sie das Besprechungsraum-Administratorportal. Laden Sie dazu **MeetingRoomPortalInstaller.msi** herunter, und führen Sie das Programm anschließend als Administrator aus.</span><span class="sxs-lookup"><span data-stu-id="27816-149">To install the Meeting Room Portal, download **MeetingRoomPortalInstaller.msi** and then run it as an administrator.</span></span>

3. <span data-ttu-id="27816-150">Öffnen Sie die Datei Web.config aus folgendem Speicherort:</span><span class="sxs-lookup"><span data-stu-id="27816-150">Open the Web.config file from the following location:</span></span>

    <span data-ttu-id="27816-151">%Program Files%\Skype for Business Server 2015\Web Components\Meeting Room Portal\Int\Handler\\</span><span class="sxs-lookup"><span data-stu-id="27816-151">%Program Files%\Skype for Business Server 2015\Web Components\Meeting Room Portal\Int\Handler\\</span></span>

4. <span data-ttu-id="27816-152">Ändern Sie die PortalUserName in der Datei "Web.config" für den Benutzernamen, die in Schritt2 erstellt haben, klicken Sie im Abschnitt "[Konfigurieren der Umgebung für die SRS v1 Administrative Webportal](room-system-v1-administrative-web-portal.md#Config_Env)" (der empfohlene Name im Schritt ist LRSApp):</span><span class="sxs-lookup"><span data-stu-id="27816-152">In the Web.Config file, change the PortalUserName to the username created in Step 2 under the section "[Configure your environment for the SRS v1 Administrative Web Portal](room-system-v1-administrative-web-portal.md#Config_Env)" (the recommended name in the step is LRSApp):</span></span>

    ```
    <add key="PortalUserName" value="sip:LRSApp@domain.com" />
    ```

5. <span data-ttu-id="27816-p110">Da das Webportal zur Verwaltung von SRS v1 eine vertrauenswürdige Anwendung ist, müssen Sie das Kennwort bei der Portalkonfiguration nicht angeben. Wenn für diesen Benutzer nicht die lokale Registrierungsstelle, sondern eine andere Registrierungsstelle verwendet wird, müssen Sie diese für den Benutzer angeben, indem Sie folgende Zeile in die Datei Web.Config einfügen: </span><span class="sxs-lookup"><span data-stu-id="27816-p110">Because the SRS v1 Admin Portal is a trusted application, you do not need to provide the password in the portal configuration. If this user is using a different registrar than local registrar, you need to specify the registrar for it by adding the following line in the Web.Config file:</span></span>

   ```
   <add key="PortalUserRegistrarFQDN" value="pool-xxxx.domain.com" />
   ```

6. <span data-ttu-id="27816-155">Wenn der verwendete Port nicht der Port 5061 ist, fügen Sie folgende Zeile in die Datei Web.Config ein: </span><span class="sxs-lookup"><span data-stu-id="27816-155">If the port used is other than 5061, add the following line in the Web.Config file:</span></span>

   ```
   <add key="PortalUserRegistrarPort" value="5061" />
   ```

### <a name="verify-installation-of-the-srs-administrative-web-portal"></a><span data-ttu-id="27816-156">Überprüfen Sie die Installation des Webportals zur Verwaltung von SRS</span><span class="sxs-lookup"><span data-stu-id="27816-156">Verify Installation of the SRS Administrative Web Portal</span></span>

<span data-ttu-id="27816-157">Wenn Sie die Installation des Webportals zur Verwaltung von SRS v1 überprüfen möchten, gehen Sie wie folgt vor.</span><span class="sxs-lookup"><span data-stu-id="27816-157">To verify installation of the SRS v1 Administrative Web Portal, do the following:</span></span>

1. <span data-ttu-id="27816-158">Navigieren Sie auf einem Front-End-Server zur folgenden URL:</span><span class="sxs-lookup"><span data-stu-id="27816-158">On a Front End server, browse to the following URL:</span></span>

    <span data-ttu-id="27816-159">https://\<Fe-Server\>/lrs</span><span class="sxs-lookup"><span data-stu-id="27816-159">https://\<fe-server\>/lrs</span></span>

    <span data-ttu-id="27816-160">Sie sollten keine Fehler sehen (siehe folgende Abbildung):</span><span class="sxs-lookup"><span data-stu-id="27816-160">You should not see any errors, as shown in the following image:</span></span>

     ![Anmeldebildschirm für das Webportal zur Verwaltung des Lync-Raumsystems](../../media/LRS_AdminPortalSignIn.png)

2. <span data-ttu-id="27816-162">Wenn Sie keine Fehler sehen, versuchen Sie, über einen anderen Computer in der Topologie auf die folgende URL zuzugreifen:</span><span class="sxs-lookup"><span data-stu-id="27816-162">If you do not see any errors, try accessing the following URL from any other computer in the topology:</span></span>

    <span data-ttu-id="27816-163">https://\<Fe-Server\>/lrs</span><span class="sxs-lookup"><span data-stu-id="27816-163">https://\<fe-server\>/lrs</span></span>

    <span data-ttu-id="27816-164">Um die Seite zu öffnen, müssen Sie die DNS-Datensätze hinzufügen, wie unter "[DNS-Einträge für die automatische Clientanmeldung erforderlich](https://go.microsoft.com/fwlink/p/?LinkId=318056)."</span><span class="sxs-lookup"><span data-stu-id="27816-164">To access the page, you will need to add the DNS records as described in "[Required DNS Records for Automatic Client Sign-In](https://go.microsoft.com/fwlink/p/?LinkId=318056)."</span></span>

## <a name="use-the-srs-administrative-web-portal"></a><span data-ttu-id="27816-165">Verwenden Sie das Webportal zur Verwaltung von SRS</span><span class="sxs-lookup"><span data-stu-id="27816-165">Use the SRS Administrative Web Portal</span></span>
<span data-ttu-id="27816-166"><a name="Use_Portal"> </a></span><span class="sxs-lookup"><span data-stu-id="27816-166"></span></span>

<span data-ttu-id="27816-167">Nach der Bereitstellung von SRS auf dem Server können Sie den Status aller SRS-Räume überprüfen, indem Sie sich von einem Browser beim Webportal für die Verwaltung von SRS v1 anmelden.</span><span class="sxs-lookup"><span data-stu-id="27816-167">After you deploy SRS on the server, you can check the status of all SRS rooms by signing into the SRS v1 Administrative Web Portal from a browser.</span></span>

### <a name="sign-in"></a><span data-ttu-id="27816-168">Anmelden</span><span class="sxs-lookup"><span data-stu-id="27816-168">Sign in</span></span>

1. <span data-ttu-id="27816-169">Navigieren Sie zu der folgenden URL:</span><span class="sxs-lookup"><span data-stu-id="27816-169">Browse to the following URL:</span></span>

    <span data-ttu-id="27816-170">https://\<Fe-Server\>/lrs</span><span class="sxs-lookup"><span data-stu-id="27816-170">https://\<fe-server\>/lrs</span></span>

2. <span data-ttu-id="27816-171">Geben Sie die Anmeldeinformationen für das LRSSupport-Konto oder ein Konto ein, das der Sicherheitsgruppe LRSSupportAdminGroup hinzugefügt wurde.</span><span class="sxs-lookup"><span data-stu-id="27816-171">Enter the credentials for the LRSSupport account or an account that was added to the LRSSupportAdminGroup security group.</span></span>

![Anmeldebildschirm für das Webportal zur Verwaltung des Lync-Raumsystems](../../media/LRS_AdminPortalSignIn.png)

### <a name="srs-administrative-web-portal-summary-page"></a><span data-ttu-id="27816-173">Übersichtsseite für das Webportal für die Verwaltung von SRS</span><span class="sxs-lookup"><span data-stu-id="27816-173">SRS Administrative Web Portal Summary Page</span></span>

<span data-ttu-id="27816-174">Die Übersichtsseite stellt die folgenden Informationen für alle SRS-Räume bereit, die auf dem Server bereitgestellt werden:</span><span class="sxs-lookup"><span data-stu-id="27816-174">The summary page provides the following information for all of the SRS rooms deployed on the server:</span></span>

- <span data-ttu-id="27816-175">**Tag** Der benutzerdefinierte Name, den der Administrator auf dem Raum ermöglicht.</span><span class="sxs-lookup"><span data-stu-id="27816-175">**Tag** The custom name that the administrator gives to the room.</span></span> <span data-ttu-id="27816-176">Das Tag kann im Portal festgelegt werden, indem Sie auf den Raumnamen klicken.</span><span class="sxs-lookup"><span data-stu-id="27816-176">The Tag can be set in the portal by clicking on the room name.</span></span>

- <span data-ttu-id="27816-177">**Integrität** Den Status des Raums, die von der aggregierte Integritätsstatus Raum abgeleitet wird der Abschnitt Integrität von der Seite Einstellungen für Raum angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="27816-177">**Health** The health status of the room, which is derived from the Aggregate Health status of the room, which is shown under the Health section of the Room Settings page.</span></span>

- <span data-ttu-id="27816-178">**Nächsten Besprechung** Datum und Uhrzeit der nächsten Besprechung geplant ist.</span><span class="sxs-lookup"><span data-stu-id="27816-178">**Next Meeting** The date and time the next meeting is scheduled.</span></span>

- <span data-ttu-id="27816-179">**SRS Version, Hersteller, Modell** Diese Werte werden in SRS voreinstellen.</span><span class="sxs-lookup"><span data-stu-id="27816-179">**SRS Version, Manufacturer, Model** These values are preset in SRS.</span></span> <span data-ttu-id="27816-180">Je nach Hersteller können diese Felder auch leer sein.</span><span class="sxs-lookup"><span data-stu-id="27816-180">Depending on the manufacturer, these fields might be left blank.</span></span>

- <span data-ttu-id="27816-181">**Letzte Aktualisierung** Zeigt das letzte Mal die Webseite aktualisiert wurde.</span><span class="sxs-lookup"><span data-stu-id="27816-181">**Last Refresh** Displays the last time the web page was refreshed.</span></span>

![Zusammenfassungsansicht für das Webportal zur Verwaltung des Lync-Raumsystems](../../media/LRS_AdminPortal_Summary_view.png)

> [!NOTE]
> <span data-ttu-id="27816-183">Klicken Sie im Menü Bulk Management wird nur angezeigt, wenn Sie Mitglied der Sicherheitsgruppe LRSPowerUserAdminsGroup sind.</span><span class="sxs-lookup"><span data-stu-id="27816-183">You will only see the Bulk Management menu if you are part of the LRSPowerUserAdminsGroup security group.</span></span>

### <a name="srs-room-information"></a><span data-ttu-id="27816-184">SRS-Rauminformationen</span><span class="sxs-lookup"><span data-stu-id="27816-184">SRS Room Information</span></span>

<span data-ttu-id="27816-p113">Im Abschnitt zu den Rauminformationen des Portals können Sie individuelle SRS-Räume anzeigen und konfigurieren. Hier finden Sie vier Abschnitte zu Einstellungen, Details, Protokollierung und Integrität.</span><span class="sxs-lookup"><span data-stu-id="27816-p113">The Room Info section of the portal allows you to view and configure individual SRS rooms. It contains four sections: Settings, Details, Logging, and Health.</span></span>

#### <a name="settings"></a><span data-ttu-id="27816-187">Einstellungen</span><span class="sxs-lookup"><span data-stu-id="27816-187">Settings</span></span>

<span data-ttu-id="27816-p114">Im Abschnitt zu den Einstellungen können Sie das Kennwort, das Tag für den Raum und die Standardlautstärke für den Raum festlegen. Wenn Sie diese Einstellungen konfigurieren, werden die Änderungen erst repliziert, nachdem Sie die SRS-Konsole neu gestartet haben. Ihnen werden nur die System-Updates-Einstellungen für SRS-Geräte angezeigt, die Version 15.12 oder höher verwenden.</span><span class="sxs-lookup"><span data-stu-id="27816-p114">In the Settings section, you can set the password, room tag, and default volume levels for the room. If you configure these settings, the changes are replicated only after you restart the SRS console. You will only see System Updates settings for SRS devices using release 15.12 and later.</span></span>

![Einstellungen für das Webportal zur Verwaltung des Lync-Raumsystems](../../media/LRS_AdminPortal_RoomInfoSettings.png)

#### <a name="details"></a><span data-ttu-id="27816-192">Details</span><span class="sxs-lookup"><span data-stu-id="27816-192">Details</span></span>

<span data-ttu-id="27816-193">Im Detailbereich enthält eine schreibgeschützte Zusammenfassung der Einstellungen für den SRS Raum sowie: der Zeitpunkt der letzten Aktualisierung; nächsten Besprechung; zuletzt aktualisiert, Wartung und Kalibrierung; Standard Lautsprecher und Mikrofon sowie Rufton; Version. SIP-URI; die Anzahl der Bildschirme und Details zu jedem Bildschirm; Status und Aktivität.</span><span class="sxs-lookup"><span data-stu-id="27816-193">The Details section provides a read-only summary of the SRS room's settings, including: the time of last refresh; next meeting; last updates, maintenance and calibration; default speaker, mic, and ringer settings; version; SIP URI; number of screens and details about each screen; status, and activity.</span></span>

![Detailansicht für das Webportal zur Verwaltung des Lync-Raumsystems](../../media/LRS_AdminPortal_Detail_view.png)

#### <a name="troubleshooting"></a><span data-ttu-id="27816-195">Problembehandlung</span><span class="sxs-lookup"><span data-stu-id="27816-195">Troubleshooting</span></span>

<span data-ttu-id="27816-p115">Im Abschnitt zur Problembehandlung können Sie remote Protokolle erfassen und sie an einem angegebenen Standort speichern. Sie können außerdem die SRS-Konsole (SRS-Benutzeroberfläche) oder das gesamte System neu starten. Stellen Sie zur Erfassung von Protokollen einen Ordnerpfad im angegebenen Format bereit und vergewissern Sie sich, dass der Ordner über Schreibberechtigungen für das SRS-Computerkonto verfügt. Bei einer sehr umfangreichen Protokollgröße kann es bis zu 5 Minuten dauern, bis der Vorgang zur Erfassung der Protokolle abgeschlossen ist. Sie erhalten den aktuellen Status, wenn Sie die Seite aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="27816-p115">The Troubleshooting section can be used to remotely collect logs and save them to a specified location. You can also restart the SRS console (SRS user interface) or restart the entire system. To collect logs, provide a folder path in the specified format and make sure that the folder has write permissions given to the SRS machine account. If the log size is too big, it can take up to 5 minutes to finish collecting logs. Refreshing the page will give you the latest status.</span></span>

#### <a name="health"></a><span data-ttu-id="27816-201">Integrität</span><span class="sxs-lookup"><span data-stu-id="27816-201">Health</span></span>

<span data-ttu-id="27816-202">Bereich "Health" bietet eine visuelle Darstellung der die Integrität der Skype für Business Server-Verbindung, Audiogerät, Videogerät, Resiliency Zustand und Bildschirm Gerät.</span><span class="sxs-lookup"><span data-stu-id="27816-202">The Health section gives a visual indication of the health of the Skype for Business Server connection, audio device, video device, resiliency state, and screen device.</span></span>

![Integrität für das Webportal zur Verwaltung des Lync-Raumsystems](../../media/LRS_AdminPortal_RoomInfoHealth.png)

### <a name="additional-notes-about-the-administrative-web-portal"></a><span data-ttu-id="27816-204">Weitere Hinweise zum Webportal für die Verwaltung</span><span class="sxs-lookup"><span data-stu-id="27816-204">Additional Notes about the Administrative Web Portal</span></span>

> [!NOTE]
>  <span data-ttu-id="27816-205">Ändert sich die Einstellung werden angewendet, wenn das System SRS .> neu gestartet ist, wenn das Kontokennwort LRSApp abläuft, Sie werden nicht den Status der Chatrooms anzeigen.</span><span class="sxs-lookup"><span data-stu-id="27816-205">Setting changes are applied only after the SRS system is restarted.>  If the LRSApp account password expires, you will not be able to see the status of the rooms.</span></span> <span data-ttu-id="27816-206">Konfigurieren Sie das Kontokennwort LRSAppuser, sodass es nie abläuft, oder müssen Sie unbedingt das Kennwort aktualisieren, wenn es in der Nähe der SRS administrative Expiration.>, dass nur lokale Bereitstellungen Webportal geführt wird.</span><span class="sxs-lookup"><span data-stu-id="27816-206">Configure the LRSAppuser account password so that it never expires, or be sure to update the password when it is near expiration.>  The SRS administrative web portal is supported for on-premises deployments only.</span></span>

### <a name="bulk-management"></a><span data-ttu-id="27816-207">Massenverwaltung </span><span class="sxs-lookup"><span data-stu-id="27816-207">Bulk management</span></span>

<span data-ttu-id="27816-208">Die Massenverwaltung von SRS-Räumen ist eine Funktion, die für fortgeschrittene IT-Administratoren entwickelt wurde, um den Workflow zu vereinfachen und durch ein zeitsparendes praktisches Tool die Remote-Verwaltung mehrerer Räume in Form eines Massenvorgangs zu ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="27816-208">Bulk management of SRS rooms is a feature designed for advanced IT administrators, to simplify their workflow, and enable them with a time-saving convenient tool to remotely manage multiple rooms in a bulk fashion.</span></span>

<span data-ttu-id="27816-209">Um diese Funktion anzuzeigen, muss der Benutzer als ein Mitglied der besonderen Sicherheitsgruppe **LRSPowerUserAdminsGroup** eingerichtet sein.  </span><span class="sxs-lookup"><span data-stu-id="27816-209">In order to see this functionality, the user need to be provisioned as a member of the special security group, **LRSPowerUserAdminsGroup**.</span></span>

<span data-ttu-id="27816-p117">Die Anzahl der für die Massenverwaltung auswählbaren SRS-Räume ist nicht begrenzt. Sie können jedoch immer nur einen Massenverwaltungsvorgang durchführen.</span><span class="sxs-lookup"><span data-stu-id="27816-p117">There is no limit to the number of SRS rooms you can select for bulk management. However, you can perform only one bulk management operation at a time.</span></span>

<span data-ttu-id="27816-212">Wählen Sie zum Durchführen eines Massenverwaltungsvorgangs die Räume, die Sie überwachen möchten, und klicken sie auf das Massenverwaltungsmenü. </span><span class="sxs-lookup"><span data-stu-id="27816-212">To perform a bulk management operation, select the rooms you want to monitor, and click on the Bulk management menu.</span></span>

### <a name="frequently-asked-questions"></a><span data-ttu-id="27816-213">Häufig gestellte Fragen</span><span class="sxs-lookup"><span data-stu-id="27816-213">Frequently asked questions</span></span>

#### <a name="why-cant-i-sign-in-to-the-administrative-web-portal"></a><span data-ttu-id="27816-214">Warum anmelden kann nicht Bereiche der administrativen Webportal?</span><span class="sxs-lookup"><span data-stu-id="27816-214">Why can't I sign in to the administrative web portal?</span></span>

<span data-ttu-id="27816-215">Beim Öffnen https://localhost/lrs, können die Anmeldeseite angezeigt, doch wenn Sie in Ihre Anmeldeinformationen eingeben, Sie können sich nicht anmelden.</span><span class="sxs-lookup"><span data-stu-id="27816-215">When you open https://localhost/lrs, you will be able to see the sign in page, but when you type in your credentials, you cannot sign in.</span></span> <span data-ttu-id="27816-216">In diesem Fall müssen Sie öffnen https://FQDNofFEserver/SRS zur Anmeldung bei des administrative Webportals.</span><span class="sxs-lookup"><span data-stu-id="27816-216">In this case, you must open https://FQDNofFEserver/SRS to sign in to the administrative web portal.</span></span>

#### <a name="why-cant-i-see-srs-v1-in-the-administrative-web-portal"></a><span data-ttu-id="27816-217">Warum wird angezeigt nicht SRS v1 in den administrativen Webportal?</span><span class="sxs-lookup"><span data-stu-id="27816-217">Why can't I see SRS v1 in the administrative web portal?</span></span>

- <span data-ttu-id="27816-218">Stellen Sie sicher, dass Sie SRS-Konten in Ihrer Bereitstellung haben und diese nach den Empfehlungen für die Bereitstellung des Webportals für die SRS-Verwaltung erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="27816-218">Make sure you have SRS accounts in your deployment and that they are created according to the SRS Administrative Web Portal deployment recommendations.</span></span> <span data-ttu-id="27816-219">Stellen Sie sicher, dass die SRS-Konten über Enable-CsMeetingRoom, nicht Enable-CsUser, bei der Skype für Business Server bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="27816-219">Make sure the SRS accounts are provisioned using Enable-CsMeetingRoom, not Enable-CsUser, on the Skype for Business Server.</span></span>

- <span data-ttu-id="27816-220">Wenn Sie SRS Konten erstellt haben und die Konten in administrative Webportal wird nicht angezeigt, sammeln Sie die Serverprotokolle mithilfe der Skype für Business Server-Protokollierungstool mit der **MeetingPortal** Komponente ausgewählt, und senden Sie diese dann an den SRS Supportmitarbeiter.</span><span class="sxs-lookup"><span data-stu-id="27816-220">If you have created SRS accounts and cannot see the accounts in administrative web portal, collect the server logs by using the Skype for Business Server Logging tool with the **MeetingPortal** component selected, and then send them to your SRS support contact.</span></span>

- <span data-ttu-id="27816-p120">Wenn Sie SRS-Konten erstellt haben und die Konten im Webportal für die Verwaltung nicht sehen können, erfassen Sie die Clientprotokolle unter Verwendung von Fiddler, kopieren Sie das Konsolenprotokoll aus den Browserentwicklungstools und senden Sie diese dann an Ihren SRS-Supportkontakt. Sie können außerdem den Wert für die Verfolgungsstufe in der Datei Web.Confi ändern, um ein ausführliches Protokoll zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="27816-p120">If you have created SRS accounts and cannot see the accounts in administrative web portal, collect the client logs using Fiddler, and also copy the console log from the browser development tools, and then send them to your SRS support contact. You can also modify the trace level value in the Web.config to get a more detailed log.</span></span>

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

#### <a name="why-cant-i-see-the-status-of-srs-in-the-administrative-web-portal"></a><span data-ttu-id="27816-223">Warum wird angezeigt den Status der SRS in den administrativen Webportal nicht?</span><span class="sxs-lookup"><span data-stu-id="27816-223">Why can't I see the status of SRS in the administrative web portal?</span></span>

- <span data-ttu-id="27816-224">Stellen Sie sicher, dass für das LRSApp-Benutzerkonto SIP aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="27816-224">Make sure that the LRSApp user account is SIP-enabled.</span></span>

- <span data-ttu-id="27816-225">Wenn Sie immer noch Probleme auftreten, sammeln Sie die Datei **Trace.log** im System SRS aus D:\Tracing\LRSAdminLogs\, und senden Sie sie an den SRS-Supportmitarbeiter.</span><span class="sxs-lookup"><span data-stu-id="27816-225">If you are still having issues, collect the **Trace.log** file in the SRS system from D:\Tracing\LRSAdminLogs\, and then send it to your SRS support contact.</span></span>

#### <a name="why-cant-i-see-the-bulk-management-menus-for-srs-in-the-administrative-web-portal"></a><span data-ttu-id="27816-226">Warum wird angezeigt nicht die Massen Management Menüs für SRS in den administrativen Webportal?</span><span class="sxs-lookup"><span data-stu-id="27816-226">Why can't I see the bulk management menus for SRS in the administrative web portal?</span></span>

<span data-ttu-id="27816-227">Stellen Sie sicher, dass das Benutzerkonto LRSApp SIP aktiviert ist, und Teil der Sicherheitsgruppe LRSPowerUserAdminsGroup ist.</span><span class="sxs-lookup"><span data-stu-id="27816-227">Make sure that the LRSApp user account is SIP-enabled, and is part of the LRSPowerUserAdminsGroup security group.</span></span>

#### <a name="does-the-srs-v1-administrative-web-portal-work-with-microsoft-teams-rooms"></a><span data-ttu-id="27816-228">Funktioniert das Webportal SRS v1 administrative mit Microsoft-Teams Räumen?</span><span class="sxs-lookup"><span data-stu-id="27816-228">Does the SRS v1 administrative web portal work with Microsoft Teams Rooms?</span></span>

<span data-ttu-id="27816-229">Nein.</span><span class="sxs-lookup"><span data-stu-id="27816-229">No.</span></span>


