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
ms.openlocfilehash: b0320cb10e4122e5f5c42a659ad8de54ce3ae5b6
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42039159"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="moving-users-to-enterprise-voice-in-lync-server-2013"></a>Verschieben von Benutzern zu Enterprise-VoIP in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2012-10-18_

Wenn Sie Benutzer von einer vorhandenen PBX-Telefonie-Infrastruktur zu Enterprise-VoIP verschieben, enthält der Bereitstellungsprozess einige Schritte, die nicht Teil des Planungsprozesses sind, der bereits unter [Planning for Enterprise Voice in lync Server 2013](lync-server-2013-planning-for-enterprise-voice.md)beschrieben wurde. Informationen zur Migration von Benutzern aus einer früheren Enterprise-VoIP-Bereitstellung finden Sie in den Migrationsdokumenten, die den Installationsdatenträgern beiliegen.

Um Benutzer von einer vorhandenen Telefonieinfrastruktur zu Enterprise-VoIP zu migrieren, müssen Sie die folgenden Schritte ausführen:

1.  Festlegen primärer Rufnummern

2.  Aktivieren von Benutzern für Enterprise-VoIP

3.  Vorbereiten von Wähleinstellungen für Benutzer

4.  Planen von VoIP-Richtlinien für Benutzer

5.  Planen von Anrufrouten

6.  Konfigurieren der Nebenstellenanlage oder des SIP-Trunks zum Umleiten von Anrufen für Benutzer mit Enterprise-VoIP-Aktivierung

7.  Benutzer zu Exchange Unified Messaging (um) umstellen (empfohlen).

In diesem Thema wird beschrieben, welche Planungsaufgaben für jeden dieser Schritte erforderlich sind.

<div>

## <a name="step-1-designate-primary-phone-numbers"></a>Schritt 1: Festlegen primärer Rufnummern

Enterprise VoIP integriert die Sprachtelefonie mit anderen Messagingmedien. Wenn also ein Anruf am Server eingeht, ordnet der Server die Rufnummer dem SIP-URI des Benutzers zu und verzweigt den Anruf dann an alle Clientendpunkte, die diesem SIP-URI zugeordnet sind. Für diesen Prozess muss jedem Benutzer eine primäre Rufnummer zugeordnet sein.

Eine primäre Rufnummer muss folgende Eigenschaften aufweisen:

  - Sie muss global eindeutig oder (im Fall interner Durchwahlen) innerhalb des Unternehmens eindeutig sein.

  - Sie muss im Besitz des Unternehmens sein und innerhalb des Unternehmens weitergeleitet werden können. Persönliche Rufnummern sollten nicht verwendet werden.

Für Enterprise-Benutzer können in Active Directory-Domänendienste zwei oder mehr Telefonnummern aufgeführt sein. Alle Rufnummern, die einem bestimmten Benutzer zugeordnet sind, können auf der Eigenschaftenseite für diesen Benutzer im Snap-In "Active Directory-Benutzer und -Computer" angezeigt oder geändert werden.

Das Feld **Rufnummer** auf der Registerkarte **Allgemein** des Dialogfelds **Benutzereigenschaften** sollte die primäre geschäftliche Rufnummer des Benutzers enthalten. Diese Nummer wird normalerweise als primäre Rufnummer des Benutzers festgelegt.

Einige Benutzer stellen möglicherweise besondere Anforderungen (z. B. eine Führungskraft, für die alle eingehenden Anrufe über das Sekretariat weitergeleitet werden sollen). Solche Ausnahmen sollten jedoch auf Fälle beschränkt werden, in denen die Anforderung klar und wichtig ist.

Nach der Auswahl einer primären Rufnummer müssen folgende Aktionen für diese durchgeführt werden:

  - Normalisierung in das E.164-Format (wenn möglich)

  - Kopieren in das Active Directory-Attribut **msRTCSIP-line**
    
    <div>
    

    > [!NOTE]  
    > <STRONG>Verwendung neben der Remoteanrufsteuerung (Remote Call Control, RCC)</STRONG><BR>RCC ist die Möglichkeit, lync Server zum Überwachen und Steuern eines Desktop-PBX-Telefons zu verwenden. Die Steuerung wird über den Server geleitet, der als Gateway zur Nebenstellenanlage dient. Auch wenn Sie einen Benutzer nicht sowohl für RCC als auch für Enterprise-VoIP konfigurieren können, stellt die Einstellung für den Anschluss-URI in beiden Fällen die primäre Rufnummer eines Benutzers dar.<BR>Wenn Sie über eine vorhandene PBX-Infrastruktur verfügen, die bestimmte Benutzer weiterhin verwenden sollen, können Sie Enterprise-VoIP stufenweise in Ihrer Organisation einführen. Ausführliche Informationen zu diesem Bereitstellungsszenario finden Sie unter <A href="lync-server-2013-direct-sip-deployment-options.md">Direct SIP Deployment Options in lync Server 2013</A> in der Planungsdokumentation.<BR>In früheren Versionen konnten Sie sowohl RCC als auch Enterprise-VoIP für einen Benutzer aktivieren, allerdings nur, wenn Sie den Benutzer auch für die Duale Verzweigung konfiguriert haben, ein Feature, bei dem ein eingehender Anruf das Nebenstellentelefon und den Communicator eines Benutzers gleichzeitig klingelt. In lync Server 2010 wird die Duale Verzweigung nicht unterstützt.

    
    </div>

Das Attribut **msRTCSIP-line** kann auf drei Arten aufgefüllt werden:

  - Microsoft Identity Integration Server (empfohlen)

  - Die Seite " **Benutzer** " im lync Server-Systemsteuerung

Wenn viele Telefonnummern verarbeitet werden müssen, ist ein von Ihrer Organisation entwickeltes Skript die bessere Wahl. Abhängig davon, wie in Ihrer Organisation Rufnummern in den Active Directory-Domänendiensten (Active Directory Domain Services, AD DS) dargestellt werden, muss das Skript die primären Rufnummern möglicherweise in das E.164-Format übertragen, bevor es sie in das Attribut **msRTCSIP-line** kopiert.

  - Wenn in Ihrer Organisation alle Rufnummern in den Active Directory-Domänendiensten im E.164-Format verwaltet werden, muss Ihr Skript lediglich jede primäre Rufnummer in das Attribut **msRTCSIP-line** schreiben.

  - Wenn in Ihrer Organisation alle Rufnummern in den Active Directory-Domänendiensten in einem einzigen Format verwaltet werden, dieses Format jedoch nicht E.164 ist, muss Ihr Skript eine entsprechende Normalisierungsregel definieren, mit der primäre Rufnummern aus ihrem vorhandenen Format in E.164 konvertiert werden können, bevor sie in das Attribut **msRTCSIP-line** geschrieben werden.

  - Wenn Ihre Organisation kein Standardformat für Rufnummern in den Active Directory-Domänendiensten erzwingt, muss Ihr Skript geeignete Normalisierungsregeln definieren, mit denen primäre Rufnummern aus ihren unterschiedlichen Formaten in E.164 konvertiert werden können, bevor sie in das Attribut **msRTCSIP-line** geschrieben werden.

In Ihrem Skript muss außerdem das Präfix **Tel:** vor jeder primären Rufnummer eingefügt werden, bevor diese Nummern in das Attribut **msRTCSIP-line** geschrieben werden.

Folgendes Format wird für die in diesem Attribut angegebene Nummer erwartet:

  - Tel: + 14255550100 übersetzt; ext = 50100.

  - Tel:5550100 (für unternehmensweit eindeutige Durchwahlen)
    
    <div>
    

    > [!IMPORTANT]  
    > Trotz der vom Adressbuchdienst (Address Book Service, ABS) durchgeführten Normalisierung muss die primäre Rufnummer jedes Benutzers in den Active Directory-Domänendiensten normalisiert werden, da ABS über keinen Zugriff auf die Active Directory-Domänendienste verfügt und daher keine primären Rufnummern in das Attribut <STRONG>msRTCSIP-line</STRONG> kopieren kann.

    
    </div>

</div>

<div>

## <a name="step-2-enable-users-for-enterprise-voice"></a>Schritt 2: Aktivieren von Benutzern für Enterprise-VoIP

In diesem Schritt muss lediglich identifiziert werden, für welche Benutzer Enterprise-VoIP aktiviert werden soll. Es ist keine besondere Planung notwendig.

</div>

<div>

## <a name="step-3-prepare-dial-plans-for-users"></a>Schritt 3: Vorbereiten von Wähleinstellungen für Benutzer

Benutzer, die für Enterprise-VoIP aktiviert sind, können ohne festgelegte Wähleinstellungen keine Anrufe an das PSTN tätigen. Wähleinstellungen sind benannte Sätze aus Normalisierungsregeln, mit deren Hilfe Telefonnummern als Bestandteil der Telefonautorisierung und Anrufweiterleitung für einen benannten Standort, einzelne Benutzer oder Kontaktobjekte in ein einzelnes Standardformat (E.164) übersetzt werden. Normalisierungsregeln definieren das Routing von Rufnummern in unterschiedlichen Formaten für den benannten Standort, Benutzer oder das Kontaktobjekt.

Informationen zum Vorbereiten von Wählplänen finden Sie unter [Wählpläne und Normalisierungsregeln in lync Server 2013](lync-server-2013-dial-plans-and-normalization-rules.md).

</div>

<div>

## <a name="step-4-plan-user-voice-policies"></a>Schritt 4: Planen von Benutzer VoIP-Richtlinien

Einstellungen für Benutzerdienstklassen auf vorhandenen Nebenstellenanlagen (wie das Recht, Auslands- oder Ferngespräche von einem Unternehmenstelefon aus zu führen) müssen für Benutzer, die zu Enterprise-VoIP migriert werden, als VoIP-Richtlinien neu konfiguriert werden. Ausführliche Informationen zum Planen und Erstellen von Richtlinien für Enterprise-VoIP finden Sie unter [VoIP-Richtlinien in lync Server 2013](lync-server-2013-voice-policies.md).

</div>

<div>

## <a name="step-5-plan-outbound-call-routes"></a>Schritt 5: Planen von Routen für ausgehende Anrufe

Anrufrouten geben an, wie lync Server ausgehende Anrufe von Enterprise-VoIP-Benutzern abwickelt. Wenn ein Benutzer eine Nummer wählt, normalisiert der Server bei Bedarf die Wählzeichenfolge in das E. 164-Format und versucht, Sie einem SIP-URI zuzuordnen. Wenn der Server die Übereinstimmung nicht herstellen kann, wendet er die Routinglogik für ausgehende Anrufe basierend auf der Nummer an. Der letzte Schritt beim Definieren dieser Logik ist das Erstellen einer separaten benannten Anrufroute für jeden Satz von Zielrufnummern, die in den einzelnen Wähleinstellungen aufgeführt sind.

Ausführliche Informationen zum Planen von Anrufrouten finden Sie unter [VoIP-Routen in lync Server 2013](lync-server-2013-voice-routes.md).

</div>

<div>

## <a name="step-6-configure-pbx-or-sip-trunk-to-reroute-calls-for-enterprise-voice-users"></a>Schritt 6. Konfigurieren von PBX-oder SIP-Trunks für die Umleitung von Anrufen für Enterprise-VoIP-Benutzer

Benutzer, die früher in einer herkömmlichen Nebenstellenanlage oder einer SIP-Trunk Verbindung mit einem Internet Telefonie-Dienstanbieter (ITSP) gehostet wurden, behalten ihre Telefonnummern nach dem Wechsel bei. Die einzige Voraussetzung ist, dass nach dem Wechsel die Nebenstellenanlage oder der SIP-Trunk neu konfiguriert werden muss, um eingehende Anrufe für Enterprise-VoIP-Benutzer an die Vermittlungsserver weiterzuleiten.

</div>

<div>

## <a name="step-7-move-users-to-exchange-unified-messaging-recommended"></a>Schritt 7: Migrieren von Benutzern zu Exchange Unified Messaging (empfohlen)

Um Benutzer zu Exchange Unified Messaging zu migrieren, ist das Ausführen der folgenden Aufgaben erforderlich:

  - Konfigurieren von Exchange Unified Messaging und lync Server zur Zusammenarbeit.

  - Aktivieren von Exchange Unified Messaging-Mailboxansagen und Outlook Voice Access für Benutzer. Diese Aufgabe wird auf dem Exchange Unified Messaging-Server ausgeführt. Ausführliche Informationen finden Sie in [http://go.microsoft.com/fwlink/p/?linkID=139372](http://go.microsoft.com/fwlink/p/?linkid=139372)der Exchange Server 2010 TechNet-Bibliothek unter.

</div>

</div>

<span> </span>

</div>

</div>

</div>

