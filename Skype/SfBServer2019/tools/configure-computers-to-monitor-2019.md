---
title: Konfigurieren der zu überwachenden Skype for Business Server Computer
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
description: 'Zusammenfassung: Installieren Sie die Operations Manager-Agent-Dateien auf dem zu überwachenden computer Skype for Business Server 2019, und konfigurieren Sie den Computer als System Center Proxy.'
ms.openlocfilehash: bb8dce9edf44557632fc4e84188606152c76d646
ms.sourcegitcommit: efd56988b22189dface73c156f6f8738f273fa61
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/30/2021
ms.locfileid: "60012179"
---
# <a name="configure-the-skype-for-business-server-computers-to-monitore"></a>Konfigurieren der zu überwachenden Skype for Business Server Computer

**Zusammenfassung:** Installieren Sie die Operations Manager-Agent-Dateien auf dem zu überwachenden computer Skype for Business Server 2019, und konfigurieren Sie den Computer als System Center Proxy.

Jeder Skype for Business Server 2019-Computer, den Sie überwachen möchten, muss in der Lage sein, sein Vorhandensein selbst an den Verwaltungsserver zu melden. Um diesen Prozess zu aktivieren, müssen Sie die Operations Manager-Agent-Dateien auf jedem der zu überwachenden Computer installieren. Nach der Installation der Agentdateien müssen Sie den Computer so konfigurieren, dass er als System Center Proxy fungiert. Stellen Sie sicher, dass Sie Skype for Business Server auf diesen Computern installiert und konfiguriert haben, bevor Sie diese Verfahren ausführen.

## <a name="installing-a-certificate-on-a-watcher-node-located-outside-the-perimeter-network"></a>Installieren eines Zertifikats auf einem Watcher-Knoten, der sich außerhalb des Umkreisnetzwerks befindet
<a name="watcher_node_outside"> </a>

System Center Operations Manager-Agents, die in einem Umkreisnetzwerk (z. B. einem Skype for Business Server Edgeserver), außerhalb des Unternehmens (z. B. einem externen Monitorknoten für synthetische Transaktionen) oder über eine Active Directory-Vertrauensstellungsgrenze ausgeführt werden, erfordern möglicherweise die Konfiguration eines System Center Operations Manager-Gatewayservers. Mit dieser Serverrolle können Agents, die keine Vertrauensstellung mit dem Stammverwaltungsserver haben, Warnungen auslösen. Ausführliche Informationen finden Sie unter [Verwalten von Gatewayservern in Operations Manager 2012.](/previous-versions/system-center/system-center-2012-R2/hh212823(v=sc.12))

Wenn Sie einen Agent an einem dieser Speicherorte bereitstellen, müssen Sie auch ein Zertifikat anfordern und konfigurieren, mit dem der Monitorknoten Warnungen an System Center Operations Manager senden kann. Um dieses Verfahren zu vereinfachen, hat das Operations Manager-Team eine Reihe an Dienstprogrammen erstellt, mit denen Sie den richtigen Typ des Zertifikats anfordern und auf dem Computer mit dem Watcher-Knoten installieren können. Ausführliche Informationen und das Herunterladen dieser Hilfsprogramme finden Sie unter ["Abrufen von Zertifikaten für nicht domänenverbundene Agents, die mit dem Assistenten zum Generieren von Zertifikaten erleichtert wurden".](https://techcommunity.microsoft.com/t5/system-center-blog/obtaining-certificates-for-non-domain-joined-agents-made-easy/ba-p/340467)

### <a name="installing-the-operation-manager-agent-files"></a>Installieren der Operations Manager-Agent-Dateien

1. Doppelklicken Sie auf ihrem System Center Setupmedium auf **Setup.exe**.

2. Klicken Sie im Setup-Assistenten für System Center Operation Manager auf **"Operations Manager-Agent installieren"** aus "Agent installieren" unter "Optionale Installationen".

3. Klicken Sie im Setup-Assistenten System Center auf der Seite "Willkommen bei der System Center Operations Manager-Setup-Assistenten" auf **"Weiter".**

4. Wählen Sie auf der Seite "Zielordner" den Ordner aus, in dem die Operations Manager-Agent-Dateien installiert werden, und klicken Sie auf **"Weiter".**

5. Wählen Sie auf der Seite "Verwaltungsgruppenkonfiguration" die Option **"Verwaltungsgruppeninformationen angeben"** aus, und klicken Sie auf **"Weiter".**

6. Geben Sie auf der Seite "Verwaltungsgruppenkonfiguration" den Namen ihrer Operations Manager-Verwaltungsgruppe in das Feld **"Verwaltungsgruppenname"** ein, und geben Sie dann den Hostnamen des Operations Manager-Servers (z. B. atl-scom-001) in das Feld **"Verwaltungsserver"** ein. Wenn Sie die von Operations Manager verwendete Portnummer geändert haben, geben Sie die neue Portnummer in das Portfeld für den **Verwaltungsserver ein.** Andernfalls behalten Sie den Port bei dem Standardwert 5723 bei, und klicken Sie dann auf **"Weiter".**

7. Wählen Sie auf der Seite "Agent-Aktionskonto" die Option **"Lokales System" aus,** und klicken Sie auf **"Weiter".**

8. Wählen Sie auf der Seite "Microsoft Update" die Option **"Ich möchte Microsoft Update nicht verwenden"** aus, und klicken Sie auf **"Weiter".**

9. Klicken Sie auf der Seite Installationsbereit auf **Installieren**.

10. Klicken Sie auf der Seite Fertigstellen des System Center Operations Manager-Setup-Assistenten auf **Fertig stellen**.

11. Klicken Sie auf **Exit**.

For System Center 2012, you can verify that the agent has been created by clicking **Start**, clicking **All Programs**, clicking System Center Operations **Manager 2012,** and then clicking **Operations 2012 Manager Shell**. Geben Sie im Operations Manager-Shell den folgenden befehl Windows PowerShell ein, und drücken Sie dann die EINGABETASTE:
```PowerShell
Get-SCOMAgent
```

Eine Liste aller Operations Manager-Agents wird angezeigt.
## <a name="configuring-the-skype-for-business-server-computer-to-participate-in-system-center-discovery"></a>Konfigurieren des Skype for Business Server Computers für die Teilnahme an System Center Discovery
<a name="watcher_node_outside"> </a>

Um sicherzustellen, dass der neue Skype for Business Server-Agent am Ermittlungsprozess für System Center Operations Manager teilnimmt, müssen Sie das folgende Verfahren auf jedem Computer ausführen, auf dem die System Center Operations Manager-Konsole installiert wurde:

1. Klicken Sie auf die Registerkarte Verwaltung auf **Mit Agents verwaltet**.

2. Klicken Sie auf den **Ermittlungs-Assistenten,** und schließen Sie den Assistenten ab, damit der Computer ermittelt werden kann.

3. Starten Sie den Integritäts-Agent-Dienst neu. Durch den Neustart des Diensts wird die Ermittlung des neuen Computers erzwungen. Wenn Sie den Dienst nicht neu starten, kann es bis zu vier Stunden dauern, bis der neue Computer von System Center Operations Manager erkannt wird.

4. Stellen Sie sicher, dass im Operations Manager-Ereignisprotokoll keine Fehlerereignisse aufgezeichnet wurden.

5. Der Computer, auf den der Agent erfolgreich übertragen wird, wird unter "Agent Managed" angezeigt, und der Computer, auf dem der Agent manuell installiert wurde, wird unter "Ausstehende Verwaltung" angezeigt, klicken Sie auf den Computernamen, und genehmigen Sie ihn.

6. Klicken Sie mit der rechten Maustaste auf den Namen des Computers, und klicken Sie dann auf **Eigenschaften**. Wählen Sie im Dialogfeld Eigenschaften auf der Registerkarte Sicherheit die Option **Dieser Agent soll als Proxyagent fungieren und verwaltete Objekte auf anderen Computern erkennen** aus, und klicken Sie dann auf **OK**.