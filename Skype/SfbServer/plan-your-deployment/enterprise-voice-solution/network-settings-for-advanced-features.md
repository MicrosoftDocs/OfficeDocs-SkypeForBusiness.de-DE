---
title: Netzwerkeinstellungen für die erweiterten Enterprise-VoIP-Features in Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
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
description: Erfahren Sie mehr über Netzwerkregionen, Netzwerkstandorte und IP-Subnetze. Alle diese müssen so konfiguriert sein, dass Sie Plan für medienumgehung in Skype for Business bereitstellen, die Steuerung der Anrufannahme in Skype for Business Server planen oder Notfalldienste in Skype for Business Server in Skype for Business Server Enterprise-VoIP planen.
ms.openlocfilehash: 25987630ae2082ca8805d87a988760296637d3f7
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2020
ms.locfileid: "41802595"
---
# <a name="network-settings-for-the-advanced-enterprise-voice-features-in-skype-for-business-server"></a>Netzwerkeinstellungen für die erweiterten Enterprise-VoIP-Features in Skype for Business Server

Erfahren Sie mehr über Netzwerkregionen, Netzwerkstandorte und IP-Subnetze. Alle diese müssen so konfiguriert sein, dass Sie [Plan für medienumgehung in Skype for Business](media-bypass.md)bereitstellen, die [Steuerung der Anrufannahme in Skype for Business Server planen](call-admission-control.md)oder [Notfalldienste in Skype for Business Server](emergency-services.md) in Skype for Business Server Enterprise-VoIP planen.

Skype for Business Server verfügt über drei erweiterte Enterprise-VoIP-Funktionen: [Planen der Anrufsteuerung in Skype for Business Server](call-admission-control.md), [Planen von Notfalldiensten in Skype for Business Server](emergency-services.md)und [Planen der medienumgehung in Skype for Business](media-bypass.md). Diese Features geben bestimmte Konfigurationsanforderungen für netzwerkregionen, Netzwerk Websites und die Zuordnung jedes Subnets in der Skype for Business Server-Topologie mit einer Netzwerk Website frei.

In diesem Thema finden Sie eine Übersicht über die Konfigurationsanforderungen, die für alle drei dieser erweiterten Enterprise-VoIP-Features üblich sind.

## <a name="network-regions"></a>Netzwerkregionen

Bei einer Netzwerkregion handelt es sich um einen Netzwerkhub oder Netzwerkbackbone, der ausschließlich in der Konfiguration von Anrufsteuerung (Call Admission Control, CAC), E9-1-1 und Medienumgehung verwendet wird.

> [!NOTE]
> Netzwerkregionen sind nicht identisch mit den Skype for Business Server-Einwahlkonferenz Regionen, die für die Zuordnung von Einwahlkonferenz-Zugriffsnummern zu einem oder mehreren Skype for Business Server-Wählplänen erforderlich sind. Ausführliche Informationen zu Regionen für Einwahlkonferenzen finden Sie unter [Planning for Dial-In Conferencing](https://technet.microsoft.com/library/9aff949e-3dac-481a-be46-a180c72e8066.aspx).

Für CAC ist es erforderlich, dass jede netzwerkregion über eine zugeordnete Skype for Business Server-zentrale Website verfügt, die den Mediendatenverkehr in der Region verwaltet (das heißt, Sie trifft Entscheidungen basierend auf den von Ihnen konfigurierten Richtlinien, ob es sich um eine echt Zeit Audio-oder Videositzung kann eingerichtet werden). Die zentralen Websites von Skype for Business Server stellen keine geographischen Speicherorte, sondern logische Gruppen von Servern dar, die als Pool oder Gruppe von Pools konfiguriert sind.

Zum Konfigurieren einer netzwerkregion können Sie entweder die Registerkarte **Regionen** im Abschnitt **Netzwerkkonfiguration** der Skype for Business Server-Systemsteuerung verwenden oder die Cmdlets für die Skype for Business Server-Verwaltungsshell für **neue CsNetworkRegion** oder **CsNetworkRegion** ausführen. Anweisungen hierzu finden Sie unter [Bereitstellen von netzwerkregionen,-Websites und-Subnetzen in Skype for Business](../../deploy/deploy-enterprise-voice/deploy-network.md) in der Bereitstellungsdokumentation oder in der Dokumentation zur Skype for Business Server-Verwaltungsshell.

Die gleichen Netzwerkbereichs Definitionen werden von allen drei erweiterten Enterprise-VoIP-Features freigegeben. Wenn Sie bereits Netzwerkregionen für eine Funktion erstellt haben, müssen Sie keine neuen Netzwerkregionen für die anderen Funktionen erstellen. Sie müssen jedoch möglicherweise eine vorhandene Definition einer Netzwerkregion ändern, um funktionsspezifische Einstellungen anzuwenden. Wenn Sie z. B. Netzwerkregionen für E9-1-1 erstellt haben (denen kein zentraler Standort zugeordnet werden muss) und zu einem späteren Zeitpunkt die Anrufsteuerung bereitstellen, müssen Sie die Definitionen der Netzwerkregionen ändern und einen zentralen Standort angeben.

Wenn Sie einen Skype for Business Server Central-Standort einem Netzwerkbereich zuordnen möchten, geben Sie den zentralen Standortnamen entweder über den Abschnitt **Netzwerkkonfiguration** der Skype for Business Server-Systemsteuerung oder durch Ausführen der Cmdlets " **New-CsNetworkRegion** " oder " **CsNetworkRegion** " an. Anweisungen hierzu finden Sie unter [Bereitstellen von netzwerkregionen,-Websites und-Subnetzen in Skype for Business](../../deploy/deploy-enterprise-voice/deploy-network.md) in der Bereitstellungsdokumentation oder in der Dokumentation zur Skype for Business Server-Verwaltungsshell.

## <a name="network-sites"></a>Netzwerkstandorte

Ein Netzwerkstandort stellt einen geografischen Standort dar, z. B. ein Zweigstellenbüro, ein regionales Büro oder ein Hauptbüro. Jeder Netzwerkstandort muss einer bestimmten Netzwerkregion zugeordnet sein.

> [!NOTE]
> Netzwerk Websites werden nur von den erweiterten Enterprise-VoIP-Features verwendet. Sie sind nicht identisch mit den Zweigstellen, die Sie in Ihrer Skype for Business Server-Topologie konfigurieren.

Um eine Netzwerk Website zu konfigurieren und Sie einer netzwerkregion zuzuordnen, können Sie entweder den Abschnitt **Netzwerkkonfiguration** der Skype for Business Server-Systemsteuerung verwenden oder die Cmdlets für die Skype for Business Server-Verwaltungsshell " **New-CsNetworkSite** " oder " **CsNetworkSite** " ausführen. Ausführliche Informationen finden Sie unter [erstellen oder Ändern einer Netzwerk Website](https://technet.microsoft.com/library/14e24856-9996-4da4-9f31-300940bdf5aa.aspx) in der Bereitstellungsdokumentation oder in der Dokumentation zur Skype for Business Server-Verwaltungsshell.

## <a name="identify-ip-subnets"></a>Identifizieren von IP-Subnetzen

Arbeiten Sie mit Ihrem Netzwerkadministrator zusammen, um zu ermitteln, welche IP-Subnetze jedem Netzwerkstandort zugewiesen sind. Wenn Ihr Netzwerkadministrator die IP-Subnetze bereits in Netzwerkregionen und Netzwerkstandorte unterteilt hat, wird diese Aufgabe erheblich vereinfacht.

Sie können z. B. dem Standort „New York“ in der Region „Nordamerika“ die folgenden IP-Subnetze zuweisen: 172.29.80.0/23, 157.57.216.0/25, 172.29.91.0/23, 172.29.81.0/24. Wenn der Benutzer Bob, der üblicherweise in Detroit arbeitet, für eine Schulung in das New Yorker Büro reist, seinen Computer einschaltet und sich mit dem Netzwerk verbindet, erhält sein Computer eine IP-Adresse aus einem der vier Bereiche, die für „New York“ zugewiesen sind, beispielsweise die Adresse 172.29.80.103.

> [!CAUTION]
> Die während der Netzwerkkonfiguration auf dem Server angegebenen IP-Subnetze müssen dem Format entsprechen, das von Clientcomputern bereitgestellt wird, damit eine ordnungsgemäße Verwendung für die Medienumgehung gewährleistet ist. Ein Skype for Business-Client übernimmt die lokale IP-Adresse und maskiert die IP-Adresse mit der zugehörigen Subnetzmaske. Bei Ermittlung der Umgehungs-ID für jeden Client vergleicht die Registrierung die Liste der IP-Subnetze für jeden Netzwerkstandort mit dem vom Client bereitgestellten Subnetz, um eine exakte Übereinstimmung zu ermitteln. Aus diesem Grund ist es wichtig, dass es sich bei den während der Netzwerkkonfiguration auf dem Server eingegebenen Subnetzen nicht um virtuelle, sondern um tatsächliche Subnetze handelt. (Wenn Sie die Anrufsteuerung, aber nicht die medienumgehung bereitstellen, funktioniert die Anrufsteuerung auch dann ordnungsgemäß, wenn Sie virtuelle Subnetze konfigurieren.) Wenn sich beispielsweise ein Skype for Business-Client auf einem Computer mit einer IP-Adresse von 172.29.81.57 mit einer IP-Subnetzmaske 255.255.255.0 anmeldet, wird die Bypass-ID angefordert, die dem Subnetz 172.29.81.0 zugeordnet ist. Wenn das Subnetz als 172.29.0.0/16 definiert ist, betrachtet die Registrierung dies – auch wenn der Client dem virtuellen Subnetz angehört – nicht als Übereinstimmung, da die Registrierung ausschließlich nach Subnetz 172.29.81.0 sucht. Daher ist es wichtig, dass der Administrator Subnetze genau so eingibt, wie dies von Skype for Business-Clients bereitgestellt wird (die mit Subnetzen während der Netzwerkkonfiguration entweder statisch oder durch DHCP (Dynamic Host Configuration Protocol) bereitgestellt werden.)

## <a name="associating-subnets-with-network-sites"></a>Zuordnen von Subnetzen zu Netzwerkstandorten

Jedes Subnetz innerhalb des Unternehmensnetzwerks muss einem geografischen Netzwerkstandort zugeordnet werden. Diese Zuordnung von Subnetzen ermöglicht es den erweiterten Enterprise-VoIP-Features, die Endpunkte geografisch zu finden. Durch die Ermittlung der Standorte von Endpunkten kann die Anrufsteuerung z. B. den Fluss von Audio- und Videoechtzeitdaten zum und vom Netzwerkstandort steuern.

Um Subnetze mit Netzwerkstandorten zu verknüpfen, können Sie entweder den Abschnitt **Netzwerkkonfiguration** der Skype for Business Server-Systemsteuerung verwenden, oder Sie können die Skype for Business Server-Verwaltungsshell verwenden. Anweisungen hierzu finden Sie unter [Zuordnen eines Subnetzes zu einer Netzwerk Website](https://technet.microsoft.com/library/aa69e3ac-542a-4ba1-9582-2e6bee29f633.aspx) in der Bereitstellungsdokumentation oder in der Dokumentation zur Skype for Business Server-Verwaltungsshell.

## <a name="see-also"></a>Siehe auch

[Planen der Anrufsteuerung in Skype for Business Server](call-admission-control.md)

[Planen von Notfalldiensten in Skype for Business Server](emergency-services.md)

[Planen der medienumgehung in Skype for Business](media-bypass.md)

