---
title: Planen der Überwachung in Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 5d5eb658-7fe0-42e6-acaf-700051d0a823
description: 'Zusammenfassung: Lesen Sie dieses Thema bei der Planung des Überwachungsdiensts in Skype for Business Server.'
ms.openlocfilehash: 0fce6f3a47c7b1b76bfb12dcfca8b3bb222f8c80
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51116043"
---
# <a name="plan-for-monitoring-in-skype-for-business-server"></a>Planen der Überwachung in Skype for Business Server

**Zusammenfassung:** Lesen Sie dieses Thema, während Sie den Überwachungsdienst in Skype for Business Server planen.

Der Überwachungsdienst in Skype for Business Server bietet Administratoren die Möglichkeit, Nutzungs- und Qualitätsdaten für die Kommunikationssitzungen in ihrer Organisation zu sammeln, wodurch sie Trends und Probleme identifizieren können. Mit der fortlaufenden Überwachung Ihrer Bereitstellung können Sie Probleme frühzeitig abfangen und die Benutzer Ihrer Organisation zufrieden stellen.

Für die Überwachung in Skype for Business Server ist keine separate Serverrolle erforderlich (wie in früheren Lync-Versionen). Stattdessen ist der Überwachungsdienst in jeden Front-End-Server integrierte. Die Überwachung ist in Skype for Business Server standardmäßig nicht aktiviert. Dieser Artikel hilft Ihnen zu bestimmen, ob die Überwachung während oder nach ihrer anfänglichen Skype for Business Server-Konfiguration aktiviert werden soll und welche SQL Ressourcen Sie benötigen, um Überwachungsaktivitäten zu unterstützen. Wenn Sie nicht sicher sind, was genau überwacht wird oder was nicht, und wie die Überwachung hilfreich sein kann, wechseln Sie zu [Grundlagen zur Überwachung](monitoring.md#Basics). Um mit dem Planungsprozess zu beginnen, wechseln Sie zu [Definieren Ihrer Anforderungen für die Überwachung](monitoring.md#requirements). Weitere Informationen zu den SQL für die Überwachung finden Sie [unter SQL Anforderungen für die Überwachung](monitoring.md#topologies).

## <a name="basics-about-monitoring"></a>Grundlagen zur Überwachung
<a name="Basics"> </a>

Eine Sitzung ist ein allgemeiner Begriff für die Verbindung eines Benutzers zu einem:

- Konferenz

- Konferenztool wie Audio/Video oder Anwendungsfreigabe

- Andere Benutzer über eine Peer-zu-Peer-Unterhaltung wie Sofortnachrichten oder Audioanruf

> [!NOTE]
> Skype for Business Server verfolgt Informationen zu jeder Sitzung: wer angerufen hat; welche Endpunkte in der Sitzung verwendet wurden; Wie lange hat die Sitzung zuletzt ge dauert; was die wahrgenommene Qualität der Sitzung war; Und so weiter. Skype for Business Server erfasst und gespeichert den tatsächlichen Anruf selbst nicht. Dies schließt Chatsitzungen ein: Obwohl Skype for Business Server Informationen zu Chatsitzungen erfasst, wird nicht jede Während der Sitzung gesendete Sofortnachricht aufgezeichnet.

Die grundlegenden Anrufdetails, die von Skype for Business Server für jede Sitzung gesammelt werden, können für:

- **Return on Investment (ROI)-Analyse.** Administratoren können die Verwendungsdaten mit ähnlichen Daten vergleichen, die für ihr vorheriges Telefoniesystem gesammelt wurden, um Kosteneinsparungen zu erzielen und die Bereitstellung von Skype for Business Server zu rechtfertigen.

- **Geräteinventarverwaltung**. Informationen zur Ressourcenverwaltung helfen Administratoren dabei, alte Geräte zu identifizieren, die noch verwendet werden müssen, die ersetzt werden müssen, und teure Geräte zu identifizieren, die nicht verwendet oder nicht verwendet werden.

- **Helpdesk**. Bei der Problembehandlung von Daten können Techniker ermitteln, warum der Anruf eines Benutzers fehlgeschlagen ist, ohne server- oder clientseitige Protokolle sammeln zu müssen. Auf diese Informationen kann sofort zugegriffen und von Supportmitarbeitern verstanden werden, die über keine tiefen technischen Kenntnisse des Skype for Business-Clients und skype for Business Server verfügen.

- **Systemproblembehandlung**. Ermöglicht Administratoren das Erkennen grundlegender Probleme, die u. U. verhindern, dass Endbenutzer einfache Aufgaben wie das Beitreten zu einer Konferenz, das Tätigen eines Anrufs oder das Senden einer Sofortnachricht ausführen können.

Die Überwachung bietet außerdem einen Mechanismus, mit dem SIP-Endpunkte (z. B. Skype for Business) Problembehandlungsinformationen bereitstellen können, auf die der Administrator andernfalls keinen Zugriff hätte:

- **Medienmetriken, die sich auf die Qualität auswirken.** Diese Metriken befassen sich mit der tatsächlichen Übertragung des Anrufs selbst. Sie bieten eine Art Reisebericht, während die Anrufe über das Netzwerk gehen. Diese Metriken (z. B. Paketverlust, Jitter und Roundtripzeiten) enthalten Informationen dazu, was mit dem Anruf passiert ist, wenn der Endpunkt einer Person bis zum Zeitpunkt des Eintreffens am Endpunkt der anderen Person verlassen wurde.

- **Dem Endbenutzer gemeldete Probleme.** Diese Metriken umfassen Benachrichtigungen schlechter Qualität, die Skype for Business Endbenutzern in Fällen präsentiert, in denen sie zu weit von einem Mikrofon entfernt sind, zu weich sprechen, eine schlechte Netzwerkverbindung haben oder eine schlechte Qualität haben, da ein anderes Programm auf dem Computer die verfügbaren Ressourcen verbraucht.

- **Umgebungsinformationen**. Diese Metriken erfassen detaillierte Faktoren der Anrufqualität wie den Typ des verwendeten Mikrofons und Lautsprechers, Angaben darüber, ob eine VPN-Verbindung verwendet wurde und Angaben darüber, ob eine WLAN-Verbindung verwendet wurde.

Am Ende jedes Anrufs übertragen SIP-kompatible Endpunkte diese Informationen an den Front-End-Server, der den Anruf erleichtert hat. Sie müssen nichts tun, um Endpunkte zum Übertragen dieser Informationen zu erhalten. dieses Verhalten ist in das SIP-Protokoll integrierte. Wenn Sie diese Informationen jedoch sammeln und speichern möchten, müssen Sie die Überwachung installieren und aktivieren. Wenn Sie die Überwachung installieren und aktivieren, werden Anrufinformationen von Agents gesammelt, die auf dem Front-End-Server ausgeführt werden und an ein Paar von SQL Server werden. Der Überwachungsdienst (in Form von "Unified Data Collection Agents") ist mit allen Front-End-Servern zusammengeknallt.

## <a name="define-your-requirements-for-monitoring"></a>Definieren Der Anforderungen für die Überwachung
<a name="requirements"> </a>

Es gibt noch einige wichtige Probleme, die behoben werden müssen, bevor Sie mit der Installation und Konfiguration der Überwachung mit Skype for Business Server beginnen:

 **Wann möchten Sie die Überwachung installieren?** Die Überwachung kann gleichzeitig installiert und konfiguriert werden, wenn Sie Skype for Business Server installieren und konfigurieren. Der Skype for Business Server-Bereitstellungs-Assistent bietet Ihnen die Möglichkeit, Ihre Front-End-Pools während des Setups einer Überwachungsdatenbank zuzuordnen. Alternativ können Sie die Überwachung installieren, nachdem Skype for Business Server selbst installiert wurde. Dazu können Sie den Topologie-Generator verwenden, um Ihre Front-End-Pools und -Server einer Überwachungsdatenbank zuzuordnen und anschließend die überarbeitete Topologie zu veröffentlichen.

Beachten Sie, dass SQL Server installiert und konfiguriert werden muss, bevor Sie die Überwachung bereitstellen und konfigurieren. Sie müssen jedoch nur die SQL Server bereitstellen. Die Überwachungsdatenbanken werden für Sie erstellt, wenn Sie Ihre Skype for Business Server-Topologie veröffentlichen.

 **Welche Art von Daten möchten Sie überwachen?** Mit Skype for Business Server können Sie zwei allgemeine Arten von Daten überwachen: Daten zur Aufzeichnung von Anrufdetails (CdR) und QoE-Daten (Quality of Experience). Die Aufzeichnung von Anrufdetails bietet Ihnen die Möglichkeit, die Verwendung von Skype for Business #A0 wie Voice over IP (VoIP)-Telefonanrufen nachverfolgt zu können. Instant Messaging (Instant Messaging); Dateiübertragungen; audio/video (A/V) conferencing; und Anwendungsfreigabesitzungen. Diese Informationen helfen Ihnen zu wissen, welche Skype for Business Server-Features verwendet werden (und welche nicht) und enthalten außerdem Informationen dazu, wann diese Features verwendet werden. Mit Den Daten zur Benutzerqualität können Sie die Qualität von Audio- und Videoanrufen in Ihrer Organisation aufzeichnen, z. B. die Anzahl der verloren gegangenen Netzwerkpakete, Hintergrundgeräusche und die Menge an "Jitter" (Unterschiede bei der Paketverzögerung).

Wenn Sie die Überwachung in Skype for Business Server aktivieren möchten, können Sie sowohl die CDR-Überwachung als auch die QoE-Überwachung aktivieren, oder Sie können einen Überwachungstyp aktivieren, während der andere Typ deaktiviert ist. Angenommen, Ihre Benutzer verwenden nur Chatnachrichten und Dateiübertragungen und tätigen keine Audio- oder Videoanrufe. In diesem Fall gibt es möglicherweise wenig Grund, die QoE-Überwachung zu aktivieren. Ebenso erleichtert Skype for Business Server das Aktivieren und Deaktivieren der Überwachung nach der Bereitstellung der Überwachung. Beispielsweise können Sie die Überwachung bereitstellen, die QoE-Überwachung jedoch zunächst deaktiviert lassen. Wenn bei Ihren Benutzern Probleme mit Audio- oder Videoanrufen auftreten, können Sie die QoE-Überwachung aktivieren und diese Daten verwenden, um Sie bei der Problembehandlung und Lösung dieser Probleme zu unterstützen.

Es gibt keinen besonderen Vorteil (oder Nachteil) für die Installation der Überwachung gleichzeitig, wenn Sie Skype for Business Server installieren, im Vergleich zur Installation der Überwachung nach der Installation von Skype for Business Server. Beachten Sie, dass Sie vor der Installation der Überwachung einen Computer zum Hosten des Back-End-Überwachungsspeichers auswählen müssen, und eine unterstützte Version von SQL Server muss auf diesem Computer installiert und konfiguriert werden, bevor dieser Computer für die Überwachung verwendet werden kann. Wenn Sie bereits SQL Server auf einem Computer installiert haben und dieser Computer einsatzbereit ist, können Sie die Überwachung gleichzeitig installieren, wenn Sie Skype for Business Server installieren. Wenn Sie keinen Back-End-Computer bereit haben, können Sie mit der Installation von Skype for Business Server allein fortfahren und die Überwachung dann installieren, wenn der Back-End-Computer einsatzbereit ist.

 **Wie viele Back-End-Überwachungsdatenbanken benötigen Sie?** Es wurde geschätzt, dass eine zusammengeknappte Datenbank für Überwachung und Archivierung 240.000 Skype for Business Server-Benutzer unterstützen kann). Darüber hinaus kann eine einzelne Überwachungsdatenbank von mehreren Front-End-Pools verwendet werden. Wenn Sie drei Front-End-Pools in Ihrer Organisation haben, können Sie alle drei Pools demselben Back-End-Speicher zuordnen.

Für viele Organisationen ist datenbankkapazität nicht der entscheidende Faktor bei der Bestimmung der Anzahl der erforderlichen Back-End-Überwachungsdatenbanken. Vielmehr könnte die Netzwerkgeschwindigkeit ein wichtigerer Faktor sein. Angenommen, es sind drei Front-End-Pools vorhanden, aber einer dieser Pools wird über eine langsame Netzwerkverbindung verwendet. In diesem Fall sollten Sie zwei Überwachungsdatenbanken verwenden: eine Datenbank für die beiden Pools mit der schnellen Netzwerkverbindung, und eine separate Datenbank für den Pool mit der langsameren Netzwerkverbindung.

Sie sollten auch berücksichtigen, dass Skype for Business Server die Verwendung von Spiegeldatenbanken unterstützt. Die "Datenbankspiegelung" bietet die Möglichkeit, zwei Kopien einer Datenbank gleichzeitig zu verwalten, wobei die Datenbanken auf unterschiedlichen Servern gespeichert werden. Immer wenn Daten in eine primäre Datenbank geschrieben werden, werden diese Daten auch in die Spiegeldatenbank geschrieben. Wenn die primäre Datenbank fehlschlagen oder anderweitig nicht verfügbar sein sollte, können Sie mit einem einfachen Skype for Business Server PowerShell-Befehl ein Failover zur Spiegeldatenbank ausführen. Beispiel:

```PowerShell
Invoke-CsDatabaseFailover -PoolFqdn atl-cs-001.litwareinc.com -DatabaseType "Monitoring" -NewPrincipal "Mirror"
```

Dies spielt eine wichtige Rolle für die Planung, da Sie für die Spiegelung die erforderliche Anzahl von Datenbanken verdoppeln müssen. Denn zusätzlich zu jeder primären Datenbank benötigen Sie eine zweite Datenbank als Spiegeldatenbank.

 **Benötigen Ihre Skype for Business Server-Websites eigene benutzerdefinierte Überwachungskonfigurationen?** Wenn Sie Skype for Business Server installieren, installieren Sie auch globale Sammlungen von CDR- und QoE-Konfigurationseinstellungen. Diese globalen Auflistungen bieten Ihnen die Möglichkeit, die gleichen CDR- und QoE-Einstellungen auf Ihre gesamte Organisation anzuwenden. In vielen Fällen ist dies ausreichend, denn oft möchten Sie z. B. die KDS-Überwachung für alle Ihre Benutzer aktivieren.

Es kann jedoch auch mal sein, dass Sie unterschiedliche Einstellungen auf verschiedene Websites anwenden möchten. Vielleicht möchten Sie beispielsweise sowohl die CDR- als auch die QoE-Überwachung an Ihrem Standort in Redmond verwenden, aber nur die CDR-Überwachung an Ihrem Standort in Dublin verwenden. Ebenso können Sie Überwachungsdaten für 60 Tage am Standort "Redmond" beibehalten, müssen diese Art von Daten jedoch nur für 30 Tage am Standort Dublin beibehalten. Mit Skype for Business Server können Sie separate Sammlungen von Konfigurationseinstellungen für CDR und QoE auf Standortseite erstellen. ermöglicht es Ihnen, jede Website unterschiedlich zu verwalten. (Dies umfasst sowohl das Aktivieren und Deaktivieren der Überwachung als auch das Konfigurieren von Verwaltungseinstellungen, z. B. wie lange Daten aufbewahrt werden sollen.)

Beachten Sie, dass Sie diese Entscheidung vor oder nach der Bereitstellung der Überwachung treffen können. Beispielsweise können Sie die Überwachung bereitstellen und anschließend die gesamte Organisation mithilfe der globalen Einstellungen verwalten. Falls Sie später Ihre Meinung ändern, können Sie eine separate Sammlung von Einstellungen z. B. für den Standort Redmond erstellen und dann die Überwachung für Redmond mithilfe dieser Einstellungen verwalten. (Einstellungen auf Standortebene haben stets Vorrang vor globalen Einstellungen.) Wenn Sie Ihre Meinung erneut ändern, können Sie einfach die Konfigurationseinstellungen löschen, die auf den Standort Redmond angewendet werden. Wenn eine Sammlung von Standorteinstellungen entfernt wird, wird die globale Sammlung von Einstellungen automatisch auf diesen Standort angewendet.

## <a name="sql-requirements-for-monitoring"></a>SQL Anforderungen für die Überwachung
<a name="topologies"> </a>

Die einheitlichen Datensammlungs-Agents werden automatisch auf jedem Front-End-Server installiert und aktiviert, wenn Sie die Überwachung aktivieren. Unterstützte Versionen von SQL Server und weitere Details finden Sie unter [Server requirements for Skype for Business Server 2015](requirements-for-your-environment/server-requirements.md)

Überwachungsdaten können eine SQL Server anderen Datentypen gemeinsam verwenden. In der Regel teilen sich die Datenbank für die Aufzeichnung von Anrufdetails (LcsCdr) und die Quality of Experience-Datenbank (QoEMetrics) dieselbe SQL Instanz. Es ist auch üblich, dass sich die beiden Überwachungsdatenbanken in der SQL der Archivierungsdatenbank (LcsLog) befinden. Die einzige tatsächliche Anforderung bei SQL Server instanzen ist, dass jede instanz von SQL Server auf Folgendes beschränkt ist:

- Eine Instanz der Skype for Business Server 2015-Back-End-Datenbank. (In der Regel wird nicht empfohlen, dass die Überwachungsdatenbank in derselben SQL-Instanz oder sogar auf demselben Computer wie die Back-End-Datenbank zusammengeknallt wird. Obwohl technisch möglich, besteht das Risiko, dass die Überwachungsdatenbank den von der Back-End-Datenbank benötigten Speicherplatz verwendet.)

- Eine Instanz der Aufzeichnungsdatenbank für Anrufdetails.

- Eine Instanz der Quality of Experience-Datenbank.

- Eine Instanz der Archivierungsdatenbank.

Anders ausgedrückt: Sie können nicht zwei Instanzen der LcsCdr-Datenbank in derselben Instanz der SQL Server. Wenn Sie mehrere Instanzen der LcsCdr-Datenbank benötigen, müssen Sie mehrere Instanzen von SQL Server.

## <a name="see-also"></a>Siehe auch


[Bereitstellen des Monitoring Servers](/previous-versions/office/lync-server-2013/lync-server-2013-deploying-monitoring)