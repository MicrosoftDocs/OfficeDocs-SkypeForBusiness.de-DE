---
title: Übersicht über Best Practices Analyzer
TOCTitle: Übersicht über Best Practices Analyzer
ms:assetid: c5fcaa05-eb1c-4092-90ad-177b127e795b
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg591349(v=OCS.15)
ms:contentKeyID: 49295354
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Übersicht über Best Practices Analyzer

 

_**Letztes Änderungsdatum des Themas:** 2012-09-19_

Mit dem Best Practices Analyzer von Lync Server 2013 können Sie Probleme im Zusammenhang mit Ihrer Lync Server 2013-Bereitstellung erkennen und beheben. Der Best Practices Analyzer von Lync Server 2013 sammelt Konfigurationsinformationen von Lync Server 2013-Komponenten.

Mit entsprechendem Netzwerkzugriff kann der Best Practices Analyzer Server Active Directory-Domänendienste, Exchange Server Unified Messaging (UM) und Lync Server 2013 überprüfen. Der Best Practices Analyzer kann für folgende Aufgaben verwendet werden:

  - Ausführen proaktiver Überprüfungen, ob die Konfiguration entsprechend der empfohlenen bewährten Methoden eingerichtet ist.

  - Automatisches Erkennen erforderlicher Updates für Lync Server 2013.

  - Generieren einer Liste von Problemen, wie z. B. nicht optimale Konfigurationseinstellungen, nicht unterstützte Optionen, fehlende Updates oder nicht empfohlene Praktiken.

  - Unterstützen der Behandlung und Korrektur bestimmter Probleme.

Der Best Practices Analyzer bietet folgende Features:

  - Minimale Installationsvoraussetzungen.

  - Onlinedokumentation zu gemeldeten Problemen, einschließlich Tipps zur Problembehandlung.

  - Konfigurationsinformationen, die Sie für die spätere Verwendung speichern können.

  - Hervorragende Systemanalyse.

Der Best Practices Analyzer bestimmt mithilfe von XML-Konfigurationsdateien, welche Informationen in Ihrer Lync Server 2013-Umgebung erfasst werden sollen. Neben den Active Directory-Domänendiensten werden auch Informationsquellen wie z. B. die Registrierung des Windows Server-Betriebssystems und Einstellungen in der Windows-Verwaltungsinstrumentation (Windows Management Instrumentation, WMI) überprüft.

Der Best Practices Analyzer vergleicht die gesammelten Daten mit einer Reihe vordefinierter Regeln für die Einstellungen und Konfigurationen von Lync Server 2013-Bereitstellungen.

Nach dem Vergleich der gesammelten Daten mit den vordefinierten Regeln meldet das Tool etwaige Probleme. Für jedes gemeldete Problem liefert der Best Practices Analyzer Informationen zum gefundenen Problem in der überprüften Lync Server 2013-Umgebung sowie die empfohlene Konfiguration. Darüber hinaus enthält der Best Practices Analyzer Links zu ausführlicheren Informationen zu den jeweiligen Problemen.


> [!NOTE]
> Der Best Practices Analyzer von Lync Server 2013 sammelt nur für Lync Server 2013-Komponenten Konfigurationsinformationen. Mit den vorherigen Versionen dieses Tool können Sie frühere Umgebungen überprüfen. Ausführliche Informationen finden Sie unter <A href="lync-server-2013-requirements-for-running-best-practices-analyzer.md">Anforderungen für das Ausführen von Best Practices Analyzer</A>.


