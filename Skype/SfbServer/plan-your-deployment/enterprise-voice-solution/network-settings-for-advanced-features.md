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
description: Erfahren Sie mehr über Netzwerkregionen, Netzwerkstandorte und IP-Subnetze. Alle diese Dienste müssen für die Bereitstellung des Plans für die Medienumgehung in Skype for Business, für die Planung der Anrufsteuerung in Skype for Business Server oder für die Planung der Notrufdienste in Skype for Business Server in Skype for Business Server Enterprise-VoIP.
ms.openlocfilehash: 3f7b11d2265c9b5f93633b03311d622ad9862abd
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2021
ms.locfileid: "49813625"
---
# <a name="network-settings-for-the-advanced-enterprise-voice-features-in-skype-for-business-server"></a>Netzwerkeinstellungen für die erweiterten Enterprise-VoIP in Skype for Business Server

Erfahren Sie mehr über Netzwerkregionen, Netzwerkstandorte und IP-Subnetze. Alle diese Dienste müssen für die Bereitstellung von Plan für die Medienumgehung [in Skype for Business,](media-bypass.md)zum Planen der Anrufsteuerung in Skype for [Business Server](call-admission-control.md)oder zum Planen der Notrufdienste in Skype for [Business Server](emergency-services.md) in Skype for Business Server Enterprise-VoIP.

Skype for Business Server verfügt über drei erweiterte Enterprise-VoIP-Funktionen: Planen der Anrufsteuerung [in Skype for Business Server,](call-admission-control.md)Planen der Notrufdienste in Skype for Business [Server](emergency-services.md)und Planen der Medienumgehung in Skype [for Business.](media-bypass.md) Diese Features teilen bestimmte Konfigurationsanforderungen für Netzwerkregionen, Netzwerkstandorte und die Zuordnung der einzelnen Subnetze in der Skype for Business Server-Topologie zu einem Netzwerkstandort.

Dieses Thema bietet eine Übersicht über die Konfigurationsanforderungen, die für alle drei dieser erweiterten Enterprise-VoIP gelten.

## <a name="network-regions"></a>Netzwerkregionen

Bei einer Netzwerkregion handelt es sich um einen Netzwerkhub oder Netzwerkbackbone, der ausschließlich in der Konfiguration von Anrufsteuerung (Call Admission Control, CAC), E9-1-1 und Medienumgehung verwendet wird.

> [!NOTE]
> Netzwerkregionen sind nicht identisch mit Skype for Business Server-Einwahlkonferenzregionen, die zum Zuordnen von Zugriffsnummern für Einwahlkonferenzen zu einem oder mehreren Skype for Business Server-Wählplänen erforderlich sind. Weitere Informationen zu Regionen für Einwahlkonferenzen finden Sie unter [Planning for Dial-In Conferencing](https://technet.microsoft.com/library/9aff949e-3dac-481a-be46-a180c72e8066.aspx).

Die Anruf anrufbehindert erfordert, dass jede Netzwerkregion über einen zugeordneten zentralen Skype for Business Server-Standort verfügen muss, der den Mediendatenverkehr innerhalb der Region verwaltet (d. h. entscheidungen basierend auf von Ihnen konfigurierten Richtlinien darüber, ob eine Audio- oder Videositzung in Echtzeit eingerichtet werden kann). Zentrale Skype for Business Server-Standorte stellen keine geografischen Standorte dar, sondern logische Servergruppen, die als Pool oder Poolgruppe konfiguriert sind.

Zum Konfigurieren einer Netzwerkregion können  Sie entweder  die Registerkarte "Regionen" im Abschnitt "Netzwerkkonfiguration" der Skype for Business Server-Systemsteuerung verwenden oder die Cmdlets **"New-CsNetworkRegion"** oder **"Set-CsNetworkRegion** Skype for Business Server Management Shell" ausführen. Anweisungen finden Sie unter "Bereitstellen von Netzwerkregionen, Standorten und Subnetzen in Skype for Business" in der [Bereitstellungsdokumentation](../../deploy/deploy-enterprise-voice/deploy-network.md) oder in der Dokumentation zur Skype for Business Server-Verwaltungsshell.

Dieselben Netzwerkregionsdefinitionen werden von allen drei erweiterten Enterprise-VoIP verwendet. Wenn Sie bereits Netzwerkregionen für eine Funktion erstellt haben, müssen Sie keine neuen Netzwerkregionen für die anderen Funktionen erstellen. Sie müssen jedoch möglicherweise eine vorhandene Definition einer Netzwerkregion ändern, um funktionsspezifische Einstellungen anzuwenden. Wenn Sie z. B. Netzwerkregionen für E9-1-1 erstellt haben (denen kein zentraler Standort zugeordnet werden muss) und Sie zu einem späteren Zeitpunkt die Anrufsteuerung bereitstellen, müssen Sie die Definitionen der Netzwerkregionen ändern und einen zentralen Standort angeben.

Zum Zuordnen eines zentralen Skype for Business Server-Standorts zu einer Netzwerkregion geben Sie den Namen des zentralen Standorts an, entweder im Abschnitt "Netzwerkkonfiguration" der Skype for Business Server-Systemsteuerung oder durch Ausführen der Cmdlets **"New-CsNetworkRegion"** oder **"Set-CsNetworkRegion".**  Anweisungen finden Sie unter "Bereitstellen von Netzwerkregionen, Standorten und Subnetzen in Skype for Business" in der [Bereitstellungsdokumentation](../../deploy/deploy-enterprise-voice/deploy-network.md) oder in der Dokumentation zur Skype for Business Server-Verwaltungsshell.

## <a name="network-sites"></a>Netzwerkstandorte

Ein Netzwerkstandort stellt einen geografischen Standort dar, z. B. ein Zweigstellenbüro, ein regionales Büro oder ein Hauptbüro. Jeder Netzwerkstandort muss einer bestimmten Netzwerkregion zugeordnet sein.

> [!NOTE]
> Netzwerkstandorte werden nur von den erweiterten Enterprise-VoIP verwendet. Sie sind nicht mit den Zweigstellenstandorten identisch, die Sie in Ihrer Skype for Business Server-Topologie konfigurieren.

Um einen Netzwerkstandort zu konfigurieren und einer Netzwerkregion  zuzuordnen, können Sie entweder den Abschnitt "Netzwerkkonfiguration" der Skype for Business Server-Systemsteuerung verwenden oder die Cmdlets **"New-CsNetworkSite"** oder **"Set-CsNetworkSite"** der Skype for Business Server-Verwaltungsshell ausführen. Ausführliche Informationen finden Sie unter ["Erstellen](https://technet.microsoft.com/library/14e24856-9996-4da4-9f31-300940bdf5aa.aspx) oder Ändern eines Netzwerkstandorts" in der Bereitstellungsdokumentation oder in der Dokumentation zur Skype for Business Server-Verwaltungsshell.

## <a name="identify-ip-subnets"></a>Identifizieren von IP-Subnetzen

Arbeiten Sie mit Ihrem Netzwerkadministrator zusammen, um zu ermitteln, welche IP-Subnetze jedem Netzwerkstandort zugewiesen sind. Wenn Ihr Netzwerkadministrator die IP-Subnetze bereits in Netzwerkregionen und Netzwerkstandorte unterteilt hat, wird diese Aufgabe erheblich vereinfacht.

Zum Beispiel können dem Standort "New York" in der Region "Nordamerika" die folgenden IP-Subnetze zugewiesen werden: 172.29.80.0/23, 157.57.216.0/25, 172.29.91.0/23, 172.29.81.0/24. Wenn der Benutzer Bob, der üblicherweise in Detroit arbeitet, für eine Schulung in das New Yorker Büro reist, seinen Computer einschaltet und sich mit dem Netzwerk verbindet, erhält sein Computer eine IP-Adresse aus einem der vier Bereiche, die für "New York" zugewiesen sind, beispielsweise die Adresse 172.29.80.103.

> [!CAUTION]
> Die während der Netzwerkkonfiguration auf dem Server angegebenen IP-Subnetze müssen dem Format entsprechen, das von Clientcomputern bereitgestellt wird, damit eine ordnungsgemäße Verwendung für die Medienumgehung gewährleistet ist. Ein Skype for Business-Client verwendet seine lokale IP-Adresse und maskiert die IP-Adresse mit der zugeordneten Subnetzmaske. Bei Ermittlung der Umgehungs-ID für jeden Client vergleicht die Registrierung die Liste der IP-Subnetze für jeden Netzwerkstandort mit dem vom Client bereitgestellten Subnetz, um eine exakte Übereinstimmung zu ermitteln. Aus diesem Grund ist es wichtig, dass es sich bei den während der Netzwerkkonfiguration auf dem Server eingegebenen Subnetzen nicht um virtuelle, sondern um tatsächliche Subnetze handelt. (Wenn Sie die Anrufsteuerung bereitstellen, jedoch keine Medienumgehung, funktioniert die Anrufsteuerung auch dann ordnungsgemäß, wenn Sie virtuelle Subnetze konfigurieren.) Wenn sich beispielsweise ein Skype for Business-Client auf einem Computer mit der IP-Adresse 172.29.81.57 mit der IP-Subnetzmaske 255.255.255.0 anpasst, wird die Umgehungs-ID des Subnetzes 172.29.81.0 anfordern. Wenn das Subnetz als 172.29.0.0/16 definiert ist, betrachtet die Registrierung dies – wenngleich der Client dem virtuellen Subnetz angehört – nicht als Übereinstimmung, da die Registrierung ausschließlich nach Subnetz 172.29.81.0 sucht. Daher ist es wichtig, dass der Administrator Subnetze genau wie von Skype for Business-Clients bereitgestellt ein (die während der Netzwerkkonfiguration entweder statisch oder über DHCP (Dynamic Host Configuration Protocol) mit Subnetzen bereitgestellt werden).

## <a name="associating-subnets-with-network-sites"></a>Zuordnen von Subnetzen zu Netzwerkstandorten

Jedes Subnetz im Unternehmensnetzwerk muss einem Netzwerkstandort zugeordnet sein (d. h. jedes Subnetz muss einem geografischen Standort zugeordnet sein). Diese Zuordnung von Subnetzen ermöglicht es den erweiterten Enterprise-VoIP, die Endpunkte geografisch zu finden. Beispielsweise ermöglicht die Suche nach den Endpunkten die Cac, um den Fluss von Audio- und Videodaten in Echtzeit zu und vom Netzwerkstandort zu regeln.

Zum Zuordnen von Subnetzen zu Netzwerkstandorten können Sie entweder den Abschnitt "Netzwerkkonfiguration" der Skype for Business Server-Systemsteuerung oder die Skype for Business Server-Verwaltungsshell verwenden.  Anweisungen finden Sie unter ["Zuordnen eines Subnetzes](https://technet.microsoft.com/library/aa69e3ac-542a-4ba1-9582-2e6bee29f633.aspx) zu einem Netzwerkstandort" in der Bereitstellungsdokumentation oder in der Dokumentation zur Skype for Business Server-Verwaltungsshell.

## <a name="see-also"></a>Weitere Informationen

[Planen der Anrufsteuerung in Skype for Business Server](call-admission-control.md)

[Planen von Notrufdiensten in Skype for Business Server](emergency-services.md)

[Planen der Medienumgehung in Skype for Business](media-bypass.md)

