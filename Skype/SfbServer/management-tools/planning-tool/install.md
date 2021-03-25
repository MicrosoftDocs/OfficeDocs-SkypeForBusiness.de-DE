---
title: Installieren des Planungstools in Skype for Business Server 2015
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 4/5/2016
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: b95b3301-fa1e-4b96-9af4-05b43d39db8d
description: Bevor Sie mit dem Entwerfen und Planen Ihrer Skype for Business Server 2015-Infrastruktur mithilfe des Skype for Business Server 2015-Planungstools beginnen, müssen Sie zuerst das Planungstool installieren. Das Planungstool muss nicht auf einer Arbeitsstation oder einem Server bereitgestellt werden, die Teil der Domäne oder Infrastruktur ist, in der Sie Skype for Business Server 2015 installieren möchten. Die Readme-Datei, die das Planungstool begleitet, enthält wichtige Informationen zum Installieren und Verwenden des Tools. Einige der Informationen in der Readme-Datei werden hier aus Gründen der Übersichtlichkeit dupliziert.
ms.openlocfilehash: 29a3bd35191cf326cafd1f4ad4f14fab50e47ea3
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51122379"
---
# <a name="install-the-planning-tool-in-skype-for-business-server-2015"></a>Installieren des Planungstools in Skype for Business Server 2015

Bevor Sie mit dem Entwerfen und Planen Ihrer Skype for Business Server 2015-Infrastruktur mithilfe des Skype for Business Server 2015-Planungstools beginnen, müssen Sie zuerst das Planungstool installieren. Das Planungstool muss nicht auf einer Arbeitsstation oder einem Server bereitgestellt werden, die Teil der Domäne oder Infrastruktur ist, in der Sie Skype for Business Server 2015 installieren möchten. Die Readme-Datei, die das Planungstool begleitet, enthält wichtige Informationen zum Installieren und Verwenden des Tools. Einige der Informationen in der Readme-Datei werden hier aus Gründen der Übersichtlichkeit dupliziert.

> [!IMPORTANT]
> Das Planungstool erfordert die Installation durch einen Benutzer mit Administratorrechten und Berechtigungen auf dem Computer, auf dem das Tool installiert werden soll.

Die unterstützten Betriebssysteme für die Installation und den Betrieb des Planungstools sind:

- Windows 10

- Windows 8

- Windows 8.1

- Windows Server 2012

- Windows Server 2012 R2

- Windows 7, 32-Bit-Edition

- Windows 7, 64-Bit-Edition mit Windows unter Win32 (WOW)

- Windows Server 2008 R2 mithilfe von WOW

Darüber hinaus erfordert das Planungstool Microsoft .NET Framework 4.5.

Nachdem die Voraussetzungen für die Vorinstallation erfüllt sind, können Sie das Planungstool installieren.



## <a name="to-install-the-planning-tool"></a>So installieren Sie das Planungstool

1. Melden Sie sich beim lokalen Computer als Mitglied der Gruppe Administratoren an.

2. Suchen Sie mithilfe von Windows Explorer oder einem Befehlsfenster nach dem Verzeichnis, in dem Sie die Installationsdateien des Planungstools heruntergeladen haben.

3. Suchen Sie nach SkypeForBusinessPlanningTool.msi. Doppelklicken Sie im Windows-Explorer auf die Datei. Geben Sie im Befehlsfenster den Namen der Datei ein, und drücken Sie dann die **EINGABETASTE,** um die Datei auszuführen.

4. Klicken Sie auf der Willkommensseite des **Skype for Business Server 2015-Assistenten** zum Einrichten des Planungstools auf **Weiter**.

5. Überprüfen Sie **den Endbenutzerlizenzvertrag,** wählen Sie Ich akzeptiere die Bedingungen **im** Lizenzvertrag aus, wenn Sie die Nutzungsbedingungen im Lizenzvertrag akzeptieren möchten, und klicken Sie dann auf **Weiter**.

6. Wählen Sie aus, wo die Planungstooldateien installiert werden. Der Standardspeicherort ist C:\Program Files (x86)\Skype for Business Server 2015\Planning Tool. Wenn Sie den Installationsspeicherort ändern möchten, klicken Sie auf **Ändern**. Navigieren **oder geben** Sie unter Zielordner ändern den Speicherort zum Installieren der Dateien ein, klicken Sie auf **OK,** und klicken Sie dann auf **Weiter**.

7. Das Installationsprogramm kann nun das Planungstool installieren. Klicken **Sie auf Installieren,** um den Installationsvorgang zu starten.

8. Die Installation wird gestartet, und der Fortschritt wird angezeigt. Nachdem die Installation erfolgreich abgeschlossen wurde, klicken Sie auf **Fertig stellen**.

9. Das Planungstool ist einsatzbereit.

## <a name="optional-software"></a>Optionale Software
<a name="Optional_Software"> </a>

Das Skype for Business Server 2015-Planungstool ist für den Export nach Microsoft Excel und Microsoft Visio konzipiert. Diese Anwendungen sind zwar nicht für den Betrieb des Planungstools erforderlich, aber sie haben einen erheblichen Nutzen für die Bereitstellung und Dokumentation Ihres Entwurfs.

### <a name="microsoft-excel"></a>Microsoft Excel

Wenn Sie Ihr Design nach Microsoft Excel exportieren, wird ein Bericht erstellt, in dem sieben Registerkarten in der Tabelle angezeigt werden:

- Zusammenfassung – Zeigt Informationen zur Websitekonfiguration an, einschließlich Benutzeranzahl, Kapazitätseinstellungen und Serverprofilinformationen.

- Hardwareprofil – Zeigt einen Bericht zu den empfohlenen Hardwarekonfigurationen für Server an, die in der Topologie angegeben sind, einschließlich CPU, Arbeitsspeicher, Datenträger und Netzwerkschnittstelle. Die Menge und die empfohlenen Spezifikationen für die Serverkomponenten sind ebenfalls enthalten. Darüber hinaus wird jeder Server nach Standort definiert, um eine vollständige Darstellung der Serveranforderungen nach Standort zu ermöglichen.

- Ports Requirements – Zeigt einen Bericht aller aktivierten Ports sowie die Zuordnung zu Dns LB (Domain Name System Load Balancing) und Hardware load balancers (HLB) an. Sie sollten diesen Bericht verwenden, um Ihre Firewall- und DNS LB- und HLB-Konfigurationen zu planen.

- Zusammenfassungsbericht – Zeigt die allgemeine Zusammenfassung der Einstellungen an, die zum Einrichten des Edgeservernetzwerks erforderlich sind.

- Zertifikatebericht – Zeigt den Namen des Betreffs und alternative Betreffnamen an, die für die Zertifikate erforderlich sind, um die Edgeserver ausführen zu können.

- Firewallbericht – Zeigt die Quell- und Zielports und IP-Adressen für externe und interne Schnittstellen an.

- DNS-Bericht – Zeigt den vollqualifizierten Domänennamen (Fully Qualified Domain Name, FQDN) und die IP/VIP-Adressen an, die für jeden von Ihnen erstellten DNS-Eintrag erforderlich sind.

### <a name="microsoft-visio"></a>Microsoft Visio

Beim Exportieren Ihres Entwurfs nach Microsoft Visio wird ein Diagramm erstellt, das Sie zur Dokumentation Ihrer konfigurierten Topologie und Infrastruktur verwenden können. Das importierte Diagramm kann bearbeitet und neu angeordnet werden, um Ihre Dokumentationsanforderungen zu erfüllen. Das typische Visio-Diagramm umfasst Folgendes:

> [!NOTE]
> Wenn Ihr Entwurf so groß ist, dass mehr als drei Front-End-Server erforderlich sind, wird eine zusätzliche Seite für den Front-End-Pool, front-End-Server, den Computer mit SQL Server, IP-Adressen und FQDNs erstellt.

- Globale Topologie – Diagramm konfigurierter Skype for Business Server 2015-Websites.

- Registerkarte Standortname – Zeigt die Standortkonfigurationstopologie mit Edgeserver, Firewall, Festnetz (Public Switched Telephone Network, PSTN) mit Gateways und die interne Serverbereitstellung an. Die interne Bereitstellung besteht aus konfigurierten Servern und Pools, einschließlich front-End-Pools, SQL Server-basierten Servern, Active Directory-Domänendiensten, Directors, Exchange Unified Messaging (UM)-Servern, Exchange-Postfachservern, Office Web Apps-Servern, Vermittlungsservern und Servern für beständigen Chat.

- Edgenetzwerkdiagramm – Diagramm, das die Edgeserverkonfiguration mit den zugeordneten IP-Adressen und FQDNs enthält. DNS-Lastenausgleich und Hardwarelastenausgleich sind ebenfalls enthalten. Darüber hinaus werden Directors und der Front-End-Server oder Front-End-Pool mit zugeordneter DNS LB oder HLB und der zugewiesenen #A0 (das Planungstool unterstützt sowohl IPv4- als auch IPv6-Adressen) und FQDN angezeigt.

## <a name="see-also"></a>Siehe auch
<a name="Optional_Software"> </a>

[Installieren des Planungstools](/previous-versions/office/lync-server-2013/lync-server-2013-installing-the-planning-tool)