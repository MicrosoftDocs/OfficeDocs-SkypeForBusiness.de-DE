---
title: Planen der Überwachung in Skype for Business Server
ms.reviewer: null
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
  - NOCSH
ms.localizationpriority: medium
ms.assetid: 5d5eb658-7fe0-42e6-acaf-700051d0a823
description: 'Zusammenfassung: Lesen Sie dieses Thema bei der Planung des Überwachungsdiensts in Skype for Business Server.'
---

# <a name="plan-for-monitoring-in-skype-for-business-server"></a>Planen der Überwachung in Skype for Business Server

**Zusammenfassung:** Lesen Sie dieses Thema bei der Planung des Überwachungsdiensts in Skype for Business Server.

Der Überwachungsdienst in Skype for Business Server bietet Administratoren eine Möglichkeit, Nutzungs- und Qualitätsdaten für die Kommunikationssitzungen zu sammeln, die in ihrer Organisation stattfinden, sodass sie Trends und Probleme erkennen können. Die fortlaufende Überwachung Ihrer Bereitstellung ermöglicht es Ihnen, Probleme frühzeitig zu erkennen und die Benutzer Ihrer Organisation zufrieden zu halten.

Für die Überwachung in Skype for Business Server ist keine separate Serverrolle erforderlich (wie dies in früheren Lync-Versionen der Fall war). Stattdessen ist der Überwachungsdienst in jeden Front-End-Server integriert. Die Überwachung ist in Skype for Business Server nicht standardmäßig aktiviert. In diesem Artikel erfahren Sie, ob Sie die Überwachung während oder nach ihrer anfänglichen Skype for Business Server-Konfiguration aktivieren und welche SQL Ressourcen Sie benötigen, um Überwachungsaktivitäten zu unterstützen. Wenn Sie nicht genau wissen, was überwacht wird oder was nicht und wie die Überwachung hilfreich sein kann, wechseln Sie zu [den Grundlagen zur Überwachung](monitoring.md#Basics). Um Mit dem Planungsprozess zu beginnen, wechseln Sie zu ["Definieren der Anforderungen für die Überwachung](monitoring.md#requirements)". Weitere Informationen zu den SQL Anforderungen für die Überwachung finden Sie unter [SQL Anforderungen für die Überwachung](monitoring.md#topologies).

## <a name="basics-about-monitoring"></a>Grundlagen zur Überwachung
<a name="Basics"> </a>

Eine Sitzung ist ein allgemeiner Begriff für die Verbindung eines Benutzers mit einer:

- Konferenz

- Konferenztool wie Audio/Video oder Anwendungsfreigabe

- Andere Benutzer über eine Peer-zu-Peer-Unterhaltung wie Sofortnachrichten oder Audioanruf

> [!NOTE]
> Skype for Business Server verfolgt Informationen zu den einzelnen Sitzungen: wer wer angerufen hat, welche Endpunkte in der Sitzung verwendet wurden, wie lange die Sitzung zuletzt war, was die wahrgenommene Qualität der Sitzung war usw. Skype for Business Server den tatsächlichen Aufruf selbst nicht aufzeichnen und speichern. Dazu gehören Chatsitzungen: Obwohl Skype for Business Server Informationen zu Chatsitzungen aufzeichnet, wird nicht jede Chatnachricht aufgezeichnet, die während der Sitzung gesendet wurde.

Die grundlegenden Anrufdetailinformationen, die von Skype for Business Server für jede Sitzung gesammelt werden, können für Folgendes verwendet werden:

- **Return on Investment (ROI)** -Analyse. Administratoren können die Nutzungsdaten mit ähnlichen Daten vergleichen, die für ihr vorheriges Telefoniesystem gesammelt wurden, um Kosteneinsparungen anzuzeigen und die Bereitstellung von Skype for Business Server zu rechtfertigen.

- **Gerätebestandsverwaltung**. Informationen zur Ressourcenverwaltung helfen Administratoren dabei, alte Geräte zu identifizieren, die noch verwendet werden, die ersetzt werden müssen, und teure Geräte zu identifizieren, die nicht verwendet oder nicht verwendet werden.

- **Helpdesk**. Die Problembehandlung von Daten hilft Supporttechnikern zu ermitteln, warum der Anruf eines Benutzers fehlgeschlagen ist, ohne server- oder clientseitige Protokolle erfassen zu müssen. Diese Informationen können von Supportmitarbeitern, die nicht über umfassende technische Kenntnisse des Skype for Business-Clients und Skype for Business Server verfügen, leicht zugänglich und verstanden werden.

- **Systemproblembehandlung**. Ermöglicht Administratoren das Erkennen grundlegender Probleme, die u. U. verhindern, dass Endbenutzer einfache Aufgaben wie das Beitreten zu einer Konferenz, das Tätigen eines Anrufs oder das Senden einer Sofortnachricht ausführen können.

Die Überwachung bietet auch einen Mechanismus, mit dem SIP-Endpunkte (z. B. Skype for Business) Informationen zur Problembehandlung bereitstellen können, auf die der Administrator andernfalls keinen Zugriff hätte:

- **Medienmetriken, die sich auf die Qualität auswirken**. Diese Metriken befassen sich mit der tatsächlichen Übertragung des Anrufs selbst. sie bieten eine Art Reisebericht als Anrufweiterleitung über das Netzwerk. Diese Metriken (z. B. Paketverlust, Jitter und Roundtripzeiten) liefern Informationen darüber, was mit dem Anruf passiert ist, von dem Zeitpunkt, an dem er den Endpunkt einer Person verlassen hat, bis zu dem Zeitpunkt, zu dem er am Endpunkt der anderen Person ankam.

- **Probleme, die an den Endbenutzer gemeldet werden**. Diese Metriken umfassen Benachrichtigungen schlechter Qualität, die Skype for Business Endbenutzern in Fällen präsentieren, in denen sie zu weit von einem Mikrofon entfernt sind, zu weich sprechen, über eine schlechte Netzwerkverbindung verfügen oder eine schlechte Qualität aufweisen, da ein anderes Programm auf dem Computer die verfügbaren Ressourcen verbraucht.

- **Umgebungsinformationen**. Diese Metriken erfassen detaillierte Faktoren der Anrufqualität wie den Typ des verwendeten Mikrofons und Lautsprechers, Angaben darüber, ob eine VPN-Verbindung verwendet wurde und Angaben darüber, ob eine WLAN-Verbindung verwendet wurde.

Am Ende jedes Anrufs übertragen SIP-kompatible Endpunkte diese Informationen an den Front-End-Server, der den Anruf erleichtert hat. Sie müssen nichts unternehmen, um Endpunkte zum Übertragen dieser Informationen zu erhalten. Dieses Verhalten ist in das SIP-Protokoll integriert. Wenn Sie diese Informationen jedoch sammeln und speichern möchten, müssen Sie die Überwachung installieren und aktivieren. Wenn Sie die Überwachung installieren und aktivieren, werden Anrufinformationen von Agents gesammelt, die auf dem Front-End-Server ausgeführt werden, und an ein Paar SQL Server Datenbanken weitergeleitet. Der Überwachungsdienst (in Form von "einheitlichen Datensammlungs-Agents") wird mit allen Front-End-Servern verbunden.

## <a name="define-your-requirements-for-monitoring"></a>Definieren der Anforderungen für die Überwachung
<a name="requirements"> </a>

Es gibt noch einige wichtige Probleme, die behoben werden sollten, bevor Sie mit der Installation und Konfiguration der Überwachung mit Skype for Business Server beginnen:

 **Wann möchten Sie die Überwachung installieren?** Die Überwachung kann gleichzeitig installiert und konfiguriert werden, wenn Sie Skype for Business Server installiert und konfiguriert haben. Der Skype for Business Server Bereitstellungs-Assistent bietet Ihnen die Möglichkeit, Ihre Front-End-Pools während des Setups einer Überwachungsdatenbank zuzuordnen. Alternativ können Sie die Überwachung installieren, nachdem Skype for Business Server selbst installiert wurde. Dazu können Sie den Topologie-Generator verwenden, um Ihre Front-End-Pools und -Server einer Überwachungsdatenbank zuzuordnen und dann die überarbeitete Topologie zu veröffentlichen.

Beachten Sie, dass SQL Server installiert und konfiguriert werden müssen, bevor Sie die Überwachung bereitstellen und konfigurieren. Sie müssen jedoch nur SQL Server selbst bereitstellen. Die Überwachungsdatenbanken werden für Sie erstellt, wenn Sie Ihre Skype for Business Server Topologie veröffentlichen.

 **Welche Art von Daten möchten Sie überwachen?** mit Skype for Business Server können Sie zwei allgemeine Arten von Daten überwachen: KDS-Daten (Call Detailing Recording) und QoE-Daten (Quality of Experience). Die Aufzeichnung von Kommunikationsdatensätzen bietet Ihnen die Möglichkeit, die Verwendung Skype for Business Server Features wie VoIP-Telefonanrufe (Voice over IP), Chatnachrichten, Dateiübertragungen, Audio-/Videokonferenzen (A/V) und Anwendungsfreigabesitzungen nachzuverfolgen. Diese Informationen helfen Ihnen zu wissen, welche Skype for Business Server Features verwendet werden (und welche nicht), und sie enthalten auch Informationen darüber, wann diese Features verwendet werden. Mit QoE-Daten können Sie die Qualität von Audio- und Videoanrufen in Ihrer Organisation aufzeichnen, z. B. die Anzahl der verloren gegangenen Netzwerkpakete, Hintergrundgeräusche und die Menge an "Jitter" (Unterschiede bei der Paketverzögerung).

Wenn Sie die Überwachung in Skype for Business Server aktivieren, können Sie sowohl die KDS-Überwachung als auch die QoE-Überwachung aktivieren oder einen Überwachungstyp aktivieren, während der andere Deaktiviert bleibt. Angenommen, Ihre Benutzer verwenden nur Chatnachrichten und Dateiübertragungen und führen keine Audio- oder Videoanrufe aus. In diesem Fall kann es wenig Grund geben, die QoE-Überwachung zu aktivieren. Ebenso erleichtert Skype for Business Server das Aktivieren und Deaktivieren der Überwachung nach der Bereitstellung der Überwachung. Sie können z. B. die Überwachung bereitstellen, die QoE-Überwachung aber zunächst deaktiviert lassen. Wenn bei Ihren Benutzern Probleme mit Audio- oder Videoanrufen auftreten, können Sie die QoE-Überwachung aktivieren und diese Daten verwenden, um diese Probleme zu beheben und zu beheben.

Es gibt keinen besonderen Vorteil (oder Nachteil) bei der Installation der Überwachung zur gleichen Zeit, in der Sie Skype for Business Server installieren, im Vergleich zur Installation der Überwachung, nachdem Skype for Business Server installiert wurde. Beachten Sie, dass Sie vor der Installation der Überwachung einen Computer zum Hosten des Back-End-Überwachungsspeichers auswählen müssen und dass eine unterstützte Version von SQL Server auf diesem Computer installiert und konfiguriert werden muss, bevor dieser Computer für die Überwachung verwendet werden kann. Wenn Sie bereits SQL Server auf einem Computer installiert haben und dieser Computer einsatzbereit ist, können Sie die Überwachung gleichzeitig installieren, während Sie Skype for Business Server installieren. Wenn Sie nicht über einen Back-End-Computer verfügen, können Sie Skype for Business Server selbst installieren und dann die Überwachung installieren, sobald der Back-End-Computer einsatzbereit ist.

 **Wie viele Back-End-Überwachungsdatenbanken benötigen Sie?** Es wurde geschätzt, dass eine verbundenen Datenbank für die Überwachung und Archivierung 240.000 Skype for Business Server Benutzer unterstützen kann). Darüber hinaus kann eine einzelne Überwachungsdatenbank von mehreren Front-End-Pools verwendet werden. Wenn Sie in Ihrer Organisation über drei Front-End-Pools verfügen, können Sie alle drei dieser Pools dem gleichen Back-End-Speicher zuordnen.

Für viele Organisationen ist die Datenbankkapazität nicht der entscheidende Faktor bei der Bestimmung der Anzahl der erforderlichen Back-End-Überwachungsdatenbanken. Vielmehr könnte die Netzwerkgeschwindigkeit ein wichtigerer Faktor sein. Angenommen, es sind drei Front-End-Pools vorhanden, aber einer dieser Pools wird über eine langsame Netzwerkverbindung verwendet. In diesem Fall sollten Sie zwei Überwachungsdatenbanken verwenden: eine Datenbank für die beiden Pools mit der schnellen Netzwerkverbindung, und eine separate Datenbank für den Pool mit der langsameren Netzwerkverbindung.

Außerdem sollten Sie berücksichtigen, dass Skype for Business Server die Verwendung von Spiegeldatenbanken unterstützt. Die "Datenbankspiegelung" bietet die Möglichkeit, zwei Kopien einer Datenbank gleichzeitig zu verwalten, wobei die Datenbanken auf unterschiedlichen Servern gespeichert werden. Immer wenn Daten in eine primäre Datenbank geschrieben werden, werden diese Daten auch in die Spiegeldatenbank geschrieben. Wenn die primäre Datenbank fehlschlagen soll oder anderweitig nicht mehr verfügbar ist, können Sie mithilfe eines einfachen Skype for Business Server PowerShell-Befehls einen Failover auf die Spiegeldatenbank ausführen. Beispiel:

```PowerShell
Invoke-CsDatabaseFailover -PoolFqdn atl-cs-001.litwareinc.com -DatabaseType "Monitoring" -NewPrincipal "Mirror"
```

Dies spielt eine wichtige Rolle für die Planung, da Sie für die Spiegelung die erforderliche Anzahl von Datenbanken verdoppeln müssen. Denn zusätzlich zu jeder primären Datenbank benötigen Sie eine zweite Datenbank als Spiegeldatenbank.

 **Benötigen Ihre Skype for Business Server Websites eigene benutzerdefinierte Überwachungskonfigurationen?** Wenn Sie Skype for Business Server installieren, installieren Sie auch globale Sammlungen von KDS- und QoE-Konfigurationseinstellungen. Mit diesen globalen Auflistungen können Sie die gleichen KDS- und QoE-Einstellungen auf Ihre gesamte Organisation anwenden. In vielen Fällen ist dies ausreichend, denn oft möchten Sie z. B. die KDS-Überwachung für alle Ihre Benutzer aktivieren.

Es kann jedoch auch Vorkommen geben, in denen Sie unterschiedliche Einstellungen auf unterschiedliche Websites anwenden möchten. Vielleicht möchten Sie z. B. die KDS- und QoE-Überwachung am Standort Redmond verwenden, aber nur die KDS-Überwachung an Ihrem Standort in Dublin verwenden. Ebenso können Sie Überwachungsdaten für 60 Tage am Standort Redmond aufbewahren, müssen diese Art von Daten jedoch nur 30 Tage am Standort Dublin aufbewahren. Skype for Business Server ermöglicht ihnen das Erstellen separater Sammlungen von KDS- und QoE-Konfigurationseinstellungen auf Standortebene, sodass Sie jeden Standort unterschiedlich verwalten können. (Dies umfasst sowohl das Aktivieren und Deaktivieren der Überwachung als auch das Konfigurieren von Verwaltungseinstellungen, z. B. wie lange Daten aufbewahrt werden sollen.)

Beachten Sie, dass Sie diese Entscheidung vor oder nach der Bereitstellung der Überwachung treffen können. Beispielsweise können Sie die Überwachung bereitstellen und anschließend die gesamte Organisation mithilfe der globalen Einstellungen verwalten. Falls Sie später Ihre Meinung ändern, können Sie eine separate Sammlung von Einstellungen z. B. für den Standort Redmond erstellen und dann die Überwachung für Redmond mithilfe dieser Einstellungen verwalten. (Einstellungen auf Standortebene haben stets Vorrang vor globalen Einstellungen.) Wenn Sie Ihre Meinung erneut ändern, können Sie einfach die Konfigurationseinstellungen löschen, die auf den Standort Redmond angewendet werden. Wenn eine Sammlung von Standorteinstellungen entfernt wird, wird die globale Sammlung von Einstellungen automatisch auf diesen Standort angewendet.

## <a name="sql-requirements-for-monitoring"></a>SQL Anforderungen für die Überwachung
<a name="topologies"> </a>

Die einheitlichen Datensammlungs-Agents werden automatisch auf jedem Front-End-Server installiert und aktiviert, wenn Sie die Überwachung aktivieren. Unterstützte Versionen von SQL Server und andere Details finden Sie unter [server requirements for Skype for Business Server 2015](requirements-for-your-environment/server-requirements.md)

Überwachungsdaten können eine SQL Server Instanz mit anderen Datentypen teilen. In der Regel verwenden die Datenbank für die Aufzeichnung von Kommunikationsdatensätzen (LcsCdr) und die QoEMetrics-Datenbank (Quality of Experience) dieselbe SQL Instanz. Es ist auch üblich, dass sich die beiden Überwachungsdatenbanken in derselben SQL Instanz wie die Archivierungsdatenbank (LcsLog) befinden. Die einzige echte Anforderung bei SQL Server Instanzen besteht darin, dass eine Instanz von SQL Server auf Folgendes beschränkt ist:

- Eine Instanz der Skype for Business Server 2015-Back-End-Datenbank. (Als allgemeine Regel wird davon abgeraten, die Überwachungsdatenbank in derselben SQL Instanz oder sogar auf demselben Computer wie die Back-End-Datenbank zu verbinden. Obwohl technisch möglich, besteht das Risiko, dass die Überwachungsdatenbank Speicherplatz belegt, der von der Back-End-Datenbank benötigt wird.)

- Eine Instanz der Datenbank für die Aufzeichnung von Kommunikationsdatensätzen.

- Eine Instanz der Quality of Experience-Datenbank.

- Eine Instanz der Archivierungsdatenbank.

Mit anderen Worten: Es können nicht zwei Instanzen der LcsCdr-Datenbank in derselben Instanz von SQL Server vorhanden sein. Wenn Sie mehrere Instanzen der LcsCdr-Datenbank benötigen, müssen Sie mehrere Instanzen von SQL Server konfigurieren.

## <a name="see-also"></a>Siehe auch


[Bereitstellen des Monitoring Servers](/previous-versions/office/lync-server-2013/lync-server-2013-deploying-monitoring)