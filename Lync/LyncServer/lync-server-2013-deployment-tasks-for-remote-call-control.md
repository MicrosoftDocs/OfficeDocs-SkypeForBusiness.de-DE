---
title: 'Lync Server 2013: Bereitstellungsaufgaben für die Remoteanrufsteuerung'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deployment tasks for remote call control
ms:assetid: 20218871-4f27-4611-9b7e-c0ca55908284
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558624(v=OCS.15)
ms:contentKeyID: 48183599
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: df80ebcdc879598677a037d60c9eeeee46ba5209
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41762553"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deployment-tasks-for-remote-call-control-in-lync-server-2013"></a><span data-ttu-id="ae9af-102">Bereitstellungsaufgaben für die Remoteanrufsteuerung in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ae9af-102">Deployment tasks for remote call control in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ae9af-103">_**Letztes Änderungsdatum des Themas:** 2012-10-05_</span><span class="sxs-lookup"><span data-stu-id="ae9af-103">_**Topic Last Modified:** 2012-10-05_</span></span>

<span data-ttu-id="ae9af-104">In diesem Thema werden die Bereitstellungsaufgaben beschrieben, die Sie ausführen müssen, um die Remoteanrufsteuerung für Benutzer in ihrer lync Server-Umgebung zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="ae9af-104">This topic describes the deployment tasks that you must perform to enable remote call control for users in your Lync Server environment.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="ae9af-105">Wenn Sie Benutzer migrieren, die zuvor für die Remoteanrufsteuerung in Microsoft Office Communicator 2007 R2 aktiviert wurden, müssen Sie eine zusätzliche Bereitstellungsaufgabe ausführen, bevor Sie mit der Durchführung der in diesem Thema beschriebenen Bereitstellungsaufgaben für Remoteanrufsteuerung beginnen.</span><span class="sxs-lookup"><span data-stu-id="ae9af-105">If you are migrating users previously enabled for remote call control in Microsoft Office Communicator 2007 R2, you must perform an additional deployment task before you begin performing the remote call control deployment tasks described in this topic.</span></span> <span data-ttu-id="ae9af-106">Während des Migrationsvorgangs zu lync Server müssen vertrauenswürdige Anwendungs Einträge (vormals als <EM>autorisierte Hosteinträge</EM>bezeichnet) mithilfe der Verwaltungstools von Office Communications Server 2007 R2 entfernt werden.</span><span class="sxs-lookup"><span data-stu-id="ae9af-106">During the migration process to Lync Server, trusted application entries (previously known as <EM>authorized host entries</EM>) must be removed by using the Office Communications Server 2007 R2 administrative tools, as appropriate.</span></span><BR><span data-ttu-id="ae9af-107">Details zum Entfernen autorisierter Hosts finden Sie unter <A href="lync-server-2013-remove-a-legacy-authorized-host-optional.md">Entfernen eines autorisierten Legacyhosts in lync Server 2013 (optional)</A>.</span><span class="sxs-lookup"><span data-stu-id="ae9af-107">For details about removing authorized hosts, see <A href="lync-server-2013-remove-a-legacy-authorized-host-optional.md">Remove a legacy authorized host in Lync Server 2013 (optional)</A>.</span></span>



</div>

<div>

## <a name="step-1-install-and-configure-the-sipcsta-gateway-to-communicate-with-your-pbx"></a><span data-ttu-id="ae9af-108">Schritt 1: Installieren und Konfigurieren des SIP/CSTA-Gateways für die Kommunikation mit Ihrer Telefonanlage</span><span class="sxs-lookup"><span data-stu-id="ae9af-108">Step 1: Install and Configure the SIP/CSTA Gateway to Communicate with Your PBX</span></span>

<span data-ttu-id="ae9af-109">Sie müssen mindestens ein SIP/CSTA-Gateway installieren, das eine Verbindung mit lync Server und der vorhandenen PBX-Anlage (Private Branch Exchange) in Ihrer Umgebung herstellen kann, um Ihren Benutzern Funktionen zur Remoteanrufsteuerung zur Verfügung zu stellen.</span><span class="sxs-lookup"><span data-stu-id="ae9af-109">You need to install at least one SIP/CSTA gateway that can connect to both Lync Server and the existing private branch exchange (PBX) in your environment in order to provide remote call control features to your users.</span></span> <span data-ttu-id="ae9af-110">Ein SIP/CSTA-Gateway ist ein Gateway zwischen SIP und einer computergestützten Telekommunikations Anwendung (CSTA).</span><span class="sxs-lookup"><span data-stu-id="ae9af-110">A SIP/CSTA gateway is a gateway between SIP and a computer-supported telecommunications application (CSTA).</span></span> <span data-ttu-id="ae9af-111">Unabhängig davon, ob Sie mehrere Gateways oder nur eine installieren, kann jeder Benutzer mit nur einem Gateway oder einer Telefonanlage konfiguriert werden.</span><span class="sxs-lookup"><span data-stu-id="ae9af-111">Whether you install multiple gateways or just one, each user can be configured with only one gateway or PBX.</span></span> <span data-ttu-id="ae9af-112">Wenn Ihre vorhandene Telefonanlage keine SIP-CSTA-Schnittstelle aufweist, stellen Sie sicher, dass Sie ein SIP/CSTA-Gateway bereitstellen, das die Telefonanlage unterstützt, einschließlich der Unterstützung für herstellerspezifische Signalisierungsprotokolle für proprietäre Telefonanlagen.</span><span class="sxs-lookup"><span data-stu-id="ae9af-112">If your existing PBX does not have a SIP/CSTA interface, ensure you deploy a SIP/CSTA gateway that can support the PBX, including support for proprietary PBX vendor-specific signaling protocols.</span></span> <span data-ttu-id="ae9af-113">Detaillierte Informationen zu den Funktionen finden Sie in den einzelnen Anbietern direkt.</span><span class="sxs-lookup"><span data-stu-id="ae9af-113">For details about capabilities, consult each vendor directly.</span></span>

<span data-ttu-id="ae9af-114">Wenn Sie bereit sind, ein SIP/CSTA-Gateway bereitzustellen, das in lync Server für die Remoteanrufsteuerung integriert werden kann, konsultieren Sie auch Ihren Gateway-Anbieter oder die Gateway-Dokumentation des Anbieters hinsichtlich der Syntax, die das Gateway für die folgenden Informationen benötigt:</span><span class="sxs-lookup"><span data-stu-id="ae9af-114">When you are ready to deploy a SIP/CSTA gateway that can integrate with Lync Server for remote call control, also consult with your gateway vendor or the vendor’s gateway documentation regarding the syntax required by the gateway for the following information:</span></span>

  - <span data-ttu-id="ae9af-115">Leitungsserver-URI des Gateways</span><span class="sxs-lookup"><span data-stu-id="ae9af-115">Line server URI of the gateway</span></span>

  - <span data-ttu-id="ae9af-116">Leitungs-URI für Benutzer, die dem Gateway zugewiesen werden</span><span class="sxs-lookup"><span data-stu-id="ae9af-116">Line URI for users that will be assigned to the gateway</span></span>

<span data-ttu-id="ae9af-117">Die vorherigen Einstellungen sind während der Benutzerkonfiguration erforderlich und müssen vom Gateway so angegeben werden, dass es ordnungsgemäß weitergeleitet und mit der Telefonanlage verbunden werden kann.</span><span class="sxs-lookup"><span data-stu-id="ae9af-117">The preceding settings are required during user configuration and must be specified as expected by the gateway to route and connect to the PBX properly.</span></span>

<span data-ttu-id="ae9af-118">Sie können auf der Website Microsoft Unified Communications Open Interoperability Program unter [http://go.microsoft.com/fwlink/p/?linkId=203309](http://go.microsoft.com/fwlink/p/?linkid=203309)auf Anbieter verweisen.</span><span class="sxs-lookup"><span data-stu-id="ae9af-118">You can refer to vendors on the Microsoft Unified Communications Open Interoperability Program website at [http://go.microsoft.com/fwlink/p/?linkId=203309](http://go.microsoft.com/fwlink/p/?linkid=203309).</span></span>

</div>

<div>

## <a name="step-2-configure-lync-server-to-route-csta-requests-to-the-sipcsta-gateway"></a><span data-ttu-id="ae9af-119">Schritt 2: Konfigurieren von lync Server zum Weiterleiten von CSTA-Anforderungen an das SIP/CSTA-Gateway</span><span class="sxs-lookup"><span data-stu-id="ae9af-119">Step 2: Configure Lync Server to Route CSTA Requests to the SIP/CSTA Gateway</span></span>

<span data-ttu-id="ae9af-120">Sie müssen statische Routen in lync Server-Pools an die Zieladresse (Server-URI) aller SIP/CSTA-Gateways in Ihrer Bereitstellung erstellen, an die Sie Remote Anruf Steuerungsanforderungen weiterleiten möchten.</span><span class="sxs-lookup"><span data-stu-id="ae9af-120">You must create static routes on Lync Server pools to the destination address (server URI) of all SIP/CSTA gateways in your deployment to which you intend to route remote call control requests.</span></span> <span data-ttu-id="ae9af-121">Sie müssen auch einen Eintrag für vertrauenswürdige Anwendungen erstellen, der den einzelnen Zieladressen entspricht.</span><span class="sxs-lookup"><span data-stu-id="ae9af-121">You must also create a trusted application entry that corresponds to each destination address.</span></span> <span data-ttu-id="ae9af-122">Wenn Sie das Gateway als vertrauenswürdige Anwendung festgelegt haben, wird der vertrauenswürdige Status für die Ausführung als Teil der lync Server-Umgebung gewährt, obwohl es von einem Drittanbieter entwickelt wurde (und den als *externer Dienst* bezeichneten Dienst ausführt, da es sich um einen Dienst handelt, der kein integrierter Teil des Produkts ist).</span><span class="sxs-lookup"><span data-stu-id="ae9af-122">When you designate the gateway as a trusted application, it is given trusted status to run as part of the Lync Server environment even though it is developed by a third party (and runs what is referred to as an *external service* because it is a service that is not a built-in part of the product).</span></span> <span data-ttu-id="ae9af-123">Wenn lync Server eine Verbindung mit dem SIP/CSTA-Gateway über eine TCP-Verbindung (Transmission Control Protocol) anstelle einer TLS-Verbindung (Transport Layer Security) herstellen soll, müssen Sie auch die Gateway-IP-Adresse mithilfe von Topology Builder definieren.</span><span class="sxs-lookup"><span data-stu-id="ae9af-123">Finally, if Lync Server will connect to the SIP/CSTA gateway using a Transmission Control Protocol (TCP) connection instead of a Transport Layer Security (TLS) connection, you must also define the gateway IP address by using Topology Builder.</span></span>

<span data-ttu-id="ae9af-124">Details zum Konfigurieren von statischen Routen finden Sie unter [Konfigurieren einer statischen Route für die Remoteanrufsteuerung in lync Server 2013](lync-server-2013-configure-a-static-route-for-remote-call-control.md).</span><span class="sxs-lookup"><span data-stu-id="ae9af-124">For details about configuring static routes, see [Configure a static route for remote call control in Lync Server 2013](lync-server-2013-configure-a-static-route-for-remote-call-control.md).</span></span>

<span data-ttu-id="ae9af-125">Details zum Konfigurieren von Einträgen für vertrauenswürdige Anwendungen finden Sie unter [Konfigurieren eines vertrauenswürdigen Anwendungseintrags für die Remoteanrufsteuerung in lync Server 2013](lync-server-2013-configure-a-trusted-application-entry-for-remote-call-control.md).</span><span class="sxs-lookup"><span data-stu-id="ae9af-125">For details about configuring trusted application entries, see [Configure a trusted application entry for remote call control in Lync Server 2013](lync-server-2013-configure-a-trusted-application-entry-for-remote-call-control.md).</span></span>

<span data-ttu-id="ae9af-126">Details zum Definieren einer IP-Adresse für SIP/CSTA-Gateways im Topologie-Generator finden Sie unter [Definieren einer IP-Adresse für SIP/CSTA-Gateways in lync Server 2013](lync-server-2013-define-a-sip-csta-gateway-ip-address.md).</span><span class="sxs-lookup"><span data-stu-id="ae9af-126">For details about defining a SIP/CSTA gateway IP address in Topology Builder, see [Define a SIP/CSTA gateway IP address in Lync Server 2013](lync-server-2013-define-a-sip-csta-gateway-ip-address.md).</span></span>

</div>

<div>

## <a name="step-3-configure-lync-users-for-remote-call-control"></a><span data-ttu-id="ae9af-127">Schritt 3: Konfigurieren von lync-Benutzern für die Remote Anrufsteuerung</span><span class="sxs-lookup"><span data-stu-id="ae9af-127">Step 3: Configure Lync Users for Remote Call Control</span></span>

<span data-ttu-id="ae9af-128">Nachdem Benutzer für lync Server aktiviert wurden, können Sie die lync Server-Systemsteuerung oder die lync Server-Verwaltungsshell verwenden, um Sie für die Remoteanrufsteuerung zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="ae9af-128">After users have been enabled for Lync Server, you can use Lync Server Control Panel or Lync Server Management Shell to enable them for remote call control.</span></span> <span data-ttu-id="ae9af-129">Während dieses bereitstellungsschritts weisen Sie jedem Benutzer einen Leitungsserver-URI und einen Leitungs-URI zu.</span><span class="sxs-lookup"><span data-stu-id="ae9af-129">It is during this deployment step that you assign each user a line server URI and a line URI.</span></span> <span data-ttu-id="ae9af-130">Der URI des Leitungs Servers ist der SIP-URI des SIP/CSTA-Gateways, das Sie dem Benutzer zuweisen möchten.</span><span class="sxs-lookup"><span data-stu-id="ae9af-130">The line server URI is the SIP URI of the SIP/CSTA gateway that you plan to assign to the user.</span></span> <span data-ttu-id="ae9af-131">Der Leitungs-URI ist die eindeutige Telefonnummer, die dem Benutzer zugewiesen ist.</span><span class="sxs-lookup"><span data-stu-id="ae9af-131">The line URI is the unique phone number assigned to the user.</span></span>

<span data-ttu-id="ae9af-132">Details zum Konfigurieren von Benutzern für die Remoteanrufsteuerung finden Sie unter [Aktivieren von lync-Benutzern für die Remoteanrufsteuerung in lync Server 2013](lync-server-2013-enable-lync-users-for-remote-call-control.md).</span><span class="sxs-lookup"><span data-stu-id="ae9af-132">For details about configuring users for remote call control, see [Enable Lync users for remote call control in Lync Server 2013](lync-server-2013-enable-lync-users-for-remote-call-control.md).</span></span>

</div>

<div>

## <a name="step-4-define-the-lync-server-phone-number-normalization-rules"></a><span data-ttu-id="ae9af-133">Schritt 4: Definieren der Normalisierungsregeln für lync Server-Telefonnummern</span><span class="sxs-lookup"><span data-stu-id="ae9af-133">Step 4: Define the Lync Server Phone Number Normalization Rules</span></span>

<span data-ttu-id="ae9af-134">In Szenarien für die Remoteanrufsteuerung verwendet lync Server Telefonnummern-Normalisierungsregeln, um Telefonnummern zu konvertieren, die vom SIP/CSTA-Gateway zum E. 164-Format empfangen werden.</span><span class="sxs-lookup"><span data-stu-id="ae9af-134">In remote call control scenarios, Lync Server uses phone number normalization rules to convert phone numbers it receives from the SIP/CSTA gateway to E.164 format.</span></span> <span data-ttu-id="ae9af-135">Telefonnummern müssen in diesem standardisierten Format vorliegen, damit bestimmte Funktionen für die Remoteanrufsteuerung ordnungsgemäß funktionieren.</span><span class="sxs-lookup"><span data-stu-id="ae9af-135">Phone numbers must be in this standardized format for certain remote call control features to function properly.</span></span> <span data-ttu-id="ae9af-136">Die Remote Anrufsteuerung verwendet die gleichen Regeln für die Telefonnummernnormalisierung, die Sie für die Normalisierung der Telefonnummern für den Adressbuchdienst konfigurieren, die sich von den für Enterprise-VoIP verwendeten Regeln für die Telefonnummer unterscheiden.</span><span class="sxs-lookup"><span data-stu-id="ae9af-136">Remote call control uses the same phone number normalization rules that you configure for Address Book Service phone number normalization, which are different from the phone number normalization rules used for Enterprise Voice.</span></span>

<span data-ttu-id="ae9af-137">Ausführliche Informationen dazu, wie die Remoteanrufsteuerung Telefonnummern-Normalisierungsregeln verwendet, finden Sie unter [Remoteanrufsteuerung und Normalisierung der Telefonnummern in lync Server 2013](lync-server-2013-remote-call-control-and-phone-number-normalization.md).</span><span class="sxs-lookup"><span data-stu-id="ae9af-137">For details about how remote call control uses phone number normalization rules, see [Remote call control and phone number normalization in Lync Server 2013](lync-server-2013-remote-call-control-and-phone-number-normalization.md).</span></span> <span data-ttu-id="ae9af-138">Details zu den Normalisierungsregeln für Telefonnummern für den Adressbuchdienst finden Sie unter [Verwalten des Adressbuchdiensts in lync Server 2013](lync-server-2013-administering-the-address-book-service.md) in der Betriebsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="ae9af-138">For details about phone number normalization rules for Address Book Service, see [Administering the Address Book Service in Lync Server 2013](lync-server-2013-administering-the-address-book-service.md) topic in the Operations documentation.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

