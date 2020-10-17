---
title: 'Lync Server 2013: Software Voraussetzungen für Enterprise-VoIP'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Software prerequisites for Enterprise Voice
ms:assetid: 41172119-9631-46c7-9d9f-386d951c650b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425916(v=OCS.15)
ms:contentKeyID: 48183960
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5b504c498b2f07915f741e6c3172e911c7d40dae
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/16/2020
ms.locfileid: "48519622"
---
# <a name="software-prerequisites-for-enterprise-voice-in-lync-server-2013"></a><span data-ttu-id="ca866-102">Software Voraussetzungen für Enterprise-VoIP in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ca866-102">Software prerequisites for Enterprise Voice in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ca866-103">_**Letztes Änderungsstand des Themas:** 2012-10-03_</span><span class="sxs-lookup"><span data-stu-id="ca866-103">_**Topic Last Modified:** 2012-10-03_</span></span>

<span data-ttu-id="ca866-104">Stellen Sie sicher, dass die zur Bereitstellung von Enterprise-VoIP vorgesehene Infrastruktur die folgenden Softwareanforderungen erfüllt:</span><span class="sxs-lookup"><span data-stu-id="ca866-104">Verify that the infrastructure in which you intend to deploy Enterprise Voice meets the following software prerequisites:</span></span>

  - <span data-ttu-id="ca866-105">Lync Server 2013 Standard Edition oder Enterprise Edition ist in Ihrem Netzwerk installiert und betriebsbereit.</span><span class="sxs-lookup"><span data-stu-id="ca866-105">Lync Server 2013 Standard Edition or Enterprise Edition is installed and operational on your network.</span></span>

  - <span data-ttu-id="ca866-106">Alle Edgeserver werden in Ihrem Umkreisnetzwerk bereitgestellt und in Betrieb genommen, einschließlich Edgeserver mit Zugriffs-Edgedienst, A/V-Edgedienst, Webkonferenz-Edgedienst und einem Reverseproxy.</span><span class="sxs-lookup"><span data-stu-id="ca866-106">All Edge Servers are deployed and operational in your perimeter network, including Edge Servers running Access Edge service, A/V Edge service, Web Conferencing Edge service, and a reverse proxy.</span></span>

  - <span data-ttu-id="ca866-107">Entweder Microsoft Exchange Server 2007 Service Pack 3 (SP3), Microsoft Exchange Server 2010 oder Microsoft Exchange Server 2013 ist für die Integration von Exchange Unified Messaging mit lync Server erforderlich, und es müssen umfangreiche Benachrichtigungen und Anrufprotokoll Informationen für die lync-Endpunkte bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="ca866-107">Either Microsoft Exchange Server 2007 Service Pack 3 (SP3), Microsoft Exchange Server 2010 or Microsoft Exchange Server 2013 is required for integrating Exchange Unified Messaging with Lync Server and to provide rich notifications and call log information to the Lync endpoints.</span></span>

  - <span data-ttu-id="ca866-108">Mindestens ein Benutzer wurde für lync Server erstellt und aktiviert.</span><span class="sxs-lookup"><span data-stu-id="ca866-108">One or more users have been created and enabled for Lync Server.</span></span>

  - <span data-ttu-id="ca866-109">Lync-Clients und-Geräte wurden erfolgreich bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="ca866-109">Lync clients and devices have been successfully deployed.</span></span>

  - <span data-ttu-id="ca866-110">Der Topologie-Generator wird auf einem Server in Ihrem Netzwerk installiert.</span><span class="sxs-lookup"><span data-stu-id="ca866-110">Topology Builder is installed on a server on your network.</span></span>

<div>

## <a name="next-steps-verify-security-and-configuration-prerequisites"></a><span data-ttu-id="ca866-111">Nächste Schritte: Überprüfen der Anforderungen an Sicherheit und Konfiguration</span><span class="sxs-lookup"><span data-stu-id="ca866-111">Next Steps: Verify Security and Configuration Prerequisites</span></span>

<span data-ttu-id="ca866-112">Nachdem Sie sich vergewissert haben, dass die Softwareanforderungen für Enterprise-VoIP erfüllt wurden, können Sie anhand der folgenden Dokumentation die Bereitstellung von Enterprise-VoIP weiter vorbereiten:</span><span class="sxs-lookup"><span data-stu-id="ca866-112">After verifying software prerequisites for Enterprise Voice, you can use the documentation to continue preparing for deploying Enterprise Voice:</span></span>

1.  <span data-ttu-id="ca866-113">Überprüfen Sie die Sicherheit, Benutzerkonfiguration und Hardware Vergünstigungen, wie unter [Sicherheits-und Konfigurationsvoraussetzungen für Enterprise-VoIP in lync Server 2013](lync-server-2013-security-and-configuration-prerequisites-for-enterprise-voice.md)beschrieben.</span><span class="sxs-lookup"><span data-stu-id="ca866-113">Verify security, user configuration, and hardware perquisites, as described in [Security and configuration prerequisites for Enterprise Voice in Lync Server 2013](lync-server-2013-security-and-configuration-prerequisites-for-enterprise-voice.md).</span></span>

2.  <span data-ttu-id="ca866-114">Installieren Sie die Vermittlungsserver, wie in [Installieren der Dateien für Vermittlungsserver in lync Server 2013](lync-server-2013-install-the-files-for-mediation-server.md)beschrieben, jedoch *nur* , wenn Sie eine eigenständige Vermittlungsserver oder einen Pool bereitstellen möchten, da Vermittlungsserver im Rahmen des Front-End-Pool-oder Standard Edition-Server Bereitstellungsprozesses installiert werden.</span><span class="sxs-lookup"><span data-stu-id="ca866-114">Install the Mediation Server, as described in [Install the files for Mediation Server in Lync Server 2013](lync-server-2013-install-the-files-for-mediation-server.md), but *only* if you want to deploy a stand-alone Mediation Server or pool because Mediation Servers are installed as part of the Front End pool or Standard Edition server deployment process when collocated.</span></span>

3.  <span data-ttu-id="ca866-115">Konfigurieren Sie trunk Verbindungen für die Bereitstellung der PSTN-Konnektivität für Benutzer, wie unter [Configuring Trunks in lync Server 2013](lync-server-2013-configuring-trunks.md)beschrieben.</span><span class="sxs-lookup"><span data-stu-id="ca866-115">Configure trunk connections to provide PSTN connectivity for users, as described in [Configuring trunks in Lync Server 2013](lync-server-2013-configuring-trunks.md).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

