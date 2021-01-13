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
description: Bevor Sie mit dem Entwerfen und Planen Ihrer Skype for Business Server 2015-Infrastruktur mithilfe des Skype for Business Server 2015-Planungstools beginnen, müssen Sie zuerst das Planungstool installieren. Das Planungstool muss nicht auf einer Arbeitsstation oder einem Server bereitgestellt werden, die Teil der Domäne oder Infrastruktur ist, in der Sie Skype for Business Server 2015 installieren möchten. In der Infodatei, die das Planungstool begleitet, werden wichtige Informationen zum Installieren und Verwenden des Tools angezeigt. Einige Informationen in der Infodatei werden hier aus Gründen der Übersichtlichkeit dupliziert.
ms.openlocfilehash: 902249e042694a37594c6dc0b753b0c1388c0729
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2021
ms.locfileid: "49834725"
---
# <a name="install-the-planning-tool-in-skype-for-business-server-2015"></a>Installieren des Planungstools in Skype for Business Server 2015

Bevor Sie mit dem Entwerfen und Planen Ihrer Skype for Business Server 2015-Infrastruktur mithilfe des Skype for Business Server 2015-Planungstools beginnen, müssen Sie zuerst das Planungstool installieren. Das Planungstool muss nicht auf einer Arbeitsstation oder einem Server bereitgestellt werden, die Teil der Domäne oder Infrastruktur ist, in der Sie Skype for Business Server 2015 installieren möchten. In der Infodatei, die das Planungstool begleitet, werden wichtige Informationen zum Installieren und Verwenden des Tools angezeigt. Einige Informationen in der Infodatei werden hier aus Gründen der Übersichtlichkeit dupliziert.

> [!IMPORTANT]
> Das Planungstool erfordert die Installation durch einen Benutzer mit Administratorrechten und -berechtigungen auf dem Computer, auf dem das Tool installiert werden soll.

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

1. Melden Sie sich als Mitglied der Gruppe Administratoren am lokalen Computer an.

2. Suchen Sie mithilfe von Windows Explorer oder einem Befehlsfenster das Verzeichnis, in das Sie die Installationsdateien des Planungstools heruntergeladen haben.

3. Suchen Sie den SkypeForBusinessPlanningTool.msi. Doppelklicken Sie in Windows Explorer auf die Datei. Geben Sie im Befehlsfenster den Namen der Datei ein, und drücken Sie dann die **EINGABETASTE,** um die Datei auszuführen.

4. Klicken Sie auf der Willkommensseite des **Skype for Business Server 2015-Setup-Assistenten** für das Planungstool auf **"Weiter".**

5. Lesen Sie **den Endbenutzer-Lizenzvertrag,** wählen Sie aus, ob ich den Bedingungen des Lizenzvertrags zugene, wenn Sie die Nutzungsbedingungen im Lizenzvertrag akzeptieren möchten, und klicken Sie dann auf  **"Weiter".**

6. Wählen Sie aus, wo die Dateien des Planungstools installiert werden. Der Standardspeicherort ist "C:\Programme (x86)\Skype for Business Server 2015\Planning Tool". Wenn Sie den Installationsspeicherort ändern möchten, klicken Sie auf **"Ändern".** Navigieren **Oder geben Sie im Zielordner** ändern den Speicherort ein, an dem die Dateien installiert werden, klicken Sie auf **"OK"** und dann auf **"Weiter".**

7. Das Installationsprogramm kann nun das Planungstool installieren. Klicken **Sie auf "Installieren",** um den Installationsvorgang zu starten.

8. Die Installation wird gestartet, und der Fortschritt wird angezeigt. Klicken Sie nach dem erfolgreichen Abschluss der Installation auf **"Fertig stellen".**

9. Das Planungstool ist einsatzbereit.

## <a name="optional-software"></a>Optionale Software
<a name="Optional_Software"> </a>

Das Skype for Business Server 2015-Planungstool wurde für den Export nach Microsoft Excel und Microsoft Visio entwickelt. Obwohl diese Anwendungen für den Betrieb des Planungstools nicht erforderlich sind, haben sie einen erheblichen Nutzen für die Bereitstellung und Dokumentation Ihres Entwurfs.

### <a name="microsoft-excel"></a>Microsoft Excel

Beim Exportieren Ihres Designs nach Microsoft Excel wird ein Bericht erstellt, in dem sieben Registerkarten in der Tabelle angezeigt werden:

- Zusammenfassung : Zeigt Informationen zur Standortkonfiguration an, einschließlich Benutzeranzahl, Kapazitätseinstellungen und Serverprofilinformationen.

- Hardwareprofil : Zeigt einen Bericht zu den empfohlenen Hardwarekonfigurationen für Server an, die in der Topologie angegeben sind, einschließlich CPU, Arbeitsspeicher, Datenträger und Netzwerkschnittstelle. Die Menge und die empfohlenen Spezifikationen für die Serverkomponenten sind ebenfalls enthalten. Darüber hinaus wird jeder Server nach Standort definiert, um eine vollständige Darstellung der Serveranforderungen nach Standort zu bieten.

- Portanforderungen : Zeigt einen Bericht über alle aktivierten Ports sowie die Zuordnung zu #A0 (Domain Name System Load Balancing, DNS LB) und Hardwaregerät zum Lastenausgleich (HlB) an. Sie sollten diesen Bericht verwenden, um Ihre Firewall- und DNS-LB- und #A0 zu planen.

- Zusammenfassungsbericht – Zeigt eine allgemeine Zusammenfassung der Einstellungen an, die zum Einrichten des Edgeservernetzwerks erforderlich sind.

- Zertifikatbericht – Zeigt den Betreffnamen und alternative Namen des Betreffs an, die für die Zertifikate erforderlich sind, damit die Edgeserver ausgeführt werden.

- Firewallbericht : Zeigt die Quell- und Zielports sowie die IP-Adressen für externe und interne Schnittstellen an.

- DNS-Bericht : Zeigt den vollqualifizierten Domänennamen (Fully Qualified Domain Name, FQDN) und die IP/VIP-Adressen an, die für jeden von Ihnen erstellten DNS-Eintrag erforderlich sind.

### <a name="microsoft-visio"></a>Microsoft Visio

Beim Exportieren Ihres Entwurfs nach Microsoft Visio wird ein Diagramm erstellt, das Sie zur Dokumentation Ihrer konfigurierten Topologie und Infrastruktur verwenden können. Das importierte Diagramm kann bearbeitet und neu angeordnet werden, um Ihre Dokumentationsanforderungen zu erfüllen. Das typische Visio-Diagramm umfasst Folgendes:

> [!NOTE]
> Wenn Ihr Entwurf so groß ist, dass mehr als drei Front-End-Server erforderlich sind, wird eine zusätzliche Seite für den Front-End-Pool, die Front-End-Server, den Computer mit SQL Server, die IP-Adressen und FQDNs erstellt.

- Globale Topologie – Diagramm der konfigurierten Skype for Business Server 2015-Standorte.

- Registerkarte "Standortname" – Zeigt die Standortkonfigurationstopologie mit Edgeserver, Firewall, Festnetz (Public Switched Telephone Network, PSTN) mit Gateways und der internen Serverbereitstellung an. Die interne Bereitstellung besteht aus konfigurierten Servern und Pools, einschließlich front-End-Pools, SQL Server-basierten Servern, Active Directory-Domänendiensten, Directors, Exchange Unified Messaging (UM)-Servern, Exchange-Postfachservern, Office Web Apps-Servern, Vermittlungsservern und Servern für beständigen Chat.

- Edgenetzwerkdiagramm – Diagramm, in dem die Edgeserverkonfiguration mit den zugehörigen IP-Adressen und FQDNs beschrieben ist. DNS-Lastenausgleich und Hardwarelastenausgleich sind ebenfalls enthalten. Darüber hinaus werden Directors und der Front-End-Server oder Front-End-Pool mit zugeordneten #A0 oder HLB und der zugewiesenen #A1 (das Planungstool unterstützt sowohl IPv4- als auch #A2 ) und FQDN angezeigt.

## <a name="see-also"></a>Siehe auch
<a name="Optional_Software"> </a>

[Installieren des Planungstools](https://technet.microsoft.com/library/ebdc9e26-4b22-4b02-85b9-7462bcfe7c93.aspx)
