---
title: Installieren des Planungstools in Skype for Business Server 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 4/5/2016
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: b95b3301-fa1e-4b96-9af4-05b43d39db8d
description: Vor Beginn entwerfen und planen Ihre Skype für Business Server 2015 Infrastruktur mithilfe der Skype für Business Server 2015-Planungstool, Sie müssen zuerst installieren das Planungstool. Das Planungstool muss nicht bereitgestellt werden, auf einer Arbeitsstation oder einem Server, der Teil der Domäne oder der Infrastruktur, in der Sie Skype für Business Server 2015 installieren möchten. Die Planungstool gehörenden Infodatei enthält wichtige Informationen zur Installation und Verwendung des Tools. Einige Informationen aus dieser Datei werden zur Verdeutlichung im Folgenden noch einmal aufgeführt.
ms.openlocfilehash: 64d510eedc01149e7119e3ec92ea09cd9a6c842a
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "33915024"
---
# <a name="install-the-planning-tool-in-skype-for-business-server-2015"></a>Installieren des Planungstools in Skype for Business Server 2015

Vor Beginn entwerfen und planen Ihre Skype für Business Server 2015 Infrastruktur mithilfe der Skype für Business Server 2015-Planungstool, Sie müssen zuerst installieren das Planungstool. Das Planungstool muss nicht bereitgestellt werden, auf einer Arbeitsstation oder einem Server, der Teil der Domäne oder der Infrastruktur, in der Sie Skype für Business Server 2015 installieren möchten. Die Planungstool gehörenden Infodatei enthält wichtige Informationen zur Installation und Verwendung des Tools. Einige Informationen aus dieser Datei werden zur Verdeutlichung im Folgenden noch einmal aufgeführt.

> [!IMPORTANT]
> Das Planungstool erfordert Installation von einem Benutzer mit Administratorrechten und-Berechtigungen auf dem Computer, auf dem das Tool installiert werden.

Die unterstützten Betriebssysteme für Installation und Verwendung des Planungstool sind:

- Windows 10

- Windows 8

- Windows 8,1

- Windows Server 2012

- Windows Server 2012 R2

- Windows 7, 32-Bit-Version

- Windows 7, 64-Bit-Version unter Verwendung von Windows on Win32 (WOW)

- Windows Server 2008 R2 unter Verwendung von WOW

Darüber hinaus erfordert das Planungstool für Microsoft .NET Framework 4.5.

Wenn die Vorinstallation Anforderungen erfüllt sind, können Sie dann das Planungstool installieren.



## <a name="to-install-the-planning-tool"></a>So installieren Sie das Planungstool

1. Melden Sie sich auf dem lokalen Computer als Mitglied der Gruppe "Administratoren" an.

2. Verwenden Sie Windows Explorer oder ein Befehlsfenster, suchen Sie das Verzeichnis, in dem Sie die Planungstool-Installationsdateien heruntergeladen haben.

3. Suchen Sie die Datei SkypeForBusinessPlanningTool.msi. Machen Sie im Windows Explorer einen Doppelklick auf die Datei. Geben Sie im Befehlsfenster den Namen der Datei ein und drücken Sie die **Eingabetaste**, um die Datei auszuführen.

4. Klicken Sie auf der Willkommensseite des Setup-Assistenten für das **Skype for Business Server 2015-Planungstool** auf **Weiter**.

5. Lesen Sie den **Endbenutzer-Lizenzvertrag**, wählen Sie die Option **Ich stimme den Bedingungen des Lizenzvertrags zu** aus, sofern Sie die Bedingungen akzeptieren, und klicken Sie anschließend auf **Weiter**.

6. Geben Sie an, in welchem Verzeichnis die Dateien des Planungstools installiert werden sollen. Der Standardspeicherort lautet „C:\Programme (x86)\Skype for Business Server 2015\Planning Tool“. Wenn Sie ein anderes Installationsverzeichnis auswählen möchten, klicken Sie auf **Ändern**. Navigieren Sie im Dialogfeld **Zielordner ändern** zum gewünschten Verzeichnis oder geben Sie ein Verzeichnis ein und klicken Sie nacheinander auf **OK** und auf **Weiter**.

7. Der Installer ist jetzt so installieren Sie das Planungstool bereit. Klicken Sie auf **Installieren**, um den Installationsvorgang zu starten.

8. Die Installation beginnt und der Installationsfortschritt wird angezeigt. Klicken Sie nach Abschluss der Installation auf **Fertigstellen**.

9. Das Planungstool ist für die Verwendung bereit.

## <a name="optional-software"></a>Optionale Software
<a name="Optional_Software"> </a>

Die Skype für Business Server 2015 Planungstool dient zum Exportieren nach Microsoft Excel und Microsoft Visio. Während dieser Anwendungen nicht für den Betrieb von Planungstool erforderlich sind, sie die Bereitstellung und die Dokumentation des Entwurfs erhebliche Wert hinzufügen.

### <a name="microsoft-excel"></a>Microsoft Excel

Beim Exportieren Ihres Entwurfs nach Microsoft Excel wird ein Bericht in Form einer Tabelle mit sieben Registerkarten erstellt:

- Zusammenfassung: Zeigt Informationen auf Standortkonfiguration, einschließlich Benutzeranzahl, Einstellungen für die Ressourcenkapazität und Profilinformationen Server.

- Hardware-Profil - zeigt einen Bericht zu den empfohlenen Hardwarekonfigurationen für Server, die in der Topologie, einschließlich CPU, Arbeitsspeicher, Festplatten und Netzwerkschnittstelle angegeben sind. Die Anzahl und die empfohlenen Spezifikationen für die Serverkomponenten sind auch enthalten. Darüber hinaus ist jeder Server nach Standort definiert, um eine vollständige Darstellung der Serveranforderungen nach Standort bereitzustellen.

- Anforderungen an Ports - Bericht für alle Ports, die aktiviert sind und die Zuordnung zu Domain Name System-Lastenausgleich (DNS-kg) und Hardwaregeräten zum Lastenausgleich (Hardwarelastenausgleich) angezeigt. Sie sollten diesen Bericht zum Planen der Konfiguration von Firewall sowie DNS-Lastenausgleich und Hardwaregeräten zum Lastenausgleich verwenden.

- Zusammenfassungsbericht - zeigt die allgemeine Zusammenfassung der Einstellungen, die zum Einrichten eines Netzwerks Edge-Server erforderlich sind.

- Zertifikatbericht – zeigt den Antragstellernamen und alternative Antragstellernamen, die für die Zertifikate erforderlich, um den Edge-Servern mit abrufen erforderlich sind.

- Bericht - zeigt die Quell- und Ziel-Ports und IP-Adressen für externe und interne Schnittstellen Firewall.

- DNS-Bericht - zeigt den vollqualifizierten Domänennamen (FQDN) und IP-Adresse/VIP-Adressen erforderlich für jeden DNS-Eintrag, zu erstellen.

### <a name="microsoft-visio"></a>Microsoft Visio

Beim Exportieren Ihres Entwurfs nach Microsoft Visio wird ein Diagramm erstellt, das Sie zur Dokumentation Ihrer konfigurierten Topologie und Infrastruktur verwenden können. Das importierte Diagramm kann bearbeitet und neu angeordnet werden, um Ihre Dokumentationsanforderungen zu erfüllen. Das typische Visio-Diagramm umfasst Folgendes:

> [!NOTE]
> Wenn Ihr Entwurf groß genug für mehr als drei Front-End-Servern erforderlich ist, wird eine zusätzliche Seite für den Front-End-Pool Front-End-Server, dem Computer mit SQL Server, IP-Adressen und FQDNs erstellt werden.

- Globale Topologie – Diagramm der konfigurierten Skype für Business Server 2015 Websites.

- Registerkarte Site-Name - Telefon zeigt die Standorttopologie Konfiguration mit Edge-Server, Firewall, Public Switched Telephone Network (PSTN)-Gateways und der interne Server-Bereitstellung. Interne Bereitstellung besteht der konfigurierten Server und Pools, einschließlich der Front-End-pools, Directors für den SQL Server-basierten Server Active Directory Domain Services, Exchange Unified Messaging (UM) Server, Exchange-Postfachserver, Office Web Apps-Server, Vermittlungsserver und Server für beständigen Chat.

- Edge-Netzplandiagramm - Diagramm mit ausführlichen Informationen zu den Edge-Server-Konfiguration mit zugeordneten IP-Adressen und FQDNs. DNS-Lastenausgleich und Hardwarelastenausgleich sind ebenfalls enthalten. Darüber hinaus werden von Directors und dem Front-End-Server oder Front-End-Pool angezeigt, mit zugeordneten DNS kg oder Hardwaregeräts zum Lastenausgleich und die zugeordnete IP-Adresse (das Planungstool unterstützt sowohl IPv4 als auch IPv6-Adressen) und den FQDN.

## <a name="see-also"></a>Siehe auch
<a name="Optional_Software"> </a>

[Installing the Planning Tool](https://technet.microsoft.com/library/ebdc9e26-4b22-4b02-85b9-7462bcfe7c93.aspx)
