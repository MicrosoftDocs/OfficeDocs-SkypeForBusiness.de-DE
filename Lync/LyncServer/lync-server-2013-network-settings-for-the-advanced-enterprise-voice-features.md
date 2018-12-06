---
title: 'Lync Server 2013: Netzwerkeinstellungen für die erweiterten Enterprise-VoIP-Funktionen'
TOCTitle: Netzwerkeinstellungen für die erweiterten Enterprise-VoIP-Funktionen
ms:assetid: 7f6de9e4-c8a4-44e4-8d14-21fe8c45283a
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg398637(v=OCS.15)
ms:contentKeyID: 49294549
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Netzwerkeinstellungen für die erweiterten Enterprise-VoIP-Funktionen in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2012-10-10_

Lync Server umfasst drei erweiterte Enterprise-VoIP-Funktionen: Anrufsteuerung (Call Admission Control, CAC), Notrufdienste (E9-1-1) und Medienumgehung. Für diese Funktionen gelten bestimmte gemeinsame Konfigurationsanforderungen im Hinblick auf Netzwerkregionen, Netzwerkstandorte und die Zuordnung der einzelnen Subnetze in der Lync Server-Topologie zu einem Netzwerkstandort. Ausführliche Informationen zur Bereitstellungsplanung für diese Funktionen finden Sie unter:

  - [Planen des Anrufsteuerungsdiensts in Lync Server 2013](lync-server-2013-planning-for-call-admission-control.md)

  - [Planen von Notrufdiensten (E9-1-1) in Lync Server 2013](lync-server-2013-planning-for-emergency-services-e9-1-1.md)

  - [Planung der Medienumgehung in Lync Server 2013](lync-server-2013-planning-for-media-bypass.md)

Ausführliche Informationen zur Bereitstellung der einzelnen Funktionen finden Sie unter [Bereitstellen von erweiterten Enterprise-VoIP-Features in Lync Server 2013](lync-server-2013-deploying-advanced-enterprise-voice-features.md) in der Bereitstellungsdokumentation.

Dieses Thema bietet einen Überblick über die Konfigurationsanforderungen, die für alle drei erweiterten Enterprise-VoIP-Funktionen gelten.

## Netzwerkregionen

Bei einer Netzwerkregion handelt es sich um einen Netzwerkhub oder Netzwerkbackbone, der ausschließlich in der Konfiguration von Anrufsteuerung (Call Admission Control, CAC), E9-1-1 und Medienumgehung verwendet wird.


> [!NOTE]
> Netzwerkregionen sind nicht mit Lync Server-Regionen für Einwahlkonferenzen identisch, die zum Zuordnen von Zugriffsnummern für Einwahlkonferenzen zu einem oder mehreren Sätzen mit Wähleinstellungen in Lync Server erforderlich sind. Ausführliche Informationen zu Regionen für Einwahlkonferenzen finden Sie unter <A href="lync-server-2013-dial-in-conferencing-requirements.md">Anforderungen für Einwahlkonferenzen in Lync Server 2013</A> in der Planungsdokumentation.



Für die Anrufsteuerung muss jeder Netzwerkregion ein zentraler Lync Server-Standort zugeordnet sein, über den der Mediendatenverkehr innerhalb der Region verwaltet wird (das heißt, dass basierend auf konfigurierten Richtlinien entschieden wird, ob Audio- oder Videoechtzeitsitzungen erstellt werden können oder nicht). Zentrale Lync Server-Standorte stellen keine geografischen Standorte dar, sondern logische Gruppen aus Servern, die als Pool oder eine Gruppe von Pools konfiguriert sind. Ausführliche Informationen zu zentralen Standorten finden Sie unter [Referenztopologien in Lync Server 2013](lync-server-2013-reference-topologies.md) in der Planungsdokumentation. Siehe auch [Unterstützte Topologien in Lync Server 2013](lync-server-2013-supported-topologies.md) in der Unterstützungsdokumentation.

Netzwerkregionen können entweder auf der Registerkarte **Regionen** im Bereich **Netzwerkkonfiguration** der Lync Server-Systemsteuerung oder durch Ausführen der Cmdlets **New-CsNetworkRegion** oder **Set-CsNetworkRegion** in der Lync Server-Verwaltungsshell konfiguriert werden. Eine Anleitung finden Sie unter [Erstellen oder Ändern einer Netzwerkregion in Lync Server 2013](lync-server-2013-create-or-modify-a-network-region.md) in der Bereitstellungsdokumentation oder in der Dokumentation zur Lync Server-Verwaltungsshell.

Die Definitionen von Netzwerkregionen werden von allen drei erweiterten Enterprise-VoIP-Funktionen gemeinsam verwendet. Wenn Sie bereits Netzwerkregionen für eine Funktion erstellt haben, müssen Sie keine neuen Netzwerkregionen für die anderen Funktionen erstellen. Sie müssen jedoch möglicherweise eine vorhandene Definition einer Netzwerkregion ändern, um funktionsspezifische Einstellungen anzuwenden. Wenn Sie z. B. Netzwerkregionen für E9-1-1 erstellt haben (denen kein zentraler Standort zugeordnet werden muss) und Sie zu einem späteren Zeitpunkt die Anrufsteuerung bereitstellen, müssen Sie die Definitionen der Netzwerkregionen ändern und einen zentralen Standort angeben.

Um einen zentralen Lync Server-Standort zu einer Netzwerkregion zuzuordnen, geben Sie entweder im Bereich **Netzwerkkonfiguration** der Lync Server-Systemsteuerung den Namen des zentralen Standorts an, oder führen Sie zu diesem Zweck die Cmdlets **New-CsNetworkRegion** oder **Set-CsNetworkRegion** in der Lync Server-Verwaltungsshell aus. Eine Anleitung finden Sie unter [Erstellen oder Ändern einer Netzwerkregion in Lync Server 2013](lync-server-2013-create-or-modify-a-network-region.md) in der Bereitstellungsdokumentation oder in der Dokumentation zur Lync Server-Verwaltungsshell.

## Netzwerkstandorte

Ein Netzwerkstandort stellt einen geografischen Standort dar, z. B. ein Zweigstellenbüro, ein regionales Büro oder ein Hauptbüro. Jeder Netzwerkstandort muss einer bestimmten Netzwerkregion zugeordnet sein.


> [!NOTE]
> Netzwerkstandorte werden ausschließlich von den erweiterten Enterprise-VoIP-Funktionen verwendet. Sie sind nicht mit Zweigstellenstandorten identisch, die Sie in Ihrer Lync Server-Topologie konfigurieren können. Ausführliche Informationen zu Zweigstellenstandorten finden Sie unter <A href="lync-server-2013-reference-topologies.md">Referenztopologien in Lync Server 2013</A> in der Planungsdokumentation. Siehe auch <A href="lync-server-2013-supported-topologies.md">Unterstützte Topologien in Lync Server 2013</A> in der Unterstützungsdokumentation.



Um einen Netzwerkstandort zu konfigurieren und einer Netzwerkregion zuzuordnen, können Sie den Bereich **Netzwerkkonfiguration** der Lync Server-Systemsteuerung verwenden oder die Cmdlets **New-CsNetworkSite** oder **Set-CsNetworkSite** in der Lync Server-Verwaltungsshell ausführen. Weitere Einzelheiten finden Sie unter [Erstellen oder Ändern eines Netzwerkstandorts in Lync Server 2013](lync-server-2013-create-or-modify-a-network-site.md) in der Bereitstellungsdokumentation oder in der Dokumentation zur Lync Server-Verwaltungsshell.

## Identifizieren von IP-Subnetzen

Arbeiten Sie mit Ihrem Netzwerkadministrator zusammen, um zu ermitteln, welche IP-Subnetze jedem Netzwerkstandort zugewiesen sind. Wenn Ihr Netzwerkadministrator die IP-Subnetze bereits in Netzwerkregionen und Netzwerkstandorte unterteilt hat, wird diese Aufgabe erheblich vereinfacht.

Zum Beispiel können dem Standort "New York" in der Region "Nordamerika" die folgenden IP-Subnetze zugewiesen werden: 172.29.80.0/23, 157.57.216.0/25, 172.29.91.0/23, 172.29.81.0/24. Wenn der Benutzer Bob, der üblicherweise in Detroit arbeitet, für eine Schulung in das New Yorker Büro reist, seinen Computer einschaltet und sich mit dem Netzwerk verbindet, erhält sein Computer eine IP-Adresse aus einem der vier Bereiche, die für "New York" zugewiesen sind, beispielsweise die Adresse 172.29.80.103.


> [!WARNING]
> Die während der Netzwerkkonfiguration auf dem Server angegebenen IP-Subnetze müssen dem Format entsprechen, das von Clientcomputern bereitgestellt wird, damit eine ordnungsgemäße Verwendung für die Medienumgehung gewährleistet ist. Ein Lync-Client maskiert die lokale IP-Adresse mit der zugeordneten Subnetzmaske. Bei Ermittlung der Umgehungs-ID für jeden Client vergleicht die Registrierung die Liste der IP-Subnetze für jeden Netzwerkstandort mit dem vom Client bereitgestellten Subnetz, um eine exakte Übereinstimmung zu ermitteln. Aus diesem Grund ist es wichtig, dass es sich bei den während der Netzwerkkonfiguration auf dem Server eingegebenen Subnetzen nicht um virtuelle, sondern um tatsächliche Subnetze handelt. (Wenn Sie die Anrufsteuerung bereitstellen, jedoch keine Medienumgehung verwenden, funktioniert die Anrufsteuerung selbst dann ordnungsgemäß, wenn Sie virtuelle Subnetze konfigurieren.)<BR>Wenn sich ein Lync-Client beispielsweise an einem Computer mit der IP-Adresse 172.29.81.57 und der IP-Subnetzmaske 255.255.255.0 anmeldet, fordert er die Umgehungs-ID an, die Subnetz 172.29.81.0 zugeordnet ist. Wenn das Subnetz als 172.29.0.0/16 definiert ist, betrachtet die Registrierung dies - wenngleich der Client dem virtuellen Subnetz angehört - nicht als Übereinstimmung, da die Registrierung ausschließlich nach Subnetz 172.29.81.0 sucht. Daher ist es wichtig, dass der Administrator Subnetze genau wie von den Lync-Clients bereitgestellt angibt (bereitgestellt mit den Subnetzen während der Netzwerkkonfiguration, entweder als statische Konfiguration oder über Dynamic Host Configuration Protocol (DHCP)).



## Zuordnen von Subnetzen zu Netzwerkstandorten

Jedes Subnetz innerhalb des Unternehmensnetzwerks muss einem Netzwerkstandort zugeordnet werden (d. h., jedes Subnetz muss einem geografischen Standort zugeordnet werden). Aufgrund dieser Zuordnung von Subnetzen können die erweiterten Enterprise-VoIP-Funktionen den Standort von Endpunkten ermitteln. Durch die Ermittlung der Standorte von Endpunkten kann die Anrufsteuerung z. B. den Fluss von Audio- und Videoechtzeitdaten zum und vom Netzwerkstandort steuern.

Zum Zuordnen von Subnetzen zu Netzwerkstandorten können Sie entweder den Bereich **Netzwerkkonfiguration** der Lync Server-Systemsteuerung verwenden oder die Lync Server-Verwaltungsshell verwenden. Eine Anleitung finden Sie unter [Zuordnen eines Subnetzes zu einem Netzwerkstandort in Lync Server 2013](lync-server-2013-associate-a-subnet-with-a-network-site.md) in der Bereitstellungsdokumentation oder in der Dokumentation zur Lync Server-Verwaltungsshell.

## Siehe auch

#### Weitere Ressourcen

[Planen des Anrufsteuerungsdiensts in Lync Server 2013](lync-server-2013-planning-for-call-admission-control.md)  
[Planen von Notrufdiensten (E9-1-1) in Lync Server 2013](lync-server-2013-planning-for-emergency-services-e9-1-1.md)  
[Planung der Medienumgehung in Lync Server 2013](lync-server-2013-planning-for-media-bypass.md)

