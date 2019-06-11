---
title: 'Lync Server 2013: VoIP-Richtlinien'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Voice policies
ms:assetid: b7433c62-9d8c-48af-89a0-19f0d34806ec
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412891(v=OCS.15)
ms:contentKeyID: 48185223
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ca1e72a1b62a224898d98aec7fcef9bc62ddf8bc
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34847178"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="voice-policies-in-lync-server-2013"></a>VoIP-Richtlinien in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2012-09-21_

Lync Server- *VoIP-Richtlinien* definieren für jeden Benutzer, jede Website oder jede Organisation, der die Richtlinie zugewiesen ist, die folgenden Punkte:

  - Eine Reihe von Anruffeatures, die aktiviert oder deaktiviert werden können, um die für Benutzer verfügbare Enterprise-VoIP-Funktionalität zu ermitteln.

  - Einer Gruppe von Telefonfestnetz-Verwendungseinträgen, die festlegen, welche Arten von Anrufen erlaubt sind.

<div>

## <a name="planning-for-voice-policies"></a>Planen von VoIP-Richtlinien

Mit den folgenden Schritten können Sie die VoIP-Richtlinien planen, die Sie für Ihre Enterprise-VoIP-Bereitstellung benötigen:

  - Legen Sie fest, wie die globale VoIP-Richtlinie (die Standard-VoIP-Richtlinie, die mit dem Produkt installiert wird) konfiguriert werden soll. Diese Richtlinie gilt für alle Enterprise-VoIP-Benutzer, denen nicht explizit eine Richtlinie auf Website-oder Benutzerebene zugewiesen ist.

  - Bestimmen der ggf. erforderlichen VoIP-Richtlinien auf Standortebene.

  - Bestimmen der ggf. erforderlichen benutzerbezogenen VoIP-Richtlinien.

  - Entscheiden, welche Anruffunktionen für jede VoIP-Richtlinie aktiviert werden sollen.

  - Bestimmen, welche PSTN-Verwendungseinträge für jede VoIP-Richtlinie konfiguriert werden sollen.

<div>

## <a name="voice-policy-scope"></a>Gültigkeitsbereich von VoIP-Richtlinien

Der *Gültigkeitsbereich von VoIP-Richtlinien* bestimmt die Hierarchieebene, auf der die Richtlinie gelten soll. In lync Server können Sie VoIP-Richtlinien mit den folgenden Bereichsebenen konfigurieren (in der Liste der am häufigsten vorgestellten).

  - Die **VoIP-Benutzerrichtlinie** kann einzelnen Benutzern, Gruppen oder Kontaktobjekten zugewiesen werden. Dies ist die niedrigste Richtlinienebene. VoIP-Benutzerrichtlinien können bereitgestellt werden, um Funktionen nur für bestimmte Benutzer oder Gruppen an einem Standort zu aktivieren. Sie können damit z. B. bei bestimmten Mitarbeitern Ferngespräche deaktivieren. Damit eine VoIP-Richtlinie zugewiesen werden kann, wird ein Kontaktobjekt wie ein Einzelbenutzer behandelt.
    
    <div>
    

    > [!NOTE]  
    > Wir empfehlen, dass Sie eine Benutzer VoIP-Richtlinie für Branch Site Enterprise-VoIP-Benutzer bereitstellen, die bei der zentralen Website Bereitstellung registriert sind, oder für Benutzer, die auf einer Survivable Branch-Appliance registriert sind.

    
    </div>

  - Eine **VoIP-Standortrichtlinie** gilt für einen gesamten Standort. Ausgenommen sind Benutzer, Gruppen oder Kontaktobjekte, denen eine Benutzerrichtlinie zugeordnet wurde. Zum Definieren einer VoIP-Standortrichtlinie müssen Sie den Standort angeben, für den die Richtlinie gelten soll. Wenn keine VoIP-Benutzerrichtlinie zugewiesen ist, wird die VoIP-Standortrichtlinie verwendet.

  - Bei der **globalen VoIP-Richtlinie** handelt es sich um die Standard VoIP-Richtlinie, die mit dem Produkt installiert wird. Sie können die globale VoIP-Richtlinie bearbeiten, um die spezifischen Anforderungen Ihrer Organisation zu erfüllen, Sie können Sie jedoch nicht umbenennen oder löschen. Diese VoIP-Richtlinie gilt für alle Enterprise-VoIP-Benutzer, Gruppen und Kontaktobjekte in Ihrer Bereitstellung, es sei denn, Sie konfigurieren und weisen eine VoIP-Richtlinie mit einem spezifischeren Bereich zu. Wenn Sie diese Richtlinie vollständig deaktivieren möchten, stellen Sie sicher, dass allen Websites und Benutzern benutzerdefinierte Richtlinien zugewiesen sind.

</div>

<div>

## <a name="call-features"></a>Anruffunktionen

Für jede Richtlinie können Sie die folgenden Anruffunktionen aktivieren oder deaktivieren:

  - **Anrufweiterleitung** ermöglicht Benutzern das Weiterleiten von Anrufen an andere Telefone und Clientgeräte. Diese Option ist standardmäßig aktiviert.

  - **Delegierung** ermöglicht Benutzern die Angabe anderer Benutzer, die in ihrem Namen Anrufe tätigen und empfangen können. Diese Option ist standardmäßig aktiviert.

  - **Anrufdurchstellung** ermöglicht Benutzern, Anrufe an andere Benutzer durchzustellen. Diese Option ist standardmäßig aktiviert.

  - **Anruf parken** ermöglicht Benutzern, Anrufe in der Warteschleife zu parken und mit einem anderen Telefon oder Clientgerät wiederaufzunehmen. Diese Option ist standardmäßig deaktiviert.

  - **Gleichzeitiges Klingeln** ermöglicht bei eingehenden Anrufen das gleichzeitige Läuten auf zusätzlichen Telefonen (z. B. einem Mobiltelefon) oder anderen Endpunktgeräten. Diese Option ist standardmäßig aktiviert.

  - **Teamanruf** ermöglicht Benutzern in einem definierten Team die Annahme von Anrufen für andere Teammitglieder. Diese Option ist standardmäßig aktiviert.

  - **PSTN-Umleitung** ermöglicht das Umleiten von Anrufen von Benutzern, denen diese Richtlinie zugewiesen wurde, an andere Benutzer im Unternehmen über das Festnetz, wenn das WAN überlastet oder nicht verfügbar ist. Diese Option ist standardmäßig aktiviert.

  - **Außerkraftsetzung der Bandbreitenrichtlinie** ermöglicht Administratoren, Richtlinienentscheidungen im Rahmen der Anrufsteuerung für einen bestimmten Benutzer außer Kraft zu setzen. Diese Option ist standardmäßig deaktiviert.

  - Durch eine **böswillige Anrufprotokollierung** können Benutzer böswillige Anrufe über den lync-Client melden und diese dann in den Anruf Detaildatensätzen kennzeichnen. Diese Option ist standardmäßig deaktiviert.

  - **Voicemail-Ausweg** verhindert, dass Anrufe sofort an das Voicemail-System des Mobiltelefons des Benutzers weitergeleitet werden, wenn gleichzeitiges Klingeln konfiguriert und das Telefon abgeschaltet, ohne Strom oder außer Reichweite ist und auf einem Timer-Wert basiert. Mit dieser Einstellung wird der Timer aktiviert und deaktiviert sowie der Wert des Timers eingestellt. Sie kann nur mithilfe der lync Server-Verwaltungsshell konfiguriert werden. Diese ist standardmäßig deaktiviert.

  - **Anrufweiterleitung und gleichzeitiges anrufen PSTN** -Nutzungen ermöglicht es Administratoren, dieselbe PSTN-Nutzung wie die VoIP-Richtlinie für die Anrufweiterleitung und gleichzeitiges Klingeln festzulegen, die Anrufweiterleitung und das gleichzeitige Klingeln nur für interne lync-Benutzer zu beschränken. oder geben Sie eine benutzerdefinierte PSTN-Nutzung an, die von der PSTN-Nutzung der VoIP-Richtlinie abweicht. Standardmäßig wird für Anrufweiterleitung und gleichzeitiges Klingeln die gleiche PSTN-Verwendung verwendet wie bei der VoIP-Richtlinie.

</div>

<div>

## <a name="pstn-usage-records"></a>PSTN-Verwendungseinträge

Jeder VoIP-Richtlinie muss mindestens ein PSTN-Verwendungseintrag zugeordnet sein. PSTN-Verwendungen können nur zum Zweck von Anrufweiterleitung und gleichzeitigem Klingeln einer VoIP-Richtlinie zugeordnet sein. Details zum Planen von PSTN-Verwendungsdatensätzen finden Sie unter [PSTN-Verwendungsdaten Sätze in lync Server 2013](lync-server-2013-pstn-usage-records.md).

<div>


> [!NOTE]  
> Die Reihenfolge der PSTN-Verwendungseinträge ist wichtig, da die Ausgangsroutingfunktion beim Zuordnen von Benutzern zu Routen die PSTN-Verwendungseinträge von oben nach unten vergleicht. Wenn der erste Eintrag mit der Anrufroute übereinstimmt, wird diese Route verwendet. Falls nicht, unterstützt die Ausgangsroutingfunktion den nächsten PSTN-Verwendungseintrag in der Liste und fährt damit fort, bis eine Übereinstimmung gefunden wird. Die nachfolgenden PSTN-Verwendungseinträge dienen zur zusätzlichen Absicherung, wenn der erste Datensatz in der Liste nicht verfügbar ist.



</div>

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

