---
title: 'Lync Server 2013: Überprüfen des Zertifikats Berichts'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Reviewing the Certificates Report
ms:assetid: 549cfc9b-3cc5-4483-a93c-fc0738c7f622
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558651(v=OCS.15)
ms:contentKeyID: 51541477
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 26a01f778e855fc5934b524c5bf4a5829a2ca31e
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42051559"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="reviewing-the-certificates-report-in-lync-server-2013"></a><span data-ttu-id="0535c-102">Überprüfen des Zertifikat Berichts in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0535c-102">Reviewing the Certificates Report in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0535c-103">_**Letztes Änderungsstand des Themas:** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="0535c-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="0535c-104">Der Zertifikat Bericht enthält alle Zertifikate, die in der empfohlenen lync Server 2013-Bereitstellung erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="0535c-104">The Certificates Report contains all certificates that are required in the recommended Lync Server 2013 deployment.</span></span> <span data-ttu-id="0535c-105">Das Planungs Tool Konten für die eingegebenen Antragstellernamen und alternativen Antragstellernamen.</span><span class="sxs-lookup"><span data-stu-id="0535c-105">The Planning Tool accounts for the subject names and subject alternative names that are entered.</span></span> <span data-ttu-id="0535c-106">Der Standardtext, der unbearbeitet bleibt, stellt möglicherweise eine potenzielle Herausforderung für das Team dar, das für das anfordern und ausgeben der Zertifikate zuständig ist.</span><span class="sxs-lookup"><span data-stu-id="0535c-106">Default text that is left unedited may represent a potential challenge for the team responsible for requesting and issuing the certificates.</span></span> <span data-ttu-id="0535c-107">In den Zertifikatinformationen ist zudem angegeben, von welcher Stelle das Zertifikat typischerweise ausgestellt werden kann.</span><span class="sxs-lookup"><span data-stu-id="0535c-107">Certificate information also contains information about where the certificate can typically be issued from.</span></span> <span data-ttu-id="0535c-108">Wenn die Infrastruktur nicht über eine interne Public Key-Infrastruktur (PKI) verfügt, können sämtliche Zertifikate über einen öffentlichen Zertifikatanbieter angefordert werden.</span><span class="sxs-lookup"><span data-stu-id="0535c-108">If the infrastructure does not have an internal public key infrastructure (PKI) in place, all certificates can be requested through a public certificate provider.</span></span> <span data-ttu-id="0535c-109">Die Felder "Erweiterte Schlüsselverwendungen" und "Zuweisen zu" des Berichts sind äußerst nützlich und liefern Informationen zum Zweck und Speicherort der einzelnen Zertifikate.</span><span class="sxs-lookup"><span data-stu-id="0535c-109">Extended key usages (EKU) and Assign To fields in the report are very helpful in understanding what the purpose and location for each certificate should be.</span></span>

<span data-ttu-id="0535c-110">![Zertifikat Administrator Bericht](images/Gg558651.63a29335-d9e4-41ae-97ec-3c9d9fd30d8a(OCS.15).jpg "Zertifikat Administrator Bericht")</span><span class="sxs-lookup"><span data-stu-id="0535c-110">![Certificates Admin Report](images/Gg558651.63a29335-d9e4-41ae-97ec-3c9d9fd30d8a(OCS.15).jpg "Certificates Admin Report")</span></span>

<span data-ttu-id="0535c-111">Überprüfen Sie sorgfältig die Verwendung und den Zweck jedes Zertifikats in der Bereitstellung, und achten Sie darauf, dass Sie dies verstehen.</span><span class="sxs-lookup"><span data-stu-id="0535c-111">Carefully review, and be sure to understand, the use and purpose of each certificate in the deployment.</span></span> <span data-ttu-id="0535c-112">Wenn es eine Frage zu dem, was ein Zertifikat ist, ermitteln, welche Server oder Dienst mit was gesprochen wird.</span><span class="sxs-lookup"><span data-stu-id="0535c-112">If there is a question about what a certificate does, determine which server or service is talking to what.</span></span> <span data-ttu-id="0535c-113">Zertifikate in lync Server 2013 werden für zwei primäre Zwecke verwendet:</span><span class="sxs-lookup"><span data-stu-id="0535c-113">Certificates in Lync Server 2013 are used for two primary purposes:</span></span>

  - <span data-ttu-id="0535c-114">Mutual Transport Layer Security (MTLS) – die an der Kommunikation beteiligten Computer stellen ein Zertifikat dar, das Ihre Identität für einen anderen Computer prüft.</span><span class="sxs-lookup"><span data-stu-id="0535c-114">Mutual Transport Layer Security (MTLS) – The computers involved in the communication each present a certificate that proves their identity to another computer.</span></span> <span data-ttu-id="0535c-115">Dies wird als Serverauthentifizierung bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="0535c-115">This is known as server authentication.</span></span> <span data-ttu-id="0535c-116">Die Kommunikation kann erst begonnen werden, wenn jeder Computer der Identität des anderen Computers vertraut.</span><span class="sxs-lookup"><span data-stu-id="0535c-116">Communication cannot begin until each computer trusts the other computer’s identity.</span></span>

  - <span data-ttu-id="0535c-117">Verschlüsselung – Die Verschlüsselung (Secure Sockets Layer, SSL, und Transport Layer Security, TLS) ist eine wichtige Methode, um eine sichere Kommunikation und die Einhaltung von Datenschutzrichtlinien zu gewährleisten sowie ein vertrauenswürdiges System für Kommunikation und Zusammenarbeit zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="0535c-117">Encryption – Encryption (Secure Sockets Layer, or SSL, and Transport Layer Security, or TLS) is a critical means to help secure communications, help ensure privacy, and to create a trusted communications and collaboration system.</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="0535c-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="0535c-118">See Also</span></span>


[<span data-ttu-id="0535c-119">Überprüfen der Administrator Berichte in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0535c-119">Reviewing the Administrator Reports in Lync Server 2013</span></span>](lync-server-2013-reviewing-the-administrator-reports.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

