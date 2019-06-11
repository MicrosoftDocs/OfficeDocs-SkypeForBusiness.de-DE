---
title: 'Lync Server 2013: Überprüfen des Zertifikats Berichts'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Reviewing the Certificates Report
ms:assetid: 549cfc9b-3cc5-4483-a93c-fc0738c7f622
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558651(v=OCS.15)
ms:contentKeyID: 51541477
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4a83167576746d3f90d96658b0dd3d65815f5375
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34822335"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="reviewing-the-certificates-report-in-lync-server-2013"></a><span data-ttu-id="4ff7d-102">Überprüfen des Berichts "Zertifikate" in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4ff7d-102">Reviewing the Certificates Report in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4ff7d-103">_**Letztes Änderungsdatum des Themas:** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="4ff7d-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="4ff7d-104">Der Bericht Zertifikate enthält alle Zertifikate, die in der empfohlenen lync Server 2013-Bereitstellung erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="4ff7d-104">The Certificates Report contains all certificates that are required in the recommended Lync Server 2013 deployment.</span></span> <span data-ttu-id="4ff7d-105">Das Planungs Tool berücksichtigt die eingegebenen Antragstellernamen und alternativen Subjektnamen.</span><span class="sxs-lookup"><span data-stu-id="4ff7d-105">The Planning Tool accounts for the subject names and subject alternative names that are entered.</span></span> <span data-ttu-id="4ff7d-106">Nicht bearbeiteter Standardtext kann eine Herausforderung für das Team darstellen, das für das Anfordern und Ausstellen der Zertifikate verantwortlich ist.</span><span class="sxs-lookup"><span data-stu-id="4ff7d-106">Default text that is left unedited may represent a potential challenge for the team responsible for requesting and issuing the certificates.</span></span> <span data-ttu-id="4ff7d-107">In den Zertifikatinformationen ist zudem angegeben, durch welche Stelle das Zertifikat typischerweise ausgestellt werden kann.</span><span class="sxs-lookup"><span data-stu-id="4ff7d-107">Certificate information also contains information about where the certificate can typically be issued from.</span></span> <span data-ttu-id="4ff7d-108">Wenn die Infrastruktur nicht über eine interne Public Key-Infrastruktur (PKI) verfügt, können sämtliche Zertifikate über einen öffentlichen Zertifikatanbieter angefordert werden.</span><span class="sxs-lookup"><span data-stu-id="4ff7d-108">If the infrastructure does not have an internal public key infrastructure (PKI) in place, all certificates can be requested through a public certificate provider.</span></span> <span data-ttu-id="4ff7d-109">Die Felder „Erweiterte Schlüsselverwendungen“ und „Zuweisen zu“ des Berichts sind äußerst nützlich und liefern Informationen zu Zweck und Speicherort der einzelnen Zertifikate.</span><span class="sxs-lookup"><span data-stu-id="4ff7d-109">Extended key usages (EKU) and Assign To fields in the report are very helpful in understanding what the purpose and location for each certificate should be.</span></span>

<span data-ttu-id="4ff7d-110">![Zertifikat-Administrator Bericht] (images/Gg558651.63a29335-d9e4-41ae-97ec-3c9d9fd30d8a(OCS.15).jpg "Zertifikat-Administrator Bericht")</span><span class="sxs-lookup"><span data-stu-id="4ff7d-110">![Certificates Admin Report](images/Gg558651.63a29335-d9e4-41ae-97ec-3c9d9fd30d8a(OCS.15).jpg "Certificates Admin Report")</span></span>

<span data-ttu-id="4ff7d-111">Überprüfen Sie die Verwendung und den Zweck der einzelnen Zertifikate innerhalb der Bereitstellung sorgfältig und stellen Sie sicher, dass Sie diese Informationen verstanden haben.</span><span class="sxs-lookup"><span data-stu-id="4ff7d-111">Carefully review, and be sure to understand, the use and purpose of each certificate in the deployment.</span></span> <span data-ttu-id="4ff7d-112">Wenn Sie Fragen zum Zweck eines Zertifikats haben, ermitteln Sie, welcher Server oder Dienst mit welcher Komponente kommuniziert.</span><span class="sxs-lookup"><span data-stu-id="4ff7d-112">If there is a question about what a certificate does, determine which server or service is talking to what.</span></span> <span data-ttu-id="4ff7d-113">Zertifikate in lync Server 2013 werden für zwei primäre Zwecke verwendet:</span><span class="sxs-lookup"><span data-stu-id="4ff7d-113">Certificates in Lync Server 2013 are used for two primary purposes:</span></span>

  - <span data-ttu-id="4ff7d-p103">Mutual Transport Layer Security (MTLS) – Die Computer, die miteinander kommunizieren, belegen ihre Identität gegenüber den anderen Computern mithilfe eines Zertifikats. Dieser Vorgang wird als Serverauthentifizierung bezeichnet. Die Kommunikation ist erst möglich, wenn sämtliche Computer die Identität der anderen Computer als vertrauenswürdig eingestuft haben.</span><span class="sxs-lookup"><span data-stu-id="4ff7d-p103">Mutual Transport Layer Security (MTLS) – The computers involved in the communication each present a certificate that proves their identity to another computer. This is known as server authentication. Communication cannot begin until each computer trusts the other computer’s identity.</span></span>

  - <span data-ttu-id="4ff7d-117">Verschlüsselung – Die Verschlüsselung (Secure Sockets Layer, SSL, und Transport Layer Security, TLS) ist eine wichtige Methode, um eine sichere Kommunikation und die Einhaltung von Datenschutzrichtlinien zu gewährleisten sowie ein vertrauenswürdiges System für Kommunikation und Zusammenarbeit zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="4ff7d-117">Encryption – Encryption (Secure Sockets Layer, or SSL, and Transport Layer Security, or TLS) is a critical means to help secure communications, help ensure privacy, and to create a trusted communications and collaboration system.</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="4ff7d-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="4ff7d-118">See Also</span></span>


[<span data-ttu-id="4ff7d-119">Überprüfen der Administratorberichte in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4ff7d-119">Reviewing the Administrator Reports in Lync Server 2013</span></span>](lync-server-2013-reviewing-the-administrator-reports.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

