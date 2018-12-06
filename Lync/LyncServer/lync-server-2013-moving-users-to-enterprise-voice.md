---
title: 'Lync Server 2013: Verschieben von Benutzern zu Enterprise-VoIP'
TOCTitle: Verschieben von Benutzern zu Enterprise-VoIP
ms:assetid: a2df6d51-5cf2-4d3e-8f97-496af5fd5e5e
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg412758(v=OCS.15)
ms:contentKeyID: 49294957
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Verschieben von Benutzern zu Enterprise-VoIP in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2016-12-08_

Wenn Sie Benutzer aus einer vorhandenen PBX-Telefonieinfrastruktur nach Enterprise-VoIP verschieben, umfasst der Bereitstellungsprozess einige Schritte, die nicht zu dem bereits unter [Planen von Enterprise-VoIP in Lync Server 2013](lync-server-2013-planning-for-enterprise-voice.md) beschriebenen Planungsprozess gehören. Informationen zur Migration von Benutzern aus einer früheren Enterprise-VoIP-Bereitstellung finden Sie in den Migrationsdokumenten, die den Installationsdatenträgern beiliegen.

Um Benutzer von einer vorhandenen Telefonieinfrastruktur zu Enterprise-VoIP zu migrieren, müssen Sie die folgenden Schritte ausführen:

1.  Festlegen primärer Rufnummern

2.  Aktivieren von Benutzern für Enterprise-VoIP

3.  Vorbereiten von Wähleinstellungen für Benutzer

4.  Planen von VoIP-Richtlinien für Benutzer

5.  Planen von Anrufrouten

6.  Konfigurieren der Nebenstellenanlage oder des SIP-Trunks zum Umleiten von Anrufen für Benutzer mit Enterprise-VoIP-Aktivierung

7.  Migrieren von Benutzern zu Exchange Unified Messaging (UM) (empfohlen)

In diesem Thema wird beschrieben, welche Planungsaufgaben für jeden dieser Schritte erforderlich sind.

## Schritt 1: Festlegen primärer Rufnummern

Enterprise-VoIP integriert die Sprachtelefonie mit anderen Messagingmedien. Wenn also ein Anruf am Server eingeht, ordnet der Server die Rufnummer dem SIP-URI des Benutzers zu und verzweigt den Anruf dann an alle Clientendpunkte, die diesem SIP-URI zugeordnet sind. Für diesen Prozess muss jedem Benutzer eine primäre Rufnummer zugeordnet sein.

Eine primäre Rufnummer muss folgende Eigenschaften aufweisen:

  - Sie muss global eindeutig oder (im Fall interner Durchwahlen) innerhalb des Unternehmens eindeutig sein.

  - Sie muss im Besitz des Unternehmens sein und innerhalb des Unternehmens weitergeleitet werden können. Persönliche Rufnummern sollten nicht verwendet werden.

Für Unternehmensbenutzer können zwei oder mehr Rufnummern in Active Directory-Domänendiensteaufgeführt sein. Alle Rufnummern, die einem bestimmten Benutzer zugeordnet sind, können auf der Eigenschaftenseite für diesen Benutzer im Snap-In "Active Directory-Benutzer und -Computer" angezeigt oder geändert werden.

Das Feld **Rufnummer** auf der Registerkarte **Allgemein** des Dialogfelds **Benutzereigenschaften** sollte die primäre geschäftliche Rufnummer des Benutzers enthalten. Diese Nummer wird normalerweise als primäre Rufnummer des Benutzers festgelegt.

Einige Benutzer stellen möglicherweise besondere Anforderungen (z. B. eine Führungskraft, für die alle eingehenden Anrufe über das Sekretariat weitergeleitet werden sollen). Solche Ausnahmen sollten jedoch auf Fälle beschränkt werden, in denen die Anforderung klar und wichtig ist.

Nach der Auswahl einer primären Rufnummer müssen folgende Aktionen für diese durchgeführt werden:

  - Normalisierung in das E.164-Format (wenn möglich)

  - Kopieren in das Active Directory-Attribut **msRTCSIP-line**
    

    > [!NOTE]
    > <STRONG>Verwendung neben der Remoteanrufsteuerung (Remote Call Control, RCC)</STRONG><BR>RCC bietet die Möglichkeit, ein PBX-Telefon mit Lync Server zu überwachen und zu steuern. Die Steuerung wird über den Server geleitet, der als Gateway zur Nebenstellenanlage dient. Auch wenn Sie einen Benutzer nicht sowohl für RCC als auch für Enterprise-VoIP konfigurieren können, stellt die Einstellung für den Anschluss-URI in beiden Fällen die primäre Rufnummer eines Benutzers dar.<BR>Wenn Sie über eine vorhandene PBX-Infrastruktur verfügen, die bestimmte Benutzer weiterhin verwenden sollen, können Sie Enterprise-VoIP stufenweise in Ihrer Organisation einführen. Ausführliche Informationen zu diesem Bereitstellungsszenario finden Sie unter <A href="lync-server-2013-direct-sip-deployment-options.md">Optionen für Bereitstellungen mit direkten SIP-Verbindungen in Lync Server 2013</A> in der Planungsdokumentation.<BR>In vorherigen Versionen konnten Sie sowohl RCC als auch Enterprise-VoIP für einen Benutzer aktivieren. Hierzu mussten Sie den Benutzer jedoch auch für die duale Verzweigung konfigurieren, eine Funktion, bei der ein eingehender Anruf gleichzeitig am PBX-Telefon eines Benutzers und in Communicator klingelt. In Lync Server 2010 wird die duale Verzweigung nicht unterstützt.



Das Attribut **msRTCSIP-line** kann auf drei Arten aufgefüllt werden:

  - Microsoft Identity Integration Server (empfohlen)

  - Die Seite **Benutzer** in der Lync Server-Systemsteuerung

Wenn viele Rufnummern verarbeitet werden müssen, ist ein benutzerdefiniertes Skript, das von Ihrer Organisation entwickelt wurde, die bessere Wahl. Abhängig davon, wie in Ihrer Organisation Rufnummern in den Active Directory-Domänendiensten (Active Directory Domain Services, AD DS) dargestellt werden, muss das Skript die primären Rufnummern möglicherweise in das E.164-Format übertragen, bevor es sie in das Attribut **msRTCSIP-line** kopiert.

  - Wenn in Ihrer Organisation alle Rufnummern in den Active Directory-Domänendiensten im E.164-Format verwaltet werden, muss Ihr Skript lediglich jede primäre Rufnummer in das Attribut **msRTCSIP-line** schreiben.

  - Wenn in Ihrer Organisation alle Rufnummern in den Active Directory-Domänendiensten in einem einzigen Format verwaltet werden, dieses Format jedoch nicht E.164 ist, muss Ihr Skript eine entsprechende Normalisierungsregel definieren, mit der primäre Rufnummern aus ihrem vorhandenen Format in E.164 konvertiert werden können, bevor sie in das Attribut **msRTCSIP-line** geschrieben werden.

  - Wenn Ihre Organisation kein Standardformat für Rufnummern in den Active Directory-Domänendiensten erzwingt, muss Ihr Skript geeignete Normalisierungsregeln definieren, mit denen primäre Rufnummern aus ihren unterschiedlichen Formaten in E.164 konvertiert werden können, bevor sie in das Attribut **msRTCSIP-line** geschrieben werden.

In Ihrem Skript muss außerdem das Präfix **Tel:** vor jeder primären Rufnummer eingefügt werden, bevor diese Nummern in das Attribut **msRTCSIP-line** geschrieben werden.

Folgendes Format wird für die in diesem Attribut angegebene Nummer erwartet:

  - Tel:+14255550100;ext=50100.

  - Tel:5550100 (für unternehmensweit eindeutige Durchwahlen)
    

    > [!IMPORTANT]
    > Trotz der vom Adressbuchdienst (Address Book Service, ABS) durchgeführten Normalisierung muss die primäre Rufnummer jedes Benutzers in den Active Directory-Domänendiensten normalisiert werden, da ABS über keinen Zugriff auf die Active Directory-Domänendienste verfügt und daher keine primären Rufnummern in das Attribut <STRONG>msRTCSIP-line</STRONG> kopieren kann.



## Schritt 2: Aktivieren von Benutzern für Enterprise-VoIP

In diesem Schritt muss lediglich identifiziert werden, für welche Benutzer Enterprise-VoIP aktiviert werden soll. Es ist keine besondere Planung notwendig.

## Schritt 3: Vorbereiten von Wähleinstellungen für Benutzer

Benutzer, die für Enterprise-VoIP aktiviert sind, können ohne festgelegte Wähleinstellungen keine Anrufe an das PSTN tätigen. Wähleinstellungen sind benannte Sätze aus Normalisierungsregeln, mit deren Hilfe Telefonnummern als Bestandteil der Telefonautorisierung und Anrufweiterleitung für einen benannten Standort, einzelne Benutzer oder Kontaktobjekte in ein einzelnes Standardformat (E.164) übersetzt werden. Normalisierungsregeln definieren das Routing von Rufnummern in unterschiedlichen Formaten für den benannten Standort, Benutzer oder das Kontaktobjekt.

Informationen zur Vorbereitung von Wähleinstellungen finden Sie unter [Wählpläne und Normalisierungsregeln in Lync Server 2013](lync-server-2013-dial-plans-and-normalization-rules.md).

## Schritt 4: Planen von VoIP-Richtlinien für Benutzer

Einstellungen für Benutzerdienstklassen auf vorhandenen Nebenstellenanlagen (wie das Recht, Auslands- oder Ferngespräche von einem Unternehmenstelefon aus zu führen) müssen für Benutzer, die zu Enterprise-VoIP migriert werden, als VoIP-Richtlinien neu konfiguriert werden. Ausführliche Informationen zum Planen und Erstellen von Richtlinien für Enterprise-VoIP finden Sie unter [VoIP-Richtlinien in Lync Server 2013](lync-server-2013-voice-policies.md).

## Schritt 5: Planen der Routen für ausgehende Anrufe

Anrufrouten legen fest, wie Lync Server ausgehende Anrufe verarbeitet, die von Enterprise-VoIP-Benutzern getätigt werden. Wenn ein Benutzer eine Nummer wählt, normalisiert der Server die Wählzeichenfolge ggf. in das E.164-Format und versucht, sie einem SIP-URI zuzuordnen. Wenn keine Zuordnung möglich ist, wendet der Server eine auf der Nummer basierende Routinglogik für ausgehende Anrufe an. Der letzte Schritt zum Definieren der Logik besteht darin, eine separate benannte Anrufroute für jeden Satz von Zielrufnummern zu erstellen, die in den Wähleinstellungen aufgeführt sind.

Ausführliche Informationen zum Planen von Anrufrouten finden Sie unter [VoIP-Routen in Lync Server 2013](lync-server-2013-voice-routes.md).

## Schritt 6: Konfigurieren der Nebenstellenanlage oder des SIP-Trunks für die Umleitung von Anrufen für Enterprise-VoIP-Benutzer

Benutzer, die zuvor auf einer herkömmlichen Nebenstellenanlage oder einer SIP-Trunkverbindung mit einem Anbieter von Internettelefoniediensten gehostet wurden, behalten ihre Rufnummern nach der Verschiebung bei. Die einzige Anforderung besteht darin, dass die Nebenstellenanlage oder der SIP-Trunk nach der Verschiebung neu konfiguriert werden muss, damit eingehende Anrufe für Enterprise-VoIP-Benutzer an den Vermittlungsserver weitergeleitet werden.

## Schritt 7: Migrieren von Benutzern zu Exchange Unified Messaging (empfohlen)

Um Benutzer zu Exchange Unified Messaging zu migrieren, ist das Ausführen der folgenden Aufgaben erforderlich:

  - Konfigurieren von Exchange Unified Messaging und Lync Server für die Zusammenarbeit.

  - Aktivieren von Exchange Unified Messaging-Mailboxansagen und Outlook Voice Access für Benutzer. Diese Aufgabe wird auf dem Exchange Unified Messaging-Server ausgeführt. Ausführliche Informationen finden Sie in der Exchange Server 2010-TechNet-Bibliothek unter <http://go.microsoft.com/fwlink/?linkid=139372>.

