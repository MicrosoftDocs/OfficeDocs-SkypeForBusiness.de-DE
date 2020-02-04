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
ms.openlocfilehash: cee1c4571dafa4e513f42613de13205ecec9de42
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41735257"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="establishing-a-backup-and-restoration-plan-for-lync-server-2013"></a><span data-ttu-id="569ed-102">Einrichten eines Sicherungs-und Wiederherstellungsplans für lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="569ed-102">Establishing a backup and restoration plan for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="569ed-103">_**Letztes Änderungsdatum des Themas:** 2013-02-17_</span><span class="sxs-lookup"><span data-stu-id="569ed-103">_**Topic Last Modified:** 2013-02-17_</span></span>

<span data-ttu-id="569ed-104">Das Erstellen eines Sicherungs-und Wiederherstellungsplans umfasst die folgenden Schritte:</span><span class="sxs-lookup"><span data-stu-id="569ed-104">Creating a backup and restoration plan involves the following steps:</span></span>

  - <span data-ttu-id="569ed-105">Entwickeln des Plans</span><span class="sxs-lookup"><span data-stu-id="569ed-105">Developing the plan.</span></span>

  - <span data-ttu-id="569ed-106">Implementieren des Plans</span><span class="sxs-lookup"><span data-stu-id="569ed-106">Implementing the plan.</span></span>

  - <span data-ttu-id="569ed-107">Den Plan pflegen.</span><span class="sxs-lookup"><span data-stu-id="569ed-107">Maintaining the plan.</span></span>

<div>

## <a name="developing-a-backup-and-restoration-plan"></a><span data-ttu-id="569ed-108">Entwickeln eines Sicherungs-und Wiederherstellungsplans</span><span class="sxs-lookup"><span data-stu-id="569ed-108">Developing a Backup and Restoration Plan</span></span>

<span data-ttu-id="569ed-109">Nachdem Sie Ihre Sicherungs-und Wiederherstellungsstrategie für lync Server entwickelt haben, verwenden Sie diese, um einen detaillierten Sicherungs-und Wiederherstellungsplan zu dokumentieren.</span><span class="sxs-lookup"><span data-stu-id="569ed-109">After you develop your backup and restoration strategy for Lync Server, use it to document a detailed backup and restoration plan.</span></span> <span data-ttu-id="569ed-110">In Ihrem Plan sollten die Prioritäten und Anforderungen für das Sichern von Daten und Einstellungen eindeutig vermittelt werden.</span><span class="sxs-lookup"><span data-stu-id="569ed-110">Your plan should clearly convey the priorities and requirements for backing up data and settings.</span></span> <span data-ttu-id="569ed-111">Sie können die Informationen beim [Einrichten einer Sicherungs-und Wiederherstellungsstrategie für lync Server 2013](lync-server-2013-establishing-a-backup-and-restoration-strategy.md) und der Arbeitsblätter in [Arbeitsblättern für die Sicherung und Wiederherstellung für lync Server 2013](lync-server-2013-backup-and-restoration-worksheets.md) verwenden, um die Dokumentation Ihrer Strategie zu vereinfachen.</span><span class="sxs-lookup"><span data-stu-id="569ed-111">You can use the information in [Establishing a backup and restoration strategy for Lync Server 2013](lync-server-2013-establishing-a-backup-and-restoration-strategy.md) and the worksheets in [Backup and restoration worksheets for Lync Server 2013](lync-server-2013-backup-and-restoration-worksheets.md) to facilitate the documentation of your strategy.</span></span> <span data-ttu-id="569ed-112">Ihr Plan sollte auch Kriterien für die Entscheidung enthalten, wann und wie der Dienst wiederhergestellt werden soll.</span><span class="sxs-lookup"><span data-stu-id="569ed-112">Your plan should also contain criteria for deciding when and how to restore service.</span></span>

<span data-ttu-id="569ed-113">Wenn Sie Ihren Plan entwickeln, müssen Sie Folgendes berücksichtigen:</span><span class="sxs-lookup"><span data-stu-id="569ed-113">As you develop your plan, you need to consider, and account for, the following:</span></span>

  - <span data-ttu-id="569ed-114">So können Sie Server auf neuer Hardware wiederherstellen.</span><span class="sxs-lookup"><span data-stu-id="569ed-114">How you will recover servers on new hardware.</span></span>

  - <span data-ttu-id="569ed-115">Hier erfahren Sie, wie Sie Dienste wiederherstellen, für die ein Tätigwerden mehrerer Geschäftsbereiche oder Abteilungen erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="569ed-115">How you will recover services that require action on the part of multiple business areas or departments.</span></span>

  - <span data-ttu-id="569ed-116">So können Sie Ersatzserver schnell erwerben.</span><span class="sxs-lookup"><span data-stu-id="569ed-116">How you can acquire spare servers quickly.</span></span>

  - <span data-ttu-id="569ed-117">Die Zeit, die für die Wiederherstellung mithilfe ihrer Strategie benötigt wird.</span><span class="sxs-lookup"><span data-stu-id="569ed-117">The time it takes to recover by using your strategy.</span></span> <span data-ttu-id="569ed-118">Bedenken Sie die Anforderungen Ihrer Organisation an Recovery Time Objective (RTO).</span><span class="sxs-lookup"><span data-stu-id="569ed-118">Consider your organization’s requirements for recovery time objective (RTO).</span></span>

<span data-ttu-id="569ed-119">Ändern Sie die Sicherungs-und Wiederherstellungsverfahren in diesem Thema, indem Sie die erforderlichen Schritte hinzufügen und löschen, um die Server und Komponenten in Ihrer Bereitstellung wiederzugeben.</span><span class="sxs-lookup"><span data-stu-id="569ed-119">Modify the backup and restoration procedures in this topic, adding and deleting procedures as appropriate, to reflect the servers and components in your deployment.</span></span> <span data-ttu-id="569ed-120">Sie können auch geeignete Details wie den Sicherungszeitplan zu den entsprechenden Verfahren hinzufügen, um sicherzustellen, dass die Informationen nicht übersehen werden.</span><span class="sxs-lookup"><span data-stu-id="569ed-120">You can also add appropriate details, such as the backup schedule, to the appropriate procedures to make sure that the information is not overlooked.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="569ed-121">Es empfiehlt sich, Skripts für so viele Schritte wie möglich zu erstellen, um die Qualität und Reproduzierbarkeit der Verfahren zu gewährleisten.</span><span class="sxs-lookup"><span data-stu-id="569ed-121">It is good practice to create scripts for as many steps as possible, to help ensure the quality and reproducibility of procedures.</span></span>



</div>

<span data-ttu-id="569ed-122">Geben Sie in Ihrem Plan an, wer für die Überprüfung des Plans verantwortlich ist, wer für das Testen und Überprüfen neuer Verfahren oder Tools verantwortlich ist und wer alle Änderungen am Plan und den zugehörigen Verfahren genehmigen muss.</span><span class="sxs-lookup"><span data-stu-id="569ed-122">In your plan, specify who is responsible for reviewing the plan, who is responsible for testing and validating any new procedures or tools, and who must approve any changes to the plan and related procedures.</span></span>

<span data-ttu-id="569ed-123">Wenn Sie sicherstellen möchten, dass Ihr Sicherungs-und Wiederherstellungsplan alle festgelegten Ziele und Prioritäten in vollem Umfang erfüllt, besorgen Sie sich die Genehmigung der zuständigen Entscheidungsträger und technischen Entscheidungsträger in Ihrer Organisation, bevor Sie den Plan implementieren.</span><span class="sxs-lookup"><span data-stu-id="569ed-123">To make sure that your backup and restoration plan fully meets all established goals and priorities, get the approval of the appropriate business decision makers and technical decision makers in your organization before you implement the plan.</span></span>

</div>

<div>

## <a name="implementing-the-backup-and-restoration-plan"></a><span data-ttu-id="569ed-124">Implementieren des Sicherungs-und Wiederherstellungsplans</span><span class="sxs-lookup"><span data-stu-id="569ed-124">Implementing the Backup and Restoration Plan</span></span>

<span data-ttu-id="569ed-125">Für die Implementierung eines Sicherungs-und Wiederherstellungsplans sind die folgenden Schritte erforderlich:</span><span class="sxs-lookup"><span data-stu-id="569ed-125">Implementing a backup and restoration plan requires the following steps:</span></span>

  - <span data-ttu-id="569ed-126">Testen und Überprüfen des Plans</span><span class="sxs-lookup"><span data-stu-id="569ed-126">Testing and validating the plan.</span></span>

  - <span data-ttu-id="569ed-127">Den Plan kommunizieren.</span><span class="sxs-lookup"><span data-stu-id="569ed-127">Communicating the plan.</span></span>

  - <span data-ttu-id="569ed-128">Überprüfen von Sicherungs-und Wiederherstellungsvorgängen</span><span class="sxs-lookup"><span data-stu-id="569ed-128">Validating backup and restoration operations.</span></span>

<div>

## <a name="testing-and-validating-the-plan"></a><span data-ttu-id="569ed-129">Testen und Überprüfen des Plans</span><span class="sxs-lookup"><span data-stu-id="569ed-129">Testing and Validating the Plan</span></span>

<span data-ttu-id="569ed-130">Die hier beschriebenen Verfahren wurden in einer Lab-Umgebung getestet und validiert.</span><span class="sxs-lookup"><span data-stu-id="569ed-130">The procedures described here have been tested and validated in a lab environment.</span></span> <span data-ttu-id="569ed-131">Wenn Sie sicherstellen möchten, dass diese oder andere Verfahren in Ihrer Umgebung funktionieren, sollten Sie jede Prozedur testen und überprüfen, die Sie implementieren möchten.</span><span class="sxs-lookup"><span data-stu-id="569ed-131">To make sure that these or any other procedures work in your environment, you should test and validate each procedure you intend to implement.</span></span> <span data-ttu-id="569ed-132">Führen Sie die Tests und die Validierung durch, bevor Sie Ihren Plan zur endgültigen Genehmigung übermitteln.</span><span class="sxs-lookup"><span data-stu-id="569ed-132">Complete the testing and the validation before you submit your plan for final approval.</span></span>

</div>

<div>

## <a name="communicating-the-plan"></a><span data-ttu-id="569ed-133">Kommunizieren des Plans</span><span class="sxs-lookup"><span data-stu-id="569ed-133">Communicating the Plan</span></span>

<span data-ttu-id="569ed-134">In Ihrem Sicherungs-und Wiederherstellungsplan sollte klar beschrieben werden, wer Prozeduren und schrittweise Anleitungen zum Durchführen der Verfahren implementiert.</span><span class="sxs-lookup"><span data-stu-id="569ed-134">Your backup and restoration plan should clearly describe who implements procedures and step-by-step instructions for carrying out the procedures.</span></span> <span data-ttu-id="569ed-135">Sie sollten sicherstellen, dass jeder, der für einen Aspekt der Sicherung und Wiederherstellung verantwortlich ist, den Plan, die Art der Implementierung und deren Rolle versteht.</span><span class="sxs-lookup"><span data-stu-id="569ed-135">You should make sure that everyone responsible for any aspect of backup and restoration understands the plan, how it is to be implemented, and what their role is.</span></span> <span data-ttu-id="569ed-136">Dazu gehören alle Implementierungsanforderungen für Folgendes:</span><span class="sxs-lookup"><span data-stu-id="569ed-136">This includes all implementation requirements for the following:</span></span>

  - <span data-ttu-id="569ed-137">Pool-und Serversicherung</span><span class="sxs-lookup"><span data-stu-id="569ed-137">Pool and server backup.</span></span>

  - <span data-ttu-id="569ed-138">Wiederherstellung des Diensts.</span><span class="sxs-lookup"><span data-stu-id="569ed-138">Restoration of service.</span></span>

<span data-ttu-id="569ed-139">**Pool-und Serversicherung**</span><span class="sxs-lookup"><span data-stu-id="569ed-139">**Pool and server backup**</span></span>

<span data-ttu-id="569ed-140">Der Sicherungs-und Wiederherstellungsplan sollte alle Informationen umfassen, die erforderlich sind, um Sicherungsverfahren kontinuierlich abzuschließen.</span><span class="sxs-lookup"><span data-stu-id="569ed-140">The backup and restoration plan should include all information required to complete backup procedures on an ongoing basis.</span></span> <span data-ttu-id="569ed-141">Die primären Informationen, die den Verantwortlichen Teammitgliedern mitgeteilt werden, umfassen Folgendes:</span><span class="sxs-lookup"><span data-stu-id="569ed-141">The primary information to be communicated to responsible team members includes the following:</span></span>

  - <span data-ttu-id="569ed-142">Team oder Person (als Einzelperson oder Rolle angegeben), die für die Sicherung der einzelnen Server verantwortlich ist.</span><span class="sxs-lookup"><span data-stu-id="569ed-142">Team or person (specified as an individual or role) responsible for backing up each server.</span></span>

  - <span data-ttu-id="569ed-143">Spezifische Zeitpläne zum Sichern der einzelnen Server.</span><span class="sxs-lookup"><span data-stu-id="569ed-143">Specific schedules for backing up each server.</span></span>

  - <span data-ttu-id="569ed-144">Sicherungsspeicherorte für die einzelnen Datentypen (Einstellungen, Datenbank und Dateifreigaben).</span><span class="sxs-lookup"><span data-stu-id="569ed-144">Backup locations for each type of data (settings, database, and file shares).</span></span>

  - <span data-ttu-id="569ed-145">Zu verwendende Sicherungsverfahren, einschließlich der Tools, die für die Ausführung der einzelnen Verfahren erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="569ed-145">Backup procedures to be used, including the tools required to complete each procedure.</span></span>

  - <span data-ttu-id="569ed-146">Informationen, die erforderlich sind, um Sicherungen abzuschließen, wie in den [Arbeitsblättern für die Sicherung und Wiederherstellung für lync Server 2013](lync-server-2013-backup-and-restoration-worksheets.md)behandelt.</span><span class="sxs-lookup"><span data-stu-id="569ed-146">Information required to complete backups, as covered in [Backup and restoration worksheets for Lync Server 2013](lync-server-2013-backup-and-restoration-worksheets.md).</span></span>

  - <span data-ttu-id="569ed-147">Überprüfungsmethoden, die verwendet werden, um sicherzustellen, dass Daten und Einstellungen entsprechend gesichert und für die Wiederherstellung verfügbar sind, die regelmäßige Überprüfungen und Testwiederherstellungen enthalten können.</span><span class="sxs-lookup"><span data-stu-id="569ed-147">Validation methods to be used to help ensure that data and settings are appropriately backed up and available for restoration, which can include periodic audits and test restorations.</span></span>

<span data-ttu-id="569ed-148">**Wiederherstellung des Diensts**</span><span class="sxs-lookup"><span data-stu-id="569ed-148">**Restoration of service**</span></span>

<span data-ttu-id="569ed-149">Der Sicherungs-und Wiederherstellungsplan sollte alle zum Wiederherstellen des Diensts erforderlichen Informationen enthalten, falls auf einem oder mehreren Servern ein Verlust auftritt, der den Dienst nicht verfügbar macht.</span><span class="sxs-lookup"><span data-stu-id="569ed-149">The backup and restoration plan should include all information required to restore service, in case one or more servers experience a loss that makes service unavailable.</span></span> <span data-ttu-id="569ed-150">Die primären Informationen, die den Verantwortlichen Teammitgliedern mitgeteilt werden, umfassen Folgendes:</span><span class="sxs-lookup"><span data-stu-id="569ed-150">The primary information to be communicated to responsible team members includes the following:</span></span>

  - <span data-ttu-id="569ed-151">Team oder Person (als Einzelperson oder Rolle angegeben), die für die Bestimmung der Notwendigkeit der Wiederherstellung des Diensts sowie der für die Wiederherstellung des Diensts zu verwendenden Verfahren sowie für das Team oder die Person verantwortlich ist, die für die Implementierung der jeweiligen Verfahren verantwortlich ist Wiederherstellungsszenario</span><span class="sxs-lookup"><span data-stu-id="569ed-151">Team or person (specified as an individual or a role) that is responsible for determining when restoration of service is required and the procedures to be used to restore service, and also the team or person responsible for implementing procedures for each restoration scenario.</span></span>

  - <span data-ttu-id="569ed-152">Kriterien zum ermitteln, welche Wiederherstellungsverfahren für eine bestimmte Situation am besten geeignet sind.</span><span class="sxs-lookup"><span data-stu-id="569ed-152">Criteria for determining which restoration procedures are most appropriate for a specific situation.</span></span>

  - <span data-ttu-id="569ed-153">Zeitschätzungen für die Wiederherstellung des Dienst-und Wiederherstellungszeit Ziels (RTO) in jedem Wiederherstellungsszenario.</span><span class="sxs-lookup"><span data-stu-id="569ed-153">Time estimates for restoration of service and recovery time objective (RTO) in each restoration scenario.</span></span>

  - <span data-ttu-id="569ed-154">Zu verwendende Wiederherstellungsverfahren, einschließlich der Tools, die für die Ausführung der einzelnen Verfahren erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="569ed-154">Restoration procedures to be used, including the tools required to complete each procedure.</span></span>

  - <span data-ttu-id="569ed-155">Informationen, die zum Wiederherstellen von Daten und Einstellungen erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="569ed-155">Information required to restore data and settings.</span></span> <span data-ttu-id="569ed-156">Arbeitsblätter werden in [Arbeitsblättern zur Sicherung und Wiederherstellung für lync Server 2013](lync-server-2013-backup-and-restoration-worksheets.md)bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="569ed-156">Worksheets are provided in [Backup and restoration worksheets for Lync Server 2013](lync-server-2013-backup-and-restoration-worksheets.md).</span></span>

</div>

<div>

## <a name="validating-backup-and-restoration-operations"></a><span data-ttu-id="569ed-157">Überprüfen von Sicherungs-und Wiederherstellungsvorgängen</span><span class="sxs-lookup"><span data-stu-id="569ed-157">Validating Backup and Restoration Operations</span></span>

<span data-ttu-id="569ed-158">Nachdem Sie die anfänglichen Sicherungsbemühungen in Ihrer Produktionsumgebung und in bestimmten Intervallen abgeschlossen haben (wie in Ihrem Sicherungs-und Wiederherstellungsplan beschrieben), sollten Sie Folgendes überprüfen:</span><span class="sxs-lookup"><span data-stu-id="569ed-158">After completing initial backup efforts in your production environment and at specified intervals (as covered in your backup and restoration plan), you should verify the following:</span></span>

  - <span data-ttu-id="569ed-159">Backups erfolgen nach Bedarf.</span><span class="sxs-lookup"><span data-stu-id="569ed-159">Backups are occurring as required.</span></span>

  - <span data-ttu-id="569ed-160">Auf gesicherte Daten und Einstellungen kann zugegriffen werden.</span><span class="sxs-lookup"><span data-stu-id="569ed-160">Backed-up data and settings are accessible.</span></span>

  - <span data-ttu-id="569ed-161">Wiederherstellungsverfahren können innerhalb der im Sicherungs-und Wiederherstellungsplan angegebenen RTO-Zeiten (Recovery Time Objective) ausgeführt werden, und die Ergebnisse erfüllen alle Geschäftsanforderungen.</span><span class="sxs-lookup"><span data-stu-id="569ed-161">Restoration procedures can be performed within the recovery time objective (RTO) times specified in the backup and restoration plan, and the results meet all business requirements.</span></span>

  - <span data-ttu-id="569ed-162">Backup-Arbeitsblätter wurden abgeschlossen und überprüft, und Sie werden an einem sicheren Ort gespeichert.</span><span class="sxs-lookup"><span data-stu-id="569ed-162">Backup worksheets have been completed and verified, and they are stored in a secure location.</span></span> <span data-ttu-id="569ed-163">Diese Arbeitsblätter werden in [Arbeitsblättern zur Sicherung und Wiederherstellung für lync Server 2013](lync-server-2013-backup-and-restoration-worksheets.md)bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="569ed-163">These worksheets are provided in [Backup and restoration worksheets for Lync Server 2013](lync-server-2013-backup-and-restoration-worksheets.md).</span></span>

  - <span data-ttu-id="569ed-164">Wiederherstellungsverfahren wurden getestet und überprüft, wie in Ihrem Sicherungs-und Wiederherstellungsplan angegeben, wie erwartet funktioniert.</span><span class="sxs-lookup"><span data-stu-id="569ed-164">Restoration procedures have been tested and verified to work as expected, as specified in your backup and restoration plan.</span></span>

</div>

</div>

<div>

## <a name="maintaining-the-backup-and-restoration-plan"></a><span data-ttu-id="569ed-165">Verwalten des Sicherungs-und Wiederherstellungsplans</span><span class="sxs-lookup"><span data-stu-id="569ed-165">Maintaining the Backup and Restoration Plan</span></span>

<span data-ttu-id="569ed-166">Eine lync Server-Topologie ist eine dynamische Umgebung, die sich in Ihrer Organisation ändert.</span><span class="sxs-lookup"><span data-stu-id="569ed-166">A Lync Server topology is a dynamic environment that changes with your organization.</span></span> <span data-ttu-id="569ed-167">Überprüfen Sie den Sicherungs-und Wiederherstellungsplan, während sich die Organisation ändert, und überprüfen Sie ihn regelmäßig, um sicherzustellen, dass er weiterhin den Anforderungen Ihres Unternehmens entspricht.</span><span class="sxs-lookup"><span data-stu-id="569ed-167">Reassess your backup and restoration plan as your organization changes, and review it periodically to make sure that it continues to meet the needs of your business.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

