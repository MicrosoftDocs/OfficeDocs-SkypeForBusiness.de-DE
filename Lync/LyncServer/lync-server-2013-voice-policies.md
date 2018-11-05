---
title: 'Lync Server 2013: VoIP-Richtlinien'
TOCTitle: VoIP-Richtlinien
ms:assetid: b7433c62-9d8c-48af-89a0-19f0d34806ec
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg412891(v=OCS.15)
ms:contentKeyID: 49295175
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# VoIP-Richtlinien in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2012-09-21_

Lync Server- *VoIP-Richtlinien* dienen zum Festlegen der folgenden Einstellungen für alle Benutzer, Standorte und Organisationen, denen die Richtlinie zugewiesen wird:

  - Einer Gruppe von Anruffunktionen, die aktiviert oder deaktiviert werden kann, um die Enterprise-VoIP-Funktionen zu bestimmen, die Benutzern zur Verfügung stehen.

  - Einer Gruppe von Telefonfestnetz-Verwendungsdatensätzen, die festlegen, welche Arten von Anrufen erlaubt sind.

## Planen der VoIP-Richtlinien

Die folgenden Schritte helfen Ihnen beim Planen der VoIP-Richtlinien, die Sie für Ihre Enterprise-VoIP-Bereitstellung benötigen:

  - Legen Sie fest, wie die globale VoIP-Richtlinie (die Standard-VoIP-Richtlinie, die mit dem Produkt installiert wird), konfiguriert werden soll. Diese Richtlinie gilt für alle Enterprise-VoIP-Benutzer, denen nicht explizit eine Richtlinie auf Standortebene oder benutzerbezogene Richtlinie zugewiesen wurde.

  - Bestimmen der ggf. erforderlichen VoIP-Richtlinien auf Standortebene.

  - Bestimmen der ggf. erforderlichen benutzerbezogenen VoIP-Richtlinien.

  - Entscheiden, welche Anruffunktionen für jede VoIP-Richtlinie aktiviert werden sollen.

  - Bestimmen, welche PSTN-Verwendungsdatensätze für jede VoIP-Richtlinie konfiguriert werden sollen.

## Gültigkeitsbereich von VoIP-Richtlinien

Der *Gültigkeitsbereich von VoIP-Richtlinien* bestimmt die Hierarchieebene, auf der die Richtlinie gelten soll. In Lync Server können Sie VoIP-Richtlinien mit den folgenden Gültigkeitsbereichsebenen (von spezifisch zu allgemein) konfigurieren.

  - Die **VoIP-Benutzerrichtlinie** kann einzelnen Benutzern, Gruppen oder Kontaktobjekten zugewiesen werden. Dies ist die niedrigste Richtlinienebene. VoIP-Benutzerrichtlinien können bereitgestellt werden, um Funktionen nur für bestimmte Benutzer oder Gruppen an einem Standort zu aktivieren. Sie können damit z. B. bei bestimmten Mitarbeitern Ferngespräche deaktivieren. Damit eine VoIP-Richtlinie zugewiesen werden kann, wird ein Kontaktobjekt wie ein Einzelbenutzer behandelt.
    

    > [!NOTE]
    > Es wird empfohlen, dass für Enterprise-VoIP-Benutzer an einem Zweigstellenstandort, die bei der Bereitstellung am zentralen Standort registriert sind oder bei einer Survivable Branch Appliance registriert sind, eine VoIP-Benutzerrichtlinie aktiviert wird.



  - Eine **VoIP-Standortrichtlinie** gilt für einen gesamten Standort. Ausgenommen sind Benutzer, Gruppen oder Kontaktobjekte, denen eine Benutzerrichtlinie zugeordnet wurde. Zum Definieren einer VoIP-Standortrichtlinie müssen Sie den Standort angeben, für den die Richtlinie gelten soll. Wenn keine VoIP-Benutzerrichtlinie zugewiesen ist, wird die VoIP-Standortrichtlinie verwendet.

  - Die **Global VoIP-Richtlinie** ist die mit dem Produkt installierte VoIP-Standardrichtlinie. Sie können die globale VoIP-Richtlinie so bearbeiten, dass bestimmte Anforderungen Ihrer Organisation erfüllt werden. Sie können sie jedoch nicht umbenennen oder löschen. Diese VoIP-Richtlinie gilt für alle Enterprise-VoIP-Benutzer, -Gruppen und -Kontaktobjekte in Ihrer Bereitstellung, es sei denn, Sie konfigurieren eine VoIP-Richtlinie mit einem spezifischeren Gültigkeitsbereich und weisen diese zu. Wenn Sie diese Richtlinie vollständig deaktivieren möchten, vergewissern Sie sich, dass allen Standorten und Benutzern benutzerdefinierte Richtlinien zugewiesen sind.

## Anruffunktionen

Für jede Richtlinie können Sie die folgenden Anruffunktionen aktivieren oder deaktivieren:

  - **Anrufweiterleitung** ermöglicht Benutzern das Weiterleiten von Anrufen an andere Telefone und Clientgeräte. Diese Option ist standardmäßig aktiviert.

  - **Delegierung** ermöglicht Benutzern die Angabe anderer Benutzer, die in ihrem Namen Anrufe tätigen und empfangen können. Diese Option ist standardmäßig aktiviert.

  - **Anrufdurchstellung** ermöglicht es, Anrufe an andere Benutzer durchzustellen. Diese Option ist standardmäßig aktiviert.

  - **Anruf parken** ermöglicht es Benutzern, Anrufe in der Warteschleife zu parken und den Anruf von einem anderen Telefon oder Client aus wiederaufzunehmen. Diese Option ist standardmäßig deaktiviert.

  - **Gleichzeitiges Klingeln** ermöglicht bei eingehenden Anrufen das gleichzeitige Läuten auf zusätzlichen Telefonen (z. B. einem Mobiltelefon) oder anderen Endpunktgeräten. Diese Option ist standardmäßig aktiviert.

  - **Teamanruf** ermöglicht Benutzern in einem definierten Team die Annahme von Anrufen für andere Teammitglieder. Diese Option ist standardmäßig aktiviert.

  - **PSTN-Umleitung** ermöglicht das Umleiten von Anrufen von Benutzern, denen diese Richtlinie zugewiesen wurde, an andere Benutzer im Unternehmen über das Festnetz, wenn das WAN überlastet oder nicht verfügbar ist. Diese Option ist standardmäßig aktiviert.

  - **Außerkraftsetzung der Bandbreitenrichtlinie** ermöglicht es Administratoren, Richtlinienentscheidungen im Rahmen der Anrufsteuerung für einen bestimmten Benutzer außer Kraft zu setzen. Diese Option ist standardmäßig deaktiviert.

  - **Nachverfolgung bei Missbrauch durch Anrufer** ermöglicht Benutzern das Melden missbräuchlicher Anrufe mithilfe des Lync-Clients, die anschließend in den Kommunikationsdatensätzen (KDS) gekennzeichnet werden. Diese Option ist standardmäßig deaktiviert.

  - **Voicemail-Ausweg** verhindert, dass Anrufe sofort an das Voicemail-System des Mobiltelefons des Benutzers weitergeleitet werden, wenn gleichzeitiges Klingeln konfiguriert und das Telefon abgeschaltet, ohne Strom oder außer Reichweite ist und auf einem Timer-Wert basiert. Diese Einstellung aktiviert und deaktiviert den Timer und stellt den Wert des Timers ein. Er kann nur durch Verwendung der Option Lync Server-Verwaltungsshell konfiguriert werden. Diese ist standardmäßig deaktiviert.

  - **PSTN-Verwendungen Anrufweiterleitung und Gleichzeitiges Klingeln** ermöglicht Administratoren, bei Anrufweiterleitung und gleichzeitigem Klingeln die gleiche PSTN-Verwendung wie für die VoIP-Richtlinie anzugeben, Anrufweiterleitung und gleichzeitiges Klingeln auf interne Lync-Benutzer zu beschränken oder eine benutzerdefinierte PSTN-Verwendung anzugeben, die sich von der PSTN-Verwendung der VoIP-Richtlinie unterscheidet. Standardmäßig wird für Anrufweiterleitung und gleichzeitiges Klingeln die gleiche PSTN-Verwendung verwendet, wie bei der VoIP-Richtlinie.

## PSTN-Verwendungsdatensätze

Jeder VoIP-Richtlinie muss mindestens ein PSTN-Verwendungsdatensatz zugeordnet sein. PSTN-Verwendungen können nur zum Zweck von Anrufweiterleitung und gleichzeitigem Klingeln einer VoIP-Richtlinie zugeordnet sein. Ausführliche Informationen zum Planen von PSTN-Verwendungsdatensätzen finden Sie unter [PSTN-Verwendungsdatensätze in Lync Server 2013](lync-server-2013-pstn-usage-records.md).


> [!NOTE]
> Die Reihenfolge der PSTN-Verwendungsdatensätze ist wichtig, da die Ausgangsroutingfunktion beim Zuordnen von Benutzern zu Routen die PSTN-Verwendungsdatensätze von oben nach unten vergleicht. Wenn der erste Datensatz mit der Anrufroute übereinstimmt, wird diese Route verwendet. Falls nicht, unterstützt die Ausgangsroutingfunktion den nächsten PSTN-Verwendungsdatensatz in der Liste und fährt damit fort, bis eine Übereinstimmung gefunden wird. Die nachfolgenden PSTN-Verwendungsdatensätze dienen der zusätzlichen Absicherung, wenn der erste Datensatz in der Liste nicht verfügbar ist.


