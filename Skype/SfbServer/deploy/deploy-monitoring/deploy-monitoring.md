---
title: Bereitstellen der Überwachung in Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 244df419-d0a8-4b1d-aedd-a92114172ab6
description: 'Zusammenfassung: Erfahren Sie, wie Sie die Überwachung in Skype for Business Server bereitstellen.'
ms.openlocfilehash: 89474b7d40a63911c6a79bee719573516a9d423a
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2021
ms.locfileid: "49802275"
---
# <a name="deploy-monitoring-in-skype-for-business-server"></a>Bereitstellen der Überwachung in Skype for Business Server

**Zusammenfassung:** Erfahren Sie, wie Sie die Überwachung in Skype for Business Server bereitstellen.

Lesen Sie vor dem Ausführen dieser Aufgaben [den Plan für die Überwachung in Skype for Business Server.](../../plan-your-deployment/monitoring.md)

In der Regel implementieren Sie Überwachungsdienste in Ihrer Topologie, indem Sie die folgenden beiden Schritte ausführen:

1. Aktivieren der Überwachung beim Einrichten eines neuen Skype for Business Server-Pools. (In Skype for Business Server wird die Überwachung pool für Pool aktiviert oder deaktiviert.) Beachten Sie, dass Sie die Überwachung für einen Pool aktivieren können, ohne tatsächlich Überwachungsdaten zu sammeln. Dies ist ein Prozess, der im Abschnitt "Konfigurieren der Aufzeichnung von Anrufdetails und der Einstellungen für die Erlebnisqualität" dieser Dokumentation erläutert wird.

2. Zuordnen eines Überwachungsspeichers (d. h. einer Überwachungsdatenbank) an den neuen Pool. Ein einzelner Überwachungsspeicher kann mehreren Pools zugeordnet werden. Anhängig von der Anzahl von Benutzern, die in Ihren Registrierungsstellenpools verwaltet werden, bedeutet dies, dass Sie keine separate Überwachungsdatenbank für jeden Pool einrichten müssen. Stattdessen können einzelne Überwachungsspeicher von mehreren Pools verwendet werden.

Obwohl es häufig einfacher ist, die Überwachung gleichzeitig mit dem Erstellen eines neuen Pools zu aktivieren, ist es auch möglich, einen neuen Pool mit deaktivierter Überwachung zu erstellen. Wenn Sie dies tun, können Sie den Dienst später mithilfe des Topologie-Generators aktivieren: Der Topologie-Generator bietet eine Möglichkeit zum Aktivieren oder Deaktivieren der Überwachung für einen Pool oder zum Zuordnen eines Pools zu einem anderen Überwachungsspeicher. Beachten Sie, dass Sie, auch wenn es keine Monitoring Server-Rolle mehr gibt, dennoch einen oder mehrere Überwachungsspeicher erstellen müssen: Back-End-Datenbanken, die zum Speichern der vom Überwachungsdienst gesammelten Daten verwendet werden. Diese Back-End-Datenbanken können mit Microsoft SQL Server 2008 R2, Microsoft SQL Server 2012, Microsoft SQL Server 2014 oder Microsoft SQL Server 2019 erstellt werden.

> [!NOTE]
> Wenn die Überwachung für einen Pool aktiviert wurde, können Sie den Prozess der Erfassung von Überwachungsdaten deaktivieren, ohne Ihre Topologie ändern zu müssen: Skype for Business Server bietet Eine Möglichkeit, die Aufzeichnung von Anrufdetaildaten (Call Detail Recording, CDR) oder QoE (Quality of Experience) zu deaktivieren (und später erneut zu aktivieren). Weitere Informationen finden Sie in diesem Dokument im Abschnitt "Konfigurieren von KDS (Aufzeichnung von Kommunikationsdatensätzen) und QoE (Quality of Experience)-Einstellungen".

Eine weitere wichtige Verbesserung bei der Überwachung in Skype for Business Server ist die Tatsache, dass Skype for Business #A0 jetzt IPv6 unterstützen: Berichte, die das #A1 verwenden, zeigen IPv4- oder #A2 an, abhängig von: 1) der verwendeten SQL-Abfrage; und 2) wo oder nicht die IPv6-Adresse in der Überwachungsdatenbank gespeichert ist.

> [!NOTE]
> Stellen Sie sicher, dass der Starttyp des SQL Server-Agent-Diensts automatisch ist und dass der SQL Server-Agent-Dienst für die SQL-Instanz ausgeführt wird, die die Überwachungsdatenbanken enthält, damit die Standardmäßigen Überwachungs-SQL Server-Wartungsaufträge auf der geplanten Basis unter der Kontrolle des SQL Server-Agent-Diensts ausgeführt werden können.

Diese Dokumentation führt Sie durch den Prozess der Installation und Konfiguration von Überwachungs- und Überwachungsberichten für Skype for Business Server. Die Dokumentation enthält Schritt-für-Schritt-Anleitungen für Folgendes:

- Aktivieren der Überwachung in Ihrer Topologie und Zuordnen eines Überwachungsspeichers zu einem Front-End-Pool.

- Installieren SQL Server Reporting Services und der Skype for Business Server-Überwachungsberichte. Überwachungsberichte sind vorkonfigurierte Berichte, die verschiedene Einsichten in die in einer Überwachungsdatenbank gespeicherten Informationen bieten.

- Konfigurieren der Aufzeichnung von Anrufdetaildaten (Call Detail Recording, CDR) und der QoE (Quality of Experience)-Datensammlung. Mit der Aufzeichnung von Anrufdetails können Sie die Nutzung von Skype for Business #A0 wie Voice over IP (VoIP)-Telefonanrufen nachverfolgen. Chat; Dateiübertragungen; Audio-/Videokonferenzen (A/V); und Anwendungsfreigabesitzungen. QoE-Metriken dienen der Überwachung der Qualität von Audio- und Videoanrufen in Ihrer Organisation, z. B. der Anzahl der verloren gegangenen Netzwerkpakete, von Hintergrundgeräuschen und der Unterschiede bei Paketverzögerung (Jitter).

- Manuelles Löschen von KDS und QoE-Datensätzen aus der Überwachungsdatenbank.

## <a name="deployment-checklist-for-monitoring"></a>Prüfliste für die Bereitstellung für die Überwachung

Obwohl die Überwachung bereits auf jedem Front-End-Server installiert und aktiviert ist, müssen Sie noch einige Schritte ausführen, bevor Sie tatsächlich Überwachungsdaten für Skype for Business Server sammeln können. Diese Schritte werden in der nachstehenden Prüfliste aufgeführt:

|**Phase**|**Schritte**|**Rollen- und Gruppenmitgliedschaft**|**Dokumentation**|
|:-----|:-----|:-----|:-----|
|**Hard- und Softwarevoraussetzungen für die Installation** <br/> |Installieren einer unterstützten Version von Microsoft SQL Server auf dem Computer, der als Back-End-Datenspeicher für die Überwachung fungiert.  <br/> |Domänenbenutzer, der auch Mitglied der lokalen Administratorgruppe ist.  <br/> |[Unterstützte Hardware](https://technet.microsoft.com/library/5f9c085d-205e-4235-9061-9ad875283cb0.aspx) <br/> [Serversoftware- und Infrastrukturunterstützung](https://technet.microsoft.com/library/4ee5fe38-0191-4710-9aa2-df8895e8c51b.aspx) <br/> |
|**Erstellen der geeigneten internen Topologie zur Unterstützung der Archivierung** <br/> |Verwenden Sie den Skype for Business Server-Topologie-Generator, um der Topologie Überwachungsdatenbanken hinzuzufügen und dann die aktualisierte Topologie zu veröffentlichen.  <br/> |Definieren einer Topologie, ein Benutzer, der Mitglied der lokalen Benutzergruppe ist.  <br/> Veröffentlichen der Topologie, ein Benutzer, der Mitglied der Domänenadministratorgruppe und der RTCUniversalServerAdmins-Gruppe ist.  <br/> |[Zuordnen eines Überwachungsspeichers zu einem Front-End-Pool in Skype for Business Server](associate-a-monitoring-store.md) <br/> |
|**Aktivieren der entsprechenden Überwachungseinstellungen** <br/> |Aktivieren Sie die Aufzeichnung von Anrufdetaildaten (Call Detail Recording, CDR) und/oder QoE (Quality of Experience) auf globaler und/oder Standort-Ebene.  <br/> |Ein Benutzer, der Mitglied der RTCUniversalServerAdmins-Gruppe ist oder dem eine RBAC-Rolle mit Zugriff auf das Cmdlet CsCdrConfiguration und auf das Cmdlet CsQoEConfiguration zugewiesen wurde.  <br/> |[Konfigurieren der Aufzeichnung von Anrufdetails und der Einstellungen für die Erlebnisqualität in Skype for Business Server](call-detail-recording-and-qoe.md) <br/> |

## <a name="enable-monitoring"></a>Aktivieren der Überwachung

Obwohl die einheitlichen Datensammlungs-Agents automatisch auf jedem Front-End-Server installiert und aktiviert werden, bedeutet dies nicht, dass Sie automatisch mit der Erfassung von Überwachungsdaten beginnen, sobald Sie die Installation von Skype for Business Server abgeschlossen haben. Stattdessen müssen Sie zwei Dinge tun: Sie müssen Ihre Front-End-Server/Front-End-Pools einer Überwachungsdatenbank zuordnen und die Überwachung der Aufzeichnung von Anrufdetaildaten (Call Detail Recording, CDR) und/oder QoE (Quality of Experience) auf globaler Ebene und/oder auf Standortbasis aktivieren.

Schrittweise Anweisungen zum Zuordnen von Front-End-Servern oder Front-End-Pools zu einer Überwachungsdatenbank finden Sie im Bereitstellungshandbuch unter "Zuordnen eines Überwachungsspeichers zu einem [Front-End-Pool in Skype for Business Server".](associate-a-monitoring-store.md) Nachdem diese Zuordnungen vorgenommen wurden und Ihre neue Skype for Business Server-Topologie veröffentlicht wurde, können Sie weiterhin keine Überwachungsdaten sammeln. Das liegt daran, dass bei der Installation von Skype for Business Server standardmäßig sowohl die Erfassung von CdR- als auch QoE-Daten deaktiviert ist.

Um mit der Datenerfassung zu beginnen, müssen Sie die CdR- und/oder QoE-Überwachung aktivieren. (Beachten Sie, dass Sie nicht sowohl die CdR- als auch die #A0 aktivieren müssen. Wenn es Ihnen lieber ist, können Sie einen Überwachungstyp aktivieren, während der andere deaktiviert ist.) Führen Sie den folgenden Befehl in der Skype for Business Server-Verwaltungsshell aus, um die Überwachung von CdR auf globaler Ebene zu aktivieren:

```powershell
Set-CsCdrConfiguration -Identity "global" -EnableCDR $True
```

Alternativ können Sie die Überwachung der CdR über die Skype for Business Server-Systemsteuerung aktivieren. Führen Sie in der Skype for Business Server-Systemsteuerung das folgende Verfahren aus:

1. Klicken Sie auf **Überwachung**.

2. Doppelklicken Sie auf der Registerkarte **Aufzeichnung von Kommunikationsdatensätzen** auf die Einstellung **Global**.

3. Wählen Sie im Bereich **Einstellung für die Aufzeichnung von Kommunikationsdatensätzen (KDS) bearbeiten** die Option **KDS-Überwachung aktivieren** aus, und klicken Sie auf **Commit**.

Führen Sie diesen Befehl in der Skype for Business Server-Verwaltungsshell aus, um die QoE-Überwachung auf globaler Ebene zu aktivieren:

```powershell
Set-CsQoEConfiguration -Identity "global" -EnableQoE $True
```

Wenn es Ihnen lieber ist, können Sie die QoE-Überwachung auch über die Skype for Business Server-Systemsteuerung aktivieren. Führen Sie in der Systemsteuerung die folgenden Schritte aus:

1. Klicken Sie auf **Überwachung**.

2. Doppelklicken Sie auf der Registerkarte **Quality of Experience-Daten** auf die Einstellung **Global**.

3. Wählen Sie im Bereich **Quality of Experience (QoE)-Einstellung bearbeiten** die Option **Überwachung von QoE-Daten aktivieren** aus, und klicken Sie dann auf **Commit**.

Wie bereits erwähnt, ermöglichen die vorstehenden Beispiele die Überwachung auf globaler Ebene. Das heißt, sie ermöglichen die CdR- und QoE-Überwachung in Ihrer gesamten Organisation. Alternativ können Sie separate CdR- und QoE-Konfigurationseinstellungen auf Standortbereich erstellen und dann die Überwachung für jeden Standort selektiv aktivieren oder deaktivieren. Sie können z. B. die Überwachung der CdR für Ihren Standort "Redmond" aktivieren und die Überwachung der CdR für Den Standort Dublin deaktivieren. Weitere Informationen zum Verwalten ihrer Überwachungskonfigurationseinstellungen finden Sie im Bereitstellungshandbuch zum Konfigurieren der Aufzeichnung von Anrufdetails und der Einstellungen für die Erlebnisqualität [in Skype for Business Server.](call-detail-recording-and-qoe.md)

## <a name="see-also"></a>Weitere Informationen

[Planen der Überwachung in Skype for Business Server](../../plan-your-deployment/monitoring.md)
