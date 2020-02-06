---
title: Konfigurieren von Skype for Business Server-Computern, die überwacht werden sollen
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: b24ea184-4b3e-4277-a244-157afb4b368b
description: 'Zusammenfassung: Installieren Sie die Operations Manager-Agentdateien auf dem Skype for Business Server 2015-Computer, die überwacht werden sollen, und konfigurieren Sie den Computer so, dass er als System Center-Proxy fungiert.'
ms.openlocfilehash: f5da9d309fd2353fbfd4009b825b731074c81fbb
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2020
ms.locfileid: "41816134"
---
# <a name="configure-the-skype-for-business-server-computers-that-will-be-monitored"></a>Konfigurieren von Skype for Business Server-Computern, die überwacht werden sollen

**Zusammenfassung:** Installieren Sie die Operations Manager-Agentdateien auf dem Skype for Business Server 2015-Computer, die überwacht werden sollen, und konfigurieren Sie den Computer so, dass er als System Center-Proxy fungiert.

Jeder Skype for Business Server 2015-Computer, den Sie überwachen möchten, muss in der Lage sein, seine Existenz dem Verwaltungs Server selbst zu melden. Um dies zu ermöglichen, müssen Sie die Operations Manager-Agent-Dateien auf allen zu überwachenden Computern installieren. Nach dem Installieren der Agent-Dateien müssen Sie die Computer für die Funktion als System Center-Proxy konfigurieren. Stellen Sie sicher, dass Sie Skype for Business Server zuerst auf diesen Computern installiert und konfiguriert haben, bevor Sie diese Schritte ausführen.

## <a name="installing-a-certificate-on-a-watcher-node-located-outside-the-perimeter-network"></a>Installieren eines Zertifikats auf einem Watcher-Knoten, der sich außerhalb des Umkreisnetzwerks befindet
<a name="watcher_node_outside"> </a>

System Center Operations Manager-Agents, die in einem Umkreisnetzwerk (wie einem Skype for Business Server Edge-Server) ausgeführt werden, außerhalb des Unternehmens (beispielsweise ein externer synthetischer Transaktions Überwachungsknoten) oder über eine Active Directory-Vertrauensgrenze verfügen, erfordern möglicherweise die Konfiguration eines System Center Operations Manager-Gatewayservers. Diese Serverrolle ermöglicht es Agents, die keine Vertrauensstellung mit dem Root Management Server haben, Warnungen auszulösen. Ausführliche Informationen finden Sie unter [Verwalten von Gatewayservern in Operations Manager 2012](https://technet.microsoft.com/en-us/library/hh212823.aspx).

Wenn Sie einen Agenten an einem dieser Speicherorte bereitstellen, müssen Sie auch ein Zertifikat anfordern und konfigurieren, das dem Watcher-Knoten die Möglichkeit gibt, Benachrichtigungen an System Center Operations Manager zu senden. Zur Vereinfachung dieses Prozesses hat das Operations Manager-Team einen Satz von Dienstprogrammen erstellt, mit denen Sie den richtigen Zertifikattyp auf dem Watcher-Knoten Computer anfordern und installieren können. Informationen zum Herunterladen dieser Dienstprogramme finden Sie unter [Abrufen von Zertifikaten für nicht zu der Domäne beige tretene Agents, die mit dem Assistenten für die Zertifikatgenerierung vereinfacht](https://go.microsoft.com/fwlink/p/?LinkID=267421&amp;amp;clcid=0x409)werden.

### <a name="installing-the-operation-manager-agent-files"></a>Installieren der Operations Manager-Agent-Dateien

1. Doppelklicken Sie auf den System Center-Setupmedien auf **Setup.exe**.

2. Klicken Sie im System Center Operation Manager-Setup-Assistenten auf **Operations Manager-Agent installieren**, vom Installations-Agent unter Optionale Installationen

3. Klicken Sie im System Center-Setup-Assistenten auf der Seite Willkommen beim Setup-Assistenten für System Center Operations Manager auf **weiter**.

4. Wählen Sie auf der Seite Zielordner den Ordner aus, in dem die Operations Manager-Agentendateien installiert werden sollen, und klicken Sie auf **weiter**.

5. Wählen Sie auf der Seite „Verwaltungsgruppenkonfiguration“ die Option **Verwaltungsgruppeninformationen angeben** aus und klicken Sie auf **Weiter**.

6. Geben Sie auf der Seite Verwaltungsgruppenkonfiguration den Namen Ihrer Operations Manager-Verwaltungsgruppe im Feld **Verwaltungsgruppenname** ein, und geben Sie dann den Hostnamen Ihres Operations Manager-Servers (beispielsweise ATL-SCOM-001) im Feld **Verwaltungsserver** ein. Wenn Sie die von Operations Manager verwendete Portnummer geändert haben, geben Sie die neue Portnummer in das Feld **Verwaltungs Server Port** ein. Behalten Sie andernfalls den Port mit dem Standardwert 5723 bei, und klicken Sie dann auf **weiter**.

7. Wählen Sie auf der Seite „Agentaktionskonto“ die Option **Lokales System** aus und klicken Sie auf **Weiter**.

8. Wählen Sie auf der Seite „Microsoft Update“ die Option **Ich möchte Microsoft Update nicht verwenden** aus und klicken Sie auf **Weiter**.

9. Klicken Sie auf der Seite „Bereit zum Installieren“ auf **Installieren**.

10. Klicken Sie auf der Seite Abschließen des Setup-Assistenten von System Center Operations Manager auf **Fertig stellen**.

11. Klicken Sie auf **Beenden**.

Bei System Center 2012 können Sie überprüfen, ob der Agent erstellt wurde, indem Sie auf **Start**klicken, auf **Alle Programme**klicken, auf **System Center Operations Manager 2012**und dann auf **Operations 2012-Manager-Shell**klicken. Geben Sie in der Operations Manager-Shell den folgenden Windows PowerShell-Befehl ein, und drücken Sie dann die EINGABETASTE:
```PowerShell
Get-SCOMAgent
```

Eine Liste aller Operations Manager-Agents wird angezeigt.
## <a name="configuring-the-skype-for-business-server-computer-to-participate-in-system-center-discovery"></a>Konfigurieren des Skype for Business Server-Computers für die Teilnahme an der System Center-Ermittlung
<a name="watcher_node_outside"> </a>

Wenn Sie sicherstellen möchten, dass Ihr neuer Skype for Business Server-Agent am Ermittlungsprozess für System Center Operations Manager teilnimmt, müssen Sie auf jedem Computer, auf dem die System Center Operations Manager-Konsole installiert wurde, das folgende Verfahren ausführen:

1. Klicken Sie auf der Registerkarte „Verwaltung“ auf **Mit Agents verwaltet**.

2. Klicken Sie auf **Ermittlungs-Assistent** und schließen Sie den Assistenten für den zu ermittelnden Computer ab.

3. Starten Sie den Systemintegritäts-Agent-Dienst neu. Durch den Neustart des Diensts wird die Erkennung des neuen Computers erzwungen. Wenn Sie den Dienst nicht neu starten, kann es bis zu 4 Stunden dauern, bis der neue Computer von System Center Operations Manager erkannt wird.

4. Stellen Sie sicher, dass keine Fehlerereignisse im Operations Manager-Ereignisprotokoll aufgezeichnet wurden.

5. Der Computer, auf dem der Agent erfolgreich abgelegt wird, wird unter "Agenten verwaltet" angezeigt, und der Computer, auf dem Agent manuell installiert wurde, wird unter "Ausstehende Verwaltung" angezeigt, klicken Sie auf den Namen des Computers und genehmigen.

6. Klicken Sie mit der rechten Maustaste auf den Namen des Computers und klicken Sie dann auf **Eigenschaften**. Wählen Sie im Dialogfeld „Eigenschaften“ auf der Registerkarte „Sicherheit“ die Option **Dieser Agent soll als Proxyagent fungieren und verwaltete Objekte auf anderen Computern erkennen** und klicken Sie dann auf **OK**.


