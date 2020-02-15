---
title: Konfigurieren der Skype for Business Server Computer, die überwacht werden sollen
ms.reviewer: ''
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 11/7/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
description: 'Zusammenfassung: Installieren Sie die Operations Manager-Agentdateien auf dem Skype for Business Server 2019-Computer, der überwacht werden soll, und konfigurieren Sie den Computer als System Center-Proxy.'
ms.openlocfilehash: d62a58b82dbafe230a33339bb6aaa645543b501a
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/14/2020
ms.locfileid: "42006030"
---
# <a name="configure-the-skype-for-business-server-computers-that-will-be-monitored"></a>Konfigurieren der Skype for Business Server Computer, die überwacht werden sollen

**Zusammenfassung:** Installieren Sie die Operations Manager-Agentdateien auf dem Skype for Business Server 2019-Computer, der überwacht werden soll, und konfigurieren Sie den Computer als System Center-Proxy.

Jeder Skype for Business Server 2019-Computer, den Sie überwachen möchten, muss seine Existenz dem Verwaltungs Server selbst melden können. Um diesen Prozess zu aktivieren, müssen Sie die Operations Manager-Agent-Dateien auf jedem Computer installieren, der überwacht werden soll. Nachdem Sie die Agentdateien installiert haben, müssen Sie den Computer so konfigurieren, dass er als System Center-Proxy fungiert. Stellen Sie sicher, dass Sie zuerst Skype for Business Server auf diesen Computern installiert und konfiguriert haben, bevor Sie diese Verfahren ausführen.

## <a name="installing-a-certificate-on-a-watcher-node-located-outside-the-perimeter-network"></a>Installieren eines Zertifikats auf einem Watcher-Knoten, der sich außerhalb des Umkreisnetzwerks befindet
<a name="watcher_node_outside"> </a>

System Center Operations Manager-Agents, die in einem Umkreisnetzwerk ausgeführt werden (beispielsweise eine Skype for Business Server Edgeserver) außerhalb des Unternehmens (beispielsweise ein externer synthetischer Transaktionsmonitor Knoten) oder über eine Active Directory Vertrauensgrenze hinaus, erfordern möglicherweise die Konfiguration eines System Center Operations Manager-Gatewayservers. Diese Serverrolle ermöglicht Agents, die nicht über eine Vertrauensstellung mit dem Stammverwaltungsserver verfügen, Warnungen auszulösen. Ausführliche Informationen finden Sie unter [Managing Gateway Servers in Operations Manager 2012](https://technet.microsoft.com/library/hh212823.aspx).

Wenn Sie einen Agent an einem dieser Speicherorte bereitstellen, müssen Sie außerdem ein Zertifikat anfordern und konfigurieren, mit dem der Watcher-Knoten Warnungen an System Center Operations Manager senden kann. Um dieses Verfahren zu vereinfachen, hat das Operations Manager-Team eine Reihe an Dienstprogrammen erstellt, mit denen Sie den richtigen Typ des Zertifikats anfordern und auf dem Computer mit dem Watcher-Knoten installieren können. Ausführliche Informationen zum Herunterladen dieser Dienstprogramme finden Sie unter [Abrufen von Zertifikaten für nicht der Domäne beigefügte Agents, die mit dem Assistenten zum Generieren von Zertifikaten vereinfacht wurden](https://go.microsoft.com/fwlink/p/?LinkID=267421&amp;amp;clcid=0x409).

### <a name="installing-the-operation-manager-agent-files"></a>Installieren der Operations Manager-Agent-Dateien

1. Doppelklicken Sie auf den System Center-Setupmedien auf **Setup. exe**.

2. Klicken Sie im System Center Operations Manager-Setup-Assistenten im Installations-Agent unter Optionale Installationen auf **Operations Manager-Agent installieren**.

3. Klicken Sie im System Center-Setup-Assistenten auf der Seite Willkommen bei System Center Operations Manager-Setup-Assistenten auf **weiter**.

4. Wählen Sie auf der Seite Zielordner den Ordner aus, in dem die Operations Manager-Agent-Dateien installiert werden sollen, und klicken Sie auf **weiter**.

5. Wählen Sie auf der Seite Verwaltungsgruppenkonfiguration die Option **Verwaltungsgruppeninformationen angeben** aus, und klicken Sie auf **weiter**.

6. Geben Sie auf der Seite Verwaltungsgruppenkonfiguration in das Feld **Verwaltungsgruppenname** den Namen Ihrer Operations Manager-Verwaltungsgruppe ein, und geben Sie dann den Hostnamen Ihres Operations Manager-Servers (beispielsweise ATL-SCOM-001) in das Feld **Verwaltungsserver** ein. Wenn Sie die Portnummer geändert haben, die von Operations Manager verwendet wurde, geben Sie die neue Portnummer in das Feld **Verwaltungs Server Port** ein. Lassen Sie andernfalls den Port mit dem Standardwert 5723, und klicken Sie dann auf **weiter**.

7. Wählen Sie auf der Seite Agent-Aktionskonto die Option **Lokales System** aus, und klicken Sie auf **weiter**.

8. Wählen Sie auf der Seite Microsoft Update die Option **Ich möchte Microsoft Update nicht verwenden** aus, und klicken Sie auf **weiter**.

9. Klicken Sie auf der Seite Installationsbereit auf **Installieren**.

10. Klicken Sie auf der Seite Fertigstellen des System Center Operations Manager-Setup-Assistenten auf **Fertig stellen**.

11. Klicken Sie auf **Exit**.

Für System Center 2012 können Sie überprüfen, ob der Agent erstellt wurde, indem Sie auf **Start**, auf **Alle Programme**, auf **System Center Operations Manager 2012**und dann auf **Operations 2012 Manager Shell**klicken. Geben Sie in der Operations Manager-Shell den folgenden Windows PowerShell Befehl ein, und drücken Sie dann die EINGABETASTE:
```PowerShell
Get-SCOMAgent
```

Eine Liste aller Operations Manager-Agents wird angezeigt.
## <a name="configuring-the-skype-for-business-server-computer-to-participate-in-system-center-discovery"></a>Konfigurieren des Skype for Business Server Computers für die Teilnahme an der System Center-Ermittlung
<a name="watcher_node_outside"> </a>

Um sicherzustellen, dass Ihr neuer Skype for Business Server-Agent am Ermittlungsprozess für System Center Operations Manager teilnimmt, müssen Sie auf jedem Computer, auf dem die System Center Operations Manager-Konsole installiert ist, das folgende Verfahren ausführen:

1. Klicken Sie auf die Registerkarte Verwaltung auf **Mit Agents verwaltet**.

2. Klicken Sie auf **Discovery Wizard** , und schließen Sie den Assistenten für den Computer ab, der ermittelt werden soll.

3. Starten Sie den Integritäts-Agent-Dienst neu. Durch einen Neustart des Diensts wird die Ermittlung des neuen Computers erzwungen. Wenn Sie den Dienst nicht neu starten, kann es bis zu 4 Stunden dauern, bis der neue Computer von System Center Operations Manager erkannt wird.

4. Stellen Sie sicher, dass im Ereignisprotokoll von Operations Manager keine Fehlerereignisse aufgezeichnet wurden.

5. Der Computer, auf dem der Agent erfolgreich abgelegt wird, wird unter "Agent Managed" angezeigt, und der Computer, auf dem Agent manuell installiert wurde, wird unter "Ausstehende Verwaltung" angezeigt, klicken Sie auf den Computernamen und genehmigen.

6. Klicken Sie mit der rechten Maustaste auf den Namen des Computers, und klicken Sie dann auf **Eigenschaften**. Wählen Sie im Dialogfeld Eigenschaften auf der Registerkarte Sicherheit die Option **Dieser Agent soll als Proxyagent fungieren und verwaltete Objekte auf anderen Computern erkennen** aus, und klicken Sie dann auf **OK**.


