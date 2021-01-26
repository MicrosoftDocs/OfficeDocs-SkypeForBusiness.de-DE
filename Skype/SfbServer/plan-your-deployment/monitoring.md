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
description: 'Zusammenfassung: Lesen Sie dieses Thema, während Sie den Überwachungsdienst in Skype for Business Server planen.'
ms.openlocfilehash: b2f269d3e4cc62ca08ee423858e13d12b23bddd1
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2021
ms.locfileid: "49825625"
---
# <a name="plan-for-monitoring-in-skype-for-business-server"></a>Planen der Überwachung in Skype for Business Server

**Zusammenfassung:** Lesen Sie dieses Thema, während Sie den Überwachungsdienst in Skype for Business Server planen.

Der Überwachungsdienst in Skype for Business Server bietet Administratoren eine Möglichkeit, Nutzungs- und Qualitätsdaten für die Kommunikationssitzungen in ihrer Organisation zu sammeln, die es ihnen ermöglichen, Trends und Probleme zu erkennen. Mit der fortlaufenden Überwachung Ihrer Bereitstellung können Sie Probleme frühzeitig abfangen und die Benutzer Ihrer Organisation zufrieden stellen.

Für die Überwachung in Skype for Business Server ist keine separate Serverrolle erforderlich (wie in früheren Lync-Versionen). Stattdessen ist der Überwachungsdienst in jeden Front-End-Server integrierte. Die Überwachung ist in Skype for Business Server nicht standardmäßig aktiviert. Dieser Artikel hilft Ihnen zu bestimmen, ob die Überwachung während oder nach ihrer anfänglichen Skype for Business Server-Konfiguration aktiviert werden soll und welche SQL Ressourcen Sie benötigen, um Überwachungsaktivitäten zu unterstützen. Wenn Sie nicht genau wissen, was überwacht wird oder was nicht, und wie die Überwachung hilfreich sein kann, wechseln Sie zu "Grundlagen zur [Überwachung".](monitoring.md#Basics) To begin your planning process, go to [Define your requirements for monitoring](monitoring.md#requirements). Weitere Informationen zu den SQL für die Überwachung finden Sie unter [SQL für die Überwachung.](monitoring.md#topologies)

## <a name="basics-about-monitoring"></a>Grundlagen zur Überwachung
<a name="Basics"> </a>

Eine Sitzung ist ein allgemeiner Begriff für die Verbindung eines Benutzers mit einem:

- Konferenz

- Konferenztool wie Audio/Video oder Anwendungsfreigabe

- Andere Benutzer über eine Peer-zu-Peer-Unterhaltung wie Sofortnachrichten oder Audioanruf

> [!NOTE]
> Skype for Business Server verfolgt Informationen zu jeder Sitzung nach: wer angerufen hat; welche Endpunkte in der Sitzung verwendet wurden; wie lange die Sitzung zuletzt war; Was war die wahrgenommene Qualität der Sitzung? Und so weiter. Skype for Business Server erfasst und speichert den tatsächlichen Anruf selbst nicht. Dazu gehören Instant Messaging-Sitzungen: Skype for Business Server zeichnet zwar Informationen zu Chatsitzungen auf, es wird jedoch nicht jede Chatnachricht aufgezeichnet, die während der Sitzung gesendet wurde.

Die grundlegenden Anrufdetailinformationen, die von Skype for Business Server für jede Sitzung gesammelt werden, können für:

- **Return on Investment (ROI)-Analyse.** Administratoren können die Nutzungsdaten mit ähnlichen Daten vergleichen, die für ihr vorheriges Telefoniesystem gesammelt wurden, um Kosteneinsparungen zu zeigen und die Bereitstellung von Skype for Business Server zu rechtfertigen.

- **Gerätebestandsverwaltung**. Mithilfe von Ressourcenverwaltungsinformationen können Administratoren alte Geräte identifizieren, die noch verwendet werden, die ersetzt werden müssen, und teure Geräte identifizieren, die nicht verwendet oder nicht verwendet werden.

- **Helpdesk**. Problembehandlungsdaten helfen Supporttechnikern zu ermitteln, warum der Anruf eines Benutzers fehlgeschlagen ist, ohne server- oder clientseitige Protokolle erfassen zu müssen. Auf diese Informationen kann problemlos zugegriffen und von Supportmitarbeitern verstanden werden, die nicht über tiefe technische Kenntnisse des Skype for Business-Clients und skype for Business Server verfügen.

- **Systemproblembehandlung**. Ermöglicht Administratoren das Erkennen grundlegender Probleme, die u. U. verhindern, dass Endbenutzer einfache Aufgaben wie das Beitreten zu einer Konferenz, das Tätigen eines Anrufs oder das Senden einer Sofortnachricht ausführen können.

Die Überwachung bietet außerdem einen Mechanismus, der es SIP-Endpunkten (z. B. Skype for Business) ermöglicht, Informationen zur Problembehandlung zur Verfügung zu stellen, auf die der Administrator andernfalls keinen Zugriff hätte:

- **Medienmetriken, die sich auf die Qualität auswirken.** Diese Metriken befassen sich mit der tatsächlichen Übermittlung des Anrufs selbst. Sie bieten eine Art Reisebericht, während der Anruf über das Netzwerk geht. Diese Metriken (z. B. Paketverlust, Jitter und Roundtripzeiten) liefern Informationen dazu, was mit dem Anruf passiert ist, als er den Endpunkt einer Person verlassen hat, bis zu dem Zeitpunkt, zu dem er am Endpunkt der anderen Person eintroffen ist.

- **Probleme, die dem Endbenutzer gemeldet wurden.** Diese Metriken umfassen Benachrichtigungen schlechter Qualität, die Skype for Business Endbenutzern präsentiert, wenn sie zu weit von einem Mikrofon entfernt sind, zu weich sprechen, eine schlechte Netzwerkverbindung haben oder eine schlechte Qualität haben, da ein anderes Programm auf dem Computer die verfügbaren Ressourcen verbraucht.

- **Umgebungsinformationen**. Diese Metriken erfassen detaillierte Faktoren der Anrufqualität wie den Typ des verwendeten Mikrofons und Lautsprechers, Angaben darüber, ob eine VPN-Verbindung verwendet wurde und Angaben darüber, ob eine WLAN-Verbindung verwendet wurde.

Am Ende jedes Anrufs übertragen SIP-kompatible Endpunkte diese Informationen an den Front-End-Server, der den Anruf erleichtert hat. Sie müssen nichts tun, um Endpunkte zu erhalten, um diese Informationen zu übertragen. dieses Verhalten ist in das SIP-Protokoll integriertes Verhalten. Wenn Sie diese Informationen jedoch sammeln und speichern möchten, müssen Sie die Überwachung installieren und aktivieren. Wenn Sie die Überwachung installieren und aktivieren, werden Anrufinformationen von Agents gesammelt, die auf dem Front-End-Server ausgeführt werden, und an ein Paar von SQL Server übertragen. Der Überwachungsdienst (in Form von "einheitlichen Datensammlungs-Agents") ist mit allen Front-End-Servern gemeinsam ausgeführt.

## <a name="define-your-requirements-for-monitoring"></a>Definieren der Anforderungen für die Überwachung
<a name="requirements"> </a>

Es gibt noch einige wichtige Probleme, die behoben werden sollten, bevor Sie mit der Installation und Konfiguration der Überwachung mit Skype for Business Server beginnen:

 **Wann möchten Sie die Überwachung installieren?** Die Überwachung kann gleichzeitig installiert und konfiguriert werden, wenn Sie Skype for Business Server installieren und konfigurieren. Der Skype for Business Server-Bereitstellungs-Assistent bietet Ihnen die Möglichkeit, Ihre Front-End-Pools während des Setups einer Überwachungsdatenbank zuzuordnen. Alternativ können Sie die Überwachung installieren, nachdem Skype for Business Server selbst installiert wurde. Dazu können Sie den Topologie-Generator verwenden, um Ihre Front-End-Pools und -Server einer Überwachungsdatenbank zuzuordnen und dann die überarbeitete Topologie zu veröffentlichen.

Beachten Sie, dass SQL Server installiert und konfiguriert werden muss, bevor Sie die Überwachung bereitstellen und konfigurieren. Sie müssen jedoch nur die SQL Server bereitstellen. Die Überwachungsdatenbanken werden für Sie erstellt, wenn Sie Ihre Skype for Business Server-Topologie veröffentlichen.

 **Welche Art von Daten möchten Sie überwachen?** Mit Skype for Business Server können Sie zwei allgemeine Arten von Daten überwachen: Daten zur Aufzeichnung von Aufgezeichneten Anrufen (CdR) und QoE (Quality of Experience). Mit der Aufzeichnung von Anrufdetails können Sie die Nutzung von Skype for Business #A0 wie Voice over IP (VoIP)-Telefonanrufen nachverfolgen. Chat; Dateiübertragungen; Audio-/Videokonferenzen (A/V); und Anwendungsfreigabesitzungen. Diese Informationen helfen Ihnen zu wissen, welche Skype for Business Server-Features verwendet werden (und welche nicht), und bieten auch Informationen dazu, wann diese Features verwendet werden. Mit Den Daten zur Erlebnisqualität können Sie die Qualität von Audio- und Videoanrufen in Ihrer Organisation aufzeichnen, z. B. die Anzahl der verloren gegangenen Netzwerkpakete, Hintergrundgeräusche und die Menge an "Jitter" (Unterschiede bei der Paketverzögerung).

Wenn Sie die Überwachung in Skype for Business Server aktivieren, können Sie sowohl die CdR- als auch die QoE-Überwachung aktivieren, oder Sie können einen Überwachungstyp aktivieren und den anderen Typ deaktiviert lassen. Angenommen, Ihre Benutzer verwenden nur Chatnachrichten und Dateiübertragungen und tätigen keine Audio- oder Videoanrufe. In diesem Fall gibt es möglicherweise keinen Grund, die QoE-Überwachung zu aktivieren. Ebenso erleichtert Skype for Business Server das Aktivieren und Deaktivieren der Überwachung nach der Bereitstellung der Überwachung. Beispielsweise können Sie die Überwachung bereitstellen, die QoE-Überwachung jedoch zunächst deaktiviert lassen. Wenn bei Ihren Benutzern Probleme mit Audio- oder Videoanrufen auftreten, können Sie die QoE-Überwachung aktivieren und diese Daten verwenden, um diese Probleme zu beheben und zu beheben.

Es gibt keinen besonderen Vorteil (oder Nachteil) bei der Installation der Überwachung gleichzeitig, wenn Sie Skype for Business Server installieren, im Vergleich zur Installation der Überwachung nach der Installation von Skype for Business Server. Beachten Sie, dass Sie vor der Installation der Überwachung einen Computer zum Hosten des Back-End-Überwachungsspeichers auswählen müssen, und eine unterstützte Version von SQL Server muss auf diesem Computer installiert und konfiguriert werden, bevor dieser Computer für die Überwachung verwendet werden kann. Wenn Sie bereits SQL Server auf einem Computer installiert haben und dieser Computer einsatzbereit ist, können Sie die Überwachung gleichzeitig installieren, wenn Sie Skype for Business Server installieren. Wenn Sie noch keinen Back-End-Computer bereit haben, können Sie mit der Installation von Skype for Business Server allein fortfahren und dann die Überwachung installieren, sobald der Back-End-Computer einsatzbereit ist.

 **Wie viele Back-End-Überwachungsdatenbanken benötigen Sie?** Es wurde geschätzt, dass eine gleichzeitige Datenbank für die Überwachung und Archivierung 240.000 Skype for Business Server-Benutzer unterstützen kann. Darüber hinaus kann eine einzelne Überwachungsdatenbank von mehreren Front-End-Pools verwendet werden. Wenn Sie drei Front-End-Pools in Ihrer Organisation haben, können Sie alle drei Pools demselben Back-End-Speicher zuordnen.

Für viele Organisationen ist die Datenbankkapazität nicht der entscheidende Faktor bei der Bestimmung der Anzahl erforderlicher Back-End-Überwachungsdatenbanken. Vielmehr könnte die Netzwerkgeschwindigkeit ein wichtigerer Faktor sein. Angenommen, es sind drei Front-End-Pools vorhanden, aber einer dieser Pools wird über eine langsame Netzwerkverbindung verwendet. In diesem Fall sollten Sie zwei Überwachungsdatenbanken verwenden: eine Datenbank für die beiden Pools mit der schnellen Netzwerkverbindung, und eine separate Datenbank für den Pool mit der langsameren Netzwerkverbindung.

Sie sollten auch berücksichtigen, dass Skype for Business Server die Verwendung von Spiegeldatenbanken unterstützt. Die "Datenbankspiegelung" bietet die Möglichkeit, zwei Kopien einer Datenbank gleichzeitig zu verwalten, wobei die Datenbanken auf unterschiedlichen Servern gespeichert werden. Immer wenn Daten in eine primäre Datenbank geschrieben werden, werden diese Daten auch in die Spiegeldatenbank geschrieben. Wenn die primäre Datenbank ausfällt oder anderweitig nicht verfügbar ist, können Sie ein Failover zur Spiegeldatenbank ausführen, indem Sie einen einfachen Skype for Business Server -PowerShell-Befehl verwenden. Beispiel:

```PowerShell
Invoke-CsDatabaseFailover -PoolFqdn atl-cs-001.litwareinc.com -DatabaseType "Monitoring" -NewPrincipal "Mirror"
```

Dies spielt eine wichtige Rolle für die Planung, da Sie für die Spiegelung die erforderliche Anzahl von Datenbanken verdoppeln müssen. Denn zusätzlich zu jeder primären Datenbank benötigen Sie eine zweite Datenbank als Spiegeldatenbank.

 **Benötigen Ihre Skype for Business Server-Websites eigene benutzerdefinierte Überwachungskonfigurationen?** Wenn Sie Skype for Business Server installieren, installieren Sie auch globale Auflistungen von CdR- und QoE-Konfigurationseinstellungen. Diese globalen Sammlungen bieten Ihnen die Möglichkeit, die gleichen CdR- und QoE-Einstellungen auf Ihre gesamte Organisation anzuwenden. In vielen Fällen ist dies ausreichend, denn oft möchten Sie z. B. die KDS-Überwachung für alle Ihre Benutzer aktivieren.

Es kann jedoch auch sein, dass Sie unterschiedliche Einstellungen auf unterschiedliche Websites anwenden möchten. Vielleicht möchten Sie beispielsweise sowohl die CDR- als auch die QoE-Überwachung am Standort "Redmond" verwenden, aber nur die Überwachung der CdR am Standort Dublin verwenden. Ebenso können Sie überwachungsdaten für 60 Tage am Standort Redmond beibehalten, müssen diese Art von Daten jedoch nur für 30 Tage am Standort Dublin beibehalten. Skype for Business Server ermöglicht ihnen das Erstellen separater Auflistungen von Konfigurationseinstellungen für die CdR und QoE auf Standortbereich. ermöglicht es Ihnen, jede Website unterschiedlich zu verwalten. (Dies umfasst sowohl das Aktivieren und Deaktivieren der Überwachung als auch das Konfigurieren von Verwaltungseinstellungen, z. B. wie lange Daten aufbewahrt werden sollen.)

Beachten Sie, dass Sie diese Entscheidung vor oder nach der Bereitstellung der Überwachung treffen können. Beispielsweise können Sie die Überwachung bereitstellen und anschließend die gesamte Organisation mithilfe der globalen Einstellungen verwalten. Falls Sie später Ihre Meinung ändern, können Sie eine separate Sammlung von Einstellungen z. B. für den Standort Redmond erstellen und dann die Überwachung für Redmond mithilfe dieser Einstellungen verwalten. (Einstellungen auf Standortebene haben stets Vorrang vor globalen Einstellungen.) Wenn Sie Ihre Meinung erneut ändern, können Sie einfach die Konfigurationseinstellungen löschen, die auf den Standort Redmond angewendet werden. Wenn eine Sammlung von Standorteinstellungen entfernt wird, wird die globale Sammlung von Einstellungen automatisch auf diesen Standort angewendet.

## <a name="sql-requirements-for-monitoring"></a>SQL anforderungen für die Überwachung
<a name="topologies"> </a>

Die einheitlichen Datensammlungs-Agents werden automatisch auf jedem Front-End-Server installiert und aktiviert, wenn Sie die Überwachung aktivieren. Unterstützte Versionen von SQL Server und weitere Informationen finden Sie unter ["Serveranforderungen für Skype for Business Server 2015"](requirements-for-your-environment/server-requirements.md)

Überwachungsdaten können eine SQL Server mit anderen Datentypen gemeinsam verwenden. In der Regel verwenden die Datenbank für die Aufzeichnung von Anrufdetaildaten (LcsCdr) und die Quality of Experience-Datenbank (QoEMetrics) dieselbe SQL Instanz; Es ist auch üblich, dass sich die beiden Überwachungsdatenbanken in der SQL der Archivierungsdatenbank (LcsLog) befinden. Die einzige tatsächliche Anforderung bei SQL Server ist, dass jede instanz von SQL Server auf Folgendes beschränkt ist:

- Eine Instanz der Skype for Business Server 2015-Back-End-Datenbank. (In der Regel wird davon abraten, die Überwachungsdatenbank in derselben SQL-Instanz oder sogar auf demselben Computer wie die Back-End-Datenbank zu verwenden. Obwohl technisch möglich, besteht das Risiko, dass die Überwachungsdatenbank den von der Back-End-Datenbank benötigten Speicherplatz auffüllt.)

- Eine Instanz der Datenbank für die Aufzeichnung von Anrufdetails.

- Eine Instanz der Quality of Experience-Datenbank.

- Eine Instanz der Archivierungsdatenbank.

Mit anderen Worten, sie können nicht zwei Instanzen der Datenbank "LcsCdr" in derselben Instanz des SQL Server. Wenn Sie mehrere Instanzen der Datenbank "LcsCdr" benötigen, müssen Sie mehrere Instanzen von SQL Server.

## <a name="see-also"></a>Siehe auch


[Bereitstellen des Monitoring Servers](https://technet.microsoft.com/library/117f4a3e-0670-4388-a553-b9854921145f.aspx)
