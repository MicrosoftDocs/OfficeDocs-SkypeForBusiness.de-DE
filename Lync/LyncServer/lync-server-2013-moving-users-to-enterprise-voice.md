---
title: 'Lync Server 2013: Verschieben von Benutzern zu Enterprise-VoIP'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Moving users to Enterprise Voice
ms:assetid: a2df6d51-5cf2-4d3e-8f97-496af5fd5e5e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412758(v=OCS.15)
ms:contentKeyID: 48184958
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e92f0a7d71d42d8551a51028afec209e795941d5
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41756689"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="moving-users-to-enterprise-voice-in-lync-server-2013"></a>Verschieben von Benutzern zu Enterprise-VoIP in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2012-10-18_

Wenn Sie Benutzer aus einer vorhandenen PBX-Telefonie-Infrastruktur in Enterprise-VoIP verschieben, enthält der Bereitstellungsprozess einige Schritte, die nicht Teil des Planungsprozesses sind, der in der [Planung für Enterprise-VoIP in lync Server 2013](lync-server-2013-planning-for-enterprise-voice.md)bereits beschrieben ist. Informationen zum Migrieren von Benutzern aus einer früheren Enterprise-VoIP-Bereitstellung finden Sie in den Migrations Dokumenten, die in Ihren Installationsmedien enthalten sind.

Der Vorgang zum Verschieben von Benutzern aus einer vorhandenen Telefonie-Infrastruktur in Enterprise-VoIP umfasst die folgenden Schritte:

1.  Primäre Telefonnummern festlegen

2.  Aktivieren von Benutzern für Enterprise-VoIP

3.  Vorbereiten von Wählplänen für Benutzer

4.  Planen von Benutzer VoIP-Richtlinien

5.  Planen Sie Anrufrouten.

6.  Konfigurieren Sie die Telefonanlage oder den SIP-Trunk, um Anrufe für für Enterprise-VoIP aktivierte Benutzer neu zu leiten.

7.  Verschieben von Benutzern in Exchange Unified Messaging (um) (empfohlen).

In diesem Thema wird die Planung beschrieben, die für jeden dieser Schritte erforderlich ist.

<div>

## <a name="step-1-designate-primary-phone-numbers"></a>Schritt 1: Festlegen von primären Telefonnummern

Enterprise-VoIP integriert Sprache mit anderen Nachrichtenmedien, so dass der Server die Nummer dem SIP-URI des Benutzers zuordnet und dann den Anruf an alle Clientendpunkte abzweigt, die diesem SIP-URI zugeordnet sind, wenn ein eingehender Anruf am Server eintrifft. Für diesen Vorgang muss jeder Benutzer einer primären Telefonnummer zugeordnet sein.

Eine primäre Telefonnummer muss sein:

  - Global eindeutig oder, im Fall interner Erweiterungen, eindeutig im Unternehmen.

  - Im Unternehmen im Besitz von und routingfähig. Persönliche Nummern sollten nicht verwendet werden.

Für Unternehmensbenutzer können in den Active Directory-Domänendiensten zwei oder mehr Telefonnummern aufgelistet sein. Alle Telefonnummern, die einem bestimmten Benutzer zugeordnet sind, können im Eigenschaftenfenster für diesen Benutzer im Snap-in Active Directory-Benutzer und-Computer angezeigt oder geändert werden.

Das Feld " **Telefonnummer** " auf der Registerkarte " **Allgemein** " im Dialogfeld " **Benutzereigenschaften** " sollte die Haupt Arbeitsnummer des Benutzers enthalten. Diese Nummer wird normalerweise als primäre Telefonnummer des Benutzers angegeben.

Einige Benutzer haben möglicherweise besondere Anforderungen (beispielsweise eine Führungskraft, die alle eingehenden Anrufe über einen administrativen Assistenten weiterleiten möchte), diese Ausnahmen sollten jedoch nur auf diejenigen begrenzt werden, in denen der Bedarf klar und kritisch ist.

Nachdem eine primäre Nummer ausgewählt wurde, muss Sie wie folgt lauten:

  - Im E. 164-Format normalisiert, wo immer dies möglich ist.

  - In das Active Directory **-Attribut msRTCSIP-** Attribut kopiert.
    
    <div>
    

    > [!NOTE]  
    > <STRONG>Mit Remoteanrufsteuerung (RCC) vorhanden</STRONG><BR>RCC ist die Möglichkeit, lync Server zum Überwachen und Steuern eines Desktop-PBX-Telefons zu verwenden. Die Steuerung wird über den Server weitergeleitet, der als Gateway zur Telefonanlage fungiert. Obwohl Sie keinen Benutzer für RCC und Enterprise-VoIP konfigurieren können, wird in beiden Fällen die Einstellung für den Leitungs-URI für die primäre Telefonnummer eines Benutzers bezeichnet.<BR>Wenn Sie über eine vorhandene PBX-Infrastruktur verfügen, die von ausgewählten Benutzern weiterhin verwendet werden soll, können Sie Enterprise-VoIP schrittweise in Ihre Organisation einführen. Details zu diesem Bereitstellungsszenario finden Sie unter <A href="lync-server-2013-direct-sip-deployment-options.md">direkte SIP-Bereitstellungsoptionen in lync Server 2013</A> in der Planungsdokumentation.<BR>In früheren Versionen konnten Sie sowohl RCC als auch Enterprise-VoIP für einen Benutzer aktivieren, jedoch nur, wenn Sie den Benutzer auch für die Duale Verzweigung konfiguriert haben, ein Feature, bei dem ein eingehender Anruf die Telefonanlage und den Communicator eines Benutzers gleichzeitig klingelt. In lync Server 2010 wird Dual-Forking nicht unterstützt.

    
    </div>

Es gibt drei Methoden zum Auffüllen des **Attribut msRTCSIP-** Attributs:

  - Microsoft Identity Integration Server (empfohlen)

  - Seite ' **Benutzer** ' in der lync Server-Systemsteuerung

Wo viele Telefonnummern verarbeitet werden müssen, ist ein von Ihrer Organisation entwickeltes benutzerdefiniertes Skript die bessere Wahl. Je nachdem, wie Ihre Organisation Telefonnummern in den Active Directory-Domänendiensten darstellt, muss das Skript die primären Telefonnummern möglicherweise im E. 164-Format normalisieren, bevor Sie Sie in das **Attribut msRTCSIP-** Attribut kopieren.

  - Wenn in Ihrer Organisation alle Telefonnummern in den Active Directory-Domänendiensten in einem einzigen Format verwaltet werden und das Format E. 164 ist, muss für Ihr Skript nur jede primäre Telefonnummer in das **Attribut msRTCSIP-** Attribut geschrieben werden.

  - Wenn in Ihrer Organisation alle Telefonnummern in den Active Directory-Domänendiensten in einem einzigen Format verwaltet werden, das Format aber nicht E. 164 ist, sollte Ihr Skript eine geeignete Normalisierungsregel definieren, um primäre Telefonnummern aus Ihrem vorhandenen Format in e. 164 zu konvertieren, bevor Sie Sie in das **Attribut msRTCSIP-** Attribut schreiben.

  - Wenn in Ihrer Organisation kein Standardformat für Telefonnummern in den Active Directory-Domänendiensten erzwungen wird, sollte Ihr Skript geeignete Normalisierungsregeln definieren, um primäre Telefonnummern aus ihren verschiedenen Formaten in die E. 164-Kompatibilität umzuwandeln, bevor die primären Telefonnummern in das **Attribut msRTCSIP-** Attribut geschrieben werden.

Ihr Skript muss auch das Präfix **Tel:** vor jeder primären Nummer einfügen, bevor es in das **Attribut msRTCSIP-** Attribut geschrieben wird.

Das erwartete Format der in diesem Attribut angegebenen Zahl lautet wie folgt:

  - Tel: + 14255550100 übersetzt.; ext = 50100.

  - Tel: 5550100 (für eindeutige Enterprise Wide-Erweiterungen)
    
    <div>
    

    > [!IMPORTANT]  
    > Die vom Adressbuchdienst (ABS) durchgeführte Normalisierung ersetzt nicht die Notwendigkeit, die primäre Telefonnummer jedes Benutzers in den Active Directory-Domänendiensten zu normalisieren, weil ABS keinen Zugriff auf die Active Directory-Domänendienste hat, und kann daher keine primär Nummern in das <STRONG>Attribut msRTCSIP-</STRONG> Attribut kopieren.

    
    </div>

</div>

<div>

## <a name="step-2-enable-users-for-enterprise-voice"></a>Schritt 2: Aktivieren von Benutzern für Enterprise-VoIP

Außer der Identifizierung, welche Benutzer aktiviert werden sollen, ist keine spezielle Planung erforderlich, um diesen Schritt ausführen zu können.

</div>

<div>

## <a name="step-3-prepare-dial-plans-for-users"></a>Schritt 3: Vorbereiten von Wählplänen für Benutzer

Benutzer, die für Enterprise-VoIP aktiviert sind, können keine Anrufe an das PSTN vornehmen, ohne dass Wählpläne vorhanden sind. Ein Wählplan ist ein benannter Satz von Normalisierungsregeln, mit deren Hilfe Telefonnummern als Bestandteil der Telefonautorisierung und Anrufweiterleitung für einen benannten Standort, für einzelne Benutzer oder für Kontaktobjekte in ein einzelnes Standardformat (E.164) übersetzt werden. Normalisierungsregeln definieren, wie Telefonnummern, die in verschiedenen Formaten ausgedrückt werden, für jeden angegebenen Speicherort, Benutzer oder Kontaktobjekt weitergeleitet werden sollen.

Informationen zum Vorbereiten von Wählplänen finden Sie unter [Wählpläne und Normalisierungsregeln in lync Server 2013](lync-server-2013-dial-plans-and-normalization-rules.md).

</div>

<div>

## <a name="step-4-plan-user-voice-policies"></a>Schritt 4: Planen von Richtlinien für Benutzer VoIP

Benutzer-Service-Einstellungen auf einer Legacy-Telefonanlage, wie etwa das Recht, Fern-oder Auslandsgespräche über Unternehmens Telefone zu führen, müssen als VoIP-Richtlinien für Benutzer neu konfiguriert werden, die in Enterprise-VoIP verschoben wurden. Details zum Planen und Erstellen von Richtlinien für Enterprise-VoIP finden Sie unter [VoIP-Richtlinien in lync Server 2013](lync-server-2013-voice-policies.md).

</div>

<div>

## <a name="step-5-plan-outbound-call-routes"></a>Schritt 5: Planen von ausgehenden Anrufrouten

Anrufrouten geben an, wie lync Server ausgehende Anrufe von Enterprise-VoIP-Benutzern abwickelt. Wenn ein Benutzer eine Nummer wählt, normalisiert der Server bei Bedarf die Wählzeichenfolge in das E. 164-Format und versucht, Sie mit einem SIP-URI zu vergleichen. Wenn der Server nicht in der Lage ist, die Übereinstimmung zu erreichen, wendet er die Routinglogik für ausgehende Anrufe basierend auf der Nummer an. Der letzte Schritt beim Definieren dieser Logik ist das Erstellen einer separaten benannten Anrufroute für jede Gruppe von Zielrufnummern, die in den einzelnen Wähleinstellungen aufgeführt sind.

Details zum Planen von Anrufrouten finden Sie unter [VoIP-Routen in lync Server 2013](lync-server-2013-voice-routes.md).

</div>

<div>

## <a name="step-6-configure-pbx-or-sip-trunk-to-reroute-calls-for-enterprise-voice-users"></a>Schritt 6: Konfigurieren von Telefonanlagen oder SIP-Stämmen zum Umleiten von Anrufen für Enterprise-VoIP-Benutzer

Benutzer, die früher in einer traditionellen Telefonanlage oder auf einer SIP-Trunk-Verbindung mit einem Internet-Telefoniedienstanbieter (ITSP) gehostet wurden, behalten ihre Telefonnummern nach dem Umzug. Die einzige Voraussetzung ist, dass nach dem Umzug die Telefonanlage oder der SIP-Stamm neu konfiguriert werden muss, um eingehende Anrufe an Enterprise-VoIP-Benutzer an den Vermittlungs Server weiterzuleiten.

</div>

<div>

## <a name="step-7-move-users-to-exchange-unified-messaging-recommended"></a>Schritt 7: Verschieben von Benutzern in Exchange Unified Messaging (empfohlen)

Das Verschieben von Benutzern in Exchange Unified Messaging umfasst die folgenden Aufgaben:

  - Konfigurieren Sie Exchange Unified Messaging und lync Server für die Zusammenarbeit.

  - Aktivieren von Benutzern für Exchange Unified Messaging-Anrufbeantwortung und Outlook Voice Access Diese Aufgabe wird auf dem Exchange Unified Messaging-Server ausgeführt. Ausführliche Informationen finden Sie in [http://go.microsoft.com/fwlink/p/?linkID=139372](http://go.microsoft.com/fwlink/p/?linkid=139372)der TechNet-Bibliothek für Exchange Server 2010 unter.

</div>

</div>

<span> </span>

</div>

</div>

</div>

