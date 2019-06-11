---
title: 'Lync Server 2013: Einrichten der Zertifikate für den Reverseproxy'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Set up certificates for the reverse proxy
ms:assetid: c03a08ec-a67b-4f11-b0d7-6677461beaaa
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412938(v=OCS.15)
ms:contentKeyID: 48185291
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: be12aabd8c4d7aa026e6c7e1ab6f1d5189a596c8
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34821929"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="set-up-certificates-for-the-reverse-proxy-in-lync-server-2013"></a><span data-ttu-id="59796-102">Einrichten der Zertifikate für den Reverseproxy in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="59796-102">Set up certificates for the reverse proxy in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="59796-103">_**Letztes Änderungsdatum des Themas:** 2012-09-08_</span><span class="sxs-lookup"><span data-stu-id="59796-103">_**Topic Last Modified:** 2012-09-08_</span></span>

<span data-ttu-id="59796-104">Für jeden Reverse-Proxy Server ist ein Webserverzertifikat zur Verwendung durch den Überwachungsdienst erforderlich.</span><span class="sxs-lookup"><span data-stu-id="59796-104">Each reverse proxy server requires a web server certificate for use by the listening service.</span></span> <span data-ttu-id="59796-105">Das Webserverzertifikat muss von einer öffentlichen Zertifizierungsstelle (Certification Authority, ca) ausgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="59796-105">The web server certificate must be issued by a public certification authority (CA).</span></span>

<span data-ttu-id="59796-106">Ausführliche Informationen zu diesen und anderen Zertifikatanforderungen finden Sie unter [Zertifikatanforderungen für den Zugriff durch externe Benutzer in lync Server 2013](lync-server-2013-certificate-requirements-for-external-user-access.md).</span><span class="sxs-lookup"><span data-stu-id="59796-106">For details about this and other certificate requirements, see [Certificate requirements for external user access in Lync Server 2013](lync-server-2013-certificate-requirements-for-external-user-access.md).</span></span>

<div>

## <a name="to-set-up-a-web-services-certificate-for-the-reverse-proxy"></a><span data-ttu-id="59796-107">So richten Sie ein Webdienste-Zertifikat für den Reverse-Proxy ein</span><span class="sxs-lookup"><span data-stu-id="59796-107">To set up a Web Services certificate for the reverse proxy</span></span>

  - <span data-ttu-id="59796-108">Sie sollten ihren Reverse-Proxy bereits eingerichtet haben, einschließlich der Einrichtung des Webdienste-Zertifikats.</span><span class="sxs-lookup"><span data-stu-id="59796-108">You should have already set up your reverse proxy, including setting up the Web Services certificate.</span></span> <span data-ttu-id="59796-109">Wenn Sie dies nicht getan haben, bevor Sie die Bereitstellung Ihrer Edgeserver gestartet haben, verwenden Sie die Verfahren unter [Einrichten von Reverse-Proxyservern für lync Server 2013](lync-server-2013-setting-up-reverse-proxy-servers.md) , um die Anforderung zu erstellen und das Webdienst Zertifikat zu installieren, und erstellen Sie dann jede Webveröffentlichungsregel, und Konfigurieren Sie die Anwendung für die Verwendung des Zertifikats.</span><span class="sxs-lookup"><span data-stu-id="59796-109">If you did not do so before starting your deployment of your Edge Servers, use the procedures in [Setting up reverse proxy servers for Lync Server 2013](lync-server-2013-setting-up-reverse-proxy-servers.md) to create request and install the Web Services certificate, and then create each web publishing rule and configure it to use the certificate.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

