---
title: Netzwerkeinstellungen für die erweiterten Enterprise-VoIP-Features in Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 7f6de9e4-c8a4-44e4-8d14-21fe8c45283a
description: Erfahren Sie mehr über Netzwerkregionen, Netzwerkstandorte und IP-Subnetze. All diese Elemente müssen so konfiguriert sein, dass der Plan für die Medienumgehung in Skype for Business, die Planung der Anrufsteuerung in Skype for Business Server) oder die Planung von Notrufdiensten in Skype for Business Server in Skype for Business Server Enterprise-VoIP bereitgestellt wird.
ms.openlocfilehash: 97cf81bb3efa9aa5d4b8717018232d479fcbf2c3
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/26/2021
ms.locfileid: "58608002"
---
# <a name="network-settings-for-the-advanced-enterprise-voice-features-in-skype-for-business-server"></a>Netzwerkeinstellungen für die erweiterten Enterprise-VoIP-Features in Skype for Business Server

Erfahren Sie mehr über Netzwerkregionen, Netzwerkstandorte und IP-Subnetze. Alle diese Müssen so konfiguriert sein, dass [der Plan für die Medienumgehung in Skype for Business,](media-bypass.md)die Planung der [Anrufsteuerung in Skype for Business Server](call-admission-control.md)oder die Planung von [Notrufdiensten in Skype for Business Server](emergency-services.md) in Skype for Business Server Enterprise-VoIP bereitgestellt wird.

Skype for Business Server verfügt über drei erweiterte Enterprise-VoIP Features: [Planen der Anrufsteuerung in Skype for Business Server,](call-admission-control.md) [Planen von Notrufdiensten in Skype for Business Server](emergency-services.md)und Planen der [Medienumgehung in Skype for Business](media-bypass.md). Diese Features teilen bestimmte Konfigurationsanforderungen für Netzwerkregionen, Netzwerkstandorte und die Zuordnung jedes Subnetzes in der Skype for Business Server Topologie mit einem Netzwerkstandort.

Dieses Thema bietet eine Übersicht über die Konfigurationsanforderungen, die für alle drei dieser erweiterten Enterprise-VoIP Features gelten.

## <a name="network-regions"></a>Netzwerkregionen

Bei einer Netzwerkregion handelt es sich um einen Netzwerkhub oder Netzwerkbackbone, der ausschließlich in der Konfiguration von Anrufsteuerung (Call Admission Control, CAC), E9-1-1 und Medienumgehung verwendet wird.

> [!NOTE]
> Netzwerkregionen sind nicht mit Skype for Business Server Regionen für Einwahlkonferenzen identisch, die erforderlich sind, um Zugriffsnummern für Einwahlkonferenzen einem oder mehreren Skype for Business Server Wählplänen zuzuordnen. Ausführliche Informationen zu Regionen für Einwahlkonferenzen finden Sie unter ["Planen von Einwahlkonferenzen".](/previous-versions/office/lync-server-2013/lync-server-2013-dial-in-conferencing-requirements)

Die Anrufsteuerung erfordert, dass jede Netzwerkregion über einen zugeordneten Skype for Business Server zentralen Standort verfügt, der den Mediendatenverkehr innerhalb der Region verwaltet (d. a. er trifft Entscheidungen basierend auf von Ihnen konfigurierten Richtlinien, um zu bestimmen, ob eine Audio- oder Videositzung in Echtzeit eingerichtet werden kann). Skype for Business Server zentralen Standorte stellen keine geografischen Standorte dar, sondern logische Servergruppen, die als Pool oder Poolgruppe konfiguriert sind.

Zum Konfigurieren einer Netzwerkregion können Sie entweder die Registerkarte **"Regionen"** im Abschnitt **"Netzwerkkonfiguration"** von Skype for Business Server Systemsteuerung verwenden oder die Cmdlets **"New-CsNetworkRegion"** oder **"Set-CsNetworkRegion"** Skype for Business Server Verwaltungsshell ausführen. Anweisungen finden Sie unter [Bereitstellen von Netzwerkregionen, Standorten und Subnetzen in Skype for Business](../../deploy/deploy-enterprise-voice/deploy-network.md) in der Bereitstellungsdokumentation oder in der Dokumentation zur Skype for Business Server Verwaltungsshell.

Die gleichen Netzwerkregionendefinitionen werden von allen drei erweiterten Enterprise-VoIP-Features gemeinsam verwendet. Wenn Sie bereits Netzwerkregionen für eine Funktion erstellt haben, müssen Sie keine neuen Netzwerkregionen für die anderen Funktionen erstellen. Sie müssen jedoch möglicherweise eine vorhandene Definition einer Netzwerkregion ändern, um funktionsspezifische Einstellungen anzuwenden. Wenn Sie z. B. Netzwerkregionen für E9-1-1 erstellt haben (denen kein zentraler Standort zugeordnet werden muss) und Sie zu einem späteren Zeitpunkt die Anrufsteuerung bereitstellen, müssen Sie die Definitionen der Netzwerkregionen ändern und einen zentralen Standort angeben.

Um einen Skype for Business Server zentralen Standort einer Netzwerkregion zuzuordnen, geben Sie den Namen des zentralen Standorts an, entweder über den Abschnitt **"Netzwerkkonfiguration"** in Skype for Business Server Systemsteuerung oder durch Ausführen der Cmdlets **"New-CsNetworkRegion"** oder **"Set-CsNetworkRegion".** Anweisungen finden Sie unter [Bereitstellen von Netzwerkregionen, Standorten und Subnetzen in Skype for Business](../../deploy/deploy-enterprise-voice/deploy-network.md) in der Bereitstellungsdokumentation oder in der Dokumentation zur Skype for Business Server Verwaltungsshell.

## <a name="network-sites"></a>Netzwerkstandorte

Ein Netzwerkstandort stellt einen geografischen Standort dar, z. B. ein Zweigstellenbüro, ein regionales Büro oder ein Hauptbüro. Jeder Netzwerkstandort muss einer bestimmten Netzwerkregion zugeordnet sein.

> [!NOTE]
> Netzwerkstandorte werden nur von den erweiterten Enterprise-VoIP-Features verwendet. Sie sind nicht identisch mit den Zweigstellen, die Sie in Ihrer Skype for Business Server-Topologie konfigurieren.

Um einen Netzwerkstandort zu konfigurieren und einer Netzwerkregion zuzuordnen, können Sie entweder den Abschnitt **"Netzwerkkonfiguration"** in Skype for Business Server Systemsteuerung verwenden oder die Cmdlets **"New-CsNetworkSite"** oder **"Set-CsNetworkSite"** Skype for Business Server Verwaltungsshell ausführen. Ausführliche Informationen finden Sie unter ["Erstellen oder Ändern eines Netzwerkstandorts"](/previous-versions/office/lync-server-2013/lync-server-2013-create-or-modify-a-network-site) in der Bereitstellungsdokumentation oder in der Dokumentation zur Skype for Business Server Verwaltungsshell.

## <a name="identify-ip-subnets"></a>Identifizieren von IP-Subnetzen

Arbeiten Sie mit Ihrem Netzwerkadministrator zusammen, um zu ermitteln, welche IP-Subnetze jedem Netzwerkstandort zugewiesen sind. Wenn Ihr Netzwerkadministrator die IP-Subnetze bereits in Netzwerkregionen und Netzwerkstandorte unterteilt hat, wird diese Aufgabe erheblich vereinfacht.

Zum Beispiel können dem Standort "New York" in der Region "Nordamerika" die folgenden IP-Subnetze zugewiesen werden: 172.29.80.0/23, 157.57.216.0/25, 172.29.91.0/23, 172.29.81.0/24. Wenn der Benutzer Bob, der üblicherweise in Detroit arbeitet, für eine Schulung in das New Yorker Büro reist, seinen Computer einschaltet und sich mit dem Netzwerk verbindet, erhält sein Computer eine IP-Adresse aus einem der vier Bereiche, die für "New York" zugewiesen sind, beispielsweise die Adresse 172.29.80.103.

> [!CAUTION]
> Die während der Netzwerkkonfiguration auf dem Server angegebenen IP-Subnetze müssen dem Format entsprechen, das von Clientcomputern bereitgestellt wird, damit eine ordnungsgemäße Verwendung für die Medienumgehung gewährleistet ist. Ein Skype for Business Client verwendet seine lokale IP-Adresse und maskiert die IP-Adresse mit der zugeordneten Subnetzmaske. Bei Ermittlung der Umgehungs-ID für jeden Client vergleicht die Registrierung die Liste der IP-Subnetze für jeden Netzwerkstandort mit dem vom Client bereitgestellten Subnetz, um eine exakte Übereinstimmung zu ermitteln. Aus diesem Grund ist es wichtig, dass es sich bei den während der Netzwerkkonfiguration auf dem Server eingegebenen Subnetzen nicht um virtuelle, sondern um tatsächliche Subnetze handelt. (Wenn Sie die Anrufsteuerung, aber keine Medienumgehung bereitstellen, funktioniert die Anrufsteuerung auch dann ordnungsgemäß, wenn Sie virtuelle Subnetze konfigurieren.) Wenn sich ein Skype for Business Client beispielsweise auf einem Computer mit der IP-Adresse 172.29.81.57 mit der IP-Subnetzmaske 255.255.255.0 anmeldet, fordert er die Umgehungs-ID an, die subnetz 172.29.81.0 zugeordnet ist. Wenn das Subnetz als 172.29.0.0/16 definiert ist, betrachtet die Registrierung dies – wenngleich der Client dem virtuellen Subnetz angehört – nicht als Übereinstimmung, da die Registrierung ausschließlich nach Subnetz 172.29.81.0 sucht. Daher ist es wichtig, dass der Administrator Subnetze genau wie von Skype for Business Clients bereitstellt (die während der Netzwerkkonfiguration entweder statisch oder über DHCP (Dynamic Host Configuration Protocol) mit Subnetzen bereitgestellt werden).

## <a name="associating-subnets-with-network-sites"></a>Zuordnen von Subnetzen zu Netzwerkstandorten

Jedes Subnetz im Unternehmensnetzwerk muss einem Netzwerkstandort zugeordnet sein (d. a. jedes Subnetz muss einem geografischen Standort zugeordnet sein). Diese Zuordnung von Subnetzen ermöglicht es den erweiterten Enterprise-VoIP Features, die Endpunkte geografisch zu lokalisieren. Durch die Suche nach den Endpunkten kann die Anrufsteuerung beispielsweise den Fluss von Audio- und Videodaten in Echtzeit steuern, die zum und vom Netzwerkstandort gesendet werden.

Zum Zuordnen von Subnetzen zu Netzwerkstandorten können Sie entweder den Abschnitt **"Netzwerkkonfiguration"** in Skype for Business Server Systemsteuerung oder die Skype for Business Server-Verwaltungsshell verwenden. Anweisungen finden Sie unter ["Zuordnen eines Subnetzes zu einem Netzwerkstandort"](/previous-versions/office/lync-server-2013/lync-server-2013-associate-a-subnet-with-a-network-site) in der Bereitstellungsdokumentation oder in der Dokumentation zur Skype for Business Server Verwaltungsshell.

## <a name="see-also"></a>Siehe auch

[Planen der Anrufsteuerung in Skype for Business Server](call-admission-control.md)

[Planen von Notrufdiensten in Skype for Business Server](emergency-services.md)

[Planen der Medienumgehung in Skype for Business](media-bypass.md)