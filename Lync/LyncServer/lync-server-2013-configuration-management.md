---
title: 'Lync Server 2013: Konfigurationsverwaltung'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuration management
ms:assetid: 00ea1196-cb40-427f-99a4-5e8037cbf367
ms:mtpsurl: https://technet.microsoft.com/library/Dn720316(v=OCS.15)
ms:contentKeyID: 63969570
ms.date: 05/16/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: cb652485b03bcaee5e63bc4fc23d25fd5df958bd
ms.sourcegitcommit: ed3a6789dedf54275e0b1ab41d4a4230eed6eb72
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/30/2020
ms.locfileid: "41628351"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configuration-management-in-lync-server-2013"></a><span data-ttu-id="9529d-102">Konfigurationsverwaltung in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9529d-102">Configuration management in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9529d-103">_**Letztes Änderungsdatum des Themas:** 2015-05-15_</span><span class="sxs-lookup"><span data-stu-id="9529d-103">_**Topic Last Modified:** 2015-05-15_</span></span>

<span data-ttu-id="9529d-104">Konfigurationsverwaltung ist der Vorgang zum Aufzeichnen und Nachverfolgen von Hardware-und Softwareressourcen sowie Systemkonfigurationsinformationen.</span><span class="sxs-lookup"><span data-stu-id="9529d-104">Configuration management is the process of recording and tracking hardware and software assets and system configuration information.</span></span> <span data-ttu-id="9529d-105">Sie wird im Allgemeinen verwendet, um Softwarelizenzen zu überwachen, einen standardmäßigen Hardware-und Software-Build für Clientcomputer und Server zu verwalten und Namensstandards für neue Computer zu definieren.</span><span class="sxs-lookup"><span data-stu-id="9529d-105">It is generally used to track software licenses, maintain a standard hardware and software build for client computers and servers, and define naming standards for new computers.</span></span> <span data-ttu-id="9529d-106">Die Konfigurationsverwaltung umfasst in der Regel die folgenden Kategorien:</span><span class="sxs-lookup"><span data-stu-id="9529d-106">Configuration management generally covers the following categories:</span></span>

  - <span data-ttu-id="9529d-107">**Hardware**   diese Kategorie verfolgt die Equipments, die die IT-Organisation besitzt, in der sich die Geräte befinden und die Geräte verwenden.</span><span class="sxs-lookup"><span data-stu-id="9529d-107">**Hardware**   This category tracks the pieces of equipment that the IT organization owns, where equipment is located, and who uses equipment.</span></span> <span data-ttu-id="9529d-108">Diese Informationen ermöglichen es einer Organisation, Upgrades zu planen und zu budgetieren, Standard-Hardware-Builds zu verwalten, den Wert von IT-Ressourcen zu Abrechnungszwecken zu melden und Diebstahl zu verhindern.</span><span class="sxs-lookup"><span data-stu-id="9529d-108">This information enables an organization to plan and budget for upgrades, maintain standard hardware builds, report on the value of IT assets for accounting purposes, and help prevent theft.</span></span>

  - <span data-ttu-id="9529d-109">**Software**   diese Kategorie verfolgt Software, die auf jedem Computer installiert ist, die Versionsnummern und die Position, an der die Lizenzen aufbewahrt werden.</span><span class="sxs-lookup"><span data-stu-id="9529d-109">**Software**   This category tracks software that is installed on each computer, the version numbers, and where the licenses are held.</span></span> <span data-ttu-id="9529d-110">Diese Informationen helfen bei der Planung von Upgrades, um sicherzustellen, dass Software lizenziert ist, und erkennen das vorhanden sein von nicht autorisierten (und nicht lizenzierten) Software.</span><span class="sxs-lookup"><span data-stu-id="9529d-110">This information helps plan upgrades, to ensure that software is licensed, and detect the presence of unauthorized (and unlicensed) software.</span></span>

  - <span data-ttu-id="9529d-111">**Standard-Builds**   mit dieser Kategorie wird der aktuelle Standard Build für die Clientcomputer und Server nachverfolgt, und ob die Clientcomputer und Server diesen Standard erfüllen.</span><span class="sxs-lookup"><span data-stu-id="9529d-111">**Standard Builds**   This category tracks the current standard build for the client computers and servers and whether the client computers and servers meet this standard.</span></span> <span data-ttu-id="9529d-112">Die Definition und Erzwingung von Standard-Builds hilft dem Supportpersonal, da das Personal nur eine begrenzte Anzahl von Versionen jeder Software verwalten muss.</span><span class="sxs-lookup"><span data-stu-id="9529d-112">Defining and enforcing standard builds helps support staff because the staff is required to maintain only a limited number of versions of each piece of software.</span></span>

  - <span data-ttu-id="9529d-113">**Kumulative Updates und Hotfixes**   diese Kategorie verfolgt, welche Service Packs getestet und für die Verwendung genehmigt wurden und welche Computer auf dem neuesten Stand sind.</span><span class="sxs-lookup"><span data-stu-id="9529d-113">**Cumulative Updates and Hotfixes**   This category tracks which service packs are tested and approved for use and which computers are up to date.</span></span> <span data-ttu-id="9529d-114">Diese Informationen sind wichtig, um das Risiko zu verringern, dass Computer gefährdet sind, und um Benutzer zu erkennen, die nicht genehmigte Updates installiert haben.</span><span class="sxs-lookup"><span data-stu-id="9529d-114">This information is important to reduce the risk of computers being compromised and to detect users who have installed unapproved updates.</span></span>

  - <span data-ttu-id="9529d-115">**Systemkonfigurationsinformationen**   in dieser Kategorie werden die Funktion eines Systems, die Interaktion zwischen Systemelementen und die Prozesse verfolgt, die von einem reibungslos funktionierenden System abhängen.</span><span class="sxs-lookup"><span data-stu-id="9529d-115">**System Configuration Information**   This category tracks the function of a system, the interaction between system elements, and the processes that depend on a system that is running smoothly.</span></span> <span data-ttu-id="9529d-116">So kann beispielsweise ein Proxy Server eines Drittanbieters auf einem einzelnen Server konfiguriert sein.</span><span class="sxs-lookup"><span data-stu-id="9529d-116">For example, third-party proxy server may be configured on a single server.</span></span> <span data-ttu-id="9529d-117">Die Abhängigkeit des Proxyservers von diesem Server sollte verstanden werden, und Notfallpläne sind möglicherweise erforderlich, wenn ein Fehler auftritt.</span><span class="sxs-lookup"><span data-stu-id="9529d-117">The proxy server’s dependence on this server should be understood and contingency plans may be required if there is a failure.</span></span> <span data-ttu-id="9529d-118">Wenn der Proxy Server auch für die Kommunikation mit einem anderen Front-End-Server konfiguriert werden kann, ändern sich wahrscheinlich Abhängigkeiten und Notfallpläne.</span><span class="sxs-lookup"><span data-stu-id="9529d-118">If the proxy server can be configured to also communicate with another front-end server, dependencies and contingency plans will probably change.</span></span>

<div>

## <a name="implementing-configuration-management"></a><span data-ttu-id="9529d-119">Implementieren der Konfigurationsverwaltung</span><span class="sxs-lookup"><span data-stu-id="9529d-119">Implementing configuration management</span></span>

<span data-ttu-id="9529d-120">Nachdem Sie festgestellt haben, welche Elemente verwaltet werden müssen, implementieren Sie die Konfigurationsverwaltung, indem Sie Daten sammeln und Daten melden.</span><span class="sxs-lookup"><span data-stu-id="9529d-120">After you determine what items need managing, implement configuration management by collecting data and reporting data.</span></span> <span data-ttu-id="9529d-121">Der einfachste Ansatz für kleine Organisationen besteht darin, Daten manuell (Anzahl und Modell von Clientcomputern, Betriebssystem, installierte Software) zu erfassen und in einem Office Word-oder Office Excel-Dokument zu speichern.</span><span class="sxs-lookup"><span data-stu-id="9529d-121">The simplest approach for small organizations is to collect data manually (number and model of client computers, operating system, installed software) and save it in an Office Word or Office Excel document.</span></span> <span data-ttu-id="9529d-122">Bei größeren, komplexeren und sich ständig ändernden Systemen muss die Ermittlung von Ressourcen und die Erfassung detaillierter Informationen automatisiert werden.</span><span class="sxs-lookup"><span data-stu-id="9529d-122">For larger, more complex, and constantly changing systems, the discovery of assets and collection of detailed information must be automated.</span></span> <span data-ttu-id="9529d-123">Entscheiden Sie, welche Informationen für Ihre Organisation relevant sind, und speichern Sie Sie in einer Datenbank.</span><span class="sxs-lookup"><span data-stu-id="9529d-123">Decide what information is relevant to your organization and record it in a database.</span></span>

<span data-ttu-id="9529d-124">Die Konfigurationsverwaltungsdatenbank ist ein hilfreiches Tool für die Unterstützung von Mitarbeitern und Verwaltung in den folgenden Bereichen:</span><span class="sxs-lookup"><span data-stu-id="9529d-124">The configuration management database is a useful tool for support staff and management in the following areas:</span></span>

  - <span data-ttu-id="9529d-125">**Sicherheitsüberwachung**   die Datenbank ermöglicht es Ihnen, Server zu identifizieren, auf denen lync Server-und Clientcomputer Systeme ausgeführt werden, auf denen Hotfixes angewendet werden müssen oder die die Installation eines Service Packs oder der neuesten Antivirus-Updates verpasst haben.</span><span class="sxs-lookup"><span data-stu-id="9529d-125">**Security Audits**   The database enables you to identify servers that are running Lync Server and client computer systems that must have hotfixes applied or that have missed the installation of a service pack or the latest antivirus updates.</span></span>

  - <span data-ttu-id="9529d-126">**Software Installation**   , die Client Softwareversionen identifiziert und diese nachverfolgt, unterstützt Administratoren bei der Planung von Versionsupdates und neuen Installationen sowie bei der Lizenzierung von Dokumentation und Compliance.</span><span class="sxs-lookup"><span data-stu-id="9529d-126">**Software Installation**   Identifying client software versions and tracking them will aid administrators in planning version updates and new installs and also by helping with licensing documentation and compliance.</span></span>

  - <span data-ttu-id="9529d-127">**Konfigurationsinformationen**   Wenn Sie eine aktuelle Liste aller Einstellungen beibehalten, die von Ihrer Standardeinstellung geändert wurden, können Sie Probleme schnell und effektiver beheben.</span><span class="sxs-lookup"><span data-stu-id="9529d-127">**Configuration Information**   If you maintain an up-to-date list of all settings that were changed from their default, then you'll be able to troubleshoot issues quickly and more effectively.</span></span>

  - <span data-ttu-id="9529d-128">**Planen von Upgrades**   wenn eine Kapazitätsüberprüfung zeigt, dass für Ihre lync-Datenbankserver zusätzlicher Speicherplatz erforderlich ist, ist es wichtig zu wissen, ob jeder Server über einen internen RAID-Controller verfügt.</span><span class="sxs-lookup"><span data-stu-id="9529d-128">**Planning Upgrades**   If a capacity review reveals that additional storage space is required on your Lync database servers, it’s important to know whether each server has an internal RAID controller.</span></span> <span data-ttu-id="9529d-129">Wenn ja, sind Sie das gleiche Modell?</span><span class="sxs-lookup"><span data-stu-id="9529d-129">If they do, then are they the same model?</span></span> <span data-ttu-id="9529d-130">Haben Sie die gleiche Anzahl von Festplatten installiert?</span><span class="sxs-lookup"><span data-stu-id="9529d-130">Do they have the same number of disks installed?</span></span> <span data-ttu-id="9529d-131">Die Konfigurationsverwaltungsdatenbank gibt den Typ des Datenträgers an, der installiert werden kann, die Nummer und den Aktualisierungspfad in jedem Fall.</span><span class="sxs-lookup"><span data-stu-id="9529d-131">The configuration management database will indicate the type of disk that can be installed, the number, and the upgrade path in each case.</span></span>

</div>

<div>

## <a name="tools-used-for-configuration-management"></a><span data-ttu-id="9529d-132">Für die Konfigurationsverwaltung verwendete Tools</span><span class="sxs-lookup"><span data-stu-id="9529d-132">Tools used for configuration management</span></span>

<span data-ttu-id="9529d-133">Es gibt viele Tools zum ermitteln, überwachen und melden von Ressourcen.</span><span class="sxs-lookup"><span data-stu-id="9529d-133">There are many tools to discover, audit, and report assets.</span></span> <span data-ttu-id="9529d-134">Einige dieser Tools werden in diesem Abschnitt erläutert.</span><span class="sxs-lookup"><span data-stu-id="9529d-134">Some of these tools are discussed in this section.</span></span>

  - <span data-ttu-id="9529d-135">**Automatisierte Skripts**   Sie können einfache Skripts schreiben, um Elemente wie das Betriebssystem, die Service Pack-Ebene zu melden und zu bestimmen, ob Software auf einem bestimmten Satz von Computern vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="9529d-135">**Automated Scripts**   You can write simple scripts to report items such as the operating system, service pack level, and whether software exists on a specific set of computers.</span></span> <span data-ttu-id="9529d-136">Sie können diese Skripts in die genauen Anforderungen einer Organisation schreiben.</span><span class="sxs-lookup"><span data-stu-id="9529d-136">You can write these scripts to an organization’s exact requirements.</span></span> <span data-ttu-id="9529d-137">Die erforderliche Anzahl von Skripts und deren Komplexität können jedoch dazu führen, dass Skripts für die Erstellung und Verwaltung kostspielig sind.</span><span class="sxs-lookup"><span data-stu-id="9529d-137">However, the required number of scripts and their complexity can make scripts expensive to create and maintain.</span></span>

  - <span data-ttu-id="9529d-138">**Automatisierte Tools**   je nach Größe Ihres Unternehmens und Ihren organisatorischen Anforderungen können Sie die Verwendung automatisierter Tools in Frage stellen.</span><span class="sxs-lookup"><span data-stu-id="9529d-138">**Automated Tools**   Depending on the size of your business and your organizational needs, you may want to consider using automated tools.</span></span> <span data-ttu-id="9529d-139">Tools wie Microsoft Endpoint Configuration Manager enthalten standardberichtsvorlagen (wie die Service Pack-Ebene) und ermöglichen Ihnen auch das Erstellen angepasster Berichte, beispielsweise für eine benutzerdefinierte Anwendung.</span><span class="sxs-lookup"><span data-stu-id="9529d-139">Tools such as Microsoft Endpoint Configuration Manager incorporate standard report templates (such as service pack level) and also enable you to create customized reports, for example, for a custom application.</span></span> <span data-ttu-id="9529d-140">Der Microsoft Endpoint Configuration Manager kann auch verwendet werden, um Hardware-und Softwarekonfigurationen zu melden.</span><span class="sxs-lookup"><span data-stu-id="9529d-140">The Microsoft Endpoint Configuration Manager can also be used to report on hardware and software configurations.</span></span>

</div>

<div>

## <a name="relationship-with-change-management"></a><span data-ttu-id="9529d-141">Beziehung mit Änderungsverwaltung</span><span class="sxs-lookup"><span data-stu-id="9529d-141">Relationship with change management</span></span>

<span data-ttu-id="9529d-142">Die Konfigurationsverwaltung steht in engem Zusammenhang mit der Änderungsverwaltung.</span><span class="sxs-lookup"><span data-stu-id="9529d-142">Configuration management is closely related to change management.</span></span> <span data-ttu-id="9529d-143">Die Konfigurationsverwaltung identifiziert den Bedarf an Änderungen und identifiziert und zeichnet, dass eine Änderung aufgetreten ist.</span><span class="sxs-lookup"><span data-stu-id="9529d-143">Configuration management identifies the need for change and identifies and records that a change has occurred.</span></span> <span data-ttu-id="9529d-144">So kann beispielsweise die Konfigurationsverwaltungsdatenbank verwendet werden, um Server zu identifizieren, für die ein Hotfix erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="9529d-144">For example, the configuration management database can be used to identify servers that require a hotfix.</span></span> <span data-ttu-id="9529d-145">Die Änderungsverwaltung definiert dann den Vorgang zum Anwenden des Hotfixes.</span><span class="sxs-lookup"><span data-stu-id="9529d-145">Change management then defines the process for applying the hotfix.</span></span>

<span data-ttu-id="9529d-146">Wenn umgekehrt ein neues Kumulatives Update bereitgestellt wird, sollte der Change Management-Prozess diese Informationen an das Konfigurationsverwaltungssystem übermitteln.</span><span class="sxs-lookup"><span data-stu-id="9529d-146">Conversely, if a new cumulative update is rolled out, the change management process should supply this information to the configuration management system.</span></span> <span data-ttu-id="9529d-147">Die Konfigurationsverwaltungstools müssen wahrscheinlich so konfiguriert werden, dass Sie die neue Software identifizieren, sodass Sie ermitteln und nachvollziehen können, wo und wann die Software bereitgestellt wird.</span><span class="sxs-lookup"><span data-stu-id="9529d-147">The configuration management tools will probably need to be configured to identify the new software so that they can discover and track where and when the software is deployed.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

