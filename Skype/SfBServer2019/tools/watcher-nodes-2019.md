---
title: Konfigurieren von Skype for Business Server-Computern, die überwacht werden sollen
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 11/7/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
description: 'Zusammenfassung: Installieren der Operations Manager-Agent-Dateien auf die Skype für Business Server 2019 Computer überwacht werden, und konfigurieren Sie den Computer, die als System Center-Proxy fungiert.'
ms.openlocfilehash: 3f2e17dcaa32a37f0ae7b5ef73cd6f351c9d4bc1
ms.sourcegitcommit: 30620021ceba916a505437ab641a23393f55827a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/15/2018
ms.locfileid: "26536043"
---
# <a name="configure-the-skype-for-business-server-computers-that-will-be-monitored"></a>Konfigurieren von Skype for Business Server-Computern, die überwacht werden sollen

**Zusammenfassung:** Installieren der Operations Manager-Agent-Dateien auf die Skype für Business Server 2019 Computer überwacht werden, und konfigurieren Sie den Computer, die als System Center-Proxy fungiert.

Jede Skype für Business Server 2019 Computer, den Sie überwachen möchten muss sein Vorhandensein an den Verwaltungsserver selbst zu melden können. Um dies zu ermöglichen, müssen Sie die Operations Manager-Agent-Dateien auf allen zu überwachenden Computern installieren. Nach dem Installieren der Agent-Dateien müssen Sie die Computer für die Funktion als System Center-Proxy konfigurieren. Stellen Sie sicher, dass Sie zuerst installiert und Skype auf diesen Computern vor dem Ausführen dieser Verfahren für Business Server konfiguriert haben.

## <a name="installing-a-certificate-on-a-watcher-node-located-outside-the-perimeter-network"></a>Installieren eines Zertifikats auf einem Watcher-Knoten, der sich außerhalb des Umkreisnetzwerks befindet
<a name="watcher_node_outside"> </a>

System Center Operations Manager-Agents in einem Umkreisnetzwerk ausgeführt Netzwerk (wie eine Skype für Business Server-Edgeserver) außerhalb des Unternehmens (beispielsweise ein externer synthetische Transaktion Watcher-Knoten) oder über eine Active Directory-Vertrauensstellung Grenze, erfordern möglicherweise die Konfiguration der ein System Center Operations Manager-Gatewayservers. Diese Serverrolle ermöglicht es Agents, die keine Vertrauensstellung mit dem Root Management Server haben, Warnungen auszulösen. Ausführliche Informationen finden Sie in [Verwalten von Gatewayservern in Operations Manager 2012](https://technet.microsoft.com/en-us/library/hh212823.aspx).

Wenn Sie einen Agent in einem der folgenden Speicherorte bereitstellen, müssen Sie auch zum Anfordern und Konfigurieren eines Zertifikats, das den Watcher-Knoten zum Senden von Benachrichtigungen zu System Center Operations Manager ermöglicht. Um diesen Prozess vereinfachen, hat das Team Operations Manager einen Satz Dienstprogramme erstellt, mit denen Sie anfordern und den korrekten Typ des Zertifikats auf dem Watcher-Knoten-Computer installieren. Ausführliche Informationen, unter anderem zum Herunterladen dieser Dienstprogramme, finden Sie unter [Obtaining Certificates for Non-Domain Joined Agents Made Easy with Certificate Generation Wizard](https://go.microsoft.com/fwlink/p/?LinkID=267421&amp;amp;clcid=0x409).

### <a name="installing-the-operation-manager-agent-files"></a>Installieren der Operations Manager-Agent-Dateien

1. Doppelklicken Sie auf den System Center-Setupmedien auf **Setup.exe**.

2. Klicken Sie im System Center Operations Manager-Setup-Assistenten auf **Operations Manager-Agent installieren**von Agent installieren, klicken Sie unter Optional Installationen

3. Klicken Sie in den System Center-Setup-Assistenten auf der Willkommensseite auf der Seite System Center Operations Manager-Setup-Assistenten auf **Weiter**.

4. Wählen Sie auf der Seite Zielordner den Ordner, in dem die Operations Manager-Agent-Dateien installiert werden sollen, und klicken Sie auf **Weiter**.

5. Wählen Sie auf der Seite „Verwaltungsgruppenkonfiguration“ die Option **Verwaltungsgruppeninformationen angeben** aus und klicken Sie auf **Weiter**.

6. Geben Sie auf der Seite Verwaltungsgruppenkonfiguration den Namen Ihrer Operations Manager Management Gruppe in das Feld **Gruppenname Management** , und geben Sie den Hostnamen des Servers Operations Manager (beispielsweise Atl-Scom-001) in die **Management Server **Feld. Wenn Sie die Portnummer von Operations Manager geändert haben, geben Sie die neue Portnummer im **Management Server-Port** . Andernfalls lassen Sie den Standardwert 5723 für den Port, und klicken Sie dann auf **Weiter**.

7. Wählen Sie auf der Seite „Agentaktionskonto“ die Option **Lokales System** aus und klicken Sie auf **Weiter**.

8. Wählen Sie auf der Seite „Microsoft Update“ die Option **Ich möchte Microsoft Update nicht verwenden** aus und klicken Sie auf **Weiter**.

9. Klicken Sie auf der Seite „Bereit zum Installieren“ auf **Installieren**.

10. Klicken Sie auf der Seite Fertigstellen des der System Center Operations Manager-Setup-Assistent-Seite klicken Sie auf **Fertig stellen**.

11. Klicken Sie auf **Beenden**.

Für System Center 2012 stellen Sie sicher, dass der Agent erstellt wurde, indem Sie klicken Sie auf **Start**, **Alle**Programme, auf **System Center Operations Manager 2012**und klicken Sie dann auf **Operations Manager 2012-Shell**. Geben Sie in der Operations Manager-Shell den folgenden Windows PowerShell-Befehl ein, und drücken Sie die EINGABETASTE:
```
Get-SCOMAgent
```

Eine Liste aller Operations Manager-Agents wird angezeigt.
## <a name="configuring-the-skype-for-business-server-computer-to-participate-in-system-center-discovery"></a>Konfigurieren des Skype for Business Server-Computers für die Teilnahme an der System Center-Ermittlung
<a name="watcher_node_outside"> </a>

Um sicherzustellen, dass Ihre neue Skype für Business Server-Agent für System Center Operations Manager in den Suchprozess beteiligt ist, müssen Sie das folgende Verfahren auf jedem Computer ausführen, auf dem die System Center Operations Manager-Konsole installiert wurde:

1. Klicken Sie auf der Registerkarte „Verwaltung“ auf **Mit Agents verwaltet**.

2. Klicken Sie auf **Ermittlungs-Assistent** und schließen Sie den Assistenten für den zu ermittelnden Computer ab.

3. Starten Sie den Systemintegritäts-Agent-Dienst neu. Durch den Neustart des Diensts wird die Erkennung des neuen Computers erzwungen. Wenn Sie den Dienst nicht neu starten, kann das 4 Stunden vor der neue Computer von System Center Operations Manager erkannt wird so lange dauern.

4. Stellen Sie sicher, dass keine Fehlerereignisse im Operations Manager-Ereignisprotokoll aufgezeichnet wurden.

5. Der Computer, auf dem der Agent erfolgreich abgelegt ist, unter "Agent verwaltet" Liste angezeigt werden und der Computer, auf dem Agent manuell installiert wurde, unter "Verwalten von ausstehenden" angezeigt werden soll, klicken Sie auf den Namen des Computers und genehmigen.

6. Klicken Sie mit der rechten Maustaste auf den Namen des Computers und klicken Sie dann auf **Eigenschaften**. Wählen Sie im Dialogfeld „Eigenschaften“ auf der Registerkarte „Sicherheit“ die Option **Dieser Agent soll als Proxyagent fungieren und verwaltete Objekte auf anderen Computern erkennen** und klicken Sie dann auf **OK**.


