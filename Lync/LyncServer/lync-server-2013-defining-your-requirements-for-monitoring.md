---
title: 'Lync Server 2013: Definieren der Anforderungen für die Überwachung'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Defining your organizations's requirements for monitoring
ms:assetid: d587ff04-9af6-4ac1-ad42-076e7a40ac75
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205284(v=OCS.15)
ms:contentKeyID: 48185491
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6f116fec331c252934c42e624c36813218d8f9ca
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/16/2020
ms.locfileid: "48504322"
---
# <a name="defining-your-requirements-for-monitoring-in-lync-server-2013"></a>Definieren der Anforderungen für die Überwachung in lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2012-09-05_

Durch die Straffung der Bereitstellung und Installation der Überwachung in Microsoft lync Server 2013 wurden auch die Prozesse rationalisiert, die für die Definition der Anforderungen Ihrer Organisation an die Überwachung erforderlich sind. Dennoch sollten einige wichtige Probleme behoben werden, bevor Sie mit der Installation und Konfiguration von lync Server 2013 beginnen:

**Welche Art von Daten möchten Sie überwachen?** Mit lync Server 2013 können Sie zwei verschiedene Arten von Daten überwachen: KDS-Daten und Quality of Experience (QoE)-Daten (Call Detailing Recording). Die Aufzeichnung von Gesprächsdaten bietet Ihnen die Möglichkeit, die Verwendung von lync Server Funktionen wie VoIP-Telefon anrufen (Voice over IP) nachzuverfolgen. Instant Messaging (Sofortnachrichten); Dateiübertragungen; Audio/Video-Konferenzen (A/V); und Anwendungsfreigabesitzungen. Anhand dieser Informationen können Sie wissen, welche lync Server Features verwendet werden (und welche nicht), und Sie erhalten Informationen darüber, wann diese Features verwendet werden. Mit den Daten der Quality of Experience können Sie eine Aufzeichnung der Qualität von Audio-und Videoanrufen in Ihrer Organisation aufrecht erhalten, einschließlich der Anzahl der verlorenen Netzwerkpakete, des Hintergrundrauschens und der Menge an "Jitter" (Unterschiede bei der Paketverzögerung).

Wenn Sie die Überwachung in lync Server 2013 aktivieren, können Sie sowohl die KDS-Überwachung als auch die QoE-Überwachung aktivieren, oder Sie können auswählen, ob ein Überwachungstyp aktiviert werden soll, während der andere Typ deaktiviert bleibt. Nehmen Sie beispielsweise an, dass Ihre Benutzer nur Chatnachrichten und Dateiübertragungen verwenden und keine Audio-oder Videoanrufe tätigen. In diesem Fall gibt es möglicherweise wenig Grund, die QoE-Überwachung zu aktivieren. Ebenso erleichtert lync Server das Aktivieren und Deaktivieren der Überwachung, nachdem die Überwachung bereitgestellt wurde. Sie können beispielsweise die Überwachung bereitstellen, die QoE-Überwachung zunächst jedoch deaktiviert lassen. Wenn Ihre Benutzer Probleme mit Audio-oder Videoanrufen auftreten, können Sie die QoE-Überwachung aktivieren und diese Daten verwenden, um Sie bei der Behandlung und Lösung dieser Probleme zu unterstützen.

Es gibt keinen besonderen Vorteil (oder keinen Nachteil) für die Installation der Überwachung, gleichzeitig installieren Sie lync Server vs Installieren der Überwachung, nachdem lync Server installiert wurde. Beachten Sie, dass Sie vor der Installation der Überwachung einen Computer auswählen müssen, der den Back-End-Überwachungsspeicher hostet, und dass eine unterstützte Version von SQL Server auf diesem Computer installiert und konfiguriert werden muss, bevor dieser Computer für die Überwachung verwendet werden kann. Wenn Sie SQL Server bereits auf einem Computer installiert haben und dieser Computer für die Verwendung bereit ist, können Sie die Überwachung gleichzeitig installieren, wenn Sie lync Server installieren. Wenn Sie nicht über einen Back-End-Computer verfügen, können Sie mit der Installation von lync Server fortfahren und dann die Überwachung installieren, sobald der Back-End-Computerbetriebs fähig ist.

**Wann möchten Sie die Überwachung installieren?** Die Überwachung kann gleichzeitig installiert und konfiguriert werden, wenn Sie lync Server 2013 installieren und konfigurieren; der Assistent für die lync Server-Bereitstellung bietet Ihnen die Möglichkeit, während des Setups Ihre Front-End-Pools einer Überwachungsdatenbank zuzuordnen. Alternativ können Sie die Überwachung installieren, nachdem lync Server selbst installiert wurde; Hierzu können Sie mithilfe des Topologie-Generators Ihre Front-End-Pools und Server einer Überwachungsdatenbank zuordnen und dann die überarbeitete Topologie veröffentlichen.

**Wie viele Back-End-Überwachungsdatenbanken benötigen Sie?** Eine einzelne Überwachungsdatenbank kann Zehntausende von Benutzern unterstützen (für Microsoft lync Server 2010 wurde geschätzt, dass eine zusammengefasste Datenbank sowohl für die Überwachung als auch für die Archivierung 240.000-Benutzer unterstützen könnte). Darüber hinaus kann eine einzelne Überwachungsdatenbank von mehreren Front-End-Pools verwendet werden. Wenn Sie drei Front-End-Pools in Ihrer Organisation haben, können Sie alle drei Pools mit dem gleichen Back-End-Speicher verknüpfen.

Dies bedeutet lediglich, dass für viele Organisationen die Datenbankkapazität nicht der entscheidende Faktor beim Ermitteln der Anzahl benötigter Back-End-Überwachungsdatenbanken ist. Vielmehr könnte die Netzwerkgeschwindigkeit ein wichtigerer Faktor sein. Angenommen, es sind drei Front-End-Pools vorhanden, aber einer dieser Pools wird über eine langsame Netzwerkverbindung verwendet. In diesem Fall sollten Sie zwei Überwachungsdatenbanken verwenden: eine Datenbank für die beiden Pools mit der schnellen Netzwerkverbindung, und eine separate Datenbank für den Pool mit der langsameren Netzwerkverbindung.

Bei der Planung Ihrer Überwachungsinfrastruktur sollten Sie auch berücksichtigen, dass lync Server 2013 die Verwendung von Spiegeldatenbanken unterstützt. Die "Datenbankspiegelung" bietet die Möglichkeit, zwei Kopien einer Datenbank gleichzeitig zu verwalten, wobei die Datenbanken auf unterschiedlichen Servern gespeichert werden. Immer wenn Daten in eine primäre Datenbank geschrieben werden, werden diese Daten auch in die Spiegeldatenbank geschrieben. Wenn die primäre Datenbank fehlschlagen oder anderweitig nicht verfügbar sein soll, können Sie mit einem einfachen lync Server PowerShell-Befehl einen Failover für die Spiegeldatenbank durchführen. Beispiel:

    Invoke-CsDatabaseFailover -PoolFqdn atl-cs-001.litwareinc.com -DatabaseType "Monitoring" -NewPrincipal "Mirror"

Dies spielt eine wichtige Rolle für die Planung, da Sie für die Spiegelung die erforderliche Anzahl von Datenbanken verdoppeln müssen. Denn zusätzlich zu jeder primären Datenbank benötigen Sie eine zweite Datenbank als Spiegeldatenbank.

**Benötigen Ihre lync Server Websites eigene benutzerdefinierte Überwachungskonfigurationen?** Wenn Sie lync Server 2013 installieren, installieren Sie auch globale Auflistungen von KDS-und QoE-Konfigurationseinstellungen; Diese globalen Auflistungen bieten Ihnen die Möglichkeit, dieselben KDS-und QoE-Einstellungen auf Ihre gesamte Organisation anzuwenden. In vielen Fällen ist dies ausreichend, denn oft möchten Sie z. B. die KDS-Überwachung für alle Ihre Benutzer aktivieren.

Es kann jedoch auch vorkommen, dass Sie unterschiedliche Einstellungen auf unterschiedliche Websites anwenden möchten. Beispielsweise möchten Sie vielleicht sowohl die KDS-als auch die QoE-Überwachung in Ihrem Standort in Redmond verwenden, aber nur die KDS-Überwachung in Ihrem Standort in Dublin verwenden. Ebenso möchten Sie möglicherweise Überwachungsdaten für 60 Tage am Standort "Redmond" aufbewahren, müssen diesen Datentyp jedoch nur 30 Tage lang am Standort Dublin verwalten. Lync Server 2013 ermöglicht Ihnen das Erstellen separater Auflistungen von KDS-und QoE-Konfigurationseinstellungen auf Standortebene; auf diese Weise können Sie jede Website unterschiedlich verwalten. (Dies umfasst sowohl das Aktivieren als auch das Deaktivieren der Überwachung sowie das Konfigurieren von Verwaltungseinstellungen, beispielsweise wie lange Daten aufbewahrt werden sollen.)

Beachten Sie, dass Sie diese Entscheidung vor oder nach der Bereitstellung der Überwachung treffen können. Beispielsweise können Sie die Überwachung bereitstellen und anschließend die gesamte Organisation mithilfe der globalen Einstellungen verwalten. Falls Sie später Ihre Meinung ändern, können Sie eine separate Sammlung von Einstellungen z. B. für den Standort Redmond erstellen und dann die Überwachung für Redmond mithilfe dieser Einstellungen verwalten. (Einstellungen auf Standortebene haben stets Vorrang vor globalen Einstellungen.) Wenn Sie Ihre Meinung erneut ändern, können Sie einfach die Konfigurationseinstellungen löschen, die auf den Standort Redmond angewendet werden. Wenn eine Sammlung von Standorteinstellungen entfernt wird, wird die globale Sammlung von Einstellungen automatisch auf diesen Standort angewendet.

</div>

<span> </span>

</div>

</div>

</div>

