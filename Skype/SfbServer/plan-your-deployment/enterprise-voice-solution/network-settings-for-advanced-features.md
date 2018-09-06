---
title: Netzwerkeinstellungen für den erweiterten Enterprise-VoIP-Funktionen in Skype für Business Server
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 7f6de9e4-c8a4-44e4-8d14-21fe8c45283a
description: Erfahren Sie mehr über Netzwerkregionen, Netzwerkstandorte und IP-Subnetze. Alle diese müssen konfiguriert werden, um Plan bereitstellen für in Skype für Unternehmen, Plan für die medienumgehung anrufsteuerung in Skype für Business Server), oder Plan für Notdienste in Skype für Business Server in Skype für Business Server Enterprise-VoIP.
ms.openlocfilehash: a58598bedb7919d97d78cc5a43cc0e807118612e
ms.sourcegitcommit: 08c6fe9955ea61dd9cded2210ae0153e06bdd8a6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/29/2018
ms.locfileid: "23263774"
---
# <a name="network-settings-for-the-advanced-enterprise-voice-features-in-skype-for-business-server"></a>Netzwerkeinstellungen für den erweiterten Enterprise-VoIP-Funktionen in Skype für Business Server

Erfahren Sie mehr über Netzwerkregionen, Netzwerkstandorte und IP-Subnetze. All diese müssen konfiguriert sein, um [Planen Medien in Skype für Unternehmen zu umgehen](media-bypass.md), [Plan für die anrufsteuerung in Skype für Business Server](call-admission-control.md)oder in Skype [für Notdienste in Skype für Business Server planen](emergency-services.md) für Business Server bereitstellen Enterprise-VoIP.

Skype für Business Server verfügt über drei erweiterten Enterprise-VoIP-Funktionen: Planen der [Plan für die anrufsteuerung in Skype für Business Server](call-admission-control.md), [für Notdienste in Skype für Business Server planen](emergency-services.md)und [medienumgehung in Skype für Unternehmen ](media-bypass.md). Diese Features freigeben bestimmte konfigurationsanforderungen für netzwerkregionen, Netzwerkstandorten und Zuordnung der einzelnen Subnetze in der Skype für Business Server-Topologie mit einem Netzwerkstandort.

Dieses Thema bietet eine Übersicht über die konfigurationsanforderungen, die alle drei dieser erweiterten Enterprise-VoIP-Funktionen gelten.

## <a name="network-regions"></a>Netzwerkregionen

Bei einer Netzwerkregion handelt es sich um einen Netzwerkhub oder Netzwerkbackbone, der ausschließlich in der Konfiguration von Anrufsteuerung (Call Admission Control, CAC), E9-1-1 und Medienumgehung verwendet wird.

> [!NOTE]
> Netzwerkregionen sind nicht identisch mit Skype für Business Server einwahlkonferenzen Bereiche, die es erforderlich, die eine oder mehrere Skype für Wählpläne Business Server Zugriffsnummern für einwahlkonferenzen zugeordnet sind. Ausführliche Informationen zu einwahlkonferenzen Regionen finden Sie unter [Planung für Einwahlkonferenzen](https://technet.microsoft.com/library/9aff949e-3dac-481a-be46-a180c72e8066.aspx).

CAC erfordert, dass jeder netzwerkregion ein zugeordneten Skype für Business Server zentralen Standort, haben die Mediendatenverkehr innerhalb der Region verwaltet (d. h., es entscheidet, die basierend auf Richtlinien, die Sie, bezüglich, ob konfiguriert haben eine in Echtzeit Audio- oder videositzung hergestellt werden). Skype für zentrale Standorte Business Server geografischen Standorten, aber vielmehr logischen Gruppen von Servern, die als Pool konfiguriert sind oder eine Gruppe von Pools nicht darstellen.

Zum Konfigurieren einer netzwerkregion können Sie entweder die Registerkarte **Regionen** auf einem Abschnitt **Netzwerkkonfiguration** Skype Business Server-Systemsteuerung verwenden oder führen Sie die **New-CsNetworkRegion** oder **Set-CsNetworkRegion** Skype für Unternehmen Server-Verwaltungsshell-Cmdlets. Anweisungen finden Sie unter [Bereitstellen von netzwerkregionen, Standorten und Subnetze in Skype für Unternehmen](../../deploy/deploy-enterprise-voice/deploy-network.md) in der Dokumentation zur Bereitstellung, oder Lesen Sie die Skype Business Server-Verwaltungsshell-Dokumentation.

Die gleichen netzwerkregionendefinitionen sind durch alle drei erweiterten Enterprise-VoIP-Funktionen freigegeben. Wenn Sie bereits Netzwerkregionen für eine Funktion erstellt haben, müssen Sie keine neuen Netzwerkregionen für die anderen Funktionen erstellen. Sie müssen jedoch möglicherweise eine vorhandene Definition einer Netzwerkregion ändern, um funktionsspezifische Einstellungen anzuwenden. Wenn Sie z. B. Netzwerkregionen für E9-1-1 erstellt haben (denen kein zentraler Standort zugeordnet werden muss) und zu einem späteren Zeitpunkt die Anrufsteuerung bereitstellen, müssen Sie die Definitionen der Netzwerkregionen ändern und einen zentralen Standort angeben.

Um einen Skype für Business Server zentralen Standort eine netzwerkregion zuzuordnen, geben Sie den zentralen Standort-Namen, entweder mithilfe des Abschnitts **Netzwerkkonfiguration** von Skype Business Server-Systemsteuerung oder indem Sie das **New-CsNetworkRegion** ausführen oder **Set-CsNetworkRegion** -Cmdlets. Anweisungen finden Sie unter [Bereitstellen von netzwerkregionen, Standorten und Subnetze in Skype für Unternehmen](../../deploy/deploy-enterprise-voice/deploy-network.md) in der Dokumentation zur Bereitstellung, oder Lesen Sie die Skype Business Server-Verwaltungsshell-Dokumentation.

## <a name="network-sites"></a>Netzwerkstandorte

Ein Netzwerkstandort stellt einen geografischen Standort dar, z. B. ein Zweigstellenbüro, ein regionales Büro oder ein Hauptbüro. Jeder Netzwerkstandort muss einer bestimmten Netzwerkregion zugeordnet sein.

> [!NOTE]
> Netzwerkstandorte dienen nur durch den erweiterten Enterprise-VoIP-Funktionen. Sie sind nicht identisch mit der Zweigniederlassungen, die in Ihrer Skype für Business Server-Topologie konfiguriert werden.

Zum Konfigurieren eines Netzwerkstandorts, und ordnen Sie ihm eine netzwerkregion, können Sie entweder die **Netzwerkkonfiguration** Abschnitt Skype Business Server-Systemsteuerung verwenden oder führen Sie die Skype für Business Server-Verwaltungsshell **New-CsNetworkSite** oder ** Set-CsNetworkSite** Cmdlets. Weitere Informationen hierzu finden Sie unter [Erstellen oder Ändern eines Netzwerkstandorts](https://technet.microsoft.com/library/14e24856-9996-4da4-9f31-300940bdf5aa.aspx) in der Dokumentation zur Bereitstellung, oder Lesen Sie die Skype Business Server-Verwaltungsshell-Dokumentation.

## <a name="identify-ip-subnets"></a>Identifizieren von IP-Subnetzen

Arbeiten Sie mit Ihrem Netzwerkadministrator zusammen, um zu ermitteln, welche IP-Subnetze jedem Netzwerkstandort zugewiesen sind. Wenn Ihr Netzwerkadministrator die IP-Subnetze bereits in Netzwerkregionen und Netzwerkstandorte unterteilt hat, wird diese Aufgabe erheblich vereinfacht.

Sie können z. B. dem Standort „New York“ in der Region „Nordamerika“ die folgenden IP-Subnetze zuweisen: 172.29.80.0/23, 157.57.216.0/25, 172.29.91.0/23, 172.29.81.0/24. Wenn der Benutzer Bob, der üblicherweise in Detroit arbeitet, für eine Schulung in das New Yorker Büro reist, seinen Computer einschaltet und sich mit dem Netzwerk verbindet, erhält sein Computer eine IP-Adresse aus einem der vier Bereiche, die für „New York“ zugewiesen sind, beispielsweise die Adresse 172.29.80.103.

> [!CAUTION]
> Die während der Netzwerkkonfiguration auf dem Server angegebenen IP-Subnetze müssen dem Format entsprechen, das von Clientcomputern bereitgestellt wird, damit eine ordnungsgemäße Verwendung für die Medienumgehung gewährleistet ist. Einen Skype für Business-Client nimmt seine lokale IP-Adresse und die IP-Adresse mit der zugehörigen Subnetzmaske maskiert. Bei Ermittlung der Umgehungs-ID für jeden Client vergleicht die Registrierung die Liste der IP-Subnetze für jeden Netzwerkstandort mit dem vom Client bereitgestellten Subnetz, um eine exakte Übereinstimmung zu ermitteln. Aus diesem Grund ist es wichtig, dass es sich bei den während der Netzwerkkonfiguration auf dem Server eingegebenen Subnetzen nicht um virtuelle, sondern um tatsächliche Subnetze handelt. (Wenn Sie die anrufsteuerung bereitstellen, aber keine medienumgehung, die anrufsteuerung funktioniert, auch wenn Sie virtuelle Subnetze konfigurieren.) Wenn eine Skype für Business-Client auf einem Computer mit der IP-Adresse 172.29.81.57 IP-Subnetzmaske 255.255.255.0 anmeldet, wird es beispielsweise die umgehungs-ID anfordern, das Subnetz 172.29.81.0 zugeordnet ist. Wenn das Subnetz als 172.29.0.0/16 definiert ist, betrachtet die Registrierung dies – wenngleich der Client dem virtuellen Subnetz angehört – nicht als Übereinstimmung, da die Registrierung ausschließlich nach Subnetz 172.29.81.0 sucht. Aus diesem Grund ist es wichtig, dass der Administrator Subnetze gibt genau wie von Skype für Business Clients bereitgestellt wird (die mit Subnetze während der Netzwerkkonfiguration, statisch oder von Dynamic Host Configuration Protocol (DHCP) bereitgestellt werden.)

## <a name="associating-subnets-with-network-sites"></a>Zuordnen von Subnetzen zu Netzwerkstandorten

Jedes Subnetz innerhalb des Unternehmensnetzwerks muss einem geografischen Netzwerkstandort zugeordnet werden. Diese Zuordnung von Subnetzen ermöglicht die erweiterten Enterprise-VoIP-Funktionen, die Endpunkte geografisch gesucht werden soll. Durch die Ermittlung der Standorte von Endpunkten kann die Anrufsteuerung z. B. den Fluss von Audio- und Videoechtzeitdaten zum und vom Netzwerkstandort steuern.

Um Subnetzen zu Netzwerkstandorten zuzuordnen, können Sie entweder die **Netzwerkkonfiguration** Abschnitt Skype Business Server-Systemsteuerung, oder Sie können die Skype für Business Server-Verwaltungsshell verwenden. Anweisungen finden Sie in der Bereitstellungsdokumentation unter [Zuordnen eines Subnetzes zu einem Netzwerkstandort](https://technet.microsoft.com/library/aa69e3ac-542a-4ba1-9582-2e6bee29f633.aspx) , oder Lesen Sie die Skype Business Server-Verwaltungsshell-Dokumentation.

## <a name="see-also"></a>Siehe auch

[Plan für die anrufsteuerung in Skype für Business Server](call-admission-control.md)

[Planen für Notdienste in Skype Business Server](emergency-services.md)

[Planen der medienumgehung in Skype für Unternehmen](media-bypass.md)

