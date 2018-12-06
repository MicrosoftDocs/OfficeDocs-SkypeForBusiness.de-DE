---
title: Die wichtigsten Sicherheitsfeatures in Lync Server 2013
TOCTitle: Die wichtigsten Sicherheitsfeatures in Lync Server 2013
ms:assetid: bf2a3b8f-73c6-47e1-8c9e-ca1dc1a502bf
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Dn342829(v=OCS.15)
ms:contentKeyID: 56269344
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Die wichtigsten Sicherheitsfeatures in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2016-12-08_

Lync Server 2013 beinhaltet verschiedene Sicherheitsfeatures wie Server-zu-Server-Authentifizierung, rollenbasierte Zugriffssteuerung und zentrale Speicherung von Konfigurationsdaten.

Dieser Artikel enthält einen allgemeinen Überblick über die Sicherheit von Lync Server 2013.

## Die wichtigsten Sicherheitsfeatures in Lync Server 2013

Sicherheit ist ein sehr umfassendes Thema. Sicherheit betrifft jedes Feature von Lync Server 2013 sowie Datenbanken, Dienste und Hardware, die ein Lync-Ökosystem bilden. In diesem Artikel werden einige der Features in Lync Server 2013, die für Sicherheitszwecke konzipiert sind, besonders umrissen.

## Planungs- und Entwurfstools

Lync Server 2013 stellt zwei Tools bereit, mit denen Planung und Entwurf vereinfacht werden können sowie das Risiko von Fehlkonfigurationen für Lync Server-Komponenten verringert werden kann.

  - Das **Topologieplanungstool** automatisiert einen Großteil des Topologieentwurfsprozesses. Sie können die Ergebnisse aus dem Planungstool in den Topologie-Generator exportieren, der das Tool ist, das zum Installieren jedes Servers mit Lync Server 2013 erforderlich ist.

  - Der **Topologie-Generator** speichert alle Konfigurationsinformationen im zentralen Verwaltungsspeicher.

Ausführliche Informationen zu diesen Tools finden Sie unter [Planung](lync-server-2013-planning.md).

## Zentraler Verwaltungsspeicher (Central Management Store, CMS)

In Lync Server 2013 sind Konfigurationsdaten zu Servern und Diensten Bestandteil des zentralen Verwaltungsspeichers. Der zentrale Verwaltungsspeicher stellt eine robuste und schematisierte Speicherung der Daten bereit, die dazu erforderlich sind, eine Lync Server-Bereitstellung zu definieren, einzurichten, zu warten, zu verwalten und zu betreiben. Darüber hinaus überprüft er die Daten, um eine konsistente Konfiguration zu gewährleisten. Alle Änderungen an diesen Konfigurationsdaten erfolgen im zentralen Verwaltungsspeicher, wodurch Synchronisierungsprobleme beseitigt werden.

Schreibgeschützte Kopien der Daten werden an alle Server in der Topologie repliziert, Edgeserver und Survivable Branch Appliances eingeschlossen. Die Replikation wird von einem Dienst verwaltet, der standardmäßig unter dem Kontext des Netzwerkdiensts ausgeführt wird, wodurch die Rechte und Berechtigungen auf die eines einfachen Benutzers auf dem Computer reduziert werden.

## Server-zu-Server-Authentifizierung

In Lync Server 2013 kann Authentifizierung zwischen Servern mit dem OAuth-Protokoll (Open Authorization) konfiguriert werden. Beispielsweise können Sie Lync Server 2013 so konfigurieren, dass Authentifizierung durch einen Server mit Exchange Server 2013 möglich ist. Durch Verwenden des OAuth-Protokolls können sich der Lync-Server und der Exchange-Server wechselseitig vertrauen. Auf diese Weise können die Produkte nahtlos kombiniert werden. Ausführliche Informationen hierzu finden Sie unter [Verwalten von Server-zu-Server-Authentifizierung (OAuth) und Partneranwendungen](lync-server-2013-managing-server-to-server-authentication-oauth-and-partner-applications.md)

## Windows PowerShell-basierte und webbasierte Verwaltungsschnittstelle

Lync Server 2013 stellt es eine leistungsstarke Verwaltungsschnittstelle bereit, die auf der Windows PowerShell-Befehlszeilenschnittstelle basiert. Sie enthält Cmdlets für die Verwaltung der Sicherheit, und Windows PowerShell-Sicherheitsfeatures sind standardmäßig aktiviert, sodass Skripts von Benutzern nicht versehentlich oder unwissentlich ausgeführt werden können. Dies bedeutet, dass die Softwarestandardeinstellungen so konfiguriert sind, dass die Sicherheit automatisch optimiert wird und Angriffsmöglichkeiten reduziert werden. Ausführliche Informationen zur Unterstützung der Verwaltung mit Windows PowerShell in Lync Server 2013 finden Sie unter [Lync Server-Verwaltungsshell](lync-server-2013-lync-server-management-shell.md).

## Rollenbasierte Zugriffssteuerung (RBAC)

Microsoft Lync Server 2013 stellt rollenbasierte Zugriffssteuerungsgruppen bereit, die Ihnen das Delegieren von Verwaltungsaufgaben ermöglichen und gleichzeitig hohe Sicherheitsstandards unterstützen. Mit der rollenbasierten Zugriffssteuerung können Sie dem Prinzip der geringsten Rechte folgen, bei dem Benutzer nur die administrativen Rechte erhalten, die sie für ihre Arbeit benötigen. Lync Server 2013 ermöglicht es außerdem, neue Rollen zu erstellen sowie vorhandene Rollen zu ändern. Ausführliche Informationen hierzu finden Sie unter [Planen für die rollenbasierte Zugriffssteuerung in Lync Server 2013](lync-server-2013-planning-for-role-based-access-control.md).

## Netzwerkadressenübersetzung (Network Address Translation, NAT)

Die Verwendung der Netzwerkadressenübersetzung (Network Address Translation, NAT) wird in der internen Schnittstelle des Edgeservers nicht von Lync Server 2013 unterstützt. Dagegen wird sowohl in Topologien mit einzelnem konsolidierten Edgeserver als auch in Topologien mit skalierten konsolidierten Edgeservern das Platzieren der externen Schnittstelle des Zugriffs-, Webkonferenz- und A/V-Edgediensts hinter einem Router oder einer Firewall, über den bzw. die eine Netzwerkadressenübersetzung durchgeführt wird, unterstützt. Mehrere Edgeserver hinter einem Hardwaregerät zum Lastenausgleich können keine NAT verwenden. Falls mehrere Edgeserver NAT in ihren externen Schnittstellen verwenden, ist ein DNS-Lastenausgleich (Domain Name System) erforderlich. Die Verwendung eines DNS-Lastenausgleichs wiederum ermöglicht die Reduzierung der Anzahl von öffentlichen IP-Adressen pro Edgeserver in einem Edgeserverpool. Ausführliche Informationen finden hierzu Sie unter [Planen des Zugriffs externer Benutzer in Lync Server 2013](lync-server-2013-planning-for-external-user-access.md).


> [!NOTE]
> Wenn Sie mit einem Verbundunternehmen zusammenarbeiten, das eine Bereitstellung von Microsoft Office Communications Server 2007 hat, und Audio-/Videofunktionen zwischen Ihrem Unternehmen und dem Verbundunternehmen unterstützt werden sollen, entsprechen die Portanforderungen denen für die bereitgestellten älteren Edgeserver. Beispielsweise müssen die für diese älteren Versionen erforderlichen Portbereiche für beide Unternehmen geöffnet sein, bis der Verbundpartner ein Upgrade der Edgeserver auf Lync Server 2013 durchgeführt hat. Dann können die Portanforderungen erneut überprüft und gemäß der neuen Konfiguration vermindert werden.



## Vereinfachte Zertifikate für Edgeserver

Der Bereitstellungs-Assistent kann Antragstellernamen (SNs) und alternative Antragstellernamen (SANs) automatisch ausfüllen. Dadurch reduziert sich das Risiko von unnötigen und potenziell unsicheren Einträgen.

## Trustworthy Computing Security Development Lifecycle (SDL)

Lync Server 2013 wurde in Übereinstimmung mit dem Microsoft Trustworthy Computing Security Development Lifecycle (SDL) entwickelt, der unter <http://go.microsoft.com/fwlink/?linkid=68761> beschrieben ist.

  - **Vertrauenswürdiger Aufbau**   Der erste Schritt beim Erstellen eines sicheren Unified Communications-Systems bestand in der Entwicklung von Gefahrenmodellen und im Testen jedes einzelnen Features während seines Entwurfs. Außerdem führt Microsoft Tests außerhalb des konzipierten Verhaltens aus, um Sicherheitsrisiken zu finden, die sich aus einem nicht erwarteten Produktverhalten ergeben. Viele sicherheitsrelevante Verbesserungen wurden während der Codephase getestet und integriert. Mit Buildzeittools werden Pufferüberläufe und andere potenzielle Sicherheitsbedrohungen erkannt, bevor der Code in das Endprodukt übernommen wird. Natürlich ist es nicht möglich, so zu entwerfen, dass alle unbekannten Sicherheitsbedrohungen abgefangen werden. Es gibt kein System, für das vollständige Sicherheit garantiert werden kann. Da bei der Produktentwicklung jedoch von Anfang an sichere Entwurfsprinzipien angewendet wurden, beinhaltet Lync Server 2013 die branchenüblichen Standardsicherheitstechnologien als grundlegenden Bestandteil seiner Architektur.

  - **Vertrauenswürdig durch seine Standardeinstellungen**   Kommunikationen über Netzwerke werden in Lync Server 2013 standardmäßig verschlüsselt. Da für alle Server Zertifikate und Kerberos-Authentifizierung, TLS, SRTP (Secure Real-Time Transport Protocol) und andere Standardverschlüsselungstechniken einschließlich der 128-Bit-Advanced Encryption Standard (AES)-Verschlüsselung verwendet werden, sind praktisch alle Lync Server-Daten im Netzwerk geschützt. Darüber hinaus ist es aufgrund der rollenbasierten Zugriffssteuerung möglich, Server mit Lync Server 2013 so bereitzustellen, dass nur die Dienste und die damit verbundenen Berechtigungen entsprechend den einzelnen Serverrollen installiert werden.

  - **Vertrauenswürdig durch die Bereitstellung**   Die gesamte Dokumentation zu Lync Server 2013 enthält bewährte Methoden und Empfehlungen, um Sie beim Erkennen und Konfigurieren der optimalen Sicherheitsebenen für Ihre Bereitstellung zu unterstützen und die Bewertung der Risiken bei der Aktivierung von nicht standardmäßigen Optionen zu ermöglichen.

