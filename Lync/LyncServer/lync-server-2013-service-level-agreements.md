---
title: 'Lync Server 2013: Vereinbarungen zum Service Level'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Service level agreements
ms:assetid: 10899bad-e8b0-422d-83c9-1599fb3a7d17
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720321(v=OCS.15)
ms:contentKeyID: 63969580
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e96edf9fe2fefb54e608ee6840cfb2717c92d136
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42048996"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="service-level-agreements-in-lync-server-2013"></a><span data-ttu-id="0f7b4-102">Vereinbarungen zum Service Level in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0f7b4-102">Service level agreements in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0f7b4-103">_**Letztes Änderungsstand des Themas:** 2014-08-18_</span><span class="sxs-lookup"><span data-stu-id="0f7b4-103">_**Topic Last Modified:** 2014-08-18_</span></span>

<span data-ttu-id="0f7b4-104">Bei der SLA handelt es sich um ein Dokument, das die Dienste definiert, die Ihr Kunde von Ihnen erwartet.</span><span class="sxs-lookup"><span data-stu-id="0f7b4-104">The SLA is a document that defines the services that your customer expects from you.</span></span> <span data-ttu-id="0f7b4-105">Die Komplexität und der Inhalt dieses Dokuments hängen weitgehend davon ab, ob Kunden intern (in Ihrer Umgebung) oder extern sind.</span><span class="sxs-lookup"><span data-stu-id="0f7b4-105">The complexity and content of this document depends largely on whether customers are internal (within your environment) or external.</span></span>

<div>

## <a name="external-customers"></a><span data-ttu-id="0f7b4-106">Externe Kunden</span><span class="sxs-lookup"><span data-stu-id="0f7b4-106">External Customers</span></span>

<span data-ttu-id="0f7b4-107">Wenn Ihr Kunde extern ist, kann die SLA Teil eines rechtlichen Vertrags mit finanziellen Anreizen und Strafen für Leistung sein, die innerhalb oder außerhalb definierter Dienstebenen liegt.</span><span class="sxs-lookup"><span data-stu-id="0f7b4-107">If your customer is external, the SLA may be part of a legal contract with financial incentives and penalties for performance that falls inside or outside defined levels of service.</span></span> <span data-ttu-id="0f7b4-108">Das Definieren dieser Dienstebenen sollte Teil der gesamten Vertragsverhandlung sein.</span><span class="sxs-lookup"><span data-stu-id="0f7b4-108">Defining these levels of service should be part of the overall contract negotiation.</span></span>

<span data-ttu-id="0f7b4-109">Wie bei allen Verträgen ist es wichtig, dass beide Parteien die Erwartungen verstehen.</span><span class="sxs-lookup"><span data-stu-id="0f7b4-109">As with all contracts, it’s important that both parties understand expectations.</span></span> <span data-ttu-id="0f7b4-110">Die SLA definiert diese Erwartungen.</span><span class="sxs-lookup"><span data-stu-id="0f7b4-110">The SLA defines these expectations.</span></span> <span data-ttu-id="0f7b4-111">Der Inhalt des Dokuments sollte unregelmäßig und nur aufgrund von Verhandlungen mit dem Kunden geändert werden.</span><span class="sxs-lookup"><span data-stu-id="0f7b4-111">The contents of the document should change infrequently and only because of negotiations with the customer.</span></span>

</div>

<div>

## <a name="internal-customers"></a><span data-ttu-id="0f7b4-112">Interne Kunden</span><span class="sxs-lookup"><span data-stu-id="0f7b4-112">Internal Customers</span></span>

<span data-ttu-id="0f7b4-113">Wenn Ihr Kunde intern ist, möchten Sie möglicherweise dennoch die Dienste definieren, die von Operations Teams und von IT-Systemen erwartet werden.</span><span class="sxs-lookup"><span data-stu-id="0f7b4-113">If your customer is internal, you may still want to define the services that are expected of operations teams and of IT systems.</span></span> <span data-ttu-id="0f7b4-114">Die SLA kann vom Betriebsmitarbeiter erstellt und als eine Reihe von Zielen für die Verfügbarkeit von IT-Diensten in Ihrer Organisation gedacht werden.</span><span class="sxs-lookup"><span data-stu-id="0f7b4-114">The SLA may be created by the operations staff and intended as a set of goals for the availability of IT services within your organization.</span></span> <span data-ttu-id="0f7b4-115">Oder Leistungsstufen können von der Verwaltung festgelegt und als Benchmarks bei der Bewertung der Leistung des Personals verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="0f7b4-115">Or, performance levels may be set by management and used as benchmarks when assessing staff performance.</span></span>

</div>

<div>

## <a name="typical-criteria"></a><span data-ttu-id="0f7b4-116">Typische Kriterien</span><span class="sxs-lookup"><span data-stu-id="0f7b4-116">Typical Criteria</span></span>

<span data-ttu-id="0f7b4-117">SLAs umfassen Abschnitte, die Kriterien für mindestverfügbarkeits Stufen, Support und Kapazität definieren.</span><span class="sxs-lookup"><span data-stu-id="0f7b4-117">SLAs include sections that define criteria of minimum levels of availability, support, and capacity.</span></span>

  - <span data-ttu-id="0f7b4-118">**Verfügbarkeit**   definieren Sie die Stunden und Betriebssysteme, auf denen Websites und andere lync-Dienste verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="0f7b4-118">**Availability**   Define the hours and the operating systems on which sites and other Lync services will be available.</span></span> <span data-ttu-id="0f7b4-119">Alle Routinewartungen, die sich auf die Dienstverfügbarkeit auswirken, sollten definiert werden.</span><span class="sxs-lookup"><span data-stu-id="0f7b4-119">Any routine maintenance that affects service availability should be defined.</span></span> <span data-ttu-id="0f7b4-120">Definieren Sie externe Faktoren, die sich auf den Dienst auswirken, beispielsweise den Verlust der Internet Konnektivität.</span><span class="sxs-lookup"><span data-stu-id="0f7b4-120">Define external factors that affect service, for example, the loss of Internet connectivity.</span></span>

  - <span data-ttu-id="0f7b4-121">**Unterstützung**   definieren Sie die Zeiten, in denen die Unterstützung für ein System verfügbar sein wird.</span><span class="sxs-lookup"><span data-stu-id="0f7b4-121">**Support**   Define the hours when support for a system will be available.</span></span> <span data-ttu-id="0f7b4-122">Geben Sie Methoden an, mit denen Kunden sich an das Support Team wenden können, wie Vorfälle gruppiert werden, und welche Zeit für eine Antwort und zur Lösung des Vorfalls gelten soll.</span><span class="sxs-lookup"><span data-stu-id="0f7b4-122">Specify methods for customers to contact support staff, how incidents are grouped, and target time to respond and to resolve the incident.</span></span> <span data-ttu-id="0f7b4-123">Definieren Sie die Häufigkeit und den Inhalt von Feedback für den Kunden.</span><span class="sxs-lookup"><span data-stu-id="0f7b4-123">Define frequency and content of feedback to the customer.</span></span>

  - <span data-ttu-id="0f7b4-124">**Kapazität**   definieren Sie die maximal aktivierte Größe von lync-Websites und die erforderlichen Schritte, wenn der Grenzwert überschritten wird.</span><span class="sxs-lookup"><span data-stu-id="0f7b4-124">**Capacity**   Define the maximum enabled size of Lync sites and the steps to take if the limit is exceeded.</span></span> <span data-ttu-id="0f7b4-125">Definieren Sie die maximal aktivierte Zeit für Standardaufgaben, beispielsweise die Zeit zum Abrufen eines Dokuments aus einer Dokumentbibliothek.</span><span class="sxs-lookup"><span data-stu-id="0f7b4-125">Define the maximum enabled time to do standard tasks, such as the time to retrieve a document from a document library.</span></span> <span data-ttu-id="0f7b4-126">Definieren Sie die maximale Anzahl von Benutzern pro lync-Pool, und stimmen Sie einem Prozess zu, um die Kapazität zu verbessern, wenn mehr Benutzer hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="0f7b4-126">Define the maximum number of users per Lync pool and agree to a process to increase capacity if more users are added.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

