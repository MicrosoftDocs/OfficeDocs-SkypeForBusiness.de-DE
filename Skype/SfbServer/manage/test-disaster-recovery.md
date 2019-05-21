---
title: Disaster Recovery-Tests in Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Durchführen einer Systemwiederherstellung für einen Skype for Business Server-Pool Server zum Testen des dokumentierten Disaster Recovery-Prozesses
ms.openlocfilehash: d65f8bfa512a3954728e09d659b571335d32a379
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2019
ms.locfileid: "34279214"
---
# <a name="disaster-recovery-testing-in-skype-for-business-server"></a><span data-ttu-id="b127b-103">Disaster Recovery-Tests in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="b127b-103">Disaster recovery testing in Skype for Business Server</span></span>

<span data-ttu-id="b127b-104">Führen Sie eine Systemwiederherstellung für einen Skype for Business Server-Pool Server aus, um Ihren dokumentierten Disaster Recovery-Prozess zu testen.</span><span class="sxs-lookup"><span data-stu-id="b127b-104">Perform a system recovery for a Skype for Business Server pool server to test your documented disaster recovery process.</span></span> <span data-ttu-id="b127b-105">Mit diesem Test wird ein vollständiger Hardwarefehler für einen Server simuliert, und es wird sichergestellt, dass die Ressourcen, Pläne und Daten für die Wiederherstellung verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="b127b-105">This test will simulate a complete hardware failure for one server, and will help guarantee that the resources, plans, and data are available for recovery.</span></span> <span data-ttu-id="b127b-106">Versuchen Sie, den Fokus des Tests monatlich zu drehen, damit Ihre Organisation den Fehler eines anderen Servers oder eines anderen Geräts jedes Mal testet.</span><span class="sxs-lookup"><span data-stu-id="b127b-106">Try to rotate the focus of the test each month so that your organization tests the failure of a different server or other piece of equipment every time.</span></span> 

<span data-ttu-id="b127b-p102">Beachten Sie, dass der Zeitplan, nach dem Organisationen Notfallwiederherstellungstests durchführen, unterschiedlich ist. Es ist sehr wichtig, dass Notfallwiederherstellungstests nicht ignoriert oder vernachlässigt werden.</span><span class="sxs-lookup"><span data-stu-id="b127b-p102">Note that the schedule by which organizations perform Disaster Recovery testing will vary. It is very important that disaster recovery testing is not ignored or neglected.</span></span> 

<span data-ttu-id="b127b-109">Exportieren Sie Ihre Skype for Business Server-Topologie,-Richtlinien und-Konfigurationseinstellungen in eine Datei.</span><span class="sxs-lookup"><span data-stu-id="b127b-109">Export your Skype for Business Server topology, policies, and configuration settings to a file.</span></span> <span data-ttu-id="b127b-110">Unter anderem kann diese Datei nach einem Upgrade, einem Hardwareausfall oder einem anderen Problem, das zu Datenverlust geführt hat, zum Wiederherstellen dieser Informationen im zentralen Verwaltungsspeicher verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="b127b-110">Among other things, this file can then be used to restore this information to the Central Management store after an upgrade, a hardware failure, or some other issue has resulted in data loss.</span></span>

<span data-ttu-id="b127b-111">Importieren Sie Ihre Skype for Business Server-Topologie,-Richtlinien und-Konfigurationseinstellungen entweder in den zentralen Verwaltungsspeicher oder auf den lokalen Computer, wie in den folgenden Befehlen gezeigt:</span><span class="sxs-lookup"><span data-stu-id="b127b-111">Import your Skype for Business Server topology, policies, and configuration settings to either the Central Management store or to the local computer as shown in the following commands:</span></span> 

`Import-CsConfiguration -ByteInput <Byte[]> [-Force <SwitchParameter>] [-LocalStore <SwitchParameter>]`

`Import-CsConfiguration -FileName <String> [-Force <SwitchParameter>] [-LocalStore <SwitchParameter>]` 

<span data-ttu-id="b127b-112">So sichern Sie Produktionsdaten:</span><span class="sxs-lookup"><span data-stu-id="b127b-112">To back up production data:</span></span>

- <span data-ttu-id="b127b-113">Sichern Sie die RTC-und LCSLog-Datenbanken mithilfe des standardmäßigen SQL Server-Sicherungsprozesses, um die Datenbank auf ein Datei-oder Bandspeicher Abbildgerät zu übernehmen.</span><span class="sxs-lookup"><span data-stu-id="b127b-113">Back up the RTC and LCSLog databases by using the standard SQL Server backup process to dump the database to a file or tape dump device.</span></span>
- <span data-ttu-id="b127b-114">Verwenden Sie eine Sicherungsanwendung von einem Drittanbieter, um die Daten in einer Datei oder auf einem Band zu sichern.</span><span class="sxs-lookup"><span data-stu-id="b127b-114">Use third-party backup application to back up the data to file or to tape.</span></span>
- <span data-ttu-id="b127b-115">Verwenden Sie das Cmdlet „Export-CsUserData“, um einen XML-Export der gesamten RTC-Datenbank zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="b127b-115">Use the Export-CsUserData cmdlet to create an XML export of the whole RTC database.</span></span>
- <span data-ttu-id="b127b-116">Verwenden Sie das Dateisystem-Backup oder Drittanbieter-Backup, um Besprechungsinhalte und Kompatibilitäts Protokolle zu sichern.</span><span class="sxs-lookup"><span data-stu-id="b127b-116">Use the file system backup or third-party backup to back up meeting content and compliance logs.</span></span>
- <span data-ttu-id="b127b-117">Verwenden Sie das Befehlszeilentool "Exportieren-CsConfiguration", um die Einstellungen für Skype for Business Server zu sichern.</span><span class="sxs-lookup"><span data-stu-id="b127b-117">Use the Export-CsConfiguration command-line tool to back up Skype for Business Server settings.</span></span>

<span data-ttu-id="b127b-118">Der erste Schritt in der Failoverprozedur besteht in einer erzwungenen Verschiebung von Benutzern aus dem Produktionspool in den Notfallwiederherstellungspool.</span><span class="sxs-lookup"><span data-stu-id="b127b-118">The first step in the failover procedure includes a forced move of users from the production pool to the Disaster Recovery pool.</span></span> <span data-ttu-id="b127b-119">Es handelt sich dabei um eine erzwungene Verschiebung, da der Produktionspool nicht verfügbar ist, um die Benutzerumsetzung zu akzeptieren.</span><span class="sxs-lookup"><span data-stu-id="b127b-119">This will be a forced move because the production pool won't be available to accept the user relocation.</span></span>

<span data-ttu-id="b127b-120">Der Skype for Business Server-Prozess "Move User" ist eine Änderung an einem Attribut für das Benutzerkontoobjekt sowie eine Datensatzaktualisierung in der RTC SQL-Datenbank.</span><span class="sxs-lookup"><span data-stu-id="b127b-120">The Skype for Business Server move user process is effectively a change to an attribute on the user account object in addition to a record update on the RTC SQL database.</span></span> <span data-ttu-id="b127b-121">Diese Daten können vom ursprünglichen Backup-Dump-Gerät aus dem Produktions-SQL-Server mithilfe des standardmäßigen SQL Server-Wiederherstellungsprozesses oder mithilfe eines Sicherungs-/Wiederherstellungstools eines Drittanbieters wiederhergestellt werden.</span><span class="sxs-lookup"><span data-stu-id="b127b-121">This data can be restored from the original backup dump device from the production SQL Server using the standard SQL Server restore process, or using a third-party backup/restore utility.</span></span>

<span data-ttu-id="b127b-122">Nach der Wiederherstellung dieser Daten können Benutzer eine Verbindung mit dem Disaster Recovery-Pool herstellen und wie gewohnt funktionieren.</span><span class="sxs-lookup"><span data-stu-id="b127b-122">After this data is restored, users can effectively connect to the Disaster Recovery pool, and operate as usual.</span></span> <span data-ttu-id="b127b-123">Damit Benutzer eine Verbindung mit dem Disaster Recovery-Pool herstellen können, ist eine Änderung des DNS-Eintrags erforderlich.</span><span class="sxs-lookup"><span data-stu-id="b127b-123">To enable users to connect to the Disaster Recovery pool, a DNS record change will be required.</span></span>

<span data-ttu-id="b127b-124">Der Produktions-Skype for Business-Pool wird von Clients, die die automatischen Konfigurations-und DNS-SRV-Einträge verwenden, referenziert:</span><span class="sxs-lookup"><span data-stu-id="b127b-124">The production Skype for Business pool will be referenced by clients using the auto-configuration and DNS SRV records of:</span></span>

- <span data-ttu-id="b127b-125">SRV: _sip. _tls. \<domain>/CNAME: SIP. \<domain></span><span class="sxs-lookup"><span data-stu-id="b127b-125">SRV: _sip._tls.\<domain> /CNAME: SIP.\<domain></span></span>
- <span data-ttu-id="b127b-126">CNAME: SIP. \<domain>/CVC-Pool-1. \<domain></span><span class="sxs-lookup"><span data-stu-id="b127b-126">CNAME: SIP.\<domain> /cvc-pool-1.\<domain></span></span>

<span data-ttu-id="b127b-127">Zur Vereinfachung des Failovers muss dieser CNAME-Eintrag so aktualisiert werden, dass er auf den DROCSPool-FQDN verweist:</span><span class="sxs-lookup"><span data-stu-id="b127b-127">To facilitate the failover, this CNAME record must be updated to reference the DROCSPool FQDN:</span></span>

- <span data-ttu-id="b127b-128">CNAME: SIP.<domain></span><span class="sxs-lookup"><span data-stu-id="b127b-128">CNAME: SIP.<domain></span></span> <span data-ttu-id="b127b-129">/DROCSPool. \<domain></span><span class="sxs-lookup"><span data-stu-id="b127b-129">/DROCSPool.\<domain></span></span>
- <span data-ttu-id="b127b-130">SIP. \<domain></span><span class="sxs-lookup"><span data-stu-id="b127b-130">Sip.\<domain></span></span>
- <span data-ttu-id="b127b-131">AV.\<domain></span><span class="sxs-lookup"><span data-stu-id="b127b-131">AV.\<domain></span></span>
- <span data-ttu-id="b127b-132">webconf. \<domain></span><span class="sxs-lookup"><span data-stu-id="b127b-132">webconf.\<domain></span></span>
