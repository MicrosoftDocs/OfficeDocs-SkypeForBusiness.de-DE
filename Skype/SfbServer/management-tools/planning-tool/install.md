---
title: Installieren des Planungstools in Skype for Business Server 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 4/5/2016
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: b95b3301-fa1e-4b96-9af4-05b43d39db8d
description: Bevor Sie mit dem Entwerfen und Planen Ihrer Skype for Business Server 2015-Infrastruktur mithilfe des Planungstools von Skype for Business Server 2015 beginnen, müssen Sie zuerst das Planungstool installieren. Das Planungs Tool muss nicht auf einer Workstation oder einem Server bereitgestellt werden, die Teil der Domäne oder Infrastruktur ist, in der Sie Skype for Business Server 2015 installieren möchten. In der Readme-Datei, die dem Planungs Tool beigefügt ist, finden Sie wichtige Informationen zum Installieren und Verwenden des Tools. Einige Informationen aus dieser Datei werden zur Verdeutlichung im Folgenden noch einmal aufgeführt.
ms.openlocfilehash: 192eae34bf6cf3fa53be82d8cb4450f960c90314
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2019
ms.locfileid: "34279127"
---
# <a name="install-the-planning-tool-in-skype-for-business-server-2015"></a>Installieren des Planungstools in Skype for Business Server 2015

Bevor Sie mit dem Entwerfen und Planen Ihrer Skype for Business Server 2015-Infrastruktur mithilfe des Planungstools von Skype for Business Server 2015 beginnen, müssen Sie zuerst das Planungstool installieren. Das Planungs Tool muss nicht auf einer Workstation oder einem Server bereitgestellt werden, die Teil der Domäne oder Infrastruktur ist, in der Sie Skype for Business Server 2015 installieren möchten. In der Readme-Datei, die dem Planungs Tool beigefügt ist, finden Sie wichtige Informationen zum Installieren und Verwenden des Tools. Einige Informationen aus dieser Datei werden zur Verdeutlichung im Folgenden noch einmal aufgeführt.

> [!IMPORTANT]
> Das Planungs Tool erfordert die Installation durch einen Benutzer mit Administratorrechten und-Berechtigungen auf dem Computer, auf dem das Tool installiert werden soll.

Die unterstützten Betriebssysteme für die Installation und den Betrieb des Planungstools sind:

- Windows 10

- Windows 8

- Windows 8,1

- Windows Server 2012

- Windows Server 2012 R2

- Windows 7, 32-Bit-Version

- Windows 7, 64-Bit-Version unter Verwendung von Windows on Win32 (WOW)

- Windows Server 2008 R2 unter Verwendung von WOW

Darüber hinaus erfordert das Planungs Tool Microsoft .NET Framework 4,5.

Nachdem die Voraussetzungen für die Vorinstallation erfüllt sind, können Sie das Planungs Tool installieren.



## <a name="to-install-the-planning-tool"></a>So installieren Sie das Planungstool

1. Melden Sie sich auf dem lokalen Computer als Mitglied der Gruppe "Administratoren" an.

2. Suchen Sie im Windows-Explorer oder einem Befehlsfenster nach dem Verzeichnis, in dem Sie die Installationsdateien des Planungstools heruntergeladen haben.

3. Suchen Sie die Datei SkypeForBusinessPlanningTool.msi. Machen Sie im Windows Explorer einen Doppelklick auf die Datei. Geben Sie im Befehlsfenster den Namen der Datei ein und drücken Sie die **Eingabetaste**, um die Datei auszuführen.

4. Klicken Sie auf der Willkommensseite des Setup-Assistenten für das **Skype for Business Server 2015-Planungstool** auf **Weiter**.

5. Lesen Sie den **Endbenutzer-Lizenzvertrag**, wählen Sie die Option **Ich stimme den Bedingungen des Lizenzvertrags zu** aus, sofern Sie die Bedingungen akzeptieren, und klicken Sie anschließend auf **Weiter**.

6. Geben Sie an, in welchem Verzeichnis die Dateien des Planungstools installiert werden sollen. Der Standardspeicherort lautet „C:\Programme (x86)\Skype for Business Server 2015\Planning Tool“. Wenn Sie ein anderes Installationsverzeichnis auswählen möchten, klicken Sie auf **Ändern**. Navigieren Sie im Dialogfeld **Zielordner ändern** zum gewünschten Verzeichnis oder geben Sie ein Verzeichnis ein und klicken Sie nacheinander auf **OK** und auf **Weiter**.

7. Das Installationsprogramm ist nun bereit, das Planungs Tool zu installieren. Klicken Sie auf **Installieren**, um den Installationsvorgang zu starten.

8. Die Installation beginnt und der Installationsfortschritt wird angezeigt. Klicken Sie nach Abschluss der Installation auf **Fertigstellen**.

9. Das Planungs Tool ist einsatzbereit.

## <a name="optional-software"></a>Optionale Software
<a name="Optional_Software"> </a>

Das Planungs Tool für Skype for Business Server 2015 ist für den Export nach Microsoft Excel und Microsoft Visio konzipiert. Obwohl diese Anwendungen nicht für den Betrieb des Planungstools erforderlich sind, fügen Sie der Bereitstellung und Dokumentation Ihres Entwurfs einen erheblichen Mehrwert hinzu.

### <a name="microsoft-excel"></a>Microsoft Excel

Beim Exportieren Ihres Entwurfs nach Microsoft Excel wird ein Bericht in Form einer Tabelle mit sieben Registerkarten erstellt:

- Zusammenfassung: zeigt Informationen zur Websitekonfiguration an, einschließlich Benutzeranzahl, Kapazitätseinstellungen und Server Profilinformationen.

- Hardwareprofil – zeigt einen Bericht zu den empfohlenen Hardwarekonfigurationen für Server an, die in der Topologie angegeben sind, einschließlich CPU, Arbeitsspeicher, Datenträger und Netzwerkschnittstelle. Die Anzahl und die empfohlenen Spezifikationen für die Serverkomponenten sind auch enthalten. Darüber hinaus ist jeder Server nach Standort definiert, um eine vollständige Darstellung der Serveranforderungen nach Standort bereitzustellen.

- Ports-Anforderungen – zeigt einen Bericht aller aktivierten Ports und die Zuordnung zu Domain Name System Load Balancing (DNS lb) und Hardware Load Balancer (HLB) an. Sie sollten diesen Bericht zum Planen der Konfiguration von Firewall sowie DNS-Lastenausgleich und Hardwaregeräten zum Lastenausgleich verwenden.

- Zusammenfassungsbericht – zeigt die allgemeine Zusammenfassung der Einstellungen an, die zum Einrichten Ihres Edge-Server-Netzwerks erforderlich sind.

- Bericht "Zertifikate" – zeigt den Antragstellernamen und die alternativen Betreffnamen an, die für die für die Ausführung der Edgeserver erforderlichen Zertifikate erforderlich sind.

- Firewallbericht – zeigt die Quell-und Zielports sowie IP-Adressen sowohl für externe als auch für interne Schnittstellen an.

- DNS-Bericht – zeigt den vollqualifizierten Domänennamen (Fully Qualified Domain Name, FQDN) und IP/VIP-Adressen für jeden von Ihnen erstellten DNS-Eintrag an.

### <a name="microsoft-visio"></a>Microsoft Visio

Beim Exportieren Ihres Entwurfs nach Microsoft Visio wird ein Diagramm erstellt, das Sie zur Dokumentation Ihrer konfigurierten Topologie und Infrastruktur verwenden können. Das importierte Diagramm kann bearbeitet und neu angeordnet werden, um Ihre Dokumentationsanforderungen zu erfüllen. Das typische Visio-Diagramm umfasst Folgendes:

> [!NOTE]
> Wenn Ihr Entwurf groß genug ist, um mehr als drei Front-End-Server zu erfordern, wird eine zusätzliche Seite für den Front-End-Pool, Front-End-Server, den Computer mit SQL Server, IP-Adressen und FQDNs erstellt.

- Globale Topologie – Diagramm der konfigurierten Skype for Business Server 2015-Websites.

- Registerkarte "Website Name" – zeigt die Topologie der Websitekonfiguration mit Edgeserver, Firewall, PSTN (Public Switched Telephone Network) mit Gateways und der internen Server Bereitstellung an. Die interne Bereitstellung besteht aus konfigurierten Servern und Pools, einschließlich der Front-End-Pools, SQL Server-basierten Servern, Active Directory-Domänendiensten, Directors, Exchange Unified Messaging (um)-Servern, Exchange-Postfachservern, Office Web Apps-Servern, Vermittlungsserver und persistente Chat Server.

- Edge-Netzwerkdiagramm – Diagramm, in dem die Edgeserver-Konfiguration mit zugehörigen IP-Adressen und FQDNs erläutert wird. DNS-Lastenausgleich und Hardwarelastenausgleich sind ebenfalls enthalten. Darüber hinaus werden Directors und der Front-End-Server oder der Front-End-Pool mit zugeordneter DNS lb oder HLB und der zugewiesenen IP-Adresse (das Planungs Tool unterstützt IPv4-und IPv6-Adressen) und dem FQDN angezeigt.

## <a name="see-also"></a>Siehe auch
<a name="Optional_Software"> </a>

[Installing the Planning Tool](https://technet.microsoft.com/library/ebdc9e26-4b22-4b02-85b9-7462bcfe7c93.aspx)
