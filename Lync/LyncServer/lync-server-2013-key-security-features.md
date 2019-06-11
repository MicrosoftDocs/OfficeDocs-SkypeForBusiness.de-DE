---
title: 'Lync Server 2013: wichtige Sicherheitsfeatures'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Key security features in Lync Server 2013
ms:assetid: bf2a3b8f-73c6-47e1-8c9e-ca1dc1a502bf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn342829(v=OCS.15)
ms:contentKeyID: 56107266
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 53a6d9e23442cb127f0f08849e18f1d63bae76d6
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34831960"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="key-security-features-in-lync-server-2013"></a>Wichtige Sicherheitsfeatures in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2013-07-18_

Lync Server 2013 umfasst verschiedene Sicherheitsfeatures, einschließlich Server-zu-Server-Authentifizierung, rollenbasierte Zugriffssteuerung und zentralisierte Speicherung von Konfigurationsdaten.

Dieser Artikel bietet eine allgemeine Übersicht über die lync Server 2013-Sicherheit.

<div>

## <a name="key-security-features-in-lync-server-2013"></a>Wichtige Sicherheits Features in lync Server 2013

Sicherheit ist ein äußerst umfangreiches Thema. Die Sicherheit erreicht alle Funktionen von lync Server 2013 sowie Datenbanken, Dienste und Hardware, die ein lync-Ökosystem ausmachen. In diesem Artikel werden einige der Features in lync Server 2013 erläutert, die speziell für die Sicherheit konzipiert sind.

<div>

## <a name="planning-and-design-tools"></a>Planungs- und Entwurfstools

Lync Server 2013 bietet zwei Tools zur Vereinfachung von Planung und Entwurf sowie zum Verkleinern der Möglichkeit, lync Server-Komponenten zu konfigurieren.

  - Das **Topologie-Planungs Tool** automatisiert einen Großteil des Topologie-Entwurfsprozesses. Sie können die Ergebnisse aus dem Planungstool in den Topologie-Generator exportieren, der das Tool ist, das zum Installieren der einzelnen Server mit lync Server 2013 erforderlich ist.

  - Der **Topologie-Generator** speichert alle Konfigurationsinformationen im zentralen Verwaltungsspeicher.

Details zu diesen Tools finden Sie unter [Planen von lync Server 2013](lync-server-2013-planning.md).

</div>

<div>

## <a name="central-management-store"></a>Zentraler Verwaltungsspeicher (Central Management Store, CMS)

In lync Server 2013 sind Konfigurationsdaten zu Servern und Diensten Teil des zentralen Verwaltungsspeichers. Der zentrale Verwaltungsspeicher bietet eine robuste, schematisierten Speicherung der Daten, die zum definieren, einrichten, verwalten, verwalten, beschreiben und betreiben einer lync Server-Bereitstellung erforderlich sind. Darüber hinaus überprüft er die Daten, um eine konsistente Konfiguration zu gewährleisten. Alle Änderungen an diesen Konfigurationsdaten erfolgen im zentralen Verwaltungsspeicher, wodurch Synchronisierungsprobleme beseitigt werden.

Schreibgeschützte Kopien der Daten werden an alle Server in der Topologie repliziert, Edgeserver und Survivable Branch Appliances eingeschlossen. Die Replikation wird von einem Dienst verwaltet, der standardmäßig unter dem Kontext des Netzwerkdiensts ausgeführt wird, wodurch die Rechte und Berechtigungen auf die eines einfachen Benutzers auf dem Computer reduziert werden.

</div>

<div>

## <a name="server-to-server-authentication"></a>Server-zu-Server-Authentifizierung

In lync Server 2013 kann die Authentifizierung zwischen Servern mithilfe des Open Authorization (OAuth)-Protokolls konfiguriert werden. So können Sie beispielsweise lync Server 2013 für die Authentifizierung bei einem Server konfigurieren, auf dem Exchange Server 2013 ausgeführt wird. Mit dem OAuth-Protokoll können sich der lync-Server und der Exchange-Server gegenseitig vertrauen. Auf diese Weise können die Produkte nahtlos integriert werden. Ausführliche Informationen finden Sie unter [Verwalten von Server-zu-Server-Authentifizierung (OAuth) und Partneranwendungen in lync Server 2013](lync-server-2013-managing-server-to-server-authentication-oauth-and-partner-applications.md)

</div>

<div>

## <a name="windows-powershell-based-management-and-web-based-management-interface"></a>Windows PowerShell-basierte und webbasierte Verwaltungsschnittstelle

Lync Server 2013 bietet eine leistungsfähige Verwaltungsschnittstelle, die auf der Windows PowerShell-Befehlszeilenschnittstelle basiert. Sie enthält Cmdlets für die Verwaltung der Sicherheit und Windows PowerShell-Sicherheitsfeatures sind standardmäßig aktiviert, sodass Skripts von Nutzern nicht versehentlich oder unwissentlich ausgeführt werden können. Dies bedeutet, dass die Softwarestandardeinstellungen so konfiguriert sind, dass die Sicherheit automatisch optimiert wird und Angriffsmöglichkeiten reduziert werden. Details zur Unterstützung der Windows PowerShell-Verwaltung in lync Server 2013 finden Sie unter [lync Server 2013-Verwaltungsshell](lync-server-2013-lync-server-management-shell.md).

</div>

<div>

## <a name="role-based-access-control-rbac"></a>Rollenbasierte Zugriffssteuerung (RBAC)

Microsoft lync Server 2013 bietet rollenbasierte Zugriffssteuerung, mit der Sie Verwaltungsaufgaben delegieren und gleichzeitig hohe Sicherheitsstandards gewährleisten können. Mit der rollenbasierten Zugriffssteuerung können Sie dem Prinzip der geringsten Rechte folgen, bei dem Nutzer nur die administrativen Rechte erhalten, die sie für ihre Arbeit benötigen. Lync Server 2013 bietet eine Einführung in die Möglichkeit, eine neue Rolle zu erstellen und auch die Möglichkeit, eine vorhandene Rolle zu ändern. Ausführliche Informationen finden Sie unter [Planen der rollenbasierten Zugriffssteuerung in lync Server 2013](lync-server-2013-planning-for-role-based-access-control.md).

</div>

</div>

<div>

## <a name="network-address-translation-nat"></a>Netzwerkadressenübersetzung (Network Address Translation, NAT)

Lync Server 2013 unterstützt nicht die Verwendung der Netzwerkadressübersetzung (Network Address Translation, NAT) auf der internen Schnittstelle des Edge-Servers, aber es unterstützt das Platzieren der externen Schnittstelle des Access Edge-Diensts, des Webkonferenz-Edgedienst und des a/V-Edgedienst hinter einer Router oder Firewall, der Netzwerkadressübersetzung (Network Address Translation, NAT) für einzelne und skalierte konsolidierte Edgeserver-Topologien ausführt. Mehrere Edgeserver hinter einem Hardware-Lastenausgleichsmodul können NAT nicht verwenden. Wenn mehrere Edgeserver für Ihre externen Schnittstellen NAT verwenden, ist ein DNS-Lastenausgleich (Domain Name System) erforderlich. Mithilfe des DNS-Lastenausgleichs können Sie wiederum die Anzahl der öffentlichen IP-Adressen pro Edgeserver in einem Edgeserver-Pool reduzieren. Ausführliche Informationen finden Sie unter[Planen des Zugriffs externer Benutzer in lync Server 2013](lync-server-2013-planning-for-external-user-access.md).

<div>


> [!NOTE]  
> Wenn Sie mit einem Verbundunternehmen zusammenarbeiten, das über eine Bereitstellung von Microsoft Office Communications Server 2007 verfügt, und wenn Audio-/Videofunktionen zwischen Ihrem Unternehmen und dem Verbundunternehmen unterstützt werden sollen, entsprechen die Portanforderungen denen für die bereitgestellten älteren Edgeserver. Beispielsweise müssen die für diese älteren Versionen erforderlichen Portbereiche für beide Unternehmen geöffnet werden, bis der Verbundpartner seine Edgeserver auf lync Server 2013 aktualisiert. Dann können die Portanforderungen erneut überprüft und gemäß der neuen Konfiguration vermindert werden.



</div>

</div>

<div>

## <a name="simplified-certificates-for-edge-servers"></a>Vereinfachte Zertifikate für Edgeserver

Der Bereitstellungs-Assistent kann Antragstellernamen (SNs) und alternative Antragstellernamen (SANs) automatisch ausfüllen. Dadurch reduziert sich das Risiko von unnötigen und potenziell unsicheren Einträgen.

</div>

<div>

## <a name="trustworthy-computing-security-development-lifecycle-sdl"></a>Trustworthy Computing Security Development Lifecycle (SDL)

Lync Server 2013 wurde in Übereinstimmung mit dem Microsoft Trustworthy Computing Security Development Lifecycle (SDL) entwickelt und entwickelt, das unter <http://go.microsoft.com/fwlink/?linkid=68761>beschrieben wird.

  - **Vertrauenswürdig durch Design**   der erste Schritt beim Erstellen eines sichereren Unified Communications-Systems war das Entwerfen von Bedrohungsmodellen und das Testen der einzelnen Features, wie Sie entworfen wurden. Außerdem führt Microsoft Tests außerhalb des konzipierten Verhaltens durch, um Sicherheitsrisiken zu finden, die sich aus einem nicht erwarteten Produktverhalten ergeben. Viele sicherheitsrelevante Verbesserungen wurden während der Codephase getestet und integriert. Mit Buildzeittools werden Pufferüberläufe und andere potenzielle Sicherheitsbedrohungen erkannt, bevor der Code in das Endprodukt übernommen wird. Natürlich ist es nicht möglich, so zu entwerfen, dass alle unbekannten Sicherheitsbedrohungen beseitigt werden. Es gibt kein System, für das vollständige Sicherheit garantiert werden kann. Da die Produktentwicklung jedoch von Anfang an sichere Entwurfsprinzipien umfasste, umfasst lync Server 2013 branchenübliche Sicherheitstechnologien als grundlegende Komponente ihrer Architektur.

  - **Vertrauenswürdig**standardmäßig werden Netzwerkkommunikationen in lync Server 2013 standardmäßig verschlüsselt.    Da alle Serverzertifikate und Kerberos-Authentifizierung, TLS, SRTP (Secure Real-Time Transport Protocol) und andere Industriestandard-Verschlüsselungstechniken verwenden, einschließlich AES-Verschlüsselung (128-Bit Advanced Encryption Standard), praktisch alle lync Server Daten sind im Netzwerk geschützt. Darüber hinaus ermöglicht die rollenbasierte Zugriffssteuerung die Bereitstellung von Servern mit lync Server 2013, damit jede Serverrolle nur die Dienste ausführt und nur die Berechtigungen enthält, die sich auf diese Dienste beziehen, die für die Serverrolle geeignet sind.

  - **Vertrauenswürdig durch Bereitstellung**   alle lync Server 2013-Dokumentation enthält bewährte Methoden und Empfehlungen, die Ihnen helfen, die optimalen Sicherheitsstufen für Ihre Bereitstellung zu ermitteln und zu konfigurieren und die Sicherheitsrisiken bei der Aktivierung nicht standardmäßiger Funktionen zu bewerten. Optionen.

</div>

</div>

<span> </span>

</div>

</div>

</div>

