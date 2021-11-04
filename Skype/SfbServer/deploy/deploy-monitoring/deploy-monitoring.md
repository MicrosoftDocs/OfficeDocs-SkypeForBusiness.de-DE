---
title: Bereitstellen der Überwachung in Skype for Business Server
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 244df419-d0a8-4b1d-aedd-a92114172ab6
description: 'Zusammenfassung: Erfahren Sie, wie Sie die Überwachung in Skype for Business Server bereitstellen.'
ms.openlocfilehash: cbb5fe0974e1b02ce5be472ba91d01221fb7df82
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/04/2021
ms.locfileid: "60764843"
---
# <a name="deploy-monitoring-in-skype-for-business-server"></a>Bereitstellen der Überwachung in Skype for Business Server

**Zusammenfassung:** Erfahren Sie, wie Sie die Überwachung in Skype for Business Server bereitstellen.

Bevor Sie diese Aufgaben ausführen, überprüfen Sie den [Plan für die Überwachung in Skype for Business Server.](../../plan-your-deployment/monitoring.md)

In der Regel implementieren Sie Überwachungsdienste in Ihrer Topologie, indem Sie die folgenden beiden Schritte ausführen:

1. Wenn Sie die Überwachung gleichzeitig aktivieren, richten Sie einen neuen Skype for Business Server-Pool ein. (In Skype for Business Server ist die Überwachung auf Pool-zu-Pool-Basis aktiviert oder deaktiviert.) Beachten Sie, dass Sie die Überwachung für einen Pool aktivieren können, ohne überwachungsdaten erfassen zu müssen. Ein Prozess, der im Abschnitt "Konfigurieren der Aufzeichnung von Kommunikationsdatensätzen und der Erlebnisqualität" Einstellungen Abschnitt dieser Dokumentation erläutert wird.

2. Zuordnen eines Überwachungsspeichers (d. h. einer Überwachungsdatenbank) an den neuen Pool. Ein einzelner Überwachungsspeicher kann mehreren Pools zugeordnet werden. Anhängig von der Anzahl von Benutzern, die in Ihren Registrierungsstellenpools verwaltet werden, bedeutet dies, dass Sie keine separate Überwachungsdatenbank für jeden Pool einrichten müssen. Stattdessen können einzelne Überwachungsspeicher von mehreren Pools verwendet werden.

Obwohl es oft einfacher ist, die Überwachung gleichzeitig mit der Erstellung eines neuen Pools zu aktivieren, ist es auch möglich, einen neuen Pool mit deaktivierter Überwachung zu erstellen. In diesem Fall können Sie später den Topologie-Generator verwenden, um den Dienst zu aktivieren: Der Topologie-Generator bietet eine Möglichkeit, die Überwachung für einen Pool zu aktivieren oder zu deaktivieren oder einen Pool einem anderen Überwachungsspeicher zuzuordnen. Bedenken Sie, dass Sie auch dann, wenn keine Monitoring Server-Rolle mehr vorhanden ist, einen oder mehrere Überwachungsspeicher erstellen müssen: Back-End-Datenbanken, die zum Speichern der vom Überwachungsdienst gesammelten Daten verwendet werden. Diese Back-End-Datenbanken können mit Microsoft SQL Server 2008 R2, Microsoft SQL Server 2012, Microsoft SQL Server 2014 oder Microsoft SQL Server 2019 erstellt werden.

> [!NOTE]
> Wenn die Überwachung für einen Pool aktiviert wurde, können Sie den Prozess der Erfassung von Überwachungsdaten deaktivieren, ohne ihre Topologie ändern zu müssen: Skype for Business Server bietet Ihnen die Möglichkeit, die Aufzeichnung von Kommunikationsdatensätzen (KDS) oder QoE-Daten (Quality of Experience) zu deaktivieren (und später erneut zu aktivieren). Weitere Informationen finden Sie in diesem Dokument im Abschnitt "Konfigurieren von KDS (Aufzeichnung von Kommunikationsdatensätzen) und QoE (Quality of Experience)-Einstellungen".

Eine weitere wichtige Verbesserung der Überwachung in Skype for Business Server ist die Tatsache, dass Skype for Business Server Überwachungsberichte jetzt IPv6 unterstützen: Berichte, die das FELD "IP-Adresse" verwenden, zeigen IPv4- oder IPv6-Adressen abhängig von : 1) die verwendete SQL Abfrage an. und, 2) wobei die IPv6-Adresse in der Überwachungsdatenbank gespeichert ist.

> [!NOTE]
> Stellen Sie sicher, dass der SQL Server Agent-Dienst-Starttyp automatisch ist und der SQL Server Agent-Dienst für die SQL Instanz ausgeführt wird, die die Überwachungsdatenbanken speichert, damit die Standardmäßige Überwachung SQL Server Wartungsaufträge unter der Kontrolle des SQL Server Agent-Diensts auf der geplanten Basis ausgeführt werden kann.

Diese Dokumentation führt Sie durch den Prozess der Installation und Konfiguration von Überwachungs- und Überwachungsberichten für Skype for Business Server. Die Dokumentation enthält Schritt-für-Schritt-Anleitungen für Folgendes:

- Aktivieren der Überwachung in Ihrer Topologie und Zuordnen eines Überwachungsspeichers zu einem Front-End-Pool.

- Installieren Sie SQL Server Reporting Services und die Skype for Business Server Überwachungsberichte. Überwachungsberichte sind vorkonfigurierte Berichte, die verschiedene Einsichten in die in einer Überwachungsdatenbank gespeicherten Informationen bieten.

- Konfigurieren sie die Datensammlung für die Aufzeichnung von Kommunikationsdatensätzen (KDS) und QoE (Quality of Experience). Die Aufzeichnung von Kommunikationsdatensätzen bietet Ihnen die Möglichkeit, die Nutzung von Skype for Business Server Funktionen wie VoIP-Telefonanrufen (Voice over IP) nachzuverfolgen. Chatnachrichten; Dateiübertragungen; Audio-/Videokonferenzen (A/V); und Anwendungsfreigabesitzungen. QoE-Metriken dienen der Überwachung der Qualität von Audio- und Videoanrufen in Ihrer Organisation, z. B. der Anzahl der verloren gegangenen Netzwerkpakete, von Hintergrundgeräuschen und der Unterschiede bei Paketverzögerung (Jitter).

- Manuelles Löschen von KDS und QoE-Datensätzen aus der Überwachungsdatenbank.

## <a name="deployment-checklist-for-monitoring"></a>Prüfliste für die Bereitstellung für die Überwachung

Obwohl die Überwachung bereits auf jedem Front-End-Server installiert und aktiviert ist, müssen Sie noch mehrere Schritte ausführen, bevor Sie überwachungsdaten für Skype for Business Server sammeln können. Diese Schritte werden in der nachstehenden Prüfliste aufgeführt:

|**Phase**|**Schritte**|**Rollen- und Gruppenmitgliedschaft**|**Dokumentation**|
|:-----|:-----|:-----|:-----|
|**Hard- und Softwarevoraussetzungen für die Installation** <br/> |Installieren einer unterstützten Version von Microsoft SQL Server auf dem Computer, der als Back-End-Datenspeicher für die Überwachung fungiert.  <br/> |Domänenbenutzer, der auch Mitglied der lokalen Administratorgruppe ist.  <br/> |[Unterstützte Hardware](/previous-versions/office/lync-server-2013/lync-server-2013-supported-hardware) <br/> [Serversoftware- und Infrastrukturunterstützung](/previous-versions/office/lync-server-2013/lync-server-2013-server-software-and-infrastructure-support) <br/> |
|**Erstellen der geeigneten internen Topologie zur Unterstützung der Archivierung** <br/> |Verwenden Sie Skype for Business Server Topologie-Generator, um der Topologie Überwachungsdatenbanken hinzuzufügen und dann die aktualisierte Topologie zu veröffentlichen.  <br/> |Definieren einer Topologie, ein Benutzer, der Mitglied der lokalen Benutzergruppe ist.  <br/> Veröffentlichen der Topologie, ein Benutzer, der Mitglied der Domänenadministratorgruppe und der RTCUniversalServerAdmins-Gruppe ist.  <br/> |[Zuordnen eines Überwachungsspeichers zu einem Front-End-Pool in Skype for Business Server](associate-a-monitoring-store.md) <br/> |
|**Aktivieren der entsprechenden Überwachungseinstellungen** <br/> |Aktivieren Sie die Überwachung der Aufzeichnung von Kommunikationsdatensätzen (KDS) und/oder QoE (Quality of Experience) auf globaler und/oder Standortebene.  <br/> |Ein Benutzer, der Mitglied der RTCUniversalServerAdmins-Gruppe ist oder dem eine RBAC-Rolle mit Zugriff auf das Cmdlet CsCdrConfiguration und auf das Cmdlet CsQoEConfiguration zugewiesen wurde.  <br/> |[Konfigurieren der Einstellungen für die Aufzeichnung von Kommunikationsdatensätzen und die Quality of Experience in Skype for Business Server](call-detail-recording-and-qoe.md) <br/> |

## <a name="enable-monitoring"></a>Aktivieren der Überwachung

Obwohl die einheitlichen Datensammlungs-Agents automatisch auf jedem Front-End-Server installiert und aktiviert werden, bedeutet dies nicht, dass Sie automatisch mit der Erfassung von Überwachungsdaten beginnen, sobald Sie die Installation Skype for Business Server abgeschlossen haben. Stattdessen müssen Sie zwei Dinge tun: Sie müssen Ihre Front-End-Server/Front-End-Pools einer Überwachungsdatenbank zuordnen, und Sie müssen die KDS-Überwachung (Call Detail Recording) und/oder QoE-Überwachung (Quality of Experience) auf globaler Ebene und/oder auf Standortebene aktivieren.

Schrittweise Anleitungen zum Zuordnen von Front-End-Servern oder Front-End-Pools zu einer Überwachungsdatenbank finden Sie im Thema ["Zuordnen eines Überwachungsspeichers zu einem Front-End-Pool in Skype for Business Server"](associate-a-monitoring-store.md) im Bereitstellungshandbuch. Nachdem diese Zuordnungen vorgenommen wurden und ihre neue Skype for Business Server Topologie veröffentlicht wurde, können Sie weiterhin keine Überwachungsdaten sammeln. Der Grund dafür ist, dass bei der Installation von Skype for Business Server standardmäßig sowohl die KDS- als auch die QoE-Datensammlung deaktiviert ist.

Um mit der Datensammlung zu beginnen, müssen Sie die KDS- und/oder QoE-Überwachung aktivieren. (Beachten Sie, dass Sie nicht sowohl die KDS- als auch die QoE-Überwachung aktivieren müssen. Wenn Sie möchten, können Sie einen Überwachungstyp aktivieren, während der andere Typ deaktiviert bleibt.) Führen Sie den folgenden Befehl in der Skype for Business Server Verwaltungsshell aus, um die KDS-Überwachung auf globaler Ebene zu aktivieren:

```powershell
Set-CsCdrConfiguration -Identity "global" -EnableCDR $True
```

Alternativ können Sie die KDS-Überwachung in der Skype for Business Server Systemsteuerung aktivieren. Führen Sie in der Skype for Business Server Systemsteuerung das folgende Verfahren aus:

1. Klicken Sie auf **Überwachung**.

2. Doppelklicken Sie auf der Registerkarte **Aufzeichnung von Kommunikationsdatensätzen** auf die Einstellung **Global**.

3. Wählen Sie im Bereich **Einstellung für die Aufzeichnung von Kommunikationsdatensätzen (KDS) bearbeiten** die Option **KDS-Überwachung aktivieren** aus, und klicken Sie auf **Commit**.

Um die QoE-Überwachung auf globaler Ebene zu aktivieren, führen Sie diesen Befehl in der Skype for Business Server Verwaltungsshell aus:

```powershell
Set-CsQoEConfiguration -Identity "global" -EnableQoE $True
```

Wenn Sie möchten, können Sie die QoE-Überwachung auch in der Skype for Business Server Systemsteuerung aktivieren. Führen Sie in der Systemsteuerung die folgenden Schritte aus:

1. Klicken Sie auf **Überwachung**.

2. Doppelklicken Sie auf der Registerkarte **Quality of Experience-Daten** auf die Einstellung **Global**.

3. Wählen Sie im Bereich **Quality of Experience (QoE)-Einstellung bearbeiten** die Option **Überwachung von QoE-Daten aktivieren** aus, und klicken Sie dann auf **Commit**.

Wie bereits erwähnt, ermöglichen die vorherigen Beispiele die Überwachung auf globaler Ebene. d. h., sie ermöglichen die KDS- und QoE-Überwachung in Ihrer gesamten Organisation. Alternativ können Sie separate KDS- und QoE-Konfigurationseinstellungen auf Standortebene erstellen und dann die Überwachung für jeden Standort selektiv aktivieren oder deaktivieren. Sie können z. B. die KDS-Überwachung für Ihren Standort Redmond aktivieren, die KDS-Überwachung für Ihren Standort Dublin jedoch deaktivieren. Weitere Informationen zum Verwalten ihrer Überwachungskonfigurationseinstellungen finden Sie im Bereitstellungshandbuch zum Konfigurieren der Einstellungen für [die Aufzeichnung von Kommunikationsdatensätzen und der QoE-Erfahrung in Skype for Business Server.](call-detail-recording-and-qoe.md)

## <a name="see-also"></a>Weitere Informationen

[Planen der Überwachung in Skype for Business Server](../../plan-your-deployment/monitoring.md)