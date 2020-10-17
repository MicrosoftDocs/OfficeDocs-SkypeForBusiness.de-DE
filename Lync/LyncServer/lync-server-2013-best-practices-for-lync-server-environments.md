---
title: 'Lync Server 2013: bewährte Methoden für lync Server Umgebungen'
description: 'Lync Server 2013: bewährte Methoden für lync Server Umgebungen.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Best practices for Lync Server environments
ms:assetid: b0e45d84-09c8-4d3e-aad0-bc6f34ce233b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720348(v=OCS.15)
ms:contentKeyID: 63969642
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ae6c02621bd6506d2a1d379aeaf92b20ce3f7ae1
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48552211"
---
# <a name="best-practices-for-lync-server-2013-environments"></a><span data-ttu-id="9a100-103">Bewährte Methoden für lync Server 2013 Umgebungen</span><span class="sxs-lookup"><span data-stu-id="9a100-103">Best practices for Lync Server 2013 environments</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9a100-104">_**Letztes Änderungsstand des Themas:** 2014-08-04_</span><span class="sxs-lookup"><span data-stu-id="9a100-104">_**Topic Last Modified:** 2014-08-04_</span></span>

<span data-ttu-id="9a100-105">Die folgenden allgemeinen Prinzipien sollten auf den laufenden Betrieb Ihres Systems angewendet werden:</span><span class="sxs-lookup"><span data-stu-id="9a100-105">The following general principles should be applied to ongoing operations of your system:</span></span>

  - <span data-ttu-id="9a100-106">**Verstehen und Verwenden von MOF**     MOF ist eine Sammlung von bewährten Methoden, Grundsätzen und Modellen, die Unternehmen technische Anleitungen zur Verwaltung von IT-Ressourcen bereitstellen, beispielsweise tägliche lync Server 2013 Vorgänge.</span><span class="sxs-lookup"><span data-stu-id="9a100-106">**Understand and utilize MOF**   MOF is a collection of best practices, principles, and models that provide organizations technical guidance about the management of IT assets, such as daily Lync Server 2013 operations.</span></span> <span data-ttu-id="9a100-107">Die folgenden MOF-Richtlinien können Ihnen dabei helfen, die Zuverlässigkeit, Verfügbarkeit, Unterstützung und Verwaltbarkeit von unternehmenskritischen Produktionssystemen für Microsoft-Produkte zu erreichen.</span><span class="sxs-lookup"><span data-stu-id="9a100-107">Following MOF guidelines can help you achieve mission-critical production system reliability, availability, supportability, and manageability for Microsoft products.</span></span> <span data-ttu-id="9a100-108">Weitere Informationen finden Sie unter [Microsoft Operations Framework 4,0](https://go.microsoft.com/fwlink/p/?linkid=40939).</span><span class="sxs-lookup"><span data-stu-id="9a100-108">For more information, see [Microsoft Operations Framework 4.0](https://go.microsoft.com/fwlink/p/?linkid=40939).</span></span>

  - <span data-ttu-id="9a100-109">Informationen **zu bewährten Methoden für lync Server 2013**     Es wird empfohlen, praktische und bewährte Verfahren zum Verwalten von lync Server 2013 zu implementieren.</span><span class="sxs-lookup"><span data-stu-id="9a100-109">**Learn about best practices for Lync Server 2013**   We recommend that you implement practical and proven procedures to manage Lync Server 2013.</span></span> <span data-ttu-id="9a100-110">Die Verwendung bewährter, getesteter und dokumentierter Methoden zur Verwaltung von Vorgängen ist möglicherweise effizienter als die Entwicklung eigener Methoden.</span><span class="sxs-lookup"><span data-stu-id="9a100-110">By using tried, tested, and documented methods of managing operations may be more efficient than developing your own methods.</span></span>

  - <span data-ttu-id="9a100-111">**Separate Vorgänge in tägliche, wöchentliche und monatliche Prozesse**     Dokumentieren Sie die erforderlichen Betriebsaufgaben, die Sie regelmäßig ausführen.</span><span class="sxs-lookup"><span data-stu-id="9a100-111">**Separate operations into daily, weekly, and monthly processes**   Document the required operational tasks that you'll regularly perform.</span></span> <span data-ttu-id="9a100-112">Durch Dokumentieren der Vorgehensweise können Sie sicherstellen, dass Ihre Informationen beibehalten werden, wenn sich Ihre Betriebsumgebung ändert, beispielsweise wenn neue Technologien bereitgestellt werden oder Änderungen am Personal vorgenommen werden.</span><span class="sxs-lookup"><span data-stu-id="9a100-112">Documenting how you perform tasks helps make sure that your information is preserved when there is a change in your operational environment such as when new technologies are deployed or staff changes occur.</span></span> <span data-ttu-id="9a100-113">Es wird empfohlen, dass Betriebsaufgaben in verwaltbare Arbeitslasten aufgeteilt werden, bei denen Aufgaben täglich, wöchentlich und monatlich ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="9a100-113">We recommend that operational tasks be separated into manageable workloads where tasks are performed daily, weekly, and monthly.</span></span> <span data-ttu-id="9a100-114">Tägliche Aufgaben konzentrieren sich auf die Funktionsweise eines Systems, und monatliche Aufgaben würden sich stärker auf die Sicherstellung der langfristigen Integrität eines Systems konzentrieren.</span><span class="sxs-lookup"><span data-stu-id="9a100-114">Daily tasks would focus efforts on the functioning of a system, and monthly tasks would focus more on ensuring the long-term health of a system.</span></span>
    
    <span data-ttu-id="9a100-115">Dieses Dokument kann in Umgebungen verwendet werden, in denen nur Instant Messaging/Presence-Komponenten (im/p) oder Chat/p mit Enterprise-VoIP bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="9a100-115">This document can be used in environments deploying only instant messaging/presence (IM/P) components or IM/P with Enterprise Voice.</span></span> <span data-ttu-id="9a100-116">Wenn Aufgaben oder Prüflistenelemente für Enterprise-VoIP spezifisch sind, wird dies erwähnt, und wenn Ihre Umgebung nicht Enterprise-VoIP enthält, wird der Teil möglicherweise übersprungen.</span><span class="sxs-lookup"><span data-stu-id="9a100-116">When tasks or checklist items are specific to Enterprise Voice, this is mentioned and if your environment does not include Enterprise Voice the portion may be skipped.</span></span>

  - <span data-ttu-id="9a100-117">**Bereitstellen der für den Betriebs lync Server 2013**     erforderlichen Tools Es stehen zahlreiche Tools zur Verfügung, mit denen Sie Probleme beheben, Aufgaben automatisieren und die lync Server 2013 Umgebung überwachen und warten können.</span><span class="sxs-lookup"><span data-stu-id="9a100-117">**Deploy the tools that are required for operating Lync Server 2013**   Many tools are available to help troubleshoot issues, automate tasks, and help monitor and maintain the Lync Server 2013 environment.</span></span> <span data-ttu-id="9a100-118">Definieren Sie einen Standardsatz von Tools für Ihre Organisation, damit die Aufgaben, die von dem Betriebsteam ausgeführt werden, genau, effizient, konsistent und kontrolliert ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="9a100-118">Define a standard set of tools for your organization so the tasks that are performed by the operations team are performed accurately, efficiently, consistently, and in a controlled manner.</span></span> <span data-ttu-id="9a100-119">Sie sollten auch Verfahren zum Verfolgen von Vorfällen und größeren Konfigurationsänderungen implementieren.</span><span class="sxs-lookup"><span data-stu-id="9a100-119">You should also implement processes to track incidents and major configuration changes.</span></span>

<div>

## <a name="reference"></a><span data-ttu-id="9a100-120">Referenz</span><span class="sxs-lookup"><span data-stu-id="9a100-120">Reference</span></span>

<span data-ttu-id="9a100-121">Im Hinblick auf Leser, die nicht bereits mit den Grundlagen der Serververwaltung im allgemeinen vertraut sind, bieten wir eine Übersicht über die Server Verwaltungsverfahren.</span><span class="sxs-lookup"><span data-stu-id="9a100-121">For the benefit of readers not already familiar with the basics of server management in general, we provide an overview of server management practices.</span></span> <span data-ttu-id="9a100-122">Leser, die bereits mit der Serververwaltung vertraut sind, können diesen Abschnitt überspringen.</span><span class="sxs-lookup"><span data-stu-id="9a100-122">Readers already familiar with server management may choose to skip this section.</span></span>

<span data-ttu-id="9a100-123">Bewährte Methoden sind Empfehlungen, die auf dem Wissen und der Erfahrung basieren, die IT-Spezialisten in vielen Umgebungen gesammelt haben.</span><span class="sxs-lookup"><span data-stu-id="9a100-123">Best practices are recommendations that are based on the knowledge and experience that IT professionals have gained across many environments.</span></span> <span data-ttu-id="9a100-124">Sie bieten Standardverfahren für typische Aufgaben, die ihre lync Server Administratoren täglich ausführen müssen, und Listen die Tools auf, die Sie zum Verwalten einer lync Server Umgebung verwenden sollten.</span><span class="sxs-lookup"><span data-stu-id="9a100-124">They provide standard procedures for typical tasks that your Lync Server administrators must perform daily, and list the tools that they should use to manage a Lync Server environment.</span></span>

<span data-ttu-id="9a100-125">Zu den typischen Aufgaben für lync-Administratoren gehören folgende:</span><span class="sxs-lookup"><span data-stu-id="9a100-125">Typical tasks for Lync administrators include the following:</span></span>

  - <span data-ttu-id="9a100-126">**Kapazitäts-und Verfügbarkeitsverwaltung**     Definieren Sie, wie und was gemessen werden soll, um zukünftige Kapazitätsanforderungen vorherzusagen, und Berichten Sie über die Kapazität, Zuverlässigkeit und Verfügbarkeit Ihrer Systeme.</span><span class="sxs-lookup"><span data-stu-id="9a100-126">**Capacity and Availability Management**   Define how and what to measure to predict future capacity requirements and to report about the capacity, reliability, and availability of your systems.</span></span> <span data-ttu-id="9a100-127">Sie müssen sicherstellen, dass die Größe der Server, auf denen lync Server ausgeführt werden, für die Verarbeitung der Systemlast ausgelegt ist und dass ungeplante Ausfallzeiten unter den in der Vereinbarung zum Service Level (SLA) definierten Ebenen aufbewahrt werden.</span><span class="sxs-lookup"><span data-stu-id="9a100-127">You must verify that servers that are running Lync Server are sized to handle the load on the system, and that unplanned downtime is kept under the levels defined in the service level agreement (SLA).</span></span> <span data-ttu-id="9a100-128">Darüber hinaus müssen Sie ein Upgrade der Hardware durchführen, um die definierten Anforderungen weiterhin zu erfüllen.</span><span class="sxs-lookup"><span data-stu-id="9a100-128">Additionally, you'll have to upgrade hardware to continue to meet the defined requirements.</span></span>

  - <span data-ttu-id="9a100-129">**Change Management und Konfigurationsverwaltung**     Steuern, wie Änderungen an IT-Systemen vorgenommen werden.</span><span class="sxs-lookup"><span data-stu-id="9a100-129">**Change Management and Configuration Management**   Control how changes are made to IT systems.</span></span> <span data-ttu-id="9a100-130">Dies sollte Tests, Anwendungs Feedback und Notfallpläne, Dokumentation aller Änderungen und Genehmigung von der Verwaltung umfassen, falls Probleme auftreten.</span><span class="sxs-lookup"><span data-stu-id="9a100-130">This should include testing, application feedback and contingency plans, documentation of all changes, and approval from management if issues occur.</span></span> <span data-ttu-id="9a100-131">Speichern Sie Ihre Software-und Hardwareressourcen sowie deren Konfigurationen.</span><span class="sxs-lookup"><span data-stu-id="9a100-131">Keep a record of your software and hardware assets and their configurations.</span></span>

  - <span data-ttu-id="9a100-132">**System Administration**     Skizzieren Sie Standardmethoden für administrative Aufgaben wie Datenbankverwaltung und Websiteverwaltung.</span><span class="sxs-lookup"><span data-stu-id="9a100-132">**System Administration**   Outline standard methods for doing administrative tasks such as database administration and site administration.</span></span>

  - <span data-ttu-id="9a100-133">**Sicherheitsverwaltung**     Verfügen über eine detaillierte Richtlinie und einen Plan, der die Vertraulichkeit von Daten, die Datenintegrität und die Datenverfügbarkeit der IT-Infrastruktur schützt.</span><span class="sxs-lookup"><span data-stu-id="9a100-133">**Security Administration**   Have a detailed policy and plan that protects data confidentiality, data integrity, and data availability of the IT infrastructure.</span></span> <span data-ttu-id="9a100-134">Dies umfasst alltägliche Aktivitäten und Aufgaben im Zusammenhang mit der Verwaltung und Anpassung der IT-Sicherheitsinfrastruktur.</span><span class="sxs-lookup"><span data-stu-id="9a100-134">This includes day-to-day activities and tasks that are related to maintaining and adjusting the IT security infrastructure.</span></span>

  - <span data-ttu-id="9a100-135">**System Problembehandlung**     Gliederungs Methoden für den Umgang mit unerwarteten Problemen, einschließlich der Schritte zum verhindern ähnlicher Probleme in der Zukunft.</span><span class="sxs-lookup"><span data-stu-id="9a100-135">**System Troubleshooting**   Outline methods for dealing with unexpected issues, including steps to prevent similar issues in the future.</span></span>

  - <span data-ttu-id="9a100-136">Vereinbarungen zum Service **Level**     Verwalten Sie eine Reihe von Zielen für die Leistung der IT-Systeme, und Messen Sie die Leistung regelmäßig anhand dieser Ziele.</span><span class="sxs-lookup"><span data-stu-id="9a100-136">**Service Level Agreements**   Maintain a set of goals for the performance of the IT systems and regularly measure performance against these goals.</span></span>

  - <span data-ttu-id="9a100-137">**Dokumentation**     Dokumentieren Sie Standardverfahren wie Konfigurationsinformationen und Lessons Learned, und stellen Sie Sie den Mitarbeitern zur Verfügung, die Sie benötigen.</span><span class="sxs-lookup"><span data-stu-id="9a100-137">**Documentation**   Document standard procedures, such as configuration information and lessons learned, and make them available to the staff members that need them.</span></span> <span data-ttu-id="9a100-138">Wenn Änderungen an der Konfiguration vorgenommen werden, aktualisieren Sie die Dokumentation entsprechend.</span><span class="sxs-lookup"><span data-stu-id="9a100-138">As changes to the configuration are made, update the documentation accordingly.</span></span>

</div>

<div>

## <a name="related-sections"></a><span data-ttu-id="9a100-139">Verwandte Abschnitte</span><span class="sxs-lookup"><span data-stu-id="9a100-139">Related Sections</span></span>

<span data-ttu-id="9a100-140">Lesen Sie die folgenden Themen zu Systemvorgängen, bevor Sie fortfahren:</span><span class="sxs-lookup"><span data-stu-id="9a100-140">Review the following topics concerning system operations before proceeding:</span></span>

  - [<span data-ttu-id="9a100-141">Kapazitäts-und Verfügbarkeitsverwaltung in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9a100-141">Capacity and availability management in Lync Server 2013</span></span>](lync-server-2013-capacity-and-availability-management.md)

  - [<span data-ttu-id="9a100-142">Änderungsverwaltung in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9a100-142">Change management in Lync Server 2013</span></span>](lync-server-2013-change-management.md)

  - [<span data-ttu-id="9a100-143">Konfigurationsverwaltung in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9a100-143">Configuration management in Lync Server 2013</span></span>](lync-server-2013-configuration-management.md)

  - [<span data-ttu-id="9a100-144">System Verwaltung in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9a100-144">System administration in Lync Server 2013</span></span>](lync-server-2013-system-administration.md)

  - [<span data-ttu-id="9a100-145">Vereinbarungen zum Service Level in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9a100-145">Service level agreements in Lync Server 2013</span></span>](lync-server-2013-service-level-agreements.md)

  - [<span data-ttu-id="9a100-146">Dokumentation in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9a100-146">Documentation in Lync Server 2013</span></span>](lync-server-2013-documentation.md)

  - [<span data-ttu-id="9a100-147">Standard Verfahren in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9a100-147">Standard procedures in Lync Server 2013</span></span>](lync-server-2013-standard-procedures.md)

  - [<span data-ttu-id="9a100-148">Notfallverfahren in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9a100-148">Emergency procedures in Lync Server 2013</span></span>](lync-server-2013-emergency-procedures.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="9a100-149">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="9a100-149">See Also</span></span>


[<span data-ttu-id="9a100-150">Microsoft Operations Framework 4,0</span><span class="sxs-lookup"><span data-stu-id="9a100-150">Microsoft Operations Framework 4.0</span></span>](https://go.microsoft.com/fwlink/p/?linkid=40939)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

