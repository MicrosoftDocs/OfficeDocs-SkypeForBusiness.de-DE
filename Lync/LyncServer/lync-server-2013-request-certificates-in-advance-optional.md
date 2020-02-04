---
title: 'Lync Server 2013: Vorabanforderung von Zertifikaten (optional)'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Request certificates in advance (optional)
ms:assetid: 9d6d7de6-ff2a-46da-b1b7-a354c8e383e4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412733(v=OCS.15)
ms:contentKeyID: 48184915
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7ee4598f35bb607a9262bfeb7931e2c88e27920c
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41723835"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="request-certificates-in-advance-optional-for-lync-server-2013"></a><span data-ttu-id="64961-102">Vorabanforderung von Zertifikaten (optional) für Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="64961-102">Request certificates in advance (optional) for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="64961-103">_**Letztes Änderungsdatum des Themas:** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="64961-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="64961-104">Zertifikate sind für alle internen Server erforderlich, auf denen lync Server 2013 ausgeführt wird, darunter jeder Enterprise Edition-Front-End-Server, Standard Edition-Server, Director, Edge-Server und eigenständiger Vermittlungsserver.</span><span class="sxs-lookup"><span data-stu-id="64961-104">Certificates are required for all internal servers that are running Lync Server 2013, including each Enterprise Edition Front End Server, Standard Edition server, Director, Edge Server and stand-alone Mediation Server.</span></span> <span data-ttu-id="64961-105">Obwohl eine interne Unternehmenszertifizierungsstelle für interne Server empfohlen wird, können Sie auch eine öffentliche Zertifizierungsstelle verwenden.</span><span class="sxs-lookup"><span data-stu-id="64961-105">Although an internal enterprise certification authority (CA) is recommended for internal servers, you can also use a public CA.</span></span> <span data-ttu-id="64961-106">Ausführliche Informationen zu Zertifikatanforderungen und zur Verwendung einer öffentlichen Zertifizierungsstelle finden Sie unter [Zertifikatanforderungen für interne Server in lync Server 2013](lync-server-2013-certificate-requirements-for-internal-servers.md) in der Planungsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="64961-106">For details about certificate requirements and about the use of a public CA, see [Certificate requirements for internal servers in Lync Server 2013](lync-server-2013-certificate-requirements-for-internal-servers.md) in the Planning documentation.</span></span>

<span data-ttu-id="64961-107">Das Setup von lync Server 2013 umfasst den Zertifikat-Assistenten, der die Aufgaben zum anfordern, zuweisen und Installieren von Zertifikaten während der Bereitstellung vereinfacht.</span><span class="sxs-lookup"><span data-stu-id="64961-107">Lync Server 2013 setup includes the Certificate Wizard, which facilitates the tasks of requesting, assigning, and installing certificates during deployment.</span></span> <span data-ttu-id="64961-108">Wenn Sie vor dem Installieren von Servern Zertifikate anfordern möchten (beispielsweise um Zeit während der eigentlichen Bereitstellung von Servern zu sparen), können Sie dies mithilfe eines Computers, auf dem die lync Server 2013-Verwaltungstools installiert sind, oder mithilfe einer Zertifikatanforderung ausführen. in Ihrer Organisation definierte Prozedur, sofern Sie sicherstellen, dass die Zertifikate exportierbar sind und alle erforderlichen Alternativen Betreff-Namen enthalten.</span><span class="sxs-lookup"><span data-stu-id="64961-108">If you want to request certificates prior to installing servers (for instance, to save time during actual deployment of servers), you can do so by using a computer on which the Lync Server 2013 administrative tools are installed or by using a certificate request procedure defined in your organization, as long as you make sure that the certificates are exportable and contain all the required subject alternative names.</span></span> <span data-ttu-id="64961-109">Das Anfordern von Zertifikaten im Voraus ist optional.</span><span class="sxs-lookup"><span data-stu-id="64961-109">Requesting certificates in advance is optional.</span></span> <span data-ttu-id="64961-110">Wenn Sie diese nicht im Voraus anfordern, müssen Sie Sie im Rahmen der Einrichtung jedes Servers anfordern, für den ein Zertifikat erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="64961-110">If you do not request them in advance, you must request them as part of the setup of each server that requires a certificate.</span></span>

<span data-ttu-id="64961-111">Diese Bereitstellungsdokumentation enthält Verfahren für die Verwendung des Zertifikat-Assistenten zum Anfordern von Zertifikaten als Teil des Setupvorgangs, wie in den Abschnitten [Konfigurieren von Zertifikaten für Server in lync Server 2013](lync-server-2013-configure-certificates-for-servers.md), [Konfigurieren von Zertifikaten für den Director in lync Server 2013](lync-server-2013-configure-certificates-for-the-director.md)und [Installieren der Dateien für den Vermittlungsserver in den Abschnitten lync Server 2013](lync-server-2013-install-the-files-for-mediation-server.md) dieser Bereitstellungsdokumentation beschrieben.</span><span class="sxs-lookup"><span data-stu-id="64961-111">This Deployment documentation provides procedures for using the Certificate Wizard to request certificates as part of the setup process, as described in the [Configure certificates for servers in Lync Server 2013](lync-server-2013-configure-certificates-for-servers.md), [Configure certificates for the Director in Lync Server 2013](lync-server-2013-configure-certificates-for-the-director.md), and [Install the files for Mediation Server in Lync Server 2013](lync-server-2013-install-the-files-for-mediation-server.md) sections of this Deployment documentation.</span></span> <span data-ttu-id="64961-112">Wenn Sie Zertifikate im Voraus anfordern, müssen Sie die Zertifikat Bereitstellungsverfahren in diesen Abschnitten nach Bedarf ändern, um die Zertifikate zu importieren und zuzuweisen, anstatt Sie zum Zeitpunkt der Bereitstellung anzufordern.</span><span class="sxs-lookup"><span data-stu-id="64961-112">If you request certificates in advance, you must modify the certificate deployment procedures in those sections as appropriate to importing and assigning the certificates instead of requesting them at the time of deployment.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="64961-113">Lync Server 2013 enthält Unterstützung für SHA-256-Zertifikate für Verbindungen von Clients, auf denen Windows Vista&nbsp;, Windows Server 2008&nbsp;,&nbsp;Windows Server 2008 R2 und Windows 7-Betriebssysteme und lync Phone Edition ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="64961-113">Lync Server 2013 includes support for SHA-256 certificates for connections from clients running the Windows Vista, Windows Server&nbsp;2008, Windows Server&nbsp;2008&nbsp;R2, and Windows 7 operating systems, and Lync Phone Edition.</span></span> <span data-ttu-id="64961-114">Um den externen Zugriff mithilfe von SHA-256 zu unterstützen, wird das externe Zertifikat von einer öffentlichen Zertifizierungsstelle mithilfe von SHA-256 ausgestellt.</span><span class="sxs-lookup"><span data-stu-id="64961-114">To support external access using SHA-256, the external certificate is issued by a public CA using SHA-256.</span></span>



</div>

</div>

<span> </span>

</div>

</div>

</div>

