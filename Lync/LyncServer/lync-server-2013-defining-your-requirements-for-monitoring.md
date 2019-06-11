---
title: 'Lync Server 2013: Definieren der Anforderungen Ihrer Organisation für die Überwachung'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Defining your organizations's requirements for monitoring
ms:assetid: d587ff04-9af6-4ac1-ad42-076e7a40ac75
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205284(v=OCS.15)
ms:contentKeyID: 48185491
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c7a81f83cddca46a50f84fb20785a59b20a3db78
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34832681"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="defining-your-requirements-for-monitoring-in-lync-server-2013"></a>Definieren der Anforderungen Ihrer Organisation für die Überwachung in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2012-09-05_

Durch eine optimierte Bereitstellung und Installation der Überwachung in Microsoft lync Server 2013 wurden auch die Prozesse optimiert, die bei der Definition der Anforderungen Ihrer Organisation für die Überwachung erforderlich sind. Es gibt jedoch noch einige wichtige Probleme, die behoben werden sollten, bevor Sie mit der Installation und Konfiguration von lync Server 2013 beginnen:

**Welche Datentypen möchten Sie überwachen?** Mit lync Server 2013 können Sie zwei unterschiedliche Datentypen überwachen: Datenerfassungs Daten (CDR) und QoE-Daten (Quality of Experience). Die Anrufdetailaufzeichnung bietet eine Möglichkeit, die Verwendung von lync Server-Features wie VoIP-Telefon anrufen (Voice over IP) zu überwachen. Instant Messaging (im) Dateiübertragungen; Audio/Video-Konferenzen (A/V); und Anwendungsfreigabesitzungen. Mithilfe dieser Informationen können Sie wissen, welche lync Server-Features verwendet werden (und welche nicht), und es werden auch Informationen darüber bereitgestellt, wann diese Features verwendet werden. Mit der Qualität der Erfahrungsdaten können Sie eine Aufzeichnung der Qualität von Audio-und Videoanrufen in Ihrer Organisation aufrecht erhalten, beispielsweise die Anzahl der verloren gegangenen Netzwerkpakete, Hintergrundgeräusche und die Anzahl der "Jitter" (Unterschiede bei der Paketverzögerung).

Wenn Sie die Überwachung in lync Server 2013 aktivieren, können Sie sowohl die CDR-Überwachung als auch die QoE-Überwachung aktivieren, oder Sie können eine Art von Überwachung aktivieren, während der andere Typ deaktiviert bleibt. Nehmen Sie beispielsweise an, dass Ihre Benutzer nur Instant Messaging und Dateiübertragungen verwenden und keine Audio-oder Videoanrufe tätigen. In diesem Fall kann es wenig Grund für die Aktivierung der QoE-Überwachung geben. Mit lync Server ist es ebenfalls einfach, die Überwachung zu aktivieren und zu deaktivieren, nachdem die Überwachung bereitgestellt wurde. So können Sie beispielsweise die Überwachung bereitstellen, aber zunächst die QoE-Überwachung deaktivieren. Wenn Ihre Benutzer Probleme mit Audio-oder Videoanrufen auftreten, können Sie die QoE-Überwachung aktivieren und diese Daten verwenden, um Sie bei der Problembehandlung zu unterstützen und diese Probleme zu beheben.

Es gibt keinen besonderen Vorteil (oder Nachteil) beim Installieren der Überwachung zur gleichen Zeit, zu der Sie lync Server vs. Installation der Überwachung installieren, nachdem lync Server installiert wurde. Beachten Sie, dass Sie vor der Installation der Überwachung einen Computer zum Hosten des Back-End-überwachungsspeichers auswählen müssen und eine unterstützte Version von SQL Server auf diesem Computer installiert und konfiguriert werden muss, bevor dieser Computer für die Überwachung verwendet werden kann. . Wenn Sie SQL Server bereits auf einem Computer installiert haben und dieser Computereinsatz bereit ist, können Sie die Überwachung zur gleichen Zeit installieren, wenn Sie lync Server installieren. Wenn Sie nicht über einen Back-End-Computer verfügen, können Sie fortfahren, lync Server selbst zu installieren, und dann die Überwachung installieren, sobald der Back-End-Computereinsatz bereit ist.

**Wann möchten Sie die Überwachung installieren?** Die Überwachung kann zur gleichen Zeit installiert und konfiguriert werden, in der Sie lync Server 2013 installieren und konfigurieren. der lync Server-Bereitstellungs-Assistent bietet Ihnen die Möglichkeit, Ihre Front-End-Pools während des Setups mit einer Überwachungsdatenbank zu verknüpfen. Alternativ können Sie die Überwachung installieren, nachdem lync Server selbst installiert wurde. Dies kann mithilfe des Topologie-Generators erfolgen, um Ihre Front-End-Pools und-Server einer Überwachungsdatenbank zuzuordnen und dann die überarbeitete Topologie zu veröffentlichen.

**Wie viele Back-End-Überwachungsdatenbanken benötigen Sie?** Eine einzige Überwachungsdatenbank kann Zehntausende von Benutzern unterstützen (für Microsoft lync Server 2010 wurde geschätzt, dass eine Datenbank für die Überwachung und Archivierung 240.000-Benutzer unterstützenkann). Darüber hinaus kann eine einzelne Überwachungsdatenbank von mehreren Front-End-Pools verwendet werden. Wenn Sie über drei Front-End-Pools in Ihrer Organisation verfügen, können Sie alle drei dieser Pools dem gleichen Back-End-Speicher zuordnen.

Das bedeutet einfach, dass die Datenbankkapazität für viele Organisationen nicht der entscheidende Faktor bei der Bestimmung der Anzahl der erforderlichen Back-End-Überwachungsdatenbanken ist. Vielmehr könnte die Netzwerkgeschwindigkeit ein wichtigerer Faktor sein. Angenommen, es sind drei Front-End-Pools vorhanden, aber einer dieser Pools läuft über eine langsame Netzwerkverbindung. In diesem Fall sollten Sie zwei Überwachungsdatenbanken verwenden: eine Datenbank für die beiden Pools mit der schnellen Netzwerkverbindung und eine separate Datenbank für den Pool mit der langsameren Netzwerkverbindung.

Bei der Planung Ihrer Überwachungsinfrastruktur sollten Sie auch berücksichtigen, dass lync Server 2013 die Verwendung von Spiegeldatenbanken unterstützt. Die „Datenbankspiegelung“ bietet die Möglichkeit, zwei Kopien einer Datenbank gleichzeitig zu verwalten, wobei die Datenbanken auf unterschiedlichen Servern gespeichert werden. Immer wenn Daten in eine primäre Datenbank geschrieben werden, werden diese Daten auch in die Spiegeldatenbank geschrieben. Wenn die primäre Datenbank fehlschlägt oder anderweitig nicht mehr zur Verfügung steht, können Sie mit einem einfachen lync Server PowerShell-Befehl "Failover" zur Spiegeldatenbank durchführen. Beispiel:

    Invoke-CsDatabaseFailover -PoolFqdn atl-cs-001.litwareinc.com -DatabaseType "Monitoring" -NewPrincipal "Mirror"

Dies spielt eine wichtige Rolle für die Planung, da Sie für die Spiegelung die erforderliche Anzahl von Datenbanken verdoppeln müssen. Denn zusätzlich zu jeder primären Datenbank benötigen Sie eine zweite Datenbank als Spiegeldatenbank.

**Benötigen Ihre lync Server-Websites eigene benutzerdefinierte Überwachungskonfigurationen?** Wenn Sie lync Server 2013 installieren, installieren Sie auch globale Sammlungen mit CDR-und QoE-Konfigurationseinstellungen. Diese globalen Auflistungen bieten Ihnen die Möglichkeit, die gleichen CDR-und QoE-Einstellungen auf Ihre gesamte Organisation anzuwenden. In many cases, this will be sufficient: often-times you will want, say, to have CDR monitoring enabled for all of your users.

Es kann aber auch vorkommen, dass Sie unterschiedliche Einstellungen auf verschiedene Websites anwenden möchten. Vielleicht möchten Sie beispielsweise die CDR-und QoE-Überwachung auf Ihrer Website in Redmond verwenden, aber nur die CDR-Überwachung in Ihrer Dublin-Website verwenden. Ebenso möchten Sie möglicherweise Überwachungsdaten für 60 Tage auf der Website "Redmond" beibehalten, müssen aber nur diese Art von Daten 30 Tage lang auf der Website von Dublin verwalten. Mit lync Server 2013 können Sie separate Sammlungen von CDR-und QoE-Konfigurationseinstellungen im Website Bereich erstellen. Damit können Sie jede Website unterschiedlich verwalten. (Dazu gehören sowohl das Aktivieren und Deaktivieren der Überwachung als auch das Konfigurieren von Verwaltungseinstellungen, wie beispielsweise die Aufbewahrungsdauer von Daten.)

Beachten Sie, dass Sie diese Entscheidung vor oder nach der Bereitstellung der Überwachung treffen können. Beispielsweise können Sie die Überwachung bereitstellen und anschließend die gesamte Organisation mithilfe der globalen Einstellungen verwalten. Falls Sie später Ihre Meinung ändern, können Sie eine separate Sammlung von Einstellungen z. B. für den Standort Redmond erstellen und dann die Überwachung für Redmond mithilfe dieser Einstellungen verwalten. (Einstellungen auf Standortebene haben stets Vorrang vor globalen Einstellungen.) Wenn Sie Ihre Meinung erneut ändern, können Sie einfach die Konfigurationseinstellungen löschen, die auf den Standort Redmond angewendet werden. Wenn eine Sammlung von Standorteinstellungen entfernt wird, wird die globale Sammlung von Einstellungen automatisch auf diesen Standort angewendet.

</div>

<span> </span>

</div>

</div>

</div>

