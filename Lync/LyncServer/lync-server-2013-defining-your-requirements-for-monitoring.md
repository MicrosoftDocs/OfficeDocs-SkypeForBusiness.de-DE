---
title: 'Lync Server 2013: Definieren der Anforderungen Ihrer Organisation für die Überwachung'
TOCTitle: Definieren der Anforderungen Ihrer Organisation für die Überwachung
ms:assetid: d587ff04-9af6-4ac1-ad42-076e7a40ac75
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ205284(v=OCS.15)
ms:contentKeyID: 49890964
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Definieren der Anforderungen Ihrer Organisation für die Überwachung in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2012-09-05_

Durch das Optimieren der Bereitstellung und Installation der Überwachung in Microsoft Lync Server 2013 wurden auch die Prozesse im Zusammenhang mit dem Definieren der Überwachungsanforderungen Ihrer Organisation optimiert. Dennoch gibt es noch einige wichtige Punkte, um die Sie sich kümmern sollten, bevor Sie mit dem Installieren und Konfigurieren von Lync Server 2013 beginnen können:

**Welche Datentypen möchten Sie überwachen?** Lync Server 2013 ermöglicht die Überwachung von zwei unterschiedlichen Datentypen: Daten zur Aufzeichnung von Kommunikationsdatensätzen (KDS) und Quality of Experience (QoE)-Daten. Die KDS-Funktion bietet eine Möglichkeit, die Nutzung von Lync Server-Features wie VoIP-Anrufe (Voice over Internet Protocol), Chat, Dateiübertragungen, Audio-/Videokonferenzen (A/V) und Anwendungsfreigabesitzungen nachzuverfolgen. Anhand dieser Informationen wissen Sie, welche Lync Server-Features verwendet werden (bzw. nicht verwendet werden) sowie wann diese Features verwendet werden. Mithilfe von Quality of Experience (QoE)-Daten können Sie die Qualität der in Ihrer Organisation getätigten Audio- und Videoanrufe erfassen, z. B. die Anzahl der verloren gegangenen Netzwerkpakete, Hintergrundgeräusche und die Unterschiede bei Paketverzögerung (Jitter).

Wenn Sie die Überwachung in Lync Server 2013 aktivieren, können Sie sowohl die KDS- als auch die QoE-Überwachung aktivieren. Sie können aber auch nur einen Überwachungstyp aktivieren und den anderen Überwachungstyp deaktiviert lassen. Angenommen, Ihre Benutzer verwenden nur Chat und Dateiübertragungen und tätigen keine Audio- oder Videoanrufe. In diesem Fall gibt es kaum einen Grund, die QoE-Überwachung zu aktivieren. Entsprechend kann die Überwachung in Lync Server nach der Bereitstellung auf einfache Weise aktiviert und deaktiviert werden. Beispielsweise könnten Sie die Überwachung bereitstellen, aber zunächst die QoE-Überwachung deaktiviert lassen. Wenn die Benutzer Probleme mit Audio- oder Videoanrufen haben, könnten Sie die QoE-Überwachung aktivieren und mithilfe der Überwachungsdaten diese Probleme behandeln und beheben.

Die gleichzeitige Installation der Überwachung zusammen mit Lync Server bietet keine speziellen Vorteile (oder Nachteile) im Vergleich zur Installation der Überwachung nach Lync Server. Sie sollten jedoch berücksichtigen, dass Sie vor der Installation der Überwachung einen Computer zum Hosten des Back-End-Überwachungsspeichers auswählen müssen. Außerdem muss eine unterstützte Version von SQL Server auf diesem Computer installiert und konfiguriert werden, bevor dieser Computer für die Überwachung verwendet werden kann. Falls Sie SQL Server bereits auf einem Computer installiert haben, der einsatzbereit ist, können Sie die Überwachung zusammen mit Lync Server installieren. Falls kein Back-End-Computer bereit ist, können Sie Lync Server separat installieren und später die Überwachung installieren, wenn der Back-End-Computer einsatzbereit ist.

**Wann möchten Sie die Überwachung installieren?** Die Überwachung kann gleichzeitig mit Lync Server 2013 installiert und konfiguriert werden. Der Lync Server-Bereitstellungs-Assistent bietet Ihnen die Möglichkeit, Ihren Front-End-Pools während des Setups eine Überwachungsdatenbank zuzuordnen. Alternativ können Sie die Überwachung nach der Installation von Lync Server separat installieren. Hierfür können Sie mit dem Topologie-Generator Ihren Front-End-Pools und -Servern eine Überwachungsdatenbank zuordnen und anschließend die geänderte Topologie veröffentlichen.

**Wie viele Back-End-Überwachungsdatenbanken benötigen Sie?** Mit einer einzelnen Überwachungsdatenbank werden Zehntausende von Benutzern unterstützt (für Microsoft Lync Server 2010 wurde davon ausgegangen, dass mit einer verbundenen Datenbank für die Überwachung und die Archivierung 240.000 Benutzer unterstützt werden). Darüber hinaus kann eine einzelne Überwachungsdatenbank von mehreren Front-End-Pools verwendet werden. Wenn in Ihrer Organisation drei Front-End-Pools vorhanden sind, könnten Sie allen drei Pools denselben Back-End-Speicher zuordnen.

Dies bedeutet lediglich, dass für viele Organisationen die Datenbankkapazität nicht der entscheidende Faktor beim Ermitteln der Anzahl benötigter Back-End-Überwachungsdatenbanken ist. Vielmehr könnte die Netzwerkgeschwindigkeit ein wichtigerer Faktor sein. Angenommen, es sind drei Front-End-Pools vorhanden, aber einer dieser Pools wird über eine langsame Netzwerkverbindung verwendet. In diesem Fall sollten Sie zwei Überwachungsdatenbanken verwenden: eine Datenbank für die beiden Pools mit der schnellen Netzwerkverbindung, und eine separate Datenbank für den Pool mit der langsameren Netzwerkverbindung.

Bei der Planung Ihrer Überwachungsinfrastruktur sollten Sie auch berücksichtigen, dass Lync Server 2013 die Verwendung der Spiegeldatenbanken unterstützt. Die "Datenbankspiegelung" bietet die Möglichkeit, zwei Kopien einer Datenbank gleichzeitig zu verwalten, wobei die Datenbanken auf unterschiedlichen Servern gespeichert werden. Immer wenn Daten in eine primäre Datenbank geschrieben werden, werden diese Daten auch in die Spiegeldatenbank geschrieben. Falls die primäre Datenbank ausfällt oder anderweitig nicht mehr verfügbar ist, können Sie mit einem einfachen Lync Server PowerShell-Befehl ein Failover auf die Spiegeldatenbank ausführen. Beispiel:

    Invoke-CsDatabaseFailover -PoolFqdn atl-cs-001.litwareinc.com -DatabaseType "Monitoring" -NewPrincipal "Mirror"

Dies spielt eine wichtige Rolle für die Planung, da Sie für die Spiegelung die erforderliche Anzahl von Datenbanken verdoppeln müssen. Denn zusätzlich zu jeder primären Datenbank benötigen Sie eine zweite Datenbank als Spiegeldatenbank.

**Benötigen Ihre Lync Server-Standorte eigene benutzerdefinierte Überwachungskonfigurationen?** Bei der Installation von Lync Server 2013 installieren Sie auch globale Sammlungen von KDS- und QoE-Konfigurationseinstellungen, mit denen Sie dieselben KDS- und QoE-Einstellungen in der gesamten Organisation verwenden können. In vielen Fällen ist dies ausreichend, denn oft möchten Sie z. B. die KDS-Überwachung für alle Ihre Benutzer aktivieren.

Es kann jedoch vorkommen, dass Sie für unterschiedliche Standorte verschiedene Einstellungen verwenden möchten. Möglicherweise möchten Sie z. B. sowohl die KDS- als auch die QoE-Überwachung an Ihrem Standort in Redmond verwenden, aber nur die KDS-Überwachung an Ihrem Standort in Dublin. Entsprechend möchten Sie Überwachungsdaten an Ihrem Standort in Redmond 60 Tage lang aufbewahren, am Standort in Dublin aber nur 30 Tage lang. Lync Server 2013 ermöglicht das Erstellen separater Sammlungen von KDS- und QoE-Konfigurationseinstellungen auf Standortebene. Auf diese Weise können Sie jeden Standort unterschiedlich verwalten. (Dies beinhaltet das Aktivieren und Deaktivieren der Überwachung sowie das Konfigurieren von Verwaltungseinstellungen wie z. B. die Aufbewahrungsdauer für Daten.)

Beachten Sie, dass Sie diese Entscheidung vor oder nach der Bereitstellung der Überwachung treffen können. Beispielsweise können Sie die Überwachung bereitstellen und anschließend die gesamte Organisation mithilfe der globalen Einstellungen verwalten. Falls Sie später Ihre Meinung ändern, können Sie eine separate Sammlung von Einstellungen z. B. für den Standort Redmond erstellen und dann die Überwachung für Redmond mithilfe dieser Einstellungen verwalten. (Einstellungen auf Standortebene haben stets Vorrang vor globalen Einstellungen.) Wenn Sie Ihre Meinung erneut ändern, können Sie einfach die Konfigurationseinstellungen löschen, die auf den Standort Redmond angewendet werden. Wenn eine Sammlung von Standorteinstellungen entfernt wird, wird die globale Sammlung von Einstellungen automatisch auf diesen Standort angewendet.

