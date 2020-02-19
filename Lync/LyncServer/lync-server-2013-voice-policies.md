---
title: 'Lync Server 2013: VoIP-Richtlinien'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Voice policies
ms:assetid: b7433c62-9d8c-48af-89a0-19f0d34806ec
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412891(v=OCS.15)
ms:contentKeyID: 48185223
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 769524594496598581814462dcf8f6827d3c2616
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2020
ms.locfileid: "42120468"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="voice-policies-in-lync-server-2013"></a>VoIP-Richtlinien in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2012-09-21_

In lync Server *VoIP-Richtlinien* werden für jeden Benutzer, Standort oder jede Organisation, dem die Richtlinie zugewiesen ist, Folgendes definiert:

  - Eine Reihe von Anruffunktionen, die aktiviert oder deaktiviert werden können, um die für Benutzer verfügbare Enterprise-VoIP-Funktionalität zu bestimmen.

  - Einer Gruppe von Telefonfestnetz-Verwendungsdatensätzen, die festlegen, welche Arten von Anrufen erlaubt sind.

<div>

## <a name="planning-for-voice-policies"></a>Planen der VoIP-Richtlinien

Die folgenden Schritte helfen Ihnen beim Planen der VoIP-Richtlinien, die Sie für Ihre Enterprise-VoIP-Bereitstellung benötigen:

  - Legen Sie fest, wie die globale VoIP-Richtlinie (die Standard-VoIP-Richtlinie, die mit dem Produkt installiert wird), konfiguriert werden soll. Diese Richtlinie gilt für alle Enterprise-VoIP-Benutzer, denen nicht explizit eine Richtlinie auf Standort-oder Benutzerebene zugewiesen ist.

  - Bestimmen der ggf. erforderlichen VoIP-Richtlinien auf Standortebene.

  - Bestimmen der ggf. erforderlichen benutzerbezogenen VoIP-Richtlinien.

  - Entscheiden, welche Anruffunktionen für jede VoIP-Richtlinie aktiviert werden sollen.

  - Bestimmen, welche PSTN-Verwendungsdatensätze für jede VoIP-Richtlinie konfiguriert werden sollen.

<div>

## <a name="voice-policy-scope"></a>Gültigkeitsbereich von VoIP-Richtlinien

Der *Gültigkeitsbereich von VoIP-Richtlinien* bestimmt die Hierarchieebene, auf der die Richtlinie gelten soll. In lync Server können Sie VoIP-Richtlinien mit den folgenden Bereichsebenen konfigurieren (aufgeführt aus den am häufigsten verwendeten für die allgemeinsten).

  - Die **VoIP-Benutzerrichtlinie** kann einzelnen Benutzern, Gruppen oder Kontaktobjekten zugewiesen werden. Dies ist die niedrigste Richtlinienebene. VoIP-Benutzerrichtlinien können bereitgestellt werden, um Funktionen nur für bestimmte Benutzer oder Gruppen an einem Standort zu aktivieren. Sie können damit z. B. bei bestimmten Mitarbeitern Ferngespräche deaktivieren. Damit eine VoIP-Richtlinie zugewiesen werden kann, wird ein Kontaktobjekt wie ein Einzelbenutzer behandelt.
    
    <div>
    

    > [!NOTE]  
    > Es wird empfohlen, eine Benutzer VoIP-Richtlinie für die Niederlassung von Enterprise-VoIP-Benutzern bereitzustellen, die bei der zentralen Standortbereitstellung registriert sind, oder für Benutzer, die in einem Survivable Branch Appliance registriert sind.

    
    </div>

  - Eine **VoIP-Standortrichtlinie** gilt für einen gesamten Standort. Ausgenommen sind Benutzer, Gruppen oder Kontaktobjekte, denen eine Benutzerrichtlinie zugeordnet wurde. Zum Definieren einer VoIP-Standortrichtlinie müssen Sie den Standort angeben, für den die Richtlinie gelten soll. Wenn keine VoIP-Benutzerrichtlinie zugewiesen ist, wird die VoIP-Standortrichtlinie verwendet.

  - **Globale VoIP-Richtlinie** ist die standardmäßige VoIP-Richtlinie, die mit dem Produkt installiert wird. Sie können die globale VoIP-Richtlinie so bearbeiten, dass Sie den spezifischen Anforderungen Ihrer Organisation entspricht, Sie können Sie jedoch nicht umbenennen oder löschen. Diese VoIP-Richtlinie gilt für alle Enterprise-VoIP-Benutzer,-Gruppen und-Kontaktobjekte in Ihrer Bereitstellung, sofern Sie keine VoIP-Richtlinie mit spezifischeren Bereich konfigurieren und zuweisen. Wenn Sie diese Richtlinie vollständig deaktivieren möchten, stellen Sie sicher, dass allen Websites und Benutzern benutzerdefinierte Richtlinien zugewiesen sind.

</div>

<div>

## <a name="call-features"></a>Anruffunktionen

Für jede Richtlinie können Sie die folgenden Anruffunktionen aktivieren oder deaktivieren:

  - **Anrufweiterleitung** ermöglicht Benutzern das Weiterleiten von Anrufen an andere Telefone und Clientgeräte. Diese Option ist standardmäßig aktiviert.

  - **Delegierung** ermöglicht Benutzern die Angabe anderer Benutzer, die in ihrem Namen Anrufe tätigen und empfangen können. Diese Option ist standardmäßig aktiviert.

  - **Anrufdurchstellung** ermöglicht es, Anrufe an andere Benutzer durchzustellen. Diese Option ist standardmäßig aktiviert.

  - **Anruf parken** ermöglicht es Benutzern, Anrufe in der Warteschleife zu parken und den Anruf von einem anderen Telefon oder Client aus wiederaufzunehmen. Diese Option ist standardmäßig deaktiviert.

  - **Gleichzeitiges Klingeln** ermöglicht bei eingehenden Anrufen das gleichzeitige Läuten auf zusätzlichen Telefonen (z. B. einem Mobiltelefon) oder anderen Endpunktgeräten. Diese Option ist standardmäßig aktiviert.

  - **Teamanruf** ermöglicht Benutzern in einem definierten Team die Annahme von Anrufen für andere Teammitglieder. Diese Option ist standardmäßig aktiviert.

  - **PSTN-Umleitung** ermöglicht das Umleiten von Anrufen von Benutzern, denen diese Richtlinie zugewiesen wurde, an andere Benutzer im Unternehmen über das Festnetz, wenn das WAN überlastet oder nicht verfügbar ist. Diese Option ist standardmäßig aktiviert.

  - **Außerkraftsetzung der Bandbreitenrichtlinie** ermöglicht es Administratoren, Richtlinienentscheidungen im Rahmen der Anrufsteuerung für einen bestimmten Benutzer außer Kraft zu setzen. Diese Option ist standardmäßig deaktiviert.

  - Durch die **Ablaufverfolgung für böswillige** Anrufe können Benutzer böswillige Anrufe über den lync-Client melden und dann solche Anrufe in den Anruf Detaildatensätzen kennzeichnen. Diese Option ist standardmäßig deaktiviert.

  - **Voicemail-Ausweg** verhindert, dass Anrufe sofort an das Voicemail-System des Mobiltelefons des Benutzers weitergeleitet werden, wenn gleichzeitiges Klingeln konfiguriert und das Telefon abgeschaltet, ohne Strom oder außer Reichweite ist und auf einem Timer-Wert basiert. Diese Einstellung aktiviert und deaktiviert den Timer und stellt den Wert des Timers ein. Sie kann nur mithilfe der lync Server-Verwaltungsshell konfiguriert werden. Diese ist standardmäßig deaktiviert.

  - **PSTN-Verwendungen Anrufweiterleitung und Gleichzeitiges Klingeln** ermöglicht Administratoren, bei Anrufweiterleitung und gleichzeitigem Klingeln die gleiche PSTN-Verwendung wie für die VoIP-Richtlinie anzugeben, Anrufweiterleitung und gleichzeitiges Klingeln auf interne Lync-Benutzer zu beschränken oder eine benutzerdefinierte PSTN-Verwendung anzugeben, die sich von der PSTN-Verwendung der VoIP-Richtlinie unterscheidet. Standardmäßig wird für Anrufweiterleitung und gleichzeitiges Klingeln die gleiche PSTN-Verwendung verwendet, wie bei der VoIP-Richtlinie.

</div>

<div>

## <a name="pstn-usage-records"></a>PSTN-Verwendungsdatensätze

Jeder VoIP-Richtlinie muss mindestens ein PSTN-Verwendungsdatensatz zugeordnet sein. PSTN-Verwendungen können nur zum Zweck von Anrufweiterleitung und gleichzeitigem Klingeln einer VoIP-Richtlinie zugeordnet sein. Ausführliche Informationen zum Planen von PSTN-Verwendungsdatensätzen finden Sie unter [PSTN-Verwendungsdaten Sätze in lync Server 2013](lync-server-2013-pstn-usage-records.md).

<div>


> [!NOTE]  
> Die Reihenfolge der PSTN-Verwendungsdatensätze ist wichtig, da die Ausgangsroutingfunktion beim Zuordnen von Benutzern zu Routen die PSTN-Verwendungsdatensätze von oben nach unten vergleicht. Wenn der erste Datensatz mit der Anrufroute übereinstimmt, wird diese Route verwendet. Falls nicht, unterstützt die Ausgangsroutingfunktion den nächsten PSTN-Verwendungsdatensatz in der Liste und fährt damit fort, bis eine Übereinstimmung gefunden wird. Die nachfolgenden PSTN-Verwendungsdatensätze dienen der zusätzlichen Absicherung, wenn der erste Datensatz in der Liste nicht verfügbar ist.



</div>

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

