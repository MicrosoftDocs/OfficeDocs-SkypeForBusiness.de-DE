---
title: 'Lync Server 2013: wichtige Sicherheitsfeatures'
description: 'Lync Server 2013: wichtige Sicherheitsfeatures.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Key security features in Lync Server 2013
ms:assetid: bf2a3b8f-73c6-47e1-8c9e-ca1dc1a502bf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn342829(v=OCS.15)
ms:contentKeyID: 56107266
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 689cf2ac54eacd24bb4d31b451836edcf676521b
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48557611"
---
# <a name="key-security-features-in-lync-server-2013"></a>Wichtige Sicherheitsfeatures in lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2013-07-18_

Lync Server 2013 umfasst verschiedene Sicherheitsfeatures, einschließlich Server-zu-Server-Authentifizierung, rollenbasierte Zugriffssteuerung und zentralisierte Speicherung von Konfigurationsdaten.

Dieser Artikel bietet eine allgemeine Übersicht über lync Server 2013 Sicherheit.

<div>

## <a name="key-security-features-in-lync-server-2013"></a>Wichtige Sicherheits Features in lync Server 2013

Sicherheit ist ein sehr breites Thema. Die Sicherheit erreicht alle Funktionen von lync Server 2013 sowie Datenbanken, Dienste und Hardware, aus denen ein lync-Ökosystem besteht. In diesem Artikel werden einige der Features in lync Server 2013 beschrieben, die speziell auf die Sicherheit ausgelegt sind.

<div>

## <a name="planning-and-design-tools"></a>Planungs-und Entwurfs Tools

Lync Server 2013 bietet zwei Tools zur Vereinfachung der Planung und des Designs sowie zur Verringerung der Wahrscheinlichkeit, dass lync Server-Komponenten nicht mehr konfiguriert werden können.

  - Das **Topologie-Planungs Tool** automatisiert einen Großteil des Topologie-Entwurfsprozesses. Sie können die Ergebnisse aus dem Planungstool in den Topologie-Generator exportieren, bei dem es sich um das Tool handelt, das zum Installieren der einzelnen Server mit lync Server 2013 erforderlich ist.

  - Im **Topologie-Generator** werden alle Konfigurationsinformationen im zentralen Verwaltungsspeicher gespeichert.

Ausführliche Informationen zu diesen Tools finden Sie unter [Planning for lync Server 2013](lync-server-2013-planning.md).

</div>

<div>

## <a name="central-management-store"></a>Zentraler Verwaltungsspeicher

In lync Server 2013 sind Konfigurationsdaten zu Servern und Diensten Teil des zentralen Verwaltungsspeichers. Der zentrale Verwaltungsspeicher bietet eine robuste, schematisierten Speicherung der Daten, die für die Definition, Einrichtung, Verwaltung, Verwaltung, Beschreibung und den Betrieb einer lync Server-Bereitstellung benötigt werden. Darüber hinaus werden die Daten überprüft, um eine konsistente Konfiguration zu gewährleisten. Alle Änderungen an diesen Konfigurationsdaten erfolgen im zentralen Verwaltungsspeicher, wodurch nicht mehr synchrone Probleme auftreten.

Schreibgeschützte Kopien der Daten werden auf alle Server in der Topologie repliziert, Edgeserver eingeschlossen. Die Replikation wird von einem Dienst verwaltet, der standardmäßig unter dem Kontext des Netzwerkdiensts ausgeführt wird, wodurch die Rechte und Berechtigungen auf die eines einfachen Benutzers auf dem Computer reduziert werden.

</div>

<div>

## <a name="server-to-server-authentication"></a>Server-zu-Server-Authentifizierung

In lync Server 2013 kann die Authentifizierung zwischen Servern mithilfe des Open Authorization (OAuth)-Protokolls konfiguriert werden. Beispielsweise können Sie lync Server 2013 für die Authentifizierung bei einem Server konfigurieren, auf dem Exchange Server 2013 läuft. Mithilfe des OAuth-Protokolls können der lync-Server und der Exchange-Server einander vertrauen. Auf diese Weise können Sie die Produkte nahtlos integrieren. Ausführliche Informationen finden Sie unter [Managing Server-to-Server Authentication (OAuth) and Partner Applications in lync Server 2013](lync-server-2013-managing-server-to-server-authentication-oauth-and-partner-applications.md)

</div>

<div>

## <a name="windows-powershell-based-management-and-web-based-management-interface"></a>Windows PowerShell basierte Verwaltung und webbasierte Verwaltungsschnittstelle

Lync Server 2013 bietet eine leistungsstarke Verwaltungsschnittstelle, die auf der Windows PowerShell-Befehlszeilenschnittstelle basiert. Sie enthält Cmdlets für die Verwaltung der Sicherheit, und Windows PowerShell-Sicherheitsfeatures sind standardmäßig aktiviert, sodass Skripts von Benutzern nicht versehentlich oder unwissentlich ausgeführt werden können. Dies bedeutet, dass die Softwarestandardeinstellungen so konfiguriert sind, dass die Sicherheit automatisch optimiert wird und Angriffsmöglichkeiten reduziert werden. Ausführliche Informationen zur Windows PowerShell-Verwaltungsunterstützung in lync Server 2013 finden Sie unter [lync Server 2013 Management Shell](lync-server-2013-lync-server-management-shell.md).

</div>

<div>

## <a name="role-based-access-control-rbac"></a>Role-Based Zugriffssteuerung (RBAC)

Microsoft lync Server 2013 bietet rollenbasierte Zugriffssteuerung (Role-Based Access Control, RBAC), mit der Sie administrative Aufgaben delegieren und gleichzeitig hohe Sicherheitsstandards aufrecht erhalten können. Mit der rollenbasierten Zugriffssteuerung können Sie dem Prinzip der geringsten Rechte folgen, bei dem Benutzer nur die administrativen Rechte erhalten, die sie für ihre Arbeit benötigen. Lync Server 2013 bietet die Möglichkeit, eine neue Rolle zu erstellen und außerdem die Möglichkeit, eine vorhandene Rolle zu ändern. Ausführliche Informationen finden Sie unter [Planen der rollenbasierten Zugriffssteuerung in lync Server 2013](lync-server-2013-planning-for-role-based-access-control.md).

</div>

</div>

<div>

## <a name="network-address-translation-nat"></a>Netzwerkadressübersetzung (Network Address Translation, NAT)

Lync Server 2013 unterstützt nicht die Verwendung der Netzwerkadressübersetzung (Network Address Translation, NAT) auf der internen Schnittstelle des Edgeserver, aber es unterstützt das Platzieren der externen Schnittstelle der Zugriffs-Edgedienst, Webkonferenz-Edgedienst und A/V-Edgedienst hinter einem Router oder einer Firewall, die Netzwerkadressübersetzung (Network Address Translation, NAT) für einzelne und skalierte konsolidierte Edgeserver Topologien ausführt. Mehrere Edgeserver hinter einem Hardwaregerät zum Lastenausgleich können keine NAT verwenden. Wenn mehrere Edgeserver NAT auf Ihren externen Schnittstellen verwenden, ist Domain Name System (DNS) Lastenausgleich erforderlich. Mithilfe des DNS-Lastenausgleichs können Sie wiederum die Anzahl der öffentlichen IP-Adressen pro Edgeserver in einem Edgeserver-Pool reduzieren. Ausführliche Informationen finden Sie unter[Planning for external User Access in lync Server 2013](lync-server-2013-planning-for-external-user-access.md).

<div>


> [!NOTE]  
> Wenn Sie einen Verbund mit Unternehmen mit einer Microsoft Office Communications Server 2007-Bereitstellung haben und Sie Audio/Video zwischen Ihrem Unternehmen und dem Verbundunternehmen verwenden müssen, werden die Portanforderungen für die ältere Version der bereitgestellten Edgeserver verwendet. Beispielsweise müssen die für diese älteren Versionen erforderlichen Portbereiche für beide Unternehmen geöffnet werden, bis der Partnerverbund seine Edgeserver auf lync Server 2013 aktualisiert. Dann können die Portanforderungen erneut überprüft und gemäß der neuen Konfiguration vermindert werden.



</div>

</div>

<div>

## <a name="simplified-certificates-for-edge-servers"></a>Vereinfachte Zertifikate für Edgeserver

Der Bereitstellungs-Assistent kann automatisch die Antragstellernamen (SNS) und die alternativen Antragstellernamen (Subject Alternative Names, Sans) auffüllen, wodurch die Möglichkeit zur Einbeziehung unnötiger und potenziell unsich

</div>

<div>

## <a name="trustworthy-computing-security-development-lifecycle-sdl"></a>Trustworthy Computing Security Development Lifecycle (SDL)

Lync Server 2013 wurde in Übereinstimmung mit dem Microsoft Trustworthy Computing Security Development Lifecycle (SDL) entworfen und entwickelt, der unter beschrieben wird <https://go.microsoft.com/fwlink/?linkid=68761> .

  - **Vertrauenswürdig nach Design**     Der erste Schritt bei der Erstellung eines sicheren Unified Communications-Systems war das Entwerfen von Bedrohungsmodellen und das Testen der einzelnen Features, die so entworfen wurden. Darüber hinaus führt Microsoft Tests außerhalb des entworfenen Verhaltens durch, um Sicherheitsrisiken zu finden, die aus einem unerwarteten Produktverhalten resultieren. Mehrere sicherheitsrelevante Verbesserungen wurden während der Codephase getestet und integriert. Mit Buildzeittools werden Pufferüberläufe und andere potenzielle Sicherheitsbedrohungen erkannt, bevor der Code in das Endprodukt aufgenommen wird. Natürlich ist es nicht möglich, alle unbekannten Sicherheitsbedrohungen vorherzusehen. Es gibt kein System ohne Sicherheitslücken. Da die Produktentwicklung jedoch von Anfang an sichere Entwurfsprinzipien umfasste, umfasst lync Server 2013 Branchenstandard-Sicherheitstechnologien als grundlegender Bestandteil ihrer Architektur.

  - **Standardmäßig**     vertrauenswürdig Die Netzwerkkommunikation in lync Server 2013 wird standardmäßig verschlüsselt. Da alle Serverzertifikate und Kerberos-Authentifizierung, TLS, Secure Real-Time Transport Protocol (SRTP) und andere Standard Verschlüsselungstechniken (einschließlich 128-Bit Advanced Encryption Standard) (AES)-Verschlüsselung verwenden, sind praktisch alle lync Server Daten im Netzwerk geschützt. Darüber hinaus ermöglicht die rollenbasierte Zugriffssteuerung die Bereitstellung von Servern, auf denen lync Server 2013 ausgeführt wird, sodass jede Serverrolle nur die Dienste ausführt und nur über die Berechtigungen für diese Dienste verfügt, die für die Serverrolle geeignet sind.

  - **Vertrauenswürdig durch Bereitstellung**     In der lync Server 2013 Dokumentation finden Sie bewährte Methoden und Empfehlungen, mit denen Sie die optimalen Sicherheitsstufen für Ihre Bereitstellung ermitteln und konfigurieren und die Sicherheitsrisiken der Aktivierung nicht standardmäßiger Optionen bewerten können.

</div>

</div>

<span> </span>

</div>

</div>

</div>

