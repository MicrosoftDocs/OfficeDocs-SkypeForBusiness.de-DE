---
title: Planen der Überwachung in Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 5d5eb658-7fe0-42e6-acaf-700051d0a823
description: 'Zusammenfassung: Lesen Sie dieses Thema beim Planen des Überwachungsdiensts in Skype for Business Server.'
ms.openlocfilehash: ebe94d3088e319a0c210c9d169f35f1c783ad5f5
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/08/2020
ms.locfileid: "40991780"
---
# <a name="plan-for-monitoring-in-skype-for-business-server"></a>Planen der Überwachung in Skype for Business Server

**Zusammenfassung:** Lesen Sie dieses Thema beim Planen des Überwachungsdiensts in Skype for Business Server.

Der Überwachungsdienst in Skype for Business Server bietet Administratoren die Möglichkeit, Nutzungs-und Qualitätsdaten für die Kommunikationssitzungen zu sammeln, die in Ihrer Organisation stattfinden, wodurch Sie Trends und Probleme erkennen können. Wenn Sie Ihre Bereitstellung kontinuierlich überwachen, können Sie Probleme frühzeitig abfangen und die Benutzer Ihrer Organisation zufrieden stellen.

Für die Überwachung in Skype for Business Server ist keine separate Server Rolle erforderlich (wie dies in früheren lync-Versionen der Fall war). Stattdessen ist der Überwachungsdienst in jedem Front-End-Server integriert. Die Überwachung ist in Skype for Business Server nicht standardmäßig aktiviert. In diesem Artikel wird erläutert, ob Sie die Überwachung während oder nach der anfänglichen Skype for Business Server-Konfiguration aktivieren und welche SQL-Ressourcen Sie zur Unterstützung von Überwachungsaktivitäten benötigen. Wenn Sie sich nicht sicher sind, was genau ist, was nicht überwacht wird und wie die Überwachung hilfreich sein kann, gehen Sie zu [Grundlagen zur Überwachung](monitoring.md#Basics). Um mit der Planung zu beginnen, gehen Sie zu [definieren Sie Ihre Anforderungen für die Überwachung](monitoring.md#requirements). Weitere Informationen zu den SQL-Anforderungen für die Überwachung finden Sie unter [SQL-Anforderungen für die Überwachung](monitoring.md#topologies).

## <a name="basics-about-monitoring"></a>Grundlagen zur Überwachung
<a name="Basics"> </a>

Bei einer Sitzung handelt es sich um einen generischen Ausdruck für die Verbindung eines Benutzers mit einem:

- Konferenz

- Konferenztools wie Audio/Video oder Anwendungsfreigabe

- Andere Benutzer über eine Peer-zu-Peer-Unterhaltung wie Sofortnachrichten oder Audioanruf

> [!NOTE]
> Skype for Business Server verfolgt Informationen zu den einzelnen Sitzungen: Wer hat wen angerufen? welche Endpunkte in der Sitzung verwendet wurden; wie lange dauerte die Sitzung? Was war die wahrgenommene Qualität der Sitzung; Und so weiter. Skype for Business Server zeichnet den eigentlichen Anruf selbst nicht auf und speichert ihn nicht. Dazu gehören Chat-Sitzungen: Obwohl Skype for Business Server Informationen zu Chat-Sitzungen aufzeichnet, wird keine Aufzeichnung der einzelnen Sofortnachrichten, die während der Sitzung gesendet wurden, verwaltet.

Die grundlegenden Anruf Detailinformationen, die von Skype for Business Server für jede Sitzung gesammelt werden, können für folgende verwendet werden:

- Rentabilitätsanalyse **(Return on Investment)** . Administratoren können die Nutzungsdaten mit ähnlichen Daten vergleichen, die für Ihr vorheriges Telefoniesystem erfasst wurden, um Kosteneinsparungen anzuzeigen und die Bereitstellung von Skype for Business Server zu rechtfertigen.

- **Verwalten des Gerätebestands**: Informationen zur Inventarverwaltung unterstützen Administratoren bei der Identifikation alter Geräte, die ersetzt werden müssen. Außerdem können auf diese Weise kostenintensive Geräte ermittelt werden, die gar nicht oder zu wenig genutzt werden.

- **Helpdesk**: Informationen zur Problembehebung helfen Supporttechnikern herauszufinden, warum beim Anruf eines Benutzers ein Fehler aufgetreten ist, ohne dass Protokolle vom Server oder Client angefordert werden müssen. Die Behandlung von Daten hilft Supportingenieuren beim ermitteln, warum der Anruf eines Benutzers fehlgeschlagen ist, ohne Server-oder clientseitige Protokolle sammeln zu müssen. Diese Informationen können von Supportmitarbeitern, die keine fundierten technischen Kenntnisse über den Skype for Business-Client und den Skype for Business-Server besitzen, problemlos abgerufen und verstanden werden.

- **Systemproblembehandlung**: Ermöglicht Administratoren das Erkennen grundlegender Probleme, die u. U. verhindern, dass Endbenutzer einfache Aufgaben wie das Beitreten zu einer Konferenz, das Durchführen eines Anrufs oder das Senden einer Chatnachricht ausführen können.

Die Überwachung bietet auch einen Mechanismus, mit dem SIP-Endpunkte (wie Skype for Business) Informationen zur Problembehandlung bereitstellen, auf die der Administrator sonst keinen Zugriff hat:

- **Medienmetriken mit Auswirkungen auf die Qualität**: Die Metriken beziehen sich auf die eigentliche Übertragung des Anrufs. Sie stellen eine Art „Reiseprotokoll“ des Anrufs durch das Netzwerk dar und beinhalten Daten wie Paketverluste, Jitter und Roundtripzeiten. Anhand dieser Informationen lässt sich erkennen, was mit dem Anruf zwischen dem Verlassen des einen Benutzerendpunkts und dem Eintreffen am anderen Benutzerendpunkt passiert.

- **Probleme, die dem Endbenutzer gemeldet**wurden. Zu diesen Metriken gehören Benachrichtigungen über schlechte Qualität, die Skype for Business für Endbenutzer in Fällen vorstellt, in denen Sie zu weit von einem Mikrofon entfernt sind, zu leise sprechen, eine schlechte Netzwerkverbindung haben oder eine schlechte Qualität aufweisen, weil ein anderes Programm auf dem der Computer beansprucht die verfügbaren Ressourcen.

- **Umgebungsinformationen**: Diese Metriken erfassen detaillierte Faktoren der Anrufqualität wie den Typ des verwendeten Mikrofons und Lautsprechers, Angaben darüber, ob eine VPN-Verbindung verwendet wurde, und darüber, ob eine WLAN-Verbindung verwendet wurde.

Am Ende jedes Anrufs übertragen SIP-kompatible Endpunkte diese Informationen automatisch an den Front-End-Server, von dem der Anruf bereitgestellt wurde. Sie müssen nichts tun, damit diese Informationen von den Endpunkten übertragen werden. Das SIP-Protokoll ist bereits entsprechend konfiguriert. Wenn Sie diese Informationen jedoch erfassen und speichern möchten, müssen Sie die Überwachung aktivieren. Wenn Sie die Überwachung installieren und aktivieren, werden die Anrufinformationen von den Agents gesammelt, die auf dem Front-End-Server ausgeführt werden, und an ein SQL Server-Datenbankpaar weitergeleitet. Der Überwachungsdienst wird (in Form von einheitlichen „Datenerfassungs-Agents“) auf allen Front-End-Servern integriert. 

## <a name="define-your-requirements-for-monitoring"></a>Definieren der Anforderungen für die Überwachung
<a name="requirements"> </a>

Es gibt immer noch einige wichtige Probleme, die behoben werden sollten, bevor Sie mit der Installation und Konfiguration der Überwachung mit Skype for Business Server beginnen:

 **Wann möchten Sie die Überwachung installieren?** Die Überwachung kann zur gleichen Zeit installiert und konfiguriert werden, wie Sie Skype for Business Server installieren und konfigurieren. der Bereitstellungs-Assistent von Skype for Business Server bietet Ihnen die Möglichkeit, Ihre Front-End-Pools während des Setups mit einer Überwachungsdatenbank zu verknüpfen. Sie können die Überwachung auch nach der Installation von Skype for Business Server selbst installieren. Dies kann mithilfe des Topologie-Generators erfolgen, um Ihre Front-End-Pools und-Server einer Überwachungsdatenbank zuzuordnen und dann die überarbeitete Topologie zu veröffentlichen.

Beachten Sie, dass SQL Server installiert und konfiguriert werden muss, bevor Sie die Überwachung bereitstellen und konfigurieren. Sie müssen jedoch nur SQL Server selbst bereitstellen. Wenn Sie Ihre Skype for Business Server-Topologie veröffentlichen, werden die Überwachungsdatenbanken für Sie erstellt.

 **Welche Datentypen möchten Sie überwachen?** Mit Skype for Business Server können Sie zwei allgemeine Datentypen überwachen: Datenerfassungs Daten (CDR) und QoE-Daten (Quality of Experience). Die Anrufdetailaufzeichnung bietet Ihnen die Möglichkeit, die Nutzung von Skype for Business Server-Funktionen wie VoIP-Telefon anrufen (Voice over IP) nachvollziehen zu können. Instant Messaging (im) Dateiübertragungen; Audio/Video-Konferenzen (A/V); und Anwendungsfreigabesitzungen. Mithilfe dieser Informationen können Sie wissen, welche Skype for Business Server-Features verwendet werden (und welche nicht), und es werden auch Informationen darüber bereitgestellt, wann diese Features verwendet werden. Mit der Qualität der Erfahrungsdaten können Sie eine Aufzeichnung der Qualität von Audio-und Videoanrufen in Ihrer Organisation aufrecht erhalten, beispielsweise die Anzahl der verloren gegangenen Netzwerkpakete, Hintergrundgeräusche und die Anzahl der "Jitter" (Unterschiede bei der Paketverzögerung).

Wenn Sie sich entscheiden, die Überwachung in Skype for Business Server zu aktivieren, können Sie sowohl die CDR-Überwachung als auch die QoE-Überwachung aktivieren, oder Sie können eine Art von Überwachung aktivieren, während der andere Typ deaktiviert bleibt. Nehmen Sie beispielsweise an, dass Ihre Benutzer nur Instant Messaging und Dateiübertragungen verwenden und keine Audio-oder Videoanrufe tätigen. In diesem Fall kann es wenig Grund für die Aktivierung der QoE-Überwachung geben. Ebenso vereinfacht Skype for Business Server die Aktivierung und Deaktivierung der Überwachung, nachdem die Überwachung bereitgestellt wurde. So können Sie beispielsweise die Überwachung bereitstellen, aber zunächst die QoE-Überwachung deaktivieren. Wenn Ihre Benutzer Probleme mit Audio-oder Videoanrufen auftreten, können Sie die QoE-Überwachung aktivieren und diese Daten verwenden, um Sie bei der Problembehandlung zu unterstützen und diese Probleme zu beheben.

Es gibt keinen besonderen Vorteil (oder Nachteil) bei der Installation von Monitoring zur gleichen Zeit, wenn Sie die Installation von Skype for Business Server vs. Installation von Monitoring nach der Installation von Skype for Business Server durchgeführt haben. Beachten Sie, dass Sie vor der Installation der Überwachung einen Computer zum Hosten des Back-End-überwachungsspeichers auswählen müssen und eine unterstützte Version von SQL Server auf diesem Computer installiert und konfiguriert werden muss, bevor dieser Computer für die Überwachung verwendet werden kann. . Wenn Sie SQL Server bereits auf einem Computer installiert haben und dieser Computereinsatz bereit ist, können Sie die Überwachung zur gleichen Zeit installieren, wenn Sie Skype for Business Server installieren. Wenn Sie nicht über einen Back-End-Computer verfügen, können Sie die Installation von Skype for Business Server selbst fortsetzen und dann die Überwachung installieren, sobald der Back-End-Computereinsatz bereit ist.

 **Wie viele Back-End-Überwachungsdatenbanken benötigen Sie?** Es wurde geschätzt, dass eine Datenbank für die Überwachung und Archivierung 240.000 Skype for Business Server-Benutzer unterstützenkann. Darüber hinaus kann eine einzelne Überwachungsdatenbank von mehreren Front-End-Pools verwendet werden. Wenn Sie über drei Front-End-Pools in Ihrer Organisation verfügen, können Sie alle drei dieser Pools dem gleichen Back-End-Speicher zuordnen.

Für viele Organisationen ist die Datenbankkapazität nicht der entscheidende Faktor beim Ermitteln der Anzahl benötigter Back-End-Überwachungsdatenbanken. Vielmehr könnte die Netzwerkgeschwindigkeit ein wichtigerer Faktor sein. Angenommen, es sind drei Front-End-Pools vorhanden, aber einer dieser Pools läuft über eine langsame Netzwerkverbindung. In diesem Fall sollten Sie zwei Überwachungsdatenbanken verwenden: eine Datenbank für die beiden Pools mit der schnellen Netzwerkverbindung und eine separate Datenbank für den Pool mit der langsameren Netzwerkverbindung.

Sie sollten auch berücksichtigen, dass Skype for Business Server die Verwendung von Spiegeldatenbanken unterstützt. Die „Datenbankspiegelung“ bietet die Möglichkeit, zwei Kopien einer Datenbank gleichzeitig zu verwalten, wobei die Datenbanken auf unterschiedlichen Servern gespeichert werden. Immer wenn Daten in eine primäre Datenbank geschrieben werden, werden diese Daten auch in die Spiegeldatenbank geschrieben. Wenn die primäre Datenbank fehlschlägt oder anderweitig nicht mehr zur Verfügung steht, können Sie mit einem einfachen Skype for Business Server PowerShell-Befehl "Failover" zur Spiegeldatenbank durchführen. Beispiel:

```PowerShell
Invoke-CsDatabaseFailover -PoolFqdn atl-cs-001.litwareinc.com -DatabaseType "Monitoring" -NewPrincipal "Mirror"
```

Dies spielt eine wichtige Rolle für die Planung, da Sie für die Spiegelung die erforderliche Anzahl von Datenbanken verdoppeln müssen. Denn zusätzlich zu jeder primären Datenbank benötigen Sie eine zweite Datenbank als Spiegeldatenbank.

 **Benötigen Ihre Skype for Business Server-Websites eigene benutzerdefinierte Überwachungskonfigurationen?** Wenn Sie Skype for Business Server installieren, installieren Sie auch globale Sammlungen mit CDR-und QoE-Konfigurationseinstellungen. Diese globalen Auflistungen bieten Ihnen die Möglichkeit, die gleichen CDR-und QoE-Einstellungen auf Ihre gesamte Organisation anzuwenden. In vielen Fällen wird dies ausreichen: oftmals möchten Sie beispielsweise, dass die CDR-Überwachung für alle Benutzer aktiviert ist.

Es kann aber auch vorkommen, dass Sie unterschiedliche Einstellungen auf verschiedene Websites anwenden möchten. Vielleicht möchten Sie beispielsweise die CDR-und QoE-Überwachung auf Ihrer Website in Redmond verwenden, aber nur die CDR-Überwachung in Ihrer Dublin-Website verwenden. Ebenso möchten Sie möglicherweise Überwachungsdaten für 60 Tage auf der Website "Redmond" beibehalten, müssen aber nur diese Art von Daten 30 Tage lang auf der Website von Dublin verwalten. Skype for Business Server ermöglicht Ihnen, getrennte Sammlungen von CDR-und QoE-Konfigurationseinstellungen im Website Bereich zu erstellen. Damit können Sie jede Website unterschiedlich verwalten. (Dazu gehören sowohl das Aktivieren und Deaktivieren der Überwachung als auch das Konfigurieren von Verwaltungseinstellungen, wie beispielsweise die Aufbewahrungsdauer von Daten.)

Beachten Sie, dass Sie diese Entscheidung vor oder nach der Bereitstellung der Überwachung treffen können. Beispielsweise können Sie die Überwachung bereitstellen und anschließend die gesamte Organisation mithilfe der globalen Einstellungen verwalten. Falls Sie später Ihre Meinung ändern, können Sie eine separate Sammlung von Einstellungen z. B. für den Standort Redmond erstellen und dann die Überwachung für Redmond mithilfe dieser Einstellungen verwalten. (Einstellungen auf Standortebene haben stets Vorrang vor globalen Einstellungen.) Wenn Sie Ihre Meinung erneut ändern, können Sie einfach die Konfigurationseinstellungen löschen, die auf den Standort Redmond angewendet werden. Wenn eine Sammlung von Standorteinstellungen entfernt wird, wird die globale Sammlung von Einstellungen automatisch auf diesen Standort angewendet.

## <a name="sql-requirements-for-monitoring"></a>SQL-Anforderungen für die Überwachung
<a name="topologies"> </a>

Die einheitlichen Datenerfassungs-Agents werden bei der Aktivierung der Überwachung automatisch auf allen Front-End-Servern installiert und aktiviert. Informationen zu unterstützten Versionen von SQL Server und anderen Details finden Sie unter [Server Anforderungen für Skype for Business Server 2015](requirements-for-your-environment/server-requirements.md)

Überwachungsdaten können eine SQL Server-Instanz gemeinsam mit anderen Datentypen verwenden. In der Regel verwenden die Datenbank für die Aufzeichnung von Kommunikationsdatensätzen (LcsCdr) und die Quality of Experience-Datenbank (QoEMetrics) dieselbe SQL-Instanz. Häufig sind die beiden Überwachungsdatenbanken auch in derselben SQL-Instanz wie die Archivierungsdatenbank (LcsLog) vorhanden. Die einzige echte Anforderung für SQL Server-Instanzen besteht darin, dass jede Instanz von SQL Server auf Folgendes beschränkt ist:

- Eine Instanz der Skype for Business Server 2015-Back-End-Datenbank. (Im Allgemeinen wird davon abgeraten, die Überwachungsdatenbank in derselben SQL-Instanz oder sogar auf demselben Computer wie die Back-End-Datenbank zu verwenden. Dies ist zwar technisch möglich, aber es besteht das Risiko, dass die Überwachungsdatenbank Speicherplatz belegt, der für die Back-End-Datenbank benötigt wird.)

- Eine Instanz der Datenbank für die Aufzeichnung von Kommunikationsdatensätzen.

- Eine Instanz der Quality of Experience-Datenbank.

- Eine Instanz der Archivierungsdatenbank.

Das heißt, zwei Instanzen der LcsCdr-Datenbank sind in derselben SQL Server-Instanz nicht zulässig. Falls Sie mehrere Instanzen der LcsCdr-Datenbank benötigen, müssen Sie mehrere SQL Server-Instanzen konfigurieren.

## <a name="see-also"></a>Siehe auch


[Deploying Monitoring](https://technet.microsoft.com/library/117f4a3e-0670-4388-a553-b9854921145f.aspx)
