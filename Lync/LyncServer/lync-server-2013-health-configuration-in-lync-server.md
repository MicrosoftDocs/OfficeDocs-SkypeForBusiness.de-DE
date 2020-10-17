---
title: 'Lync Server 2013: Integritäts Konfiguration in lync Server'
description: 'Lync Server 2013: Integritäts Konfiguration in lync Server.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Health configuration in Lync Server 2013
ms:assetid: c00a8c8e-c2d2-4557-8c42-211c7cc96550
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205234(v=OCS.15)
ms:contentKeyID: 48185305
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 999a6d5401cb34382a4120f9255c91c846f72422
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48552851"
---
# <a name="health-configuration-in-lync-server-2013"></a><span data-ttu-id="ad827-103">Integritäts Konfiguration in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ad827-103">Health configuration in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ad827-104">_**Letztes Änderungsstand des Themas:** 2012-10-22_</span><span class="sxs-lookup"><span data-stu-id="ad827-104">_**Topic Last Modified:** 2012-10-22_</span></span>

<span data-ttu-id="ad827-105">Zwischen verschiedenen Websites, Microsoft Knowledge Base-Artikeln und lync Server Resource Kit-Tools sind Administratoren, die bei der Ausführung von lync Server auf Probleme stoßen, nie weit weg, um diese Probleme zu lösen.</span><span class="sxs-lookup"><span data-stu-id="ad827-105">Between various websites, Microsoft Knowledge Base articles, and Lync Server Resource Kit tools, administrators who encounter problems when running Lync Server are never far from a way to solve those problems.</span></span>

<span data-ttu-id="ad827-106">Offensichtlich gibt es keine Möglichkeit sicherzustellen, dass Probleme mit lync Server 2013 nie auftreten, da lync Server von vielen Dingen wie Netzwerk abstürzen und Hardwarefehlern betroffen sein können, die das Produkt selbst nicht steuern kann.</span><span class="sxs-lookup"><span data-stu-id="ad827-106">Obviously there is no way to guarantee that you will never encounter problems with Lync Server 2013 because Lync Server can be affected by many things—like network crashes and hardware failures—that the product itself cannot control.</span></span> <span data-ttu-id="ad827-107">Durch die Implementierung der Zustandsüberwachung können Administratoren potenzielle Probleme ermitteln, bevor sie zu wirklichen Problemen werden.</span><span class="sxs-lookup"><span data-stu-id="ad827-107">By implementing health monitoring, administrators can identify potential problems before they turn into actual problems.</span></span> <span data-ttu-id="ad827-108">Administratoren können beispielsweise die lync Server Überwachung verwenden, um Trends und Tendenzen zu identifizieren.</span><span class="sxs-lookup"><span data-stu-id="ad827-108">For example, administrators can use Lync Server monitoring to identify trends and tendencies.</span></span> <span data-ttu-id="ad827-109">So kann beispielsweise eine stete Zunahme der Anzahl von Audio-/Videokonferenzen ein Hinweis darauf sein, dass die Kapazität erhöht werden muss, um eine Überlastung des Systems zu verhindern.</span><span class="sxs-lookup"><span data-stu-id="ad827-109">For example, a steady increase in the number of audio/video conferences might suggest a need to add capacity before the system becomes overloaded.</span></span>

<span data-ttu-id="ad827-110">Auf ähnliche Weise können Administratoren System Center Operations Manager verwenden, um beim Auftreten bestimmter Ereignisse Echtzeitwarnungen auszugeben und synthetische Transaktionen auszuführen, mit denen das System proaktiv getestet wird.</span><span class="sxs-lookup"><span data-stu-id="ad827-110">In a similar fashion, administrators can use System Center Operations Manager to do such things as issue real-time alerts when specified events occur, and to run synthetic transactions that proactively test the system.</span></span> <span data-ttu-id="ad827-111">Synthetische Transaktionen werden in lync Server verwendet, um sicherzustellen, dass Benutzer allgemeine Aufgaben wie das Anmelden am System, das Austauschen von Chatnachrichten oder das Telefonieren von Anrufen im öffentlichen Telefonnetz (PSTN) erfolgreich ausführen können.</span><span class="sxs-lookup"><span data-stu-id="ad827-111">Synthetic transactions are used in Lync Server to verify that users are able to successfully complete common tasks such as logging on to the system, exchanging instant messages, or making calls to a phone located on the public switched telephone network (PSTN).</span></span> <span data-ttu-id="ad827-112">Beispielsweise können Sie diese Tests regelmäßig ausführen, um potenzielle Probleme mit Benutzern bei der Anmeldung bei lync Server zu warnen, und Sie haben die Möglichkeit, das Problem zu beheben, bevor Ihr Support Team mit Anrufen von Benutzern überflutet wird, die keine Verbindung herstellen können.</span><span class="sxs-lookup"><span data-stu-id="ad827-112">For example, periodically running these tests can alert you to potential problems with users logging on to Lync Server, and give you a chance to correct the problem before your support team is flooded with calls from users unable to make a connection.</span></span> <span data-ttu-id="ad827-113">Durch die Verwendung von System Center Operations Manager zur Ausführung dieser synthetischen Transaktionen können Administratoren die Bereitstellung von lync Server routinemäßig 24 Stunden lang kontinuierlich überwachen, ohne vieles mehr tun zu müssen, als auf eventuell ausgegebene Warnungen zu reagieren.</span><span class="sxs-lookup"><span data-stu-id="ad827-113">By using System Center Operations Manager to run these synthetic transactions, administrators can routinely monitor their deployment of Lync Server continuously for 24 hours every day without having to do much of anything beyond responding to any alerts that might be issued.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="ad827-114">Für lync Server 2013 kann das Management Pack für System Center Operations Manager auch "externe" Probleme erkennen, die sich negativ auf lync Server auswirken können.</span><span class="sxs-lookup"><span data-stu-id="ad827-114">For Lync Server 2013, the Management Pack for System Center Operations Manager is also able to detect "external" issues that can adversely affect Lync Server.</span></span> <span data-ttu-id="ad827-115">Administratoren können beispielsweise benachrichtigt werden, wenn Internet Information Services (IIS) offline geht, Systemressourcen auf einem lync Server Computer unter einen bestimmten Betrag fallen oder wenn ein lync Server Computer einen Hardwarefehler auftritt.</span><span class="sxs-lookup"><span data-stu-id="ad827-115">For example, administrators can be notified if Internet Information Services (IIS) goes offline, system resources on a Lync Server computer fall below a specified amount, or a Lync Server computer experiences a hardware failure.</span></span>



</div>

<span data-ttu-id="ad827-116">Die Integritäts Konfiguration in lync Server 2013 ist um System Center Operations Manager und die Verwendung von lync Server Management Packs aufgebaut.</span><span class="sxs-lookup"><span data-stu-id="ad827-116">Health configuration in Lync Server 2013 is built around System Center Operations Manager and the use of Lync Server Management Packs.</span></span> <span data-ttu-id="ad827-117">Diese Management Packs weisen die folgenden neuen Features und Verbesserungen auf:</span><span class="sxs-lookup"><span data-stu-id="ad827-117">These Management Packs include a number of new features and enhancements, including:</span></span>

  - <span data-ttu-id="ad827-118">**Szenarioverfügbarkeit an jedem Standort.**</span><span class="sxs-lookup"><span data-stu-id="ad827-118">**Scenario availability from any location.**</span></span> <span data-ttu-id="ad827-119">Mit dem lync Server 2010 Management Pack wurde das Konzept der Überwachung der Verfügbarkeit von Endbenutzerszenarien mit synthetischen Transaktionen eingeführt.</span><span class="sxs-lookup"><span data-stu-id="ad827-119">The Lync Server 2010 Management Pack introduced the concept of monitoring end user scenario availability with synthetic transactions.</span></span> <span data-ttu-id="ad827-120">In lync Server 2013 verfügen diese Agents über mehr synthetische Transaktionen und können an einer Vielzahl von Speicherorten innerhalb des Unternehmens ausgeführt werden, von Remotestandorten außerhalb des Unternehmens bis hin zu Zweigstellen-Appliances und lync Server 2010-Bereitstellungen, um ältere Edge-Bereitstellungen mit Abdeckung zu versehen.</span><span class="sxs-lookup"><span data-stu-id="ad827-120">In Lync Server 2013, these agents have more synthetic transactions and can be run from a variety of locations inside the enterprise, from remote geographic locations outside of the enterprise, against branch office appliances and against Lync Server 2010 deployments to add coverage to legacy Edge deployments.</span></span>

  - <span data-ttu-id="ad827-121">**Synthetische Transaktionsprotokolle.**</span><span class="sxs-lookup"><span data-stu-id="ad827-121">**Synthetic transaction logs.**</span></span> <span data-ttu-id="ad827-122">Wenn bei einer synthetischen Transaktion ein Fehler auftritt, haben Administratoren Zugriff auf HTML-Protokolle, um die Ursache für den Fehler zu bestimmen.</span><span class="sxs-lookup"><span data-stu-id="ad827-122">When a synthetic transaction fails, administrators have access to HTML logs to help determine what failed.</span></span> <span data-ttu-id="ad827-123">Hierzu gehört das Ermitteln der fehlgeschlagenen Aktion, die Wartezeit jeder Aktion, die zum Ausführen des Tests verwendete Befehlszeile sowie der gefundene Fehler.</span><span class="sxs-lookup"><span data-stu-id="ad827-123">This includes understanding which action failed, the latency of each action, the command-line used to run the test, and the error that was encountered.</span></span>

  - <span data-ttu-id="ad827-124">**Höhere Anrufzuverlässigkeitsabdeckung.**</span><span class="sxs-lookup"><span data-stu-id="ad827-124">**Increased call reliability coverage.**</span></span> <span data-ttu-id="ad827-125">Mit dem lync Server 2010 Management Packs wurde die Anruf Zuverlässigkeits Warnung zur Erkennung schwerer Verbindungsprobleme eingeführt, die sich auf die Audioanrufe von Endbenutzern auswirken.</span><span class="sxs-lookup"><span data-stu-id="ad827-125">The Lync Server 2010 Management Pack introduced call reliability alerting to detect severe connectivity issues that affect the audio calls of end users.</span></span> <span data-ttu-id="ad827-126">Die lync Server 2013 Management Packs bieten eine Abdeckung für Peer-zu-Peer-Sofortnachrichten (Instant Messaging) und andere grundlegende Konferenzfunktionen zur Maximierung der Reichweite bei gleichzeitiger Reduzierung des Rauschens.</span><span class="sxs-lookup"><span data-stu-id="ad827-126">The Lync Server 2013 Management Packs add coverage for peer-to-peer instant messaging (IM) and other basic conferencing features to maximize coverage while reducing noise.</span></span>

  - <span data-ttu-id="ad827-127">**Abhängigkeitsüberwachung.**</span><span class="sxs-lookup"><span data-stu-id="ad827-127">**Dependency monitoring.**</span></span> <span data-ttu-id="ad827-128">Lync Server Szenarien können aufgrund einer Vielzahl externer Faktoren wie IIS offline, CPU-und Arbeitsspeicherressourcen sowie Datenträgerproblemen fehlschlagen.</span><span class="sxs-lookup"><span data-stu-id="ad827-128">Lync Server scenarios can fail due to a variety of external factors such as IIS being offline, limited CPU and memory resources, and disk issues.</span></span> <span data-ttu-id="ad827-129">Die neuen Management Packs überprüfen mehrere wichtige Abhängigkeiten, um sicherzustellen, dass Administratoren ihre Auswirkungen kennen.</span><span class="sxs-lookup"><span data-stu-id="ad827-129">The new management packs check several critical dependencies to ensure administrators are aware of their impact.</span></span>

  - <span data-ttu-id="ad827-130">**Erweiterte Berichterstellung.**</span><span class="sxs-lookup"><span data-stu-id="ad827-130">**Enhanced reporting.**</span></span> <span data-ttu-id="ad827-131">Es gibt eine Reihe von Berichten, damit Administratoren die Szenarioverfügbarkeit abschätzen, die Kapazität planen sowie die Komponenten mit den meisten Problemen ermitteln können.</span><span class="sxs-lookup"><span data-stu-id="ad827-131">A set of reports to help administrators estimate scenario availability, plan for capacity, and see which components are experiencing the most issues.</span></span>

<span data-ttu-id="ad827-132">Die Management Packs enthalten auch eine Vielzahl von Funktionen, die Ihnen bei der Erkennung und Diagnose zur Verfügung stehen, um in Echtzeit einen Einblick in die Integrität ihrer lync Server Bereitstellung zu geben.</span><span class="sxs-lookup"><span data-stu-id="ad827-132">The Management Packs also include a variety of features to help detect and diagnose provide real-time visibility into the health your Lync Server deployment.</span></span> <span data-ttu-id="ad827-133">Eine Aufstellung dieser Features finden Sie in der folgenden Tabelle.</span><span class="sxs-lookup"><span data-stu-id="ad827-133">These features are listed in the following table.</span></span>

### <a name="management-pack-features"></a><span data-ttu-id="ad827-134">Management Pack-Features</span><span class="sxs-lookup"><span data-stu-id="ad827-134">Management Pack Features</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="ad827-135">Feature</span><span class="sxs-lookup"><span data-stu-id="ad827-135">Feature</span></span></th>
<th><span data-ttu-id="ad827-136">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="ad827-136">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ad827-137">Synthetische Transaktionen</span><span class="sxs-lookup"><span data-stu-id="ad827-137">Synthetic Transactions</span></span></p></td>
<td><p><span data-ttu-id="ad827-138">Windows PowerShell-Cmdlets, die von verschiedenen Standorten aus ausgeführt werden können, um sicherzustellen, dass Endbenutzerszenarien wie Anmeldung, Anwesenheitsinformationen, Chatnachrichten und Konferenzen bereit stehen.</span><span class="sxs-lookup"><span data-stu-id="ad827-138">Windows PowerShell cmdlets that can be run from various locations to ensure that end user scenarios such as sign-in, presence, IM, and conferencing are readily available to end users.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ad827-139">Warnungen zur Anrufzuverlässigkeit</span><span class="sxs-lookup"><span data-stu-id="ad827-139">Call Reliability Alerts</span></span></p></td>
<td><p><span data-ttu-id="ad827-140">Datenbankabfragen für Kommunikationsdatensätze (KDS).</span><span class="sxs-lookup"><span data-stu-id="ad827-140">Database queries for Call Detail Records (CDR).</span></span> <span data-ttu-id="ad827-141">Diese Einträge werden von Front-End-Servern geschrieben, um zu reflektieren, ob Endbenutzer eine Verbindung mit einem Anruf herstellen konnten oder warum ein Anruf beendet wurde.</span><span class="sxs-lookup"><span data-stu-id="ad827-141">These records are written by Front End Servers to reflect whether end users were able to connect to a call or why a call was terminated.</span></span> <span data-ttu-id="ad827-142">Diese Abfragen führen zu Warnungen, wenn viele Endbenutzer Konnektivitätsprobleme bei Peer-zu-Peer-Anrufen oder einfacher Konferenzfunktionalität haben.</span><span class="sxs-lookup"><span data-stu-id="ad827-142">These queries result in alerts that indicate when a wide range of end users are experiencing connectivity issues for peer-to-peer calls or basic conferencing functionality.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ad827-143">Warnungen zur Medienqualität</span><span class="sxs-lookup"><span data-stu-id="ad827-143">Media Quality Alerts</span></span></p></td>
<td><p><span data-ttu-id="ad827-p112">Datenbankabfragen für Berichte zu QoE-Daten (Quality of Experience), die von Clients am Ende jedes Anrufs veröffentlicht werden. Diese Abfragen führen zu Warnungen, die auf Szenarien hinweisen, bei denen Benutzer während Anrufen und Konferenzen wahrscheinlich eine mangelhafte Medienqualität feststellen. Die Daten basieren auf wichtigen Metriken wie z. B. Paketwartezeit und Paketverlust, die bekanntermaßen einen direkten Beitrag zur Anrufqualität leisten.</span><span class="sxs-lookup"><span data-stu-id="ad827-p112">Database queries that look at Quality of Experience (QoE) reports published by clients at the end of each call. These queries result in alerts that pinpoint scenarios where users are likely to be experiencing poor media quality during calls and conferences. The data is built upon key metrics such as packet latency and loss, metrics that are known to directly contribute to call quality.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ad827-147">Komponentenintegrität</span><span class="sxs-lookup"><span data-stu-id="ad827-147">Component Health</span></span></p></td>
<td><p><span data-ttu-id="ad827-p113">Einzelne Serverkomponenten lösen mithilfe von Ereignisprotokollen und Leistungsindikatoren Warnungen aus. Diese Warnungen weisen auf Fehlerbedingungen hin, die beträchtliche negative Auswirkungen auf eines oder mehrere Endbenutzerszenarien haben können. Diese Warnungen können auch ein Hinweis auf eine Reihe anderer Fehlerbedingungen sein, wie z. B. nicht ausgeführte Dienste, hohe Fehlerraten, lange Nachrichtenwartezeiten oder Konnektivitätsprobleme.</span><span class="sxs-lookup"><span data-stu-id="ad827-p113">Individual server components raise alerts by using event logs and performance counters. These alerts indicate failure conditions that can severely impact one or more end user scenarios. These alerts can also indicate a variety of other failure conditions, including services not running, high failure rates, high message latency, or connectivity issues.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ad827-151">Abhängigkeitsintegrität</span><span class="sxs-lookup"><span data-stu-id="ad827-151">Dependency Health</span></span></p></td>
<td><p><span data-ttu-id="ad827-152">Fehler können aus einer Vielzahl von externen Gründen auftreten.</span><span class="sxs-lookup"><span data-stu-id="ad827-152">Failures can occur for a variety of external reasons.</span></span> <span data-ttu-id="ad827-153">Die Management Packs überwachen und erfassen nun Daten für einige der wichtigen externen Abhängigkeiten, die auf schwerwiegende Probleme hindeuten können, einschließlich der Verfügbarkeit von IIS, der CPU-und Speicherauslastung von Servern und Prozessen sowie Datenträger Metriken.</span><span class="sxs-lookup"><span data-stu-id="ad827-153">The management packs now monitor and collect data for some of the critical external dependencies that might indicate severe issues, including IIS availability, CPU and memory usage of servers and processes, and disk metrics.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="ad827-154">Die vom System ausgelösten Warnungen wurden in die folgenden drei allgemeinen Kategorien unterteilt:</span><span class="sxs-lookup"><span data-stu-id="ad827-154">The alerts issued by the system have been classified into three general categories:</span></span>

  - <span data-ttu-id="ad827-155">**Warnungen mit hoher Priorität.**</span><span class="sxs-lookup"><span data-stu-id="ad827-155">**High-priority Alerts.**</span></span> <span data-ttu-id="ad827-156">Diese Warnungen weisen auf Bedingungen hin, die für große Benutzergruppen zu Dienstausfällen führen.</span><span class="sxs-lookup"><span data-stu-id="ad827-156">These alerts indicate conditions that will cause service outages for large groups of users.</span></span> <span data-ttu-id="ad827-157">Beispielsweise ist ein Komponentenfehler auf einem einzelnen Computer keine Warnung mit hoher Priorität, da lync Server 2013 über integrierte Features für hohe Verfügbarkeit verfügt.</span><span class="sxs-lookup"><span data-stu-id="ad827-157">For example, a component failure on a single machine is not a high-priority alert because Lync Server 2013 has built-in high availability features.</span></span> <span data-ttu-id="ad827-158">Warnungen mit hoher Priorität sind dagegen Probleme, die ernst genug sind, um "Administratoren nachts aus dem Bett zu holen".</span><span class="sxs-lookup"><span data-stu-id="ad827-158">Instead, high-priority alerts represent problems serious enough “to wake up administrators at night.”</span></span> <span data-ttu-id="ad827-159">Von synthetischen Transaktionen und Offlinediensten festgestellte Ausfälle (z. B. Audio-/Videokonferenzen) gelten als Warnungen mit hoher Priorität.</span><span class="sxs-lookup"><span data-stu-id="ad827-159">Outages detected by synthetic transactions and offline services (for example, audio/video conferencing) qualify as high-priority alerts.</span></span>

  - <span data-ttu-id="ad827-160">**Warnungen mittlerer Priorität.**.</span><span class="sxs-lookup"><span data-stu-id="ad827-160">**Medium-priority alerts.**.</span></span> <span data-ttu-id="ad827-161">Diese Warnungen sind ein Hinweis auf Bedingungen, die einen Teil der Benutzer betreffen, oder sie sind ein Hinweis auf eine beeinträchtigte Anrufqualität.</span><span class="sxs-lookup"><span data-stu-id="ad827-161">These alerts indicate conditions that affect a subset of users or indicate call quality degradation.</span></span> <span data-ttu-id="ad827-162">Dies beinhaltet Probleme wie z. B. Komponentenfehler, Wartezeiten bei der Anrufverbindungsherstellung oder beeinträchtigte Audioqualität bei Anrufen.</span><span class="sxs-lookup"><span data-stu-id="ad827-162">That includes problems such as component failures, latency in call establishment, or degraded audio quality in call.</span></span> <span data-ttu-id="ad827-163">Warnungen in dieser Kategorie sind statusbehaftet und verweisen auf den aktuellen Status des Problems.</span><span class="sxs-lookup"><span data-stu-id="ad827-163">Alerts in this category are stateful and indicate the current status of the issue.</span></span> <span data-ttu-id="ad827-164">Angenommen, die Zeiten für die Anrufverbindungsherstellung überschreiten den Schwellenwert für Warnungen.</span><span class="sxs-lookup"><span data-stu-id="ad827-164">For example, suppose your call establishment times exceed the alert threshold.</span></span> <span data-ttu-id="ad827-165">Wenn die Anruf Erstellungszeiten wieder normal sind, werden diese Warnungen automatisch in System Center Operations Manager aufgelöst.</span><span class="sxs-lookup"><span data-stu-id="ad827-165">If call establishment times return to normal, these alerts will be auto-resolved in System Center Operations Manager.</span></span> <span data-ttu-id="ad827-166">Bei diesen Warnungen wird davon ausgegangen, dass sie von einem Administrator am selben Arbeitstag geprüft werden.</span><span class="sxs-lookup"><span data-stu-id="ad827-166">The expectation for these alerts is that an administrator will look at them on the same business day.</span></span>

  - <span data-ttu-id="ad827-167">**Andere Warnungen.**</span><span class="sxs-lookup"><span data-stu-id="ad827-167">**Other alerts.**</span></span> <span data-ttu-id="ad827-168">Hierbei handelt es sich um Warnungen von Komponenten, die einen bestimmten Benutzer oder einen Teil der Benutzer betreffen können.</span><span class="sxs-lookup"><span data-stu-id="ad827-168">These are alerts from components that might affect a specific user or subset of users.</span></span> <span data-ttu-id="ad827-169">Beispielsweise könnte es sein, dass der Adressbuchdienst den Active Directory-Eintrag eines bestimmten Benutzers nicht analysieren konnte.</span><span class="sxs-lookup"><span data-stu-id="ad827-169">For example, perhaps the Address Book service could not parse the Active Directory entry of a given user.</span></span> <span data-ttu-id="ad827-170">Bei diesen Warnungen wird davon ausgegangen, dass sie von Administratoren bearbeitet werden, sobald sie dafür Zeit haben.</span><span class="sxs-lookup"><span data-stu-id="ad827-170">The expectation for these alerts is that administrators will get to them when they have time available.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="ad827-171">Inhalt dieses Abschnitts</span><span class="sxs-lookup"><span data-stu-id="ad827-171">In This Section</span></span>

  - [<span data-ttu-id="ad827-172">Konfigurieren lync Server 2013 für die Verwendung mit System Center Operations Manager</span><span class="sxs-lookup"><span data-stu-id="ad827-172">Configuring Lync Server 2013 to work with System Center Operations Manager</span></span>](lync-server-2013-configuring-lync-server-to-work-with-system-center-operations-manager.md)

  - [<span data-ttu-id="ad827-173">Verwenden der umfangreichen Protokollierung für synthetische Transaktionen in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ad827-173">Using rich logging for synthetic transactions in Lync Server 2013</span></span>](lync-server-2013-using-rich-logging-for-synthetic-transactions.md)

  - [<span data-ttu-id="ad827-174">Verwenden von Microsoft SQL Server 2008 R2 als System Center Operations Manager-Datenbank für lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ad827-174">Using Microsoft SQL Server 2008 R2 as your System Center Operations Manager database for Lync Server 2013</span></span>](lync-server-2013-using-microsoft-sql-server-2008-r2-as-your-system-center-operations-manager-database.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

