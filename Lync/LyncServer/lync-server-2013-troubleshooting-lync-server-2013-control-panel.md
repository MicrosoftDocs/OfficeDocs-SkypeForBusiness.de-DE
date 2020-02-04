---
title: 'Lync Server 2013: Problembehandlung bei der lync Server 2013-Systemsteuerung'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Troubleshooting Lync Server 2013 Control Panel
ms:assetid: 54e7ab57-34ce-4a07-bcc9-643379eb4eb7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg195689(v=OCS.15)
ms:contentKeyID: 48184145
ms.date: 07/28/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ff82a1e63a064d0053fc77614d6a9b5fa818c23e
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41745015"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="troubleshooting-lync-server-2013-control-panel"></a><span data-ttu-id="81e58-102">Problembehandlung bei der lync Server 2013-Systemsteuerung</span><span class="sxs-lookup"><span data-stu-id="81e58-102">Troubleshooting Lync Server 2013 Control Panel</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="81e58-103">_**Letztes Änderungsdatum des Themas:** 2016-07-28_</span><span class="sxs-lookup"><span data-stu-id="81e58-103">_**Topic Last Modified:** 2016-07-28_</span></span>

<span data-ttu-id="81e58-104">Dieses Thema enthält Informationen und Verfahren, die Ihnen bei der Problembehandlung beim Zugriff auf die lync Server 2013-Systemsteuerung helfen können.</span><span class="sxs-lookup"><span data-stu-id="81e58-104">This topic provides information and procedures that can help you troubleshoot access to Lync Server 2013 Control Panel.</span></span>

<div>

## <a name="internet-browser-requirements"></a><span data-ttu-id="81e58-105">Anforderungen des Internet Browsers</span><span class="sxs-lookup"><span data-stu-id="81e58-105">Internet Browser Requirements</span></span>

<span data-ttu-id="81e58-106">Die lync Server-Systemsteuerung setzt voraus, dass die Microsoft Silverlight-Browser-Plug-in-Version 4.0.50524.0 oder neueste Version installiert ist.</span><span class="sxs-lookup"><span data-stu-id="81e58-106">Lync Server Control Panel requires that Microsoft Silverlight browser plug-in version 4.0.50524.0 or latest version is installed.</span></span> <span data-ttu-id="81e58-107">Wenn Silverlight nicht installiert ist oder wenn eine frühere Version installiert ist, folgen Sie den Anweisungen in der Nachricht, um die erforderliche Version zu installieren.</span><span class="sxs-lookup"><span data-stu-id="81e58-107">If Silverlight is not installed or if an earlier version is installed, follow the instructions in the message to install the required version.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="81e58-108">Andere Softwareanforderungen für lync Server Control Panel beziehen sich auf das Betriebssystem, auf dem lync Server Control Panel und alle anderen lync Server 2013-Verwaltungstools installiert werden können.</span><span class="sxs-lookup"><span data-stu-id="81e58-108">Other software requirements for Lync Server Control Panel pertain to the operating system on which Lync Server Control Panel and all other Lync Server 2013 administrative tools can be installed.</span></span> <span data-ttu-id="81e58-109">Ausführliche Informationen finden Sie unter unter <A href="lync-server-2013-server-and-tools-operating-system-support.md">Stützung von Server-und Tools-Betriebssystemen in lync Server 2013</A> in der Dokumentation zur Unterstützung.</span><span class="sxs-lookup"><span data-stu-id="81e58-109">For details, see <A href="lync-server-2013-server-and-tools-operating-system-support.md">Server and tools operating system support in Lync Server 2013</A> in the Supportability documentation.</span></span>



</div>

<span data-ttu-id="81e58-110">Wenn Ihr Internet Browser die Installation von Silverlight aufgrund von Sicherheitsüberlegungen blockiert, fügen Sie die URL (Uniform Resource Locator) hinzu, mit der die lync Server-Systemsteuerung der Liste der vertrauenswürdigen Websites geöffnet wird.</span><span class="sxs-lookup"><span data-stu-id="81e58-110">If your Internet browser blocks installation of Silverlight due to security considerations, add the Uniform Resource Locator (URL) that opens Lync Server Control Panel to the list of trusted sites.</span></span> <span data-ttu-id="81e58-111">Stellen Sie sicher, dass in den Sicherheitseinstellungen von Internet Explorer die Option **ActiveX-Steuerelemente und Plug-Ins ausführen** auf **aktiviert**festgesetzt ist.</span><span class="sxs-lookup"><span data-stu-id="81e58-111">In Internet Explorer security settings, ensure that **Run ActiveX controls and plug-ins** is set to **Enabled**.</span></span> <span data-ttu-id="81e58-112">Ausführliche Informationen finden Sie [http://go.microsoft.com/fwlink/p/?linkId=214060](http://go.microsoft.com/fwlink/p/?linkid=214060)unter.</span><span class="sxs-lookup"><span data-stu-id="81e58-112">For details, see [http://go.microsoft.com/fwlink/p/?linkId=214060](http://go.microsoft.com/fwlink/p/?linkid=214060).</span></span> <span data-ttu-id="81e58-113">Stellen Sie außerdem sicher, dass der Browser für die Verwendung von SSL 3,0 konfiguriert ist.</span><span class="sxs-lookup"><span data-stu-id="81e58-113">Furthermore, ensure that the browser is configured to use SSL 3.0.</span></span>

<span data-ttu-id="81e58-114">Wenn der Internet Browser für die Verwendung eines Proxyservers konfiguriert ist, überprüfen Sie, ob der Browser so konfiguriert ist, dass der Proxy Server für Websites umgangen wird, die automatisch als interne Websites erkannt werden.</span><span class="sxs-lookup"><span data-stu-id="81e58-114">If the Internet browser is configured to use a proxy server, verify that the browser is configured to bypass the proxy server for sites that are automatically detected as internal sites.</span></span> <span data-ttu-id="81e58-115">Oder fügen Sie die Adresse der Ausnahmeliste des Browsers in den Konfigurationseinstellungen des Proxyservers hinzu.</span><span class="sxs-lookup"><span data-stu-id="81e58-115">Or, add the address to the browser's exception list in the proxy server configuration settings.</span></span>

</div>

<div>

## <a name="dns-record-and-certificate-requirements-for-the-administrative-access-url"></a><span data-ttu-id="81e58-116">DNS-Eintrag und Zertifikatanforderungen für die Administratorzugriffs-URL</span><span class="sxs-lookup"><span data-stu-id="81e58-116">DNS Record and Certificate Requirements for the Administrative Access URL</span></span>

<span data-ttu-id="81e58-117">Wenn Sie eine einfache URL für den Zugriff auf die lync Server-Systemsteuerung konfiguriert haben, stellen Sie sicher, dass Sie auch den statischen DNS-Host (Domain Name System)-Ressourceneintrag und das Zertifikat konfiguriert haben, das für die Verwendung dieser administrativen Zugriffs-URL erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="81e58-117">If you configured a simple URL to access Lync Server Control Panel, ensure that you also configured the static Domain Name System (DNS) host (A) resource record and certificate necessary to use that administrative access URL.</span></span> <span data-ttu-id="81e58-118">Wenn Sie die Basis-URL jederzeit ändern, stellen Sie sicher, dass sich die Änderung im entsprechenden DNS-Eintrag und-Zertifikat widerspiegelt und dass Sie die *enable-CsComputer* auf jedem Director und Front-End-Server ausführen, um die Änderung zu registrieren.</span><span class="sxs-lookup"><span data-stu-id="81e58-118">If you change the base URL at any time, ensure that the change is reflected in the appropriate DNS record and certificate and that you run the *Enable-CsComputer* on each Director and Front End Server to register the change.</span></span> <span data-ttu-id="81e58-119">Ausführliche Informationen finden Sie in den folgenden Themen in der Planungsdokumentation:</span><span class="sxs-lookup"><span data-stu-id="81e58-119">For details, see the following topics in the Planning documentation:</span></span>

  - [<span data-ttu-id="81e58-120">Planung für einfache URLs in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="81e58-120">Planning for simple URLs in Lync Server 2013</span></span>](lync-server-2013-planning-for-simple-urls.md)

  - [<span data-ttu-id="81e58-121">DNS-Anforderungen für einfache URLs in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="81e58-121">DNS requirements for simple URLs in Lync Server 2013</span></span>](lync-server-2013-dns-requirements-for-simple-urls.md)

  - [<span data-ttu-id="81e58-122">Anforderungen an Zertifikate für interne Server in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="81e58-122">Certificate requirements for internal servers in Lync Server 2013</span></span>](lync-server-2013-certificate-requirements-for-internal-servers.md)

<span data-ttu-id="81e58-123">Eine schrittweise Anleitung zum Konfigurieren der Administratorzugriffs-URL finden Sie unter [Bearbeiten oder konfigurieren einfacher URLs in lync Server 2013](lync-server-2013-edit-or-configure-simple-urls.md) in der Bereitstellungsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="81e58-123">For step-by-step procedures to configure the administrative access URL, see [Edit or configure simple URLs in Lync Server 2013](lync-server-2013-edit-or-configure-simple-urls.md) in the Deployment documentation.</span></span>

</div>

<div>

## <a name="internet-information-services-iis-requirements"></a><span data-ttu-id="81e58-124">Anforderungen für Internet Informationsdienste (IIS)</span><span class="sxs-lookup"><span data-stu-id="81e58-124">Internet Information Services (IIS) Requirements</span></span>

<span data-ttu-id="81e58-125">Lync Server Control Panel ist eine der Komponenten von lync Server 2013, die Internet Informationsdienste (IIS) erfordert.</span><span class="sxs-lookup"><span data-stu-id="81e58-125">Lync Server Control Panel is one of the components of Lync Server 2013 that requires Internet Information Services (IIS).</span></span> <span data-ttu-id="81e58-126">Stellen Sie insbesondere sicher, dass die http-Umleitungs-und Windows-Authentifizierungsfeatures aktiviert sind und dass der World Wide Web Publishing Service (W3SVC) ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="81e58-126">In particular, ensure that HTTP redirection and Windows authentication features are enabled, and that the World Wide Web Publishing Service (W3SVC) is running.</span></span>

<div>

## <a name="world-wide-publishing-service-windows-service-dependency"></a><span data-ttu-id="81e58-127">Weltweiter Publishing Service (Windows-Dienst)-Abhängigkeit</span><span class="sxs-lookup"><span data-stu-id="81e58-127">World Wide Publishing Service (Windows Service) Dependency</span></span>

<span data-ttu-id="81e58-128">Wenn der www-Publishing Dienst beendet wird, können Sie nicht auf die lync Server-Systemsteuerung zugreifen.</span><span class="sxs-lookup"><span data-stu-id="81e58-128">When the World Wide Web Publishing Service is stopped, you cannot access Lync Server Control Panel.</span></span> <span data-ttu-id="81e58-129">Sie können den Dienst mithilfe der Microsoft Management Console (MMC) für Windows-Dienste neu starten.</span><span class="sxs-lookup"><span data-stu-id="81e58-129">You can restart the service by using the Windows Services Microsoft Management Console (MMC).</span></span>

<span data-ttu-id="81e58-130">**So starten Sie den WWW-Publishing Dienst**</span><span class="sxs-lookup"><span data-stu-id="81e58-130">**To start the World Wide Web Publishing Service**</span></span>

1.  <span data-ttu-id="81e58-131">Melden Sie sich bei dem Computer an, auf dem der www-Publishing Dienst als Teil der Internet Informationsdienste (IIS) installiert ist.</span><span class="sxs-lookup"><span data-stu-id="81e58-131">Log on to the computer where the World Wide Web Publishing Service is installed as part of Internet Information Services (IIS).</span></span>

2.  <span data-ttu-id="81e58-132">Klicken Sie auf **Start**, klicken Sie auf **Verwaltung**, und klicken Sie dann auf **Dienste**.</span><span class="sxs-lookup"><span data-stu-id="81e58-132">Click **Start**, click **Administrative Tools**, and then click **Services**.</span></span>

3.  <span data-ttu-id="81e58-133">Klicken Sie mit der rechten Maustaste auf www- **Publishing Dienst**, und klicken Sie dann auf **Start**.</span><span class="sxs-lookup"><span data-stu-id="81e58-133">Right-click **World Wide Web Publishing Service**, and then click **Start**.</span></span>

</div>

<div>

## <a name="application-pool-mode"></a><span data-ttu-id="81e58-134">Anwendungs Pool Modus</span><span class="sxs-lookup"><span data-stu-id="81e58-134">Application Pool Mode</span></span>

<span data-ttu-id="81e58-135">Konfigurieren Sie IIS so, dass der CsManagementAppPool-Anwendungspool das Netzwerkdienstkonto als Prozessmodell Identität verwendet.</span><span class="sxs-lookup"><span data-stu-id="81e58-135">Configure IIS so that the CsManagementAppPool application pool uses the Network Service account as its process model identity.</span></span>

</div>

</div>

<div>

## <a name="user-rights-and-permissions"></a><span data-ttu-id="81e58-136">Benutzerrechte und-Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="81e58-136">User Rights and Permissions</span></span>

<span data-ttu-id="81e58-137">Sie müssen sich mit einem Domänenkonto, das ein Mitglied der CsAdministrator-Gruppe ist, oder mithilfe eines Kontos, an das Sie Benutzerrechte und-Berechtigungen delegiert haben, bei der lync Server Control Panel-Anwendung anmelden.</span><span class="sxs-lookup"><span data-stu-id="81e58-137">You must sign in to Lync Server Control Panel either by using a domain account that is a member of the CsAdministrator group or by using an account to which you have delegated user rights and permissions.</span></span> <span data-ttu-id="81e58-138">Sie können sich nicht über ein lokales Computerkonto bei der lync Server Control Panel-Anwendung anmelden.</span><span class="sxs-lookup"><span data-stu-id="81e58-138">You cannot sign in to Lync Server Control Panel by using a local machine account.</span></span> <span data-ttu-id="81e58-139">Ausführliche Informationen zum Delegieren von administrativen Aufgaben über rollenbasierte Zugriffssteuerung (Role-Based Access Control, RBAC) finden Sie unter [Planen der rollenbasierten Zugriffssteuerung in lync Server 2013](lync-server-2013-planning-for-role-based-access-control.md) in der Planungsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="81e58-139">For details about delegating administrative tasks through role-based access control (RBAC), see [Planning for role-based access control in Lync Server 2013](lync-server-2013-planning-for-role-based-access-control.md) in the Planning documentation.</span></span>

<span data-ttu-id="81e58-140">Wenn Sie eine einfache URL für den Zugriff auf die lync Server-Systemsteuerung verwenden, stellen Sie sicher, dass die Webservern den RTCUniversalServerAdmins-und RTCUniversalUserAdmins-Gruppen hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="81e58-140">If you use a simple URL to access Lync Server Control Panel, ensure that web servers are added to the RTCUniversalServerAdmins and RTCUniversalUserAdmins groups.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="81e58-141">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="81e58-141">See Also</span></span>


[<span data-ttu-id="81e58-142">Lync Server 2013-Verwaltungstools</span><span class="sxs-lookup"><span data-stu-id="81e58-142">Lync Server 2013 administrative tools</span></span>](lync-server-2013-lync-server-administrative-tools.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

