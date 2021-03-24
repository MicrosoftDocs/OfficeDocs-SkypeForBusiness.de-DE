---
title: Netzwerkeinstellungen für die erweiterten Enterprise-VoIP in Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 7f6de9e4-c8a4-44e4-8d14-21fe8c45283a
description: Erfahren Sie mehr über Netzwerkregionen, Netzwerkstandorte und IP-Subnetze. Alle diese Müssen so konfiguriert sein, dass sie plan for media bypass in Skype for Business, Plan for call admission control in Skype for Business Server oder Plan for emergency services in Skype for Business Server in Skype for Business Server Enterprise-VoIP.
ms.openlocfilehash: 4cedfa6b425bd120a62997d02548d57ce5d619b4
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51101291"
---
# <a name="network-settings-for-the-advanced-enterprise-voice-features-in-skype-for-business-server"></a>Netzwerkeinstellungen für die erweiterten Enterprise-VoIP in Skype for Business Server

Erfahren Sie mehr über Netzwerkregionen, Netzwerkstandorte und IP-Subnetze. Alle diese Müssen so konfiguriert sein, dass sie plan [for media bypass in Skype for Business,](media-bypass.md)Plan for call admission control in Skype for Business [Server](call-admission-control.md)oder Plan for emergency services in Skype for [Business Server](emergency-services.md) in Skype for Business Server Enterprise-VoIP.

Skype for Business Server verfügt über drei erweiterte Enterprise-VoIP-Features: Planen der Anrufsteuerung [in Skype for Business Server,](call-admission-control.md)Plan for emergency services in Skype for Business [Server](emergency-services.md)und Plan for media bypass in Skype [for Business](media-bypass.md). Diese Features teilen bestimmte Konfigurationsanforderungen für Netzwerkregionen, Netzwerkstandorte und die Zuordnung der einzelnen Subnetze in der Skype for Business Server-Topologie mit einem Netzwerkstandort.

Dieses Thema bietet eine Übersicht über die Konfigurationsanforderungen, die für alle drei dieser erweiterten Features Enterprise-VoIP sind.

## <a name="network-regions"></a>Netzwerkregionen

Bei einer Netzwerkregion handelt es sich um einen Netzwerkhub oder Netzwerkbackbone, der ausschließlich in der Konfiguration von Anrufsteuerung (Call Admission Control, CAC), E9-1-1 und Medienumgehung verwendet wird.

> [!NOTE]
> Netzwerkregionen sind nicht identisch mit Skype for Business Server-Einwahlkonferenzregionen, die zum Zuordnen von Zugriffsnummern für Einwahlkonferenzen mit einem oder mehreren Skype for Business Server-Wählplänen erforderlich sind. Weitere Informationen zu Einwahlkonferenzregionen finden Sie unter [Planning for Dial-In Conferencing](/previous-versions/office/lync-server-2013/lync-server-2013-dial-in-conferencing-requirements).

Für jede Netzwerkregion muss ein zentraler Skype for Business Server-Standort vorhanden sein, der den Mediendatenverkehr innerhalb der Region verwaltet (d. h., sie trifft Entscheidungen basierend auf von Ihnen konfigurierten Richtlinien, ob eine Audio- oder Videositzung in Echtzeit eingerichtet werden kann). Zentrale Skype for Business Server-Standorte stellen keine geografischen Standorte dar, sondern logische Servergruppen, die als Pool oder als Poolgruppe konfiguriert sind.

Zum Konfigurieren einer Netzwerkregion können  Sie entweder  die Registerkarte Regionen im Abschnitt Netzwerkkonfiguration der Skype for Business Server-Systemsteuerung verwenden oder die **Cmdlets New-CsNetworkRegion** oder **Set-CsNetworkRegion** Skype for Business Server Management Shell ausführen. Anweisungen finden Sie unter Bereitstellen von [Netzwerkregionen, Standorten](../../deploy/deploy-enterprise-voice/deploy-network.md) und Subnetzen in Skype for Business in der Bereitstellungsdokumentation oder in der Dokumentation zur Skype for Business Server Management Shell.

Dieselben Netzwerkregionsdefinitionen werden von allen drei erweiterten Enterprise-VoIP gemeinsam verwendet. Wenn Sie bereits Netzwerkregionen für eine Funktion erstellt haben, müssen Sie keine neuen Netzwerkregionen für die anderen Funktionen erstellen. Sie müssen jedoch möglicherweise eine vorhandene Definition einer Netzwerkregion ändern, um funktionsspezifische Einstellungen anzuwenden. Wenn Sie z. B. Netzwerkregionen für E9-1-1 erstellt haben (denen kein zentraler Standort zugeordnet werden muss) und Sie zu einem späteren Zeitpunkt die Anrufsteuerung bereitstellen, müssen Sie die Definitionen der Netzwerkregionen ändern und einen zentralen Standort angeben.

Zum Zuordnen eines zentralen Skype for Business Server-Standorts zu einer Netzwerkregion geben Sie den zentralen Standortnamen an, entweder mithilfe des Abschnitts Netzwerkkonfiguration der Skype for Business Server-Systemsteuerung oder durch Ausführen der **Cmdlets New-CsNetworkRegion** oder **Set-CsNetworkRegion.**  Anweisungen finden Sie unter Bereitstellen von [Netzwerkregionen, Standorten](../../deploy/deploy-enterprise-voice/deploy-network.md) und Subnetzen in Skype for Business in der Bereitstellungsdokumentation oder in der Dokumentation zur Skype for Business Server Management Shell.

## <a name="network-sites"></a>Netzwerkstandorte

Ein Netzwerkstandort stellt einen geografischen Standort dar, z. B. ein Zweigstellenbüro, ein regionales Büro oder ein Hauptbüro. Jeder Netzwerkstandort muss einer bestimmten Netzwerkregion zugeordnet sein.

> [!NOTE]
> Netzwerkstandorte werden nur von den erweiterten Enterprise-VoIP verwendet. Sie sind nicht mit den Zweigstellenstandorten identisch, die Sie in Ihrer Skype for Business Server-Topologie konfigurieren.

Um einen Netzwerkstandort zu konfigurieren und einer Netzwerkregion  zuzuordnen, können Sie entweder den Abschnitt Netzwerkkonfiguration der Skype for Business Server-Systemsteuerung verwenden oder die Skype for Business Server Management Shell **New-CsNetworkSite** oder **Set-CsNetworkSite-Cmdlets** ausführen. Ausführliche Informationen finden Sie unter [Create or Modify a Network Site](/previous-versions/office/lync-server-2013/lync-server-2013-create-or-modify-a-network-site) in der Bereitstellungsdokumentation oder in der Dokumentation zur Skype for Business Server Management Shell.

## <a name="identify-ip-subnets"></a>Identifizieren von IP-Subnetzen

Arbeiten Sie mit Ihrem Netzwerkadministrator zusammen, um zu ermitteln, welche IP-Subnetze jedem Netzwerkstandort zugewiesen sind. Wenn Ihr Netzwerkadministrator die IP-Subnetze bereits in Netzwerkregionen und Netzwerkstandorte unterteilt hat, wird diese Aufgabe erheblich vereinfacht.

Zum Beispiel können dem Standort "New York" in der Region "Nordamerika" die folgenden IP-Subnetze zugewiesen werden: 172.29.80.0/23, 157.57.216.0/25, 172.29.91.0/23, 172.29.81.0/24. Wenn der Benutzer Bob, der üblicherweise in Detroit arbeitet, für eine Schulung in das New Yorker Büro reist, seinen Computer einschaltet und sich mit dem Netzwerk verbindet, erhält sein Computer eine IP-Adresse aus einem der vier Bereiche, die für "New York" zugewiesen sind, beispielsweise die Adresse 172.29.80.103.

> [!CAUTION]
> Die während der Netzwerkkonfiguration auf dem Server angegebenen IP-Subnetze müssen dem Format entsprechen, das von Clientcomputern bereitgestellt wird, damit eine ordnungsgemäße Verwendung für die Medienumgehung gewährleistet ist. Ein Skype for Business-Client verwendet seine lokale IP-Adresse und maskiert die IP-Adresse mit der zugeordneten Subnetzmaske. Bei Ermittlung der Umgehungs-ID für jeden Client vergleicht die Registrierung die Liste der IP-Subnetze für jeden Netzwerkstandort mit dem vom Client bereitgestellten Subnetz, um eine exakte Übereinstimmung zu ermitteln. Aus diesem Grund ist es wichtig, dass es sich bei den während der Netzwerkkonfiguration auf dem Server eingegebenen Subnetzen nicht um virtuelle, sondern um tatsächliche Subnetze handelt. (Wenn Sie die Anrufsteuerung, aber keine Medienumgehung bereitstellen, funktioniert die Anrufsteuerung auch dann ordnungsgemäß, wenn Sie virtuelle Subnetze konfigurieren.) Wenn sich beispielsweise ein Skype for Business-Client auf einem Computer mit der IP-Adresse 172.29.81.57 mit der IP-Subnetzmaske 255.255.255.0 einschreibt, wird die Umgehungs-ID anfordern, die dem Subnetz 172.29.81.0 zugeordnet ist. Wenn das Subnetz als 172.29.0.0/16 definiert ist, betrachtet die Registrierung dies – wenngleich der Client dem virtuellen Subnetz angehört – nicht als Übereinstimmung, da die Registrierung ausschließlich nach Subnetz 172.29.81.0 sucht. Daher ist es wichtig, dass der Administrator Subnetze genau wie von Skype for Business-Clients bereitgestellt betritt (die während der Netzwerkkonfiguration mit Subnetzen bereitgestellt werden, entweder statisch oder durch DHCP (Dynamic Host Configuration Protocol).

## <a name="associating-subnets-with-network-sites"></a>Zuordnen von Subnetzen zu Netzwerkstandorten

Jedes Subnetz im Unternehmensnetzwerk muss einem Netzwerkstandort zugeordnet sein (d. h. jedes Subnetz muss einem geografischen Standort zugeordnet sein). Diese Zuordnung von Subnetzen ermöglicht es den erweiterten Enterprise-VoIP, die Endpunkte geografisch zu finden. Beispielsweise ermöglicht das Suchen der Endpunkte die Cac-Funktion, um den Fluss von Audio- und Videodaten in Echtzeit zu und vom Netzwerkstandort zu regeln.

Zum Zuordnen von Subnetzen zu Netzwerkstandorten können Sie entweder den Abschnitt Netzwerkkonfiguration der Skype for Business Server-Systemsteuerung verwenden oder die Skype for Business Server-Verwaltungsshell verwenden.  Anweisungen finden Sie unter [Zuordnen eines Subnetzes](/previous-versions/office/lync-server-2013/lync-server-2013-associate-a-subnet-with-a-network-site) zu einem Netzwerkstandort in der Bereitstellungsdokumentation oder in der Dokumentation zur Skype for Business Server Management Shell.

## <a name="see-also"></a>Siehe auch

[Planen der Anrufsteuerung in Skype for Business Server](call-admission-control.md)

[Planen von Notrufdiensten in Skype for Business Server](emergency-services.md)

[Planen der Medienumgehung in Skype for Business](media-bypass.md)