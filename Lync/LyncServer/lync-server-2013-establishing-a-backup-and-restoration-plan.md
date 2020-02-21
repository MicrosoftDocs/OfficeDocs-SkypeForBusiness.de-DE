---
title: 'Lync Server 2013: Einrichten eines Sicherungs-und Wiederherstellungsplans'
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
ms.openlocfilehash: b08b2588ea7510bf2a6ac2de544d0dce7b0fe134
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/21/2020
ms.locfileid: "42204801"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="establishing-a-backup-and-restoration-plan-for-lync-server-2013"></a><span data-ttu-id="0b9f1-102">Einrichten eines Sicherungs-und Wiederherstellungsplans für lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0b9f1-102">Establishing a backup and restoration plan for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0b9f1-103">_**Letztes Änderungsstand des Themas:** 2013-02-17_</span><span class="sxs-lookup"><span data-stu-id="0b9f1-103">_**Topic Last Modified:** 2013-02-17_</span></span>

<span data-ttu-id="0b9f1-104">Das Erstellen eines Sicherungs- und Wiederherstellungsplans beinhaltet die folgenden Schritte:</span><span class="sxs-lookup"><span data-stu-id="0b9f1-104">Creating a backup and restoration plan involves the following steps:</span></span>

  - <span data-ttu-id="0b9f1-105">Entwickeln des Plans.</span><span class="sxs-lookup"><span data-stu-id="0b9f1-105">Developing the plan.</span></span>

  - <span data-ttu-id="0b9f1-106">Implementieren des Plans.</span><span class="sxs-lookup"><span data-stu-id="0b9f1-106">Implementing the plan.</span></span>

  - <span data-ttu-id="0b9f1-107">Verwalten des Plans.</span><span class="sxs-lookup"><span data-stu-id="0b9f1-107">Maintaining the plan.</span></span>

<div>

## <a name="developing-a-backup-and-restoration-plan"></a><span data-ttu-id="0b9f1-108">Entwickeln eines Sicherungs- und Wiederherstellungsplans</span><span class="sxs-lookup"><span data-stu-id="0b9f1-108">Developing a Backup and Restoration Plan</span></span>

<span data-ttu-id="0b9f1-109">Nachdem Sie die Sicherungs-und Wiederherstellungsstrategie für lync Server entwickelt haben, verwenden Sie diese, um einen detaillierten Sicherungs-und Wiederherstellungsplan zu dokumentieren.</span><span class="sxs-lookup"><span data-stu-id="0b9f1-109">After you develop your backup and restoration strategy for Lync Server, use it to document a detailed backup and restoration plan.</span></span> <span data-ttu-id="0b9f1-110">In diesem Plan sollten die Prioritäten und Anforderungen zum Sichern von Daten und Einstellungen eindeutig festgehalten sein.</span><span class="sxs-lookup"><span data-stu-id="0b9f1-110">Your plan should clearly convey the priorities and requirements for backing up data and settings.</span></span> <span data-ttu-id="0b9f1-111">Sie können die Informationen unter [Einrichten einer Sicherungs-und Wiederherstellungsstrategie für lync Server 2013](lync-server-2013-establishing-a-backup-and-restoration-strategy.md) und der Arbeitsblätter in [Sicherungs-und Wiederherstellungs Arbeitsblättern für lync Server 2013](lync-server-2013-backup-and-restoration-worksheets.md) verwenden, um die Dokumentation Ihrer Strategie zu vereinfachen.</span><span class="sxs-lookup"><span data-stu-id="0b9f1-111">You can use the information in [Establishing a backup and restoration strategy for Lync Server 2013](lync-server-2013-establishing-a-backup-and-restoration-strategy.md) and the worksheets in [Backup and restoration worksheets for Lync Server 2013](lync-server-2013-backup-and-restoration-worksheets.md) to facilitate the documentation of your strategy.</span></span> <span data-ttu-id="0b9f1-112">Ihr Plan sollte außerdem Kriterien enthalten, wann und wie die Serverbereitschaft wiederhergestellt werden soll.</span><span class="sxs-lookup"><span data-stu-id="0b9f1-112">Your plan should also contain criteria for deciding when and how to restore service.</span></span>

<span data-ttu-id="0b9f1-113">Während Sie Ihren Plan entwickeln, müssen Sie Folgendes berücksichtigen und berücksichtigen:</span><span class="sxs-lookup"><span data-stu-id="0b9f1-113">As you develop your plan, you need to consider, and account for, the following:</span></span>

  - <span data-ttu-id="0b9f1-114">Wie Server auf neuer Hardware wiederhergestellt werden</span><span class="sxs-lookup"><span data-stu-id="0b9f1-114">How you will recover servers on new hardware.</span></span>

  - <span data-ttu-id="0b9f1-115">Wie Dienste wiederhergestellt werden, an denen mehrere Unternehmensbereiche oder Abteilungen involviert sind</span><span class="sxs-lookup"><span data-stu-id="0b9f1-115">How you will recover services that require action on the part of multiple business areas or departments.</span></span>

  - <span data-ttu-id="0b9f1-116">Wie Ersatzserver schnell beschafft werden können</span><span class="sxs-lookup"><span data-stu-id="0b9f1-116">How you can acquire spare servers quickly.</span></span>

  - <span data-ttu-id="0b9f1-117">Den Zeitaufwand für die Wiederherstellung mithilfe Ihrer Strategie</span><span class="sxs-lookup"><span data-stu-id="0b9f1-117">The time it takes to recover by using your strategy.</span></span> <span data-ttu-id="0b9f1-118">Überprüfen Sie die Anforderungen Ihrer Organisation an die RTO (Recovery Time Objective).</span><span class="sxs-lookup"><span data-stu-id="0b9f1-118">Consider your organization’s requirements for recovery time objective (RTO).</span></span>

<span data-ttu-id="0b9f1-119">Ändern Sie die Sicherungs-und Wiederherstellungsverfahren in diesem Thema, indem Sie Verfahren entsprechend hinzufügen und löschen, um die Server und Komponenten in Ihrer Bereitstellung widerzuspiegeln.</span><span class="sxs-lookup"><span data-stu-id="0b9f1-119">Modify the backup and restoration procedures in this topic, adding and deleting procedures as appropriate, to reflect the servers and components in your deployment.</span></span> <span data-ttu-id="0b9f1-120">Sie können den entsprechenden Verfahren auch entsprechende Details wie den Sicherungszeitplan hinzufügen, um sicherzustellen, dass die Informationen nicht außer acht lassen.</span><span class="sxs-lookup"><span data-stu-id="0b9f1-120">You can also add appropriate details, such as the backup schedule, to the appropriate procedures to make sure that the information is not overlooked.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="0b9f1-121">Es empfiehlt sich, Skripts für so viele Schritte wie möglich zu erstellen, um die Qualität und Reproduzierbarkeit von Verfahren sicherzustellen.</span><span class="sxs-lookup"><span data-stu-id="0b9f1-121">It is good practice to create scripts for as many steps as possible, to help ensure the quality and reproducibility of procedures.</span></span>



</div>

<span data-ttu-id="0b9f1-122">Geben Sie in Ihrem Plan an, wer für die Überprüfung des Plans zuständig ist, wer für das Testen und validieren neuer Verfahren oder Tools zuständig ist und welche Änderungen am Plan und den dazugehörigen Verfahren genehmigt werden müssen.</span><span class="sxs-lookup"><span data-stu-id="0b9f1-122">In your plan, specify who is responsible for reviewing the plan, who is responsible for testing and validating any new procedures or tools, and who must approve any changes to the plan and related procedures.</span></span>

<span data-ttu-id="0b9f1-123">Um sicherzustellen, dass Ihr Sicherungs-und Wiederherstellungsplan alle festgelegten Ziele und Prioritäten vollständig erfüllt, müssen Sie vor der Implementierung des Plans die Genehmigung der entsprechenden geschäftlichen Entscheidungsträger und technischen Entscheidungsträger in Ihrer Organisation einholen.</span><span class="sxs-lookup"><span data-stu-id="0b9f1-123">To make sure that your backup and restoration plan fully meets all established goals and priorities, get the approval of the appropriate business decision makers and technical decision makers in your organization before you implement the plan.</span></span>

</div>

<div>

## <a name="implementing-the-backup-and-restoration-plan"></a><span data-ttu-id="0b9f1-124">Implementieren des Sicherungs- und Wiederherstellungsplans</span><span class="sxs-lookup"><span data-stu-id="0b9f1-124">Implementing the Backup and Restoration Plan</span></span>

<span data-ttu-id="0b9f1-125">Die Implementierung eines Sicherungs-und Wiederherstellungsplans erfordert die folgenden Schritte:</span><span class="sxs-lookup"><span data-stu-id="0b9f1-125">Implementing a backup and restoration plan requires the following steps:</span></span>

  - <span data-ttu-id="0b9f1-126">Testen und Überprüfen des Plans.</span><span class="sxs-lookup"><span data-stu-id="0b9f1-126">Testing and validating the plan.</span></span>

  - <span data-ttu-id="0b9f1-127">Kommunizieren des Plans.</span><span class="sxs-lookup"><span data-stu-id="0b9f1-127">Communicating the plan.</span></span>

  - <span data-ttu-id="0b9f1-128">Überprüfen der Sicherungs-und Wiederherstellungsvorgänge</span><span class="sxs-lookup"><span data-stu-id="0b9f1-128">Validating backup and restoration operations.</span></span>

<div>

## <a name="testing-and-validating-the-plan"></a><span data-ttu-id="0b9f1-129">Testen und Überprüfen des Plans</span><span class="sxs-lookup"><span data-stu-id="0b9f1-129">Testing and Validating the Plan</span></span>

<span data-ttu-id="0b9f1-130">Die hier beschriebenen Verfahren wurden in einer Testumgebung getestet und validiert.</span><span class="sxs-lookup"><span data-stu-id="0b9f1-130">The procedures described here have been tested and validated in a lab environment.</span></span> <span data-ttu-id="0b9f1-131">Um sicherzustellen, dass diese oder andere Verfahren in Ihrer Umgebung funktionieren, sollten Sie die einzelnen Verfahren testen und validieren, die Sie implementieren möchten.</span><span class="sxs-lookup"><span data-stu-id="0b9f1-131">To make sure that these or any other procedures work in your environment, you should test and validate each procedure you intend to implement.</span></span> <span data-ttu-id="0b9f1-132">Schließen Sie die Tests und die Überprüfung ab, bevor Sie Ihren Plan zur endgültigen Genehmigung übermitteln.</span><span class="sxs-lookup"><span data-stu-id="0b9f1-132">Complete the testing and the validation before you submit your plan for final approval.</span></span>

</div>

<div>

## <a name="communicating-the-plan"></a><span data-ttu-id="0b9f1-133">Vermitteln des Plans</span><span class="sxs-lookup"><span data-stu-id="0b9f1-133">Communicating the Plan</span></span>

<span data-ttu-id="0b9f1-134">In Ihrem Sicherungs- und Wiederherstellungsplan sollten die Personen, die Verfahren implementieren, sowie die schrittweisen Anleitungen zum Ausführen der Verfahren eindeutig beschrieben sein.</span><span class="sxs-lookup"><span data-stu-id="0b9f1-134">Your backup and restoration plan should clearly describe who implements procedures and step-by-step instructions for carrying out the procedures.</span></span> <span data-ttu-id="0b9f1-135">Sie sollten sicherstellen, dass jeder, der für alle Aspekte der Sicherung und Wiederherstellung verantwortlich ist, den Plan, die Implementierung und die Rolle des Plans versteht.</span><span class="sxs-lookup"><span data-stu-id="0b9f1-135">You should make sure that everyone responsible for any aspect of backup and restoration understands the plan, how it is to be implemented, and what their role is.</span></span> <span data-ttu-id="0b9f1-136">Dies beinhaltet alle Implementierungsanforderungen für Folgendes:</span><span class="sxs-lookup"><span data-stu-id="0b9f1-136">This includes all implementation requirements for the following:</span></span>

  - <span data-ttu-id="0b9f1-137">Pool-und Serversicherung.</span><span class="sxs-lookup"><span data-stu-id="0b9f1-137">Pool and server backup.</span></span>

  - <span data-ttu-id="0b9f1-138">Wiederherstellung des Diensts.</span><span class="sxs-lookup"><span data-stu-id="0b9f1-138">Restoration of service.</span></span>

<span data-ttu-id="0b9f1-139">**Pool- und Serversicherung**</span><span class="sxs-lookup"><span data-stu-id="0b9f1-139">**Pool and server backup**</span></span>

<span data-ttu-id="0b9f1-p106">Der Sicherungs- und Wiederherstellungsplan sollte alle erforderlichen Informationen beinhalten, um Sicherungsverfahren fortlaufend auszuführen. Dies sind die wichtigsten Informationen, welche die zuständigen Teammitglieder benötigen:</span><span class="sxs-lookup"><span data-stu-id="0b9f1-p106">The backup and restoration plan should include all information required to complete backup procedures on an ongoing basis. The primary information to be communicated to responsible team members includes the following:</span></span>

  - <span data-ttu-id="0b9f1-142">Team oder Person (als Person oder Rolle angegeben), die für die Sicherung der einzelnen Server verantwortlich ist.</span><span class="sxs-lookup"><span data-stu-id="0b9f1-142">Team or person (specified as an individual or role) responsible for backing up each server.</span></span>

  - <span data-ttu-id="0b9f1-143">Bestimmte Zeitpläne für die Sicherung der einzelnen Server.</span><span class="sxs-lookup"><span data-stu-id="0b9f1-143">Specific schedules for backing up each server.</span></span>

  - <span data-ttu-id="0b9f1-144">Sicherungsspeicherorte für die einzelnen Datentypen (Einstellungen, Datenbanken und Dateifreigaben).</span><span class="sxs-lookup"><span data-stu-id="0b9f1-144">Backup locations for each type of data (settings, database, and file shares).</span></span>

  - <span data-ttu-id="0b9f1-145">Zu verwendende Sicherungsverfahren, einschließlich der Tools, die zum Abschließen der einzelnen Verfahren erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="0b9f1-145">Backup procedures to be used, including the tools required to complete each procedure.</span></span>

  - <span data-ttu-id="0b9f1-146">Informationen, die zum Abschließen von Sicherungen erforderlich sind, wie in [Sicherungs-und Wiederherstellungs Arbeitsblättern für lync Server 2013](lync-server-2013-backup-and-restoration-worksheets.md)behandelt.</span><span class="sxs-lookup"><span data-stu-id="0b9f1-146">Information required to complete backups, as covered in [Backup and restoration worksheets for Lync Server 2013](lync-server-2013-backup-and-restoration-worksheets.md).</span></span>

  - <span data-ttu-id="0b9f1-147">Validierungsmethoden, die verwendet werden, um sicherzustellen, dass Daten und Einstellungen ordnungsgemäß gesichert und für die Wiederherstellung verfügbar sind, die regelmäßige Überprüfungen und Testwiederherstellungen umfassen kann.</span><span class="sxs-lookup"><span data-stu-id="0b9f1-147">Validation methods to be used to help ensure that data and settings are appropriately backed up and available for restoration, which can include periodic audits and test restorations.</span></span>

<span data-ttu-id="0b9f1-148">**Wiederherstellung der Serverbereitschaft**</span><span class="sxs-lookup"><span data-stu-id="0b9f1-148">**Restoration of service**</span></span>

<span data-ttu-id="0b9f1-149">Der Sicherungs-und Wiederherstellungsplan sollte alle Informationen enthalten, die zum Wiederherstellen des Diensts erforderlich sind, für den Fall, dass ein oder mehrere Server einen Verlust erfahren, der den Dienst nicht verfügbar machen kann.</span><span class="sxs-lookup"><span data-stu-id="0b9f1-149">The backup and restoration plan should include all information required to restore service, in case one or more servers experience a loss that makes service unavailable.</span></span> <span data-ttu-id="0b9f1-150">Dies sind die wichtigsten Informationen, welche die zuständigen Teammitglieder benötigen:</span><span class="sxs-lookup"><span data-stu-id="0b9f1-150">The primary information to be communicated to responsible team members includes the following:</span></span>

  - <span data-ttu-id="0b9f1-151">Das Team oder die Person (Angabe als Einzelperson oder Rolle), das bzw. die entscheidet, wann die Serverbereitschaft wiederhergestellt werden muss und welche Verfahren dabei verwendet werden. Außerdem das Team oder die Person, das bzw. die für das Implementieren der Verfahren für jedes Wiederherstellungsszenario zuständig ist.</span><span class="sxs-lookup"><span data-stu-id="0b9f1-151">Team or person (specified as an individual or a role) that is responsible for determining when restoration of service is required and the procedures to be used to restore service, and also the team or person responsible for implementing procedures for each restoration scenario.</span></span>

  - <span data-ttu-id="0b9f1-152">Kriterien, um die für eine bestimmte Situation geeignetsten Wiederherstellungsverfahren zu bestimmen.</span><span class="sxs-lookup"><span data-stu-id="0b9f1-152">Criteria for determining which restoration procedures are most appropriate for a specific situation.</span></span>

  - <span data-ttu-id="0b9f1-153">Zeitschätzungen für die Wiederherstellung des Dienst-und Wiederherstellungszeit Ziels (RTO) in jedem Wiederherstellungsszenario.</span><span class="sxs-lookup"><span data-stu-id="0b9f1-153">Time estimates for restoration of service and recovery time objective (RTO) in each restoration scenario.</span></span>

  - <span data-ttu-id="0b9f1-154">Zu verwendende Wiederherstellungsverfahren, einschließlich der erforderlichen Tools zum Ausführen der einzelnen Verfahren.</span><span class="sxs-lookup"><span data-stu-id="0b9f1-154">Restoration procedures to be used, including the tools required to complete each procedure.</span></span>

  - <span data-ttu-id="0b9f1-155">Erforderliche Informationen zum Wiederherstellen von Daten und Einstellungen.</span><span class="sxs-lookup"><span data-stu-id="0b9f1-155">Information required to restore data and settings.</span></span> <span data-ttu-id="0b9f1-156">Arbeitsblätter werden in [Sicherungs-und Wiederherstellungs Arbeitsblättern für lync Server 2013](lync-server-2013-backup-and-restoration-worksheets.md)bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="0b9f1-156">Worksheets are provided in [Backup and restoration worksheets for Lync Server 2013](lync-server-2013-backup-and-restoration-worksheets.md).</span></span>

</div>

<div>

## <a name="validating-backup-and-restoration-operations"></a><span data-ttu-id="0b9f1-157">Überprüfen der Sicherungs- und Wiederherstellungsvorgänge</span><span class="sxs-lookup"><span data-stu-id="0b9f1-157">Validating Backup and Restoration Operations</span></span>

<span data-ttu-id="0b9f1-158">Nach Abschluss der ersten Sicherungsschritte in Ihrer Produktionsumgebung und in den angegebenen Intervallen (gemäß Sicherungs- und Wiederherstellungsplan) sollten Sie Folgendes überprüfen:</span><span class="sxs-lookup"><span data-stu-id="0b9f1-158">After completing initial backup efforts in your production environment and at specified intervals (as covered in your backup and restoration plan), you should verify the following:</span></span>

  - <span data-ttu-id="0b9f1-159">Sicherungen erfolgen bedarfsgemäß.</span><span class="sxs-lookup"><span data-stu-id="0b9f1-159">Backups are occurring as required.</span></span>

  - <span data-ttu-id="0b9f1-160">Auf gesicherte Daten und Einstellungen kann zugegriffen werden.</span><span class="sxs-lookup"><span data-stu-id="0b9f1-160">Backed-up data and settings are accessible.</span></span>

  - <span data-ttu-id="0b9f1-161">Wiederherstellungsverfahren können innerhalb der im Sicherungs-und Wiederherstellungsplan angegebenen RTO-Zeiten (Recovery Time Object) durchgeführt werden, und die Ergebnisse erfüllen alle geschäftlichen Anforderungen.</span><span class="sxs-lookup"><span data-stu-id="0b9f1-161">Restoration procedures can be performed within the recovery time objective (RTO) times specified in the backup and restoration plan, and the results meet all business requirements.</span></span>

  - <span data-ttu-id="0b9f1-162">Sicherungsarbeitsblätter wurden ausgefüllt und geprüft und sind an einem sicheren Speicherort gespeichert.</span><span class="sxs-lookup"><span data-stu-id="0b9f1-162">Backup worksheets have been completed and verified, and they are stored in a secure location.</span></span> <span data-ttu-id="0b9f1-163">Diese Arbeitsblätter werden in [Sicherungs-und Wiederherstellungs Arbeitsblättern für lync Server 2013](lync-server-2013-backup-and-restoration-worksheets.md)bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="0b9f1-163">These worksheets are provided in [Backup and restoration worksheets for Lync Server 2013](lync-server-2013-backup-and-restoration-worksheets.md).</span></span>

  - <span data-ttu-id="0b9f1-164">Wiederherstellungsverfahren wurden getestet und geprüft, um sicherzustellen, dass sie gemäß Sicherungs- und Wiederherstellungsplan ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="0b9f1-164">Restoration procedures have been tested and verified to work as expected, as specified in your backup and restoration plan.</span></span>

</div>

</div>

<div>

## <a name="maintaining-the-backup-and-restoration-plan"></a><span data-ttu-id="0b9f1-165">Verwalten des Sicherungs- und Wiederherstellungsplans</span><span class="sxs-lookup"><span data-stu-id="0b9f1-165">Maintaining the Backup and Restoration Plan</span></span>

<span data-ttu-id="0b9f1-166">Eine lync Server Topologie ist eine dynamische Umgebung, die sich in Ihrer Organisation ändert.</span><span class="sxs-lookup"><span data-stu-id="0b9f1-166">A Lync Server topology is a dynamic environment that changes with your organization.</span></span> <span data-ttu-id="0b9f1-167">Überprüfen Sie den Sicherungs-und Wiederherstellungsplan, wenn sich Ihre Organisation ändert, und überprüfen Sie ihn regelmäßig, um sicherzustellen, dass er weiterhin den Anforderungen Ihres Unternehmens entspricht.</span><span class="sxs-lookup"><span data-stu-id="0b9f1-167">Reassess your backup and restoration plan as your organization changes, and review it periodically to make sure that it continues to meet the needs of your business.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

