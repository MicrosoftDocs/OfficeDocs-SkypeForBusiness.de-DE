---
title: Installieren des Planungstools in Skype for Business Server 2015
ms.reviewer: null
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 4/5/2016
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
  - NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.assetid: b95b3301-fa1e-4b96-9af4-05b43d39db8d
description: 'Bevor Sie mit dem Entwerfen und Planen Ihrer Skype for Business Server 2015-Infrastruktur mithilfe des Skype for Business Server 2015-Planungstools beginnen, müssen Sie zuerst das Planungstool installieren. Das Planungstool muss nicht auf einer Arbeitsstation oder einem Server bereitgestellt werden, die Teil der Domäne oder Infrastruktur ist, in der Sie Skype for Business Server 2015 installieren möchten. Die Infodatei, die das Planungstool begleitet, enthält wichtige Informationen zur Installation und Verwendung des Tools. Einige der Informationen in der Infodatei werden hier aus Gründen der Übersichtlichkeit dupliziert.'
---

# <a name="install-the-planning-tool-in-skype-for-business-server-2015"></a>Installieren des Planungstools in Skype for Business Server 2015

Bevor Sie mit dem Entwerfen und Planen Ihrer Skype for Business Server 2015-Infrastruktur mithilfe des Skype for Business Server 2015-Planungstools beginnen, müssen Sie zuerst das Planungstool installieren. Das Planungstool muss nicht auf einer Arbeitsstation oder einem Server bereitgestellt werden, die Teil der Domäne oder Infrastruktur ist, in der Sie Skype for Business Server 2015 installieren möchten. Die Infodatei, die das Planungstool begleitet, enthält wichtige Informationen zur Installation und Verwendung des Tools. Einige der Informationen in der Infodatei werden hier aus Gründen der Übersichtlichkeit dupliziert.

> [!IMPORTANT]
> Das Planungstool erfordert die Installation durch einen Benutzer mit Administratorrechten und Berechtigungen auf dem Computer, auf dem das Tool installiert werden soll.

Die unterstützten Betriebssysteme für die Installation und den Betrieb des Planungstools sind:

- Windows 10

- Windows 8

- Windows 8.1

- Windows Server 2012

- Windows Server 2012 R2

- Windows 7- und 32-Bit-Edition

- Windows 7- und 64-Bit-Edition mit Windows auf Win32 (WOW)

- Windows Server 2008 R2 mit WOW

Darüber hinaus erfordert das Planungstool Microsoft .NET Framework 4.5.

Nachdem die Vorinstallationsanforderungen erfüllt sind, können Sie das Planungstool installieren.



## <a name="to-install-the-planning-tool"></a>So installieren Sie das Planungstool

1. Melden Sie sich beim lokalen Computer als Mitglied der Gruppe "Administratoren" an.

2. Suchen Sie mit Windows Explorer oder einem Befehlsfenster nach dem Verzeichnis, in das Sie die Installationsdateien des Planungstools heruntergeladen haben.

3. Suchen Sie die SkypeForBusinessPlanningTool.msi. Doppelklicken Sie im Windows Explorer auf die Datei. Geben Sie im Befehlsfenster den Namen der Datei ein, und drücken Sie dann die **EINGABETASTE** , um die Datei auszuführen.

4. Klicken Sie auf der Willkommensseite des **Setup-Assistenten Skype for Business Server 2015** auf **"Weiter**".

5. Überprüfen Sie den **Endbenutzer-Lizenzvertrag**, wählen Sie **"Ich stimme den Bedingungen im Lizenzvertrag** zu, wenn Sie die Nutzungsbedingungen im Lizenzvertrag akzeptieren", und klicken Sie dann auf **"Weiter**".

6. Wählen Sie aus, wo die Dateien des Planungstools installiert werden sollen. Der Standardspeicherort lautet "C:\Programme (x86)\Skype for Business Server 2015\Planning Tool". Wenn Sie den Installationsspeicherort ändern möchten, klicken Sie auf **"Ändern**". Navigieren **Oder geben Sie im Ordner "Ziel ändern**" den Speicherort für die Installation der Dateien ein, klicken Sie auf **"OK**" und dann auf **"Weiter**".

7. Das Installationsprogramm kann nun das Planungstool installieren. Klicken Sie auf **"Installieren** ", um den Installationsvorgang zu starten.

8. Die Installation wird gestartet, und der Fortschritt wird angezeigt. Klicken Sie nach dem erfolgreichen Abschluss der Installation auf **"Fertig stellen**".

9. Das Planungstool ist einsatzbereit.

## <a name="optional-software"></a>Optionale Software
<a name="Optional_Software"> </a>

Das Skype for Business Server 2015-Planungstool wurde entwickelt, um nach Microsoft Excel und Microsoft Visio zu exportieren. Obwohl diese Anwendungen für den Betrieb des Planungstools nicht erforderlich sind, tragen sie erheblich zur Bereitstellung und Dokumentation Ihres Entwurfs bei.

### <a name="microsoft-excel"></a>Microsoft Excel

Wenn Sie Ihr Design in Microsoft Excel exportieren, wird ein Bericht erstellt, in dem sieben Registerkarten in der Tabelle angezeigt werden:

- Zusammenfassung : Zeigt Informationen zur Standortkonfiguration an, einschließlich Benutzeranzahl, Kapazitätseinstellungen und Serverprofilinformationen.

- Hardwareprofil : Zeigt einen Bericht zu den empfohlenen Hardwarekonfigurationen für Server an, die in der Topologie angegeben sind, einschließlich CPU, Arbeitsspeicher, Datenträger und Netzwerkschnittstelle. Die Menge und die empfohlenen Spezifikationen für die Serverkomponenten sind ebenfalls enthalten. Darüber hinaus wird jeder Server nach Standort definiert, um eine vollständige Darstellung der Serveranforderungen nach Standort bereitzustellen.

- Ports requirements - Zeigt einen Bericht aller ports, die aktiviert sind, und die Zuordnung zum Domain Name System Load Balancing (DNS LB) und Hardware Load Balancers (HLB) an. Sie sollten diesen Bericht verwenden, um Ihre Firewall- und DNS-LB- und HLB-Konfigurationen zu planen.

- Zusammenfassungsbericht : Zeigt die allgemeine Zusammenfassung der Einstellungen an, die zum Einrichten des Edgeservernetzwerks erforderlich sind.

- Zertifikatbericht : Zeigt den Antragstellernamen und alternative Antragstellernamen an, die für die Zertifikate erforderlich sind, um die Edgeserver auszuführen.

- Firewallbericht : Zeigt die Quell- und Zielports und IP-Adressen für externe und interne Schnittstellen an.

- DNS-Bericht : Zeigt den vollqualifizierten Domänennamen (FQDN) und die IP-/VIP-Adressen an, die für jeden von Ihnen erstellten DNS-Eintrag erforderlich sind.

### <a name="microsoft-visio"></a>Microsoft Visio

Beim Exportieren Ihres Entwurfs nach Microsoft Visio wird ein Diagramm erstellt, das Sie zur Dokumentation Ihrer konfigurierten Topologie und Infrastruktur verwenden können. Das importierte Diagramm kann bearbeitet und neu angeordnet werden, um Ihre Dokumentationsanforderungen zu erfüllen. Das typische Visio-Diagramm umfasst Folgendes:

> [!NOTE]
> Wenn Ihr Entwurf so groß ist, dass mehr als drei Front-End-Server erforderlich sind, wird eine zusätzliche Seite für den Front-End-Pool, die Front-End-Server, den Computer mit SQL Server, IP-Adressen und FQDNs erstellt.

- Globale Topologie – Diagramm der konfigurierten Skype for Business Server 2015-Standorte.

- Registerkarte "Standortname": Zeigt die Standortkonfigurationstopologie mit Edgeserver, Firewall, PSTN (Public Switched Telephone Network) mit Gateways und die interne Serverbereitstellung an. Die interne Bereitstellung besteht aus konfigurierten Servern und Pools, einschließlich der Front-End-Pools, SQL Server-basierten Servern, Active Directory Domain Services, Directors, Exchange Unified Messaging(UM)-Servern, Exchange Postfachservern, Office Web Apps-Servern, Vermittlungsservern und Servern für beständigen Chat.

- Edgenetzwerkdiagramm – Diagramm, das die Edgeserverkonfiguration mit den zugeordneten IP-Adressen und FQDNs angibt. DNS-Lastenausgleich und Hardwarelastenausgleich sind ebenfalls enthalten. Darüber hinaus werden Directors und der Front-End-Server oder Front-End-Pool mit zugeordneter DNS-Lb- oder HLB-Adresse und der zugewiesenen IP-Adresse (das Planungstool unterstützt sowohl IPv4- als auch IPv6-Adressen) und FQDN angezeigt.

## <a name="see-also"></a>Siehe auch
<a name="Optional_Software"> </a>

[Installieren des Planungstools](/previous-versions/office/lync-server-2013/lync-server-2013-installing-the-planning-tool)