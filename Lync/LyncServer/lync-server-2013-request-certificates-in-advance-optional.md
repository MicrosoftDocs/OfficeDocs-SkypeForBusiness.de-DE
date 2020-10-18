---
title: 'Lync Server 2013: Anfordern von Zertifikaten im Voraus (optional)'
description: 'Lync Server 2013: fordern Sie Zertifikate vorab an (optional).'
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
ms.openlocfilehash: 7d92ac9b68012487d07f25f08649689611117202
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48579031"
---
# <a name="request-certificates-in-advance-optional-for-lync-server-2013"></a><span data-ttu-id="1ea55-103">Anfordern von Zertifikaten im Voraus (optional) für lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1ea55-103">Request certificates in advance (optional) for Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1ea55-104">_**Letztes Änderungsstand des Themas:** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="1ea55-104">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="1ea55-105">Zertifikate sind für alle internen Server mit lync Server 2013 erforderlich, einschließlich der einzelnen Enterprise Edition-Front-End-Server, Standard Edition-Server, Director, Edgeserver und eigenständigen Vermittlungsserver.</span><span class="sxs-lookup"><span data-stu-id="1ea55-105">Certificates are required for all internal servers that are running Lync Server 2013, including each Enterprise Edition Front End Server, Standard Edition server, Director, Edge Server and stand-alone Mediation Server.</span></span> <span data-ttu-id="1ea55-106">Wenngleich für interne Server die Verwendung einer internen Unternehmenszertifizierungsstelle empfohlen wird, können Sie auch eine öffentliche Zertifizierungsstelle verwenden.</span><span class="sxs-lookup"><span data-stu-id="1ea55-106">Although an internal enterprise certification authority (CA) is recommended for internal servers, you can also use a public CA.</span></span> <span data-ttu-id="1ea55-107">Ausführliche Informationen zu Zertifikatanforderungen und zur Verwendung einer öffentlichen Zertifizierungsstelle finden Sie unter [Zertifikatanforderungen für interne Server in lync Server 2013](lync-server-2013-certificate-requirements-for-internal-servers.md) in der Planungsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="1ea55-107">For details about certificate requirements and about the use of a public CA, see [Certificate requirements for internal servers in Lync Server 2013](lync-server-2013-certificate-requirements-for-internal-servers.md) in the Planning documentation.</span></span>

<span data-ttu-id="1ea55-108">Lync Server 2013-Setup umfasst den Zertifikat-Assistenten, der die Aufgaben zum anfordern, zuweisen und Installieren von Zertifikaten während der Bereitstellung erleichtert.</span><span class="sxs-lookup"><span data-stu-id="1ea55-108">Lync Server 2013 setup includes the Certificate Wizard, which facilitates the tasks of requesting, assigning, and installing certificates during deployment.</span></span> <span data-ttu-id="1ea55-109">Wenn Sie Zertifikate vor dem Installieren von Servern anfordern möchten (beispielsweise, um Zeit bei der tatsächlichen Bereitstellung von Servern zu sparen), können Sie dies über einen Computer verwenden, auf dem die lync Server 2013 Verwaltungstools installiert sind, oder indem Sie ein in Ihrer Organisation definiertes Zertifikat Anforderungsverfahren verwenden, solange Sie sicherstellen, dass die Zertifikate exportierbar sind und alle erforderlichen alternativen Antragstellernamen enthalten.</span><span class="sxs-lookup"><span data-stu-id="1ea55-109">If you want to request certificates prior to installing servers (for instance, to save time during actual deployment of servers), you can do so by using a computer on which the Lync Server 2013 administrative tools are installed or by using a certificate request procedure defined in your organization, as long as you make sure that the certificates are exportable and contain all the required subject alternative names.</span></span> <span data-ttu-id="1ea55-110">Das Anfordern von Zertifikaten im Voraus ist optional.</span><span class="sxs-lookup"><span data-stu-id="1ea55-110">Requesting certificates in advance is optional.</span></span> <span data-ttu-id="1ea55-111">Wenn Sie diese nicht im Voraus anfordern, müssen Sie Sie im Rahmen der Einrichtung jedes Servers anfordern, für den ein Zertifikat erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="1ea55-111">If you do not request them in advance, you must request them as part of the setup of each server that requires a certificate.</span></span>

<span data-ttu-id="1ea55-112">In dieser Bereitstellungsdokumentation finden Sie Verfahren für die Verwendung des Zertifikat-Assistenten zum Anfordern von Zertifikaten als Teil des Installationsvorgangs, wie im Abschnitt [Konfigurieren von Zertifikaten für Server in lync Server 2013](lync-server-2013-configure-certificates-for-servers.md)beschrieben, [Konfigurieren von Zertifikaten für den Director in lync Server 2013](lync-server-2013-configure-certificates-for-the-director.md)und [Installieren der Dateien für Vermittlungsserver in lync Server 2013](lync-server-2013-install-the-files-for-mediation-server.md) Abschnitten dieser Bereitstellungsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="1ea55-112">This Deployment documentation provides procedures for using the Certificate Wizard to request certificates as part of the setup process, as described in the [Configure certificates for servers in Lync Server 2013](lync-server-2013-configure-certificates-for-servers.md), [Configure certificates for the Director in Lync Server 2013](lync-server-2013-configure-certificates-for-the-director.md), and [Install the files for Mediation Server in Lync Server 2013](lync-server-2013-install-the-files-for-mediation-server.md) sections of this Deployment documentation.</span></span> <span data-ttu-id="1ea55-113">Wenn Sie Zertifikate vorab anfordern, müssen Sie die Zertifikat Bereitstellungsverfahren in diesen Abschnitten entsprechend dem Importieren und Zuweisen der Zertifikate ändern, anstatt Sie zum Zeitpunkt der Bereitstellung anzufordern.</span><span class="sxs-lookup"><span data-stu-id="1ea55-113">If you request certificates in advance, you must modify the certificate deployment procedures in those sections as appropriate to importing and assigning the certificates instead of requesting them at the time of deployment.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="1ea55-114">Lync Server 2013 enthält Unterstützung für SHA-256-Zertifikate für Verbindungen von Clients, auf denen die Windows Vista, Windows Server &nbsp; 2008, Windows Server &nbsp; 2008 &nbsp; R2 und Windows 7-Betriebssysteme sowie lync Phone Edition ausführen.</span><span class="sxs-lookup"><span data-stu-id="1ea55-114">Lync Server 2013 includes support for SHA-256 certificates for connections from clients running the Windows Vista, Windows Server&nbsp;2008, Windows Server&nbsp;2008&nbsp;R2, and Windows 7 operating systems, and Lync Phone Edition.</span></span> <span data-ttu-id="1ea55-115">Damit der externe Zugriff über SHA-256 unterstützt wird, wird das externe Zertifikat von einer öffentlichen Zertifizierungsstelle ausgestellt, die SHA-256 verwendet.</span><span class="sxs-lookup"><span data-stu-id="1ea55-115">To support external access using SHA-256, the external certificate is issued by a public CA using SHA-256.</span></span>



</div>

</div>

<span> </span>

</div>

</div>

</div>

