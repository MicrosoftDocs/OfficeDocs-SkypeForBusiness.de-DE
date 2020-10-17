---
title: 'Lync Server 2013: Einrichten eines Sicherungs-und Wiederherstellungsplans'
description: 'Lync Server 2013: Einrichten eines Sicherungs-und Wiederherstellungsplans.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Establishing a backup and restoration plan
ms:assetid: 9f562ef1-3804-41e2-b3e4-d45b2e8c63c9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202183(v=OCS.15)
ms:contentKeyID: 51541499
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 06d93c713364bf6b5f230b255b68a2c1dfe1d04a
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48555051"
---
# <a name="establishing-a-backup-and-restoration-plan-for-lync-server-2013"></a><span data-ttu-id="7f6a2-103">Einrichten eines Sicherungs-und Wiederherstellungsplans für lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7f6a2-103">Establishing a backup and restoration plan for Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7f6a2-104">_**Letztes Änderungsstand des Themas:** 2013-02-17_</span><span class="sxs-lookup"><span data-stu-id="7f6a2-104">_**Topic Last Modified:** 2013-02-17_</span></span>

<span data-ttu-id="7f6a2-105">Das Erstellen eines Sicherungs- und Wiederherstellungsplans beinhaltet die folgenden Schritte:</span><span class="sxs-lookup"><span data-stu-id="7f6a2-105">Creating a backup and restoration plan involves the following steps:</span></span>

  - <span data-ttu-id="7f6a2-106">Entwickeln des Plans.</span><span class="sxs-lookup"><span data-stu-id="7f6a2-106">Developing the plan.</span></span>

  - <span data-ttu-id="7f6a2-107">Implementieren des Plans.</span><span class="sxs-lookup"><span data-stu-id="7f6a2-107">Implementing the plan.</span></span>

  - <span data-ttu-id="7f6a2-108">Verwalten des Plans.</span><span class="sxs-lookup"><span data-stu-id="7f6a2-108">Maintaining the plan.</span></span>

<div>

## <a name="developing-a-backup-and-restoration-plan"></a><span data-ttu-id="7f6a2-109">Entwickeln eines Sicherungs- und Wiederherstellungsplans</span><span class="sxs-lookup"><span data-stu-id="7f6a2-109">Developing a Backup and Restoration Plan</span></span>

<span data-ttu-id="7f6a2-110">Nachdem Sie die Sicherungs-und Wiederherstellungsstrategie für lync Server entwickelt haben, verwenden Sie diese, um einen detaillierten Sicherungs-und Wiederherstellungsplan zu dokumentieren.</span><span class="sxs-lookup"><span data-stu-id="7f6a2-110">After you develop your backup and restoration strategy for Lync Server, use it to document a detailed backup and restoration plan.</span></span> <span data-ttu-id="7f6a2-111">In diesem Plan sollten die Prioritäten und Anforderungen zum Sichern von Daten und Einstellungen eindeutig festgehalten sein.</span><span class="sxs-lookup"><span data-stu-id="7f6a2-111">Your plan should clearly convey the priorities and requirements for backing up data and settings.</span></span> <span data-ttu-id="7f6a2-112">Sie können die Informationen unter [Einrichten einer Sicherungs-und Wiederherstellungsstrategie für lync Server 2013](lync-server-2013-establishing-a-backup-and-restoration-strategy.md) und der Arbeitsblätter in [Sicherungs-und Wiederherstellungs Arbeitsblättern für lync Server 2013](lync-server-2013-backup-and-restoration-worksheets.md) verwenden, um die Dokumentation Ihrer Strategie zu vereinfachen.</span><span class="sxs-lookup"><span data-stu-id="7f6a2-112">You can use the information in [Establishing a backup and restoration strategy for Lync Server 2013](lync-server-2013-establishing-a-backup-and-restoration-strategy.md) and the worksheets in [Backup and restoration worksheets for Lync Server 2013](lync-server-2013-backup-and-restoration-worksheets.md) to facilitate the documentation of your strategy.</span></span> <span data-ttu-id="7f6a2-113">Ihr Plan sollte außerdem Kriterien enthalten, wann und wie die Serverbereitschaft wiederhergestellt werden soll.</span><span class="sxs-lookup"><span data-stu-id="7f6a2-113">Your plan should also contain criteria for deciding when and how to restore service.</span></span>

<span data-ttu-id="7f6a2-114">Während Sie Ihren Plan entwickeln, müssen Sie Folgendes berücksichtigen und berücksichtigen:</span><span class="sxs-lookup"><span data-stu-id="7f6a2-114">As you develop your plan, you need to consider, and account for, the following:</span></span>

  - <span data-ttu-id="7f6a2-115">Wie Server auf neuer Hardware wiederhergestellt werden</span><span class="sxs-lookup"><span data-stu-id="7f6a2-115">How you will recover servers on new hardware.</span></span>

  - <span data-ttu-id="7f6a2-116">Wie Dienste wiederhergestellt werden, an denen mehrere Unternehmensbereiche oder Abteilungen involviert sind</span><span class="sxs-lookup"><span data-stu-id="7f6a2-116">How you will recover services that require action on the part of multiple business areas or departments.</span></span>

  - <span data-ttu-id="7f6a2-117">Wie Ersatzserver schnell beschafft werden können</span><span class="sxs-lookup"><span data-stu-id="7f6a2-117">How you can acquire spare servers quickly.</span></span>

  - <span data-ttu-id="7f6a2-118">Den Zeitaufwand für die Wiederherstellung mithilfe Ihrer Strategie</span><span class="sxs-lookup"><span data-stu-id="7f6a2-118">The time it takes to recover by using your strategy.</span></span> <span data-ttu-id="7f6a2-119">Überprüfen Sie die Anforderungen Ihrer Organisation an die RTO (Recovery Time Objective).</span><span class="sxs-lookup"><span data-stu-id="7f6a2-119">Consider your organization’s requirements for recovery time objective (RTO).</span></span>

<span data-ttu-id="7f6a2-120">Ändern Sie die Sicherungs-und Wiederherstellungsverfahren in diesem Thema, indem Sie Verfahren entsprechend hinzufügen und löschen, um die Server und Komponenten in Ihrer Bereitstellung widerzuspiegeln.</span><span class="sxs-lookup"><span data-stu-id="7f6a2-120">Modify the backup and restoration procedures in this topic, adding and deleting procedures as appropriate, to reflect the servers and components in your deployment.</span></span> <span data-ttu-id="7f6a2-121">Sie können den entsprechenden Verfahren auch entsprechende Details wie den Sicherungszeitplan hinzufügen, um sicherzustellen, dass die Informationen nicht außer acht lassen.</span><span class="sxs-lookup"><span data-stu-id="7f6a2-121">You can also add appropriate details, such as the backup schedule, to the appropriate procedures to make sure that the information is not overlooked.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="7f6a2-122">Es empfiehlt sich, Skripts für so viele Schritte wie möglich zu erstellen, um die Qualität und Reproduzierbarkeit von Verfahren sicherzustellen.</span><span class="sxs-lookup"><span data-stu-id="7f6a2-122">It is good practice to create scripts for as many steps as possible, to help ensure the quality and reproducibility of procedures.</span></span>



</div>

<span data-ttu-id="7f6a2-123">Geben Sie in Ihrem Plan an, wer für die Überprüfung des Plans zuständig ist, wer für das Testen und validieren neuer Verfahren oder Tools zuständig ist und welche Änderungen am Plan und den dazugehörigen Verfahren genehmigt werden müssen.</span><span class="sxs-lookup"><span data-stu-id="7f6a2-123">In your plan, specify who is responsible for reviewing the plan, who is responsible for testing and validating any new procedures or tools, and who must approve any changes to the plan and related procedures.</span></span>

<span data-ttu-id="7f6a2-124">Um sicherzustellen, dass Ihr Sicherungs-und Wiederherstellungsplan alle festgelegten Ziele und Prioritäten vollständig erfüllt, müssen Sie vor der Implementierung des Plans die Genehmigung der entsprechenden geschäftlichen Entscheidungsträger und technischen Entscheidungsträger in Ihrer Organisation einholen.</span><span class="sxs-lookup"><span data-stu-id="7f6a2-124">To make sure that your backup and restoration plan fully meets all established goals and priorities, get the approval of the appropriate business decision makers and technical decision makers in your organization before you implement the plan.</span></span>

</div>

<div>

## <a name="implementing-the-backup-and-restoration-plan"></a><span data-ttu-id="7f6a2-125">Implementieren des Sicherungs- und Wiederherstellungsplans</span><span class="sxs-lookup"><span data-stu-id="7f6a2-125">Implementing the Backup and Restoration Plan</span></span>

<span data-ttu-id="7f6a2-126">Die Implementierung eines Sicherungs-und Wiederherstellungsplans erfordert die folgenden Schritte:</span><span class="sxs-lookup"><span data-stu-id="7f6a2-126">Implementing a backup and restoration plan requires the following steps:</span></span>

  - <span data-ttu-id="7f6a2-127">Testen und Überprüfen des Plans.</span><span class="sxs-lookup"><span data-stu-id="7f6a2-127">Testing and validating the plan.</span></span>

  - <span data-ttu-id="7f6a2-128">Kommunizieren des Plans.</span><span class="sxs-lookup"><span data-stu-id="7f6a2-128">Communicating the plan.</span></span>

  - <span data-ttu-id="7f6a2-129">Überprüfen der Sicherungs-und Wiederherstellungsvorgänge</span><span class="sxs-lookup"><span data-stu-id="7f6a2-129">Validating backup and restoration operations.</span></span>

<div>

## <a name="testing-and-validating-the-plan"></a><span data-ttu-id="7f6a2-130">Testen und Überprüfen des Plans</span><span class="sxs-lookup"><span data-stu-id="7f6a2-130">Testing and Validating the Plan</span></span>

<span data-ttu-id="7f6a2-131">Die hier beschriebenen Verfahren wurden in einer Testumgebung getestet und validiert.</span><span class="sxs-lookup"><span data-stu-id="7f6a2-131">The procedures described here have been tested and validated in a lab environment.</span></span> <span data-ttu-id="7f6a2-132">Um sicherzustellen, dass diese oder andere Verfahren in Ihrer Umgebung funktionieren, sollten Sie die einzelnen Verfahren testen und validieren, die Sie implementieren möchten.</span><span class="sxs-lookup"><span data-stu-id="7f6a2-132">To make sure that these or any other procedures work in your environment, you should test and validate each procedure you intend to implement.</span></span> <span data-ttu-id="7f6a2-133">Schließen Sie die Tests und die Überprüfung ab, bevor Sie Ihren Plan zur endgültigen Genehmigung übermitteln.</span><span class="sxs-lookup"><span data-stu-id="7f6a2-133">Complete the testing and the validation before you submit your plan for final approval.</span></span>

</div>

<div>

## <a name="communicating-the-plan"></a><span data-ttu-id="7f6a2-134">Vermitteln des Plans</span><span class="sxs-lookup"><span data-stu-id="7f6a2-134">Communicating the Plan</span></span>

<span data-ttu-id="7f6a2-135">In Ihrem Sicherungs- und Wiederherstellungsplan sollten die Personen, die Verfahren implementieren, sowie die schrittweisen Anleitungen zum Ausführen der Verfahren eindeutig beschrieben sein.</span><span class="sxs-lookup"><span data-stu-id="7f6a2-135">Your backup and restoration plan should clearly describe who implements procedures and step-by-step instructions for carrying out the procedures.</span></span> <span data-ttu-id="7f6a2-136">Sie sollten sicherstellen, dass jeder, der für alle Aspekte der Sicherung und Wiederherstellung verantwortlich ist, den Plan, die Implementierung und die Rolle des Plans versteht.</span><span class="sxs-lookup"><span data-stu-id="7f6a2-136">You should make sure that everyone responsible for any aspect of backup and restoration understands the plan, how it is to be implemented, and what their role is.</span></span> <span data-ttu-id="7f6a2-137">Dies beinhaltet alle Implementierungsanforderungen für Folgendes:</span><span class="sxs-lookup"><span data-stu-id="7f6a2-137">This includes all implementation requirements for the following:</span></span>

  - <span data-ttu-id="7f6a2-138">Pool-und Serversicherung.</span><span class="sxs-lookup"><span data-stu-id="7f6a2-138">Pool and server backup.</span></span>

  - <span data-ttu-id="7f6a2-139">Wiederherstellung des Diensts.</span><span class="sxs-lookup"><span data-stu-id="7f6a2-139">Restoration of service.</span></span>

<span data-ttu-id="7f6a2-140">**Pool- und Serversicherung**</span><span class="sxs-lookup"><span data-stu-id="7f6a2-140">**Pool and server backup**</span></span>

<span data-ttu-id="7f6a2-p106">Der Sicherungs- und Wiederherstellungsplan sollte alle erforderlichen Informationen beinhalten, um Sicherungsverfahren fortlaufend auszuführen. Dies sind die wichtigsten Informationen, welche die zuständigen Teammitglieder benötigen:</span><span class="sxs-lookup"><span data-stu-id="7f6a2-p106">The backup and restoration plan should include all information required to complete backup procedures on an ongoing basis. The primary information to be communicated to responsible team members includes the following:</span></span>

  - <span data-ttu-id="7f6a2-143">Team oder Person (als Person oder Rolle angegeben), die für die Sicherung der einzelnen Server verantwortlich ist.</span><span class="sxs-lookup"><span data-stu-id="7f6a2-143">Team or person (specified as an individual or role) responsible for backing up each server.</span></span>

  - <span data-ttu-id="7f6a2-144">Bestimmte Zeitpläne für die Sicherung der einzelnen Server.</span><span class="sxs-lookup"><span data-stu-id="7f6a2-144">Specific schedules for backing up each server.</span></span>

  - <span data-ttu-id="7f6a2-145">Sicherungsspeicherorte für die einzelnen Datentypen (Einstellungen, Datenbanken und Dateifreigaben).</span><span class="sxs-lookup"><span data-stu-id="7f6a2-145">Backup locations for each type of data (settings, database, and file shares).</span></span>

  - <span data-ttu-id="7f6a2-146">Zu verwendende Sicherungsverfahren, einschließlich der Tools, die zum Abschließen der einzelnen Verfahren erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="7f6a2-146">Backup procedures to be used, including the tools required to complete each procedure.</span></span>

  - <span data-ttu-id="7f6a2-147">Informationen, die zum Abschließen von Sicherungen erforderlich sind, wie in [Sicherungs-und Wiederherstellungs Arbeitsblättern für lync Server 2013](lync-server-2013-backup-and-restoration-worksheets.md)behandelt.</span><span class="sxs-lookup"><span data-stu-id="7f6a2-147">Information required to complete backups, as covered in [Backup and restoration worksheets for Lync Server 2013](lync-server-2013-backup-and-restoration-worksheets.md).</span></span>

  - <span data-ttu-id="7f6a2-148">Validierungsmethoden, die verwendet werden, um sicherzustellen, dass Daten und Einstellungen ordnungsgemäß gesichert und für die Wiederherstellung verfügbar sind, die regelmäßige Überprüfungen und Testwiederherstellungen umfassen kann.</span><span class="sxs-lookup"><span data-stu-id="7f6a2-148">Validation methods to be used to help ensure that data and settings are appropriately backed up and available for restoration, which can include periodic audits and test restorations.</span></span>

<span data-ttu-id="7f6a2-149">**Wiederherstellung der Serverbereitschaft**</span><span class="sxs-lookup"><span data-stu-id="7f6a2-149">**Restoration of service**</span></span>

<span data-ttu-id="7f6a2-150">Der Sicherungs-und Wiederherstellungsplan sollte alle Informationen enthalten, die zum Wiederherstellen des Diensts erforderlich sind, für den Fall, dass ein oder mehrere Server einen Verlust erfahren, der den Dienst nicht verfügbar machen kann.</span><span class="sxs-lookup"><span data-stu-id="7f6a2-150">The backup and restoration plan should include all information required to restore service, in case one or more servers experience a loss that makes service unavailable.</span></span> <span data-ttu-id="7f6a2-151">Dies sind die wichtigsten Informationen, welche die zuständigen Teammitglieder benötigen:</span><span class="sxs-lookup"><span data-stu-id="7f6a2-151">The primary information to be communicated to responsible team members includes the following:</span></span>

  - <span data-ttu-id="7f6a2-152">Das Team oder die Person (Angabe als Einzelperson oder Rolle), das bzw. die entscheidet, wann die Serverbereitschaft wiederhergestellt werden muss und welche Verfahren dabei verwendet werden. Außerdem das Team oder die Person, das bzw. die für das Implementieren der Verfahren für jedes Wiederherstellungsszenario zuständig ist.</span><span class="sxs-lookup"><span data-stu-id="7f6a2-152">Team or person (specified as an individual or a role) that is responsible for determining when restoration of service is required and the procedures to be used to restore service, and also the team or person responsible for implementing procedures for each restoration scenario.</span></span>

  - <span data-ttu-id="7f6a2-153">Kriterien, um die für eine bestimmte Situation geeignetsten Wiederherstellungsverfahren zu bestimmen.</span><span class="sxs-lookup"><span data-stu-id="7f6a2-153">Criteria for determining which restoration procedures are most appropriate for a specific situation.</span></span>

  - <span data-ttu-id="7f6a2-154">Zeitschätzungen für die Wiederherstellung des Dienst-und Wiederherstellungszeit Ziels (RTO) in jedem Wiederherstellungsszenario.</span><span class="sxs-lookup"><span data-stu-id="7f6a2-154">Time estimates for restoration of service and recovery time objective (RTO) in each restoration scenario.</span></span>

  - <span data-ttu-id="7f6a2-155">Zu verwendende Wiederherstellungsverfahren, einschließlich der erforderlichen Tools zum Ausführen der einzelnen Verfahren.</span><span class="sxs-lookup"><span data-stu-id="7f6a2-155">Restoration procedures to be used, including the tools required to complete each procedure.</span></span>

  - <span data-ttu-id="7f6a2-156">Erforderliche Informationen zum Wiederherstellen von Daten und Einstellungen.</span><span class="sxs-lookup"><span data-stu-id="7f6a2-156">Information required to restore data and settings.</span></span> <span data-ttu-id="7f6a2-157">Arbeitsblätter werden in [Sicherungs-und Wiederherstellungs Arbeitsblättern für lync Server 2013](lync-server-2013-backup-and-restoration-worksheets.md)bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="7f6a2-157">Worksheets are provided in [Backup and restoration worksheets for Lync Server 2013](lync-server-2013-backup-and-restoration-worksheets.md).</span></span>

</div>

<div>

## <a name="validating-backup-and-restoration-operations"></a><span data-ttu-id="7f6a2-158">Überprüfen der Sicherungs- und Wiederherstellungsvorgänge</span><span class="sxs-lookup"><span data-stu-id="7f6a2-158">Validating Backup and Restoration Operations</span></span>

<span data-ttu-id="7f6a2-159">Nach Abschluss der ersten Sicherungsschritte in Ihrer Produktionsumgebung und in den angegebenen Intervallen (gemäß Sicherungs- und Wiederherstellungsplan) sollten Sie Folgendes überprüfen:</span><span class="sxs-lookup"><span data-stu-id="7f6a2-159">After completing initial backup efforts in your production environment and at specified intervals (as covered in your backup and restoration plan), you should verify the following:</span></span>

  - <span data-ttu-id="7f6a2-160">Sicherungen erfolgen bedarfsgemäß.</span><span class="sxs-lookup"><span data-stu-id="7f6a2-160">Backups are occurring as required.</span></span>

  - <span data-ttu-id="7f6a2-161">Auf gesicherte Daten und Einstellungen kann zugegriffen werden.</span><span class="sxs-lookup"><span data-stu-id="7f6a2-161">Backed-up data and settings are accessible.</span></span>

  - <span data-ttu-id="7f6a2-162">Wiederherstellungsverfahren können innerhalb der im Sicherungs-und Wiederherstellungsplan angegebenen RTO-Zeiten (Recovery Time Object) durchgeführt werden, und die Ergebnisse erfüllen alle geschäftlichen Anforderungen.</span><span class="sxs-lookup"><span data-stu-id="7f6a2-162">Restoration procedures can be performed within the recovery time objective (RTO) times specified in the backup and restoration plan, and the results meet all business requirements.</span></span>

  - <span data-ttu-id="7f6a2-163">Sicherungsarbeitsblätter wurden ausgefüllt und geprüft und sind an einem sicheren Speicherort gespeichert.</span><span class="sxs-lookup"><span data-stu-id="7f6a2-163">Backup worksheets have been completed and verified, and they are stored in a secure location.</span></span> <span data-ttu-id="7f6a2-164">Diese Arbeitsblätter werden in [Sicherungs-und Wiederherstellungs Arbeitsblättern für lync Server 2013](lync-server-2013-backup-and-restoration-worksheets.md)bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="7f6a2-164">These worksheets are provided in [Backup and restoration worksheets for Lync Server 2013](lync-server-2013-backup-and-restoration-worksheets.md).</span></span>

  - <span data-ttu-id="7f6a2-165">Wiederherstellungsverfahren wurden getestet und geprüft, um sicherzustellen, dass sie gemäß Sicherungs- und Wiederherstellungsplan ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="7f6a2-165">Restoration procedures have been tested and verified to work as expected, as specified in your backup and restoration plan.</span></span>

</div>

</div>

<div>

## <a name="maintaining-the-backup-and-restoration-plan"></a><span data-ttu-id="7f6a2-166">Verwalten des Sicherungs- und Wiederherstellungsplans</span><span class="sxs-lookup"><span data-stu-id="7f6a2-166">Maintaining the Backup and Restoration Plan</span></span>

<span data-ttu-id="7f6a2-167">Eine lync Server Topologie ist eine dynamische Umgebung, die sich in Ihrer Organisation ändert.</span><span class="sxs-lookup"><span data-stu-id="7f6a2-167">A Lync Server topology is a dynamic environment that changes with your organization.</span></span> <span data-ttu-id="7f6a2-168">Überprüfen Sie den Sicherungs-und Wiederherstellungsplan, wenn sich Ihre Organisation ändert, und überprüfen Sie ihn regelmäßig, um sicherzustellen, dass er weiterhin den Anforderungen Ihres Unternehmens entspricht.</span><span class="sxs-lookup"><span data-stu-id="7f6a2-168">Reassess your backup and restoration plan as your organization changes, and review it periodically to make sure that it continues to meet the needs of your business.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

