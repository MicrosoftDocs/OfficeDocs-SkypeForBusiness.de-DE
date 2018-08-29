---
title: Planen der Überwachung in Skype für Business Server
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 5d5eb658-7fe0-42e6-acaf-700051d0a823
description: 'Zusammenfassung: Lesen Sie diesen Abschnitt beim Planen des Überwachungsdienst in Skype für Business Server.'
ms.openlocfilehash: ab2b96063d94471ce47564845c64a63dfc5710c8
ms.sourcegitcommit: 08c6fe9955ea61dd9cded2210ae0153e06bdd8a6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/28/2018
ms.locfileid: "23243347"
---
# <a name="plan-for-monitoring-in-skype-for-business-server"></a>Planen der Überwachung in Skype für Business Server

**Zusammenfassung:** Überprüfen Sie beim Planen des Überwachungsdienst in Skype für Business Server in diesem Thema.

Der Überwachungsdienst in Skype für Business Server bietet die Möglichkeit für Administratoren, Verwendung und QoE-Daten für die kommunikationssitzungen zu erfassen, die in ihrer Organisation, d. h., sie stattfinden um Trends und Probleme zu identifizieren. Fortlaufende Überwachung Ihrer Bereitstellung können Sie Probleme früh catch und stellen den Benutzern Ihrer Organisation erfüllt.

Überwachung in Skype für Business Server einen separaten Server-Role nicht erforderlich ist (wie in früheren Versionen von Lync der Fall war); Stattdessen wird der Überwachungsdienst in jedem Front-End-Server integriert. Überwachung wird standardmäßig in Skype für Business Server nicht aktiviert. Dieser Artikel hilft Ihnen bei der Bestimmung, ob die Überwachung während oder nach Ihrer anfänglichen Skype für Business Server-Konfiguration aktiviert, und welche SQL-Ressourcen, die Sie benötigen unterstützt Überwachung Aktivitäten. Wenn Sie nicht sicher sind genau, was ist oder wird nicht überwacht und wie monitoring hilfreich sein kann, wechseln Sie zur [Grundlagen zu überwachen](monitoring.md#Basics). Um Ihre Planung beginnen, wechseln Sie zum [Definieren der Anforderungen für die Überwachung](monitoring.md#requirements). Weitere Informationen zu den SQL-Anforderungen für die Überwachung finden Sie unter [SQL-Anforderungen für die Überwachung](monitoring.md#topologies).

## <a name="basics-about-monitoring"></a>Grundlagen zur Überwachung
<a name="Basics"> </a>

Eine Sitzung ist ein allgemeiner Begriff für eine Verbindung mit a:

- Konferenz

- Konferenztools wie Audio/Video oder Anwendungsfreigabe

- Andere Benutzer über eine Peer-zu-Peer-Unterhaltung wie Sofortnachrichten oder Audioanruf

> [!NOTE]
> Skype für Business Server verfolgt Verwalten von Informationen über jede Sitzung:, die aufgerufen werden, die; Welche Endpunkte in der Sitzung verwendet wurden. wie lange die Sitzung zuletzt; Was war die wahrgenommene Qualität der Sitzung; Und so weiter. Skype für Business Server nicht aufzeichnen und speichern den tatsächlichen Aufruf selbst. Sofortnachrichtensitzungen enthält: zwar Skype für Business Server Informationen zu instant messaging-Sitzungen aufzeichnet, verwaltet es keinen Datensatz jeder Sofortnachricht angezeigt, die während der Sitzung gesendet wurde.

Die grundlegende Call Detail von Informationen zu Skype für Business Server für jede Sitzung kann für verwendet werden:

- Analyse der **Investment (ROI) zurückzugeben** . Administratoren können die Nutzungsdaten ähnliche Daten erfasst für ihre vorherigen Telefonsystem, um Kosten zu sparen anzeigen und unterstützen die Bereitstellung von Skype für Business Server rechtfertigen vergleichen.

- **Verwalten des Gerätebestands**: Informationen zur Inventarverwaltung unterstützen Administratoren bei der Identifikation alter Geräte, die ersetzt werden müssen. Außerdem können auf diese Weise kostenintensive Geräte ermittelt werden, die gar nicht oder zu wenig genutzt werden.

- **Helpdesk**: Informationen zur Problembehebung helfen Supporttechnikern herauszufinden, warum beim Anruf eines Benutzers ein Fehler aufgetreten ist, ohne dass Protokolle vom Server oder Client angefordert werden müssen. Problembehandlung bei Daten kann Support, den Techniker zu ermitteln, warum eines Benutzers fehlgeschlagenen, rufen Sie ohne Server oder Client-Side-Protokolle gespeichert. Diese Informationen kann sofort zugegriffen und von Supportpersonal, die nicht über eine intensive technischen Kenntnisse der Skype für Business-Client und Skype für Business Server verfügen verarbeitet werden.

- **Systemproblembehandlung**: Ermöglicht Administratoren das Erkennen grundlegender Probleme, die u. U. verhindern, dass Endbenutzer einfache Aufgaben wie das Beitreten zu einer Konferenz, das Durchführen eines Anrufs oder das Senden einer Chatnachricht ausführen können.

Überwachung bietet auch einen Mechanismus, der SIP-Endpunkte (beispielsweise Skype für Unternehmen) ermöglicht, um Informationen zur Problembehandlung bereitzustellen, die der Administrator andernfalls haben keinen Zugriff auf würde:

- **Medienmetriken mit Auswirkungen auf die Qualität**: Die Metriken beziehen sich auf die eigentliche Übertragung des Anrufs. Sie stellen eine Art „Reiseprotokoll“ des Anrufs durch das Netzwerk dar und beinhalten Daten wie Paketverluste, Jitter und Roundtripzeiten. Anhand dieser Informationen lässt sich erkennen, was mit dem Anruf zwischen dem Verlassen des einen Benutzerendpunkts und dem Eintreffen am anderen Benutzerendpunkt passiert.

- **Probleme, die für den Endbenutzer gemeldet**. Diese Kennzahlen beinhalten schlechter Qualität Benachrichtigungen, dass Skype für Unternehmen für Endbenutzer in Fällen zeigt, wo sie zu weit über ein Mikrofon sind, zu leise sprechen Schlechte Netzwerk verbunden ist, oder sind schlechten Qualität auftritt, da ein anderes Programm aus, klicken Sie auf der Computer ist die verfügbaren Ressourcen beanspruchen.

- **Umgebungsinformationen**: Diese Metriken erfassen detaillierte Faktoren der Anrufqualität wie den Typ des verwendeten Mikrofons und Lautsprechers, Angaben darüber, ob eine VPN-Verbindung verwendet wurde, und darüber, ob eine WLAN-Verbindung verwendet wurde.

Am Ende jedes Anrufs übertragen SIP-kompatible Endpunkte diese Informationen automatisch an den Front-End-Server, von dem der Anruf bereitgestellt wurde. Sie müssen nichts tun, damit diese Informationen von den Endpunkten übertragen werden. Das SIP-Protokoll ist bereits entsprechend konfiguriert. Wenn Sie diese Informationen jedoch erfassen und speichern möchten, müssen Sie die Überwachung aktivieren. Wenn Sie die Überwachung installieren und aktivieren, werden die Anrufinformationen von den Agents gesammelt, die auf dem Front-End-Server ausgeführt werden, und an ein SQL Server-Datenbankpaar weitergeleitet. Der Überwachungsdienst wird (in Form von einheitlichen „Datenerfassungs-Agents“) auf allen Front-End-Servern integriert. 

## <a name="define-your-requirements-for-monitoring"></a>Definieren der Anforderungen für die Überwachung
<a name="requirements"> </a>

Es gibt immer noch einige wichtige Punkte, die berücksichtigt werden sollten, bevor Sie beginnen, installieren und Konfigurieren der Überwachung mit Skype für Business Server:

 **Wenn möchten Sie monitoring installieren?** Überwachung kann installiert und konfiguriert gleichzeitig installieren und Skype für Business Server konfiguriert werden; die Skype für Business Server-Bereitstellungs-Assistenten wird die Möglichkeit, eine Überwachungsdatenbank, die während des Setups die Front-End-Pools zuordnen bereitgestellt werden. Alternativ können Sie die Überwachung nach der Installation von Skype für Business Server selbst installieren. Dies kann mithilfe des Topologie-Generators eine Überwachungsdatenbank, die Ihre Front-End-Pools und Server zugeordnet, und klicken Sie dann Veröffentlichen der überarbeiteten Topologie erfolgen.

Lassen Sie beachten Sie, dass SQL Server installiert und konfiguriert werden, bevor Sie bereitstellen und Konfigurieren der Überwachung werden muss. Sie müssen jedoch nur zum Bereitstellen von SQL Server selbst. die überwachen Datenbanken werden für Sie erstellt werden, wenn Sie Ihre Skype für Business Server-Topologie veröffentlichen.

 **Welche Art von Daten möchten Sie überwachen?** Skype für Business Server können Sie zwei allgemeine Datentypen überwachen: Anruf mit ausführlichen Informationen zu Recording (CDR) und Quality of Experience (QoE)-Daten. Die Aufzeichnung von kommunikationsdatensätzen bietet eine Möglichkeit zum Nachverfolgen der Verwendung von Skype für Business Server-Features wie Voice over IP (VoIP) Telefonanrufe. Instant messaging (Sofortnachrichten); dateiübertragungen; Audio/Video (A / V) Konferenzen; und die Anwendungsfreigabe Sitzungen. Diese Informationen unterstützen Sie darauf hingewiesen, welche Skype für Business Server-Features verwendet werden (und die Schriftarten sind nicht) und enthält auch Informationen, wann diese Features verwendet werden. Daten Quality of Experience ermöglicht es Ihnen, die Qualität von Audio- und Videodaten Anrufe in Ihrer Organisation, z. B. wie die Anzahl von Netzwerkpaketen verloren aufzuzeichnen, Hintergrundgeräusche und die Menge des "jitter" (Unterschiede bei Paket Verzögerung).

Wenn Sie aktivieren können Überwachung in Skype für Business Server Sie monitoring KDS und QoE aktivieren können monitoring, oder Sie eine Art der Überwachung, während die anderen Typs deaktiviert lassen aktivieren. Nehmen wir beispielsweise bei Ihren Benutzern nur instant messaging und dateiübertragungen verwenden, und treffen Sie keine Audio-oder Videoanrufe. In diesem Fall möglicherweise wenig Sinn, QoE-Überwachung aktivieren. Ebenso erleichtert Skype für Business Server aktivieren und Deaktivieren der Überwachung nach monitoring bereitgestellt wurde. Sie können beispielsweise zum Bereitstellen des monitoring jedoch zunächst QoE-Überwachung deaktiviert lassen. Wenn Ihre Benutzer beginnen, um Probleme mit Audio-oder Videoanrufe konnte dann QoE-Überwachung aktivieren und mithilfe dieser Daten können Sie das Suchen und Beheben dieser Probleme.

Es gibt keine besonderen Vorteil (oder Nachteil) zu installieren, Sie Skype für Business Server installieren im Vergleich zu installieren, Überwachung nach der Installation von Skype für Business Server, gleichzeitig überwachen. Der einen Punkt im Hinterkopf behalten besteht darin, dass vor der Installation von monitoring, müssen Sie einen Computer zum Hosten der Back-End-monitoring Store auswählen und eine unterstützte Version von SQL Server muss installieren und auf diesem Computer konfiguriert sein, bevor dieses Computers für die Überwachung verwendet werden können . Wenn Sie SQL Server bereits auf einem Computer installiert haben und der Computer bereit für die Verwendung ist können Sie installieren monitoring gleichzeitig Skype für Business Server zu installieren. Wenn Sie nicht mit einen Back-End-Computer bereit verfügen können Sie fahren Sie mit Skype für Business Server selbst installieren dann installieren monitoring, sobald der Back-End-Computer zur Verfügung steht.

 **Wie viele Back-End-monitoring-Datenbanken benötigen Sie?** Es wurde geschätzt, dass eine verbundene Datenbank für Überwachung und Archivierung 240.000 Skype für Business Server-Benutzer unterstützen kann). Darüber hinaus kann ein einzelnes Überwachungsdatenbank durch mehrere Front-End-Pools verwendet werden. Wenn Sie drei Front-End-Pools in Ihrer Organisation haben könnten Sie alle drei dieser Pools mit dem gleichen Back-End-Speicher zuordnen.

Für viele Organisationen ist die Datenbankkapazität nicht der entscheidende Faktor beim Ermitteln der Anzahl benötigter Back-End-Überwachungsdatenbanken. Vielmehr könnte die Netzwerkgeschwindigkeit ein wichtigerer Faktor sein. Angenommen, es sind drei Front-End-Pools vorhanden, aber einer dieser Pools läuft über eine langsame Netzwerkverbindung. In diesem Fall sollten Sie zwei Überwachungsdatenbanken verwenden: eine Datenbank für die beiden Pools mit der schnellen Netzwerkverbindung und eine separate Datenbank für den Pool mit der langsameren Netzwerkverbindung.

Sie sollten auch bedenken, dass Skype für Business Server die Verwendung von Spiegeldatenbanken unterstützt. Die „Datenbankspiegelung“ bietet die Möglichkeit, zwei Kopien einer Datenbank gleichzeitig zu verwalten, wobei die Datenbanken auf unterschiedlichen Servern gespeichert werden. Immer wenn Daten in eine primäre Datenbank geschrieben werden, werden diese Daten auch in die Spiegeldatenbank geschrieben. Wenn die primäre Datenbank ausfällt oder anderweitig nicht verfügbar sind mehr, können Sie "Spiegeldatenbank Failover auf" mit einer einfachen Skype für Business Server PowerShell-Befehl. Beispiel:

```
Invoke-CsDatabaseFailover -PoolFqdn atl-cs-001.litwareinc.com -DatabaseType "Monitoring" -NewPrincipal "Mirror"
```

Dies spielt eine wichtige Rolle für die Planung, da Sie für die Spiegelung die erforderliche Anzahl von Datenbanken verdoppeln müssen. Denn zusätzlich zu jeder primären Datenbank benötigen Sie eine zweite Datenbank als Spiegeldatenbank.

 **Ist Ihre Skype für Business Server Websites ihre eigenen benutzerdefinierten Konfigurationen für die überwachen erforderlich?** Bei der Installation von Skype für Business Server installieren Sie auch globalen Auflistung von KDS und QoE-Konfigurationseinstellungen. Diese globalen Sammlungen Geben Sie die Möglichkeit, denselben KDS und QoE-Einstellungen für die gesamte Organisation gelten. In vielen Fällen ist dies ausreichend, denn Sie könne damit z. B. die KDS-Überwachung für alle Ihre Benutzer aktivieren.

Jedoch auch möglicherweise vorkommen, dass Sie unterschiedliche Einstellungen auf verschiedenen Websites anwenden möchten. Beispielsweise vielleicht Sie KDS und QoE-Überwachung in Ihrem Standort "Redmond" verwenden möchten, jedoch nur CDR Überwachung in Ihrer Dublin-Website verwenden. Sie möchten ebenso Überwachungsdaten für 60 Tage in den Standort Redmond beibehalten, aber nur diese Art von Daten für 30 Tage auf der Website Dublin verwalten müssen. Skype für Business Server können Sie separate Sammlungen von KDS und QoE-Konfigurationseinstellungen auf Standortebene zu erstellen. mit dem Sie jede Website unterschiedlich zu verwalten. (Dies umfasst beide aktivieren und Deaktivieren der Überwachung und Konfigurieren von Einstellungen für die Verwaltung wie etwa wie lange Daten aufbewahrt werden, ist).

Beachten Sie, dass Sie diese Entscheidung vor oder nach der Bereitstellung der Überwachung treffen können. Beispielsweise können Sie die Überwachung bereitstellen und anschließend die gesamte Organisation mithilfe der globalen Einstellungen verwalten. Falls Sie später Ihre Meinung ändern, können Sie eine separate Sammlung von Einstellungen z. B. für den Standort Redmond erstellen und dann die Überwachung für Redmond mithilfe dieser Einstellungen verwalten. (Einstellungen auf Standortebene haben stets Vorrang vor globalen Einstellungen.) Wenn Sie Ihre Meinung erneut ändern, können Sie einfach die Konfigurationseinstellungen löschen, die auf den Standort Redmond angewendet werden. Wenn eine Sammlung von Standorteinstellungen entfernt wird, wird die globale Sammlung von Einstellungen automatisch auf diesen Standort angewendet.

## <a name="sql-requirements-for-monitoring"></a>SQL-Anforderungen für die Überwachung
<a name="topologies"> </a>

Die einheitlichen Datenerfassungs-Agents werden bei der Aktivierung der Überwachung automatisch auf allen Front-End-Servern installiert und aktiviert. Unterstützte Versionen von SQL Server sowie andere Details finden Sie unter [Server-Anforderungen für Skype für Business Server 2015](requirements-for-your-environment/server-requirements.md)

Überwachungsdaten können eine SQL Server-Instanz gemeinsam mit anderen Datentypen verwenden. In der Regel verwenden die Datenbank für die Aufzeichnung von Kommunikationsdatensätzen (LcsCdr) und die Quality of Experience-Datenbank (QoEMetrics) dieselbe SQL-Instanz. Häufig sind die beiden Überwachungsdatenbanken auch in derselben SQL-Instanz wie die Archivierungsdatenbank (LcsLog) vorhanden. Die einzige echte Anforderung für SQL Server-Instanzen besteht darin, dass jede Instanz von SQL Server auf Folgendes beschränkt ist:

- Eine Instanz der der Skype für Business Server 2015 Back-End-Datenbank. (Im Allgemeinen wird davon abgeraten, die Überwachungsdatenbank in derselben SQL-Instanz oder sogar auf demselben Computer wie die Back-End-Datenbank zu verwenden. Dies ist zwar technisch möglich, aber es besteht das Risiko, dass die Überwachungsdatenbank Speicherplatz belegt, der für die Back-End-Datenbank benötigt wird.)

- Eine Instanz der Datenbank für die Aufzeichnung von Kommunikationsdatensätzen.

- Eine Instanz der Quality of Experience-Datenbank.

- Eine Instanz der Archivierungsdatenbank.

Das heißt, zwei Instanzen der LcsCdr-Datenbank sind in derselben SQL Server-Instanz nicht zulässig. Falls Sie mehrere Instanzen der LcsCdr-Datenbank benötigen, müssen Sie mehrere SQL Server-Instanzen konfigurieren.

## <a name="see-also"></a>Siehe auch


[Bereitstellen des Monitoring](https://technet.microsoft.com/library/117f4a3e-0670-4388-a553-b9854921145f.aspx)