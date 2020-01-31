---
title: Bereitstellen der Überwachung in Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 244df419-d0a8-4b1d-aedd-a92114172ab6
description: 'Zusammenfassung: Hier erfahren Sie, wie Sie die Überwachung in Skype for Business Server bereitstellen.'
ms.openlocfilehash: c6ccf371d07dfa7d4fbee582a47c7d1306d6c509
ms.sourcegitcommit: 013190ad10cdc02ce02e583961f433d024d5d370
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/31/2020
ms.locfileid: "41634848"
---
# <a name="deploy-monitoring-in-skype-for-business-server"></a>Bereitstellen der Überwachung in Skype for Business Server

**Zusammenfassung:** Hier erfahren Sie, wie Sie die Überwachung in Skype for Business Server bereitstellen.

Überprüfen Sie vor der Durchführung dieser Aufgaben den [Plan für die Überwachung in Skype for Business Server](../../plan-your-deployment/monitoring.md).

Anhand der folgenden beiden Schritte können Sie Überwachungsdienste in Ihrer Topologie implementieren:

1. Aktivieren der Überwachung zur gleichen Zeit, in der Sie einen neuen Skype for Business Server-Pool einrichten. (In Skype for Business Server ist die Überwachung in Pool-by-Pool-Basis aktiviert oder deaktiviert.) Beachten Sie, dass Sie die Überwachung für einen Pool aktivieren können, ohne tatsächlich Überwachungsdaten zu sammeln, was im Abschnitt Konfigurieren der Aufzeichnung von Anrufdetails und der Einstellungen für die Qualität der Benutzerfreundlichkeit dieser Dokumentation erläutert wird.

2. Zuordnen eines Überwachungsspeichers (d. h. einer Überwachungsdatenbank) zum neuen Pool. Ein einzelner Überwachungsspeicher kann mehreren Pools zugeordnet werden. Abhängig von der Anzahl von Benutzern, die in Ihren Registrierungsstellenpools verwaltet werden, bedeutet dies, dass Sie keine separate Überwachungsdatenbank für jeden Pool einrichten müssen. Stattdessen können einzelne Überwachungsspeicher von mehreren Pools verwendet werden.

Zwar ist es oft einfacher, die Überwachung zur gleichen Zeit zu aktivieren, in der Sie einen neuen Pool erstellen, aber es ist auch möglich, einen neuen Pool mit deaktivierter Überwachung zu erstellen. In diesem Fall können Sie später mithilfe des Topologie-Generators den Dienst aktivieren: Topologie-Generator bietet eine Möglichkeit zum Aktivieren oder Deaktivieren der Überwachung für einen Pool oder zum Zuordnen eines Pools zu einem anderen Überwachungsspeicher. Beachten Sie, dass Sie zwar nicht mehr über eine Überwachungs Server Rolle verfügen, aber dennoch mindestens einen Überwachungsspeicher erstellen müssen: Back-End-Datenbanken, die zum Speichern der vom Überwachungsdienst gesammelten Daten verwendet werden. Diese Back-End-Datenbankenkönnen mit Microsoft SQL Server 2008 R2, Microsoft SQL Server 2012, Microsoft SQL Server 2014 oder Microsoft SQL Server 2019 erstellt werden.

> [!NOTE]
> Wenn die Überwachung für einen Pool aktiviert wurde, können Sie den Prozess des Sammelns von Überwachungsdaten deaktivieren, ohne Ihre Topologie ändern zu müssen: Skype for Business Server bietet eine Möglichkeit, die Anruf Detail Aufzeichnung (CDR) oder die Qualität von Experience (QoE)-Datensammlung. Weitere Informationen finden Sie in diesem Dokument im Abschnitt „Konfigurieren von KDS (Aufzeichnung von Kommunikationsdatensätzen)“ und „QoE (Quality of Experience)-Einstellungen“.

Eine weitere wichtige Verbesserung der Überwachung in Skype for Business Server ist die Tatsache, dass Skype for Business Server-Überwachungsberichte nun IPv6 unterstützen: Berichte, die das Feld IP-Adresse verwenden, werden je nach: 1) der SQL-Abfrage entweder IPv4-oder IPv6-Adressen angezeigt. verwendet wird; und 2) Wenn die IPv6-Adresse in der Überwachungsdatenbank gespeichert ist.

> [!NOTE]
> Vergewissern Sie sich, dass der Starttyp des SQL Server-Agent-Diensts „Automatisch“ ist und der SQL Server-Agent-Dienst für die SQL-Instanz mit den Überwachungsdatenbanken ausgeführt wird, damit die SQL Server-Wartungsaufträge für die Standardüberwachung plangemäß unter der Kontrolle des SQL Server-Agent-Diensts ausgeführt werden können.

Diese Dokumentation führt Sie durch den Vorgang zum Installieren und Konfigurieren von Überwachungs-und Überwachungsberichten für Skype for Business Server. Die Dokumentation enthält Schritt-für-Schritt-Anleitungen für Folgendes:

- Aktivieren der Überwachung in Ihrer Topologie und Zuordnen eines Überwachungsspeichers zu einem Front-End-Pool.

- Installieren Sie SQL Server Reporting Services und die Skype for Business Server-Überwachungsberichte. Überwachungsberichte sind vorkonfigurierte Berichte, die verschiedene Einsichten in die in einer Überwachungsdatenbank gespeicherten Informationen bieten.

- Konfigurieren der Aufzeichnung von Kommunikationsdatensätzen (KDS) und der Sammlung von QoE (Quality of Experience)-Daten. Die Anrufdetailaufzeichnung bietet eine Möglichkeit, die Nutzung von Skype for Business Server-Funktionen wie VoIP-Telefon anrufen (Voice over IP) zu nachvollziehen. Instant Messaging (im) Dateiübertragungen; Audio/Video-Konferenzen (A/V); und Anwendungsfreigabesitzungen. QoE-Metriken dienen zur Überwachung der Qualität von Audio- und Videoanrufen in Ihrer Organisation, z. B. der Anzahl der verloren gegangenen Netzwerkpakete, von Hintergrundgeräuschen und der Unterschiede bei der Paketverzögerung (Jitter).

- Manuelles Löschen von KDS und/oder QoE-Datensätzen aus der Überwachungsdatenbank.

## <a name="deployment-checklist-for-monitoring"></a>Prüfliste zur Bereitstellung für die Überwachung

Obwohl die Überwachung auf jedem Front-End-Server bereits installiert und aktiviert ist, müssen Sie noch einige Schritte Unternehmen, bevor Sie tatsächlich Überwachungsdaten für Skype for Business Server erfassen können. Diese Schritte werden in der nachstehenden Prüfliste aufgeführt:

|**Phase**|**Schritte**|**Rolle und Gruppenmitgliedschaft**|**Dokumentation**|
|:-----|:-----|:-----|:-----|
|**Installieren der erforderlichen Hardware und Software** <br/> |Installieren einer unterstützten Version von Microsoft SQL Server auf dem Computer, der als Back-End-Datenspeicher für die Überwachung fungiert.  <br/> |Domänenbenutzer, der auch Mitglied der lokalen Administratorgruppe ist.  <br/> |[Supported Hardware](https://technet.microsoft.com/library/5f9c085d-205e-4235-9061-9ad875283cb0.aspx) <br/> [Server Software and Infrastructure Support](https://technet.microsoft.com/library/4ee5fe38-0191-4710-9aa2-df8895e8c51b.aspx) <br/> |
|**Erstellen der geeigneten internen Topologie zur Unterstützung der Überwachung** <br/> |Verwenden Sie den Skype for Business Server-Topologie-Generator, um der Topologie Überwachungsdatenbanken hinzuzufügen, und veröffentlichen Sie dann die aktualisierte Topologie.  <br/> |Definieren einer Topologie, ein Benutzer, der Mitglied der lokalen Benutzergruppe ist.  <br/> Veröffentlichen der Topologie, ein Benutzer, der Mitglied der Domänenadministratorgruppe und der RTCUniversalServerAdmins-Gruppe ist.  <br/> |[Zuordnen eines überwachungsspeichers zu einem Front-End-Pool in Skype for Business Server](associate-a-monitoring-store.md) <br/> |
|**Aktivieren der entsprechenden Überwachungseinstellungen** <br/> |Aktivieren Sie die Aufzeichnung von Kommunikationsdatensätzen und/oder die QoE-Überwachung (Quality of Experience) auf globaler und/oder auf Standortebene.  <br/> |Ein Benutzer, der Mitglied der RTCUniversalServerAdmins-Gruppe ist oder dem eine RBAC-Rolle mit Zugriff auf das Cmdlet CsCdrConfiguration und auf das Cmdlet CsQoEConfiguration zugewiesen wurde.  <br/> |[Konfigurieren der Aufzeichnung von Anrufdetails und Einstellungen für die Qualität der Benutzerfreundlichkeit in Skype for Business Server](call-detail-recording-and-qoe.md) <br/> |

## <a name="enable-monitoring"></a>Aktivieren der Überwachung

Obwohl die Unified Data Collection-Agents automatisch auf jedem Front-End-Server installiert und aktiviert werden, bedeutet dies nicht, dass Sie automatisch mit der Erfassung von Überwachungsdaten beginnen, sobald Sie die Installation von Skype for Business Server abgeschlossen haben. Stattdessen müssen Sie zwei Schritte vornehmen: Sie müssen Ihre Front-End-Server/Front-End-Pools einer Überwachungsdatenbank zuweisen und die Überwachung der Aufzeichnung von Kommunikationsdatensätzen (KDS) und/oder von QoE (Quality of Experience) auf globaler und/oder Standortebene aktivieren.

Schritt-für-Schritt-Anleitungen zum Zuordnen von Front-End-Servern oder Front-End-Pools zu einer Überwachungsdatenbank finden Sie im Bereitstellungshandbuch im Thema [Zuordnen eines überwachungsspeichers zu einem Front-End-Pool in Skype for Business Server](associate-a-monitoring-store.md) . Nachdem diese Zuordnungen vorgenommen wurden und nachdem Ihre neue Skype for Business Server-Topologie veröffentlicht wurde, können Sie weiterhin keine Überwachungsdaten sammeln. Das liegt daran, dass die Datensammlung für CDR und QoE standardmäßig deaktiviert ist, wenn Sie Skype for Business Server installieren.

Um mit der Datensammlung beginnen zu können, müssen Sie die CDR-und/oder QoE-Überwachung aktivieren. (Beachten Sie, dass Sie nicht sowohl die CDR-als auch die QoE-Überwachung aktivieren müssen; Wenn Sie möchten, können Sie eine Art von Überwachung aktivieren, während der andere Typ deaktiviert bleibt.) Führen Sie in der Skype for Business Server-Verwaltungsshell den folgenden Befehl aus, um die CDR-Überwachung auf globaler Ebene zu aktivieren:

```powershell
Set-CsCdrConfiguration -Identity "global" -EnableCDR $True
```

Alternativ können Sie die CDR-Überwachung über das Skype Control Panel für Unternehmens-Server aktivieren. Führen Sie im Skype for Business Server-Control Panel die folgenden Schritte aus:

1. Klicken Sie auf **Überwachung**.

2. Doppelklicken Sie auf der Registerkarte **Aufzeichnung von Kommunikationsdatensätzen** auf die Einstellung **Global**.

3. Wählen Sie im Bereich **KDS-Einstellungen (Aufzeichnung von Kommunikationsdatensätzen) bearbeiten** die Option **Überwachung von KDS-Aufzeichnungen aktivieren** aus und klicken Sie auf **Commit ausführen**.

Um die QoE-Überwachung im globalen Bereich zu aktivieren, führen Sie diesen Befehl in der Skype for Business Server-Verwaltungsshell aus:

```powershell
Set-CsQoEConfiguration -Identity "global" -EnableQoE $True
```

Wenn Sie möchten, können Sie die QoE-Überwachung auch innerhalb des Skype for Business Server-Control Panels aktivieren. Führen Sie in der Systemsteuerung die folgenden Schritte aus:

1. Klicken Sie auf **Überwachung**.

2. Doppelklicken Sie auf der Registerkarte **Quality of Experience-Daten** auf die Einstellung **Global**.

3. Wählen Sie im Bereich **QoE-Einstellungen (Quality of Experience) bearbeiten** die Option **Überwachung von QoE-Daten aktivieren** aus und klicken Sie dann auf **Commit ausführen**.

Wie bereits erwähnt, ermöglichen die obigen Beispiele die Überwachung auf globaler Ebene; Das bedeutet, dass Sie die CDR-und QoE-Überwachung in Ihrer Organisation aktivieren. Alternativ können Sie separate CDR-und QoE-Konfigurationseinstellungen im Website Bereich erstellen und dann die Überwachung für jede Website selektiv aktivieren oder deaktivieren. So können Sie beispielsweise die CDR-Überwachung für Ihre Redmond-Website aktivieren und dennoch die CDR-Überwachung für Ihre Dublin-Website deaktivieren. Weitere Informationen zum Verwalten der Konfigurationseinstellungen für die Überwachung finden Sie im Bereitstellungshandbuch unter [Konfigurieren der Aufzeichnung von Anrufdetails und Einstellungen für die Qualität der Benutzerfreundlichkeit in Skype for Business Server](call-detail-recording-and-qoe.md).

## <a name="see-also"></a>Siehe auch

[Planen der Überwachung in Skype for Business Server](../../plan-your-deployment/monitoring.md)
