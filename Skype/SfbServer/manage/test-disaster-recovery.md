---
title: Disaster Recovery-Tests in Skype für Business Server
ms.reviewer: ''
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Führen Sie eine Wiederherstellung für eine Skype für Business Server-Pool zum Testen Ihrer dokumentierte Disaster Recovery-Prozess
ms.openlocfilehash: 876470f0e4193f02efe0a2094be80f7bdf891fdd
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/27/2019
ms.locfileid: "30884964"
---
# <a name="disaster-recovery-testing-in-skype-for-business-server"></a><span data-ttu-id="d8ccc-103">Disaster Recovery-Tests in Skype für Business Server</span><span class="sxs-lookup"><span data-stu-id="d8ccc-103">Disaster recovery testing in Skype for Business Server</span></span>

<span data-ttu-id="d8ccc-104">Führen Sie eine Wiederherstellung für eine Skype für Business Server-Pool zum Testen Ihrer dokumentierte notfallwiederherstellungsprozess.</span><span class="sxs-lookup"><span data-stu-id="d8ccc-104">Perform a system recovery for a Skype for Business Server pool server to test your documented disaster recovery process.</span></span> <span data-ttu-id="d8ccc-105">Bei diesem Test simuliert einen vollständige Hardwarefehler für einen Server, und wird sichergestellt, dass die Ressourcen, Pläne und Daten für die Wiederherstellung verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="d8ccc-105">This test will simulate a complete hardware failure for one server, and will help guarantee that the resources, plans, and data are available for recovery.</span></span> <span data-ttu-id="d8ccc-106">Versuchen Sie, den Fokus des Tests jeden Monat drehen, sodass Ihrer Organisation den Ausfall einen anderen Server oder eine sonstige Codekomponente Geräte bei jedem überprüft.</span><span class="sxs-lookup"><span data-stu-id="d8ccc-106">Try to rotate the focus of the test each month so that your organization tests the failure of a different server or other piece of equipment every time.</span></span> 

<span data-ttu-id="d8ccc-p102">Beachten Sie, dass der Zeitplan, nach dem Organisationen Notfallwiederherstellungstests durchführen, unterschiedlich ist. Es ist sehr wichtig, dass Notfallwiederherstellungstests nicht ignoriert oder vernachlässigt werden.</span><span class="sxs-lookup"><span data-stu-id="d8ccc-p102">Note that the schedule by which organizations perform Disaster Recovery testing will vary. It is very important that disaster recovery testing is not ignored or neglected.</span></span> 

<span data-ttu-id="d8ccc-109">Exportieren Sie Ihre Skype für Business Server-Topologie, Richtlinien und-Konfigurationseinstellungen in eine Datei.</span><span class="sxs-lookup"><span data-stu-id="d8ccc-109">Export your Skype for Business Server topology, policies, and configuration settings to a file.</span></span> <span data-ttu-id="d8ccc-110">Unter anderem kann diese Datei nach einem Upgrade, einem Hardwareausfall oder einem anderen Problem, das zu Datenverlust geführt hat, zum Wiederherstellen dieser Informationen im zentralen Verwaltungsspeicher verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="d8ccc-110">Among other things, this file can then be used to restore this information to the Central Management store after an upgrade, a hardware failure, or some other issue has resulted in data loss.</span></span>

<span data-ttu-id="d8ccc-111">Importieren Sie Ihre Skype für Business Server-Topologie, Richtlinien und Konfigurationseinstellungen auf dem zentralen Verwaltungsspeicher oder auf dem lokalen Computer wie in den folgenden Befehlen gezeigt:</span><span class="sxs-lookup"><span data-stu-id="d8ccc-111">Import your Skype for Business Server topology, policies, and configuration settings to either the Central Management store or to the local computer as shown in the following commands:</span></span> 

`Import-CsConfiguration -ByteInput <Byte[]> [-Force <SwitchParameter>] [-LocalStore <SwitchParameter>]`

`Import-CsConfiguration -FileName <String> [-Force <SwitchParameter>] [-LocalStore <SwitchParameter>]` 

<span data-ttu-id="d8ccc-112">So sichern Sie Produktionsdaten</span><span class="sxs-lookup"><span data-stu-id="d8ccc-112">To back up production data:</span></span>

- <span data-ttu-id="d8ccc-113">Sichern Sie die Datenbanken RTC und LCSLog mithilfe der standardmäßigen SQL Server backup-Vorgang, um die Datenbank auf eine Datei oder auf Band Sicherungsmedium dump.</span><span class="sxs-lookup"><span data-stu-id="d8ccc-113">Back up the RTC and LCSLog databases by using the standard SQL Server backup process to dump the database to a file or tape dump device.</span></span>
- <span data-ttu-id="d8ccc-114">Verwenden Sie eine Sicherungsanwendung von einem Drittanbieter, um die Daten in einer Datei oder auf einem Band zu sichern.</span><span class="sxs-lookup"><span data-stu-id="d8ccc-114">Use third-party backup application to back up the data to file or to tape.</span></span>
- <span data-ttu-id="d8ccc-115">Verwenden Sie das Cmdlet „Export-CsUserData“, um einen XML-Export der gesamten RTC-Datenbank zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="d8ccc-115">Use the Export-CsUserData cmdlet to create an XML export of the whole RTC database.</span></span>
- <span data-ttu-id="d8ccc-116">Verwenden Sie die Datei System oder Drittanbieter-Sicherung um zu sichernden Daten meeting Inhalte und Kompatibilitätsdaten von Protokollen.</span><span class="sxs-lookup"><span data-stu-id="d8ccc-116">Use the file system backup or third-party backup to back up meeting content and compliance logs.</span></span>
- <span data-ttu-id="d8ccc-117">Verwenden Sie das Export-CsConfiguration-Befehlszeilentool zum Sichern von Skype für Business Server-Einstellungen.</span><span class="sxs-lookup"><span data-stu-id="d8ccc-117">Use the Export-CsConfiguration command-line tool to back up Skype for Business Server settings.</span></span>

<span data-ttu-id="d8ccc-118">Der erste Schritt in der Failoverprozedur besteht in einer erzwungenen Verschiebung von Benutzern aus dem Produktionspool in den Notfallwiederherstellungspool.</span><span class="sxs-lookup"><span data-stu-id="d8ccc-118">The first step in the failover procedure includes a forced move of users from the production pool to the Disaster Recovery pool.</span></span> <span data-ttu-id="d8ccc-119">Es handelt sich dabei um eine erzwungene Verschiebung, da der Produktionspool nicht verfügbar ist, um die Benutzerumsetzung zu akzeptieren.</span><span class="sxs-lookup"><span data-stu-id="d8ccc-119">This will be a forced move because the production pool won't be available to accept the user relocation.</span></span>

<span data-ttu-id="d8ccc-120">Die Skype für Business Server Verschiebens Benutzer ist praktisch eine Änderung für ein Attribut für das Konto Benutzerobjekt zusätzlich zu einem Datensatz Update auf der RTC-SQL-Datenbank.</span><span class="sxs-lookup"><span data-stu-id="d8ccc-120">The Skype for Business Server move user process is effectively a change to an attribute on the user account object in addition to a record update on the RTC SQL database.</span></span> <span data-ttu-id="d8ccc-121">Diese Daten können wiederhergestellt werden aus der ursprünglichen backup Dump-Gerät aus der Produktion SQL Server mithilfe der standardmäßigen SQL Server Wiederherstellungsvorgang oder mithilfe eines Drittanbieters-Sicherung/Wiederherstellung Dienstprogramm.</span><span class="sxs-lookup"><span data-stu-id="d8ccc-121">This data can be restored from the original backup dump device from the production SQL Server using the standard SQL Server restore process, or using a third-party backup/restore utility.</span></span>

<span data-ttu-id="d8ccc-122">Nach der Wiederherstellung dieser Daten können wie gewohnt Benutzer effektiv Verbinden mit den Disaster Recovery-Pool, und betreiben.</span><span class="sxs-lookup"><span data-stu-id="d8ccc-122">After this data is restored, users can effectively connect to the Disaster Recovery pool, and operate as usual.</span></span> <span data-ttu-id="d8ccc-123">Um Benutzern die Verbindung zu dem Pool Disaster Recovery zu aktivieren, wird eine DNS-Datensatz Änderung erforderlich sein.</span><span class="sxs-lookup"><span data-stu-id="d8ccc-123">To enable users to connect to the Disaster Recovery pool, a DNS record change will be required.</span></span>

<span data-ttu-id="d8ccc-124">Clients verwenden die automatische Konfiguration und der DNS-SRV-Einträge werden die Produktion Skype für Business Pool verweist:</span><span class="sxs-lookup"><span data-stu-id="d8ccc-124">The production Skype for Business pool will be referenced by clients using the auto-configuration and DNS SRV records of:</span></span>

- <span data-ttu-id="d8ccc-125">SRV: _sip. \<Domain> /CNAME: SIP. \<Domain></span><span class="sxs-lookup"><span data-stu-id="d8ccc-125">SRV: _sip._tls.\<domain> /CNAME: SIP.\<domain></span></span>
- <span data-ttu-id="d8ccc-126">CNAME: SIP. \<Domain> /cvc-pool-1. \<Domain></span><span class="sxs-lookup"><span data-stu-id="d8ccc-126">CNAME: SIP.\<domain> /cvc-pool-1.\<domain></span></span>

<span data-ttu-id="d8ccc-127">Zur Vereinfachung des Failovers muss dieser CNAME-Eintrag so aktualisiert werden, dass er auf den DROCSPool-FQDN verweist:</span><span class="sxs-lookup"><span data-stu-id="d8ccc-127">To facilitate the failover, this CNAME record must be updated to reference the DROCSPool FQDN:</span></span>

- <span data-ttu-id="d8ccc-128">CNAME: SIP.<domain></span><span class="sxs-lookup"><span data-stu-id="d8ccc-128">CNAME: SIP.<domain></span></span> <span data-ttu-id="d8ccc-129">/ DROCSPool. \<Domain></span><span class="sxs-lookup"><span data-stu-id="d8ccc-129">/DROCSPool.\<domain></span></span>
- <span data-ttu-id="d8ccc-130">SIP. \<Domain></span><span class="sxs-lookup"><span data-stu-id="d8ccc-130">Sip.\<domain></span></span>
- <span data-ttu-id="d8ccc-131">AV.\<Domain></span><span class="sxs-lookup"><span data-stu-id="d8ccc-131">AV.\<domain></span></span>
- <span data-ttu-id="d8ccc-132">Webconf. \<Domain></span><span class="sxs-lookup"><span data-stu-id="d8ccc-132">webconf.\<domain></span></span>
