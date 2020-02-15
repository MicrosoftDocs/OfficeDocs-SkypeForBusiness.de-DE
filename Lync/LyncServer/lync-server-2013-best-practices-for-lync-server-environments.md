---
title: 'Lync Server 2013: bewährte Methoden für lync Server Umgebungen'
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
ms.openlocfilehash: d02d9ed669cf9404b1bf8d07db32c9d331769ec9
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42041114"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="best-practices-for-lync-server-2013-environments"></a><span data-ttu-id="7478b-102">Bewährte Methoden für lync Server 2013 Umgebungen</span><span class="sxs-lookup"><span data-stu-id="7478b-102">Best practices for Lync Server 2013 environments</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7478b-103">_**Letztes Änderungsstand des Themas:** 2014-08-04_</span><span class="sxs-lookup"><span data-stu-id="7478b-103">_**Topic Last Modified:** 2014-08-04_</span></span>

<span data-ttu-id="7478b-104">Die folgenden allgemeinen Prinzipien sollten auf den laufenden Betrieb Ihres Systems angewendet werden:</span><span class="sxs-lookup"><span data-stu-id="7478b-104">The following general principles should be applied to ongoing operations of your system:</span></span>

  - <span data-ttu-id="7478b-105">**Das Verständnis und die Verwendung von MOF**   MOF sind eine Sammlung von bewährten Methoden, Grundsätzen und Modellen, die Unternehmen technische Anleitungen zur Verwaltung von IT-Ressourcen bereitstellen, beispielsweise tägliche lync Server 2013 Vorgänge.</span><span class="sxs-lookup"><span data-stu-id="7478b-105">**Understand and utilize MOF**   MOF is a collection of best practices, principles, and models that provide organizations technical guidance about the management of IT assets, such as daily Lync Server 2013 operations.</span></span> <span data-ttu-id="7478b-106">Die folgenden MOF-Richtlinien können Ihnen dabei helfen, die Zuverlässigkeit, Verfügbarkeit, Unterstützung und Verwaltbarkeit von unternehmenskritischen Produktionssystemen für Microsoft-Produkte zu erreichen.</span><span class="sxs-lookup"><span data-stu-id="7478b-106">Following MOF guidelines can help you achieve mission-critical production system reliability, availability, supportability, and manageability for Microsoft products.</span></span> <span data-ttu-id="7478b-107">Weitere Informationen finden Sie unter [Microsoft Operations Framework 4,0](http://go.microsoft.com/fwlink/p/?linkid=40939).</span><span class="sxs-lookup"><span data-stu-id="7478b-107">For more information, see [Microsoft Operations Framework 4.0](http://go.microsoft.com/fwlink/p/?linkid=40939).</span></span>

  - <span data-ttu-id="7478b-108">**Informationen zu bewährten Methoden für lync Server 2013**   es wird empfohlen, praktische und bewährte Verfahren zum Verwalten von lync Server 2013 zu implementieren.</span><span class="sxs-lookup"><span data-stu-id="7478b-108">**Learn about best practices for Lync Server 2013**   We recommend that you implement practical and proven procedures to manage Lync Server 2013.</span></span> <span data-ttu-id="7478b-109">Die Verwendung bewährter, getesteter und dokumentierter Methoden zur Verwaltung von Vorgängen ist möglicherweise effizienter als die Entwicklung eigener Methoden.</span><span class="sxs-lookup"><span data-stu-id="7478b-109">By using tried, tested, and documented methods of managing operations may be more efficient than developing your own methods.</span></span>

  - <span data-ttu-id="7478b-110">**Separate Vorgänge in tägliche, wöchentliche und monatliche Prozesse**   dokumentieren die erforderlichen Betriebsaufgaben, die Sie regelmäßig ausführen.</span><span class="sxs-lookup"><span data-stu-id="7478b-110">**Separate operations into daily, weekly, and monthly processes**   Document the required operational tasks that you'll regularly perform.</span></span> <span data-ttu-id="7478b-111">Durch Dokumentieren der Vorgehensweise können Sie sicherstellen, dass Ihre Informationen beibehalten werden, wenn sich Ihre Betriebsumgebung ändert, beispielsweise wenn neue Technologien bereitgestellt werden oder Änderungen am Personal vorgenommen werden.</span><span class="sxs-lookup"><span data-stu-id="7478b-111">Documenting how you perform tasks helps make sure that your information is preserved when there is a change in your operational environment such as when new technologies are deployed or staff changes occur.</span></span> <span data-ttu-id="7478b-112">Es wird empfohlen, dass Betriebsaufgaben in verwaltbare Arbeitslasten aufgeteilt werden, bei denen Aufgaben täglich, wöchentlich und monatlich ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="7478b-112">We recommend that operational tasks be separated into manageable workloads where tasks are performed daily, weekly, and monthly.</span></span> <span data-ttu-id="7478b-113">Tägliche Aufgaben konzentrieren sich auf die Funktionsweise eines Systems, und monatliche Aufgaben würden sich stärker auf die Sicherstellung der langfristigen Integrität eines Systems konzentrieren.</span><span class="sxs-lookup"><span data-stu-id="7478b-113">Daily tasks would focus efforts on the functioning of a system, and monthly tasks would focus more on ensuring the long-term health of a system.</span></span>
    
    <span data-ttu-id="7478b-114">Dieses Dokument kann in Umgebungen verwendet werden, in denen nur Instant Messaging/Presence-Komponenten (im/p) oder Chat/p mit Enterprise-VoIP bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="7478b-114">This document can be used in environments deploying only instant messaging/presence (IM/P) components or IM/P with Enterprise Voice.</span></span> <span data-ttu-id="7478b-115">Wenn Aufgaben oder Prüflistenelemente für Enterprise-VoIP spezifisch sind, wird dies erwähnt, und wenn Ihre Umgebung nicht Enterprise-VoIP enthält, wird der Teil möglicherweise übersprungen.</span><span class="sxs-lookup"><span data-stu-id="7478b-115">When tasks or checklist items are specific to Enterprise Voice, this is mentioned and if your environment does not include Enterprise Voice the portion may be skipped.</span></span>

  - <span data-ttu-id="7478b-116">**Bereitstellen der Tools, die für den Betrieb erforderlich sind lync Server 2013**   viele Tools stehen zur Verfügung, um Probleme zu beheben, Aufgaben zu automatisieren und die lync Server 2013 Umgebung zu überwachen und zu warten.</span><span class="sxs-lookup"><span data-stu-id="7478b-116">**Deploy the tools that are required for operating Lync Server 2013**   Many tools are available to help troubleshoot issues, automate tasks, and help monitor and maintain the Lync Server 2013 environment.</span></span> <span data-ttu-id="7478b-117">Definieren Sie einen Standardsatz von Tools für Ihre Organisation, damit die Aufgaben, die von dem Betriebsteam ausgeführt werden, genau, effizient, konsistent und kontrolliert ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="7478b-117">Define a standard set of tools for your organization so the tasks that are performed by the operations team are performed accurately, efficiently, consistently, and in a controlled manner.</span></span> <span data-ttu-id="7478b-118">Sie sollten auch Verfahren zum Verfolgen von Vorfällen und größeren Konfigurationsänderungen implementieren.</span><span class="sxs-lookup"><span data-stu-id="7478b-118">You should also implement processes to track incidents and major configuration changes.</span></span>

<div>

## <a name="reference"></a><span data-ttu-id="7478b-119">Referenz</span><span class="sxs-lookup"><span data-stu-id="7478b-119">Reference</span></span>

<span data-ttu-id="7478b-120">Im Hinblick auf Leser, die nicht bereits mit den Grundlagen der Serververwaltung im allgemeinen vertraut sind, bieten wir eine Übersicht über die Server Verwaltungsverfahren.</span><span class="sxs-lookup"><span data-stu-id="7478b-120">For the benefit of readers not already familiar with the basics of server management in general, we provide an overview of server management practices.</span></span> <span data-ttu-id="7478b-121">Leser, die bereits mit der Serververwaltung vertraut sind, können diesen Abschnitt überspringen.</span><span class="sxs-lookup"><span data-stu-id="7478b-121">Readers already familiar with server management may choose to skip this section.</span></span>

<span data-ttu-id="7478b-122">Bewährte Methoden sind Empfehlungen, die auf dem Wissen und der Erfahrung basieren, die IT-Spezialisten in vielen Umgebungen gesammelt haben.</span><span class="sxs-lookup"><span data-stu-id="7478b-122">Best practices are recommendations that are based on the knowledge and experience that IT professionals have gained across many environments.</span></span> <span data-ttu-id="7478b-123">Sie bieten Standardverfahren für typische Aufgaben, die ihre lync Server Administratoren täglich ausführen müssen, und Listen die Tools auf, die Sie zum Verwalten einer lync Server Umgebung verwenden sollten.</span><span class="sxs-lookup"><span data-stu-id="7478b-123">They provide standard procedures for typical tasks that your Lync Server administrators must perform daily, and list the tools that they should use to manage a Lync Server environment.</span></span>

<span data-ttu-id="7478b-124">Zu den typischen Aufgaben für lync-Administratoren gehören folgende:</span><span class="sxs-lookup"><span data-stu-id="7478b-124">Typical tasks for Lync administrators include the following:</span></span>

  - <span data-ttu-id="7478b-125">**Kapazitäts-und Verfügbarkeitsverwaltung**   legen Sie fest, wie und was gemessen werden soll, um künftige Kapazitätsanforderungen vorherzusagen und über die Kapazität, Zuverlässigkeit und Verfügbarkeit Ihrer Systeme zu berichten.</span><span class="sxs-lookup"><span data-stu-id="7478b-125">**Capacity and Availability Management**   Define how and what to measure to predict future capacity requirements and to report about the capacity, reliability, and availability of your systems.</span></span> <span data-ttu-id="7478b-126">Sie müssen sicherstellen, dass die Größe der Server, auf denen lync Server ausgeführt werden, für die Verarbeitung der Systemlast ausgelegt ist und dass ungeplante Ausfallzeiten unter den in der Vereinbarung zum Service Level (SLA) definierten Ebenen aufbewahrt werden.</span><span class="sxs-lookup"><span data-stu-id="7478b-126">You must verify that servers that are running Lync Server are sized to handle the load on the system, and that unplanned downtime is kept under the levels defined in the service level agreement (SLA).</span></span> <span data-ttu-id="7478b-127">Darüber hinaus müssen Sie ein Upgrade der Hardware durchführen, um die definierten Anforderungen weiterhin zu erfüllen.</span><span class="sxs-lookup"><span data-stu-id="7478b-127">Additionally, you'll have to upgrade hardware to continue to meet the defined requirements.</span></span>

  - <span data-ttu-id="7478b-128">**Change Management und Konfigurationsverwaltung**   steuern, wie Änderungen an IT-Systemen vorgenommen werden.</span><span class="sxs-lookup"><span data-stu-id="7478b-128">**Change Management and Configuration Management**   Control how changes are made to IT systems.</span></span> <span data-ttu-id="7478b-129">Dies sollte Tests, Anwendungs Feedback und Notfallpläne, Dokumentation aller Änderungen und Genehmigung von der Verwaltung umfassen, falls Probleme auftreten.</span><span class="sxs-lookup"><span data-stu-id="7478b-129">This should include testing, application feedback and contingency plans, documentation of all changes, and approval from management if issues occur.</span></span> <span data-ttu-id="7478b-130">Speichern Sie Ihre Software-und Hardwareressourcen sowie deren Konfigurationen.</span><span class="sxs-lookup"><span data-stu-id="7478b-130">Keep a record of your software and hardware assets and their configurations.</span></span>

  - <span data-ttu-id="7478b-131">**System Administration**   Übersicht über Standardmethoden für Verwaltungsaufgaben wie Datenbankverwaltung und Websiteverwaltung.</span><span class="sxs-lookup"><span data-stu-id="7478b-131">**System Administration**   Outline standard methods for doing administrative tasks such as database administration and site administration.</span></span>

  - <span data-ttu-id="7478b-132">**Die Sicherheitsverwaltung**   verfügt über eine detaillierte Richtlinie und einen Plan, der die Vertraulichkeit von Daten, die Datenintegrität und die Datenverfügbarkeit der IT-Infrastruktur schützt.</span><span class="sxs-lookup"><span data-stu-id="7478b-132">**Security Administration**   Have a detailed policy and plan that protects data confidentiality, data integrity, and data availability of the IT infrastructure.</span></span> <span data-ttu-id="7478b-133">Dies umfasst alltägliche Aktivitäten und Aufgaben im Zusammenhang mit der Verwaltung und Anpassung der IT-Sicherheitsinfrastruktur.</span><span class="sxs-lookup"><span data-stu-id="7478b-133">This includes day-to-day activities and tasks that are related to maintaining and adjusting the IT security infrastructure.</span></span>

  - <span data-ttu-id="7478b-134">**System Problembehandlung**   : Gliederungs Methoden für den Umgang mit unerwarteten Problemen, einschließlich der Schritte zum verhindern ähnlicher Probleme in der Zukunft.</span><span class="sxs-lookup"><span data-stu-id="7478b-134">**System Troubleshooting**   Outline methods for dealing with unexpected issues, including steps to prevent similar issues in the future.</span></span>

  - <span data-ttu-id="7478b-135">**Vereinbarungen zum Service Level**   halten eine Reihe von Zielen für die Leistung der IT-Systeme aufrecht und Messen regelmäßig die Leistung anhand dieser Ziele.</span><span class="sxs-lookup"><span data-stu-id="7478b-135">**Service Level Agreements**   Maintain a set of goals for the performance of the IT systems and regularly measure performance against these goals.</span></span>

  - <span data-ttu-id="7478b-136">**Dokumentation**   dokumentieren Sie Standardverfahren wie Konfigurationsinformationen und Lessons Learned, und stellen Sie Sie den Mitarbeitern zur Verfügung, die Sie benötigen.</span><span class="sxs-lookup"><span data-stu-id="7478b-136">**Documentation**   Document standard procedures, such as configuration information and lessons learned, and make them available to the staff members that need them.</span></span> <span data-ttu-id="7478b-137">Wenn Änderungen an der Konfiguration vorgenommen werden, aktualisieren Sie die Dokumentation entsprechend.</span><span class="sxs-lookup"><span data-stu-id="7478b-137">As changes to the configuration are made, update the documentation accordingly.</span></span>

</div>

<div>

## <a name="related-sections"></a><span data-ttu-id="7478b-138">Verwandte Abschnitte</span><span class="sxs-lookup"><span data-stu-id="7478b-138">Related Sections</span></span>

<span data-ttu-id="7478b-139">Lesen Sie die folgenden Themen zu Systemvorgängen, bevor Sie fortfahren:</span><span class="sxs-lookup"><span data-stu-id="7478b-139">Review the following topics concerning system operations before proceeding:</span></span>

  - [<span data-ttu-id="7478b-140">Kapazitäts-und Verfügbarkeitsverwaltung in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7478b-140">Capacity and availability management in Lync Server 2013</span></span>](lync-server-2013-capacity-and-availability-management.md)

  - [<span data-ttu-id="7478b-141">Änderungsverwaltung in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7478b-141">Change management in Lync Server 2013</span></span>](lync-server-2013-change-management.md)

  - [<span data-ttu-id="7478b-142">Konfigurationsverwaltung in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7478b-142">Configuration management in Lync Server 2013</span></span>](lync-server-2013-configuration-management.md)

  - [<span data-ttu-id="7478b-143">System Verwaltung in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7478b-143">System administration in Lync Server 2013</span></span>](lync-server-2013-system-administration.md)

  - [<span data-ttu-id="7478b-144">Vereinbarungen zum Service Level in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7478b-144">Service level agreements in Lync Server 2013</span></span>](lync-server-2013-service-level-agreements.md)

  - [<span data-ttu-id="7478b-145">Dokumentation in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7478b-145">Documentation in Lync Server 2013</span></span>](lync-server-2013-documentation.md)

  - [<span data-ttu-id="7478b-146">Standard Verfahren in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7478b-146">Standard procedures in Lync Server 2013</span></span>](lync-server-2013-standard-procedures.md)

  - [<span data-ttu-id="7478b-147">Notfallverfahren in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7478b-147">Emergency procedures in Lync Server 2013</span></span>](lync-server-2013-emergency-procedures.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="7478b-148">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="7478b-148">See Also</span></span>


[<span data-ttu-id="7478b-149">Microsoft Operations Framework 4,0</span><span class="sxs-lookup"><span data-stu-id="7478b-149">Microsoft Operations Framework 4.0</span></span>](http://go.microsoft.com/fwlink/p/?linkid=40939)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

