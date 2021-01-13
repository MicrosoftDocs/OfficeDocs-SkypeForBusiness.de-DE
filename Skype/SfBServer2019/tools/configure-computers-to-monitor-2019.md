---
title: Konfigurieren der Skype for Business Server-Computer, die überwacht werden
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
localization_priority: Normal
ms.collection: IT_Skype16
description: 'Zusammenfassung: Installieren Sie die Operations Manager-Agent-Dateien auf dem zu überwachenden Computer mit Skype for Business Server 2019, und konfigurieren Sie den Computer als System Center-Proxy.'
ms.openlocfilehash: 08328e430acd4fa651fccd89b827d5c103066dd1
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2021
ms.locfileid: "49806075"
---
# <a name="configure-the-skype-for-business-server-computers-that-will-be-monitored"></a>Konfigurieren der Skype for Business Server-Computer, die überwacht werden

**Zusammenfassung:** Installieren Sie die Operations Manager-Agent-Dateien auf dem zu überwachenden Computer mit Skype for Business Server 2019, und konfigurieren Sie den Computer als System Center-Proxy.

Jeder Skype for Business Server 2019-Computer, den Sie überwachen möchten, muss in der Lage sein, seine Existenz selbst an den Verwaltungsserver zu melden. Um diesen Prozess zu aktivieren, müssen Sie die Operations Manager-Agent-Dateien auf jedem zu überwachenden Computer installieren. Nach der Installation der Agentdateien müssen Sie den Computer als System Center-Proxy konfigurieren. Stellen Sie sicher, dass Sie Skype for Business Server zuerst auf diesen Computern installiert und konfiguriert haben, bevor Sie diese Verfahren durchführen.

## <a name="installing-a-certificate-on-a-watcher-node-located-outside-the-perimeter-network"></a>Installieren eines Zertifikats auf einem Watcher-Knoten, der sich außerhalb des Umkreisnetzwerks befindet
<a name="watcher_node_outside"> </a>

Für System Center Operations Manager-Agents, die in einem Umkreisnetzwerk (z. B. einem Skype for Business Server-Edgeserver), außerhalb des Unternehmens (z. B. einem externen Knoten für synthetische Transaktionen) oder über eine Active Directory-Vertrauensstellungsgrenze ausgeführt werden, muss möglicherweise ein System Center Operations Manager Gateway Server konfiguriert werden. Diese Serverrolle ermöglicht Agents, die keine Vertrauensstellung mit dem Stammverwaltungsserver haben, das Auslösen von Warnungen. Weitere Informationen finden Sie [unter Managing Gateway Servers in Operations Manager 2012](https://technet.microsoft.com/library/hh212823.aspx).

Wenn Sie einen Agent an einem dieser Speicherorte bereitstellen, müssen Sie auch ein Zertifikat anfordern und konfigurieren, das es dem Watcherknoten ermöglicht, Warnungen an System Center Operations Manager zu senden. Um dieses Verfahren zu vereinfachen, hat das Operations Manager-Team eine Reihe an Dienstprogrammen erstellt, mit denen Sie den richtigen Typ des Zertifikats anfordern und auf dem Computer mit dem Watcher-Knoten installieren können. Weitere Informationen und informationen zum Herunterladen dieser Dienstprogramme finden Sie unter Abrufen von Zertifikaten für [Nicht-Domänen-beigetretene Agents, die](https://go.microsoft.com/fwlink/p/?LinkID=267421&amp;amp;clcid=0x409)mit dem Assistenten zum Erstellen von Zertifikaten einfach gemacht werden.

### <a name="installing-the-operation-manager-agent-files"></a>Installieren der Operations Manager-Agent-Dateien

1. Doppelklicken Sie auf dem System Center-Setupmedium auf **Setup.exe**.

2. Klicken Sie im Setup-Assistenten für System Center Operation Manager im Installations-Agent unter "Optionale Installationen" auf "Operations **Manager-Agent** installieren".

3. Klicken Sie im System Center-Setup-Assistenten auf der Seite "Willkommen beim System Center Operations Manager-Setup-Assistenten" auf **"Weiter".**

4. Wählen Sie auf der Seite "Zielordner" den Ordner aus, in dem die Operations Manager -Agent-Dateien installiert werden sollen, und klicken Sie auf **"Weiter".**

5. Wählen Sie auf der Seite "Verwaltungsgruppenkonfiguration" die Option **"Verwaltungsgruppeninformationen angeben"** aus, und klicken Sie auf **"Weiter".**

6. Geben Sie auf der Seite "Verwaltungsgruppenkonfiguration" im  Feld "Verwaltungsgruppenname" den Namen Ihrer Operations Manager-Verwaltungsgruppe ein, und geben Sie dann den Hostnamen Ihres Operations Manager-Servers (z. B. "atl-scom-001") in das Feld **"Verwaltungsserver"** ein. Wenn Sie die von Operations Manager verwendete Portnummer geändert haben, geben Sie die neue Portnummer in das Feld **"Verwaltungsserverport"** ein. Lassen Sie den Port andernfalls auf den Standardwert 5723, und klicken Sie dann auf **Weiter**.

7. Wählen Sie auf der Seite "Agentaktionskonto" die Option **"Lokales System" aus, und** klicken Sie auf **"Weiter".**

8. Wählen Sie auf der Seite "Microsoft Update" die Option "Ich möchte Microsoft Update nicht **verwenden" aus,** und klicken Sie auf **"Weiter".**

9. Klicken Sie auf der Seite Installationsbereit auf **Installieren**.

10. Klicken Sie auf der Seite Fertigstellen des System Center Operations Manager-Setup-Assistenten auf **Fertig stellen**.

11. Klicken Sie auf **Exit**.

Für System Center 2012 können Sie überprüfen, ob der Agent erstellt wurde, indem Sie auf **"Start",**"Alle Programme", **"System Center Operations Manager 2012"** und dann auf **"Operations 2012-Manager-Shell"** klicken. Geben Sie in der Operations Manager Shell den folgenden Befehl Windows PowerShell ein, und drücken Sie dann die EINGABETASTE:
```PowerShell
Get-SCOMAgent
```

Eine Liste aller Operations Manager-Agents wird angezeigt.
## <a name="configuring-the-skype-for-business-server-computer-to-participate-in-system-center-discovery"></a>Konfigurieren des Skype for Business Server-Computers für die Teilnahme an System Center Discovery
<a name="watcher_node_outside"> </a>

Um sicherzustellen, dass Ihr neuer Skype for Business Server-Agent am Ermittlungsprozess für System Center Operations Manager beteiligt ist, müssen Sie auf jedem Computer, auf dem die System Center Operations Manager-Konsole installiert wurde, das folgende Verfahren abschließen:

1. Klicken Sie auf die Registerkarte Verwaltung auf **Mit Agents verwaltet**.

2. Klicken Sie auf **den Discovery-Assistenten,** und schließen Sie den Assistenten ab, damit der Computer ermittelt werden kann.

3. Starten Sie den Integritäts-Agent-Dienst neu. Durch einen Neustart des Diensts wird die Ermittlung des neuen Computers erzwingen. Wenn Sie den Dienst nicht neu starten, kann es bis zu vier Stunden dauern, bis der neue Computer von System Center Operations Manager erkannt wird.

4. Stellen Sie sicher, dass im Operations Manager-Ereignisprotokoll keine Fehlerereignisse aufgezeichnet wurden.

5. Der Computer, auf dem der Agent erfolgreich per Push übertragen wird, wird unter "Agent Managed" angezeigt, und der Computer, auf dem der Agent manuell installiert wurde, wird unter "Ausstehende Verwaltung" angezeigt, auf den Computernamen klicken und genehmigen.

6. Klicken Sie mit der rechten Maustaste auf den Namen des Computers, und klicken Sie dann auf **Eigenschaften**. Wählen Sie im Dialogfeld Eigenschaften auf der Registerkarte Sicherheit die Option **Dieser Agent soll als Proxyagent fungieren und verwaltete Objekte auf anderen Computern erkennen** aus, und klicken Sie dann auf **OK**.


