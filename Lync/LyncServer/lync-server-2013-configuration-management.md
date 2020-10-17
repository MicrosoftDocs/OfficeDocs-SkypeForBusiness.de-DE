---
title: 'Lync Server 2013: Konfigurationsverwaltung'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuration management
ms:assetid: 00ea1196-cb40-427f-99a4-5e8037cbf367
ms:mtpsurl: https://technet.microsoft.com/library/Dn720316(v=OCS.15)
ms:contentKeyID: 63969570
ms.date: 05/16/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: de390f21c76a9636fc9ba2d6a7d3ee017681b6ba
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/16/2020
ms.locfileid: "48507832"
---
# <a name="configuration-management-in-lync-server-2013"></a><span data-ttu-id="cd78e-102">Konfigurationsverwaltung in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="cd78e-102">Configuration management in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="cd78e-103">_**Letztes Änderungsstand des Themas:** 2015-05-15_</span><span class="sxs-lookup"><span data-stu-id="cd78e-103">_**Topic Last Modified:** 2015-05-15_</span></span>

<span data-ttu-id="cd78e-104">Bei der Konfigurationsverwaltung handelt es sich um den Vorgang der Aufzeichnung und Nachverfolgung von Hardware-und Softwareobjekten sowie Systemkonfigurationsinformationen.</span><span class="sxs-lookup"><span data-stu-id="cd78e-104">Configuration management is the process of recording and tracking hardware and software assets and system configuration information.</span></span> <span data-ttu-id="cd78e-105">Er wird in der Regel zum Nachverfolgen von Softwarelizenzen, zum Verwalten einer Standardhardware und-Software für Clientcomputer und-Server und zum Definieren von Benennungsstandards für neue Computer verwendet.</span><span class="sxs-lookup"><span data-stu-id="cd78e-105">It is generally used to track software licenses, maintain a standard hardware and software build for client computers and servers, and define naming standards for new computers.</span></span> <span data-ttu-id="cd78e-106">Die Konfigurationsverwaltung umfasst im Allgemeinen die folgenden Kategorien:</span><span class="sxs-lookup"><span data-stu-id="cd78e-106">Configuration management generally covers the following categories:</span></span>

  - <span data-ttu-id="cd78e-107">**Hardware**     In dieser Kategorie werden die Geräte aufgeführt, die die IT-Organisation besitzt, wo sich Geräte befinden und wer Geräte verwendet.</span><span class="sxs-lookup"><span data-stu-id="cd78e-107">**Hardware**   This category tracks the pieces of equipment that the IT organization owns, where equipment is located, and who uses equipment.</span></span> <span data-ttu-id="cd78e-108">Mithilfe dieser Informationen kann eine Organisation Upgrades planen und budgetieren, Standardhardware-Builds erstellen, den Wert von IT-Ressourcen für Kontoführungs Zwecke melden und Diebstahl verhindern.</span><span class="sxs-lookup"><span data-stu-id="cd78e-108">This information enables an organization to plan and budget for upgrades, maintain standard hardware builds, report on the value of IT assets for accounting purposes, and help prevent theft.</span></span>

  - <span data-ttu-id="cd78e-109">**Software**     In dieser Kategorie werden Software verfolgt, die auf jedem Computer installiert ist, die Versionsnummern und wo die Lizenzen aufbewahrt werden.</span><span class="sxs-lookup"><span data-stu-id="cd78e-109">**Software**   This category tracks software that is installed on each computer, the version numbers, and where the licenses are held.</span></span> <span data-ttu-id="cd78e-110">Mithilfe dieser Informationen können Sie Upgrades planen, sicherstellen, dass Software lizenziert ist, und das vorhanden sein von nicht autorisierten (und nicht lizenzierten) Software erkennen.</span><span class="sxs-lookup"><span data-stu-id="cd78e-110">This information helps plan upgrades, to ensure that software is licensed, and detect the presence of unauthorized (and unlicensed) software.</span></span>

  - <span data-ttu-id="cd78e-111">**Standard-Builds**     In dieser Kategorie wird der aktuelle Standard Build für die Clientcomputer und Server nachverfolgt, und ob die Clientcomputer und Server diesen Standard erfüllen.</span><span class="sxs-lookup"><span data-stu-id="cd78e-111">**Standard Builds**   This category tracks the current standard build for the client computers and servers and whether the client computers and servers meet this standard.</span></span> <span data-ttu-id="cd78e-112">Das definieren und Erzwingen von Standard Builds unterstützt die Mitarbeiter, da die Mitarbeiter nur eine beschränkte Anzahl von Versionen jeder Software aufbewahren müssen.</span><span class="sxs-lookup"><span data-stu-id="cd78e-112">Defining and enforcing standard builds helps support staff because the staff is required to maintain only a limited number of versions of each piece of software.</span></span>

  - <span data-ttu-id="cd78e-113">**Kumulative Updates und Hotfixes**     In dieser Kategorie wird nachverfolgt, welche Service Packs getestet und für die Verwendung genehmigt wurden und welche Computer auf dem neuesten Stand sind.</span><span class="sxs-lookup"><span data-stu-id="cd78e-113">**Cumulative Updates and Hotfixes**   This category tracks which service packs are tested and approved for use and which computers are up to date.</span></span> <span data-ttu-id="cd78e-114">Diese Informationen sind wichtig, um das Risiko zu verringern, dass Computer kompromittiert werden, und um Benutzer zu erkennen, die nicht genehmigte Updates installiert haben.</span><span class="sxs-lookup"><span data-stu-id="cd78e-114">This information is important to reduce the risk of computers being compromised and to detect users who have installed unapproved updates.</span></span>

  - <span data-ttu-id="cd78e-115">Informationen zur System **Konfiguration**     In dieser Kategorie werden die Funktionen eines Systems, die Interaktion zwischen Systemelementen und die Prozesse verfolgt, die von einem reibungslos ausgeführten System abhängen.</span><span class="sxs-lookup"><span data-stu-id="cd78e-115">**System Configuration Information**   This category tracks the function of a system, the interaction between system elements, and the processes that depend on a system that is running smoothly.</span></span> <span data-ttu-id="cd78e-116">Beispielsweise kann ein Drittanbieter-Proxy Server auf einem einzelnen Server konfiguriert werden.</span><span class="sxs-lookup"><span data-stu-id="cd78e-116">For example, third-party proxy server may be configured on a single server.</span></span> <span data-ttu-id="cd78e-117">Die Abhängigkeit des Proxyservers auf diesem Server sollte verstanden werden, und Notfallpläne sind möglicherweise erforderlich, wenn ein Fehler aufgetreten ist.</span><span class="sxs-lookup"><span data-stu-id="cd78e-117">The proxy server’s dependence on this server should be understood and contingency plans may be required if there is a failure.</span></span> <span data-ttu-id="cd78e-118">Wenn der Proxy Server so konfiguriert werden kann, dass er auch mit einem anderen Front-End-Server kommuniziert, ändern sich wahrscheinlich Abhängigkeiten und Notfallpläne.</span><span class="sxs-lookup"><span data-stu-id="cd78e-118">If the proxy server can be configured to also communicate with another front-end server, dependencies and contingency plans will probably change.</span></span>

<div>

## <a name="implementing-configuration-management"></a><span data-ttu-id="cd78e-119">Implementieren der Konfigurationsverwaltung</span><span class="sxs-lookup"><span data-stu-id="cd78e-119">Implementing configuration management</span></span>

<span data-ttu-id="cd78e-120">Nachdem Sie festgestellt haben, welche Elemente verwaltet werden müssen, implementieren Sie die Konfigurationsverwaltung durch das Sammeln von Daten und Berichtsdaten.</span><span class="sxs-lookup"><span data-stu-id="cd78e-120">After you determine what items need managing, implement configuration management by collecting data and reporting data.</span></span> <span data-ttu-id="cd78e-121">Der einfachste Ansatz für kleine Organisationen besteht darin, Daten manuell zu erfassen (Anzahl und Modell von Clientcomputern, Betriebssystem, installierte Software) und in einem Office Word-oder Office Excel-Dokument zu speichern.</span><span class="sxs-lookup"><span data-stu-id="cd78e-121">The simplest approach for small organizations is to collect data manually (number and model of client computers, operating system, installed software) and save it in an Office Word or Office Excel document.</span></span> <span data-ttu-id="cd78e-122">Für größere, komplexere und sich ständig verändernde Systeme müssen die Ermittlung von Objekten und die Sammlung detaillierter Informationen automatisiert werden.</span><span class="sxs-lookup"><span data-stu-id="cd78e-122">For larger, more complex, and constantly changing systems, the discovery of assets and collection of detailed information must be automated.</span></span> <span data-ttu-id="cd78e-123">Entscheiden Sie, welche Informationen für Ihre Organisation relevant sind, und zeichnen Sie Sie in einer Datenbank auf.</span><span class="sxs-lookup"><span data-stu-id="cd78e-123">Decide what information is relevant to your organization and record it in a database.</span></span>

<span data-ttu-id="cd78e-124">Die Konfigurationsverwaltungsdatenbank ist ein nützliches Tool für Supportmitarbeiter und-Verwaltung in den folgenden Bereichen:</span><span class="sxs-lookup"><span data-stu-id="cd78e-124">The configuration management database is a useful tool for support staff and management in the following areas:</span></span>

  - <span data-ttu-id="cd78e-125">**Sicherheitsüberprüfungen**     Mit der Datenbank können Sie Server identifizieren, auf denen lync Server-und Clientcomputer Systeme ausgeführt werden, auf denen Hotfixes angewendet werden müssen oder die die Installation eines Service Packs oder der neuesten Antiviren-Updates verpasst haben.</span><span class="sxs-lookup"><span data-stu-id="cd78e-125">**Security Audits**   The database enables you to identify servers that are running Lync Server and client computer systems that must have hotfixes applied or that have missed the installation of a service pack or the latest antivirus updates.</span></span>

  - <span data-ttu-id="cd78e-126">**Software Installation**     Das Identifizieren von Client Softwareversionen und deren Nachverfolgung unterstützt Administratoren beim Planen von Versionsupdates und neuen Installationen sowie bei der Lizenzierung von Dokumentationen und der Compliance.</span><span class="sxs-lookup"><span data-stu-id="cd78e-126">**Software Installation**   Identifying client software versions and tracking them will aid administrators in planning version updates and new installs and also by helping with licensing documentation and compliance.</span></span>

  - <span data-ttu-id="cd78e-127">**Konfigurationsinformationen**     Wenn Sie eine aktuelle Liste aller Einstellungen beibehalten, die von ihrem Standardwert geändert wurden, können Sie Probleme schnell und effektiver behandeln.</span><span class="sxs-lookup"><span data-stu-id="cd78e-127">**Configuration Information**   If you maintain an up-to-date list of all settings that were changed from their default, then you'll be able to troubleshoot issues quickly and more effectively.</span></span>

  - <span data-ttu-id="cd78e-128">**Planen von Upgrades**     Wenn bei einer Kapazitätsüberprüfung zusätzlicher Speicherplatz auf Ihren lync-Datenbankservern erforderlich ist, müssen Sie unbedingt wissen, ob jeder Server über einen internen RAID-Controller verfügt.</span><span class="sxs-lookup"><span data-stu-id="cd78e-128">**Planning Upgrades**   If a capacity review reveals that additional storage space is required on your Lync database servers, it’s important to know whether each server has an internal RAID controller.</span></span> <span data-ttu-id="cd78e-129">Wenn dies der Fall ist, handelt es sich dabei um das gleiche Modell?</span><span class="sxs-lookup"><span data-stu-id="cd78e-129">If they do, then are they the same model?</span></span> <span data-ttu-id="cd78e-130">Haben Sie die gleiche Anzahl von Datenträgern installiert?</span><span class="sxs-lookup"><span data-stu-id="cd78e-130">Do they have the same number of disks installed?</span></span> <span data-ttu-id="cd78e-131">Die Konfigurationsverwaltungsdatenbank gibt den Typ des Datenträgers an, der installiert werden kann, die Nummer und den Aktualisierungspfad in jedem Fall.</span><span class="sxs-lookup"><span data-stu-id="cd78e-131">The configuration management database will indicate the type of disk that can be installed, the number, and the upgrade path in each case.</span></span>

</div>

<div>

## <a name="tools-used-for-configuration-management"></a><span data-ttu-id="cd78e-132">Für die Konfigurationsverwaltung verwendete Tools</span><span class="sxs-lookup"><span data-stu-id="cd78e-132">Tools used for configuration management</span></span>

<span data-ttu-id="cd78e-133">Es gibt zahlreiche Tools zum ermitteln, überwachen und melden von Objekten.</span><span class="sxs-lookup"><span data-stu-id="cd78e-133">There are many tools to discover, audit, and report assets.</span></span> <span data-ttu-id="cd78e-134">Einige dieser Tools werden in diesem Abschnitt erläutert.</span><span class="sxs-lookup"><span data-stu-id="cd78e-134">Some of these tools are discussed in this section.</span></span>

  - <span data-ttu-id="cd78e-135">**Automatisierte Skripts**     Sie können einfache Skripts schreiben, um Elemente wie Betriebssystem, Service Pack-Ebene und Software auf einem bestimmten Satz von Computern zu melden.</span><span class="sxs-lookup"><span data-stu-id="cd78e-135">**Automated Scripts**   You can write simple scripts to report items such as the operating system, service pack level, and whether software exists on a specific set of computers.</span></span> <span data-ttu-id="cd78e-136">Sie können diese Skripts in die genauen Anforderungen einer Organisation schreiben.</span><span class="sxs-lookup"><span data-stu-id="cd78e-136">You can write these scripts to an organization’s exact requirements.</span></span> <span data-ttu-id="cd78e-137">Die erforderliche Anzahl von Skripts und deren Komplexität können Skripts jedoch teuer erstellen und warten lassen.</span><span class="sxs-lookup"><span data-stu-id="cd78e-137">However, the required number of scripts and their complexity can make scripts expensive to create and maintain.</span></span>

  - <span data-ttu-id="cd78e-138">**Automatisierte Tools**     Je nach Größe Ihres Unternehmens und Ihren organisatorischen Anforderungen sollten Sie die Verwendung von automatisierten Tools in Frage stellen.</span><span class="sxs-lookup"><span data-stu-id="cd78e-138">**Automated Tools**   Depending on the size of your business and your organizational needs, you may want to consider using automated tools.</span></span> <span data-ttu-id="cd78e-139">Tools wie Microsoft Endpoint Configuration Manager enthalten standardberichtsvorlagen (wie Service Pack-Ebene) und ermöglichen Ihnen auch das Erstellen von benutzerdefinierten Berichten, beispielsweise für eine benutzerdefinierte Anwendung.</span><span class="sxs-lookup"><span data-stu-id="cd78e-139">Tools such as Microsoft Endpoint Configuration Manager incorporate standard report templates (such as service pack level) and also enable you to create customized reports, for example, for a custom application.</span></span> <span data-ttu-id="cd78e-140">Der Microsoft Endpoint Configuration Manager kann auch zum Melden von Hardware-und Softwarekonfigurationen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="cd78e-140">The Microsoft Endpoint Configuration Manager can also be used to report on hardware and software configurations.</span></span>

</div>

<div>

## <a name="relationship-with-change-management"></a><span data-ttu-id="cd78e-141">Beziehung zur Änderungsverwaltung</span><span class="sxs-lookup"><span data-stu-id="cd78e-141">Relationship with change management</span></span>

<span data-ttu-id="cd78e-142">Die Konfigurationsverwaltung steht im engen Zusammenhang mit der Änderungsverwaltung.</span><span class="sxs-lookup"><span data-stu-id="cd78e-142">Configuration management is closely related to change management.</span></span> <span data-ttu-id="cd78e-143">Die Konfigurationsverwaltung gibt an, dass Änderungen erforderlich sind, und identifiziert und zeichnet eine Änderung auf.</span><span class="sxs-lookup"><span data-stu-id="cd78e-143">Configuration management identifies the need for change and identifies and records that a change has occurred.</span></span> <span data-ttu-id="cd78e-144">Beispielsweise kann die Konfigurationsverwaltungsdatenbank verwendet werden, um Server zu identifizieren, die einen Hotfix erfordern.</span><span class="sxs-lookup"><span data-stu-id="cd78e-144">For example, the configuration management database can be used to identify servers that require a hotfix.</span></span> <span data-ttu-id="cd78e-145">Change Management definiert dann den Prozess für die Anwendung des Hotfixes.</span><span class="sxs-lookup"><span data-stu-id="cd78e-145">Change management then defines the process for applying the hotfix.</span></span>

<span data-ttu-id="cd78e-146">Wenn umgekehrt ein neues Kumulatives Update ausgeführt wird, sollte der Änderungsverwaltungsprozess diese Informationen dem Konfigurationsverwaltungssystem bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="cd78e-146">Conversely, if a new cumulative update is rolled out, the change management process should supply this information to the configuration management system.</span></span> <span data-ttu-id="cd78e-147">Die Konfigurationsverwaltungstools müssen möglicherweise so konfiguriert werden, dass die neue Software so identifiziert wird, dass Sie erkennt und nachverfolgen kann, wo und wann die Software bereitgestellt wird.</span><span class="sxs-lookup"><span data-stu-id="cd78e-147">The configuration management tools will probably need to be configured to identify the new software so that they can discover and track where and when the software is deployed.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

