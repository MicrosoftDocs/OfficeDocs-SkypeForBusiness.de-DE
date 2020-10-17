---
title: 'Lync Server 2013: Front-End-Pool koppeln von Datensicherheit'
description: 'Lync Server 2013: Front-End-Pool kopplungsdaten Sicherheit.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Front End pool pairing data security
ms:assetid: edb852b8-ea86-4948-b756-60fe6ee876d2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721930(v=OCS.15)
ms:contentKeyID: 49733865
ms.date: 10/07/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 32a2ce72752819392429c8407649e663494f1daf
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48567131"
---
# <a name="front-end-pool-pairing-data-security-in-lync-server-2013"></a><span data-ttu-id="8be86-103">Front-End-Pool koppeln von Datensicherheit in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8be86-103">Front End pool pairing data security in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8be86-104">_**Letztes Änderungsstand des Themas:** 2014-10-07_</span><span class="sxs-lookup"><span data-stu-id="8be86-104">_**Topic Last Modified:** 2014-10-07_</span></span>

<span data-ttu-id="8be86-105">Der Sicherungsdienst ist ein in lync Server 2013 eingeführter Datenreplikationsmechanismus, der Benutzerdaten und Konferenzinhalte zwischen zwei gekoppelten Front-End-Pools kontinuierlich über zwei Rechenzentren zur Notfallwiederherstellung überträgt.</span><span class="sxs-lookup"><span data-stu-id="8be86-105">The Backup Service is a data replication mechanism introduced in Lync Server 2013 that transfers user data and conference content between two paired Front End pools continuously across two data centers for disaster recovery purposes.</span></span> <span data-ttu-id="8be86-106">Die Benutzerdaten enthalten Benutzer-SIP-URIs sowie Kontaktlisten und-Einstellungen.</span><span class="sxs-lookup"><span data-stu-id="8be86-106">The user data contains user SIP URIs as well as contact lists and settings.</span></span> <span data-ttu-id="8be86-107">Konferenzinhalte umfassen Microsoft PowerPoint 2010 Uploads sowie Whiteboards, die in Konferenzen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="8be86-107">Conference content includes Microsoft PowerPoint 2010 uploads, as well as whiteboards used in conferences.</span></span> <span data-ttu-id="8be86-108">Aus dem Quell Pool werden Benutzerdaten und Konferenzinhalte aus dem lokalen Speicher exportiert, gezippt, an den Ziel Pool übertragen, wo er entpackt und in den lokalen Speicher importiert wird.</span><span class="sxs-lookup"><span data-stu-id="8be86-108">From the source pool, user data and conference content are exported from the local storage, zipped, transferred to the target Pool, where it is unzipped and imported to local storage.</span></span> <span data-ttu-id="8be86-109">Der Sicherungsdienst geht davon aus, dass sich die Kommunikationsverbindungzwischen den beiden Rechenzentren innerhalb des Unternehmensnetzwerks befindet, das vor dem Internet geschützt ist.</span><span class="sxs-lookup"><span data-stu-id="8be86-109">The Backup Service assumes that the communications link between the two data centers is within the corporate network that is protected from the Internet.</span></span> <span data-ttu-id="8be86-110">Die übertragenen Daten zwischen den beiden Rechenzentren werden nicht verschlüsselt, noch ist Sie nativ in ein sicheres Protokoll wie HTTPS gekapselt.</span><span class="sxs-lookup"><span data-stu-id="8be86-110">It does not encrypt the transferred data between the two data centers, nor is it natively encapsulated within a secure protocol, such as HTTPS.</span></span> <span data-ttu-id="8be86-111">Daher ist ein man-in-the-Middle-Angriff von internen Mitarbeitern innerhalb des Unternehmensnetzwerks möglich.</span><span class="sxs-lookup"><span data-stu-id="8be86-111">Therefore, man-in-the-middle attack from internal personnel within the corporate network is possible.</span></span>

<div>

## <a name="evaluating-security-risks"></a><span data-ttu-id="8be86-112">Bewerten von Sicherheitsrisiken</span><span class="sxs-lookup"><span data-stu-id="8be86-112">Evaluating Security Risks</span></span>

<span data-ttu-id="8be86-113">Jedes Unternehmen, das lync Server 2013 in mehreren Rechenzentren bereitstellt und die Notfallwiederherstellungsfunktion verwendet, muss sicherstellen, dass der datenbankübergreifende Datenverkehr durch das Unternehmens Intranet geschützt ist.</span><span class="sxs-lookup"><span data-stu-id="8be86-113">Any enterprise which deploys Lync Server 2013 across multiple data centers and uses the disaster recovery feature must ensure that cross-data center traffic is protected by their corporate Intranet.</span></span> <span data-ttu-id="8be86-114">Unternehmen, die ihren Datenverkehr vor internen Angriffen schützen möchten, müssen die Kommunikationsverbindungen zwischen den Rechenzentren schützen.</span><span class="sxs-lookup"><span data-stu-id="8be86-114">Enterprises which care about internal attack protection must secure the communication links among the data centers.</span></span>

<span data-ttu-id="8be86-p103">Es ist eine weit verbreitete Annahme, dass Rechenzentren eines Unternehmens hinter dem firmeneigenen Intranet geschützt sind. Viele andere Arten von vertraulichen Unternehmensdaten werden ebenfalls zwischen diesen Rechenzentren übertragen. Die IT-Infrastruktur des Unternehmens ist massiv gefährdet, wenn diese rechenzentrenübergreifenden Verbindungen nicht geschützt werden.</span><span class="sxs-lookup"><span data-stu-id="8be86-p103">The assumption that data centers of an enterprise are protected behind the corporate Intranet is standard. There are many other types of corporate sensitive data transferred among these data centers. The enterprise’s IT infrastructure is at dire risk if these cross-data center links are not protected.</span></span>

<span data-ttu-id="8be86-p104">Das Risiko von Man-in-the-Middle-Angriffen innerhalb des Unternehmensnetzwerks besteht zwar, doch ist es im Vergleich zur Gefährdung des Datenverkehrs im Internet relativ begrenzt. Insbesondere die Benutzerdaten, die vom Sicherungsdienst verfügbar gemacht werden (z. B. SIP-URIs), sind für alle Mitarbeiter im Unternehmen über andere Mittel wie etwa das globale Adressbuch von Exchange oder andere Verzeichnissoftware allgemein verfügbar. Daher sollte der Schwerpunkt auf dem Schutz des WANs zwischen den beiden Rechenzentren liegen, wenn der Sicherungsdienst zum Kopieren von Daten zwischen einem Poolpaar verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="8be86-p104">While the risk of man-in-the-middle attacks within the corporate network exists, it is relatively contained as compared to exposing the traffic to the Internet. Specifically, the user data exposed by Backup Service (such as SIP URIs) are generally available to all employees within the company via other means such as the Global Address Book by Exchange or other directory software. Hence, the focus should be on securing the WAN between the two data centers when the Backup Service is used to copy data between the two paired Pools.</span></span>

</div>

<div>

## <a name="mitigating-security-risks"></a><span data-ttu-id="8be86-121">Minimieren von Sicherheitsrisiken</span><span class="sxs-lookup"><span data-stu-id="8be86-121">Mitigating Security Risks</span></span>

<span data-ttu-id="8be86-122">Es gibt viele Möglichkeiten, den Sicherheitsschutz für den Sicherungsdienst Datenverkehr zu verbessern, angefangen beim Einschränken des Zugriffs auf die Rechenzentren bis hin zum Sichern des WAN-Transports zwischen den beiden Rechenzentren.</span><span class="sxs-lookup"><span data-stu-id="8be86-122">There are many ways to enhance security protection for the Backup Service traffic, ranging from restricting access to the data centers to securing the WAN transport between the two data centers.</span></span> <span data-ttu-id="8be86-123">In den meisten Fällen verfügen Unternehmen, die lync Server 2013 bereitstellen, möglicherweise bereits über die erforderliche Sicherheitsinfrastruktur.</span><span class="sxs-lookup"><span data-stu-id="8be86-123">In most cases, enterprises deploying Lync Server 2013 might already have the required security infrastructure in place.</span></span> <span data-ttu-id="8be86-124">Für Unternehmen, die nach Anleitungen suchen, stellt Microsoft die Lösung als Beispiel für die Erstellung einer sicheren IT-Infrastruktur bereit.</span><span class="sxs-lookup"><span data-stu-id="8be86-124">For enterprises looking for guidance, Microsoft provides solution as an example of how to build a secure IT infrastructure.</span></span> <span data-ttu-id="8be86-125">Dies impliziert jedoch nicht, dass es sich um die einzige Lösung handelt, auch nicht, dass es die bevorzugte Lösung für lync Server ist.</span><span class="sxs-lookup"><span data-stu-id="8be86-125">However, this does not imply that it is the only solution, nor does it imply that it is the preferred solution for Lync Server.</span></span> <span data-ttu-id="8be86-126">Es wird empfohlen, dass Unternehmenskunden basierend auf Ihrer IT-Sicherheitsinfrastruktur und-Anforderungen die Lösung auswählen, die ihren spezifischen Anforderungen entspricht. In der Microsoft-Beispiellösung werden IPSec-und Gruppenrichtlinien für die Server-und Domänenisolierung verwendet.</span><span class="sxs-lookup"><span data-stu-id="8be86-126">We recommend that enterprise customers choose the solution suits their specific needs, based on their IT security infrastructure and requirements.The example Microsoft solution employs IPSec and Group Policy for Server and Domain Isolation.</span></span> <span data-ttu-id="8be86-127">Ausführliche Informationen finden Sie unter [https://go.microsoft.com/fwlink/p/?LinkId=268544](https://go.microsoft.com/fwlink/p/?linkid=268544) .</span><span class="sxs-lookup"><span data-stu-id="8be86-127">For details, see [https://go.microsoft.com/fwlink/p/?LinkId=268544](https://go.microsoft.com/fwlink/p/?linkid=268544).</span></span> <span data-ttu-id="8be86-128">Wenden Sie sich bei Fragen und Kommentaren an SecWish@Microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="8be86-128">For questions and comments, contact secwish@microsoft.com.</span></span>

<span data-ttu-id="8be86-129">Eine weitere mögliche Lösung besteht in der Verwendung von IPSec, um die vom Sicherungsdienst selbst gesendeten Daten zu schützen.</span><span class="sxs-lookup"><span data-stu-id="8be86-129">Another possible solution is to use IPSec just to help secure the data sent by the Backup Service itself.</span></span> <span data-ttu-id="8be86-130">Wenn Sie diese Methode auswählen, sollten Sie die IPSec-Regeln für das SMB-Protokoll für die folgenden Server konfigurieren, wobei Pool a und Pool B zwei gekoppelte Front-End-Pools sind.</span><span class="sxs-lookup"><span data-stu-id="8be86-130">If you choose this method, you should configure the IPSec rules for the SMB protocol for the following servers, where Pool A and Pool B are two paired Front End pools.</span></span>

  - <span data-ttu-id="8be86-131">Der SMB-Dienst (TCP/445) von jeder Front-End-Server in Pool a auf die Dateispeicher, die von Pool B verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="8be86-131">The SMB Service (TCP/445) from each Front End Server in Pool A to the File Store used by Pool B.</span></span>

  - <span data-ttu-id="8be86-132">Der SMB-Dienst (TCP/445) von jeder Front-End-Server in Pool B zu der Dateispeicher, die von Pool A verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="8be86-132">The SMB Service (TCP/445) from each Front End Server in Pool B to the File Store used by Pool A.</span></span>

<div>


> [!WARNING]  
> <span data-ttu-id="8be86-133">IPSec ist nicht als Ersatz für die Sicherheit auf Anwendungsebene wie SSL/TLS gedacht.</span><span class="sxs-lookup"><span data-stu-id="8be86-133">IPsec is not intended as a replacement for application-level security, such as SSL/TLS.</span></span> <span data-ttu-id="8be86-134">Ein Vorteil der Verwendung von IPSec besteht darin, dass Sie die Sicherheit von Netzwerkdatenverkehr für vorhandene Anwendungen bereitstellen kann, ohne Sie ändern zu müssen.</span><span class="sxs-lookup"><span data-stu-id="8be86-134">One advantage of using IPsec is that it can provide network traffic security for existing applications without having to change them.</span></span> <span data-ttu-id="8be86-135">Unternehmen, die lediglich den Transport zwischen den beiden Rechenzentren sichern möchten, sollten ihre jeweiligen Netzwerkhardware Anbieter über die Möglichkeiten zum Einrichten sicherer WAN-Verbindungen mithilfe der Geräte des Herstellers konsultieren.</span><span class="sxs-lookup"><span data-stu-id="8be86-135">Enterprises that want to just secure the transport between the two data centers should consult their respective networking hardware vendors about ways to set up secure WAN connections by using the vendor’s equipment.</span></span>



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

